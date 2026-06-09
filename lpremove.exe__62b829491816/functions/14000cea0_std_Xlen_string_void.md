# std::_Xlen_string(void)

- ea: `0x14000cea0`
- end: `0x14000ceb2`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400042a4`
- `0x1400045d4`
- `0x140004718`
- `0x140004924`
- `0x14000e878`
- `0x14000e970`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000ceab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000ceab`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000cea0  sub     rsp, 28h
0x14000cea4  lea     rcx, aStringTooLong; "string too long"
0x14000ceab  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
