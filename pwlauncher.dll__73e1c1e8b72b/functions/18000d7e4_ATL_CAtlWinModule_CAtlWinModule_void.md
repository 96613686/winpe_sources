# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000d7e4`
- end: `0x18000d89b`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010db0`

## callees

- `0x180005028`
- `0x18000d7e4`

## import_xrefs

- `msvcrt!free` at `0x18000d83b`
- `msvcrt!free` at `0x18000d86a`
- `msvcrt!free` at `0x18000d83b`
- `msvcrt!free` at `0x18000d86a`
- `USER32!UnregisterClassA` at `0x18000d825`
- `USER32!UnregisterClassA` at `0x18000d825`
- `KERNEL32!DeleteCriticalSection` at `0x18000d855`
- `KERNEL32!DeleteCriticalSection` at `0x18000d855`

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
        JUMPOUT(0x18000D89ALL);
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
0x18000d7e4  mov     [rsp+arg_0], rbx
0x18000d7e9  mov     [rsp+arg_8], rsi
0x18000d7ee  push    rdi
0x18000d7ef  sub     rsp, 20h
0x18000d7f3  mov     rbx, rcx
0x18000d7f6  test    rcx, rcx
0x18000d7f9  jz      short loc_18000D861
0x18000d7fb  cmp     dword ptr [rcx], 48h ; 'H'
0x18000d7fe  jnz     short loc_18000D861
0x18000d800  mov     rsi, cs:hInstance
0x18000d807  xor     edi, edi
0x18000d809  cmp     [rcx+40h], edi
0x18000d80c  jle     short loc_18000D832
0x18000d80e  test    edi, edi
0x18000d810  js      short loc_18000D890
0x18000d812  cmp     edi, [rbx+40h]
0x18000d815  jge     short loc_18000D890
0x18000d817  mov     rax, [rbx+38h]
0x18000d81b  mov     rdx, rsi; hInstance
0x18000d81e  movsxd  rcx, edi
0x18000d821  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000d825  call    cs:__imp_UnregisterClassA
0x18000d82b  inc     edi
0x18000d82d  cmp     edi, [rbx+40h]
0x18000d830  jl      short loc_18000D80E
0x18000d832  mov     rcx, [rbx+38h]; Block
0x18000d836  test    rcx, rcx
0x18000d839  jz      short loc_18000D849
0x18000d83b  call    cs:__imp_free
0x18000d841  mov     qword ptr [rbx+38h], 0
0x18000d849  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d84d  mov     qword ptr [rbx+40h], 0
0x18000d855  call    cs:__imp_DeleteCriticalSection
0x18000d85b  mov     dword ptr [rbx], 0
0x18000d861  mov     rcx, [rbx+38h]; Block
0x18000d865  test    rcx, rcx
0x18000d868  jz      short loc_18000D878
0x18000d86a  call    cs:__imp_free
0x18000d870  mov     qword ptr [rbx+38h], 0
0x18000d878  mov     rsi, [rsp+28h+arg_8]
0x18000d87d  mov     qword ptr [rbx+40h], 0
0x18000d885  mov     rbx, [rsp+28h+arg_0]
0x18000d88a  add     rsp, 20h
0x18000d88e  pop     rdi
0x18000d88f  retn
0x18000d890  mov     ecx, 0C000008Ch; unsigned int
0x18000d895  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
