# [thunk]:ATL::CComObject<CMSDiscRecorderObj>::AddRef`adjustor{8}' (void)

- ea: `0x180004d40`
- end: `0x180004d49`
- name: `?AddRef@?$CComObject@VCMSDiscRecorderObj@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004d10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscRecorderObj>::AddRef(__int64 a1)
{
  return ATL::CComObject<CMSDiscRecorderObj>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180004d40  sub     rcx, 8
0x180004d44  jmp     ?AddRef@?$CComObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscRecorderObj>::AddRef(void)
```
