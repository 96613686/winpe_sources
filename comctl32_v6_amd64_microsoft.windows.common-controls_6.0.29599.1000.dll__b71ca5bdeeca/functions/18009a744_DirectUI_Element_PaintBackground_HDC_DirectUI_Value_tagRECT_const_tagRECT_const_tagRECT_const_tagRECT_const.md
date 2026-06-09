# DirectUI::Element::PaintBackground(HDC__ *,DirectUI::Value *,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)

- ea: `0x18009a744`
- end: `0x18009b0a7`
- name: `?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z`
- size: `2403`
- prototype: `void __usercall(DirectUI::Element *__hidden this@<rcx>, HDC@<rdx>, struct DirectUI::Value *@<r8>, const struct tagRECT *@<r9>, const struct tagRECT *, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18009a490`

## callees

- `0x1800999b8`
- `0x1800999e0`
- `0x18009a744`
- `0x18009b9a0`
- `0x1800df104`
- `0x1801047b4`
- `0x180114520`
- `0x180114ebc`
- `0x180165390`
- `0x180169730`
- `0x1801697bc`
- `0x18016995c`
- `0x180169e34`
- `0x18016a86c`
- `0x18018ce98`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009a7b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009a7b9`
- `GDI32!CreateSolidBrush` at `0x18009ad54`
- `GDI32!CreateSolidBrush` at `0x18009ad54`
- `GDI32!DeleteObject` at `0x18009b07e`
- `GDI32!DeleteObject` at `0x18009b07e`
- `GDI32!SelectObject` at `0x18009ab04`
- `GDI32!SelectObject` at `0x18009ab7d`
- `GDI32!SelectObject` at `0x18009ab04`
- `GDI32!SelectObject` at `0x18009ab7d`
- `GDI32!DeleteDC` at `0x18009ab86`
- `GDI32!DeleteDC` at `0x18009ab86`
- `GDI32!CreateCompatibleDC` at `0x18009aaf5`
- `GDI32!CreateCompatibleDC` at `0x18009aaf5`
- `GDI32!GdiGradientFill` at `0x18009af28`
- `GDI32!GdiGradientFill` at `0x18009af28`
- `GDI32!StretchBlt` at `0x18009ab66`
- `GDI32!StretchBlt` at `0x18009ab66`
- `GDI32!SetStretchBltMode` at `0x18009a856`
- `GDI32!SetStretchBltMode` at `0x18009aab2`
- `GDI32!SetStretchBltMode` at `0x18009ab15`
- `GDI32!SetStretchBltMode` at `0x18009ab71`
- `GDI32!SetStretchBltMode` at `0x18009a856`
- `GDI32!SetStretchBltMode` at `0x18009aab2`
- `GDI32!SetStretchBltMode` at `0x18009ab15`
- `GDI32!SetStretchBltMode` at `0x18009ab71`
- `GDI32!PlayEnhMetaFile` at `0x18009a980`
- `GDI32!PlayEnhMetaFile` at `0x18009a980`
- `USER32!FillRect` at `0x18009b018`
- `USER32!FillRect` at `0x18009b018`
- `USER32!CopyRect` at `0x18009a8e4`
- `USER32!CopyRect` at `0x18009a8e4`
- `USER32!IsRectEmpty` at `0x18009afbf`
- `USER32!IsRectEmpty` at `0x18009afbf`
- `USER32!IntersectRect` at `0x18009afb5`
- `USER32!IntersectRect` at `0x18009afb5`
- `USER32!GetSysColorBrush` at `0x18009af4e`
- `USER32!GetSysColorBrush` at `0x18009af4e`
- `USER32!SetRect` at `0x18009a8a5`
- `USER32!SetRect` at `0x18009a8d6`
- `USER32!SetRect` at `0x18009a8a5`
- `USER32!SetRect` at `0x18009a8d6`
- `USER32!DrawFrameControl` at `0x18009ad1a`
- `USER32!DrawFrameControl` at `0x18009ad1a`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18009acfd`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18009acfd`
- `DUser!GetStdColorBrushI` at `0x18009af56`
- `DUser!GetStdColorBrushI` at `0x18009af56`
- `DUser!UtilDrawBlendRect` at `0x18009b051`
- `DUser!UtilDrawBlendRect` at `0x18009b051`

## pseudocode

```c
void __fastcall DirectUI::Element::PaintBackground(
        DirectUI::Element *this,
        HDC a2,
        struct DirectUI::Value *a3,
        struct tagRECT *a4,
        struct tagRECT *a5,
        const struct tagRECT *a6,
        const struct tagRECT *a7)
{
  HBRUSH SolidBrush; // rbx
  RECT v8; // xmm0
  DWORD v11; // r15d
  char v12; // r14
  int v14; // esi
  __int64 v15; // rdx
  LPVOID Value; // r8
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // r14
  char v21; // al
  int v22; // esi
  bool v23; // dl
  void *v24; // rax
  int v25; // r9d
  int *v26; // rdi
  int v27; // ecx
  char v28; // al
  unsigned __int64 v29; // rdx
  int v30; // r8d
  int v31; // r9d
  unsigned int ContentAlign; // eax
  int v33; // r8d
  char v34; // al
  LONG v35; // ecx
  HENHMETAFILE Image; // rax
  int v37; // ecx
  int v38; // r9d
  LONG v39; // ecx
  int v40; // ecx
  char v41; // al
  int v42; // ecx
  int v43; // ecx
  void *v44; // rbx
  HDC CompatibleDC; // rsi
  HGDIOBJ v46; // rdi
  const struct tagRECT *v47; // r8
  __int64 (__fastcall *v48)(LPVOID, void *, struct DirectUI::Value *); // rbx
  void *v49; // rax
  __int64 v50; // rax
  unsigned int v51; // edi
  const unsigned __int16 *v52; // rdx
  int v53; // r9d
  HDC v54; // r8
  bool v55; // zf
  RECT v56; // xmm0
  int v57; // ecx
  char v58; // r9
  ULONG v59; // r11d
  unsigned int v60; // edx
  unsigned int v61; // eax
  unsigned int v62; // edx
  unsigned int v63; // eax
  __int64 v64; // rcx
  HBRUSH StdColorBrushI; // rax
  __int64 v66; // r9
  __int64 v67; // rcx
  unsigned __int8 yBottom; // [rsp+20h] [rbp-E0h]
  const struct tagRECT *hdcSrc; // [rsp+28h] [rbp-D8h]
  HBRUSH v70; // [rsp+68h] [rbp-98h]
  HTHEME hTheme; // [rsp+78h] [rbp-88h] BYREF
  RECT *lprcSrc1; // [rsp+80h] [rbp-80h]
  LPVOID v73; // [rsp+88h] [rbp-78h]
  int v74; // [rsp+90h] [rbp-70h] BYREF
  HDC v75; // [rsp+98h] [rbp-68h]
  struct tagRECT rcDst; // [rsp+A0h] [rbp-60h] BYREF
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
  RECT rect; // [rsp+150h] [rbp+50h] BYREF
  DTBGOPTS pOptions; // [rsp+160h] [rbp+60h] BYREF
  _TRIVERTEX pVertex; // [rsp+180h] [rbp+80h] BYREF
  LONG left; // [rsp+190h] [rbp+90h]
  LONG top; // [rsp+194h] [rbp+94h]
  __int16 v99; // [rsp+198h] [rbp+98h]
  __int16 v100; // [rsp+19Ah] [rbp+9Ah]
  __int16 v101; // [rsp+19Ch] [rbp+9Ch]
  __int16 v102; // [rsp+19Eh] [rbp+9Eh]
  LONG right; // [rsp+1A0h] [rbp+A0h]
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
  *(_QWORD *)&pOptions.dwSize = a7;
  v11 = 1;
  v12 = 1;
  hTheme = a4;
  lprcSrc1 = a5;
  v70 = 0;
  LOBYTE(v14) = -1;
  rect = v8;
  Value = TlsGetValue(DirectUI::g_dwFontCacheSlot);
  v17 = (int)(*(_DWORD *)a3 << 26) >> 26;
  v73 = Value;
  v18 = v17 - 1;
  if ( !v18 )
  {
    v64 = *((unsigned int *)a3 + 2);
    v12 = 0;
    if ( (unsigned int)(v64 - 10000) > 0x270F )
      StdColorBrushI = (HBRUSH)GetStdColorBrushI(v64, v15, Value);
    else
      StdColorBrushI = GetSysColorBrush((int)v64 - 10000);
    SolidBrush = StdColorBrushI;
    v70 = StdColorBrushI;
    v51 = ARGBColorFromEnumI(*((unsigned int *)a3 + 2));
    v14 = (int)(*((_DWORD *)this + 34) * HIBYTE(v51)) / 255;
LABEL_73:
    if ( !(_BYTE)v14 )
      goto LABEL_87;
LABEL_78:
    *(_OWORD *)&pOptions.dwSize = 0;
    IntersectRect((LPRECT)&pOptions, lprcSrc1, &rect);
    if ( !IsRectEmpty((const RECT *)&pOptions) )
    {
      if ( *((char *)this + 151) >= 0 )
      {
        if ( (unsigned __int8)v14 < 0xFAu )
        {
          LOBYTE(v66) = v14;
          UtilDrawBlendRect(a2, &pOptions, SolidBrush, v66, 0, 0);
        }
        else
        {
          if ( (Microsoft_Windows_DUIEnableBits & 1) != 0 )
            McTemplateMofU0(0, &DirectUI_ElementRenderFillRect_Start, &DirectUI_ElementRenderFillRectId);
          FillRect(a2, (const RECT *)&pOptions, SolidBrush);
          if ( (Microsoft_Windows_DUIEnableBits & 1) != 0 )
            McTemplateMofU0(v67, &DirectUI_ElementRenderFillRect_Stop, &DirectUI_ElementRenderFillRectId);
        }
      }
      else
      {
        LOBYTE(v66) = v14;
        DirectUI::_FillWithAlpha(a2, (HDC)&pOptions, (struct tagRECT *)v51, v66, yBottom);
      }
    }
    goto LABEL_87;
  }
  v19 = v18 - 8;
  if ( !v19 )
  {
    if ( *((_BYTE *)a3 + 8) && *((_BYTE *)a3 + 8) != 1 )
    {
      if ( *((_BYTE *)a3 + 8) == 2 )
      {
        v51 = *((_DWORD *)a3 + 4);
        v57 = *((_DWORD *)this + 34) * HIBYTE(v51);
        if ( (unsigned __int8)(v57 / 255) )
        {
          LOBYTE(v14) = v57 / 255;
          SolidBrush = CreateSolidBrush(v51 & 0xFFFFFF);
          v70 = SolidBrush;
          goto LABEL_78;
        }
        goto LABEL_56;
      }
      if ( *((_BYTE *)a3 + 8) != 3 && *((_BYTE *)a3 + 8) != 4 )
      {
        if ( *((_BYTE *)a3 + 8) == 5 )
        {
          DrawFrameControl(a2, &rect, *((_DWORD *)a3 + 4), *((_DWORD *)a3 + 5));
        }
        else
        {
          if ( *((_BYTE *)a3 + 8) != 6 )
          {
LABEL_77:
            v51 = 0;
            goto LABEL_78;
          }
          v52 = (const unsigned __int16 *)*((_QWORD *)a3 + 2);
          hTheme = 0;
          if ( v52 && DirectUI::Element::GetTheme(this, v52, &hTheme) >= 0 )
          {
            v53 = *((_DWORD *)a3 + 7);
            v54 = (HDC)*((unsigned int *)a3 + 6);
            if ( ((unsigned __int64)hTheme & 0xFFFFFFFFFFFF0000uLL) != 0 )
            {
              v55 = (*((_BYTE *)this + 152) & 0x40) == 0;
              pOptions.dwSize = 24;
              if ( !v55 )
                v11 = 33;
              v56 = *lprcSrc1;
              pOptions.dwFlags = v11;
              pOptions.rcClip = v56;
              DrawThemeBackgroundEx(hTheme, a2, (int)v54, v53, &rect, &pOptions);
            }
            else
            {
              DirectUI::EmulateDrawThemeBackground((DirectUI *)hTheme, a2, v54, v53, (int)&rect, hdcSrc);
            }
          }
        }
LABEL_56:
        v12 = 0;
        goto LABEL_88;
      }
    }
    v58 = *((_BYTE *)a3 + 8);
    pVertex.x = rect.left;
    pVertex.y = rect.top;
    left = rect.left;
    top = rect.top;
    right = rect.right;
    bottom = rect.bottom;
    v109 = rect.right;
    v110 = rect.bottom;
    if ( !v58 || v58 == 3 )
    {
      v59 = 0;
      v55 = (*((_BYTE *)this + 152) & 0x40) == 0;
      right = (rect.left + rect.right) / 2;
      left = right;
      if ( !v55 )
      {
        pVertex.x = rect.right;
        v109 = rect.left;
      }
    }
    else
    {
      v59 = 1;
      bottom = (rect.bottom + rect.top) / 2;
      top = bottom;
    }
    v60 = *((_DWORD *)a3 + 4);
    pVertex.Red = (unsigned __int8)v60 << 8;
    pOptions.dwSize = 0;
    pVertex.Green = v60 & 0xFF00;
    v61 = HIWORD(v60);
    pVertex.Alpha = HIBYTE(v60) << 8;
    v62 = *((_DWORD *)a3 + 5);
    pVertex.Blue = (unsigned __int8)v61 << 8;
    if ( (unsigned __int8)(v58 - 3) <= 1u )
    {
      v105 = (unsigned __int8)v62 << 8;
      v99 = v105;
      pOptions.rcClip.left = 1;
      v106 = v62 & 0xFF00;
      v11 = 2;
      v100 = v62 & 0xFF00;
      v63 = HIWORD(v62);
      v108 = HIBYTE(v62) << 8;
      v102 = v108;
      v62 = *((_DWORD *)a3 + 6);
      pOptions.dwFlags = 2;
      pOptions.rcClip.top = 3;
      v107 = (unsigned __int8)v63 << 8;
      v101 = v107;
    }
    else
    {
      pOptions.dwFlags = 3;
    }
    v111 = (unsigned __int8)v62 << 8;
    v112 = v62 & 0xFF00;
    v113 = BYTE2(v62) << 8;
    v114 = HIBYTE(v62) << 8;
    GdiGradientFill(a2, &pVertex, 4u, &pOptions, v11, v59);
    SolidBrush = 0;
    goto LABEL_56;
  }
  if ( v19 != 2 )
  {
LABEL_76:
    SolidBrush = 0;
    goto LABEL_77;
  }
  v20 = *((_QWORD *)a3 + 1);
  v21 = *(_BYTE *)(v20 + 20) & 7;
  if ( v21 )
  {
    if ( v21 == 2 )
    {
      Image = (HENHMETAFILE)DirectUI::Value::GetImage(a3, (*((_DWORD *)this + 38) & 0x40) != 0, 1.0);
      PlayEnhMetaFile(a2, Image, &rect);
LABEL_18:
      v12 = 1;
LABEL_87:
      SolidBrush = v70;
      goto LABEL_88;
    }
    if ( v21 != 4 )
    {
LABEL_75:
      v12 = 1;
      goto LABEL_76;
    }
  }
  if ( ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) == 1 )
  {
    v14 = *((_DWORD *)this + 34) * *(unsigned __int8 *)(v20 + 22) / 255;
    if ( !(_BYTE)v14 )
    {
      v12 = 0;
      goto LABEL_87;
    }
    goto LABEL_40;
  }
  if ( ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) != 4 )
  {
    if ( ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) == 5
      || ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xF) == 6
      || ((*(unsigned __int8 *)(v20 + 20) >> 3) & 0xFu) - 7 <= 1 )
    {
      memset_0(&v74, 0, 0xC0u);
      v22 = SetStretchBltMode(a2, 3);
      v23 = (*((_DWORD *)this + 38) & 0x40) != 0;
      v74 = 192;
      v75 = a2;
      v77 = 1;
      v24 = DirectUI::Value::GetImage(a3, v23, 1.0);
      v25 = *(unsigned __int16 *)(v20 + 16);
      v78 = v24;
      SetRect(&rc, 0, 0, v25, *(unsigned __int16 *)(v20 + 18));
      v26 = *(int **)&pOptions.dwSize;
      SetRect(
        &rcSrc,
        *(_DWORD *)hTheme - **(_DWORD **)&pOptions.dwSize,
        *((_DWORD *)hTheme + 1) - *(_DWORD *)(*(_QWORD *)&pOptions.dwSize + 4LL),
        *(_DWORD *)(*(_QWORD *)&pOptions.dwSize + 8LL) + *((_DWORD *)hTheme + 2),
        *(_DWORD *)(*(_QWORD *)&pOptions.dwSize + 12LL) + *((_DWORD *)hTheme + 3));
      CopyRect(&rcDst, &rcSrc);
      v27 = *v26;
      v28 = *(_BYTE *)(v20 + 20) & 0x78;
      v29 = (unsigned int)v26[2];
      v30 = v26[1];
      v31 = v26[3];
      v85 = *v26;
      v86 = v29;
      v87 = v30;
      v88 = v31;
      if ( v28 != 64 )
      {
        v81 = v27;
        v82 = v29;
        v83 = v30;
        v84 = v31;
        goto LABEL_30;
      }
      ContentAlign = DirectUI::Element::GetContentAlign(this);
      v34 = DirectUI::MapAlign(this, (struct DirectUI::Element *)ContentAlign, v33);
      if ( (v34 & 3) != 0 )
      {
        if ( (v34 & 3) == 1 )
        {
          v37 = *(unsigned __int16 *)(v20 + 16);
          v29 = (unsigned int)((rcSrc.right - v37 - rcSrc.left) >> 31);
          LODWORD(v29) = (rcSrc.right - v37 - rcSrc.left) % 2;
          v81 = (rcSrc.right - v37 - rcSrc.left) / 2;
          v82 = rcSrc.right - v37 - rcSrc.left - v81;
          goto LABEL_22;
        }
        if ( (v34 & 3) != 2 )
          goto LABEL_22;
        v29 = (unsigned int)a6->right;
        v35 = rcSrc.right - *(unsigned __int16 *)(v20 + 16) - v29 - rcSrc.left;
      }
      else
      {
        v35 = a6->left;
        v29 = rcSrc.right - (unsigned int)*(unsigned __int16 *)(v20 + 16) - a6->left - rcSrc.left;
      }
      v82 = v29;
      v81 = v35;
LABEL_22:
      v38 = v34 & 0xC;
      if ( (v34 & 0xC) != 0 )
      {
        if ( v38 == 4 )
        {
          v40 = *(unsigned __int16 *)(v20 + 18);
          v29 = (unsigned int)((rcSrc.bottom - v40 - rcSrc.top) >> 31);
          LODWORD(v29) = (rcSrc.bottom - v40 - rcSrc.top) % 2;
          v83 = (rcSrc.bottom - v40 - rcSrc.top) / 2;
          v84 = rcSrc.bottom - v40 - rcSrc.top - v83;
        }
        else if ( v38 == 8 )
        {
          v29 = (unsigned int)a6->bottom;
          v39 = rcSrc.bottom - *(unsigned __int16 *)(v20 + 18) - v29 - rcSrc.top;
LABEL_28:
          v83 = v39;
          v84 = v29;
        }
LABEL_30:
        v41 = *(_BYTE *)(v20 + 20) & 0x78;
        if ( v41 == 48 )
        {
          v42 = (*(unsigned __int8 *)(v20 + 24) << 16) | (*(unsigned __int8 *)(v20 + 23) << 8);
          v89 = 2;
          v90 = *(unsigned __int8 *)(v20 + 22) | v42;
        }
        else if ( v41 == 56 )
        {
          v43 = *((_DWORD *)this + 34) * *(unsigned __int8 *)(v20 + 22);
          v89 = 1;
          v91 = 0;
          v93 = 1;
          v29 = (unsigned int)(v43 / 255);
          v92 = v43 / 255;
        }
        DirectUI::DrawNineGrid((DirectUI *)&v74, (struct DirectUI::NGINFO *)v29);
        SetStretchBltMode(a2, v22);
        goto LABEL_18;
      }
      v39 = a6->top;
      v29 = rcSrc.bottom - (unsigned int)*(unsigned __int16 *)(v20 + 18) - v39 - rcSrc.top;
      goto LABEL_28;
    }
LABEL_40:
    if ( Value )
    {
      v48 = *(__int64 (__fastcall **)(LPVOID, void *, struct DirectUI::Value *))(*(_QWORD *)Value + 16LL);
      v49 = DirectUI::Value::GetImage(a3, (*((_DWORD *)this + 38) & 0x40) != 0, 1.0);
      v50 = v48(v73, v49, a3);
      v51 = 0;
      SolidBrush = (HBRUSH)v50;
      v70 = (HBRUSH)v50;
      v12 = 0;
      goto LABEL_73;
    }
    goto LABEL_75;
  }
  DirectUI::AutoClipRect::AutoClipRect(
    (DirectUI::AutoClipRect *)&pOptions,
    a2,
    (const struct tagRECT *)hTheme,
    lprcSrc1);
  v44 = DirectUI::Value::GetImage(a3, (*((_DWORD *)this + 38) & 0x40) != 0, 1.0);
  CompatibleDC = CreateCompatibleDC(a2);
  v46 = SelectObject(CompatibleDC, v44);
  LODWORD(v44) = SetStretchBltMode(a2, 4);
  StretchBlt(
    a2,
    rect.left,
    rect.top,
    rect.right - rect.left,
    rect.bottom - rect.top,
    CompatibleDC,
    0,
    0,
    *(unsigned __int16 *)(v20 + 16),
    *(unsigned __int16 *)(v20 + 18),
    0xCC0020u);
  SetStretchBltMode(a2, (int)v44);
  SelectObject(CompatibleDC, v46);
  DeleteDC(CompatibleDC);
  if ( *((char *)this + 151) < 0 )
    DirectUI::MakeOpaque((DirectUI *)a2, (HDC)&rect, v47);
  DirectUI::AutoClipRect::~AutoClipRect((DirectUI::AutoClipRect *)&pOptions);
  SolidBrush = 0;
  v12 = 1;
LABEL_88:
  if ( v73 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v73 + 24LL))(v73);
  if ( SolidBrush )
  {
    if ( v12 )
      DeleteObject(SolidBrush);
  }
}

```

## disassembly

```asm
0x18009a744  push    rbp
0x18009a746  push    rbx
0x18009a747  push    rsi
0x18009a748  push    rdi
0x18009a749  push    r12
0x18009a74b  push    r13
0x18009a74d  push    r14
0x18009a74f  push    r15
0x18009a751  lea     rbp, [rsp-0D8h]
0x18009a759  sub     rsp, 1D8h
0x18009a760  mov     rax, cs:__security_cookie
0x18009a767  xor     rax, rsp
0x18009a76a  mov     [rbp+110h+var_50], rax
0x18009a771  mov     rax, [rbp+110h+arg_30]
0x18009a778  xor     ebx, ebx
0x18009a77a  movups  xmm0, xmmword ptr [r9]
0x18009a77e  mov     qword ptr [rbp+110h+pOptions.dwSize], rax
0x18009a782  mov     r13, rcx
0x18009a785  mov     rax, [rbp+110h+arg_20]
0x18009a78c  mov     rdi, r8
0x18009a78f  mov     ecx, cs:?g_dwFontCacheSlot@DirectUI@@3KA; dwTlsIndex
0x18009a795  lea     r15d, [rbx+1]
0x18009a799  mov     r14b, r15b
0x18009a79c  mov     [rsp+210h+hTheme], r9
0x18009a7a1  mov     r12, rdx
0x18009a7a4  mov     [rbp+110h+lprcSrc1], rax
0x18009a7a8  mov     [rsp+210h+var_1A8], rbx
0x18009a7ad  mov     sil, 0FFh
0x18009a7b0  movdqu  xmmword ptr [rbp+110h+rect.left], xmm0
0x18009a7b5  mov     [rsp+210h+var_1A0], ebx
0x18009a7b9  call    cs:__imp_TlsGetValue
0x18009a7bf  mov     ecx, [rdi]
0x18009a7c1  mov     r8, rax
0x18009a7c4  shl     ecx, 1Ah
0x18009a7c7  sar     ecx, 1Ah
0x18009a7ca  mov     [rbp+110h+var_188], rax
0x18009a7ce  sub     ecx, r15d
0x18009a7d1  jz      loc_18009AF35
0x18009a7d7  sub     ecx, 8
0x18009a7da  jz      loc_18009AC36
0x18009a7e0  lea     ebx, [r15+1]
0x18009a7e4  cmp     ecx, ebx
0x18009a7e6  jnz     loc_18009AF9B
0x18009a7ec  mov     r14, [rdi+8]
0x18009a7f0  mov     al, [r14+14h]
0x18009a7f4  and     al, 7
0x18009a7f6  jz      short loc_18009A808
0x18009a7f8  cmp     al, bl
0x18009a7fa  jz      loc_18009A959
0x18009a800  cmp     al, 4
0x18009a802  jnz     loc_18009AF98
0x18009a808  movzx   ecx, byte ptr [r14+14h]
0x18009a80d  shr     ecx, 3
0x18009a810  and     ecx, 0Fh
0x18009a813  sub     ecx, r15d
0x18009a816  jz      loc_18009ABB5
0x18009a81c  sub     ecx, 3
0x18009a81f  jz      loc_18009AABD
0x18009a825  sub     ecx, r15d
0x18009a828  jz      short loc_18009A83D
0x18009a82a  sub     ecx, r15d
0x18009a82d  jz      short loc_18009A83D
0x18009a82f  sub     ecx, r15d
0x18009a832  jz      short loc_18009A83D
0x18009a834  cmp     ecx, r15d
0x18009a837  jnz     loc_18009ABE3
0x18009a83d  xor     edx, edx; Val
0x18009a83f  lea     rcx, [rbp+110h+var_180]; void *
0x18009a843  mov     r8d, 0C0h; Size
0x18009a849  call    memset_0
0x18009a84e  mov     edx, 3; mode
0x18009a853  mov     rcx, r12; hdc
0x18009a856  call    cs:__imp_SetStretchBltMode
0x18009a85c  mov     edx, [r13+98h]
0x18009a863  mov     rcx, rdi; this
0x18009a866  movss   xmm2, cs:__real@3f800000; float
0x18009a86e  mov     esi, eax
0x18009a870  shr     edx, 6
0x18009a873  and     dl, r15b; bool
0x18009a876  mov     [rbp+110h+var_180], 0C0h
0x18009a87d  mov     [rbp+110h+var_178], r12
0x18009a881  mov     [rbp+110h+var_160], r15d
0x18009a885  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18009a88a  movzx   r9d, word ptr [r14+10h]; xRight
0x18009a88f  lea     rcx, [rbp+110h+rc]; lprc
0x18009a893  mov     [rbp+110h+var_158], rax
0x18009a897  xor     r8d, r8d; yTop
0x18009a89a  movzx   eax, word ptr [r14+12h]
0x18009a89f  xor     edx, edx; xLeft
0x18009a8a1  mov     [rsp+210h+yBottom], eax; yBottom
0x18009a8a5  call    cs:__imp_SetRect
0x18009a8ab  mov     rcx, [rsp+210h+hTheme]
0x18009a8b0  mov     rdi, qword ptr [rbp+110h+pOptions.dwSize]
0x18009a8b4  mov     eax, [rcx+0Ch]
0x18009a8b7  mov     r9d, [rcx+8]
0x18009a8bb  mov     r8d, [rcx+4]
0x18009a8bf  mov     edx, [rcx]
0x18009a8c1  lea     rcx, [rbp+110h+rcSrc]; lprc
0x18009a8c5  add     eax, [rdi+0Ch]
0x18009a8c8  add     r9d, [rdi+8]; xRight
0x18009a8cc  sub     r8d, [rdi+4]; yTop
0x18009a8d0  sub     edx, [rdi]; xLeft
0x18009a8d2  mov     [rsp+210h+yBottom], eax; yBottom
0x18009a8d6  call    cs:__imp_SetRect
0x18009a8dc  lea     rdx, [rbp+110h+rcSrc]; lprcSrc
0x18009a8e0  lea     rcx, [rbp+110h+rcDst]; lprcDst
0x18009a8e4  call    cs:__imp_CopyRect
0x18009a8ea  mov     al, [r14+14h]
0x18009a8ee  mov     ecx, [rdi]
0x18009a8f0  and     al, 78h
0x18009a8f2  mov     edx, [rdi+8]
0x18009a8f5  mov     r8d, [rdi+4]
0x18009a8f9  mov     r9d, [rdi+0Ch]
0x18009a8fd  mov     [rbp+110h+var_120], ecx
0x18009a900  mov     [rbp+110h+var_11C], edx
0x18009a903  mov     [rbp+110h+var_118], r8d
0x18009a907  mov     [rbp+110h+var_114], r9d
0x18009a90b  cmp     al, 40h ; '@'
0x18009a90d  jnz     loc_18009AA36
0x18009a913  mov     rcx, r13; this
0x18009a916  call    ?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x18009a91b  mov     edx, eax; struct DirectUI::Element *
0x18009a91d  mov     rcx, r13; this
0x18009a920  call    ?MapAlign@DirectUI@@YAHPEAVElement@1@H@Z; DirectUI::MapAlign(DirectUI::Element *,int)
0x18009a925  mov     r10, [rbp+110h+arg_28]
0x18009a92c  mov     ecx, eax
0x18009a92e  mov     r9d, eax
0x18009a931  and     ecx, 3
0x18009a934  jz      short loc_18009A9B5
0x18009a936  sub     ecx, r15d
0x18009a939  jz      short loc_18009A98E
0x18009a93b  cmp     ecx, r15d
0x18009a93e  jnz     loc_18009A9CD
0x18009a944  movzx   eax, word ptr [r14+10h]
0x18009a949  mov     ecx, [rbp+110h+rcSrc.right]
0x18009a94c  mov     edx, [r10+8]
0x18009a950  sub     ecx, eax
0x18009a952  sub     ecx, edx
0x18009a954  sub     ecx, [rbp+110h+rcSrc.left]
0x18009a957  jmp     short loc_18009A9C7
0x18009a959  mov     edx, [r13+98h]
0x18009a960  mov     rcx, rdi; this
0x18009a963  movss   xmm2, cs:__real@3f800000; float
0x18009a96b  shr     edx, 6
0x18009a96e  and     dl, r15b; bool
0x18009a971  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18009a976  lea     r8, [rbp+110h+rect]; lprect
0x18009a97a  mov     rdx, rax; hmf
0x18009a97d  mov     rcx, r12; hdc
0x18009a980  call    cs:__imp_PlayEnhMetaFile
0x18009a986  mov     r14b, r15b
0x18009a989  jmp     loc_18009B057
0x18009a98e  mov     r8d, [rbp+110h+rcSrc.right]
0x18009a992  mov     eax, r8d
0x18009a995  movzx   ecx, word ptr [r14+10h]
0x18009a99a  sub     eax, ecx
0x18009a99c  sub     r8d, ecx
0x18009a99f  sub     eax, [rbp+110h+rcSrc.left]
0x18009a9a2  sub     r8d, [rbp+110h+rcSrc.left]
0x18009a9a6  cdq
0x18009a9a7  idiv    ebx
0x18009a9a9  sub     r8d, eax
0x18009a9ac  mov     [rbp+110h+var_130], eax
0x18009a9af  mov     [rbp+110h+var_12C], r8d
0x18009a9b3  jmp     short loc_18009A9CD
0x18009a9b5  movzx   eax, word ptr [r14+10h]
0x18009a9ba  mov     edx, [rbp+110h+rcSrc.right]
0x18009a9bd  mov     ecx, [r10]
0x18009a9c0  sub     edx, eax
0x18009a9c2  sub     edx, ecx
0x18009a9c4  sub     edx, [rbp+110h+rcSrc.left]
0x18009a9c7  mov     [rbp+110h+var_12C], edx
0x18009a9ca  mov     [rbp+110h+var_130], ecx
0x18009a9cd  and     r9d, 0Ch
0x18009a9d1  jz      short loc_18009AA1B
0x18009a9d3  cmp     r9d, 4
0x18009a9d7  jz      short loc_18009A9F4
0x18009a9d9  cmp     r9d, 8
0x18009a9dd  jnz     short loc_18009AA44
0x18009a9df  movzx   eax, word ptr [r14+12h]
0x18009a9e4  mov     ecx, [rbp+110h+rcSrc.bottom]
0x18009a9e7  mov     edx, [r10+0Ch]
0x18009a9eb  sub     ecx, eax
0x18009a9ed  sub     ecx, edx
0x18009a9ef  sub     ecx, [rbp+110h+rcSrc.top]
0x18009a9f2  jmp     short loc_18009AA2E
0x18009a9f4  mov     r8d, [rbp+110h+rcSrc.bottom]
0x18009a9f8  mov     eax, r8d
0x18009a9fb  movzx   ecx, word ptr [r14+12h]
0x18009aa00  sub     eax, ecx
0x18009aa02  sub     r8d, ecx
0x18009aa05  sub     eax, [rbp+110h+rcSrc.top]
0x18009aa08  sub     r8d, [rbp+110h+rcSrc.top]
0x18009aa0c  cdq
0x18009aa0d  idiv    ebx
0x18009aa0f  sub     r8d, eax
0x18009aa12  mov     [rbp+110h+var_128], eax
0x18009aa15  mov     [rbp+110h+var_124], r8d
0x18009aa19  jmp     short loc_18009AA44
0x18009aa1b  movzx   eax, word ptr [r14+12h]
0x18009aa20  mov     edx, [rbp+110h+rcSrc.bottom]
0x18009aa23  mov     ecx, [r10+4]
0x18009aa27  sub     edx, eax
0x18009aa29  sub     edx, ecx
0x18009aa2b  sub     edx, [rbp+110h+rcSrc.top]
0x18009aa2e  mov     [rbp+110h+var_128], ecx
0x18009aa31  mov     [rbp+110h+var_124], edx
0x18009aa34  jmp     short loc_18009AA44
0x18009aa36  mov     [rbp+110h+var_130], ecx
0x18009aa39  mov     [rbp+110h+var_12C], edx
0x18009aa3c  mov     [rbp+110h+var_128], r8d
0x18009aa40  mov     [rbp+110h+var_124], r9d
0x18009aa44  mov     al, [r14+14h]
0x18009aa48  and     al, 78h
0x18009aa4a  cmp     al, 30h ; '0'
0x18009aa4c  jnz     short loc_18009AA6F
0x18009aa4e  movzx   ecx, byte ptr [r14+17h]
0x18009aa53  movzx   eax, byte ptr [r14+18h]
0x18009aa58  shl     eax, 10h
0x18009aa5b  shl     ecx, 8
0x18009aa5e  or      ecx, eax
0x18009aa60  mov     [rbp+110h+var_108], ebx
0x18009aa63  movzx   eax, byte ptr [r14+16h]
0x18009aa68  or      ecx, eax
0x18009aa6a  mov     [rbp+110h+var_E8], ecx
0x18009aa6d  jmp     short loc_18009AAA4
0x18009aa6f  cmp     al, 38h ; '8'
0x18009aa71  jnz     short loc_18009AAA4
0x18009aa73  movzx   ecx, byte ptr [r14+16h]
0x18009aa78  mov     eax, 80808081h
0x18009aa7d  imul    ecx, [r13+88h]
0x18009aa85  mov     [rbp+110h+var_108], r15d
0x18009aa89  mov     [rbp+110h+var_E4], 0
0x18009aa8f  mov     [rbp+110h+var_E1], r15b
0x18009aa93  imul    ecx
0x18009aa95  add     edx, ecx
0x18009aa97  sar     edx, 7
0x18009aa9a  mov     eax, edx
0x18009aa9c  shr     eax, 1Fh
0x18009aa9f  add     edx, eax; struct DirectUI::NGINFO *
0x18009aaa1  mov     [rbp+110h+var_E2], dl
0x18009aaa4  lea     rcx, [rbp+110h+var_180]; this
0x18009aaa8  call    ?DrawNineGrid@DirectUI@@YAJPEAUNGINFO@1@@Z; DirectUI::DrawNineGrid(DirectUI::NGINFO *)
0x18009aaad  mov     edx, esi; mode
0x18009aaaf  mov     rcx, r12; hdc
0x18009aab2  call    cs:__imp_SetStretchBltMode
0x18009aab8  jmp     loc_18009A986
0x18009aabd  mov     r9, [rbp+110h+lprcSrc1]; struct tagRECT *
0x18009aac1  lea     rcx, [rbp+110h+pOptions]; this
0x18009aac5  mov     r8, [rsp+210h+hTheme]; struct tagRECT *
0x18009aaca  mov     rdx, r12; HDC
0x18009aacd  call    ??0AutoClipRect@DirectUI@@QEAA@PEAUHDC__@@PEBUtagRECT@@1@Z; DirectUI::AutoClipRect::AutoClipRect(HDC__ *,tagRECT const *,tagRECT const *)
0x18009aad2  mov     edx, [r13+98h]
0x18009aad9  mov     rcx, rdi; this
0x18009aadc  movss   xmm2, cs:__real@3f800000; float
0x18009aae4  shr     edx, 6
0x18009aae7  and     dl, r15b; bool
0x18009aaea  call    ?GetImage@Value@DirectUI@@QEAAPEAX_NM@Z; DirectUI::Value::GetImage(bool,float)
0x18009aaef  mov     rcx, r12; hdc
0x18009aaf2  mov     rbx, rax
0x18009aaf5  call    cs:__imp_CreateCompatibleDC
0x18009aafb  mov     rcx, rax; hdc
0x18009aafe  mov     rdx, rbx; h
0x18009ab01  mov     rsi, rax
0x18009ab04  call    cs:__imp_SelectObject
0x18009ab0a  mov     edx, 4; mode
0x18009ab0f  mov     rcx, r12; hdc
0x18009ab12  mov     rdi, rax
0x18009ab15  call    cs:__imp_SetStretchBltMode
0x18009ab1b  movzx   ecx, word ptr [r14+10h]
0x18009ab20  mov     ebx, eax
0x18009ab22  movzx   eax, word ptr [r14+12h]
0x18009ab27  xor     r14d, r14d
0x18009ab2a  mov     r10d, [rbp+110h+rect.bottom]
0x18009ab2e  mov     r8d, [rbp+110h+rect.top]; yDest
0x18009ab32  sub     r10d, r8d
0x18009ab35  mov     r9d, [rbp+110h+rect.right]
0x18009ab39  mov     edx, [rbp+110h+rect.left]; xDest
0x18009ab3c  sub     r9d, edx; wDest
0x18009ab3f  mov     [rsp+210h+rop], 0CC0020h; rop
0x18009ab47  mov     [rsp+210h+hSrc], eax; hSrc
0x18009ab4b  mov     [rsp+210h+wSrc], ecx; wSrc
0x18009ab4f  mov     rcx, r12; hdcDest
0x18009ab52  mov     [rsp+210h+ySrc], r14d; ySrc
0x18009ab57  mov     [rsp+210h+xSrc], r14d; xSrc
0x18009ab5c  mov     [rsp+210h+hdcSrc], rsi; hdcSrc
0x18009ab61  mov     [rsp+210h+yBottom], r10d; hDest
0x18009ab66  call    cs:__imp_StretchBlt
0x18009ab6c  mov     edx, ebx; mode
0x18009ab6e  mov     rcx, r12; hdc
0x18009ab71  call    cs:__imp_SetStretchBltMode
0x18009ab77  mov     rdx, rdi; h
0x18009ab7a  mov     rcx, rsi; hdc
0x18009ab7d  call    cs:__imp_SelectObject
0x18009ab83  mov     rcx, rsi; hdc
0x18009ab86  call    cs:__imp_DeleteDC
0x18009ab8c  cmp     [r13+97h], r14b
0x18009ab93  jge     short loc_18009ABA1
0x18009ab95  lea     rdx, [rbp+110h+rect]; HDC
0x18009ab99  mov     rcx, r12; this
  ... truncated ...
```
