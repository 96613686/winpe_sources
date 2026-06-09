# _CreateMapofWmiUri_::_1_::dtor$28

- ea: `0x18001f7b7`
- end: `0x18001f7c3`
- name: `_CreateMapofWmiUri_::_1_::dtor$28`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007720`

## pseudocode

```c
void __fastcall CreateMapofWmiUri_::_1_::dtor_28(__int64 a1, __int64 a2)
{
  std::wstring::~wstring(*(char ***)(a2 + 336));
}

```

## disassembly

```asm
0x18001f7b7  mov     rcx, [rdx+150h]; void *
0x18001f7be  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
