# _CDeclaredConfigurationLogger::GetLogger_::_1_::dtor$0

- ea: `0x180011e11`
- end: `0x180011e1d`
- name: `_CDeclaredConfigurationLogger::GetLogger_::_1_::dtor$0`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800028a0`

## pseudocode

```c
__int64 CDeclaredConfigurationLogger::GetLogger_::_1_::dtor_0()
{
  return Init_thread_abort(&dword_18001BA10);
}

```

## disassembly

```asm
0x180011e11  lea     rcx, dword_18001BA10
0x180011e18  jmp     _Init_thread_abort
```
