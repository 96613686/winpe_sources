# ATL::CComObject<CRAHelperClass>::AddRef(void)

- ea: `0x180008e00`
- end: `0x180008e09`
- name: `?AddRef@?$CComObject@VCRAHelperClass@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e10`
- `0x180008e20`

## callees

- `0x18000bb8c`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CRAHelperClass>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 64));
}

```

## disassembly

```asm
0x180008e00  add     rcx, 40h ; '@'; volatile int *
0x180008e04  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
