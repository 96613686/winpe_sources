# [thunk]:CCompileProgressNotification::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x14000a040`
- end: `0x14000a049`
- name: `?QueryInterface@CCompileProgressNotification@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007270`

## pseudocode

```c
__int64 __fastcall CCompileProgressNotification::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CCompileProgressNotification::QueryInterface((CCompileProgressNotification *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x14000a040  sub     rcx, 8; this
0x14000a044  jmp     ?QueryInterface@CCompileProgressNotification@@UEAAJAEBU_GUID@@PEAPEAX@Z; CCompileProgressNotification::QueryInterface(_GUID const &,void * *)
```
