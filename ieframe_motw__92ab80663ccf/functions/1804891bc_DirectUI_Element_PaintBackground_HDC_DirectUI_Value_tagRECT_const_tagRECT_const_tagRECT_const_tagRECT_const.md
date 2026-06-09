# DirectUI::Element::PaintBackground(HDC__ *,DirectUI::Value *,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)

- ea: `0x1804891bc`
- end: `0x180489b88`
- name: `?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z`
- size: `2508`
- prototype: `void __usercall(DirectUI::Element *__hidden this@<rcx>, HDC hdc@<rdx>, struct DirectUI::Value *@<r8>, const struct tagRECT *@<r9>, const struct tagRECT *, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180488f80`
- `0x1804da620`

## callees

- `0x1800c1c36`
- `0x180342898`
- `0x180487104`
- `0x180487de4`
- `0x180487e8c`
- `0x18048824c`
- `0x180488d9c`
- `0x180488e94`
- `0x180488f34`
- `0x1804891bc`
- `0x18048b090`
- `0x18048c940`
- `0x180495170`
- `0x180495244`
- `0x1804cbaf4`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180489233`
- `KERNEL32!TlsGetValue` at `0x180489233`
- `GDI32!CreateSolidBrush` at `0x180489890`
- `GDI32!CreateSolidBrush` at `0x180489890`
- `GDI32!GdiGradientFill` at `0x180489a67`
- `GDI32!GdiGradientFill` at `0x180489a67`
- `GDI32!PlayEnhMetaFile` at `0x180489313`
- `GDI32!PlayEnhMetaFile` at `0x180489313`
- `GDI32!SetStretchBltMode` at `0x180489375`
- `GDI32!SetStretchBltMode` at `0x1804895b0`
- `GDI32!SetStretchBltMode` at `0x180489625`
- `GDI32!SetStretchBltMode` at `0x180489690`
- `GDI32!SetStretchBltMode` at `0x180489375`
- `GDI32!SetStretchBltMode` at `0x1804895b0`
- `GDI32!SetStretchBltMode` at `0x180489625`
- `GDI32!SetStretchBltMode` at `0x180489690`
- `GDI32!StretchBlt` at `0x18048967f`
- `GDI32!StretchBlt` at `0x18048967f`
- `GDI32!DeleteObject` at `0x180489b58`
- `GDI32!DeleteObject` at `0x180489b58`
- `GDI32!SelectObject` at `0x18048960e`
- `GDI32!SelectObject` at `0x1804896a2`
- `GDI32!SelectObject` at `0x18048960e`
- `GDI32!SelectObject` at `0x1804896a2`
- `GDI32!DeleteDC` at `0x1804896b1`
- `GDI32!DeleteDC` at `0x1804896b1`
- `GDI32!CreateCompatibleDC` at `0x1804895f9`
- `GDI32!CreateCompatibleDC` at `0x1804895f9`
- `USER32!IntersectRect` at `0x1804892a2`
- `USER32!IntersectRect` at `0x1804892a2`
- `USER32!IsRectEmpty` at `0x1804892b2`
- `USER32!IsRectEmpty` at `0x1804892b2`
- `USER32!FillRect` at `0x180489aee`
- `USER32!FillRect` at `0x180489aee`
- `USER32!SetRect` at `0x1804893ca`
- `USER32!SetRect` at `0x180489401`
- `USER32!SetRect` at `0x1804893ca`
- `USER32!SetRect` at `0x180489401`
- `USER32!CopyRect` at `0x180489415`
- `USER32!CopyRect` at `0x180489415`
- `USER32!DrawFrameControl` at `0x180489850`
- `USER32!DrawFrameControl` at `0x180489850`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18048982b`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18048982b`

## pseudocode

```c
void __fastcall DirectUI::Element::PaintBackground(
        DirectUI::Element *this,
        DirectUI *hdc,
        struct DirectUI::Value *a3,
        struct tagRECT *a4,
        struct tagRECT *a5,
        const struct tagRECT *a6,
        const struct tagRECT *a7)
{
  HBRUSH SolidBrush; // r14
  RECT v8; // xmm0
  DWORD v11; // r15d
  char v12; // bl
  int v14; // esi
  const unsigned __int16 *v15; // rdx
  LPVOID Value; // r8
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // r14
  char v21; // al
  unsigned int v22; // edi
  __int64 v23; // r9
  HENHMETAFILE Image; // rax
  int v25; // esi
  bool v26; // dl
  void *v27; // rax
  int v28; // r9d
  int *v29; // rdi
  int v30; // ecx
  char v31; // al
  unsigned __int64 right; // rdx
  int v33; // r8d
  int v34; // r9d
  unsigned int ContentAlign; // eax
  int v36; // r8d
  char v37; // al
  LONG left; // ecx
  int v39; // ecx
  int v40; // r9d
  LONG top; // ecx
  int v42; // ecx
  char v43; // al
  int v44; // ecx
  int v45; // ecx
  void *v46; // rbx
  HDC CompatibleDC; // rsi
  HGDIOBJ v48; // rdi
  const struct tagRECT *v49; // r8
  int v50; // ecx
  __int64 (__fastcall *v51)(LPVOID, void *, struct DirectUI::Value *); // rbx
  void *v52; // rax
  __int64 v53; // rax
  int v54; // r9d
  HDC v55; // r8
  bool v56; // zf
  RECT v57; // xmm0
  void *v58; // rdi
  int v59; // ecx
  char v60; // r9
  ULONG v61; // r11d
  unsigned int v62; // edx
  unsigned int v63; // eax
  unsigned int v64; // edx
  unsigned int v65; // eax
  int v66; // ecx
  __int64 v67; // rcx
  unsigned __int8 yBottom; // [rsp+20h] [rbp-E0h]
  const struct tagRECT *hdcSrc; // [rsp+28h] [rbp-D8h]
  void *v70; // [rsp+68h] [rbp-98h]
  HTHEME hTheme; // [rsp+78h] [rbp-88h] BYREF
  RECT *lprcSrc1; // [rsp+80h] [rbp-80h]
  LPVOID v73; // [rsp+88h] [rbp-78h]
  int v74; // [rsp+90h] [rbp-70h] BYREF
  DirectUI *v75; // [rsp+98h] [rbp-68h]
  struct tagRECT v76; // [rsp+A0h] [rbp-60h] BYREF
  int v77; // [rsp+B0h] [rbp-50h]
  void *v78; // [rsp+B8h] [rbp-48h]
  struct tagRECT rc; // [rsp+C0h] [rbp-40h] BYREF
  RECT rcSrc; // [rsp+D0h] [rbp-30h] BYREF
  int v81; // [rsp+E0h] [rbp-20h]
  int v82; // [rsp+E4h] [rbp-1Ch]
  int v83; // [rsp+E8h] [rbp-18h]
  int v84; // [rsp+ECh] [rbp-14h]
  int v85; // [rsp+F0h] [rbp-10h]
  int v86; // [rsp+F4h] [rbp-Ch]
  int v87; // [rsp+F8h] [rbp-8h]
  int v88; // [rsp+FCh] [rbp-4h]
  int v89; // [rsp+108h] [rbp+8h]
  int v90; // [rsp+128h] [rbp+28h]
  __int16 v91; // [rsp+12Ch] [rbp+2Ch]
  char v92; // [rsp+12Eh] [rbp+2Eh]
  char v93; // [rsp+12Fh] [rbp+2Fh]
  RECT rcSrc2; // [rsp+150h] [rbp+50h] BYREF
  DTBGOPTS rcDst; // [rsp+160h] [rbp+60h] BYREF
  struct _TRIVERTEX pVertex; // [rsp+180h] [rbp+80h] BYREF
  LONG v97; // [rsp+190h] [rbp+90h]
  LONG v98; // [rsp+194h] [rbp+94h]
  __int16 v99; // [rsp+198h] [rbp+98h]
  __int16 v100; // [rsp+19Ah] [rbp+9Ah]
  __int16 v101; // [rsp+19Ch] [rbp+9Ch]
  __int16 v102; // [rsp+19Eh] [rbp+9Eh]
  LONG v103; // [rsp+1A0h] [rbp+A0h]
  LONG bottom; // [rsp+1A4h] [rbp+A4h]
  __int16 v105; // [rsp+1A8h] [rbp+A8h]
  __int16 v106; // [rsp+1AAh] [rbp+AAh]
  __int16 v107; // [rsp+1ACh] [rbp+ACh]
  __int16 v108; // [rsp+1AEh] [rbp+AEh]
  LONG v109; // [rsp+1B0h] [rbp+B0h]
  LONG v110; // [rsp+1B4h] [rbp+B4h]
  __int16 v111; // [rsp+1B8h] [rbp+B8h]
  __int16 v112; // [rsp+1BAh] [rbp+BAh]
  __int16 v113; // [rsp+1BCh] [rbp+BCh]
  __int16 v114; // [rsp+1BEh] [rbp+BEh]

  SolidBrush = 0;
  v8 = *a4;
  *(_QWORD *)&rcDst.dwSize = a7;
  v11 = 1;
  v12 = 1;
  hTheme = a4;
  lprcSrc1 = a5;
  v70 = 0;
  LOBYTE(v14) = -1;
  rcSrc2 = v8;
  Value = TlsGetValue(DirectUI::g_dwFontCacheSlot);
  v17 = (int)(*(_DWORD *)a3 << 26) >> 26;
  v73 = Value;
  v18 = v17 - 1;
  if ( !v18 )
  {
    v12 = 0;
    SolidBrush = (HBRUSH)BrushFromEnumI(*((unsigned int *)a3 + 2), v15, Value);
    v70 = SolidBrush;
    v22 = ARGBColorFromEnumI(*((unsigned int *)a3 + 2));
    v66 = *((_DWORD *)this + 34) * HIBYTE(v22);
    v15 = (const unsigned __int16 *)(unsigned int)((int)((unsigned __int64)(2155905153LL * v66) >> 32) >> 7);
    v14 = v66 / 255;
LABEL_76:
    if ( !(_BYTE)v14 )
      goto LABEL_84;
LABEL_10:
    *(_OWORD *)&rcDst.dwSize = 0;
    IntersectRect((LPRECT)&rcDst, lprcSrc1, &rcSrc2);
    if ( !IsRectEmpty((const RECT *)&rcDst) )
    {
      if ( *((char *)this + 151) >= 0 )
      {
        if ( (unsigned __int8)v14 < 0xFAu )
        {
          LOBYTE(v23) = v14;
          UtilDrawBlendRect_0(hdc, &rcDst, SolidBrush, v23, 0, 0);
        }
        else
        {
          if ( (Microsoft_Windows_DUIEnableBits & 1) != 0 )
            McTemplateMofU0(0, DirectUI_ElementRenderFillRect_Start, DirectUI_ElementRenderFillRectId);
          FillRect((HDC)hdc, (const RECT *)&rcDst, SolidBrush);
          if ( (Microsoft_Windows_DUIEnableBits & 1) != 0 )
            McTemplateMofU0(v67, DirectUI_ElementRenderFillRect_Stop, DirectUI_ElementRenderFillRectId);
        }
      }
      else
      {
        LOBYTE(v23) = v14;
        DirectUI::_FillWithAlpha((HDC)hdc, (HDC)&rcDst, (struct tagRECT *)v22, v23, yBottom);
      }
    }
    goto LABEL_84;
  }
  v19 = v18 - 8;
  if ( v19 )
  {
    if ( v19 != 2 )
    {
LABEL_8:
      v12 = 1;
LABEL_9:
      v22 = 0;
      goto LABEL_10;
    }
    v20 = *((_QWORD *)a3 + 1);
    v21 = *(_BYTE *)(v20 + 20) & 7;
    if ( v21 )
    {
      if ( v21 == 2 )
      {
        Image = (HENHMETAFILE)DirectUI::Value::GetImage(a3, (*((_DWORD *)this + 38) & 0x40) != 0, 1.0);
        PlayEnhMetaFile((HDC)hdc, Image, &rcSrc2);
LABEL_14:
        v12 = 1;
LABEL_84:
        v58 = v70;
        goto LABEL_85;
      }
      if ( v21 != 4 )
      {
LABEL_7:
        SolidBrush = 0;
        goto LABEL_8;
      }
    }
    if ( ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) == 1 )
    {
      v50 = *((_DWORD *)this + 34) * *(unsigned __int8 *)(v20 + 22);
      LODWORD(v15) = (unsigned __int64)(-2139062143LL * v50) >> 32;
      v14 = v50 / 255;
      if ( !(unsigned __int8)(v50 / 255) )
      {
        v12 = 0;
        goto LABEL_84;
      }
    }
    else
    {
      if ( ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) == 4 )
      {
        DirectUI::AutoClipRect::AutoClipRect(
          (DirectUI::AutoClipRect *)&rcDst,
          (HDC)hdc,
          (const struct tagRECT *)hTheme,
          lprcSrc1);
        v46 = DirectUI::Value::GetImage(a3, (*((_DWORD *)this + 38) & 0x40) != 0, 1.0);
        CompatibleDC = CreateCompatibleDC((HDC)hdc);
        v48 = SelectObject(CompatibleDC, v46);
        LODWORD(v46) = SetStretchBltMode((HDC)hdc, 4);
        StretchBlt(
          (HDC)hdc,
          rcSrc2.left,
          rcSrc2.top,
          rcSrc2.right - rcSrc2.left,
          rcSrc2.bottom - rcSrc2.top,
          CompatibleDC,
          0,
          0,
          *(unsigned __int16 *)(v20 + 16),
          *(unsigned __int16 *)(v20 + 18),
          0xCC0020u);
        SetStretchBltMode((HDC)hdc, (int)v46);
        SelectObject(CompatibleDC, v48);
        DeleteDC(CompatibleDC);
        if ( *((char *)this + 151) < 0 )
          DirectUI::MakeOpaque(hdc, (HDC)&rcSrc2, v49);
        DirectUI::AutoClipRect::~AutoClipRect((DirectUI::AutoClipRect *)&rcDst);
        goto LABEL_14;
      }
      if ( ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) == 5
        || ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) == 6
        || ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xFu) - 7 <= 1 )
      {
        memset_0(&v74, 0, 0xC0u);
        v25 = SetStretchBltMode((HDC)hdc, 3);
        v26 = (*((_DWORD *)this + 38) & 0x40) != 0;
        v74 = 192;
        v75 = hdc;
        v77 = 1;
        v27 = DirectUI::Value::GetImage(a3, v26, 1.0);
        v28 = *(unsigned __int16 *)(v20 + 16);
        v78 = v27;
        SetRect(&rc, 0, 0, v28, *(unsigned __int16 *)(v20 + 18));
        v29 = *(int **)&rcDst.dwSize;
        SetRect(
          &rcSrc,
          *(_DWORD *)hTheme - **(_DWORD **)&rcDst.dwSize,
          *((_DWORD *)hTheme + 1) - *(_DWORD *)(*(_QWORD *)&rcDst.dwSize + 4LL),
          *(_DWORD *)(*(_QWORD *)&rcDst.dwSize + 8LL) + *((_DWORD *)hTheme + 2),
          *(_DWORD *)(*(_QWORD *)&rcDst.dwSize + 12LL) + *((_DWORD *)hTheme + 3));
        CopyRect(&v76, &rcSrc);
        v30 = *v29;
        v31 = *(_BYTE *)(v20 + 20) & 0x78;
        right = (unsigned int)v29[2];
        v33 = v29[1];
        v34 = v29[3];
        v85 = *v29;
        v86 = right;
        v87 = v33;
        v88 = v34;
        if ( v31 != 64 )
        {
          v81 = v30;
          v82 = right;
          v83 = v33;
          v84 = v34;
          goto LABEL_36;
        }
        ContentAlign = DirectUI::Element::GetContentAlign(this);
        v37 = DirectUI::MapAlign(this, (struct DirectUI::Element *)ContentAlign, v36);
        if ( (v37 & 3) != 0 )
        {
          if ( (v37 & 3) == 1 )
          {
            v39 = *(unsigned __int16 *)(v20 + 16);
            right = (unsigned int)((rcSrc.right - v39 - rcSrc.left) >> 31);
            LODWORD(right) = (rcSrc.right - v39 - rcSrc.left) % 2;
            v81 = (rcSrc.right - v39 - rcSrc.left) / 2;
            v82 = rcSrc.right - v81 - v39 - rcSrc.left;
            goto LABEL_28;
          }
          if ( (v37 & 3) != 2 )
            goto LABEL_28;
          right = (unsigned int)a6->right;
          left = rcSrc.right - *(unsigned __int16 *)(v20 + 16) - right - rcSrc.left;
        }
        else
        {
          left = a6->left;
          right = rcSrc.right - (unsigned int)*(unsigned __int16 *)(v20 + 16) - a6->left - rcSrc.left;
        }
        v82 = right;
        v81 = left;
LABEL_28:
        v40 = v37 & 0xC;
        if ( (v37 & 0xC) != 0 )
        {
          if ( v40 == 4 )
          {
            v42 = *(unsigned __int16 *)(v20 + 18);
            right = (unsigned int)((rcSrc.bottom - v42 - rcSrc.top) >> 31);
            LODWORD(right) = (rcSrc.bottom - v42 - rcSrc.top) % 2;
            v83 = (rcSrc.bottom - v42 - rcSrc.top) / 2;
            v84 = rcSrc.bottom - v83 - v42 - rcSrc.top;
          }
          else if ( v40 == 8 )
          {
            right = (unsigned int)a6->bottom;
            top = rcSrc.bottom - *(unsigned __int16 *)(v20 + 18) - right - rcSrc.top;
LABEL_34:
            v83 = top;
            v84 = right;
          }
LABEL_36:
          v43 = *(_BYTE *)(v20 + 20) & 0x78;
          if ( v43 == 48 )
          {
            v44 = (*(unsigned __int8 *)(v20 + 24) << 16) | (*(unsigned __int8 *)(v20 + 23) << 8);
            v89 = 2;
            v90 = *(unsigned __int8 *)(v20 + 22) | v44;
          }
          else if ( v43 == 56 )
          {
            v45 = *((_DWORD *)this + 34) * *(unsigned __int8 *)(v20 + 22);
            v89 = 1;
            v91 = 0;
            v93 = 1;
            right = (unsigned int)(v45 / 255);
            v92 = v45 / 255;
          }
          DirectUI::DrawNineGrid((DirectUI *)&v74, (struct DirectUI::NGINFO *)right);
          SetStretchBltMode((HDC)hdc, v25);
          goto LABEL_14;
        }
        top = a6->top;
        right = rcSrc.bottom - (unsigned int)*(unsigned __int16 *)(v20 + 18) - top - rcSrc.top;
        goto LABEL_34;
      }
    }
    if ( !Value )
      goto LABEL_7;
    v51 = *(__int64 (__fastcall **)(LPVOID, void *, struct DirectUI::Value *))(*(_QWORD *)Value + 16LL);
    v52 = DirectUI::Value::GetImage(a3, (*((_DWORD *)this + 38) & 0x40) != 0, 1.0);
    v53 = v51(v73, v52, a3);
    v22 = 0;
    SolidBrush = (HBRUSH)v53;
    v70 = (void *)v53;
    v12 = 0;
    goto LABEL_76;
  }
  if ( *((_BYTE *)a3 + 8) && *((_BYTE *)a3 + 8) != 1 )
  {
    if ( *((_BYTE *)a3 + 8) == 2 )
    {
      v22 = *((_DWORD *)a3 + 4);
      v59 = *((_DWORD *)this + 34) * HIBYTE(v22);
      v15 = (const unsigned __int16 *)(unsigned int)(v59 / 255);
      if ( (_BYTE)v15 )
      {
        LOBYTE(v14) = v59 / 255;
        SolidBrush = CreateSolidBrush(v22 & 0xFFFFFF);
        v70 = SolidBrush;
        goto LABEL_10;
      }
LABEL_62:
      v12 = 0;
      v58 = 0;
      goto LABEL_85;
    }
    if ( *((_BYTE *)a3 + 8) != 3 && *((_BYTE *)a3 + 8) != 4 )
    {
      if ( *((_BYTE *)a3 + 8) == 5 )
      {
        DrawFrameControl((HDC)hdc, &rcSrc2, *((_DWORD *)a3 + 4), *((_DWORD *)a3 + 5));
      }
      else
      {
        if ( *((_BYTE *)a3 + 8) != 6 )
          goto LABEL_9;
        v15 = (const unsigned __int16 *)*((_QWORD *)a3 + 2);
        hTheme = 0;
        if ( v15 && (int)DirectUI::Element::GetTheme(this, v15, &hTheme) >= 0 )
        {
          v54 = *((_DWORD *)a3 + 7);
          v55 = (HDC)*((unsigned int *)a3 + 6);
          if ( ((unsigned __int64)hTheme & 0xFFFFFFFFFFFF0000uLL) != 0 )
          {
            v56 = (*((_BYTE *)this + 152) & 0x40) == 0;
            rcDst.dwSize = 24;
            if ( !v56 )
              v11 = 33;
            v57 = *lprcSrc1;
            rcDst.dwFlags = v11;
            rcDst.rcClip = v57;
            DrawThemeBackgroundEx(hTheme, (HDC)hdc, (int)v55, v54, &rcSrc2, &rcDst);
          }
          else
          {
            DirectUI::EmulateDrawThemeBackground((DirectUI *)hTheme, hdc, v55, v54, (int)&rcSrc2, hdcSrc);
          }
        }
      }
      goto LABEL_62;
    }
  }
  v60 = *((_BYTE *)a3 + 8);
  pVertex.x = rcSrc2.left;
  pVertex.y = rcSrc2.top;
  v97 = rcSrc2.left;
  v98 = rcSrc2.top;
  v103 = rcSrc2.right;
  bottom = rcSrc2.bottom;
  v109 = rcSrc2.right;
  v110 = rcSrc2.bottom;
  if ( !v60 || v60 == 3 )
  {
    v61 = 0;
    v56 = (*((_BYTE *)this + 152) & 0x40) == 0;
    v103 = (rcSrc2.left + rcSrc2.right) / 2;
    v97 = v103;
    if ( !v56 )
    {
      pVertex.x = rcSrc2.right;
      v109 = rcSrc2.left;
    }
  }
  else
  {
    v61 = 1;
    bottom = (rcSrc2.bottom + rcSrc2.top) / 2;
    v98 = bottom;
  }
  v62 = *((_DWORD *)a3 + 4);
  pVertex.Red = (unsigned __int8)v62 << 8;
  rcDst.dwSize = 0;
  pVertex.Green = v62 & 0xFF00;
  v63 = HIWORD(v62);
  pVertex.Alpha = HIBYTE(v62) << 8;
  v64 = *((_DWORD *)a3 + 5);
  pVertex.Blue = (unsigned __int8)v63 << 8;
  if ( (unsigned __int8)(v60 - 3) <= 1u )
  {
    v105 = (unsigned __int8)v64 << 8;
    v99 = v105;
    rcDst.rcClip.left = 1;
    v106 = v64 & 0xFF00;
    v11 = 2;
    v100 = v64 & 0xFF00;
    v65 = HIWORD(v64);
    v108 = HIBYTE(v64) << 8;
    v102 = v108;
    v64 = *((_DWORD *)a3 + 6);
    rcDst.dwFlags = 2;
    rcDst.rcClip.top = 3;
    v107 = (unsigned __int8)v65 << 8;
    v101 = v107;
  }
  else
  {
    rcDst.dwFlags = 3;
  }
  v111 = (unsigned __int8)v64 << 8;
  v112 = v64 & 0xFF00;
  v113 = BYTE2(v64) << 8;
  v114 = HIBYTE(v64) << 8;
  GdiGradientFill((HDC)hdc, &pVertex, 4u, &rcDst, v11, v61);
  v58 = 0;
  v12 = 0;
LABEL_85:
  if ( v73 )
    (*(void (__fastcall **)(LPVOID, const unsigned __int16 *, LPVOID))(*(_QWORD *)v73 + 24LL))(v73, v15, Value);
  if ( v58 )
  {
    if ( v12 )
      DeleteObject(v58);
  }
}

```

## disassembly

```asm
0x1804891bc  push    rbp
0x1804891be  push    rbx
0x1804891bf  push    rsi
0x1804891c0  push    rdi
0x1804891c1  push    r12
0x1804891c3  push    r13
0x1804891c5  push    r14
0x1804891c7  push    r15
0x1804891c9  lea     rbp, [rsp-0D8h]
0x1804891d1  sub     rsp, 1D8h
0x1804891d8  mov     rax, cs:__security_cookie
0x1804891df  xor     rax, rsp
0x1804891e2  mov     [rbp+110h+var_50], rax
0x1804891e9  mov     rax, [rbp+110h+arg_30]
0x1804891f0  xor     r14d, r14d
0x1804891f3  movups  xmm0, xmmword ptr [r9]
0x1804891f7  mov     qword ptr [rbp+110h+rcDst.left], rax
0x1804891fb  mov     r13, rcx
0x1804891fe  mov     rax, [rbp+110h+arg_20]
0x180489205  mov     rdi, r8
0x180489208  mov     ecx, cs:?g_dwFontCacheSlot@DirectUI@@3KA; dwTlsIndex
0x18048920e  lea     r15d, [r14+1]
0x180489212  mov     bl, r15b
0x180489215  mov     [rsp+210h+hTheme], r9
0x18048921a  mov     r12, rdx
0x18048921d  mov     [rbp+110h+lprcSrc1], rax
0x180489221  mov     [rsp+210h+var_1A8], r14
0x180489226  mov     sil, 0FFh
0x180489229  movdqu  xmmword ptr [rbp+110h+rcSrc2.left], xmm0
0x18048922e  mov     [rsp+210h+var_1A0], r14d
0x180489233  call    cs:__imp_TlsGetValue
0x18048923a  nop     dword ptr [rax+rax+00h]
0x18048923f  mov     ecx, [rdi]
0x180489241  mov     r8, rax
0x180489244  shl     ecx, 1Ah
0x180489247  sar     ecx, 1Ah
0x18048924a  mov     [rbp+110h+var_188], rax
0x18048924e  sub     ecx, r15d
0x180489251  jz      loc_180489A7C
0x180489257  sub     ecx, 8
0x18048925a  jz      loc_180489760
0x180489260  lea     ebx, [r14+2]
0x180489264  cmp     ecx, ebx
0x180489266  jnz     short loc_180489289
0x180489268  mov     r14, [rdi+8]
0x18048926c  mov     al, [r14+14h]
0x180489270  and     al, 7
0x180489272  jz      loc_180489327
0x180489278  cmp     al, bl
0x18048927a  jz      short loc_1804892EC
0x18048927c  cmp     al, 4
0x18048927e  jz      loc_180489327
0x180489284  mov     r14, [rsp+210h+var_1A8]
0x180489289  mov     bl, r15b
0x18048928c  mov     edi, r14d
0x18048928f  mov     rdx, [rbp+110h+lprcSrc1]; lprcSrc1
0x180489293  lea     r8, [rbp+110h+rcSrc2]; lprcSrc2
0x180489297  xorps   xmm0, xmm0
0x18048929a  lea     rcx, [rbp+110h+rcDst]; lprcDst
0x18048929e  movups  xmmword ptr [rbp+110h+rcDst.left], xmm0
0x1804892a2  call    cs:__imp_IntersectRect
0x1804892a9  nop     dword ptr [rax+rax+00h]
0x1804892ae  lea     rcx, [rbp+110h+rcDst]; lprc
0x1804892b2  call    cs:__imp_IsRectEmpty
0x1804892b9  nop     dword ptr [rax+rax+00h]
0x1804892be  xor     ecx, ecx
0x1804892c0  test    eax, eax
0x1804892c2  jnz     loc_180489B32
0x1804892c8  cmp     [r13+97h], cl
0x1804892cf  jge     loc_180489AC2
0x1804892d5  mov     r9b, sil; unsigned int
0x1804892d8  lea     rdx, [rbp+110h+rcDst]; HDC
0x1804892dc  mov     r8d, edi; struct tagRECT *
0x1804892df  mov     rcx, r12; hdc
0x1804892e2  call    ?_FillWithAlpha@DirectUI@@YAXPEAUHDC__@@AEAUtagRECT@@KE@Z; DirectUI::_FillWithAlpha(HDC__ *,tagRECT &,ulong,uchar)
0x1804892e7  jmp     loc_180489B32
0x1804892ec  mov     edx, [r13+98h]
0x1804892f3  mov     rcx, rdi; this
0x1804892f6  movss   xmm2, cs:__real@3f800000; float
0x1804892fe  shr     edx, 6
0x180489301  and     dl, r15b; bool
0x180489304  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x180489309  lea     r8, [rbp+110h+rcSrc2]; lprect
0x18048930d  mov     rdx, rax; hmf
0x180489310  mov     rcx, r12; hdc
0x180489313  call    cs:__imp_PlayEnhMetaFile
0x18048931a  nop     dword ptr [rax+rax+00h]
0x18048931f  mov     bl, r15b
0x180489322  jmp     loc_180489B32
0x180489327  movzx   ecx, byte ptr [r14+14h]
0x18048932c  shr     ecx, 3
0x18048932f  and     ecx, 0Fh
0x180489332  sub     ecx, r15d
0x180489335  jz      loc_1804896E1
0x18048933b  sub     ecx, 3
0x18048933e  jz      loc_1804895C1
0x180489344  sub     ecx, r15d
0x180489347  jz      short loc_18048935C
0x180489349  sub     ecx, r15d
0x18048934c  jz      short loc_18048935C
0x18048934e  sub     ecx, r15d
0x180489351  jz      short loc_18048935C
0x180489353  cmp     ecx, r15d
0x180489356  jnz     loc_18048970E
0x18048935c  xor     edx, edx; Val
0x18048935e  lea     rcx, [rbp+110h+var_180]; void *
0x180489362  mov     r8d, 0C0h; Size
0x180489368  call    memset_0
0x18048936d  mov     edx, 3; mode
0x180489372  mov     rcx, r12; hdc
0x180489375  call    cs:__imp_SetStretchBltMode
0x18048937c  nop     dword ptr [rax+rax+00h]
0x180489381  mov     edx, [r13+98h]
0x180489388  mov     rcx, rdi; this
0x18048938b  movss   xmm2, cs:__real@3f800000; float
0x180489393  mov     esi, eax
0x180489395  shr     edx, 6
0x180489398  and     dl, r15b; bool
0x18048939b  mov     [rbp+110h+var_180], 0C0h
0x1804893a2  mov     [rbp+110h+var_178], r12
0x1804893a6  mov     [rbp+110h+var_160], r15d
0x1804893aa  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x1804893af  movzx   r9d, word ptr [r14+10h]; xRight
0x1804893b4  lea     rcx, [rbp+110h+rc]; lprc
0x1804893b8  mov     [rbp+110h+var_158], rax
0x1804893bc  xor     r8d, r8d; yTop
0x1804893bf  movzx   eax, word ptr [r14+12h]
0x1804893c4  xor     edx, edx; xLeft
0x1804893c6  mov     [rsp+210h+yBottom], eax; yBottom
0x1804893ca  call    cs:__imp_SetRect
0x1804893d1  nop     dword ptr [rax+rax+00h]
0x1804893d6  mov     rcx, [rsp+210h+hTheme]
0x1804893db  mov     rdi, qword ptr [rbp+110h+rcDst.left]
0x1804893df  mov     eax, [rcx+0Ch]
0x1804893e2  mov     r9d, [rcx+8]
0x1804893e6  mov     r8d, [rcx+4]
0x1804893ea  mov     edx, [rcx]
0x1804893ec  lea     rcx, [rbp+110h+rcSrc]; lprc
0x1804893f0  add     eax, [rdi+0Ch]
0x1804893f3  add     r9d, [rdi+8]; xRight
0x1804893f7  sub     r8d, [rdi+4]; yTop
0x1804893fb  sub     edx, [rdi]; xLeft
0x1804893fd  mov     [rsp+210h+yBottom], eax; yBottom
0x180489401  call    cs:__imp_SetRect
0x180489408  nop     dword ptr [rax+rax+00h]
0x18048940d  lea     rdx, [rbp+110h+rcSrc]; lprcSrc
0x180489411  lea     rcx, [rbp+110h+var_170]; lprcDst
0x180489415  call    cs:__imp_CopyRect
0x18048941c  nop     dword ptr [rax+rax+00h]
0x180489421  mov     al, [r14+14h]
0x180489425  mov     ecx, [rdi]
0x180489427  and     al, 78h
0x180489429  mov     edx, [rdi+8]
0x18048942c  mov     r8d, [rdi+4]
0x180489430  mov     r9d, [rdi+0Ch]
0x180489434  mov     [rbp+110h+var_120], ecx
0x180489437  mov     [rbp+110h+var_11C], edx
0x18048943a  mov     [rbp+110h+var_118], r8d
0x18048943e  mov     [rbp+110h+var_114], r9d
0x180489442  cmp     al, 40h ; '@'
0x180489444  jnz     loc_180489534
0x18048944a  mov     rcx, r13; this
0x18048944d  call    ?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x180489452  mov     edx, eax; struct DirectUI::Element *
0x180489454  mov     rcx, r13; this
0x180489457  call    ?MapAlign@DirectUI@@YAHPEAVElement@1@H@Z; DirectUI::MapAlign(DirectUI::Element *,int)
0x18048945c  mov     r10, [rbp+110h+arg_28]
0x180489463  mov     ecx, eax
0x180489465  mov     r9d, eax
0x180489468  and     ecx, 3
0x18048946b  jz      short loc_1804894B3
0x18048946d  sub     ecx, r15d
0x180489470  jz      short loc_18048948C
0x180489472  cmp     ecx, r15d
0x180489475  jnz     short loc_1804894CB
0x180489477  movzx   eax, word ptr [r14+10h]
0x18048947c  mov     ecx, [rbp+110h+rcSrc.right]
0x18048947f  mov     edx, [r10+8]
0x180489483  sub     ecx, eax
0x180489485  sub     ecx, edx
0x180489487  sub     ecx, [rbp+110h+rcSrc.left]
0x18048948a  jmp     short loc_1804894C5
0x18048948c  mov     r8d, [rbp+110h+rcSrc.right]
0x180489490  mov     eax, r8d
0x180489493  movzx   ecx, word ptr [r14+10h]
0x180489498  sub     eax, ecx
0x18048949a  sub     eax, [rbp+110h+rcSrc.left]
0x18048949d  cdq
0x18048949e  idiv    ebx
0x1804894a0  sub     r8d, eax
0x1804894a3  mov     [rbp+110h+var_130], eax
0x1804894a6  sub     r8d, ecx
0x1804894a9  sub     r8d, [rbp+110h+rcSrc.left]
0x1804894ad  mov     [rbp+110h+var_12C], r8d
0x1804894b1  jmp     short loc_1804894CB
0x1804894b3  movzx   eax, word ptr [r14+10h]
0x1804894b8  mov     edx, [rbp+110h+rcSrc.right]
0x1804894bb  mov     ecx, [r10]
0x1804894be  sub     edx, eax
0x1804894c0  sub     edx, ecx
0x1804894c2  sub     edx, [rbp+110h+rcSrc.left]
0x1804894c5  mov     [rbp+110h+var_12C], edx
0x1804894c8  mov     [rbp+110h+var_130], ecx
0x1804894cb  and     r9d, 0Ch
0x1804894cf  jz      short loc_180489519
0x1804894d1  cmp     r9d, 4
0x1804894d5  jz      short loc_1804894F2
0x1804894d7  cmp     r9d, 8
0x1804894db  jnz     short loc_180489542
0x1804894dd  movzx   eax, word ptr [r14+12h]
0x1804894e2  mov     ecx, [rbp+110h+rcSrc.bottom]
0x1804894e5  mov     edx, [r10+0Ch]
0x1804894e9  sub     ecx, eax
0x1804894eb  sub     ecx, edx
0x1804894ed  sub     ecx, [rbp+110h+rcSrc.top]
0x1804894f0  jmp     short loc_18048952C
0x1804894f2  mov     r8d, [rbp+110h+rcSrc.bottom]
0x1804894f6  mov     eax, r8d
0x1804894f9  movzx   ecx, word ptr [r14+12h]
0x1804894fe  sub     eax, ecx
0x180489500  sub     eax, [rbp+110h+rcSrc.top]
0x180489503  cdq
0x180489504  idiv    ebx
0x180489506  sub     r8d, eax
0x180489509  mov     [rbp+110h+var_128], eax
0x18048950c  sub     r8d, ecx
0x18048950f  sub     r8d, [rbp+110h+rcSrc.top]
0x180489513  mov     [rbp+110h+var_124], r8d
0x180489517  jmp     short loc_180489542
0x180489519  movzx   eax, word ptr [r14+12h]
0x18048951e  mov     edx, [rbp+110h+rcSrc.bottom]
0x180489521  mov     ecx, [r10+4]
0x180489525  sub     edx, eax
0x180489527  sub     edx, ecx
0x180489529  sub     edx, [rbp+110h+rcSrc.top]
0x18048952c  mov     [rbp+110h+var_128], ecx
0x18048952f  mov     [rbp+110h+var_124], edx
0x180489532  jmp     short loc_180489542
0x180489534  mov     [rbp+110h+var_130], ecx
0x180489537  mov     [rbp+110h+var_12C], edx
0x18048953a  mov     [rbp+110h+var_128], r8d
0x18048953e  mov     [rbp+110h+var_124], r9d
0x180489542  mov     al, [r14+14h]
0x180489546  and     al, 78h
0x180489548  cmp     al, 30h ; '0'
0x18048954a  jnz     short loc_18048956D
0x18048954c  movzx   ecx, byte ptr [r14+17h]
0x180489551  movzx   eax, byte ptr [r14+18h]
0x180489556  shl     eax, 10h
0x180489559  shl     ecx, 8
0x18048955c  or      ecx, eax
0x18048955e  mov     [rbp+110h+var_108], ebx
0x180489561  movzx   eax, byte ptr [r14+16h]
0x180489566  or      ecx, eax
0x180489568  mov     [rbp+110h+var_E8], ecx
0x18048956b  jmp     short loc_1804895A2
0x18048956d  cmp     al, 38h ; '8'
0x18048956f  jnz     short loc_1804895A2
0x180489571  movzx   ecx, byte ptr [r14+16h]
0x180489576  mov     eax, 80808081h
0x18048957b  imul    ecx, [r13+88h]
0x180489583  mov     [rbp+110h+var_108], r15d
0x180489587  mov     [rbp+110h+var_E4], 0
0x18048958d  mov     [rbp+110h+var_E1], r15b
0x180489591  imul    ecx
0x180489593  add     edx, ecx
0x180489595  sar     edx, 7
0x180489598  mov     eax, edx
0x18048959a  shr     eax, 1Fh
0x18048959d  add     edx, eax; struct DirectUI::NGINFO *
0x18048959f  mov     [rbp+110h+var_E2], dl
0x1804895a2  lea     rcx, [rbp+110h+var_180]; this
0x1804895a6  call    ?DrawNineGrid@DirectUI@@YAJPEAUNGINFO@1@@Z; DirectUI::DrawNineGrid(DirectUI::NGINFO *)
0x1804895ab  mov     edx, esi; mode
0x1804895ad  mov     rcx, r12; hdc
0x1804895b0  call    cs:__imp_SetStretchBltMode
0x1804895b7  nop     dword ptr [rax+rax+00h]
0x1804895bc  jmp     loc_18048931F
0x1804895c1  mov     r9, [rbp+110h+lprcSrc1]; struct tagRECT *
0x1804895c5  lea     rcx, [rbp+110h+rcDst]; this
0x1804895c9  mov     r8, [rsp+210h+hTheme]; struct tagRECT *
0x1804895ce  mov     rdx, r12; HDC
0x1804895d1  call    ??0AutoClipRect@DirectUI@@QEAA@PEAUHDC__@@PEBUtagRECT@@1@Z; DirectUI::AutoClipRect::AutoClipRect(HDC__ *,tagRECT const *,tagRECT const *)
0x1804895d6  mov     edx, [r13+98h]
0x1804895dd  mov     rcx, rdi; this
0x1804895e0  movss   xmm2, cs:__real@3f800000; float
0x1804895e8  shr     edx, 6
0x1804895eb  and     dl, r15b; bool
0x1804895ee  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x1804895f3  mov     rcx, r12; hdc
0x1804895f6  mov     rbx, rax
0x1804895f9  call    cs:__imp_CreateCompatibleDC
0x180489600  nop     dword ptr [rax+rax+00h]
0x180489605  mov     rcx, rax; hdc
0x180489608  mov     rdx, rbx; h
0x18048960b  mov     rsi, rax
0x18048960e  call    cs:__imp_SelectObject
0x180489615  nop     dword ptr [rax+rax+00h]
0x18048961a  mov     edx, 4; mode
0x18048961f  mov     rcx, r12; hdc
  ... truncated ...
```
