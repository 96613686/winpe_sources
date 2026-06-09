# CPolicyValueHandler::CSettings::Refresh(void)

- ea: `0x18001e5b4`
- end: `0x18001e9e6`
- name: `?Refresh@CSettings@CPolicyValueHandler@@QEAAJXZ`
- size: `1074`
- prototype: `__int64 __fastcall(CPolicyValueHandler::CSettings *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005f514`

## callees

- `0x18001e5b4`
- `0x18001e9ec`
- `0x18001edf0`
- `0x18002594c`
- `0x18002b2ac`
- `0x18002f10c`
- `0x180036394`
- `0x180039204`
- `0x180039610`
- `0x18003c460`
- `0x18003c5ec`
- `0x18003c698`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18001e7ff`
- `ntdll!RtlAcquireResourceShared` at `0x18001e7ff`
- `ntdll!RtlReleaseResource` at `0x18001e82d`
- `ntdll!RtlReleaseResource` at `0x18001e82d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e6d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e6d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e6ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e6ea`
- `OLEAUT32!__imp_VariantClear` at `0x18001e711`
- `OLEAUT32!__imp_VariantClear` at `0x18001e8b2`
- `OLEAUT32!__imp_VariantClear` at `0x18001e711`
- `OLEAUT32!__imp_VariantClear` at `0x18001e8b2`
- `USERENV!LeaveCriticalPolicySection` at `0x18001e988`
- `USERENV!LeaveCriticalPolicySection` at `0x18001e988`
- `USERENV!EnterCriticalPolicySection` at `0x18001e64e`
- `USERENV!EnterCriticalPolicySection` at `0x18001e64e`
- `KERNEL32!lstrcmpiW` at `0x18001e742`
- `KERNEL32!lstrcmpiW` at `0x18001e742`

## string_xrefs

- `0x18001e87f`: `Computer`
- `0x18001e8f1`: `Computer`

## pseudocode

```c

```
