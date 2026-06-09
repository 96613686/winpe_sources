# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xran(void)

- ea: `0x180002180`
- end: `0x180002191`
- name: `?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002198`
- `0x180002470`

## callees

- `0x180002154`

## pseudocode

```c
void __noreturn std::string::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180002180  sub     rsp, 28h
0x180002184  lea     rcx, aInvalidStringP
0x18000218b  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
