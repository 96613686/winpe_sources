# std::_Xlen_string(void)

- ea: `0x1800163d4`
- end: `0x1800163ec`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `24`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180005c80`
- `0x180005d4c`
- `0x180005e94`
- `0x180006ec4`
- `0x18001fb4c`
- `0x18001fc48`
- `0x18001fd80`
- `0x18001fedc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800163df`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800163df`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1800163d4  sub     rsp, 28h
0x1800163d8  lea     rcx, aStringTooLong; "string too long"
0x1800163df  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
