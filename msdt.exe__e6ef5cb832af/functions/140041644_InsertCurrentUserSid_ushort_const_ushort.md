# InsertCurrentUserSid(ushort const *,ushort * *)

- ea: `0x140041644`
- end: `0x140041753`
- name: `?InsertCurrentUserSid@@YAJPEBGPEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400409b8`

## callees

- `0x1400070b0`
- `0x140020420`
- `0x140041150`
- `0x140041644`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14004168d`
- `KERNEL32!HeapAlloc` at `0x14004168d`
- `KERNEL32!HeapFree` at `0x14004173b`
- `KERNEL32!HeapFree` at `0x14004173b`
- `KERNEL32!GetProcessHeap` at `0x140041676`
- `KERNEL32!GetProcessHeap` at `0x140041727`
- `KERNEL32!GetProcessHeap` at `0x140041676`
- `KERNEL32!GetProcessHeap` at `0x140041727`
- `KERNEL32!LocalFree` at `0x140041716`
- `KERNEL32!LocalFree` at `0x140041716`
- `OLEAUT32!__imp_SysAllocString` at `0x1400416cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1400416cf`

## string_xrefs

- `0x1400416f0`: `InsertCurrentUserSid`

## pseudocode

```c

```
