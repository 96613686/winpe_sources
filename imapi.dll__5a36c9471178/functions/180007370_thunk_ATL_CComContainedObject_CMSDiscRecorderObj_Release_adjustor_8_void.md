# [thunk]:ATL::CComContainedObject<CMSDiscRecorderObj>::Release`adjustor{8}' (void)

- ea: `0x180007370`
- end: `0x180007379`
- name: `?Release@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007350`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscRecorderObj>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CMSDiscRecorderObj>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180007370  sub     rcx, 8
0x180007374  jmp     ?Release@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscRecorderObj>::Release(void)
```
