# [thunk]:ATL::CComObject<CDocWrapAnchor>::Release`adjustor{8}' (void)

- ea: `0x18000a840`
- end: `0x18000a849`
- name: `?Release@?$CComObject@VCDocWrapAnchor@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a7e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapAnchor>::Release(__int64 a1)
{
  return ATL::CComObject<CDocWrapAnchor>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x18000a840  sub     rcx, 8
0x18000a844  jmp     ?Release@?$CComObject@VCDocWrapAnchor@@@ATL@@UEAAKXZ; ATL::CComObject<CDocWrapAnchor>::Release(void)
```
