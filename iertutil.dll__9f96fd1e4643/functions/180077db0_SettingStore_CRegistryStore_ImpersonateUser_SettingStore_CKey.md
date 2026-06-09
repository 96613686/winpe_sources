# SettingStore::CRegistryStore::ImpersonateUser(SettingStore::CKey *)

- ea: `0x180077db0`
- end: `0x180077e47`
- name: `?ImpersonateUser@CRegistryStore@SettingStore@@UEAAJPEAVCKey@2@@Z`
- size: `151`
- prototype: `int(SettingStore::CRegistryStore *__hidden this, struct SettingStore::CKey *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800750a0`

## callees

- `0x180077db0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077e02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077e02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077dd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077dd1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180077e1a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180077e1a`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180077de0`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180077de0`

## pseudocode

```c

```
