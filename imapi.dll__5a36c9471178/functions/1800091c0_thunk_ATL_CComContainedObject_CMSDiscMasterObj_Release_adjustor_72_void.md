# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::Release`adjustor{72}' (void)

- ea: `0x1800091c0`
- end: `0x1800091c9`
- name: `?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WEI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009170`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscMasterObj>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CMSDiscMasterObj>::Release(a1 - 72);
}

```

## disassembly

```asm
0x1800091c0  sub     rcx, 48h ; 'H'
0x1800091c4  jmp     ?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::Release(void)
```
