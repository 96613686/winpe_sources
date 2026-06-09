# LsaDbpLocateBindingCacheEntry(_UNICODE_STRING *,uchar)

- ea: `0x1800166a4`
- end: `0x180016738`
- name: `?LsaDbpLocateBindingCacheEntry@@YAPEAU_LSAP_BINDING_CACHE_ENTRY@@PEAU_UNICODE_STRING@@E@Z`
- size: `148`
- prototype: `struct _LSAP_BINDING_CACHE_ENTRY *__fastcall(PCUNICODE_STRING String2, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800164a8`
- `0x18001aa00`

## callees

- `0x1800166a4`
- `0x180016740`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x18001670c`
- `ntdll!NtQuerySystemTime` at `0x18001670c`
- `ntdll!RtlLeaveCriticalSection` at `0x180016722`
- `ntdll!RtlLeaveCriticalSection` at `0x180016722`
- `ntdll!RtlEnterCriticalSection` at `0x1800166c3`
- `ntdll!RtlEnterCriticalSection` at `0x1800166c3`
- `ntdll!RtlEqualUnicodeString` at `0x1800166e6`
- `ntdll!RtlEqualUnicodeString` at `0x1800166e6`

## pseudocode

```c

```
