# RegistryKeyWatcher::Shutdown(void)

- ea: `0x180075618`
- end: `0x180075679`
- name: `?Shutdown@RegistryKeyWatcher@@QEAAXXZ`
- size: `97`
- prototype: `void __fastcall(RegistryKeyWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001f4cc`
- `0x18002404c`

## callees

- `0x180075618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007562c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007562c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075652`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075652`
- `RTWorkQ!RtwqCancelWorkItem` at `0x18007563b`
- `RTWorkQ!RtwqCancelWorkItem` at `0x18007563b`

## pseudocode

```c

```
