# _CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$1

- ea: `0x18001de15`
- end: `0x18001de21`
- name: `_CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007788`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::GetOwnershipSid_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return array_autoptr<unsigned short>::~array_autoptr<unsigned short>(a2 + 48);
}

```

## disassembly

```asm
0x18001de15  lea     rcx, [rdx+30h]
0x18001de1c  jmp     ??1?$array_autoptr@G@@UEAA@XZ; array_autoptr<ushort>::~array_autoptr<ushort>(void)
```
