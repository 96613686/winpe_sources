# [thunk]:ATL::CComObject<CDocWrapAnchor>::AddRef`adjustor{24}' (void)

- ea: `0x180005c90`
- end: `0x180005c99`
- name: `?AddRef@?$CComObject@VCDocWrapAnchor@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CDocWrapACP>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x180005c90  sub     rcx, 18h
0x180005c94  jmp     ?AddRef@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::AddRef(void)
```
