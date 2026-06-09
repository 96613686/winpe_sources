# _DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor$0

- ea: `0x1400190b8`
- end: `0x1400190c4`
- name: `_DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000fa84`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 64);
}

```

## disassembly

```asm
0x1400190b8  lea     rcx, [rdx+40h]
0x1400190bf  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
