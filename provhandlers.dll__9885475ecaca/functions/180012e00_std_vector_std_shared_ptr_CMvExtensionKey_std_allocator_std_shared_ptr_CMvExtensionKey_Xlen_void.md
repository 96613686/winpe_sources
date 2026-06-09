# std::vector<std::shared_ptr<CMvExtensionKey>,std::allocator<std::shared_ptr<CMvExtensionKey>>>::_Xlen(void)

- ea: `0x180012e00`
- end: `0x180012e12`
- name: `?_Xlen@?$vector@V?$shared_ptr@VCMvExtensionKey@@@std@@V?$allocator@V?$shared_ptr@VCMvExtensionKey@@@std@@@2@@std@@IEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `15`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800114a0`
- `0x180012c70`
- `0x180012d04`
- `0x180014b20`
- `0x180024ad4`
- `0x180024c50`
- `0x180024e34`
- `0x1800308d0`
- `0x180037274`
- `0x18003831c`
- `0x180038498`
- `0x180038554`
- `0x18003b1e0`
- `0x18003b2d0`
- `0x18003b3b8`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012e0b`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012e0b`

## pseudocode

```c
void __noreturn std::vector<std::shared_ptr<CMvExtensionKey>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x180012e00  sub     rsp, 28h
0x180012e04  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x180012e0b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
