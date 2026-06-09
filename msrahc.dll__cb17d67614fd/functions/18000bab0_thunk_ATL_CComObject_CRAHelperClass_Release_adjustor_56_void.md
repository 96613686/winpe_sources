# [thunk]:ATL::CComObject<CRAHelperClass>::Release`adjustor{56}' (void)

- ea: `0x18000bab0`
- end: `0x18000bab9`
- name: `?Release@?$CComObject@VCRAHelperClass@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ba30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRAHelperClass>::Release(__int64 a1)
{
  return ATL::CComObject<CRAHelperClass>::Release((volatile int *)(a1 - 56));
}

```

## disassembly

```asm
0x18000bab0  sub     rcx, 38h ; '8'
0x18000bab4  jmp     ?Release@?$CComObject@VCRAHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CRAHelperClass>::Release(void)
```
