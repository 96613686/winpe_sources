# PrintBand(HDC__ *,HENHMETAFILE__ *,_POINTL *,tagRECT *,tagSIZE *,tagRECT *)

- ea: `0x18006e3c8`
- end: `0x18006e75a`
- name: `?PrintBand@@YAXPEAUHDC__@@PEAUHENHMETAFILE__@@PEAU_POINTL@@PEAUtagRECT@@PEAUtagSIZE@@3@Z`
- size: `914`
- prototype: `void __usercall(HDC hdc@<rcx>, HENHMETAFILE@<rdx>, struct _POINTL *@<r8>, struct tagRECT *@<r9>, struct tagSIZE *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180056ca4`
- `0x180099e04`

## callees

- `0x180018c30`
- `0x18006e3c8`
- `0x18006e760`
- `0x18007f800`
- `0x18008bd90`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x18006e649`
- `GDI32!CreateRectRgn` at `0x18006e649`
- `GDI32!GetClipBox` at `0x18006e66e`
- `GDI32!GetClipBox` at `0x18006e66e`
- `GDI32!RestoreDC` at `0x18006e6ed`
- `GDI32!RestoreDC` at `0x18006e6ed`
- `GDI32!SaveDC` at `0x18006e682`
- `GDI32!SaveDC` at `0x18006e682`
- `GDI32!SelectClipRgn` at `0x18006e6c0`
- `GDI32!SelectClipRgn` at `0x18006e6fd`
- `GDI32!SelectClipRgn` at `0x18006e6c0`
- `GDI32!SelectClipRgn` at `0x18006e6fd`
- `GDI32!ExtSelectClipRgn` at `0x18006e6ac`
- `GDI32!ExtSelectClipRgn` at `0x18006e6ac`
- `GDI32!DeleteObject` at `0x18006e70c`
- `GDI32!DeleteObject` at `0x18006e70c`
- `USER32!IntersectRect` at `0x18006e5d9`
- `USER32!IntersectRect` at `0x18006e5d9`
- `win32u!NtGdiGetPerBandInfo` at `0x18006e475`
- `win32u!NtGdiGetPerBandInfo` at `0x18006e475`

## pseudocode

```c
void __fastcall PrintBand(
        HDC hdc,
        HENHMETAFILE a2,
        struct _POINTL *a3,
        struct tagRECT *a4,
        struct tagSIZE *a5,
        struct tagRECT *lprcSrc1)
{
  struct tagSIZE *v6; // r15
  struct _POINTL *v8; // r14
  int v10; // r8d
  int v11; // edx
  int v12; // ebx
  int v13; // edi
  int cy; // eax
  int PerBandInfo; // eax
  int v16; // edx
  int cx; // ecx
  float v18; // xmm7_4
  float v19; // xmm6_4
  __m128i v20; // xmm1
  float y; // xmm0_4
  LONG x; // edi
  int v23; // ebx
  int v24; // edx
  int v25; // ecx
  int v26; // r9d
  int v27; // r8d
  int v28; // r14d
  int v29; // r15d
  LONG right; // r8d
  LONG bottom; // r9d
  int v32; // r15d
  HRGN RectRgn; // r14
  int y2[4]; // [rsp+40h] [rbp-71h] BYREF
  int v37; // [rsp+50h] [rbp-61h]
  RECT rect; // [rsp+58h] [rbp-59h] BYREF
  RECT rcSrc2; // [rsp+68h] [rbp-49h] BYREF
  struct tagRECT rcDst; // [rsp+78h] [rbp-39h] BYREF

  v6 = a5;
  *(_OWORD *)y2 = 0;
  v37 = 0;
  v8 = a3;
  do
  {
    v10 = -v8->y;
    v11 = -v8->x;
    rect = *a4;
    SetViewportOrgEx(hdc, v11, v10, 0);
    v12 = a4->right - a4->left;
    v13 = a4->bottom - a4->top;
    y2[1] = v6->cx;
    cy = v6->cy;
    y2[3] = v12;
    v37 = v13;
    y2[2] = cy;
    y2[0] = 0;
    PerBandInfo = NtGdiGetPerBandInfo(hdc, y2);
    if ( PerBandInfo == -1 )
      break;
    if ( PerBandInfo )
    {
      if ( v12 != y2[3] || v13 != v37 )
      {
        v18 = (float)v12 / (float)y2[3];
        v19 = (float)v13 / (float)v37;
        rect.left = (int)(float)((float)rect.left / v18);
        rect.top = (int)(float)((float)rect.top / v19);
        v20 = _mm_cvtsi32_si128(v8->x);
        rect.right = (int)(float)((float)rect.right / v18);
        y = (float)v8->y;
        rect.bottom = (int)(float)((float)rect.bottom / v19);
        x = (int)(float)(_mm_cvtepi32_ps(v20).m128_f32[0] / v18);
        v23 = (int)(float)(y / v19);
        SetViewportOrgEx(hdc, -x, -v23, 0);
        v24 = 0;
        v25 = 0;
        v26 = (int)(float)((float)y2[2] / v19);
        v27 = (int)(float)((float)y2[1] / v18);
LABEL_23:
        v32 = 0;
        RectRgn = CreateRectRgn(v25, v24, v27, v26);
        if ( RectRgn )
        {
          rcDst = 0;
          if ( (unsigned int)GetClipBox(hdc, &rcDst) <= 1 )
          {
            SelectClipRgn(hdc, RectRgn);
          }
          else
          {
            SaveDC(hdc);
            OffsetClipRgn(hdc, -x, -v23);
            ExtSelectClipRgn(hdc, RectRgn, 1);
            v32 = 1;
          }
        }
        PlayEnhMetaFile(hdc, a2, &rect);
        if ( RectRgn )
        {
          if ( v32 )
            RestoreDC(hdc, -1);
          else
            SelectClipRgn(hdc, 0);
          DeleteObject(RectRgn);
        }
        goto LABEL_32;
      }
      v16 = y2[2];
      cx = y2[1];
    }
    else
    {
      cx = v6->cx;
      v16 = v6->cy;
      y2[1] = v6->cx;
      y2[2] = v16;
      y2[0] = 0;
      y2[3] = v12;
      v37 = v13;
    }
    v28 = 0;
    v29 = 0;
    x = a3->x;
    v23 = a3->y;
    if ( !lprcSrc1 )
    {
      right = a4->right;
      bottom = a4->bottom;
LABEL_16:
      if ( x + cx <= right )
        v27 = cx;
      else
        v27 = right - x;
      if ( v23 + v16 <= bottom )
        v26 = v16;
      else
        v26 = bottom - v23;
      v24 = v29;
      v25 = v28;
      goto LABEL_23;
    }
    rcSrc2.left = a3->x;
    rcSrc2.right = x + cx;
    rcSrc2.top = v23;
    rcSrc2.bottom = v23 + v16;
    rcDst = 0;
    if ( IntersectRect(&rcDst, lprcSrc1, &rcSrc2) )
    {
      right = lprcSrc1->right;
      bottom = lprcSrc1->bottom;
      if ( lprcSrc1->left > x )
        v28 = lprcSrc1->left - x;
      v16 = y2[2];
      cx = y2[1];
      if ( lprcSrc1->top > v23 )
        v29 = lprcSrc1->top - v23;
      goto LABEL_16;
    }
LABEL_32:
    v8 = a3;
    v6 = a5;
  }
  while ( y2[0] );
}

```

## disassembly

```asm
0x18006e3c8  mov     rax, rsp
0x18006e3cb  push    rbp
0x18006e3cc  push    rbx
0x18006e3cd  push    rsi
0x18006e3ce  push    rdi
0x18006e3cf  push    r12
0x18006e3d1  push    r13
0x18006e3d3  push    r14
0x18006e3d5  push    r15
0x18006e3d7  lea     rbp, [rax-4Fh]
0x18006e3db  sub     rsp, 0B8h
0x18006e3e2  movaps  xmmword ptr [rax-58h], xmm6
0x18006e3e6  movaps  xmmword ptr [rax-68h], xmm7
0x18006e3ea  mov     rax, cs:__security_cookie
0x18006e3f1  xor     rax, rsp
0x18006e3f4  mov     [rbp+47h+var_70], rax
0x18006e3f8  mov     r15, [rbp+47h+arg_20]
0x18006e3fc  xorps   xmm0, xmm0
0x18006e3ff  mov     r12, [rbp+47h+lprcSrc1]
0x18006e403  xor     eax, eax
0x18006e405  mov     [rbp+47h+var_C0], r15
0x18006e409  mov     r13, r9
0x18006e40c  movups  xmmword ptr [rbp+47h+y2], xmm0
0x18006e410  mov     [rbp+47h+var_A8], eax
0x18006e413  mov     r14, r8
0x18006e416  mov     [rsp+0F0h+var_D0], r8
0x18006e41b  mov     rsi, rcx
0x18006e41e  mov     [rsp+0F0h+hmf], rdx
0x18006e423  movups  xmm0, xmmword ptr [r13+0]
0x18006e428  mov     r8d, [r14+4]
0x18006e42c  xor     r9d, r9d; lppt
0x18006e42f  mov     edx, [r14]
0x18006e432  neg     r8d; y
0x18006e435  neg     edx; x
0x18006e437  mov     rcx, rsi; hdc
0x18006e43a  movdqu  xmmword ptr [rbp+47h+rect.left], xmm0
0x18006e43f  call    SetViewportOrgEx
0x18006e444  mov     eax, [r15]
0x18006e447  lea     rdx, [rbp+47h+y2]
0x18006e44b  mov     ebx, [r13+8]
0x18006e44f  mov     rcx, rsi
0x18006e452  mov     edi, [r13+0Ch]
0x18006e456  sub     ebx, [r13+0]
0x18006e45a  sub     edi, [r13+4]
0x18006e45e  mov     [rbp+47h+y2+4], eax
0x18006e461  mov     eax, [r15+4]
0x18006e465  mov     [rbp+47h+y2+0Ch], ebx
0x18006e468  mov     [rbp+47h+var_A8], edi
0x18006e46b  mov     [rbp+47h+y2+8], eax
0x18006e46e  mov     [rbp+47h+y2], 0
0x18006e475  call    cs:__imp_NtGdiGetPerBandInfo
0x18006e47c  nop     dword ptr [rax+rax+00h]
0x18006e481  cmp     eax, 0FFFFFFFFh
0x18006e484  jz      loc_18006E72B
0x18006e48a  test    eax, eax
0x18006e48c  jz      loc_18006E586
0x18006e492  cmp     ebx, [rbp+47h+y2+0Ch]
0x18006e495  jnz     short loc_18006E4A7
0x18006e497  cmp     edi, [rbp+47h+var_A8]
0x18006e49a  jnz     short loc_18006E4A7
0x18006e49c  mov     edx, [rbp+47h+y2+8]
0x18006e49f  mov     ecx, [rbp+47h+y2+4]
0x18006e4a2  jmp     loc_18006E5A0
0x18006e4a7  movd    xmm1, [rbp+47h+rect.left]
0x18006e4ac  xorps   xmm0, xmm0
0x18006e4af  cvtdq2ps xmm1, xmm1
0x18006e4b2  mov     eax, ebx
0x18006e4b4  xor     r9d, r9d; lppt
0x18006e4b7  mov     rcx, rsi; hdc
0x18006e4ba  xorps   xmm7, xmm7
0x18006e4bd  xorps   xmm6, xmm6
0x18006e4c0  cvtsi2ss xmm7, rax
0x18006e4c5  mov     eax, [rbp+47h+y2+0Ch]
0x18006e4c8  cvtsi2ss xmm0, rax
0x18006e4cd  mov     eax, edi
0x18006e4cf  cvtsi2ss xmm6, rax
0x18006e4d4  mov     eax, [rbp+47h+var_A8]
0x18006e4d7  divss   xmm7, xmm0
0x18006e4db  xorps   xmm0, xmm0
0x18006e4de  cvtsi2ss xmm0, rax
0x18006e4e3  divss   xmm1, xmm7
0x18006e4e7  divss   xmm6, xmm0
0x18006e4eb  movd    xmm0, [rbp+47h+rect.top]
0x18006e4f0  cvttss2si eax, xmm1
0x18006e4f4  movd    xmm1, [rbp+47h+rect.right]
0x18006e4f9  cvtdq2ps xmm0, xmm0
0x18006e4fc  mov     [rbp+47h+rect.left], eax
0x18006e4ff  cvtdq2ps xmm1, xmm1
0x18006e502  divss   xmm0, xmm6
0x18006e506  divss   xmm1, xmm7
0x18006e50a  cvttss2si eax, xmm0
0x18006e50e  movd    xmm0, [rbp+47h+rect.bottom]
0x18006e513  cvtdq2ps xmm0, xmm0
0x18006e516  mov     [rbp+47h+rect.top], eax
0x18006e519  cvttss2si eax, xmm1
0x18006e51d  movd    xmm1, dword ptr [r14]
0x18006e522  divss   xmm0, xmm6
0x18006e526  mov     [rbp+47h+rect.right], eax
0x18006e529  cvtdq2ps xmm1, xmm1
0x18006e52c  cvttss2si eax, xmm0
0x18006e530  movd    xmm0, dword ptr [r14+4]
0x18006e536  cvtdq2ps xmm0, xmm0
0x18006e539  mov     [rbp+47h+rect.bottom], eax
0x18006e53c  divss   xmm1, xmm7
0x18006e540  divss   xmm0, xmm6
0x18006e544  cvttss2si edi, xmm1
0x18006e548  cvttss2si ebx, xmm0
0x18006e54c  mov     edx, edi
0x18006e54e  neg     edx; x
0x18006e550  mov     r8d, ebx
0x18006e553  neg     r8d; y
0x18006e556  call    SetViewportOrgEx
0x18006e55b  movd    xmm0, [rbp+47h+y2+8]
0x18006e560  xor     edx, edx
0x18006e562  movd    xmm1, [rbp+47h+y2+4]
0x18006e567  xor     ecx, ecx
0x18006e569  cvtdq2ps xmm0, xmm0
0x18006e56c  cvtdq2ps xmm1, xmm1
0x18006e56f  divss   xmm0, xmm6
0x18006e573  divss   xmm1, xmm7
0x18006e577  cvttss2si r9, xmm0
0x18006e57c  cvttss2si r8, xmm1
0x18006e581  jmp     loc_18006E649
0x18006e586  mov     ecx, [r15]
0x18006e589  mov     edx, [r15+4]
0x18006e58d  mov     [rbp+47h+y2+4], ecx
0x18006e590  mov     [rbp+47h+y2+8], edx
0x18006e593  mov     [rbp+47h+y2], 0
0x18006e59a  mov     [rbp+47h+y2+0Ch], ebx
0x18006e59d  mov     [rbp+47h+var_A8], edi
0x18006e5a0  mov     rbx, [rsp+0F0h+var_D0]
0x18006e5a5  xor     r14d, r14d
0x18006e5a8  xor     r15d, r15d
0x18006e5ab  mov     edi, [rbx]
0x18006e5ad  mov     ebx, [rbx+4]
0x18006e5b0  test    r12, r12
0x18006e5b3  jz      short loc_18006E61B
0x18006e5b5  lea     eax, [rdi+rcx]
0x18006e5b8  mov     [rbp+47h+rcSrc2.left], edi
0x18006e5bb  mov     [rbp+47h+rcSrc2.right], eax
0x18006e5be  lea     r8, [rbp+47h+rcSrc2]; lprcSrc2
0x18006e5c2  lea     eax, [rbx+rdx]
0x18006e5c5  mov     [rbp+47h+rcSrc2.top], ebx
0x18006e5c8  xorps   xmm0, xmm0
0x18006e5cb  mov     [rbp+47h+rcSrc2.bottom], eax
0x18006e5ce  mov     rdx, r12; lprcSrc1
0x18006e5d1  lea     rcx, [rbp+47h+rcDst]; lprcDst
0x18006e5d5  movups  xmmword ptr [rbp+47h+rcDst.left], xmm0
0x18006e5d9  call    cs:__imp_IntersectRect
0x18006e5e0  nop     dword ptr [rax+rax+00h]
0x18006e5e5  test    eax, eax
0x18006e5e7  jz      loc_18006E718
0x18006e5ed  mov     r8d, [r12+8]
0x18006e5f2  mov     r9d, [r12+0Ch]
0x18006e5f7  cmp     [r12], edi
0x18006e5fb  jle     short loc_18006E604
0x18006e5fd  mov     r14d, [r12]
0x18006e601  sub     r14d, edi
0x18006e604  mov     edx, [rbp+47h+y2+8]
0x18006e607  mov     ecx, [rbp+47h+y2+4]
0x18006e60a  cmp     [r12+4], ebx
0x18006e60f  jle     short loc_18006E623
0x18006e611  mov     r15d, [r12+4]
0x18006e616  sub     r15d, ebx
0x18006e619  jmp     short loc_18006E623
0x18006e61b  mov     r8d, [r13+8]
0x18006e61f  mov     r9d, [r13+0Ch]
0x18006e623  lea     eax, [rdi+rcx]
0x18006e626  cmp     eax, r8d
0x18006e629  jle     short loc_18006E630
0x18006e62b  sub     r8d, edi
0x18006e62e  jmp     short loc_18006E633
0x18006e630  mov     r8d, ecx; x2
0x18006e633  lea     eax, [rbx+rdx]
0x18006e636  cmp     eax, r9d
0x18006e639  jle     short loc_18006E640
0x18006e63b  sub     r9d, ebx
0x18006e63e  jmp     short loc_18006E643
0x18006e640  mov     r9d, edx; y2
0x18006e643  mov     edx, r15d; y1
0x18006e646  mov     ecx, r14d; x1
0x18006e649  call    cs:__imp_CreateRectRgn
0x18006e650  nop     dword ptr [rax+rax+00h]
0x18006e655  xor     r15d, r15d
0x18006e658  mov     r14, rax
0x18006e65b  test    rax, rax
0x18006e65e  jz      short loc_18006E6CC
0x18006e660  xorps   xmm0, xmm0
0x18006e663  lea     rdx, [rbp+47h+rcDst]; lprect
0x18006e667  mov     rcx, rsi; hdc
0x18006e66a  movups  xmmword ptr [rbp+47h+rcDst.left], xmm0
0x18006e66e  call    cs:__imp_GetClipBox
0x18006e675  nop     dword ptr [rax+rax+00h]
0x18006e67a  mov     rcx, rsi; hdc
0x18006e67d  cmp     eax, 1
0x18006e680  jbe     short loc_18006E6BD
0x18006e682  call    cs:__imp_SaveDC
0x18006e689  nop     dword ptr [rax+rax+00h]
0x18006e68e  neg     ebx
0x18006e690  neg     edi
0x18006e692  mov     r8d, ebx; y
0x18006e695  mov     edx, edi; x
0x18006e697  mov     rcx, rsi; hdc
0x18006e69a  call    OffsetClipRgn
0x18006e69f  lea     ebx, [r15+1]
0x18006e6a3  mov     rdx, r14; hrgn
0x18006e6a6  mov     r8d, ebx; mode
0x18006e6a9  mov     rcx, rsi; hdc
0x18006e6ac  call    cs:__imp_ExtSelectClipRgn
0x18006e6b3  nop     dword ptr [rax+rax+00h]
0x18006e6b8  mov     r15d, ebx
0x18006e6bb  jmp     short loc_18006E6CC
0x18006e6bd  mov     rdx, r14; hrgn
0x18006e6c0  call    cs:__imp_SelectClipRgn
0x18006e6c7  nop     dword ptr [rax+rax+00h]
0x18006e6cc  mov     rdx, [rsp+0F0h+hmf]; hmf
0x18006e6d1  lea     r8, [rbp+47h+rect]; lprect
0x18006e6d5  mov     rcx, rsi; hdc
0x18006e6d8  call    PlayEnhMetaFile
0x18006e6dd  test    r14, r14
0x18006e6e0  jz      short loc_18006E718
0x18006e6e2  mov     rcx, rsi; hdc
0x18006e6e5  test    r15d, r15d
0x18006e6e8  jz      short loc_18006E6FB
0x18006e6ea  or      edx, 0FFFFFFFFh; nSavedDC
0x18006e6ed  call    cs:__imp_RestoreDC
0x18006e6f4  nop     dword ptr [rax+rax+00h]
0x18006e6f9  jmp     short loc_18006E709
0x18006e6fb  xor     edx, edx; hrgn
0x18006e6fd  call    cs:__imp_SelectClipRgn
0x18006e704  nop     dword ptr [rax+rax+00h]
0x18006e709  mov     rcx, r14; ho
0x18006e70c  call    cs:__imp_DeleteObject
0x18006e713  nop     dword ptr [rax+rax+00h]
0x18006e718  cmp     [rbp+47h+y2], 0
0x18006e71c  mov     r14, [rsp+0F0h+var_D0]
0x18006e721  mov     r15, [rbp+47h+var_C0]
0x18006e725  jnz     loc_18006E423
0x18006e72b  mov     rcx, [rbp+47h+var_70]
0x18006e72f  xor     rcx, rsp; StackCookie
0x18006e732  call    __security_check_cookie
0x18006e737  lea     r11, [rsp+0F0h+var_38]
0x18006e73f  movaps  xmm6, xmmword ptr [r11-18h]
0x18006e744  movaps  xmm7, xmmword ptr [r11-28h]
0x18006e749  mov     rsp, r11
0x18006e74c  pop     r15
0x18006e74e  pop     r14
0x18006e750  pop     r13
0x18006e752  pop     r12
0x18006e754  pop     rdi
0x18006e755  pop     rsi
0x18006e756  pop     rbx
0x18006e757  pop     rbp
0x18006e758  retn
```
