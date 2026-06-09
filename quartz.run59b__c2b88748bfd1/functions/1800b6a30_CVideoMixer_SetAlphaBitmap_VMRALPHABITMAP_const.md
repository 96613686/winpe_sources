# CVideoMixer::SetAlphaBitmap(_VMRALPHABITMAP const *)

- ea: `0x1800b6a30`
- end: `0x1800b6f76`
- name: `?SetAlphaBitmap@CVideoMixer@@UEAAJPEBU_VMRALPHABITMAP@@@Z`
- size: `1350`
- prototype: `__int64 __fastcall(CVideoMixer *__hidden this, const struct _VMRALPHABITMAP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002d864`
- `0x1800388a0`
- `0x180039250`
- `0x1800b6a30`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800b6aa9`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6b07`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6b23`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6b50`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6f24`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6f37`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6aa9`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6b07`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6b23`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6b50`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6f24`
- `KERNEL32!LeaveCriticalSection` at `0x1800b6f37`
- `KERNEL32!EnterCriticalSection` at `0x1800b6a71`
- `KERNEL32!EnterCriticalSection` at `0x1800b6a71`
- `GDI32!DeleteObject` at `0x1800b6af1`
- `GDI32!DeleteObject` at `0x1800b6b94`
- `GDI32!DeleteObject` at `0x1800b6af1`
- `GDI32!DeleteObject` at `0x1800b6b94`
- `GDI32!DeleteDC` at `0x1800b6eb9`
- `GDI32!DeleteDC` at `0x18015c7bc`
- `GDI32!DeleteDC` at `0x1800b6eb9`
- `GDI32!DeleteDC` at `0x18015c7bc`
- `GDI32!CreateCompatibleDC` at `0x1800b6d45`
- `GDI32!CreateCompatibleDC` at `0x1800b6d45`
- `GDI32!SelectObject` at `0x1800b6e0c`
- `GDI32!SelectObject` at `0x1800b6e7c`
- `GDI32!SelectObject` at `0x1800b6e0c`
- `GDI32!SelectObject` at `0x1800b6e7c`
- `GDI32!BitBlt` at `0x1800b6e56`
- `GDI32!BitBlt` at `0x1800b6e56`
- `GDI32!CreateDIBSection` at `0x1800b6de4`
- `GDI32!CreateDIBSection` at `0x1800b6de4`
- `USER32!IsRectEmpty` at `0x1800b6cc4`
- `USER32!IsRectEmpty` at `0x1800b6cc4`

## pseudocode

```c
__int64 __fastcall CVideoMixer::SetAlphaBitmap(CVideoMixer *this, const struct _VMRALPHABITMAP *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  int v5; // eax
  LONG v6; // r12d
  DWORD dwFlags; // eax
  void *v9; // rcx
  float fAlpha; // xmm1_4
  void *v11; // rcx
  int v12; // ebx
  HDC CompatibleDC; // r15
  LONG v14; // r13d
  const RECT *v15; // r12
  _DWORD *v16; // r13
  HBITMAP v17; // rax
  HGDIOBJ v18; // r13
  COLORREF clrSrcKey; // eax
  int x1; // [rsp+30h] [rbp-168h]
  LONG cy; // [rsp+54h] [rbp-144h]
  int v22; // [rsp+58h] [rbp-140h]
  HDC hdcSrc; // [rsp+60h] [rbp-138h] BYREF
  HBITMAP v24; // [rsp+68h] [rbp-130h]
  HDC v25; // [rsp+70h] [rbp-128h]
  LONG v26; // [rsp+78h] [rbp-120h]
  LONG v27; // [rsp+7Ch] [rbp-11Ch]
  void *ppvBits[3]; // [rsp+80h] [rbp-118h] BYREF
  BITMAPINFO pbmi; // [rsp+98h] [rbp-100h] BYREF
  int v30; // [rsp+D0h] [rbp-C8h] BYREF
  _BYTE v31[4]; // [rsp+D4h] [rbp-C4h] BYREF
  int v32; // [rsp+D8h] [rbp-C0h]
  int v33; // [rsp+DCh] [rbp-BCh]
  int v34; // [rsp+12Ch] [rbp-6Ch]
  int v35; // [rsp+13Ch] [rbp-5Ch]

  ppvBits[1] = (void *)a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v5 = *((_DWORD *)this + 131) & 0xFF00;
  if ( v5 == 33024 || v5 == 4096 )
  {
    LeaveCriticalSection(v4);
    return 2147549183LL;
  }
  v6 = 0;
  if ( !a2 )
  {
    LeaveCriticalSection(v4);
    return 2147500035LL;
  }
  dwFlags = a2->dwFlags;
  if ( (a2->dwFlags & 0xFFFFFFF0) != 0 )
    goto LABEL_17;
  if ( (dwFlags & 1) != 0 )
  {
    if ( dwFlags == 1 )
    {
      RELEASE<IDDVideoAcceleratorContainer>((char *)this + 2152);
      v9 = (void *)*((_QWORD *)this + 273);
      if ( v9 )
      {
        DeleteObject(v9);
        *((_QWORD *)this + 273) = 0;
      }
      LeaveCriticalSection(v4);
      return 0;
    }
    goto LABEL_17;
  }
  if ( !*((_QWORD *)this + 10) )
  {
    LeaveCriticalSection(v4);
    return 2147500037LL;
  }
  if ( (dwFlags & 2) != 0 )
  {
    if ( (dwFlags & 4) != 0 || !a2->hdc || a2->pDDS )
      goto LABEL_17;
  }
  else if ( a2->hdc || !a2->pDDS )
  {
    goto LABEL_17;
  }
  fAlpha = a2->fAlpha;
  if ( fAlpha < 0.0 || fAlpha > 1.0 )
  {
LABEL_17:
    LeaveCriticalSection(v4);
    return 2147942487LL;
  }
  v11 = (void *)*((_QWORD *)this + 273);
  if ( v11 )
  {
    DeleteObject(v11);
    *((_QWORD *)this + 273) = 0;
  }
  v12 = 0;
  hdcSrc = 0;
  CompatibleDC = 0;
  v25 = 0;
  v24 = 0;
  v14 = 0;
  cy = 0;
  v30 = 136;
  memset_0(v31, 0, 0x84u);
  *((_DWORD *)this + 550) = 0;
  if ( (a2->dwFlags & 4) != 0 )
  {
    v12 = ((__int64 (__fastcall *)(LPDIRECTDRAWSURFACE7, int *))a2->pDDS->lpVtbl->GetSurfaceDesc)(a2->pDDS, &v30);
    if ( v12 < 0 )
      goto LABEL_47;
    if ( v34 != 32 )
      goto LABEL_27;
    if ( v35 == -16777216 )
    {
      if ( (a2->dwFlags & 8) != 0 )
      {
LABEL_27:
        v12 = -2147024809;
        goto LABEL_47;
      }
      *((_DWORD *)this + 550) = 1;
    }
    else
    {
      *((_DWORD *)this + 550) = 2;
    }
    *((_DWORD *)this + 543) = 0;
    v15 = (const RECT *)((char *)this + 2168);
    *((_DWORD *)this + 542) = 0;
    v16 = (_DWORD *)((char *)this + 2176);
    *((_DWORD *)this + 544) = v33;
    *((_DWORD *)this + 545) = v32;
  }
  else
  {
    *((_DWORD *)this + 550) = 4;
    v15 = (const RECT *)((char *)this + 2168);
    *(RECT *)((char *)this + 2168) = a2->rSrc;
    v16 = (_DWORD *)((char *)this + 2176);
  }
  if ( !IsRectEmpty(v15) )
  {
    v14 = *v16 - v15->left;
    v22 = v14;
    v26 = v14;
    cy = *((_DWORD *)this + 545) - *((_DWORD *)this + 543);
    v27 = cy;
    if ( (a2->dwFlags & 2) != 0 )
    {
      hdcSrc = a2->hdc;
    }
    else
    {
      v12 = ((__int64 (__fastcall *)(LPDIRECTDRAWSURFACE7, HDC *))a2->pDDS->lpVtbl->GetDC)(a2->pDDS, &hdcSrc);
      if ( v12 < 0 )
        goto LABEL_46;
    }
    CompatibleDC = CreateCompatibleDC(0);
    v25 = CompatibleDC;
    if ( CompatibleDC )
    {
      ppvBits[0] = 0;
      memset(&pbmi.bmiHeader.biCompression, 0, 28);
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v14;
      pbmi.bmiHeader.biHeight = cy;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      v17 = CreateDIBSection(CompatibleDC, &pbmi, 0, ppvBits, 0, 0);
      v24 = v17;
      ppvBits[2] = v17;
      if ( v17 )
      {
        v18 = SelectObject(CompatibleDC, v17);
        x1 = v15->left;
        v6 = cy;
        if ( BitBlt(CompatibleDC, 0, 0, v22, cy, hdcSrc, x1, *((_DWORD *)this + 543), 0xCC0020u) )
          SelectObject(CompatibleDC, v18);
        else
          v12 = -2147467259;
        v14 = v22;
        goto LABEL_47;
      }
    }
    v12 = -2147024882;
    goto LABEL_46;
  }
  v12 = -2147024809;
  v14 = 0;
LABEL_46:
  v6 = cy;
LABEL_47:
  if ( hdcSrc && (a2->dwFlags & 2) == 0 )
    ((void (__fastcall *)(LPDIRECTDRAWSURFACE7))a2->pDDS->lpVtbl->ReleaseDC)(a2->pDDS);
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  if ( !v12 )
  {
    *((_QWORD *)this + 273) = v24;
    RELEASE<IDDVideoAcceleratorContainer>((char *)this + 2152);
    if ( (a2->dwFlags & 8) != 0 )
      clrSrcKey = a2->clrSrcKey;
    else
      clrSrcKey = -1;
    *((_DWORD *)this + 533) = clrSrcKey;
    *((_DWORD *)this + 534) = -1;
    *((_OWORD *)this + 132) = a2->rDest;
    *((_DWORD *)this + 532) = LODWORD(a2->fAlpha);
    *((_DWORD *)this + 548) = v14;
    *((_DWORD *)this + 549) = v6;
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800b6a30  mov     [rsp+arg_10], rbx
0x1800b6a35  mov     [rsp+arg_18], rsi
0x1800b6a3a  push    rdi
0x1800b6a3b  push    r12
0x1800b6a3d  push    r13
0x1800b6a3f  push    r14
0x1800b6a41  push    r15
0x1800b6a43  sub     rsp, 170h
0x1800b6a4a  mov     rax, cs:__security_cookie
0x1800b6a51  xor     rax, rsp
0x1800b6a54  mov     [rsp+198h+var_38], rax
0x1800b6a5c  mov     rsi, rdx
0x1800b6a5f  mov     rdi, rcx
0x1800b6a62  mov     [rsp+198h+var_110], rdx
0x1800b6a6a  lea     r14, [rcx+8]
0x1800b6a6e  mov     rcx, r14; lpCriticalSection
0x1800b6a71  call    cs:__imp_EnterCriticalSection
0x1800b6a78  nop     dword ptr [rax+rax+00h]
0x1800b6a7d  mov     eax, [rdi+20Ch]
0x1800b6a83  and     eax, 0FF00h
0x1800b6a88  cmp     eax, 8100h
0x1800b6a8d  jz      loc_1800B6F34
0x1800b6a93  cmp     eax, 1000h
0x1800b6a98  jz      loc_1800B6F34
0x1800b6a9e  xor     r12d, r12d
0x1800b6aa1  test    rsi, rsi
0x1800b6aa4  jnz     short loc_1800B6ABF
0x1800b6aa6  mov     rcx, r14; lpCriticalSection
0x1800b6aa9  call    cs:__imp_LeaveCriticalSection
0x1800b6ab0  nop     dword ptr [rax+rax+00h]
0x1800b6ab5  mov     eax, 80004003h
0x1800b6aba  jmp     loc_1800B6F48
0x1800b6abf  mov     eax, [rsi]
0x1800b6ac1  test    eax, 0FFFFFFF0h
0x1800b6ac6  jnz     loc_1800B6B4D
0x1800b6acc  mov     ecx, 1
0x1800b6ad1  test    cl, al
0x1800b6ad3  jz      short loc_1800B6B1A
0x1800b6ad5  cmp     eax, ecx
0x1800b6ad7  jnz     short loc_1800B6B4D
0x1800b6ad9  lea     rcx, [rdi+868h]
0x1800b6ae0  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b6ae5  mov     rcx, [rdi+888h]; ho
0x1800b6aec  test    rcx, rcx
0x1800b6aef  jz      short loc_1800B6B04
0x1800b6af1  call    cs:__imp_DeleteObject
0x1800b6af8  nop     dword ptr [rax+rax+00h]
0x1800b6afd  mov     [rdi+888h], r12
0x1800b6b04  mov     rcx, r14; lpCriticalSection
0x1800b6b07  call    cs:__imp_LeaveCriticalSection
0x1800b6b0e  nop     dword ptr [rax+rax+00h]
0x1800b6b13  xor     eax, eax
0x1800b6b15  jmp     loc_1800B6F48
0x1800b6b1a  cmp     [rdi+50h], r12
0x1800b6b1e  jnz     short loc_1800B6B39
0x1800b6b20  mov     rcx, r14; lpCriticalSection
0x1800b6b23  call    cs:__imp_LeaveCriticalSection
0x1800b6b2a  nop     dword ptr [rax+rax+00h]
0x1800b6b2f  mov     eax, 80004005h
0x1800b6b34  jmp     loc_1800B6F48
0x1800b6b39  test    al, 2
0x1800b6b3b  jz      short loc_1800B6B66
0x1800b6b3d  test    al, 4
0x1800b6b3f  jnz     short loc_1800B6B4D
0x1800b6b41  cmp     [rsi+8], r12
0x1800b6b45  jz      short loc_1800B6B4D
0x1800b6b47  cmp     [rsi+10h], r12
0x1800b6b4b  jz      short loc_1800B6B72
0x1800b6b4d  mov     rcx, r14; lpCriticalSection
0x1800b6b50  call    cs:__imp_LeaveCriticalSection
0x1800b6b57  nop     dword ptr [rax+rax+00h]
0x1800b6b5c  mov     eax, 80070057h
0x1800b6b61  jmp     loc_1800B6F48
0x1800b6b66  cmp     [rsi+8], r12
0x1800b6b6a  jnz     short loc_1800B6B4D
0x1800b6b6c  cmp     [rsi+10h], r12
0x1800b6b70  jz      short loc_1800B6B4D
0x1800b6b72  movss   xmm1, dword ptr [rsi+38h]
0x1800b6b77  xorps   xmm0, xmm0
0x1800b6b7a  comiss  xmm0, xmm1
0x1800b6b7d  ja      short loc_1800B6B4D
0x1800b6b7f  comiss  xmm1, cs:__real@3f800000
0x1800b6b86  ja      short loc_1800B6B4D
0x1800b6b88  mov     rcx, [rdi+888h]; ho
0x1800b6b8f  test    rcx, rcx
0x1800b6b92  jz      short loc_1800B6BA7
0x1800b6b94  call    cs:__imp_DeleteObject
0x1800b6b9b  nop     dword ptr [rax+rax+00h]
0x1800b6ba0  mov     [rdi+888h], r12
0x1800b6ba7  mov     ebx, r12d
0x1800b6baa  mov     [rsp+198h+hdcSrc], r12
0x1800b6baf  mov     r15, r12
0x1800b6bb2  mov     [rsp+198h+var_128], r12
0x1800b6bb7  mov     [rsp+198h+var_130], r12
0x1800b6bbc  mov     r13d, r12d
0x1800b6bbf  mov     [rsp+198h+var_140], r12d
0x1800b6bc4  mov     [rsp+198h+cy], r12d
0x1800b6bc9  mov     [rsp+198h+var_C8], 88h
0x1800b6bd4  xor     edx, edx; Val
0x1800b6bd6  mov     r8d, 84h; Size
0x1800b6bdc  lea     rcx, [rsp+198h+var_C4]; void *
0x1800b6be4  call    memset_0
0x1800b6be9  mov     dword ptr [rdi+898h], 0
0x1800b6bf3  test    byte ptr [rsi], 4
0x1800b6bf6  jz      loc_1800B6C9F
0x1800b6bfc  mov     rcx, [rsi+10h]
0x1800b6c00  mov     rax, [rcx]
0x1800b6c03  lea     rdx, [rsp+198h+var_C8]
0x1800b6c0b  mov     rax, [rax+0B0h]
0x1800b6c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c17  mov     ebx, eax
0x1800b6c19  mov     [rsp+198h+var_148], eax
0x1800b6c1d  test    eax, eax
0x1800b6c1f  js      loc_1800B6E8F
0x1800b6c25  cmp     [rsp+198h+var_6C], 20h ; ' '
0x1800b6c2d  jz      short loc_1800B6C3D
0x1800b6c2f  mov     ebx, 80070057h
0x1800b6c34  mov     [rsp+198h+var_148], ebx
0x1800b6c38  jmp     loc_1800B6E8F
0x1800b6c3d  cmp     [rsp+198h+var_5C], 0FF000000h
0x1800b6c48  jnz     short loc_1800B6C5B
0x1800b6c4a  test    byte ptr [rsi], 8
0x1800b6c4d  jnz     short loc_1800B6C2F
0x1800b6c4f  mov     dword ptr [rdi+898h], 1
0x1800b6c59  jmp     short loc_1800B6C65
0x1800b6c5b  mov     dword ptr [rdi+898h], 2
0x1800b6c65  mov     dword ptr [rdi+87Ch], 0
0x1800b6c6f  lea     r12, [rdi+878h]
0x1800b6c76  mov     dword ptr [r12], 0
0x1800b6c7e  lea     r13, [rdi+880h]
0x1800b6c85  mov     eax, [rsp+198h+var_BC]
0x1800b6c8c  mov     [r13+0], eax
0x1800b6c90  mov     eax, [rsp+198h+var_C0]
0x1800b6c97  mov     [rdi+884h], eax
0x1800b6c9d  jmp     short loc_1800B6CC1
0x1800b6c9f  mov     dword ptr [rdi+898h], 4
0x1800b6ca9  lea     r12, [rdi+878h]
0x1800b6cb0  movups  xmm0, xmmword ptr [rsi+18h]
0x1800b6cb4  movdqu  xmmword ptr [r12], xmm0
0x1800b6cba  lea     r13, [rdi+880h]
0x1800b6cc1  mov     rcx, r12; lprc
0x1800b6cc4  call    cs:__imp_IsRectEmpty
0x1800b6ccb  nop     dword ptr [rax+rax+00h]
0x1800b6cd0  test    eax, eax
0x1800b6cd2  jz      short loc_1800B6CE7
0x1800b6cd4  mov     ebx, 80070057h
0x1800b6cd9  mov     [rsp+198h+var_148], ebx
0x1800b6cdd  mov     r13d, [rsp+198h+var_140]
0x1800b6ce2  jmp     loc_1800B6E8A
0x1800b6ce7  mov     r13d, [r13+0]
0x1800b6ceb  sub     r13d, [r12]
0x1800b6cef  mov     [rsp+198h+var_140], r13d
0x1800b6cf4  mov     [rsp+198h+var_120], r13d
0x1800b6cf9  mov     eax, [rdi+884h]
0x1800b6cff  sub     eax, [rdi+87Ch]
0x1800b6d05  mov     [rsp+198h+cy], eax
0x1800b6d09  mov     [rsp+198h+var_11C], eax
0x1800b6d0d  test    byte ptr [rsi], 2
0x1800b6d10  jz      short loc_1800B6D1D
0x1800b6d12  mov     rax, [rsi+8]
0x1800b6d16  mov     [rsp+198h+hdcSrc], rax
0x1800b6d1b  jmp     short loc_1800B6D43
0x1800b6d1d  mov     rcx, [rsi+10h]
0x1800b6d21  mov     rax, [rcx]
0x1800b6d24  lea     rdx, [rsp+198h+hdcSrc]
0x1800b6d29  mov     rax, [rax+88h]
0x1800b6d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6d35  mov     ebx, eax
0x1800b6d37  mov     [rsp+198h+var_148], eax
0x1800b6d3b  test    eax, eax
0x1800b6d3d  js      loc_1800B6E8A
0x1800b6d43  xor     ecx, ecx; hdc
0x1800b6d45  call    cs:__imp_CreateCompatibleDC
0x1800b6d4c  nop     dword ptr [rax+rax+00h]
0x1800b6d51  mov     r15, rax
0x1800b6d54  mov     [rsp+198h+var_128], rax
0x1800b6d59  test    rax, rax
0x1800b6d5c  jnz     short loc_1800B6D6C
0x1800b6d5e  mov     ebx, 8007000Eh
0x1800b6d63  mov     [rsp+198h+var_148], ebx
0x1800b6d67  jmp     loc_1800B6E8A
0x1800b6d6c  mov     [rsp+198h+ppvBits], 0
0x1800b6d78  xorps   xmm0, xmm0
0x1800b6d7b  movups  xmmword ptr [rsp+198h+pbmi.bmiHeader.biSize], xmm0
0x1800b6d83  movups  xmmword ptr [rsp+198h+pbmi.bmiHeader.biCompression], xmm0
0x1800b6d8b  movups  xmmword ptr [rsp+198h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x1800b6d93  mov     [rsp+198h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800b6d9e  mov     [rsp+198h+pbmi.bmiHeader.biWidth], r13d
0x1800b6da6  mov     eax, [rsp+198h+cy]
0x1800b6daa  mov     [rsp+198h+pbmi.bmiHeader.biHeight], eax
0x1800b6db1  mov     qword ptr [rsp+198h+pbmi.bmiHeader.biPlanes], 200001h
0x1800b6dbd  mov     [rsp+198h+offset], 0; offset
0x1800b6dc5  mov     [rsp+198h+hSection], 0; hSection
0x1800b6dce  lea     r9, [rsp+198h+ppvBits]; ppvBits
0x1800b6dd6  xor     r8d, r8d; usage
0x1800b6dd9  lea     rdx, [rsp+198h+pbmi]; pbmi
0x1800b6de1  mov     rcx, r15; hdc
0x1800b6de4  call    cs:__imp_CreateDIBSection
0x1800b6deb  nop     dword ptr [rax+rax+00h]
0x1800b6df0  mov     [rsp+198h+var_130], rax
0x1800b6df5  mov     [rsp+198h+var_108], rax
0x1800b6dfd  test    rax, rax
0x1800b6e00  jz      loc_1800B6D5E
0x1800b6e06  mov     rdx, rax; h
0x1800b6e09  mov     rcx, r15; hdc
0x1800b6e0c  call    cs:__imp_SelectObject
0x1800b6e13  nop     dword ptr [rax+rax+00h]
0x1800b6e18  mov     r13, rax
0x1800b6e1b  mov     [rsp+198h+rop], 0CC0020h; rop
0x1800b6e23  mov     ecx, [rdi+87Ch]
0x1800b6e29  mov     [rsp+198h+y1], ecx; y1
0x1800b6e2d  mov     ecx, [r12]
0x1800b6e31  mov     [rsp+198h+x1], ecx; x1
0x1800b6e35  mov     rcx, [rsp+198h+hdcSrc]
0x1800b6e3a  mov     qword ptr [rsp+198h+offset], rcx; hdcSrc
0x1800b6e3f  mov     r12d, [rsp+198h+cy]
0x1800b6e44  mov     dword ptr [rsp+198h+hSection], r12d; cy
0x1800b6e49  mov     r9d, [rsp+198h+var_140]; cx
0x1800b6e4e  xor     r8d, r8d; y
0x1800b6e51  xor     edx, edx; x
0x1800b6e53  mov     rcx, r15; hdc
0x1800b6e56  call    cs:__imp_BitBlt
0x1800b6e5d  nop     dword ptr [rax+rax+00h]
0x1800b6e62  test    eax, eax
0x1800b6e64  jnz     short loc_1800B6E76
0x1800b6e66  mov     ebx, 80004005h
0x1800b6e6b  mov     [rsp+198h+var_148], ebx
0x1800b6e6f  mov     r13d, [rsp+198h+var_140]
0x1800b6e74  jmp     short loc_1800B6E8F
0x1800b6e76  mov     rdx, r13; h
0x1800b6e79  mov     rcx, r15; hdc
0x1800b6e7c  call    cs:__imp_SelectObject
0x1800b6e83  nop     dword ptr [rax+rax+00h]
0x1800b6e88  jmp     short loc_1800B6E6F
0x1800b6e8a  mov     r12d, [rsp+198h+cy]
0x1800b6e8f  mov     rdx, [rsp+198h+hdcSrc]
0x1800b6e94  test    rdx, rdx
0x1800b6e97  jz      short loc_1800B6EB1
0x1800b6e99  test    byte ptr [rsi], 2
0x1800b6e9c  jnz     short loc_1800B6EB1
0x1800b6e9e  mov     rcx, [rsi+10h]
0x1800b6ea2  mov     rax, [rcx]
0x1800b6ea5  mov     rax, [rax+0D0h]
0x1800b6eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6eb1  test    r15, r15
0x1800b6eb4  jz      short loc_1800B6EC5
0x1800b6eb6  mov     rcx, r15; hdc
0x1800b6eb9  call    cs:__imp_DeleteDC
0x1800b6ec0  nop     dword ptr [rax+rax+00h]
0x1800b6ec5  test    ebx, ebx
0x1800b6ec7  jnz     short loc_1800B6F21
0x1800b6ec9  mov     rax, [rsp+198h+var_130]
0x1800b6ece  mov     [rdi+888h], rax
0x1800b6ed5  lea     rcx, [rdi+868h]
0x1800b6edc  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b6ee1  test    byte ptr [rsi], 8
0x1800b6ee4  jz      short loc_1800B6EEB
0x1800b6ee6  mov     eax, [rsi+3Ch]
0x1800b6ee9  jmp     short loc_1800B6EEE
0x1800b6eeb  or      eax, 0FFFFFFFFh
0x1800b6eee  mov     [rdi+854h], eax
0x1800b6ef4  mov     dword ptr [rdi+858h], 0FFFFFFFFh
0x1800b6efe  movups  xmm0, xmmword ptr [rsi+28h]
0x1800b6f02  movdqu  xmmword ptr [rdi+840h], xmm0
0x1800b6f0a  mov     eax, [rsi+38h]
0x1800b6f0d  mov     [rdi+850h], eax
0x1800b6f13  mov     [rdi+890h], r13d
0x1800b6f1a  mov     [rdi+894h], r12d
0x1800b6f21  mov     rcx, r14; lpCriticalSection
0x1800b6f24  call    cs:__imp_LeaveCriticalSection
0x1800b6f2b  nop     dword ptr [rax+rax+00h]
0x1800b6f30  mov     eax, ebx
0x1800b6f32  jmp     short loc_1800B6F48
0x1800b6f34  mov     rcx, r14; lpCriticalSection
0x1800b6f37  call    cs:__imp_LeaveCriticalSection
0x1800b6f3e  nop     dword ptr [rax+rax+00h]
0x1800b6f43  mov     eax, 8000FFFFh
0x1800b6f48  mov     rcx, [rsp+198h+var_38]
0x1800b6f50  xor     rcx, rsp; StackCookie
0x1800b6f53  call    __security_check_cookie
0x1800b6f58  lea     r11, [rsp+198h+var_28]
0x1800b6f60  mov     rbx, [r11+40h]
0x1800b6f64  mov     rsi, [r11+48h]
0x1800b6f68  mov     rsp, r11
0x1800b6f6b  pop     r15
0x1800b6f6d  pop     r14
0x1800b6f6f  pop     r13
0x1800b6f71  pop     r12
0x1800b6f73  pop     rdi
0x1800b6f74  retn
0x18015c77e  push    rbp
0x18015c780  sub     rsp, 50h
0x18015c784  mov     rbp, rdx
0x18015c787  mov     rdx, [rbp+60h]
0x18015c78b  test    rdx, rdx
0x18015c78e  jz      short loc_18015C7B3
0x18015c790  mov     rcx, [rbp+88h]
0x18015c797  test    byte ptr [rcx], 2
0x18015c79a  jnz     short loc_18015C7B3
0x18015c79c  mov     rax, [rcx+10h]
  ... truncated ...
```
