# [thunk]:ATL::CComObject<CWFPClientsHelperClass>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180009dd0`
- end: `0x180009dd9`
- name: `?QueryInterface@?$CComObject@VCWFPClientsHelperClass@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009db0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWFPClientsHelperClass>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CWFPClientsHelperClass>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180009dd0  sub     rcx, 8
0x180009dd4  jmp     ?QueryInterface@?$CComObject@VCWFPClientsHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CWFPClientsHelperClass>::QueryInterface(_GUID const &,void * *)
```
