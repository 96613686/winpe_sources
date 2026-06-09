# ATL::CComAggObject<CGameExplorer>::AddRef(void)

- ea: `0x180001d90`
- end: `0x180001d99`
- name: `?AddRef@?$CComAggObject@VCGameExplorer@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800024f8`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CGameExplorer>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
}

```

## disassembly

```asm
0x180001d90  add     rcx, 8; volatile int *
0x180001d94  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
