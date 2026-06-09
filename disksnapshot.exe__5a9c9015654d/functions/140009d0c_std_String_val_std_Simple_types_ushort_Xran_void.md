# std::_String_val<std::_Simple_types<ushort>>::_Xran(void)

- ea: `0x140009d0c`
- end: `0x140009d1e`
- name: `?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140008590`
- `0x14000a604`
- `0x14000ba74`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x140009d17`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x140009d17`

## pseudocode

```c
void __noreturn std::_String_val<std::_Simple_types<unsigned short>>::_Xran()
{
  std::_Xout_of_range("invalid string position");
  JUMPOUT(0x140009D1DLL);
}

```

## disassembly

```asm
0x140009d0c  sub     rsp, 28h
0x140009d10  lea     rcx, aInvalidStringP; "invalid string position"
0x140009d17  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
