# _uus::Session::GetFullPath_::_1_::dtor$0

- ea: `0x18000db0e`
- end: `0x18000db1a`
- name: `_uus::Session::GetFullPath_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008ee8`

## pseudocode

```c
void __fastcall uus::Session::GetFullPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((char **)(a2 + 136));
}

```

## disassembly

```asm
0x18000db0e  lea     rcx, [rdx+88h]; this
0x18000db15  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
