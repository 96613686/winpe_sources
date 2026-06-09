# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Xlen(void)

- ea: `0x18001120c`
- end: `0x18001121d`
- name: `?_Xlen@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180010fbc`
- `0x180011050`
- `0x1800110e4`
- `0x1800112a0`
- `0x180011690`
- `0x1800117e8`

## callees

- `0x1800014b0`

## pseudocode

```c
void __noreturn std::vector<std::wstring>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x18001120c  sub     rsp, 28h
0x180011210  lea     rcx, aVectorTTooLong
0x180011217  call    ?_Xlength_error@std@@YAXPEBD@Z
```
