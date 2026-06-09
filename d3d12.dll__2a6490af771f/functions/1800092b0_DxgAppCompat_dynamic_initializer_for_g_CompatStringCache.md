# DxgAppCompat::_dynamic_initializer_for__g_CompatStringCache__

- ea: `0x1800092b0`
- end: `0x1800092d0`
- name: `DxgAppCompat::_dynamic_initializer_for__g_CompatStringCache__`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a6fc`
- `0x18000b7c0`

## pseudocode

```c
int DxgAppCompat::_dynamic_initializer_for__g_CompatStringCache__()
{
  std::string::_Construct_empty(&DxgAppCompat::g_CompatStringCache);
  return atexit((void (__cdecl *)())DxgAppCompat::_dynamic_atexit_destructor_for__g_CompatStringCache__);
}

```

## disassembly

```asm
0x1800092b0  sub     rsp, 28h
0x1800092b4  lea     rcx, ?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x1800092bb  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x1800092c0  lea     rcx, DxgAppCompat___dynamic_atexit_destructor_for__g_CompatStringCache__
0x1800092c7  add     rsp, 28h
0x1800092cb  jmp     atexit
```
