# [thunk]:ATL::CComContainedObject<CASCLOG>::QueryInterface`adjustor{408}' (_GUID const &,void * *)

- ea: `0x180009fe0`
- end: `0x180009fec`
- name: `?QueryInterface@?$CComContainedObject@VCASCLOG@@@ATL@@WBJI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009fc0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CASCLOG>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CASCLOG>::QueryInterface(a1 - 408);
}

```

## disassembly

```asm
0x180009fe0  sub     rcx, 198h
0x180009fe7  jmp     ?QueryInterface@?$CComContainedObject@VCASCLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CASCLOG>::QueryInterface(_GUID const &,void * *)
```
