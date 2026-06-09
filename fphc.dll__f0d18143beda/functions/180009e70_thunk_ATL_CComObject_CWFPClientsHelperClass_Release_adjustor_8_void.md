# [thunk]:ATL::CComObject<CWFPClientsHelperClass>::Release`adjustor{8}' (void)

- ea: `0x180009e70`
- end: `0x180009e79`
- name: `?Release@?$CComObject@VCWFPClientsHelperClass@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009de0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWFPClientsHelperClass>::Release(__int64 a1)
{
  return ATL::CComObject<CWFPClientsHelperClass>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180009e70  sub     rcx, 8
0x180009e74  jmp     ?Release@?$CComObject@VCWFPClientsHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWFPClientsHelperClass>::Release(void)
```
