# _SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$1

- ea: `0x18001192b`
- end: `0x180011937`
- name: `_SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002ed8`

## pseudocode

```c
void __fastcall SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Windows::Internal::String::~String((HSTRING *)(a2 + 120));
}

```

## disassembly

```asm
0x18001192b  lea     rcx, [rdx+78h]; this
0x180011932  jmp     ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
```
