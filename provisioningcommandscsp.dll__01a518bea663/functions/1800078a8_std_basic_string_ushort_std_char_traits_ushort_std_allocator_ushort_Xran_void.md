# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x1800078a8`
- end: `0x1800078ba`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800078c0`
- `0x180007b08`
- `0x180007d98`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800078b3`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800078b3`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
  JUMPOUT(0x1800078B9LL);
}

```

## disassembly

```asm
0x1800078a8  sub     rsp, 28h
0x1800078ac  lea     rcx, aInvalidStringP; "invalid string position"
0x1800078b3  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
