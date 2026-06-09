# std::_Xlen_string(void)

- ea: `0x1800156c8`
- end: `0x1800156da`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180005ef0`
- `0x180005fa4`
- `0x1800060e4`
- `0x180006e1c`
- `0x18001e794`
- `0x18001e88c`
- `0x18001e9a8`
- `0x18001eaac`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800156d3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800156d3`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1800156c8  sub     rsp, 28h
0x1800156cc  lea     rcx, aStringTooLong; "string too long"
0x1800156d3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
