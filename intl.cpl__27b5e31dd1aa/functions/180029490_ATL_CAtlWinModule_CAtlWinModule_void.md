# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180029490`
- end: `0x180029515`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002ad70`

## callees

- `0x18001782c`
- `0x180029490`
- `0x180029550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800294ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800294ed`
- `USER32!UnregisterClassA` at `0x1800294ce`
- `USER32!UnregisterClassA` at `0x1800294ce`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rbp
  int v4; // edi
  _QWORD *v5; // rsi

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    v4 = 0;
    if ( *((int *)this + 16) <= 0 )
    {
      v5 = (_QWORD *)((char *)this + 56);
    }
    else
    {
      do
      {
        if ( v4 < 0 || (v5 = (_QWORD *)((char *)this + 56), v4 >= *((_DWORD *)this + 16)) )
        {
          ATL::_AtlRaiseException(0xC000008C, a2);
          JUMPOUT(0x180029514LL);
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v5 + 2LL * v4++), v3);
      }
      while ( v4 < *((_DWORD *)this + 16) );
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v5);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x180029490  push    rbx
0x180029492  push    rbp
0x180029493  push    rsi
0x180029494  push    rdi
0x180029495  sub     rsp, 28h
0x180029499  mov     rbx, rcx
0x18002949c  test    rcx, rcx
0x18002949f  jz      short loc_1800294F9
0x1800294a1  cmp     dword ptr [rcx], 48h ; 'H'
0x1800294a4  jnz     short loc_1800294F9
0x1800294a6  mov     rbp, cs:hInstance
0x1800294ad  xor     edi, edi
0x1800294af  cmp     [rcx+40h], edi
0x1800294b2  jle     short loc_1800294DD
0x1800294b4  test    edi, edi
0x1800294b6  js      short loc_18002950A
0x1800294b8  lea     rsi, [rbx+38h]
0x1800294bc  cmp     edi, [rsi+8]
0x1800294bf  jge     short loc_18002950A
0x1800294c1  mov     rax, [rsi]
0x1800294c4  mov     rdx, rbp; hInstance
0x1800294c7  movsxd  rcx, edi
0x1800294ca  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800294ce  call    cs:__imp_UnregisterClassA
0x1800294d4  inc     edi
0x1800294d6  cmp     edi, [rbx+40h]
0x1800294d9  jl      short loc_1800294B4
0x1800294db  jmp     short loc_1800294E1
0x1800294dd  lea     rsi, [rcx+38h]
0x1800294e1  mov     rcx, rsi
0x1800294e4  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x1800294e9  lea     rcx, [rbx+8]; lpCriticalSection
0x1800294ed  call    cs:__imp_DeleteCriticalSection
0x1800294f3  mov     dword ptr [rbx], 0
0x1800294f9  lea     rcx, [rbx+38h]
0x1800294fd  add     rsp, 28h
0x180029501  pop     rdi
0x180029502  pop     rsi
0x180029503  pop     rbp
0x180029504  pop     rbx
0x180029505  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18002950a  mov     ecx, 0C000008Ch; unsigned int
0x18002950f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
