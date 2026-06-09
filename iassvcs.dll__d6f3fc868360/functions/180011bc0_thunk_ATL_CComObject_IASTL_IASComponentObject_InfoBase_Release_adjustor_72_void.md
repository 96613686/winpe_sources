# [thunk]:ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::Release`adjustor{72}' (void)

- ea: `0x180011bc0`
- end: `0x180011bc9`
- name: `?Release@?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@WEI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011b30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::Release(__int64 a1)
{
  return ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::Release((volatile signed __int32 *)(a1 - 72));
}

```

## disassembly

```asm
0x180011bc0  sub     rcx, 48h ; 'H'
0x180011bc4  jmp     ?Release@?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@UEAAKXZ; ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::Release(void)
```
