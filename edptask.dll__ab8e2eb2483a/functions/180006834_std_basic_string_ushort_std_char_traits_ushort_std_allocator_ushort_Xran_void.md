# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180006834`
- end: `0x180006845`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000684c`
- `0x180006be0`
- `0x1800123a0`

## callees

- `0x1800015fc`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180006834  sub     rsp, 28h
0x180006838  lea     rcx, aInvalidStringP
0x18000683f  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
