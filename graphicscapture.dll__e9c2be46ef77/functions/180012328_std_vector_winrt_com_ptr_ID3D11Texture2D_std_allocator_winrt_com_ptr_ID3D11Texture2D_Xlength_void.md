# std::vector<winrt::com_ptr<ID3D11Texture2D>,std::allocator<winrt::com_ptr<ID3D11Texture2D>>>::_Xlength(void)

- ea: `0x180012328`
- end: `0x18001233a`
- name: `?_Xlength@?$vector@U?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d974`
- `0x18000dac0`
- `0x18000dc0c`
- `0x18001e1c8`
- `0x18001e314`
- `0x18001e564`
- `0x18001e678`
- `0x1800215e0`
- `0x180021914`
- `0x180022368`
- `0x180023870`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012333`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012333`

## pseudocode

```c
void __noreturn std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180012328  sub     rsp, 28h
0x18001232c  lea     rcx, aVectorTooLong; "vector too long"
0x180012333  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
