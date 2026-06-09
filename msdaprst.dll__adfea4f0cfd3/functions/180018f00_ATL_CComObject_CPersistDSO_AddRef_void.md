# ATL::CComObject<CPersistDSO>::AddRef(void)

- ea: `0x180018f00`
- end: `0x180018f09`
- name: `?AddRef@?$CComObject@VCPersistDSO@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018f10`
- `0x180018f20`
- `0x180018f30`
- `0x180018f50`
- `0x180018f70`
- `0x180018f90`
- `0x180018fb0`
- `0x180018fc0`
- `0x180018fd0`

## callees

- `0x18000ca34`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CPersistDSO>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((int *)(a1 + 48));
}

```

## disassembly

```asm
0x180018f00  add     rcx, 30h ; '0'; int *
0x180018f04  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeIncrementReferenceMultiThread(long *)
```
