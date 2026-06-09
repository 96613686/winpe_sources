# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::_Xlen(void)

- ea: `0x18000fd40`
- end: `0x18000fd58`
- name: `?_Xlen@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEBAXXZ`
- size: `24`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fbb4`
- `0x18000fc30`
- `0x1800287dc`
- `0x1800293a8`
- `0x180029550`
- `0x18002a6fc`
- `0x18002ad68`
- `0x18002d0d4`
- `0x18002f038`
- `0x180030ed4`
- `0x180030fc4`
- `0x1800310b4`
- `0x180031818`
- `0x1800318b8`
- `0x1800322c0`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fd4b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fd4b`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<ProvPackage>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x18000fd40  sub     rsp, 28h
0x18000fd44  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x18000fd4b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
