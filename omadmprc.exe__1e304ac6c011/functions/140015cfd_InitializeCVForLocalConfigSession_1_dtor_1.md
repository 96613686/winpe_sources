# _InitializeCVForLocalConfigSession_::_1_::dtor$1

- ea: `0x140015cfd`
- end: `0x140015d09`
- name: `_InitializeCVForLocalConfigSession_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002968`

## pseudocode

```c
void InitializeCVForLocalConfigSession_::_1_::dtor_1()
{
  Init_thread_abort(&dword_1400242F8);
}

```

## disassembly

```asm
0x140015cfd  lea     rcx, dword_1400242F8
0x140015d04  jmp     _Init_thread_abort
```
