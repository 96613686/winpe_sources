# TClientMemoryPool::~TClientMemoryPool(void)

- ea: `0x140019da4`
- end: `0x140019e34`
- name: `??1TClientMemoryPool@@UEAA@XZ`
- size: `144`
- prototype: `void __fastcall(TClientMemoryPool *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140019e60`

## callees

- `0x1400086f8`
- `0x140019da4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140019e0a`
- `KERNEL32!DeleteCriticalSection` at `0x140019e0a`

## pseudocode

```c
void __fastcall TClientMemoryPool::~TClientMemoryPool(TClientMemoryPool *this)
{
  bool v1; // zf

  v1 = *((_DWORD *)this + 23) == 0;
  *(_QWORD *)this = &TClientMemoryPool::`vftable'{for `IMemoryPool'};
  *((_QWORD *)this + 1) = &TClientMemoryPool::`vftable'{for `NCOMLibrary::TUnknown'};
  if ( !v1
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5d3f4855fb0a319ffdf97c264d67d061_Traceguids);
  }
  if ( *((int *)this + 18) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 18) = -2147467259;
  }
  *((_QWORD *)this + 1) = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x140019da4  mov     [rsp+arg_0], rbx
0x140019da9  push    rdi
0x140019daa  sub     rsp, 20h
0x140019dae  cmp     dword ptr [rcx+5Ch], 0
0x140019db2  lea     rax, ??_7TClientMemoryPool@@6BIMemoryPool@@@; const TClientMemoryPool::`vftable'{for `IMemoryPool'}
0x140019db9  mov     [rcx], rax
0x140019dbc  mov     rbx, rcx
0x140019dbf  lea     rax, ??_7TClientMemoryPool@@6BTUnknown@NCOMLibrary@@@; const TClientMemoryPool::`vftable'{for `NCOMLibrary::TUnknown'}
0x140019dc6  mov     [rcx+8], rax
0x140019dca  jz      short loc_140019E00
0x140019dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140019dd3  lea     rax, WPP_GLOBAL_Control
0x140019dda  cmp     rcx, rax
0x140019ddd  jz      short loc_140019E00
0x140019ddf  test    byte ptr [rcx+1Ch], 8
0x140019de3  jz      short loc_140019E00
0x140019de5  cmp     byte ptr [rcx+19h], 3
0x140019de9  jb      short loc_140019E00
0x140019deb  mov     rcx, [rcx+10h]
0x140019def  lea     r8, WPP_5d3f4855fb0a319ffdf97c264d67d061_Traceguids
0x140019df6  mov     edx, 0Fh
0x140019dfb  call    WPP_SF_
0x140019e00  cmp     dword ptr [rbx+48h], 0
0x140019e04  jl      short loc_140019E17
0x140019e06  lea     rcx, [rbx+18h]; lpCriticalSection
0x140019e0a  call    cs:__imp_DeleteCriticalSection
0x140019e10  mov     dword ptr [rbx+48h], 80004005h
0x140019e17  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140019e1e  mov     [rbx+8], rax
0x140019e22  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x140019e29  mov     rbx, [rsp+28h+arg_0]
0x140019e2e  add     rsp, 20h
0x140019e32  pop     rdi
0x140019e33  retn
```
