# [thunk]:ATL::CComObject<CDocWrapACP>::Release`adjustor{32}' (void)

- ea: `0x18000a7b0`
- end: `0x18000a7b9`
- name: `?Release@?$CComObject@VCDocWrapACP@@@ATL@@WCA@EAAKXZ`
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
  return ATL::CComObject<CDocWrapACP>::Release((_DWORD *)(a1 - 32));
}

```

## disassembly

```asm
0x18000a7b0  sub     rcx, 20h ; ' '
0x18000a7b4  jmp     ?Release@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::Release(void)
```
