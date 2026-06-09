# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::Release`adjustor{24}' (void)

- ea: `0x1800091b0`
- end: `0x1800091b9`
- name: `?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComContainedObject<CMSDiscMasterObj>::Release(a1 - 24);
}

```

## disassembly

```asm
0x1800091b0  sub     rcx, 18h
0x1800091b4  jmp     ?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::Release(void)
```
