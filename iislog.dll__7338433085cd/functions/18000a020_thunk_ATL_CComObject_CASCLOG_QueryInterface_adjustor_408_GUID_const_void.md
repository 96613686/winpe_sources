# [thunk]:ATL::CComObject<CASCLOG>::QueryInterface`adjustor{408}' (_GUID const &,void * *)

- ea: `0x18000a020`
- end: `0x18000a02c`
- name: `?QueryInterface@?$CComObject@VCASCLOG@@@ATL@@WBJI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a000`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CASCLOG>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CASCLOG>::QueryInterface(a1 - 408, a2, a3);
}

```

## disassembly

```asm
0x18000a020  sub     rcx, 198h
0x18000a027  jmp     ?QueryInterface@?$CComObject@VCASCLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CASCLOG>::QueryInterface(_GUID const &,void * *)
```
