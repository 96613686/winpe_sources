# _InitializeCVForLocalConfigSession_::_1_::dtor$2

- ea: `0x140015d0f`
- end: `0x140015d1b`
- name: `_InitializeCVForLocalConfigSession_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002968`

## pseudocode

```c
void InitializeCVForLocalConfigSession_::_1_::dtor_2()
{
  Init_thread_abort(&dword_1400242FC);
}

```

## disassembly

```asm
0x140015d0f  lea     rcx, dword_1400242FC
0x140015d16  jmp     _Init_thread_abort
```
