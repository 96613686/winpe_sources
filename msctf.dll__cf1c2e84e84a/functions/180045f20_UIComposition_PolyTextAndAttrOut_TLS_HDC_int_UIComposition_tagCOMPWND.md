# UIComposition::PolyTextAndAttrOut(TLS *,HDC__ *,int,UIComposition::tagCOMPWND *)

- ea: `0x180045f20`
- end: `0x18004662e`
- name: `?PolyTextAndAttrOut@UIComposition@@AEAAJPEAVTLS@@PEAUHDC__@@HPEAUtagCOMPWND@1@@Z`
- size: `1806`
- prototype: `int(UIComposition *__hidden this, struct TLS *, HDC, int, struct UIComposition::tagCOMPWND *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180045b70`

## callees

- `0x1800139a4`
- `0x18001cc80`
- `0x180045f20`
- `0x180046634`
- `0x1800467bc`
- `0x18008fe88`
- `0x180106a60`

## import_xrefs

- `USER32!GetSysColor` at `0x180046011`
- `USER32!GetSysColor` at `0x180046031`
- `USER32!GetSysColor` at `0x18004613c`
- `USER32!GetSysColor` at `0x180046361`
- `USER32!GetSysColor` at `0x180046377`
- `USER32!GetSysColor` at `0x180046473`
- `USER32!GetSysColor` at `0x180046011`
- `USER32!GetSysColor` at `0x180046031`
- `USER32!GetSysColor` at `0x18004613c`
- `USER32!GetSysColor` at `0x180046361`
- `USER32!GetSysColor` at `0x180046377`
- `USER32!GetSysColor` at `0x180046473`
- `USER32!GetClientRect` at `0x18004633e`
- `USER32!GetClientRect` at `0x18004633e`
- `GDI32!GetTextColor` at `0x18004647e`
- `GDI32!GetTextColor` at `0x18004647e`
- `GDI32!MoveToEx` at `0x180046291`
- `GDI32!MoveToEx` at `0x180046291`
- `GDI32!DeleteObject` at `0x1800462be`
- `GDI32!DeleteObject` at `0x1800462be`
- `GDI32!LineTo` at `0x1800462a6`
- `GDI32!LineTo` at `0x1800462a6`
- `GDI32!SelectObject` at `0x1800461fd`
- `GDI32!SelectObject` at `0x1800462b5`
- `GDI32!SelectObject` at `0x1800461fd`
- `GDI32!SelectObject` at `0x1800462b5`
- `GDI32!GetTextExtentPoint32W` at `0x18004622c`
- `GDI32!GetTextExtentPoint32W` at `0x180046553`
- `GDI32!GetTextExtentPoint32W` at `0x18004658a`
- `GDI32!GetTextExtentPoint32W` at `0x18004622c`
- `GDI32!GetTextExtentPoint32W` at `0x180046553`
- `GDI32!GetTextExtentPoint32W` at `0x18004658a`
- `GDI32!SetBkColor` at `0x18004603c`
- `GDI32!SetBkColor` at `0x180046147`
- `GDI32!SetBkColor` at `0x18004636c`
- `GDI32!SetBkColor` at `0x18004603c`
- `GDI32!SetBkColor` at `0x180046147`
- `GDI32!SetBkColor` at `0x18004636c`
- `GDI32!SetTextColor` at `0x18004601c`
- `GDI32!SetTextColor` at `0x180046382`
- `GDI32!SetTextColor` at `0x18004601c`
- `GDI32!SetTextColor` at `0x180046382`
- `GDI32!ExtTextOutW` at `0x1800460fe`
- `GDI32!ExtTextOutW` at `0x1800461a9`
- `GDI32!ExtTextOutW` at `0x1800460fe`
- `GDI32!ExtTextOutW` at `0x1800461a9`
- `GDI32!BitBlt` at `0x1800465ec`
- `GDI32!BitBlt` at `0x1800465ec`
- `GDI32!ExtCreatePen` at `0x1800460ba`
- `GDI32!ExtCreatePen` at `0x1800460ba`
- `GDI32!Polyline` at `0x180046319`
- `GDI32!Polyline` at `0x180046319`

## string_xrefs

- `0x180045f83`: `UIComposition::PolyTextAndAttrOut. cic==NULL`

## pseudocode

```c
__int64 __fastcall UIComposition::PolyTextAndAttrOut(
        UIComposition *this,
        CicBridge **a2,
        HDC a3,
        int a4,
        struct UIComposition::tagCOMPWND *a5)
{
  CicBridge *v5; // r12
  __int64 *v6; // r13
  int v7; // r14d
  __int64 v9; // r8
  const struct tagPOLYTEXTW *v10; // rdi
  int v11; // ecx
  unsigned int *v12; // rdx
  unsigned int v13; // edx
  int v14; // ecx
  COLORREF cr; // edx
  int v16; // ecx
  COLORREF v17; // edx
  DWORD v18; // r12d
  DWORD v19; // r14d
  DWORD v20; // r15d
  HPEN v21; // rax
  int v22; // r14d
  HPEN v23; // r12
  LONG *p_left; // r12
  int v25; // r13d
  COLORREF v26; // eax
  int v27; // ecx
  int v28; // edx
  HGDIOBJ v30; // r13
  int n; // r8d
  const WCHAR *lpstr; // rdx
  LONG y; // r8d
  LONG cx; // eax
  LONG cy; // edx
  LONG bottom; // r14d
  LONG x; // r10d
  LONG right; // r15d
  int v39; // ecx
  int v40; // r9d
  struct tagPOLYTEXTW *v41; // rcx
  COLORREF SysColor; // eax
  COLORREF v43; // eax
  __int64 v44; // rdx
  COLORREF TextColor; // eax
  int v46; // edx
  signed int v47; // r15d
  int v48; // ecx
  LONG v49; // eax
  LONG left; // r9d
  int v51; // r8d
  int v52; // edx
  LONG v53; // r9d
  LONG v54; // ecx
  LONG top; // ecx
  int pstyle; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+54h] [rbp-ACh]
  struct tagSIZE v59; // [rsp+58h] [rbp-A8h] BYREF
  struct tagSIZE v60; // [rsp+60h] [rbp-A0h] BYREF
  int v61; // [rsp+68h] [rbp-98h]
  struct tagSIZE psizl; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+78h] [rbp-88h]
  int v64; // [rsp+7Ch] [rbp-84h]
  UIComposition *v65; // [rsp+80h] [rbp-80h]
  CicBridge *v66; // [rsp+88h] [rbp-78h]
  struct TF_DISPLAYATTRIBUTE nIndex; // [rsp+90h] [rbp-70h] BYREF
  struct tagPOLYTEXTW lpString; // [rsp+B8h] [rbp-48h] BYREF
  LOGBRUSH plbrush; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT Rect; // [rsp+100h] [rbp+0h] BYREF

  v5 = *a2;
  v6 = 0;
  v7 = a4;
  v65 = this;
  v66 = v5;
  if ( !v5 )
  {
    Internal_PolyTextOutW(a3, *((const struct tagPOLYTEXTW **)a5 + 3), *((_DWORD *)a5 + 8));
    CicTrace(2u, "UIComposition::PolyTextAndAttrOut. cic==NULL");
    return 0;
  }
  if ( !*((_DWORD *)a5 + 16) )
  {
    SysColor = GetSysColor(5);
    SetBkColor(a3, SysColor);
    v43 = GetSysColor(8);
    SetTextColor(a3, v43);
    Internal_PolyTextOutW(a3, *((const struct tagPOLYTEXTW **)a5 + 3), *((_DWORD *)a5 + 8));
    return 0;
  }
  v41 = *(struct tagPOLYTEXTW **)a5;
  Rect = 0;
  GetClientRect((HWND)v41, &Rect);
  v28 = *((_DWORD *)a5 + 16);
  v27 = 0;
  v61 = 0;
  if ( v28 > 0 )
  {
    while ( 1 )
    {
      v9 = *((_QWORD *)a5 + 3);
      v10 = (const struct tagPOLYTEXTW *)(v9 + v27 * *((_DWORD *)a5 + 9));
      v64 = v27 + 1;
      if ( v27 + 1 >= v28
        || (v44 = *((_DWORD *)a5 + 9) * (v27 + 1), !v7) && *(_DWORD *)(v44 + v9) < v10->rcl.right
        || (v58 = 0, v7) && *(_DWORD *)(v44 + v9 + 4) < v10->rcl.bottom )
      {
        v58 = 1;
      }
      v11 = *((_DWORD *)a5 + 17) * v27;
      memset(&nIndex, 0, sizeof(nIndex));
      v63 = 0;
      v12 = (unsigned int *)(*((_QWORD *)a5 + 7) + v11);
      if ( v12 )
        v13 = *v12;
      else
        v13 = 0;
      if ( (int)CicBridge::GetDisplayAttributeInfo(v5, v13, &nIndex) < 0 )
      {
        nIndex.crText = 0;
        nIndex.crLine.type = TF_CT_SYSCOLOR;
        v63 = 1;
        nIndex.crBk = 0;
        *(_QWORD *)&nIndex.lsStyle = 2;
        *(_QWORD *)&nIndex.crLine.nIndex = 8;
      }
      if ( nIndex.crText.type == TF_CT_SYSCOLOR )
        break;
      if ( nIndex.crText.type != TF_CT_COLORREF )
      {
        v14 = 8;
        goto LABEL_11;
      }
      cr = nIndex.crText.cr;
LABEL_12:
      SetTextColor(a3, cr);
      if ( nIndex.crBk.type == TF_CT_SYSCOLOR )
      {
        v16 = nIndex.crBk.nIndex;
LABEL_14:
        v17 = GetSysColor(v16);
        goto LABEL_15;
      }
      if ( nIndex.crBk.type != TF_CT_COLORREF )
      {
        v16 = 5;
        goto LABEL_14;
      }
      v17 = nIndex.crBk.cr;
LABEL_15:
      SetBkColor(a3, v17);
      v18 = 0;
      v19 = 0x10000;
      if ( nIndex.lsStyle )
      {
        if ( nIndex.lsStyle != TF_LS_SOLID )
        {
          if ( nIndex.lsStyle == TF_LS_DOT )
          {
            v19 = 65543;
            v6 = &qword_1801249D0;
            v18 = 2;
          }
          else if ( nIndex.lsStyle == TF_LS_DASH )
          {
            v19 = 65543;
            v6 = &qword_1801249D8;
            v18 = 2;
          }
        }
      }
      else
      {
        v19 = 5;
      }
      v20 = 1;
      *(_QWORD *)&plbrush.lbStyle = 0;
      plbrush.lbHatch = 0;
      if ( nIndex.fBoldLine )
        v20 = 2;
      switch ( nIndex.crLine.type )
      {
        case TF_CT_NONE:
          TextColor = GetTextColor(a3);
          goto LABEL_62;
        case TF_CT_SYSCOLOR:
          TextColor = GetSysColor(nIndex.crLine.nIndex);
          goto LABEL_62;
        case TF_CT_COLORREF:
          TextColor = nIndex.crLine.cr;
LABEL_62:
          plbrush.lbColor = TextColor;
          break;
      }
      v21 = ExtCreatePen(v19, v20, &plbrush, v18, (const DWORD *)v6);
      v22 = 0;
      v23 = v21;
      if ( v21 )
      {
        v30 = SelectObject(a3, v21);
        Internal_PolyTextOutW(a3, v10, 1);
        n = v10->n;
        lpstr = v10->lpstr;
        psizl = 0;
        GetTextExtentPoint32W(a3, lpstr, n, &psizl);
        y = v10->y;
        v60 = 0;
        v59 = 0;
        if ( a4 )
        {
          cx = psizl.cx;
          cy = psizl.cy;
          bottom = v10->rcl.bottom;
          x = v10->rcl.left + 1;
          right = x;
          psizl.cx = psizl.cy;
          psizl.cy = cx;
          v60.cx = x;
          v60.cy = y;
          v59.cx = x;
          v59.cy = bottom;
          if ( !v58 )
          {
            bottom -= cy / 4;
            v59.cy = bottom;
          }
        }
        else
        {
          y += psizl.cy;
          x = v10->x;
          right = v10->rcl.right;
          v60.cx = v10->x;
          v60.cy = y;
          v59.cx = right;
          if ( !v58 )
          {
            right -= psizl.cy / 4;
            v59.cx = right;
          }
          bottom = y;
          v59.cy = y;
        }
        MoveToEx(a3, x, y, 0);
        if ( nIndex.lsStyle == TF_LS_SQUIGGLE )
        {
          v22 = 0;
          *(_QWORD *)&lpString.x = &CStructArray<char>::`vftable';
          *(_QWORD *)&lpString.n = 0;
          lpString.lpstr = (LPCWSTR)0x800000000LL;
          lpString.uiFlags = 0;
          UIComposition::MakeSquiggleLine(v39, v60.cx, v59.cx, v40, pstyle, a4, (CVoidStructArray *)&lpString);
          Polyline(a3, *(const POINT **)&lpString.n, (int)lpString.lpstr);
          cicMemFree(*(_QWORD *)&lpString.n);
        }
        else
        {
          LineTo(a3, right, bottom);
          v22 = 0;
        }
        SelectObject(a3, v30);
        DeleteObject(v23);
        p_left = &v10->rcl.left;
      }
      else
      {
        p_left = &v10->rcl.left;
        ExtTextOutW(a3, v10->x, v10->y, v10->uiFlags, &v10->rcl, v10->lpstr, v10->n, v10->pdx);
      }
      v25 = v61;
      if ( v63
        && (v46 = *((_DWORD *)a5 + 33)) != 0
        && (v47 = v10->n, v48 = *((_DWORD *)a5 + 32), v47 + v61 > v48)
        && v61 <= v48 + v46 )
      {
        v60 = 0;
        v59 = 0;
        if ( v48 - v61 >= 0 )
          v22 = v48 - v61;
        if ( v48 - v22 - v61 + v46 <= v47 )
          v47 = v48 - v22 - v61 + v46;
        if ( v22 )
        {
          GetTextExtentPoint32W(a3, v10->lpstr, v22, &v60);
        }
        else
        {
          if ( (*((_BYTE *)a5 + 136) & 1) != 0 )
            v49 = *((_DWORD *)v65 + 152);
          else
            v49 = *((_DWORD *)v65 + 156);
          v60.cy = v49;
        }
        GetTextExtentPoint32W(a3, v10->lpstr, v47 + v22, &v59);
        v7 = a4;
        left = v10->rcl.left;
        if ( a4 )
        {
          top = v10->rcl.top;
          v52 = v10->rcl.left;
          v53 = v10->rcl.right;
          v51 = top + v60.cx;
          v54 = v59.cx + top;
        }
        else
        {
          v51 = v10->rcl.top;
          v52 = left + v60.cx;
          v53 = v59.cx + left;
          v54 = v10->rcl.bottom;
        }
        BitBlt(a3, v52, v51, v53 - v52, v54 - v51, a3, v52, v51, 0x550009u);
      }
      else
      {
        v7 = a4;
      }
      if ( v58 )
      {
        memset(&lpString, 0, sizeof(lpString));
        v26 = GetSysColor(5);
        SetBkColor(a3, v26);
        lpString.uiFlags = 2;
        if ( v7 )
        {
          lpString.rcl.top = v10->rcl.bottom;
          lpString.rcl.bottom = Rect.bottom;
          lpString.rcl.left = *p_left;
          lpString.rcl.right = v10->x;
          Internal_PolyTextOutW(a3, &lpString, 1);
        }
        else
        {
          lpString.rcl.top = v10->y;
          lpString.rcl.bottom = v10->rcl.bottom;
          lpString.rcl.left = p_left[2];
          lpString.rcl.right = Rect.right;
          ExtTextOutW(a3, lpString.x, lpString.y, 2u, &lpString.rcl, lpString.lpstr, lpString.n, lpString.pdx);
        }
      }
      v27 = v64;
      v28 = *((_DWORD *)a5 + 16);
      v5 = v66;
      v61 = v10->n + v25;
      v6 = 0;
      if ( v64 >= v28 )
        return 0;
    }
    v14 = nIndex.crText.nIndex;
LABEL_11:
    cr = GetSysColor(v14);
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180045f20  mov     [rsp-8+arg_18], rbx
0x180045f25  push    rbp
0x180045f26  push    rsi
0x180045f27  push    rdi
0x180045f28  push    r12
0x180045f2a  push    r13
0x180045f2c  push    r14
0x180045f2e  push    r15
0x180045f30  lea     rbp, [rsp-20h]
0x180045f35  sub     rsp, 120h
0x180045f3c  mov     rax, cs:__security_cookie
0x180045f43  xor     rax, rsp
0x180045f46  mov     [rbp+50h+var_40], rax
0x180045f4a  mov     r12, [rdx]
0x180045f4d  xor     r13d, r13d
0x180045f50  mov     rsi, [rbp+50h+arg_20]
0x180045f57  mov     r14d, r9d
0x180045f5a  mov     [rsp+150h+var_100], r9d
0x180045f5f  mov     rbx, r8
0x180045f62  mov     [rbp+50h+var_D0], rcx
0x180045f66  mov     [rbp+50h+var_C8], r12
0x180045f6a  test    r12, r12
0x180045f6d  jnz     loc_18004632A
0x180045f73  mov     r8d, [rsi+20h]; int
0x180045f77  mov     rcx, rbx; hdc
0x180045f7a  mov     rdx, [rsi+18h]; struct tagPOLYTEXTW *
0x180045f7e  call    ?Internal_PolyTextOutW@@YAHPEAUHDC__@@PEBUtagPOLYTEXTW@@H@Z; Internal_PolyTextOutW(HDC__ *,tagPOLYTEXTW const *,int)
0x180045f83  lea     rdx, aUicompositionP; "UIComposition::PolyTextAndAttrOut. cic="...
0x180045f8a  lea     ecx, [r12+2]; unsigned int
0x180045f8f  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180045f94  jmp     loc_1800461D1
0x180045f99  mov     r15d, 2
0x180045f9f  mov     eax, [rsi+24h]
0x180045fa2  mov     r8, [rsi+18h]
0x180045fa6  imul    eax, ecx
0x180045fa9  movsxd  rdi, eax
0x180045fac  lea     eax, [rcx+1]
0x180045faf  add     rdi, r8
0x180045fb2  mov     [rsp+150h+var_D4], eax
0x180045fb6  cmp     eax, edx
0x180045fb8  jl      loc_18004639D
0x180045fbe  mov     [rsp+150h+var_FC], 1
0x180045fc6  imul    ecx, [rsi+44h]
0x180045fca  xor     eax, eax
0x180045fcc  xorps   xmm0, xmm0
0x180045fcf  mov     [rbp+50h+var_A0], eax
0x180045fd2  movups  xmmword ptr [rbp+50h+nIndex], xmm0
0x180045fd6  mov     [rsp+150h+var_D8], r13d
0x180045fdb  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x180045fdf  movsxd  rdx, ecx
0x180045fe2  add     rdx, [rsi+38h]
0x180045fe6  jz      loc_1800463D7
0x180045fec  mov     edx, [rdx]; unsigned int
0x180045fee  lea     r8, [rbp+50h+nIndex]; struct TF_DISPLAYATTRIBUTE *
0x180045ff2  mov     rcx, r12; this
0x180045ff5  call    ?GetDisplayAttributeInfo@CicBridge@@QEAAJKPEAUTF_DISPLAYATTRIBUTE@@@Z; CicBridge::GetDisplayAttributeInfo(ulong,TF_DISPLAYATTRIBUTE *)
0x180045ffa  test    eax, eax
0x180045ffc  js      loc_1800463DF
0x180046002  mov     ecx, [rbp+50h+nIndex]
0x180046005  sub     ecx, 1
0x180046008  jnz     loc_180046408
0x18004600e  mov     ecx, [rbp+50h+nIndex+4]; nIndex
0x180046011  call    cs:__imp_GetSysColor
0x180046017  mov     edx, eax; color
0x180046019  mov     rcx, rbx; hdc
0x18004601c  call    cs:__imp_SetTextColor
0x180046022  mov     ecx, [rbp+50h+nIndex+8]
0x180046025  sub     ecx, 1
0x180046028  jnz     loc_18004641F
0x18004602e  mov     ecx, [rbp+50h+nIndex+0Ch]; nIndex
0x180046031  call    cs:__imp_GetSysColor
0x180046037  mov     edx, eax; color
0x180046039  mov     rcx, rbx; hdc
0x18004603c  call    cs:__imp_SetBkColor
0x180046042  mov     ecx, [rbp+50h+var_B0]
0x180046045  xor     edx, edx
0x180046047  mov     r8d, 10000h
0x18004604d  mov     r12d, r13d
0x180046050  mov     r14d, r8d
0x180046053  test    ecx, ecx
0x180046055  jz      loc_180046460
0x18004605b  sub     ecx, 1
0x18004605e  jz      short loc_180046072
0x180046060  sub     ecx, 1
0x180046063  jz      loc_18004644B
0x180046069  sub     ecx, 1
0x18004606c  jz      loc_180046436
0x180046072  cmp     [rbp+50h+var_B0+4], edx
0x180046075  mov     r15d, 1
0x18004607b  mov     ecx, [rbp+50h+var_B0+8]
0x18004607e  mov     qword ptr [rbp+50h+plbrush.lbStyle], rdx
0x180046082  mov     [rbp+50h+plbrush.lbHatch], rdx
0x180046086  lea     eax, [r15+1]
0x18004608a  cmovnz  r15d, eax
0x18004608e  test    ecx, ecx
0x180046090  jz      loc_18004647B
0x180046096  sub     ecx, 1
0x180046099  jz      loc_180046470
0x18004609f  cmp     ecx, 1
0x1800460a2  jz      loc_18004646B
0x1800460a8  mov     r9d, r12d; cStyle
0x1800460ab  mov     [rsp+150h+pstyle], r13; int
0x1800460b0  lea     r8, [rbp+50h+plbrush]; plbrush
0x1800460b4  mov     edx, r15d; cWidth
0x1800460b7  mov     ecx, r14d; iPenStyle
0x1800460ba  call    cs:__imp_ExtCreatePen
0x1800460c0  xor     r14d, r14d
0x1800460c3  mov     rcx, rbx; hdc
0x1800460c6  mov     r12, rax
0x1800460c9  test    rax, rax
0x1800460cc  jnz     loc_1800461FA
0x1800460d2  mov     rax, [rdi+30h]
0x1800460d6  lea     r12, [rdi+1Ch]
0x1800460da  mov     r9d, [rdi+18h]; options
0x1800460de  mov     r8d, [rdi+4]; y
0x1800460e2  mov     edx, [rdi]; x
0x1800460e4  mov     [rsp+150h+lpDx], rax; lpDx
0x1800460e9  mov     eax, [rdi+8]
0x1800460ec  mov     [rsp+150h+c], eax; c
0x1800460f0  mov     rax, [rdi+10h]
0x1800460f4  mov     [rsp+150h+lpString], rax; lpString
0x1800460f9  mov     [rsp+150h+pstyle], r12; lprect
0x1800460fe  call    cs:__imp_ExtTextOutW
0x180046104  mov     r13d, [rsp+150h+var_E8]
0x180046109  cmp     [rsp+150h+var_D8], r14d
0x18004610e  jnz     loc_1800464E4
0x180046114  mov     r14d, [rsp+150h+var_100]
0x180046119  cmp     [rsp+150h+var_FC], 0
0x18004611e  jz      loc_180046623
0x180046124  xorps   xmm0, xmm0
0x180046127  xor     eax, eax
0x180046129  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18004612d  mov     [rbp+50h+var_68], rax
0x180046131  movups  xmmword ptr [rbp+50h+rect.left], xmm0
0x180046135  lea     ecx, [rax+5]; nIndex
0x180046138  movups  [rbp+50h+var_78], xmm0
0x18004613c  call    cs:__imp_GetSysColor
0x180046142  mov     edx, eax; color
0x180046144  mov     rcx, rbx; hdc
0x180046147  call    cs:__imp_SetBkColor
0x18004614d  mov     r15d, 2
0x180046153  mov     rcx, rbx; hdc
0x180046156  mov     [rbp+50h+rect.right], r15d
0x18004615a  test    r14d, r14d
0x18004615d  jnz     loc_1800465F7
0x180046163  mov     eax, [rdi+4]
0x180046166  mov     r9d, r15d; options
0x180046169  mov     r8d, [rbp+50h+var_98+4]; y
0x18004616d  mov     edx, [rbp+50h+var_98]; x
0x180046170  mov     dword ptr [rbp+50h+var_78], eax
0x180046173  mov     eax, [rdi+28h]
0x180046176  mov     dword ptr [rbp+50h+var_78+8], eax
0x180046179  mov     eax, [r12+8]
0x18004617e  mov     [rbp+50h+rect.bottom], eax
0x180046181  mov     eax, [rbp+50h+Rect.right]
0x180046184  mov     dword ptr [rbp+50h+var_78+4], eax
0x180046187  mov     rax, [rbp+50h+var_68]
0x18004618b  mov     [rsp+150h+lpDx], rax; lpDx
0x180046190  mov     eax, [rbp+50h+var_98+8]
0x180046193  mov     [rsp+150h+c], eax; c
0x180046197  mov     rax, qword ptr [rbp+50h+rect.left]
0x18004619b  mov     [rsp+150h+lpString], rax; lpString
0x1800461a0  lea     rax, [rbp+50h+rect.bottom]
0x1800461a4  mov     [rsp+150h+pstyle], rax; lprect
0x1800461a9  call    cs:__imp_ExtTextOutW
0x1800461af  add     r13d, [rdi+8]
0x1800461b3  mov     ecx, [rsp+150h+var_D4]
0x1800461b7  mov     edx, [rsi+40h]
0x1800461ba  mov     r12, [rbp+50h+var_C8]
0x1800461be  mov     [rsp+150h+var_E8], r13d
0x1800461c3  mov     r13d, 0
0x1800461c9  cmp     ecx, edx
0x1800461cb  jl      loc_180045F9F
0x1800461d1  xor     eax, eax
0x1800461d3  mov     rcx, [rbp+50h+var_40]
0x1800461d7  xor     rcx, rsp; StackCookie
0x1800461da  call    __security_check_cookie
0x1800461df  mov     rbx, [rsp+150h+arg_18]
0x1800461e7  add     rsp, 120h
0x1800461ee  pop     r15
0x1800461f0  pop     r14
0x1800461f2  pop     r13
0x1800461f4  pop     r12
0x1800461f6  pop     rdi
0x1800461f7  pop     rsi
0x1800461f8  pop     rbp
0x1800461f9  retn
0x1800461fa  mov     rdx, r12; h
0x1800461fd  call    cs:__imp_SelectObject
0x180046203  mov     r8d, 1; int
0x180046209  mov     rdx, rdi; struct tagPOLYTEXTW *
0x18004620c  mov     rcx, rbx; hdc
0x18004620f  mov     r13, rax
0x180046212  call    ?Internal_PolyTextOutW@@YAHPEAUHDC__@@PEBUtagPOLYTEXTW@@H@Z; Internal_PolyTextOutW(HDC__ *,tagPOLYTEXTW const *,int)
0x180046217  mov     r8d, [rdi+8]; c
0x18004621b  lea     r9, [rsp+150h+psizl]; psizl
0x180046220  mov     rdx, [rdi+10h]; lpString
0x180046224  mov     rcx, rbx; hdc
0x180046227  mov     qword ptr [rsp+150h+psizl.cx], r14
0x18004622c  call    cs:__imp_GetTextExtentPoint32W
0x180046232  mov     r8d, [rdi+4]; y
0x180046236  mov     qword ptr [rsp+150h+var_F0.cx], r14
0x18004623b  mov     qword ptr [rsp+150h+var_F8.cx], r14
0x180046240  cmp     [rsp+150h+var_100], r14d
0x180046245  jz      loc_18004648C
0x18004624b  mov     eax, [rsp+150h+psizl.cx]
0x18004624f  mov     edx, [rsp+150h+psizl.cy]
0x180046253  mov     r10d, [rdi+1Ch]
0x180046257  mov     r14d, [rdi+28h]
0x18004625b  inc     r10d
0x18004625e  cmp     [rsp+150h+var_FC], 0
0x180046263  mov     r15d, r10d
0x180046266  mov     [rsp+150h+psizl.cx], edx
0x18004626a  mov     [rsp+150h+psizl.cy], eax
0x18004626e  mov     [rsp+150h+var_F0.cx], r10d
0x180046273  mov     [rsp+150h+var_F0.cy], r8d
0x180046278  mov     [rsp+150h+var_F8.cx], r10d
0x18004627d  mov     [rsp+150h+var_F8.cy], r14d
0x180046282  jz      loc_1800464CD
0x180046288  xor     r9d, r9d; lppt
0x18004628b  mov     edx, r10d; x
0x18004628e  mov     rcx, rbx; hdc
0x180046291  call    cs:__imp_MoveToEx
0x180046297  cmp     [rbp+50h+var_B0], 4
0x18004629b  jz      short loc_1800462CD
0x18004629d  mov     r8d, r14d; y
0x1800462a0  mov     edx, r15d; x
0x1800462a3  mov     rcx, rbx; hdc
0x1800462a6  call    cs:__imp_LineTo
0x1800462ac  xor     r14d, r14d
0x1800462af  mov     rdx, r13; h
0x1800462b2  mov     rcx, rbx; hdc
0x1800462b5  call    cs:__imp_SelectObject
0x1800462bb  mov     rcx, r12; ho
0x1800462be  call    cs:__imp_DeleteObject
0x1800462c4  lea     r12, [rdi+1Ch]
0x1800462c8  jmp     loc_180046104
0x1800462cd  mov     r8, qword ptr [rsp+150h+var_F8.cx]; int
0x1800462d2  lea     rax, ??_7?$CStructArray@D@@6B@; const CStructArray<char>::`vftable'
0x1800462d9  mov     rdx, qword ptr [rsp+150h+var_F0.cx]; int
0x1800462de  xor     r14d, r14d
0x1800462e1  mov     qword ptr [rbp+50h+var_98], rax
0x1800462e5  lea     rax, [rbp+50h+var_98]
0x1800462e9  mov     qword ptr [rsp+150h+c], rax; CVoidStructArray *
0x1800462ee  mov     eax, [rsp+150h+var_100]
0x1800462f2  mov     dword ptr [rsp+150h+lpString], eax; int
0x1800462f6  mov     qword ptr [rbp+50h+var_98+8], r14
0x1800462fa  mov     [rbp+50h+rect.top], 8
0x180046301  mov     [rbp+50h+rect.left], r14d
0x180046305  mov     [rbp+50h+rect.right], r14d
0x180046309  call    ?MakeSquiggleLine@UIComposition@@AEAAJUtagPOINT@@0HHHPEAV?$CStructArray@UtagPOINT@@@@@Z; UIComposition::MakeSquiggleLine(tagPOINT,tagPOINT,int,int,int,CStructArray<tagPOINT> *)
0x18004630e  mov     r8d, [rbp+50h+rect.left]; cpt
0x180046312  mov     rcx, rbx; hdc
0x180046315  mov     rdx, qword ptr [rbp+50h+var_98+8]; apt
0x180046319  call    cs:__imp_Polyline
0x18004631f  mov     rcx, qword ptr [rbp+50h+var_98+8]
0x180046323  call    cicMemFree
0x180046328  jmp     short loc_1800462AF
0x18004632a  cmp     [rsi+40h], r13d
0x18004632e  jz      short loc_18004635C
0x180046330  mov     rcx, [rsi]; hWnd
0x180046333  lea     rdx, [rbp+50h+Rect]; lpRect
0x180046337  xorps   xmm0, xmm0
0x18004633a  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x18004633e  call    cs:__imp_GetClientRect
0x180046344  mov     edx, [rsi+40h]
0x180046347  mov     ecx, r13d
0x18004634a  mov     [rsp+150h+var_E8], r13d
0x18004634f  test    edx, edx
0x180046351  jle     loc_1800461D1
0x180046357  jmp     loc_180045F99
0x18004635c  mov     ecx, 5; nIndex
0x180046361  call    cs:__imp_GetSysColor
0x180046367  mov     edx, eax; color
0x180046369  mov     rcx, rbx; hdc
0x18004636c  call    cs:__imp_SetBkColor
0x180046372  mov     ecx, 8; nIndex
0x180046377  call    cs:__imp_GetSysColor
0x18004637d  mov     edx, eax; color
0x18004637f  mov     rcx, rbx; hdc
0x180046382  call    cs:__imp_SetTextColor
0x180046388  mov     r8d, [rsi+20h]; int
0x18004638c  mov     rcx, rbx; hdc
0x18004638f  mov     rdx, [rsi+18h]; struct tagPOLYTEXTW *
0x180046393  call    ?Internal_PolyTextOutW@@YAHPEAUHDC__@@PEBUtagPOLYTEXTW@@H@Z; Internal_PolyTextOutW(HDC__ *,tagPOLYTEXTW const *,int)
0x180046398  jmp     loc_1800461D1
0x18004639d  imul    eax, [rsi+24h]
0x1800463a1  movsxd  rdx, eax
0x1800463a4  test    r14d, r14d
0x1800463a7  jnz     short loc_1800463B6
0x1800463a9  mov     eax, [rdi+24h]
0x1800463ac  cmp     [rdx+r8], eax
0x1800463b0  jl      loc_180045FBE
0x1800463b6  mov     [rsp+150h+var_FC], r13d
0x1800463bb  test    r14d, r14d
0x1800463be  jz      loc_180045FC6
0x1800463c4  mov     eax, [rdi+28h]
0x1800463c7  cmp     [rdx+r8+4], eax
0x1800463cc  jge     loc_180045FC6
0x1800463d2  jmp     loc_180045FBE
  ... truncated ...
```
