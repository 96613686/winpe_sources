# std::_Xlen_string(void)

- ea: `0x140006d7c`
- end: `0x140006d8e`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000311c`
- `0x1400032b8`
- `0x140003438`
- `0x14000356c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006d87`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140006d87`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x140006d7c  sub     rsp, 28h
0x140006d80  lea     rcx, aStringTooLong; "string too long"
0x140006d87  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
