# Header_DrawItem(HD *,HDC__ *,int,int,tagRECT const *,uint,int)

- ea: `0x180009d9c`
- end: `0x18000b1e5`
- name: `?Header_DrawItem@@YAXPEAUHD@@PEAUHDC__@@HHPEBUtagRECT@@IH@Z`
- size: `5193`
- prototype: `void __usercall(struct HD *@<rcx>, HDC hdc@<rdx>, int@<r8d>, int@<r9d>, RECT *lprect, char, int)`
- caller_count: `2`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180008184`
- `0x1801360cc`

## callees

- `0x180007fc4`
- `0x18000805c`
- `0x1800099c0`
- `0x180009d38`
- `0x180009d9c`
- `0x18000b1ec`
- `0x18000b5c4`
- `0x180019b30`
- `0x180034b4c`
- `0x180036850`
- `0x18009df50`
- `0x1800b07e0`
- `0x1800bfaf0`
- `0x1800cb060`
- `0x1800ede24`
- `0x1800ffda0`
- `0x180103594`
- `0x180107fe0`
- `0x180114520`
- `0x180114ebc`
- `0x180135b30`
- `0x180136850`
- `0x180137404`
- `0x1801cebfc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a957`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a957`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000acf6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000acf6`
- `GDI32!DeleteObject` at `0x18000a80c`
- `GDI32!DeleteObject` at `0x18000a815`
- `GDI32!DeleteObject` at `0x18000a81e`
- `GDI32!DeleteObject` at `0x18000a8e1`
- `GDI32!DeleteObject` at `0x18000b0b5`
- `GDI32!DeleteObject` at `0x18000b0be`
- `GDI32!DeleteObject` at `0x18000b1c9`
- `GDI32!DeleteObject` at `0x18000a80c`
- `GDI32!DeleteObject` at `0x18000a815`
- `GDI32!DeleteObject` at `0x18000a81e`
- `GDI32!DeleteObject` at `0x18000a8e1`
- `GDI32!DeleteObject` at `0x18000b0b5`
- `GDI32!DeleteObject` at `0x18000b0be`
- `GDI32!DeleteObject` at `0x18000b1c9`
- `GDI32!RestoreDC` at `0x18000a3aa`
- `GDI32!RestoreDC` at `0x18000a7fc`
- `GDI32!RestoreDC` at `0x18000a3aa`
- `GDI32!RestoreDC` at `0x18000a7fc`
- `GDI32!GetObjectW` at `0x18000ade0`
- `GDI32!GetObjectW` at `0x18000ade0`
- `GDI32!SetTextColor` at `0x18000a476`
- `GDI32!SetTextColor` at `0x18000aa73`
- `GDI32!SetTextColor` at `0x18000a476`
- `GDI32!SetTextColor` at `0x18000aa73`
- `GDI32!PatBlt` at `0x18000a9e2`
- `GDI32!PatBlt` at `0x18000a9e2`
- `GDI32!SaveDC` at `0x18000a6c0`
- `GDI32!SaveDC` at `0x18000a6c0`
- `GDI32!CombineRgn` at `0x18000a7b4`
- `GDI32!CombineRgn` at `0x18000a8d8`
- `GDI32!CombineRgn` at `0x18000b0ac`
- `GDI32!CombineRgn` at `0x18000b1c0`
- `GDI32!CombineRgn` at `0x18000a7b4`
- `GDI32!CombineRgn` at `0x18000a8d8`
- `GDI32!CombineRgn` at `0x18000b0ac`
- `GDI32!CombineRgn` at `0x18000b1c0`
- `GDI32!SelectClipRgn` at `0x18000a7c0`
- `GDI32!SelectClipRgn` at `0x18000a7c0`
- `GDI32!CreateRectRgn` at `0x18000a797`
- `GDI32!CreateRectRgn` at `0x18000b094`
- `GDI32!CreateRectRgn` at `0x18000b0e4`
- `GDI32!CreateRectRgn` at `0x18000b1a8`
- `GDI32!CreateRectRgn` at `0x18000a797`
- `GDI32!CreateRectRgn` at `0x18000b094`
- `GDI32!CreateRectRgn` at `0x18000b0e4`
- `GDI32!CreateRectRgn` at `0x18000b1a8`
- `GDI32!GetTextExtentPointW` at `0x18000ad0e`
- `GDI32!GetTextExtentPointW` at `0x18000ad0e`
- `GDI32!GetBkColor` at `0x18000a066`
- `GDI32!GetBkColor` at `0x18000a8fa`
- `GDI32!GetBkColor` at `0x18000a066`
- `GDI32!GetBkColor` at `0x18000a8fa`
- `GDI32!GetTextColor` at `0x18000a05a`
- `GDI32!GetTextColor` at `0x18000a8ef`
- `GDI32!GetTextColor` at `0x18000a05a`
- `GDI32!GetTextColor` at `0x18000a8ef`
- `GDI32!ExtTextOutW` at `0x18000a7f0`
- `GDI32!ExtTextOutW` at `0x18000a7f0`
- `GDI32!CreateRectRgnIndirect` at `0x18000a66e`
- `GDI32!CreateRectRgnIndirect` at `0x18000a77b`
- `GDI32!CreateRectRgnIndirect` at `0x18000a8c0`
- `GDI32!CreateRectRgnIndirect` at `0x18000b05b`
- `GDI32!CreateRectRgnIndirect` at `0x18000a66e`
- `GDI32!CreateRectRgnIndirect` at `0x18000a77b`
- `GDI32!CreateRectRgnIndirect` at `0x18000a8c0`
- `GDI32!CreateRectRgnIndirect` at `0x18000b05b`
- `USER32!DrawFocusRect` at `0x18000a486`
- `USER32!DrawFocusRect` at `0x18000aa80`
- `USER32!DrawFocusRect` at `0x18000a486`
- `USER32!DrawFocusRect` at `0x18000aa80`
- `USER32!InflateRect` at `0x18000a460`
- `USER32!InflateRect` at `0x18000aa5f`
- `USER32!InflateRect` at `0x18000a460`
- `USER32!InflateRect` at `0x18000aa5f`
- `USER32!SendMessageW` at `0x18000a043`
- `USER32!SendMessageW` at `0x18000a043`
- `USER32!GetSystemMetrics` at `0x18000a43d`
- `USER32!GetSystemMetrics` at `0x18000a44c`
- `USER32!GetSystemMetrics` at `0x18000a710`
- `USER32!GetSystemMetrics` at `0x18000aa3a`
- `USER32!GetSystemMetrics` at `0x18000aa4d`
- `USER32!GetSystemMetrics` at `0x18000ac3d`
- `USER32!GetSystemMetrics` at `0x18000ada6`
- `USER32!GetSystemMetrics` at `0x18000a43d`
- `USER32!GetSystemMetrics` at `0x18000a44c`
- `USER32!GetSystemMetrics` at `0x18000a710`
- `USER32!GetSystemMetrics` at `0x18000aa3a`
- `USER32!GetSystemMetrics` at `0x18000aa4d`
- `USER32!GetSystemMetrics` at `0x18000ac3d`
- `USER32!GetSystemMetrics` at `0x18000ada6`
- `USER32!GetDlgCtrlID` at `0x180009fee`
- `USER32!GetDlgCtrlID` at `0x180009fee`
- `USER32!GetSysColor` at `0x18000a46b`
- `USER32!GetSysColor` at `0x18000a962`
- `USER32!GetSysColor` at `0x18000a970`
- `USER32!GetSysColor` at `0x18000aa68`
- `USER32!GetSysColor` at `0x18000b100`
- `USER32!GetSysColor` at `0x18000a46b`
- `USER32!GetSysColor` at `0x18000a962`
- `USER32!GetSysColor` at `0x18000a970`
- `USER32!GetSysColor` at `0x18000aa68`
- `USER32!GetSysColor` at `0x18000b100`
- `UxTheme!DrawThemeBackground` at `0x18000a257`
- `UxTheme!DrawThemeBackground` at `0x18000a257`
- `UxTheme!GetThemeBackgroundContentRect` at `0x18000a175`
- `UxTheme!GetThemeBackgroundContentRect` at `0x18000a175`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18000af5f`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18000af5f`

## pseudocode

```c
void __fastcall Header_DrawItem(struct HD *a1, HDC hdc, int a3, int a4, RECT *lprect, char a6, int a7)
{
  int v7; // ebx
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  bool v13; // zf
  __int64 v14; // r12
  unsigned int v15; // r13d
  int IsTracking; // eax
  int v17; // r11d
  int v18; // ecx
  __int64 v19; // r15
  _DWORD *v20; // rax
  _DWORD *v21; // rbx
  _DWORD *v22; // rdx
  int v23; // r10d
  __int64 v24; // r8
  unsigned int v25; // eax
  int v26; // r9d
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  HWND v30; // rcx
  unsigned int DlgCtrlID; // eax
  struct tagRECT v32; // xmm0
  int v33; // ebx
  HWND v34; // rcx
  HDC v35; // r15
  unsigned int fmt; // r15d
  void *v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rdx
  int v40; // esi
  __int64 v41; // rdx
  int v42; // edi
  int left; // edx
  void *v44; // rcx
  HDC v45; // rbx
  HRGN RectRgn; // rsi
  int v47; // edx
  __int64 v48; // r10
  int v49; // eax
  COLORREF v50; // esi
  _DWORD *v51; // rdi
  char *v52; // rcx
  int v53; // ebx
  int v54; // eax
  COLORREF v55; // eax
  RECT v56; // xmm0
  unsigned int SortColor; // ebx
  COLORREF v58; // eax
  int v59; // ecx
  int v60; // r8d
  __int16 v61; // ax
  int v62; // r8d
  int v63; // ebx
  HRGN v64; // r12
  HRGN v65; // r15
  LONG v66; // edi
  int v67; // eax
  int dy; // edi
  int v69; // esi
  int v70; // ebx
  int v71; // eax
  HRGN v72; // rbx
  HRGN v73; // rax
  HRGN v74; // rdi
  HRGN v75; // rbx
  struct _HD_ITEMW *p_Buffer; // rdi
  int v77; // r15d
  int v78; // ebx
  int SystemMetrics; // eax
  COLORREF SysColor; // eax
  int v81; // r9d
  int v82; // eax
  int v83; // eax
  int v84; // ecx
  int v85; // edx
  int v86; // r9d
  int v87; // edx
  int v88; // r8d
  int v89; // ecx
  int v90; // eax
  void *v91; // rcx
  int ObjectW; // eax
  LONG v93; // eax
  int *v94; // rdx
  int v95; // ecx
  LONG v96; // eax
  int v97; // ecx
  int v98; // r8d
  LONG right; // eax
  HRGN v100; // rax
  unsigned int v101; // r8d
  struct _HD_ITEMW **v102; // rbx
  HRGN v103; // rbx
  struct DPISCALEINFO *pBoundingRect; // [rsp+20h] [rbp-E0h]
  struct tagSIZE *rgbBk; // [rsp+38h] [rbp-C8h]
  struct DPISCALEINFO *rgbFg; // [rsp+40h] [rbp-C0h]
  COLORREF rgbFga; // [rsp+40h] [rbp-C0h]
  int v108; // [rsp+70h] [rbp-90h]
  unsigned int iStateId; // [rsp+78h] [rbp-88h]
  COLORREF TextColor; // [rsp+80h] [rbp-80h]
  int v114; // [rsp+90h] [rbp-70h]
  int v115; // [rsp+94h] [rbp-6Ch]
  int v116; // [rsp+98h] [rbp-68h]
  char v117[4]; // [rsp+9Ch] [rbp-64h]
  int nSavedDC; // [rsp+A0h] [rbp-60h]
  int v119; // [rsp+A4h] [rbp-5Ch]
  COLORREF BkColor; // [rsp+A8h] [rbp-58h]
  int v121; // [rsp+ACh] [rbp-54h]
  int v122; // [rsp+B0h] [rbp-50h]
  const WCHAR *pszText; // [rsp+B8h] [rbp-48h]
  _DWORD *v124; // [rsp+C0h] [rbp-40h]
  char v125; // [rsp+C8h] [rbp-38h]
  int y1[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v127; // [rsp+E0h] [rbp-20h]
  RECT y; // [rsp+E8h] [rbp-18h] BYREF
  LPARAM lParam[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v130; // [rsp+110h] [rbp+10h]
  HDC v131; // [rsp+120h] [rbp+20h]
  struct tagRECT v132; // [rsp+128h] [rbp+28h]
  __int64 v133; // [rsp+138h] [rbp+38h]
  __int64 v134; // [rsp+140h] [rbp+40h] BYREF
  char v135[16]; // [rsp+148h] [rbp+48h] BYREF
  int v136; // [rsp+158h] [rbp+58h]
  HDC v137; // [rsp+160h] [rbp+60h]
  RECT v138; // [rsp+168h] [rbp+68h]
  __int64 v139; // [rsp+178h] [rbp+78h]
  int v140; // [rsp+180h] [rbp+80h]
  __int64 v141; // [rsp+188h] [rbp+88h]
  int cy[4]; // [rsp+190h] [rbp+90h] BYREF
  struct tagRECT v143; // [rsp+1A0h] [rbp+A0h] BYREF
  RECT v144; // [rsp+1B0h] [rbp+B0h] BYREF
  RECT rect; // [rsp+1C0h] [rbp+C0h] BYREF
  struct tagSIZE sz; // [rsp+1D0h] [rbp+D0h] BYREF
  struct tagRECT rc; // [rsp+1E0h] [rbp+E0h] BYREF
  RECT pRect; // [rsp+1F0h] [rbp+F0h] BYREF
  struct _HD_ITEMW Buffer; // [rsp+200h] [rbp+100h] BYREF
  __int16 v150; // [rsp+280h] [rbp+180h] BYREF

  v7 = a3;
  v10 = Header_ItemOrderToIndex(a1, a3);
  v11 = *((_QWORD *)a1 + 14);
  if ( !v11 )
    return;
  if ( v10 < 0 )
    return;
  if ( v10 >= *(_DWORD *)v11 )
    return;
  v12 = *(_DWORD *)(v11 + 20) * v10;
  v13 = *(_QWORD *)(v11 + 8) + v12 == 0;
  v14 = *(_QWORD *)(v11 + 8) + v12;
  v127 = v14;
  if ( v13 )
    return;
  y = *lprect;
  v144 = y;
  pRect = y;
  v15 = *(_DWORD *)(v14 + 8) & 0xFFFFFFFC;
  v114 = *(_DWORD *)(v14 + 8) & 0x2000000;
  if ( (*(_DWORD *)(v14 + 8) & 0x1000000) == 0 )
    v15 = *(_DWORD *)(v14 + 8);
  if ( *((_QWORD *)a1 + 38) && !*((_DWORD *)a1 + 74) && (v15 & 0x600) != 0 )
  {
    SortColor = Header_OnGetSortColor(a1);
    if ( SortColor != Header_OnGetBkgColor(a1) )
    {
      v58 = Header_OnGetSortColor(a1);
      FillRectClr(hdc, lprect, v58);
    }
    v7 = a3;
  }
  IsTracking = Header_IsTracking(a1);
  v17 = a4;
  if ( IsTracking
    && (*((_DWORD *)a1 + 32) & 0x2002) == 2
    && *((_DWORD *)a1 + 30) == a4
    && (*((_BYTE *)a1 + 124) & 1) != 0 )
  {
    v18 = 1;
    v115 = 1;
  }
  else
  {
    v18 = 0;
    v115 = 0;
    if ( !IsTracking )
    {
LABEL_10:
      v122 = 0;
      goto LABEL_11;
    }
  }
  if ( (*((_DWORD *)a1 + 32) & 0x2000) == 0 )
    goto LABEL_10;
  if ( *((_DWORD *)a1 + 30) != a4 )
    goto LABEL_10;
  v122 = 1;
  if ( (*((_BYTE *)a1 + 124) & 1) == 0 )
    goto LABEL_10;
LABEL_11:
  v19 = *((_QWORD *)a1 + 38);
  if ( v19
    || (*((_BYTE *)a1 + 124) & 8) == 0
    || *((_DWORD *)a1 + 51) != v7
    || (v121 = 1, (*((_BYTE *)a1 + 48) & 1) != 0) )
  {
    v121 = 0;
  }
  v20 = &unk_1801F0264;
  v21 = &unk_1801F0270;
  if ( v18 )
  {
    v124 = (_DWORD *)((char *)a1 + 176);
    v22 = &unk_1801F0274;
    v20 = &unk_1801F0268;
LABEL_15:
    cy[0] = 2;
    v23 = v114;
    goto LABEL_16;
  }
  v52 = (char *)a1 + 176;
  v124 = (_DWORD *)((char *)a1 + 176);
  if ( a4 == *((_DWORD *)a1 + 44) && *((_DWORD *)a1 + 45) != 1 )
    goto LABEL_158;
  if ( (*((_BYTE *)a1 + 124) & 8) != 0 )
  {
    v82 = Header_ItemOrderToIndex(a1, *((_DWORD *)a1 + 51));
    v17 = a4;
    if ( a4 != v82 )
    {
      v52 = (char *)a1 + 176;
      goto LABEL_87;
    }
    v20 = &unk_1801F0264;
LABEL_158:
    v22 = &unk_1801F0270;
    goto LABEL_15;
  }
LABEL_87:
  v23 = v114;
  v124 = v52;
  v20 = &unk_1801F0260;
  v22 = &unk_1801F026C;
  cy[0] = (v114 != 0) + 1;
LABEL_16:
  v24 = *((int *)a1 + 74);
  if ( (v15 & 0x600) == 0 )
    v22 = v20;
  v25 = v22[6 * v24];
  iStateId = v25;
  if ( v17 != *v124 )
  {
    v26 = cy[0];
LABEL_20:
    iStateId = v25;
    goto LABEL_21;
  }
  if ( *((_DWORD *)a1 + 45) != 1 )
  {
    v26 = cy[0];
    goto LABEL_21;
  }
  v26 = 3;
  if ( (v15 & 0x600) == 0 )
    v21 = &unk_1801F0264;
  v25 = v21[6 * (int)v24];
  iStateId = v25;
  cy[0] = 3;
  if ( !v23 )
    goto LABEL_20;
LABEL_21:
  v27 = *((_QWORD *)a1 + 14);
  if ( v27
    && a3 >= 0
    && a3 < *(_DWORD *)v27
    && (v28 = *(_QWORD *)(v27 + 8) + (unsigned int)(*(_DWORD *)(v27 + 20) * a3)) != 0
    && (*(_DWORD *)(v28 + 8) & 0x1000000) != 0
    && (!v19 || v26 != 1) )
  {
    v116 = 1;
  }
  else
  {
    v116 = 0;
    if ( !v27 || a3 < 0 || a3 >= *(_DWORD *)v27 )
      goto LABEL_31;
  }
  v29 = (unsigned int)(*(_DWORD *)(v27 + 20) * a3) + *(_QWORD *)(v27 + 8);
  if ( !v29 || (*(_DWORD *)(v29 + 8) & 0x1000000) == 0 )
  {
LABEL_31:
    v119 = 0;
    goto LABEL_32;
  }
  v119 = *((_DWORD *)a1 + 69) + *((_DWORD *)a1 + 70);
LABEL_32:
  v134 = 0;
  memset_0(v135, 0, 0x48u);
  memset_0(&Buffer, 0, sizeof(Buffer));
  *(_OWORD *)y1 = 0;
  if ( (v15 & 0x8000) == 0 )
  {
    v56 = *lprect;
    v35 = hdc;
    v13 = (*((_BYTE *)a1 + 48) & 1) == 0;
    v140 = v115 != 0;
    v139 = a4;
    v137 = hdc;
    v138 = v56;
    v141 = *(_QWORD *)(v14 + 40);
    if ( v13 )
      v140 = (v115 != 0) | 0x200;
    if ( (*((_BYTE *)a1 + 20) & 0x20) == 0
      || (v136 = 65537, v61 = CCSendNotify(a1, 4294967284LL, &v134), v125 = v61, (v61 & 0xFE01) != 0) )
    {
      v125 = 0;
    }
    else if ( (v61 & 4) != 0 )
    {
      return;
    }
LABEL_34:
    nSavedDC = 0;
    TextColor = GetTextColor(v35);
    BkColor = GetBkColor(v35);
    if ( (*((_DWORD *)a1 + 4) & 0x100) != 0 )
    {
      Header_GetFilterRects(lprect, &v144, &y, (struct tagRECT *)y1, pBoundingRect);
      pRect = v144;
    }
    if ( (v15 & 0x40) != 0 )
      v144.left += 2 + GetSystemMetrics(45) + *((_DWORD *)a1 + 20);
    v143 = v144;
    *(_DWORD *)v117 = 32 * v115 + 4194374;
    rect = v144;
    v150 = 0;
    if ( (v15 & 0x6800) == 0 && (*((_DWORD *)a1 + 4) & 0x100) == 0 )
    {
      fmt = Buffer.fmt;
    }
    else
    {
      Buffer.pszText = (LPWSTR)&v150;
      wcscpy((wchar_t *)&Buffer, L"6");
      Buffer.cchTextMax = 260;
      Header_OnGetItem(a1, a4, &Buffer);
      LOBYTE(fmt) = Buffer.fmt;
      v108 = Buffer.fmt;
      if ( (Buffer.fmt & 0x1000000) == 0 )
      {
LABEL_43:
        v37 = (void *)*((_QWORD *)a1 + 38);
        if ( v37 )
        {
          GetThemeBackgroundContentRect(v37, hdc, 1, iStateId, &v144, &rect);
          v38 = *((_QWORD *)a1 + 38);
          v143 = rect;
        }
        else
        {
          v38 = 0;
        }
        v39 = *((_QWORD *)a1 + 14);
        v40 = cy[0];
        if ( v39
          && a3 >= 0
          && a3 < *(_DWORD *)v39
          && (v41 = (unsigned int)(*(_DWORD *)(v39 + 20) * a3) + *(_QWORD *)(v39 + 8)) != 0
          && (*(_DWORD *)(v41 + 8) & 0x1000000) != 0
          && (!v38 || cy[0] != 1) )
        {
          v144.right -= v119;
          rect.right -= v119;
          v143.right -= v119;
          v116 = 1;
        }
        else
        {
          v144.right = _mm_cvtsi128_si32(_mm_srli_si128(_mm_load_si128((const __m128i *)&v144), 8));
          v116 = 0;
        }
        if ( v38 || (v42 = 1, (v15 & 0x600) == 0) )
          v42 = 0;
        pszText = Buffer.pszText;
        if ( (v15 & 0x4000) == 0 || (v15 & 0x2800) == 0 && !v42 )
        {
          left = rect.left;
LABEL_57:
          if ( v116 )
          {
            *(RECT *)(v14 + 60) = pRect;
            v97 = *(_DWORD *)(v14 + 68);
            *(_DWORD *)(v14 + 60) = v97 - v119;
            *(_DWORD *)(v14 + 68) = v97 - *((_DWORD *)a1 + 70);
            left = rect.left;
          }
          v44 = (void *)*((_QWORD *)a1 + 38);
          v45 = hdc;
          if ( v44 )
          {
            DrawThemeBackground(v44, hdc, 1, iStateId, &pRect, 0);
            if ( v116 )
              DrawThemeBackgroundEx(*((HTHEME *)a1 + 38), hdc, (v114 != 0) + 5, v40, (LPCRECT)(v14 + 60), 0);
            left = rect.left;
          }
          RectRgn = 0;
          if ( (v15 & 0x600) != 0 )
          {
            v81 = v15 & 0x400;
            if ( *((_QWORD *)a1 + 38) )
              _Header_DrawThemedSortArrow(a1, hdc, &pRect, v81);
            else
              _Header_DrawSortArrow(a1, hdc, &v143, v81);
          }
          else if ( (v15 & 0x800) != 0 || (v15 & 0x2000) != 0 )
          {
            v62 = v108;
            v63 = 0;
            v64 = 0;
            v65 = 0;
            v66 = 0;
            rc = 0;
            if ( (v15 & 0x800) != 0 && (v15 & 0x2000) != 0 )
            {
              v62 = v108 ^ 0x2000;
              v63 = 1;
              Buffer.fmt = v108 ^ 0x2000;
            }
            if ( (a6 & 1) == 0 )
            {
              v66 = _Header_DrawBitmap(
                      hdc,
                      *((HIMAGELIST *)a1 + 19),
                      &Buffer,
                      &v143,
                      v62 & 3,
                      v117[0],
                      &rc,
                      *((_DWORD *)a1 + 50),
                      rgbFg);
              v64 = CreateRectRgnIndirect(&rc);
              v62 = Buffer.fmt;
              left = rect.left;
              pszText = Buffer.pszText;
              LOBYTE(v108) = Buffer.fmt;
            }
            if ( v63 )
            {
              v98 = v62 ^ 0x2800;
              Buffer.fmt = v98;
              if ( (v98 & 1) != 0 )
              {
                v143.right = v66;
                if ( (v98 & 0x4000) != 0 )
                {
                  if ( v143.left < left )
                    left = v143.left;
                  v143.right = left;
                }
                v143.left = v144.left;
              }
              else
              {
                v143.left = v66;
                if ( (v98 & 0x4000) != 0 )
                {
                  right = rect.right;
                  if ( v143.right > rect.right )
                    right = v143.right;
                  v143.left = right;
                }
                v143.right = v144.right;
              }
              if ( (a6 & 1) == 0 )
              {
                _Header_DrawBitmap(
                  hdc,
                  *((HIMAGELIST *)a1 + 19),
                  &Buffer,
                  &v143,
                  v98 & 1,
                  v117[0],
                  &rc,
                  *((_DWORD *)a1 + 50),
                  rgbFg);
                v100 = CreateRectRgnIndirect(&rc);
                LOBYTE(v98) = Buffer.fmt;
                v65 = v100;
                pszText = Buffer.pszText;
              }
              LOBYTE(v108) = v98;
            }
            if ( v64 )
            {
              if ( v65 )
              {
                RectRgn = CreateRectRgn(0, 0, 0, 0);
                CombineRgn(RectRgn, v64, v65, 2);
                DeleteObject(v64);
                DeleteObject(v65);
              }
              else
              {
                RectRgn = v64;
              }
            }
            else if ( v65 )
            {
              RectRgn = v65;
            }
            if ( (a6 & 1) != 0 && !RectRgn )
              RectRgn = CreateRectRgn(0, 0, 0, 0);
            v45 = hdc;
            v67 = SaveDC(hdc);
            LOBYTE(fmt) = v108;
            v14 = v127;
            nSavedDC = v67;
          }
          if ( (v15 & 0x4000) != 0 )
          {
            v47 = 32 * v115 + 4194374;
            if ( (fmt & 4) != 0 )
              v47 = *(_DWORD *)v117 | 0x800;
            v48 = *((_QWORD *)a1 + 38);
            v49 = BkColor;
            if ( v48 )
              v49 = -1;
            BkColor = v49;
            LODWORD(rgbBk) = fmt & 3;
            SHThemeDrawText(v48, v45, 1, iStateId, 0, pszText, &rect, rgbBk, v47, *((_DWORD *)a1 + 19));
            if ( RectRgn )
            {
              v75 = CreateRectRgnIndirect(&rect);
              CombineRgn(RectRgn, v75, RectRgn, 2);
              DeleteObject(v75);
            }
          }
          if ( (*((_DWORD *)a1 + 4) & 0x100) != 0 )
          {
            memset_0(&Buffer, 0, 0x80u);
            p_Buffer = &Buffer;
            v77 = ((fmt & 4) << 9) | 0x46;
            if ( (*(_DWORD *)(v14 + 80) & 0x8000) != 0 )
            {
              LoadStringW(g_hinst, 0x1050u, (LPWSTR)&Buffer, 64);
              TextColor = GetSysColor(17);
            }
            else
            {
              TextColor = GetSysColor(8);
              if ( (*(_DWORD *)(v14 + 80) & 0xF) != 0 )
              {
                if ( (*(_DWORD *)(v14 + 80) & 0xF) == 1 )
                {
                  StringCchPrintfW((unsigned __int16 *)&Buffer, 0x40u, L"%d", *(unsigned int *)(v14 + 104));
                }
                else if ( (*(_DWORD *)(v14 + 80) & 0xF) == 2 )
                {
                  v102 = (struct _HD_ITEMW **)(v14 + 88);
                  if ( *(_QWORD *)(v14 + 88) )
                    goto LABEL_246;
                  _FormatDate((const struct _SYSTEMTIME *)(v14 + 108), (unsigned __int16 *)&Buffer, v101, v15);
                  if ( LOWORD(Buffer.mask) )
                    Str_Set(v14 + 88, &Buffer);
                  if ( *v102 )
LABEL_246:
                    p_Buffer = *v102;
                }
              }
              else
              {
                p_Buffer = *(struct _HD_ITEMW **)(v14 + 88);
              }
            }
            GetSysColor(5);
            rgbFga = v77;
            v35 = hdc;
            LODWORD(rgbBk) = 0;
            SHThemeDrawText(0, hdc, 0, 0, 0, p_Buffer, &y, rgbBk, rgbFga, *((_DWORD *)a1 + 19));
            PatBlt(hdc, y.left, y.bottom, y.right - y.left, 1, 0x42u);
            Header_DrawFilterGlyph(a1, hdc, (const struct tagRECT *)y1, a3 == *((_DWORD *)a1 + 53));
            if ( RectRgn )
            {
              v103 = CreateRectRgn(y.left, y1[1], y1[2], y1[3]);
              CombineRgn(RectRgn, v103, RectRgn, 2);
              DeleteObject(v103);
            }
            if ( (*((_BYTE *)a1 + 124) & 8) != 0 && *((_DWORD *)a1 + 51) == a3 && (*((_BYTE *)a1 + 48) & 1) == 0 )
            {
              v78 = GetSystemMetrics(46) / -2;
              SystemMetrics = GetSystemMetrics(45);
              InflateRect(&y, SystemMetrics / -2, v78);
              SysColor = GetSysColor(8);
              SetTextColor(hdc, SysColor);
              DrawFocusRect(hdc, &y);
              v121 = 0;
            }
          }
          else
          {
            v35 = hdc;
          }
          if ( RectRgn )
          {
            if ( !*((_QWORD *)a1 + 38) )
            {
              v72 = CreateRectRgnIndirect(&pRect);
              if ( v72 )
              {
                v73 = CreateRectRgn(0, 0, 0, 0);
                v74 = v73;
                if ( v73 )
                {
                  CombineRgn(v73, v72, RectRgn, 3);
                  SelectClipRgn(v35, v74);
                  ExtTextOutW(v35, 0, 0, 2u, &pRect, 0, 0, 0);
                  RestoreDC(v35, nSavedDC);
                  nSavedDC = 0;
                  DeleteObject(v74);
                }
                DeleteObject(v72);
              }
            }
            DeleteObject(RectRgn);
          }
          if ( nSavedDC )
            RestoreDC(v35, nSavedDC);
          v33 = a4;
          v50 = TextColor;
          goto LABEL_79;
        }
        if ( *(_DWORD *)(v14 + 52) != 0x7FFFFFFF )
        {
          v59 = *(_DWORD *)(v14 + 48);
          if ( v59 != 0x7FFFFFFF && (!a7 || (v15 & 0x40) == 0) )
          {
LABEL_103:
            v60 = v59 + rect.left;
            v143.left = v59 + rect.left;
            left = *(_DWORD *)(v14 + 52) + rect.left;
            rect.left = left;
            if ( (v15 & 0x1000) != 0 || v42 )
            {
              v143.right = left + *(_DWORD *)(v14 + 56);
              rect.right = v143.left;
            }
            else
            {
              v143.right = left;
              rect.right = v60 + *(_DWORD *)(v14 + 56);
            }
            goto LABEL_57;
          }
        }
        sz = 0;
        if ( v38 )
        {
          rgbBk = &sz;
          SHGetThemeTextExtent(v38, hdc, v38, iStateId, Buffer.pszText);
        }
        else
        {
          v83 = lstrlenW(Buffer.pszText);
          GetTextExtentPointW(hdc, pszText, v83, &sz);
        }
        v84 = *((_DWORD *)a1 + 49);
        *(_QWORD *)cy = 0;
        sz.cx += 2 * v84;
        if ( (v15 & 0x800) != 0 )
        {
          ImageList_GetIconSize(*((HIMAGELIST *)a1 + 19), cy, &cy[1]);
LABEL_182:
          v85 = cy[0];
          goto LABEL_183;
        }
        if ( v42 )
        {
          v90 = GetSystemMetrics(45);
          cy[1] = sz.cy;
          v85 = sz.cy + 2 * v90;
        }
        else
        {
          if ( (v15 & 0x2000) == 0 )
            goto LABEL_182;
          v91 = *(void **)(v14 + 24);
          *(_OWORD *)lParam = 0;
          v130 = 0;
          ObjectW = GetObjectW(v91, 32, lParam);
          v85 = cy[0];
          if ( ObjectW )
            v85 = HIDWORD(lParam[0]);
        }
LABEL_183:
        v86 = v85 + 2 * *((_DWORD *)a1 + 50);
        v87 = v86 + sz.cx;
        cy[0] = v86;
        *(_DWORD *)(v14 + 56) = v86 + sz.cx;
        v88 = v144.right - v144.left;
        v89 = v144.right - v144.left - v87;
        if ( v89 >= 0 )
        {
          v88 = v87;
        }
        else
        {
          v89 = 0;
          *(_DWORD *)(v14 + 56) = v88;
        }
        if ( (v15 & 0x1000) == 0 && !v42 )
        {
          if ( (v15 & 3) != 0 )
          {
            if ( (v15 & 3) != 1 )
            {
              if ( (v15 & 3) == 2 )
                *(_DWORD *)(v14 + 48) = v143.left + ((unsigned int)v89 >> 1);
              goto LABEL_201;
            }
            v93 = v143.right - v88;
          }
          else
          {
            v93 = v143.left;
          }
          *(_DWORD *)(v14 + 48) = v93;
LABEL_201:
          v94 = (int *)(v14 + 48);
          v95 = *(_DWORD *)(v14 + 48);
          *(_DWORD *)(v14 + 52) = v86 + v95;
          if ( v86 + v95 > v144.right )
            *(_DWORD *)(v14 + 52) = v144.right;
LABEL_215:
          v59 = v95 - v143.left;
          *v94 = v59;
          *(_DWORD *)(v14 + 52) -= rect.left;
          goto LABEL_103;
        }
        if ( (v15 & 3) != 0 )
        {
          if ( (v15 & 3) == 1 )
          {
            v96 = rect.right - v88;
          }
          else
          {
            if ( (v15 & 3) != 2 )
              goto LABEL_210;
            v96 = rect.left + ((unsigned int)v89 >> 1);
          }
        }
        else
        {
          v96 = rect.left;
        }
        *(_DWORD *)(v14 + 52) = v96;
LABEL_210:
        v94 = (int *)(v14 + 48);
        if ( v89 )
          v95 = sz.cx + *(_DWORD *)(v14 + 52);
        else
          v95 = rect.right - v86;
        *v94 = v95;
        if ( v95 < v144.left )
        {
          *v94 = v144.left;
          v95 = v144.left;
        }
        goto LABEL_215;
      }
      fmt = Buffer.fmt & 0xFFFFFFFC;
      Buffer.fmt &= 0xFFFFFFFC;
    }
    v108 = fmt;
    goto LABEL_43;
  }
  v125 = 0;
  memset_0(lParam, 0, 0x40u);
  v30 = *(HWND *)a1;
  *((_DWORD *)a1 + 31) |= 4u;
  LODWORD(lParam[0]) = 100;
  DlgCtrlID = GetDlgCtrlID(v30);
  v32 = *lprect;
  v33 = a4;
  v34 = (HWND)*((_QWORD *)a1 + 1);
  v35 = hdc;
  LODWORD(v130) = v115 != 0;
  *((_QWORD *)&v130 + 1) = *(_QWORD *)a1;
  v133 = *(_QWORD *)(v14 + 40);
  HIDWORD(lParam[0]) = DlgCtrlID;
  lParam[1] = (unsigned int)a4 | 0x100000000LL;
  v131 = hdc;
  v132 = v32;
  if ( !SendMessageW(v34, 0x2Bu, DlgCtrlID, (LPARAM)lParam) )
    goto LABEL_34;
  v50 = GetTextColor(hdc);
  BkColor = GetBkColor(hdc);
LABEL_79:
  v51 = (_DWORD *)((char *)a1 + 16);
  if ( !*((_QWORD *)a1 + 38) && ((a6 & 2) == 0 && (*v51 & 0x200) == 0 || v33 == *v124) )
  {
    rc = pRect;
    rc.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)pRect, 8)) - v119;
    Header_DrawButtonEdges(a1, v35, &rc, v115);
    if ( v116 )
    {
      Header_DrawButtonEdges(a1, v35, (struct tagRECT *)(v14 + 60), v122);
      DrawScrollArrow(v35, (struct tagRECT *)(v14 + 60), 16 * (v122 + 6), v50);
    }
  }
  if ( v121 )
  {
    rc = v144;
    v53 = -GetSystemMetrics(46);
    v54 = GetSystemMetrics(45);
    InflateRect(&rc, -v54, v53);
    v55 = GetSysColor(8);
    SetTextColor(v35, v55);
    DrawFocusRect(v35, &rc);
  }
  if ( (v15 & 0x40) != 0 && (*v51 & 0x400) != 0 && *((_QWORD *)a1 + 20) )
  {
    dy = *((_DWORD *)a1 + 21);
    v69 = *((_DWORD *)a1 + 20);
    v70 = (v144.bottom - v144.top - dy) / 2 + v144.top;
    v71 = GetSystemMetrics(45);
    ImageList_DrawEx(
      *((HIMAGELIST *)a1 + 20),
      (v15 >> 7) & 1,
      v35,
      v71 + pRect.left + 2,
      v70,
      v69,
      dy,
      BkColor,
      0xFF000000,
      1u);
  }
  if ( (v125 & 0x10) != 0 && (*((_BYTE *)a1 + 20) & 0x20) != 0 )
  {
    v136 = 65538;
    CCSendNotify(a1, 4294967284LL, &v134);
  }
}

```

## disassembly

```asm
0x180009d9c  push    rbp
0x180009d9e  push    rbx
0x180009d9f  push    rsi
0x180009da0  push    rdi
0x180009da1  push    r12
0x180009da3  push    r13
0x180009da5  push    r14
0x180009da7  push    r15
0x180009da9  lea     rbp, [rsp-3A8h]
0x180009db1  sub     rsp, 4A8h
0x180009db8  mov     rax, cs:__security_cookie
0x180009dbf  xor     rax, rsp
0x180009dc2  mov     [rbp+3E0h+var_50], rax
0x180009dc9  mov     rsi, [rbp+3E0h+lprect]
0x180009dd0  mov     ebx, r8d
0x180009dd3  mov     rdi, rdx
0x180009dd6  mov     [rbp+3E0h+hdc], rdx
0x180009dda  mov     edx, r8d; int
0x180009ddd  mov     [rsp+4E0h+var_464], ebx
0x180009de1  mov     [rsp+4E0h+var_46C], r9d
0x180009de6  mov     r14, rcx
0x180009de9  call    ?Header_ItemOrderToIndex@@YAHPEAUHD@@H@Z; Header_ItemOrderToIndex(HD *,int)
0x180009dee  mov     rdx, [r14+70h]
0x180009df2  xor     r15d, r15d
0x180009df5  test    rdx, rdx
0x180009df8  jz      loc_18000A382
0x180009dfe  test    eax, eax
0x180009e00  js      loc_18000A382
0x180009e06  cmp     eax, [rdx]
0x180009e08  jge     loc_18000A382
0x180009e0e  imul    eax, [rdx+14h]
0x180009e12  mov     r12d, eax
0x180009e15  add     r12, [rdx+8]
0x180009e19  mov     [rbp+3E0h+var_400], r12
0x180009e1d  jz      loc_18000A382
0x180009e23  movups  xmm0, xmmword ptr [rsi]
0x180009e26  movdqu  xmmword ptr [rbp+3E0h+y.left], xmm0
0x180009e2b  movdqu  xmmword ptr [rbp+3E0h+var_330.left], xmm0
0x180009e33  movdqu  xmmword ptr [rbp+3E0h+pRect.left], xmm0
0x180009e3b  mov     ecx, [r12+8]
0x180009e40  mov     eax, ecx
0x180009e42  and     eax, 2000000h
0x180009e47  mov     r13d, ecx
0x180009e4a  and     r13d, 0FFFFFFFCh
0x180009e4e  mov     [rbp+3E0h+var_450], eax
0x180009e51  bt      ecx, 18h
0x180009e55  cmovnb  r13d, ecx
0x180009e59  cmp     [r14+130h], r15
0x180009e60  jnz     loc_18000A4EA
0x180009e66  mov     rcx, r14; struct HD *
0x180009e69  call    ?Header_IsTracking@@YAHPEAUHD@@@Z; Header_IsTracking(HD *)
0x180009e6e  mov     r11d, [rsp+4E0h+var_46C]
0x180009e73  mov     edx, 1
0x180009e78  lea     r10d, [rdx+1]
0x180009e7c  test    eax, eax
0x180009e7e  jnz     loc_18000AAD4
0x180009e84  mov     ecx, r15d
0x180009e87  mov     [rbp+3E0h+var_44C], ecx
0x180009e8a  test    eax, eax
0x180009e8c  jnz     loc_18000AB03
0x180009e92  mov     [rbp+3E0h+var_430], r15d
0x180009e96  mov     r15, [r14+130h]
0x180009e9d  xor     r9d, r9d
0x180009ea0  test    r15, r15
0x180009ea3  jz      loc_18000AB30
0x180009ea9  mov     [rbp+3E0h+var_434], r9d
0x180009ead  lea     rax, unk_1801F0264
0x180009eb4  lea     rbx, unk_1801F0270
0x180009ebb  test    ecx, ecx
0x180009ebd  jz      loc_18000A3B2
0x180009ec3  lea     rax, [r14+0B0h]
0x180009eca  mov     [rbp+3E0h+var_420], rax
0x180009ece  lea     rdx, unk_1801F0274
0x180009ed5  lea     rax, unk_1801F0268
0x180009edc  mov     [rbp+3E0h+cy], r10d
0x180009ee3  mov     r10d, [rbp+3E0h+var_450]
0x180009ee7  movsxd  r8, dword ptr [r14+128h]
0x180009eee  mov     edi, r13d
0x180009ef1  and     edi, 600h
0x180009ef7  cmovz   rdx, rax
0x180009efb  lea     rcx, [r8+r8*2]
0x180009eff  lea     rax, [rdx+rcx*8]
0x180009f03  mov     rcx, [rbp+3E0h+var_420]
0x180009f07  mov     eax, [rax]
0x180009f09  mov     edx, 3
0x180009f0e  mov     [rsp+4E0h+iStateId], eax
0x180009f12  cmp     r11d, [rcx]
0x180009f15  jz      loc_18000ABA7
0x180009f1b  mov     r9d, [rbp+3E0h+cy]
0x180009f22  xor     r11d, r11d
0x180009f25  mov     [rsp+4E0h+iStateId], eax
0x180009f29  mov     rdx, [r14+70h]
0x180009f2d  mov     r10d, [rsp+4E0h+var_464]
0x180009f32  test    rdx, rdx
0x180009f35  jz      short loc_180009F5D
0x180009f37  test    r10d, r10d
0x180009f3a  js      short loc_180009F5D
0x180009f3c  cmp     r10d, [rdx]
0x180009f3f  jge     short loc_180009F5D
0x180009f41  mov     r8d, r10d
0x180009f44  imul    r8d, [rdx+14h]
0x180009f49  add     r8, [rdx+8]
0x180009f4d  jz      short loc_180009F5D
0x180009f4f  test    dword ptr [r8+8], 1000000h
0x180009f57  jnz     loc_18000ABF2
0x180009f5d  mov     [rbp+3E0h+var_448], r11d
0x180009f61  test    rdx, rdx
0x180009f64  jz      short loc_180009F8B
0x180009f66  test    r10d, r10d
0x180009f69  js      short loc_180009F8B
0x180009f6b  cmp     r10d, [rdx]
0x180009f6e  jge     short loc_180009F8B
0x180009f70  imul    r10d, [rdx+14h]
0x180009f75  mov     rdx, [rdx+8]
0x180009f79  add     rdx, r10
0x180009f7c  jz      short loc_180009F8B
0x180009f7e  test    dword ptr [rdx+8], 1000000h
0x180009f85  jnz     loc_18000A539
0x180009f8b  mov     [rbp+3E0h+var_43C], r11d
0x180009f8f  mov     ebx, 48h ; 'H'
0x180009f94  mov     [rbp+3E0h+var_3A0], r11
0x180009f98  mov     r8d, ebx; Size
0x180009f9b  lea     rcx, [rbp+3E0h+var_398]; void *
0x180009f9f  xor     edx, edx; Val
0x180009fa1  call    memset_0
0x180009fa6  mov     r8d, ebx; Size
0x180009fa9  lea     rcx, [rbp+3E0h+Buffer]; void *
0x180009fb0  xor     edx, edx; Val
0x180009fb2  call    memset_0
0x180009fb7  xorps   xmm0, xmm0
0x180009fba  movups  xmmword ptr [rbp+3E0h+y1], xmm0
0x180009fbe  bt      r13d, 0Fh
0x180009fc3  jnb     loc_18000A491
0x180009fc9  xor     r15d, r15d
0x180009fcc  lea     r8d, [rbx-8]; Size
0x180009fd0  xor     edx, edx; Val
0x180009fd2  mov     dword ptr [rbp+3E0h+var_418], r15d
0x180009fd6  lea     rcx, [rbp+3E0h+lParam]; void *
0x180009fda  call    memset_0
0x180009fdf  mov     rcx, [r14]; hWnd
0x180009fe2  or      dword ptr [r14+7Ch], 4
0x180009fe7  mov     dword ptr [rbp+3E0h+lParam], 64h ; 'd'
0x180009fee  call    cs:__imp_GetDlgCtrlID
0x180009ff4  cmp     [rbp+3E0h+var_44C], r15d
0x180009ff8  lea     r9, [rbp+3E0h+lParam]; lParam
0x180009ffc  movups  xmm0, xmmword ptr [rsi]
0x180009fff  mov     ebx, [rsp+4E0h+var_46C]
0x18000a003  mov     edx, 2Bh ; '+'; Msg
0x18000a008  mov     rcx, [r14+8]; hWnd
0x18000a00c  mov     r8d, eax; wParam
0x18000a00f  mov     eax, r15d
0x18000a012  mov     r15, [rbp+3E0h+hdc]
0x18000a016  setnz   al
0x18000a019  mov     dword ptr [rbp+3E0h+var_3D0], eax
0x18000a01c  mov     rax, [r14]
0x18000a01f  mov     qword ptr [rbp+3E0h+var_3D0+8], rax
0x18000a023  mov     rax, [r12+28h]
0x18000a028  mov     [rbp+3E0h+var_3A8], rax
0x18000a02c  mov     dword ptr [rbp+3E0h+lParam+4], r8d
0x18000a030  mov     dword ptr [rbp+3E0h+lParam+8], ebx
0x18000a033  mov     dword ptr [rbp+3E0h+lParam+0Ch], 1
0x18000a03a  mov     [rbp+3E0h+var_3C0], r15
0x18000a03e  movdqu  [rbp+3E0h+var_3B8], xmm0
0x18000a043  call    cs:__imp_SendMessageW
0x18000a049  xor     edx, edx
0x18000a04b  test    rax, rax
0x18000a04e  jnz     loc_18000A8EC
0x18000a054  mov     rcx, r15; hdc
0x18000a057  mov     [rbp+3E0h+nSavedDC], edx
0x18000a05a  call    cs:__imp_GetTextColor
0x18000a060  mov     rcx, r15; hdc
0x18000a063  mov     [rbp+3E0h+var_460], eax
0x18000a066  call    cs:__imp_GetBkColor
0x18000a06c  test    dword ptr [r14+10h], 100h
0x18000a074  mov     [rbp+3E0h+var_438], eax
0x18000a077  jnz     loc_18000AC0D
0x18000a07d  mov     ebx, r13d
0x18000a080  and     ebx, 40h
0x18000a083  jnz     loc_18000AC38
0x18000a089  movaps  xmm0, xmmword ptr [rbp+3E0h+var_330.left]
0x18000a090  movss   [rbp+3E0h+var_330.left], xmm0
0x18000a098  movaps  xmm0, xmmword ptr [rbp+3E0h+var_330.left]
0x18000a09f  xor     r11d, r11d
0x18000a0a2  mov     eax, [rbp+3E0h+var_44C]
0x18000a0a5  shl     eax, 5
0x18000a0a8  add     eax, 400046h
0x18000a0ad  movdqa  xmmword ptr [rbp+3E0h+var_340.left], xmm0
0x18000a0b5  test    r13d, 6800h
0x18000a0bc  mov     dword ptr [rbp+3E0h+var_444], eax
0x18000a0bf  movdqa  xmmword ptr [rbp+3E0h+rect.left], xmm0
0x18000a0c7  setz    cl
0x18000a0ca  mov     [rbp+3E0h+var_260], r11w
0x18000a0d2  test    dword ptr [r14+10h], 100h
0x18000a0da  setz    al
0x18000a0dd  test    al, cl
0x18000a0df  jnz     short loc_18000A132
0x18000a0e1  mov     edx, [rsp+4E0h+var_46C]; int
0x18000a0e5  lea     rax, [rbp+3E0h+var_260]
0x18000a0ec  lea     r8, [rbp+3E0h+Buffer]; struct _HD_ITEMW *
0x18000a0f3  mov     [rbp+3E0h+lpString], rax
0x18000a0fa  mov     rcx, r14; struct HD *
0x18000a0fd  mov     dword ptr [rbp+3E0h+Buffer], 36h ; '6'
0x18000a107  mov     [rbp+3E0h+var_2C8], 104h
0x18000a111  call    ?Header_OnGetItem@@YAHPEAUHD@@HPEAU_HD_ITEMW@@@Z; Header_OnGetItem(HD *,int,_HD_ITEMW *)
0x18000a116  mov     r15d, [rbp+3E0h+var_2C4]
0x18000a11d  mov     [rsp+4E0h+var_470], r15d
0x18000a122  bt      r15d, 18h
0x18000a127  jb      loc_18000AC5F
0x18000a12d  xor     r11d, r11d
0x18000a130  jmp     short loc_18000A13E
0x18000a132  mov     r15d, [rbp+3E0h+var_2C4]
0x18000a139  mov     [rsp+4E0h+var_470], r15d
0x18000a13e  mov     rcx, [r14+130h]; hTheme
0x18000a145  test    rcx, rcx
0x18000a148  jz      loc_18000AC72
0x18000a14e  mov     r9d, [rsp+4E0h+iStateId]; iStateId
0x18000a153  lea     rax, [rbp+3E0h+rect]
0x18000a15a  mov     rdx, [rbp+3E0h+hdc]; hdc
0x18000a15e  mov     r8d, 1; iPartId
0x18000a164  mov     [rsp+4E0h+pContentRect], rax; pContentRect
0x18000a169  lea     rax, [rbp+3E0h+var_330]
0x18000a170  mov     [rsp+4E0h+pBoundingRect], rax; pBoundingRect
0x18000a175  call    cs:__imp_GetThemeBackgroundContentRect
0x18000a17b  movaps  xmm0, xmmword ptr [rbp+3E0h+rect.left]
0x18000a182  xor     r11d, r11d
0x18000a185  mov     r8, [r14+130h]
0x18000a18c  movdqa  xmmword ptr [rbp+3E0h+var_340.left], xmm0
0x18000a194  mov     rdx, [r14+70h]
0x18000a198  mov     esi, [rbp+3E0h+cy]
0x18000a19e  test    rdx, rdx
0x18000a1a1  jz      short loc_18000A1CB
0x18000a1a3  mov     eax, [rsp+4E0h+var_464]
0x18000a1a7  test    eax, eax
0x18000a1a9  js      short loc_18000A1CB
0x18000a1ab  cmp     eax, [rdx]
0x18000a1ad  jge     short loc_18000A1CB
0x18000a1af  imul    eax, [rdx+14h]
0x18000a1b3  mov     rdx, [rdx+8]
0x18000a1b7  mov     ecx, eax
0x18000a1b9  add     rdx, rcx
0x18000a1bc  jz      short loc_18000A1CB
0x18000a1be  test    dword ptr [rdx+8], 1000000h
0x18000a1c5  jnz     loc_18000AC7A
0x18000a1cb  movdqa  xmm0, xmmword ptr [rbp+3E0h+var_330.left]
0x18000a1d3  psrldq  xmm0, 8
0x18000a1d8  movd    [rbp+3E0h+var_330.right], xmm0
0x18000a1e0  mov     [rbp+3E0h+var_448], r11d
0x18000a1e4  test    r8, r8
0x18000a1e7  jz      loc_18000ACA9
0x18000a1ed  mov     edi, r11d
0x18000a1f0  mov     rax, [rbp+3E0h+lpString]
0x18000a1f7  mov     [rbp+3E0h+var_428], rax
0x18000a1fb  bt      r13d, 0Eh
0x18000a200  jnb     short loc_18000A217
0x18000a202  test    r13d, 2800h
0x18000a209  jnz     loc_18000A54F
0x18000a20f  test    edi, edi
0x18000a211  jnz     loc_18000A54F
0x18000a217  mov     edx, [rbp+3E0h+rect.left]
0x18000a21d  mov     edi, [rbp+3E0h+var_448]
0x18000a220  test    edi, edi
0x18000a222  jnz     loc_18000AF02
0x18000a228  mov     rcx, [r14+130h]; hTheme
0x18000a22f  mov     rbx, [rbp+3E0h+hdc]
0x18000a233  test    rcx, rcx
0x18000a236  jz      short loc_18000A26E
0x18000a238  mov     r9d, [rsp+4E0h+iStateId]; iStateId
0x18000a23d  lea     rax, [rbp+3E0h+pRect]
0x18000a244  mov     [rsp+4E0h+pContentRect], r11; pClipRect
0x18000a249  mov     r8d, 1; iPartId
0x18000a24f  mov     rdx, rbx; hdc
0x18000a252  mov     [rsp+4E0h+pBoundingRect], rax; pRect
0x18000a257  call    cs:__imp_DrawThemeBackground
0x18000a25d  xor     r11d, r11d
0x18000a260  test    edi, edi
0x18000a262  jnz     loc_18000AF36
0x18000a268  mov     edx, [rbp+3E0h+rect.left]
0x18000a26e  mov     rsi, r11
0x18000a271  test    r13d, 600h
0x18000a278  jnz     loc_18000AA99
0x18000a27e  mov     eax, r13d
0x18000a281  mov     ecx, 2000h
0x18000a286  and     eax, 800h
0x18000a28b  jnz     loc_18000A5F4
0x18000a291  test    ecx, r13d
0x18000a294  jnz     loc_18000A5F4
0x18000a29a  bt      r13d, 0Eh
0x18000a29f  jnb     short loc_18000A31E
0x18000a2a1  mov     edx, dword ptr [rbp+3E0h+var_444]
0x18000a2a4  test    r15b, 4
0x18000a2a8  jnz     loc_18000B0F2
0x18000a2ae  mov     r10, [r14+130h]
0x18000a2b5  or      ecx, 0FFFFFFFFh
0x18000a2b8  mov     eax, [rbp+3E0h+var_438]
0x18000a2bb  test    r10, r10
0x18000a2be  mov     r9d, [rsp+4E0h+iStateId]
0x18000a2c3  mov     r8d, 1
0x18000a2c9  cmovnz  eax, ecx
0x18000a2cc  mov     ecx, r15d
0x18000a2cf  mov     [rsp+4E0h+var_480], eax
  ... truncated ...
```
