# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180004b88`
- end: `0x180004b99`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ba0`
- `0x180004e70`
- `0x180005ff0`
- `0x18000620c`
- `0x1800092b8`

## callees

- `0x18000128c`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180004b88  sub     rsp, 28h
0x180004b8c  lea     rcx, aInvalidStringP
0x180004b93  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
