# BrandingTheme<VSSPLASHSCREENTHEME5>::~BrandingTheme<VSSPLASHSCREENTHEME5>(void)

- ea: `0x14003d3c4`
- end: `0x14003d45e`
- name: `??1?$BrandingTheme@UVSSPLASHSCREENTHEME5@@@@QEAA@XZ`
- size: `154`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14003c020`
- `0x14003da68`
- `0x14003dbd8`
- `0x14003e6d4`

## callees

- `0x14003d3c4`

## import_xrefs

- `GDI32!DeleteObject` at `0x14003d3dd`
- `GDI32!DeleteObject` at `0x14003d3f0`
- `GDI32!DeleteObject` at `0x14003d404`
- `GDI32!DeleteObject` at `0x14003d3dd`
- `GDI32!DeleteObject` at `0x14003d3f0`
- `GDI32!DeleteObject` at `0x14003d404`

## pseudocode

```c
__int64 __fastcall BrandingTheme<VSSPLASHSCREENTHEME5>::~BrandingTheme<VSSPLASHSCREENTHEME5>(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  volatile signed __int32 *v5; // rdx
  volatile signed __int32 *v6; // rdx
  signed __int32 v7; // eax
  bool v8; // cc
  __int64 result; // rax

  if ( (*(_DWORD *)a1 & 0xFFFF0000) != 0 )
  {
    v2 = *(void **)a1;
    if ( v2 )
    {
      DeleteObject(v2);
      *(_QWORD *)a1 = 0;
    }
    v3 = *(void **)(a1 + 104);
    if ( v3 )
    {
      DeleteObject(v3);
      *(_QWORD *)(a1 + 104) = 0;
    }
    v4 = *(void **)(a1 + 120);
    if ( v4 )
    {
      DeleteObject(v4);
      *(_QWORD *)(a1 + 120) = 0;
    }
  }
  v5 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 136) - 24LL);
  if ( _InterlockedExchangeAdd(v5 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  }
  v6 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 128) - 24LL);
  v7 = _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF);
  v8 = v7 <= 1;
  result = (unsigned int)(v7 - 1);
  if ( v8 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  }
  return result;
}

```

## disassembly

```asm
0x14003d3c4  push    rbx
0x14003d3c6  sub     rsp, 20h
0x14003d3ca  mov     rbx, rcx
0x14003d3cd  test    dword ptr [rcx], 0FFFF0000h
0x14003d3d3  jz      short loc_14003D40F
0x14003d3d5  mov     rcx, [rcx]; ho
0x14003d3d8  test    rcx, rcx
0x14003d3db  jz      short loc_14003D3E7
0x14003d3dd  call    cs:__imp_DeleteObject
0x14003d3e3  and     qword ptr [rbx], 0
0x14003d3e7  mov     rcx, [rbx+68h]; ho
0x14003d3eb  test    rcx, rcx
0x14003d3ee  jz      short loc_14003D3FB
0x14003d3f0  call    cs:__imp_DeleteObject
0x14003d3f6  and     qword ptr [rbx+68h], 0
0x14003d3fb  mov     rcx, [rbx+78h]; ho
0x14003d3ff  test    rcx, rcx
0x14003d402  jz      short loc_14003D40F
0x14003d404  call    cs:__imp_DeleteObject
0x14003d40a  and     qword ptr [rbx+78h], 0
0x14003d40f  mov     rdx, [rbx+88h]
0x14003d416  sub     rdx, 18h
0x14003d41a  or      eax, 0FFFFFFFFh
0x14003d41d  lock xadd [rdx+10h], eax
0x14003d422  sub     eax, 1
0x14003d425  jg      short loc_14003D433
0x14003d427  lfence
0x14003d42a  mov     rcx, [rdx]
0x14003d42d  mov     rax, [rcx]
0x14003d430  call    qword ptr [rax+8]
0x14003d433  mov     rdx, [rbx+80h]
0x14003d43a  sub     rdx, 18h
0x14003d43e  or      eax, 0FFFFFFFFh
0x14003d441  lock xadd [rdx+10h], eax
0x14003d446  sub     eax, 1
0x14003d449  jg      short loc_14003D458
0x14003d44b  lfence
0x14003d44e  mov     rcx, [rdx]
0x14003d451  mov     rax, [rcx]
0x14003d454  call    qword ptr [rax+8]
0x14003d457  nop
0x14003d458  add     rsp, 20h
0x14003d45c  pop     rbx
0x14003d45d  retn
```
