# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800171d8`
- end: `0x180017268`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800645a0`

## callees

- `0x1800171d8`
- `0x180017270`

## import_xrefs

- `USER32!UnregisterClassA` at `0x180017216`
- `USER32!UnregisterClassA` at `0x180017216`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001724b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001724b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017234`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017234`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  HINSTANCE v2; // rbp
  int v3; // esi
  _QWORD *v4; // rdi

  if ( this && *(_DWORD *)this == 72 )
  {
    v2 = hInstance;
    v3 = 0;
    if ( *((int *)this + 16) <= 0 )
    {
      v4 = (_QWORD *)((char *)this + 56);
    }
    else
    {
      do
      {
        if ( v3 < 0 || (v4 = (_QWORD *)((char *)this + 56), v3 >= *((_DWORD *)this + 16)) )
        {
          RaiseException(0xC000008C, 1u, 0, 0);
          __debugbreak();
        }
        UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v4 + 2LL * v3++), v2);
      }
      while ( v3 < *((_DWORD *)this + 16) );
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x1800171d8  push    rbx
0x1800171da  push    rbp
0x1800171db  push    rsi
0x1800171dc  push    rdi
0x1800171dd  sub     rsp, 28h
0x1800171e1  mov     rbx, rcx
0x1800171e4  test    rcx, rcx
0x1800171e7  jz      short loc_180017257
0x1800171e9  cmp     dword ptr [rcx], 48h ; 'H'
0x1800171ec  jnz     short loc_180017257
0x1800171ee  mov     rbp, cs:hInstance
0x1800171f5  xor     esi, esi
0x1800171f7  cmp     [rcx+40h], esi
0x1800171fa  jle     short loc_18001723B
0x1800171fc  test    esi, esi
0x1800171fe  js      short loc_180017225
0x180017200  lea     rdi, [rbx+38h]
0x180017204  cmp     esi, [rdi+8]
0x180017207  jge     short loc_180017225
0x180017209  mov     rax, [rdi]
0x18001720c  mov     rdx, rbp; hInstance
0x18001720f  movsxd  rcx, esi
0x180017212  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180017216  call    cs:__imp_UnregisterClassA
0x18001721c  inc     esi
0x18001721e  cmp     esi, [rbx+40h]
0x180017221  jl      short loc_1800171FC
0x180017223  jmp     short loc_18001723F
0x180017225  xor     r9d, r9d; lpArguments
0x180017228  xor     r8d, r8d; nNumberOfArguments
0x18001722b  mov     ecx, 0C000008Ch; dwExceptionCode
0x180017230  lea     edx, [r9+1]; dwExceptionFlags
0x180017234  call    cs:__imp_RaiseException
0x18001723a  int     3; Trap to Debugger
0x18001723b  lea     rdi, [rcx+38h]
0x18001723f  mov     rcx, rdi
0x180017242  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180017247  lea     rcx, [rbx+8]; lpCriticalSection
0x18001724b  call    cs:__imp_DeleteCriticalSection
0x180017251  mov     dword ptr [rbx], 0
0x180017257  lea     rcx, [rbx+38h]
0x18001725b  add     rsp, 28h
0x18001725f  pop     rdi
0x180017260  pop     rsi
0x180017261  pop     rbp
0x180017262  pop     rbx
0x180017263  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
