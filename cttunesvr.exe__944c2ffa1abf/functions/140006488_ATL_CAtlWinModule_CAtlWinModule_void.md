# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x140006488`
- end: `0x14000653f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400067e0`

## callees

- `0x14000522c`
- `0x140006488`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400064f9`
- `KERNEL32!DeleteCriticalSection` at `0x1400064f9`
- `USER32!UnregisterClassA` at `0x1400064c9`
- `USER32!UnregisterClassA` at `0x1400064c9`
- `msvcrt!free` at `0x1400064df`
- `msvcrt!free` at `0x14000650e`
- `msvcrt!free` at `0x1400064df`
- `msvcrt!free` at `0x14000650e`

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
        JUMPOUT(0x14000653ELL);
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
0x140006488  mov     [rsp+arg_0], rbx
0x14000648d  mov     [rsp+arg_8], rsi
0x140006492  push    rdi
0x140006493  sub     rsp, 20h
0x140006497  mov     rbx, rcx
0x14000649a  test    rcx, rcx
0x14000649d  jz      short loc_140006505
0x14000649f  cmp     dword ptr [rcx], 48h ; 'H'
0x1400064a2  jnz     short loc_140006505
0x1400064a4  mov     rsi, cs:hInstance
0x1400064ab  xor     edi, edi
0x1400064ad  cmp     [rcx+40h], edi
0x1400064b0  jle     short loc_1400064D6
0x1400064b2  test    edi, edi
0x1400064b4  js      short loc_140006534
0x1400064b6  cmp     edi, [rbx+40h]
0x1400064b9  jge     short loc_140006534
0x1400064bb  mov     rax, [rbx+38h]
0x1400064bf  mov     rdx, rsi; hInstance
0x1400064c2  movsxd  rcx, edi
0x1400064c5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1400064c9  call    cs:__imp_UnregisterClassA
0x1400064cf  inc     edi
0x1400064d1  cmp     edi, [rbx+40h]
0x1400064d4  jl      short loc_1400064B2
0x1400064d6  mov     rcx, [rbx+38h]; Block
0x1400064da  test    rcx, rcx
0x1400064dd  jz      short loc_1400064ED
0x1400064df  call    cs:__imp_free
0x1400064e5  mov     qword ptr [rbx+38h], 0
0x1400064ed  lea     rcx, [rbx+8]; lpCriticalSection
0x1400064f1  mov     qword ptr [rbx+40h], 0
0x1400064f9  call    cs:__imp_DeleteCriticalSection
0x1400064ff  mov     dword ptr [rbx], 0
0x140006505  mov     rcx, [rbx+38h]; Block
0x140006509  test    rcx, rcx
0x14000650c  jz      short loc_14000651C
0x14000650e  call    cs:__imp_free
0x140006514  mov     qword ptr [rbx+38h], 0
0x14000651c  mov     rsi, [rsp+28h+arg_8]
0x140006521  mov     qword ptr [rbx+40h], 0
0x140006529  mov     rbx, [rsp+28h+arg_0]
0x14000652e  add     rsp, 20h
0x140006532  pop     rdi
0x140006533  retn
0x140006534  mov     ecx, 0C000008Ch; unsigned int
0x140006539  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
