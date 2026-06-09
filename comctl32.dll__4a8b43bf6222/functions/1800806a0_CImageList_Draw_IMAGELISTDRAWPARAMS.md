# CImageList::Draw(_IMAGELISTDRAWPARAMS *)

- ea: `0x1800806a0`
- end: `0x180080fe5`
- name: `?Draw@CImageList@@UEAAJPEAU_IMAGELISTDRAWPARAMS@@@Z`
- size: `2373`
- prototype: `__int64 __fastcall(CImageList *__hidden this, struct _IMAGELISTDRAWPARAMS *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1800115f0`
- `0x1800806a0`
- `0x180081454`
- `0x180081768`
- `0x180081960`
- `0x180081e68`
- `0x180084d30`
- `0x18008ea60`
- `0x180090020`

## import_xrefs

- `GDI32!SelectObject` at `0x180080940`
- `GDI32!SelectObject` at `0x18008098d`
- `GDI32!SelectObject` at `0x180080db3`
- `GDI32!SelectObject` at `0x180080e01`
- `GDI32!SelectObject` at `0x180080940`
- `GDI32!SelectObject` at `0x18008098d`
- `GDI32!SelectObject` at `0x180080db3`
- `GDI32!SelectObject` at `0x180080e01`
- `GDI32!BitBlt` at `0x180080888`
- `GDI32!BitBlt` at `0x180080930`
- `GDI32!BitBlt` at `0x18008097f`
- `GDI32!BitBlt` at `0x180080aaf`
- `GDI32!BitBlt` at `0x180080b48`
- `GDI32!BitBlt` at `0x180080ba5`
- `GDI32!BitBlt` at `0x180080be0`
- `GDI32!BitBlt` at `0x180080c1e`
- `GDI32!BitBlt` at `0x180080c64`
- `GDI32!BitBlt` at `0x180080c9d`
- `GDI32!BitBlt` at `0x180080d73`
- `GDI32!BitBlt` at `0x180080df5`
- `GDI32!BitBlt` at `0x180080e58`
- `GDI32!BitBlt` at `0x180080eb3`
- `GDI32!BitBlt` at `0x180080888`
- `GDI32!BitBlt` at `0x180080930`
- `GDI32!BitBlt` at `0x18008097f`
- `GDI32!BitBlt` at `0x180080aaf`
- `GDI32!BitBlt` at `0x180080b48`
- `GDI32!BitBlt` at `0x180080ba5`
- `GDI32!BitBlt` at `0x180080be0`
- `GDI32!BitBlt` at `0x180080c1e`
- `GDI32!BitBlt` at `0x180080c64`
- `GDI32!BitBlt` at `0x180080c9d`
- `GDI32!BitBlt` at `0x180080d73`
- `GDI32!BitBlt` at `0x180080df5`
- `GDI32!BitBlt` at `0x180080e58`
- `GDI32!BitBlt` at `0x180080eb3`
- `GDI32!DeleteObject` at `0x180080e0a`
- `GDI32!DeleteObject` at `0x180080e0a`
- `GDI32!GetStockObject` at `0x180080f92`
- `GDI32!GetStockObject` at `0x180080f92`
- `GDI32!GetDeviceCaps` at `0x180080f83`
- `GDI32!GetDeviceCaps` at `0x180080f83`
- `GDI32!SelectPalette` at `0x180080fa2`
- `GDI32!SelectPalette` at `0x180080fa2`
- `GDI32!SetBkColor` at `0x180080a60`
- `GDI32!SetBkColor` at `0x180080ae9`
- `GDI32!SetBkColor` at `0x180080cd1`
- `GDI32!SetBkColor` at `0x180080a60`
- `GDI32!SetBkColor` at `0x180080ae9`
- `GDI32!SetBkColor` at `0x180080cd1`
- `GDI32!SetTextColor` at `0x180080ad7`
- `GDI32!SetTextColor` at `0x180080cc4`
- `GDI32!SetTextColor` at `0x180080ad7`
- `GDI32!SetTextColor` at `0x180080cc4`
- `GDI32!SetBrushOrgEx` at `0x180080d9e`
- `GDI32!SetBrushOrgEx` at `0x180080e1b`
- `GDI32!SetBrushOrgEx` at `0x180080d9e`
- `GDI32!SetBrushOrgEx` at `0x180080e1b`
- `GDI32!CreateSolidBrush` at `0x180080da7`
- `GDI32!CreateSolidBrush` at `0x180080da7`
- `GDI32!GetLayout` at `0x180080750`
- `GDI32!GetLayout` at `0x180080750`
- `GDI32!GetBkColor` at `0x180080a48`
- `GDI32!GetBkColor` at `0x180080a48`
- `KERNEL32!EnterCriticalSection` at `0x180080780`
- `KERNEL32!EnterCriticalSection` at `0x180080780`
- `KERNEL32!LeaveCriticalSection` at `0x180080faf`
- `KERNEL32!LeaveCriticalSection` at `0x180080faf`

## pseudocode

```c
__int64 __fastcall CImageList::Draw(CImageList *this, struct _IMAGELISTDRAWPARAMS *a2)
{
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  int i; // eax
  int v9; // r12d
  int v10; // r13d
  COLORREF rgbBk; // eax
  int cx; // edx
  int cy; // ecx
  HDC *p_hdcDst; // r15
  HDC v15; // r8
  UINT fStyle; // eax
  HDC WorkDC; // rax
  int v18; // edx
  int v19; // r8d
  COLORREF rgbFg; // ecx
  HDC v21; // r14
  int v22; // edx
  int v23; // r8d
  __int64 v24; // rdx
  int v25; // eax
  HGDIOBJ v26; // rbx
  int v27; // edx
  int v28; // r9d
  BOOL v29; // ebx
  DWORD dwRop; // eax
  COLORREF BkColor; // eax
  COLORREF v32; // edx
  DWORD v33; // ecx
  int *p_y; // r13
  int *p_x; // r12
  COLORREF v36; // edx
  HDC v37; // rcx
  int v38; // eax
  COLORREF v39; // r12d
  HBRUSH SolidBrush; // rax
  HGDIOBJ v41; // rbx
  HGDIOBJ v42; // rax
  __int64 v43; // rdx
  UINT v44; // eax
  UINT v45; // eax
  HPALETTE StockObject; // rax
  HDC hdcSrc; // [rsp+28h] [rbp-D8h]
  int x1; // [rsp+30h] [rbp-D0h]
  int y1; // [rsp+38h] [rbp-C8h]
  DWORD rop; // [rsp+40h] [rbp-C0h]
  int y; // [rsp+50h] [rbp-B0h]
  int v52; // [rsp+54h] [rbp-ACh]
  int v53; // [rsp+58h] [rbp-A8h]
  int v54; // [rsp+5Ch] [rbp-A4h]
  COLORREF color; // [rsp+60h] [rbp-A0h]
  COLORREF colora; // [rsp+60h] [rbp-A0h]
  COLORREF colorb; // [rsp+60h] [rbp-A0h]
  HDC hdc; // [rsp+68h] [rbp-98h]
  HDC v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+70h] [rbp-90h]
  COLORREF v61; // [rsp+78h] [rbp-88h]
  _OWORD v62[6]; // [rsp+80h] [rbp-80h] BYREF
  int v63[4]; // [rsp+E0h] [rbp-20h] BYREF
  int x[4]; // [rsp+F0h] [rbp-10h] BYREF

  *(_OWORD *)v63 = 0;
  *(_OWORD *)x = 0;
  memset(v62, 0, 0x58u);
  if ( a2->cbSize != 88 )
  {
    if ( a2->cbSize != 72 )
      return 2147942487LL;
    v4 = *(_OWORD *)&a2->i;
    v62[0] = *(_OWORD *)&a2->cbSize;
    v5 = *(_OWORD *)&a2->x;
    LODWORD(v62[0]) = 88;
    v62[1] = v4;
    v6 = *(_OWORD *)&a2->xBitmap;
    v62[2] = v5;
    *(_QWORD *)&v5 = *(_QWORD *)&a2->fStyle;
    a2 = (struct _IMAGELISTDRAWPARAMS *)v62;
    *(_QWORD *)&v62[4] = v5;
    v62[3] = v6;
  }
  i = a2->i;
  if ( i < 0 || i >= *((_DWORD *)this + 10) )
    return 2147942487LL;
  if ( *((_QWORD *)this + 60) && (GetLayout(a2->hdcDst) & 1) != 0 )
    return (*(__int64 (__fastcall **)(__int64, struct _IMAGELISTDRAWPARAMS *))(*(_QWORD *)(*((_QWORD *)this + 60) + 16LL)
                                                                             + 64LL))(
             *((_QWORD *)this + 60) + 16LL,
             a2);
  EnterCriticalSection(&g_csDll);
  (*(void (__fastcall **)(CImageList *, _QWORD, int *))(*(_QWORD *)this + 120LL))(this, (unsigned int)a2->i, v63);
  v9 = a2->xBitmap + v63[0];
  v10 = a2->yBitmap + v63[1];
  rgbBk = a2->rgbBk;
  v53 = v9;
  v63[0] = v9;
  v54 = v10;
  v63[1] = v10;
  if ( rgbBk == -16777216 )
  {
    rgbBk = *((_DWORD *)this + 18);
    a2->rgbBk = rgbBk;
  }
  if ( rgbBk == -1 )
    a2->fStyle |= 1u;
  cx = a2->cx;
  if ( !cx )
  {
    cx = v63[2] - v9;
    a2->cx = v63[2] - v9;
  }
  cy = a2->cy;
  if ( !cy )
  {
    cy = v63[3] - v10;
    a2->cy = v63[3] - v10;
  }
  p_hdcDst = &a2->hdcDst;
  do
  {
    v15 = (HDC)*((_QWORD *)this + 14);
    fStyle = a2->fStyle;
    hdc = v15;
    if ( (fStyle & 0xE) != 0 )
    {
      WorkDC = ImageList_GetWorkDC(*p_hdcDst, cx, cy);
      rgbFg = a2->rgbFg;
      v21 = WorkDC;
      v52 = 0;
      y = 0;
      if ( rgbFg == -1 && hdc )
      {
        if ( (*((_DWORD *)this + 16) & 0xFE) != 0x10 || (a2->fStyle & 0x10) != 0 )
        {
          v24 = *((unsigned int *)this + 10);
          *((_DWORD *)this + 10) = v24 + 1;
          v25 = (*(__int64 (__fastcall **)(CImageList *, __int64, int *))(*(_QWORD *)this + 120LL))(this, v24, x);
          --*((_DWORD *)this + 10);
          if ( !v25 )
          {
            v9 = x[0];
            v10 = x[1];
            v53 = x[0];
            v54 = x[1];
          }
          BitBlt(v21, 0, 0, a2->cx, a2->cy, *((HDC *)this + 13), v63[0], v63[1], 0xCC0020u);
          v26 = SelectObject(hdc, g_hbrMonoDither);
          BitBlt(hdc, x[0], x[1], a2->cx, a2->cy, *((HDC *)this + 14), v63[0], v63[1], 0xFC008Au);
          SelectObject(hdc, v26);
        }
        else
        {
          BitBlt(WorkDC, 0, 0, a2->cx, a2->cy, *p_hdcDst, a2->x, a2->y, 0xCC0020u);
          ImageList_Blend16(
            v21,
            v22,
            v23,
            (CImageList *)((char *)this - 16),
            v63[0],
            v63[1],
            a2->cx,
            a2->cy,
            a2->rgbFg,
            a2->fStyle);
        }
        a2->fStyle |= 1u;
      }
      else
      {
        ImageList_Blend(
          WorkDC,
          v18,
          v19,
          (CImageList *)((char *)this - 16),
          v63[0],
          v63[1],
          a2->cx,
          a2->cy,
          rgbFg,
          a2->fStyle);
      }
      v27 = 0;
      v28 = 0;
      fStyle = a2->fStyle;
      v15 = hdc;
    }
    else
    {
      v21 = (HDC)*((_QWORD *)this + 13);
      v27 = v9;
      v52 = v9;
      v28 = v10;
      y = v10;
    }
    v59 = (HDC)*((_QWORD *)this + 13);
    v29 = v21 == v59;
    if ( (fStyle & 0x10) != 0 && v15 )
    {
      if ( (fStyle & 0x40) != 0 )
        dwRop = a2->dwRop;
      else
        dwRop = (fStyle & 1) != 0 ? 8913094 : 13369376;
      rop = dwRop;
      y1 = v54;
      x1 = v53;
      hdcSrc = v15;
      goto LABEL_70;
    }
    if ( (fStyle & 0x20) != 0 )
    {
      BkColor = GetBkColor(v21);
      v32 = a2->rgbBk;
      color = BkColor;
      if ( v32 != -16777216 )
        SetBkColor(v21, v32);
      if ( (a2->fStyle & 0x40) != 0 )
        v33 = a2->dwRop;
      else
        v33 = 13369376;
      p_y = &a2->y;
      p_x = &a2->x;
      BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, v21, v52, y, v33);
      v36 = color;
      v37 = v21;
      goto LABEL_55;
    }
    if ( (fStyle & 1) != 0 && v15 )
    {
      colora = SetTextColor(*p_hdcDst, 0);
      v61 = SetBkColor(*p_hdcDst, 0xFFFFFFu);
      if ( v21 == v59 )
      {
        v38 = *((_DWORD *)this + 18);
        if ( v38 == 0xFFFFFF )
        {
          p_y = &a2->y;
          p_x = &a2->x;
          BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, hdc, v53, v54, 0xBB0226u);
          BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, v21, v52, y, 0x8800C6u);
LABEL_54:
          SetTextColor(*p_hdcDst, colora);
          v36 = v61;
          v37 = *p_hdcDst;
LABEL_55:
          SetBkColor(v37, v36);
          goto LABEL_71;
        }
        if ( ((v38 + 1) & 0xFFFFFFFE) == 0 )
        {
          p_y = &a2->y;
          p_x = &a2->x;
          BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, hdc, v53, v54, 0x8800C6u);
          BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, v21, v52, y, 0xEE0086u);
          goto LABEL_54;
        }
      }
      BitBlt(v21, v52, y, a2->cx, a2->cy, hdc, v9, v10, 0x220326u);
      p_y = &a2->y;
      p_x = &a2->x;
      BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, hdc, v53, v54, 0x8800C6u);
      BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, v21, v52, y, 0xEE0086u);
      if ( v21 == v59 )
        CImageList::_ResetBkColor((CImageList *)((char *)this - 16), a2->i, a2->i, *((_DWORD *)this + 18));
      goto LABEL_54;
    }
    if ( v21 == v59 && a2->rgbBk == *((_DWORD *)this + 18) && *((_DWORD *)this + 8) )
      goto LABEL_69;
    if ( !v15 )
    {
      p_hdcDst = &a2->hdcDst;
LABEL_69:
      rop = 13369376;
      y1 = v28;
      x1 = v27;
      hdcSrc = v21;
LABEL_70:
      p_y = &a2->y;
      p_x = &a2->x;
      BitBlt(*p_hdcDst, a2->x, a2->y, a2->cx, a2->cy, hdcSrc, x1, y1, rop);
      goto LABEL_71;
    }
    if ( v21 != v59
      || ((v39 = a2->rgbBk, v39 != *((_DWORD *)this + 18)) || *((_DWORD *)this + 8))
      && GetNearestColor32(v21, v39) == v39 )
    {
      colorb = v21 == v59;
    }
    else
    {
      v21 = ImageList_GetWorkDC(*p_hdcDst, a2->cx, a2->cy);
      v52 = 0;
      y = 0;
      colorb = 0;
      BitBlt(v21, 0, 0, a2->cx, a2->cy, *((HDC *)this + 13), v63[0], v63[1], 0xCC0020u);
    }
    p_y = &a2->y;
    p_x = &a2->x;
    SetBrushOrgEx(v21, v52 - a2->x, y - a2->y, 0);
    SolidBrush = CreateSolidBrush(a2->rgbBk);
    v41 = SelectObject(v21, SolidBrush);
    BitBlt(v21, v52, y, a2->cx, a2->cy, hdc, v53, v54, 0xE20746u);
    v42 = SelectObject(v21, v41);
    DeleteObject(v42);
    SetBrushOrgEx(v21, 0, 0, 0);
    p_hdcDst = &a2->hdcDst;
    BitBlt(a2->hdcDst, a2->x, a2->y, a2->cx, a2->cy, v21, v52, y, 0xCC0020u);
    v29 = colorb;
    if ( colorb )
      CImageList::_ResetBkColor((CImageList *)((char *)this - 16), a2->i, a2->i, *((_DWORD *)this + 18));
LABEL_71:
    if ( (a2->fStyle & 0xF00) == 0 )
      break;
    v60 = (a2->fStyle >> 8) & 0xF;
    v43 = *((unsigned int *)this + v60 + 29);
    a2->i = v43;
    (*(void (__fastcall **)(CImageList *, __int64, int *))(*(_QWORD *)this + 120LL))(this, v43, v63);
    cx = *((_DWORD *)this + v60 + 74);
    a2->cx = cx;
    cy = *((_DWORD *)this + v60 + 89);
    a2->cy = cy;
    *p_x += *((_DWORD *)this + v60 + 44);
    *p_y += *((_DWORD *)this + v60 + 59);
    v9 = *((_DWORD *)this + v60 + 44) + a2->xBitmap + v63[0];
    v10 = *((_DWORD *)this + v60 + 59) + a2->yBitmap + v63[1];
    v53 = v9;
    v44 = a2->fStyle & 0x10;
    v63[0] = v9;
    v44 |= 1u;
    v54 = v10;
    a2->fStyle = v44;
    v45 = *((_DWORD *)this + v60 + 104) | v44;
    v63[1] = v10;
    a2->fStyle = v45;
    if ( cx <= 0 )
      break;
  }
  while ( cy > 0 );
  if ( !v29 && (GetDeviceCaps(v21, 38) & 0x100) != 0 )
  {
    StockObject = (HPALETTE)GetStockObject(15);
    SelectPalette(v21, StockObject, 1);
  }
  LeaveCriticalSection(&g_csDll);
  return 0;
}

```

## disassembly

```asm
0x1800806a0  mov     [rsp-8+arg_10], rbx
0x1800806a5  push    rbp
0x1800806a6  push    rsi
0x1800806a7  push    rdi
0x1800806a8  push    r12
0x1800806aa  push    r13
0x1800806ac  push    r14
0x1800806ae  push    r15
0x1800806b0  lea     rbp, [rsp-10h]
0x1800806b5  sub     rsp, 110h
0x1800806bc  mov     rax, cs:__security_cookie
0x1800806c3  xor     rax, rsp
0x1800806c6  mov     [rbp+40h+var_40], rax
0x1800806ca  mov     rdi, rdx
0x1800806cd  mov     rsi, rcx
0x1800806d0  xorps   xmm0, xmm0
0x1800806d3  lea     rcx, [rbp+40h+var_C0]; void *
0x1800806d7  xorps   xmm1, xmm1
0x1800806da  mov     ebx, 58h ; 'X'
0x1800806df  mov     r8d, ebx; Size
0x1800806e2  xor     edx, edx; Val
0x1800806e4  movups  xmmword ptr [rbp+40h+var_60], xmm0
0x1800806e8  movups  xmmword ptr [rbp+40h+x], xmm1
0x1800806ec  call    memset
0x1800806f1  cmp     [rdi], ebx
0x1800806f3  jz      short loc_18008072E
0x1800806f5  cmp     dword ptr [rdi], 48h ; 'H'
0x1800806f8  jnz     loc_180080FB9
0x1800806fe  movups  xmm0, xmmword ptr [rdi]
0x180080701  movups  xmm1, xmmword ptr [rdi+10h]
0x180080705  movaps  [rbp+40h+var_C0], xmm0
0x180080709  movups  xmm0, xmmword ptr [rdi+20h]
0x18008070d  mov     dword ptr [rbp+40h+var_C0], ebx
0x180080710  movaps  [rbp+40h+var_B0], xmm1
0x180080714  movups  xmm1, xmmword ptr [rdi+30h]
0x180080718  movaps  [rbp+40h+var_A0], xmm0
0x18008071c  movsd   xmm0, qword ptr [rdi+40h]
0x180080721  lea     rdi, [rbp+40h+var_C0]
0x180080725  movsd   [rbp+40h+var_80], xmm0
0x18008072a  movaps  [rbp+40h+var_90], xmm1
0x18008072e  mov     eax, [rdi+10h]
0x180080731  test    eax, eax
0x180080733  js      loc_180080FB9
0x180080739  cmp     eax, [rsi+28h]
0x18008073c  jge     loc_180080FB9
0x180080742  cmp     qword ptr [rsi+1E0h], 0
0x18008074a  jz      short loc_180080779
0x18008074c  mov     rcx, [rdi+18h]; hdc
0x180080750  call    cs:__imp_GetLayout
0x180080756  test    al, 1
0x180080758  jz      short loc_180080779
0x18008075a  mov     rcx, [rsi+1E0h]
0x180080761  mov     rdx, rdi
0x180080764  add     rcx, 10h
0x180080768  mov     rax, [rcx]
0x18008076b  mov     rax, [rax+40h]
0x18008076f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080774  jmp     loc_180080FBE
0x180080779  lea     rcx, g_csDll; lpCriticalSection
0x180080780  call    cs:__imp_EnterCriticalSection
0x180080786  mov     rax, [rsi]
0x180080789  lea     r8, [rbp+40h+var_60]
0x18008078d  mov     edx, [rdi+10h]
0x180080790  mov     rcx, rsi
0x180080793  mov     rax, [rax+78h]
0x180080797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008079c  mov     r12d, [rbp+40h+var_60]
0x1800807a0  add     r12d, [rdi+30h]
0x1800807a4  mov     r13d, [rbp+40h+var_60+4]
0x1800807a8  add     r13d, [rdi+34h]
0x1800807ac  mov     eax, [rdi+38h]
0x1800807af  mov     [rsp+140h+var_E8], r12d
0x1800807b4  mov     [rbp+40h+var_60], r12d
0x1800807b8  mov     [rsp+140h+var_E4], r13d
0x1800807bd  mov     [rbp+40h+var_60+4], r13d
0x1800807c1  cmp     eax, 0FF000000h
0x1800807c6  jnz     short loc_1800807CE
0x1800807c8  mov     eax, [rsi+48h]
0x1800807cb  mov     [rdi+38h], eax
0x1800807ce  cmp     eax, 0FFFFFFFFh
0x1800807d1  jnz     short loc_1800807D7
0x1800807d3  or      dword ptr [rdi+40h], 1
0x1800807d7  mov     edx, [rdi+28h]
0x1800807da  test    edx, edx
0x1800807dc  jnz     short loc_1800807E7
0x1800807de  mov     edx, [rbp+40h+var_60+8]
0x1800807e1  sub     edx, r12d; cx
0x1800807e4  mov     [rdi+28h], edx
0x1800807e7  mov     ecx, [rdi+2Ch]
0x1800807ea  test    ecx, ecx
0x1800807ec  jnz     short loc_1800807F7
0x1800807ee  mov     ecx, [rbp+40h+var_60+0Ch]
0x1800807f1  sub     ecx, r13d
0x1800807f4  mov     [rdi+2Ch], ecx
0x1800807f7  lea     r15, [rdi+18h]
0x1800807fb  mov     r8, [rsi+70h]
0x1800807ff  mov     eax, [rdi+40h]
0x180080802  mov     [rsp+140h+hdc], r8
0x180080807  test    al, 0Eh
0x180080809  jz      loc_1800809DD
0x18008080f  mov     r8d, ecx; cy
0x180080812  mov     rcx, [r15]; hdc
0x180080815  call    ?ImageList_GetWorkDC@@YAPEAUHDC__@@PEAU1@HH@Z; ImageList_GetWorkDC(HDC__ *,int,int)
0x18008081a  mov     ecx, [rdi+3Ch]
0x18008081d  mov     r14, rax
0x180080820  mov     [rsp+140h+var_EC], 0
0x180080828  mov     [rsp+140h+y], 0
0x180080830  cmp     ecx, 0FFFFFFFFh
0x180080833  jnz     loc_1800809A8
0x180080839  mov     rbx, [rsp+140h+hdc]
0x18008083e  test    rbx, rbx
0x180080841  jz      loc_1800809A8
0x180080847  mov     ecx, [rsi+40h]
0x18008084a  and     cl, 0FEh
0x18008084d  cmp     cl, 10h
0x180080850  jnz     short loc_1800808C9
0x180080852  test    [rdi+40h], cl
0x180080855  jnz     short loc_1800808C9
0x180080857  mov     eax, [rdi+24h]
0x18008085a  xor     r8d, r8d; y
0x18008085d  mov     r9d, [rdi+28h]; cx
0x180080861  xor     edx, edx; x
0x180080863  mov     [rsp+140h+rop], 0CC0020h; rop
0x18008086b  mov     rcx, r14; hdc
0x18008086e  mov     [rsp+140h+y1], eax; y1
0x180080872  mov     eax, [rdi+20h]
0x180080875  mov     [rsp+140h+x1], eax; x1
0x180080879  mov     rax, [r15]
0x18008087c  mov     [rsp+140h+hdcSrc], rax; hdcSrc
0x180080881  mov     eax, [rdi+2Ch]
0x180080884  mov     [rsp+140h+cy], eax; cy
0x180080888  call    cs:__imp_BitBlt
0x18008088e  mov     eax, [rdi+40h]
0x180080891  lea     r9, [rsi-10h]; struct CImageList *
0x180080895  mov     [rsp+140h+var_F8], eax; unsigned int
0x180080899  mov     rcx, r14; hdc
0x18008089c  mov     eax, [rdi+3Ch]
0x18008089f  mov     [rsp+140h+rop], eax; unsigned int
0x1800808a3  mov     eax, [rdi+2Ch]
0x1800808a6  mov     [rsp+140h+y1], eax; int
0x1800808aa  mov     eax, [rdi+28h]
0x1800808ad  mov     [rsp+140h+x1], eax; int
0x1800808b1  mov     eax, [rbp+40h+var_60+4]
0x1800808b4  mov     dword ptr [rsp+140h+hdcSrc], eax; int
0x1800808b8  mov     eax, [rbp+40h+var_60]
0x1800808bb  mov     [rsp+140h+cy], eax; int
0x1800808bf  call    ?ImageList_Blend16@@YAXPEAUHDC__@@HHPEAVCImageList@@HHHHKI@Z; ImageList_Blend16(HDC__ *,int,int,CImageList *,int,int,int,int,ulong,uint)
0x1800808c4  jmp     loc_180080993
0x1800808c9  mov     edx, [rsi+28h]
0x1800808cc  lea     r8, [rbp+40h+x]
0x1800808d0  mov     rcx, rsi
0x1800808d3  lea     eax, [rdx+1]
0x1800808d6  mov     [rsi+28h], eax
0x1800808d9  mov     rax, [rsi]
0x1800808dc  mov     rax, [rax+78h]
0x1800808e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800808e5  dec     dword ptr [rsi+28h]
0x1800808e8  test    eax, eax
0x1800808ea  jnz     short loc_1800808FE
0x1800808ec  mov     r12d, [rbp+40h+x]
0x1800808f0  mov     r13d, [rbp+40h+x+4]
0x1800808f4  mov     [rsp+140h+var_E8], r12d
0x1800808f9  mov     [rsp+140h+var_E4], r13d
0x1800808fe  mov     eax, [rbp+40h+var_60+4]
0x180080901  xor     r8d, r8d; y
0x180080904  mov     r9d, [rdi+28h]; cx
0x180080908  xor     edx, edx; x
0x18008090a  mov     [rsp+140h+rop], 0CC0020h; rop
0x180080912  mov     rcx, r14; hdc
0x180080915  mov     [rsp+140h+y1], eax; y1
0x180080919  mov     eax, [rbp+40h+var_60]
0x18008091c  mov     [rsp+140h+x1], eax; x1
0x180080920  mov     rax, [rsi+68h]
0x180080924  mov     [rsp+140h+hdcSrc], rax; hdcSrc
0x180080929  mov     eax, [rdi+2Ch]
0x18008092c  mov     [rsp+140h+cy], eax; cy
0x180080930  call    cs:__imp_BitBlt
0x180080936  mov     rdx, cs:g_hbrMonoDither; h
0x18008093d  mov     rcx, rbx; hdc
0x180080940  call    cs:__imp_SelectObject
0x180080946  mov     ecx, [rbp+40h+var_60+4]
0x180080949  mov     rbx, rax
0x18008094c  mov     r9d, [rdi+28h]; cx
0x180080950  mov     r8d, [rbp+40h+x+4]; y
0x180080954  mov     edx, [rbp+40h+x]; x
0x180080957  mov     [rsp+140h+rop], 0FC008Ah; rop
0x18008095f  mov     [rsp+140h+y1], ecx; y1
0x180080963  mov     ecx, [rbp+40h+var_60]
0x180080966  mov     [rsp+140h+x1], ecx; x1
0x18008096a  mov     rcx, [rsi+70h]
0x18008096e  mov     [rsp+140h+hdcSrc], rcx; hdcSrc
0x180080973  mov     ecx, [rdi+2Ch]
0x180080976  mov     [rsp+140h+cy], ecx; cy
0x18008097a  mov     rcx, [rsp+140h+hdc]; hdc
0x18008097f  call    cs:__imp_BitBlt
0x180080985  mov     rcx, [rsp+140h+hdc]; hdc
0x18008098a  mov     rdx, rbx; h
0x18008098d  call    cs:__imp_SelectObject
0x180080993  or      dword ptr [rdi+40h], 1
0x180080997  mov     edx, [rsp+140h+var_EC]
0x18008099b  mov     r9d, edx
0x18008099e  mov     eax, [rdi+40h]
0x1800809a1  mov     r8, [rsp+140h+hdc]
0x1800809a6  jmp     short loc_1800809F0
0x1800809a8  mov     eax, [rdi+40h]
0x1800809ab  lea     r9, [rsi-10h]; struct CImageList *
0x1800809af  mov     [rsp+140h+var_F8], eax; unsigned int
0x1800809b3  mov     eax, [rdi+2Ch]
0x1800809b6  mov     [rsp+140h+rop], ecx; unsigned int
0x1800809ba  mov     rcx, r14; hdc
0x1800809bd  mov     [rsp+140h+y1], eax; int
0x1800809c1  mov     eax, [rdi+28h]
0x1800809c4  mov     [rsp+140h+x1], eax; int
0x1800809c8  mov     eax, [rbp+40h+var_60+4]
0x1800809cb  mov     dword ptr [rsp+140h+hdcSrc], eax; int
0x1800809cf  mov     eax, [rbp+40h+var_60]
0x1800809d2  mov     [rsp+140h+cy], eax; int
0x1800809d6  call    ?ImageList_Blend@@YAXPEAUHDC__@@HHPEAVCImageList@@HHHHKI@Z; ImageList_Blend(HDC__ *,int,int,CImageList *,int,int,int,int,ulong,uint)
0x1800809db  jmp     short loc_180080997
0x1800809dd  mov     r14, [rsi+68h]
0x1800809e1  mov     edx, r12d
0x1800809e4  mov     [rsp+140h+var_EC], edx
0x1800809e8  mov     r9d, r13d
0x1800809eb  mov     [rsp+140h+y], r13d
0x1800809f0  mov     rcx, [rsi+68h]
0x1800809f4  xor     ebx, ebx
0x1800809f6  cmp     r14, rcx
0x1800809f9  mov     [rsp+140h+var_D0], rcx
0x1800809fe  setz    bl
0x180080a01  test    al, 10h
0x180080a03  jz      short loc_180080A41
0x180080a05  test    r8, r8
0x180080a08  jz      short loc_180080A41
0x180080a0a  test    al, 40h
0x180080a0c  jz      short loc_180080A13
0x180080a0e  mov     eax, [rdi+44h]
0x180080a11  jmp     short loc_180080A23
0x180080a13  and     al, 1
0x180080a15  neg     al
0x180080a17  sbb     eax, eax
0x180080a19  and     eax, 0FFBC00A6h
0x180080a1e  add     eax, 0CC0020h
0x180080a23  mov     [rsp+140h+rop], eax
0x180080a27  mov     eax, [rsp+140h+var_E4]
0x180080a2b  mov     [rsp+140h+y1], eax
0x180080a2f  mov     eax, [rsp+140h+var_E8]
0x180080a33  mov     [rsp+140h+x1], eax
0x180080a37  mov     [rsp+140h+hdcSrc], r8
0x180080a3c  jmp     loc_180080E95
0x180080a41  test    al, 20h
0x180080a43  jz      short loc_180080AC1
0x180080a45  mov     rcx, r14; hdc
0x180080a48  call    cs:__imp_GetBkColor
0x180080a4e  mov     edx, [rdi+38h]; color
0x180080a51  mov     [rsp+140h+color], eax
0x180080a55  cmp     edx, 0FF000000h
0x180080a5b  jz      short loc_180080A66
0x180080a5d  mov     rcx, r14; hdc
0x180080a60  call    cs:__imp_SetBkColor
0x180080a66  test    byte ptr [rdi+40h], 40h
0x180080a6a  jz      short loc_180080A71
0x180080a6c  mov     ecx, [rdi+44h]
0x180080a6f  jmp     short loc_180080A76
0x180080a71  mov     ecx, 0CC0020h
0x180080a76  mov     r8d, [rsp+140h+y]
0x180080a7b  lea     r13, [rdi+24h]
0x180080a7f  mov     edx, [rsp+140h+var_EC]
0x180080a83  lea     r12, [rdi+20h]
0x180080a87  mov     eax, [rdi+2Ch]
0x180080a8a  mov     r9d, [rdi+28h]; cx
0x180080a8e  mov     [rsp+140h+rop], ecx; rop
0x180080a92  mov     rcx, [r15]; hdc
0x180080a95  mov     [rsp+140h+y1], r8d; y1
0x180080a9a  mov     r8d, [r13+0]; y
0x180080a9e  mov     [rsp+140h+x1], edx; x1
0x180080aa2  mov     edx, [r12]; x
0x180080aa6  mov     [rsp+140h+hdcSrc], r14; hdcSrc
0x180080aab  mov     [rsp+140h+cy], eax; cy
0x180080aaf  call    cs:__imp_BitBlt
0x180080ab5  mov     edx, [rsp+140h+color]
0x180080ab9  mov     rcx, r14
0x180080abc  jmp     loc_180080CD1
0x180080ac1  test    al, 1
0x180080ac3  jz      loc_180080CDC
0x180080ac9  test    r8, r8
0x180080acc  jz      loc_180080CDC
0x180080ad2  mov     rcx, [r15]; hdc
0x180080ad5  xor     edx, edx; color
0x180080ad7  call    cs:__imp_SetTextColor
0x180080add  mov     rcx, [r15]; hdc
0x180080ae0  mov     edx, 0FFFFFFh; color
0x180080ae5  mov     [rsp+140h+color], eax
0x180080ae9  call    cs:__imp_SetBkColor
0x180080aef  mov     [rsp+140h+var_C8], eax
0x180080af3  cmp     r14, [rsp+140h+var_D0]
0x180080af8  jnz     loc_180080BEB
0x180080afe  mov     eax, [rsi+48h]
0x180080b01  cmp     eax, 0FFFFFFh
0x180080b06  jnz     short loc_180080B58
0x180080b08  mov     eax, [rsp+140h+var_E4]
  ... truncated ...
```
