# [thunk]:ATL::CComObject<CMSDiscMasterObj>::Release`adjustor{16}' (void)

- ea: `0x180009290`
- end: `0x180009299`
- name: `?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800091e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscMasterObj>::Release(__int64 a1)
{
  return ATL::CComObject<CMSDiscMasterObj>::Release((volatile signed __int32 *)(a1 - 16));
}

```

## disassembly

```asm
0x180009290  sub     rcx, 10h
0x180009294  jmp     ?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::Release(void)
```
