# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180007238`
- end: `0x1800072ef`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f010`

## callees

- `0x18000619c`
- `0x180007238`

## import_xrefs

- `msvcrt!free` at `0x18000728f`
- `msvcrt!free` at `0x1800072be`
- `msvcrt!free` at `0x18000728f`
- `msvcrt!free` at `0x1800072be`
- `KERNEL32!DeleteCriticalSection` at `0x1800072a9`
- `KERNEL32!DeleteCriticalSection` at `0x1800072a9`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180007279`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x180007279`

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
        JUMPOUT(0x1800072EELL);
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
0x180007238  mov     [rsp+arg_0], rbx
0x18000723d  mov     [rsp+arg_8], rsi
0x180007242  push    rdi
0x180007243  sub     rsp, 20h
0x180007247  mov     rbx, rcx
0x18000724a  test    rcx, rcx
0x18000724d  jz      short loc_1800072B5
0x18000724f  cmp     dword ptr [rcx], 48h ; 'H'
0x180007252  jnz     short loc_1800072B5
0x180007254  mov     rsi, cs:hInstance
0x18000725b  xor     edi, edi
0x18000725d  cmp     [rcx+40h], edi
0x180007260  jle     short loc_180007286
0x180007262  test    edi, edi
0x180007264  js      short loc_1800072E4
0x180007266  cmp     edi, [rbx+40h]
0x180007269  jge     short loc_1800072E4
0x18000726b  mov     rax, [rbx+38h]
0x18000726f  mov     rdx, rsi; hInstance
0x180007272  movsxd  rcx, edi
0x180007275  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180007279  call    cs:__imp_UnregisterClassA
0x18000727f  inc     edi
0x180007281  cmp     edi, [rbx+40h]
0x180007284  jl      short loc_180007262
0x180007286  mov     rcx, [rbx+38h]; Block
0x18000728a  test    rcx, rcx
0x18000728d  jz      short loc_18000729D
0x18000728f  call    cs:__imp_free
0x180007295  mov     qword ptr [rbx+38h], 0
0x18000729d  lea     rcx, [rbx+8]; lpCriticalSection
0x1800072a1  mov     qword ptr [rbx+40h], 0
0x1800072a9  call    cs:__imp_DeleteCriticalSection
0x1800072af  mov     dword ptr [rbx], 0
0x1800072b5  mov     rcx, [rbx+38h]; Block
0x1800072b9  test    rcx, rcx
0x1800072bc  jz      short loc_1800072CC
0x1800072be  call    cs:__imp_free
0x1800072c4  mov     qword ptr [rbx+38h], 0
0x1800072cc  mov     rsi, [rsp+28h+arg_8]
0x1800072d1  mov     qword ptr [rbx+40h], 0
0x1800072d9  mov     rbx, [rsp+28h+arg_0]
0x1800072de  add     rsp, 20h
0x1800072e2  pop     rdi
0x1800072e3  retn
0x1800072e4  mov     ecx, 0C000008Ch; unsigned int
0x1800072e9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
