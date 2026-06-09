# [thunk]:ATL::CComObject<CEXTLOG>::AddRef`adjustor{408}' (void)

- ea: `0x180009770`
- end: `0x18000977c`
- name: `?AddRef@?$CComObject@VCEXTLOG@@@ATL@@WBJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009700`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEXTLOG>::AddRef(__int64 a1)
{
  return ATL::CComObject<CEXTLOG>::AddRef(a1 - 408);
}

```

## disassembly

```asm
0x180009770  sub     rcx, 198h
0x180009777  jmp     ?AddRef@?$CComObject@VCEXTLOG@@@ATL@@UEAAKXZ; ATL::CComObject<CEXTLOG>::AddRef(void)
```
