# _SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$2

- ea: `0x18001193d`
- end: `0x180011949`
- name: `_SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002ed8`

## pseudocode

```c
void __fastcall SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Windows::Internal::String::~String((HSTRING *)(a2 + 112));
}

```

## disassembly

```asm
0x18001193d  lea     rcx, [rdx+70h]; this
0x180011944  jmp     ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
```
