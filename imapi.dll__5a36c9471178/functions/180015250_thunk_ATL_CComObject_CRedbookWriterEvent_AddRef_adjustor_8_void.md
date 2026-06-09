# [thunk]:ATL::CComObject<CRedbookWriterEvent>::AddRef`adjustor{8}' (void)

- ea: `0x180015250`
- end: `0x180015259`
- name: `?AddRef@?$CComObject@VCRedbookWriterEvent@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015220`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRedbookWriterEvent>::AddRef(__int64 a1)
{
  return ATL::CComObject<CRedbookWriterEvent>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180015250  sub     rcx, 8
0x180015254  jmp     ?AddRef@?$CComObject@VCRedbookWriterEvent@@@ATL@@UEAAKXZ; ATL::CComObject<CRedbookWriterEvent>::AddRef(void)
```
