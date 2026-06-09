# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::Release`adjustor{120}' (void)

- ea: `0x1800091d0`
- end: `0x1800091d9`
- name: `?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WHI@EAAKXZ`
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
  return ATL::CComContainedObject<CMSDiscMasterObj>::Release(a1 - 120);
}

```

## disassembly

```asm
0x1800091d0  sub     rcx, 78h ; 'x'
0x1800091d4  jmp     ?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::Release(void)
```
