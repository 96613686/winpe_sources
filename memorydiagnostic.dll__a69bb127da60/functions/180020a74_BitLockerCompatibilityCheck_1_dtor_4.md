# _BitLockerCompatibilityCheck_::_1_::dtor$4

- ea: `0x180020a74`
- end: `0x180020a80`
- name: `_BitLockerCompatibilityCheck_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007818`

## pseudocode

```c
__int64 __fastcall BitLockerCompatibilityCheck_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 136));
}

```

## disassembly

```asm
0x180020a74  lea     rcx, [rdx+88h]
0x180020a7b  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
