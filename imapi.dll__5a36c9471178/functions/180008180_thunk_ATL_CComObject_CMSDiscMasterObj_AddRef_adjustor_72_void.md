# [thunk]:ATL::CComObject<CMSDiscMasterObj>::AddRef`adjustor{72}' (void)

- ea: `0x180008180`
- end: `0x180008189`
- name: `?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@WEI@EAAKXZ`
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
  return ATL::CComObject<CMSDiscMasterObj>::AddRef(a1 - 72);
}

```

## disassembly

```asm
0x180008180  sub     rcx, 48h ; 'H'
0x180008184  jmp     ?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::AddRef(void)
```
