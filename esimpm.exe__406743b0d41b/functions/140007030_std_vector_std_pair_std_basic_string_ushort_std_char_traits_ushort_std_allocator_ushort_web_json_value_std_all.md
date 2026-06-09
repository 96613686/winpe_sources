# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Xlength(void)

- ea: `0x140007030`
- end: `0x140007041`
- name: `?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400043e0`
- `0x1400055e0`
- `0x1400061a0`
- `0x140006d10`
- `0x140008630`
- `0x1400088d0`
- `0x140008ef0`
- `0x14000ae00`

## callees

- `0x14000297e`

## pseudocode

```c
void __noreturn std::vector<std::pair<std::wstring,web::json::value>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x140007030  sub     rsp, 28h
0x140007034  lea     rcx, aVectorTooLong; "vector too long"
0x14000703b  call    ?_Xlength_error@std@@YAXPEBD@Z_0; std::_Xlength_error(char const *)
```
