# _BitLockerCompatibilityCheck_::_1_::dtor$2

- ea: `0x180020a50`
- end: `0x180020a5c`
- name: `_BitLockerCompatibilityCheck_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007818`

## pseudocode

```c
__int64 __fastcall BitLockerCompatibilityCheck_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 104));
}

```

## disassembly

```asm
0x180020a50  lea     rcx, [rdx+68h]
0x180020a57  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
