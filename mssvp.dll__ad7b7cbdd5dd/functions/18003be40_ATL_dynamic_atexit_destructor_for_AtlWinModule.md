# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x18003be40`
- end: `0x18003be95`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004950`
- `0x180006d84`
- `0x18003be40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003be64`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003be64`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  if ( ATL::_AtlWinModule == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_180054078);
    DeleteCriticalSection(&stru_180054048);
    ATL::_AtlWinModule = 0;
  }
  if ( qword_180054078 )
  {
    free(qword_180054078);
    qword_180054078 = 0;
  }
  qword_180054080 = 0;
}

```

## disassembly

```asm
0x18003be40  push    rbx
0x18003be42  sub     rsp, 20h
0x18003be46  xor     ebx, ebx
0x18003be48  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x18003be4f  jnz     short loc_18003BE70
0x18003be51  lea     rcx, qword_180054078
0x18003be58  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18003be5d  lea     rcx, stru_180054048; lpCriticalSection
0x18003be64  call    cs:__imp_DeleteCriticalSection
0x18003be6a  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, ebx; ATL::CAtlWinModule ATL::_AtlWinModule
0x18003be70  mov     rcx, cs:qword_180054078; Block
0x18003be77  test    rcx, rcx
0x18003be7a  jz      short loc_18003BE88
0x18003be7c  call    free
0x18003be81  mov     cs:qword_180054078, rbx
0x18003be88  mov     cs:qword_180054080, rbx
0x18003be8f  add     rsp, 20h
0x18003be93  pop     rbx
0x18003be94  retn
```
