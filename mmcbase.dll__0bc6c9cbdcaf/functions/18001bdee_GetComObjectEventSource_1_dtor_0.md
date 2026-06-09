# _GetComObjectEventSource_::_1_::dtor$0

- ea: `0x18001bdee`
- end: `0x18001bdfa`
- name: `_GetComObjectEventSource_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a184`

## pseudocode

```c
void GetComObjectEventSource_::_1_::dtor_0()
{
  Init_thread_abort(&dword_18002F928);
}

```

## disassembly

```asm
0x18001bdee  lea     rcx, dword_18002F928
0x18001bdf5  jmp     _Init_thread_abort
```
