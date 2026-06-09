# _COmaDmPrcLogger::GetLogger_::_1_::dtor$0

- ea: `0x140015c37`
- end: `0x140015c43`
- name: `_COmaDmPrcLogger::GetLogger_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002968`

## pseudocode

```c
void COmaDmPrcLogger::GetLogger_::_1_::dtor_0()
{
  Init_thread_abort(&dword_1400242F0);
}

```

## disassembly

```asm
0x140015c37  lea     rcx, dword_1400242F0
0x140015c3e  jmp     _Init_thread_abort
```
