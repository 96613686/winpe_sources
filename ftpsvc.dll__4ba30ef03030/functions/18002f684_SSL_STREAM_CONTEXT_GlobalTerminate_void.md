# SSL_STREAM_CONTEXT::GlobalTerminate(void)

- ea: `0x18002f684`
- end: `0x18002f786`
- name: `?GlobalTerminate@SSL_STREAM_CONTEXT@@SAXXZ`
- size: `258`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004a18`
- `0x18002f540`

## callees

- `0x180001250`
- `0x18002f684`
- `0x180030818`
- `0x180030b18`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002f6da`
- `KERNEL32!SetEvent` at `0x18002f6da`
- `KERNEL32!WaitForSingleObject` at `0x18002f6ea`
- `KERNEL32!WaitForSingleObject` at `0x18002f6ea`
- `KERNEL32!CloseHandle` at `0x18002f6f7`
- `KERNEL32!CloseHandle` at `0x18002f6f7`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18002f6a6`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18002f6b8`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18002f6a6`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18002f6b8`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18002f73a`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18002f73a`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18002f762`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18002f762`

## pseudocode

```c

```
