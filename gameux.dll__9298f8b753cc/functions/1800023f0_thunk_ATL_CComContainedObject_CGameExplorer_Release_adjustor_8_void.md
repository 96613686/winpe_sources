# [thunk]:ATL::CComContainedObject<CGameExplorer>::Release`adjustor{8}' (void)

- ea: `0x1800023f0`
- end: `0x1800023f9`
- name: `?Release@?$CComContainedObject@VCGameExplorer@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800023d0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameExplorer>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CGameExplorer>::Release(a1 - 8);
}

```

## disassembly

```asm
0x1800023f0  sub     rcx, 8
0x1800023f4  jmp     ?Release@?$CComContainedObject@VCGameExplorer@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CGameExplorer>::Release(void)
```
