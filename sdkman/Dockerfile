FROM openjdk:8-jre-alpine

# Install and configure sdkman
# https://sdkman.io/
ENV SDKMAN_DIR=/root/.sdkman

RUN apk add --no-cache --update ca-certificates bash curl zip unzip && \
    rm -rf /var/lib/apt/lists/* && \
    curl -s "https://get.sdkman.io" | bash && \
    echo "sdkman_auto_answer=true" > $SDKMAN_DIR/etc/config && \
    echo "sdkman_auto_selfupdate=false" >> $SDKMAN_DIR/etc/config && \
    bash -c "source ${SDKMAN_DIR}/bin/sdkman-init.sh && \
    sdk i maven && \
    sdk i kotlin && \
    sdk i kscript && \
    sdk flush archives && \
    sdk flush temp && \
    sdk offline"

ENTRYPOINT /bin/bash