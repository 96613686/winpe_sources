# [thunk]:CIISWebService::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x1800062d0`
- end: `0x1800062d9`
- name: `?QueryInterface@CIISWebService@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006290`

## pseudocode

```c
__int64 __fastcall CIISWebService::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CIISApp::QueryInterface((CIISApp *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x1800062d0  sub     rcx, 18h; this
0x1800062d4  jmp     ?QueryInterface@CIISApp@@UEAAJAEBU_GUID@@PEAPEAX@Z; CIISApp::QueryInterface(_GUID const &,void * *)
```
