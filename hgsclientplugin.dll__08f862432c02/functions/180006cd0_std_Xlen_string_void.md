# std::_Xlen_string(void)

- ea: `0x180006cd0`
- end: `0x180006ce2`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005e18`
- `0x180005f34`
- `0x180008a90`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006cdb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006cdb`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180006cd0  sub     rsp, 28h
0x180006cd4  lea     rcx, aStringTooLong; "string too long"
0x180006cdb  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
