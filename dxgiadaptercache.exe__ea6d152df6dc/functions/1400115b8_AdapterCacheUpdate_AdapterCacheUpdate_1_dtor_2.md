# _AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$2

- ea: `0x1400115b8`
- end: `0x1400115c8`
- name: `_AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000651c`

## pseudocode

```c
void __fastcall AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::map<std::wstring,CachedAdapterInformation>::~map<std::wstring,CachedAdapterInformation>((void **)(*(_QWORD *)(a2 + 176) + 16LL));
}

```

## disassembly

```asm
0x1400115b8  mov     rcx, [rdx+0B0h]
0x1400115bf  add     rcx, 10h
0x1400115c3  jmp     ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,CachedAdapterInformation>::~map<std::wstring,CachedAdapterInformation>(void)
```
