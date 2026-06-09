# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180002f60`
- end: `0x180002f71`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002474`
- `0x180002f78`
- `0x1800031b0`
- `0x180003480`
- `0x1800066a0`
- `0x18000c7c8`
- `0x18000c8d8`

## callees

- `0x18000156c`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180002f60  sub     rsp, 28h
0x180002f64  lea     rcx, aInvalidStringP
0x180002f6b  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
