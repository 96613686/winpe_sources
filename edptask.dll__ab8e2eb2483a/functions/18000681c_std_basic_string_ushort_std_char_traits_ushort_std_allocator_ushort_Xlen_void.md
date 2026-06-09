# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x18000681c`
- end: `0x18000682d`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000684c`
- `0x180006944`
- `0x180007cb4`
- `0x1800123a0`

## callees

- `0x1800015d0`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000681c  sub     rsp, 28h
0x180006820  lea     rcx, aStringTooLong
0x180006827  call    ?_Xlength_error@std@@YAXPEBD@Z
```
