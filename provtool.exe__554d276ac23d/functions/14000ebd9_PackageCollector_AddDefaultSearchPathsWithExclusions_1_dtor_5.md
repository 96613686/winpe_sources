# _PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$5

- ea: `0x14000ebd9`
- end: `0x14000ebe5`
- name: `_PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003938`

## pseudocode

```c
__int64 __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 176);
}

```

## disassembly

```asm
0x14000ebd9  lea     rcx, [rdx+0B0h]
0x14000ebe0  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
