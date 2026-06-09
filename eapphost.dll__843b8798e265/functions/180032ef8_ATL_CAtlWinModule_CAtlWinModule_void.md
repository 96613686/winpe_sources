# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180032ef8`
- end: `0x180032f38`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180038940`

## callees

- `0x180032ef8`
- `0x180032f74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032f18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032f18`

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
0x180032ef8  push    rbx
0x180032efa  sub     rsp, 20h
0x180032efe  mov     rbx, rcx
0x180032f01  test    rcx, rcx
0x180032f04  jz      short loc_180032F2A
0x180032f06  cmp     dword ptr [rcx], 48h ; 'H'
0x180032f09  jnz     short loc_180032F2A
0x180032f0b  add     rcx, 38h ; '8'
0x180032f0f  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180032f14  lea     rcx, [rbx+8]; lpCriticalSection
0x180032f18  call    cs:__imp_DeleteCriticalSection
0x180032f1f  nop     dword ptr [rax+rax+00h]
0x180032f24  mov     dword ptr [rbx], 0
0x180032f2a  lea     rcx, [rbx+38h]
0x180032f2e  add     rsp, 20h
0x180032f32  pop     rbx
0x180032f33  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
