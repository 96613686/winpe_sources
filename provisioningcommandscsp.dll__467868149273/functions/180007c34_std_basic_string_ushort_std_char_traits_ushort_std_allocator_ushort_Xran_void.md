# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180007c34`
- end: `0x180007c4c`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c54`
- `0x180007e9c`
- `0x180008140`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180007c3f`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180007c3f`

## pseudocode

```c
void std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
  __debugbreak();
  JUMPOUT(0x180007C4CLL);
}

```

## disassembly

```asm
0x180007c34  sub     rsp, 28h
0x180007c38  lea     rcx, aInvalidStringP; "invalid string position"
0x180007c3f  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180007c46  nop     dword ptr [rax+rax+00h]
0x180007c4b  int     3; Trap to Debugger
```
