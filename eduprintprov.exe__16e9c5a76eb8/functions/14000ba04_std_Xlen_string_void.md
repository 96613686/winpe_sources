# std::_Xlen_string(void)

- ea: `0x14000ba04`
- end: `0x14000ba16`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14000452c`
- `0x14000466c`
- `0x14000c318`
- `0x14000cc6c`
- `0x14000e440`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000ba0f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000ba0f`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000ba04  sub     rsp, 28h
0x14000ba08  lea     rcx, aStringTooLong; "string too long"
0x14000ba0f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
