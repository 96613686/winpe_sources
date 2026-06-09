# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180005b8c`
- end: `0x180005b9e`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c74`
- `0x1800078c0`
- `0x1800079c0`
- `0x180007b08`
- `0x180007c18`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005b97`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005b97`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180005b8c  sub     rsp, 28h
0x180005b90  lea     rcx, aStringTooLong; "string too long"
0x180005b97  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
