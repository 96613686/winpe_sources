# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x14002bf00`
- end: `0x14002bfb0`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002ff90`

## callees

- `0x1400027c0`
- `0x14002bf00`
- `0x14002c054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002bf70`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14002bf70`
- `USER32!UnregisterClassA` at `0x14002bf41`
- `USER32!UnregisterClassA` at `0x14002bf41`

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
    v3 = (HINSTANCE)hInstance;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException((unsigned int)this, a2);
        JUMPOUT(0x14002BFAFLL);
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
0x14002bf00  mov     [rsp+arg_0], rbx
0x14002bf05  mov     [rsp+arg_8], rsi
0x14002bf0a  push    rdi
0x14002bf0b  sub     rsp, 20h
0x14002bf0f  mov     rbx, rcx
0x14002bf12  test    rcx, rcx
0x14002bf15  jz      short loc_14002BF7C
0x14002bf17  cmp     dword ptr [rcx], 48h ; 'H'
0x14002bf1a  jnz     short loc_14002BF7C
0x14002bf1c  mov     rsi, cs:hInstance
0x14002bf23  xor     edi, edi
0x14002bf25  cmp     [rcx+40h], edi
0x14002bf28  jle     short loc_14002BF4E
0x14002bf2a  test    edi, edi
0x14002bf2c  js      short loc_14002BFAA
0x14002bf2e  cmp     edi, [rbx+40h]
0x14002bf31  jge     short loc_14002BFAA
0x14002bf33  mov     rax, [rbx+38h]
0x14002bf37  mov     rdx, rsi; hInstance
0x14002bf3a  movsxd  rcx, edi
0x14002bf3d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x14002bf41  call    cs:__imp_UnregisterClassA
0x14002bf47  inc     edi
0x14002bf49  cmp     edi, [rbx+40h]
0x14002bf4c  jl      short loc_14002BF2A
0x14002bf4e  mov     rcx, [rbx+38h]; Block
0x14002bf52  test    rcx, rcx
0x14002bf55  jz      short loc_14002BF64
0x14002bf57  call    free
0x14002bf5c  mov     qword ptr [rbx+38h], 0
0x14002bf64  lea     rcx, [rbx+8]; lpCriticalSection
0x14002bf68  mov     qword ptr [rbx+40h], 0
0x14002bf70  call    cs:__imp_DeleteCriticalSection
0x14002bf76  mov     dword ptr [rbx], 0
0x14002bf7c  mov     rcx, [rbx+38h]; Block
0x14002bf80  test    rcx, rcx
0x14002bf83  jz      short loc_14002BF92
0x14002bf85  call    free
0x14002bf8a  mov     qword ptr [rbx+38h], 0
0x14002bf92  mov     rsi, [rsp+28h+arg_8]
0x14002bf97  mov     qword ptr [rbx+40h], 0
0x14002bf9f  mov     rbx, [rsp+28h+arg_0]
0x14002bfa4  add     rsp, 20h
0x14002bfa8  pop     rdi
0x14002bfa9  retn
0x14002bfaa  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
