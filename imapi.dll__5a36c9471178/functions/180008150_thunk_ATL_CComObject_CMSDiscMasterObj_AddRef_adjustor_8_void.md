# [thunk]:ATL::CComObject<CMSDiscMasterObj>::AddRef`adjustor{8}' (void)

- ea: `0x180008150`
- end: `0x180008159`
- name: `?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008110`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscMasterObj>::AddRef(__int64 a1)
{
  return ATL::CComObject<CMSDiscMasterObj>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180008150  sub     rcx, 8
0x180008154  jmp     ?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::AddRef(void)
```
