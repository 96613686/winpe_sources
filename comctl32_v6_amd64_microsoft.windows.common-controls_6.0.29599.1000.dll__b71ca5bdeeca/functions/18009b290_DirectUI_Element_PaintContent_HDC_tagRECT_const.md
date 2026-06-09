# DirectUI::Element::PaintContent(HDC__ *,tagRECT const *)

- ea: `0x18009b290`
- end: `0x18009b84f`
- name: `?PaintContent@Element@DirectUI@@QEAAXPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `1471`
- prototype: `void __fastcall(DirectUI::Element *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009a490`

## callees

- `0x180085150`
- `0x180085548`
- `0x1800999b8`
- `0x1800999e0`
- `0x18009b290`
- `0x18009b9a0`
- `0x18009bdb4`
- `0x18009bdf4`
- `0x180114520`
- `0x180114e74`
- `0x180165390`
- `0x18016995c`
- `0x180169df4`

## import_xrefs

- `GDI32!SelectObject` at `0x18009b59d`
- `GDI32!SelectObject` at `0x18009b74b`
- `GDI32!SelectObject` at `0x18009b59d`
- `GDI32!SelectObject` at `0x18009b74b`
- `GDI32!DeleteDC` at `0x18009b754`
- `GDI32!DeleteDC` at `0x18009b754`
- `GDI32!CreateCompatibleDC` at `0x18009b55e`
- `GDI32!CreateCompatibleDC` at `0x18009b55e`
- `GDI32!BitBlt` at `0x18009b6d7`
- `GDI32!BitBlt` at `0x18009b6d7`
- `GDI32!StretchBlt` at `0x18009b733`
- `GDI32!StretchBlt` at `0x18009b733`
- `GDI32!SetStretchBltMode` at `0x18009b6eb`
- `GDI32!SetStretchBltMode` at `0x18009b73e`
- `GDI32!SetStretchBltMode` at `0x18009b6eb`
- `GDI32!SetStretchBltMode` at `0x18009b73e`
- `GDI32!GdiAlphaBlend` at `0x18009b692`
- `GDI32!GdiAlphaBlend` at `0x18009b692`
- `GDI32!GdiTransparentBlt` at `0x18009b61c`
- `GDI32!GdiTransparentBlt` at `0x18009b61c`
- `GDI32!PlayEnhMetaFile` at `0x18009b550`
- `GDI32!PlayEnhMetaFile` at `0x18009b550`
- `USER32!DrawIconEx` at `0x18009b511`
- `USER32!DrawIconEx` at `0x18009b511`
- `UxTheme!GetThemePartSize` at `0x18009b3fb`
- `UxTheme!GetThemePartSize` at `0x18009b3fb`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18009b802`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18009b802`

## pseudocode

```c
void __fastcall DirectUI::Element::PaintContent(DirectUI::Element *this, HDC a2, const struct tagRECT *a3)
{
  bool v3; // zf
  struct tagRECT v5; // xmm0
  unsigned int ContentAlign; // eax
  int v9; // r8d
  int v10; // r14d
  DirectUI::Element *v11; // rcx
  struct DirectUI::UpdateCache *v12; // r9
  struct DirectUI::Value *Value; // rax
  struct DirectUI::Value *v14; // rsi
  int v15; // ecx
  int cy; // edi
  DWORD v17; // ebx
  __int64 v18; // rdi
  int v19; // ebx
  float ElementScaleFactor; // xmm0_4
  LONG v21; // eax
  int v22; // ebx
  float v23; // xmm0_4
  const unsigned __int16 *v24; // rdx
  LONG cx; // r13d
  int v26; // r9d
  unsigned __int64 v27; // r8
  int v28; // r14d
  __int64 v29; // r14
  HICON v30; // rax
  int v31; // edx
  HENHMETAFILE Image; // rax
  HDC CompatibleDC; // r12
  void *v34; // rax
  HDC v35; // rcx
  HGDIOBJ v36; // rax
  unsigned __int8 v37; // r8
  int v38; // edx
  int v39; // edx
  int v40; // edx
  int v41; // ecx
  int v42; // edx
  int hSrc; // ecx
  int v44; // edx
  HDC v45; // r15
  int v46; // ebx
  const unsigned __int16 *v47; // rdx
  int v48; // r9d
  HDC v49; // r8
  const struct tagRECT *eSize; // [rsp+28h] [rbp-61h]
  SIZE psz; // [rsp+60h] [rbp-29h] BYREF
  HTHEME hTheme; // [rsp+68h] [rbp-21h] BYREF
  HDC hdcDest; // [rsp+70h] [rbp-19h] BYREF
  HGDIOBJ h; // [rsp+78h] [rbp-11h]
  int xLeft[4]; // [rsp+80h] [rbp-9h] BYREF
  DTBGOPTS pOptions; // [rsp+90h] [rbp+7h] BYREF

  v3 = (*((_BYTE *)this + 149) & 0x40) == 0;
  v5 = *a3;
  hdcDest = a2;
  *(struct tagRECT *)xLeft = v5;
  if ( !v3 )
  {
    ContentAlign = DirectUI::Element::GetContentAlign(this);
    v10 = DirectUI::MapAlign(this, (struct DirectUI::Element *)ContentAlign, v9);
    Value = DirectUI::Element::GetValue(v11, DirectUI::Element::ContentProp, 2, v12);
    v14 = Value;
    v15 = (int)(*(_DWORD *)Value << 26) >> 26;
    if ( v15 == 5 )
    {
      DirectUI::Element::PaintStringContent(this, a2, a3, Value, v10);
      goto LABEL_64;
    }
    if ( v15 != 9 && v15 != 11 )
      goto LABEL_64;
    psz = 0;
    cy = 0;
    v17 = 1;
    if ( v15 == 11 )
    {
      v18 = *((_QWORD *)Value + 1);
      if ( (*(_BYTE *)(v18 + 56) & 2) != 0 )
      {
        v19 = *(_DWORD *)(v18 + 48);
        ElementScaleFactor = DirectUI::Element::GetElementScaleFactor(this);
        v21 = (int)floorf((float)(ElementScaleFactor * (float)v19) + 0.5);
        v17 = 1;
      }
      else
      {
        v21 = *(unsigned __int16 *)(v18 + 16);
      }
      psz.cx = v21;
      if ( (*(_BYTE *)(v18 + 56) & 1) != 0 )
      {
        v22 = *(_DWORD *)(v18 + 52);
        v23 = DirectUI::Element::GetElementScaleFactor(this);
        cy = (int)floorf((float)(v23 * (float)v22) + 0.5);
        v17 = 1;
      }
      else
      {
        cy = *(unsigned __int16 *)(v18 + 18);
      }
      psz.cy = cy;
    }
    else
    {
      if ( *((_BYTE *)Value + 8) != 6 )
        goto LABEL_64;
      v24 = (const unsigned __int16 *)*((_QWORD *)Value + 2);
      hTheme = 0;
      if ( v24 )
      {
        if ( DirectUI::Element::GetTheme(this, v24, &hTheme) >= 0 )
          GetThemePartSize(hTheme, a2, *((_DWORD *)v14 + 6), *((_DWORD *)v14 + 7), 0, TS_TRUE, &psz);
        cy = psz.cy;
      }
    }
    cx = psz.cx;
    v26 = xLeft[0];
    v27 = (unsigned int)xLeft[1];
    if ( xLeft[2] - xLeft[0] < psz.cx )
      cx = xLeft[2] - xLeft[0];
    if ( xLeft[3] - xLeft[1] < cy )
      cy = xLeft[3] - xLeft[1];
    if ( (v10 & 3) == 1 )
    {
      v26 = (xLeft[2] - cx - xLeft[0]) / 2 + xLeft[0];
    }
    else
    {
      if ( (v10 & 3) != 2 )
        goto LABEL_27;
      v26 = xLeft[2] - cx;
    }
    xLeft[0] = v26;
LABEL_27:
    v28 = v10 & 0xC;
    if ( v28 == 4 )
    {
      v27 = (unsigned int)((xLeft[3] - cy - xLeft[1]) / 2 + xLeft[1]);
    }
    else
    {
      if ( v28 != 8 )
        goto LABEL_32;
      v27 = (unsigned int)(xLeft[3] - cy);
    }
    xLeft[1] = v27;
LABEL_32:
    if ( (*(_BYTE *)v14 & 0x3F) != 0xB )
    {
      hdcDest = 0;
      xLeft[2] = v26 + cx;
      xLeft[3] = cy + v27;
      v47 = (const unsigned __int16 *)*((_QWORD *)v14 + 2);
      if ( v47 && DirectUI::Element::GetTheme(this, v47, (void **)&hdcDest) >= 0 )
      {
        v48 = *((_DWORD *)v14 + 7);
        v49 = (HDC)*((unsigned int *)v14 + 6);
        if ( ((unsigned __int64)hdcDest & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          v3 = (*((_BYTE *)this + 152) & 0x40) == 0;
          pOptions.rcClip = *(RECT *)xLeft;
          if ( !v3 )
            v17 = 33;
          pOptions.dwSize = 24;
          pOptions.dwFlags = v17;
          DrawThemeBackgroundEx(hdcDest, a2, (int)v49, v48, (LPCRECT)xLeft, &pOptions);
        }
        else
        {
          DirectUI::EmulateDrawThemeBackground((DirectUI *)hdcDest, a2, v49, v48, (int)xLeft, eSize);
        }
      }
      goto LABEL_64;
    }
    v29 = *((_QWORD *)v14 + 1);
    switch ( *(_BYTE *)(v29 + 20) & 7 )
    {
      case 0:
        goto LABEL_42;
      case 1:
        goto LABEL_38;
      case 2:
        v31 = *((_DWORD *)this + 38);
        xLeft[2] = v26 + cx;
        xLeft[3] = cy + v27;
        Image = (HENHMETAFILE)DirectUI::Value::GetImage(v14, (v31 & 0x40) != 0, 1.0);
        PlayEnhMetaFile(a2, Image, (const RECT *)xLeft);
        break;
      case 4:
LABEL_42:
        CompatibleDC = CreateCompatibleDC(a2);
        v34 = DirectUI::Value::GetImage(v14, (*((_DWORD *)this + 38) & 0x40) != 0, 1.0);
        if ( CompatibleDC )
        {
          v35 = CompatibleDC;
          if ( v34 )
          {
            v36 = SelectObject(CompatibleDC, v34);
            v37 = *(_BYTE *)(v29 + 20);
            h = v36;
            v38 = (v37 >> 3) & 0xF;
            if ( v38 )
            {
              v39 = v38 - 1;
              if ( v39 && (v40 = v39 - 1) != 0 )
              {
                if ( v40 == 1 )
                  GdiTransparentBlt(
                    hdcDest,
                    xLeft[0],
                    xLeft[1],
                    cx,
                    cy,
                    CompatibleDC,
                    0,
                    0,
                    *(unsigned __int16 *)(v29 + 16),
                    *(unsigned __int16 *)(v29 + 18),
                    *(unsigned __int8 *)(v29 + 22)
                  | (*(unsigned __int8 *)(v29 + 24) << 16)
                  | (*(unsigned __int8 *)(v29 + 23) << 8));
              }
              else
              {
                v41 = *((_DWORD *)this + 34) * *(unsigned __int8 *)(v29 + 22);
                LOWORD(hTheme) = 0;
                v42 = (unsigned __int64)(2155905153LL * v41) >> 32;
                hSrc = *(unsigned __int16 *)(v29 + 18);
                BYTE2(hTheme) = (v42 >> 7 < 0) + (v42 >> 7);
                v44 = *(unsigned __int16 *)(v29 + 16);
                BYTE3(hTheme) = (v37 & 0x78) == 16;
                GdiAlphaBlend(hdcDest, xLeft[0], xLeft[1], cx, cy, CompatibleDC, 0, 0, v44, hSrc, (BLENDFUNCTION)hTheme);
              }
            }
            else if ( cx == *(unsigned __int16 *)(v29 + 16) && cy == *(unsigned __int16 *)(v29 + 18) )
            {
              BitBlt(hdcDest, xLeft[0], xLeft[1], cx, cy, CompatibleDC, 0, 0, 0xCC0020u);
            }
            else
            {
              v45 = hdcDest;
              v46 = SetStretchBltMode(hdcDest, 4);
              StretchBlt(
                v45,
                xLeft[0],
                xLeft[1],
                cx,
                cy,
                CompatibleDC,
                0,
                0,
                *(unsigned __int16 *)(v29 + 16),
                *(unsigned __int16 *)(v29 + 18),
                0xCC0020u);
              SetStretchBltMode(v45, v46);
            }
            SelectObject(CompatibleDC, h);
            v35 = CompatibleDC;
          }
          DeleteDC(v35);
        }
        break;
      case 5:
LABEL_38:
        if ( cx )
        {
          if ( cy )
          {
            v30 = DirectUI::GethIcon(v14, this, (struct DirectUI::Element *)v27);
            DrawIconEx(a2, xLeft[0], xLeft[1], v30, cx, cy, 0, 0, 3u);
          }
        }
        break;
    }
LABEL_64:
    DirectUI::Value::Release(v14);
  }
}

```

## disassembly

```asm
0x18009b290  mov     [rsp-8+arg_18], rbx
0x18009b295  push    rbp
0x18009b296  push    rsi
0x18009b297  push    rdi
0x18009b298  push    r12
0x18009b29a  push    r13
0x18009b29c  push    r14
0x18009b29e  push    r15
0x18009b2a0  lea     rbp, [rsp-27h]
0x18009b2a5  sub     rsp, 0B0h
0x18009b2ac  mov     rax, cs:__security_cookie
0x18009b2b3  xor     rax, rsp
0x18009b2b6  mov     [rbp+57h+var_38], rax
0x18009b2ba  test    byte ptr [rcx+95h], 40h
0x18009b2c1  mov     rbx, r8
0x18009b2c4  movups  xmm0, xmmword ptr [r8]
0x18009b2c8  mov     r12, rdx
0x18009b2cb  mov     [rbp+57h+hdcDest], rdx
0x18009b2cf  mov     r15, rcx
0x18009b2d2  movdqu  xmmword ptr [rbp+57h+xLeft], xmm0
0x18009b2d7  jz      loc_18009B828
0x18009b2dd  call    ?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x18009b2e2  mov     edx, eax; struct DirectUI::Element *
0x18009b2e4  mov     rcx, r15; this
0x18009b2e7  call    ?MapAlign@DirectUI@@YAHPEAVElement@1@H@Z; DirectUI::MapAlign(DirectUI::Element *,int)
0x18009b2ec  lea     rdx, ?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; const struct DirectUI::PropertyInfo *(*)(void)
0x18009b2f3  mov     r8d, 2; int
0x18009b2f9  mov     r14d, eax
0x18009b2fc  call    ?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18009b301  mov     rsi, rax
0x18009b304  mov     ecx, [rax]
0x18009b306  shl     ecx, 1Ah
0x18009b309  sar     ecx, 1Ah
0x18009b30c  cmp     ecx, 5
0x18009b30f  jz      loc_18009B80A
0x18009b315  cmp     ecx, 9
0x18009b318  jz      short loc_18009B323
0x18009b31a  cmp     ecx, 0Bh
0x18009b31d  jnz     loc_18009B820
0x18009b323  xor     r13d, r13d
0x18009b326  mov     qword ptr [rbp+57h+var_80.cx], r13
0x18009b32a  mov     edi, r13d
0x18009b32d  lea     ebx, [r13+1]
0x18009b331  cmp     ecx, 0Bh
0x18009b334  jnz     short loc_18009B3B3
0x18009b336  mov     rdi, [rax+8]
0x18009b33a  test    byte ptr [rdi+38h], 2
0x18009b33e  jz      short loc_18009B36D
0x18009b340  mov     ebx, [rdi+30h]
0x18009b343  mov     rcx, r15; this
0x18009b346  call    ?GetElementScaleFactor@Element@DirectUI@@QEAAMXZ; DirectUI::Element::GetElementScaleFactor(void)
0x18009b34b  movd    xmm1, ebx
0x18009b34f  cvtdq2ps xmm1, xmm1
0x18009b352  mulss   xmm0, xmm1
0x18009b356  addss   xmm0, cs:__real@3f000000; X
0x18009b35e  call    floorf
0x18009b363  cvttss2si eax, xmm0
0x18009b367  lea     ebx, [r13+1]
0x18009b36b  jmp     short loc_18009B371
0x18009b36d  movzx   eax, word ptr [rdi+10h]
0x18009b371  mov     [rbp+57h+var_80.cx], eax
0x18009b374  test    [rdi+38h], bl
0x18009b377  jz      short loc_18009B3AA
0x18009b379  mov     ebx, [rdi+34h]
0x18009b37c  mov     rcx, r15; this
0x18009b37f  call    ?GetElementScaleFactor@Element@DirectUI@@QEAAMXZ; DirectUI::Element::GetElementScaleFactor(void)
0x18009b384  movd    xmm1, ebx
0x18009b388  cvtdq2ps xmm1, xmm1
0x18009b38b  mulss   xmm0, xmm1
0x18009b38f  addss   xmm0, cs:__real@3f000000; X
0x18009b397  call    floorf
0x18009b39c  cvttss2si edi, xmm0
0x18009b3a0  mov     ebx, 1
0x18009b3a5  mov     [rbp+57h+var_80.cy], edi
0x18009b3a8  jmp     short loc_18009B404
0x18009b3aa  movzx   edi, word ptr [rdi+12h]
0x18009b3ae  mov     [rbp+57h+var_80.cy], edi
0x18009b3b1  jmp     short loc_18009B404
0x18009b3b3  cmp     byte ptr [rax+8], 6
0x18009b3b7  jnz     loc_18009B820
0x18009b3bd  mov     rdx, [rax+10h]; unsigned __int16 *
0x18009b3c1  mov     [rbp+57h+hTheme], r13
0x18009b3c5  test    rdx, rdx
0x18009b3c8  jz      short loc_18009B404
0x18009b3ca  lea     r8, [rbp+57h+hTheme]; void **
0x18009b3ce  mov     rcx, r15; this
0x18009b3d1  call    ?GetTheme@Element@DirectUI@@AEAAJPEBGPEAPEAX@Z; DirectUI::Element::GetTheme(ushort const *,void * *)
0x18009b3d6  test    eax, eax
0x18009b3d8  js      short loc_18009B401
0x18009b3da  mov     r9d, [rsi+1Ch]; iStateId
0x18009b3de  lea     rax, [rbp+57h+var_80]
0x18009b3e2  mov     r8d, [rsi+18h]; iPartId
0x18009b3e6  mov     rdx, r12; hdc
0x18009b3e9  mov     rcx, [rbp+57h+hTheme]; hTheme
0x18009b3ed  mov     [rsp+0E0h+psz], rax; psz
0x18009b3f2  mov     [rsp+0E0h+eSize], ebx; struct tagRECT *
0x18009b3f6  mov     [rsp+0E0h+prc], r13; prc
0x18009b3fb  call    cs:__imp_GetThemePartSize
0x18009b401  mov     edi, [rbp+57h+var_80.cy]
0x18009b404  mov     r13d, [rbp+57h+var_80.cx]
0x18009b408  mov     edx, r14d
0x18009b40b  mov     ecx, [rbp+57h+xLeft+8]
0x18009b40e  mov     r11d, 2
0x18009b414  mov     r9d, [rbp+57h+xLeft]
0x18009b418  mov     eax, ecx
0x18009b41a  mov     r10d, [rbp+57h+xLeft+0Ch]
0x18009b41e  sub     eax, r9d
0x18009b421  mov     r8d, [rbp+57h+xLeft+4]
0x18009b425  cmp     eax, r13d
0x18009b428  cmovl   r13d, eax
0x18009b42c  mov     eax, r10d
0x18009b42f  sub     eax, r8d
0x18009b432  cmp     eax, edi
0x18009b434  cmovl   edi, eax
0x18009b437  and     edx, 3
0x18009b43a  sub     edx, 1
0x18009b43d  jz      short loc_18009B44C
0x18009b43f  cmp     edx, 1
0x18009b442  jnz     short loc_18009B45F
0x18009b444  mov     r9d, ecx
0x18009b447  sub     r9d, r13d
0x18009b44a  jmp     short loc_18009B45B
0x18009b44c  sub     ecx, r13d
0x18009b44f  sub     ecx, r9d
0x18009b452  mov     eax, ecx
0x18009b454  cdq
0x18009b455  idiv    r11d
0x18009b458  add     r9d, eax
0x18009b45b  mov     [rbp+57h+xLeft], r9d
0x18009b45f  and     r14d, 0Ch
0x18009b463  cmp     r14d, 4
0x18009b467  jz      short loc_18009B477
0x18009b469  cmp     r14d, 8
0x18009b46d  jnz     short loc_18009B48B
0x18009b46f  mov     r8d, r10d
0x18009b472  sub     r8d, edi
0x18009b475  jmp     short loc_18009B487
0x18009b477  sub     r10d, edi
0x18009b47a  sub     r10d, r8d
0x18009b47d  mov     eax, r10d
0x18009b480  cdq
0x18009b481  idiv    r11d
0x18009b484  add     r8d, eax; struct DirectUI::Element *
0x18009b487  mov     [rbp+57h+xLeft+4], r8d
0x18009b48b  mov     eax, [rsi]
0x18009b48d  and     eax, 3Fh
0x18009b490  cmp     al, 0Bh
0x18009b492  jnz     loc_18009B75F
0x18009b498  mov     r14, [rsi+8]
0x18009b49c  movzx   ecx, byte ptr [r14+14h]
0x18009b4a1  and     ecx, 7
0x18009b4a4  jz      loc_18009B55B
0x18009b4aa  sub     ecx, 1
0x18009b4ad  jz      short loc_18009B4C6
0x18009b4af  sub     ecx, 1
0x18009b4b2  jz      short loc_18009B51C
0x18009b4b4  sub     ecx, r11d
0x18009b4b7  jz      loc_18009B55B
0x18009b4bd  cmp     ecx, 1
0x18009b4c0  jnz     loc_18009B820
0x18009b4c6  test    r13d, r13d
0x18009b4c9  jz      loc_18009B820
0x18009b4cf  test    edi, edi
0x18009b4d1  jz      loc_18009B820
0x18009b4d7  mov     rdx, r15; struct DirectUI::Value *
0x18009b4da  mov     rcx, rsi; this
0x18009b4dd  call    ?GethIcon@DirectUI@@YAPEAUHICON__@@PEAVValue@1@PEAVElement@1@@Z; DirectUI::GethIcon(DirectUI::Value *,DirectUI::Element *)
0x18009b4e2  mov     r8d, [rbp+57h+xLeft+4]; yTop
0x18009b4e6  mov     r9, rax; hIcon
0x18009b4e9  mov     edx, [rbp+57h+xLeft]; xLeft
0x18009b4ec  mov     rcx, r12; hdc
0x18009b4ef  mov     [rsp+0E0h+diFlags], 3; diFlags
0x18009b4f7  mov     [rsp+0E0h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x18009b500  mov     dword ptr [rsp+0E0h+psz], 0; istepIfAniCur
0x18009b508  mov     [rsp+0E0h+eSize], edi; cyWidth
0x18009b50c  mov     dword ptr [rsp+0E0h+prc], r13d; cxWidth
0x18009b511  call    cs:__imp_DrawIconEx
0x18009b517  jmp     loc_18009B820
0x18009b51c  mov     edx, [r15+98h]
0x18009b523  lea     eax, [r9+r13]
0x18009b527  movss   xmm2, cs:__real@3f800000; float
0x18009b52f  mov     rcx, rsi; this
0x18009b532  mov     [rbp+57h+xLeft+8], eax
0x18009b535  lea     eax, [rdi+r8]
0x18009b539  shr     edx, 6
0x18009b53c  and     dl, bl; bool
0x18009b53e  mov     [rbp+57h+xLeft+0Ch], eax
0x18009b541  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18009b546  lea     r8, [rbp+57h+xLeft]; lprect
0x18009b54a  mov     rdx, rax; hmf
0x18009b54d  mov     rcx, r12; hdc
0x18009b550  call    cs:__imp_PlayEnhMetaFile
0x18009b556  jmp     loc_18009B820
0x18009b55b  mov     rcx, r12; hdc
0x18009b55e  call    cs:__imp_CreateCompatibleDC
0x18009b564  mov     edx, [r15+98h]
0x18009b56b  mov     rcx, rsi; this
0x18009b56e  movss   xmm2, cs:__real@3f800000; float
0x18009b576  mov     r12, rax
0x18009b579  shr     edx, 6
0x18009b57c  and     dl, bl; bool
0x18009b57e  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18009b583  xor     ebx, ebx
0x18009b585  test    r12, r12
0x18009b588  jz      loc_18009B820
0x18009b58e  mov     rcx, r12; hdc
0x18009b591  test    rax, rax
0x18009b594  jz      loc_18009B754
0x18009b59a  mov     rdx, rax; h
0x18009b59d  call    cs:__imp_SelectObject
0x18009b5a3  movzx   r8d, byte ptr [r14+14h]
0x18009b5a8  mov     edx, r8d
0x18009b5ab  mov     [rbp+57h+h], rax
0x18009b5af  shr     edx, 3
0x18009b5b2  and     edx, 0Fh
0x18009b5b5  jz      loc_18009B69D
0x18009b5bb  sub     edx, 1
0x18009b5be  jz      short loc_18009B627
0x18009b5c0  sub     edx, 1
0x18009b5c3  jz      short loc_18009B627
0x18009b5c5  cmp     edx, 1
0x18009b5c8  jnz     loc_18009B744
0x18009b5ce  movzx   ecx, word ptr [r14+10h]
0x18009b5d3  mov     r9d, r13d; wDest
0x18009b5d6  movzx   edx, byte ptr [r14+17h]
0x18009b5db  movzx   eax, byte ptr [r14+18h]
0x18009b5e0  mov     r8d, [rbp+57h+xLeft+4]; yoriginDest
0x18009b5e4  shl     edx, 8
0x18009b5e7  shl     eax, 10h
0x18009b5ea  or      edx, eax
0x18009b5ec  movzx   eax, byte ptr [r14+16h]
0x18009b5f1  or      edx, eax
0x18009b5f3  movzx   eax, word ptr [r14+12h]
0x18009b5f8  mov     [rsp+0E0h+crTransparent], edx; crTransparent
0x18009b5fc  mov     edx, [rbp+57h+xLeft]; xoriginDest
0x18009b5ff  mov     [rsp+0E0h+hSrc], eax; hSrc
0x18009b603  mov     [rsp+0E0h+diFlags], ecx; wSrc
0x18009b607  mov     rcx, [rbp+57h+hdcDest]; hdcDest
0x18009b60b  mov     dword ptr [rsp+0E0h+hbrFlickerFreeDraw], ebx; yoriginSrc
0x18009b60f  mov     dword ptr [rsp+0E0h+psz], ebx; xoriginSrc
0x18009b613  mov     qword ptr [rsp+0E0h+eSize], r12; hdcSrc
0x18009b618  mov     dword ptr [rsp+0E0h+prc], edi; hDest
0x18009b61c  call    cs:__imp_GdiTransparentBlt
0x18009b622  jmp     loc_18009B744
0x18009b627  movzx   ecx, byte ptr [r14+16h]
0x18009b62c  and     r8b, 78h
0x18009b630  imul    ecx, [r15+88h]
0x18009b638  mov     eax, 80808081h
0x18009b63d  mov     word ptr [rbp+57h+hTheme], bx
0x18009b641  mov     r9d, r13d; wDest
0x18009b644  imul    ecx
0x18009b646  add     edx, ecx
0x18009b648  movzx   ecx, word ptr [r14+12h]
0x18009b64d  sar     edx, 7
0x18009b650  mov     eax, edx
0x18009b652  shr     eax, 1Fh
0x18009b655  add     edx, eax
0x18009b657  mov     byte ptr [rbp+57h+hTheme+2], dl
0x18009b65a  cmp     r8b, 10h
0x18009b65e  movzx   edx, word ptr [r14+10h]
0x18009b663  mov     r8d, [rbp+57h+xLeft+4]; yoriginDest
0x18009b667  setz    byte ptr [rbp+57h+hTheme+3]
0x18009b66b  mov     eax, dword ptr [rbp+57h+hTheme]
0x18009b66e  mov     [rsp+0E0h+crTransparent], eax; ftn
0x18009b672  mov     [rsp+0E0h+hSrc], ecx; hSrc
0x18009b676  mov     rcx, [rbp+57h+hdcDest]; hdcDest
0x18009b67a  mov     [rsp+0E0h+diFlags], edx; wSrc
0x18009b67e  mov     edx, [rbp+57h+xLeft]; xoriginDest
0x18009b681  mov     dword ptr [rsp+0E0h+hbrFlickerFreeDraw], ebx; yoriginSrc
0x18009b685  mov     dword ptr [rsp+0E0h+psz], ebx; xoriginSrc
0x18009b689  mov     qword ptr [rsp+0E0h+eSize], r12; hdcSrc
0x18009b68e  mov     dword ptr [rsp+0E0h+prc], edi; hDest
0x18009b692  call    cs:__imp_GdiAlphaBlend
0x18009b698  jmp     loc_18009B744
0x18009b69d  movzx   eax, word ptr [r14+10h]
0x18009b6a2  cmp     r13d, eax
0x18009b6a5  jnz     short loc_18009B6DF
0x18009b6a7  movzx   eax, word ptr [r14+12h]
0x18009b6ac  cmp     edi, eax
0x18009b6ae  jnz     short loc_18009B6DF
0x18009b6b0  mov     r8d, [rbp+57h+xLeft+4]; y
0x18009b6b4  mov     r9d, r13d; cx
0x18009b6b7  mov     edx, [rbp+57h+xLeft]; x
0x18009b6ba  mov     rcx, [rbp+57h+hdcDest]; hdc
0x18009b6be  mov     [rsp+0E0h+diFlags], 0CC0020h; rop
0x18009b6c6  mov     dword ptr [rsp+0E0h+hbrFlickerFreeDraw], ebx; y1
0x18009b6ca  mov     dword ptr [rsp+0E0h+psz], ebx; x1
0x18009b6ce  mov     qword ptr [rsp+0E0h+eSize], r12; hdcSrc
0x18009b6d3  mov     dword ptr [rsp+0E0h+prc], edi; cy
0x18009b6d7  call    cs:__imp_BitBlt
0x18009b6dd  jmp     short loc_18009B744
0x18009b6df  mov     r15, [rbp+57h+hdcDest]
0x18009b6e3  mov     edx, 4; mode
0x18009b6e8  mov     rcx, r15; hdc
0x18009b6eb  call    cs:__imp_SetStretchBltMode
0x18009b6f1  movzx   ecx, word ptr [r14+12h]
0x18009b6f6  mov     r9d, r13d; wDest
0x18009b6f9  movzx   edx, word ptr [r14+10h]
0x18009b6fe  mov     ebx, eax
0x18009b700  mov     r8d, [rbp+57h+xLeft+4]; yDest
  ... truncated ...
```
