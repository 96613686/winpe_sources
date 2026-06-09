# _BitLockerCompatibilityCheck_::_1_::dtor$2

- ea: `0x1800221fa`
- end: `0x180022206`
- name: `_BitLockerCompatibilityCheck_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007858`

## pseudocode

```c
__int64 __fastcall BitLockerCompatibilityCheck_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 144);
}

```

## disassembly

```asm
0x1800221fa  lea     rcx, [rdx+90h]
0x180022201  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
