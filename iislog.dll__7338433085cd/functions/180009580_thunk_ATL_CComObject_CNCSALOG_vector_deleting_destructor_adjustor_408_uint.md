# [thunk]:ATL::CComObject<CNCSALOG>::`vector deleting destructor'`adjustor{408}' (uint)

- ea: `0x180009580`
- end: `0x18000958c`
- name: `??_E?$CComObject@VCNCSALOG@@@ATL@@WBJI@EAAPEAXI@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800096a0`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CNCSALOG>::`vector deleting destructor'(__int64 a1, char a2)
{
  return ATL::CComObject<CNCSALOG>::`vector deleting destructor'((_DWORD *)(a1 - 408), a2);
}

```

## disassembly

```asm
0x180009580  sub     rcx, 198h; Block
0x180009587  jmp     ??_E?$CComObject@VCNCSALOG@@@ATL@@UEAAPEAXI@Z; ATL::CComObject<CNCSALOG>::`vector deleting destructor'(uint)
```
