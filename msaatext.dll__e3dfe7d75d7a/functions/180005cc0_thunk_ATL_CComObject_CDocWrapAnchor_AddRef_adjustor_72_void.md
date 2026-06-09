# [thunk]:ATL::CComObject<CDocWrapAnchor>::AddRef`adjustor{72}' (void)

- ea: `0x180005cc0`
- end: `0x180005cc9`
- name: `?AddRef@?$CComObject@VCDocWrapAnchor@@@ATL@@WEI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapAnchor>::AddRef(__int64 a1)
{
  return ATL::CComObject<CDocWrapACP>::AddRef(a1 - 72);
}

```

## disassembly

```asm
0x180005cc0  sub     rcx, 48h ; 'H'
0x180005cc4  jmp     ?AddRef@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::AddRef(void)
```
