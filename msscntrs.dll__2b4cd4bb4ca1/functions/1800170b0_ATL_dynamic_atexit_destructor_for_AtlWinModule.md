# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800170b0`
- end: `0x180017127`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800032e4`
- `0x1800170b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800170eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800170eb`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    qword_180021D10 = 0;
    DeleteCriticalSection(&stru_180021CD8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180021D10 = 0;
}

```

## disassembly

```asm
0x1800170b0  sub     rsp, 28h
0x1800170b4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800170bb  jnz     short loc_1800170FB
0x1800170bd  mov     rcx, cs:Block; Block
0x1800170c4  test    rcx, rcx
0x1800170c7  jz      short loc_1800170D9
0x1800170c9  call    free
0x1800170ce  mov     cs:Block, 0
0x1800170d9  lea     rcx, stru_180021CD8; lpCriticalSection
0x1800170e0  mov     cs:qword_180021D10, 0
0x1800170eb  call    cs:__imp_DeleteCriticalSection
0x1800170f1  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800170fb  mov     rcx, cs:Block; Block
0x180017102  test    rcx, rcx
0x180017105  jz      short loc_180017117
0x180017107  call    free
0x18001710c  mov     cs:Block, 0
0x180017117  mov     cs:qword_180021D10, 0
0x180017122  add     rsp, 28h
0x180017126  retn
```
