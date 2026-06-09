# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000795c`
- end: `0x180007a13`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b710`

## callees

- `0x180002964`
- `0x18000795c`

## import_xrefs

- `msvcrt!free` at `0x1800079b3`
- `msvcrt!free` at `0x1800079e2`
- `msvcrt!free` at `0x1800079b3`
- `msvcrt!free` at `0x1800079e2`
- `KERNEL32!DeleteCriticalSection` at `0x1800079cd`
- `KERNEL32!DeleteCriticalSection` at `0x1800079cd`
- `USER32!UnregisterClassA` at `0x18000799d`
- `USER32!UnregisterClassA` at `0x18000799d`

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
        JUMPOUT(0x180007A12LL);
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
0x18000795c  mov     [rsp+arg_0], rbx
0x180007961  mov     [rsp+arg_8], rsi
0x180007966  push    rdi
0x180007967  sub     rsp, 20h
0x18000796b  mov     rbx, rcx
0x18000796e  test    rcx, rcx
0x180007971  jz      short loc_1800079D9
0x180007973  cmp     dword ptr [rcx], 48h ; 'H'
0x180007976  jnz     short loc_1800079D9
0x180007978  mov     rsi, cs:hInstance
0x18000797f  xor     edi, edi
0x180007981  cmp     [rcx+40h], edi
0x180007984  jle     short loc_1800079AA
0x180007986  test    edi, edi
0x180007988  js      short loc_180007A08
0x18000798a  cmp     edi, [rbx+40h]
0x18000798d  jge     short loc_180007A08
0x18000798f  mov     rax, [rbx+38h]
0x180007993  mov     rdx, rsi; hInstance
0x180007996  movsxd  rcx, edi
0x180007999  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000799d  call    cs:__imp_UnregisterClassA
0x1800079a3  inc     edi
0x1800079a5  cmp     edi, [rbx+40h]
0x1800079a8  jl      short loc_180007986
0x1800079aa  mov     rcx, [rbx+38h]; Block
0x1800079ae  test    rcx, rcx
0x1800079b1  jz      short loc_1800079C1
0x1800079b3  call    cs:__imp_free
0x1800079b9  mov     qword ptr [rbx+38h], 0
0x1800079c1  lea     rcx, [rbx+8]; lpCriticalSection
0x1800079c5  mov     qword ptr [rbx+40h], 0
0x1800079cd  call    cs:__imp_DeleteCriticalSection
0x1800079d3  mov     dword ptr [rbx], 0
0x1800079d9  mov     rcx, [rbx+38h]; Block
0x1800079dd  test    rcx, rcx
0x1800079e0  jz      short loc_1800079F0
0x1800079e2  call    cs:__imp_free
0x1800079e8  mov     qword ptr [rbx+38h], 0
0x1800079f0  mov     rsi, [rsp+28h+arg_8]
0x1800079f5  mov     qword ptr [rbx+40h], 0
0x1800079fd  mov     rbx, [rsp+28h+arg_0]
0x180007a02  add     rsp, 20h
0x180007a06  pop     rdi
0x180007a07  retn
0x180007a08  mov     ecx, 0C000008Ch; unsigned int
0x180007a0d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
