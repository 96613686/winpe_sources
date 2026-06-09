# [thunk]:ATL::CComObject<AuditChannel>::Release`adjustor{8}' (void)

- ea: `0x180011c60`
- end: `0x180011c69`
- name: `?Release@?$CComObject@VAuditChannel@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011bd0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<AuditChannel>::Release(__int64 a1)
{
  return ATL::CComObject<AuditChannel>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180011c60  sub     rcx, 8
0x180011c64  jmp     ?Release@?$CComObject@VAuditChannel@@@ATL@@UEAAKXZ; ATL::CComObject<AuditChannel>::Release(void)
```
