# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::Release`adjustor{8}' (void)

- ea: `0x180009190`
- end: `0x180009199`
- name: `?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@W7EAAKXZ`
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
  return ATL::CComContainedObject<CMSDiscMasterObj>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180009190  sub     rcx, 8
0x180009194  jmp     ?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::Release(void)
```
