# [thunk]:ATL::CComObject<CDocWrapACP>::Release`adjustor{24}' (void)

- ea: `0x18000a7a0`
- end: `0x18000a7a9`
- name: `?Release@?$CComObject@VCDocWrapACP@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a6c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapACP>::Release(__int64 a1)
{
  return ATL::CComObject<CDocWrapACP>::Release((_DWORD *)(a1 - 24));
}

```

## disassembly

```asm
0x18000a7a0  sub     rcx, 18h
0x18000a7a4  jmp     ?Release@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::Release(void)
```
