# DirectUI::DrawNineGrid(DirectUI::NGINFO *)

- ea: `0x18018ce98`
- end: `0x18018d6fb`
- name: `?DrawNineGrid@DirectUI@@YAJPEAUNGINFO@1@@Z`
- size: `2147`
- prototype: `__int64 __fastcall(DirectUI *__hidden this, struct DirectUI::NGINFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009a744`

## callees

- `0x180114520`
- `0x180114ebc`
- `0x18018ce98`
- `0x18018d704`
- `0x18018d9a4`
- `0x18018da60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018cfe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018cfe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018d0fc`
- `GDI32!CreateSolidBrush` at `0x18018d0ee`
- `GDI32!CreateSolidBrush` at `0x18018d0ee`
- `GDI32!DeleteObject` at `0x18018d11b`
- `GDI32!DeleteObject` at `0x18018d11b`
- `GDI32!SetBkColor` at `0x18018d2b4`
- `GDI32!SetBkColor` at `0x18018d317`
- `GDI32!SetBkColor` at `0x18018d2b4`
- `GDI32!SetBkColor` at `0x18018d317`
- `GDI32!SelectObject` at `0x18018d036`
- `GDI32!SelectObject` at `0x18018d6bb`
- `GDI32!SelectObject` at `0x18018d036`
- `GDI32!SelectObject` at `0x18018d6bb`
- `GDI32!DeleteDC` at `0x18018d6c4`
- `GDI32!DeleteDC` at `0x18018d6c4`
- `GDI32!CreateCompatibleDC` at `0x18018cfcf`
- `GDI32!CreateCompatibleDC` at `0x18018cfcf`
- `GDI32!SetLayout` at `0x18018d029`
- `GDI32!SetLayout` at `0x18018d6a6`
- `GDI32!SetLayout` at `0x18018d029`
- `GDI32!SetLayout` at `0x18018d6a6`
- `GDI32!ExtTextOutW` at `0x18018d30b`
- `GDI32!ExtTextOutW` at `0x18018d30b`
- `GDI32!GetLayout` at `0x18018d00e`
- `GDI32!GetLayout` at `0x18018d00e`
- `USER32!FillRect` at `0x18018d112`
- `USER32!FillRect` at `0x18018d112`

## pseudocode

```c
__int64 __fastcall DirectUI::DrawNineGrid(DirectUI *this, struct DirectUI::NGINFO *a2)
{
  int v3; // edx
  RECT v4; // xmm0
  int v5; // r13d
  int v6; // r15d
  int v7; // r12d
  LONG left; // ecx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // xmm0_8
  int v11; // r14d
  int v12; // ebx
  int v13; // esi
  HGDIOBJ v14; // rax
  int v15; // r11d
  int v16; // ecx
  int v17; // r10d
  __int128 v18; // xmm0
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // ecx
  HBRUSH SolidBrush; // rax
  HBRUSH v25; // rbx
  DWORD LastError; // eax
  enum HALIGN v27; // edx
  DirectUI *v28; // rcx
  __int64 v29; // rdx
  __int64 top; // r9
  __int64 v31; // r8
  int v32; // r9d
  int v33; // ecx
  unsigned __int64 v34; // r8
  int v35; // eax
  int v36; // r14d
  int v37; // r9d
  double v38; // xmm1_8
  COLORREF *v39; // r9
  COLORREF v40; // ebx
  unsigned int v41; // ebx
  unsigned int v42; // r10d
  int lprect; // [rsp+20h] [rbp-E0h]
  int lpString; // [rsp+28h] [rbp-D8h]
  struct tagRECT *c; // [rsp+30h] [rbp-D0h]
  int v47; // [rsp+50h] [rbp-B0h]
  int v48; // [rsp+50h] [rbp-B0h]
  int v49; // [rsp+54h] [rbp-ACh]
  int v50; // [rsp+58h] [rbp-A8h]
  int v51; // [rsp+5Ch] [rbp-A4h]
  int v52; // [rsp+60h] [rbp-A0h]
  int v53; // [rsp+64h] [rbp-9Ch]
  unsigned int v54; // [rsp+64h] [rbp-9Ch]
  int v55; // [rsp+68h] [rbp-98h]
  int v56; // [rsp+6Ch] [rbp-94h]
  int v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+74h] [rbp-8Ch]
  int v59; // [rsp+78h] [rbp-88h]
  unsigned int v60; // [rsp+7Ch] [rbp-84h]
  unsigned int v61; // [rsp+80h] [rbp-80h]
  DWORD l; // [rsp+84h] [rbp-7Ch]
  HDC hdc; // [rsp+90h] [rbp-70h]
  __int64 v64; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v65[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v66; // [rsp+B8h] [rbp-48h]
  __int64 v67; // [rsp+C8h] [rbp-38h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  int v69; // [rsp+D8h] [rbp-28h]
  __int64 v70; // [rsp+DCh] [rbp-24h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  __int64 v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  HGDIOBJ h; // [rsp+110h] [rbp+10h]
  RECT rc; // [rsp+118h] [rbp+18h] BYREF
  RECT rect; // [rsp+128h] [rbp+28h] BYREF

  v64 = 112;
  memset_0(v65, 0, 0x68u);
  v3 = *((_DWORD *)this + 24);
  v51 = v3;
  v4 = (RECT)*((_OWORD *)this + 4);
  rc = v4;
  if ( v3 < 0 )
    return (unsigned int)-2147467259;
  v5 = *((_DWORD *)this + 25);
  if ( v5 < 0 )
    return (unsigned int)-2147467259;
  v6 = *((_DWORD *)this + 26);
  if ( v6 < 0 )
    return (unsigned int)-2147467259;
  v7 = *((_DWORD *)this + 27);
  if ( v7 < 0 )
    return (unsigned int)-2147467259;
  left = v4.left;
  v50 = *((_DWORD *)this + 12);
  v49 = *((_DWORD *)this + 13);
  v53 = *((_DWORD *)this + 14);
  v47 = *((_DWORD *)this + 15);
  v9 = HIDWORD(*(_QWORD *)&v4.left);
  v10 = _mm_srli_si128((__m128i)v4, 8).m128i_u64[0];
  v11 = v10 - left;
  v12 = HIDWORD(v10) - v9;
  if ( v3 + v5 > (int)v10 - left )
  {
    v51 = (int)((float)((float)(v3 * v11) / (float)(v3 + v5)) + 0.5);
    v5 = v11 - v51;
  }
  if ( v7 + v6 > v12 )
  {
    v6 = (int)((float)((float)(v6 * v12) / (float)(v7 + v6)) + 0.5);
    v7 = v12 - v6;
  }
  hdc = CreateCompatibleDC(*((HDC *)this + 1));
  if ( !hdc )
    return GetLastError();
  v48 = v47 - v49;
  v54 = v53 - v50;
  l = 0;
  if ( *((char *)this + 120) < 0 )
  {
    l = GetLayout(hdc);
    SetLayout(hdc, (l & 1) == 0);
  }
  v14 = SelectObject(hdc, *((HGDIOBJ *)this + 5));
  v15 = *((_DWORD *)this + 30);
  v16 = *((_DWORD *)this + 38);
  v17 = v15 & 0x20000;
  v18 = *((_OWORD *)this + 1);
  h = v14;
  v65[0] = *((_QWORD *)this + 1);
  v74 = *((_DWORD *)this + 39);
  v70 = *(_QWORD *)((char *)this + 124);
  v19 = *((_QWORD *)this + 20);
  v73 = v16;
  v20 = *((_QWORD *)this + 5);
  v75 = v19;
  v21 = *((_QWORD *)this + 14);
  v67 = v20;
  v22 = *((_QWORD *)this + 18);
  v68 = v21;
  v72 = v22;
  v71 = *((_QWORD *)this + 17);
  v23 = *((_DWORD *)this + 8);
  v65[1] = hdc;
  v69 = v15;
  v76 = 0;
  v59 = v15 & 0x10000;
  v66 = v18;
  if ( !v23 && (v15 & 0x10000) == 0 && !v17 )
  {
    if ( (v15 & 0x100000) != 0 )
    {
      SolidBrush = CreateSolidBrush(*((_DWORD *)this + 44));
      v25 = SolidBrush;
      if ( !SolidBrush )
      {
        LastError = GetLastError();
LABEL_59:
        v13 = LastError;
        goto LABEL_60;
      }
      FillRect(*((HDC *)this + 1), &rc, SolidBrush);
      DeleteObject(v25);
    }
    v27 = *((_DWORD *)this + 45);
    v28 = (DirectUI *)*((unsigned int *)this + 46);
    rect = 0;
    DirectUI::GetAlignedRect(v28, v27, (enum VALIGN)&rc, (const struct tagRECT *)v54, v48, (__int64)&rect, c);
    v29 = 0;
    top = (unsigned int)rect.top;
    v31 = (unsigned int)rect.left;
LABEL_58:
    LastError = DirectUI::MultiBlt(&v64, v29, v31, top);
    goto LABEL_59;
  }
  v13 = 0;
  v29 = (unsigned int)v23;
  if ( v23 > 2 )
    v29 = 1;
  v60 = v29;
  if ( v51 || v5 || v6 || v7 )
  {
    v32 = *((_DWORD *)this + 20);
    v33 = *((_DWORD *)this + 23);
    v34 = *((unsigned int *)this + 22);
    v56 = v11 - *((_DWORD *)this + 21) - v32;
    v52 = v32;
    v55 = v34;
    v58 = v12 - v33 - v34;
    v35 = v32 + *((_DWORD *)this + 21);
    v57 = v33;
    if ( v35 <= v11 )
    {
      v36 = *((_DWORD *)this + 21);
    }
    else
    {
      v52 = (int)((float)((float)(v11 * v32) / (float)v35) + 0.5);
      v36 = v11 - v52;
    }
    v37 = v33 + v34;
    if ( v33 + (int)v34 > v12 )
    {
      v38 = (float)((float)(v12 * (int)v34) / (float)v37) + 0.5;
      v34 = (unsigned int)(int)v38;
      v55 = (int)v38;
      v57 = v12 - v34;
    }
    if ( !v17 )
    {
      if ( (v15 & 0x80000) != 0 && (v39 = (COLORREF *)*((_QWORD *)this + 21)) != 0 )
      {
        v40 = SetBkColor(*((HDC *)this + 1), *v39);
        rect.left = rc.left + v52;
        rect.right = rc.right - v36;
        rect.top = rc.top + v55;
        rect.bottom = rc.bottom - v57;
        ExtTextOutW(*((HDC *)this + 1), 0, 0, 2u, &rect, 0, 0, 0);
        SetBkColor(*((HDC *)this + 1), v40);
      }
      else
      {
        if ( *((_DWORD *)this + 8) == 5 )
          v29 = 2;
        LODWORD(c) = v51 + v50;
        lpString = v58;
        lprect = v56;
        v13 = DirectUI::MultiBlt(&v64, v29, (unsigned int)(rc.left + v52), (unsigned int)(v34 + rc.top));
        if ( v13 < 0 )
          goto LABEL_60;
      }
    }
    if ( !v59 )
    {
      if ( (*((_DWORD *)this + 30) & 0x40000) != 0 && *((_QWORD *)this + 21) )
      {
        LastError = DirectUI::DrawSampledBorders(
                      this,
                      (struct DirectUI::NGINFO *)v29,
                      (HDC)v34,
                      v37,
                      lprect,
                      lpString,
                      (int)c);
        goto LABEL_59;
      }
      v41 = v60;
      v42 = v60;
      if ( *((_DWORD *)this + 8) == 3 )
        v42 = 2;
      v76 = 2;
      v61 = v42;
      v13 = DirectUI::MultiBlt(&v64, v42, (unsigned int)(rc.left + v52), (unsigned int)rc.top);
      if ( v13 < 0 )
        goto LABEL_60;
      v76 = 4;
      v13 = DirectUI::MultiBlt(&v64, v61, (unsigned int)(rc.left + v52), (unsigned int)(rc.bottom - v57));
      if ( v13 < 0 )
        goto LABEL_60;
      if ( *((_DWORD *)this + 8) == 4 )
        v41 = 2;
      v76 = 1;
      v13 = DirectUI::MultiBlt(&v64, v41, (unsigned int)rc.left, (unsigned int)(rc.top + v55));
      if ( v13 < 0 )
        goto LABEL_60;
      v76 = 3;
      v13 = DirectUI::MultiBlt(&v64, v41, (unsigned int)(rc.right - v36), (unsigned int)(rc.top + v55));
      if ( v13 < 0 )
        goto LABEL_60;
      v13 = DirectUI::MultiBlt(&v64, v41, (unsigned int)rc.left, (unsigned int)rc.top);
      if ( v13 < 0 )
        goto LABEL_60;
      v13 = DirectUI::MultiBlt(&v64, v41, (unsigned int)(rc.right - v36), (unsigned int)rc.top);
      if ( v13 < 0 )
        goto LABEL_60;
      v13 = DirectUI::MultiBlt(&v64, v41, (unsigned int)(rc.right - v36), (unsigned int)(rc.bottom - v57));
      if ( v13 < 0 )
        goto LABEL_60;
      v29 = v41;
      top = (unsigned int)(rc.bottom - v57);
      goto LABEL_57;
    }
  }
  else if ( !v17 )
  {
    top = (unsigned int)rc.top;
LABEL_57:
    v31 = (unsigned int)rc.left;
    goto LABEL_58;
  }
LABEL_60:
  if ( *((char *)this + 120) < 0 )
    SetLayout(hdc, l);
  if ( h )
    SelectObject(hdc, h);
  DeleteDC(hdc);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18018ce98  mov     rax, rsp
0x18018ce9b  push    rbp
0x18018ce9c  push    rbx
0x18018ce9d  push    rsi
0x18018ce9e  push    rdi
0x18018ce9f  push    r12
0x18018cea1  push    r13
0x18018cea3  push    r14
0x18018cea5  push    r15
0x18018cea7  lea     rbp, [rsp-58h]
0x18018ceac  sub     rsp, 158h
0x18018ceb3  movaps  xmmword ptr [rax-58h], xmm6
0x18018ceb7  mov     rax, cs:__security_cookie
0x18018cebe  xor     rax, rsp
0x18018cec1  mov     [rbp+90h+var_58], rax
0x18018cec5  xor     edx, edx; Val
0x18018cec7  mov     [rbp+90h+var_F0], 70h ; 'p'
0x18018cecf  mov     rdi, rcx
0x18018ced2  lea     rcx, [rbp+90h+var_E8]; void *
0x18018ced6  lea     r8d, [rdx+68h]; Size
0x18018ceda  call    memset_0
0x18018cedf  mov     edx, [rdi+60h]
0x18018cee2  mov     [rsp+190h+var_134], edx
0x18018cee6  movups  xmm0, xmmword ptr [rdi+40h]
0x18018ceea  movups  xmmword ptr [rbp+90h+rc.left], xmm0
0x18018ceee  test    edx, edx
0x18018cef0  js      loc_18018D6CC
0x18018cef6  mov     r13d, [rdi+64h]
0x18018cefa  test    r13d, r13d
0x18018cefd  js      loc_18018D6CC
0x18018cf03  mov     r15d, [rdi+68h]
0x18018cf07  test    r15d, r15d
0x18018cf0a  js      loc_18018D6CC
0x18018cf10  mov     r12d, [rdi+6Ch]
0x18018cf14  test    r12d, r12d
0x18018cf17  js      loc_18018D6CC
0x18018cf1d  mov     eax, [rdi+30h]
0x18018cf20  movq    rcx, xmm0
0x18018cf25  movsd   xmm6, cs:__real@3fe0000000000000
0x18018cf2d  mov     [rsp+190h+var_138], eax
0x18018cf31  mov     eax, [rdi+34h]
0x18018cf34  mov     [rsp+190h+var_13C], eax
0x18018cf38  mov     eax, [rdi+38h]
0x18018cf3b  mov     dword ptr [rsp+190h+var_12C], eax
0x18018cf3f  mov     eax, [rdi+3Ch]
0x18018cf42  mov     [rsp+190h+var_140], eax
0x18018cf46  mov     rax, rcx
0x18018cf49  shr     rax, 20h
0x18018cf4d  psrldq  xmm0, 8
0x18018cf52  movq    r14, xmm0
0x18018cf57  mov     rbx, r14
0x18018cf5a  sub     r14d, ecx
0x18018cf5d  shr     rbx, 20h
0x18018cf61  lea     ecx, [rdx+r13]
0x18018cf65  sub     ebx, eax
0x18018cf67  cmp     ecx, r14d
0x18018cf6a  jle     short loc_18018CF99
0x18018cf6c  mov     eax, r14d
0x18018cf6f  movd    xmm0, ecx
0x18018cf73  imul    eax, edx
0x18018cf76  mov     r13d, r14d
0x18018cf79  cvtdq2ps xmm0, xmm0
0x18018cf7c  movd    xmm1, eax
0x18018cf80  cvtdq2ps xmm1, xmm1
0x18018cf83  divss   xmm1, xmm0
0x18018cf87  cvtps2pd xmm1, xmm1
0x18018cf8a  addsd   xmm1, xmm6
0x18018cf8e  cvttsd2si eax, xmm1
0x18018cf92  mov     [rsp+190h+var_134], eax
0x18018cf96  sub     r13d, eax
0x18018cf99  lea     ecx, [r12+r15]
0x18018cf9d  cmp     ecx, ebx
0x18018cf9f  jle     short loc_18018CFCB
0x18018cfa1  mov     eax, ebx
0x18018cfa3  movd    xmm0, ecx
0x18018cfa7  imul    eax, r15d
0x18018cfab  mov     r12d, ebx
0x18018cfae  cvtdq2ps xmm0, xmm0
0x18018cfb1  movd    xmm1, eax
0x18018cfb5  cvtdq2ps xmm1, xmm1
0x18018cfb8  divss   xmm1, xmm0
0x18018cfbc  cvtps2pd xmm1, xmm1
0x18018cfbf  addsd   xmm1, xmm6
0x18018cfc3  cvttsd2si r15d, xmm1
0x18018cfc8  sub     r12d, r15d
0x18018cfcb  mov     rcx, [rdi+8]; hdc
0x18018cfcf  call    cs:__imp_CreateCompatibleDC
0x18018cfd5  mov     [rbp+90h+hdc], rax
0x18018cfd9  mov     rsi, rax
0x18018cfdc  test    rax, rax
0x18018cfdf  jnz     short loc_18018CFEE
0x18018cfe1  call    cs:__imp_GetLastError
0x18018cfe7  mov     esi, eax
0x18018cfe9  jmp     loc_18018D6D1
0x18018cfee  mov     eax, [rsp+190h+var_13C]
0x18018cff2  sub     [rsp+190h+var_140], eax
0x18018cff6  mov     eax, [rsp+190h+var_138]
0x18018cffa  sub     dword ptr [rsp+190h+var_12C], eax
0x18018cffe  test    byte ptr [rdi+78h], 80h
0x18018d002  mov     [rbp+90h+l], 0
0x18018d009  jz      short loc_18018D02F
0x18018d00b  mov     rcx, rsi; hdc
0x18018d00e  call    cs:__imp_GetLayout
0x18018d014  mov     ecx, 1
0x18018d019  mov     [rbp+90h+l], eax
0x18018d01c  test    cl, al
0x18018d01e  jz      short loc_18018D024
0x18018d020  xor     edx, edx
0x18018d022  jmp     short loc_18018D026
0x18018d024  mov     edx, ecx; l
0x18018d026  mov     rcx, rsi; hdc
0x18018d029  call    cs:__imp_SetLayout
0x18018d02f  mov     rdx, [rdi+28h]; h
0x18018d033  mov     rcx, rsi; hdc
0x18018d036  call    cs:__imp_SelectObject
0x18018d03c  mov     r11d, [rdi+78h]
0x18018d040  mov     r10d, r11d
0x18018d043  mov     ecx, [rdi+98h]
0x18018d049  and     r10d, 20000h
0x18018d050  movups  xmm0, xmmword ptr [rdi+10h]
0x18018d054  mov     [rbp+90h+h], rax
0x18018d058  mov     rax, [rdi+8]
0x18018d05c  mov     [rbp+90h+var_E8], rax
0x18018d060  mov     eax, [rdi+9Ch]
0x18018d066  mov     [rbp+90h+var_94], eax
0x18018d069  mov     rax, [rdi+7Ch]
0x18018d06d  mov     [rbp+90h+var_B4], rax
0x18018d071  mov     rax, [rdi+0A0h]
0x18018d078  mov     [rbp+90h+var_98], ecx
0x18018d07b  mov     rcx, [rdi+28h]
0x18018d07f  mov     [rbp+90h+var_90], rax
0x18018d083  mov     rax, [rdi+70h]
0x18018d087  mov     [rbp+90h+var_C8], rcx
0x18018d08b  mov     rcx, [rdi+90h]
0x18018d092  mov     [rbp+90h+var_C0], rax
0x18018d096  mov     eax, r11d
0x18018d099  mov     [rbp+90h+var_A0], rcx
0x18018d09d  and     eax, 10000h
0x18018d0a2  mov     rcx, [rdi+88h]
0x18018d0a9  mov     [rbp+90h+var_A8], rcx
0x18018d0ad  mov     ecx, [rdi+20h]
0x18018d0b0  mov     [rbp+90h+var_E0], rsi
0x18018d0b4  mov     [rbp+90h+var_B8], r11d
0x18018d0b8  mov     [rbp+90h+var_88], 0
0x18018d0bf  mov     [rsp+190h+var_118], eax
0x18018d0c3  movdqu  [rbp+90h+var_D8], xmm0
0x18018d0c8  test    ecx, ecx
0x18018d0ca  jnz     loc_18018D184
0x18018d0d0  test    eax, eax
0x18018d0d2  jnz     loc_18018D184
0x18018d0d8  test    r10d, r10d
0x18018d0db  jnz     loc_18018D184
0x18018d0e1  bt      r11d, 14h
0x18018d0e6  jnb     short loc_18018D121
0x18018d0e8  mov     ecx, [rdi+0B0h]; color
0x18018d0ee  call    cs:__imp_CreateSolidBrush
0x18018d0f4  mov     rbx, rax
0x18018d0f7  test    rax, rax
0x18018d0fa  jnz     short loc_18018D107
0x18018d0fc  call    cs:__imp_GetLastError
0x18018d102  jmp     loc_18018D694
0x18018d107  mov     rcx, [rdi+8]; hDC
0x18018d10b  lea     rdx, [rbp+90h+rc]; lprc
0x18018d10f  mov     r8, rbx; hbr
0x18018d112  call    cs:__imp_FillRect
0x18018d118  mov     rcx, rbx; ho
0x18018d11b  call    cs:__imp_DeleteObject
0x18018d121  mov     esi, dword ptr [rsp+190h+var_12C]
0x18018d125  lea     rax, [rbp+90h+rect]
0x18018d129  mov     ebx, [rsp+190h+var_140]
0x18018d12d  lea     r8, [rbp+90h+rc]; enum VALIGN
0x18018d131  mov     edx, [rdi+0B4h]; enum HALIGN
0x18018d137  xorps   xmm0, xmm0
0x18018d13a  mov     ecx, [rdi+0B8h]; this
0x18018d140  mov     r9d, esi; struct tagRECT *
0x18018d143  mov     [rsp+190h+lpString], rax; __int64
0x18018d148  mov     dword ptr [rsp+190h+lprect], ebx; int
0x18018d14c  movups  xmmword ptr [rbp+90h+rect.left], xmm0
0x18018d150  call    ?GetAlignedRect@DirectUI@@YAXW4HALIGN@1@W4VALIGN@1@PEBUtagRECT@@HHPEAU4@@Z; DirectUI::GetAlignedRect(DirectUI::HALIGN,DirectUI::VALIGN,tagRECT const *,int,int,tagRECT *)
0x18018d155  mov     eax, [rsp+190h+var_13C]
0x18018d159  xor     edx, edx
0x18018d15b  mov     r9d, [rbp+90h+rect.top]
0x18018d15f  mov     r8d, [rbp+90h+rect.left]
0x18018d163  mov     [rsp+190h+var_148], ebx
0x18018d167  mov     [rsp+190h+var_150], esi
0x18018d16b  mov     dword ptr [rsp+190h+lpDx], eax
0x18018d16f  mov     eax, [rsp+190h+var_138]
0x18018d173  mov     dword ptr [rsp+190h+c], eax
0x18018d177  mov     dword ptr [rsp+190h+lpString], ebx
0x18018d17b  mov     dword ptr [rsp+190h+lprect], esi
0x18018d17f  jmp     loc_18018D68B
0x18018d184  xor     esi, esi
0x18018d186  mov     edx, ecx
0x18018d188  cmp     ecx, 2
0x18018d18b  lea     eax, [rsi+1]
0x18018d18e  cmovg   edx, eax
0x18018d191  mov     [rsp+190h+var_114], edx
0x18018d195  cmp     [rsp+190h+var_134], esi
0x18018d199  jnz     short loc_18018D1E5
0x18018d19b  test    r13d, r13d
0x18018d19e  jnz     short loc_18018D1E5
0x18018d1a0  test    r15d, r15d
0x18018d1a3  jnz     short loc_18018D1E5
0x18018d1a5  test    r12d, r12d
0x18018d1a8  jnz     short loc_18018D1E5
0x18018d1aa  test    r10d, r10d
0x18018d1ad  jnz     loc_18018D696
0x18018d1b3  mov     eax, dword ptr [rsp+190h+var_12C]
0x18018d1b7  mov     ecx, [rsp+190h+var_140]
0x18018d1bb  mov     r9d, [rbp+90h+rc.top]
0x18018d1bf  mov     [rsp+190h+var_148], ecx
0x18018d1c3  mov     [rsp+190h+var_150], eax
0x18018d1c7  mov     eax, [rsp+190h+var_13C]
0x18018d1cb  mov     dword ptr [rsp+190h+lpDx], eax
0x18018d1cf  mov     eax, [rsp+190h+var_138]
0x18018d1d3  mov     dword ptr [rsp+190h+c], eax
0x18018d1d7  mov     dword ptr [rsp+190h+lpString], ebx
0x18018d1db  mov     dword ptr [rsp+190h+lprect], r14d
0x18018d1e0  jmp     loc_18018D687
0x18018d1e5  mov     r9d, [rdi+50h]
0x18018d1e9  mov     eax, r14d
0x18018d1ec  sub     eax, [rdi+54h]
0x18018d1ef  mov     ecx, [rdi+5Ch]
0x18018d1f2  sub     eax, r9d
0x18018d1f5  mov     r8d, [rdi+58h]
0x18018d1f9  mov     [rsp+190h+var_124], eax
0x18018d1fd  mov     eax, ebx
0x18018d1ff  sub     eax, ecx
0x18018d201  mov     [rsp+190h+var_130], r9d
0x18018d206  sub     eax, r8d
0x18018d209  mov     dword ptr [rsp+190h+var_12C+4], r8d
0x18018d20e  mov     [rsp+190h+var_11C], eax
0x18018d212  mov     eax, [rdi+54h]
0x18018d215  add     eax, r9d
0x18018d218  mov     [rsp+190h+var_120], ecx
0x18018d21c  cmp     eax, r14d
0x18018d21f  jle     short loc_18018D24E
0x18018d221  imul    r9d, r14d
0x18018d225  movd    xmm0, eax
0x18018d229  cvtdq2ps xmm0, xmm0
0x18018d22c  movd    xmm1, r9d
0x18018d231  cvtdq2ps xmm1, xmm1
0x18018d234  divss   xmm1, xmm0
0x18018d238  cvtps2pd xmm1, xmm1
0x18018d23b  addsd   xmm1, xmm6
0x18018d23f  cvttsd2si r9d, xmm1
0x18018d244  mov     [rsp+190h+var_130], r9d
0x18018d249  sub     r14d, r9d
0x18018d24c  jmp     short loc_18018D252
0x18018d24e  mov     r14d, [rdi+54h]
0x18018d252  mov     eax, [rsp+190h+var_134]
0x18018d256  lea     r9d, [rcx+r8]
0x18018d25a  cmp     r9d, ebx
0x18018d25d  jle     short loc_18018D291
0x18018d25f  imul    r8d, ebx
0x18018d263  mov     ecx, ebx
0x18018d265  movd    xmm0, r9d
0x18018d26a  cvtdq2ps xmm0, xmm0
0x18018d26d  movd    xmm1, r8d
0x18018d272  cvtdq2ps xmm1, xmm1
0x18018d275  divss   xmm1, xmm0
0x18018d279  cvtps2pd xmm1, xmm1
0x18018d27c  addsd   xmm1, xmm6
0x18018d280  cvttsd2si r8d, xmm1
0x18018d285  sub     ecx, r8d
0x18018d288  mov     dword ptr [rsp+190h+var_12C+4], r8d
0x18018d28d  mov     [rsp+190h+var_120], ecx
0x18018d291  test    r10d, r10d
0x18018d294  jnz     loc_18018D398
0x18018d29a  bt      r11d, 13h
0x18018d29f  jnb     short loc_18018D31F
0x18018d2a1  mov     r9, [rdi+0A8h]
0x18018d2a8  test    r9, r9
0x18018d2ab  jz      short loc_18018D31F
0x18018d2ad  mov     edx, [r9]; color
0x18018d2b0  mov     rcx, [rdi+8]; hdc
0x18018d2b4  call    cs:__imp_SetBkColor
0x18018d2ba  mov     ecx, [rbp+90h+rc.right]
0x18018d2bd  mov     r9d, 2; options
0x18018d2c3  mov     edx, [rsp+190h+var_130]
0x18018d2c7  sub     ecx, r14d
0x18018d2ca  add     edx, [rbp+90h+rc.left]
0x18018d2cd  mov     ebx, eax
0x18018d2cf  xor     eax, eax
0x18018d2d1  mov     [rbp+90h+rect.left], edx
0x18018d2d4  mov     edx, dword ptr [rsp+190h+var_12C+4]
0x18018d2d8  xor     r8d, r8d; y
0x18018d2db  add     edx, [rbp+90h+rc.top]
0x18018d2de  mov     [rsp+190h+lpDx], rax; lpDx
0x18018d2e3  mov     [rbp+90h+rect.right], ecx
0x18018d2e6  mov     ecx, [rbp+90h+rc.bottom]
0x18018d2e9  sub     ecx, [rsp+190h+var_120]
0x18018d2ed  mov     dword ptr [rsp+190h+c], eax; c
0x18018d2f1  mov     [rsp+190h+lpString], rax; lpString
0x18018d2f6  lea     rax, [rbp+90h+rect]
0x18018d2fa  mov     [rbp+90h+rect.top], edx
0x18018d2fd  xor     edx, edx; x
0x18018d2ff  mov     [rbp+90h+rect.bottom], ecx
0x18018d302  mov     rcx, [rdi+8]; hdc
0x18018d306  mov     [rsp+190h+lprect], rax; lprect
  ... truncated ...
```
