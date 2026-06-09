# _AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$8

- ea: `0x140011b0d`
- end: `0x140011b1f`
- name: `_AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$8`
- size: `18`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011b18`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(a2 + 304);
}

```

## disassembly

```asm
0x140011b0d  lea     rcx, [rdx+110h]
0x140011b14  add     rcx, 20h ; ' '
0x140011b18  jmp     cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
```
