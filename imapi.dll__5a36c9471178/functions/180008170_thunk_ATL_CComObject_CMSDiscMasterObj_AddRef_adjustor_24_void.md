# [thunk]:ATL::CComObject<CMSDiscMasterObj>::AddRef`adjustor{24}' (void)

- ea: `0x180008170`
- end: `0x180008179`
- name: `?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CMSDiscMasterObj>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x180008170  sub     rcx, 18h
0x180008174  jmp     ?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::AddRef(void)
```
