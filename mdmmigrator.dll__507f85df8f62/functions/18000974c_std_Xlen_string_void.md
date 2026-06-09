# std::_Xlen_string(void)

- ea: `0x18000974c`
- end: `0x18000975e`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180007b38`
- `0x180007c94`
- `0x180007f40`
- `0x180009cb4`
- `0x18000cc28`
- `0x18000d1b0`
- `0x18000d2a8`
- `0x18000d3c4`
- `0x180010864`
- `0x180011610`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009757`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009757`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000974c  sub     rsp, 28h
0x180009750  lea     rcx, aStringTooLong; "string too long"
0x180009757  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
