# CCalendar::_PaintCalendar(HDC__ *,tagRECT const *,int,CALDATETIME const *)

- ea: `0x18015734c`
- end: `0x180157cb8`
- name: `?_PaintCalendar@CCalendar@@AEAAXPEAUHDC__@@PEBUtagRECT@@HPEBUCALDATETIME@@@Z`
- size: `2412`
- prototype: `void __usercall(CCalendar *__hidden this@<rcx>, HDC hdc@<rdx>, const struct tagRECT *@<r8>, int@<r9d>, const struct CALDATETIME *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18010d6d4`

## callees

- `0x1800cef08`
- `0x1800cf5fc`
- `0x1800cf714`
- `0x1800cf9e8`
- `0x1800e30d0`
- `0x1800f490c`
- `0x1800fc86c`
- `0x1800fcebc`
- `0x1800fcf58`
- `0x1800fcf84`
- `0x1800fd274`
- `0x18010474c`
- `0x180114520`
- `0x1801554d4`
- `0x1801571c4`
- `0x18015734c`
- `0x18015fd34`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180157794`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18015795e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180157794`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18015795e`
- `GDI32!SetTextColor` at `0x1801576b4`
- `GDI32!SetTextColor` at `0x1801576b4`
- `GDI32!RectVisible` at `0x1801574a6`
- `GDI32!RectVisible` at `0x180157531`
- `GDI32!RectVisible` at `0x1801575a9`
- `GDI32!RectVisible` at `0x1801576eb`
- `GDI32!RectVisible` at `0x180157802`
- `GDI32!RectVisible` at `0x1801578c9`
- `GDI32!RectVisible` at `0x180157a0b`
- `GDI32!RectVisible` at `0x180157a66`
- `GDI32!RectVisible` at `0x180157bc6`
- `GDI32!RectVisible` at `0x1801574a6`
- `GDI32!RectVisible` at `0x180157531`
- `GDI32!RectVisible` at `0x1801575a9`
- `GDI32!RectVisible` at `0x1801576eb`
- `GDI32!RectVisible` at `0x180157802`
- `GDI32!RectVisible` at `0x1801578c9`
- `GDI32!RectVisible` at `0x180157a0b`
- `GDI32!RectVisible` at `0x180157a66`
- `GDI32!RectVisible` at `0x180157bc6`
- `GDI32!SelectObject` at `0x180157463`
- `GDI32!SelectObject` at `0x18015766f`
- `GDI32!SelectObject` at `0x180157692`
- `GDI32!SelectObject` at `0x180157c8b`
- `GDI32!SelectObject` at `0x180157463`
- `GDI32!SelectObject` at `0x18015766f`
- `GDI32!SelectObject` at `0x180157692`
- `GDI32!SelectObject` at `0x180157c8b`
- `GDI32!MoveToEx` at `0x180157578`
- `GDI32!MoveToEx` at `0x180157a22`
- `GDI32!MoveToEx` at `0x180157578`
- `GDI32!MoveToEx` at `0x180157a22`
- `GDI32!LineTo` at `0x180157588`
- `GDI32!LineTo` at `0x180157a32`
- `GDI32!LineTo` at `0x180157588`
- `GDI32!LineTo` at `0x180157a32`
- `GDI32!GetStockObject` at `0x180157663`
- `GDI32!GetStockObject` at `0x180157663`
- `USER32!DrawTextW` at `0x1801577b0`
- `USER32!DrawTextW` at `0x18015797a`
- `USER32!DrawTextW` at `0x1801577b0`
- `USER32!DrawTextW` at `0x18015797a`
- `USER32!FillRect` at `0x180157686`
- `USER32!FillRect` at `0x180157686`
- `USER32!OffsetRect` at `0x180157524`
- `USER32!OffsetRect` at `0x1801576de`
- `USER32!OffsetRect` at `0x1801577c3`
- `USER32!OffsetRect` at `0x1801577f5`
- `USER32!OffsetRect` at `0x18015787b`
- `USER32!OffsetRect` at `0x1801579c8`
- `USER32!OffsetRect` at `0x180157a59`
- `USER32!OffsetRect` at `0x180157b36`
- `USER32!OffsetRect` at `0x180157b56`
- `USER32!OffsetRect` at `0x180157c30`
- `USER32!OffsetRect` at `0x180157c57`
- `USER32!OffsetRect` at `0x180157524`
- `USER32!OffsetRect` at `0x1801576de`
- `USER32!OffsetRect` at `0x1801577c3`
- `USER32!OffsetRect` at `0x1801577f5`
- `USER32!OffsetRect` at `0x18015787b`
- `USER32!OffsetRect` at `0x1801579c8`
- `USER32!OffsetRect` at `0x180157a59`
- `USER32!OffsetRect` at `0x180157b36`
- `USER32!OffsetRect` at `0x180157b56`
- `USER32!OffsetRect` at `0x180157c30`
- `USER32!OffsetRect` at `0x180157c57`
- `UxTheme!DrawThemeText` at `0x180157788`
- `UxTheme!DrawThemeText` at `0x180157952`
- `UxTheme!DrawThemeText` at `0x180157788`
- `UxTheme!DrawThemeText` at `0x180157952`
- `UxTheme!DrawThemeBackground` at `0x1801574d8`
- `UxTheme!DrawThemeBackground` at `0x180157563`
- `UxTheme!DrawThemeBackground` at `0x180157656`
- `UxTheme!DrawThemeBackground` at `0x1801574d8`
- `UxTheme!DrawThemeBackground` at `0x180157563`
- `UxTheme!DrawThemeBackground` at `0x180157656`

## pseudocode

```c
void __fastcall CCalendar::_PaintCalendar(
        CCalendar *this,
        HDC hdc,
        const struct tagRECT *a3,
        int a4,
        const struct CALDATETIME *a5)
{
  const struct tagRECT *v6; // r15
  __int64 v9; // r9
  int v10; // ebx
  unsigned int CellUnit; // r14d
  __int64 v12; // rcx
  unsigned int CalendarUnit; // ebx
  CCalendar *v14; // rcx
  signed int ColCount; // r13d
  CCalendar *v16; // rcx
  LONG v17; // ecx
  void *v18; // rcx
  int v19; // edx
  LONG v20; // ecx
  int top; // r8d
  LONG v22; // eax
  int left; // edx
  void *v24; // rcx
  __int128 v25; // xmm1
  void *v26; // rcx
  HGDIOBJ StockObject; // rax
  HGDIOBJ v28; // rbx
  unsigned int v29; // eax
  int v30; // r8d
  int v31; // edx
  signed int v32; // ebx
  void *v33; // rcx
  int v34; // eax
  int v35; // r8d
  int v36; // edx
  int v37; // ebx
  __int128 v38; // xmm1
  unsigned int StartCol; // r14d
  int v40; // r14d
  int v41; // r13d
  signed int v42; // ebx
  unsigned int v43; // eax
  __int64 v44; // rcx
  void *v45; // rcx
  int v46; // eax
  int v47; // ecx
  int v48; // r8d
  int v49; // edx
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  unsigned int v52; // ebx
  unsigned int v53; // ebx
  signed int v54; // r15d
  signed int v55; // r14d
  unsigned int v56; // ebx
  unsigned int v57; // eax
  __int64 v58; // rcx
  int v59; // eax
  int v60; // ebx
  int v61; // [rsp+50h] [rbp-B0h]
  signed int v62; // [rsp+54h] [rbp-ACh]
  signed int v63; // [rsp+54h] [rbp-ACh]
  unsigned int v64; // [rsp+58h] [rbp-A8h]
  signed int RowCount; // [rsp+5Ch] [rbp-A4h]
  int v66; // [rsp+60h] [rbp-A0h]
  int v67; // [rsp+64h] [rbp-9Ch]
  int v68; // [rsp+68h] [rbp-98h]
  LONG v69; // [rsp+6Ch] [rbp-94h]
  HGDIOBJ h; // [rsp+70h] [rbp-90h]
  struct tagRECT rc; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszText[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v73; // [rsp+A0h] [rbp-60h]
  __int64 v74; // [rsp+B0h] [rbp-50h]
  RECT v75; // [rsp+C0h] [rbp-40h] BYREF
  RECT rect; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR String[64]; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&v75.left = a3;
  v6 = a3;
  v9 = 6;
  rc = 0;
  if ( a4
    || (v10 = *((_DWORD *)this + 4), (v10 & 0x40) != 0)
    || (int)CCalInfo::CalDateCompare(this, (char *)this + 1324, (char *)this + 1244, 6, 0) >= 0 )
  {
    v10 = *((_DWORD *)this + 4);
    v67 = 0;
  }
  else
  {
    v67 = 1;
  }
  if ( a4 != *((_DWORD *)this + 235) - 1
    || (v10 & 0x40) != 0
    || (v68 = 1, (int)CCalInfo::CalDateCompare(this, (char *)this + 1364, (char *)this + 1284, v9, 0) <= 0) )
  {
    v68 = 0;
  }
  CellUnit = CCalendar::_GetCellUnit(this);
  v64 = CellUnit;
  CalendarUnit = CCalendar::_GetCalendarUnit(v12);
  ColCount = CCalendar::_GetColCount(v14);
  v62 = ColCount;
  RowCount = CCalendar::_GetRowCount(v16);
  v61 = 1;
  h = 0;
  if ( !*((_QWORD *)this + 99) )
    h = SelectObject(hdc, *((HGDIOBJ *)this + 94));
  CCalendar::_PaintCalHeader(this, hdc, v6, a5);
  v17 = *((_DWORD *)this + 223) + HIDWORD(*(_QWORD *)&v6->left) - *((_DWORD *)this + 221);
  rect = *v6;
  rect.top = v17;
  if ( RectVisible(hdc, &rect) )
  {
    v18 = (void *)*((_QWORD *)this + 99);
    if ( v18 )
      DrawThemeBackground(v18, hdc, 3, 0, &rect, 0);
  }
  if ( !*((_DWORD *)this + 398) )
  {
    v19 = *((_DWORD *)this + 216);
    v20 = v19 + *((_DWORD *)this + 256);
    top = v6->top;
    v22 = *((_DWORD *)this + 258) - v19;
    left = v6->left;
    rc.left = v20;
    rc.top = *((_DWORD *)this + 259);
    rc.bottom = *((_DWORD *)this + 217) + rc.top;
    rc.right = v22;
    OffsetRect(&rc, left, top);
    if ( RectVisible(hdc, &rc) )
    {
      v24 = (void *)*((_QWORD *)this + 99);
      if ( v24 )
      {
        DrawThemeBackground(v24, hdc, 4, 0, &rc, 0);
      }
      else
      {
        MoveToEx(hdc, rc.left, rc.top, 0);
        LineTo(hdc, rc.right, rc.top);
      }
    }
  }
  if ( (*((_BYTE *)this + 16) & 2) != 0
    && (*((_BYTE *)this + 16) & 0x40) != 0
    && RectVisible(hdc, &rect)
    && (v25 = *((_OWORD *)a5 + 1),
        *(_OWORD *)pszText = *(_OWORD *)a5,
        v74 = *((_QWORD *)a5 + 4),
        v73 = v25,
        CCalendar::_DateSetEnd(this, pszText, CalendarUnit),
        (int)CCalendar::_DateCmpByCell(this, (CCalendar *)((char *)this + 1404), a5) <= 0)
    && (int)CCalendar::_DateCmpByCell(this, (CCalendar *)((char *)this + 1444), (const struct CALDATETIME *)pszText) >= 0 )
  {
    v26 = (void *)*((_QWORD *)this + 99);
    if ( v26 )
    {
      DrawThemeBackground(v26, hdc, 5, (*((_BYTE *)this + 1588) & 0x10) != 0 ? 1 : 4, &rect, 0);
    }
    else
    {
      StockObject = GetStockObject(8);
      v28 = SelectObject(hdc, StockObject);
      FillRect(hdc, &rect, *((HBRUSH *)this + 93));
      SelectObject(hdc, v28);
    }
    v29 = 0;
    v61 = 0;
  }
  else
  {
    v29 = 1;
  }
  SetTextColor(hdc, *((_DWORD *)this + (v29 ^ 1LL) + 194));
  if ( !*((_DWORD *)this + 398) )
  {
    v30 = v6->top;
    v31 = v6->left;
    rc = (struct tagRECT)*((_OWORD *)this + 64);
    OffsetRect(&rc, v31, v30);
    if ( RectVisible(hdc, &rc) )
    {
      v32 = 0;
      for ( rc.right = rc.left + *((_DWORD *)this + 268); v32 < ColCount; ++v32 )
      {
        if ( CCalendar::_GetDoWString(this, (v32 + *((_DWORD *)this + 149)) % 7, pszText, 0xBu) )
        {
          v33 = (void *)*((_QWORD *)this + 99);
          if ( v33 )
          {
            DrawThemeText(v33, hdc, 6, 0, pszText, -1, 0x925u, 0, &rc);
          }
          else
          {
            v34 = lstrlenW(pszText);
            DrawTextW(hdc, pszText, v34, &rc, 0x925u);
          }
        }
        OffsetRect(&rc, *((_DWORD *)this + 268), 0);
      }
    }
    if ( (*((_BYTE *)this + 16) & 4) != 0 )
    {
      v35 = v6->top;
      v36 = v6->left;
      rc = (struct tagRECT)*((_OWORD *)this + 65);
      OffsetRect(&rc, v36, v35);
      if ( RectVisible(hdc, &rc) )
      {
        v37 = *((_DWORD *)this + 269);
        v38 = *((_OWORD *)a5 + 1);
        v69 = rc.top;
        *(_OWORD *)pszText = *(_OWORD *)a5;
        rc.bottom = v37 + rc.top;
        v74 = *((_QWORD *)a5 + 4);
        v73 = v38;
        StartCol = CCalendar::_GetStartCol(this, (const struct CALDATETIME *)pszText);
        v40 = CCalendar::_GetDateValue(this, (const struct CALDATETIME *)pszText) + StartCol;
        v66 = v40;
        v41 = v40 / ColCount;
        OffsetRect(&rc, 0, v37 * v41);
        v42 = v41;
        if ( v41 < RowCount )
        {
          do
          {
            v43 = CCalendar::_GetCalendarUnit(this);
            if ( (int)CCalInfo::CalDateCompare(v44, a5, pszText, v43, 0) < 0 && !v68 )
              break;
            if ( RectVisible(hdc, &rc) )
            {
              if ( CCalInfo::GetWeekNumber(
                     (CCalendar *)((char *)this + 576),
                     (const struct CALDATETIME *)pszText,
                     String,
                     0x40u) >= 0 )
              {
                CCalInfo::GetWeekNumber(
                  (CCalendar *)((char *)this + 576),
                  (const struct CALDATETIME *)pszText,
                  String,
                  0x40u);
                v45 = (void *)*((_QWORD *)this + 99);
                if ( v45 )
                {
                  DrawThemeText(v45, hdc, 6, 0, String, -1, 0x925u, 0, &rc);
                }
                else
                {
                  v46 = lstrlenW(String);
                  DrawTextW(hdc, String, v46, &rc, 0x925u);
                }
              }
              v40 = v66;
            }
            CCalendar::_DateAdjustByStart(this, pszText, (unsigned int)v62, v64);
            if ( v42 == v41 )
              CCalendar::_DateAdjustByStart(this, pszText, (unsigned int)-(v40 % v62), v64);
            OffsetRect(&rc, 0, *((_DWORD *)this + 269));
            ++v42;
          }
          while ( v42 < RowCount );
          v6 = *(const struct tagRECT **)&v75.left;
        }
        v47 = *((_DWORD *)this + 216);
        rc.left = rc.right;
        rc.right += *((_DWORD *)this + 217);
        rc.bottom = rc.top - v47;
        rc.top = v47 + v69;
        if ( RectVisible(hdc, &rc) )
        {
          MoveToEx(hdc, rc.left, rc.top, 0);
          LineTo(hdc, rc.left, rc.bottom);
        }
        CellUnit = v64;
        ColCount = v62;
      }
    }
  }
  v48 = v6->top;
  v49 = v6->left;
  rc = (struct tagRECT)*((_OWORD *)this + 66);
  OffsetRect(&rc, v49, v48);
  if ( RectVisible(hdc, &rc) )
  {
    v50 = *(_OWORD *)a5;
    rc.right = rc.left + *((_DWORD *)this + 268);
    v51 = *((_OWORD *)a5 + 1);
    rc.bottom = rc.top + *((_DWORD *)this + 269);
    *(_OWORD *)pszText = v50;
    *(_QWORD *)&v50 = *((_QWORD *)a5 + 4);
    v73 = v51;
    v74 = v50;
    v52 = CCalendar::_GetStartCol(this, (const struct CALDATETIME *)pszText);
    v53 = CCalendar::_GetDateValue(this, (const struct CALDATETIME *)pszText) + v52;
    if ( v67 )
    {
      CCalendar::_DateAdjustByStart(this, pszText, -v53, CellUnit);
      v53 -= CCalInfo::CalDateRange((char *)this + 576, pszText, a5, CellUnit);
    }
    v54 = v53 / CCalendar::_GetColCount(this);
    v63 = v54;
    v55 = v53 % CCalendar::_GetColCount(this);
    OffsetRect(&rc, 0, *((_DWORD *)this + 269) * v54);
    v75 = rc;
    OffsetRect(&v75, *((_DWORD *)this + 268) * v55, 0);
    v56 = 1;
    while ( v54 < RowCount && v56 )
    {
      if ( v55 < ColCount )
      {
        do
        {
          if ( !v56 )
            break;
          if ( (v57 = CCalendar::_GetCalendarUnit(this),
                v59 = CCalInfo::CalDateCompare(v58, pszText, a5, v57, 0),
                (v60 = v59) == 0)
            || v67 && v59 < 0
            || v68 )
          {
            if ( RectVisible(hdc, &v75) )
              CCalendar::_DrawCell(this, hdc, &v75, (const struct CALDATETIME *)pszText, v60 != 0, v61);
            v56 = (unsigned int)CCalendar::_DateCmpByCell(
                                  this,
                                  (const struct CALDATETIME *)pszText,
                                  (CCalendar *)((char *)this + 1164)) >> 31;
            CCalendar::_DateAdjustByStart(this, pszText, 1, v64);
            OffsetRect(&v75, *((_DWORD *)this + 268), 0);
          }
          else
          {
            v56 = 0;
          }
          ++v55;
        }
        while ( v55 < ColCount );
        v54 = v63;
      }
      v55 = 0;
      OffsetRect(&rc, 0, *((_DWORD *)this + 269));
      ++v54;
      v75 = rc;
      v63 = v54;
    }
  }
  if ( !*((_QWORD *)this + 99) )
    SelectObject(hdc, h);
}

```

## disassembly

```asm
0x18015734c  mov     [rsp-8+arg_18], rbx
0x180157351  push    rbp
0x180157352  push    rsi
0x180157353  push    rdi
0x180157354  push    r12
0x180157356  push    r13
0x180157358  push    r14
0x18015735a  push    r15
0x18015735c  lea     rbp, [rsp-70h]
0x180157361  sub     rsp, 170h
0x180157368  mov     rax, cs:__security_cookie
0x18015736f  xor     rax, rsp
0x180157372  mov     [rbp+0A0h+var_40], rax
0x180157376  mov     r12, [rbp+0A0h+arg_20]
0x18015737d  mov     r14d, r9d
0x180157380  xor     r13d, r13d
0x180157383  mov     qword ptr [rbp+0A0h+var_E0.left], r8
0x180157387  xorps   xmm0, xmm0
0x18015738a  mov     r15, r8
0x18015738d  mov     rsi, rdx
0x180157390  mov     rdi, rcx
0x180157393  mov     r9d, 6
0x180157399  movups  xmmword ptr [rbp+0A0h+rc.left], xmm0
0x18015739d  test    r14d, r14d
0x1801573a0  jnz     short loc_1801573D0
0x1801573a2  mov     ebx, [rcx+10h]
0x1801573a5  test    bl, 40h
0x1801573a8  jnz     short loc_1801573D0
0x1801573aa  lea     r8, [rcx+4DCh]
0x1801573b1  mov     dword ptr [rsp+1A0h+pRect], r13d
0x1801573b6  lea     rdx, [rcx+52Ch]
0x1801573bd  call    ?CalDateCompare@CCalInfo@@QEAAHPEBUCALDATETIME@@0W4CALUNIT@@1@Z; CCalInfo::CalDateCompare(CALDATETIME const *,CALDATETIME const *,CALUNIT,CALUNIT)
0x1801573c2  test    eax, eax
0x1801573c4  jns     short loc_1801573D0
0x1801573c6  mov     [rsp+1A0h+var_13C], 1
0x1801573ce  jmp     short loc_1801573D8
0x1801573d0  mov     ebx, [rdi+10h]
0x1801573d3  mov     [rsp+1A0h+var_13C], r13d
0x1801573d8  mov     eax, [rdi+3ACh]
0x1801573de  dec     eax
0x1801573e0  cmp     r14d, eax
0x1801573e3  jnz     short loc_18015740E
0x1801573e5  test    bl, 40h
0x1801573e8  jnz     short loc_18015740E
0x1801573ea  lea     r8, [rdi+504h]
0x1801573f1  mov     dword ptr [rsp+1A0h+pRect], r13d
0x1801573f6  lea     rdx, [rdi+554h]
0x1801573fd  call    ?CalDateCompare@CCalInfo@@QEAAHPEBUCALDATETIME@@0W4CALUNIT@@1@Z; CCalInfo::CalDateCompare(CALDATETIME const *,CALDATETIME const *,CALUNIT,CALUNIT)
0x180157402  mov     [rsp+1A0h+var_138], 1
0x18015740a  test    eax, eax
0x18015740c  jg      short loc_180157413
0x18015740e  mov     [rsp+1A0h+var_138], r13d
0x180157413  mov     rcx, rdi
0x180157416  call    ?_GetCellUnit@CCalendar@@AEAA?AW4CALUNIT@@XZ; CCalendar::_GetCellUnit(void)
0x18015741b  mov     r14d, eax
0x18015741e  mov     [rsp+1A0h+var_148], eax
0x180157422  call    ?_GetCalendarUnit@CCalendar@@AEAA?AW4CALUNIT@@XZ; CCalendar::_GetCalendarUnit(void)
0x180157427  mov     ebx, eax
0x180157429  call    ?_GetColCount@CCalendar@@AEAAIXZ; CCalendar::_GetColCount(void)
0x18015742e  mov     r13d, eax
0x180157431  mov     [rsp+1A0h+var_14C], eax
0x180157435  call    ?_GetRowCount@CCalendar@@AEAAIXZ; CCalendar::_GetRowCount(void)
0x18015743a  cmp     qword ptr [rdi+318h], 0
0x180157442  mov     [rsp+1A0h+var_144], eax
0x180157446  mov     [rsp+1A0h+var_150], 1
0x18015744e  mov     [rsp+1A0h+h], 0
0x180157457  jnz     short loc_18015746E
0x180157459  mov     rdx, [rdi+2F0h]; h
0x180157460  mov     rcx, rsi; hdc
0x180157463  call    cs:__imp_SelectObject
0x180157469  mov     [rsp+1A0h+h], rax
0x18015746e  mov     r9, r12; struct CALDATETIME *
0x180157471  mov     r8, r15; struct tagRECT *
0x180157474  mov     rdx, rsi; hdc
0x180157477  mov     rcx, rdi; this
0x18015747a  call    ?_PaintCalHeader@CCalendar@@AEAAXPEAUHDC__@@PEBUtagRECT@@PEBUCALDATETIME@@@Z; CCalendar::_PaintCalHeader(HDC__ *,tagRECT const *,CALDATETIME const *)
0x18015747f  movups  xmm0, xmmword ptr [r15]
0x180157483  lea     rdx, [rbp+0A0h+rect]; lprect
0x180157487  movq    rcx, xmm0
0x18015748c  shr     rcx, 20h
0x180157490  sub     ecx, [rdi+374h]
0x180157496  add     ecx, [rdi+37Ch]
0x18015749c  movups  xmmword ptr [rbp+0A0h+rect.left], xmm0
0x1801574a0  mov     [rbp+0A0h+rect.top], ecx
0x1801574a3  mov     rcx, rsi; hdc
0x1801574a6  call    cs:__imp_RectVisible
0x1801574ac  test    eax, eax
0x1801574ae  jz      short loc_1801574DE
0x1801574b0  mov     rcx, [rdi+318h]; hTheme
0x1801574b7  test    rcx, rcx
0x1801574ba  jz      short loc_1801574DE
0x1801574bc  xor     r9d, r9d; iStateId
0x1801574bf  mov     [rsp+1A0h+pClipRect], 0; pClipRect
0x1801574c8  lea     rax, [rbp+0A0h+rect]
0x1801574cc  mov     rdx, rsi; hdc
0x1801574cf  mov     [rsp+1A0h+pRect], rax; pRect
0x1801574d4  lea     r8d, [r9+3]; iPartId
0x1801574d8  call    cs:__imp_DrawThemeBackground
0x1801574de  cmp     dword ptr [rdi+638h], 0
0x1801574e5  jnz     loc_18015758E
0x1801574eb  mov     edx, [rdi+360h]
0x1801574f1  mov     ecx, [rdi+400h]
0x1801574f7  mov     eax, [rdi+408h]
0x1801574fd  add     ecx, edx
0x1801574ff  mov     r8d, [r15+4]; dy
0x180157503  sub     eax, edx
0x180157505  mov     edx, [r15]; dx
0x180157508  mov     [rbp+0A0h+rc.left], ecx
0x18015750b  mov     ecx, [rdi+40Ch]
0x180157511  mov     [rbp+0A0h+rc.top], ecx
0x180157514  add     ecx, [rdi+364h]
0x18015751a  mov     [rbp+0A0h+rc.bottom], ecx
0x18015751d  lea     rcx, [rbp+0A0h+rc]; lprc
0x180157521  mov     [rbp+0A0h+rc.right], eax
0x180157524  call    cs:__imp_OffsetRect
0x18015752a  lea     rdx, [rbp+0A0h+rc]; lprect
0x18015752e  mov     rcx, rsi; hdc
0x180157531  call    cs:__imp_RectVisible
0x180157537  test    eax, eax
0x180157539  jz      short loc_18015758E
0x18015753b  mov     rcx, [rdi+318h]; hTheme
0x180157542  test    rcx, rcx
0x180157545  jz      short loc_18015756B
0x180157547  xor     r9d, r9d; iStateId
0x18015754a  mov     [rsp+1A0h+pClipRect], 0; pClipRect
0x180157553  lea     rax, [rbp+0A0h+rc]
0x180157557  mov     rdx, rsi; hdc
0x18015755a  mov     [rsp+1A0h+pRect], rax; pRect
0x18015755f  lea     r8d, [r9+4]; iPartId
0x180157563  call    cs:__imp_DrawThemeBackground
0x180157569  jmp     short loc_18015758E
0x18015756b  mov     r8d, [rbp+0A0h+rc.top]; y
0x18015756f  xor     r9d, r9d; lppt
0x180157572  mov     edx, [rbp+0A0h+rc.left]; x
0x180157575  mov     rcx, rsi; hdc
0x180157578  call    cs:__imp_MoveToEx
0x18015757e  mov     r8d, [rbp+0A0h+rc.top]; y
0x180157582  mov     rcx, rsi; hdc
0x180157585  mov     edx, [rbp+0A0h+rc.right]; x
0x180157588  call    cs:__imp_LineTo
0x18015758e  test    byte ptr [rdi+10h], 2
0x180157592  jz      loc_1801576A0
0x180157598  test    byte ptr [rdi+10h], 40h
0x18015759c  jz      loc_1801576A0
0x1801575a2  lea     rdx, [rbp+0A0h+rect]; lprect
0x1801575a6  mov     rcx, rsi; hdc
0x1801575a9  call    cs:__imp_RectVisible
0x1801575af  test    eax, eax
0x1801575b1  jz      loc_1801576A0
0x1801575b7  movups  xmm0, xmmword ptr [r12]
0x1801575bc  mov     r8d, ebx
0x1801575bf  lea     rdx, [rbp+0A0h+pszText]
0x1801575c3  movups  xmm1, xmmword ptr [r12+10h]
0x1801575c9  mov     rcx, rdi
0x1801575cc  movups  xmmword ptr [rbp+0A0h+pszText], xmm0
0x1801575d0  movsd   xmm0, qword ptr [r12+20h]
0x1801575d7  movsd   [rbp+0A0h+var_F0], xmm0
0x1801575dc  movups  [rbp+0A0h+var_100], xmm1
0x1801575e0  call    ?_DateSetEnd@CCalendar@@AEAAHPEAUCALDATETIME@@W4CALUNIT@@@Z; CCalendar::_DateSetEnd(CALDATETIME *,CALUNIT)
0x1801575e5  lea     rdx, [rdi+57Ch]; struct CALDATETIME *
0x1801575ec  mov     r8, r12; struct CALDATETIME *
0x1801575ef  mov     rcx, rdi; this
0x1801575f2  call    ?_DateCmpByCell@CCalendar@@AEAAHPEBUCALDATETIME@@0@Z; CCalendar::_DateCmpByCell(CALDATETIME const *,CALDATETIME const *)
0x1801575f7  test    eax, eax
0x1801575f9  jg      loc_1801576A0
0x1801575ff  lea     rdx, [rdi+5A4h]; struct CALDATETIME *
0x180157606  mov     rcx, rdi; this
0x180157609  lea     r8, [rbp+0A0h+pszText]; struct CALDATETIME *
0x18015760d  call    ?_DateCmpByCell@CCalendar@@AEAAHPEBUCALDATETIME@@0@Z; CCalendar::_DateCmpByCell(CALDATETIME const *,CALDATETIME const *)
0x180157612  test    eax, eax
0x180157614  js      loc_1801576A0
0x18015761a  mov     al, [rdi+634h]
0x180157620  mov     rcx, [rdi+318h]; hTheme
0x180157627  and     al, 10h
0x180157629  neg     al
0x18015762b  sbb     r9d, r9d
0x18015762e  and     r9d, 0FFFFFFFDh
0x180157632  add     r9d, 4; iStateId
0x180157636  test    rcx, rcx
0x180157639  jz      short loc_18015765E
0x18015763b  lea     rax, [rbp+0A0h+rect]
0x18015763f  mov     [rsp+1A0h+pClipRect], 0; pClipRect
0x180157648  mov     r8d, 5; iPartId
0x18015764e  mov     [rsp+1A0h+pRect], rax; pRect
0x180157653  mov     rdx, rsi; hdc
0x180157656  call    cs:__imp_DrawThemeBackground
0x18015765c  jmp     short loc_180157698
0x18015765e  mov     ecx, 8; i
0x180157663  call    cs:__imp_GetStockObject
0x180157669  mov     rdx, rax; h
0x18015766c  mov     rcx, rsi; hdc
0x18015766f  call    cs:__imp_SelectObject
0x180157675  mov     r8, [rdi+2E8h]; hbr
0x18015767c  lea     rdx, [rbp+0A0h+rect]; lprc
0x180157680  mov     rcx, rsi; hDC
0x180157683  mov     rbx, rax
0x180157686  call    cs:__imp_FillRect
0x18015768c  mov     rdx, rbx; h
0x18015768f  mov     rcx, rsi; hdc
0x180157692  call    cs:__imp_SelectObject
0x180157698  xor     eax, eax
0x18015769a  mov     [rsp+1A0h+var_150], eax
0x18015769e  jmp     short loc_1801576A4
0x1801576a0  mov     eax, [rsp+1A0h+var_150]
0x1801576a4  mov     edx, eax
0x1801576a6  mov     rcx, rsi; hdc
0x1801576a9  xor     rdx, 1
0x1801576ad  mov     edx, [rdi+rdx*4+308h]; color
0x1801576b4  call    cs:__imp_SetTextColor
0x1801576ba  cmp     dword ptr [rdi+638h], 0
0x1801576c1  jnz     loc_180157A42
0x1801576c7  movups  xmm0, xmmword ptr [rdi+400h]
0x1801576ce  mov     r8d, [r15+4]; dy
0x1801576d2  lea     rcx, [rbp+0A0h+rc]; lprc
0x1801576d6  mov     edx, [r15]; dx
0x1801576d9  movdqu  xmmword ptr [rbp+0A0h+rc.left], xmm0
0x1801576de  call    cs:__imp_OffsetRect
0x1801576e4  lea     rdx, [rbp+0A0h+rc]; lprect
0x1801576e8  mov     rcx, rsi; hdc
0x1801576eb  call    cs:__imp_RectVisible
0x1801576f1  test    eax, eax
0x1801576f3  jz      loc_1801577D4
0x1801576f9  mov     ecx, [rdi+430h]
0x1801576ff  xor     ebx, ebx
0x180157701  add     ecx, [rbp+0A0h+rc.left]
0x180157704  mov     [rbp+0A0h+rc.right], ecx
0x180157707  test    r13d, r13d
0x18015770a  jle     loc_1801577D4
0x180157710  mov     ecx, [rdi+254h]
0x180157716  lea     r8, [rbp+0A0h+pszText]; unsigned __int16 *
0x18015771a  add     ecx, ebx
0x18015771c  mov     eax, 92492493h
0x180157721  imul    ecx
0x180157723  mov     r9d, 0Bh; unsigned __int64
0x180157729  add     edx, ecx
0x18015772b  sar     edx, 2
0x18015772e  mov     eax, edx
0x180157730  shr     eax, 1Fh
0x180157733  add     edx, eax
0x180157735  imul    eax, edx, 7
0x180157738  sub     ecx, eax
0x18015773a  mov     edx, ecx; unsigned int
0x18015773c  mov     rcx, rdi; this
0x18015773f  call    ?_GetDoWString@CCalendar@@AEAAHIPEAG_K@Z; CCalendar::_GetDoWString(uint,ushort *,unsigned __int64)
0x180157744  test    eax, eax
0x180157746  jz      short loc_1801577B6
0x180157748  mov     rcx, [rdi+318h]; hTheme
0x18015774f  test    rcx, rcx
0x180157752  jz      short loc_180157790
0x180157754  lea     rax, [rbp+0A0h+rc]
0x180157758  xor     r9d, r9d; iStateId
0x18015775b  mov     [rsp+1A0h+var_160], rax; pRect
0x180157760  mov     rdx, rsi; hdc
0x180157763  mov     [rsp+1A0h+dwTextFlags2], 0; dwTextFlags2
0x18015776b  lea     rax, [rbp+0A0h+pszText]
0x18015776f  mov     [rsp+1A0h+dwTextFlags], 925h; dwTextFlags
0x180157777  mov     dword ptr [rsp+1A0h+pClipRect], 0FFFFFFFFh; cchText
0x18015777f  lea     r8d, [r9+6]; iPartId
0x180157783  mov     [rsp+1A0h+pRect], rax; pszText
0x180157788  call    cs:__imp_DrawThemeText
0x18015778e  jmp     short loc_1801577B6
0x180157790  lea     rcx, [rbp+0A0h+pszText]; lpString
0x180157794  call    cs:__imp_lstrlenW
0x18015779a  lea     r9, [rbp+0A0h+rc]; lprc
0x18015779e  mov     dword ptr [rsp+1A0h+pRect], 925h; format
0x1801577a6  mov     r8d, eax; cchText
0x1801577a9  lea     rdx, [rbp+0A0h+pszText]; lpchText
0x1801577ad  mov     rcx, rsi; hdc
0x1801577b0  call    cs:__imp_DrawTextW
0x1801577b6  mov     edx, [rdi+430h]; dx
0x1801577bc  lea     rcx, [rbp+0A0h+rc]; lprc
0x1801577c0  xor     r8d, r8d; dy
0x1801577c3  call    cs:__imp_OffsetRect
0x1801577c9  inc     ebx
0x1801577cb  cmp     ebx, r13d
0x1801577ce  jl      loc_180157710
0x1801577d4  test    byte ptr [rdi+10h], 4
0x1801577d8  jz      loc_180157A42
0x1801577de  movups  xmm0, xmmword ptr [rdi+410h]
0x1801577e5  mov     r8d, [r15+4]; dy
0x1801577e9  lea     rcx, [rbp+0A0h+rc]; lprc
0x1801577ed  mov     edx, [r15]; dx
0x1801577f0  movdqu  xmmword ptr [rbp+0A0h+rc.left], xmm0
0x1801577f5  call    cs:__imp_OffsetRect
0x1801577fb  lea     rdx, [rbp+0A0h+rc]; lprect
0x1801577ff  mov     rcx, rsi; hdc
0x180157802  call    cs:__imp_RectVisible
0x180157808  test    eax, eax
0x18015780a  jz      loc_180157A42
0x180157810  mov     eax, [rbp+0A0h+rc.top]
0x180157813  lea     rdx, [rbp+0A0h+pszText]; struct CALDATETIME *
0x180157817  movups  xmm0, xmmword ptr [r12]
0x18015781c  mov     ebx, [rdi+434h]
0x180157822  mov     rcx, rdi; this
0x180157825  movups  xmm1, xmmword ptr [r12+10h]
0x18015782b  mov     [rsp+1A0h+var_134], eax
0x18015782f  add     eax, ebx
0x180157831  movups  xmmword ptr [rbp+0A0h+pszText], xmm0
0x180157835  mov     [rbp+0A0h+rc.bottom], eax
0x180157838  movsd   xmm0, qword ptr [r12+20h]
  ... truncated ...
```
