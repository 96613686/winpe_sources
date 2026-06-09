# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18002a430`
- end: `0x18002a46a`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180033cf0`

## callees

- `0x18002a430`
- `0x18002a4a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a450`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a450`

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
0x18002a430  push    rbx
0x18002a432  sub     rsp, 20h
0x18002a436  mov     rbx, rcx
0x18002a439  test    rcx, rcx
0x18002a43c  jz      short loc_18002A45C
0x18002a43e  cmp     dword ptr [rcx], 48h ; 'H'
0x18002a441  jnz     short loc_18002A45C
0x18002a443  add     rcx, 38h ; '8'
0x18002a447  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002a44c  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a450  call    cs:__imp_DeleteCriticalSection
0x18002a456  mov     dword ptr [rbx], 0
0x18002a45c  lea     rcx, [rbx+38h]
0x18002a460  add     rsp, 20h
0x18002a464  pop     rbx
0x18002a465  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
