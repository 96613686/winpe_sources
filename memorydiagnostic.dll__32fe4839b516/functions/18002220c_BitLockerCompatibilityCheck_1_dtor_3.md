# _BitLockerCompatibilityCheck_::_1_::dtor$3

- ea: `0x18002220c`
- end: `0x180022218`
- name: `_BitLockerCompatibilityCheck_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007858`

## pseudocode

```c
__int64 __fastcall BitLockerCompatibilityCheck_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 208);
}

```

## disassembly

```asm
0x18002220c  lea     rcx, [rdx+0D0h]
0x180022213  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
