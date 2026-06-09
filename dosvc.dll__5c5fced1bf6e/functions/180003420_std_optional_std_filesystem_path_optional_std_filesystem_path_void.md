# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x180003420`
- end: `0x180003425`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a7a0`
- `0x18000a7c0`
- `0x18000ab31`

## callees

- `0x18000342c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::optional<std::filesystem::path>::~optional<std::filesystem::path>(__int64 a1)
{
  return std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(a1);
}

```

## disassembly

```asm
0x180003420  jmp     ??1?$_Optional_destruct_base@Vpath@filesystem@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(void)
```
