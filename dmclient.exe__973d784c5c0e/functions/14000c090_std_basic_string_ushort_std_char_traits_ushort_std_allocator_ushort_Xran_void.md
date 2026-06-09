# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x14000c090`
- end: `0x14000c0a1`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c0a8`
- `0x14000c5c0`
- `0x1400100fc`
- `0x140015778`

## callees

- `0x14000227c`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x14000c090  sub     rsp, 28h
0x14000c094  lea     rcx, aInvalidStringP; "invalid string position"
0x14000c09b  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
