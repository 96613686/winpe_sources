# [thunk]:ATL::CComObject<CDocWrapAnchor>::Release`adjustor{72}' (void)

- ea: `0x18000a890`
- end: `0x18000a899`
- name: `?Release@?$CComObject@VCDocWrapAnchor@@@ATL@@WEI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a7e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapAnchor>::Release(__int64 a1)
{
  return ATL::CComObject<CDocWrapAnchor>::Release((_DWORD *)(a1 - 72));
}

```

## disassembly

```asm
0x18000a890  sub     rcx, 48h ; 'H'
0x18000a894  jmp     ?Release@?$CComObject@VCDocWrapAnchor@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapAnchor>::Release(void)
```
