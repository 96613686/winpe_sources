# [thunk]:ATL::CComObject<CASCLOG>::`vector deleting destructor'`adjustor{408}' (uint)

- ea: `0x180009540`
- end: `0x18000954c`
- name: `??_E?$CComObject@VCASCLOG@@@ATL@@WBJI@EAAPEAXI@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800095e0`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CASCLOG>::`vector deleting destructor'(__int64 a1, char a2)
{
  return ATL::CComObject<CASCLOG>::`scalar deleting destructor'((_DWORD *)(a1 - 408), a2);
}

```

## disassembly

```asm
0x180009540  sub     rcx, 198h; Block
0x180009547  jmp     ??_G?$CComObject@VCASCLOG@@@ATL@@UEAAPEAXI@Z; ATL::CComObject<CASCLOG>::`scalar deleting destructor'(uint)
```
