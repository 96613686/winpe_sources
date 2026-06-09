# [thunk]:ATL::CComObject<CExtractIcon>::AddRef`adjustor{8}' (void)

- ea: `0x180002e50`
- end: `0x180002e59`
- name: `?AddRef@?$CComObject@VCExtractIcon@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CExtractIcon>::AddRef(__int64 a1)
{
  return ATL::CComObject<CExtractIcon>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180002e50  sub     rcx, 8
0x180002e54  jmp     ?AddRef@?$CComObject@VCExtractIcon@@@ATL@@UEAAKXZ; ATL::CComObject<CExtractIcon>::AddRef(void)
```
