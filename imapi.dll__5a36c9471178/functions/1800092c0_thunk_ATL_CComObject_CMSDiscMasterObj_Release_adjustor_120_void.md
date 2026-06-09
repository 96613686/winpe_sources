# [thunk]:ATL::CComObject<CMSDiscMasterObj>::Release`adjustor{120}' (void)

- ea: `0x1800092c0`
- end: `0x1800092c9`
- name: `?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@WHI@EAAKXZ`
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
  return ATL::CComObject<CMSDiscMasterObj>::Release((volatile signed __int32 *)(a1 - 120));
}

```

## disassembly

```asm
0x1800092c0  sub     rcx, 78h ; 'x'
0x1800092c4  jmp     ?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::Release(void)
```
