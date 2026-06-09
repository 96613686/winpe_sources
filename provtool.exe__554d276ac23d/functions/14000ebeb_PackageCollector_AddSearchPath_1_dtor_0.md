# _PackageCollector::AddSearchPath_::_1_::dtor$0

- ea: `0x14000ebeb`
- end: `0x14000ebf7`
- name: `_PackageCollector::AddSearchPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400039d0`

## pseudocode

```c
__int64 __fastcall PackageCollector::AddSearchPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short const *>::~vector<unsigned short const *>(a2 + 64);
}

```

## disassembly

```asm
0x14000ebeb  lea     rcx, [rdx+40h]
0x14000ebf2  jmp     ??1?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::~vector<ushort const *>(void)
```
