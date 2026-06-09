# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x1800036b4`
- end: `0x1800036c5`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036e4`
- `0x1800037dc`
- `0x18000a418`
- `0x18000a528`

## callees

- `0x1800014b0`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1800036b4  sub     rsp, 28h
0x1800036b8  lea     rcx, aStringTooLong
0x1800036bf  call    ?_Xlength_error@std@@YAXPEBD@Z
```
