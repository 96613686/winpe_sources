# [thunk]:ATL::CComObject<CVPNDiagHelper>::Release`adjustor{8}' (void)

- ea: `0x180007d00`
- end: `0x180007d09`
- name: `?Release@?$CComObject@VCVPNDiagHelper@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007c70`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVPNDiagHelper>::Release(__int64 a1)
{
  return ATL::CComObject<CRasDiagHelper>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180007d00  sub     rcx, 8
0x180007d04  jmp     ?Release@?$CComObject@VCRasDiagHelper@@@ATL@@UEAAKXZ; ATL::CComObject<CRasDiagHelper>::Release(void)
```
