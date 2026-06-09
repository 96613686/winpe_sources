# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180024168`
- end: `0x1800241a2`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025c60`

## callees

- `0x180024168`
- `0x1800242b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024188`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024188`

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
0x180024168  push    rbx
0x18002416a  sub     rsp, 20h
0x18002416e  mov     rbx, rcx
0x180024171  test    rcx, rcx
0x180024174  jz      short loc_180024194
0x180024176  cmp     dword ptr [rcx], 48h ; 'H'
0x180024179  jnz     short loc_180024194
0x18002417b  add     rcx, 38h ; '8'
0x18002417f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180024184  lea     rcx, [rbx+8]; lpCriticalSection
0x180024188  call    cs:__imp_DeleteCriticalSection
0x18002418e  mov     dword ptr [rbx], 0
0x180024194  lea     rcx, [rbx+38h]
0x180024198  add     rsp, 20h
0x18002419c  pop     rbx
0x18002419d  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
