# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x14000c078`
- end: `0x14000c089`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c0a8`
- `0x14000c1a0`
- `0x14000deac`
- `0x1400100fc`
- `0x140014cf8`
- `0x140015778`

## callees

- `0x140002250`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000c078  sub     rsp, 28h
0x14000c07c  lea     rcx, aStringTooLong; "string too long"
0x14000c083  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
