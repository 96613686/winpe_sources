# [thunk]:ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::QueryInterface`adjustor{72}' (_GUID const &,void * *)

- ea: `0x180010d50`
- end: `0x180010d59`
- name: `?QueryInterface@?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@WEI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010d30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::QueryInterface((char *)(a1 - 72), a2, a3);
}

```

## disassembly

```asm
0x180010d50  sub     rcx, 48h ; 'H'
0x180010d54  jmp     ?QueryInterface@?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::QueryInterface(_GUID const &,void * *)
```
