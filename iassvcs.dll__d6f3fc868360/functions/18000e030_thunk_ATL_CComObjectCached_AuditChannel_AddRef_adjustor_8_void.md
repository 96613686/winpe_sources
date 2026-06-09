# [thunk]:ATL::CComObjectCached<AuditChannel>::AddRef`adjustor{8}' (void)

- ea: `0x18000e030`
- end: `0x18000e039`
- name: `?AddRef@?$CComObjectCached@VAuditChannel@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000dfe0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<AuditChannel>::AddRef(__int64 a1)
{
  return ATL::CComObjectCached<AuditChannel>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000e030  sub     rcx, 8
0x18000e034  jmp     ?AddRef@?$CComObjectCached@VAuditChannel@@@ATL@@UEAAKXZ; ATL::CComObjectCached<AuditChannel>::AddRef(void)
```
