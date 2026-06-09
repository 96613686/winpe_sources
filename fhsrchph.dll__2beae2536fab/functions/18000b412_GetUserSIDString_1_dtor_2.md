# _GetUserSIDString_::_1_::dtor$2

- ea: `0x18000b412`
- end: `0x18000b41e`
- name: `_GetUserSIDString_::_1_::dtor$2`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007c20`

## pseudocode

```c
HLOCAL __fastcall GetUserSIDString_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::unique_ptr<unsigned short,LocalFreeDeleter>::~unique_ptr<unsigned short,LocalFreeDeleter>((void **)(a2 + 160));
}

```

## disassembly

```asm
0x18000b412  lea     rcx, [rdx+0A0h]
0x18000b419  jmp     ??1?$unique_ptr@GULocalFreeDeleter@@@std@@QEAA@XZ; std::unique_ptr<ushort,LocalFreeDeleter>::~unique_ptr<ushort,LocalFreeDeleter>(void)
```
