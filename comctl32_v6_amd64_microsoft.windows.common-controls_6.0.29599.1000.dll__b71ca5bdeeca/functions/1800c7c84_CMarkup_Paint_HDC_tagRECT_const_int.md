# CMarkup::Paint(HDC__ *,tagRECT const *,int)

- ea: `0x1800c7c84`
- end: `0x1800c86f3`
- name: `?Paint@CMarkup@@AEAAXPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `2671`
- prototype: `void __fastcall(CMarkup *__hidden this, HDC, RECT *lprcSrc, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800c7a00`
- `0x1800c7a30`

## callees

- `0x180011f44`
- `0x1800abd00`
- `0x1800b725c`
- `0x1800bf88c`
- `0x1800c7c84`
- `0x1800d1c6c`
- `0x180114520`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800c7e60`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800c7e60`
- `GDI32!SetTextColor` at `0x1800c850f`
- `GDI32!SetTextColor` at `0x1800c85c2`
- `GDI32!SetTextColor` at `0x1800c86ae`
- `GDI32!SetTextColor` at `0x1800c850f`
- `GDI32!SetTextColor` at `0x1800c85c2`
- `GDI32!SetTextColor` at `0x1800c86ae`
- `GDI32!GetTextMetricsW` at `0x1800c7d58`
- `GDI32!GetTextMetricsW` at `0x1800c7d7e`
- `GDI32!GetTextMetricsW` at `0x1800c7d58`
- `GDI32!GetTextMetricsW` at `0x1800c7d7e`
- `GDI32!SelectObject` at `0x1800c7d4b`
- `GDI32!SelectObject` at `0x1800c7d71`
- `GDI32!SelectObject` at `0x1800c7e56`
- `GDI32!SelectObject` at `0x1800c84c3`
- `GDI32!SelectObject` at `0x1800c86c3`
- `GDI32!SelectObject` at `0x1800c7d4b`
- `GDI32!SelectObject` at `0x1800c7d71`
- `GDI32!SelectObject` at `0x1800c7e56`
- `GDI32!SelectObject` at `0x1800c84c3`
- `GDI32!SelectObject` at `0x1800c86c3`
- `GDI32!GetTextColor` at `0x1800c7cd8`
- `GDI32!GetTextColor` at `0x1800c84d4`
- `GDI32!GetTextColor` at `0x1800c7cd8`
- `GDI32!GetTextColor` at `0x1800c84d4`
- `GDI32!GetCurrentObject` at `0x1800c7ce8`
- `GDI32!GetCurrentObject` at `0x1800c7ce8`
- `USER32!CopyRect` at `0x1800c7ed0`
- `USER32!CopyRect` at `0x1800c81a4`
- `USER32!CopyRect` at `0x1800c842a`
- `USER32!CopyRect` at `0x1800c7ed0`
- `USER32!CopyRect` at `0x1800c81a4`
- `USER32!CopyRect` at `0x1800c842a`
- `USER32!DrawFocusRect` at `0x1800c85d4`
- `USER32!DrawFocusRect` at `0x1800c85d4`
- `USER32!GetSysColor` at `0x1800c84ff`
- `USER32!GetSysColor` at `0x1800c84ff`
- `USER32!SetRect` at `0x1800c813f`
- `USER32!SetRect` at `0x1800c813f`
- `USER32!EqualRect` at `0x1800c7dfa`
- `USER32!EqualRect` at `0x1800c7dfa`
- `UxTheme!GetThemeTextMetrics` at `0x1800c7dac`
- `UxTheme!GetThemeTextMetrics` at `0x1800c7dd8`
- `UxTheme!GetThemeTextMetrics` at `0x1800c7dac`
- `UxTheme!GetThemeTextMetrics` at `0x1800c7dd8`

## pseudocode

```c
void __fastcall CMarkup::Paint(CMarkup *this, HDC a2, RECT *lprcSrc, int a4)
{
  int v4; // r13d
  RECT *v5; // r12
  HGDIOBJ CurrentObject; // rax
  HGDIOBJ v9; // rsi
  int IsMarkupState; // eax
  void *v11; // rcx
  LONG tmExternalLeading; // edi
  RECT v13; // xmm0
  void *v14; // rdx
  __int64 v15; // r15
  int v16; // r11d
  unsigned int v17; // eax
  void *v18; // rdx
  int v19; // eax
  unsigned __int16 *v20; // r13
  int v21; // esi
  __int64 v22; // rdi
  int v23; // edx
  int v24; // ecx
  int v25; // r13d
  const unsigned __int16 *v26; // r8
  unsigned int v27; // esi
  int v28; // eax
  LONG left; // r8d
  WCHAR tmBreakChar; // r12
  int v31; // r15d
  int v32; // esi
  int IsLineBreakChar; // eax
  int v34; // edx
  int v35; // r15d
  int v36; // ecx
  int v37; // eax
  __int64 v38; // rdx
  LONG right; // edx
  LONG v40; // r8d
  LONG v41; // r10d
  LONG v42; // r9d
  unsigned int v43; // edx
  struct tagRECT *v44; // rax
  struct tagRECT *v45; // rsi
  __int64 v46; // rax
  struct tagRECT **v47; // rcx
  int v48; // edx
  bool v49; // cc
  bool v50; // zf
  LONG top; // eax
  int v52; // r8d
  int v53; // ecx
  __int64 i; // rdx
  __int64 j; // rax
  int v56; // r9d
  int v57; // ecx
  int v58; // edx
  __int64 k; // r8
  __int64 m; // rdx
  int v61; // ecx
  __int64 v62; // r10
  int v63; // r13d
  int v64; // ecx
  unsigned int v65; // r13d
  _DWORD *n; // rdi
  int v67; // esi
  int v68; // r15d
  void *v69; // rdx
  HDC v70; // rcx
  int v71; // esi
  COLORREF TextColor; // eax
  int v73; // ecx
  COLORREF v74; // edx
  __int64 v75; // r12
  __int64 ii; // rsi
  int v77; // r9d
  const unsigned __int16 *v78; // r8
  __int64 jj; // rsi
  __int64 v80; // rax
  BOOL v81; // [rsp+30h] [rbp-D0h]
  int v82; // [rsp+50h] [rbp-B0h]
  int v83; // [rsp+54h] [rbp-ACh]
  int v84; // [rsp+58h] [rbp-A8h]
  int v85; // [rsp+5Ch] [rbp-A4h]
  unsigned int v86; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v87; // [rsp+68h] [rbp-98h]
  int v88; // [rsp+70h] [rbp-90h]
  int v89; // [rsp+74h] [rbp-8Ch] BYREF
  LONG v90; // [rsp+78h] [rbp-88h]
  int v91; // [rsp+7Ch] [rbp-84h]
  COLORREF color; // [rsp+80h] [rbp-80h]
  int v93; // [rsp+84h] [rbp-7Ch]
  int v94; // [rsp+88h] [rbp-78h]
  unsigned int v95; // [rsp+8Ch] [rbp-74h]
  int v96; // [rsp+90h] [rbp-70h]
  int v97; // [rsp+94h] [rbp-6Ch]
  int v98; // [rsp+98h] [rbp-68h]
  RECT *v99; // [rsp+A0h] [rbp-60h]
  HGDIOBJ v100; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v101; // [rsp+B0h] [rbp-50h]
  HGDIOBJ h; // [rsp+B8h] [rbp-48h]
  __int64 v103; // [rsp+C0h] [rbp-40h] BYREF
  RECT rcSrc; // [rsp+C8h] [rbp-38h] BYREF
  struct tagRECT rcDst; // [rsp+D8h] [rbp-28h] BYREF
  struct tagRECT rc; // [rsp+E8h] [rbp-18h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+F8h] [rbp-8h] BYREF
  _DWORD v108[256]; // [rsp+140h] [rbp+40h]

  v97 = a4;
  v4 = a4;
  v5 = lprcSrc;
  v99 = lprcSrc;
  if ( !*((_QWORD *)this + 2) )
    return;
  color = GetTextColor(a2);
  CurrentObject = GetCurrentObject(a2, 6u);
  v9 = (HGDIOBJ)*((_QWORD *)this + 8);
  h = CurrentObject;
  IsMarkupState = CMarkup::IsMarkupState(this, 1u);
  v11 = (void *)*((_QWORD *)this + 15);
  memset(&tm.tmOverhang, 0, 28);
  v98 = IsMarkupState;
  if ( !v9 )
    v9 = g_hfontSystem;
  tmExternalLeading = 0;
  v100 = v9;
  v108[0] = 0;
  memset(&tm, 0, 32);
  v13 = *v5;
  *((_DWORD *)this + 10) = 0;
  rcSrc = v13;
  if ( v11 )
  {
    GetThemeTextMetrics(v11, a2, *((_DWORD *)this + 32), *((_DWORD *)this + 33), &tm);
    if ( tm.tmExternalLeading > 0 )
      tmExternalLeading = tm.tmExternalLeading;
    GetThemeTextMetrics(*((HTHEME *)this + 15), a2, *((_DWORD *)this + 32), *((_DWORD *)this + 34), &tm);
    if ( tm.tmExternalLeading > tmExternalLeading )
      tmExternalLeading = tm.tmExternalLeading;
    v90 = tmExternalLeading;
  }
  else
  {
    SelectObject(a2, v9);
    GetTextMetricsW(a2, &tm);
    v14 = (void *)*((_QWORD *)this + 7);
    if ( tm.tmExternalLeading > 0 )
      tmExternalLeading = tm.tmExternalLeading;
    v90 = tmExternalLeading;
    SelectObject(a2, v14);
    GetTextMetricsW(a2, &tm);
    if ( tm.tmExternalLeading > tmExternalLeading )
      v90 = tm.tmExternalLeading;
  }
  if ( *((_DWORD *)this + 24) == 1 || !EqualRect((const RECT *)((char *)this + 100), v5) )
  {
    v15 = *((_QWORD *)this + 2);
    v86 = 0;
    v16 = 0;
    v82 = 0;
    v17 = *((_DWORD *)this + 23) & 0xFFFFFBD0 | 0x420;
    v91 = 0;
    v95 = v17;
    v103 = v15;
    if ( v15 )
    {
      do
      {
        if ( !*((_QWORD *)this + 15) )
        {
          v18 = v9;
          if ( *(_DWORD *)v15 == -1 )
            v18 = (void *)*((_QWORD *)this + 7);
          if ( v18 )
            SelectObject(a2, v18);
        }
        v19 = lstrlenW(*(LPCWSTR *)(v15 + 120));
        v20 = *(unsigned __int16 **)(v15 + 120);
        v21 = v19;
        v83 = v19;
        v87 = v20;
        v101 = v20;
        TEXTBLOCK::FreeRects((TEXTBLOCK *)v15);
        v16 = v82;
        v94 = 1;
        while ( v21 > 0 )
        {
          v96 = v16 + 1;
          if ( (unsigned int)(v16 + 1) >= 0xFF || (*((_BYTE *)this + 92) & 0x20) != 0 && v16 > 0 )
            break;
          v88 = 0;
          rc = 0;
          rcDst = 0;
          CopyRect(&rcDst, &rcSrc);
          v22 = 0;
          v23 = 1;
          while ( v20[v22] != 10 )
          {
            if ( v20[v22] == 13 )
              goto LABEL_56;
            v22 = (unsigned int)(v22 + 1);
            if ( (int)v22 >= v21 )
            {
              v24 = 0;
              v93 = 0;
              v25 = 0;
              LODWORD(v22) = v21;
              v23 = 0;
              goto LABEL_32;
            }
          }
          if ( v20[v22] != 13 )
            goto LABEL_57;
LABEL_56:
          v24 = 2;
          if ( v20[v22 + 1] == 10 )
            goto LABEL_58;
LABEL_57:
          v24 = 1;
LABEL_58:
          v93 = v22;
          v25 = 1;
LABEL_32:
          v85 = v23;
          v84 = v24;
          if ( rcDst.right == rcDst.left )
          {
            LODWORD(v22) = 0;
          }
          else
          {
            v26 = v87;
            do
            {
              v27 = v95;
              CMarkup::ThemedDrawText(this, a2, v26, v22, &rcDst, v95, *(_DWORD *)v15 != -1);
              v86 = rcDst.bottom - rcDst.top;
              if ( !(_DWORD)v22 && v25 == 1 )
              {
                rcDst.left = v5->left;
                rcDst.right = v5->right;
                v28 = CMarkup::ThemedDrawText(this, a2, L"a", 1, &rcDst, v27, *(_DWORD *)v15 != -1);
                rcDst.right = rcDst.left;
                v86 = v28;
              }
              left = rcSrc.left;
              if ( rcDst.right - rcDst.left <= rcSrc.right - rcSrc.left )
                break;
              tmBreakChar = tm.tmBreakChar;
              v31 = v22 - 1;
              v32 = v22 - 1;
              v88 = 0;
              v89 = 0;
              if ( (int)v22 - 1 >= 0 )
              {
                do
                {
                  IsLineBreakChar = CMarkup::_IsLineBreakChar(v87, v32, tmBreakChar, &v89);
                  if ( IsLineBreakChar < 0 )
                  {
                    v88 = v89;
                  }
                  else
                  {
                    v88 = v89;
                    if ( IsLineBreakChar != (_DWORD)v22 || v89 )
                    {
                      v5 = v99;
                      LODWORD(v22) = IsLineBreakChar;
                      goto LABEL_43;
                    }
                  }
                  --v32;
                }
                while ( v32 >= 0 );
                left = rcSrc.left;
              }
              v5 = v99;
              v37 = v22;
              v38 = (int)v22;
              LODWORD(v22) = 0;
              if ( v99->left != left || v37 <= 0 )
                break;
              LODWORD(v22) = v31;
              if ( v31 <= 1 )
              {
LABEL_43:
                v26 = v87;
              }
              else
              {
                v26 = v87;
                if ( (unsigned __int16)(v87[v38 - 1] + 9216) <= 0x3FFu
                  && (unsigned __int16)(v87[v38 - 2] + 10240) <= 0x3FFu )
                {
                  LODWORD(v22) = v31 - 1;
                }
              }
              v15 = v103;
            }
            while ( (int)v22 > 0 );
            v21 = v83;
            v24 = v84;
          }
          v34 = v85;
          if ( v25 )
          {
            if ( v93 > (int)v22 )
              v34 = 0;
            v85 = v34;
          }
          v35 = v22;
          if ( (int)v22 < v21 && v34 )
            v35 = v24 + v22;
          v36 = v91;
          if ( v91 )
          {
            v16 = v82;
            v20 = &v87[v35];
            v87 = v20;
          }
          else
          {
            SetRect(&rc, rcDst.left, 0, rcDst.right, rcDst.bottom - rcDst.top);
            right = v5->right;
            v40 = rc.right;
            v41 = rc.left;
            v42 = rcSrc.left;
            if ( rcSrc.left + rc.right - rc.left < right )
              right = rcSrc.left + rc.right - rc.left;
            rcSrc.right = right;
            v43 = v86;
            rcSrc.bottom = v86 + rcSrc.top;
            if ( (_DWORD)v22 )
            {
              if ( (*((_BYTE *)this + 92) & 0x20) == 0 || (v16 = v82) == 0 )
              {
                v44 = (struct tagRECT *)DirectUI::AccHAllocAndZero((DirectUI *)0x28, v86);
                v45 = v44;
                if ( v44 )
                {
                  CopyRect(v44, &rcSrc);
                  v16 = v82;
                  v45[1].left = v87 - v101;
                  *(_QWORD *)&v45[2].left = 0;
                  v45[1].top = v35;
                  v45[1].right = v82;
                }
                else
                {
                  v16 = v82;
                }
                v46 = *(_QWORD *)(v103 + 112);
                if ( v46 )
                {
                  do
                  {
                    v47 = (struct tagRECT **)(v46 + 32);
                    v46 = *(_QWORD *)(v46 + 32);
                  }
                  while ( v46 );
                  *v47 = v45;
                }
                else
                {
                  *(_QWORD *)(v103 + 112) = v45;
                }
                v21 = v83;
                v41 = rc.left;
                v40 = rc.right;
                v42 = rcSrc.left;
              }
              v48 = v108[v16];
              if ( v48 <= v42 + v40 - v5->left - v41 )
                v48 = v42 + v40 - v5->left - v41;
              v49 = *((_DWORD *)this + 10) <= v48;
              v108[v16] = v48;
              if ( !v49 )
                v48 = *((_DWORD *)this + 10);
              *((_DWORD *)this + 10) = v48;
              v43 = v86;
            }
            else
            {
              v16 = v82;
            }
            if ( (int)v22 >= v21 )
            {
              v20 = v87;
              rcSrc.left = v40 - v41 + v42;
            }
            else
            {
              v16 = v96;
              v82 = v96;
              if ( v88 )
                ++v35;
              v50 = (*((_BYTE *)this + 92) & 0x20) == 0;
              v108[v96] = 0;
              v20 = &v87[v35];
              v87 = v20;
              rcSrc.left = v5->left;
              if ( v50 )
                top = v5->top + v43 * v16;
              else
                top = v5->top;
              rcSrc.top = top;
              rcSrc.bottom = v43 + v90 + top;
            }
            v36 = v91;
            rcSrc.right = v5->right;
            *((_DWORD *)this + 9) = rcSrc.bottom - v5->top;
          }
          if ( (*((_BYTE *)this + 92) & 0x10) == 0 )
          {
            if ( (int)v22 < v21 )
              v36 = 1;
            if ( v85 )
              v36 = 0;
            v91 = v36;
          }
          if ( !v94 && !v35 )
          {
            if ( v16 > 0 )
              v82 = --v16;
            v15 = v103;
            rcSrc.top = v5->top + v16 * v86;
            break;
          }
          v21 -= v35;
          v94 = v35;
          v15 = v103;
          v83 = v21;
        }
        v15 = *(_QWORD *)(v15 + 104);
        v9 = v100;
        v103 = v15;
      }
      while ( v15 );
      v4 = v97;
    }
    v52 = *((_DWORD *)this + 23);
    if ( (v52 & 0x20) != 0 && (v52 & 0xC) != 0 )
    {
      v53 = 0;
      if ( (v52 & 4) != 0 )
        v53 = (v5->bottom - v5->top - *((_DWORD *)this + 9)) / 2;
      if ( (v52 & 8) != 0 )
        v53 = v5->bottom - v5->top - *((_DWORD *)this + 9);
      for ( i = *((_QWORD *)this + 2); i; i = *(_QWORD *)(i + 104) )
      {
        for ( j = *(_QWORD *)(i + 112); j; j = *(_QWORD *)(j + 32) )
        {
          *(_DWORD *)(j + 4) += v53;
          *(_DWORD *)(j + 12) += v53;
        }
      }
    }
    if ( (*((_BYTE *)this + 92) & 3) != 0 )
    {
      if ( v16 >= 0 )
      {
        v56 = 0;
        v57 = v5->right - v5->left;
        do
        {
          v58 = v108[v56];
          if ( v57 <= v58 )
          {
            v108[v56] = 0;
          }
          else
          {
            if ( (*((_BYTE *)this + 92) & 1) != 0 )
            {
              v58 = (v57 - v58) / 2;
              v108[v56] = v58;
            }
            if ( (*((_BYTE *)this + 92) & 2) != 0 )
              v108[v56] = v57 - v58;
          }
          ++v56;
        }
        while ( v56 <= v16 );
      }
      for ( k = *((_QWORD *)this + 2); k; k = *(_QWORD *)(k + 104) )
      {
        for ( m = *(_QWORD *)(k + 112); m; m = *(_QWORD *)(m + 32) )
        {
          v61 = v108[*(unsigned int *)(m + 24)];
          *(_DWORD *)m += v61;
          *(_DWORD *)(m + 8) += v61;
        }
      }
    }
    CopyRect((LPRECT)((char *)this + 100), v5);
    *((_DWORD *)this + 24) = 0;
  }
  if ( !v4 )
  {
    v80 = *(_QWORD *)this;
    rc = 0;
    if ( (*(int (__fastcall **)(CMarkup *, struct tagRECT *))(v80 + 232))(this, &rc) < 0 )
    {
      *(_QWORD *)((char *)this + 36) = 0;
    }
    else
    {
      *((_DWORD *)this + 10) = rc.right - rc.left;
      *((_DWORD *)this + 9) = rc.bottom;
    }
    goto LABEL_177;
  }
  v62 = *((_QWORD *)this + 10);
  v63 = *((_DWORD *)this + 23);
  v64 = *((_DWORD *)this + 2);
  v103 = 0;
  v65 = v63 & 0xFFFFFBD0 | 0x20;
  (*(void (__fastcall **)(__int64, __int64, HDC, RECT *, int, _DWORD, _DWORD, __int64 *))(*(_QWORD *)v62 + 48LL))(
    v62,
    1,
    a2,
    v5,
    v64,
    0,
    0,
    &v103);
  for ( n = (_DWORD *)*((_QWORD *)this + 2); n; n = (_DWORD *)*((_QWORD *)n + 13) )
  {
    v67 = *n;
    v68 = n[1] & 2;
    if ( !*((_QWORD *)this + 15) )
    {
      v69 = v100;
      if ( v67 == -1 )
        v69 = (void *)*((_QWORD *)this + 7);
      if ( v69 )
        SelectObject(a2, v69);
    }
    v70 = a2;
    if ( v67 != -1 )
    {
      v71 = n[1];
      TextColor = GetTextColor(a2);
      if ( (v71 & 2) != 0 )
      {
        if ( (v71 & 0x10) == 0 )
        {
          if ( (v71 & 8) != 0 )
            v73 = 13;
          else
            v73 = 26;
LABEL_154:
          TextColor = GetSysColor(v73);
        }
        v74 = TextColor;
        v70 = a2;
        goto LABEL_157;
      }
      v73 = 17;
      goto LABEL_154;
    }
    v74 = color;
LABEL_157:
    SetTextColor(v70, v74);
    if ( (v103 & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD, __int64, HDC, _QWORD, _DWORD, _DWORD, int, _QWORD))(**((_QWORD **)this + 10) + 48LL))(
        *((_QWORD *)this + 10),
        65537,
        a2,
        0,
        *((_DWORD *)this + 2),
        *n,
        v68 != 0 ? 32 : 4,
        0);
    v75 = *((_QWORD *)n + 15);
    for ( ii = *((_QWORD *)n + 14); ii; ii = *(_QWORD *)(ii + 32) )
    {
      v77 = *(_DWORD *)(ii + 20);
      v81 = *n != -1;
      v78 = (const unsigned __int16 *)(v75 + 2LL * *(unsigned int *)(ii + 16));
      rc = *(struct tagRECT *)ii;
      CMarkup::ThemedDrawText(this, a2, v78, v77, &rc, v65, v81);
    }
    if ( v98 && *n == *((_DWORD *)this + 8) && *n != -1 )
    {
      SetTextColor(a2, color);
      for ( jj = *((_QWORD *)n + 14); jj; jj = *(_QWORD *)(jj + 32) )
        DrawFocusRect(a2, (const RECT *)jj);
    }
    if ( (v103 & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD, __int64, HDC, _QWORD, _DWORD, _DWORD, int, _QWORD))(**((_QWORD **)this + 10) + 48LL))(
        *((_QWORD *)this + 10),
        65538,
        a2,
        0,
        *((_DWORD *)this + 2),
        *n,
        v68 != 0 ? 32 : 4,
        0);
  }
  if ( (v103 & 0x10) != 0 )
    (*(void (__fastcall **)(_QWORD, __int64, HDC, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD))(**((_QWORD **)this + 10)
                                                                                         + 48LL))(
      *((_QWORD *)this + 10),
      2,
      a2,
      0,
      *((_DWORD *)this + 2),
      0,
      0,
      0);
LABEL_177:
  SetTextColor(a2, color);
  if ( h )
    SelectObject(a2, h);
}

```

## disassembly

```asm
0x1800c7c84  mov     [rsp-8+arg_18], rbx
0x1800c7c89  push    rbp
0x1800c7c8a  push    rsi
0x1800c7c8b  push    rdi
0x1800c7c8c  push    r12
0x1800c7c8e  push    r13
0x1800c7c90  push    r14
0x1800c7c92  push    r15
0x1800c7c94  lea     rbp, [rsp-450h]
0x1800c7c9c  sub     rsp, 550h
0x1800c7ca3  mov     rax, cs:__security_cookie
0x1800c7caa  xor     rax, rsp
0x1800c7cad  mov     [rbp+480h+var_40], rax
0x1800c7cb4  xor     r15d, r15d
0x1800c7cb7  mov     [rbp+480h+var_4EC], r9d
0x1800c7cbb  mov     r13d, r9d
0x1800c7cbe  mov     r12, r8
0x1800c7cc1  mov     r14, rdx
0x1800c7cc4  mov     [rbp+480h+var_4E0], r8
0x1800c7cc8  mov     rbx, rcx
0x1800c7ccb  cmp     [rcx+10h], r15
0x1800c7ccf  jz      loc_1800C86C9
0x1800c7cd5  mov     rcx, rdx; hdc
0x1800c7cd8  call    cs:__imp_GetTextColor
0x1800c7cde  lea     edx, [r15+6]; type
0x1800c7ce2  mov     rcx, r14; hdc
0x1800c7ce5  mov     [rbp+480h+color], eax
0x1800c7ce8  call    cs:__imp_GetCurrentObject
0x1800c7cee  mov     rsi, [rbx+40h]
0x1800c7cf2  lea     edx, [r15+1]; unsigned int
0x1800c7cf6  mov     rcx, rbx; this
0x1800c7cf9  mov     [rbp+480h+h], rax
0x1800c7cfd  call    ?IsMarkupState@CMarkup@@AEAAHK@Z; CMarkup::IsMarkupState(ulong)
0x1800c7d02  mov     rcx, [rbx+78h]; hTheme
0x1800c7d06  xorps   xmm0, xmm0
0x1800c7d09  movups  xmmword ptr [rbp+480h+tm.tmOverhang], xmm0
0x1800c7d0d  test    rsi, rsi
0x1800c7d10  mov     [rbp+480h+var_4E8], eax
0x1800c7d13  movups  xmmword ptr [rbp+480h+tm.tmFirstChar], xmm0
0x1800c7d17  cmovz   rsi, cs:g_hfontSystem
0x1800c7d1f  mov     edi, r15d
0x1800c7d22  mov     [rbp+480h+var_4D8], rsi
0x1800c7d26  mov     [rbp+480h+var_440], r15d
0x1800c7d2a  movups  xmmword ptr [rbp+480h+tm.tmHeight], xmm0
0x1800c7d2e  movups  xmmword ptr [rbp+480h+tm.tmExternalLeading], xmm0
0x1800c7d32  movups  xmm0, xmmword ptr [r12]
0x1800c7d37  mov     [rbx+28h], r15d
0x1800c7d3b  movdqu  xmmword ptr [rbp+480h+rcSrc.left], xmm0
0x1800c7d40  test    rcx, rcx
0x1800c7d43  jnz     short loc_1800C7D92
0x1800c7d45  mov     rdx, rsi; h
0x1800c7d48  mov     rcx, r14; hdc
0x1800c7d4b  call    cs:__imp_SelectObject
0x1800c7d51  lea     rdx, [rbp+480h+tm]; lptm
0x1800c7d55  mov     rcx, r14; hdc
0x1800c7d58  call    cs:__imp_GetTextMetricsW
0x1800c7d5e  mov     eax, [rbp+480h+tm.tmExternalLeading]
0x1800c7d61  mov     rcx, r14; hdc
0x1800c7d64  mov     rdx, [rbx+38h]; h
0x1800c7d68  test    eax, eax
0x1800c7d6a  cmovg   edi, eax
0x1800c7d6d  mov     [rsp+580h+var_508], edi
0x1800c7d71  call    cs:__imp_SelectObject
0x1800c7d77  lea     rdx, [rbp+480h+tm]; lptm
0x1800c7d7b  mov     rcx, r14; hdc
0x1800c7d7e  call    cs:__imp_GetTextMetricsW
0x1800c7d84  cmp     [rbp+480h+tm.tmExternalLeading], edi
0x1800c7d87  jle     short loc_1800C7DE9
0x1800c7d89  mov     eax, [rbp+480h+tm.tmExternalLeading]
0x1800c7d8c  mov     [rsp+580h+var_508], eax
0x1800c7d90  jmp     short loc_1800C7DE9
0x1800c7d92  mov     r9d, [rbx+84h]; iStateId
0x1800c7d99  lea     rax, [rbp+480h+tm]
0x1800c7d9d  mov     r8d, [rbx+80h]; iPartId
0x1800c7da4  mov     rdx, r14; hdc
0x1800c7da7  mov     [rsp+580h+ptm], rax; ptm
0x1800c7dac  call    cs:__imp_GetThemeTextMetrics
0x1800c7db2  mov     eax, [rbp+480h+tm.tmExternalLeading]
0x1800c7db5  mov     rdx, r14; hdc
0x1800c7db8  mov     r9d, [rbx+88h]; iStateId
0x1800c7dbf  test    eax, eax
0x1800c7dc1  mov     r8d, [rbx+80h]; iPartId
0x1800c7dc8  mov     rcx, [rbx+78h]; hTheme
0x1800c7dcc  cmovg   edi, eax
0x1800c7dcf  lea     rax, [rbp+480h+tm]
0x1800c7dd3  mov     [rsp+580h+ptm], rax; ptm
0x1800c7dd8  call    cs:__imp_GetThemeTextMetrics
0x1800c7dde  cmp     [rbp+480h+tm.tmExternalLeading], edi
0x1800c7de1  cmovg   edi, [rbp+480h+tm.tmExternalLeading]
0x1800c7de5  mov     [rsp+580h+var_508], edi
0x1800c7de9  mov     edi, 1
0x1800c7dee  cmp     [rbx+60h], edi
0x1800c7df1  jz      short loc_1800C7E08
0x1800c7df3  lea     rcx, [rbx+64h]; lprc1
0x1800c7df7  mov     rdx, r12; lprc2
0x1800c7dfa  call    cs:__imp_EqualRect
0x1800c7e00  test    eax, eax
0x1800c7e02  jnz     loc_1800C8437
0x1800c7e08  mov     r15, [rbx+10h]
0x1800c7e0c  xor     eax, eax
0x1800c7e0e  mov     dword ptr [rsp+580h+var_520], eax
0x1800c7e12  xor     r11d, r11d
0x1800c7e15  mov     eax, [rbx+5Ch]
0x1800c7e18  and     eax, 0FFFFFFF0h
0x1800c7e1b  mov     [rsp+580h+var_530], r11d
0x1800c7e20  or      eax, 420h
0x1800c7e25  mov     [rsp+580h+var_504], r11d
0x1800c7e2a  mov     [rbp+480h+var_4F4], eax
0x1800c7e2d  mov     [rbp+480h+var_4C0], r15
0x1800c7e31  test    r15, r15
0x1800c7e34  jz      loc_1800C833B
0x1800c7e3a  cmp     qword ptr [rbx+78h], 0
0x1800c7e3f  jnz     short loc_1800C7E5C
0x1800c7e41  cmp     dword ptr [r15], 0FFFFFFFFh
0x1800c7e45  mov     rdx, rsi
0x1800c7e48  jnz     short loc_1800C7E4E
0x1800c7e4a  mov     rdx, [rbx+38h]; h
0x1800c7e4e  test    rdx, rdx
0x1800c7e51  jz      short loc_1800C7E5C
0x1800c7e53  mov     rcx, r14; hdc
0x1800c7e56  call    cs:__imp_SelectObject
0x1800c7e5c  mov     rcx, [r15+78h]; lpString
0x1800c7e60  call    cs:__imp_lstrlenW
0x1800c7e66  mov     r13, [r15+78h]
0x1800c7e6a  mov     rcx, r15; this
0x1800c7e6d  mov     esi, eax
0x1800c7e6f  mov     [rsp+580h+var_52C], eax
0x1800c7e73  mov     [rsp+580h+var_518], r13
0x1800c7e78  mov     [rbp+480h+var_4D0], r13
0x1800c7e7c  call    ?FreeRects@TEXTBLOCK@@QEAAXXZ; TEXTBLOCK::FreeRects(void)
0x1800c7e81  mov     r11d, [rsp+580h+var_530]
0x1800c7e86  mov     [rbp+480h+var_4F8], edi
0x1800c7e89  test    esi, esi
0x1800c7e8b  jle     loc_1800C8322
0x1800c7e91  lea     eax, [r11+1]
0x1800c7e95  mov     [rbp+480h+var_4F0], eax
0x1800c7e98  cmp     eax, 0FFh
0x1800c7e9d  jnb     loc_1800C8322
0x1800c7ea3  test    byte ptr [rbx+5Ch], 20h
0x1800c7ea7  jz      short loc_1800C7EB2
0x1800c7ea9  test    r11d, r11d
0x1800c7eac  jg      loc_1800C8322
0x1800c7eb2  xorps   xmm0, xmm0
0x1800c7eb5  mov     [rsp+580h+var_510], 0
0x1800c7ebd  xorps   xmm1, xmm1
0x1800c7ec0  lea     rdx, [rbp+480h+rcSrc]; lprcSrc
0x1800c7ec4  lea     rcx, [rbp+480h+rcDst]; lprcDst
0x1800c7ec8  movups  xmmword ptr [rbp+480h+rc.left], xmm0
0x1800c7ecc  movups  xmmword ptr [rbp+480h+rcDst.left], xmm1
0x1800c7ed0  call    cs:__imp_CopyRect
0x1800c7ed6  xor     edi, edi
0x1800c7ed8  test    esi, esi
0x1800c7eda  jz      short loc_1800C7F01
0x1800c7edc  lea     edx, [rdi+1]
0x1800c7edf  lea     ecx, [rdi+0Dh]
0x1800c7ee2  cmp     word ptr [r13+rdi*2+0], 0Ah
0x1800c7ee9  jz      loc_1800C8080
0x1800c7eef  cmp     [r13+rdi*2+0], cx
0x1800c7ef5  jz      loc_1800C8088
0x1800c7efb  add     edi, edx
0x1800c7efd  cmp     edi, esi
0x1800c7eff  jl      short loc_1800C7EE2
0x1800c7f01  xor     ecx, ecx
0x1800c7f03  mov     [rbp+480h+var_4FC], 0
0x1800c7f0a  xor     r13d, r13d
0x1800c7f0d  mov     edi, esi
0x1800c7f0f  xor     edx, edx
0x1800c7f11  mov     eax, [rbp+480h+rcDst.right]
0x1800c7f14  mov     [rsp+580h+var_524], edx
0x1800c7f18  mov     [rsp+580h+var_528], ecx
0x1800c7f1c  cmp     eax, [rbp+480h+rcDst.left]
0x1800c7f1f  jz      loc_1800C8120
0x1800c7f25  mov     r8, [rsp+580h+var_518]; unsigned __int16 *
0x1800c7f2a  mov     esi, [rbp+480h+var_4F4]
0x1800c7f2d  xor     eax, eax
0x1800c7f2f  cmp     dword ptr [r15], 0FFFFFFFFh
0x1800c7f33  mov     r9d, edi; int
0x1800c7f36  mov     rdx, r14; HDC
0x1800c7f39  mov     rcx, rbx; this
0x1800c7f3c  setnz   al
0x1800c7f3f  mov     [rsp+580h+var_550], eax; int
0x1800c7f43  lea     rax, [rbp+480h+rcDst]
0x1800c7f47  mov     [rsp+580h+var_558], esi; unsigned int
0x1800c7f4b  mov     [rsp+580h+ptm], rax; struct tagRECT *
0x1800c7f50  call    ?ThemedDrawText@CMarkup@@AEAAHPEAUHDC__@@PEBGHPEAUtagRECT@@IH@Z; CMarkup::ThemedDrawText(HDC__ *,ushort const *,int,tagRECT *,uint,int)
0x1800c7f55  mov     eax, [rbp+480h+rcDst.bottom]
0x1800c7f58  sub     eax, [rbp+480h+rcDst.top]
0x1800c7f5b  mov     dword ptr [rsp+580h+var_520], eax
0x1800c7f5f  test    edi, edi
0x1800c7f61  jnz     short loc_1800C7FB1
0x1800c7f63  cmp     r13d, 1
0x1800c7f67  jnz     short loc_1800C7FB1
0x1800c7f69  mov     eax, [r12]
0x1800c7f6d  lea     r8, aA_1; "a"
0x1800c7f74  mov     [rbp+480h+rcDst.left], eax
0x1800c7f77  mov     r9d, r13d; int
0x1800c7f7a  mov     eax, [r12+8]
0x1800c7f7f  mov     rdx, r14; HDC
0x1800c7f82  mov     [rbp+480h+rcDst.right], eax
0x1800c7f85  mov     rcx, rbx; this
0x1800c7f88  xor     eax, eax
0x1800c7f8a  cmp     dword ptr [r15], 0FFFFFFFFh
0x1800c7f8e  setnz   al
0x1800c7f91  mov     [rsp+580h+var_550], eax; int
0x1800c7f95  lea     rax, [rbp+480h+rcDst]
0x1800c7f99  mov     [rsp+580h+var_558], esi; unsigned int
0x1800c7f9d  mov     [rsp+580h+ptm], rax; struct tagRECT *
0x1800c7fa2  call    ?ThemedDrawText@CMarkup@@AEAAHPEAUHDC__@@PEBGHPEAUtagRECT@@IH@Z; CMarkup::ThemedDrawText(HDC__ *,ushort const *,int,tagRECT *,uint,int)
0x1800c7fa7  mov     ecx, [rbp+480h+rcDst.left]
0x1800c7faa  mov     [rbp+480h+rcDst.right], ecx
0x1800c7fad  mov     dword ptr [rsp+580h+var_520], eax
0x1800c7fb1  mov     edx, [rbp+480h+rcSrc.right]
0x1800c7fb4  mov     ecx, [rbp+480h+rcDst.right]
0x1800c7fb7  mov     r8d, [rbp+480h+rcSrc.left]
0x1800c7fbb  sub     edx, r8d
0x1800c7fbe  sub     ecx, [rbp+480h+rcDst.left]
0x1800c7fc1  cmp     ecx, edx
0x1800c7fc3  jle     short loc_1800C802C
0x1800c7fc5  movzx   r12d, [rbp+480h+tm.tmBreakChar]
0x1800c7fca  lea     r15d, [rdi-1]
0x1800c7fce  xor     ecx, ecx
0x1800c7fd0  mov     esi, r15d
0x1800c7fd3  mov     [rsp+580h+var_510], ecx
0x1800c7fd7  mov     [rsp+580h+var_50C], ecx
0x1800c7fdb  test    r15d, r15d
0x1800c7fde  js      loc_1800C80B8
0x1800c7fe4  mov     rcx, [rsp+580h+var_518]; unsigned __int16 *
0x1800c7fe9  lea     r9, [rsp+580h+var_50C]; int *
0x1800c7fee  movzx   r8d, r12w; unsigned __int16
0x1800c7ff2  mov     edx, esi; int
0x1800c7ff4  call    ?_IsLineBreakChar@CMarkup@@CAHPEBGHGPEAH@Z; CMarkup::_IsLineBreakChar(ushort const *,int,ushort,int *)
0x1800c7ff9  test    eax, eax
0x1800c7ffb  js      loc_1800C80A3
0x1800c8001  mov     ecx, [rsp+580h+var_50C]
0x1800c8005  mov     [rsp+580h+var_510], ecx
0x1800c8009  cmp     eax, edi
0x1800c800b  jnz     short loc_1800C8015
0x1800c800d  test    ecx, ecx
0x1800c800f  jz      loc_1800C80AB
0x1800c8015  mov     r12, [rbp+480h+var_4E0]
0x1800c8019  mov     edi, eax
0x1800c801b  mov     r8, [rsp+580h+var_518]
0x1800c8020  mov     r15, [rbp+480h+var_4C0]
0x1800c8024  test    edi, edi
0x1800c8026  jg      loc_1800C7F2A
0x1800c802c  mov     esi, [rsp+580h+var_52C]
0x1800c8030  mov     ecx, [rsp+580h+var_528]
0x1800c8034  mov     edx, [rsp+580h+var_524]
0x1800c8038  test    r13d, r13d
0x1800c803b  jz      short loc_1800C8049
0x1800c803d  xor     eax, eax
0x1800c803f  cmp     [rbp+480h+var_4FC], edi
0x1800c8042  cmovg   edx, eax
0x1800c8045  mov     [rsp+580h+var_524], edx
0x1800c8049  mov     r15d, edi
0x1800c804c  cmp     edi, esi
0x1800c804e  jge     short loc_1800C8058
0x1800c8050  test    edx, edx
0x1800c8052  jz      short loc_1800C8058
0x1800c8054  lea     r15d, [rcx+rdi]
0x1800c8058  mov     ecx, [rsp+580h+var_504]
0x1800c805c  test    ecx, ecx
0x1800c805e  jz      loc_1800C8127
0x1800c8064  mov     r13, [rsp+580h+var_518]
0x1800c8069  mov     r11d, [rsp+580h+var_530]
0x1800c806e  movsxd  rax, r15d
0x1800c8071  lea     r13, [r13+rax*2+0]
0x1800c8076  mov     [rsp+580h+var_518], r13
0x1800c807b  jmp     loc_1800C82BE
0x1800c8080  cmp     [r13+rdi*2+0], cx
0x1800c8086  jnz     short loc_1800C8096
0x1800c8088  cmp     word ptr [r13+rdi*2+2], 0Ah
0x1800c808f  mov     ecx, 2
0x1800c8094  jz      short loc_1800C8098
0x1800c8096  mov     ecx, edx
0x1800c8098  mov     [rbp+480h+var_4FC], edi
0x1800c809b  mov     r13d, edx
0x1800c809e  jmp     loc_1800C7F11
0x1800c80a3  mov     eax, [rsp+580h+var_50C]
0x1800c80a7  mov     [rsp+580h+var_510], eax
0x1800c80ab  sub     esi, 1
0x1800c80ae  jns     loc_1800C7FE4
0x1800c80b4  mov     r8d, [rbp+480h+rcSrc.left]
0x1800c80b8  mov     r12, [rbp+480h+var_4E0]
0x1800c80bc  mov     eax, edi
0x1800c80be  movsxd  rdx, edi
0x1800c80c1  xor     edi, edi
0x1800c80c3  cmp     [r12], r8d
0x1800c80c7  jnz     loc_1800C802C
0x1800c80cd  test    eax, eax
0x1800c80cf  jle     loc_1800C802C
0x1800c80d5  mov     edi, r15d
0x1800c80d8  cmp     r15d, 1
0x1800c80dc  jle     loc_1800C801B
0x1800c80e2  mov     r8, [rsp+580h+var_518]
0x1800c80e7  mov     ecx, 2400h
0x1800c80ec  mov     r9d, 3FFh
0x1800c80f2  add     cx, [r8+rdx*2-2]
0x1800c80f8  cmp     cx, r9w
0x1800c80fc  ja      loc_1800C8020
  ... truncated ...
```
