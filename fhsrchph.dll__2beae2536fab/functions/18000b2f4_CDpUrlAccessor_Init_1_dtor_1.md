# _CDpUrlAccessor::Init_::_1_::dtor$1

- ea: `0x18000b2f4`
- end: `0x18000b300`
- name: `_CDpUrlAccessor::Init_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ffc`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::Init_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 208);
}

```

## disassembly

```asm
0x18000b2f4  lea     rcx, [rdx+0D0h]
0x18000b2fb  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
