# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180016ee8`
- end: `0x180016f9f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018970`

## callees

- `0x1800046fc`
- `0x180016ee8`

## import_xrefs

- `msvcrt!free` at `0x180016f3f`
- `msvcrt!free` at `0x180016f6e`
- `msvcrt!free` at `0x180016f3f`
- `msvcrt!free` at `0x180016f6e`
- `USER32!UnregisterClassA` at `0x180016f29`
- `USER32!UnregisterClassA` at `0x180016f29`
- `KERNEL32!DeleteCriticalSection` at `0x180016f59`
- `KERNEL32!DeleteCriticalSection` at `0x180016f59`

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
        JUMPOUT(0x180016F9ELL);
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
0x180016ee8  mov     [rsp+arg_0], rbx
0x180016eed  mov     [rsp+arg_8], rsi
0x180016ef2  push    rdi
0x180016ef3  sub     rsp, 20h
0x180016ef7  mov     rbx, rcx
0x180016efa  test    rcx, rcx
0x180016efd  jz      short loc_180016F65
0x180016eff  cmp     dword ptr [rcx], 48h ; 'H'
0x180016f02  jnz     short loc_180016F65
0x180016f04  mov     rsi, cs:hInstance
0x180016f0b  xor     edi, edi
0x180016f0d  cmp     [rcx+40h], edi
0x180016f10  jle     short loc_180016F36
0x180016f12  test    edi, edi
0x180016f14  js      short loc_180016F94
0x180016f16  cmp     edi, [rbx+40h]
0x180016f19  jge     short loc_180016F94
0x180016f1b  mov     rax, [rbx+38h]
0x180016f1f  mov     rdx, rsi; hInstance
0x180016f22  movsxd  rcx, edi
0x180016f25  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180016f29  call    cs:__imp_UnregisterClassA
0x180016f2f  inc     edi
0x180016f31  cmp     edi, [rbx+40h]
0x180016f34  jl      short loc_180016F12
0x180016f36  mov     rcx, [rbx+38h]; Block
0x180016f3a  test    rcx, rcx
0x180016f3d  jz      short loc_180016F4D
0x180016f3f  call    cs:__imp_free
0x180016f45  mov     qword ptr [rbx+38h], 0
0x180016f4d  lea     rcx, [rbx+8]; lpCriticalSection
0x180016f51  mov     qword ptr [rbx+40h], 0
0x180016f59  call    cs:__imp_DeleteCriticalSection
0x180016f5f  mov     dword ptr [rbx], 0
0x180016f65  mov     rcx, [rbx+38h]; Block
0x180016f69  test    rcx, rcx
0x180016f6c  jz      short loc_180016F7C
0x180016f6e  call    cs:__imp_free
0x180016f74  mov     qword ptr [rbx+38h], 0
0x180016f7c  mov     rsi, [rsp+28h+arg_8]
0x180016f81  mov     qword ptr [rbx+40h], 0
0x180016f89  mov     rbx, [rsp+28h+arg_0]
0x180016f8e  add     rsp, 20h
0x180016f92  pop     rdi
0x180016f93  retn
0x180016f94  mov     ecx, 0C000008Ch; unsigned int
0x180016f99  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
