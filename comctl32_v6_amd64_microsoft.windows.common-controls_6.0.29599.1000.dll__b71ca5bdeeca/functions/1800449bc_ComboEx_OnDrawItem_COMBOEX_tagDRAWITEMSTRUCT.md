# ComboEx_OnDrawItem(COMBOEX *,tagDRAWITEMSTRUCT *)

- ea: `0x1800449bc`
- end: `0x180045120`
- name: `?ComboEx_OnDrawItem@@YAXPEAUCOMBOEX@@PEAUtagDRAWITEMSTRUCT@@@Z`
- size: `1892`
- prototype: `void __fastcall(struct COMBOEX *, struct tagDRAWITEMSTRUCT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800483a0`

## callees

- `0x180016c78`
- `0x1800449bc`
- `0x180045128`
- `0x1800b16b0`
- `0x1800c4030`
- `0x180114520`
- `0x18013e45c`

## import_xrefs

- `GDI32!SetTextAlign` at `0x180044e1b`
- `GDI32!SetTextAlign` at `0x180045115`
- `GDI32!SetTextAlign` at `0x180044e1b`
- `GDI32!SetTextAlign` at `0x180045115`
- `GDI32!CreateSolidBrush` at `0x180044d76`
- `GDI32!CreateSolidBrush` at `0x180044d76`
- `GDI32!DeleteObject` at `0x180044dc4`
- `GDI32!DeleteObject` at `0x180044dcd`
- `GDI32!DeleteObject` at `0x180044dc4`
- `GDI32!DeleteObject` at `0x180044dcd`
- `GDI32!SetBkColor` at `0x180044bd7`
- `GDI32!SetBkColor` at `0x180044c88`
- `GDI32!SetBkColor` at `0x180044bd7`
- `GDI32!SetBkColor` at `0x180044c88`
- `GDI32!SetTextColor` at `0x180044bed`
- `GDI32!SetTextColor` at `0x180044fa4`
- `GDI32!SetTextColor` at `0x180044bed`
- `GDI32!SetTextColor` at `0x180044fa4`
- `GDI32!GetTextAlign` at `0x180044e08`
- `GDI32!GetTextAlign` at `0x180044e08`
- `GDI32!SelectObject` at `0x180044d6a`
- `GDI32!SelectObject` at `0x180044d85`
- `GDI32!SelectObject` at `0x180044daf`
- `GDI32!SelectObject` at `0x180044dbb`
- `GDI32!SelectObject` at `0x180044d6a`
- `GDI32!SelectObject` at `0x180044d85`
- `GDI32!SelectObject` at `0x180044daf`
- `GDI32!SelectObject` at `0x180044dbb`
- `GDI32!CreatePen` at `0x180044d5b`
- `GDI32!CreatePen` at `0x180044d5b`
- `GDI32!GetTextExtentPointW` at `0x180044b49`
- `GDI32!GetTextExtentPointW` at `0x180044b49`
- `GDI32!Rectangle` at `0x180044da3`
- `GDI32!Rectangle` at `0x180044da3`
- `USER32!DrawFocusRect` at `0x180045103`
- `USER32!DrawFocusRect` at `0x180045103`
- `USER32!DrawTextExW` at `0x180044df3`
- `USER32!DrawTextExW` at `0x180044df3`
- `USER32!IsWindowEnabled` at `0x180044a1e`
- `USER32!IsWindowEnabled` at `0x180044a1e`
- `USER32!GetWindowLongW` at `0x180044a49`
- `USER32!GetWindowLongW` at `0x180044a49`
- `USER32!SendMessageW` at `0x180044e72`
- `USER32!SendMessageW` at `0x180044e72`
- `USER32!GetWindowLongPtrW` at `0x180044a32`
- `USER32!GetWindowLongPtrW` at `0x180044a32`
- `USER32!GetSysColor` at `0x180044bcc`
- `USER32!GetSysColor` at `0x180044be2`
- `USER32!GetSysColor` at `0x180044c7d`
- `USER32!GetSysColor` at `0x180044f79`
- `USER32!GetSysColor` at `0x180045008`
- `USER32!GetSysColor` at `0x180044bcc`
- `USER32!GetSysColor` at `0x180044be2`
- `USER32!GetSysColor` at `0x180044c7d`
- `USER32!GetSysColor` at `0x180044f79`
- `USER32!GetSysColor` at `0x180045008`
- `UxTheme!DrawThemeText` at `0x180044ff6`
- `UxTheme!DrawThemeText` at `0x180044ff6`
- `UxTheme!GetThemeColor` at `0x180044cbc`
- `UxTheme!GetThemeColor` at `0x180044d3f`
- `UxTheme!GetThemeColor` at `0x180044cbc`
- `UxTheme!GetThemeColor` at `0x180044d3f`

## pseudocode

```c
void __fastcall ComboEx_OnDrawItem(struct COMBOEX *a1, struct tagDRAWITEMSTRUCT *a2)
{
  HDC hDC; // r12
  HWND v4; // rcx
  LONG_PTR WindowLongPtrW; // rbx
  __int64 v7; // r11
  bool v8; // zf
  int v9; // r14d
  struct _IMAGELIST *v10; // rdx
  int v11; // eax
  int v12; // esi
  int v13; // ecx
  int v14; // edx
  __int64 v15; // rcx
  WCHAR *v16; // rax
  __int64 v17; // r14
  __int64 v18; // rdi
  int v19; // ebx
  int v20; // eax
  COLORREF SysColor; // eax
  COLORREF v22; // eax
  int v23; // ecx
  COLORREF v24; // eax
  COLORREF v25; // eax
  HPEN Pen; // r14
  HGDIOBJ v27; // rdi
  HBRUSH SolidBrush; // rsi
  HGDIOBJ v29; // rbx
  int v30; // eax
  UINT itemID; // ebx
  const unsigned __int16 *v32; // r8
  COLORREF CueBannerFontColor; // eax
  LONG right; // eax
  int v35; // eax
  int v36; // ecx
  int v37; // r8d
  int iImage; // edx
  int v39; // [rsp+50h] [rbp-B0h]
  int v40; // [rsp+54h] [rbp-ACh]
  int v41; // [rsp+58h] [rbp-A8h]
  int v42; // [rsp+5Ch] [rbp-A4h]
  int v43; // [rsp+60h] [rbp-A0h]
  int v44; // [rsp+64h] [rbp-9Ch]
  UINT align; // [rsp+68h] [rbp-98h]
  UINT format[2]; // [rsp+70h] [rbp-90h]
  int formata; // [rsp+70h] [rbp-90h]
  UINT formatb; // [rsp+70h] [rbp-90h]
  LONG v49; // [rsp+78h] [rbp-88h]
  int x; // [rsp+7Ch] [rbp-84h]
  int v51; // [rsp+80h] [rbp-80h]
  int cchText; // [rsp+88h] [rbp-78h]
  struct tagCOMBOBOXEXITEMW v53; // [rsp+90h] [rbp-70h] BYREF
  COLORREF color; // [rsp+C8h] [rbp-38h] BYREF
  int v55; // [rsp+CCh] [rbp-34h] BYREF
  int bottom[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v57; // [rsp+E0h] [rbp-20h] BYREF
  struct tagSIZE sz; // [rsp+E8h] [rbp-18h] BYREF
  struct tagRECT rc; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR String[264]; // [rsp+100h] [rbp+0h] BYREF

  hDC = a2->hDC;
  v4 = (HWND)*((_QWORD *)a1 + 8);
  *(RECT *)bottom = a2->rcItem;
  sz = 0;
  memset(&v53, 0, sizeof(v53));
  v42 = IsWindowEnabled(v4);
  align = 0;
  WindowLongPtrW = GetWindowLongPtrW(*((HWND *)a1 + 8), 0);
  *(_QWORD *)format = WindowLongPtrW;
  v51 = GetWindowLongW(a2->hwndItem, -20) & 0x2000;
  if ( v51 )
  {
    align = GetTextAlign(hDC);
    SetTextAlign(hDC, align | 0x100);
  }
  v7 = 0;
  v8 = a2->itemID == -1;
  v9 = 0;
  v44 = 0;
  v40 = 0;
  String[0] = 0;
  if ( !v8 )
  {
    v53.mask = 31;
    v53.pszText = String;
    v53.iItem = (int)a2->itemID;
    v53.cchTextMax = 260;
    ComboEx_OnGetItem(a1, &v53);
    v30 = *((_DWORD *)a1 + 27);
    if ( v30 == a2->itemID
      || v30 == -1 && (itemID = a2->itemID, itemID == (unsigned int)SendMessageW(*((HWND *)a1 + 8), 0x147u, 0, 0)) )
    {
      v44 = 1;
    }
    goto LABEL_6;
  }
  if ( (*((_BYTE *)a1 + 148) & 1) != 0 )
  {
    v53.mask = 31;
    v53.pszText = String;
    v53.cchTextMax = 260;
    v53.iItem = -1;
    ComboEx_OnGetItem(a1, &v53);
LABEL_6:
    v7 = 0;
    goto LABEL_7;
  }
  v32 = *(const unsigned __int16 **)(WindowLongPtrW + 224);
  if ( v32 )
  {
    StringCchCopyW(String, 0x104u, v32);
    v9 = 1;
    v40 = 1;
  }
LABEL_7:
  v10 = (struct _IMAGELIST *)*((_QWORD *)a1 + 11);
  v11 = v7;
  v55 = v7;
  v57 = v7;
  if ( v10 )
  {
    if ( (*((_BYTE *)a1 + 80) & 2) == 0 )
    {
      DPISCALEINFO::GetIconSize((struct COMBOEX *)((char *)a1 + 52), v10, &v55, &v57);
      v11 = v55;
      v7 = 0;
      if ( v55 )
      {
        v11 = v55 + 4;
        v55 += 4;
      }
    }
  }
  v12 = v7;
  if ( (a2->itemState & 0x1000) != 0 )
  {
    v13 = v7;
    LOBYTE(v12) = *((_QWORD *)a1 + 9) != v7;
    v39 = v12;
    if ( (*((_BYTE *)a1 + 80) & 2) != 0 )
    {
      v11 = v7;
    }
    else
    {
      v39 = v12;
      if ( !v9 )
        goto LABEL_10;
      v11 = 4;
    }
    v55 = v11;
    goto LABEL_10;
  }
  v39 = v7;
  v13 = *((_DWORD *)a1 + 26) * v53.iIndent + 3;
LABEL_10:
  v14 = bottom[0];
  x = bottom[0] + v13;
  v49 = bottom[0] + v13 + v11;
  v15 = 260;
  v16 = String;
  do
  {
    if ( *v16 == (_WORD)v7 )
      break;
    ++v16;
    --v15;
  }
  while ( v15 );
  v17 = (260 - v15) & -(__int64)(v15 != 0);
  cchText = v17;
  if ( v15 )
  {
    GetTextExtentPointW(hDC, String, v17, &sz);
    v14 = bottom[0];
    v7 = 0;
  }
  else
  {
    LODWORD(v17) = v7;
    cchText = v7;
  }
  v18 = *(_QWORD *)format;
  bottom[0] = v14 + 1;
  if ( *(_QWORD *)(*(_QWORD *)format + 16LL) == v7 )
    --bottom[2];
  if ( a2->itemAction == 4 )
    goto LABEL_91;
  v19 = v7;
  v43 = (bottom[1] + bottom[3]) / 2;
  formata = sz.cy / 2;
  if ( (*((_BYTE *)a1 + 148) & 0x40) == 0
    || *(_QWORD *)(v18 + 16) == v7
    || (*((_DWORD *)a1 + 4) & 3) == 2
    || (v20 = 1, (a2->itemState & 0x1000) == 0) )
  {
    v20 = v7;
  }
  v41 = v20;
  if ( (a2->itemState & 1) != 0 && !v20 )
    v19 = 1;
  if ( v42 == (_DWORD)v7 )
  {
    SysColor = GetSysColor(15);
    SetBkColor(hDC, SysColor);
    v22 = GetSysColor(17);
  }
  else
  {
    v24 = GetSysColor(8 * v19 + 5);
    SetBkColor(hDC, v24);
    v8 = (*((_BYTE *)a1 + 80) & 0x40) == 0;
    color = 0;
    if ( v8 || GetThemeColor(*(HTHEME *)(v18 + 16), 9, v19 + 1, 3803, &color) < 0 )
    {
      v22 = GetSysColor(v19 != 0 ? 14 : 8);
      color = v22;
    }
    else
    {
      v22 = color;
    }
  }
  SetTextColor(hDC, v22);
  if ( !v40 )
    goto LABEL_24;
  if ( !*(_QWORD *)(v18 + 16) )
  {
    CueBannerFontColor = ComboBox_GetCueBannerFontColor((struct tagCBox *)v18);
    SetTextColor(hDC, CueBannerFontColor);
LABEL_24:
    v23 = 5;
    goto LABEL_25;
  }
  v23 = 8;
LABEL_25:
  if ( (a2->itemState & 0x1000) != 0 )
  {
    right = bottom[2];
    if ( bottom[2] > a2->rcItem.right )
      right = a2->rcItem.right;
    bottom[2] = right;
  }
  if ( !v12 && (int)v17 > 0 )
  {
    *(_QWORD *)&rc.right = *(_QWORD *)&bottom[2];
    rc.left = v49;
    rc.top = v43 - formata;
    formatb = ((*((_DWORD *)a1 + 20) & 0x20) << 10) | 0x820;
    if ( v41 )
    {
      DrawThemeText(
        *(HTHEME *)(v18 + 16),
        hDC,
        v23,
        1,
        String,
        v17,
        ((*((_DWORD *)a1 + 20) & 0x20) << 10) | 0x820,
        0,
        &rc);
    }
    else
    {
      v8 = (*((_BYTE *)a1 + 80) & 0x40) == 0;
      color = 0;
      if ( v8 || GetThemeColor(*(HTHEME *)(v18 + 16), 9, v19 + 1, 3802, &color) < 0 )
      {
        v25 = GetSysColor(8 * v19 + 5);
        color = v25;
      }
      else
      {
        v25 = color;
      }
      Pen = CreatePen(6, 1, v25);
      v27 = SelectObject(hDC, Pen);
      SolidBrush = CreateSolidBrush(color);
      v29 = SelectObject(hDC, SolidBrush);
      Rectangle(hDC, bottom[0], bottom[1], bottom[2], bottom[3]);
      SelectObject(hDC, v27);
      SelectObject(hDC, v29);
      DeleteObject(Pen);
      DeleteObject(SolidBrush);
      DrawTextExW(hDC, String, cchText, &rc, formatb, 0);
      v12 = v39;
    }
  }
  if ( *((_QWORD *)a1 + 11)
    && (a2->itemID != -1 || (*((_BYTE *)a1 + 148) & 1) != 0)
    && ((*((_DWORD *)a1 + 20) & 3) == 0 || (a2->itemState & 0x1000) == 0) )
  {
    v35 = *((_DWORD *)a1 + 37);
    if ( (v35 & 0x20) != 0 || (v35 & 0x40) != 0 || (v36 = 0, (a2->itemState & 0x1000) != 0) && !v42 )
      v36 = 1;
    if ( (a2->itemID != -1 || (v35 & 1) != 0) && (*((_DWORD *)a1 + 20) & 3) == 0 )
    {
      if ( (a2->itemState & 1) != 0 )
        v36 |= 6u;
      v37 = v36 | 0x4000;
      if ( (*((_DWORD *)a1 + 15) & 1) == 0 )
        v37 = v36;
      iImage = v53.iImage;
      if ( v44 )
        iImage = v53.iSelectedImage;
      ImageList_Draw(*((HIMAGELIST *)a1 + 11), iImage, hDC, x, v43 - v57 / 2, (v53.iOverlay << 8) | v37);
    }
  }
  if ( a2->itemAction == 4 || (a2->itemState & 0x10) != 0 )
  {
LABEL_91:
    if ( (*((_BYTE *)a1 + 48) & 1) == 0 && !v12 )
      DrawFocusRect(hDC, (const RECT *)bottom);
  }
  if ( v51 )
    SetTextAlign(hDC, align);
}

```

## disassembly

```asm
0x1800449bc  mov     [rsp-8+arg_10], rbx
0x1800449c1  push    rbp
0x1800449c2  push    rsi
0x1800449c3  push    rdi
0x1800449c4  push    r12
0x1800449c6  push    r13
0x1800449c8  push    r14
0x1800449ca  push    r15
0x1800449cc  lea     rbp, [rsp-220h]
0x1800449d4  sub     rsp, 320h
0x1800449db  mov     rax, cs:__security_cookie
0x1800449e2  xor     rax, rsp
0x1800449e5  mov     [rbp+250h+var_40], rax
0x1800449ec  movups  xmm0, xmmword ptr [rdx+28h]
0x1800449f0  mov     r12, [rdx+20h]
0x1800449f4  mov     r15, rcx
0x1800449f7  mov     rcx, [rcx+40h]; hWnd
0x1800449fb  xor     eax, eax
0x1800449fd  movdqu  xmmword ptr [rbp+250h+bottom], xmm0
0x180044a02  mov     [rbp+250h+var_2C0.lParam], rax
0x180044a06  xor     ebx, ebx
0x180044a08  xorps   xmm0, xmm0
0x180044a0b  mov     qword ptr [rbp+250h+sz.cx], rbx
0x180044a0f  movups  xmmword ptr [rbp+250h+var_2C0.mask], xmm0
0x180044a13  mov     r13, rdx
0x180044a16  movups  xmmword ptr [rbp+250h+var_2C0.pszText], xmm0
0x180044a1a  movups  xmmword ptr [rbp+250h+var_2C0.iSelectedImage], xmm0
0x180044a1e  call    cs:__imp_IsWindowEnabled
0x180044a24  mov     rcx, [r15+40h]; hWnd
0x180044a28  xor     edx, edx; nIndex
0x180044a2a  mov     [rsp+350h+var_2F4], eax
0x180044a2e  mov     [rsp+350h+align], ebx
0x180044a32  call    cs:__imp_GetWindowLongPtrW
0x180044a38  mov     rcx, [r13+18h]; hWnd
0x180044a3c  mov     edx, 0FFFFFFECh; nIndex
0x180044a41  mov     rbx, rax
0x180044a44  mov     qword ptr [rsp+350h+format], rax
0x180044a49  call    cs:__imp_GetWindowLongW
0x180044a4f  and     eax, 2000h
0x180044a54  mov     [rbp+250h+var_2D0], eax
0x180044a57  jnz     loc_180044E05
0x180044a5d  xor     r11d, r11d
0x180044a60  mov     edi, 104h
0x180044a65  cmp     dword ptr [r13+8], 0FFFFFFFFh
0x180044a6a  mov     r14d, r11d
0x180044a6d  mov     [rsp+350h+var_2EC], r11d
0x180044a72  mov     [rsp+350h+var_2FC], r11d
0x180044a77  lea     esi, [r11+1]
0x180044a7b  mov     [rbp+250h+String], r11w
0x180044a80  jnz     loc_180044E26
0x180044a86  test    [r15+94h], sil
0x180044a8d  jz      loc_180044E89
0x180044a93  lea     rax, [rbp+250h+String]
0x180044a97  mov     [rbp+250h+var_2C0.mask], 1Fh
0x180044a9e  lea     rdx, [rbp+250h+var_2C0]; struct tagCOMBOBOXEXITEMW *
0x180044aa2  mov     [rbp+250h+var_2C0.pszText], rax
0x180044aa6  mov     rcx, r15; struct COMBOEX *
0x180044aa9  mov     [rbp+250h+var_2C0.cchTextMax], edi
0x180044aac  mov     [rbp+250h+var_2C0.iItem], 0FFFFFFFFFFFFFFFFh
0x180044ab4  call    ?ComboEx_OnGetItem@@YAHPEAUCOMBOEX@@PEAUtagCOMBOBOXEXITEMW@@@Z; ComboEx_OnGetItem(COMBOEX *,tagCOMBOBOXEXITEMW *)
0x180044ab9  xor     r11d, r11d
0x180044abc  mov     rdx, [r15+58h]; struct _IMAGELIST *
0x180044ac0  mov     eax, r11d
0x180044ac3  mov     [rbp+250h+var_284], eax
0x180044ac6  mov     r8d, 2
0x180044acc  mov     [rbp+250h+var_270], r11d
0x180044ad0  test    rdx, rdx
0x180044ad3  jnz     loc_180044EB1
0x180044ad9  test    dword ptr [r13+10h], 1000h
0x180044ae1  mov     esi, r11d
0x180044ae4  jnz     loc_180044EE9
0x180044aea  mov     ecx, [rbp+250h+var_2C0.iIndent]
0x180044aed  imul    ecx, [r15+68h]
0x180044af2  mov     [rsp+350h+var_300], r11d
0x180044af7  add     ecx, 3
0x180044afa  mov     edx, [rbp+250h+bottom]
0x180044afd  add     ecx, edx
0x180044aff  add     eax, ecx
0x180044b01  mov     [rsp+350h+x], ecx
0x180044b05  mov     [rsp+350h+var_2D8], eax
0x180044b09  mov     rcx, rdi
0x180044b0c  lea     rax, [rbp+250h+String]
0x180044b10  cmp     [rax], r11w
0x180044b14  jz      short loc_180044B1F
0x180044b16  add     rax, r8
0x180044b19  sub     rcx, 1
0x180044b1d  jnz     short loc_180044B10
0x180044b1f  sub     rdi, rcx
0x180044b22  mov     rax, rcx
0x180044b25  neg     rax
0x180044b28  sbb     r14, r14
0x180044b2b  and     r14, rdi
0x180044b2e  mov     qword ptr [rbp+250h+cchText], r14
0x180044b32  test    rcx, rcx
0x180044b35  jz      loc_180044F1D
0x180044b3b  lea     r9, [rbp+250h+sz]; lpsz
0x180044b3f  mov     r8d, r14d; c
0x180044b42  lea     rdx, [rbp+250h+String]; lpString
0x180044b46  mov     rcx, r12; hdc
0x180044b49  call    cs:__imp_GetTextExtentPointW
0x180044b4f  mov     edx, [rbp+250h+bottom]
0x180044b52  xor     r11d, r11d
0x180044b55  mov     rdi, qword ptr [rsp+350h+format]
0x180044b5a  mov     r8d, 1
0x180044b60  add     edx, r8d
0x180044b63  mov     [rbp+250h+bottom], edx
0x180044b66  cmp     [rdi+10h], r11
0x180044b6a  jz      loc_180044F29
0x180044b70  cmp     dword ptr [r13+0Ch], 4
0x180044b75  jz      loc_1800450EA
0x180044b7b  mov     eax, [rbp+250h+bottom+0Ch]
0x180044b7e  mov     r9d, 2
0x180044b84  add     eax, [rbp+250h+bottom+4]
0x180044b87  mov     ebx, r11d
0x180044b8a  cdq
0x180044b8b  idiv    r9d
0x180044b8e  mov     [rsp+350h+var_2F0], eax
0x180044b92  mov     eax, [rbp+250h+sz.cy]
0x180044b95  cdq
0x180044b96  idiv    r9d
0x180044b99  test    byte ptr [r15+94h], 40h
0x180044ba1  mov     [rsp+350h+format], eax
0x180044ba5  jnz     loc_180044F32
0x180044bab  mov     eax, r11d
0x180044bae  mov     [rsp+350h+var_2F8], eax
0x180044bb2  test    [r13+10h], r8b
0x180044bb6  jnz     loc_180044F62
0x180044bbc  cmp     [rsp+350h+var_2F4], r11d
0x180044bc1  jnz     loc_180044C76
0x180044bc7  mov     ecx, 0Fh; nIndex
0x180044bcc  call    cs:__imp_GetSysColor
0x180044bd2  mov     edx, eax; color
0x180044bd4  mov     rcx, r12; hdc
0x180044bd7  call    cs:__imp_SetBkColor
0x180044bdd  mov     ecx, 11h; nIndex
0x180044be2  call    cs:__imp_GetSysColor
0x180044be8  mov     edx, eax; color
0x180044bea  mov     rcx, r12; hdc
0x180044bed  call    cs:__imp_SetTextColor
0x180044bf3  xor     r11d, r11d
0x180044bf6  cmp     [rsp+350h+var_2FC], r11d
0x180044bfb  jnz     loc_180044F87
0x180044c01  mov     ecx, 5
0x180044c06  test    dword ptr [r13+10h], 1000h
0x180044c0e  jnz     loc_180044FB2
0x180044c14  test    esi, esi
0x180044c16  jz      loc_180044CD2
0x180044c1c  mov     r8d, 1
0x180044c22  cmp     [r15+58h], r11
0x180044c26  jnz     loc_180045016
0x180044c2c  cmp     dword ptr [r13+0Ch], 4
0x180044c31  jz      loc_1800450EA
0x180044c37  test    byte ptr [r13+10h], 10h
0x180044c3c  jnz     loc_1800450EA
0x180044c42  cmp     [rbp+250h+var_2D0], 0
0x180044c46  jnz     loc_18004510E
0x180044c4c  mov     rcx, [rbp+250h+var_40]
0x180044c53  xor     rcx, rsp; StackCookie
0x180044c56  call    __security_check_cookie
0x180044c5b  mov     rbx, [rsp+350h+arg_10]
0x180044c63  add     rsp, 320h
0x180044c6a  pop     r15
0x180044c6c  pop     r14
0x180044c6e  pop     r13
0x180044c70  pop     r12
0x180044c72  pop     rdi
0x180044c73  pop     rsi
0x180044c74  pop     rbp
0x180044c75  retn
0x180044c76  lea     ecx, ds:5[rbx*8]; nIndex
0x180044c7d  call    cs:__imp_GetSysColor
0x180044c83  mov     edx, eax; color
0x180044c85  mov     rcx, r12; hdc
0x180044c88  call    cs:__imp_SetBkColor
0x180044c8e  test    byte ptr [r15+50h], 40h
0x180044c93  mov     [rbp+250h+color], 0
0x180044c9a  jz      loc_180044F6D
0x180044ca0  mov     rcx, [rdi+10h]; hTheme
0x180044ca4  lea     rax, [rbp+250h+color]
0x180044ca8  lea     r8d, [rbx+1]; iStateId
0x180044cac  mov     [rsp+350h+pColor], rax; pColor
0x180044cb1  mov     edx, 9; iPartId
0x180044cb6  mov     r9d, 0EDBh; iPropId
0x180044cbc  call    cs:__imp_GetThemeColor
0x180044cc2  test    eax, eax
0x180044cc4  js      loc_180044F6D
0x180044cca  mov     eax, [rbp+250h+color]
0x180044ccd  jmp     loc_180044BE8
0x180044cd2  test    r14d, r14d
0x180044cd5  jle     loc_180044C1C
0x180044cdb  mov     eax, [rsp+350h+var_2D8]
0x180044cdf  movaps  xmm0, xmmword ptr [rbp+250h+bottom]
0x180044ce3  movdqa  xmmword ptr [rbp+250h+rc.left], xmm0
0x180044ce8  mov     [rbp+250h+rc.left], eax
0x180044ceb  mov     eax, [rsp+350h+var_2F0]
0x180044cef  sub     eax, [rsp+350h+format]
0x180044cf3  mov     [rbp+250h+rc.top], eax
0x180044cf6  mov     eax, [r15+50h]
0x180044cfa  and     eax, 20h
0x180044cfd  shl     eax, 0Ah
0x180044d00  or      eax, 820h
0x180044d05  mov     [rsp+350h+format], eax
0x180044d09  cmp     [rsp+350h+var_2F8], r11d
0x180044d0e  jnz     loc_180044FC6
0x180044d14  test    byte ptr [r15+50h], 40h
0x180044d19  mov     [rbp+250h+color], r11d
0x180044d1d  jz      loc_180045001
0x180044d23  mov     rcx, [rdi+10h]; hTheme
0x180044d27  lea     rax, [rbp+250h+color]
0x180044d2b  lea     r8d, [rbx+1]; iStateId
0x180044d2f  mov     [rsp+350h+pColor], rax; pColor
0x180044d34  mov     edx, 9; iPartId
0x180044d39  mov     r9d, 0EDAh; iPropId
0x180044d3f  call    cs:__imp_GetThemeColor
0x180044d45  test    eax, eax
0x180044d47  js      loc_180045001
0x180044d4d  mov     eax, [rbp+250h+color]
0x180044d50  mov     edx, 1; cWidth
0x180044d55  mov     r8d, eax; color
0x180044d58  lea     ecx, [rdx+5]; iStyle
0x180044d5b  call    cs:__imp_CreatePen
0x180044d61  mov     rdx, rax; h
0x180044d64  mov     rcx, r12; hdc
0x180044d67  mov     r14, rax
0x180044d6a  call    cs:__imp_SelectObject
0x180044d70  mov     ecx, [rbp+250h+color]; color
0x180044d73  mov     rdi, rax
0x180044d76  call    cs:__imp_CreateSolidBrush
0x180044d7c  mov     rdx, rax; h
0x180044d7f  mov     rcx, r12; hdc
0x180044d82  mov     rsi, rax
0x180044d85  call    cs:__imp_SelectObject
0x180044d8b  mov     ecx, [rbp+250h+bottom+0Ch]
0x180044d8e  mov     rbx, rax
0x180044d91  mov     r9d, [rbp+250h+bottom+8]; right
0x180044d95  mov     r8d, [rbp+250h+bottom+4]; top
0x180044d99  mov     edx, [rbp+250h+bottom]; left
0x180044d9c  mov     dword ptr [rsp+350h+pColor], ecx; bottom
0x180044da0  mov     rcx, r12; hdc
0x180044da3  call    cs:__imp_Rectangle
0x180044da9  mov     rdx, rdi; h
0x180044dac  mov     rcx, r12; hdc
0x180044daf  call    cs:__imp_SelectObject
0x180044db5  mov     rdx, rbx; h
0x180044db8  mov     rcx, r12; hdc
0x180044dbb  call    cs:__imp_SelectObject
0x180044dc1  mov     rcx, r14; ho
0x180044dc4  call    cs:__imp_DeleteObject
0x180044dca  mov     rcx, rsi; ho
0x180044dcd  call    cs:__imp_DeleteObject
0x180044dd3  mov     eax, [rsp+350h+format]
0x180044dd7  lea     r9, [rbp+250h+rc]; lprc
0x180044ddb  mov     r8d, [rbp+250h+cchText]; cchText
0x180044ddf  lea     rdx, [rbp+250h+String]; lpchText
0x180044de3  mov     rcx, r12; hdc
0x180044de6  mov     [rsp+350h+lpdtp], 0; lpdtp
0x180044def  mov     dword ptr [rsp+350h+pColor], eax; format
0x180044df3  call    cs:__imp_DrawTextExW
0x180044df9  mov     esi, [rsp+350h+var_300]
0x180044dfd  xor     r11d, r11d
0x180044e00  jmp     loc_180044C1C
0x180044e05  mov     rcx, r12; hdc
0x180044e08  call    cs:__imp_GetTextAlign
0x180044e0e  mov     edx, eax
0x180044e10  mov     [rsp+350h+align], eax
0x180044e14  bts     edx, 8; align
0x180044e18  mov     rcx, r12; hdc
0x180044e1b  call    cs:__imp_SetTextAlign
0x180044e21  jmp     loc_180044A5D
0x180044e26  lea     rax, [rbp+250h+String]
0x180044e2a  mov     [rbp+250h+var_2C0.mask], 1Fh
0x180044e31  mov     [rbp+250h+var_2C0.pszText], rax
0x180044e35  lea     rdx, [rbp+250h+var_2C0]; struct tagCOMBOBOXEXITEMW *
0x180044e39  movsxd  rax, dword ptr [r13+8]
0x180044e3d  mov     rcx, r15; struct COMBOEX *
0x180044e40  mov     [rbp+250h+var_2C0.iItem], rax
0x180044e44  mov     [rbp+250h+var_2C0.cchTextMax], edi
0x180044e47  call    ?ComboEx_OnGetItem@@YAHPEAUCOMBOEX@@PEAUtagCOMBOBOXEXITEMW@@@Z; ComboEx_OnGetItem(COMBOEX *,tagCOMBOBOXEXITEMW *)
0x180044e4c  mov     eax, [r15+6Ch]
0x180044e50  cmp     eax, [r13+8]
0x180044e54  jz      short loc_180044E80
0x180044e56  cmp     eax, 0FFFFFFFFh
0x180044e59  jnz     loc_180044AB9
0x180044e5f  mov     rcx, [r15+40h]; hWnd
0x180044e63  xor     r9d, r9d; lParam
0x180044e66  mov     ebx, [r13+8]
0x180044e6a  xor     r8d, r8d; wParam
0x180044e6d  mov     edx, 147h; Msg
0x180044e72  call    cs:__imp_SendMessageW
0x180044e78  cmp     ebx, eax
0x180044e7a  jnz     loc_180044AB9
0x180044e80  mov     [rsp+350h+var_2EC], esi
0x180044e84  jmp     loc_180044AB9
0x180044e89  mov     r8, [rbx+0E0h]; unsigned __int16 *
0x180044e90  test    r8, r8
0x180044e93  jz      loc_180044ABC
0x180044e99  mov     rdx, rdi; unsigned __int64
0x180044e9c  lea     rcx, [rbp+250h+String]; unsigned __int16 *
0x180044ea0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044ea5  mov     r14d, esi
  ... truncated ...
```
