# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180004b70`
- end: `0x180004b81`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ba0`
- `0x180004c98`
- `0x180005ff0`
- `0x180006100`
- `0x180007818`
- `0x1800092b8`

## callees

- `0x180001260`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180004b70  sub     rsp, 28h
0x180004b74  lea     rcx, aStringTooLong
0x180004b7b  call    ?_Xlength_error@std@@YAXPEBD@Z
```
