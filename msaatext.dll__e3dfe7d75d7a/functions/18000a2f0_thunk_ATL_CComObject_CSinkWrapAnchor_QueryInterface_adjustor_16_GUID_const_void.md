# [thunk]:ATL::CComObject<CSinkWrapAnchor>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x18000a2f0`
- end: `0x18000a2f9`
- name: `?QueryInterface@?$CComObject@VCSinkWrapAnchor@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a2c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapAnchor>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CSinkWrapAnchor>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x18000a2f0  sub     rcx, 10h
0x18000a2f4  jmp     ?QueryInterface@?$CComObject@VCSinkWrapAnchor@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CSinkWrapAnchor>::QueryInterface(_GUID const &,void * *)
```
