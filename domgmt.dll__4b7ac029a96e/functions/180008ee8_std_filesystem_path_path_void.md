# std::filesystem::path::~path(void)

- ea: `0x180008ee8`
- end: `0x180008eed`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(char **this)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000db0e`
- `0x18000db20`
- `0x18000db8c`
- `0x18000dba2`
- `0x18000dbb8`
- `0x18000dbca`
- `0x18000dbf6`
- `0x18000dc22`
- `0x18000dc58`
- `0x18000dc6a`
- `0x18000dc8e`
- `0x18000dca0`
- `0x18000dcb2`
- `0x18000dcc4`

## callees

- `0x180008d88`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(char **this)
{
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x180008ee8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
