# _NGenParser::IsCommandLineOption_::_1_::dtor$1

- ea: `0x140013ffe`
- end: `0x14001400a`
- name: `_NGenParser::IsCommandLineOption_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001354`

## pseudocode

```c
void __fastcall NGenParser::IsCommandLineOption_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  SString::AbstractScratchBuffer::~AbstractScratchBuffer((void **)(a2 + 5584));
}

```

## disassembly

```asm
0x140013ffe  lea     rcx, [rdx+15D0h]; this
0x140014005  jmp     ??1AbstractScratchBuffer@SString@@QEAA@XZ; SString::AbstractScratchBuffer::~AbstractScratchBuffer(void)
```
