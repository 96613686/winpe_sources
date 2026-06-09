# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180031cb8`
- end: `0x180031cf2`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180037540`

## callees

- `0x180031cb8`
- `0x180031d2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031cd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031cd8`

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
0x180031cb8  push    rbx
0x180031cba  sub     rsp, 20h
0x180031cbe  mov     rbx, rcx
0x180031cc1  test    rcx, rcx
0x180031cc4  jz      short loc_180031CE4
0x180031cc6  cmp     dword ptr [rcx], 48h ; 'H'
0x180031cc9  jnz     short loc_180031CE4
0x180031ccb  add     rcx, 38h ; '8'
0x180031ccf  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180031cd4  lea     rcx, [rbx+8]; lpCriticalSection
0x180031cd8  call    cs:__imp_DeleteCriticalSection
0x180031cde  mov     dword ptr [rbx], 0
0x180031ce4  lea     rcx, [rbx+38h]
0x180031ce8  add     rsp, 20h
0x180031cec  pop     rbx
0x180031ced  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
