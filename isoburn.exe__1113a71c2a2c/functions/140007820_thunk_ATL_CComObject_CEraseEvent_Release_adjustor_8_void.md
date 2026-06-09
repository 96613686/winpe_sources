# [thunk]:ATL::CComObject<CEraseEvent>::Release`adjustor{8}' (void)

- ea: `0x140007820`
- end: `0x140007829`
- name: `?Release@?$CComObject@VCEraseEvent@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007790`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEraseEvent>::Release(__int64 a1)
{
  return ATL::CComObject<CEraseEvent>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x140007820  sub     rcx, 8
0x140007824  jmp     ?Release@?$CComObject@VCEraseEvent@@@ATL@@UEAAKXZ; ATL::CComObject<CEraseEvent>::Release(void)
```
