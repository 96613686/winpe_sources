# [thunk]:ATL::CComObjectCached<AuditChannel>::Release`adjustor{8}' (void)

- ea: `0x180011de0`
- end: `0x180011de9`
- name: `?Release@?$CComObjectCached@VAuditChannel@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011d30`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<AuditChannel>::Release(__int64 a1)
{
  return ATL::CComObjectCached<AuditChannel>::Release((char *)(a1 - 8));
}

```

## disassembly

```asm
0x180011de0  sub     rcx, 8; Block
0x180011de4  jmp     ?Release@?$CComObjectCached@VAuditChannel@@@ATL@@UEAAKXZ; ATL::CComObjectCached<AuditChannel>::Release(void)
```
