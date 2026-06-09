# _CFileOwnerDialog::CompareLVItems_::_1_::dtor$0

- ea: `0x18001dd85`
- end: `0x18001dd91`
- name: `_CFileOwnerDialog::CompareLVItems_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
__int64 CFileOwnerDialog::CompareLVItems_::_1_::dtor_0()
{
  return Init_thread_abort(&dword_1800286A0);
}

```

## disassembly

```asm
0x18001dd85  lea     rcx, dword_1800286A0
0x18001dd8c  jmp     _Init_thread_abort
```
