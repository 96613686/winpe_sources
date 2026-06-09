# [thunk]:ATL::CComObject<CDocWrapACP>::Release`adjustor{16}' (void)

- ea: `0x18000a790`
- end: `0x18000a799`
- name: `?Release@?$CComObject@VCDocWrapACP@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CDocWrapACP>::Release((_DWORD *)(a1 - 16));
}

```

## disassembly

```asm
0x18000a790  sub     rcx, 10h
0x18000a794  jmp     ?Release@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::Release(void)
```
