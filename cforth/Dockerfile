FROM debian 
RUN mkdir /src
VOLUME /src
WORKDIR /src
RUN apt-get update -q \
  && DEBIAN_FRONTEND=noninteractive \
  apt-get install -qy automake libtool libtool-bin gcc make git \
  && apt-get clean \
  && rm -rf /var/lib/apt
WORKDIR /
RUN git clone https://github.com/MitchBradley/cforth.git
WORKDIR /cforth/build/host-serial-linux64
RUN make 
#WORKDIR /src
ENTRYPOINT ["/cforth/build/host-serial-linux64/forth"]
