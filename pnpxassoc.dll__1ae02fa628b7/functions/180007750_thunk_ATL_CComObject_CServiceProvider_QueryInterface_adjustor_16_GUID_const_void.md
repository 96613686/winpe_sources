# [thunk]:ATL::CComObject<CServiceProvider>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180007750`
- end: `0x180007759`
- name: `?QueryInterface@?$CComObject@VCServiceProvider@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007720`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServiceProvider>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CServiceProvider>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x180007750  sub     rcx, 10h
0x180007754  jmp     ?QueryInterface@?$CComObject@VCServiceProvider@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CServiceProvider>::QueryInterface(_GUID const &,void * *)
```
