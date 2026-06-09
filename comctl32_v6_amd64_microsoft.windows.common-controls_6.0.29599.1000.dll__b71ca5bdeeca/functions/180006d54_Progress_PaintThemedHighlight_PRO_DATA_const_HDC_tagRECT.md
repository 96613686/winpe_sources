# Progress_PaintThemedHighlight(PRO_DATA const *,HDC__ *,tagRECT)

- ea: `0x180006d54`
- end: `0x18000711c`
- name: `?Progress_PaintThemedHighlight@@YA_NPEBUPRO_DATA@@PEAUHDC__@@UtagRECT@@@Z`
- size: `968`
- prototype: `bool(const struct PRO_DATA *, HDC, struct tagRECT *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006a38`

## callees

- `0x180006d54`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180006f2c`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180006f2c`
- `GDI32!GdiAlphaBlend` at `0x180007025`
- `GDI32!GdiAlphaBlend` at `0x180007025`
- `USER32!OffsetRect` at `0x180006e48`
- `USER32!OffsetRect` at `0x1800070a5`
- `USER32!OffsetRect` at `0x180006e48`
- `USER32!OffsetRect` at `0x1800070a5`
- `USER32!CopyRect` at `0x180006e1b`
- `USER32!CopyRect` at `0x180006ecb`
- `USER32!CopyRect` at `0x180006e1b`
- `USER32!CopyRect` at `0x180006ecb`
- `UxTheme!DrawThemeBackground` at `0x180006e75`
- `UxTheme!DrawThemeBackground` at `0x180006fbd`
- `UxTheme!DrawThemeBackground` at `0x180006e75`
- `UxTheme!DrawThemeBackground` at `0x180006fbd`
- `UxTheme!GetThemePartSize` at `0x180006e02`
- `UxTheme!GetThemePartSize` at `0x180006eae`
- `UxTheme!GetThemePartSize` at `0x180006e02`
- `UxTheme!GetThemePartSize` at `0x180006eae`
- `UxTheme!EndBufferedPaint` at `0x180007033`
- `UxTheme!EndBufferedPaint` at `0x180007033`
- `UxTheme!BeginBufferedPaint` at `0x180006f8b`
- `UxTheme!BeginBufferedPaint` at `0x180006f8b`
- `UxTheme!GetThemeEnumValue` at `0x180006efc`
- `UxTheme!GetThemeEnumValue` at `0x180007067`
- `UxTheme!GetThemeEnumValue` at `0x180006efc`
- `UxTheme!GetThemeEnumValue` at `0x180007067`

## pseudocode

```c
char __fastcall Progress_PaintThemedHighlight(const struct PRO_DATA *a1, HDC a2, struct tagRECT *a3)
{
  LONG left; // r10d
  LONG top; // edx
  LONG bottom; // r9d
  int v8; // ecx
  int v9; // r12d
  int v10; // r9d
  int v11; // edi
  int v12; // r14d
  char v13; // si
  int v14; // edx
  void *v15; // rcx
  int v16; // eax
  char v17; // di
  HPAINTBUFFER v18; // r12
  HDC phdc; // [rsp+60h] [rbp-49h] BYREF
  int piVal; // [rsp+68h] [rbp-41h] BYREF
  struct tagRECT rcDst; // [rsp+70h] [rbp-39h] BYREF
  SIZE psz; // [rsp+80h] [rbp-29h] BYREF
  RECT rcSrc; // [rsp+90h] [rbp-19h] BYREF
  RECT prcTarget; // [rsp+A0h] [rbp-9h] BYREF
  BP_PAINTPARAMS pPaintParams; // [rsp+B0h] [rbp+7h] BYREF

  left = a3->left;
  top = a3->top;
  bottom = a3->bottom;
  v8 = *((_DWORD *)a1 + 2) & 4;
  rcSrc.right = a3->right;
  rcSrc.bottom = bottom;
  rcSrc.top = top;
  rcSrc.left = left;
  psz = 0;
  v9 = v8 != 0 ? 10 : 8;
  v10 = bottom - top;
  v11 = rcSrc.right - left;
  v12 = v8 != 0 ? 9 : 7;
  v13 = 0;
  if ( v8 )
    v11 = v10;
  if ( GetThemePartSize(*((HTHEME *)a1 + 7), a2, v8 != 0 ? 10 : 8, 0, &rcSrc, TS_TRUE, &psz) >= 0 )
  {
    rcDst = 0;
    CopyRect(&rcDst, &rcSrc);
    v14 = *((_DWORD *)a1 + 17);
    if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
    {
      v11 += psz.cy;
      rcDst.top = rcDst.bottom - psz.cy;
      OffsetRect(&rcDst, 0, psz.cy - v14);
      if ( rcDst.bottom <= rcSrc.top )
        goto LABEL_7;
      goto LABEL_6;
    }
    v11 += psz.cx;
    rcDst.right = psz.cx + rcDst.left;
    OffsetRect(&rcDst, v14 - psz.cx, 0);
    if ( rcDst.left < rcSrc.right )
    {
LABEL_6:
      DrawThemeBackground(*((HTHEME *)a1 + 7), a2, v9, 0, &rcDst, &rcSrc);
      v13 = 1;
    }
  }
LABEL_7:
  if ( *((_DWORD *)a1 + 17) < v11 && GetThemePartSize(*((HTHEME *)a1 + 7), a2, v12, 0, &rcSrc, TS_TRUE, &psz) >= 0 )
  {
    rcDst = 0;
    CopyRect(&rcDst, &rcSrc);
    v15 = (void *)*((_QWORD *)a1 + 7);
    if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
    {
      piVal = 0;
      GetThemeEnumValue(v15, v12, 0, 4005, &piVal);
      if ( piVal )
      {
        if ( piVal == 1 )
        {
          rcDst.left += (rcDst.right - rcDst.left - psz.cx) / 2;
          rcDst.right = rcDst.left + psz.cx;
        }
        else
        {
          rcDst.left = rcDst.right - psz.cx;
        }
      }
      else
      {
        rcDst.right = rcDst.left + psz.cx;
      }
    }
    else
    {
      piVal = 2;
      GetThemeEnumValue(v15, v12, 0, 4007, &piVal);
      if ( piVal )
      {
        if ( piVal == 1 )
        {
          rcDst.top += (rcDst.bottom - rcDst.top - psz.cy) / 2;
          rcDst.bottom = rcDst.top + psz.cy;
        }
        else
        {
          rcDst.top = rcDst.bottom - psz.cy;
        }
      }
      else
      {
        rcDst.bottom = rcDst.top + psz.cy;
      }
    }
    v16 = MulDiv(*((_DWORD *)a1 + 17), 511, v11);
    *(_QWORD *)&prcTarget.left = 0;
    v17 = -1 - v16;
    pPaintParams.cbSize = 24;
    pPaintParams.dwFlags = 1;
    phdc = 0;
    if ( v16 <= 255 )
      v17 = v16;
    prcTarget.right = rcDst.right - rcDst.left;
    prcTarget.bottom = rcDst.bottom - rcDst.top;
    *(_OWORD *)&pPaintParams.prcExclude = 0;
    v18 = BeginBufferedPaint(a2, &prcTarget, BPBF_COMPATIBLEBITMAP, &pPaintParams, &phdc);
    if ( v18 )
    {
      if ( DrawThemeBackground(*((HTHEME *)a1 + 7), phdc, v12, 0, &prcTarget, 0) >= 0 )
      {
        BYTE2(piVal) = v17;
        LOWORD(piVal) = 0;
        HIBYTE(piVal) = 1;
        GdiAlphaBlend(
          a2,
          rcDst.left,
          rcDst.top,
          rcDst.right - rcDst.left,
          rcDst.bottom - rcDst.top,
          phdc,
          prcTarget.left,
          prcTarget.top,
          prcTarget.right - prcTarget.left,
          prcTarget.bottom - prcTarget.top,
          (BLENDFUNCTION)piVal);
      }
      v13 = 1;
      EndBufferedPaint(v18, 0);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180006d54  push    rbp
0x180006d56  push    rbx
0x180006d57  push    rsi
0x180006d58  push    rdi
0x180006d59  push    r12
0x180006d5b  push    r14
0x180006d5d  push    r15
0x180006d5f  lea     rbp, [rsp-27h]
0x180006d64  sub     rsp, 0D0h
0x180006d6b  mov     rax, cs:__security_cookie
0x180006d72  xor     rax, rsp
0x180006d75  mov     [rbp+57h+var_38], rax
0x180006d79  mov     r10d, [r8]
0x180006d7c  mov     rbx, rcx
0x180006d7f  mov     edi, [r8+8]
0x180006d83  mov     r15, rdx
0x180006d86  mov     edx, [r8+4]
0x180006d8a  mov     r9d, [r8+0Ch]
0x180006d8e  mov     r8d, 2
0x180006d94  mov     ecx, [rcx+8]
0x180006d97  and     ecx, 4
0x180006d9a  mov     [rbp+57h+rcSrc.right], edi
0x180006d9d  mov     eax, ecx
0x180006d9f  mov     [rbp+57h+rcSrc.bottom], r9d
0x180006da3  neg     eax
0x180006da5  mov     [rbp+57h+rcSrc.top], edx
0x180006da8  mov     eax, ecx
0x180006daa  mov     [rbp+57h+rcSrc.left], r10d
0x180006dae  sbb     r12d, r12d
0x180006db1  mov     qword ptr [rbp+57h+var_80.cx], 0
0x180006db9  and     r12d, r8d
0x180006dbc  add     r12d, 8
0x180006dc0  neg     eax
0x180006dc2  lea     rax, [rbp+57h+var_80]
0x180006dc6  sbb     r14d, r14d
0x180006dc9  mov     [rsp+100h+psz], rax; psz
0x180006dce  sub     r9d, edx
0x180006dd1  mov     [rsp+100h+eSize], 1; eSize
0x180006dd9  and     r14d, r8d
0x180006ddc  lea     rax, [rbp+57h+rcSrc]
0x180006de0  sub     edi, r10d
0x180006de3  mov     [rsp+100h+prc], rax; prc
0x180006de8  add     r14d, 7
0x180006dec  xor     sil, sil
0x180006def  test    ecx, ecx
0x180006df1  mov     r8d, r12d; iPartId
0x180006df4  mov     rcx, [rbx+38h]; hTheme
0x180006df8  mov     rdx, r15; hdc
0x180006dfb  cmovnz  edi, r9d
0x180006dff  xor     r9d, r9d; iStateId
0x180006e02  call    cs:__imp_GetThemePartSize
0x180006e08  test    eax, eax
0x180006e0a  js      short loc_180006E7E
0x180006e0c  xorps   xmm0, xmm0
0x180006e0f  lea     rdx, [rbp+57h+rcSrc]; lprcSrc
0x180006e13  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180006e17  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180006e1b  call    cs:__imp_CopyRect
0x180006e21  test    byte ptr [rbx+8], 4
0x180006e25  lea     rcx, [rbp+57h+rcDst]; lprc
0x180006e29  mov     edx, [rbx+44h]
0x180006e2c  jnz     loc_180007090
0x180006e32  mov     rax, qword ptr [rbp+57h+var_80.cx]
0x180006e36  mov     r8d, [rbp+57h+rcDst.left]
0x180006e3a  sub     edx, eax; dx
0x180006e3c  add     r8d, eax
0x180006e3f  add     edi, eax
0x180006e41  mov     [rbp+57h+rcDst.right], r8d
0x180006e45  xor     r8d, r8d; dy
0x180006e48  call    cs:__imp_OffsetRect
0x180006e4e  mov     eax, [rbp+57h+rcSrc.right]
0x180006e51  cmp     [rbp+57h+rcDst.left], eax
0x180006e54  jge     short loc_180006E7E
0x180006e56  mov     rcx, [rbx+38h]; hTheme
0x180006e5a  lea     rax, [rbp+57h+rcSrc]
0x180006e5e  mov     qword ptr [rsp+100h+eSize], rax; pClipRect
0x180006e63  xor     r9d, r9d; iStateId
0x180006e66  lea     rax, [rbp+57h+rcDst]
0x180006e6a  mov     r8d, r12d; iPartId
0x180006e6d  mov     rdx, r15; hdc
0x180006e70  mov     [rsp+100h+prc], rax; pRect
0x180006e75  call    cs:__imp_DrawThemeBackground
0x180006e7b  mov     sil, 1
0x180006e7e  cmp     [rbx+44h], edi
0x180006e81  jge     loc_180007039
0x180006e87  mov     rcx, [rbx+38h]; hTheme
0x180006e8b  lea     rax, [rbp+57h+var_80]
0x180006e8f  mov     [rsp+100h+psz], rax; psz
0x180006e94  xor     r9d, r9d; iStateId
0x180006e97  lea     rax, [rbp+57h+rcSrc]
0x180006e9b  mov     [rsp+100h+eSize], 1; eSize
0x180006ea3  mov     r8d, r14d; iPartId
0x180006ea6  mov     [rsp+100h+prc], rax; prc
0x180006eab  mov     rdx, r15; hdc
0x180006eae  call    cs:__imp_GetThemePartSize
0x180006eb4  test    eax, eax
0x180006eb6  js      loc_180007039
0x180006ebc  xorps   xmm0, xmm0
0x180006ebf  lea     rdx, [rbp+57h+rcSrc]; lprcSrc
0x180006ec3  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180006ec7  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180006ecb  call    cs:__imp_CopyRect
0x180006ed1  mov     rcx, [rbx+38h]; hTheme
0x180006ed5  lea     rax, [rbp+57h+piVal]
0x180006ed9  xor     r8d, r8d; iStateId
0x180006edc  mov     [rsp+100h+prc], rax; piVal
0x180006ee1  test    byte ptr [rbx+8], 4
0x180006ee5  mov     edx, r14d; iPartId
0x180006ee8  jnz     loc_18000705A
0x180006eee  lea     r12d, [r8+2]
0x180006ef2  mov     r9d, 0FA7h; iPropId
0x180006ef8  mov     [rbp+57h+piVal], r12d
0x180006efc  call    cs:__imp_GetThemeEnumValue
0x180006f02  mov     eax, [rbp+57h+piVal]
0x180006f05  test    eax, eax
0x180006f07  jz      loc_180007082
0x180006f0d  cmp     eax, 1
0x180006f10  mov     eax, [rbp+57h+rcDst.bottom]
0x180006f13  jz      loc_1800070BC
0x180006f19  sub     eax, [rbp+57h+var_80.cy]
0x180006f1c  mov     [rbp+57h+rcDst.top], eax
0x180006f1f  mov     ecx, [rbx+44h]; nNumber
0x180006f22  mov     r8d, edi; nDenominator
0x180006f25  mov     edi, 1FFh
0x180006f2a  mov     edx, edi; nNumerator
0x180006f2c  call    cs:__imp_MulDiv
0x180006f32  xorps   xmm0, xmm0
0x180006f35  mov     qword ptr [rbp+57h+prcTarget.left], 0
0x180006f3d  sub     edi, eax
0x180006f3f  mov     [rbp+57h+pPaintParams.cbSize], 18h
0x180006f46  cmp     eax, 0FFh
0x180006f4b  mov     [rbp+57h+pPaintParams.dwFlags], 1
0x180006f52  lea     r9, [rbp+57h+pPaintParams]; pPaintParams
0x180006f56  mov     [rbp+57h+phdc], 0
0x180006f5e  cmovle  edi, eax
0x180006f61  lea     rdx, [rbp+57h+prcTarget]; prcTarget
0x180006f65  mov     eax, [rbp+57h+rcDst.right]
0x180006f68  xor     r8d, r8d; dwFormat
0x180006f6b  sub     eax, [rbp+57h+rcDst.left]
0x180006f6e  mov     rcx, r15; hdcTarget
0x180006f71  mov     [rbp+57h+prcTarget.right], eax
0x180006f74  mov     eax, [rbp+57h+rcDst.bottom]
0x180006f77  sub     eax, [rbp+57h+rcDst.top]
0x180006f7a  mov     [rbp+57h+prcTarget.bottom], eax
0x180006f7d  lea     rax, [rbp+57h+phdc]
0x180006f81  mov     [rsp+100h+prc], rax; phdc
0x180006f86  movdqu  xmmword ptr [rbp+57h+pPaintParams.prcExclude], xmm0
0x180006f8b  call    cs:__imp_BeginBufferedPaint
0x180006f91  mov     r12, rax
0x180006f94  test    rax, rax
0x180006f97  jz      loc_180007039
0x180006f9d  mov     rdx, [rbp+57h+phdc]; hdc
0x180006fa1  lea     rax, [rbp+57h+prcTarget]
0x180006fa5  mov     rcx, [rbx+38h]; hTheme
0x180006fa9  xor     r9d, r9d; iStateId
0x180006fac  mov     qword ptr [rsp+100h+eSize], 0; pClipRect
0x180006fb5  mov     r8d, r14d; iPartId
0x180006fb8  mov     [rsp+100h+prc], rax; pRect
0x180006fbd  call    cs:__imp_DrawThemeBackground
0x180006fc3  test    eax, eax
0x180006fc5  js      short loc_18000702B
0x180006fc7  mov     esi, [rbp+57h+prcTarget.top]
0x180006fca  mov     rcx, r15; hdcDest
0x180006fcd  mov     r11d, [rbp+57h+prcTarget.left]
0x180006fd1  mov     ebx, [rbp+57h+prcTarget.bottom]
0x180006fd4  mov     r10d, [rbp+57h+prcTarget.right]
0x180006fd8  sub     ebx, esi
0x180006fda  mov     r8d, [rbp+57h+rcDst.top]; yoriginDest
0x180006fde  sub     r10d, r11d
0x180006fe1  mov     r9d, [rbp+57h+rcDst.right]
0x180006fe5  mov     edx, [rbp+57h+rcDst.left]; xoriginDest
0x180006fe8  sub     r9d, edx; wDest
0x180006feb  mov     byte ptr [rbp+57h+piVal+2], dil
0x180006fef  mov     edi, [rbp+57h+rcDst.bottom]
0x180006ff2  sub     edi, r8d
0x180006ff5  mov     word ptr [rbp+57h+piVal], 0
0x180006ffb  mov     byte ptr [rbp+57h+piVal+3], 1
0x180006fff  mov     eax, [rbp+57h+piVal]
0x180007002  mov     dword ptr [rsp+100h+ftn.BlendOp], eax; ftn
0x180007006  mov     rax, [rbp+57h+phdc]
0x18000700a  mov     [rsp+100h+hSrc], ebx; hSrc
0x18000700e  mov     [rsp+100h+wSrc], r10d; wSrc
0x180007013  mov     [rsp+100h+yoriginSrc], esi; yoriginSrc
0x180007017  mov     dword ptr [rsp+100h+psz], r11d; xoriginSrc
0x18000701c  mov     qword ptr [rsp+100h+eSize], rax; hdcSrc
0x180007021  mov     dword ptr [rsp+100h+prc], edi; hDest
0x180007025  call    cs:__imp_GdiAlphaBlend
0x18000702b  xor     edx, edx; fUpdateTarget
0x18000702d  mov     rcx, r12; hBufferedPaint
0x180007030  mov     sil, 1
0x180007033  call    cs:__imp_EndBufferedPaint
0x180007039  mov     al, sil
0x18000703c  mov     rcx, [rbp+57h+var_38]
0x180007040  xor     rcx, rsp; StackCookie
0x180007043  call    __security_check_cookie
0x180007048  add     rsp, 0D0h
0x18000704f  pop     r15
0x180007051  pop     r14
0x180007053  pop     r12
0x180007055  pop     rdi
0x180007056  pop     rsi
0x180007057  pop     rbx
0x180007058  pop     rbp
0x180007059  retn
0x18000705a  mov     r9d, 0FA5h; iPropId
0x180007060  mov     [rbp+57h+piVal], 0
0x180007067  call    cs:__imp_GetThemeEnumValue
0x18000706d  mov     eax, [rbp+57h+piVal]
0x180007070  test    eax, eax
0x180007072  jnz     short loc_1800070DF
0x180007074  mov     ecx, [rbp+57h+var_80.cx]
0x180007077  add     ecx, [rbp+57h+rcDst.left]
0x18000707a  mov     [rbp+57h+rcDst.right], ecx
0x18000707d  jmp     loc_180006F1F
0x180007082  mov     ecx, [rbp+57h+var_80.cy]
0x180007085  add     ecx, [rbp+57h+rcDst.top]
0x180007088  mov     [rbp+57h+rcDst.bottom], ecx
0x18000708b  jmp     loc_180006F1F
0x180007090  mov     r8d, [rbp+57h+var_80.cy]
0x180007094  add     edi, r8d
0x180007097  mov     eax, [rbp+57h+rcDst.bottom]
0x18000709a  sub     eax, r8d
0x18000709d  sub     r8d, edx; dy
0x1800070a0  xor     edx, edx; dx
0x1800070a2  mov     [rbp+57h+rcDst.top], eax
0x1800070a5  call    cs:__imp_OffsetRect
0x1800070ab  mov     eax, [rbp+57h+rcSrc.top]
0x1800070ae  cmp     [rbp+57h+rcDst.bottom], eax
0x1800070b1  jle     loc_180006E7E
0x1800070b7  jmp     loc_180006E56
0x1800070bc  mov     r8d, [rbp+57h+rcDst.top]
0x1800070c0  sub     eax, r8d
0x1800070c3  mov     ecx, [rbp+57h+var_80.cy]
0x1800070c6  sub     eax, ecx
0x1800070c8  cdq
0x1800070c9  idiv    r12d
0x1800070cc  add     r8d, eax
0x1800070cf  mov     [rbp+57h+rcDst.top], r8d
0x1800070d3  lea     eax, [r8+rcx]
0x1800070d7  mov     [rbp+57h+rcDst.bottom], eax
0x1800070da  jmp     loc_180006F1F
0x1800070df  cmp     eax, 1
0x1800070e2  mov     eax, [rbp+57h+rcDst.right]
0x1800070e5  jnz     short loc_180007111
0x1800070e7  mov     r8d, [rbp+57h+rcDst.left]
0x1800070eb  mov     r12d, 2
0x1800070f1  mov     rcx, qword ptr [rbp+57h+var_80.cx]
0x1800070f5  sub     eax, r8d
0x1800070f8  sub     eax, ecx
0x1800070fa  cdq
0x1800070fb  idiv    r12d
0x1800070fe  add     r8d, eax
0x180007101  mov     [rbp+57h+rcDst.left], r8d
0x180007105  lea     eax, [r8+rcx]
0x180007109  mov     [rbp+57h+rcDst.right], eax
0x18000710c  jmp     loc_180006F1F
0x180007111  sub     eax, [rbp+57h+var_80.cx]
0x180007114  mov     [rbp+57h+rcDst.left], eax
0x180007117  jmp     loc_180006F1F
```
