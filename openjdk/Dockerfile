FROM ubuntu:18.04
ENV JAVA_HOME /opt/openjdk-14
ENV PATH $JAVA_HOME/bin:$PATH

# https://jdk.java.net/
ENV OPENJDK_VERSION 14-ea+12
ENV JAVA_URL https://download.java.net/java/early_access/jdk14/12/GPL/openjdk-14-ea+12_linux-x64_bin.tar.gz

RUN set -eux; \
	\
	wget -O /tmp/openjdk-"$OPENJDK_VERSION"_linux-x64_bin.tar.gz "$JAVA_URL"; \
	mkdir -p "$JAVA_HOME"; \
	tar --extract --file /tmp/openjdk-"$OPENJDK_VERSION"_linux-x64_bin.tar.gz --directory "$JAVA_HOME" --strip-components 1; \
	rm -f /tmp/openjdk-"$OPENJDK_VERSION"_linux-x64_bin.tar.gz; \
	\
# basic smoke test
	java --version; \
	javac --version

CMD ["jshell"]
