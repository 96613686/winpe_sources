# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x14000bcc8`
- end: `0x14000bcd9`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bcf8`
- `0x14000bdf0`
- `0x14000d96c`
- `0x14000fb30`
- `0x140016f88`
- `0x140017908`

## callees

- `0x140002230`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000bcc8  sub     rsp, 28h
0x14000bccc  lea     rcx, aStringTooLong; "string too long"
0x14000bcd3  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
