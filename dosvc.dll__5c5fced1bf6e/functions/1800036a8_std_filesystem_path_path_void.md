# std::filesystem::path::~path(void)

- ea: `0x1800036a8`
- end: `0x1800036ad`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(std::filesystem::path *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a760`
- `0x18000a780`
- `0x18000a7e0`
- `0x18000a800`
- `0x18000a820`
- `0x18000a940`
- `0x18000a980`
- `0x18000ab1f`
- `0x18000ab55`
- `0x18000ab6b`
- `0x18000ab81`

## callees

- `0x1800036b4`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(std::filesystem::path *this)
{
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x1800036a8  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
