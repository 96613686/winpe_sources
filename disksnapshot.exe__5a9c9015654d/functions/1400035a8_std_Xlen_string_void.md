# std::_Xlen_string(void)

- ea: `0x1400035a8`
- end: `0x1400035ba`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002c84`
- `0x140002d90`
- `0x1400052b0`
- `0x14000ae5c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400035b3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400035b3`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1400035a8  sub     rsp, 28h
0x1400035ac  lea     rcx, aStringTooLong; "string too long"
0x1400035b3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
