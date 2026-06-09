# [thunk]:ATL::CComObject<CEXTLOG>::`vector deleting destructor'`adjustor{408}' (uint)

- ea: `0x180009560`
- end: `0x18000956c`
- name: `??_E?$CComObject@VCEXTLOG@@@ATL@@WBJI@EAAPEAXI@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009640`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CEXTLOG>::`vector deleting destructor'(__int64 a1, char a2)
{
  return ATL::CComObject<CEXTLOG>::`vector deleting destructor'((_DWORD *)(a1 - 408), a2);
}

```

## disassembly

```asm
0x180009560  sub     rcx, 198h; Block
0x180009567  jmp     ??_E?$CComObject@VCEXTLOG@@@ATL@@UEAAPEAXI@Z; ATL::CComObject<CEXTLOG>::`vector deleting destructor'(uint)
```
