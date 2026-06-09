# [thunk]:ATL::CComObject<CDocWrapACP>::Release`adjustor{8}' (void)

- ea: `0x18000a780`
- end: `0x18000a789`
- name: `?Release@?$CComObject@VCDocWrapACP@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CDocWrapACP>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x18000a780  sub     rcx, 8
0x18000a784  jmp     ?Release@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::Release(void)
```
