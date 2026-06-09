# [thunk]:ATL::CComContainedObject<CMSDiscMasterObj>::AddRef`adjustor{16}' (void)

- ea: `0x1800080d0`
- end: `0x1800080d9`
- name: `?AddRef@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x1800080d0  sub     rcx, 10h
0x1800080d4  jmp     ?AddRef@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(void)
```
