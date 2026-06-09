# _GetUserSIDString_::_1_::dtor$0

- ea: `0x18000b3ee`
- end: `0x18000b3fa`
- name: `_GetUserSIDString_::_1_::dtor$0`
- size: `12`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180006904`

## pseudocode

```c
int __fastcall GetUserSIDString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::unique_ptr<void,HandleDeleter>::~unique_ptr<void,HandleDeleter>((void **)(a2 + 168));
}

```

## disassembly

```asm
0x18000b3ee  lea     rcx, [rdx+0A8h]
0x18000b3f5  jmp     ??1?$unique_ptr@XUHandleDeleter@@@std@@QEAA@XZ; std::unique_ptr<void,HandleDeleter>::~unique_ptr<void,HandleDeleter>(void)
```
