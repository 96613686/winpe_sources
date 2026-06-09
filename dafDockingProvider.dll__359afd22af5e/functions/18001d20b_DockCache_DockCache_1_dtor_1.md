# _DockCache::DockCache_::_1_::dtor$1

- ea: `0x18001d20b`
- end: `0x18001d21b`
- name: `_DockCache::DockCache_::_1_::dtor$1`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011220`

## pseudocode

```c
__int64 __fastcall DockCache::DockCache_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<Dock>::~vector<Dock>(*(_QWORD *)(a2 + 80) + 40LL);
}

```

## disassembly

```asm
0x18001d20b  mov     rcx, [rdx+50h]
0x18001d212  add     rcx, 28h ; '('
0x18001d216  jmp     ??1?$vector@VDock@@V?$allocator@VDock@@@std@@@std@@QEAA@XZ; std::vector<Dock>::~vector<Dock>(void)
```
