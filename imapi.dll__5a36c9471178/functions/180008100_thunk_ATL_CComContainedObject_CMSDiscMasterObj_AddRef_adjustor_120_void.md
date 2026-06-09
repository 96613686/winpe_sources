# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::AddRef`adjustor{120}' (void)

- ea: `0x180008100`
- end: `0x180008109`
- name: `?AddRef@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WHI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800080a0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(a1 - 120);
}

```

## disassembly

```asm
0x180008100  sub     rcx, 78h ; 'x'
0x180008104  jmp     ?AddRef@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(void)
```
