# _CFileOwnerDialog::OnCommand_::_1_::dtor$0

- ea: `0x18001dea5`
- end: `0x18001deb1`
- name: `_CFileOwnerDialog::OnCommand_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007800`

## pseudocode

```c
void __fastcall CFileOwnerDialog::OnCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoSetRedraw::~CAutoSetRedraw((CAutoSetRedraw *)(a2 + 232));
}

```

## disassembly

```asm
0x18001dea5  lea     rcx, [rdx+0E8h]; this
0x18001deac  jmp     ??1CAutoSetRedraw@@QEAA@XZ; CAutoSetRedraw::~CAutoSetRedraw(void)
```
