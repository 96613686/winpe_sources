# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18005b640`
- end: `0x18005b6b7`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002ee4`
- `0x18005b640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005b67b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005b67b`

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
    qword_1800882A0 = 0;
    DeleteCriticalSection(&stru_180088268);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800882A0 = 0;
}

```

## disassembly

```asm
0x18005b640  sub     rsp, 28h
0x18005b644  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18005b64b  jnz     short loc_18005B68B
0x18005b64d  mov     rcx, cs:Block; Block
0x18005b654  test    rcx, rcx
0x18005b657  jz      short loc_18005B669
0x18005b659  call    free
0x18005b65e  mov     cs:Block, 0
0x18005b669  lea     rcx, stru_180088268; lpCriticalSection
0x18005b670  mov     cs:qword_1800882A0, 0
0x18005b67b  call    cs:__imp_DeleteCriticalSection
0x18005b681  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18005b68b  mov     rcx, cs:Block; Block
0x18005b692  test    rcx, rcx
0x18005b695  jz      short loc_18005B6A7
0x18005b697  call    free
0x18005b69c  mov     cs:Block, 0
0x18005b6a7  mov     cs:qword_1800882A0, 0
0x18005b6b2  add     rsp, 28h
0x18005b6b6  retn
```
