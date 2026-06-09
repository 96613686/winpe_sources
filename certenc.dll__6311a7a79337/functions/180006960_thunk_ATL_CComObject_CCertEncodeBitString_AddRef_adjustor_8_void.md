# [thunk]:ATL::CComObject<CCertEncodeBitString>::AddRef`adjustor{8}' (void)

- ea: `0x180006960`
- end: `0x180006969`
- name: `?AddRef@?$CComObject@VCCertEncodeBitString@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006930`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeBitString>::AddRef(__int64 a1)
{
  return ATL::CComObject<CCertEncodeStringArray>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180006960  sub     rcx, 8
0x180006964  jmp     ?AddRef@?$CComObject@VCCertEncodeStringArray@@@ATL@@UEAAKXZ; ATL::CComObject<CCertEncodeStringArray>::AddRef(void)
```
