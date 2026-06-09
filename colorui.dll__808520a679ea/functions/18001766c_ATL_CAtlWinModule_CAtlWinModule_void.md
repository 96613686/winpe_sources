# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18001766c`
- end: `0x180017723`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018ae0`

## callees

- `0x18000b3dc`
- `0x18001766c`

## import_xrefs

- `msvcrt!free` at `0x1800176c3`
- `msvcrt!free` at `0x1800176f2`
- `msvcrt!free` at `0x1800176c3`
- `msvcrt!free` at `0x1800176f2`
- `KERNEL32!DeleteCriticalSection` at `0x1800176dd`
- `KERNEL32!DeleteCriticalSection` at `0x1800176dd`
- `USER32!UnregisterClassA` at `0x1800176ad`
- `USER32!UnregisterClassA` at `0x1800176ad`

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
    v3 = hInstance;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180017722LL);
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
0x18001766c  mov     [rsp+arg_0], rbx
0x180017671  mov     [rsp+arg_8], rsi
0x180017676  push    rdi
0x180017677  sub     rsp, 20h
0x18001767b  mov     rbx, rcx
0x18001767e  test    rcx, rcx
0x180017681  jz      short loc_1800176E9
0x180017683  cmp     dword ptr [rcx], 48h ; 'H'
0x180017686  jnz     short loc_1800176E9
0x180017688  mov     rsi, cs:hInstance
0x18001768f  xor     edi, edi
0x180017691  cmp     [rcx+40h], edi
0x180017694  jle     short loc_1800176BA
0x180017696  test    edi, edi
0x180017698  js      short loc_180017718
0x18001769a  cmp     edi, [rbx+40h]
0x18001769d  jge     short loc_180017718
0x18001769f  mov     rax, [rbx+38h]
0x1800176a3  mov     rdx, rsi; hInstance
0x1800176a6  movsxd  rcx, edi
0x1800176a9  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800176ad  call    cs:__imp_UnregisterClassA
0x1800176b3  inc     edi
0x1800176b5  cmp     edi, [rbx+40h]
0x1800176b8  jl      short loc_180017696
0x1800176ba  mov     rcx, [rbx+38h]; Block
0x1800176be  test    rcx, rcx
0x1800176c1  jz      short loc_1800176D1
0x1800176c3  call    cs:__imp_free
0x1800176c9  mov     qword ptr [rbx+38h], 0
0x1800176d1  lea     rcx, [rbx+8]; lpCriticalSection
0x1800176d5  mov     qword ptr [rbx+40h], 0
0x1800176dd  call    cs:__imp_DeleteCriticalSection
0x1800176e3  mov     dword ptr [rbx], 0
0x1800176e9  mov     rcx, [rbx+38h]; Block
0x1800176ed  test    rcx, rcx
0x1800176f0  jz      short loc_180017700
0x1800176f2  call    cs:__imp_free
0x1800176f8  mov     qword ptr [rbx+38h], 0
0x180017700  mov     rsi, [rsp+28h+arg_8]
0x180017705  mov     qword ptr [rbx+40h], 0
0x18001770d  mov     rbx, [rsp+28h+arg_0]
0x180017712  add     rsp, 20h
0x180017716  pop     rdi
0x180017717  retn
0x180017718  mov     ecx, 0C000008Ch; unsigned int
0x18001771d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
