# MetInsertCurrentUserSid(ushort const *,ushort * *)

- ea: `0x140057158`
- end: `0x140057267`
- name: `?MetInsertCurrentUserSid@@YAJPEBGPEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140056c70`

## callees

- `0x1400070b0`
- `0x140020420`
- `0x140056efc`
- `0x140057158`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400571a1`
- `KERNEL32!HeapAlloc` at `0x1400571a1`
- `KERNEL32!HeapFree` at `0x14005724f`
- `KERNEL32!HeapFree` at `0x14005724f`
- `KERNEL32!GetProcessHeap` at `0x14005718a`
- `KERNEL32!GetProcessHeap` at `0x14005723b`
- `KERNEL32!GetProcessHeap` at `0x14005718a`
- `KERNEL32!GetProcessHeap` at `0x14005723b`
- `KERNEL32!LocalFree` at `0x14005722a`
- `KERNEL32!LocalFree` at `0x14005722a`
- `OLEAUT32!__imp_SysAllocString` at `0x1400571e3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400571e3`

## string_xrefs

- `0x140057204`: `MetInsertCurrentUserSid`

## pseudocode

```c

```
