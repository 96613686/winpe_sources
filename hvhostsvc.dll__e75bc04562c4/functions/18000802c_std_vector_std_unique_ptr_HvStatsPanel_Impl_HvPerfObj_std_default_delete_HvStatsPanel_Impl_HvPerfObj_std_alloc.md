# std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>::_Xlength(void)

- ea: `0x18000802c`
- end: `0x18000803e`
- name: `?_Xlength@?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006b68`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008037`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008037`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x18000802c  sub     rsp, 28h
0x180008030  lea     rcx, aVectorTooLong; "vector too long"
0x180008037  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
