## THIS PART IS MAINTAINED BY yuranos

### Adding datagen:
Run docker-compose first.
See config examples [here](https://github.com/confluentinc/kafka-connect-datagen/tree/master/config)

Configure connector with quickstart as described
[here](https://github.com/confluentinc/kafka-connect-datagen):

    curl -X POST -H "Content-Type: application/json" --data @users_conf.json http://localhost:8083/connectors

View logs:

    docker-compose logs connect-datagen

Check what's going on in Kafka:

    docker-compose exec kafka /bin/bash
    [appuser@kafka ~]$ kafka-run-class kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic users

Or:

    docker-compose exec connect-datagen kafka-console-consumer --topic users --bootstrap-server kafka:29092  --property print.key=true --max-messages 5 --from-beginning



[![Build Status](https://travis-ci.org/simplesteph/kafka-streams-course.svg?branch=master)](https://travis-ci.org/simplesteph/kafka-streams-course)

# Learning

This is a companion repository for my [**Kafka Streams course on Udemy**](https://links.datacumulus.com/kafka-streams-coupon)

Happy learning!

<p align="center">
    <a href="https://www.udemy.com/kafka-streams/?couponCode=GITHUB">
        <img src="http://i.imgur.com/YRJijb0.png" alt="Kafka Streams Course Logo"/>
    </a>
</p>

# Content

 - Starter project with dependencies
 - Word Count to learn the basic API
 - Favourite Colour for a more advanced example (`Scala` version included)
 - Bank Balance to demonstrate exactly once semantics
 - User Event matcher to learn about joins between `KStream` and `GlobalKTable`.
