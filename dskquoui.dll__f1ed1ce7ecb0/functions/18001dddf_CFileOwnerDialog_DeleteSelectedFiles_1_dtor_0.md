# _CFileOwnerDialog::DeleteSelectedFiles_::_1_::dtor$0

- ea: `0x18001dddf`
- end: `0x18001ddeb`
- name: `_CFileOwnerDialog::DeleteSelectedFiles_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007874`

## pseudocode

```c
void __fastcall CFileOwnerDialog::DeleteSelectedFiles_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DblNulTermList::~DblNulTermList((DblNulTermList *)(a2 + 32));
}

```

## disassembly

```asm
0x18001dddf  lea     rcx, [rdx+20h]; this
0x18001dde6  jmp     ??1DblNulTermList@@QEAA@XZ; DblNulTermList::~DblNulTermList(void)
```
