# std::_Xlen_string(void)

- ea: `0x18000aa3c`
- end: `0x18000aa4e`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180007414`
- `0x180007504`
- `0x18000773c`
- `0x180007834`
- `0x1800079a8`
- `0x180007ae8`
- `0x180007c50`
- `0x180007da4`
- `0x180007ec0`
- `0x180007ff8`
- `0x1800081ec`
- `0x180008a68`
- `0x18000c06c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000aa47`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000aa47`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000aa3c  sub     rsp, 28h
0x18000aa40  lea     rcx, aStringTooLong; "string too long"
0x18000aa47  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
