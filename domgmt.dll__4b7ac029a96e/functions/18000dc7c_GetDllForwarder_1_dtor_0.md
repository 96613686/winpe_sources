# _GetDllForwarder_::_1_::dtor$0

- ea: `0x18000dc7c`
- end: `0x18000dc88`
- name: `_GetDllForwarder_::_1_::dtor$0`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002110`

## pseudocode

```c
__int64 GetDllForwarder_::_1_::dtor_0()
{
  return Init_thread_abort(&dword_1800188D8);
}

```

## disassembly

```asm
0x18000dc7c  lea     rcx, dword_1800188D8
0x18000dc83  jmp     _Init_thread_abort
```
