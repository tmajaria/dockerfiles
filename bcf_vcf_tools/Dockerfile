FROM ubuntu:xenial

MAINTAINER Tim Majarian <tmajaria@broadinstitute.org>

RUN apt-get update && apt-get install -y wget lbzip2 gcc libz-dev libbz2-dev liblzma-dev make g++ pkg-config

RUN wget https://github.com/samtools/bcftools/releases/download/1.9/bcftools-1.9.tar.bz2 && \
	tar -xf bcftools-1.9.tar.bz2 && \
	rm bcftools-1.9.tar.bz2 && \
	cd bcftools-1.9 && \
	./configure --prefix=/home && \
	make && \
	make install && \
	cd ..

RUN wget https://github.com/vcftools/vcftools/releases/download/v0.1.16/vcftools-0.1.16.tar.gz && \
	tar -xf vcftools-0.1.16.tar.gz && \
	rm vcftools-0.1.16.tar.gz && \
	cd vcftools-0.1.16 && \
	./configure --prefix=/home && \
	make && \
	make install && \
	cd ..

RUN wget https://github.com/samtools/htslib/releases/download/1.9/htslib-1.9.tar.bz2 && \
	tar -xf htslib-1.9.tar.bz2 && \
	rm htslib-1.9.tar.bz2 && \
	cd htslib-1.9 && \
	./configure --prefix=/home && \
	make && \
	make install 

ENV PATH="/home/bin:${PATH}"
