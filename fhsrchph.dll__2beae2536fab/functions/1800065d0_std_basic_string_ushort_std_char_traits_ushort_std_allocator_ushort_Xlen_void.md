# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x1800065d0`
- end: `0x1800065e1`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006600`
- `0x1800067b4`
- `0x18000a52c`
- `0x18000a62c`

## callees

- `0x1800012b8`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1800065d0  sub     rsp, 28h
0x1800065d4  lea     rcx, aStringTooLong
0x1800065db  call    ?_Xlength_error@std@@YAXPEBD@Z
```
