# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18002cca4`
- end: `0x18002ccde`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e1e0`

## callees

- `0x18002cca4`
- `0x18002cd18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ccc4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ccc4`

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
0x18002cca4  push    rbx
0x18002cca6  sub     rsp, 20h
0x18002ccaa  mov     rbx, rcx
0x18002ccad  test    rcx, rcx
0x18002ccb0  jz      short loc_18002CCD0
0x18002ccb2  cmp     dword ptr [rcx], 48h ; 'H'
0x18002ccb5  jnz     short loc_18002CCD0
0x18002ccb7  add     rcx, 38h ; '8'
0x18002ccbb  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002ccc0  lea     rcx, [rbx+8]; lpCriticalSection
0x18002ccc4  call    cs:__imp_DeleteCriticalSection
0x18002ccca  mov     dword ptr [rbx], 0
0x18002ccd0  lea     rcx, [rbx+38h]
0x18002ccd4  add     rsp, 20h
0x18002ccd8  pop     rbx
0x18002ccd9  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
