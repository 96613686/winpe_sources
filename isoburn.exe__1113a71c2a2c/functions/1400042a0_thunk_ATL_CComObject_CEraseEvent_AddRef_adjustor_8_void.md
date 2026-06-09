# [thunk]:ATL::CComObject<CEraseEvent>::AddRef`adjustor{8}' (void)

- ea: `0x1400042a0`
- end: `0x1400042a9`
- name: `?AddRef@?$CComObject@VCEraseEvent@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004270`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEraseEvent>::AddRef(__int64 a1)
{
  return ATL::CComObject<CEraseEvent>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1400042a0  sub     rcx, 8
0x1400042a4  jmp     ?AddRef@?$CComObject@VCEraseEvent@@@ATL@@UEAAKXZ; ATL::CComObject<CEraseEvent>::AddRef(void)
```
