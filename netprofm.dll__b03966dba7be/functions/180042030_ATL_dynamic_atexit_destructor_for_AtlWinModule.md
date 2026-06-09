# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180042030`
- end: `0x180042070`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009e14`
- `0x180042030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042050`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042050`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(qword_18005FD28);
    DeleteCriticalSection(&stru_18005FCF8);
    ATL::_AtlWinModule = 0;
  }
  return ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(qword_18005FD28);
}

```

## disassembly

```asm
0x180042030  sub     rsp, 28h
0x180042034  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18004203b  jnz     short loc_180042060
0x18004203d  lea     rcx, qword_18005FD28
0x180042044  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180042049  lea     rcx, stru_18005FCF8; lpCriticalSection
0x180042050  call    cs:__imp_DeleteCriticalSection
0x180042056  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180042060  lea     rcx, qword_18005FD28
0x180042067  add     rsp, 28h
0x18004206b  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
