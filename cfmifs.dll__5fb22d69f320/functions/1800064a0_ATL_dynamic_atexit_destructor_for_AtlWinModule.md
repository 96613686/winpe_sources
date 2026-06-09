# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800064a0`
- end: `0x180006519`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800064a0`

## import_xrefs

- `msvcrt!free` at `0x1800064b9`
- `msvcrt!free` at `0x1800064f8`
- `msvcrt!free` at `0x1800064b9`
- `msvcrt!free` at `0x1800064f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800064dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800064dc`

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
    qword_18000B210 = 0;
    DeleteCriticalSection(&stru_18000B1D8);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_18000B210 = 0;
}

```

## disassembly

```asm
0x1800064a0  sub     rsp, 28h
0x1800064a4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800064ab  jnz     short loc_1800064EC
0x1800064ad  mov     rcx, cs:Block; Block
0x1800064b4  test    rcx, rcx
0x1800064b7  jz      short loc_1800064CA
0x1800064b9  call    cs:__imp_free
0x1800064bf  mov     cs:Block, 0
0x1800064ca  lea     rcx, stru_18000B1D8; lpCriticalSection
0x1800064d1  mov     cs:qword_18000B210, 0
0x1800064dc  call    cs:__imp_DeleteCriticalSection
0x1800064e2  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800064ec  mov     rcx, cs:Block; Block
0x1800064f3  test    rcx, rcx
0x1800064f6  jz      short loc_180006509
0x1800064f8  call    cs:__imp_free
0x1800064fe  mov     cs:Block, 0
0x180006509  mov     cs:qword_18000B210, 0
0x180006514  add     rsp, 28h
0x180006518  retn
```
