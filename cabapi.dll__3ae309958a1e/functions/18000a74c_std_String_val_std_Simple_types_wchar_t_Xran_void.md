# std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)

- ea: `0x18000a74c`
- end: `0x18000a75d`
- name: `?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008d80`
- `0x180008fd8`
- `0x18000bcac`
- `0x18000c060`

## callees

- `0x180007b38`

## pseudocode

```c
void __noreturn std::_String_val<std::_Simple_types<wchar_t>>::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x18000a74c  sub     rsp, 28h
0x18000a750  lea     rcx, aInvalidStringP
0x18000a757  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
