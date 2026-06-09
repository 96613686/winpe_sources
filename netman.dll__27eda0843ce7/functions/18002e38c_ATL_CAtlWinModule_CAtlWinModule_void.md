# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18002e38c`
- end: `0x18002e3c6`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800359c0`

## callees

- `0x18002e38c`
- `0x18002e400`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e3ac`
- `KERNEL32!DeleteCriticalSection` at `0x18002e3ac`

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
0x18002e38c  push    rbx
0x18002e38e  sub     rsp, 20h
0x18002e392  mov     rbx, rcx
0x18002e395  test    rcx, rcx
0x18002e398  jz      short loc_18002E3B8
0x18002e39a  cmp     dword ptr [rcx], 48h ; 'H'
0x18002e39d  jnz     short loc_18002E3B8
0x18002e39f  add     rcx, 38h ; '8'
0x18002e3a3  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002e3a8  lea     rcx, [rbx+8]; lpCriticalSection
0x18002e3ac  call    cs:__imp_DeleteCriticalSection
0x18002e3b2  mov     dword ptr [rbx], 0
0x18002e3b8  lea     rcx, [rbx+38h]
0x18002e3bc  add     rsp, 20h
0x18002e3c0  pop     rbx
0x18002e3c1  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
