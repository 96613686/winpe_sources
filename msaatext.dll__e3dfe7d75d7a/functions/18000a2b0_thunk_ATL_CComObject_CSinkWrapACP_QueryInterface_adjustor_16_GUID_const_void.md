# [thunk]:ATL::CComObject<CSinkWrapACP>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x18000a2b0`
- end: `0x18000a2b9`
- name: `?QueryInterface@?$CComObject@VCSinkWrapACP@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a280`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapACP>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CSinkWrapACP>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x18000a2b0  sub     rcx, 10h
0x18000a2b4  jmp     ?QueryInterface@?$CComObject@VCSinkWrapACP@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CSinkWrapACP>::QueryInterface(_GUID const &,void * *)
```
