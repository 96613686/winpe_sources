# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::Release`adjustor{16}' (void)

- ea: `0x1800091a0`
- end: `0x1800091a9`
- name: `?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CMSDiscMasterObj>::Release(a1 - 16);
}

```

## disassembly

```asm
0x1800091a0  sub     rcx, 10h
0x1800091a4  jmp     ?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::Release(void)
```
