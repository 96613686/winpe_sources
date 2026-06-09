# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x180026bf0`
- end: `0x180026c30`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000dd68`
- `0x180026bf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026c10`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026c10`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_1800365C8);
    DeleteCriticalSection(&stru_180036598);
    ATL::_AtlWinModule = 0;
  }
  return ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_1800365C8);
}

```

## disassembly

```asm
0x180026bf0  sub     rsp, 28h
0x180026bf4  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180026bfb  jnz     short loc_180026C20
0x180026bfd  lea     rcx, qword_1800365C8
0x180026c04  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180026c09  lea     rcx, stru_180036598; lpCriticalSection
0x180026c10  call    cs:__imp_DeleteCriticalSection
0x180026c16  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x180026c20  lea     rcx, qword_1800365C8
0x180026c27  add     rsp, 28h
0x180026c2b  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
