# _SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$8

- ea: `0x180011997`
- end: `0x1800119a3`
- name: `_SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002dfc`

## pseudocode

```c
__int64 __fastcall SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 432);
}

```

## disassembly

```asm
0x180011997  lea     rcx, [rdx+1B0h]
0x18001199e  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
