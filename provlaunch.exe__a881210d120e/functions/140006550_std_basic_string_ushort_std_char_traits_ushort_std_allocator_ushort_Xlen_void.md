# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x140006550`
- end: `0x140006562`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `18`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400031c8`
- `0x140008484`
- `0x14000951c`
- `0x14000961c`
- `0x14000972c`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000655b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000655b`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x140006550  sub     rsp, 28h
0x140006554  lea     rcx, aStringTooLong; "string too long"
0x14000655b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
