# _uus::Session::GetFullPath_::_1_::dtor$1

- ea: `0x18000dc8e`
- end: `0x18000dc9a`
- name: `_uus::Session::GetFullPath_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008ee8`

## pseudocode

```c
void __fastcall uus::Session::GetFullPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((char **)(a2 + 72));
}

```

## disassembly

```asm
0x18000dc8e  lea     rcx, [rdx+48h]; this
0x18000dc95  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
