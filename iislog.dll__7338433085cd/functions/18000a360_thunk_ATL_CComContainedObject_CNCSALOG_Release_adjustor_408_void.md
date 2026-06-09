# [thunk]:ATL::CComContainedObject<CNCSALOG>::Release`adjustor{408}' (void)

- ea: `0x18000a360`
- end: `0x18000a36c`
- name: `?Release@?$CComContainedObject@VCNCSALOG@@@ATL@@WBJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a340`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CNCSALOG>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CODBCLOG>::Release(a1 - 408);
}

```

## disassembly

```asm
0x18000a360  sub     rcx, 198h
0x18000a367  jmp     ?Release@?$CComContainedObject@VCODBCLOG@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CODBCLOG>::Release(void)
```
