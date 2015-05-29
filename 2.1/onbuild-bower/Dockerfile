FROM yyolk/docker-iojs-graphicsmagick:2.1.0

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY package.json /usr/src/app/
ONBUILD RUN npm install
ONBUILD COPY bower.json /usr/src/app/
ONBUILD ENV PATH node_modules/.bin:$PATH
ONBUILD RUN bower install --allow-root --production
ONBUILD COPY . /usr/src/app

CMD [ "npm", "start" ]
