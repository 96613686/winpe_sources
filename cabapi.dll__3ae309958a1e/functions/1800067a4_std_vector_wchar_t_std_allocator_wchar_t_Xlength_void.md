# std::vector<wchar_t,std::allocator<wchar_t>>::_Xlength(void)

- ea: `0x1800067a4`
- end: `0x1800067b5`
- name: `?_Xlength@?$vector@_WV?$allocator@_W@std@@@std@@CAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003030`
- `0x180007b64`
- `0x18000acb0`
- `0x18000adf0`
- `0x18000da00`

## callees

- `0x180007b0c`

## pseudocode

```c
void __noreturn std::vector<wchar_t>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x1800067a4  sub     rsp, 28h
0x1800067a8  lea     rcx, aVectorTooLong; "vector too long"
0x1800067af  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
