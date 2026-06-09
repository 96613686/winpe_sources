# [thunk]:ATL::CComObject<CFilteringPlatformHelperClass>::Release`adjustor{8}' (void)

- ea: `0x180008830`
- end: `0x180008839`
- name: `?Release@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CFilteringPlatformHelperClass>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180008830  sub     rcx, 8
0x180008834  jmp     ?Release@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CFilteringPlatformHelperClass>::Release(void)
```
