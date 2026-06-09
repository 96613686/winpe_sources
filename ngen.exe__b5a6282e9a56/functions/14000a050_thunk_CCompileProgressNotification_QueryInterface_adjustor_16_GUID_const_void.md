# [thunk]:CCompileProgressNotification::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x14000a050`
- end: `0x14000a059`
- name: `?QueryInterface@CCompileProgressNotification@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return CCompileProgressNotification::QueryInterface((CCompileProgressNotification *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x14000a050  sub     rcx, 10h; this
0x14000a054  jmp     ?QueryInterface@CCompileProgressNotification@@UEAAJAEBU_GUID@@PEAPEAX@Z; CCompileProgressNotification::QueryInterface(_GUID const &,void * *)
```
