# [thunk]:ATL::CComObject<CMSDiscRecorderObj>::Release`adjustor{8}' (void)

- ea: `0x180007410`
- end: `0x180007419`
- name: `?Release@?$CComObject@VCMSDiscRecorderObj@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007380`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscRecorderObj>::Release(__int64 a1)
{
  return ATL::CComObject<CMSDiscRecorderObj>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180007410  sub     rcx, 8
0x180007414  jmp     ?Release@?$CComObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ; ATL::CComObject<CMSDiscRecorderObj>::Release(void)
```
