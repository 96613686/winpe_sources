# [thunk]:ATL::CComObject<CMSDiscMasterObj>::AddRef`adjustor{120}' (void)

- ea: `0x180008190`
- end: `0x180008199`
- name: `?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@WHI@EAAKXZ`
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
  return ATL::CComObject<CMSDiscMasterObj>::AddRef(a1 - 120);
}

```

## disassembly

```asm
0x180008190  sub     rcx, 78h ; 'x'
0x180008194  jmp     ?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::AddRef(void)
```
