# [thunk]:ATL::CComContainedObject<CMSDiscRecorderObj>::AddRef`adjustor{8}' (void)

- ea: `0x180004d00`
- end: `0x180004d09`
- name: `?AddRef@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ce0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscRecorderObj>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CMSDiscRecorderObj>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180004d00  sub     rcx, 8
0x180004d04  jmp     ?AddRef@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscRecorderObj>::AddRef(void)
```
