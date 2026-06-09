# ATL::CComObject<CGameExplorer>::AddRef(void)

- ea: `0x180001dd0`
- end: `0x180001dd9`
- name: `?AddRef@?$CComObject@VCGameExplorer@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001de0`

## callees

- `0x1800024f8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGameExplorer>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 16));
}

```

## disassembly

```asm
0x180001dd0  add     rcx, 10h; volatile int *
0x180001dd4  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
