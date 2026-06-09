# [thunk]:ATL::CComContainedObject<CASCLOG>::AddRef`adjustor{408}' (void)

- ea: `0x180009750`
- end: `0x18000975c`
- name: `?AddRef@?$CComContainedObject@VCASCLOG@@@ATL@@WBJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009730`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CASCLOG>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CODBCLOG>::AddRef(a1 - 408);
}

```

## disassembly

```asm
0x180009750  sub     rcx, 198h
0x180009757  jmp     ?AddRef@?$CComContainedObject@VCODBCLOG@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CODBCLOG>::AddRef(void)
```
