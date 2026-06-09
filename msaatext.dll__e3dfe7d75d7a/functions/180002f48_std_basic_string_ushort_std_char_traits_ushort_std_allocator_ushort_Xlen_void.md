# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180002f48`
- end: `0x180002f59`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dcc`
- `0x180002f78`
- `0x180003078`
- `0x1800031b0`
- `0x1800032a8`
- `0x1800036c0`
- `0x180005424`
- `0x18000c7c8`

## callees

- `0x180001540`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180002f48  sub     rsp, 28h
0x180002f4c  lea     rcx, aStringTooLong
0x180002f53  call    ?_Xlength_error@std@@YAXPEBD@Z
```
