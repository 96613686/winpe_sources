# _PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$0

- ea: `0x14000eb91`
- end: `0x14000eb9d`
- name: `_PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003a0c`

## pseudocode

```c
__int64 __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::_Tidy(*(_QWORD *)(a2 + 120));
}

```

## disassembly

```asm
0x14000eb91  mov     rcx, [rdx+78h]
0x14000eb98  jmp     ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
```
