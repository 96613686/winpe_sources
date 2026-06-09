# MCPaintMonth

- ea: `0x1800457f8`
- end: `0x1800460dd`
- name: `MCPaintMonth`
- size: `2277`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180045370`

## callees

- `0x1800115f0`
- `0x18001ac40`
- `0x180042570`
- `0x180042de0`
- `0x180043218`
- `0x1800457f8`
- `0x180072058`
- `0x18007222c`
- `0x180072380`
- `0x1800724e0`

## import_xrefs

- `GDI32!SelectObject` at `0x180045898`
- `GDI32!SelectObject` at `0x1800458ac`
- `GDI32!SelectObject` at `0x18004591a`
- `GDI32!SelectObject` at `0x180045974`
- `GDI32!SelectObject` at `0x180045dd4`
- `GDI32!SelectObject` at `0x180045df5`
- `GDI32!SelectObject` at `0x180045e9b`
- `GDI32!SelectObject` at `0x180045ebf`
- `GDI32!SelectObject` at `0x180045fd4`
- `GDI32!SelectObject` at `0x1800460b7`
- `GDI32!SelectObject` at `0x180045898`
- `GDI32!SelectObject` at `0x1800458ac`
- `GDI32!SelectObject` at `0x18004591a`
- `GDI32!SelectObject` at `0x180045974`
- `GDI32!SelectObject` at `0x180045dd4`
- `GDI32!SelectObject` at `0x180045df5`
- `GDI32!SelectObject` at `0x180045e9b`
- `GDI32!SelectObject` at `0x180045ebf`
- `GDI32!SelectObject` at `0x180045fd4`
- `GDI32!SelectObject` at `0x1800460b7`
- `GDI32!GetStockObject` at `0x180045eb3`
- `GDI32!GetStockObject` at `0x180045eb3`
- `GDI32!SetTextColor` at `0x18004590a`
- `GDI32!SetTextColor` at `0x18004597f`
- `GDI32!SetTextColor` at `0x180045ce7`
- `GDI32!SetTextColor` at `0x180045e8a`
- `GDI32!SetTextColor` at `0x180045fc6`
- `GDI32!SetTextColor` at `0x180046070`
- `GDI32!SetTextColor` at `0x18004590a`
- `GDI32!SetTextColor` at `0x18004597f`
- `GDI32!SetTextColor` at `0x180045ce7`
- `GDI32!SetTextColor` at `0x180045e8a`
- `GDI32!SetTextColor` at `0x180045fc6`
- `GDI32!SetTextColor` at `0x180046070`
- `GDI32!RectVisible` at `0x1800458e4`
- `GDI32!RectVisible` at `0x1800459b0`
- `GDI32!RectVisible` at `0x180045b7d`
- `GDI32!RectVisible` at `0x180045d75`
- `GDI32!RectVisible` at `0x1800458e4`
- `GDI32!RectVisible` at `0x1800459b0`
- `GDI32!RectVisible` at `0x180045b7d`
- `GDI32!RectVisible` at `0x180045d75`
- `GDI32!MoveToEx` at `0x1800459d6`
- `GDI32!MoveToEx` at `0x180045b9e`
- `GDI32!MoveToEx` at `0x1800459d6`
- `GDI32!MoveToEx` at `0x180045b9e`
- `GDI32!LineTo` at `0x1800459ec`
- `GDI32!LineTo` at `0x180045bb4`
- `GDI32!LineTo` at `0x1800459ec`
- `GDI32!LineTo` at `0x180045bb4`
- `GDI32!Ellipse` at `0x180045eeb`
- `GDI32!Ellipse` at `0x180045eeb`
- `GDI32!Rectangle` at `0x180045f49`
- `GDI32!Rectangle` at `0x180045f49`
- `KERNEL32!lstrlenW` at `0x180045948`
- `KERNEL32!lstrlenW` at `0x180045a33`
- `KERNEL32!lstrlenW` at `0x180045948`
- `KERNEL32!lstrlenW` at `0x180045a33`
- `USER32!DrawTextW` at `0x180045964`
- `USER32!DrawTextW` at `0x180045a55`
- `USER32!DrawTextW` at `0x180045c34`
- `USER32!DrawTextW` at `0x180045f74`
- `USER32!DrawTextW` at `0x180045964`
- `USER32!DrawTextW` at `0x180045a55`
- `USER32!DrawTextW` at `0x180045c34`
- `USER32!DrawTextW` at `0x180045f74`

## pseudocode

```c
HGDIOBJ __fastcall MCPaintMonth(__int64 a1, HDC a2, int *a3, int a4, __int16 a5, int a6, int a7, int a8, void *a9)
{
  void *v10; // rdx
  int v11; // r14d
  int v13; // r13d
  int *v14; // r15
  COLORREF v15; // eax
  HGDIOBJ v16; // rax
  void *v17; // rdx
  int v18; // ecx
  RECT v19; // xmm0
  COLORREF *v20; // rbx
  int v21; // eax
  int v22; // eax
  int v23; // ecx
  RECT v24; // xmm0
  int v25; // eax
  int v26; // r14d
  __int64 v27; // rbx
  int v28; // eax
  int v29; // eax
  int v30; // r9d
  int v31; // r11d
  int v32; // r10d
  int v33; // r12d
  __int16 v34; // r14
  int v35; // ecx
  bool v36; // zf
  __int16 v37; // ax
  int v38; // ebx
  int v39; // r13d
  int v40; // ecx
  RECT v41; // xmm0
  LONG v42; // edx
  __int64 v43; // r8
  __int64 v44; // rdx
  int v45; // r14d
  int WeekNumber; // ebx
  int v47; // eax
  int v48; // ebx
  int DaysForMonth; // eax
  unsigned __int16 v50; // cx
  int v51; // r11d
  int i; // eax
  int v53; // eax
  __int64 v54; // r8
  __int64 v55; // rdx
  COLORREF v56; // edx
  RECT v57; // xmm0
  int v58; // r14d
  int v59; // r15d
  int v60; // ebx
  int v61; // edx
  int v62; // ecx
  int v63; // r9d
  int v64; // eax
  int v65; // r9d
  int v66; // ebx
  HGDIOBJ StockObject; // rax
  LONG right; // r9d
  LONG left; // ecx
  int v70; // eax
  int v71; // ecx
  int v72; // eax
  COLORREF v73; // edx
  int v74; // eax
  int v76; // [rsp+30h] [rbp-D0h]
  int v77; // [rsp+30h] [rbp-D0h]
  int v78; // [rsp+34h] [rbp-CCh]
  int v79; // [rsp+38h] [rbp-C8h]
  int v80; // [rsp+3Ch] [rbp-C4h]
  int v81; // [rsp+40h] [rbp-C0h]
  int v82; // [rsp+44h] [rbp-BCh]
  int v84; // [rsp+48h] [rbp-B8h]
  COLORREF v85; // [rsp+50h] [rbp-B0h]
  COLORREF color; // [rsp+58h] [rbp-A8h]
  COLORREF v87; // [rsp+5Ch] [rbp-A4h]
  COLORREF v88; // [rsp+60h] [rbp-A0h]
  HGDIOBJ v89; // [rsp+68h] [rbp-98h]
  __int128 v90; // [rsp+70h] [rbp-90h] BYREF
  HGDIOBJ h; // [rsp+80h] [rbp-80h]
  HGDIOBJ v92; // [rsp+88h] [rbp-78h]
  RECT rect; // [rsp+90h] [rbp-70h] BYREF
  RECT rc; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v95; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR String[64]; // [rsp+C0h] [rbp-40h] BYREF

  v10 = *(void **)(a1 + 1672);
  v11 = a6;
  h = a9;
  color = *(_DWORD *)(a1 + 1692);
  v13 = a4;
  v14 = a3;
  v87 = *(_DWORD *)(a1 + 1708);
  v15 = *(_DWORD *)(a1 + 1700);
  v76 = a4;
  v79 = a6;
  rect = 0;
  v89 = 0;
  rc = 0;
  v85 = 0;
  v95 = 0;
  v88 = v15;
  v16 = SelectObject(a2, v10);
  v17 = *(void **)(a1 + 1656);
  v92 = v16;
  SelectObject(a2, v17);
  v18 = *v14;
  v20 = (COLORREF *)(a1 + 1696);
  rect = *(RECT *)(a1 + 2024);
  v19 = rect;
  rect.right += v18;
  rect.left = v18 + _mm_cvtsi128_si32((__m128i)v19);
  v21 = v14[1];
  rect.top += v21;
  rect.bottom += v21;
  if ( RectVisible(a2, &rect) )
  {
    FillRectClr(a2, &rect, *v20);
    SetTextColor(a2, *(_DWORD *)(a1 + 1700));
    SelectObject(a2, *(HGDIOBJ *)(a1 + 1680));
    LOWORD(v95) = a5;
    WORD1(v95) = v13;
    MCGetMonthFormat(a1, &v95, String);
    v22 = lstrlenW(String);
    DrawTextW(a2, String, v22, &rect, 0x925u);
    SelectObject(a2, *(HGDIOBJ *)(a1 + 1672));
  }
  SetTextColor(a2, *v20);
  v23 = *v14;
  rect = *(RECT *)(a1 + 2040);
  v24 = rect;
  rect.right += v23;
  rect.left = v23 + _mm_cvtsi128_si32((__m128i)v24);
  v25 = v14[1];
  rect.top += v25;
  rect.bottom += v25;
  if ( RectVisible(a2, &rect) )
  {
    MoveToEx(a2, rect.left + 4, rect.bottom - 1, 0);
    LineTo(a2, rect.right - 4, rect.bottom - 1);
    v26 = 0;
    rect.right = rect.left + *(_DWORD *)(a1 + 1712);
    do
    {
      v27 = 22LL * ((v26 + *(_DWORD *)(a1 + 1468)) % 7);
      v28 = lstrlenW((LPCWSTR)(v27 + a1 + 1312));
      DrawTextW(a2, (LPCWSTR)(v27 + a1 + 1312), v28, &rect, 0x825u);
      v29 = *(_DWORD *)(a1 + 1712);
      ++v26;
      rect.left += v29;
      rect.right += v29;
    }
    while ( v26 < 7 );
    v11 = a6;
    v13 = v76;
  }
  v30 = v11 + 1;
  v31 = *(_DWORD *)(a1 + 4LL * v11 + 2164);
  v32 = *(_DWORD *)(a1 + 4LL * v11 + 2220);
  v81 = v31;
  if ( a8 )
    v33 = 6;
  else
    v33 = (v31 + *(_DWORD *)(a1 + 4LL * v30 + 2164) - v32 + 6) / 7;
  v34 = a5;
  if ( v32 == v31 )
  {
    v39 = 1;
    v78 = 1;
    LOWORD(v38) = v76;
    v79 = v30;
    v81 = *(_DWORD *)(a1 + 4LL * v30 + 2164);
  }
  else
  {
    v35 = v13 - 1;
    v78 = 0;
    v36 = v13 == 1;
    v37 = a5 - 1;
    v38 = v13 - 1;
    v39 = v32 + 1;
    if ( v35 < 0 || v36 )
      v38 = 12;
    else
      v37 = a5;
    v76 = v38;
    v34 = v37;
    a5 = v37;
  }
  if ( (*(_BYTE *)(a1 + 16) & 4) != 0 )
  {
    v40 = *v14;
    rect = *(RECT *)(a1 + 2056);
    v41 = rect;
    v42 = v14[1] + rect.top;
    rect.right += v40;
    rect.top = v42;
    rect.left = v40 + _mm_cvtsi128_si32((__m128i)v41);
    rect.bottom = v42 + *(_DWORD *)(a1 + 1716) * v33;
    if ( RectVisible(a2, &rect) )
    {
      MoveToEx(a2, rect.right - 1, rect.top + 4, 0);
      LineTo(a2, rect.right - 1, rect.bottom - 4);
      v43 = *(unsigned int *)(a1 + 1472);
      v44 = *(unsigned int *)(a1 + 1468);
      LOWORD(v95) = v34;
      WORD1(v95) = v38;
      WORD3(v95) = v39;
      v45 = 0;
      WeekNumber = GetWeekNumber(&v95, v44, v43);
      rect.bottom = rect.top + *(_DWORD *)(a1 + 1716);
      if ( v33 > 0 )
      {
        do
        {
          StringCchPrintfW(String, 0x40u, L"%d", (unsigned int)WeekNumber);
          DrawTextW(a2, String, (WeekNumber > 9) + 1, &rect, 0x925u);
          v47 = *(_DWORD *)(a1 + 1716);
          v48 = 7;
          rect.top += v47;
          rect.bottom += v47;
          DaysForMonth = GetDaysForMonth((unsigned __int16)v95, WORD1(v95));
          v50 = WORD3(v95);
          v51 = DaysForMonth;
          for ( i = WORD3(v95) + 7; i > v51; i = v48 + WORD3(v95) )
          {
            WORD3(v95) = 1;
            v48 += v50 - v51 - 1;
            IncrSystemTime(&v95, &v95, 1, 2);
            v53 = GetDaysForMonth((unsigned __int16)v95, WORD1(v95));
            v50 = WORD3(v95);
            v51 = v53;
          }
          v54 = *(unsigned int *)(a1 + 1472);
          v55 = *(unsigned int *)(a1 + 1468);
          WORD3(v95) = v48 + v50;
          ++v45;
          WeekNumber = GetWeekNumber(&v95, v55, v54);
        }
        while ( v45 < v33 );
        v14 = a3;
      }
    }
  }
  v56 = v87;
  if ( v78 )
    v56 = color;
  SetTextColor(a2, v56);
  v57 = *(RECT *)(a1 + 2072);
  v82 = 0;
  v80 = 0;
  rect = v57;
  rect.top = v14[1] + v57.top;
  v84 = 0;
  rect.left = *v14 + _mm_cvtsi128_si32((__m128i)v57);
  rect.right = *(_DWORD *)(a1 + 1712) + rect.left;
  rect.bottom = rect.top + *(_DWORD *)(a1 + 1716);
  if ( v33 > 0 )
  {
    v58 = v79;
    v59 = v76;
    do
    {
      v60 = 0;
      rc = rect;
      v77 = 0;
      do
      {
        v61 = v78;
        if ( v78 || a7 )
        {
          if ( RectVisible(a2, &rc) )
          {
            StringCchPrintfW(String, 0x40u, L"%d", (unsigned int)v39);
            if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
            {
              if ( a1 == -2288
                || (v62 = *(_DWORD *)(a1 + 4LL * v58 + 2288), !_bittest(&v62, (unsigned __int8)(v39 - 1))) )
              {
                if ( v80 )
                {
                  SelectObject(a2, *(HGDIOBJ *)(a1 + 1672));
                  v80 = 0;
                }
              }
              else if ( !v80 )
              {
                SelectObject(a2, *(HGDIOBJ *)(a1 + 1680));
                v80 = 1;
              }
            }
            v90 = 0;
            LOWORD(v90) = a5;
            WORD1(v90) = v59;
            WORD3(v90) = v39;
            v63 = CmpDate(&v90, a1 + 1820);
            if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
            {
              v64 = CmpDate(&v90, a1 + 1836);
              if ( v65 > 0 && v64 < 0 )
              {
                v66 = 4;
                goto LABEL_49;
              }
              v66 = v65 == 0;
              if ( !v64 )
                v66 |= 2u;
              if ( v66 )
              {
LABEL_49:
                v85 = SetTextColor(a2, v88);
                v82 = 1;
                v89 = SelectObject(a2, h);
                StockObject = GetStockObject(8);
                SelectObject(a2, StockObject);
                right = rc.right;
                if ( (v66 & 3) != 0 )
                {
                  Ellipse(a2, rc.left + 2, rc.top + 2, rc.right - 1, rc.bottom - 1);
                  if ( v66 == 1 )
                  {
                    right = rc.right;
                    left = rc.left + (rc.right - rc.left) / 2;
                    goto LABEL_55;
                  }
                  if ( v66 == 2 )
                  {
                    left = rc.left;
                    right = rc.left + (rc.right - rc.left) / 2;
                    goto LABEL_55;
                  }
                }
                else
                {
                  left = rc.left;
LABEL_55:
                  if ( left && right )
                    Rectangle(a2, left, rc.top + 2, right + 1, rc.bottom - 1);
                }
              }
              v60 = v77;
            }
            else if ( !v63 )
            {
              v66 = 3;
              goto LABEL_49;
            }
            DrawTextW(a2, String, (v39 > 9) + 1, &rc, 0x925u);
            if ( (*(_BYTE *)(a1 + 16) & 8) == 0
              && (*(_BYTE *)(a1 + 2392) & 0x20) != 0
              && a6 == *(_DWORD *)(a1 + 2088)
              && v60 == *(_DWORD *)(a1 + 2096)
              && v84 == *(_DWORD *)(a1 + 2092) )
            {
              MCDrawTodayCircle(a1, a2, &rc);
            }
            if ( v82 )
            {
              SetTextColor(a2, v85);
              SelectObject(a2, v89);
              v82 = 0;
            }
          }
          v61 = v78;
        }
        v70 = *(_DWORD *)(a1 + 1712);
        rc.left += v70;
        rc.right += v70;
        if ( ++v39 > v81 )
        {
          v71 = v79;
          if ( !a8 && v79 > a6 )
            return SelectObject(a2, v92);
          v39 = 1;
          ++v79;
          v81 = *(_DWORD *)(a1 + 4LL * v71 + 2168);
          v72 = v59 + 1;
          if ( v59 + 1 > 12 )
            ++a5;
          v59 = 1;
          if ( v72 <= 12 )
            v59 = v72;
          if ( v61 )
          {
            v73 = v87;
            v78 = 0;
          }
          else
          {
            v73 = color;
            v78 = 1;
          }
          SetTextColor(a2, v73);
          a7 = a8;
          v58 = v79;
        }
        v77 = ++v60;
      }
      while ( v60 < 7 );
      v74 = *(_DWORD *)(a1 + 1716);
      rect.top += v74;
      rect.bottom += v74;
      ++v84;
    }
    while ( v84 < v33 );
  }
  return SelectObject(a2, v92);
}

```

## disassembly

```asm
0x1800457f8  push    rbp
0x1800457fa  push    rbx
0x1800457fb  push    rsi
0x1800457fc  push    rdi
0x1800457fd  push    r12
0x1800457ff  push    r13
0x180045801  push    r14
0x180045803  push    r15
0x180045805  lea     rbp, [rsp-58h]
0x18004580a  sub     rsp, 158h
0x180045811  mov     rax, cs:__security_cookie
0x180045818  xor     rax, rsp
0x18004581b  mov     [rbp+90h+var_50], rax
0x18004581f  mov     rax, [rbp+90h+arg_40]
0x180045826  mov     rsi, rdx
0x180045829  mov     rdx, [rcx+688h]; h
0x180045830  xorps   xmm0, xmm0
0x180045833  mov     r14d, [rbp+90h+arg_28]
0x18004583a  mov     rdi, rcx
0x18004583d  mov     [rbp+90h+h], rax
0x180045841  xorps   xmm1, xmm1
0x180045844  mov     eax, [rcx+69Ch]
0x18004584a  xor     r12d, r12d
0x18004584d  mov     [rsp+190h+color], eax
0x180045851  mov     r13d, r9d
0x180045854  mov     eax, [rcx+6ACh]
0x18004585a  mov     r15, r8
0x18004585d  mov     [rsp+190h+var_134], eax
0x180045861  mov     eax, [rcx+6A4h]
0x180045867  mov     rcx, rsi; hdc
0x18004586a  mov     [rsp+190h+var_160], r9d
0x18004586f  mov     [rsp+190h+var_148], r8
0x180045874  mov     [rsp+190h+var_158], r14d
0x180045879  movups  xmmword ptr [rbp+90h+rect.left], xmm0
0x18004587d  mov     [rsp+190h+var_128], r12
0x180045882  movups  xmmword ptr [rbp+90h+rc.left], xmm1
0x180045886  mov     [rsp+190h+var_140], r12d
0x18004588b  movups  [rbp+90h+var_E0], xmm0
0x18004588f  mov     [rsp+190h+var_13C], r14d
0x180045894  mov     [rsp+190h+var_130], eax
0x180045898  call    cs:__imp_SelectObject
0x18004589e  mov     rdx, [rdi+678h]; h
0x1800458a5  mov     rcx, rsi; hdc
0x1800458a8  mov     [rbp+90h+var_108], rax
0x1800458ac  call    cs:__imp_SelectObject
0x1800458b2  mov     ecx, [r15]
0x1800458b5  lea     rdx, [rbp+90h+rect]; lprect
0x1800458b9  movups  xmm0, xmmword ptr [rdi+7E8h]
0x1800458c0  lea     rbx, [rdi+6A0h]
0x1800458c7  movaps  xmmword ptr [rbp+90h+rect.left], xmm0
0x1800458cb  add     [rbp+90h+rect.right], ecx
0x1800458ce  movd    eax, xmm0
0x1800458d2  add     eax, ecx
0x1800458d4  mov     rcx, rsi; hdc
0x1800458d7  mov     [rbp+90h+rect.left], eax
0x1800458da  mov     eax, [r15+4]
0x1800458de  add     [rbp+90h+rect.top], eax
0x1800458e1  add     [rbp+90h+rect.bottom], eax
0x1800458e4  call    cs:__imp_RectVisible
0x1800458ea  test    eax, eax
0x1800458ec  jz      loc_18004597A
0x1800458f2  mov     r8d, [rbx]; color
0x1800458f5  lea     rdx, [rbp+90h+rect]; lprect
0x1800458f9  mov     rcx, rsi; hdc
0x1800458fc  call    FillRectClr
0x180045901  mov     edx, [rdi+6A4h]; color
0x180045907  mov     rcx, rsi; hdc
0x18004590a  call    cs:__imp_SetTextColor
0x180045910  mov     rdx, [rdi+690h]; h
0x180045917  mov     rcx, rsi; hdc
0x18004591a  call    cs:__imp_SelectObject
0x180045920  mov     eax, dword ptr [rbp+90h+arg_20]
0x180045926  lea     r8, [rbp+90h+String]
0x18004592a  lea     rdx, [rbp+90h+var_E0]
0x18004592e  mov     word ptr [rbp+90h+var_E0], ax
0x180045932  mov     rcx, rdi
0x180045935  mov     word ptr [rbp+90h+var_E0+2], r13w
0x18004593a  mov     qword ptr [rsp+190h+format], r12
0x18004593f  call    MCGetMonthFormat
0x180045944  lea     rcx, [rbp+90h+String]; lpString
0x180045948  call    cs:__imp_lstrlenW
0x18004594e  lea     r9, [rbp+90h+rect]; lprc
0x180045952  mov     [rsp+190h+format], 925h; format
0x18004595a  mov     r8d, eax; cchText
0x18004595d  lea     rdx, [rbp+90h+String]; lpchText
0x180045961  mov     rcx, rsi; hdc
0x180045964  call    cs:__imp_DrawTextW
0x18004596a  mov     rdx, [rdi+688h]; h
0x180045971  mov     rcx, rsi; hdc
0x180045974  call    cs:__imp_SelectObject
0x18004597a  mov     edx, [rbx]; color
0x18004597c  mov     rcx, rsi; hdc
0x18004597f  call    cs:__imp_SetTextColor
0x180045985  mov     ecx, [r15]
0x180045988  lea     rdx, [rbp+90h+rect]; lprect
0x18004598c  movups  xmm0, xmmword ptr [rdi+7F8h]
0x180045993  movaps  xmmword ptr [rbp+90h+rect.left], xmm0
0x180045997  add     [rbp+90h+rect.right], ecx
0x18004599a  movd    eax, xmm0
0x18004599e  add     eax, ecx
0x1800459a0  mov     rcx, rsi; hdc
0x1800459a3  mov     [rbp+90h+rect.left], eax
0x1800459a6  mov     eax, [r15+4]
0x1800459aa  add     [rbp+90h+rect.top], eax
0x1800459ad  add     [rbp+90h+rect.bottom], eax
0x1800459b0  call    cs:__imp_RectVisible
0x1800459b6  mov     ebx, 1
0x1800459bb  test    eax, eax
0x1800459bd  jz      loc_180045A7F
0x1800459c3  mov     r8d, [rbp+90h+rect.bottom]
0x1800459c7  xor     r9d, r9d; lppt
0x1800459ca  mov     edx, [rbp+90h+rect.left]
0x1800459cd  dec     r8d; y
0x1800459d0  add     edx, 4; x
0x1800459d3  mov     rcx, rsi; hdc
0x1800459d6  call    cs:__imp_MoveToEx
0x1800459dc  mov     r8d, [rbp+90h+rect.bottom]
0x1800459e0  mov     rcx, rsi; hdc
0x1800459e3  mov     edx, [rbp+90h+rect.right]
0x1800459e6  dec     r8d; y
0x1800459e9  add     edx, 0FFFFFFFCh; x
0x1800459ec  call    cs:__imp_LineTo
0x1800459f2  mov     ecx, [rdi+6B0h]
0x1800459f8  mov     r14d, r12d
0x1800459fb  add     ecx, [rbp+90h+rect.left]
0x1800459fe  mov     [rbp+90h+rect.right], ecx
0x180045a01  mov     ecx, [rdi+5BCh]
0x180045a07  mov     eax, 92492493h
0x180045a0c  add     ecx, r14d
0x180045a0f  imul    ecx
0x180045a11  add     edx, ecx
0x180045a13  sar     edx, 2
0x180045a16  mov     eax, edx
0x180045a18  shr     eax, 1Fh
0x180045a1b  add     edx, eax
0x180045a1d  imul    eax, edx, 7
0x180045a20  sub     ecx, eax
0x180045a22  movsxd  rax, ecx
0x180045a25  lea     rcx, [rdi+520h]
0x180045a2c  imul    rbx, rax, 16h
0x180045a30  add     rcx, rbx; lpString
0x180045a33  call    cs:__imp_lstrlenW
0x180045a39  lea     rdx, [rdi+520h]
0x180045a40  mov     [rsp+190h+format], 825h; format
0x180045a48  add     rdx, rbx; lpchText
0x180045a4b  lea     r9, [rbp+90h+rect]; lprc
0x180045a4f  mov     r8d, eax; cchText
0x180045a52  mov     rcx, rsi; hdc
0x180045a55  call    cs:__imp_DrawTextW
0x180045a5b  mov     eax, [rdi+6B0h]
0x180045a61  inc     r14d
0x180045a64  add     [rbp+90h+rect.left], eax
0x180045a67  add     [rbp+90h+rect.right], eax
0x180045a6a  cmp     r14d, 7
0x180045a6e  jl      short loc_180045A01
0x180045a70  mov     r14d, [rsp+190h+var_158]
0x180045a75  mov     ebx, 1
0x180045a7a  mov     r13d, [rsp+190h+var_160]
0x180045a7f  lea     r9d, [r14+1]
0x180045a83  movsxd  rax, r14d
0x180045a86  mov     r11d, [rdi+rax*4+874h]
0x180045a8e  mov     r10d, [rdi+rax*4+8ACh]
0x180045a96  mov     [rsp+190h+var_150], r11d
0x180045a9b  cmp     [rbp+90h+arg_38], r12d
0x180045aa2  jz      short loc_180045AAC
0x180045aa4  mov     r12d, 6
0x180045aaa  jmp     short loc_180045ADA
0x180045aac  movsxd  rax, r9d
0x180045aaf  mov     r8d, [rdi+rax*4+874h]
0x180045ab7  mov     eax, 92492493h
0x180045abc  sub     r8d, r10d
0x180045abf  add     r8d, 6
0x180045ac3  add     r8d, r11d
0x180045ac6  imul    r8d
0x180045ac9  lea     r12d, [r8+rdx]
0x180045acd  sar     r12d, 2
0x180045ad1  mov     eax, r12d
0x180045ad4  shr     eax, 1Fh
0x180045ad7  add     r12d, eax
0x180045ada  mov     r14d, dword ptr [rbp+90h+arg_20]
0x180045ae1  mov     eax, r9d
0x180045ae4  mov     edx, 0Ch
0x180045ae9  cmp     r10d, r11d
0x180045aec  jz      short loc_180045B1C
0x180045aee  lea     ecx, [r13-1]
0x180045af2  mov     [rsp+190h+var_15C], 0
0x180045afa  test    ecx, ecx
0x180045afc  lea     eax, [r14-1]
0x180045b00  mov     ebx, ecx
0x180045b02  lea     r13d, [r10+1]
0x180045b06  cmovg   eax, r14d
0x180045b0a  cmovle  ebx, edx
0x180045b0d  mov     [rsp+190h+var_160], ebx
0x180045b11  mov     r14d, eax
0x180045b14  mov     dword ptr [rbp+90h+arg_20], eax
0x180045b1a  jmp     short loc_180045B39
0x180045b1c  cdqe
0x180045b1e  mov     r13d, ebx
0x180045b21  mov     [rsp+190h+var_15C], ebx
0x180045b25  mov     ebx, [rsp+190h+var_160]
0x180045b29  mov     [rsp+190h+var_158], r9d
0x180045b2e  mov     eax, [rdi+rax*4+874h]
0x180045b35  mov     [rsp+190h+var_150], eax
0x180045b39  test    byte ptr [rdi+10h], 4
0x180045b3d  jz      loc_180045CD5
0x180045b43  mov     ecx, [r15]
0x180045b46  movups  xmm0, xmmword ptr [rdi+808h]
0x180045b4d  movaps  xmmword ptr [rbp+90h+rect.left], xmm0
0x180045b51  mov     edx, [rbp+90h+rect.top]
0x180045b54  add     edx, [r15+4]
0x180045b58  add     [rbp+90h+rect.right], ecx
0x180045b5b  movd    eax, xmm0
0x180045b5f  mov     [rbp+90h+rect.top], edx
0x180045b62  add     eax, ecx
0x180045b64  mov     rcx, rsi; hdc
0x180045b67  mov     [rbp+90h+rect.left], eax
0x180045b6a  mov     eax, r12d
0x180045b6d  imul    eax, [rdi+6B4h]
0x180045b74  add     eax, edx
0x180045b76  lea     rdx, [rbp+90h+rect]; lprect
0x180045b7a  mov     [rbp+90h+rect.bottom], eax
0x180045b7d  call    cs:__imp_RectVisible
0x180045b83  test    eax, eax
0x180045b85  jz      loc_180045CD5
0x180045b8b  mov     r8d, [rbp+90h+rect.top]
0x180045b8f  xor     r9d, r9d; lppt
0x180045b92  mov     edx, [rbp+90h+rect.right]
0x180045b95  add     r8d, 4; y
0x180045b99  dec     edx; x
0x180045b9b  mov     rcx, rsi; hdc
0x180045b9e  call    cs:__imp_MoveToEx
0x180045ba4  mov     r8d, [rbp+90h+rect.bottom]
0x180045ba8  mov     rcx, rsi; hdc
0x180045bab  mov     edx, [rbp+90h+rect.right]
0x180045bae  add     r8d, 0FFFFFFFCh; y
0x180045bb2  dec     edx; x
0x180045bb4  call    cs:__imp_LineTo
0x180045bba  mov     r8d, [rdi+5C0h]
0x180045bc1  lea     rcx, [rbp+90h+var_E0]
0x180045bc5  mov     edx, [rdi+5BCh]
0x180045bcb  mov     word ptr [rbp+90h+var_E0], r14w
0x180045bd0  mov     word ptr [rbp+90h+var_E0+2], bx
0x180045bd4  mov     word ptr [rbp+90h+var_E0+6], r13w
0x180045bd9  call    GetWeekNumber
0x180045bde  mov     ecx, [rdi+6B4h]
0x180045be4  xor     r14d, r14d
0x180045be7  add     ecx, [rbp+90h+rect.top]
0x180045bea  mov     ebx, eax
0x180045bec  mov     [rbp+90h+rect.bottom], ecx
0x180045bef  test    r12d, r12d
0x180045bf2  jle     loc_180045CD5
0x180045bf8  lea     r15d, [r14+1]
0x180045bfc  mov     r9d, ebx
0x180045bff  lea     r8, aD; "%d"
0x180045c06  mov     edx, 40h ; '@'; unsigned __int64
0x180045c0b  lea     rcx, [rbp+90h+String]; Buffer
0x180045c0f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045c14  xor     r8d, r8d
0x180045c17  mov     [rsp+190h+format], 925h; format
0x180045c1f  cmp     ebx, 9
0x180045c22  lea     r9, [rbp+90h+rect]; lprc
0x180045c26  lea     rdx, [rbp+90h+String]; lpchText
0x180045c2a  mov     rcx, rsi; hdc
0x180045c2d  setnle  r8b
0x180045c31  add     r8d, r15d; cchText
0x180045c34  call    cs:__imp_DrawTextW
0x180045c3a  mov     eax, [rdi+6B4h]
0x180045c40  mov     ebx, 7
0x180045c45  add     [rbp+90h+rect.top], eax
0x180045c48  add     [rbp+90h+rect.bottom], eax
0x180045c4b  movzx   edx, word ptr [rbp+90h+var_E0+2]
0x180045c4f  movzx   ecx, word ptr [rbp+90h+var_E0]
0x180045c53  call    GetDaysForMonth
0x180045c58  movzx   ecx, word ptr [rbp+90h+var_E0+6]
0x180045c5c  mov     r11d, eax
0x180045c5f  lea     eax, [rcx+7]
0x180045c62  jmp     short loc_180045CA0
0x180045c64  movzx   eax, cx
0x180045c67  lea     rdx, [rbp+90h+var_E0]
0x180045c6b  sub     eax, r11d
0x180045c6e  mov     word ptr [rbp+90h+var_E0+6], r15w
0x180045c73  dec     eax
0x180045c75  lea     rcx, [rbp+90h+var_E0]
0x180045c79  mov     r9d, 2
0x180045c7f  mov     r8d, r15d
0x180045c82  add     ebx, eax
0x180045c84  call    IncrSystemTime
0x180045c89  movzx   edx, word ptr [rbp+90h+var_E0+2]
0x180045c8d  movzx   ecx, word ptr [rbp+90h+var_E0]
0x180045c91  call    GetDaysForMonth
0x180045c96  movzx   ecx, word ptr [rbp+90h+var_E0+6]
0x180045c9a  mov     r11d, eax
0x180045c9d  lea     eax, [rbx+rcx]
0x180045ca0  cmp     eax, r11d
0x180045ca3  jg      short loc_180045C64
0x180045ca5  mov     r8d, [rdi+5C0h]
0x180045cac  add     cx, bx
0x180045caf  mov     edx, [rdi+5BCh]
0x180045cb5  mov     word ptr [rbp+90h+var_E0+6], cx
0x180045cb9  lea     rcx, [rbp+90h+var_E0]
  ... truncated ...
```
