# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180008e14`
- end: `0x180008e25`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a10`
- `0x180006b24`
- `0x180008e44`
- `0x180008f44`

## callees

- `0x1800012d8`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180008e14  sub     rsp, 28h
0x180008e18  lea     rcx, aStringTooLong
0x180008e1f  call    ?_Xlength_error@std@@YAXPEBD@Z
```
