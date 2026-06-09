# _CreateMapofWmiUri_::_1_::dtor$1

- ea: `0x18001f781`
- end: `0x18001f78d`
- name: `_CreateMapofWmiUri_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000dd30`

## pseudocode

```c
__int64 __fastcall CreateMapofWmiUri_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(a2 + 48);
}

```

## disassembly

```asm
0x18001f781  lea     rcx, [rdx+30h]
0x18001f788  jmp     ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
```
