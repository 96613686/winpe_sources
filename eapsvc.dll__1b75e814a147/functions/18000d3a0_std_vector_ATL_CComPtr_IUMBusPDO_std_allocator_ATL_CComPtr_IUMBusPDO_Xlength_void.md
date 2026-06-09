# std::vector<ATL::CComPtr<IUMBusPDO>,std::allocator<ATL::CComPtr<IUMBusPDO>>>::_Xlength(void)

- ea: `0x18000d3a0`
- end: `0x18000d3b2`
- name: `?_Xlength@?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000c880`
- `0x18001100c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d3ab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d3ab`

## pseudocode

```c
void __noreturn std::vector<ATL::CComPtr<IUMBusPDO>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x18000d3a0  sub     rsp, 28h
0x18000d3a4  lea     rcx, aVectorTooLong; "vector too long"
0x18000d3ab  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
