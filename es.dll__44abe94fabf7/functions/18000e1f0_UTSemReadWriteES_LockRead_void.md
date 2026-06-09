# UTSemReadWriteES::LockRead(void)

- ea: `0x18000e1f0`
- end: `0x18000e2ed`
- name: `?LockRead@UTSemReadWriteES@@QEAAXXZ`
- size: `253`
- prototype: `void __fastcall(UTSemReadWriteES *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000dc70`
- `0x18000e330`
- `0x18001cb30`
- `0x180024ac0`
- `0x1800254b4`
- `0x180025870`
- `0x180040330`

## callees

- `0x18000e1f0`
- `0x180012654`
- `0x180029130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e2e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e2e2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e288`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e2a6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e288`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e2a6`

## string_xrefs

- `0x18000e249`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000e269`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000e23d`: `(m_dwFlag & READERS_MASK) != 0`
- `0x18000e25d`: `(m_dwFlag & WRITERS_MASK) == 0`

## pseudocode

```c

```
