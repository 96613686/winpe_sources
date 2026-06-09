# _CMapsToastTaskHandler::ParseArguments_::_1_::dtor$8

- ea: `0x180009832`
- end: `0x180009840`
- name: `_CMapsToastTaskHandler::ParseArguments_::_1_::dtor$8`
- size: `14`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180009839`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ParseArguments_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::basic_streambuf<unsigned short>::~basic_streambuf<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)(a2 + 336));
}

```

## disassembly

```asm
0x180009832  mov     rcx, [rdx+150h]
0x180009839  jmp     cs:__imp_??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_streambuf<ushort>::~basic_streambuf<ushort,std::char_traits<ushort>>(void)
```
