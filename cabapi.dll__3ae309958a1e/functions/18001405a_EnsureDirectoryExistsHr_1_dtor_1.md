# _EnsureDirectoryExistsHr_::_1_::dtor$1

- ea: `0x18001405a`
- end: `0x180014066`
- name: `_EnsureDirectoryExistsHr_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800036b4`

## pseudocode

```c
void __fastcall EnsureDirectoryExistsHr_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 152);
}

```

## disassembly

```asm
0x18001405a  lea     rcx, [rdx+98h]
0x180014061  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
