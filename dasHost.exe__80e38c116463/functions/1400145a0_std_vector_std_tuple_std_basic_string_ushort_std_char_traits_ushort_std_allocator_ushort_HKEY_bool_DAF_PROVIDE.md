# std::vector<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>,std::allocator<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>>>::_Xlength(void)

- ea: `0x1400145a0`
- end: `0x1400145b2`
- name: `?_Xlength@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140011224`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400145ab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400145ab`

## pseudocode

```c
void __noreturn std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x1400145a0  sub     rsp, 28h
0x1400145a4  lea     rcx, aVectorTooLong; "vector too long"
0x1400145ab  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
