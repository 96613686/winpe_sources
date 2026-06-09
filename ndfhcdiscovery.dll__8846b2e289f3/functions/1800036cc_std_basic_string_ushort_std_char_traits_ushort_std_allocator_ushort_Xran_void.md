# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x1800036cc`
- end: `0x1800036dd`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036e4`
- `0x180003aa0`
- `0x18000a418`
- `0x18000ae64`

## callees

- `0x1800014dc`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x1800036cc  sub     rsp, 28h
0x1800036d0  lea     rcx, aInvalidStringP
0x1800036d7  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
