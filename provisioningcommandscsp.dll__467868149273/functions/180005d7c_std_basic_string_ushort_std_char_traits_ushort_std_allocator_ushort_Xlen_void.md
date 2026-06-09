# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180005d7c`
- end: `0x180005d94`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002cbc`
- `0x180007c54`
- `0x180007d54`
- `0x180007e9c`
- `0x180007fac`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005d87`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005d87`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180005d7c  sub     rsp, 28h
0x180005d80  lea     rcx, aStringTooLong; "string too long"
0x180005d87  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
