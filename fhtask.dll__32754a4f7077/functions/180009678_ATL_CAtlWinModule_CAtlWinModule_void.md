# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180009678`
- end: `0x18000972f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a0d0`

## callees

- `0x180005328`
- `0x180009678`

## import_xrefs

- `msvcrt!free` at `0x1800096cf`
- `msvcrt!free` at `0x1800096fe`
- `msvcrt!free` at `0x1800096cf`
- `msvcrt!free` at `0x1800096fe`
- `KERNEL32!DeleteCriticalSection` at `0x1800096e9`
- `KERNEL32!DeleteCriticalSection` at `0x1800096e9`
- `USER32!UnregisterClassA` at `0x1800096b9`
- `USER32!UnregisterClassA` at `0x1800096b9`

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
        JUMPOUT(0x18000972ELL);
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
0x180009678  mov     [rsp+arg_0], rbx
0x18000967d  mov     [rsp+arg_8], rsi
0x180009682  push    rdi
0x180009683  sub     rsp, 20h
0x180009687  mov     rbx, rcx
0x18000968a  test    rcx, rcx
0x18000968d  jz      short loc_1800096F5
0x18000968f  cmp     dword ptr [rcx], 48h ; 'H'
0x180009692  jnz     short loc_1800096F5
0x180009694  mov     rsi, cs:hInstance
0x18000969b  xor     edi, edi
0x18000969d  cmp     [rcx+40h], edi
0x1800096a0  jle     short loc_1800096C6
0x1800096a2  test    edi, edi
0x1800096a4  js      short loc_180009724
0x1800096a6  cmp     edi, [rbx+40h]
0x1800096a9  jge     short loc_180009724
0x1800096ab  mov     rax, [rbx+38h]
0x1800096af  mov     rdx, rsi; hInstance
0x1800096b2  movsxd  rcx, edi
0x1800096b5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x1800096b9  call    cs:__imp_UnregisterClassA
0x1800096bf  inc     edi
0x1800096c1  cmp     edi, [rbx+40h]
0x1800096c4  jl      short loc_1800096A2
0x1800096c6  mov     rcx, [rbx+38h]; Block
0x1800096ca  test    rcx, rcx
0x1800096cd  jz      short loc_1800096DD
0x1800096cf  call    cs:__imp_free
0x1800096d5  mov     qword ptr [rbx+38h], 0
0x1800096dd  lea     rcx, [rbx+8]; lpCriticalSection
0x1800096e1  mov     qword ptr [rbx+40h], 0
0x1800096e9  call    cs:__imp_DeleteCriticalSection
0x1800096ef  mov     dword ptr [rbx], 0
0x1800096f5  mov     rcx, [rbx+38h]; Block
0x1800096f9  test    rcx, rcx
0x1800096fc  jz      short loc_18000970C
0x1800096fe  call    cs:__imp_free
0x180009704  mov     qword ptr [rbx+38h], 0
0x18000970c  mov     rsi, [rsp+28h+arg_8]
0x180009711  mov     qword ptr [rbx+40h], 0
0x180009719  mov     rbx, [rsp+28h+arg_0]
0x18000971e  add     rsp, 20h
0x180009722  pop     rdi
0x180009723  retn
0x180009724  mov     ecx, 0C000008Ch; unsigned int
0x180009729  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
