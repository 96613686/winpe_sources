# _AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$2

- ea: `0x140011abe`
- end: `0x140011aca`
- name: `_AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140007044`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(a2 + 272);
}

```

## disassembly

```asm
0x140011abe  lea     rcx, [rdx+110h]
0x140011ac5  jmp     ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
```
