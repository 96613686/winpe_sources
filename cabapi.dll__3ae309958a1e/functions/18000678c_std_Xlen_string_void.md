# std::_Xlen_string(void)

- ea: `0x18000678c`
- end: `0x18000679d`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e54`
- `0x180002f70`
- `0x180007e88`
- `0x180007fd0`
- `0x18000ab80`
- `0x18000c7a4`
- `0x18000f83c`

## callees

- `0x180007b0c`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000678c  sub     rsp, 28h
0x180006790  lea     rcx, aStringTooLong; "string too long"
0x180006797  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
