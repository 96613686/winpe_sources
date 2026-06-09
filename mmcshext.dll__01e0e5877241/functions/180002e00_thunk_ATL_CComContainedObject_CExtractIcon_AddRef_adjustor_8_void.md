# [thunk]:ATL::CComContainedObject<CExtractIcon>::AddRef`adjustor{8}' (void)

- ea: `0x180002e00`
- end: `0x180002e09`
- name: `?AddRef@?$CComContainedObject@VCExtractIcon@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002de0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CExtractIcon>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CExtractIcon>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180002e00  sub     rcx, 8
0x180002e04  jmp     ?AddRef@?$CComContainedObject@VCExtractIcon@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CExtractIcon>::AddRef(void)
```
