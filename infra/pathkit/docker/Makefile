EMSDK_VERSION=1.38.16_v1

# Can check CHROME_VERSION with
# docker run karma-chrome-tests /usr/bin/google-chrome-stable --version
CHROME_VERSION=68.0.3440.106_v5

publish_emsdk_base:
	docker build --no-cache -t emsdk-base ./emsdk-base/
	docker tag emsdk-base gcr.io/skia-public/emsdk-release:${EMSDK_VERSION}
	docker push gcr.io/skia-public/emsdk-release:${EMSDK_VERSION}
	docker tag emsdk-base gcr.io/skia-public/emsdk-release:prod
	docker push gcr.io/skia-public/emsdk-release:prod

publish_karma_chrome_tests:
	docker build --no-cache -t karma-chrome-tests ./karma-chrome-tests/
	docker tag karma-chrome-tests gcr.io/skia-public/karma-chrome-tests:${CHROME_VERSION}
	docker push gcr.io/skia-public/karma-chrome-tests:${CHROME_VERSION}

