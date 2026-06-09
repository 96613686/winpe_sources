# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180007e08`
- end: `0x180007ebd`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012880`

## callees

- `0x180002a34`
- `0x1800063bc`
- `0x180007e08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007e78`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007e78`
- `USER32!UnregisterClassA` at `0x180007e49`
- `USER32!UnregisterClassA` at `0x180007e49`

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
        JUMPOUT(0x180007EBCLL);
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
0x180007e08  mov     [rsp+arg_0], rbx
0x180007e0d  mov     [rsp+arg_8], rsi
0x180007e12  push    rdi
0x180007e13  sub     rsp, 20h
0x180007e17  mov     rbx, rcx
0x180007e1a  test    rcx, rcx
0x180007e1d  jz      short loc_180007E84
0x180007e1f  cmp     dword ptr [rcx], 48h ; 'H'
0x180007e22  jnz     short loc_180007E84
0x180007e24  mov     rsi, cs:hInstance
0x180007e2b  xor     edi, edi
0x180007e2d  cmp     [rcx+40h], edi
0x180007e30  jle     short loc_180007E56
0x180007e32  test    edi, edi
0x180007e34  js      short loc_180007EB2
0x180007e36  cmp     edi, [rbx+40h]
0x180007e39  jge     short loc_180007EB2
0x180007e3b  mov     rax, [rbx+38h]
0x180007e3f  mov     rdx, rsi; hInstance
0x180007e42  movsxd  rcx, edi
0x180007e45  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180007e49  call    cs:__imp_UnregisterClassA
0x180007e4f  inc     edi
0x180007e51  cmp     edi, [rbx+40h]
0x180007e54  jl      short loc_180007E32
0x180007e56  mov     rcx, [rbx+38h]; Block
0x180007e5a  test    rcx, rcx
0x180007e5d  jz      short loc_180007E6C
0x180007e5f  call    free
0x180007e64  mov     qword ptr [rbx+38h], 0
0x180007e6c  lea     rcx, [rbx+8]; lpCriticalSection
0x180007e70  mov     qword ptr [rbx+40h], 0
0x180007e78  call    cs:__imp_DeleteCriticalSection
0x180007e7e  mov     dword ptr [rbx], 0
0x180007e84  mov     rcx, [rbx+38h]; Block
0x180007e88  test    rcx, rcx
0x180007e8b  jz      short loc_180007E9A
0x180007e8d  call    free
0x180007e92  mov     qword ptr [rbx+38h], 0
0x180007e9a  mov     rsi, [rsp+28h+arg_8]
0x180007e9f  mov     qword ptr [rbx+40h], 0
0x180007ea7  mov     rbx, [rsp+28h+arg_0]
0x180007eac  add     rsp, 20h
0x180007eb0  pop     rdi
0x180007eb1  retn
0x180007eb2  mov     ecx, 0C000008Ch; unsigned int
0x180007eb7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
