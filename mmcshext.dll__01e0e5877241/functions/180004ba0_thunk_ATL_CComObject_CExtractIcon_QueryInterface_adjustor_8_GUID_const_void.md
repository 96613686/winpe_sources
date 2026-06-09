# [thunk]:ATL::CComObject<CExtractIcon>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180004ba0`
- end: `0x180004ba9`
- name: `?QueryInterface@?$CComObject@VCExtractIcon@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004b80`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CExtractIcon>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CExtractIcon>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180004ba0  sub     rcx, 8
0x180004ba4  jmp     ?QueryInterface@?$CComObject@VCExtractIcon@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CExtractIcon>::QueryInterface(_GUID const &,void * *)
```
