# _SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$6

- ea: `0x180011985`
- end: `0x180011991`
- name: `_SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f80`

## pseudocode

```c
__int64 __fastcall SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(a2 + 144);
}

```

## disassembly

```asm
0x180011985  lea     rcx, [rdx+90h]
0x18001198c  jmp     ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
```
