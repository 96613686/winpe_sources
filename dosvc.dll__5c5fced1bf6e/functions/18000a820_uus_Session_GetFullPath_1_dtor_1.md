# _uus::Session::GetFullPath_::_1_::dtor$1

- ea: `0x18000a820`
- end: `0x18000a82c`
- name: `_uus::Session::GetFullPath_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800036a8`

## pseudocode

```c
void __fastcall uus::Session::GetFullPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((std::filesystem::path *)(a2 + 80));
}

```

## disassembly

```asm
0x18000a820  lea     rcx, [rdx+50h]; this
0x18000a827  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
