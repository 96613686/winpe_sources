# _IsNewCommandLine_::_1_::dtor$0

- ea: `0x140014b2b`
- end: `0x140014b37`
- name: `_IsNewCommandLine_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008414`

## pseudocode

```c
void __fastcall IsNewCommandLine_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  NewCommandLineOptions::~NewCommandLineOptions((NewCommandLineOptions *)(a2 + 64));
}

```

## disassembly

```asm
0x140014b2b  lea     rcx, [rdx+40h]; this
0x140014b32  jmp     ??1NewCommandLineOptions@@QEAA@XZ; NewCommandLineOptions::~NewCommandLineOptions(void)
```
