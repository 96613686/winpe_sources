# [thunk]:ATL::CComObject<CCertEncodeLongArray>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007270`
- end: `0x180007279`
- name: `?QueryInterface@?$CComObject@VCCertEncodeLongArray@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007250`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeLongArray>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CCertEncodeLongArray>::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x180007270  sub     rcx, 8
0x180007274  jmp     ?QueryInterface@?$CComObject@VCCertEncodeLongArray@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCertEncodeLongArray>::QueryInterface(_GUID const &,void * *)
```
