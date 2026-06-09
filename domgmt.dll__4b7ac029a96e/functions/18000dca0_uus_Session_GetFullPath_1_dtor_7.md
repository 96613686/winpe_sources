# _uus::Session::GetFullPath_::_1_::dtor$7

- ea: `0x18000dca0`
- end: `0x18000dcac`
- name: `_uus::Session::GetFullPath_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008ee8`

## pseudocode

```c
void __fastcall uus::Session::GetFullPath_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((char **)(a2 + 104));
}

```

## disassembly

```asm
0x18000dca0  lea     rcx, [rdx+68h]; this
0x18000dca7  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
