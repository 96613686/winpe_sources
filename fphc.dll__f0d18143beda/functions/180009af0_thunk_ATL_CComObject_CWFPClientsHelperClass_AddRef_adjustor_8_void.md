# [thunk]:ATL::CComObject<CWFPClientsHelperClass>::AddRef`adjustor{8}' (void)

- ea: `0x180009af0`
- end: `0x180009af9`
- name: `?AddRef@?$CComObject@VCWFPClientsHelperClass@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009ac0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWFPClientsHelperClass>::AddRef(__int64 a1)
{
  return ATL::CComObject<CWFPClientsHelperClass>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180009af0  sub     rcx, 8
0x180009af4  jmp     ?AddRef@?$CComObject@VCWFPClientsHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWFPClientsHelperClass>::AddRef(void)
```
