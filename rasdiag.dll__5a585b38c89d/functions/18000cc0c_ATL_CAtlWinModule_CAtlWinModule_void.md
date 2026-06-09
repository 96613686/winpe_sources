# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000cc0c`
- end: `0x18000cce8`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `220`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e670`

## callees

- `0x180005ca0`
- `0x18000cc0c`

## import_xrefs

- `msvcrt!free` at `0x18000cc75`
- `msvcrt!free` at `0x18000ccb0`
- `msvcrt!free` at `0x18000cc75`
- `msvcrt!free` at `0x18000ccb0`
- `KERNEL32!DeleteCriticalSection` at `0x18000cc95`
- `KERNEL32!DeleteCriticalSection` at `0x18000cc95`
- `USER32!UnregisterClassA` at `0x18000cc59`
- `USER32!UnregisterClassA` at `0x18000cc59`

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
        JUMPOUT(0x18000CCE7LL);
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
0x18000cc0c  mov     [rsp+arg_0], rbx
0x18000cc11  mov     [rsp+arg_8], rsi
0x18000cc16  push    rdi
0x18000cc17  sub     rsp, 20h
0x18000cc1b  mov     rbx, rcx
0x18000cc1e  test    rcx, rcx
0x18000cc21  jz      loc_18000CCA7
0x18000cc27  cmp     dword ptr [rcx], 48h ; 'H'
0x18000cc2a  jnz     short loc_18000CCA7
0x18000cc2c  mov     rsi, cs:hModule
0x18000cc33  xor     edi, edi
0x18000cc35  cmp     [rcx+40h], edi
0x18000cc38  jle     short loc_18000CC6C
0x18000cc3a  test    edi, edi
0x18000cc3c  js      loc_18000CCDD
0x18000cc42  cmp     edi, [rbx+40h]
0x18000cc45  jge     loc_18000CCDD
0x18000cc4b  mov     rax, [rbx+38h]
0x18000cc4f  mov     rdx, rsi; hInstance
0x18000cc52  movsxd  rcx, edi
0x18000cc55  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000cc59  call    cs:__imp_UnregisterClassA
0x18000cc60  nop     dword ptr [rax+rax+00h]
0x18000cc65  inc     edi
0x18000cc67  cmp     edi, [rbx+40h]
0x18000cc6a  jl      short loc_18000CC3A
0x18000cc6c  mov     rcx, [rbx+38h]; Block
0x18000cc70  test    rcx, rcx
0x18000cc73  jz      short loc_18000CC89
0x18000cc75  call    cs:__imp_free
0x18000cc7c  nop     dword ptr [rax+rax+00h]
0x18000cc81  mov     qword ptr [rbx+38h], 0
0x18000cc89  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cc8d  mov     qword ptr [rbx+40h], 0
0x18000cc95  call    cs:__imp_DeleteCriticalSection
0x18000cc9c  nop     dword ptr [rax+rax+00h]
0x18000cca1  mov     dword ptr [rbx], 0
0x18000cca7  mov     rcx, [rbx+38h]; Block
0x18000ccab  test    rcx, rcx
0x18000ccae  jz      short loc_18000CCC4
0x18000ccb0  call    cs:__imp_free
0x18000ccb7  nop     dword ptr [rax+rax+00h]
0x18000ccbc  mov     qword ptr [rbx+38h], 0
0x18000ccc4  mov     rsi, [rsp+28h+arg_8]
0x18000ccc9  mov     qword ptr [rbx+40h], 0
0x18000ccd1  mov     rbx, [rsp+28h+arg_0]
0x18000ccd6  add     rsp, 20h
0x18000ccda  pop     rdi
0x18000ccdb  retn
0x18000ccdd  mov     ecx, 0C000008Ch; unsigned int
0x18000cce2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
