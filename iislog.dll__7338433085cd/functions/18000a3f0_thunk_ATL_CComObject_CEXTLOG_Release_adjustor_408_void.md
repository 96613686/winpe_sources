# [thunk]:ATL::CComObject<CEXTLOG>::Release`adjustor{408}' (void)

- ea: `0x18000a3f0`
- end: `0x18000a3fc`
- name: `?Release@?$CComObject@VCEXTLOG@@@ATL@@WBJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a380`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEXTLOG>::Release(__int64 a1)
{
  return ATL::CComObject<CEXTLOG>::Release((volatile signed __int32 *)(a1 - 408));
}

```

## disassembly

```asm
0x18000a3f0  sub     rcx, 198h
0x18000a3f7  jmp     ?Release@?$CComObject@VCEXTLOG@@@ATL@@UEAAKXZ; ATL::CComObject<CEXTLOG>::Release(void)
```
