# [thunk]:ATL::CComObject<CNCSALOG>::QueryInterface`adjustor{408}' (_GUID const &,void * *)

- ea: `0x18000a0a0`
- end: `0x18000a0ac`
- name: `?QueryInterface@?$CComObject@VCNCSALOG@@@ATL@@WBJI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a080`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CNCSALOG>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CNCSALOG>::QueryInterface(a1 - 408, a2, a3);
}

```

## disassembly

```asm
0x18000a0a0  sub     rcx, 198h
0x18000a0a7  jmp     ?QueryInterface@?$CComObject@VCNCSALOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CNCSALOG>::QueryInterface(_GUID const &,void * *)
```
