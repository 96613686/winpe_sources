# [thunk]:CIEAdminBrokerObject::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x140008190`
- end: `0x140008199`
- name: `?QueryInterface@CIEAdminBrokerObject@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008030`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CIEAdminBrokerObject::QueryInterface((CIEAdminBrokerObject *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x140008190  sub     rcx, 10h; this
0x140008194  jmp     ?QueryInterface@CIEAdminBrokerObject@@UEAAJAEBU_GUID@@PEAPEAX@Z; CIEAdminBrokerObject::QueryInterface(_GUID const &,void * *)
```
