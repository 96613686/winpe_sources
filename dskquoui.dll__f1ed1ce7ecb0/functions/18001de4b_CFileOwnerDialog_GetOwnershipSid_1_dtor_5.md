# _CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$5

- ea: `0x18001de4b`
- end: `0x18001de57`
- name: `_CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007788`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::GetOwnershipSid_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return array_autoptr<unsigned short>::~array_autoptr<unsigned short>(a2 + 96);
}

```

## disassembly

```asm
0x18001de4b  lea     rcx, [rdx+60h]
0x18001de52  jmp     ??1?$array_autoptr@G@@UEAA@XZ; array_autoptr<ushort>::~array_autoptr<ushort>(void)
```
