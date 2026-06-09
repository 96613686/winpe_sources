# [thunk]:ATL::CComObject<CFilteringPlatformHelperClass>::AddRef`adjustor{8}' (void)

- ea: `0x180006050`
- end: `0x180006059`
- name: `?AddRef@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CFilteringPlatformHelperClass>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180006050  sub     rcx, 8
0x180006054  jmp     ?AddRef@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CFilteringPlatformHelperClass>::AddRef(void)
```
