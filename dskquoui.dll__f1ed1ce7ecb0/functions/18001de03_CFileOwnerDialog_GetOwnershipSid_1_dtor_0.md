# _CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$0

- ea: `0x18001de03`
- end: `0x18001de0f`
- name: `_CFileOwnerDialog::GetOwnershipSid_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180011ea8`

## pseudocode

```c
void __fastcall CFileOwnerDialog::GetOwnershipSid_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWin32Handle::~CWin32Handle((CWin32Handle *)(a2 + 208));
}

```

## disassembly

```asm
0x18001de03  lea     rcx, [rdx+0D0h]; this
0x18001de0a  jmp     ??1CWin32Handle@@QEAA@XZ; CWin32Handle::~CWin32Handle(void)
```
