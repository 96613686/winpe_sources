# DirectUI::Element::PaintBackground(HDC__ *,DirectUI::Value *,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)

- ea: `0x18044dec4`
- end: `0x18044e807`
- name: `?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z`
- size: `2371`
- prototype: `void __usercall(DirectUI::Element *__hidden this@<rcx>, HDC hdc@<rdx>, struct DirectUI::Value *@<r8>, const struct tagRECT *@<r9>, const struct tagRECT *, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18044dc90`
- `0x18049d780`

## callees

- `0x1800baf06`
- `0x180317de4`
- `0x18044bf54`
- `0x18044cc24`
- `0x18044ccb0`
- `0x18044d050`
- `0x18044dabc`
- `0x18044dbac`
- `0x18044dc4c`
- `0x18044dec4`
- `0x18044fbd8`
- `0x180451380`
- `0x180459988`
- `0x180459a54`
- `0x18048f118`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18044df3b`
- `KERNEL32!TlsGetValue` at `0x18044df3b`
- `GDI32!CreateSolidBrush` at `0x18044e528`
- `GDI32!CreateSolidBrush` at `0x18044e528`
- `GDI32!GdiGradientFill` at `0x18044e6f9`
- `GDI32!GdiGradientFill` at `0x18044e6f9`
- `GDI32!PlayEnhMetaFile` at `0x18044e009`
- `GDI32!PlayEnhMetaFile` at `0x18044e009`
- `GDI32!SetStretchBltMode` at `0x18044e065`
- `GDI32!SetStretchBltMode` at `0x18044e288`
- `GDI32!SetStretchBltMode` at `0x18044e2eb`
- `GDI32!SetStretchBltMode` at `0x18044e34a`
- `GDI32!SetStretchBltMode` at `0x18044e065`
- `GDI32!SetStretchBltMode` at `0x18044e288`
- `GDI32!SetStretchBltMode` at `0x18044e2eb`
- `GDI32!SetStretchBltMode` at `0x18044e34a`
- `GDI32!StretchBlt` at `0x18044e33f`
- `GDI32!StretchBlt` at `0x18044e33f`
- `GDI32!DeleteObject` at `0x18044e7de`
- `GDI32!DeleteObject` at `0x18044e7de`
- `GDI32!SelectObject` at `0x18044e2da`
- `GDI32!SelectObject` at `0x18044e356`
- `GDI32!SelectObject` at `0x18044e2da`
- `GDI32!SelectObject` at `0x18044e356`
- `GDI32!DeleteDC` at `0x18044e35f`
- `GDI32!DeleteDC` at `0x18044e35f`
- `GDI32!CreateCompatibleDC` at `0x18044e2cb`
- `GDI32!CreateCompatibleDC` at `0x18044e2cb`
- `USER32!IntersectRect` at `0x18044dfa4`
- `USER32!IntersectRect` at `0x18044dfa4`
- `USER32!IsRectEmpty` at `0x18044dfae`
- `USER32!IsRectEmpty` at `0x18044dfae`
- `USER32!FillRect` at `0x18044e77a`
- `USER32!FillRect` at `0x18044e77a`
- `USER32!SetRect` at `0x18044e0b4`
- `USER32!SetRect` at `0x18044e0e5`
- `USER32!SetRect` at `0x18044e0b4`
- `USER32!SetRect` at `0x18044e0e5`
- `USER32!CopyRect` at `0x18044e0f3`
- `USER32!CopyRect` at `0x18044e0f3`
- `USER32!DrawFrameControl` at `0x18044e4ee`
- `USER32!DrawFrameControl` at `0x18044e4ee`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18044e4cf`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18044e4cf`

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
0x18044dec4  push    rbp
0x18044dec6  push    rbx
0x18044dec7  push    rsi
0x18044dec8  push    rdi
0x18044dec9  push    r12
0x18044decb  push    r13
0x18044decd  push    r14
0x18044decf  push    r15
0x18044ded1  lea     rbp, [rsp-0D8h]
0x18044ded9  sub     rsp, 1D8h
0x18044dee0  mov     rax, cs:__security_cookie
0x18044dee7  xor     rax, rsp
0x18044deea  mov     [rbp+110h+var_50], rax
0x18044def1  mov     rax, [rbp+110h+arg_30]
0x18044def8  xor     r14d, r14d
0x18044defb  movups  xmm0, xmmword ptr [r9]
0x18044deff  mov     qword ptr [rbp+110h+rcDst.left], rax
0x18044df03  mov     r13, rcx
0x18044df06  mov     rax, [rbp+110h+arg_20]
0x18044df0d  mov     rdi, r8
0x18044df10  mov     ecx, cs:?g_dwFontCacheSlot@DirectUI@@3KA; dwTlsIndex
0x18044df16  lea     r15d, [r14+1]
0x18044df1a  mov     bl, r15b
0x18044df1d  mov     [rsp+210h+hTheme], r9
0x18044df22  mov     r12, rdx
0x18044df25  mov     [rbp+110h+lprcSrc1], rax
0x18044df29  mov     [rsp+210h+var_1A8], r14
0x18044df2e  mov     sil, 0FFh
0x18044df31  movdqu  xmmword ptr [rbp+110h+rcSrc2.left], xmm0
0x18044df36  mov     [rsp+210h+var_1A0], r14d
0x18044df3b  call    cs:__imp_TlsGetValue
0x18044df41  mov     ecx, [rdi]
0x18044df43  mov     r8, rax
0x18044df46  shl     ecx, 1Ah
0x18044df49  sar     ecx, 1Ah
0x18044df4c  mov     [rbp+110h+var_188], rax
0x18044df50  sub     ecx, r15d
0x18044df53  jz      loc_18044E708
0x18044df59  sub     ecx, 8
0x18044df5c  jz      loc_18044E408
0x18044df62  lea     ebx, [r14+2]
0x18044df66  cmp     ecx, ebx
0x18044df68  jnz     short loc_18044DF8B
0x18044df6a  mov     r14, [rdi+8]
0x18044df6e  mov     al, [r14+14h]
0x18044df72  and     al, 7
0x18044df74  jz      loc_18044E017
0x18044df7a  cmp     al, bl
0x18044df7c  jz      short loc_18044DFE2
0x18044df7e  cmp     al, 4
0x18044df80  jz      loc_18044E017
0x18044df86  mov     r14, [rsp+210h+var_1A8]
0x18044df8b  mov     bl, r15b
0x18044df8e  mov     edi, r14d
0x18044df91  mov     rdx, [rbp+110h+lprcSrc1]; lprcSrc1
0x18044df95  lea     r8, [rbp+110h+rcSrc2]; lprcSrc2
0x18044df99  xorps   xmm0, xmm0
0x18044df9c  lea     rcx, [rbp+110h+rcDst]; lprcDst
0x18044dfa0  movups  xmmword ptr [rbp+110h+rcDst.left], xmm0
0x18044dfa4  call    cs:__imp_IntersectRect
0x18044dfaa  lea     rcx, [rbp+110h+rcDst]; lprc
0x18044dfae  call    cs:__imp_IsRectEmpty
0x18044dfb4  xor     ecx, ecx
0x18044dfb6  test    eax, eax
0x18044dfb8  jnz     loc_18044E7B8
0x18044dfbe  cmp     [r13+97h], cl
0x18044dfc5  jge     loc_18044E74E
0x18044dfcb  mov     r9b, sil; unsigned int
0x18044dfce  lea     rdx, [rbp+110h+rcDst]; HDC
0x18044dfd2  mov     r8d, edi; struct tagRECT *
0x18044dfd5  mov     rcx, r12; hdc
0x18044dfd8  call    ?_FillWithAlpha@DirectUI@@YAXPEAUHDC__@@AEAUtagRECT@@KE@Z; DirectUI::_FillWithAlpha(HDC__ *,tagRECT &,ulong,uchar)
0x18044dfdd  jmp     loc_18044E7B8
0x18044dfe2  mov     edx, [r13+98h]
0x18044dfe9  mov     rcx, rdi; this
0x18044dfec  movss   xmm2, cs:__real@3f800000; float
0x18044dff4  shr     edx, 6
0x18044dff7  and     dl, r15b; bool
0x18044dffa  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18044dfff  lea     r8, [rbp+110h+rcSrc2]; lprect
0x18044e003  mov     rdx, rax; hmf
0x18044e006  mov     rcx, r12; hdc
0x18044e009  call    cs:__imp_PlayEnhMetaFile
0x18044e00f  mov     bl, r15b
0x18044e012  jmp     loc_18044E7B8
0x18044e017  movzx   ecx, byte ptr [r14+14h]
0x18044e01c  shr     ecx, 3
0x18044e01f  and     ecx, 0Fh
0x18044e022  sub     ecx, r15d
0x18044e025  jz      loc_18044E389
0x18044e02b  sub     ecx, 3
0x18044e02e  jz      loc_18044E293
0x18044e034  sub     ecx, r15d
0x18044e037  jz      short loc_18044E04C
0x18044e039  sub     ecx, r15d
0x18044e03c  jz      short loc_18044E04C
0x18044e03e  sub     ecx, r15d
0x18044e041  jz      short loc_18044E04C
0x18044e043  cmp     ecx, r15d
0x18044e046  jnz     loc_18044E3B6
0x18044e04c  xor     edx, edx; Val
0x18044e04e  lea     rcx, [rbp+110h+var_180]; void *
0x18044e052  mov     r8d, 0C0h; Size
0x18044e058  call    memset_0
0x18044e05d  mov     edx, 3; mode
0x18044e062  mov     rcx, r12; hdc
0x18044e065  call    cs:__imp_SetStretchBltMode
0x18044e06b  mov     edx, [r13+98h]
0x18044e072  mov     rcx, rdi; this
0x18044e075  movss   xmm2, cs:__real@3f800000; float
0x18044e07d  mov     esi, eax
0x18044e07f  shr     edx, 6
0x18044e082  and     dl, r15b; bool
0x18044e085  mov     [rbp+110h+var_180], 0C0h
0x18044e08c  mov     [rbp+110h+var_178], r12
0x18044e090  mov     [rbp+110h+var_160], r15d
0x18044e094  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18044e099  movzx   r9d, word ptr [r14+10h]; xRight
0x18044e09e  lea     rcx, [rbp+110h+rc]; lprc
0x18044e0a2  mov     [rbp+110h+var_158], rax
0x18044e0a6  xor     r8d, r8d; yTop
0x18044e0a9  movzx   eax, word ptr [r14+12h]
0x18044e0ae  xor     edx, edx; xLeft
0x18044e0b0  mov     [rsp+210h+yBottom], eax; yBottom
0x18044e0b4  call    cs:__imp_SetRect
0x18044e0ba  mov     rcx, [rsp+210h+hTheme]
0x18044e0bf  mov     rdi, qword ptr [rbp+110h+rcDst.left]
0x18044e0c3  mov     eax, [rcx+0Ch]
0x18044e0c6  mov     r9d, [rcx+8]
0x18044e0ca  mov     r8d, [rcx+4]
0x18044e0ce  mov     edx, [rcx]
0x18044e0d0  lea     rcx, [rbp+110h+rcSrc]; lprc
0x18044e0d4  add     eax, [rdi+0Ch]
0x18044e0d7  add     r9d, [rdi+8]; xRight
0x18044e0db  sub     r8d, [rdi+4]; yTop
0x18044e0df  sub     edx, [rdi]; xLeft
0x18044e0e1  mov     [rsp+210h+yBottom], eax; yBottom
0x18044e0e5  call    cs:__imp_SetRect
0x18044e0eb  lea     rdx, [rbp+110h+rcSrc]; lprcSrc
0x18044e0ef  lea     rcx, [rbp+110h+var_170]; lprcDst
0x18044e0f3  call    cs:__imp_CopyRect
0x18044e0f9  mov     al, [r14+14h]
0x18044e0fd  mov     ecx, [rdi]
0x18044e0ff  and     al, 78h
0x18044e101  mov     edx, [rdi+8]
0x18044e104  mov     r8d, [rdi+4]
0x18044e108  mov     r9d, [rdi+0Ch]
0x18044e10c  mov     [rbp+110h+var_120], ecx
0x18044e10f  mov     [rbp+110h+var_11C], edx
0x18044e112  mov     [rbp+110h+var_118], r8d
0x18044e116  mov     [rbp+110h+var_114], r9d
0x18044e11a  cmp     al, 40h ; '@'
0x18044e11c  jnz     loc_18044E20C
0x18044e122  mov     rcx, r13; this
0x18044e125  call    ?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x18044e12a  mov     edx, eax; struct DirectUI::Element *
0x18044e12c  mov     rcx, r13; this
0x18044e12f  call    ?MapAlign@DirectUI@@YAHPEAVElement@1@H@Z; DirectUI::MapAlign(DirectUI::Element *,int)
0x18044e134  mov     r10, [rbp+110h+arg_28]
0x18044e13b  mov     ecx, eax
0x18044e13d  mov     r9d, eax
0x18044e140  and     ecx, 3
0x18044e143  jz      short loc_18044E18B
0x18044e145  sub     ecx, r15d
0x18044e148  jz      short loc_18044E164
0x18044e14a  cmp     ecx, r15d
0x18044e14d  jnz     short loc_18044E1A3
0x18044e14f  movzx   eax, word ptr [r14+10h]
0x18044e154  mov     ecx, [rbp+110h+rcSrc.right]
0x18044e157  mov     edx, [r10+8]
0x18044e15b  sub     ecx, eax
0x18044e15d  sub     ecx, edx
0x18044e15f  sub     ecx, [rbp+110h+rcSrc.left]
0x18044e162  jmp     short loc_18044E19D
0x18044e164  mov     r8d, [rbp+110h+rcSrc.right]
0x18044e168  mov     eax, r8d
0x18044e16b  movzx   ecx, word ptr [r14+10h]
0x18044e170  sub     eax, ecx
0x18044e172  sub     eax, [rbp+110h+rcSrc.left]
0x18044e175  cdq
0x18044e176  idiv    ebx
0x18044e178  sub     r8d, eax
0x18044e17b  mov     [rbp+110h+var_130], eax
0x18044e17e  sub     r8d, ecx
0x18044e181  sub     r8d, [rbp+110h+rcSrc.left]
0x18044e185  mov     [rbp+110h+var_12C], r8d
0x18044e189  jmp     short loc_18044E1A3
0x18044e18b  movzx   eax, word ptr [r14+10h]
0x18044e190  mov     edx, [rbp+110h+rcSrc.right]
0x18044e193  mov     ecx, [r10]
0x18044e196  sub     edx, eax
0x18044e198  sub     edx, ecx
0x18044e19a  sub     edx, [rbp+110h+rcSrc.left]
0x18044e19d  mov     [rbp+110h+var_12C], edx
0x18044e1a0  mov     [rbp+110h+var_130], ecx
0x18044e1a3  and     r9d, 0Ch
0x18044e1a7  jz      short loc_18044E1F1
0x18044e1a9  cmp     r9d, 4
0x18044e1ad  jz      short loc_18044E1CA
0x18044e1af  cmp     r9d, 8
0x18044e1b3  jnz     short loc_18044E21A
0x18044e1b5  movzx   eax, word ptr [r14+12h]
0x18044e1ba  mov     ecx, [rbp+110h+rcSrc.bottom]
0x18044e1bd  mov     edx, [r10+0Ch]
0x18044e1c1  sub     ecx, eax
0x18044e1c3  sub     ecx, edx
0x18044e1c5  sub     ecx, [rbp+110h+rcSrc.top]
0x18044e1c8  jmp     short loc_18044E204
0x18044e1ca  mov     r8d, [rbp+110h+rcSrc.bottom]
0x18044e1ce  mov     eax, r8d
0x18044e1d1  movzx   ecx, word ptr [r14+12h]
0x18044e1d6  sub     eax, ecx
0x18044e1d8  sub     eax, [rbp+110h+rcSrc.top]
0x18044e1db  cdq
0x18044e1dc  idiv    ebx
0x18044e1de  sub     r8d, eax
0x18044e1e1  mov     [rbp+110h+var_128], eax
0x18044e1e4  sub     r8d, ecx
0x18044e1e7  sub     r8d, [rbp+110h+rcSrc.top]
0x18044e1eb  mov     [rbp+110h+var_124], r8d
0x18044e1ef  jmp     short loc_18044E21A
0x18044e1f1  movzx   eax, word ptr [r14+12h]
0x18044e1f6  mov     edx, [rbp+110h+rcSrc.bottom]
0x18044e1f9  mov     ecx, [r10+4]
0x18044e1fd  sub     edx, eax
0x18044e1ff  sub     edx, ecx
0x18044e201  sub     edx, [rbp+110h+rcSrc.top]
0x18044e204  mov     [rbp+110h+var_128], ecx
0x18044e207  mov     [rbp+110h+var_124], edx
0x18044e20a  jmp     short loc_18044E21A
0x18044e20c  mov     [rbp+110h+var_130], ecx
0x18044e20f  mov     [rbp+110h+var_12C], edx
0x18044e212  mov     [rbp+110h+var_128], r8d
0x18044e216  mov     [rbp+110h+var_124], r9d
0x18044e21a  mov     al, [r14+14h]
0x18044e21e  and     al, 78h
0x18044e220  cmp     al, 30h ; '0'
0x18044e222  jnz     short loc_18044E245
0x18044e224  movzx   ecx, byte ptr [r14+17h]
0x18044e229  movzx   eax, byte ptr [r14+18h]
0x18044e22e  shl     eax, 10h
0x18044e231  shl     ecx, 8
0x18044e234  or      ecx, eax
0x18044e236  mov     [rbp+110h+var_108], ebx
0x18044e239  movzx   eax, byte ptr [r14+16h]
0x18044e23e  or      ecx, eax
0x18044e240  mov     [rbp+110h+var_E8], ecx
0x18044e243  jmp     short loc_18044E27A
0x18044e245  cmp     al, 38h ; '8'
0x18044e247  jnz     short loc_18044E27A
0x18044e249  movzx   ecx, byte ptr [r14+16h]
0x18044e24e  mov     eax, 80808081h
0x18044e253  imul    ecx, [r13+88h]
0x18044e25b  mov     [rbp+110h+var_108], r15d
0x18044e25f  mov     [rbp+110h+var_E4], 0
0x18044e265  mov     [rbp+110h+var_E1], r15b
0x18044e269  imul    ecx
0x18044e26b  add     edx, ecx
0x18044e26d  sar     edx, 7
0x18044e270  mov     eax, edx
0x18044e272  shr     eax, 1Fh
0x18044e275  add     edx, eax; struct DirectUI::NGINFO *
0x18044e277  mov     [rbp+110h+var_E2], dl
0x18044e27a  lea     rcx, [rbp+110h+var_180]; this
0x18044e27e  call    ?DrawNineGrid@DirectUI@@YAJPEAUNGINFO@1@@Z; DirectUI::DrawNineGrid(DirectUI::NGINFO *)
0x18044e283  mov     edx, esi; mode
0x18044e285  mov     rcx, r12; hdc
0x18044e288  call    cs:__imp_SetStretchBltMode
0x18044e28e  jmp     loc_18044E00F
0x18044e293  mov     r9, [rbp+110h+lprcSrc1]; struct tagRECT *
0x18044e297  lea     rcx, [rbp+110h+rcDst]; this
0x18044e29b  mov     r8, [rsp+210h+hTheme]; struct tagRECT *
0x18044e2a0  mov     rdx, r12; HDC
0x18044e2a3  call    ??0AutoClipRect@DirectUI@@QEAA@PEAUHDC__@@PEBUtagRECT@@1@Z; DirectUI::AutoClipRect::AutoClipRect(HDC__ *,tagRECT const *,tagRECT const *)
0x18044e2a8  mov     edx, [r13+98h]
0x18044e2af  mov     rcx, rdi; this
0x18044e2b2  movss   xmm2, cs:__real@3f800000; float
0x18044e2ba  shr     edx, 6
0x18044e2bd  and     dl, r15b; bool
0x18044e2c0  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18044e2c5  mov     rcx, r12; hdc
0x18044e2c8  mov     rbx, rax
0x18044e2cb  call    cs:__imp_CreateCompatibleDC
0x18044e2d1  mov     rcx, rax; hdc
0x18044e2d4  mov     rdx, rbx; h
0x18044e2d7  mov     rsi, rax
0x18044e2da  call    cs:__imp_SelectObject
0x18044e2e0  mov     edx, 4; mode
0x18044e2e5  mov     rcx, r12; hdc
0x18044e2e8  mov     rdi, rax
0x18044e2eb  call    cs:__imp_SetStretchBltMode
0x18044e2f1  movzx   ecx, word ptr [r14+10h]
0x18044e2f6  mov     ebx, eax
0x18044e2f8  movzx   eax, word ptr [r14+12h]
0x18044e2fd  mov     r10d, [rbp+110h+rcSrc2.bottom]
0x18044e301  mov     r8d, [rbp+110h+rcSrc2.top]; yDest
0x18044e305  sub     r10d, r8d
0x18044e308  mov     r9d, [rbp+110h+rcSrc2.right]
0x18044e30c  mov     edx, [rbp+110h+rcSrc2.left]; xDest
0x18044e30f  sub     r9d, edx; wDest
  ... truncated ...
```
