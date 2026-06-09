# Header_DrawItem

- ea: `0x18005ec54`
- end: `0x18005f5de`
- name: `Header_DrawItem`
- size: `2442`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18005e7ec`
- `0x18005ffa0`

## callees

- `0x1800115f0`
- `0x18001ac40`
- `0x18001d894`
- `0x180036e24`
- `0x18005dde0`
- `0x18005ea30`
- `0x18005eb28`
- `0x18005ec54`
- `0x18005f8c8`
- `0x18005fc30`
- `0x1800605a0`
- `0x1800628ec`
- `0x180085eb0`
- `0x18008ea60`

## import_xrefs

- `GDI32!GetTextExtentPointW` at `0x18005ef27`
- `GDI32!GetTextExtentPointW` at `0x18005ef27`
- `GDI32!DeleteObject` at `0x18005f285`
- `GDI32!DeleteObject` at `0x18005f28e`
- `GDI32!DeleteObject` at `0x18005f347`
- `GDI32!DeleteObject` at `0x18005f479`
- `GDI32!DeleteObject` at `0x18005f568`
- `GDI32!DeleteObject` at `0x18005f571`
- `GDI32!DeleteObject` at `0x18005f57a`
- `GDI32!DeleteObject` at `0x18005f285`
- `GDI32!DeleteObject` at `0x18005f28e`
- `GDI32!DeleteObject` at `0x18005f347`
- `GDI32!DeleteObject` at `0x18005f479`
- `GDI32!DeleteObject` at `0x18005f568`
- `GDI32!DeleteObject` at `0x18005f571`
- `GDI32!DeleteObject` at `0x18005f57a`
- `GDI32!CreateRectRgn` at `0x18005f264`
- `GDI32!CreateRectRgn` at `0x18005f2b8`
- `GDI32!CreateRectRgn` at `0x18005f458`
- `GDI32!CreateRectRgn` at `0x18005f4f8`
- `GDI32!CreateRectRgn` at `0x18005f264`
- `GDI32!CreateRectRgn` at `0x18005f2b8`
- `GDI32!CreateRectRgn` at `0x18005f458`
- `GDI32!CreateRectRgn` at `0x18005f4f8`
- `GDI32!GetObjectW` at `0x18005ef70`
- `GDI32!GetObjectW` at `0x18005ef70`
- `GDI32!ExtTextOutW` at `0x18005f553`
- `GDI32!ExtTextOutW` at `0x18005f553`
- `GDI32!GetTextColor` at `0x18005ee03`
- `GDI32!GetTextColor` at `0x18005ee03`
- `GDI32!SetTextColor` at `0x18005f4c5`
- `GDI32!SetTextColor` at `0x18005f4c5`
- `GDI32!SaveDC` at `0x18005f2c4`
- `GDI32!SaveDC` at `0x18005f2c4`
- `GDI32!RestoreDC` at `0x18005f55f`
- `GDI32!RestoreDC` at `0x18005f55f`
- `GDI32!PatBlt` at `0x18005f41f`
- `GDI32!PatBlt` at `0x18005f41f`
- `GDI32!SelectClipRgn` at `0x18005f51c`
- `GDI32!SelectClipRgn` at `0x18005f51c`
- `GDI32!CombineRgn` at `0x18005f27c`
- `GDI32!CombineRgn` at `0x18005f33e`
- `GDI32!CombineRgn` at `0x18005f470`
- `GDI32!CombineRgn` at `0x18005f510`
- `GDI32!CombineRgn` at `0x18005f27c`
- `GDI32!CombineRgn` at `0x18005f33e`
- `GDI32!CombineRgn` at `0x18005f470`
- `GDI32!CombineRgn` at `0x18005f510`
- `GDI32!CreateRectRgnIndirect` at `0x18005f164`
- `GDI32!CreateRectRgnIndirect` at `0x18005f22f`
- `GDI32!CreateRectRgnIndirect` at `0x18005f326`
- `GDI32!CreateRectRgnIndirect` at `0x18005f4e5`
- `GDI32!CreateRectRgnIndirect` at `0x18005f164`
- `GDI32!CreateRectRgnIndirect` at `0x18005f22f`
- `GDI32!CreateRectRgnIndirect` at `0x18005f326`
- `GDI32!CreateRectRgnIndirect` at `0x18005f4e5`
- `GDI32!GetBkColor` at `0x18005ee10`
- `GDI32!GetBkColor` at `0x18005ee10`
- `KERNEL32!lstrlenW` at `0x18005ef13`
- `KERNEL32!lstrlenW` at `0x18005ef13`
- `USER32!SendMessageW` at `0x18005ed95`
- `USER32!SendMessageW` at `0x18005ed95`
- `USER32!GetDlgCtrlID` at `0x18005ed4b`
- `USER32!GetDlgCtrlID` at `0x18005ed4b`
- `USER32!InflateRect` at `0x18005f4b6`
- `USER32!InflateRect` at `0x18005f4b6`
- `USER32!DrawFocusRect` at `0x18005f4d2`
- `USER32!DrawFocusRect` at `0x18005f4d2`

## pseudocode

```c
int __fastcall Header_DrawItem(__int64 a1, HDC a2, unsigned int a3, int a4, RECT *a5, char a6)
{
  __int64 v7; // r12
  int IsTracking; // ebx
  __int64 ItemPtrByOrder; // rax
  __int64 v12; // rdi
  BOOL v13; // ebx
  char v14; // r15
  HWND v15; // rcx
  unsigned int DlgCtrlID; // eax
  RECT v17; // xmm0
  HWND v18; // rcx
  LRESULT RectRgnIndirect; // rax
  RECT v20; // xmm0
  bool v21; // zf
  int v22; // ebx
  HRGN RectRgn; // r15
  COLORREF BkColor; // eax
  RECT v25; // xmm1
  int v26; // eax
  int v27; // r8d
  LONG right; // eax
  const WCHAR *v29; // r12
  bool v30; // cl
  int v31; // ecx
  int v32; // eax
  LONG top; // ecx
  LONG v34; // r10d
  int v35; // r11d
  int v36; // eax
  LONG v37; // r9d
  int v38; // r8d
  int v39; // edx
  int v40; // ecx
  int v41; // ecx
  unsigned int v42; // eax
  LONG *v43; // r8
  LONG v44; // ecx
  LONG v45; // eax
  int v46; // ecx
  LONG left; // r11d
  LONG v48; // r9d
  int v49; // ecx
  int v50; // edx
  int v51; // r8d
  int v52; // r10d
  int v53; // r14d
  HRGN v54; // rbx
  LONG v55; // r12d
  LONG cx; // r10d
  HRGN v57; // r12
  HRGN v58; // rbx
  wchar_t *v59; // r12
  int v60; // r14d
  COLORREF v61; // ebx
  int v62; // eax
  unsigned int v63; // edi
  HRGN v64; // rbx
  HRGN v65; // rdi
  HRGN v66; // rbx
  char v68[4]; // [rsp+50h] [rbp-B0h]
  BOOL v69; // [rsp+54h] [rbp-ACh]
  char v70; // [rsp+58h] [rbp-A8h]
  struct tagSIZE sz; // [rsp+60h] [rbp-A0h] BYREF
  int cy[2]; // [rsp+68h] [rbp-98h] BYREF
  COLORREF v73; // [rsp+70h] [rbp-90h]
  COLORREF color; // [rsp+74h] [rbp-8Ch]
  unsigned int v75; // [rsp+78h] [rbp-88h]
  const WCHAR *v76; // [rsp+80h] [rbp-80h]
  int y1[4]; // [rsp+88h] [rbp-78h] BYREF
  HRGN hrgnSrc1; // [rsp+98h] [rbp-68h]
  int y[4]; // [rsp+A0h] [rbp-60h] BYREF
  RECT lParam[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v81[10]; // [rsp+F0h] [rbp-10h] BYREF
  RECT v82; // [rsp+140h] [rbp+40h] BYREF
  RECT v83; // [rsp+150h] [rbp+50h]
  RECT rect; // [rsp+160h] [rbp+60h] BYREF
  wchar_t Buffer[32]; // [rsp+170h] [rbp+70h] BYREF
  char v86; // [rsp+1B0h] [rbp+B0h] BYREF

  v75 = a3;
  v7 = a4;
  v82 = 0;
  *(_OWORD *)y = 0;
  *(_OWORD *)y1 = 0;
  rect = 0;
  v83 = 0;
  memset(Buffer, 0, sizeof(Buffer));
  IsTracking = Header_IsTracking(a1);
  memset(v81, 0, sizeof(v81));
  *(RECT *)y = *a5;
  v82 = *(RECT *)y;
  ItemPtrByOrder = Header_GetItemPtrByOrder(a1, a3);
  v12 = ItemPtrByOrder;
  v13 = IsTracking
     && (*(_BYTE *)(a1 + 104) & 2) != 0
     && *(_DWORD *)(a1 + 96) == (_DWORD)v7
     && (*(_BYTE *)(a1 + 100) & 1) != 0;
  v69 = v13;
  if ( (*(_DWORD *)(ItemPtrByOrder + 8) & 0x8000) != 0 )
  {
    v14 = 0;
    v70 = 0;
    memset(lParam, 0, sizeof(lParam));
    v15 = *(HWND *)a1;
    *(_DWORD *)(a1 + 100) |= 4u;
    lParam[0].left = 100;
    DlgCtrlID = GetDlgCtrlID(v15);
    v17 = *a5;
    v18 = *(HWND *)(a1 + 8);
    lParam[0].top = DlgCtrlID;
    lParam[0].right = v7;
    lParam[0].bottom = 1;
    *(_QWORD *)&lParam[2].left = a2;
    lParam[1].left = v13;
    *(_QWORD *)&lParam[1].right = *(_QWORD *)a1;
    *(_QWORD *)&lParam[3].right = *(_QWORD *)(v12 + 40);
    *(RECT *)&lParam[2].right = v17;
    RectRgnIndirect = SendMessageW(v18, 0x2Bu, DlgCtrlID, (LPARAM)lParam);
    if ( RectRgnIndirect )
    {
LABEL_108:
      if ( (a6 & 2) == 0 )
        LODWORD(RectRgnIndirect) = Header_DrawButtonEdges(a1, a2, &v82, v13);
      if ( (v14 & 0x10) != 0 )
        LODWORD(RectRgnIndirect) = CICustomDrawNotify(a1, 65538, v81);
      return RectRgnIndirect;
    }
LABEL_13:
    v22 = 32 * v13 + 70;
    RectRgn = 0;
    *(_DWORD *)v68 = v22;
    color = GetTextColor(a2);
    BkColor = GetBkColor(a2);
    v21 = (*(_DWORD *)(a1 + 16) & 0x100) == 0;
    v73 = BkColor;
    if ( !v21 )
    {
      v25 = *a5;
      v26 = a5->bottom + ~a5->top;
      v82 = v25;
      v27 = v26 / 2;
      v82.bottom = v26 / 2 + v25.top;
      right = a5->right;
      y[0] = v25.left;
      y[2] = -13 - 4 * g_cxBorder + right;
      *(_QWORD *)&y1[2] = *(_QWORD *)&v25.right;
      y1[0] = y[2];
      y[3] = v27 + v25.top + v27;
      y[1] = v27 + v25.top;
      y1[1] = v27 + v25.top;
    }
    v83 = v82;
    rect = v82;
    if ( (*(_DWORD *)(v12 + 8) & 0x6800) != 0 )
    {
      wcscpy(Buffer, L"6");
      *(_QWORD *)&Buffer[4] = &v86;
      wcscpy(&Buffer[12], L"Ą");
      Header_OnGetItem(a1, (unsigned int)v7, Buffer);
    }
    v29 = *(const WCHAR **)&Buffer[4];
    v30 = (*(_DWORD *)(v12 + 8) & 0x2800) != 0;
    v76 = *(const WCHAR **)&Buffer[4];
    if ( (v30 & _bittest((const signed __int32 *)(v12 + 8), 0xEu)) == 0 )
    {
      left = v82.left;
      LODWORD(RectRgnIndirect) = rect.right;
      v49 = rect.left;
      v50 = v83.right;
      v48 = v83.left;
LABEL_54:
      v51 = *(_DWORD *)(v12 + 8) & 0x2000;
      v52 = *(_DWORD *)(v12 + 8) & 0x800;
      if ( v52 || v51 )
      {
        cy[0] = 0;
        v54 = 0;
        hrgnSrc1 = 0;
        v55 = 0;
        lParam[0] = 0;
        if ( v52 && v51 )
        {
          v53 = *(_DWORD *)&Buffer[14] ^ 0x2000;
          cy[0] = 1;
          *(_DWORD *)&Buffer[14] ^= 0x2000u;
        }
        else
        {
          v53 = *(_DWORD *)&Buffer[14];
        }
        cx = a6 & 1;
        sz.cx = cx;
        if ( (a6 & 1) == 0 )
        {
          v55 = Header_DrawBitmap(a2, *(HIMAGELIST *)(a1 + 128), v53 & 3, v68[0], lParam, *(_DWORD *)(a1 + 168));
          RectRgnIndirect = (LRESULT)CreateRectRgnIndirect(lParam);
          left = v82.left;
          v49 = rect.left;
          v50 = v83.right;
          v48 = v83.left;
          v53 = *(_DWORD *)&Buffer[14];
          cx = sz.cx;
          hrgnSrc1 = (HRGN)RectRgnIndirect;
          LODWORD(RectRgnIndirect) = rect.right;
          v76 = *(const WCHAR **)&Buffer[4];
        }
        if ( cy[0] )
        {
          v53 ^= 0x2800u;
          *(_DWORD *)&Buffer[14] = v53;
          if ( (v53 & 1) != 0 )
          {
            v83.right = v55;
            if ( (v53 & 0x4000) != 0 )
            {
              if ( v48 < v49 )
                v49 = v48;
              v83.right = v49;
            }
            v83.left = left;
          }
          else
          {
            v83.left = v55;
            if ( (v53 & 0x4000) != 0 )
            {
              if ( v50 > (int)RectRgnIndirect )
                LODWORD(RectRgnIndirect) = v50;
              v83.left = RectRgnIndirect;
            }
            v83.right = v82.right;
          }
          if ( !cx )
          {
            Header_DrawBitmap(a2, *(HIMAGELIST *)(a1 + 128), v53 & 1, v68[0], lParam, *(_DWORD *)(a1 + 168));
            v54 = CreateRectRgnIndirect(lParam);
            LOBYTE(v53) = Buffer[14];
            v76 = *(const WCHAR **)&Buffer[4];
          }
        }
        v57 = hrgnSrc1;
        if ( hrgnSrc1 )
        {
          if ( v54 )
          {
            RectRgn = CreateRectRgn(0, 0, 0, 0);
            CombineRgn(RectRgn, v57, v54, 2);
            DeleteObject(v57);
            DeleteObject(v54);
          }
          else
          {
            RectRgn = hrgnSrc1;
          }
        }
        else if ( v54 )
        {
          RectRgn = v54;
        }
        if ( sz.cx && !RectRgn )
          RectRgn = CreateRectRgn(0, 0, 0, 0);
        LODWORD(RectRgnIndirect) = SaveDC(a2);
        v22 = *(_DWORD *)v68;
        v29 = v76;
      }
      else
      {
        LOBYTE(v53) = Buffer[14];
      }
      if ( (*(_DWORD *)(v12 + 8) & 0x4000) != 0 )
      {
        if ( (v53 & 4) != 0 )
          v22 |= 0x800u;
        LODWORD(RectRgnIndirect) = SHDrawText(
                                     a2,
                                     v29,
                                     &rect,
                                     v22,
                                     *(_DWORD *)(a1 + 68),
                                     *(_DWORD *)(a1 + 60),
                                     color,
                                     v73);
        if ( RectRgn )
        {
          v58 = CreateRectRgnIndirect(&rect);
          CombineRgn(RectRgn, v58, RectRgn, 2);
          LODWORD(RectRgnIndirect) = DeleteObject(v58);
        }
      }
      if ( (*(_DWORD *)(a1 + 16) & 0x100) != 0 )
      {
        memset(Buffer, 0, sizeof(Buffer));
        v59 = Buffer;
        v60 = ((v53 & 4) << 9) | 0x46;
        if ( (*(_DWORD *)(v12 + 64) & 0x8000) != 0 )
        {
          LocalizedLoadString(4176, Buffer, 32);
          v61 = g_clrGrayText;
        }
        else
        {
          v61 = g_clrWindowText;
          v62 = *(_DWORD *)(v12 + 64) & 0xF;
          if ( v62 )
          {
            if ( v62 == 1 )
              StringCchPrintfW(Buffer, 0x20u, L"%d", *(unsigned int *)(v12 + 88));
          }
          else
          {
            v59 = *(wchar_t **)(v12 + 72);
          }
        }
        SHDrawText(a2, v59, (RECT *)y, v60, *(_DWORD *)(a1 + 68), *(_DWORD *)(a1 + 60), v61, g_clrWindow);
        PatBlt(a2, y[0], y[3], y[2] - y[0], 1, 0x42u);
        v63 = v75;
        LODWORD(RectRgnIndirect) = Header_DrawFilterGlyph(a1, a2, y1, v75 == *(_DWORD *)(a1 + 180));
        if ( RectRgn )
        {
          v64 = CreateRectRgn(y[0], y1[1], y1[2], y1[3]);
          CombineRgn(RectRgn, v64, RectRgn, 2);
          LODWORD(RectRgnIndirect) = DeleteObject(v64);
        }
        if ( (*(_BYTE *)(a1 + 100) & 8) != 0 && *(_DWORD *)(a1 + 172) == v63 && (*(_BYTE *)(a1 + 48) & 1) == 0 )
        {
          InflateRect((LPRECT)y, g_cxEdge / -2, g_cyEdge / -2);
          SetTextColor(a2, g_clrWindowText);
          LODWORD(RectRgnIndirect) = DrawFocusRect(a2, (const RECT *)y);
        }
      }
      if ( RectRgn )
      {
        v65 = CreateRectRgnIndirect(&v82);
        v66 = CreateRectRgn(0, 0, 0, 0);
        CombineRgn(v66, v65, RectRgn, 3);
        SelectClipRgn(a2, v66);
        ExtTextOutW(a2, 0, 0, 2u, &v82, 0, 0, 0);
        RestoreDC(a2, -1);
        DeleteObject(RectRgn);
        DeleteObject(v66);
        LODWORD(RectRgnIndirect) = DeleteObject(v65);
      }
      v14 = v70;
      v13 = v69;
      goto LABEL_108;
    }
    if ( *(_DWORD *)(v12 + 52) != 0x7FFFFFFF )
    {
      v31 = *(_DWORD *)(v12 + 48);
      if ( v31 != 0x7FFFFFFF )
      {
LABEL_49:
        left = v82.left;
        v48 = v31 + v82.left;
        v83.left = v31 + v82.left;
        v49 = v82.left + *(_DWORD *)(v12 + 52);
        rect.left = v49;
        if ( (*(_DWORD *)(v12 + 8) & 0x1000) != 0 )
        {
          LODWORD(RectRgnIndirect) = v48;
          v50 = v49 + *(_DWORD *)(v12 + 56);
          v83.right = v50;
        }
        else
        {
          v83.right = v49;
          v50 = v49;
          LODWORD(RectRgnIndirect) = v48 + *(_DWORD *)(v12 + 56);
        }
        rect.right = RectRgnIndirect;
        goto LABEL_54;
      }
    }
    sz = 0;
    *(_QWORD *)cy = 0;
    memset(lParam, 0, 32);
    v32 = lstrlenW(*(LPCWSTR *)&Buffer[4]);
    GetTextExtentPointW(a2, v29, v32, &sz);
    v21 = (*(_DWORD *)(v12 + 8) & 0x800) == 0;
    sz.cx += 2 * *(_DWORD *)(a1 + 164);
    if ( v21 )
    {
      GetObjectW(*(HANDLE *)(v12 + 24), 32, lParam);
      top = lParam[0].top;
    }
    else
    {
      ImageList_GetIconSize(*(HIMAGELIST *)(a1 + 128), cy, &cy[1]);
      top = cy[0];
    }
    v34 = sz.cx;
    v35 = top + 2 * *(_DWORD *)(a1 + 168);
    v36 = v35 + sz.cx;
    *(_DWORD *)(v12 + 56) = v35 + sz.cx;
    v37 = v82.left;
    v38 = v82.right - v82.left;
    v39 = v82.right - v82.left - v36;
    if ( v39 >= 0 )
    {
      v38 = v36;
    }
    else
    {
      *(_DWORD *)(v12 + 56) = v38;
      v39 = 0;
      v37 = v82.left;
    }
    v40 = *(_DWORD *)(v12 + 8) & 3;
    if ( (*(_DWORD *)(v12 + 8) & 0x1000) == 0 )
    {
      if ( v40 )
      {
        v46 = v40 - 1;
        if ( v46 )
        {
          if ( v46 == 1 )
            *(_DWORD *)(v12 + 48) = v37 + ((unsigned int)v39 >> 1);
        }
        else
        {
          *(_DWORD *)(v12 + 48) = v82.right - v38;
        }
      }
      else
      {
        *(_DWORD *)(v12 + 48) = v37;
      }
      v43 = (LONG *)(v12 + 48);
      v44 = *(_DWORD *)(v12 + 48);
      *(_DWORD *)(v12 + 52) = v35 + v44;
      if ( v35 + v44 > v82.right )
        *(_DWORD *)(v12 + 52) = v82.right;
      v45 = v82.left;
      goto LABEL_48;
    }
    if ( v40 )
    {
      v41 = v40 - 1;
      if ( v41 )
      {
        if ( v41 != 1 )
          goto LABEL_34;
        v42 = v37 + ((unsigned int)v39 >> 1);
      }
      else
      {
        v42 = v82.right - v38;
      }
      *(_DWORD *)(v12 + 52) = v42;
    }
    else
    {
      *(_DWORD *)(v12 + 52) = v37;
    }
LABEL_34:
    v43 = (LONG *)(v12 + 48);
    if ( v39 )
      v44 = v34 + *(_DWORD *)(v12 + 52);
    else
      v44 = v82.right - v35;
    *v43 = v44;
    v45 = v82.left;
    if ( v44 < v82.left )
    {
      *v43 = v82.left;
      v45 = v82.left;
      v44 = v82.left;
    }
LABEL_48:
    v31 = v44 - v45;
    *v43 = v31;
    *(_DWORD *)(v12 + 52) -= v82.left;
    goto LABEL_49;
  }
  v20 = *a5;
  v81[7] = v7;
  v81[4] = a2;
  *(RECT *)&v81[5] = v20;
  v21 = (*(_BYTE *)(a1 + 48) & 1) == 0;
  LODWORD(v81[8]) = v13;
  v81[9] = *(_QWORD *)(ItemPtrByOrder + 40);
  if ( v21 )
    LODWORD(v81[8]) = v13 | 0x200;
  LODWORD(RectRgnIndirect) = CICustomDrawNotify(a1, 65537, v81);
  v70 = RectRgnIndirect;
  if ( (RectRgnIndirect & 4) == 0 )
    goto LABEL_13;
  return RectRgnIndirect;
}

```

## disassembly

```asm
0x18005ec54  push    rbp
0x18005ec56  push    rbx
0x18005ec57  push    rsi
0x18005ec58  push    rdi
0x18005ec59  push    r12
0x18005ec5b  push    r13
0x18005ec5d  push    r14
0x18005ec5f  push    r15
0x18005ec61  lea     rbp, [rsp-2D8h]
0x18005ec69  sub     rsp, 3D8h
0x18005ec70  mov     rax, cs:__security_cookie
0x18005ec77  xor     rax, rsp
0x18005ec7a  mov     [rbp+310h+var_50], rax
0x18005ec81  mov     r14, [rbp+310h+arg_20]
0x18005ec88  xorps   xmm0, xmm0
0x18005ec8b  xorps   xmm1, xmm1
0x18005ec8e  mov     [rsp+410h+var_398], r8d
0x18005ec93  mov     r13, rdx
0x18005ec96  movsxd  r12, r9d
0x18005ec99  xor     edx, edx; Val
0x18005ec9b  mov     edi, r8d
0x18005ec9e  mov     rsi, rcx
0x18005eca1  lea     rcx, [rbp+310h+Buffer]; void *
0x18005eca5  movups  xmmword ptr [rbp+310h+var_2D0.left], xmm0
0x18005eca9  lea     r8d, [rdx+40h]; Size
0x18005ecad  movups  xmmword ptr [rbp+310h+y], xmm1
0x18005ecb1  movups  xmmword ptr [rbp+310h+y1], xmm0
0x18005ecb5  movups  xmmword ptr [rbp+310h+rect.left], xmm1
0x18005ecb9  movups  [rbp+310h+var_2C0], xmm0
0x18005ecbd  call    memset
0x18005ecc2  mov     rcx, rsi
0x18005ecc5  call    Header_IsTracking
0x18005ecca  xor     edx, edx; Val
0x18005eccc  lea     rcx, [rbp+310h+var_320]; void *
0x18005ecd0  mov     ebx, eax
0x18005ecd2  lea     r8d, [rdx+50h]; Size
0x18005ecd6  call    memset
0x18005ecdb  movups  xmm0, xmmword ptr [r14]
0x18005ecdf  mov     edx, edi
0x18005ece1  mov     rcx, rsi
0x18005ece4  movdqu  xmmword ptr [rbp+310h+y], xmm0
0x18005ece9  movdqu  xmmword ptr [rbp+310h+var_2D0.left], xmm0
0x18005ecee  call    Header_GetItemPtrByOrder
0x18005ecf3  mov     rdi, rax
0x18005ecf6  test    ebx, ebx
0x18005ecf8  jz      short loc_18005ED13
0x18005ecfa  test    byte ptr [rsi+68h], 2
0x18005ecfe  jz      short loc_18005ED13
0x18005ed00  cmp     [rsi+60h], r12d
0x18005ed04  jnz     short loc_18005ED13
0x18005ed06  test    byte ptr [rsi+64h], 1
0x18005ed0a  jz      short loc_18005ED13
0x18005ed0c  mov     ebx, 1
0x18005ed11  jmp     short loc_18005ED15
0x18005ed13  xor     ebx, ebx
0x18005ed15  test    dword ptr [rax+8], 8000h
0x18005ed1c  mov     [rsp+410h+var_3BC], ebx
0x18005ed20  jz      loc_18005EDA6
0x18005ed26  xor     r15d, r15d
0x18005ed29  lea     rcx, [rbp+310h+lParam]; void *
0x18005ed2d  xor     edx, edx; Val
0x18005ed2f  mov     dword ptr [rsp+410h+var_3B8], r15d
0x18005ed34  lea     r8d, [r15+40h]; Size
0x18005ed38  call    memset
0x18005ed3d  mov     rcx, [rsi]; hWnd
0x18005ed40  or      dword ptr [rsi+64h], 4
0x18005ed44  mov     dword ptr [rbp+310h+lParam], 64h ; 'd'
0x18005ed4b  call    cs:__imp_GetDlgCtrlID
0x18005ed51  movups  xmm0, xmmword ptr [r14]
0x18005ed55  mov     rcx, [rsi+8]; hWnd
0x18005ed59  lea     r9, [rbp+310h+lParam]; lParam
0x18005ed5d  mov     r8d, eax; wParam
0x18005ed60  lea     edx, [r15+2Bh]; Msg
0x18005ed64  xor     eax, eax
0x18005ed66  mov     dword ptr [rbp+310h+lParam+4], r8d
0x18005ed6a  test    ebx, ebx
0x18005ed6c  mov     dword ptr [rbp+310h+lParam+8], r12d
0x18005ed70  mov     dword ptr [rbp+310h+lParam+0Ch], 1
0x18005ed77  setnz   al
0x18005ed7a  mov     [rbp+310h+var_340], r13
0x18005ed7e  mov     dword ptr [rbp+310h+var_350], eax
0x18005ed81  mov     rax, [rsi]
0x18005ed84  mov     qword ptr [rbp+310h+var_350+8], rax
0x18005ed88  mov     rax, [rdi+28h]
0x18005ed8c  mov     [rbp+310h+var_328], rax
0x18005ed90  movdqu  [rbp+310h+var_338], xmm0
0x18005ed95  call    cs:__imp_SendMessageW
0x18005ed9b  test    rax, rax
0x18005ed9e  jnz     loc_18005F589
0x18005eda4  jmp     short loc_18005EDF3
0x18005eda6  movups  xmm0, xmmword ptr [r14]
0x18005edaa  xor     ecx, ecx
0x18005edac  mov     [rbp+310h+var_2E8], r12
0x18005edb0  test    ebx, ebx
0x18005edb2  mov     [rbp+310h+var_300], r13
0x18005edb6  movdqu  [rbp+310h+var_2F8], xmm0
0x18005edbb  setnz   cl
0x18005edbe  test    byte ptr [rsi+30h], 1
0x18005edc2  mov     [rbp+310h+var_2E0], ecx
0x18005edc5  mov     rax, [rax+28h]
0x18005edc9  mov     [rbp+310h+var_2D8], rax
0x18005edcd  jnz     short loc_18005EDD6
0x18005edcf  bts     ecx, 9
0x18005edd3  mov     [rbp+310h+var_2E0], ecx
0x18005edd6  lea     r8, [rbp+310h+var_320]
0x18005edda  mov     edx, 10001h
0x18005eddf  mov     rcx, rsi
0x18005ede2  call    CICustomDrawNotify
0x18005ede7  mov     dword ptr [rsp+410h+var_3B8], eax
0x18005edeb  test    al, 4
0x18005eded  jnz     loc_18005F5BB
0x18005edf3  shl     ebx, 5
0x18005edf6  mov     rcx, r13; hdc
0x18005edf9  add     ebx, 46h ; 'F'
0x18005edfc  xor     r15d, r15d
0x18005edff  mov     dword ptr [rsp+410h+var_3C0], ebx
0x18005ee03  call    cs:__imp_GetTextColor
0x18005ee09  mov     rcx, r13; hdc
0x18005ee0c  mov     [rsp+410h+color], eax
0x18005ee10  call    cs:__imp_GetBkColor
0x18005ee16  test    dword ptr [rsi+10h], 100h
0x18005ee1d  mov     [rsp+410h+var_3A0], eax
0x18005ee21  jz      short loc_18005EE7C
0x18005ee23  movups  xmm1, xmmword ptr [r14]
0x18005ee27  mov     eax, [r14+4]
0x18005ee2b  lea     ecx, [r15-0Dh]
0x18005ee2f  not     eax
0x18005ee31  add     eax, [r14+0Ch]
0x18005ee35  cdq
0x18005ee36  movaps  xmmword ptr [rbp+310h+var_2D0.left], xmm1
0x18005ee3a  sub     eax, edx
0x18005ee3c  movq    rdx, xmm1
0x18005ee41  sar     eax, 1
0x18005ee43  mov     r8d, eax
0x18005ee46  shr     rdx, 20h
0x18005ee4a  add     edx, eax
0x18005ee4c  mov     eax, cs:g_cxBorder
0x18005ee52  shl     eax, 2
0x18005ee55  sub     ecx, eax
0x18005ee57  mov     [rbp+310h+var_2D0.bottom], edx
0x18005ee5a  mov     eax, [r14+8]
0x18005ee5e  add     eax, ecx
0x18005ee60  movups  xmmword ptr [rbp+310h+y], xmm1
0x18005ee64  mov     [rbp+310h+y+8], eax
0x18005ee67  movdqu  xmmword ptr [rbp+310h+y1], xmm1
0x18005ee6c  mov     [rbp+310h+y1], eax
0x18005ee6f  lea     eax, [rdx+r8]
0x18005ee73  mov     [rbp+310h+y+0Ch], eax
0x18005ee76  mov     [rbp+310h+y+4], edx
0x18005ee79  mov     [rbp+310h+y1+4], edx
0x18005ee7c  movaps  xmm0, xmmword ptr [rbp+310h+var_2D0.left]
0x18005ee80  movdqa  [rbp+310h+var_2C0], xmm0
0x18005ee85  movdqa  xmmword ptr [rbp+310h+rect.left], xmm0
0x18005ee8a  test    dword ptr [rdi+8], 6800h
0x18005ee91  jz      short loc_18005EEBE
0x18005ee93  lea     rax, [rbp+310h+var_260]
0x18005ee9a  mov     dword ptr [rbp+310h+Buffer], 36h ; '6'
0x18005eea1  lea     r8, [rbp+310h+Buffer]
0x18005eea5  mov     [rbp+310h+lpString], rax
0x18005eea9  mov     edx, r12d
0x18005eeac  mov     dword ptr [rbp+310h+var_288], 104h
0x18005eeb6  mov     rcx, rsi
0x18005eeb9  call    Header_OnGetItem
0x18005eebe  test    dword ptr [rdi+8], 2800h
0x18005eec5  mov     r12, [rbp+310h+lpString]
0x18005eec9  setnz   cl
0x18005eecc  mov     [rbp+310h+var_390], r12
0x18005eed0  bt      dword ptr [rdi+8], 0Eh
0x18005eed5  setb    al
0x18005eed8  test    al, cl
0x18005eeda  jz      loc_18005F091
0x18005eee0  mov     eax, 7FFFFFFFh
0x18005eee5  mov     r14d, 1000h
0x18005eeeb  cmp     [rdi+34h], eax
0x18005eeee  jz      short loc_18005EEFB
0x18005eef0  mov     ecx, [rdi+30h]
0x18005eef3  cmp     ecx, eax
0x18005eef5  jnz     loc_18005F059
0x18005eefb  xorps   xmm0, xmm0
0x18005eefe  mov     qword ptr [rsp+410h+sz.cx], r15
0x18005ef03  mov     rcx, r12; lpString
0x18005ef06  mov     qword ptr [rsp+410h+cy], r15
0x18005ef0b  movups  xmmword ptr [rbp+310h+lParam], xmm0
0x18005ef0f  movups  [rbp+310h+var_350], xmm0
0x18005ef13  call    cs:__imp_lstrlenW
0x18005ef19  lea     r9, [rsp+410h+sz]; lpsz
0x18005ef1e  mov     rdx, r12; lpString
0x18005ef21  mov     r8d, eax; c
0x18005ef24  mov     rcx, r13; hdc
0x18005ef27  call    cs:__imp_GetTextExtentPointW
0x18005ef2d  test    dword ptr [rdi+8], 800h
0x18005ef34  mov     eax, [rsp+410h+sz.cx]
0x18005ef38  mov     ecx, [rsi+0A4h]
0x18005ef3e  lea     ecx, [rax+rcx*2]
0x18005ef41  mov     [rsp+410h+sz.cx], ecx
0x18005ef45  jz      short loc_18005EF63
0x18005ef47  mov     rcx, [rsi+80h]; himl
0x18005ef4e  lea     r8, [rsp+410h+cy+4]; cy
0x18005ef53  lea     rdx, [rsp+410h+cy]; cx
0x18005ef58  call    ImageList_GetIconSize
0x18005ef5d  mov     ecx, [rsp+410h+cy]
0x18005ef61  jmp     short loc_18005EF79
0x18005ef63  mov     rcx, [rdi+18h]; h
0x18005ef67  lea     r8, [rbp+310h+lParam]; pv
0x18005ef6b  mov     edx, 20h ; ' '; c
0x18005ef70  call    cs:__imp_GetObjectW
0x18005ef76  mov     ecx, dword ptr [rbp+310h+lParam+4]
0x18005ef79  mov     eax, [rsi+0A8h]
0x18005ef7f  mov     r10d, [rsp+410h+sz.cx]
0x18005ef84  lea     r11d, [rcx+rax*2]
0x18005ef88  lea     eax, [r11+r10]
0x18005ef8c  mov     [rdi+38h], eax
0x18005ef8f  mov     r8d, [rbp+310h+var_2D0.right]
0x18005ef93  mov     r9d, [rbp+310h+var_2D0.left]
0x18005ef97  sub     r8d, r9d
0x18005ef9a  mov     edx, r8d
0x18005ef9d  sub     edx, eax
0x18005ef9f  jns     short loc_18005EFAD
0x18005efa1  mov     [rdi+38h], r8d
0x18005efa5  xor     edx, edx
0x18005efa7  mov     r9d, [rbp+310h+var_2D0.left]
0x18005efab  jmp     short loc_18005EFB0
0x18005efad  mov     r8d, eax
0x18005efb0  mov     ecx, [rdi+8]
0x18005efb3  and     ecx, 3
0x18005efb6  test    [rdi+8], r14d
0x18005efba  jz      short loc_18005F00C
0x18005efbc  test    ecx, ecx
0x18005efbe  jz      short loc_18005EFDE
0x18005efc0  sub     ecx, 1
0x18005efc3  jz      short loc_18005EFD3
0x18005efc5  cmp     ecx, 1
0x18005efc8  jnz     short loc_18005EFE2
0x18005efca  mov     eax, edx
0x18005efcc  shr     eax, 1
0x18005efce  add     eax, r9d
0x18005efd1  jmp     short loc_18005EFD9
0x18005efd3  mov     eax, [rbp+310h+var_2D0.right]
0x18005efd6  sub     eax, r8d
0x18005efd9  mov     [rdi+34h], eax
0x18005efdc  jmp     short loc_18005EFE2
0x18005efde  mov     [rdi+34h], r9d
0x18005efe2  lea     r8, [rdi+30h]
0x18005efe6  test    edx, edx
0x18005efe8  jnz     short loc_18005EFF2
0x18005efea  mov     ecx, [rbp+310h+var_2D0.right]
0x18005efed  sub     ecx, r11d
0x18005eff0  jmp     short loc_18005EFF8
0x18005eff2  mov     ecx, [rdi+34h]
0x18005eff5  add     ecx, r10d
0x18005eff8  mov     [r8], ecx
0x18005effb  mov     eax, [rbp+310h+var_2D0.left]
0x18005effe  cmp     ecx, eax
0x18005f000  jge     short loc_18005F04E
0x18005f002  mov     [r8], eax
0x18005f005  mov     eax, [rbp+310h+var_2D0.left]
0x18005f008  mov     ecx, eax
0x18005f00a  jmp     short loc_18005F04E
0x18005f00c  test    ecx, ecx
0x18005f00e  jz      short loc_18005F02F
0x18005f010  sub     ecx, 1
0x18005f013  jz      short loc_18005F024
0x18005f015  cmp     ecx, 1
0x18005f018  jnz     short loc_18005F033
0x18005f01a  shr     edx, 1
0x18005f01c  add     edx, r9d
0x18005f01f  mov     [rdi+30h], edx
0x18005f022  jmp     short loc_18005F033
0x18005f024  mov     eax, [rbp+310h+var_2D0.right]
0x18005f027  sub     eax, r8d
0x18005f02a  mov     [rdi+30h], eax
0x18005f02d  jmp     short loc_18005F033
0x18005f02f  mov     [rdi+30h], r9d
0x18005f033  lea     r8, [rdi+30h]
0x18005f037  mov     ecx, [r8]
0x18005f03a  lea     eax, [r11+rcx]
0x18005f03e  mov     [rdi+34h], eax
0x18005f041  mov     edx, [rbp+310h+var_2D0.right]
0x18005f044  cmp     eax, edx
0x18005f046  jle     short loc_18005F04B
0x18005f048  mov     [rdi+34h], edx
0x18005f04b  mov     eax, [rbp+310h+var_2D0.left]
0x18005f04e  sub     ecx, eax
0x18005f050  mov     [r8], ecx
0x18005f053  mov     eax, [rbp+310h+var_2D0.left]
0x18005f056  sub     [rdi+34h], eax
0x18005f059  mov     r11d, [rbp+310h+var_2D0.left]
0x18005f05d  lea     r9d, [rcx+r11]
0x18005f061  mov     dword ptr [rbp+310h+var_2C0], r9d
0x18005f065  mov     ecx, [rdi+34h]
0x18005f068  add     ecx, r11d
0x18005f06b  mov     [rbp+310h+rect.left], ecx
0x18005f06e  test    [rdi+8], r14d
0x18005f072  jz      short loc_18005F084
0x18005f074  mov     edx, [rdi+38h]
0x18005f077  mov     eax, r9d
0x18005f07a  add     edx, ecx
0x18005f07c  mov     dword ptr [rbp+310h+var_2C0+8], edx
0x18005f07f  mov     [rbp+310h+rect.right], eax
0x18005f082  jmp     short loc_18005F0A2
  ... truncated ...
```
