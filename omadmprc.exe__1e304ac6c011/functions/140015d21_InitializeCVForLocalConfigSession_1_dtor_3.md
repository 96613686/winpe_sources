# _InitializeCVForLocalConfigSession_::_1_::dtor$3

- ea: `0x140015d21`
- end: `0x140015d2d`
- name: `_InitializeCVForLocalConfigSession_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002968`

## pseudocode

```c
void InitializeCVForLocalConfigSession_::_1_::dtor_3()
{
  Init_thread_abort(&dword_1400242F4);
}

```

## disassembly

```asm
0x140015d21  lea     rcx, dword_1400242F4
0x140015d28  jmp     _Init_thread_abort
```
