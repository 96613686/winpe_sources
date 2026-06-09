# [thunk]:ATL::CComObject<CRedbookWriterEvent>::Release`adjustor{8}' (void)

- ea: `0x180016bb0`
- end: `0x180016bb9`
- name: `?Release@?$CComObject@VCRedbookWriterEvent@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016b20`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRedbookWriterEvent>::Release(__int64 a1)
{
  return ATL::CComObject<CRedbookWriterEvent>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180016bb0  sub     rcx, 8
0x180016bb4  jmp     ?Release@?$CComObject@VCRedbookWriterEvent@@@ATL@@UEAAKXZ; ATL::CComObject<CRedbookWriterEvent>::Release(void)
```
