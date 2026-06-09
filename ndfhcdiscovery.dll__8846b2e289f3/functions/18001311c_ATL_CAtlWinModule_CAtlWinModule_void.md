# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18001311c`
- end: `0x1800131f8`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `220`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800144e0`

## callees

- `0x180009fb0`
- `0x18001311c`

## import_xrefs

- `msvcrt!free` at `0x180013185`
- `msvcrt!free` at `0x1800131c0`
- `msvcrt!free` at `0x180013185`
- `msvcrt!free` at `0x1800131c0`
- `KERNEL32!DeleteCriticalSection` at `0x1800131a5`
- `KERNEL32!DeleteCriticalSection` at `0x1800131a5`
- `USER32!UnregisterClassA` at `0x180013169`
- `USER32!UnregisterClassA` at `0x180013169`

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
        JUMPOUT(0x1800131F7LL);
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
0x18001311c  mov     [rsp+arg_0], rbx
0x180013121  mov     [rsp+arg_8], rsi
0x180013126  push    rdi
0x180013127  sub     rsp, 20h
0x18001312b  mov     rbx, rcx
0x18001312e  test    rcx, rcx
0x180013131  jz      loc_1800131B7
0x180013137  cmp     dword ptr [rcx], 48h ; 'H'
0x18001313a  jnz     short loc_1800131B7
0x18001313c  mov     rsi, cs:hInstance
0x180013143  xor     edi, edi
0x180013145  cmp     [rcx+40h], edi
0x180013148  jle     short loc_18001317C
0x18001314a  test    edi, edi
0x18001314c  js      loc_1800131ED
0x180013152  cmp     edi, [rbx+40h]
0x180013155  jge     loc_1800131ED
0x18001315b  mov     rax, [rbx+38h]
0x18001315f  mov     rdx, rsi; hInstance
0x180013162  movsxd  rcx, edi
0x180013165  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180013169  call    cs:__imp_UnregisterClassA
0x180013170  nop     dword ptr [rax+rax+00h]
0x180013175  inc     edi
0x180013177  cmp     edi, [rbx+40h]
0x18001317a  jl      short loc_18001314A
0x18001317c  mov     rcx, [rbx+38h]; Block
0x180013180  test    rcx, rcx
0x180013183  jz      short loc_180013199
0x180013185  call    cs:__imp_free
0x18001318c  nop     dword ptr [rax+rax+00h]
0x180013191  mov     qword ptr [rbx+38h], 0
0x180013199  lea     rcx, [rbx+8]; lpCriticalSection
0x18001319d  mov     qword ptr [rbx+40h], 0
0x1800131a5  call    cs:__imp_DeleteCriticalSection
0x1800131ac  nop     dword ptr [rax+rax+00h]
0x1800131b1  mov     dword ptr [rbx], 0
0x1800131b7  mov     rcx, [rbx+38h]; Block
0x1800131bb  test    rcx, rcx
0x1800131be  jz      short loc_1800131D4
0x1800131c0  call    cs:__imp_free
0x1800131c7  nop     dword ptr [rax+rax+00h]
0x1800131cc  mov     qword ptr [rbx+38h], 0
0x1800131d4  mov     rsi, [rsp+28h+arg_8]
0x1800131d9  mov     qword ptr [rbx+40h], 0
0x1800131e1  mov     rbx, [rsp+28h+arg_0]
0x1800131e6  add     rsp, 20h
0x1800131ea  pop     rdi
0x1800131eb  retn
0x1800131ed  mov     ecx, 0C000008Ch; unsigned int
0x1800131f2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
