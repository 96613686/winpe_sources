# [thunk]:ATL::CComObject<CVPNDiagHelper>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007c40`
- end: `0x180007c49`
- name: `?QueryInterface@?$CComObject@VCVPNDiagHelper@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007c20`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVPNDiagHelper>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CL2TPDiagHelper>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180007c40  sub     rcx, 8
0x180007c44  jmp     ?QueryInterface@?$CComObject@VCL2TPDiagHelper@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CL2TPDiagHelper>::QueryInterface(_GUID const &,void * *)
```
