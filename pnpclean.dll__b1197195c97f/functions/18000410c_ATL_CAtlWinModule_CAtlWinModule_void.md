# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000410c`
- end: `0x1800041c3`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009270`

## callees

- `0x1800029a4`
- `0x18000410c`

## import_xrefs

- `msvcrt!free` at `0x180004163`
- `msvcrt!free` at `0x180004192`
- `msvcrt!free` at `0x180004163`
- `msvcrt!free` at `0x180004192`
- `KERNEL32!DeleteCriticalSection` at `0x18000417d`
- `KERNEL32!DeleteCriticalSection` at `0x18000417d`
- `USER32!UnregisterClassA` at `0x18000414d`
- `USER32!UnregisterClassA` at `0x18000414d`

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
        JUMPOUT(0x1800041C2LL);
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
0x18000410c  mov     [rsp+arg_0], rbx
0x180004111  mov     [rsp+arg_8], rsi
0x180004116  push    rdi
0x180004117  sub     rsp, 20h
0x18000411b  mov     rbx, rcx
0x18000411e  test    rcx, rcx
0x180004121  jz      short loc_180004189
0x180004123  cmp     dword ptr [rcx], 48h ; 'H'
0x180004126  jnz     short loc_180004189
0x180004128  mov     rsi, cs:hInstance
0x18000412f  xor     edi, edi
0x180004131  cmp     [rcx+40h], edi
0x180004134  jle     short loc_18000415A
0x180004136  test    edi, edi
0x180004138  js      short loc_1800041B8
0x18000413a  cmp     edi, [rbx+40h]
0x18000413d  jge     short loc_1800041B8
0x18000413f  mov     rax, [rbx+38h]
0x180004143  mov     rdx, rsi; hInstance
0x180004146  movsxd  rcx, edi
0x180004149  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000414d  call    cs:__imp_UnregisterClassA
0x180004153  inc     edi
0x180004155  cmp     edi, [rbx+40h]
0x180004158  jl      short loc_180004136
0x18000415a  mov     rcx, [rbx+38h]; Block
0x18000415e  test    rcx, rcx
0x180004161  jz      short loc_180004171
0x180004163  call    cs:__imp_free
0x180004169  mov     qword ptr [rbx+38h], 0
0x180004171  lea     rcx, [rbx+8]; lpCriticalSection
0x180004175  mov     qword ptr [rbx+40h], 0
0x18000417d  call    cs:__imp_DeleteCriticalSection
0x180004183  mov     dword ptr [rbx], 0
0x180004189  mov     rcx, [rbx+38h]; Block
0x18000418d  test    rcx, rcx
0x180004190  jz      short loc_1800041A0
0x180004192  call    cs:__imp_free
0x180004198  mov     qword ptr [rbx+38h], 0
0x1800041a0  mov     rsi, [rsp+28h+arg_8]
0x1800041a5  mov     qword ptr [rbx+40h], 0
0x1800041ad  mov     rbx, [rsp+28h+arg_0]
0x1800041b2  add     rsp, 20h
0x1800041b6  pop     rdi
0x1800041b7  retn
0x1800041b8  mov     ecx, 0C000008Ch; unsigned int
0x1800041bd  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
