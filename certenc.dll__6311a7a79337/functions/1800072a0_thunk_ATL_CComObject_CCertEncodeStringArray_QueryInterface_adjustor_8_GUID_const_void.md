# [thunk]:ATL::CComObject<CCertEncodeStringArray>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800072a0`
- end: `0x1800072a9`
- name: `?QueryInterface@?$CComObject@VCCertEncodeStringArray@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007280`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeStringArray>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CCertEncodeStringArray>::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x1800072a0  sub     rcx, 8
0x1800072a4  jmp     ?QueryInterface@?$CComObject@VCCertEncodeStringArray@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCertEncodeStringArray>::QueryInterface(_GUID const &,void * *)
```
