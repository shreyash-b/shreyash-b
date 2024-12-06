<p id="introducing-rainmaker-rs-rust-implementation-of-the-esp-rainmaker-agent">We're super excited to share a project we've been working on since some time: rainmaker-rs, the Rust implementation of the ESP RainMaker agent! If you love Rust and you're passionate about IoT, we're pretty sure you'll love this.</p>


<h1 id="what-is-esp-rainmaker">What is ESP-RainMaker?</h1>


<p>ESP-RainMaker is an end-to-end IoT home automation solution developed by Espressif Systems. It allows hobbyists and developers to quickly write firmware applications for the ESP32 series of microcontrollers, such that it can be quickly controlled through phone applications or through voice commands (Alexa, Google Assistant).</p>


<p>It consists of the RainMaker agent, primarily aimed at running on ESP32 series of microcontrollers, Phone applications (iOS/Android) and a serverless cloud backend. You can learn more about ESP-RainMaker on their website over <a href="rainmaker.espressif.com">here</a></p>


<h1 id="why-rainmaker-rs">Why rainmaker-rs?</h1>


<p>Well, because why not?
Rust is being explored and gradually adopted as a memory safe alternative to low level languages such as C and C++. Rust is especially helpful for writing memory safe code while working on low level applications such as kernel development and embedded systems. As engineering students, working on rainmaker-rs served as a great means for us to get our hands wet working on Rust as well as assessing the state of embedded Rust. Moreover we aim to support running the RainMaker agent on Linux devices as well, which can greatly increase the number of applications in the RainMaker ecosystem as well as make development and testing cycle of firmware much quicker.</p>


<p>Now that the project is at a state where it can be used and evaluated by other developers, we would like to invite the Rust and overall IoT and Embedded Devices community to try out out this crate and provide us with valuable feedback.</p>


<h1 id="poc-a-smart-lightbulb-running-on-rainmaker-rs">POC: A smart lightbulb running on rainmaker-rs</h1>


<p>Here's a Proof-of-Concept LightBulb controled using rainmaker-rs running on a ESP8685.<br>It also contains the OTA component(not yet merged into main) which allows it's firmware to be updated remotely. <br><br></p>


<figure><img src="https://cdn.hackaday.io/images/5473011733496016256.png" data-image="1733496016931"></figure>


<p>Console logs(captured by running the same firmware on a ESP32C3 devkit)<br></p>


<figure><img src="https://cdn.hackaday.io/images/60071733495865118.png" data-image="1733495865740"></figure>


<p>


</p>


<h1 id="project-overview">Project Overview</h1>


<h4 id="what-is-currently-implemented">What is currently implemented</h4>


<ul>
<li>WiFi Provisioning*: <br>Providing WiFi for a new device. No need to hardcode WiFi credentials!</li>
<li>Remote Control: <br>Controlling Devices connected to a node over internet using phone application.</li>
<li>User Node Association: <br>Associating a specific node to a user account for control.</li>
<li>Device sharing: <br>Share access to a device with multiple members.</li>
<li>Contol using Home Assistants: <br>RainMaker devices can be added to and controlled using Amazon Alexa / Google Home. More details <a href="https://rainmaker.espressif.com/docs/3rd-party#enabling-alexa">here</a></li>
</ul>


<p>* Currently only supported on ESP32, not on Linux</p>


<h4 id="work-in-progress">Work in progress:</h4>


<ul>
<li>OTA: <br>Supports remotely updating firmware over internet for bugfix / adding new features</li>
<li>Local Control: <br>Supports remotely updating firmware over internet for bugfix / adding new features</li>
<li>Assisted claiming: <br>Enables device claiming directly using the phone applicaton in the provisioning workflow. <br>More details <a href="https://rainmaker.espressif.com/docs/claiming#assisted-claiming">here</a></li>
</ul>


<h2 id="getting-started">Getting Started</h2>


<p>You can head over to the <a href="https://github.com/rainmaker-rs/rainmaker">GitHub Repo</a> to learn more about the framework and try out examples.</p>


<p>Alternatively if you are feeling daring today, you can start developing an application by creating a new project.</p>


<ul>
<li>Make sure you have <a href="https://github.com/rainmaker-rs/rainmaker/blob/main/docs/PREREQUISITES.md">pre-requisites</a> installed.</li>
<li>Install <em>cargo-generate<pre data-language="bash" class="hljs bash"><span class="hljs-attribute">cargo</span> install cargo-generate</pre></em></li><li>Initialize the project using template<br><pre data-language="bash" class="hljs bash"><span class="hljs-attribute">cargo</span> generate rainmaker-rs/templat</pre></li></ul>


<p>You can read more about the generated template <a href="https://github.com/rainmaker-rs/template">here</a></p>


<hr>


<p>If you encounter any issue or have any suggestion, Issues/PR are always welcome.</p>


<p>Looking forward to see y'all on GitHub <br>Happy coding!</p>
