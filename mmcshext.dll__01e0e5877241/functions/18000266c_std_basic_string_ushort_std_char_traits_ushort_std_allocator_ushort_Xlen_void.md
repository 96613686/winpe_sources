# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x18000266c`
- end: `0x18000267d`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000269c`
- `0x180002794`
- `0x180007eb4`
- `0x1800089f0`

## callees

- `0x180001370`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000266c  sub     rsp, 28h
0x180002670  lea     rcx, aStringTooLong
0x180002677  call    ?_Xlength_error@std@@YAXPEBD@Z
```
