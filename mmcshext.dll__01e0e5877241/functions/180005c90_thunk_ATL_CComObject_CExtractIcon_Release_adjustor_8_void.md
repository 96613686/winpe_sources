# [thunk]:ATL::CComObject<CExtractIcon>::Release`adjustor{8}' (void)

- ea: `0x180005c90`
- end: `0x180005c99`
- name: `?Release@?$CComObject@VCExtractIcon@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c00`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CExtractIcon>::Release(__int64 a1)
{
  return ATL::CComObject<CExtractIcon>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x180005c90  sub     rcx, 8
0x180005c94  jmp     ?Release@?$CComObject@VCExtractIcon@@@ATL@@UEAAKXZ; ATL::CComObject<CExtractIcon>::Release(void)
```
