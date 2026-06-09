# [thunk]:ATL::CComObject<CCertEncodeDateArray>::Release`adjustor{8}' (void)

- ea: `0x180007540`
- end: `0x180007549`
- name: `?Release@?$CComObject@VCCertEncodeDateArray@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800074b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeDateArray>::Release(__int64 a1)
{
  return ATL::CComObject<CCertEncodeDateArray>::Release((CCertEncodeDateArray *)(a1 - 8));
}

```

## disassembly

```asm
0x180007540  sub     rcx, 8; this
0x180007544  jmp     ?Release@?$CComObject@VCCertEncodeDateArray@@@ATL@@UEAAKXZ; ATL::CComObject<CCertEncodeDateArray>::Release(void)
```
