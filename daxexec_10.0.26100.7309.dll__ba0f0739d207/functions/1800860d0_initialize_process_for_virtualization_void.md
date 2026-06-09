# initialize_process_for_virtualization(void)

- ea: `0x1800860d0`
- end: `0x1800861a9`
- name: `?initialize_process_for_virtualization@@YAXXZ`
- size: `217`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007a790`
- `0x18008deec`

## callees

- `0x1800091f8`
- `0x1800202bc`
- `0x18002031c`
- `0x1800860d0`
- `0x18008b400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800860ff`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800860ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180086168`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180086168`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800860ef`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800860ef`
- `api-ms-win-core-fibers-l1-1-0!FlsAlloc` at `0x180086136`
- `api-ms-win-core-fibers-l1-1-0!FlsAlloc` at `0x180086136`

## string_xrefs

- `0x180086185`: `onecore\base\appmodel\execmodel\desktopappx\libjitv\thread_state.cpp`
- `0x180086197`: `onecore\base\appmodel\execmodel\desktopappx\libjitv\thread_state.cpp`

## pseudocode

```c

```
