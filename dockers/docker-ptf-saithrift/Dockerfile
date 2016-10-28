FROM docker-ptf

RUN apt-get update

COPY ["deps/saithrift-0.9.tar.gz", "/deps/"]

COPY ["deps/SAI/test/saithrift/tests/*", "/usr/share/ptf-tests/"]

RUN tar xzf /deps/saithrift-0.9.tar.gz -C /usr/share/; \
    cd usr/share/saithrift-0.9;   \
    python setup.py install;      \
    rm -rf /deps

ENTRYPOINT ["/usr/bin/ptf", "--test-dir", "/usr/share/ptf-tests"]
