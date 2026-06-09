# ATL::CComObject<CEnhancedStorageSiloAction>::AddRef(void)

- ea: `0x180002200`
- end: `0x180002209`
- name: `?AddRef@?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800038bc`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageSiloAction>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
}

```

## disassembly

```asm
0x180002200  add     rcx, 8; volatile int *
0x180002204  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
