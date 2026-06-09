# [thunk]:ATL::CComObject<CMSDiscMasterObj>::Release`adjustor{8}' (void)

- ea: `0x180009280`
- end: `0x180009289`
- name: `?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CMSDiscMasterObj>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180009280  sub     rcx, 8
0x180009284  jmp     ?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscMasterObj>::Release(void)
```
