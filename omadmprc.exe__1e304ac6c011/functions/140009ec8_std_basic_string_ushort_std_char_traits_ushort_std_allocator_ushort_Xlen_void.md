# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x140009ec8`
- end: `0x140009ed9`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140009f24`
- `0x14000a01c`
- `0x14000ed04`
- `0x140014460`

## callees

- `0x140001e60`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x140009ec8  sub     rsp, 28h
0x140009ecc  lea     rcx, aStringTooLong; "string too long"
0x140009ed3  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
