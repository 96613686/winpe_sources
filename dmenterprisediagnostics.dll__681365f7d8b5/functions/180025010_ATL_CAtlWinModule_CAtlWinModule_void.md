# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180025010`
- end: `0x180025050`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026b20`

## callees

- `0x180025010`
- `0x180025174`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025030`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025030`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  if ( this && *(_DWORD *)this == 72 )
  {
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x180025010  push    rbx
0x180025012  sub     rsp, 20h
0x180025016  mov     rbx, rcx
0x180025019  test    rcx, rcx
0x18002501c  jz      short loc_180025042
0x18002501e  cmp     dword ptr [rcx], 48h ; 'H'
0x180025021  jnz     short loc_180025042
0x180025023  add     rcx, 38h ; '8'
0x180025027  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002502c  lea     rcx, [rbx+8]; lpCriticalSection
0x180025030  call    cs:__imp_DeleteCriticalSection
0x180025037  nop     dword ptr [rax+rax+00h]
0x18002503c  mov     dword ptr [rbx], 0
0x180025042  lea     rcx, [rbx+38h]
0x180025046  add     rsp, 20h
0x18002504a  pop     rbx
0x18002504b  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
