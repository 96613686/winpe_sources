# [thunk]:ATL::CComObject<CFilteringPlatformHelperClass>::Release`adjustor{56}' (void)

- ea: `0x180008840`
- end: `0x180008849`
- name: `?Release@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800087a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFilteringPlatformHelperClass>::Release(__int64 a1)
{
  return ATL::CComObject<CFilteringPlatformHelperClass>::Release((volatile signed __int32 *)(a1 - 56));
}

```

## disassembly

```asm
0x180008840  sub     rcx, 38h ; '8'
0x180008844  jmp     ?Release@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CFilteringPlatformHelperClass>::Release(void)
```
