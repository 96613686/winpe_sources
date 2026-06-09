# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x140034528`
- end: `0x140034604`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `220`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14004c110`

## callees

- `0x1400187b0`
- `0x140034528`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400345b1`
- `KERNEL32!DeleteCriticalSection` at `0x1400345b1`
- `USER32!UnregisterClassA` at `0x140034575`
- `USER32!UnregisterClassA` at `0x140034575`
- `msvcrt!free` at `0x140034591`
- `msvcrt!free` at `0x1400345cc`
- `msvcrt!free` at `0x140034591`
- `msvcrt!free` at `0x1400345cc`

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
        JUMPOUT(0x140034603LL);
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
0x140034528  mov     [rsp+arg_0], rbx
0x14003452d  mov     [rsp+arg_8], rsi
0x140034532  push    rdi
0x140034533  sub     rsp, 20h
0x140034537  mov     rbx, rcx
0x14003453a  test    rcx, rcx
0x14003453d  jz      loc_1400345C3
0x140034543  cmp     dword ptr [rcx], 48h ; 'H'
0x140034546  jnz     short loc_1400345C3
0x140034548  mov     rsi, cs:hInstance
0x14003454f  xor     edi, edi
0x140034551  cmp     [rcx+40h], edi
0x140034554  jle     short loc_140034588
0x140034556  test    edi, edi
0x140034558  js      loc_1400345F9
0x14003455e  cmp     edi, [rbx+40h]
0x140034561  jge     loc_1400345F9
0x140034567  mov     rax, [rbx+38h]
0x14003456b  mov     rdx, rsi; hInstance
0x14003456e  movsxd  rcx, edi
0x140034571  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x140034575  call    cs:__imp_UnregisterClassA
0x14003457c  nop     dword ptr [rax+rax+00h]
0x140034581  inc     edi
0x140034583  cmp     edi, [rbx+40h]
0x140034586  jl      short loc_140034556
0x140034588  mov     rcx, [rbx+38h]; Block
0x14003458c  test    rcx, rcx
0x14003458f  jz      short loc_1400345A5
0x140034591  call    cs:__imp_free
0x140034598  nop     dword ptr [rax+rax+00h]
0x14003459d  mov     qword ptr [rbx+38h], 0
0x1400345a5  lea     rcx, [rbx+8]; lpCriticalSection
0x1400345a9  mov     qword ptr [rbx+40h], 0
0x1400345b1  call    cs:__imp_DeleteCriticalSection
0x1400345b8  nop     dword ptr [rax+rax+00h]
0x1400345bd  mov     dword ptr [rbx], 0
0x1400345c3  mov     rcx, [rbx+38h]; Block
0x1400345c7  test    rcx, rcx
0x1400345ca  jz      short loc_1400345E0
0x1400345cc  call    cs:__imp_free
0x1400345d3  nop     dword ptr [rax+rax+00h]
0x1400345d8  mov     qword ptr [rbx+38h], 0
0x1400345e0  mov     rsi, [rsp+28h+arg_8]
0x1400345e5  mov     qword ptr [rbx+40h], 0
0x1400345ed  mov     rbx, [rsp+28h+arg_0]
0x1400345f2  add     rsp, 20h
0x1400345f6  pop     rdi
0x1400345f7  retn
0x1400345f9  mov     ecx, 0C000008Ch; unsigned int
0x1400345fe  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
