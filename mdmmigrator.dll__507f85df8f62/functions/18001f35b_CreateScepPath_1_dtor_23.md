# _CreateScepPath_::_1_::dtor$23

- ea: `0x18001f35b`
- end: `0x18001f367`
- name: `_CreateScepPath_::_1_::dtor$23`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007720`

## pseudocode

```c
void __fastcall CreateScepPath_::_1_::dtor_23(__int64 a1, __int64 a2)
{
  std::wstring::~wstring((char **)(a2 + 216));
}

```

## disassembly

```asm
0x18001f35b  lea     rcx, [rdx+0D8h]; void *
0x18001f362  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
