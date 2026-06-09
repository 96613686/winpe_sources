# CReBar::_DrawBand(tagREBARBAND const *,HDC__ *)

- ea: `0x180051210`
- end: `0x1800518d3`
- name: `?_DrawBand@CReBar@@AEAAXPEBUtagREBARBAND@@PEAUHDC__@@@Z`
- size: `1731`
- prototype: `void __fastcall(CReBar *__hidden this, const struct tagREBARBAND *, HDC)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180050f38`

## callees

- `0x1800199c0`
- `0x180034a84`
- `0x180036850`
- `0x18004ce64`
- `0x180051210`
- `0x180052740`
- `0x180053ca0`
- `0x1800d9958`
- `0x1800ec654`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180051677`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800516ee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180051677`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800516ee`
- `GDI32!IntersectClipRect` at `0x1800513aa`
- `GDI32!IntersectClipRect` at `0x1800513aa`
- `GDI32!DeleteObject` at `0x18005137d`
- `GDI32!DeleteObject` at `0x18005151f`
- `GDI32!DeleteObject` at `0x18005137d`
- `GDI32!DeleteObject` at `0x18005151f`
- `GDI32!SetBkColor` at `0x1800512c9`
- `GDI32!SetBkColor` at `0x180051505`
- `GDI32!SetBkColor` at `0x1800512c9`
- `GDI32!SetBkColor` at `0x180051505`
- `GDI32!SetBkMode` at `0x1800512ef`
- `GDI32!SetBkMode` at `0x180051553`
- `GDI32!SetBkMode` at `0x1800512ef`
- `GDI32!SetBkMode` at `0x180051553`
- `GDI32!SetTextColor` at `0x1800512a3`
- `GDI32!SetTextColor` at `0x1800514f8`
- `GDI32!SetTextColor` at `0x1800512a3`
- `GDI32!SetTextColor` at `0x1800514f8`
- `GDI32!SelectObject` at `0x18005165e`
- `GDI32!SelectObject` at `0x18005169e`
- `GDI32!SelectObject` at `0x18005165e`
- `GDI32!SelectObject` at `0x18005169e`
- `GDI32!SelectClipRgn` at `0x180051511`
- `GDI32!SelectClipRgn` at `0x180051511`
- `GDI32!GetClipRgn` at `0x180051370`
- `GDI32!GetClipRgn` at `0x180051370`
- `GDI32!CreateRectRgnIndirect` at `0x180051361`
- `GDI32!CreateRectRgnIndirect` at `0x180051361`
- `USER32!DrawTextW` at `0x180051690`
- `USER32!DrawTextW` at `0x180051690`
- `USER32!GetSystemMetrics` at `0x18005148f`
- `USER32!GetSystemMetrics` at `0x180051822`
- `USER32!GetSystemMetrics` at `0x180051845`
- `USER32!GetSystemMetrics` at `0x18005148f`
- `USER32!GetSystemMetrics` at `0x180051822`
- `USER32!GetSystemMetrics` at `0x180051845`
- `USER32!GetSysColor` at `0x180051298`
- `USER32!GetSysColor` at `0x180051753`
- `USER32!GetSysColor` at `0x180051298`
- `USER32!GetSysColor` at `0x180051753`
- `USER32!GetSystemMetricsForDpi` at `0x1800515d6`
- `USER32!GetSystemMetricsForDpi` at `0x1800515d6`
- `UxTheme!DrawThemeText` at `0x180051727`
- `UxTheme!DrawThemeText` at `0x180051727`
- `UxTheme!DrawThemeBackground` at `0x18005143a`
- `UxTheme!DrawThemeBackground` at `0x18005143a`

## pseudocode

```c
void __fastcall CReBar::_DrawBand(CReBar *this, const struct tagREBARBAND *a2, HDC a3)
{
  int v3; // eax
  char v4; // r12
  int v8; // r14d
  COLORREF SysColor; // eax
  COLORREF BkColor; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // edx
  int v14; // eax
  int v15; // ecx
  int v16; // ecx
  HRGN v17; // rsi
  int v18; // r8d
  int v19; // edx
  int v20; // ecx
  int v21; // r9d
  void *v22; // r10
  LONG v23; // edx
  LONG v24; // ecx
  LONG v25; // r8d
  LONG v26; // r9d
  bool v27; // zf
  int v28; // eax
  int v29; // ecx
  int SystemMetrics; // eax
  int v31; // r14d
  LONG v32; // r8d
  __int16 v33; // ax
  int SystemMetricsForDpi; // eax
  _WORD *v35; // rax
  UINT dwTextFlags; // r14d
  int *v37; // r9
  int v38; // ecx
  int v39; // kr00_4
  LONG v40; // edx
  LONG v41; // ecx
  void *v42; // rdx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // edx
  LONG v48; // ecx
  LONG v49; // eax
  LONG v50; // ecx
  int v51; // [rsp+50h] [rbp-B0h]
  int v52; // [rsp+50h] [rbp-B0h]
  int v53; // [rsp+54h] [rbp-ACh]
  unsigned int h; // [rsp+58h] [rbp-A8h]
  HGDIOBJ ha; // [rsp+58h] [rbp-A8h]
  int mode; // [rsp+60h] [rbp-A0h]
  COLORREF color; // [rsp+64h] [rbp-9Ch]
  COLORREF v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v60[16]; // [rsp+78h] [rbp-88h] BYREF
  int v61; // [rsp+88h] [rbp-78h]
  HDC v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  int v65; // [rsp+A0h] [rbp-60h]
  int v66; // [rsp+A4h] [rbp-5Ch]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+B0h] [rbp-50h]
  __int64 v69; // [rsp+B8h] [rbp-48h]
  IMAGELISTDRAWPARAMS pimldp; // [rsp+C0h] [rbp-40h] BYREF
  RECT pRect; // [rsp+120h] [rbp+20h] BYREF
  RECT rect; // [rsp+130h] [rbp+30h] BYREF

  v3 = *((_DWORD *)this + 18);
  v4 = 0;
  v8 = v3 & 0x80;
  if ( (v3 & 0x80) == 0 || (h = 0, (v3 & 0x4000) != 0) )
    h = 1;
  v59 = 0;
  memset_0(v60, 0, 0x48u);
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    SysColor = *((_DWORD *)a2 + 1);
    if ( SysColor == -16777216 || SysColor == -1 && (SysColor = *((_DWORD *)this + 75), SysColor == -16777216) )
      SysColor = GetSysColor(18);
    color = SetTextColor(a3, SysColor);
    BkColor = *((_DWORD *)a2 + 2);
    if ( BkColor == -16777216 )
    {
      BkColor = GetSysColor(15);
    }
    else if ( BkColor == -1 )
    {
      BkColor = CReBar::_GetBkColor(this);
    }
    v58 = SetBkColor(a3, BkColor);
    if ( *((_QWORD *)a2 + 12) || (mode = 0, *((_QWORD *)this + 42)) )
      mode = SetBkMode(a3, 1);
    v11 = *((_DWORD *)a2 + 13);
    v12 = v11 + *((_DWORD *)a2 + 15);
    v13 = *((_DWORD *)a2 + 12);
    v14 = *(_DWORD *)a2 & 0x202;
    v67 = *((unsigned int *)a2 + 26);
    v69 = *((_QWORD *)a2 + 14);
    v62 = a3;
    v68 = 0;
    v64 = v11;
    v63 = v13;
    v66 = v12;
    if ( v14 == 512 && *((_DWORD *)a2 + 18) > *((_DWORD *)a2 + 8) )
    {
      SystemMetricsForDpi = GetSystemMetricsForDpi(2, *((unsigned int *)this + 27));
      v12 = v66;
      v15 = SystemMetricsForDpi;
      v11 = v64;
      v13 = v63;
    }
    else
    {
      v15 = 0;
    }
    v16 = *((_DWORD *)a2 + 17) - v15 - *((_DWORD *)a2 + 8) + v13;
    v65 = v16;
    if ( v8 )
    {
      v63 = v11;
      v64 = v13;
      v65 = v12;
      v66 = v16;
    }
    rect = 0;
    v17 = CreateRectRgnIndirect(&rect);
    if ( !GetClipRgn(a3, v17) )
    {
      DeleteObject(v17);
      v17 = 0;
    }
    if ( v8 )
    {
      v18 = *((_DWORD *)a2 + 12);
      v19 = *((_DWORD *)a2 + 13);
      v20 = *((_DWORD *)a2 + 14);
      v21 = *((_DWORD *)a2 + 15);
    }
    else
    {
      v18 = *((_DWORD *)a2 + 13);
      v19 = *((_DWORD *)a2 + 12);
      v20 = *((_DWORD *)a2 + 15);
      v21 = *((_DWORD *)a2 + 14);
    }
    IntersectClipRect(a3, v19, v18, v19 + v21, v18 + v20);
    v22 = (void *)*((_QWORD *)this + 42);
    if ( v22 )
    {
      v23 = *((_DWORD *)a2 + 12);
      v24 = *((_DWORD *)a2 + 13);
      v25 = v24 + *((_DWORD *)a2 + 15);
      pRect.left = v23;
      pRect.top = v24;
      v26 = v23 + *((_DWORD *)a2 + 14);
      pRect.bottom = v25;
      v27 = (*(_DWORD *)a2 & 0x20000000) == 0;
      pRect.right = v26;
      if ( v27 )
      {
        v23 -= *((_DWORD *)this + 57);
        v24 -= *((_DWORD *)this + 59);
        v26 += *((_DWORD *)this + 58);
        v25 += *((_DWORD *)this + 60);
        pRect.bottom = v25;
        pRect.left = v23;
        pRect.top = v24;
        pRect.right = v26;
      }
      if ( v8 )
      {
        pRect.left = v24;
        pRect.top = v23;
        pRect.right = v25;
        pRect.bottom = v26;
      }
      DrawThemeBackground(v22, a3, 3, 0, &pRect, 0);
    }
    if ( (*((_BYTE *)this + 76) & 0x20) != 0 )
    {
      v61 = 65537;
      v33 = CCSendNotify((char *)this + 56, 4294967284LL, &v59);
      v4 = v33;
      if ( (v33 & 0xFE01) != 0 )
      {
        v4 = 0;
      }
      else if ( (v33 & 4) != 0 )
      {
LABEL_36:
        if ( (v4 & 0x10) != 0 )
          CICustomDrawNotify((char *)this + 56, 65538, &v59);
        if ( *((_QWORD *)a2 + 12) || *((_QWORD *)this + 42) )
          SetBkMode(a3, mode);
        SetTextColor(a3, color);
        SetBkColor(a3, v58);
        SelectClipRgn(a3, v17);
        if ( v17 )
          DeleteObject(v17);
        return;
      }
    }
    if ( (*((_DWORD *)this + 18) & 0x4080) == 0x4080 )
      v28 = *((_DWORD *)a2 + 12) + (int)CReBar::_GetHeaderWidth(this, a2) / 2;
    else
      v28 = *((_DWORD *)a2 + 13) + *((_DWORD *)a2 + 15) / 2;
    v53 = v28;
    v51 = *((_DWORD *)a2 + 12);
    if ( (*(_DWORD *)a2 & 0x100) == 0 && ((*(_DWORD *)a2 & 0x80u) != 0 || (unsigned int)CReBar::_CanBandMove(this, a2)) )
      v51 = CReBar::_DrawGripper(this, a2, a3);
    if ( v8 )
      v29 = 46;
    else
      v29 = 45;
    SystemMetrics = GetSystemMetrics(v29);
    v31 = *((_DWORD *)a2 + 7);
    v32 = v51 + 2 * SystemMetrics;
    v52 = v32;
    if ( v31 != -1 )
    {
      memset_0(&pimldp, 0, sizeof(pimldp));
      v45 = *((_DWORD *)this + h + 54);
      pimldp.cbSize = 88;
      pimldp.i = v31;
      pimldp.hdcDst = a3;
      pimldp.himl = (HIMAGELIST)*((_QWORD *)this + 31);
      pimldp.rgbBk = -16777216;
      pimldp.rgbFg = -16777216;
      pimldp.fStyle = 1;
      pimldp.fState = 0;
      if ( h )
      {
        pimldp.y = v53 - v45 / 2;
        pimldp.x = v52;
        ImageList_DrawIndirect(&pimldp);
        v46 = GetSystemMetrics(45);
        v47 = *((_DWORD *)this + 54);
      }
      else
      {
        pimldp.x = v53 - v45 / 2;
        pimldp.y = v52;
        ImageList_DrawIndirect(&pimldp);
        v46 = GetSystemMetrics(46);
        v47 = *((_DWORD *)this + 55);
      }
      v32 = v46 + v47 + v52;
    }
    if ( (*(_DWORD *)a2 & 0x400) == 0 )
    {
      v35 = (_WORD *)*((_QWORD *)a2 + 2);
      if ( v35 )
      {
        if ( *v35 )
        {
          dwTextFlags = 0;
          v37 = (int *)((char *)this + 208);
          *(_QWORD *)&pRect.left = 0;
          if ( h )
          {
            v38 = *((_DWORD *)a2 + 6);
            v39 = *v37;
            pRect.left = v32;
            v40 = v53 - v39 / 2 - 1;
            pRect.top = v40;
            pRect.right = v32 + v38;
          }
          else
          {
            v48 = 0;
            v49 = *((_DWORD *)a2 + 15);
            if ( v53 - *((_DWORD *)a2 + 6) / 2 > 0 )
              v48 = v53 - *((_DWORD *)a2 + 6) / 2;
            v40 = v32;
            pRect.left = v48;
            v50 = *((_DWORD *)a2 + 6) + v48;
            pRect.top = v32;
            pRect.right = v50;
            if ( v50 > v49 )
            {
              pRect.right = v49;
              dwTextFlags = 32800;
            }
          }
          v41 = v40 + *v37;
          v42 = (void *)*((_QWORD *)this + 32);
          v27 = (*((_BYTE *)this + 104) & 2) == 0;
          pRect.bottom = v41;
          if ( !v27 )
            dwTextFlags = 0x100000;
          ha = SelectObject(a3, v42);
          if ( !*((_QWORD *)this + 42)
            || (v44 = lstrlenW(*((LPCWSTR *)a2 + 2)),
                DrawThemeText(*((HTHEME *)this + 42), a3, 0, 0, *((LPCWSTR *)a2 + 2), v44, dwTextFlags, 0, &pRect) < 0) )
          {
            v43 = lstrlenW(*((LPCWSTR *)a2 + 2));
            DrawTextW(a3, *((LPCWSTR *)a2 + 2), v43, &pRect, dwTextFlags);
          }
          SelectObject(a3, ha);
        }
      }
    }
    if ( (*(_DWORD *)a2 & 0x202) == 0x200 && *((_DWORD *)a2 + 18) > *((_DWORD *)a2 + 8) && *((_DWORD *)a2 + 30) )
      CReBar::_DrawChevron(this, a2, a3);
    goto LABEL_36;
  }
}

```

## disassembly

```asm
0x180051210  push    rbp
0x180051212  push    rbx
0x180051213  push    rdi
0x180051214  push    r12
0x180051216  push    r13
0x180051218  push    r14
0x18005121a  push    r15
0x18005121c  lea     rbp, [rsp-50h]
0x180051221  sub     rsp, 150h
0x180051228  mov     rax, cs:__security_cookie
0x18005122f  xor     rax, rsp
0x180051232  mov     [rbp+80h+var_40], rax
0x180051236  mov     eax, [rcx+48h]
0x180051239  xor     r12d, r12d
0x18005123c  mov     r14d, eax
0x18005123f  mov     rdi, r8
0x180051242  mov     rbx, rdx
0x180051245  mov     r15, rcx
0x180051248  and     r14d, 80h
0x18005124f  jnz     loc_18005173A
0x180051255  mov     dword ptr [rsp+180h+h], 1
0x18005125d  xor     edx, edx; Val
0x18005125f  mov     [rsp+180h+var_110], r12
0x180051264  mov     r8d, 48h ; 'H'; Size
0x18005126a  lea     rcx, [rsp+180h+var_108]; void *
0x18005126f  call    memset_0
0x180051274  test    byte ptr [rbx], 8
0x180051277  jnz     loc_18005152D
0x18005127d  mov     eax, [rbx+4]
0x180051280  mov     [rsp+180h+arg_18], rsi
0x180051288  cmp     eax, 0FF000000h
0x18005128d  jnz     loc_1800515A1
0x180051293  mov     ecx, 12h; nIndex
0x180051298  call    cs:__imp_GetSysColor
0x18005129e  mov     edx, eax; color
0x1800512a0  mov     rcx, rdi; hdc
0x1800512a3  call    cs:__imp_SetTextColor
0x1800512a9  mov     [rsp+180h+color], eax
0x1800512ad  mov     eax, [rbx+8]
0x1800512b0  cmp     eax, 0FF000000h
0x1800512b5  jz      loc_18005174E
0x1800512bb  cmp     eax, 0FFFFFFFFh
0x1800512be  jz      loc_180051594
0x1800512c4  mov     edx, eax; color
0x1800512c6  mov     rcx, rdi; hdc
0x1800512c9  call    cs:__imp_SetBkColor
0x1800512cf  mov     [rsp+180h+var_118], eax
0x1800512d3  cmp     [rbx+60h], r12
0x1800512d7  jnz     short loc_1800512E7
0x1800512d9  mov     [rsp+180h+mode], r12d
0x1800512de  cmp     [r15+150h], r12
0x1800512e5  jz      short loc_1800512F9
0x1800512e7  mov     edx, 1; mode
0x1800512ec  mov     rcx, rdi; hdc
0x1800512ef  call    cs:__imp_SetBkMode
0x1800512f5  mov     [rsp+180h+mode], eax
0x1800512f9  mov     ecx, [rbx+68h]
0x1800512fc  mov     r8d, [rbx+34h]
0x180051300  mov     r9d, [rbx+3Ch]
0x180051304  mov     eax, [rbx]
0x180051306  add     r9d, r8d
0x180051309  mov     edx, [rbx+30h]
0x18005130c  and     eax, 202h
0x180051311  mov     [rbp+80h+var_D8], rcx
0x180051315  mov     rcx, [rbx+70h]
0x180051319  mov     [rbp+80h+var_C8], rcx
0x18005131d  mov     [rbp+80h+var_F0], rdi
0x180051321  mov     [rbp+80h+var_D0], r12d
0x180051325  mov     [rbp+80h+var_E4], r8d
0x180051329  mov     [rbp+80h+var_E8], edx
0x18005132c  mov     [rbp+80h+var_DC], r9d
0x180051330  cmp     eax, 200h
0x180051335  jz      loc_1800515C1
0x18005133b  mov     ecx, r12d
0x18005133e  mov     eax, [rbx+44h]
0x180051341  sub     eax, ecx
0x180051343  sub     eax, [rbx+20h]
0x180051346  lea     ecx, [rax+rdx]
0x180051349  mov     [rbp+80h+var_E0], ecx
0x18005134c  test    r14d, r14d
0x18005134f  jnz     loc_18005175E
0x180051355  xorps   xmm0, xmm0
0x180051358  lea     rcx, [rbp+80h+rect]; lprect
0x18005135c  movdqu  xmmword ptr [rbp+80h+rect.left], xmm0
0x180051361  call    cs:__imp_CreateRectRgnIndirect
0x180051367  mov     rdx, rax; hrgn
0x18005136a  mov     rcx, rdi; hdc
0x18005136d  mov     rsi, rax
0x180051370  call    cs:__imp_GetClipRgn
0x180051376  test    eax, eax
0x180051378  jnz     short loc_180051386
0x18005137a  mov     rcx, rsi; ho
0x18005137d  call    cs:__imp_DeleteObject
0x180051383  mov     rsi, r12
0x180051386  test    r14d, r14d
0x180051389  jnz     loc_1800516D7
0x18005138f  mov     r8d, [rbx+34h]; top
0x180051393  mov     edx, [rbx+30h]; left
0x180051396  mov     ecx, [rbx+3Ch]
0x180051399  mov     r9d, [rbx+38h]
0x18005139d  add     ecx, r8d
0x1800513a0  add     r9d, edx; right
0x1800513a3  mov     [rsp+180h+bottom], ecx; bottom
0x1800513a7  mov     rcx, rdi; hdc
0x1800513aa  call    cs:__imp_IntersectClipRect
0x1800513b0  mov     r10, [r15+150h]
0x1800513b7  test    r10, r10
0x1800513ba  jz      loc_180051440
0x1800513c0  mov     edx, [rbx+30h]
0x1800513c3  mov     ecx, [rbx+34h]
0x1800513c6  mov     r8d, [rbx+3Ch]
0x1800513ca  add     r8d, ecx
0x1800513cd  mov     [rbp+80h+pRect.left], edx
0x1800513d0  mov     [rbp+80h+pRect.top], ecx
0x1800513d3  mov     r9d, [rbx+38h]
0x1800513d7  add     r9d, edx
0x1800513da  mov     [rbp+80h+pRect.bottom], r8d
0x1800513de  test    dword ptr [rbx], 20000000h
0x1800513e4  mov     [rbp+80h+pRect.right], r9d
0x1800513e8  jnz     short loc_180051414
0x1800513ea  sub     edx, [r15+0E4h]
0x1800513f1  sub     ecx, [r15+0ECh]
0x1800513f8  add     r9d, [r15+0E8h]
0x1800513ff  add     r8d, [r15+0F0h]
0x180051406  mov     [rbp+80h+pRect.bottom], r8d
0x18005140a  mov     [rbp+80h+pRect.left], edx
0x18005140d  mov     [rbp+80h+pRect.top], ecx
0x180051410  mov     [rbp+80h+pRect.right], r9d
0x180051414  test    r14d, r14d
0x180051417  jnz     loc_180051771
0x18005141d  lea     rax, [rbp+80h+pRect]
0x180051421  mov     [rsp+180h+pClipRect], r12; pClipRect
0x180051426  xor     r9d, r9d; iStateId
0x180051429  mov     qword ptr [rsp+180h+bottom], rax; pRect
0x18005142e  mov     r8d, 3; iPartId
0x180051434  mov     rdx, rdi; hdc
0x180051437  mov     rcx, r10; hTheme
0x18005143a  call    cs:__imp_DrawThemeBackground
0x180051440  test    byte ptr [r15+4Ch], 20h
0x180051445  jnz     loc_18005155B
0x18005144b  mov     eax, [r15+48h]
0x18005144f  and     eax, 4080h
0x180051454  cmp     eax, 4080h
0x180051459  jz      loc_180051784
0x18005145f  mov     eax, [rbx+3Ch]
0x180051462  cdq
0x180051463  sub     eax, edx
0x180051465  sar     eax, 1
0x180051467  add     eax, [rbx+34h]
0x18005146a  mov     ecx, [rbx]
0x18005146c  mov     [rsp+180h+var_12C], eax
0x180051470  mov     eax, [rbx+30h]
0x180051473  mov     [rsp+180h+var_130], eax
0x180051477  bt      ecx, 8
0x18005147b  jnb     loc_1800516A9
0x180051481  test    r14d, r14d
0x180051484  jnz     loc_18005179C
0x18005148a  mov     ecx, 2Dh ; '-'; nIndex
0x18005148f  call    cs:__imp_GetSystemMetrics
0x180051495  mov     ecx, [rsp+180h+var_130]
0x180051499  mov     r14d, [rbx+1Ch]
0x18005149d  lea     r8d, [rcx+rax*2]
0x1800514a1  mov     [rsp+180h+var_130], r8d
0x1800514a6  cmp     r14d, 0FFFFFFFFh
0x1800514aa  jnz     loc_1800517A6
0x1800514b0  test    dword ptr [rbx], 400h
0x1800514b6  jz      loc_1800515EE
0x1800514bc  mov     eax, [rbx]
0x1800514be  and     eax, 202h
0x1800514c3  cmp     eax, 200h
0x1800514c8  jnz     short loc_1800514D6
0x1800514ca  mov     eax, [rbx+20h]
0x1800514cd  cmp     [rbx+48h], eax
0x1800514d0  jg      loc_18005189E
0x1800514d6  test    r12b, 10h
0x1800514da  jnz     loc_1800518BB
0x1800514e0  cmp     qword ptr [rbx+60h], 0
0x1800514e5  jnz     short loc_18005154C
0x1800514e7  cmp     qword ptr [r15+150h], 0
0x1800514ef  jnz     short loc_18005154C
0x1800514f1  mov     edx, [rsp+180h+color]; color
0x1800514f5  mov     rcx, rdi; hdc
0x1800514f8  call    cs:__imp_SetTextColor
0x1800514fe  mov     edx, [rsp+180h+var_118]; color
0x180051502  mov     rcx, rdi; hdc
0x180051505  call    cs:__imp_SetBkColor
0x18005150b  mov     rdx, rsi; hrgn
0x18005150e  mov     rcx, rdi; hdc
0x180051511  call    cs:__imp_SelectClipRgn
0x180051517  test    rsi, rsi
0x18005151a  jz      short loc_180051525
0x18005151c  mov     rcx, rsi; ho
0x18005151f  call    cs:__imp_DeleteObject
0x180051525  mov     rsi, [rsp+180h+arg_18]
0x18005152d  mov     rcx, [rbp+80h+var_40]
0x180051531  xor     rcx, rsp; StackCookie
0x180051534  call    __security_check_cookie
0x180051539  add     rsp, 150h
0x180051540  pop     r15
0x180051542  pop     r14
0x180051544  pop     r13
0x180051546  pop     r12
0x180051548  pop     rdi
0x180051549  pop     rbx
0x18005154a  pop     rbp
0x18005154b  retn
0x18005154c  mov     edx, [rsp+180h+mode]; mode
0x180051550  mov     rcx, rdi; hdc
0x180051553  call    cs:__imp_SetBkMode
0x180051559  jmp     short loc_1800514F1
0x18005155b  lea     r8, [rsp+180h+var_110]
0x180051560  mov     [rbp+80h+var_F8], 10001h
0x180051567  mov     edx, 0FFFFFFF4h
0x18005156c  lea     rcx, [r15+38h]
0x180051570  call    CCSendNotify
0x180051575  mov     r12, rax
0x180051578  test    eax, 0FE01h
0x18005157d  jnz     short loc_18005158C
0x18005157f  test    al, 4
0x180051581  jz      loc_18005144B
0x180051587  jmp     loc_1800514D6
0x18005158c  xor     r12d, r12d
0x18005158f  jmp     loc_18005144B
0x180051594  mov     rcx, r15; this
0x180051597  call    ?_GetBkColor@CReBar@@AEAAKXZ; CReBar::_GetBkColor(void)
0x18005159c  jmp     loc_1800512C4
0x1800515a1  cmp     eax, 0FFFFFFFFh
0x1800515a4  jnz     loc_18005129E
0x1800515aa  mov     eax, [r15+12Ch]
0x1800515b1  cmp     eax, 0FF000000h
0x1800515b6  jnz     loc_18005129E
0x1800515bc  jmp     loc_180051293
0x1800515c1  mov     eax, [rbx+20h]
0x1800515c4  cmp     [rbx+48h], eax
0x1800515c7  jle     loc_18005133B
0x1800515cd  mov     edx, [r15+6Ch]
0x1800515d1  mov     ecx, 2
0x1800515d6  call    cs:__imp_GetSystemMetricsForDpi
0x1800515dc  mov     r9d, [rbp+80h+var_DC]
0x1800515e0  mov     ecx, eax
0x1800515e2  mov     r8d, [rbp+80h+var_E4]
0x1800515e6  mov     edx, [rbp+80h+var_E8]
0x1800515e9  jmp     loc_18005133E
0x1800515ee  mov     rax, [rbx+10h]
0x1800515f2  test    rax, rax
0x1800515f5  jz      loc_1800514BC
0x1800515fb  cmp     word ptr [rax], 0
0x1800515ff  jz      loc_1800514BC
0x180051605  xor     r14d, r14d
0x180051608  lea     r9, [r15+0D0h]
0x18005160f  mov     qword ptr [rbp+80h+pRect.left], r14
0x180051613  cmp     dword ptr [rsp+180h+h], r14d
0x180051618  jz      loc_180051861
0x18005161e  mov     eax, [r9]
0x180051621  mov     ecx, [rbx+18h]
0x180051624  cdq
0x180051625  sub     eax, edx
0x180051627  mov     [rbp+80h+pRect.left], r8d
0x18005162b  mov     edx, [rsp+180h+var_12C]
0x18005162f  sar     eax, 1
0x180051631  sub     edx, eax
0x180051633  dec     edx
0x180051635  add     ecx, r8d
0x180051638  mov     [rbp+80h+pRect.top], edx
0x18005163b  mov     [rbp+80h+pRect.right], ecx
0x18005163e  mov     ecx, [r9]
0x180051641  mov     eax, 100000h
0x180051646  add     ecx, edx
0x180051648  mov     rdx, [r15+100h]; h
0x18005164f  test    byte ptr [r15+68h], 2
0x180051654  mov     [rbp+80h+pRect.bottom], ecx
0x180051657  mov     rcx, rdi; hdc
0x18005165a  cmovnz  r14d, eax
0x18005165e  call    cs:__imp_SelectObject
0x180051664  cmp     qword ptr [r15+150h], 0
0x18005166c  mov     [rsp+180h+h], rax
0x180051671  jnz     short loc_1800516EA
0x180051673  mov     rcx, [rbx+10h]; lpString
0x180051677  call    cs:__imp_lstrlenW
0x18005167d  mov     rdx, [rbx+10h]; lpchText
0x180051681  lea     r9, [rbp+80h+pRect]; lprc
0x180051685  mov     r8d, eax; cchText
0x180051688  mov     [rsp+180h+bottom], r14d; format
0x18005168d  mov     rcx, rdi; hdc
0x180051690  call    cs:__imp_DrawTextW
0x180051696  mov     rdx, [rsp+180h+h]; h
0x18005169b  mov     rcx, rdi; hdc
0x18005169e  call    cs:__imp_SelectObject
0x1800516a4  jmp     loc_1800514BC
0x1800516a9  test    cl, cl
0x1800516ab  js      short loc_1800516C0
0x1800516ad  mov     rdx, rbx; struct tagREBARBAND *
0x1800516b0  mov     rcx, r15; this
0x1800516b3  call    ?_CanBandMove@CReBar@@AEAAHPEBUtagREBARBAND@@@Z; CReBar::_CanBandMove(tagREBARBAND const *)
0x1800516b8  test    eax, eax
0x1800516ba  jz      loc_180051481
0x1800516c0  mov     r8, rdi; HDC
0x1800516c3  mov     rdx, rbx; struct tagREBARBAND *
0x1800516c6  mov     rcx, r15; this
0x1800516c9  call    ?_DrawGripper@CReBar@@AEAAHPEBUtagREBARBAND@@PEAUHDC__@@@Z; CReBar::_DrawGripper(tagREBARBAND const *,HDC__ *)
  ... truncated ...
```
