# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180038dfc`
- end: `0x180038e36`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180040a70`

## callees

- `0x180038dfc`
- `0x180038e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038e1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038e1c`

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
0x180038dfc  push    rbx
0x180038dfe  sub     rsp, 20h
0x180038e02  mov     rbx, rcx
0x180038e05  test    rcx, rcx
0x180038e08  jz      short loc_180038E28
0x180038e0a  cmp     dword ptr [rcx], 48h ; 'H'
0x180038e0d  jnz     short loc_180038E28
0x180038e0f  add     rcx, 38h ; '8'
0x180038e13  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180038e18  lea     rcx, [rbx+8]; lpCriticalSection
0x180038e1c  call    cs:__imp_DeleteCriticalSection
0x180038e22  mov     dword ptr [rbx], 0
0x180038e28  lea     rcx, [rbx+38h]
0x180038e2c  add     rsp, 20h
0x180038e30  pop     rbx
0x180038e31  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
