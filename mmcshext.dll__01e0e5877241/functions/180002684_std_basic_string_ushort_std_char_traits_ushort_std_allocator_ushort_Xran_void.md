# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180002684`
- end: `0x180002695`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000269c`
- `0x180002970`
- `0x1800089f0`

## callees

- `0x18000139c`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180002684  sub     rsp, 28h
0x180002688  lea     rcx, aInvalidStringP
0x18000268f  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
