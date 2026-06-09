# [thunk]:ATL::CComObject<CEXTLOG>::QueryInterface`adjustor{408}' (_GUID const &,void * *)

- ea: `0x18000a060`
- end: `0x18000a06c`
- name: `?QueryInterface@?$CComObject@VCEXTLOG@@@ATL@@WBJI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a040`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEXTLOG>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return ATL::CComObject<CEXTLOG>::QueryInterface(a1 - 408, a2, a3);
}

```

## disassembly

```asm
0x18000a060  sub     rcx, 198h
0x18000a067  jmp     ?QueryInterface@?$CComObject@VCEXTLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CEXTLOG>::QueryInterface(_GUID const &,void * *)
```
