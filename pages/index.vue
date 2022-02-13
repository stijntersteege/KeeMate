<template>
  <div class="bg-blue-900">
    <div class="max-w-7xl mx-auto py-16 px-4 sm:py-24 sm:px-6 lg:px-8">
      <div class="text-center">
        <h2
          class="text-base font-semibold text-blue-400 tracking-wide uppercase"
        >
          KeeMate
        </h2>
        <p
          class="
            mt-1
            text-4xl
            font-extrabold
            text-white
            sm:text-5xl sm:tracking-tight
            lg:text-6xl
          "
        >
          Generate secure passwords easily.
        </p>
        <p class="max-w-xl mt-5 mx-auto text-xl text-blue-300">
          Select your desired complexity and hit the generate button to get your
          uniquely generated password.
        </p>
      </div>
    </div>
    <div class="max-w-3xl mx-auto pb-24">
      <div class="bg-white shadow sm:rounded-lg">
        <div class="px-4 py-5 sm:p-6">
          <h3 class="text-lg leading-6 font-medium text-gray-900">
            Password type
          </h3>
          <div class="mt-2 text-sm text-gray-500">
            <p>
              Select the type of password you want to generate. Then hit the
              generate button and copy your uniquely generated password by
              clicking the password field.
            </p>
          </div>

          <div class="py-5">
            <div class="space-y-2" role="none">
              <div
                v-on:click="updatePasswordType(1)"
                v-bind:class="{
                  'bg-blue-900 text-white': selectedPasswordType === 1,
                }"
                class="
                  relative
                  rounded-lg
                  shadow-md
                  px-5
                  py-4
                  cursor-pointer
                  flex
                  focus:outline-none
                "
              >
                <div class="flex items-center justify-between w-full">
                  <div class="flex items-center">
                    <div class="text-sm">
                      <p
                        v-bind:class="{
                          'text-white': selectedPasswordType === 1,
                        }"
                        class="font-medium"
                      >
                        Strong
                      </p>
                      <span
                        v-bind:class="{
                          'text-blue-100': selectedPasswordType === 1,
                        }"
                        class="inline text-gray-500"
                      ><span>16 Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Lowercase Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Uppercase Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Numbers</span>
                      </span>
                    </div>
                  </div>
                  <div
                    v-if="selectedPasswordType === 1"
                    class="flex-shrink-0 text-white"
                  >
                    <svg viewBox="0 0 24 24" fill="none" class="w-6 h-6">
                      <circle
                        cx="12"
                        cy="12"
                        r="12"
                        fill="#fff"
                        opacity="0.2"
                      ></circle>
                      <path
                        d="M7 13l3 3 7-7"
                        stroke="#fff"
                        stroke-width="1.5"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </div>
              </div>
              <div
                v-on:click="updatePasswordType(2)"
                v-bind:class="{
                  'bg-blue-900 text-white': selectedPasswordType === 2,
                }"
                class="
                  relative
                  rounded-lg
                  shadow-md
                  px-5
                  py-4
                  cursor-pointer
                  flex
                  focus:outline-none
                "
                tabindex="0"
              >
                <div class="flex items-center justify-between w-full">
                  <div class="flex items-center">
                    <div class="text-sm">
                      <p
                        v-bind:class="{
                          'text-white': selectedPasswordType === 2,
                        }"
                        class="font-medium"
                      >
                        Complex
                      </p>
                      <span
                        v-bind:class="{
                          'text-blue-100': selectedPasswordType === 2,
                        }"
                        class="inline text-gray-500">
                        <span>32 Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Lowercase Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Uppercase Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Numbers</span>
                        <span aria-hidden="true">·</span>
                        <span>Symbols (e.g. @!#$%)</span>
                      </span>
                    </div>
                  </div>
                  <div
                    v-if="selectedPasswordType === 2"
                    class="flex-shrink-0 text-white"
                  >
                    <svg viewBox="0 0 24 24" fill="none" class="w-6 h-6">
                      <circle
                        cx="12"
                        cy="12"
                        r="12"
                        fill="#fff"
                        opacity="0.2"
                      ></circle>
                      <path
                        d="M7 13l3 3 7-7"
                        stroke="#fff"
                        stroke-width="1.5"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </div>
              </div>
              <div
                v-on:click="updatePasswordType(3)"
                v-bind:class="{
                  'bg-blue-900 text-white': selectedPasswordType === 3,
                }"
                class="
                  relative
                  rounded-lg
                  shadow-md
                  px-5
                  py-4
                  cursor-pointer
                  flex
                  focus:outline-none
                "
                tabindex="0"
              >
                <div class="flex items-center justify-between w-full">
                  <div class="flex items-center">
                    <div class="text-sm">
                      <p
                        v-bind:class="{
                          'text-white': selectedPasswordType === 3,
                        }"
                        class="font-medium"
                      >
                        Extreme
                      </p>
                      <span
                        v-bind:class="{
                          'text-blue-100': selectedPasswordType === 3,
                        }"
                        class="inline text-gray-500"
                      ><span>64 Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Lowercase Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Uppercase Characters</span>
                        <span aria-hidden="true">·</span>
                        <span>Numbers</span>
                        <span aria-hidden="true">·</span>
                        <span>Symbols (e.g. @!#$%)</span>
                      </span>
                    </div>
                  </div>
                  <div
                    v-if="selectedPasswordType === 3"
                    class="flex-shrink-0 text-white">
                    <svg viewBox="0 0 24 24" fill="none" class="w-6 h-6">
                      <circle
                        cx="12"
                        cy="12"
                        r="12"
                        fill="#fff"
                        opacity="0.2"
                      ></circle>
                      <path
                        d="M7 13l3 3 7-7"
                        stroke="#fff"
                        stroke-width="1.5"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="relative mt-3">
            <button
              @click="generate()"
              type="button"
              class="
                inline-flex
                items-center
                px-4
                py-2
                border border-transparent
                shadow-sm
                font-medium
                rounded-md
                text-white
                bg-blue-900
                focus:outline-none
                focus:ring-2
                focus:ring-offset-2
                focus:ring-blue-900
                sm:text-sm
                w-full
              "
            >
              Generate Password
            </button>
          </div>

          <div @click="copy()" data-copy-state="copy" class="relative mt-3">
            <div
              class="
                flex
                absolute
                inset-y-0
                left-0
                items-center
                pl-3
                pointer-events-none
              "
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-500 dark:text-gray-400"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M8 16H6a2 2 0 01-2-2V6a2 2 0 012-2h8a2 2 0 012 2v2m-6 12h8a2 2 0 002-2v-8a2 2 0 00-2-2h-8a2 2 0 00-2 2v8a2 2 0 002 2z"
                />
              </svg>
            </div>
            <input
              type="text"
              v-on:focus="$event.target.select()"
              ref="password"
              class="
                cursor-pointer
                bg-gray-50
                border border-gray-300
                text-gray-900 text-sm
                rounded-lg
                focus:ring-blue-900 focus:border-blue-900
                block
                w-full
                pl-10
                p-2.5
                dark:bg-gray-700
                dark:border-gray-600
                dark:placeholder-gray-400
                dark:text-white
                dark:focus:ring-blue-900
                dark:focus:border-blue-900
              "
              placeholder="Your unique password will appear here"
              readonly
            />
          </div>
          <p v-if="passwordCopied" class="text-xs text-gray-500">
            Password has been copied to clipboard.
          </p>
        </div>
      </div>
    </div>
    <footer>
      <div
        class="
          max-w-7xl
          mx-auto
          py-12
          px-4
          sm:px-6
          md:flex md:items-center md:justify-between
          lg:px-8
        "
      >
        <div class="flex justify-center space-x-6 md:order-2">
          <a
            href="https://github.com/stijntersteege"
            class="text-blue-300 hover:text-blue-400"
          >
            <span class="sr-only">GitHub</span>
            <svg
              class="h-6 w-6"
              fill="currentColor"
              viewBox="0 0 24 24"
              aria-hidden="true"
            >
              <path
                fill-rule="evenodd"
                d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
                clip-rule="evenodd"
              />
            </svg>
          </a>
        </div>
        <div class="mt-8 md:mt-0 md:order-1">
          <p class="text-center text-base text-blue-300">
            &copy; 2022 Stijn ter Steege
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      selectedPasswordType: 1,
      passwordCopied: false,
    };
  },
  methods: {
    updatePasswordType(type) {
      this.selectedPasswordType = type;
    },
    generate() {
      this.passwordCopied = false;

      var chars =
        "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
      var symbols = "!@#$%^&*()";
      var passwordLength = 16;
      var password = "";

      if (this.selectedPasswordType === 2) {
        chars += symbols;
        passwordLength = 32;
      } else if (this.selectedPasswordType === 3) {
        chars += symbols;
        passwordLength = 64;
      }

      for (var i = 0; i <= passwordLength; i++) {
        var randomNumber = Math.floor(Math.random() * chars.length);
        password += chars.substring(randomNumber, randomNumber + 1);
      }

      this.$refs.password.value = password;
    },
    copy() {
      if (this.$refs.password.value !== "") {
        this.$refs.password.focus();
        document.execCommand("copy");
        this.passwordCopied = true;
        setTimeout(() => {
          this.passwordCopied = false;
        }, 3000);
      }
    },
  },
};
</script>
