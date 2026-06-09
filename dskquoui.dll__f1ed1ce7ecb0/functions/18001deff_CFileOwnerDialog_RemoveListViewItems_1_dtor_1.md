# _CFileOwnerDialog::RemoveListViewItems_::_1_::dtor$1

- ea: `0x18001deff`
- end: `0x18001df0b`
- name: `_CFileOwnerDialog::RemoveListViewItems_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007800`

## pseudocode

```c
void __fastcall CFileOwnerDialog::RemoveListViewItems_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CAutoSetRedraw::~CAutoSetRedraw((CAutoSetRedraw *)(a2 + 200));
}

```

## disassembly

```asm
0x18001deff  lea     rcx, [rdx+0C8h]; this
0x18001df06  jmp     ??1CAutoSetRedraw@@QEAA@XZ; CAutoSetRedraw::~CAutoSetRedraw(void)
```
