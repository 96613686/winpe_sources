# std::_Xlen_string(void)

- ea: `0x1800063dc`
- end: `0x1800063ee`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020a4`
- `0x1800021e4`
- `0x1800044a8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800063e7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800063e7`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1800063dc  sub     rsp, 28h
0x1800063e0  lea     rcx, aStringTooLong; "string too long"
0x1800063e7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
