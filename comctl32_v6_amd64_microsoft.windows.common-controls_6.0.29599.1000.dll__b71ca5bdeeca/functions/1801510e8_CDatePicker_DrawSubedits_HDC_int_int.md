# CDatePicker::_DrawSubedits(HDC__ *,int,int)

- ea: `0x1801510e8`
- end: `0x1801514d9`
- name: `?_DrawSubedits@CDatePicker@@AEAAXPEAUHDC__@@HH@Z`
- size: `1009`
- prototype: `void __fastcall(CDatePicker *__hidden this, HDC hdc, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180153348`

## callees

- `0x180007fc4`
- `0x18009df50`
- `0x180114520`
- `0x1801510e8`
- `0x1801519b4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180151299`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1801512ab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180151299`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1801512ab`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x180151306`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x180151325`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x180151360`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x180151306`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x180151325`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x180151360`
- `GDI32!IntersectClipRect` at `0x180151165`
- `GDI32!IntersectClipRect` at `0x180151165`
- `GDI32!SetBkColor` at `0x18015117b`
- `GDI32!SetBkColor` at `0x18015117b`
- `GDI32!SetBkMode` at `0x1801511f5`
- `GDI32!SetBkMode` at `0x180151214`
- `GDI32!SetBkMode` at `0x180151229`
- `GDI32!SetBkMode` at `0x1801511f5`
- `GDI32!SetBkMode` at `0x180151214`
- `GDI32!SetBkMode` at `0x180151229`
- `GDI32!SetTextColor` at `0x18015123f`
- `GDI32!SetTextColor` at `0x18015123f`
- `GDI32!SelectObject` at `0x180151139`
- `GDI32!SelectObject` at `0x1801514a9`
- `GDI32!SelectObject` at `0x180151139`
- `GDI32!SelectObject` at `0x1801514a9`
- `GDI32!SelectClipRgn` at `0x18015149b`
- `GDI32!SelectClipRgn` at `0x18015149b`
- `USER32!DrawTextW` at `0x180151483`
- `USER32!DrawTextW` at `0x180151483`
- `USER32!OffsetRect` at `0x1801511dc`
- `USER32!OffsetRect` at `0x1801511dc`
- `USER32!GetSysColor` at `0x180151170`
- `USER32!GetSysColor` at `0x180151234`
- `USER32!GetSysColor` at `0x1801513fb`
- `USER32!GetSysColor` at `0x180151170`
- `USER32!GetSysColor` at `0x180151234`
- `USER32!GetSysColor` at `0x1801513fb`
- `UxTheme!DrawThemeText` at `0x180151457`
- `UxTheme!DrawThemeText` at `0x180151457`

## pseudocode

```c
void __fastcall CDatePicker::_DrawSubedits(CDatePicker *this, HDC hdc, int a3, int a4)
{
  void *v5; // rdx
  int v7; // r12d
  COLORREF SysColor; // eax
  int v10; // r15d
  int v11; // r14d
  int v12; // edx
  __int64 v13; // rbx
  int v14; // ecx
  COLORREF v15; // eax
  unsigned int v16; // r9d
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  bool v24; // zf
  int v25; // eax
  int v26; // ecx
  bool v27; // zf
  bool v28; // sf
  bool v29; // of
  int v30; // eax
  int v31; // ecx
  int v32; // ecx
  int v33; // r13d
  unsigned int v34; // r9d
  __int64 v35; // rax
  int v36; // ecx
  unsigned __int16 *v37; // rax
  __int64 v38; // rdx
  unsigned __int16 *v39; // r15
  __int64 v40; // r9
  COLORREF v41; // eax
  int iStateId; // [rsp+50h] [rbp-B0h]
  int v43; // [rsp+54h] [rbp-ACh]
  int v44; // [rsp+58h] [rbp-A8h]
  HGDIOBJ h; // [rsp+60h] [rbp-A0h]
  struct tagRECT rc; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v48[12]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v49[128]; // [rsp+90h] [rbp-70h] BYREF

  v5 = (void *)*((_QWORD *)this + 81);
  v7 = a4;
  v49[0] = 0;
  h = SelectObject(hdc, v5);
  IntersectClipRect(
    hdc,
    *((_DWORD *)this + 164),
    *((_DWORD *)this + 165),
    *((_DWORD *)this + 166),
    *((_DWORD *)this + 167));
  SysColor = GetSysColor(13);
  SetBkColor(hdc, SysColor);
  if ( a3 )
    v10 = *((_DWORD *)this + 169);
  else
    v10 = -1;
  v11 = 0;
  v43 = v10;
  while ( v11 < *((_DWORD *)this + 170) )
  {
    v12 = *((_DWORD *)this + 168);
    v13 = 80LL * v11;
    rc = *(struct tagRECT *)(v13 + *((_QWORD *)this + 87) + 4);
    if ( v12 )
      OffsetRect(&rc, -v12, 0);
    if ( v7 )
    {
      if ( v10 == v11 )
      {
        iStateId = 3;
        SetBkMode(hdc, 2);
        v14 = 14;
      }
      else
      {
        iStateId = 1;
        SetBkMode(hdc, 1);
        v14 = 8;
      }
    }
    else
    {
      iStateId = 2;
      SetBkMode(hdc, 1);
      v14 = 17;
    }
    v15 = GetSysColor(v14);
    SetTextColor(hdc, v15);
    if ( v11 != *((_DWORD *)this + 169) || (v17 = *((_QWORD *)this + 87), !*(_DWORD *)(v13 + v17 + 48)) )
    {
      v39 = CDatePicker::_FormatSubed(this, (struct SUBEDIT *)(v13 + *((_QWORD *)this + 87)), v49, v16);
      goto LABEL_37;
    }
    v18 = *(_DWORD *)(v13 + v17);
    if ( v18 > 7 )
    {
      v31 = v18 - 8;
      if ( !v31 )
      {
        v26 = 1;
        goto LABEL_34;
      }
      v32 = v31 - 1;
      if ( !v32 )
        goto LABEL_35;
      v24 = v32 == 1;
      goto LABEL_29;
    }
    if ( v18 != 7 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( !v20 || (v21 = v20 - 1) == 0 )
        {
LABEL_35:
          v40 = *((_QWORD *)this + 87);
          v48[0] = 0;
          StringCchPrintfW(v48, 0xAu, L"%%0%dd", *(unsigned int *)(v13 + v40 + 48));
          StringCchPrintfW(v49, 0x80u, v48, *(unsigned int *)(v13 + *((_QWORD *)this + 87) + 52));
          v39 = v49;
          goto LABEL_37;
        }
        v22 = v21 - 1;
        if ( !v22 )
        {
          v30 = lstrlenW(*(LPCWSTR *)(v13 + v17 + 64));
          v26 = 0;
          v29 = __OFSUB__(v30, 2);
          v27 = v30 == 2;
          v28 = v30 - 2 < 0;
LABEL_25:
          LOBYTE(v26) = v28 ^ v29 | v27;
LABEL_34:
          if ( v26 )
            goto LABEL_35;
          goto LABEL_30;
        }
        v23 = v22 - 1;
        if ( !v23 )
        {
          v25 = lstrlenW(*(LPCWSTR *)(v13 + v17 + 64));
          v26 = 0;
          v29 = __OFSUB__(v25, 4);
          v27 = v25 == 4;
          v28 = v25 - 4 < 0;
          goto LABEL_25;
        }
        v24 = v23 == 1;
LABEL_29:
        if ( v24 )
          goto LABEL_35;
      }
    }
LABEL_30:
    v44 = *((_DWORD *)this + 109);
    v33 = **(_DWORD **)(v13 + *((_QWORD *)this + 87) + 24);
    *((_DWORD *)this + 109) = 1;
    UpdateCalendarDayOfWeek((char *)this + 420);
    v35 = *((_QWORD *)this + 87);
    v36 = *(_DWORD *)(v13 + v35 + 52);
    if ( v36 )
    {
      **(_DWORD **)(v13 + v35 + 24) = v36;
      UpdateCalendarDayOfWeek((char *)this + 420);
    }
    v37 = CDatePicker::_FormatSubed(this, (struct SUBEDIT *)(v13 + *((_QWORD *)this + 87)), v49, v34);
    v38 = *((_QWORD *)this + 87);
    v39 = v37;
    *((_DWORD *)this + 109) = v44;
    **(_DWORD **)(v13 + v38 + 24) = v33;
    UpdateCalendarDayOfWeek((char *)this + 420);
    v7 = a4;
LABEL_37:
    if ( *((_QWORD *)this + 76) )
    {
      if ( v11 == *((_DWORD *)this + 169) )
      {
        v41 = GetSysColor(13);
        FillRectClr(hdc, &rc, v41);
      }
      DrawThemeText(
        *((HTHEME *)this + 76),
        hdc,
        1,
        iStateId,
        v39,
        -1,
        *(_DWORD *)(v13 + *((_QWORD *)this + 87) + 56) | 0x820,
        0,
        &rc);
    }
    else
    {
      DrawTextW(hdc, v39, -1, &rc, *(_DWORD *)(v13 + *((_QWORD *)this + 87) + 56) | 0x820);
    }
    v10 = v43;
    ++v11;
  }
  SelectClipRgn(hdc, 0);
  SelectObject(hdc, h);
}

```

## disassembly

```asm
0x1801510e8  mov     [rsp-8+arg_10], rbx
0x1801510ed  push    rbp
0x1801510ee  push    rsi
0x1801510ef  push    rdi
0x1801510f0  push    r12
0x1801510f2  push    r13
0x1801510f4  push    r14
0x1801510f6  push    r15
0x1801510f8  lea     rbp, [rsp-0A0h]
0x180151100  sub     rsp, 1A0h
0x180151107  mov     rax, cs:__security_cookie
0x18015110e  xor     rax, rsp
0x180151111  mov     [rbp+0D0h+var_40], rax
0x180151118  mov     rsi, rdx
0x18015111b  mov     [rsp+1D0h+var_174], r9d
0x180151120  mov     rdx, [rcx+288h]; h
0x180151127  mov     rdi, rcx
0x18015112a  xor     eax, eax
0x18015112c  mov     rcx, rsi; hdc
0x18015112f  mov     r12d, r9d
0x180151132  mov     [rbp+0D0h+var_140], ax
0x180151136  mov     ebx, r8d
0x180151139  call    cs:__imp_SelectObject
0x18015113f  mov     ecx, [rdi+29Ch]
0x180151145  mov     r9d, [rdi+298h]; right
0x18015114c  mov     r8d, [rdi+294h]; top
0x180151153  mov     edx, [rdi+290h]; left
0x180151159  mov     [rsp+1D0h+bottom], ecx; bottom
0x18015115d  mov     rcx, rsi; hdc
0x180151160  mov     [rsp+1D0h+h], rax
0x180151165  call    cs:__imp_IntersectClipRect
0x18015116b  mov     ecx, 0Dh; nIndex
0x180151170  call    cs:__imp_GetSysColor
0x180151176  mov     edx, eax; color
0x180151178  mov     rcx, rsi; hdc
0x18015117b  call    cs:__imp_SetBkColor
0x180151181  test    ebx, ebx
0x180151183  jnz     short loc_18015118B
0x180151185  or      r15d, 0FFFFFFFFh
0x180151189  jmp     short loc_180151192
0x18015118b  mov     r15d, [rdi+2A4h]
0x180151192  xor     r14d, r14d
0x180151195  mov     [rsp+1D0h+var_17C], r15d
0x18015119a  lea     r13d, [r14+1]
0x18015119e  cmp     r14d, [rdi+2A8h]
0x1801511a5  jge     loc_180151496
0x1801511ab  mov     edx, [rdi+2A0h]
0x1801511b1  movsxd  rax, r14d
0x1801511b4  lea     rbx, [rax+rax*4]
0x1801511b8  mov     rax, [rdi+2B8h]
0x1801511bf  shl     rbx, 4
0x1801511c3  movups  xmm0, xmmword ptr [rbx+rax+4]
0x1801511c8  movdqu  xmmword ptr [rsp+1D0h+rc.left], xmm0
0x1801511ce  test    edx, edx
0x1801511d0  jz      short loc_1801511E2
0x1801511d2  neg     edx; dx
0x1801511d4  lea     rcx, [rsp+1D0h+rc]; lprc
0x1801511d9  xor     r8d, r8d; dy
0x1801511dc  call    cs:__imp_OffsetRect
0x1801511e2  mov     rcx, rsi; hdc
0x1801511e5  test    r12d, r12d
0x1801511e8  jnz     short loc_180151202
0x1801511ea  mov     edx, r13d; mode
0x1801511ed  mov     [rsp+1D0h+iStateId], 2
0x1801511f5  call    cs:__imp_SetBkMode
0x1801511fb  lea     ecx, [r12+11h]
0x180151200  jmp     short loc_180151234
0x180151202  cmp     r15d, r14d
0x180151205  jnz     short loc_180151221
0x180151207  mov     edx, 2; mode
0x18015120c  mov     [rsp+1D0h+iStateId], 3
0x180151214  call    cs:__imp_SetBkMode
0x18015121a  mov     ecx, 0Eh
0x18015121f  jmp     short loc_180151234
0x180151221  mov     edx, r13d; mode
0x180151224  mov     [rsp+1D0h+iStateId], r13d
0x180151229  call    cs:__imp_SetBkMode
0x18015122f  mov     ecx, 8; nIndex
0x180151234  call    cs:__imp_GetSysColor
0x18015123a  mov     edx, eax; color
0x18015123c  mov     rcx, rsi; hdc
0x18015123f  call    cs:__imp_SetTextColor
0x180151245  cmp     r14d, [rdi+2A4h]
0x18015124c  jnz     loc_1801513CA
0x180151252  mov     rdx, [rdi+2B8h]
0x180151259  cmp     dword ptr [rbx+rdx+30h], 0
0x18015125e  jz      loc_1801513CA
0x180151264  mov     ecx, [rbx+rdx]
0x180151267  cmp     ecx, 7
0x18015126a  jg      short loc_1801512BE
0x18015126c  jz      short loc_1801512D9
0x18015126e  sub     ecx, 1
0x180151271  jz      short loc_1801512D9
0x180151273  sub     ecx, 1
0x180151276  jz      loc_18015137E
0x18015127c  sub     ecx, 1
0x18015127f  jz      loc_18015137E
0x180151285  sub     ecx, 1
0x180151288  jz      short loc_1801512A6
0x18015128a  sub     ecx, 1
0x18015128d  jz      short loc_180151294
0x18015128f  cmp     ecx, 1
0x180151292  jmp     short loc_1801512D3
0x180151294  mov     rcx, [rbx+rdx+40h]; lpString
0x180151299  call    cs:__imp_lstrlenW
0x18015129f  xor     ecx, ecx
0x1801512a1  cmp     eax, 4
0x1801512a4  jmp     short loc_1801512B6
0x1801512a6  mov     rcx, [rbx+rdx+40h]; lpString
0x1801512ab  call    cs:__imp_lstrlenW
0x1801512b1  xor     ecx, ecx
0x1801512b3  cmp     eax, 2
0x1801512b6  setle   cl
0x1801512b9  jmp     loc_180151376
0x1801512be  sub     ecx, 8
0x1801512c1  jz      loc_180151373
0x1801512c7  sub     ecx, 1
0x1801512ca  jz      loc_18015137E
0x1801512d0  sub     ecx, 1
0x1801512d3  jz      loc_18015137E
0x1801512d9  mov     rax, [rdi+2B8h]
0x1801512e0  lea     r12, [rdi+1A4h]
0x1801512e7  mov     rcx, [rbx+rax+18h]
0x1801512ec  mov     eax, [rdi+1B4h]
0x1801512f2  mov     [rsp+1D0h+var_178], eax
0x1801512f6  mov     r13d, [rcx]
0x1801512f9  mov     rcx, r12
0x1801512fc  mov     dword ptr [rdi+1B4h], 1
0x180151306  call    cs:__imp_UpdateCalendarDayOfWeek
0x18015130c  mov     rax, [rdi+2B8h]
0x180151313  mov     ecx, [rbx+rax+34h]
0x180151317  test    ecx, ecx
0x180151319  jz      short loc_18015132B
0x18015131b  mov     rax, [rbx+rax+18h]
0x180151320  mov     [rax], ecx
0x180151322  mov     rcx, r12
0x180151325  call    cs:__imp_UpdateCalendarDayOfWeek
0x18015132b  mov     rdx, [rdi+2B8h]
0x180151332  lea     r8, [rbp+0D0h+var_140]; unsigned __int16 *
0x180151336  add     rdx, rbx; struct SUBEDIT *
0x180151339  mov     rcx, rdi; this
0x18015133c  call    ?_FormatSubed@CDatePicker@@AEAAPEAGPEAUSUBEDIT@@PEAGI@Z; CDatePicker::_FormatSubed(SUBEDIT *,ushort *,uint)
0x180151341  mov     rdx, [rdi+2B8h]
0x180151348  mov     r15, rax
0x18015134b  mov     eax, [rsp+1D0h+var_178]
0x18015134f  mov     rcx, r12
0x180151352  mov     [rdi+1B4h], eax
0x180151358  mov     r8, [rbx+rdx+18h]
0x18015135d  mov     [r8], r13d
0x180151360  call    cs:__imp_UpdateCalendarDayOfWeek
0x180151366  mov     r12d, [rsp+1D0h+var_174]
0x18015136b  mov     r13d, 1
0x180151371  jmp     short loc_1801513E3
0x180151373  mov     ecx, r13d
0x180151376  test    ecx, ecx
0x180151378  jz      loc_1801512D9
0x18015137e  mov     r9, [rdi+2B8h]
0x180151385  lea     r8, a0Dd; "%%0%dd"
0x18015138c  xor     eax, eax
0x18015138e  lea     rcx, [rsp+1D0h+var_158]; unsigned __int16 *
0x180151393  mov     [rsp+1D0h+var_158], ax
0x180151398  mov     r9d, [rbx+r9+30h]
0x18015139d  lea     edx, [rax+0Ah]; unsigned __int64
0x1801513a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801513a5  mov     r9, [rdi+2B8h]
0x1801513ac  lea     r8, [rsp+1D0h+var_158]; unsigned __int16 *
0x1801513b1  mov     edx, 80h; unsigned __int64
0x1801513b6  lea     rcx, [rbp+0D0h+var_140]; unsigned __int16 *
0x1801513ba  mov     r9d, [rbx+r9+34h]
0x1801513bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801513c4  lea     r15, [rbp+0D0h+var_140]
0x1801513c8  jmp     short loc_1801513E3
0x1801513ca  mov     rdx, [rdi+2B8h]
0x1801513d1  lea     r8, [rbp+0D0h+var_140]; unsigned __int16 *
0x1801513d5  add     rdx, rbx; struct SUBEDIT *
0x1801513d8  mov     rcx, rdi; this
0x1801513db  call    ?_FormatSubed@CDatePicker@@AEAAPEAGPEAUSUBEDIT@@PEAGI@Z; CDatePicker::_FormatSubed(SUBEDIT *,ushort *,uint)
0x1801513e0  mov     r15, rax
0x1801513e3  cmp     qword ptr [rdi+260h], 0
0x1801513eb  jz      short loc_18015145F
0x1801513ed  cmp     r14d, [rdi+2A4h]
0x1801513f4  jnz     short loc_180151411
0x1801513f6  mov     ecx, 0Dh; nIndex
0x1801513fb  call    cs:__imp_GetSysColor
0x180151401  lea     rdx, [rsp+1D0h+rc]; lprect
0x180151406  mov     rcx, rsi; hdc
0x180151409  mov     r8d, eax; color
0x18015140c  call    FillRectClr
0x180151411  mov     rax, [rdi+2B8h]
0x180151418  mov     r8d, r13d; iPartId
0x18015141b  mov     r9d, [rsp+1D0h+iStateId]; iStateId
0x180151420  mov     rdx, rsi; hdc
0x180151423  mov     ecx, [rbx+rax+38h]
0x180151427  lea     rax, [rsp+1D0h+rc]
0x18015142c  mov     [rsp+1D0h+pRect], rax; pRect
0x180151431  or      ecx, 820h
0x180151437  mov     [rsp+1D0h+dwTextFlags2], 0; dwTextFlags2
0x18015143f  mov     [rsp+1D0h+dwTextFlags], ecx; dwTextFlags
0x180151443  mov     rcx, [rdi+260h]; hTheme
0x18015144a  mov     [rsp+1D0h+cchText], 0FFFFFFFFh; cchText
0x180151452  mov     qword ptr [rsp+1D0h+bottom], r15; pszText
0x180151457  call    cs:__imp_DrawThemeText
0x18015145d  jmp     short loc_180151489
0x18015145f  mov     rax, [rdi+2B8h]
0x180151466  lea     r9, [rsp+1D0h+rc]; lprc
0x18015146b  or      r8d, 0FFFFFFFFh; cchText
0x18015146f  mov     rdx, r15; lpchText
0x180151472  mov     ecx, [rbx+rax+38h]
0x180151476  or      ecx, 820h
0x18015147c  mov     [rsp+1D0h+bottom], ecx; format
0x180151480  mov     rcx, rsi; hdc
0x180151483  call    cs:__imp_DrawTextW
0x180151489  mov     r15d, [rsp+1D0h+var_17C]
0x18015148e  add     r14d, r13d
0x180151491  jmp     loc_18015119E
0x180151496  xor     edx, edx; hrgn
0x180151498  mov     rcx, rsi; hdc
0x18015149b  call    cs:__imp_SelectClipRgn
0x1801514a1  mov     rdx, [rsp+1D0h+h]; h
0x1801514a6  mov     rcx, rsi; hdc
0x1801514a9  call    cs:__imp_SelectObject
0x1801514af  mov     rcx, [rbp+0D0h+var_40]
0x1801514b6  xor     rcx, rsp; StackCookie
0x1801514b9  call    __security_check_cookie
0x1801514be  mov     rbx, [rsp+1D0h+arg_10]
0x1801514c6  add     rsp, 1A0h
0x1801514cd  pop     r15
0x1801514cf  pop     r14
0x1801514d1  pop     r13
0x1801514d3  pop     r12
0x1801514d5  pop     rdi
0x1801514d6  pop     rsi
0x1801514d7  pop     rbp
0x1801514d8  retn
```
