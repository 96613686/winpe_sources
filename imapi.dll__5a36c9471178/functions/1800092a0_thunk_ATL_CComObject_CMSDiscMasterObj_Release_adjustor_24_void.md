# [thunk]:ATL::CComObject<CMSDiscMasterObj>::Release`adjustor{24}' (void)

- ea: `0x1800092a0`
- end: `0x1800092a9`
- name: `?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800091e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscMasterObj>::Release(__int64 a1)
{
  return ATL::CComObject<CMSDiscMasterObj>::Release((volatile signed __int32 *)(a1 - 24));
}

```

## disassembly

```asm
0x1800092a0  sub     rcx, 18h
0x1800092a4  jmp     ?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::Release(void)
```
