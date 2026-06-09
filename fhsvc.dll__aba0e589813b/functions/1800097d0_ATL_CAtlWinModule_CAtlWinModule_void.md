# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x1800097d0`
- end: `0x180009860`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012750`

## callees

- `0x1800097d0`
- `0x18000b8b4`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000982c`
- `KERNEL32!RaiseException` at `0x18000982c`
- `KERNEL32!DeleteCriticalSection` at `0x180009843`
- `KERNEL32!DeleteCriticalSection` at `0x180009843`
- `USER32!UnregisterClassA` at `0x18000980e`
- `USER32!UnregisterClassA` at `0x18000980e`

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
0x1800097d0  push    rbx
0x1800097d2  push    rbp
0x1800097d3  push    rsi
0x1800097d4  push    rdi
0x1800097d5  sub     rsp, 28h
0x1800097d9  mov     rbx, rcx
0x1800097dc  test    rcx, rcx
0x1800097df  jz      short loc_18000984F
0x1800097e1  cmp     dword ptr [rcx], 48h ; 'H'
0x1800097e4  jnz     short loc_18000984F
0x1800097e6  mov     rbp, cs:hInstance
0x1800097ed  xor     esi, esi
0x1800097ef  cmp     [rcx+40h], esi
0x1800097f2  jle     short loc_180009833
0x1800097f4  test    esi, esi
0x1800097f6  js      short loc_18000981D
0x1800097f8  lea     rdi, [rbx+38h]
0x1800097fc  cmp     esi, [rdi+8]
0x1800097ff  jge     short loc_18000981D
0x180009801  mov     rax, [rdi]
0x180009804  mov     rdx, rbp; hInstance
0x180009807  movsxd  rcx, esi
0x18000980a  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000980e  call    cs:__imp_UnregisterClassA
0x180009814  inc     esi
0x180009816  cmp     esi, [rbx+40h]
0x180009819  jl      short loc_1800097F4
0x18000981b  jmp     short loc_180009837
0x18000981d  xor     r9d, r9d; lpArguments
0x180009820  xor     r8d, r8d; nNumberOfArguments
0x180009823  mov     ecx, 0C000008Ch; dwExceptionCode
0x180009828  lea     edx, [r9+1]; dwExceptionFlags
0x18000982c  call    cs:__imp_RaiseException
0x180009832  int     3; Trap to Debugger
0x180009833  lea     rdi, [rcx+38h]
0x180009837  mov     rcx, rdi
0x18000983a  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000983f  lea     rcx, [rbx+8]; lpCriticalSection
0x180009843  call    cs:__imp_DeleteCriticalSection
0x180009849  mov     dword ptr [rbx], 0
0x18000984f  lea     rcx, [rbx+38h]
0x180009853  add     rsp, 28h
0x180009857  pop     rdi
0x180009858  pop     rsi
0x180009859  pop     rbp
0x18000985a  pop     rbx
0x18000985b  jmp     ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
```
