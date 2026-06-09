# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x14000ee40`
- end: `0x14000eef5`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f900`

## callees

- `0x140002b8a`
- `0x140009858`
- `0x14000ee40`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000eeb0`
- `KERNEL32!DeleteCriticalSection` at `0x14000eeb0`
- `USER32!UnregisterClassA` at `0x14000ee81`
- `USER32!UnregisterClassA` at `0x14000ee81`

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
        JUMPOUT(0x14000EEF4LL);
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
0x14000ee40  mov     [rsp+arg_0], rbx
0x14000ee45  mov     [rsp+arg_8], rsi
0x14000ee4a  push    rdi
0x14000ee4b  sub     rsp, 20h
0x14000ee4f  mov     rbx, rcx
0x14000ee52  test    rcx, rcx
0x14000ee55  jz      short loc_14000EEBC
0x14000ee57  cmp     dword ptr [rcx], 48h ; 'H'
0x14000ee5a  jnz     short loc_14000EEBC
0x14000ee5c  mov     rsi, cs:hModule
0x14000ee63  xor     edi, edi
0x14000ee65  cmp     [rcx+40h], edi
0x14000ee68  jle     short loc_14000EE8E
0x14000ee6a  test    edi, edi
0x14000ee6c  js      short loc_14000EEEA
0x14000ee6e  cmp     edi, [rbx+40h]
0x14000ee71  jge     short loc_14000EEEA
0x14000ee73  mov     rax, [rbx+38h]
0x14000ee77  mov     rdx, rsi; hInstance
0x14000ee7a  movsxd  rcx, edi
0x14000ee7d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x14000ee81  call    cs:__imp_UnregisterClassA
0x14000ee87  inc     edi
0x14000ee89  cmp     edi, [rbx+40h]
0x14000ee8c  jl      short loc_14000EE6A
0x14000ee8e  mov     rcx, [rbx+38h]; Block
0x14000ee92  test    rcx, rcx
0x14000ee95  jz      short loc_14000EEA4
0x14000ee97  call    free
0x14000ee9c  mov     qword ptr [rbx+38h], 0
0x14000eea4  lea     rcx, [rbx+8]; lpCriticalSection
0x14000eea8  mov     qword ptr [rbx+40h], 0
0x14000eeb0  call    cs:__imp_DeleteCriticalSection
0x14000eeb6  mov     dword ptr [rbx], 0
0x14000eebc  mov     rcx, [rbx+38h]; Block
0x14000eec0  test    rcx, rcx
0x14000eec3  jz      short loc_14000EED2
0x14000eec5  call    free
0x14000eeca  mov     qword ptr [rbx+38h], 0
0x14000eed2  mov     rsi, [rsp+28h+arg_8]
0x14000eed7  mov     qword ptr [rbx+40h], 0
0x14000eedf  mov     rbx, [rsp+28h+arg_0]
0x14000eee4  add     rsp, 20h
0x14000eee8  pop     rdi
0x14000eee9  retn
0x14000eeea  mov     ecx, 0C000008Ch; unsigned int
0x14000eeef  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
