# CDirectDraw::CDirectDraw(CRenderer *,CCritSec *,IUnknown *,long *)

- ea: `0x18009e414`
- end: `0x18009e68d`
- name: `??0CDirectDraw@@QEAA@PEAVCRenderer@@PEAVCCritSec@@PEAUIUnknown@@PEAJ@Z`
- size: `633`
- prototype: `CDirectDraw *__fastcall(CDirectDraw *__hidden this, struct CRenderer *, struct CCritSec *, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18009c2cc`

## callees

- `0x180039250`
- `0x18005cbd4`
- `0x18009e414`

## import_xrefs

- `KERNEL32!GetProfileIntW` at `0x18009e5b0`
- `KERNEL32!GetProfileIntW` at `0x18009e5d4`
- `KERNEL32!GetProfileIntW` at `0x18009e5f4`
- `KERNEL32!GetProfileIntW` at `0x18009e614`
- `KERNEL32!GetProfileIntW` at `0x18009e634`
- `KERNEL32!GetProfileIntW` at `0x18009e5b0`
- `KERNEL32!GetProfileIntW` at `0x18009e5d4`
- `KERNEL32!GetProfileIntW` at `0x18009e5f4`
- `KERNEL32!GetProfileIntW` at `0x18009e614`
- `KERNEL32!GetProfileIntW` at `0x18009e634`
- `KERNEL32!InitializeCriticalSection` at `0x18009e450`
- `KERNEL32!InitializeCriticalSection` at `0x18009e450`
- `USER32!SetRectEmpty` at `0x18009e557`
- `USER32!SetRectEmpty` at `0x18009e56a`
- `USER32!SetRectEmpty` at `0x18009e57d`
- `USER32!SetRectEmpty` at `0x18009e590`
- `USER32!SetRectEmpty` at `0x18009e557`
- `USER32!SetRectEmpty` at `0x18009e56a`
- `USER32!SetRectEmpty` at `0x18009e57d`
- `USER32!SetRectEmpty` at `0x18009e590`

## pseudocode

```c
CDirectDraw *__fastcall CDirectDraw::CDirectDraw(
        CDirectDraw *this,
        struct CRenderer *a2,
        struct CCritSec *a3,
        struct IUnknown *a4,
        int *a5)
{
  struct IUnknown *v8; // rax
  void *v9; // rcx

  _InterlockedAdd(&CBaseObject::m_cObjects, 1u);
  v8 = (struct IUnknown *)((char *)this + 8);
  if ( a4 )
    v8 = a4;
  *((_QWORD *)this + 2) = v8;
  *((_DWORD *)this + 6) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_QWORD *)this + 104) = 0;
  *(_QWORD *)this = &CDirectDraw::`vftable'{for `IDirectDrawVideo'};
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 1) = &CDirectDraw::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 106) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 109) = 0;
  *((_QWORD *)this + 110) = 0;
  *((_QWORD *)this + 111) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 113) = 0;
  *((_QWORD *)this + 114) = 0;
  *((_QWORD *)this + 115) = a2;
  *((_QWORD *)this + 116) = a3;
  memset_0((char *)this + 936, 0, 0x58u);
  *((_DWORD *)this + 244) = 1;
  *((_DWORD *)this + 242) = 1;
  *((_DWORD *)this + 256) = 255;
  *((_QWORD *)this + 129) = 0;
  *((_DWORD *)this + 260) = 0;
  *((_DWORD *)this + 261) = 1;
  *((_QWORD *)this + 131) = 1;
  *((_QWORD *)this + 132) = 0;
  *((_QWORD *)this + 133) = 0;
  *((_DWORD *)this + 268) = 0;
  *((_DWORD *)this + 269) = 1;
  *((_QWORD *)this + 135) = 1;
  *((_QWORD *)this + 136) = 0;
  *((_QWORD *)this + 137) = 0;
  *((_QWORD *)this + 138) = 0;
  *((_DWORD *)this + 278) = 0;
  SetRectEmpty((LPRECT)((char *)this + 1116));
  SetRectEmpty((LPRECT)((char *)this + 1132));
  SetRectEmpty((LPRECT)((char *)this + 1148));
  SetRectEmpty((LPRECT)((char *)this + 1164));
  if ( !GetProfileIntW(L"DrawDib", L"dva", 1) )
    *((_DWORD *)this + 261) = 0;
  *((_DWORD *)this + 256) = GetProfileIntW(L"DrawDib", L"AMovieDraw", 255);
  *((_DWORD *)this + 269) = GetProfileIntW(L"DrawDib", L"ScanLine", 1);
  *((_DWORD *)this + 270) = GetProfileIntW(L"DrawDib", L"Stretch", 1);
  *((_DWORD *)this + 271) = GetProfileIntW(L"DrawDib", L"FullScreen", 0);
  CMediaType::AllocFormatBuffer((CDirectDraw *)((char *)this + 936), 0x468u);
  v9 = (void *)*((_QWORD *)this + 127);
  if ( v9 )
    memset_0(v9, 0, 0x468u);
  else
    *a5 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x18009e414  push    rbx
0x18009e416  push    rbp
0x18009e417  push    rsi
0x18009e418  push    rdi
0x18009e419  push    r14
0x18009e41b  push    r15
0x18009e41d  sub     rsp, 28h
0x18009e421  mov     rsi, r8
0x18009e424  mov     rdi, rdx
0x18009e427  mov     r14, rcx
0x18009e42a  mov     r15d, 1
0x18009e430  lock add cs:?m_cObjects@CBaseObject@@0JA, r15d; long CBaseObject::m_cObjects
0x18009e438  lea     rax, [rcx+8]
0x18009e43c  xor     ebp, ebp
0x18009e43e  test    r9, r9
0x18009e441  cmovnz  rax, r9
0x18009e445  mov     [rcx+10h], rax
0x18009e449  mov     [rcx+18h], ebp
0x18009e44c  add     rcx, 20h ; ' '; lpCriticalSection
0x18009e450  call    cs:__imp_InitializeCriticalSection
0x18009e457  nop     dword ptr [rax+rax+00h]
0x18009e45c  mov     [r14+340h], rbp
0x18009e463  lea     rax, ??_7CDirectDraw@@6BIDirectDrawVideo@@@; const CDirectDraw::`vftable'{for `IDirectDrawVideo'}
0x18009e46a  mov     [r14], rax
0x18009e46d  lea     rbx, [r14+3A8h]
0x18009e474  mov     [r14+348h], rbp
0x18009e47b  lea     rax, ??_7CDirectDraw@@6BCUnknown@@@; const CDirectDraw::`vftable'{for `CUnknown'}
0x18009e482  mov     [r14+8], rax
0x18009e486  lea     r8d, [r15+57h]; Size
0x18009e48a  mov     [r14+350h], rbp
0x18009e491  xor     edx, edx; Val
0x18009e493  mov     [r14+358h], rbp
0x18009e49a  mov     rcx, rbx; void *
0x18009e49d  mov     [r14+360h], rbp
0x18009e4a4  mov     [r14+368h], rbp
0x18009e4ab  mov     [r14+370h], rbp
0x18009e4b2  mov     [r14+378h], rbp
0x18009e4b9  mov     [r14+380h], rbp
0x18009e4c0  mov     [r14+388h], rbp
0x18009e4c7  mov     [r14+390h], rbp
0x18009e4ce  mov     [r14+398h], rdi
0x18009e4d5  mov     [r14+3A0h], rsi
0x18009e4dc  call    memset_0
0x18009e4e1  mov     [rbx+28h], r15d
0x18009e4e5  lea     rcx, [r14+45Ch]; lprc
0x18009e4ec  mov     [rbx+20h], r15d
0x18009e4f0  mov     esi, 0FFh
0x18009e4f5  mov     [r14+400h], esi
0x18009e4fc  mov     [r14+408h], rbp
0x18009e503  mov     [r14+410h], ebp
0x18009e50a  mov     [r14+414h], r15d
0x18009e511  mov     [r14+418h], r15
0x18009e518  mov     [r14+420h], rbp
0x18009e51f  mov     [r14+428h], rbp
0x18009e526  mov     [r14+430h], ebp
0x18009e52d  mov     [r14+434h], r15d
0x18009e534  mov     [r14+438h], r15
0x18009e53b  mov     [r14+440h], rbp
0x18009e542  mov     [r14+448h], rbp
0x18009e549  mov     [r14+450h], rbp
0x18009e550  mov     [r14+458h], ebp
0x18009e557  call    cs:__imp_SetRectEmpty
0x18009e55e  nop     dword ptr [rax+rax+00h]
0x18009e563  lea     rcx, [r14+46Ch]; lprc
0x18009e56a  call    cs:__imp_SetRectEmpty
0x18009e571  nop     dword ptr [rax+rax+00h]
0x18009e576  lea     rcx, [r14+47Ch]; lprc
0x18009e57d  call    cs:__imp_SetRectEmpty
0x18009e584  nop     dword ptr [rax+rax+00h]
0x18009e589  lea     rcx, [r14+48Ch]; lprc
0x18009e590  call    cs:__imp_SetRectEmpty
0x18009e597  nop     dword ptr [rax+rax+00h]
0x18009e59c  lea     rdi, aDrawdib; "DrawDib"
0x18009e5a3  mov     r8d, r15d; nDefault
0x18009e5a6  mov     rcx, rdi; lpAppName
0x18009e5a9  lea     rdx, aDva; "dva"
0x18009e5b0  call    cs:__imp_GetProfileIntW
0x18009e5b7  nop     dword ptr [rax+rax+00h]
0x18009e5bc  test    eax, eax
0x18009e5be  jnz     short loc_18009E5C7
0x18009e5c0  mov     [r14+414h], ebp
0x18009e5c7  mov     r8d, esi; nDefault
0x18009e5ca  lea     rdx, aAmoviedraw; "AMovieDraw"
0x18009e5d1  mov     rcx, rdi; lpAppName
0x18009e5d4  call    cs:__imp_GetProfileIntW
0x18009e5db  nop     dword ptr [rax+rax+00h]
0x18009e5e0  mov     r8d, r15d; nDefault
0x18009e5e3  lea     rdx, aScanline; "ScanLine"
0x18009e5ea  mov     rcx, rdi; lpAppName
0x18009e5ed  mov     [r14+400h], eax
0x18009e5f4  call    cs:__imp_GetProfileIntW
0x18009e5fb  nop     dword ptr [rax+rax+00h]
0x18009e600  mov     r8d, r15d; nDefault
0x18009e603  lea     rdx, aStretch; "Stretch"
0x18009e60a  mov     rcx, rdi; lpAppName
0x18009e60d  mov     [r14+434h], eax
0x18009e614  call    cs:__imp_GetProfileIntW
0x18009e61b  nop     dword ptr [rax+rax+00h]
0x18009e620  xor     r8d, r8d; nDefault
0x18009e623  lea     rdx, aFullscreen; "FullScreen"
0x18009e62a  mov     rcx, rdi; lpAppName
0x18009e62d  mov     [r14+438h], eax
0x18009e634  call    cs:__imp_GetProfileIntW
0x18009e63b  nop     dword ptr [rax+rax+00h]
0x18009e640  mov     edi, 468h
0x18009e645  mov     rcx, rbx; this
0x18009e648  mov     edx, edi; unsigned int
0x18009e64a  mov     [r14+43Ch], eax
0x18009e651  call    ?AllocFormatBuffer@CMediaType@@QEAAPEAEK@Z; CMediaType::AllocFormatBuffer(ulong)
0x18009e656  mov     rcx, [r14+3F8h]; void *
0x18009e65d  test    rcx, rcx
0x18009e660  jz      short loc_18009E66E
0x18009e662  mov     r8d, edi; Size
0x18009e665  xor     edx, edx; Val
0x18009e667  call    memset_0
0x18009e66c  jmp     short loc_18009E67C
0x18009e66e  mov     rax, [rsp+58h+arg_20]
0x18009e676  mov     dword ptr [rax], 8007000Eh
0x18009e67c  mov     rax, r14
0x18009e67f  add     rsp, 28h
0x18009e683  pop     r15
0x18009e685  pop     r14
0x18009e687  pop     rdi
0x18009e688  pop     rsi
0x18009e689  pop     rbp
0x18009e68a  pop     rbx
0x18009e68b  retn
```
