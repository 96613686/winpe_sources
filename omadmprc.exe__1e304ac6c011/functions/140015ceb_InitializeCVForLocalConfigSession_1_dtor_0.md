# _InitializeCVForLocalConfigSession_::_1_::dtor$0

- ea: `0x140015ceb`
- end: `0x140015cf7`
- name: `_InitializeCVForLocalConfigSession_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002968`

## pseudocode

```c
void InitializeCVForLocalConfigSession_::_1_::dtor_0()
{
  Init_thread_abort(&dword_140024300);
}

```

## disassembly

```asm
0x140015ceb  lea     rcx, dword_140024300
0x140015cf2  jmp     _Init_thread_abort
```
