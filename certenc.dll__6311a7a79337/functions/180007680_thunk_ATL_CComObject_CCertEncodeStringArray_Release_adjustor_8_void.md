# [thunk]:ATL::CComObject<CCertEncodeStringArray>::Release`adjustor{8}' (void)

- ea: `0x180007680`
- end: `0x180007689`
- name: `?Release@?$CComObject@VCCertEncodeStringArray@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800075f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeStringArray>::Release(__int64 a1)
{
  return ATL::CComObject<CCertEncodeStringArray>::Release((CCertEncodeStringArray *)(a1 - 8));
}

```

## disassembly

```asm
0x180007680  sub     rcx, 8; this
0x180007684  jmp     ?Release@?$CComObject@VCCertEncodeStringArray@@@ATL@@UEAAKXZ; ATL::CComObject<CCertEncodeStringArray>::Release(void)
```
