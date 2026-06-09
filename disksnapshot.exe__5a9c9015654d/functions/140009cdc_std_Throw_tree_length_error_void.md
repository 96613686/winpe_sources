# std::_Throw_tree_length_error(void)

- ea: `0x140009cdc`
- end: `0x140009cee`
- name: `?_Throw_tree_length_error@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000549c`
- `0x14000588c`
- `0x140006424`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009ce7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009ce7`

## pseudocode

```c
void __noreturn std::_Throw_tree_length_error(void)
{
  std::_Xlength_error("map/set too long");
}

```

## disassembly

```asm
0x140009cdc  sub     rsp, 28h
0x140009ce0  lea     rcx, aMapSetTooLong; "map/set too long"
0x140009ce7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
