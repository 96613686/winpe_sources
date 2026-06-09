# [thunk]:ATL::CComObject<AuditChannel>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180010d80`
- end: `0x180010d89`
- name: `?QueryInterface@?$CComObject@VAuditChannel@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010d60`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<AuditChannel>::QueryInterface(__int64 a1)
{
  return ATL::CComObjectCached<AuditChannel>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x180010d80  sub     rcx, 8
0x180010d84  jmp     ?QueryInterface@?$CComObjectCached@VAuditChannel@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObjectCached<AuditChannel>::QueryInterface(_GUID const &,void * *)
```
