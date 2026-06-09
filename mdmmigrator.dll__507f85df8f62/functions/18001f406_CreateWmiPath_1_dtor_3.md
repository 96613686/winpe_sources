# _CreateWmiPath_::_1_::dtor$3

- ea: `0x18001f406`
- end: `0x18001f412`
- name: `_CreateWmiPath_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007720`

## pseudocode

```c
void __fastcall CreateWmiPath_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::wstring::~wstring((char **)(a2 + 112));
}

```

## disassembly

```asm
0x18001f406  lea     rcx, [rdx+70h]; void *
0x18001f40d  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
