# [thunk]:CDSLink::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180010090`
- end: `0x180010099`
- name: `?QueryInterface@CDSLink@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ffe0`

## pseudocode

```c
__int64 __fastcall CDSLink::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CDSLink::QueryInterface((CDSLink *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180010090  sub     rcx, 8; this
0x180010094  jmp     ?QueryInterface@CDSLink@@UEAAJAEBU_GUID@@PEAPEAX@Z; CDSLink::QueryInterface(_GUID const &,void * *)
```
