# NegpIsUplevelDomain(_LUID *,_SECURITY_LOGON_TYPE,_UNICODE_STRING *)

- ea: `0x180088bb0`
- end: `0x180088d63`
- name: `?NegpIsUplevelDomain@@YA?AW4_NEG_DOMAIN_TYPES@@PEAU_LUID@@W4_SECURITY_LOGON_TYPE@@PEAU_UNICODE_STRING@@@Z`
- size: `435`
- prototype: `enum _NEG_DOMAIN_TYPES __high(struct _LUID *, enum _SECURITY_LOGON_TYPE, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009ac50`

## callees

- `0x180088bb0`
- `0x180088d6c`
- `0x1800d5218`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180088c4d`
- `ntdll!RtlLeaveCriticalSection` at `0x180088c63`
- `ntdll!RtlLeaveCriticalSection` at `0x180088c4d`
- `ntdll!RtlLeaveCriticalSection` at `0x180088c63`
- `ntdll!RtlEnterCriticalSection` at `0x180088c21`
- `ntdll!RtlEnterCriticalSection` at `0x180088c21`
- `ntdll!RtlEqualUnicodeString` at `0x180088bf0`
- `ntdll!RtlEqualUnicodeString` at `0x180088c3a`
- `ntdll!RtlEqualUnicodeString` at `0x180088cbc`
- `ntdll!RtlEqualUnicodeString` at `0x180088bf0`
- `ntdll!RtlEqualUnicodeString` at `0x180088c3a`
- `ntdll!RtlEqualUnicodeString` at `0x180088cbc`
- `ntdll!RtlInitUnicodeString` at `0x180088ca5`
- `ntdll!RtlInitUnicodeString` at `0x180088ca5`
- `logoncli!DsGetDcNameW` at `0x180088d1b`
- `logoncli!DsGetDcNameW` at `0x180088d1b`
- `netutils!NetApiBufferFree` at `0x180088d30`
- `netutils!NetApiBufferFree` at `0x180088d30`

## pseudocode

```c

```
