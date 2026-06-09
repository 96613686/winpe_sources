# [thunk]:ATL::CComObject<CFilteringPlatformHelperClass>::AddRef`adjustor{56}' (void)

- ea: `0x180006060`
- end: `0x180006069`
- name: `?AddRef@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006020`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFilteringPlatformHelperClass>::AddRef(__int64 a1)
{
  return ATL::CComObject<CFilteringPlatformHelperClass>::AddRef(a1 - 56);
}

```

## disassembly

```asm
0x180006060  sub     rcx, 38h ; '8'
0x180006064  jmp     ?AddRef@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CFilteringPlatformHelperClass>::AddRef(void)
```
