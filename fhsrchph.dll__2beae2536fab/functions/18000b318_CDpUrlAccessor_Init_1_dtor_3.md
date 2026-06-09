# _CDpUrlAccessor::Init_::_1_::dtor$3

- ea: `0x18000b318`
- end: `0x18000b324`
- name: `_CDpUrlAccessor::Init_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ffc`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::Init_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 128);
}

```

## disassembly

```asm
0x18000b318  lea     rcx, [rdx+80h]
0x18000b31f  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
