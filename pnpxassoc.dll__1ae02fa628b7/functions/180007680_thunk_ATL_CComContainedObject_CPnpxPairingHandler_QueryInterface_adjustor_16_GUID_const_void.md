# [thunk]:ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180007680`
- end: `0x180007689`
- name: `?QueryInterface@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007650`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(a1 - 16);
}

```

## disassembly

```asm
0x180007680  sub     rcx, 10h
0x180007684  jmp     ?QueryInterface@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(_GUID const &,void * *)
```
