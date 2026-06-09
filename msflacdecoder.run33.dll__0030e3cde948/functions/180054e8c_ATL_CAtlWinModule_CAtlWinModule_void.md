# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180054e8c`
- end: `0x180054ec6`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180055d60`

## callees

- `0x180054e8c`
- `0x180054f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054eac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054eac`

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
0x180054e8c  push    rbx
0x180054e8e  sub     rsp, 20h
0x180054e92  mov     rbx, rcx
0x180054e95  test    rcx, rcx
0x180054e98  jz      short loc_180054EB8
0x180054e9a  cmp     dword ptr [rcx], 48h ; 'H'
0x180054e9d  jnz     short loc_180054EB8
0x180054e9f  add     rcx, 38h ; '8'
0x180054ea3  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180054ea8  lea     rcx, [rbx+8]; lpCriticalSection
0x180054eac  call    cs:__imp_DeleteCriticalSection
0x180054eb2  mov     dword ptr [rbx], 0
0x180054eb8  lea     rcx, [rbx+38h]
0x180054ebc  add     rsp, 20h
0x180054ec0  pop     rbx
0x180054ec1  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
