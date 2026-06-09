# _CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$3

- ea: `0x18001de39`
- end: `0x18001de45`
- name: `_CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007788`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::GetOwnershipSid_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return array_autoptr<unsigned short>::~array_autoptr<unsigned short>(a2 + 72);
}

```

## disassembly

```asm
0x18001de39  lea     rcx, [rdx+48h]
0x18001de40  jmp     ??1?$array_autoptr@G@@UEAA@XZ; array_autoptr<ushort>::~array_autoptr<ushort>(void)
```
