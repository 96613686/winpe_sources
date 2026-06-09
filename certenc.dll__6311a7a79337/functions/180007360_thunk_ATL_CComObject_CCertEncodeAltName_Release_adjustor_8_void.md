# [thunk]:ATL::CComObject<CCertEncodeAltName>::Release`adjustor{8}' (void)

- ea: `0x180007360`
- end: `0x180007369`
- name: `?Release@?$CComObject@VCCertEncodeAltName@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800072d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeAltName>::Release(__int64 a1)
{
  return ATL::CComObject<CCertEncodeAltName>::Release((CCertEncodeAltName *)(a1 - 8));
}

```

## disassembly

```asm
0x180007360  sub     rcx, 8; this
0x180007364  jmp     ?Release@?$CComObject@VCCertEncodeAltName@@@ATL@@UEAAKXZ; ATL::CComObject<CCertEncodeAltName>::Release(void)
```
