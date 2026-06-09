# _CFileOwnerDialog::CompareLVItems_::_1_::dtor$1

- ea: `0x18001dd97`
- end: `0x18001dda3`
- name: `_CFileOwnerDialog::CompareLVItems_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
__int64 CFileOwnerDialog::CompareLVItems_::_1_::dtor_1()
{
  return Init_thread_abort(&dword_1800286B8);
}

```

## disassembly

```asm
0x18001dd97  lea     rcx, dword_1800286B8
0x18001dd9e  jmp     _Init_thread_abort
```
