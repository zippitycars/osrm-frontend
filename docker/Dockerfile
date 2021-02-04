FROM alpine:3.5

# Enables customized options using environment variables
ENV OSRM_BACKEND='https://osrm-4x.zippity.cc'
ENV OSRM_CENTER='42.357266,-71.0603766'
ENV OSRM_ZOOM='13'
ENV OSRM_LANGUAGE='en'
ENV OSRM_LABEL='Car (fastest)'

# Copy package.json
RUN mkdir -p /src
COPY package.json /src

# Install app dependencies
RUN apk add --no-cache sed nodejs && \
    cd /src && \
    npm install

# Create app directory
COPY . /src
WORKDIR /src

# Run App
EXPOSE 9966
CMD ["npm", "start"]
