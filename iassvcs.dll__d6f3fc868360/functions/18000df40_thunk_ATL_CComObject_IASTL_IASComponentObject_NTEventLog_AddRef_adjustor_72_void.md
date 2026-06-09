# [thunk]:ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::AddRef`adjustor{72}' (void)

- ea: `0x18000df40`
- end: `0x18000df49`
- name: `?AddRef@?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@WEI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000df10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::AddRef(__int64 a1)
{
  return ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::AddRef(a1 - 72);
}

```

## disassembly

```asm
0x18000df40  sub     rcx, 48h ; 'H'
0x18000df44  jmp     ?AddRef@?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@UEAAKXZ; ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::AddRef(void)
```
