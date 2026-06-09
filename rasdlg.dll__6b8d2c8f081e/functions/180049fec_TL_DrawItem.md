# TL_DrawItem

- ea: `0x180049fec`
- end: `0x18004a69f`
- name: `TL_DrawItem`
- size: `1715`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004ad00`

## callees

- `0x180039650`
- `0x180039718`
- `0x18003bea0`
- `0x18004815c`
- `0x180049fec`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004a3b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004a4fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004a3b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004a4fa`
- `GDI32!DeleteDC` at `0x18004a66d`
- `GDI32!DeleteDC` at `0x18004a66d`
- `GDI32!ExtTextOutW` at `0x18004a401`
- `GDI32!ExtTextOutW` at `0x18004a488`
- `GDI32!ExtTextOutW` at `0x18004a52e`
- `GDI32!ExtTextOutW` at `0x18004a5da`
- `GDI32!ExtTextOutW` at `0x18004a401`
- `GDI32!ExtTextOutW` at `0x18004a488`
- `GDI32!ExtTextOutW` at `0x18004a52e`
- `GDI32!ExtTextOutW` at `0x18004a5da`
- `GDI32!CreateCompatibleDC` at `0x18004a057`
- `GDI32!CreateCompatibleDC` at `0x18004a057`
- `GDI32!CreateCompatibleBitmap` at `0x18004a0aa`
- `GDI32!CreateCompatibleBitmap` at `0x18004a0aa`
- `GDI32!DeleteObject` at `0x18004a092`
- `GDI32!DeleteObject` at `0x18004a092`
- `GDI32!SelectObject` at `0x18004a0cc`
- `GDI32!SelectObject` at `0x18004a0f0`
- `GDI32!SelectObject` at `0x18004a657`
- `GDI32!SelectObject` at `0x18004a664`
- `GDI32!SelectObject` at `0x18004a0cc`
- `GDI32!SelectObject` at `0x18004a0f0`
- `GDI32!SelectObject` at `0x18004a657`
- `GDI32!SelectObject` at `0x18004a664`
- `GDI32!SetBkColor` at `0x18004a158`
- `GDI32!SetBkColor` at `0x18004a158`
- `GDI32!SetTextColor` at `0x18004a125`
- `GDI32!SetTextColor` at `0x18004a142`
- `GDI32!SetTextColor` at `0x18004a125`
- `GDI32!SetTextColor` at `0x18004a142`
- `GDI32!BitBlt` at `0x18004a1e7`
- `GDI32!BitBlt` at `0x18004a263`
- `GDI32!BitBlt` at `0x18004a64a`
- `GDI32!BitBlt` at `0x18004a1e7`
- `GDI32!BitBlt` at `0x18004a263`
- `GDI32!BitBlt` at `0x18004a64a`
- `USER32!SendMessageW` at `0x18004a0e4`
- `USER32!SendMessageW` at `0x18004a17d`
- `USER32!SendMessageW` at `0x18004a297`
- `USER32!SendMessageW` at `0x18004a30e`
- `USER32!SendMessageW` at `0x18004a43a`
- `USER32!SendMessageW` at `0x18004a4ad`
- `USER32!SendMessageW` at `0x18004a58c`
- `USER32!SendMessageW` at `0x18004a0e4`
- `USER32!SendMessageW` at `0x18004a17d`
- `USER32!SendMessageW` at `0x18004a297`
- `USER32!SendMessageW` at `0x18004a30e`
- `USER32!SendMessageW` at `0x18004a43a`
- `USER32!SendMessageW` at `0x18004a4ad`
- `USER32!SendMessageW` at `0x18004a58c`
- `USER32!GetSysColor` at `0x18004a11a`
- `USER32!GetSysColor` at `0x18004a137`
- `USER32!GetSysColor` at `0x18004a14d`
- `USER32!GetSysColor` at `0x18004a11a`
- `USER32!GetSysColor` at `0x18004a137`
- `USER32!GetSysColor` at `0x18004a14d`
- `USER32!DrawFocusRect` at `0x18004a612`
- `USER32!DrawFocusRect` at `0x18004a612`
- `USER32!FillRect` at `0x18004a108`
- `USER32!FillRect` at `0x18004a108`

## pseudocode

```c
HDC __fastcall TL_DrawItem(__int64 a1, __int64 a2)
{
  int v3; // r13d
  HDC v4; // rcx
  void *v5; // r14
  __int64 v6; // rbx
  HDC result; // rax
  HDC hdcSrc; // rsi
  HBITMAP CompatibleBitmap; // rdx
  _DWORD *v10; // rdi
  HGDIOBJ v11; // rax
  HWND v12; // rcx
  void *v13; // rax
  HGDIOBJ v14; // rax
  HBRUSH v15; // r8
  DWORD SysColor; // eax
  int v17; // ecx
  DWORD v18; // eax
  DWORD v19; // eax
  int v20; // edi
  int v21; // eax
  __int64 v22; // r12
  int v23; // r9d
  int v24; // edi
  LPCWSTR v25; // rdx
  int v26; // ecx
  int v27; // r9d
  struct _IMAGELIST *v28; // rax
  struct _IMAGELIST *v29; // r13
  int v30; // edi
  struct _IMAGELIST *v31; // rax
  struct _IMAGELIST *v32; // r13
  const WCHAR *v33; // rax
  WCHAR *v34; // r13
  UINT v35; // eax
  int v36; // eax
  __int64 *v37; // r13
  int v38; // r12d
  int v39; // eax
  int v40; // r8d
  bool v41; // cc
  HWND v42; // rcx
  int v43; // eax
  void *v44; // rax
  LONG left; // ebx
  int v46; // edi
  UINT v47; // eax
  int v48; // r12d
  HWND v49; // rcx
  int v50; // eax
  int v51; // r8d
  int y; // [rsp+50h] [rbp-49h]
  int ya; // [rsp+50h] [rbp-49h]
  int x; // [rsp+54h] [rbp-45h]
  int v55; // [rsp+58h] [rbp-41h] BYREF
  int v56; // [rsp+5Ch] [rbp-3Dh] BYREF
  LPCWSTR lpString; // [rsp+60h] [rbp-39h]
  __int64 *v58; // [rsp+68h] [rbp-31h]
  void *v59; // [rsp+70h] [rbp-29h]
  __int64 v60; // [rsp+78h] [rbp-21h]
  HGDIOBJ h; // [rsp+80h] [rbp-19h]
  HGDIOBJ v62; // [rsp+88h] [rbp-11h]
  RECT rect; // [rsp+90h] [rbp-9h] BYREF
  int cy[4]; // [rsp+A0h] [rbp+7h] BYREF

  v3 = *(_DWORD *)(a1 + 228);
  v4 = *(HDC *)(a2 + 32);
  v5 = (void *)a2;
  v6 = *(_QWORD *)(a2 + 56);
  cy[2] = *(_DWORD *)(a2 + 48) - *(_DWORD *)(a2 + 40);
  cy[3] = *(_DWORD *)(a2 + 52) - *(_DWORD *)(a2 + 44);
  v59 = (void *)a2;
  rect = 0;
  v56 = 0;
  v55 = 0;
  *(_QWORD *)cy = 0;
  result = CreateCompatibleDC(v4);
  hdcSrc = result;
  if ( !result )
    return result;
  CompatibleBitmap = *(HBITMAP *)(a1 + 248);
  v10 = (_DWORD *)(a1 + 256);
  if ( !CompatibleBitmap )
    goto LABEL_6;
  if ( cy[2] > *v10 || cy[3] > *(_DWORD *)(a1 + 260) )
  {
    DeleteObject(*(HGDIOBJ *)(a1 + 248));
    *(_QWORD *)(a1 + 248) = 0;
LABEL_6:
    CompatibleBitmap = CreateCompatibleBitmap(*((HDC *)v5 + 4), cy[2], cy[3]);
    *(_QWORD *)(a1 + 248) = CompatibleBitmap;
    *v10 = cy[2];
    *(_DWORD *)(a1 + 260) = cy[3];
  }
  v11 = SelectObject(hdcSrc, CompatibleBitmap);
  v12 = (HWND)*((_QWORD *)v5 + 3);
  h = v11;
  v13 = (void *)SendMessageW(v12, 0x31u, 0, 0);
  v14 = SelectObject(hdcSrc, v13);
  v15 = *(HBRUSH *)(a1 + 272);
  v62 = v14;
  FillRect(hdcSrc, (const RECT *)cy, v15);
  if ( (*((_BYTE *)v5 + 16) & 1) != 0 )
  {
    SysColor = GetSysColor(14);
    SetTextColor(hdcSrc, SysColor);
    v17 = 13;
  }
  else
  {
    v18 = GetSysColor(8);
    SetTextColor(hdcSrc, v18);
    v17 = 5;
  }
  v19 = GetSysColor(v17);
  SetBkColor(hdcSrc, v19);
  y = cy[1];
  v20 = cy[0] + *(_DWORD *)(v6 + 56) * v3;
  v21 = SendMessageW(*((HWND *)v5 + 3), 0x101Du, 0, 0);
  v22 = (unsigned int)(cy[0] + v21);
  v60 = v22;
  x = v20 + v3;
  if ( v20 < (int)v22 )
  {
    v23 = v3;
    if ( v3 >= (int)v22 - v20 )
      v23 = v22 - v20;
    BitBlt(hdcSrc, v20, y, v23, *(_DWORD *)(a1 + 220), *(HDC *)(a1 + 232), *(_DWORD *)(v6 + 176) * v3, 0, 0xCC0020u);
  }
  v24 = v20 - v3;
  v25 = *(LPCWSTR *)v6;
  v26 = *(_DWORD *)(v6 + 56) - 1;
  lpString = *(LPCWSTR *)v6;
  LODWORD(v58) = v26;
  if ( v26 > 0 )
  {
    do
    {
      if ( v24 < (int)v22 && *((_QWORD *)v25 + 1) != *(_QWORD *)v25 + 24LL )
      {
        v27 = v3;
        if ( v3 >= (int)v22 - v24 )
          v27 = v22 - v24;
        BitBlt(hdcSrc, v24, y, v27, *(_DWORD *)(a1 + 220), *(HDC *)(a1 + 232), 0, 0, 0xCC0020u);
        v26 = (int)v58;
        v25 = lpString;
      }
      v25 = *(LPCWSTR *)v25;
      --v26;
      v24 -= v3;
      lpString = v25;
      LODWORD(v58) = v26;
    }
    while ( v26 > 0 );
    v5 = v59;
  }
  v28 = (struct _IMAGELIST *)SendMessageW(*((HWND *)v5 + 3), 0x1002u, 2u, 0);
  v29 = v28;
  if ( v28 && (*(_DWORD *)(v6 + 84) & 0xF000) != 0 )
  {
    ImageList_GetIconSize(v28, &v56, &v55);
    ImageList_Draw(
      v29,
      ((unsigned __int8)HIBYTE(*(_WORD *)(v6 + 84)) >> 4) - 1,
      hdcSrc,
      x,
      y + *(_DWORD *)(a1 + 220) - v55,
      0);
    v30 = v56 + x;
    x += v56;
  }
  else
  {
    v30 = x;
  }
  v31 = (struct _IMAGELIST *)SendMessageW(*((HWND *)v5 + 3), 0x1002u, 1u, 0);
  v32 = v31;
  if ( v31 && (*(_BYTE *)(v6 + 72) & 2) != 0 )
  {
    ImageList_GetIconSize(v31, &v56, &v55);
    ImageList_Draw(v32, *(_DWORD *)(v6 + 108), hdcSrc, v30, y + ((unsigned int)(*(_DWORD *)(a1 + 220) - v55) >> 1), 0);
    v30 += v56;
    x = v30;
  }
  rect.top = cy[1];
  rect.bottom = cy[3];
  rect.left = v30;
  rect.right = v22;
  if ( (*(_BYTE *)(v6 + 72) & 1) != 0 )
  {
    v33 = (const WCHAR *)Ellipsisize(hdcSrc, *(STRSAFE_LPCWSTR *)(v6 + 160));
    v34 = (WCHAR *)v33;
    if ( !v33 )
      v33 = *(const WCHAR **)(v6 + 160);
    lpString = v33;
    v35 = lstrlenW(v33);
    ExtTextOutW(
      hdcSrc,
      rect.left + 2,
      rect.top + ((unsigned int)(*(_DWORD *)(a1 + 220) - *(_DWORD *)(a1 + 224)) >> 1),
      6u,
      &rect,
      lpString,
      v35,
      0);
    Free0(v34);
  }
  v36 = 1;
  v37 = *(__int64 **)(v6 + 40);
  ya = 1;
  v58 = (__int64 *)(v6 + 40);
  if ( v37 != (__int64 *)(v6 + 40) )
  {
    v38 = 1;
    do
    {
      while ( 1 )
      {
        v41 = v38 < *((_DWORD *)v37 + 5);
        v42 = (HWND)*((_QWORD *)v5 + 3);
        rect.left = rect.right;
        if ( !v41 )
          break;
        v39 = SendMessageW(v42, 0x101Du, v38, 0);
        v40 = rect.top + ((unsigned int)(*(_DWORD *)(a1 + 220) - *(_DWORD *)(a1 + 224)) >> 1);
        rect.right = rect.left + v39;
        ExtTextOutW(hdcSrc, rect.left + 2, v40, 6u, &rect, &WideCharStr, 0, 0);
        ++v38;
      }
      v43 = SendMessageW(v42, 0x101Du, *((int *)v37 + 5), 0);
      rect.right = v43 + rect.left;
      v44 = (void *)Ellipsisize(hdcSrc, (STRSAFE_LPCWSTR)v37[3]);
      v59 = v44;
      if ( !v44 )
        v44 = (void *)v37[3];
      left = rect.left;
      v46 = rect.top + ((unsigned int)(*(_DWORD *)(a1 + 220) - *(_DWORD *)(a1 + 224)) >> 1);
      lpString = (LPCWSTR)v44;
      v47 = lstrlenW((LPCWSTR)v44);
      ExtTextOutW(hdcSrc, left + 2, v46, 6u, &rect, lpString, v47, 0);
      Free0(v59);
      v37 = (__int64 *)*v37;
      ++v38;
    }
    while ( v37 != v58 );
    v30 = x;
    ya = v38;
    v36 = v38;
    LODWORD(v22) = v60;
  }
  if ( v36 < *(_DWORD *)(a1 + 216) )
  {
    v48 = ya;
    do
    {
      v49 = (HWND)*((_QWORD *)v5 + 3);
      rect.left = rect.right;
      v50 = SendMessageW(v49, 0x101Du, v48, 0);
      v51 = rect.top + ((unsigned int)(*(_DWORD *)(a1 + 220) - *(_DWORD *)(a1 + 224)) >> 1);
      rect.right = rect.left + v50;
      ExtTextOutW(hdcSrc, rect.left + 2, v51, 6u, &rect, &WideCharStr, 0, 0);
      ++v48;
    }
    while ( v48 < *(_DWORD *)(a1 + 216) );
    LODWORD(v22) = v60;
  }
  if ( (*((_BYTE *)v5 + 16) & 0x10) != 0 )
  {
    rect = *(RECT *)cy;
    if ( v30 < (int)v22 )
      LODWORD(v22) = v30;
    rect.left = v22;
    DrawFocusRect(hdcSrc, &rect);
  }
  BitBlt(*((HDC *)v5 + 4), *((_DWORD *)v5 + 10), *((_DWORD *)v5 + 11), cy[2], cy[3], hdcSrc, cy[0], cy[1], 0xCC0020u);
  SelectObject(hdcSrc, h);
  SelectObject(hdcSrc, v62);
  DeleteDC(hdcSrc);
  return (HDC)1;
}

```

## disassembly

```asm
0x180049fec  mov     [rsp-8+arg_10], rbx
0x180049ff1  push    rbp
0x180049ff2  push    rsi
0x180049ff3  push    rdi
0x180049ff4  push    r12
0x180049ff6  push    r13
0x180049ff8  push    r14
0x180049ffa  push    r15
0x180049ffc  lea     rbp, [rsp-27h]
0x18004a001  sub     rsp, 0C0h
0x18004a008  mov     rax, cs:__security_cookie
0x18004a00f  xor     rax, rsp
0x18004a012  mov     [rbp+57h+var_40], rax
0x18004a016  mov     eax, [rdx+30h]
0x18004a019  xor     r12d, r12d
0x18004a01c  sub     eax, [rdx+28h]
0x18004a01f  mov     r15, rcx
0x18004a022  mov     r13d, [rcx+0E4h]
0x18004a029  xorps   xmm0, xmm0
0x18004a02c  mov     rcx, [rdx+20h]; hdc
0x18004a030  mov     r14, rdx
0x18004a033  mov     rbx, [rdx+38h]
0x18004a037  mov     [rbp+57h+cy+8], eax
0x18004a03a  mov     eax, [rdx+34h]
0x18004a03d  sub     eax, [rdx+2Ch]
0x18004a040  mov     [rbp+57h+cy+0Ch], eax
0x18004a043  mov     [rbp+57h+var_80], rdx
0x18004a047  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x18004a04b  mov     [rbp+57h+var_94], r12d
0x18004a04f  mov     [rbp+57h+var_98], r12d
0x18004a053  mov     qword ptr [rbp+57h+cy], r12
0x18004a057  call    cs:__imp_CreateCompatibleDC
0x18004a05d  mov     rsi, rax
0x18004a060  test    rax, rax
0x18004a063  jz      loc_18004A678
0x18004a069  mov     rdx, [r15+0F8h]
0x18004a070  lea     rdi, [r15+100h]
0x18004a077  test    rdx, rdx
0x18004a07a  jz      short loc_18004A09F
0x18004a07c  mov     eax, [rdi]
0x18004a07e  cmp     [rbp+57h+cy+8], eax
0x18004a081  jg      short loc_18004A08F
0x18004a083  mov     eax, [r15+104h]
0x18004a08a  cmp     [rbp+57h+cy+0Ch], eax
0x18004a08d  jle     short loc_18004A0C9
0x18004a08f  mov     rcx, rdx; ho
0x18004a092  call    cs:__imp_DeleteObject
0x18004a098  mov     [r15+0F8h], r12
0x18004a09f  mov     r8d, [rbp+57h+cy+0Ch]; cy
0x18004a0a3  mov     edx, [rbp+57h+cy+8]; cx
0x18004a0a6  mov     rcx, [r14+20h]; hdc
0x18004a0aa  call    cs:__imp_CreateCompatibleBitmap
0x18004a0b0  mov     rdx, rax; h
0x18004a0b3  mov     [r15+0F8h], rax
0x18004a0ba  mov     eax, [rbp+57h+cy+8]
0x18004a0bd  mov     [rdi], eax
0x18004a0bf  mov     eax, [rbp+57h+cy+0Ch]
0x18004a0c2  mov     [r15+104h], eax
0x18004a0c9  mov     rcx, rsi; hdc
0x18004a0cc  call    cs:__imp_SelectObject
0x18004a0d2  mov     rcx, [r14+18h]; hWnd
0x18004a0d6  xor     r9d, r9d; lParam
0x18004a0d9  xor     r8d, r8d; wParam
0x18004a0dc  mov     [rbp+57h+h], rax
0x18004a0e0  lea     edx, [r9+31h]; Msg
0x18004a0e4  call    cs:__imp_SendMessageW
0x18004a0ea  mov     rdx, rax; h
0x18004a0ed  mov     rcx, rsi; hdc
0x18004a0f0  call    cs:__imp_SelectObject
0x18004a0f6  mov     r8, [r15+110h]; hbr
0x18004a0fd  lea     rdx, [rbp+57h+cy]; lprc
0x18004a101  mov     rcx, rsi; hDC
0x18004a104  mov     [rbp+57h+var_68], rax
0x18004a108  call    cs:__imp_FillRect
0x18004a10e  test    byte ptr [r14+10h], 1
0x18004a113  jz      short loc_18004A132
0x18004a115  mov     ecx, 0Eh; nIndex
0x18004a11a  call    cs:__imp_GetSysColor
0x18004a120  mov     edx, eax; color
0x18004a122  mov     rcx, rsi; hdc
0x18004a125  call    cs:__imp_SetTextColor
0x18004a12b  mov     ecx, 0Dh
0x18004a130  jmp     short loc_18004A14D
0x18004a132  mov     ecx, 8; nIndex
0x18004a137  call    cs:__imp_GetSysColor
0x18004a13d  mov     edx, eax; color
0x18004a13f  mov     rcx, rsi; hdc
0x18004a142  call    cs:__imp_SetTextColor
0x18004a148  mov     ecx, 5; nIndex
0x18004a14d  call    cs:__imp_GetSysColor
0x18004a153  mov     edx, eax; color
0x18004a155  mov     rcx, rsi; hdc
0x18004a158  call    cs:__imp_SetBkColor
0x18004a15e  mov     eax, [rbp+57h+cy+4]
0x18004a161  mov     edi, r13d
0x18004a164  imul    edi, [rbx+38h]
0x18004a168  xor     r9d, r9d; lParam
0x18004a16b  mov     rcx, [r14+18h]; hWnd
0x18004a16f  xor     r8d, r8d; wParam
0x18004a172  mov     edx, 101Dh; Msg
0x18004a177  mov     [rbp+57h+y], eax
0x18004a17a  add     edi, [rbp+57h+cy]
0x18004a17d  call    cs:__imp_SendMessageW
0x18004a183  mov     r12, rax
0x18004a186  lea     eax, [rdi+r13]
0x18004a18a  add     r12d, [rbp+57h+cy]
0x18004a18e  mov     [rbp+57h+var_78], r12
0x18004a192  mov     [rbp+57h+x], eax
0x18004a195  cmp     edi, r12d
0x18004a198  jge     short loc_18004A1ED
0x18004a19a  mov     rax, [r15+0E8h]
0x18004a1a1  mov     ecx, r13d
0x18004a1a4  imul    ecx, [rbx+0B0h]
0x18004a1ab  mov     edx, r12d
0x18004a1ae  mov     r8d, [rbp+57h+y]; y
0x18004a1b2  sub     edx, edi
0x18004a1b4  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18004a1bc  cmp     r13d, edx
0x18004a1bf  mov     [rsp+0F0h+y1], 0; y1
0x18004a1c7  mov     r9d, r13d
0x18004a1ca  cmovge  r9d, edx; cx
0x18004a1ce  mov     edx, edi; x
0x18004a1d0  mov     [rsp+0F0h+x1], ecx; x1
0x18004a1d4  mov     rcx, rsi; hdc
0x18004a1d7  mov     [rsp+0F0h+hdcSrc], rax; hdcSrc
0x18004a1dc  mov     eax, [r15+0DCh]
0x18004a1e3  mov     dword ptr [rsp+0F0h+lprect], eax; cy
0x18004a1e7  call    cs:__imp_BitBlt
0x18004a1ed  mov     ecx, [rbx+38h]
0x18004a1f0  sub     edi, r13d
0x18004a1f3  mov     rdx, [rbx]
0x18004a1f6  dec     ecx
0x18004a1f8  mov     [rbp+57h+lpString], rdx
0x18004a1fc  mov     dword ptr [rbp+57h+var_88], ecx
0x18004a1ff  test    ecx, ecx
0x18004a201  jle     loc_18004A287
0x18004a207  mov     r14d, [rbp+57h+y]
0x18004a20b  cmp     edi, r12d
0x18004a20e  jge     short loc_18004A270
0x18004a210  mov     rax, [rdx]
0x18004a213  add     rax, 18h
0x18004a217  cmp     [rdx+8], rax
0x18004a21b  jz      short loc_18004A270
0x18004a21d  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18004a225  mov     eax, r12d
0x18004a228  sub     eax, edi
0x18004a22a  mov     [rsp+0F0h+y1], 0; y1
0x18004a232  cmp     r13d, eax
0x18004a235  mov     [rsp+0F0h+x1], 0; x1
0x18004a23d  mov     r9d, r13d
0x18004a240  mov     r8d, r14d; y
0x18004a243  cmovge  r9d, eax; cx
0x18004a247  mov     edx, edi; x
0x18004a249  mov     rax, [r15+0E8h]
0x18004a250  mov     rcx, rsi; hdc
0x18004a253  mov     [rsp+0F0h+hdcSrc], rax; hdcSrc
0x18004a258  mov     eax, [r15+0DCh]
0x18004a25f  mov     dword ptr [rsp+0F0h+lprect], eax; cy
0x18004a263  call    cs:__imp_BitBlt
0x18004a269  mov     ecx, dword ptr [rbp+57h+var_88]
0x18004a26c  mov     rdx, [rbp+57h+lpString]
0x18004a270  mov     rdx, [rdx]
0x18004a273  dec     ecx
0x18004a275  sub     edi, r13d
0x18004a278  mov     [rbp+57h+lpString], rdx
0x18004a27c  mov     dword ptr [rbp+57h+var_88], ecx
0x18004a27f  test    ecx, ecx
0x18004a281  jg      short loc_18004A20B
0x18004a283  mov     r14, [rbp+57h+var_80]
0x18004a287  mov     rcx, [r14+18h]; hWnd
0x18004a28b  xor     r9d, r9d; lParam
0x18004a28e  mov     edx, 1002h; Msg
0x18004a293  lea     r8d, [r9+2]; wParam
0x18004a297  call    cs:__imp_SendMessageW
0x18004a29d  mov     r13, rax
0x18004a2a0  test    rax, rax
0x18004a2a3  jz      short loc_18004A2FB
0x18004a2a5  test    dword ptr [rbx+54h], 0F000h
0x18004a2ac  jz      short loc_18004A2FB
0x18004a2ae  lea     r8, [rbp+57h+var_98]; cy
0x18004a2b2  mov     rcx, rax; himl
0x18004a2b5  lea     rdx, [rbp+57h+var_94]; cx
0x18004a2b9  call    ImageList_GetIconSize
0x18004a2be  mov     ecx, [r15+0DCh]
0x18004a2c5  mov     r8, rsi; hdcDst
0x18004a2c8  sub     ecx, [rbp+57h+var_98]
0x18004a2cb  add     ecx, [rbp+57h+y]
0x18004a2ce  mov     edx, [rbx+54h]
0x18004a2d1  mov     edi, [rbp+57h+x]
0x18004a2d4  mov     r9d, edi; x
0x18004a2d7  shr     edx, 0Ch
0x18004a2da  and     edx, 0Fh
0x18004a2dd  mov     dword ptr [rsp+0F0h+hdcSrc], 0; fStyle
0x18004a2e5  mov     dword ptr [rsp+0F0h+lprect], ecx; y
0x18004a2e9  dec     edx; i
0x18004a2eb  mov     rcx, r13; himl
0x18004a2ee  call    ImageList_Draw
0x18004a2f3  add     edi, [rbp+57h+var_94]
0x18004a2f6  mov     [rbp+57h+x], edi
0x18004a2f9  jmp     short loc_18004A2FE
0x18004a2fb  mov     edi, [rbp+57h+x]
0x18004a2fe  mov     rcx, [r14+18h]; hWnd
0x18004a302  xor     r9d, r9d; lParam
0x18004a305  mov     edx, 1002h; Msg
0x18004a30a  lea     r8d, [r9+1]; wParam
0x18004a30e  call    cs:__imp_SendMessageW
0x18004a314  mov     r13, rax
0x18004a317  test    rax, rax
0x18004a31a  jz      short loc_18004A364
0x18004a31c  test    byte ptr [rbx+48h], 2
0x18004a320  jz      short loc_18004A364
0x18004a322  lea     r8, [rbp+57h+var_98]; cy
0x18004a326  mov     rcx, rax; himl
0x18004a329  lea     rdx, [rbp+57h+var_94]; cx
0x18004a32d  call    ImageList_GetIconSize
0x18004a332  mov     ecx, [r15+0DCh]
0x18004a339  mov     r9d, edi; x
0x18004a33c  sub     ecx, [rbp+57h+var_98]
0x18004a33f  mov     r8, rsi; hdcDst
0x18004a342  mov     edx, [rbx+6Ch]; i
0x18004a345  shr     ecx, 1
0x18004a347  add     ecx, [rbp+57h+y]
0x18004a34a  mov     dword ptr [rsp+0F0h+hdcSrc], 0; fStyle
0x18004a352  mov     dword ptr [rsp+0F0h+lprect], ecx; y
0x18004a356  mov     rcx, r13; himl
0x18004a359  call    ImageList_Draw
0x18004a35e  add     edi, [rbp+57h+var_94]
0x18004a361  mov     [rbp+57h+x], edi
0x18004a364  mov     eax, [rbp+57h+cy+4]
0x18004a367  mov     [rbp+57h+rect.top], eax
0x18004a36a  mov     eax, [rbp+57h+cy+0Ch]
0x18004a36d  mov     [rbp+57h+rect.bottom], eax
0x18004a370  mov     [rbp+57h+rect.left], edi
0x18004a373  mov     [rbp+57h+rect.right], r12d
0x18004a377  test    byte ptr [rbx+48h], 1
0x18004a37b  jz      loc_18004A40F
0x18004a381  mov     rdx, [rbx+0A0h]; pszSrc
0x18004a388  mov     r8d, r12d
0x18004a38b  sub     r8d, edi
0x18004a38e  xor     r9d, r9d
0x18004a391  mov     rcx, rsi; hdc
0x18004a394  call    Ellipsisize
0x18004a399  mov     r13, rax
0x18004a39c  test    rax, rax
0x18004a39f  jz      short loc_18004A3AA
0x18004a3a1  mov     [rbp+57h+lpString], rax
0x18004a3a5  mov     rcx, rax
0x18004a3a8  jmp     short loc_18004A3B8
0x18004a3aa  mov     rax, [rbx+0A0h]
0x18004a3b1  mov     [rbp+57h+lpString], rax
0x18004a3b5  mov     rcx, rax; lpString
0x18004a3b8  call    cs:__imp_lstrlenW
0x18004a3be  mov     r8d, [r15+0DCh]
0x18004a3c5  mov     r9d, 6; options
0x18004a3cb  sub     r8d, [r15+0E0h]
0x18004a3d2  mov     rcx, rsi; hdc
0x18004a3d5  mov     edx, [rbp+57h+rect.left]
0x18004a3d8  mov     qword ptr [rsp+0F0h+y1], 0; lpDx
0x18004a3e1  add     edx, 2; x
0x18004a3e4  mov     [rsp+0F0h+x1], eax; c
0x18004a3e8  mov     rax, [rbp+57h+lpString]
0x18004a3ec  mov     [rsp+0F0h+hdcSrc], rax; lpString
0x18004a3f1  lea     rax, [rbp+57h+rect]
0x18004a3f5  shr     r8d, 1
0x18004a3f8  add     r8d, [rbp+57h+rect.top]; y
0x18004a3fc  mov     [rsp+0F0h+lprect], rax; lprect
0x18004a401  call    cs:__imp_ExtTextOutW
0x18004a407  mov     rcx, r13
0x18004a40a  call    Free0
0x18004a40f  lea     rcx, [rbx+28h]
0x18004a413  mov     eax, 1
0x18004a418  mov     r13, [rcx]
0x18004a41b  lea     rbx, WideCharStr
0x18004a422  mov     [rbp+57h+y], eax
0x18004a425  mov     [rbp+57h+var_88], rcx
0x18004a429  cmp     r13, rcx
0x18004a42c  jz      loc_18004A56A
0x18004a432  mov     r12d, eax
0x18004a435  jmp     short loc_18004A491
0x18004a437  movsxd  r8, r12d; wParam
0x18004a43a  call    cs:__imp_SendMessageW
0x18004a440  mov     edx, [rbp+57h+rect.left]
0x18004a443  mov     r9d, 6; options
0x18004a449  mov     r8d, [r15+0DCh]
0x18004a450  add     eax, edx
0x18004a452  sub     r8d, [r15+0E0h]
0x18004a459  add     edx, 2; x
0x18004a45c  mov     qword ptr [rsp+0F0h+y1], 0; lpDx
0x18004a465  mov     rcx, rsi; hdc
0x18004a468  shr     r8d, 1
0x18004a46b  add     r8d, [rbp+57h+rect.top]; y
0x18004a46f  mov     [rbp+57h+rect.right], eax
0x18004a472  lea     rax, [rbp+57h+rect]
0x18004a476  mov     [rsp+0F0h+x1], 0; c
0x18004a47e  mov     [rsp+0F0h+hdcSrc], rbx; lpString
0x18004a483  mov     [rsp+0F0h+lprect], rax; lprect
0x18004a488  call    cs:__imp_ExtTextOutW
0x18004a48e  inc     r12d
0x18004a491  mov     eax, [rbp+57h+rect.right]
0x18004a494  xor     r9d, r9d; lParam
  ... truncated ...
```
