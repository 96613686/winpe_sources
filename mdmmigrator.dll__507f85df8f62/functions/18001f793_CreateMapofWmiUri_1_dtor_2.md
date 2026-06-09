# _CreateMapofWmiUri_::_1_::dtor$2

- ea: `0x18001f793`
- end: `0x18001f79f`
- name: `_CreateMapofWmiUri_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007720`

## pseudocode

```c
void __fastcall CreateMapofWmiUri_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::wstring::~wstring((char **)(a2 + 304));
}

```

## disassembly

```asm
0x18001f793  lea     rcx, [rdx+130h]; void *
0x18001f79a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
