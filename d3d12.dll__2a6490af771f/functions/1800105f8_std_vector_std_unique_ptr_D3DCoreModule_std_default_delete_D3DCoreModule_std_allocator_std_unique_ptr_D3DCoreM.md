# std::vector<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>>::_Xlength(void)

- ea: `0x1800105f8`
- end: `0x18001060a`
- name: `?_Xlength@?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006ebc`
- `0x1800072cc`
- `0x180012344`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010603`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010603`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<D3DCoreModule>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x1800105f8  sub     rsp, 28h
0x1800105fc  lea     rcx, aVectorTooLong; "vector too long"
0x180010603  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
