# [thunk]:ATL::CComObject<CGameExplorer>::AddRef`adjustor{8}' (void)

- ea: `0x180001de0`
- end: `0x180001de9`
- name: `?AddRef@?$CComObject@VCGameExplorer@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001dd0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGameExplorer>::AddRef(__int64 a1)
{
  return ATL::CComObject<CGameExplorer>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180001de0  sub     rcx, 8
0x180001de4  jmp     ?AddRef@?$CComObject@VCGameExplorer@@@ATL@@UEAAKXZ; ATL::CComObject<CGameExplorer>::AddRef(void)
```
