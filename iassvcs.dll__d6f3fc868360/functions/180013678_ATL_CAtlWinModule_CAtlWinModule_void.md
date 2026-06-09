# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180013678`
- end: `0x18001372f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018d40`

## callees

- `0x1800127fc`
- `0x180013678`

## import_xrefs

- `msvcrt!free` at `0x1800136cf`
- `msvcrt!free` at `0x1800136fe`
- `msvcrt!free` at `0x1800136cf`
- `msvcrt!free` at `0x1800136fe`
- `KERNEL32!DeleteCriticalSection` at `0x1800136e9`
- `KERNEL32!DeleteCriticalSection` at `0x1800136e9`
- `USER32!UnregisterClassA` at `0x1800136b9`
- `USER32!UnregisterClassA` at `0x1800136b9`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rsi
  int i; // edi
  void *v5; // rcx
  void *v6; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hModule;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x18001372ELL);
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)this + 7) + 2LL * i), v3);
    }
    v5 = (void *)*((_QWORD *)this + 7);
    if ( v5 )
    {
      free(v5);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x180013678  mov     [rsp+arg_0], rbx
0x18001367d  mov     [rsp+arg_8], rsi
0x180013682  push    rdi
0x180013683  sub     rsp, 20h
0x180013687  mov     rbx, rcx
0x18001368a  test    rcx, rcx
0x18001368d  jz      short loc_1800136F5
0x18001368f  cmp     dword ptr [rcx], 48h ; 'H'
0x180013692  jnz     short loc_1800136F5
0x180013694  mov     rsi, cs:hModule
0x18001369b  xor     edi, edi
0x18001369d  cmp     [rcx+40h], edi
0x1800136a0  jle     short loc_1800136C6
0x1800136a2  test    edi, edi
0x1800136a4  js      short loc_180013724
0x1800136a6  cmp     edi, [rbx+40h]
0x1800136a9  jge     short loc_180013724
0x1800136ab  mov     rax, [rbx+38h]
0x1800136af  mov     rdx, rsi; hInstance
0x1800136b2  movsxd  rcx, edi
0x1800136b5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800136b9  call    cs:__imp_UnregisterClassA
0x1800136bf  inc     edi
0x1800136c1  cmp     edi, [rbx+40h]
0x1800136c4  jl      short loc_1800136A2
0x1800136c6  mov     rcx, [rbx+38h]; Block
0x1800136ca  test    rcx, rcx
0x1800136cd  jz      short loc_1800136DD
0x1800136cf  call    cs:__imp_free
0x1800136d5  mov     qword ptr [rbx+38h], 0
0x1800136dd  lea     rcx, [rbx+8]; lpCriticalSection
0x1800136e1  mov     qword ptr [rbx+40h], 0
0x1800136e9  call    cs:__imp_DeleteCriticalSection
0x1800136ef  mov     dword ptr [rbx], 0
0x1800136f5  mov     rcx, [rbx+38h]; Block
0x1800136f9  test    rcx, rcx
0x1800136fc  jz      short loc_18001370C
0x1800136fe  call    cs:__imp_free
0x180013704  mov     qword ptr [rbx+38h], 0
0x18001370c  mov     rsi, [rsp+28h+arg_8]
0x180013711  mov     qword ptr [rbx+40h], 0
0x180013719  mov     rbx, [rsp+28h+arg_0]
0x18001371e  add     rsp, 20h
0x180013722  pop     rdi
0x180013723  retn
0x180013724  mov     ecx, 0C000008Ch; unsigned int
0x180013729  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
