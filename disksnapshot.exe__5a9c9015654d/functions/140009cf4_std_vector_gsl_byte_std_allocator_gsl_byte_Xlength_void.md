# std::vector<gsl::byte,std::allocator<gsl::byte>>::_Xlength(void)

- ea: `0x140009cf4`
- end: `0x140009d06`
- name: `?_Xlength@?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140004dc8`
- `0x140004fec`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009cff`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009cff`

## pseudocode

```c
void __noreturn std::vector<enum gsl::byte>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x140009cf4  sub     rsp, 28h
0x140009cf8  lea     rcx, aVectorTooLong; "vector too long"
0x140009cff  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
