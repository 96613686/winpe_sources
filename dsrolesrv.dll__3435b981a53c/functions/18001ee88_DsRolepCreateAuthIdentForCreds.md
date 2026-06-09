# DsRolepCreateAuthIdentForCreds

- ea: `0x18001ee88`
- end: `0x18001f040`
- name: `DsRolepCreateAuthIdentForCreds`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, PVOID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800100c0`
- `0x180016d54`
- `0x180017890`
- `0x180020084`

## callees

- `0x180008fd4`
- `0x1800150a8`
- `0x18001ee88`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001ef87`
- `msvcrt!wcsstr` at `0x18001ef87`
- `ntdll!RtlAllocateHeap` at `0x18001eec2`
- `ntdll!RtlAllocateHeap` at `0x18001ef5d`
- `ntdll!RtlAllocateHeap` at `0x18001eec2`
- `ntdll!RtlAllocateHeap` at `0x18001ef5d`
- `ntdll!RtlFreeHeap` at `0x18001eeef`
- `ntdll!RtlFreeHeap` at `0x18001ef0f`
- `ntdll!RtlFreeHeap` at `0x18001eeef`
- `ntdll!RtlFreeHeap` at `0x18001ef0f`

## pseudocode

```c

```
