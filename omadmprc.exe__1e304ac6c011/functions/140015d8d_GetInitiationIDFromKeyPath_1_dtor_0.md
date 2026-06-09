# _GetInitiationIDFromKeyPath_::_1_::dtor$0

- ea: `0x140015d8d`
- end: `0x140015d99`
- name: `_GetInitiationIDFromKeyPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000edb4`

## pseudocode

```c
__int64 __fastcall GetInitiationIDFromKeyPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x140015d8d  mov     rcx, [rdx+30h]
0x140015d94  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
