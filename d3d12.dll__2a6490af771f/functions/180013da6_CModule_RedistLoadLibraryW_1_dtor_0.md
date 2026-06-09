# _CModule::RedistLoadLibraryW_::_1_::dtor$0

- ea: `0x180013da6`
- end: `0x180013db2`
- name: `_CModule::RedistLoadLibraryW_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006c64`

## pseudocode

```c
__int64 __fastcall CModule::RedistLoadLibraryW_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short>::~vector<unsigned short>(a2 + 32);
}

```

## disassembly

```asm
0x180013da6  lea     rcx, [rdx+20h]
0x180013dad  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
