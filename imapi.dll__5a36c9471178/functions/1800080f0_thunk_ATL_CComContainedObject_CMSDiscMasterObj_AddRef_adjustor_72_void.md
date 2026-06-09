# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::AddRef`adjustor{72}' (void)

- ea: `0x1800080f0`
- end: `0x1800080f9`
- name: `?AddRef@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WEI@EAAKXZ`
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
  return ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(a1 - 72);
}

```

## disassembly

```asm
0x1800080f0  sub     rcx, 48h ; 'H'
0x1800080f4  jmp     ?AddRef@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(void)
```
