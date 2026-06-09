# [thunk]:ATL::CComObject<AuditChannel>::AddRef`adjustor{8}' (void)

- ea: `0x18000df80`
- end: `0x18000df89`
- name: `?AddRef@?$CComObject@VAuditChannel@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000df50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<AuditChannel>::AddRef(__int64 a1)
{
  return ATL::CComObject<AuditChannel>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000df80  sub     rcx, 8
0x18000df84  jmp     ?AddRef@?$CComObject@VAuditChannel@@@ATL@@UEAAKXZ; ATL::CComObject<AuditChannel>::AddRef(void)
```
