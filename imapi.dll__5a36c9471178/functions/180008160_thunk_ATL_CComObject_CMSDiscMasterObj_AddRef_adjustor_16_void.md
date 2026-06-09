# [thunk]:ATL::CComObject<CMSDiscMasterObj>::AddRef`adjustor{16}' (void)

- ea: `0x180008160`
- end: `0x180008169`
- name: `?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CMSDiscMasterObj>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180008160  sub     rcx, 10h
0x180008164  jmp     ?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::AddRef(void)
```
