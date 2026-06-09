# _CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$4

- ea: `0x18001de27`
- end: `0x18001de33`
- name: `_CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007788`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::GetOwnershipSid_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return array_autoptr<unsigned short>::~array_autoptr<unsigned short>(a2 + 120);
}

```

## disassembly

```asm
0x18001de27  lea     rcx, [rdx+78h]
0x18001de2e  jmp     ??1?$array_autoptr@G@@UEAA@XZ; array_autoptr<ushort>::~array_autoptr<ushort>(void)
```
