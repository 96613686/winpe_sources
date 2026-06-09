# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800346c0`
- end: `0x180034700`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e0a0`
- `0x1800346c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800346e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800346e0`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(qword_1800492A8);
    DeleteCriticalSection(&stru_180049278);
    ATL::_AtlWinModule = 0;
  }
  return ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(qword_1800492A8);
}

```

## disassembly

```asm
0x1800346c0  sub     rsp, 28h
0x1800346c4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800346cb  jnz     short loc_1800346F0
0x1800346cd  lea     rcx, qword_1800492A8
0x1800346d4  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800346d9  lea     rcx, stru_180049278; lpCriticalSection
0x1800346e0  call    cs:__imp_DeleteCriticalSection
0x1800346e6  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800346f0  lea     rcx, qword_1800492A8
0x1800346f7  add     rsp, 28h
0x1800346fb  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
