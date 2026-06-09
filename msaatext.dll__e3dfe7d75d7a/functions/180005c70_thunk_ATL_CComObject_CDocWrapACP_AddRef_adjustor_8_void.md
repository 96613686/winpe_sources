# [thunk]:ATL::CComObject<CDocWrapACP>::AddRef`adjustor{8}' (void)

- ea: `0x180005c70`
- end: `0x180005c79`
- name: `?AddRef@?$CComObject@VCDocWrapACP@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapACP>::AddRef(__int64 a1)
{
  return ATL::CComObject<CDocWrapACP>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180005c70  sub     rcx, 8
0x180005c74  jmp     ?AddRef@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapACP>::AddRef(void)
```
