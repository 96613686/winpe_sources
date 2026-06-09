# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xlen(void)

- ea: `0x180002110`
- end: `0x180002121`
- name: `?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002198`
- `0x180002290`

## callees

- `0x180002128`

## pseudocode

```c
void __noreturn std::string::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180002110  sub     rsp, 28h
0x180002114  lea     rcx, aStringTooLong; "string too long"
0x18000211b  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
