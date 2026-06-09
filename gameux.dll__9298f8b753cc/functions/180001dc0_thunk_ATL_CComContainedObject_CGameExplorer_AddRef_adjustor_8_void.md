# [thunk]:ATL::CComContainedObject<CGameExplorer>::AddRef`adjustor{8}' (void)

- ea: `0x180001dc0`
- end: `0x180001dc9`
- name: `?AddRef@?$CComContainedObject@VCGameExplorer@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001da0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameExplorer>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CGameExplorer>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180001dc0  sub     rcx, 8
0x180001dc4  jmp     ?AddRef@?$CComContainedObject@VCGameExplorer@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CGameExplorer>::AddRef(void)
```
