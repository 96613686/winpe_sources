# [thunk]:ATL::CComObject<CGameExplorer>::Release`adjustor{8}' (void)

- ea: `0x180002470`
- end: `0x180002479`
- name: `?Release@?$CComObject@VCGameExplorer@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002400`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGameExplorer>::Release(__int64 a1)
{
  return ATL::CComObject<CGameExplorer>::Release((volatile int *)(a1 - 8));
}

```

## disassembly

```asm
0x180002470  sub     rcx, 8
0x180002474  jmp     ?Release@?$CComObject@VCGameExplorer@@@ATL@@UEAAKXZ; ATL::CComObject<CGameExplorer>::Release(void)
```
