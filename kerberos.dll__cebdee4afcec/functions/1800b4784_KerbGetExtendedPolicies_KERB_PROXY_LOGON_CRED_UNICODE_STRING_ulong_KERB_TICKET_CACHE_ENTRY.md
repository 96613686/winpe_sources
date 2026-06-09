# KerbGetExtendedPolicies(_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x1800b4784`
- end: `0x1800b4cb7`
- name: `?KerbGetExtendedPolicies@@YAJPEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `1331`
- prototype: `__int64 __fastcall(struct _KERB_PROXY_LOGON_CRED *, struct _UNICODE_STRING *, int, struct _KERB_TICKET_CACHE_ENTRY **)`
- caller_count: `3`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callers

- `0x180019678`
- `0x180042a40`
- `0x1800b4df0`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x180010e90`
- `0x1800190c0`
- `0x180029f10`
- `0x18002f8b0`
- `0x18006b558`
- `0x18006cb94`
- `0x18008a304`
- `0x18008b70c`
- `0x1800b46c0`
- `0x1800b4784`
- `0x1800b4d10`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800b4824`
- `ntdll!RtlEqualUnicodeString` at `0x1800b487b`
- `ntdll!RtlEqualUnicodeString` at `0x1800b4897`
- `ntdll!RtlEqualUnicodeString` at `0x1800b4bec`
- `ntdll!RtlEqualUnicodeString` at `0x1800b4824`
- `ntdll!RtlEqualUnicodeString` at `0x1800b487b`
- `ntdll!RtlEqualUnicodeString` at `0x1800b4897`
- `ntdll!RtlEqualUnicodeString` at `0x1800b4bec`
- `ntdll!RtlInitUnicodeString` at `0x1800b4814`
- `ntdll!RtlInitUnicodeString` at `0x1800b4814`
- `ntdll!RtlReleaseResource` at `0x1800b48aa`
- `ntdll!RtlReleaseResource` at `0x1800b48e4`
- `ntdll!RtlReleaseResource` at `0x1800b48aa`
- `ntdll!RtlReleaseResource` at `0x1800b48e4`
- `ntdll!RtlAcquireResourceShared` at `0x1800b4868`
- `ntdll!RtlAcquireResourceShared` at `0x1800b48c5`
- `ntdll!RtlAcquireResourceShared` at `0x1800b4868`
- `ntdll!RtlAcquireResourceShared` at `0x1800b48c5`

## string_xrefs

- `0x1800b494f`: `probed domain %wZ, detect no trust from cache\n`
- `0x1800b49ae`: `Failed to build krbtgt service principal to probe domain %wZ: %#x, Status %#x\n`
- `0x1800b4b66`: `Failed to create a domain cache entry for %wZ with no trust: %#x\n`
- `0x1800b4c15`: `Failed to create a domain cache entry with dns domain: %#x\n`

## pseudocode

```c

```
