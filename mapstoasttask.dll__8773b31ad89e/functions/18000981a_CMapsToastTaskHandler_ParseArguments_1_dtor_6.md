# _CMapsToastTaskHandler::ParseArguments_::_1_::dtor$6

- ea: `0x18000981a`
- end: `0x18000982c`
- name: `_CMapsToastTaskHandler::ParseArguments_::_1_::dtor$6`
- size: `18`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180009825`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ParseArguments_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::basic_istream<unsigned short>::~basic_istream<unsigned short,std::char_traits<unsigned short>>(a2 + 120);
}

```

## disassembly

```asm
0x18000981a  lea     rcx, [rdx+60h]
0x180009821  add     rcx, 18h
0x180009825  jmp     cs:__imp_??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_istream<ushort>::~basic_istream<ushort,std::char_traits<ushort>>(void)
```
