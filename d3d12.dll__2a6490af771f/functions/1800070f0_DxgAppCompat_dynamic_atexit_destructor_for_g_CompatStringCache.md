# DxgAppCompat::_dynamic_atexit_destructor_for__g_CompatStringCache__

- ea: `0x1800070f0`
- end: `0x1800070fc`
- name: `DxgAppCompat::_dynamic_atexit_destructor_for__g_CompatStringCache__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007104`

## pseudocode

```c
__int64 DxgAppCompat::_dynamic_atexit_destructor_for__g_CompatStringCache__()
{
  return std::string::~string(&DxgAppCompat::g_CompatStringCache);
}

```

## disassembly

```asm
0x1800070f0  lea     rcx, ?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x1800070f7  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
