# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18001b960`
- end: `0x18001ba17`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020a90`

## callees

- `0x180006f84`
- `0x18001b960`

## import_xrefs

- `msvcrt!free` at `0x18001b9b7`
- `msvcrt!free` at `0x18001b9e6`
- `msvcrt!free` at `0x18001b9b7`
- `msvcrt!free` at `0x18001b9e6`
- `KERNEL32!DeleteCriticalSection` at `0x18001b9d1`
- `KERNEL32!DeleteCriticalSection` at `0x18001b9d1`
- `USER32!UnregisterClassA` at `0x18001b9a1`
- `USER32!UnregisterClassA` at `0x18001b9a1`

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
        JUMPOUT(0x18001BA16LL);
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
0x18001b960  mov     [rsp+arg_0], rbx
0x18001b965  mov     [rsp+arg_8], rsi
0x18001b96a  push    rdi
0x18001b96b  sub     rsp, 20h
0x18001b96f  mov     rbx, rcx
0x18001b972  test    rcx, rcx
0x18001b975  jz      short loc_18001B9DD
0x18001b977  cmp     dword ptr [rcx], 48h ; 'H'
0x18001b97a  jnz     short loc_18001B9DD
0x18001b97c  mov     rsi, cs:hModule
0x18001b983  xor     edi, edi
0x18001b985  cmp     [rcx+40h], edi
0x18001b988  jle     short loc_18001B9AE
0x18001b98a  test    edi, edi
0x18001b98c  js      short loc_18001BA0C
0x18001b98e  cmp     edi, [rbx+40h]
0x18001b991  jge     short loc_18001BA0C
0x18001b993  mov     rax, [rbx+38h]
0x18001b997  mov     rdx, rsi; hInstance
0x18001b99a  movsxd  rcx, edi
0x18001b99d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18001b9a1  call    cs:__imp_UnregisterClassA
0x18001b9a7  inc     edi
0x18001b9a9  cmp     edi, [rbx+40h]
0x18001b9ac  jl      short loc_18001B98A
0x18001b9ae  mov     rcx, [rbx+38h]; Block
0x18001b9b2  test    rcx, rcx
0x18001b9b5  jz      short loc_18001B9C5
0x18001b9b7  call    cs:__imp_free
0x18001b9bd  mov     qword ptr [rbx+38h], 0
0x18001b9c5  lea     rcx, [rbx+8]; lpCriticalSection
0x18001b9c9  mov     qword ptr [rbx+40h], 0
0x18001b9d1  call    cs:__imp_DeleteCriticalSection
0x18001b9d7  mov     dword ptr [rbx], 0
0x18001b9dd  mov     rcx, [rbx+38h]; Block
0x18001b9e1  test    rcx, rcx
0x18001b9e4  jz      short loc_18001B9F4
0x18001b9e6  call    cs:__imp_free
0x18001b9ec  mov     qword ptr [rbx+38h], 0
0x18001b9f4  mov     rsi, [rsp+28h+arg_8]
0x18001b9f9  mov     qword ptr [rbx+40h], 0
0x18001ba01  mov     rbx, [rsp+28h+arg_0]
0x18001ba06  add     rsp, 20h
0x18001ba0a  pop     rdi
0x18001ba0b  retn
0x18001ba0c  mov     ecx, 0C000008Ch; unsigned int
0x18001ba11  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
