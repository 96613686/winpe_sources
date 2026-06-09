# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x14000bce0`
- end: `0x14000bcf1`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bcf8`
- `0x14000c120`
- `0x14000fb30`
- `0x140017908`

## callees

- `0x14000225c`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x14000bce0  sub     rsp, 28h
0x14000bce4  lea     rcx, aInvalidStringP; "invalid string position"
0x14000bceb  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
