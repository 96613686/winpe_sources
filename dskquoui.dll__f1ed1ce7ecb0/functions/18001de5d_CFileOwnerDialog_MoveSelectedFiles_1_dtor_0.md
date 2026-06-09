# _CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor$0

- ea: `0x18001de5d`
- end: `0x18001de69`
- name: `_CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007874`

## pseudocode

```c
void __fastcall CFileOwnerDialog::MoveSelectedFiles_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DblNulTermList::~DblNulTermList((DblNulTermList *)(a2 + 96));
}

```

## disassembly

```asm
0x18001de5d  lea     rcx, [rdx+60h]; this
0x18001de64  jmp     ??1DblNulTermList@@QEAA@XZ; DblNulTermList::~DblNulTermList(void)
```
