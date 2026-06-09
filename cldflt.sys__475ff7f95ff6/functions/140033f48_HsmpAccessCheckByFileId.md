# HsmpAccessCheckByFileId

- ea: `0x140033f48`
- end: `0x140033ffc`
- name: `HsmpAccessCheckByFileId`
- size: `180`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14007e674`

## callees

- `0x140003c50`
- `0x140033f48`
- `0x1400503a0`
- `0x14005e76c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140033fcc`
- `ntoskrnl!ObfDereferenceObject` at `0x140033fcc`
- `FLTMGR!FltClose` at `0x140033fe2`
- `FLTMGR!FltClose` at `0x140033fe2`

## pseudocode

```c

```
