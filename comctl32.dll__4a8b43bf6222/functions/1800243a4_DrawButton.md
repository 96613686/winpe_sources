# DrawButton

- ea: `0x1800243a4`
- end: `0x180024def`
- name: `DrawButton`
- size: `2635`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int, int)`
- caller_count: `4`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180025584`
- `0x1800258a4`
- `0x180026cc4`
- `0x18004b9a8`

## callees

- `0x1800115f0`
- `0x180023cdc`
- `0x1800242dc`
- `0x1800243a4`
- `0x180024df8`
- `0x180025f7c`
- `0x1800262c4`
- `0x180026bf4`
- `0x180026f00`
- `0x1800293b4`
- `0x180029ac4`
- `0x18002a94c`
- `0x180035fe0`
- `0x180036e24`
- `0x180089960`
- `0x18008ea60`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180024a2a`
- `GDI32!CreateCompatibleDC` at `0x180024a2a`
- `GDI32!SelectObject` at `0x1800246c8`
- `GDI32!SelectObject` at `0x180024850`
- `GDI32!SelectObject` at `0x1800248b0`
- `GDI32!SelectObject` at `0x180024a53`
- `GDI32!SelectObject` at `0x180024a61`
- `GDI32!SelectObject` at `0x180024b03`
- `GDI32!SelectObject` at `0x180024b5c`
- `GDI32!SelectObject` at `0x180024b6c`
- `GDI32!SelectObject` at `0x180024bc0`
- `GDI32!SelectObject` at `0x180024c14`
- `GDI32!SelectObject` at `0x180024d90`
- `GDI32!SelectObject` at `0x1800246c8`
- `GDI32!SelectObject` at `0x180024850`
- `GDI32!SelectObject` at `0x1800248b0`
- `GDI32!SelectObject` at `0x180024a53`
- `GDI32!SelectObject` at `0x180024a61`
- `GDI32!SelectObject` at `0x180024b03`
- `GDI32!SelectObject` at `0x180024b5c`
- `GDI32!SelectObject` at `0x180024b6c`
- `GDI32!SelectObject` at `0x180024bc0`
- `GDI32!SelectObject` at `0x180024c14`
- `GDI32!SelectObject` at `0x180024d90`
- `GDI32!BitBlt` at `0x180024b50`
- `GDI32!BitBlt` at `0x180024bb4`
- `GDI32!BitBlt` at `0x180024c07`
- `GDI32!BitBlt` at `0x180024b50`
- `GDI32!BitBlt` at `0x180024bb4`
- `GDI32!BitBlt` at `0x180024c07`
- `GDI32!DeleteObject` at `0x180024daf`
- `GDI32!DeleteObject` at `0x180024daf`
- `GDI32!GetObjectW` at `0x180024694`
- `GDI32!GetObjectW` at `0x180024694`
- `GDI32!CreateFontIndirectW` at `0x1800246ac`
- `GDI32!CreateFontIndirectW` at `0x1800246ac`
- `GDI32!SetLayout` at `0x180024a90`
- `GDI32!SetLayout` at `0x180024a90`
- `GDI32!SetBkColor` at `0x18002487b`
- `GDI32!SetBkColor` at `0x1800248c7`
- `GDI32!SetBkColor` at `0x180024ae3`
- `GDI32!SetBkColor` at `0x18002487b`
- `GDI32!SetBkColor` at `0x1800248c7`
- `GDI32!SetBkColor` at `0x180024ae3`
- `GDI32!SetTextColor` at `0x1800246d8`
- `GDI32!SetTextColor` at `0x18002486c`
- `GDI32!SetTextColor` at `0x1800248bc`
- `GDI32!SetTextColor` at `0x180024a42`
- `GDI32!SetTextColor` at `0x180024ad5`
- `GDI32!SetTextColor` at `0x180024d9d`
- `GDI32!SetTextColor` at `0x1800246d8`
- `GDI32!SetTextColor` at `0x18002486c`
- `GDI32!SetTextColor` at `0x1800248bc`
- `GDI32!SetTextColor` at `0x180024a42`
- `GDI32!SetTextColor` at `0x180024ad5`
- `GDI32!SetTextColor` at `0x180024d9d`
- `GDI32!PatBlt` at `0x1800248a4`
- `GDI32!PatBlt` at `0x1800248a4`
- `GDI32!GetLayout` at `0x180024a6d`
- `GDI32!GetLayout` at `0x180024a7b`
- `GDI32!GetLayout` at `0x180024a6d`
- `GDI32!GetLayout` at `0x180024a7b`
- `USER32!SetRect` at `0x180024509`
- `USER32!SetRect` at `0x180024509`
- `USER32!GetCapture` at `0x180024483`
- `USER32!GetCapture` at `0x180024483`
- `USER32!GetKeyState` at `0x180024475`
- `USER32!GetKeyState` at `0x180024475`

## pseudocode

```c
int __fastcall DrawButton(HDC hdc, int a2, int a3, __int64 a4, __int64 a5, int a6)
{
  int v8; // eax
  int v9; // r13d
  int v10; // ecx
  unsigned int v11; // r12d
  int v12; // r14d
  HWND v13; // rbx
  int v14; // ebx
  int v15; // ecx
  HDC CompatibleDC; // rax
  unsigned int v17; // edx
  int v18; // ecx
  int v19; // edx
  LONG v20; // eax
  unsigned int v21; // r12d
  char v22; // al
  int v23; // eax
  HFONT v24; // rdx
  COLORREF v25; // eax
  int v26; // r8d
  int v27; // r14d
  int v28; // r9d
  int v29; // eax
  int v30; // ebx
  int v31; // eax
  int v32; // r10d
  unsigned int v33; // r13d
  int v34; // eax
  signed int v35; // eax
  bool v36; // zf
  int v37; // eax
  int v38; // ecx
  char v39; // r14
  int v40; // ecx
  LONG left; // eax
  LONG v42; // ecx
  HGDIOBJ v43; // r12
  LONG v44; // edx
  COLORREF v45; // r14d
  COLORREF v46; // ebx
  LONG v47; // ecx
  int v48; // r12d
  int v49; // r8d
  unsigned int v50; // ebx
  HGDIOBJ v51; // r14
  __int64 v52; // rax
  HGDIOBJ v53; // rbx
  HGDIOBJ v54; // rbx
  char v55; // al
  __int64 v56; // rbx
  __int64 v57; // r14
  int v58; // r10d
  unsigned __int16 v59; // r9
  int yTopa; // [rsp+50h] [rbp-B0h]
  int y; // [rsp+54h] [rbp-ACh]
  int ya; // [rsp+54h] [rbp-ACh]
  unsigned int w; // [rsp+58h] [rbp-A8h]
  int v66; // [rsp+5Ch] [rbp-A4h]
  unsigned int cy; // [rsp+60h] [rbp-A0h]
  int xLefta; // [rsp+64h] [rbp-9Ch]
  char v70; // [rsp+68h] [rbp-98h]
  LONG v71; // [rsp+6Ch] [rbp-94h]
  LONG top; // [rsp+70h] [rbp-90h]
  LONG bottom; // [rsp+74h] [rbp-8Ch]
  COLORREF v74; // [rsp+7Ch] [rbp-84h]
  HGDIOBJ v75; // [rsp+80h] [rbp-80h]
  HFONT ho; // [rsp+88h] [rbp-78h]
  _QWORD v77[8]; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT v78[12]; // [rsp+D0h] [rbp-30h] BYREF
  RECT rcSrc; // [rsp+190h] [rbp+90h] BYREF
  LOGFONTW pv; // [rsp+1A0h] [rbp+A0h] BYREF

  v8 = TBWidthOfButton(a4, a5, hdc);
  v9 = *(_DWORD *)(a4 + 184);
  y = v8;
  memset(v78, 0, sizeof(v78));
  v10 = *(unsigned __int8 *)(a5 + 8);
  if ( (v10 & 0x10) != 0 )
  {
    if ( (v10 & 2) != 0 || (v10 & 4) == 0 )
      v10 &= ~0x10u;
    else
      v10 = 16;
  }
  v11 = v10 & 0xFFFFFFFB;
  v12 = 0;
  if ( a6 )
    v11 = v10;
  if ( (*(_DWORD *)(a4 + 16) & 0x800) != 0 && *(_QWORD *)(a4 + 80) + 40LL * *(int *)(a4 + 284) == a5 )
    v12 = 1;
  if ( (v11 & 2) != 0 || GetKeyState(1) >= 0 || (v13 = *(HWND *)a4, GetCapture() != v13) )
  {
    if ( v12 )
      goto LABEL_18;
  }
  else
  {
    v12 = 0;
  }
  if ( *(_DWORD *)(a4 + 288) == (a5 - *(_QWORD *)(a4 + 80)) / 40 )
    v12 = 1;
LABEL_18:
  *(_QWORD *)&v78[6].left = *(int *)(a5 + 4);
  *(_QWORD *)&v78[7].left = *(_QWORD *)(a5 + 16);
  v78[6].right = 0;
  v14 = a2;
  *(_QWORD *)&v78[4].right = hdc;
  SetRect(&v78[5], a2, a3, a2 + y, a3 + v9);
  v15 = v9;
  if ( (*(_BYTE *)(a4 + 56) & 4) == 0 )
    v15 = v9 - 2 * g_cyEdge;
  InitTBDrawItem((int)v78, a4, a5, v11, v12, y - 3 * g_cxEdge, v15);
  LODWORD(CompatibleDC) = CICustomDrawNotify(a4, 65537, &v78[2].right);
  v78[2].left = (int)CompatibleDC;
  v71 = v78[6].right & 0x40;
  v78[1].top = v71;
  if ( ((unsigned __int8)CompatibleDC & 4) != 0 )
    goto LABEL_135;
  ho = 0;
  v17 = ((unsigned int)v78[6].right >> 3) & 1 | 2;
  if ( (v78[6].right & 1) == 0 )
    v17 = ((unsigned int)v78[6].right >> 3) & 1;
  v18 = v17 | 4;
  if ( (v78[6].right & 4) != 0 )
    v18 = v17;
  v19 = v18 | 0x80;
  if ( (v78[6].right & 0x80) == 0 )
    v19 = v18;
  v20 = v19 | 0x10;
  if ( (v78[6].right & 0x100) == 0 )
    v20 = v19;
  v70 = v20;
  v78[1].left = v20;
  v21 = y - 2 * g_cxEdge;
  w = v21;
  xLefta = v78[11].left - v78[10].right;
  bottom = v78[10].bottom;
  top = v78[11].top;
  cy = v9 - 2 * g_cyEdge;
  if ( (*(_BYTE *)(a4 + 56) & 1) != 0 && (v22 = *(_BYTE *)(a5 + 9), (v22 & 8) != 0)
    || (v22 = *(_BYTE *)(a5 + 9), v22 < 0) )
  {
    if ( (*(_DWORD *)(a4 + 16) & 0x1000) != 0 || v22 >= 0 || *(int *)(a4 + 164) <= 0 || !TB_StrForButton(a4, a5) )
    {
      v23 = TBDDArrowAdjustment(a4, a5);
      v21 -= v23;
      xLefta -= v23;
      w = v21;
    }
  }
  if ( (*(_DWORD *)(a4 + 316) & 0x20000) != 0
    || (memset(&pv, 0, sizeof(pv)), !GetObjectW(*(HANDLE *)(a4 + 128), 92, &pv))
    || (pv.lfQuality = 3, ho = CreateFontIndirectW(&pv), (v24 = ho) == 0) )
  {
    v24 = *(HFONT *)(a4 + 128);
  }
  v75 = SelectObject(hdc, v24);
  v25 = SetTextColor(hdc, v78[9].left);
  v26 = *(_DWORD *)(a4 + 16);
  v74 = v25;
  v27 = a3;
  if ( (v26 & 0x800) == 0 )
  {
    DrawBlankButton(hdc, v9, (__int64)v78);
    v26 = *(_DWORD *)(a4 + 16);
  }
  v28 = g_cxEdge;
  v29 = v14 + g_cxEdge;
  v30 = a3 + g_cyEdge;
  yTopa = v29;
  ya = v27 + g_cyEdge;
  if ( (*(_BYTE *)(a4 + 56) & 4) != 0 )
    v31 = *(_DWORD *)(a4 + 184) - *(_DWORD *)(a4 + 176);
  else
    v31 = *(_DWORD *)(a4 + 220) - 2 * g_cyEdge;
  v32 = 0;
  v33 = 0;
  v34 = v31 / 2;
  if ( v34 >= 0 )
    v33 = v34;
  if ( (v26 & 0x1000) == 0 )
  {
    if ( *(char *)(a5 + 9) < 0 && *(int *)(a4 + 164) > 0 )
    {
      v36 = TB_StrForButton(a4, a5) == 0;
      v37 = 1;
      if ( !v36 )
        goto LABEL_57;
    }
    goto LABEL_56;
  }
  if ( !*(_DWORD *)(a4 + 164) || (*(_BYTE *)(a4 + 56) & 8) != 0 && (*(_BYTE *)(a5 + 9) & 0x40) == 0 )
  {
LABEL_56:
    v37 = v32;
LABEL_57:
    v38 = *(_DWORD *)(a4 + 172);
    if ( v37 )
      v35 = v21 + 2 * v28 - *(_DWORD *)(a4 + 208) - v38;
    else
      v35 = v21 - v38;
    goto LABEL_60;
  }
  v35 = *(_DWORD *)(a4 + 216);
LABEL_60:
  v39 = v70;
  v66 = v35 / 2;
  v40 = v35 / 2;
  left = v78[2].left;
  if ( (v70 & 3) != 0 && (v78[2].left & 0x40000) == 0 )
  {
    v66 = v40 + 1;
    ++v33;
  }
  v42 = v71;
  if ( (!v71 || *(__int64 *)(a4 + 40) < 5)
    && ((v70 & 0x11) != 0 || v70 < 0 && (*(_DWORD *)(a4 + 16) & 0x800) == 0 && (v78[2].left & 0x80000) == 0)
    && *(_QWORD *)&v78[7].right )
  {
    v43 = SelectObject(hdc, *(HGDIOBJ *)&v78[7].right);
    if ( v43 )
    {
      v44 = v78[9].top;
      if ( v70 >= 0 )
        v44 = v78[10].left;
      v45 = SetTextColor(hdc, v44);
      v46 = SetBkColor(hdc, v78[9].bottom);
      PatBlt(hdc, yTopa, ya, w, cy, 0xF00021u);
      SelectObject(hdc, v43);
      SetTextColor(hdc, v45);
      SetBkColor(hdc, v46);
      v30 = ya;
      v39 = v70;
    }
    v42 = v71;
    left = v78[2].left;
  }
  if ( (left & 0x20000) != 0 && v42 )
    PatB(hdc, v78[5].bottom - v78[5].top, v78[10].top);
  v47 = *(_DWORD *)a5;
  v78[1].bottom = v47;
  if ( v47 == -1 && (*(_BYTE *)(a4 + 316) & 2) != 0 )
  {
    memset(v77, 0, sizeof(v77));
    HIDWORD(v77[3]) = *(_DWORD *)(a5 + 4);
    v77[4] = *(_QWORD *)(a5 + 16);
    LODWORD(v77[3]) = 1;
    LODWORD(v77[5]) = -1;
    CCSendNotify(a4, 4294966579LL, v77);
    v47 = v77[5];
    if ( (v77[3] & 0x10000000) != 0 && (v77[3] & 1) != 0 )
      *(_DWORD *)a5 = v77[5];
  }
  v78[1].bottom = (__int16)v47;
  v78[1].right = SHIWORD(v47);
  v48 = v39 & 4;
  if ( (v39 & 4) != 0 && ((*(_DWORD *)(a4 + 16) & 0x8000000) == 0 || *(__int64 *)(a4 + 40) < 5) || TBGetImageList(a4, 2) )
  {
    v49 = v30;
    if ( (*(_BYTE *)(a4 + 56) & 4) != 0 )
      v49 = v30 - g_cyEdge;
    v50 = v66;
    DrawFace((_DWORD)hdc, yTopa, v49, v66, v33, xLefta, top - bottom, (__int64)v78);
  }
  else
  {
    v50 = v66;
  }
  if ( (v39 & 4) == 0 || (*(_DWORD *)(a4 + 16) & 0x8000000) != 0 && *(__int64 *)(a4 + 40) >= 5 )
  {
    if ( !*(_QWORD *)(a4 + 64) )
    {
      CompatibleDC = CreateCompatibleDC(hdc);
      *(_QWORD *)(a4 + 64) = CompatibleDC;
      if ( !CompatibleDC )
        return (int)CompatibleDC;
      SetTextColor(CompatibleDC, 0);
      SelectObject(*(HDC *)(a4 + 64), *(HGDIOBJ *)(a4 + 128));
    }
    v51 = SelectObject(*(HDC *)(a4 + 64), *(HGDIOBJ *)(a4 + 72));
    if ( (GetLayout(hdc) & 1) != 0 && (GetLayout(*(HDC *)(a4 + 64)) & 1) == 0 )
      SetLayout(*(HDC *)(a4 + 64), 1u);
    v52 = TBGetImageList(a4, 2);
    CreateMask(v50, v33, w, cy, v52 == 0, v78);
    SetTextColor(hdc, 0);
    SetBkColor(hdc, 0xFFFFFFu);
    if ( (v70 & 0x10) == 0 && (v78[2].left & 0x100000) == 0 )
    {
      v53 = SelectObject(hdc, g_hbrBtnHighlight);
      if ( v53 )
      {
        BitBlt(hdc, yTopa + 1, ya + 1, w, cy, *(HDC *)(a4 + 64), 0, 0, 0xB8074Au);
        SelectObject(hdc, v53);
      }
    }
    v54 = SelectObject(hdc, g_hbrBtnShadow);
    if ( v54 )
    {
      BitBlt(hdc, yTopa, ya, w, cy, *(HDC *)(a4 + 64), 0, 0, 0xB8074Au);
      SelectObject(hdc, v54);
    }
    if ( (v70 & 1) != 0 )
      BitBlt(*(HDC *)(a4 + 64), 1, 1, w - 1, cy - 1, *(HDC *)(a4 + 64), 0, 0, 0x8800C6u);
    SelectObject(*(HDC *)(a4 + 64), v51);
  }
  if ( (*(_BYTE *)(a4 + 56) & 1) != 0 && (v55 = *(_BYTE *)(a5 + 9), (v55 & 8) != 0)
    || (v55 = *(_BYTE *)(a5 + 9), v55 < 0) )
  {
    v36 = (*(_DWORD *)(a4 + 16) & 0x1000) == 0;
    v56 = *(_QWORD *)(a4 + 80);
    v57 = *(int *)(a4 + 288);
    rcSrc = 0;
    if ( v36 && v55 < 0 && *(int *)(a4 + 164) > 0 && TB_StrForButton(a4, a5) )
    {
      rcSrc.left = yTopa + *(_DWORD *)(a4 + 172) + v66;
      rcSrc.right = *(_DWORD *)(a4 + 208) + rcSrc.left;
      rcSrc.top = v33 + ya;
      rcSrc.bottom = *(_DWORD *)(a4 + 176) + v33 + ya;
    }
    else
    {
      TB_GetItemRect(a4, 0xCCCCCCCCCCCCCCCDuLL * ((a5 - v56) >> 3), &rcSrc);
      rcSrc.left = rcSrc.right - *(_DWORD *)(a4 + 208);
      v58 = 0;
    }
    v59 = ((*(char *)(a5 + 9) >> 15) & 0x100) + 96;
    if ( !v48 || (*(_DWORD *)(a4 + 16) & 0x8000000) != 0 && *(__int64 *)(a4 + 40) >= 5 )
    {
      v59 |= 0x80u;
    }
    else if ( (v56 + 40 * v57 == a5 || (v70 & 3) != v58)
           && ((*(_DWORD *)(a4 + 16) & 0x1000) != 0
            || *(char *)(a5 + 9) >= (char)v58
            || *(_DWORD *)(a4 + 164) <= v58
            || !TB_StrForButton(a4, a5)) )
    {
      v59 |= 0x10u;
    }
    else if ( v71 != v58 || (*(_DWORD *)(a4 + 16) & 0x800) == 0 )
    {
      v59 |= 8u;
    }
    DrawScrollArrow(hdc, &rcSrc, v59);
  }
  SelectObject(hdc, v75);
  SetTextColor(hdc, v74);
  LODWORD(CompatibleDC) = (_DWORD)ho;
  if ( ho )
    LODWORD(CompatibleDC) = DeleteObject(ho);
LABEL_135:
  if ( (v78[2].left & 0x10) != 0 )
    LODWORD(CompatibleDC) = CICustomDrawNotify(a4, 65538, &v78[2].right);
  return (int)CompatibleDC;
}

```

## disassembly

```asm
0x1800243a4  push    rbp
0x1800243a6  push    rbx
0x1800243a7  push    rsi
0x1800243a8  push    rdi
0x1800243a9  push    r12
0x1800243ab  push    r13
0x1800243ad  push    r14
0x1800243af  push    r15
0x1800243b1  lea     rbp, [rsp-118h]
0x1800243b9  sub     rsp, 218h
0x1800243c0  mov     rax, cs:__security_cookie
0x1800243c7  xor     rax, rsp
0x1800243ca  mov     [rbp+150h+var_50], rax
0x1800243d1  mov     rsi, [rbp+150h+arg_20]
0x1800243d8  mov     r15, rcx
0x1800243db  mov     [rsp+250h+yTop], r8d
0x1800243e0  mov     rdi, r9
0x1800243e3  mov     r8, rcx
0x1800243e6  mov     [rsp+250h+xLeft], edx
0x1800243ea  mov     rdx, rsi
0x1800243ed  mov     rcx, r9
0x1800243f0  call    TBWidthOfButton
0x1800243f5  mov     r13d, [rdi+0B8h]
0x1800243fc  lea     rcx, [rbp+150h+var_180]; void *
0x180024400  xor     edx, edx; Val
0x180024402  mov     [rsp+250h+y], eax
0x180024406  mov     r8d, 0C0h; Size
0x18002440c  call    memset
0x180024411  movzx   ecx, byte ptr [rsi+8]
0x180024415  mov     eax, 10h
0x18002441a  test    al, cl
0x18002441c  jz      short loc_18002442F
0x18002441e  test    cl, 2
0x180024421  jnz     short loc_18002442C
0x180024423  test    cl, 4
0x180024426  jz      short loc_18002442C
0x180024428  mov     ecx, eax
0x18002442a  jmp     short loc_18002442F
0x18002442c  and     ecx, 0FFFFFFEFh
0x18002442f  xor     ebx, ebx
0x180024431  mov     r12d, ecx
0x180024434  and     r12d, 0FFFFFFFBh
0x180024438  mov     r14d, ebx
0x18002443b  cmp     [rbp+150h+arg_28], ebx
0x180024441  cmovnz  r12d, ecx
0x180024445  lea     r8d, [rbx+1]
0x180024449  test    dword ptr [rdi+10h], 800h
0x180024450  jz      short loc_18002446C
0x180024452  movsxd  rax, dword ptr [rdi+11Ch]
0x180024459  mov     rcx, [rdi+50h]
0x18002445d  lea     rax, [rax+rax*4]
0x180024461  lea     rdx, [rcx+rax*8]
0x180024465  cmp     rdx, rsi
0x180024468  cmovz   r14d, r8d
0x18002446c  test    r12b, 2
0x180024470  jnz     short loc_180024497
0x180024472  mov     ecx, r8d; nVirtKey
0x180024475  call    cs:__imp_GetKeyState
0x18002447b  test    ax, ax
0x18002447e  jns     short loc_180024497
0x180024480  mov     rbx, [rdi]
0x180024483  call    cs:__imp_GetCapture
0x180024489  cmp     rax, rbx
0x18002448c  jnz     short loc_180024495
0x18002448e  xor     ebx, ebx
0x180024490  mov     r14d, ebx
0x180024493  jmp     short loc_18002449C
0x180024495  xor     ebx, ebx
0x180024497  test    r14d, r14d
0x18002449a  jnz     short loc_1800244D1
0x18002449c  mov     rcx, rsi
0x18002449f  mov     rax, 6666666666666667h
0x1800244a9  sub     rcx, [rdi+50h]
0x1800244ad  imul    rcx
0x1800244b0  sar     rdx, 4
0x1800244b4  mov     rax, rdx
0x1800244b7  shr     rax, 3Fh
0x1800244bb  add     rdx, rax
0x1800244be  movsxd  rax, dword ptr [rdi+120h]
0x1800244c5  cmp     rax, rdx
0x1800244c8  mov     eax, 1
0x1800244cd  cmovz   r14d, eax
0x1800244d1  movsxd  rax, dword ptr [rsi+4]
0x1800244d5  mov     ecx, [rsp+250h+yTop]
0x1800244d9  mov     r8d, ecx; yTop
0x1800244dc  mov     r9d, [rsp+250h+y]
0x1800244e1  mov     [rbp+150h+var_120], rax
0x1800244e5  mov     rax, [rsi+10h]
0x1800244e9  mov     [rbp+150h+var_110], rax
0x1800244ed  lea     eax, [rcx+r13]
0x1800244f1  mov     [rbp+150h+var_118], ebx
0x1800244f4  lea     rcx, [rbp+150h+rc]; lprc
0x1800244f8  mov     ebx, [rsp+250h+xLeft]
0x1800244fc  add     r9d, ebx; xRight
0x1800244ff  mov     edx, ebx; xLeft
0x180024501  mov     [rsp+250h+yBottom], eax; yBottom
0x180024505  mov     [rbp+150h+var_138], r15
0x180024509  call    cs:__imp_SetRect
0x18002450f  mov     eax, cs:g_cxEdge
0x180024515  mov     edx, [rsp+250h+y]
0x180024519  lea     ecx, [rax+rax*2]
0x18002451c  sub     edx, ecx
0x18002451e  mov     ecx, r13d
0x180024521  test    byte ptr [rdi+38h], 4
0x180024525  jnz     short loc_180024531
0x180024527  mov     eax, cs:g_cyEdge
0x18002452d  add     eax, eax
0x18002452f  sub     ecx, eax
0x180024531  mov     [rsp+250h+x1], ecx; int
0x180024535  mov     r9d, r12d; int
0x180024538  mov     [rsp+250h+rop], edx; xRight
0x18002453c  lea     rcx, [rbp+150h+var_180]; int
0x180024540  mov     rdx, rdi; int
0x180024543  mov     [rsp+250h+yBottom], r14d; int
0x180024548  mov     r8, rsi; int
0x18002454b  call    InitTBDrawItem
0x180024550  lea     r8, [rbp+150h+var_158]
0x180024554  mov     edx, 10001h
0x180024559  mov     rcx, rdi
0x18002455c  call    CICustomDrawNotify
0x180024561  mov     r8d, [rbp+150h+var_118]
0x180024565  mov     ecx, r8d
0x180024568  and     ecx, 40h
0x18002456b  mov     [rbp+150h+var_160], eax
0x18002456e  mov     [rsp+250h+var_1E4], ecx
0x180024572  mov     [rbp+150h+var_16C], ecx
0x180024575  test    al, 4
0x180024577  jnz     loc_180024DB5
0x18002457d  mov     r14d, [rsp+250h+y]
0x180024582  xor     r9d, r9d
0x180024585  mov     ecx, r8d
0x180024588  mov     [rbp+150h+ho], r9
0x18002458c  shr     ecx, 3
0x18002458f  mov     r12d, r14d
0x180024592  lea     r10d, [r9+1]
0x180024596  and     ecx, r10d
0x180024599  lea     r11d, [r10+7Fh]
0x18002459d  mov     edx, ecx
0x18002459f  or      edx, 2
0x1800245a2  test    r10b, r8b
0x1800245a5  cmovz   edx, ecx
0x1800245a8  mov     ecx, edx
0x1800245aa  or      ecx, 4
0x1800245ad  test    r8b, 4
0x1800245b1  cmovnz  ecx, edx
0x1800245b4  mov     edx, ecx
0x1800245b6  or      edx, r11d
0x1800245b9  test    r11b, r8b
0x1800245bc  cmovz   edx, ecx
0x1800245bf  mov     ecx, r13d
0x1800245c2  mov     eax, edx
0x1800245c4  or      eax, 10h
0x1800245c7  bt      r8d, 8
0x1800245cc  cmovnb  eax, edx
0x1800245cf  mov     [rsp+250h+var_1E8], eax
0x1800245d3  mov     [rbp+150h+var_170], eax
0x1800245d6  mov     eax, cs:g_cxEdge
0x1800245dc  add     eax, eax
0x1800245de  sub     r12d, eax
0x1800245e1  mov     eax, cs:g_cyEdge
0x1800245e7  add     eax, eax
0x1800245e9  mov     [rsp+250h+w], r12d
0x1800245ee  sub     ecx, eax
0x1800245f0  mov     eax, [rbp+150h+var_D0]
0x1800245f6  sub     eax, [rbp+150h+var_D8]
0x1800245f9  mov     [rsp+250h+xLeft], eax
0x1800245fd  mov     eax, [rbp+150h+var_D4]
0x180024600  mov     [rsp+250h+var_1DC], eax
0x180024604  mov     eax, [rbp+150h+var_CC]
0x18002460a  mov     [rsp+250h+var_1E0], eax
0x18002460e  mov     [rsp+250h+cy], ecx
0x180024612  test    [rdi+38h], r10b
0x180024616  jz      short loc_18002461F
0x180024618  mov     al, [rsi+9]
0x18002461b  test    al, 8
0x18002461d  jnz     short loc_180024626
0x18002461f  mov     al, [rsi+9]
0x180024622  test    al, al
0x180024624  jns     short loc_180024663
0x180024626  test    dword ptr [rdi+10h], 1000h
0x18002462d  jnz     short loc_18002464C
0x18002462f  test    al, al
0x180024631  jns     short loc_18002464C
0x180024633  cmp     [rdi+0A4h], r9d
0x18002463a  jle     short loc_18002464C
0x18002463c  mov     rdx, rsi
0x18002463f  mov     rcx, rdi
0x180024642  call    TB_StrForButton
0x180024647  test    rax, rax
0x18002464a  jnz     short loc_180024663
0x18002464c  mov     rdx, rsi
0x18002464f  mov     rcx, rdi
0x180024652  call    TBDDArrowAdjustment
0x180024657  sub     r12d, eax
0x18002465a  sub     [rsp+250h+xLeft], eax
0x18002465e  mov     [rsp+250h+w], r12d
0x180024663  test    dword ptr [rdi+13Ch], 20000h
0x18002466d  jnz     short loc_1800246BE
0x18002466f  xor     edx, edx; Val
0x180024671  lea     rcx, [rbp+150h+pv]; void *
0x180024678  lea     r8d, [rdx+5Ch]; Size
0x18002467c  call    memset
0x180024681  mov     rcx, [rdi+80h]; h
0x180024688  lea     r8, [rbp+150h+pv]; pv
0x18002468f  mov     edx, 5Ch ; '\'; c
0x180024694  call    cs:__imp_GetObjectW
0x18002469a  test    eax, eax
0x18002469c  jz      short loc_1800246BE
0x18002469e  lea     rcx, [rbp+150h+pv]; lplf
0x1800246a5  mov     [rbp+150h+var_96], 3
0x1800246ac  call    cs:__imp_CreateFontIndirectW
0x1800246b2  mov     [rbp+150h+ho], rax
0x1800246b6  mov     rdx, rax
0x1800246b9  test    rax, rax
0x1800246bc  jnz     short loc_1800246C5
0x1800246be  mov     rdx, [rdi+80h]; h
0x1800246c5  mov     rcx, r15; hdc
0x1800246c8  call    cs:__imp_SelectObject
0x1800246ce  mov     edx, [rbp+150h+color]; color
0x1800246d1  mov     rcx, r15; hdc
0x1800246d4  mov     [rbp+150h+var_1D0], rax
0x1800246d8  call    cs:__imp_SetTextColor
0x1800246de  mov     r8d, [rdi+10h]
0x1800246e2  mov     [rsp+250h+var_1D4], eax
0x1800246e6  bt      r8d, 0Bh
0x1800246eb  jb      short loc_180024716
0x1800246ed  lea     rax, [rbp+150h+var_180]
0x1800246f1  mov     r9d, r14d
0x1800246f4  mov     r14d, [rsp+250h+yTop]
0x1800246f9  mov     edx, ebx
0x1800246fb  mov     qword ptr [rsp+250h+rop], rax; __int64
0x180024700  mov     r8d, r14d
0x180024703  mov     rcx, r15; hdc
0x180024706  mov     [rsp+250h+yBottom], r13d; int
0x18002470b  call    DrawBlankButton
0x180024710  mov     r8d, [rdi+10h]
0x180024714  jmp     short loc_18002471B
0x180024716  mov     r14d, [rsp+250h+yTop]
0x18002471b  mov     r9d, cs:g_cxEdge
0x180024722  lea     eax, [rbx+r9]
0x180024726  mov     ebx, cs:g_cyEdge
0x18002472c  add     ebx, r14d
0x18002472f  mov     [rsp+250h+yTop], eax
0x180024733  test    byte ptr [rdi+38h], 4
0x180024737  mov     [rsp+250h+y], ebx
0x18002473b  jz      short loc_18002474B
0x18002473d  mov     eax, [rdi+0B8h]
0x180024743  sub     eax, [rdi+0B0h]
0x180024749  jmp     short loc_18002475D
0x18002474b  mov     eax, cs:g_cyEdge
0x180024751  mov     ecx, [rdi+0DCh]
0x180024757  add     eax, eax
0x180024759  sub     ecx, eax
0x18002475b  mov     eax, ecx
0x18002475d  xor     r10d, r10d
0x180024760  cdq
0x180024761  sub     eax, edx
0x180024763  mov     r13d, r10d
0x180024766  sar     eax, 1
0x180024768  test    eax, eax
0x18002476a  cmovns  r13d, eax
0x18002476e  bt      r8d, 0Ch
0x180024773  jnb     short loc_180024792
0x180024775  cmp     [rdi+0A4h], r10d
0x18002477c  jz      short loc_1800247B6
0x18002477e  test    byte ptr [rdi+38h], 8
0x180024782  jz      short loc_18002478A
0x180024784  test    byte ptr [rsi+9], 40h
0x180024788  jz      short loc_1800247B6
0x18002478a  mov     eax, [rdi+0D8h]
0x180024790  jmp     short loc_1800247D9
0x180024792  cmp     [rsi+9], r10b
0x180024796  jge     short loc_1800247B6
0x180024798  cmp     [rdi+0A4h], r10d
0x18002479f  jle     short loc_1800247B6
0x1800247a1  mov     rdx, rsi
0x1800247a4  mov     rcx, rdi
0x1800247a7  call    TB_StrForButton
0x1800247ac  test    rax, rax
0x1800247af  mov     eax, 1
0x1800247b4  jnz     short loc_1800247B9
0x1800247b6  mov     eax, r10d
0x1800247b9  mov     ecx, [rdi+0ACh]
0x1800247bf  test    eax, eax
0x1800247c1  jz      short loc_1800247D4
0x1800247c3  lea     eax, [r9+r9]
0x1800247c7  sub     eax, [rdi+0D0h]
0x1800247cd  sub     eax, ecx
0x1800247cf  add     eax, r12d
0x1800247d2  jmp     short loc_1800247D9
0x1800247d4  mov     eax, r12d
0x1800247d7  sub     eax, ecx
0x1800247d9  mov     r14d, [rsp+250h+var_1E8]
0x1800247de  cdq
0x1800247df  sub     eax, edx
0x1800247e1  mov     edx, r14d
0x1800247e4  sar     eax, 1
0x1800247e6  and     edx, 3
0x1800247e9  mov     [rsp+250h+var_1F4], eax
0x1800247ed  mov     ecx, eax
  ... truncated ...
```
