# std::_Xlen_string(void)

- ea: `0x180008548`
- end: `0x18000855a`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000805c`
- `0x1800085a0`
- `0x1800086a0`
- `0x180010630`
- `0x180010a00`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008553`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008553`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180008548  sub     rsp, 28h
0x18000854c  lea     rcx, aStringTooLong; "string too long"
0x180008553  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
