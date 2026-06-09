# std::vector<std::vector<std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>,std::allocator<std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>>>,std::allocator<std::vector<std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>,std::allocator<std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>>>>>::_Xlength(void)

- ea: `0x18001329c`
- end: `0x1800132ae`
- name: `?_Xlength@?$vector@V?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@std@@V?$allocator@V?$vector@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@V?$allocator@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@2@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dd0c`
- `0x18001a3b4`
- `0x18001a508`
- `0x18001e244`
- `0x180021204`
- `0x180025290`
- `0x180025c78`
- `0x180025d04`
- `0x180026120`
- `0x180026224`
- `0x1800424d8`
- `0x180042614`
- `0x180042730`
- `0x180042864`
- `0x1800429d4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800132a7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800132a7`

## pseudocode

```c
void __noreturn std::vector<std::vector<std::unique_ptr<unsigned char [0]>>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x18001329c  sub     rsp, 28h
0x1800132a0  lea     rcx, aVectorTooLong; "vector too long"
0x1800132a7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
