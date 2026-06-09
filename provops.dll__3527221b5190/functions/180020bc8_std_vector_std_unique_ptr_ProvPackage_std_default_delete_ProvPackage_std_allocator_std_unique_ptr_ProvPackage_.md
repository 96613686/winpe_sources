# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::_Xlen(void)

- ea: `0x180020bc8`
- end: `0x180020bda`
- name: `?_Xlen@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b980`
- `0x18000bb14`
- `0x18000cc6c`
- `0x18000cd1c`
- `0x18000e8f4`
- `0x18000ea5c`
- `0x18001daa0`
- `0x18001f2c4`
- `0x18002066c`
- `0x180021edc`
- `0x180021fd0`
- `0x1800220c0`
- `0x180022da4`
- `0x180024f80`
- `0x180026068`
- `0x180028d48`
- `0x1800296a0`
- `0x18002a340`
- `0x18002b410`
- `0x18002f5dc`
- `0x18003348c`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180020bd3`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180020bd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn std::vector<std::unique_ptr<ProvPackage>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x180020bc8  sub     rsp, 28h
0x180020bcc  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x180020bd3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
