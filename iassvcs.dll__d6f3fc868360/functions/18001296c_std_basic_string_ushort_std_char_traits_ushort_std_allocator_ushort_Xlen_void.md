# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x18001296c`
- end: `0x18001297d`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001299c`
- `0x180012a94`
- `0x1800137e8`

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
0x18001296c  sub     rsp, 28h
0x180012970  lea     rcx, aStringTooLong
0x180012977  call    ?_Xlength_error@std@@YAXPEBD@Z
```
