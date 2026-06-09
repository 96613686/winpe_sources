# [thunk]:ATL::CComObject<CIsoBurn>::Release`adjustor{56}' (void)

- ea: `0x1400078d0`
- end: `0x1400078d9`
- name: `?Release@?$CComObject@VCIsoBurn@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007830`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::Release(__int64 a1)
{
  return ATL::CComObject<CIsoBurn>::Release((volatile signed __int32 *)(a1 - 56));
}

```

## disassembly

```asm
0x1400078d0  sub     rcx, 38h ; '8'
0x1400078d4  jmp     ?Release@?$CComObject@VCIsoBurn@@@ATL@@UEAAKXZ; ATL::CComObject<CIsoBurn>::Release(void)
```
