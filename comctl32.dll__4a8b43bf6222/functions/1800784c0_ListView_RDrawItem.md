# ListView_RDrawItem

- ea: `0x1800784c0`
- end: `0x180078bb4`
- name: `ListView_RDrawItem`
- size: `1780`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800526a8`

## callees

- `0x1800115f0`
- `0x180036e24`
- `0x180055de0`
- `0x1800563ec`
- `0x180056604`
- `0x18005dde0`
- `0x180073a44`
- `0x1800784c0`
- `0x180078bbc`
- `0x180078c50`
- `0x180078e98`
- `0x18008ea60`

## import_xrefs

- `GDI32!GetTextExtentPointW` at `0x1800789a0`
- `GDI32!GetTextExtentPointW` at `0x1800789a0`
- `GDI32!SelectObject` at `0x18007893c`
- `GDI32!SelectObject` at `0x180078955`
- `GDI32!SelectObject` at `0x180078a7d`
- `GDI32!SelectObject` at `0x18007893c`
- `GDI32!SelectObject` at `0x180078955`
- `GDI32!SelectObject` at `0x180078a7d`
- `USER32!GetSysColor` at `0x1800788f7`
- `USER32!GetSysColor` at `0x1800788f7`
- `USER32!SendMessageW` at `0x180078682`
- `USER32!SendMessageW` at `0x1800786ee`
- `USER32!SendMessageW` at `0x180078acd`
- `USER32!SendMessageW` at `0x180078b71`
- `USER32!SendMessageW` at `0x180078682`
- `USER32!SendMessageW` at `0x1800786ee`
- `USER32!SendMessageW` at `0x180078acd`
- `USER32!SendMessageW` at `0x180078b71`
- `USER32!SetRectEmpty` at `0x180078608`
- `USER32!SetRectEmpty` at `0x180078608`
- `USER32!UnionRect` at `0x180078824`
- `USER32!UnionRect` at `0x180078824`
- `USER32!GetDlgCtrlID` at `0x180078af4`
- `USER32!GetDlgCtrlID` at `0x180078af4`
- `USER32!FillRect` at `0x1800787d0`
- `USER32!FillRect` at `0x1800787d0`
- `USER32!IntersectRect` at `0x180078578`
- `USER32!IntersectRect` at `0x180078578`
- `USER32!DrawFocusRect` at `0x180078a1a`
- `USER32!DrawFocusRect` at `0x180078b86`
- `USER32!DrawFocusRect` at `0x180078a1a`
- `USER32!DrawFocusRect` at `0x180078b86`
- `USER32!OffsetRect` at `0x1800785d4`
- `USER32!OffsetRect` at `0x1800786af`
- `USER32!OffsetRect` at `0x1800786c1`
- `USER32!OffsetRect` at `0x1800785d4`
- `USER32!OffsetRect` at `0x1800786af`
- `USER32!OffsetRect` at `0x1800786c1`

## pseudocode

```c
__int64 __fastcall ListView_RDrawItem(_QWORD *a1)
{
  __int64 v1; // rsi
  const RECT *v3; // r8
  _DWORD *v5; // rax
  int v6; // r12d
  int v7; // ebx
  int v8; // r15d
  int v9; // r13d
  bool v10; // zf
  int v11; // r14d
  HWND v12; // rcx
  int v13; // ebx
  __int64 v14; // rcx
  unsigned __int8 v15; // al
  int v16; // r8d
  unsigned int v17; // r14d
  int v18; // edx
  unsigned int left; // ebx
  LONG right; // r12d
  HDC v21; // rcx
  __int16 v22; // r13
  LPARAM *v23; // r8
  int v24; // eax
  int v25; // ebx
  LONG v26; // edx
  LONG v27; // eax
  COLORREF v28; // ebx
  __int16 v29; // r12
  void *v30; // r13
  HGDIOBJ v31; // rax
  COLORREF color; // r15d
  HDC v33; // rcx
  int v34; // ebx
  HWND v35; // rcx
  unsigned int DlgCtrlID; // eax
  WPARAM v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  COLORREF v40; // [rsp+40h] [rbp-C0h]
  int v41; // [rsp+50h] [rbp-B0h]
  int dy; // [rsp+54h] [rbp-ACh]
  unsigned __int8 v43; // [rsp+58h] [rbp-A8h]
  int v44; // [rsp+5Ch] [rbp-A4h]
  int v45; // [rsp+60h] [rbp-A0h]
  LONG v46; // [rsp+64h] [rbp-9Ch]
  __int128 v47; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpString[2]; // [rsp+78h] [rbp-88h]
  __int128 v49; // [rsp+88h] [rbp-78h]
  __int64 v50; // [rsp+98h] [rbp-68h]
  LPARAM lParam[8]; // [rsp+A0h] [rbp-60h] BYREF
  LPARAM v52[10]; // [rsp+E0h] [rbp-20h] BYREF
  RECT rcSrc2; // [rsp+130h] [rbp+30h] BYREF
  LPARAM v54[2]; // [rsp+140h] [rbp+40h] BYREF
  struct tagRECT rc; // [rsp+150h] [rbp+50h] BYREF
  RECT rcSrc1; // [rsp+160h] [rbp+60h] BYREF
  struct tagRECT rcDst; // [rsp+170h] [rbp+70h] BYREF
  char v58; // [rsp+180h] [rbp+80h] BYREF

  v1 = *a1;
  v50 = 0;
  rc = 0;
  rcSrc2 = 0;
  rcSrc1 = 0;
  rcDst = 0;
  v47 = 0;
  *(_OWORD *)lpString = 0;
  v49 = 0;
  memset(lParam, 0, sizeof(lParam));
  ListView_RGetRects(v1, *((_DWORD *)a1 + 26), 0, 0, (__int64)&rcSrc1, 0);
  if ( rcSrc1.bottom <= *(_DWORD *)(v1 + 448) )
    return 1;
  v3 = (const RECT *)a1[2];
  if ( v3 )
  {
    if ( rcSrc1.top >= v3->bottom )
      return 0;
    if ( !IntersectRect(&rcDst, &rcSrc1, v3) )
      return 1;
  }
  if ( rcSrc1.top >= *(_DWORD *)(v1 + 168) )
    return 0;
  v5 = (_DWORD *)a1[1];
  v6 = 0;
  v7 = 0;
  v45 = 0;
  v8 = 0;
  v41 = 0;
  if ( v5 )
  {
    v9 = *v5 - rcSrc1.left;
    v44 = v9;
    dy = v5[1] - rcSrc1.top;
    OffsetRect(&rcSrc1, v9, dy);
  }
  else
  {
    v9 = 0;
    dy = 0;
    v44 = 0;
  }
  v10 = (*(_DWORD *)(v1 + 16) & 0x400) == 0;
  DWORD1(v47) = *((_DWORD *)a1 + 26);
  LODWORD(lpString[0]) = 0xFFFF;
  HIDWORD(v47) = 0;
  if ( !v10 )
    goto LABEL_12;
  SetRectEmpty(&rcDst);
  while ( v7 < *(_DWORD *)(v1 + 428) )
  {
    v8 = SendMessageW(*(HWND *)(v1 + 440), 0x120Fu, v7, 0);
LABEL_12:
    DWORD2(v47) = v8;
    *(_QWORD *)&v49 = -4294967036LL;
    lpString[1] = (LPCWSTR)&v58;
    LODWORD(v47) = v8 != 0 ? 11 : 27;
    ListView_OnGetItem(v1, &v47);
    if ( !v8 && (*(_DWORD *)(v1 + 16) & 0x400) != 0 )
    {
      memset(v52, 0, 0x40u);
      v35 = *(HWND *)v1;
      LODWORD(v52[0]) = 102;
      DlgCtrlID = GetDlgCtrlID(v35);
      LODWORD(v52[1]) = *((_DWORD *)a1 + 26);
      v52[3] = *(_QWORD *)v1;
      v52[4] = a1[10];
      v37 = DlgCtrlID;
      v52[5] = *(_QWORD *)&rcSrc1.left;
      v38 = a1[4];
      v52[6] = *(_QWORD *)&rcSrc1.right;
      HIDWORD(v52[0]) = v37;
      HIDWORD(v52[1]) = 1;
      if ( v38 )
        v52[7] = *(_QWORD *)(v38 + 32);
      v39 = v52[2];
      if ( (BYTE12(v47) & 1) != 0 )
      {
        v39 = LODWORD(v52[2]) | 0x10;
        LODWORD(v52[2]) |= 0x10u;
      }
      if ( (BYTE12(v47) & 2) != 0 )
        LODWORD(v52[2]) = v39 | 1;
      SendMessageW(*(HWND *)(v1 + 8), 0x2Bu, v37, (LPARAM)v52);
      return 1;
    }
    v11 = *((_DWORD *)a1 + 6);
    LODWORD(lParam[0]) = 5;
    SendMessageW(*(HWND *)(v1 + 440), 0x120Bu, v8, (LPARAM)lParam);
    ListView_RGetRectsEx(v1, *((_DWORD *)a1 + 26), v8, (unsigned int)&rc, (__int64)&rcSrc2);
    OffsetRect(&rc, v9, dy);
    OffsetRect(&rcSrc2, v9, dy);
    if ( (a1[5] & 0x20) != 0 )
    {
      v12 = *(HWND *)(v1 + 440);
      v13 = *((_DWORD *)a1 + 28);
      *(_OWORD *)v54 = 0;
      SendMessageW(v12, 0x1207u, v8, (LPARAM)v54);
      v14 = *a1;
      *((_DWORD *)a1 + 22) = v54[0];
      *((_DWORD *)a1 + 24) = v54[1];
      *((_DWORD *)a1 + 34) = v8;
      v15 = CICustomDrawNotify(v14, 196609, a1 + 6);
      v16 = *((_DWORD *)a1 + 28);
      *((_DWORD *)a1 + 28) = v13;
      v43 = v15;
      if ( (v15 & 4) != 0 )
        goto LABEL_80;
      v7 = v41;
      v17 = v11 & 0xFFFFFF87;
      v18 = v17 | 8;
      if ( (v16 & 0x10) == 0 )
        v18 = v17;
      if ( (v16 & 1) != 0 )
      {
        v11 = v18 | (16 * (((*(_DWORD *)(*a1 + 72LL) & 1) == 0) + 1));
        if ( *(_DWORD *)(*a1 + 532LL) == *((_DWORD *)a1 + 26) )
          v11 |= 0x40u;
      }
      else
      {
        v11 = v18;
      }
    }
    else
    {
      v43 = 0;
    }
    if ( v8 )
    {
      if ( DWORD1(v49) == -1 )
        goto LABEL_32;
      rcSrc2.left += *(_DWORD *)(v1 + 240);
    }
    if ( DWORD1(v49) != -1 && (*(_BYTE *)(v1 + 76) & 0x20) != 0 && v7 )
    {
      left = rc.left;
      right = rc.right;
      if ( !v8 )
        rc.left = rc.left - *(_DWORD *)(v1 + 488) - g_cxEdge;
      v21 = (HDC)a1[10];
      rc.right = rcSrc2.right;
      FillRect(v21, &rc, *(HBRUSH *)(v1 + 112));
      rc.left = left;
      rc.right = right;
      goto LABEL_33;
    }
LABEL_32:
    left = rc.left;
LABEL_33:
    v22 = ListView_DrawImageEx(v1, &v47, a1[10], left, rc.top, v11, rcSrc2.right);
    if ( (*(_BYTE *)(v1 + 76) & 0x20) != 0 && (v11 & 8) != 0 )
      UnionRect(&rcDst, &rcDst, &rcSrc2);
    if ( lpString[1] )
    {
      v46 = rcSrc2.right;
      if ( (*(_BYTE *)(v1 + 76) & 0x20) == 0 && ((v22 & 0x108) != 0 || (BYTE12(v47) & 1) != 0) )
      {
        if ( v8 )
        {
          v25 = 6 * g_cxLabelMargin;
          v24 = v25 + ListView_OnGetStringWidth(v1, lpString[1], a1[10]);
        }
        else
        {
          memset(v52, 0, 0x48u);
          v23 = (LPARAM *)a1[4];
          if ( !v23 )
          {
            v23 = v52;
            v52[0] = (LPARAM)lpString[1];
          }
          v24 = (__int16)ListView_RGetCXLabel(v1, *((_DWORD *)a1 + 26), (_DWORD)v23, a1[10], 1);
        }
        v26 = v24 + rcSrc2.left;
        v27 = rcSrc2.right;
        if ( rcSrc2.right > v26 )
          v27 = v26;
        rcSrc2.right = v27;
      }
      if ( v8 || *(_DWORD *)(v1 + 336) != *((_DWORD *)a1 + 26) )
      {
        v28 = *((_DWORD *)a1 + 32);
        v29 = v22 | (v8 != 0 ? 66 : 2);
        v30 = 0;
        if ( (v28 == GetSysColor(26)
           || (*(_DWORD *)(v1 + 76) & 0x800) != 0
           && ((*(_BYTE *)(v1 + 76) & 0x40) != 0
            || *(char *)(*a1 + 76LL) < 0 && (unsigned int)ListView_OnGetItemState(*a1, *((unsigned int *)a1 + 26), 2)))
          && v8
          && (*(_BYTE *)(v1 + 76) & 0x20) == 0 )
        {
          v31 = SelectObject((HDC)a1[10], *(HGDIOBJ *)(v1 + 88));
          v30 = v31;
          if ( v31 != *(HGDIOBJ *)(v1 + 536) )
          {
            SelectObject((HDC)a1[10], v31);
            v30 = 0;
          }
          color = *(_DWORD *)(v1 + 104);
        }
        else
        {
          color = v28;
        }
        if ( (v29 & 8) != 0 && (v11 & 0x40) != 0 )
          v29 |= 0x200u;
        if ( ((*((_BYTE *)a1 + 40) | v43) & 2) != 0 )
        {
          v33 = (HDC)a1[10];
          v54[0] = 0;
          GetTextExtentPointW(v33, L"...", 3, (LPSIZE)v54);
          v34 = v54[0];
        }
        else
        {
          v34 = *(_DWORD *)(v1 + 136);
        }
        SHDrawText(
          (HDC)a1[10],
          (WCHAR *)lpString[1],
          &rcSrc2,
          BYTE4(lParam[3]) & 3,
          v29,
          *(_DWORD *)(v1 + 128),
          v34,
          color,
          *((_DWORD *)a1 + 33));
        if ( (v11 & 8) != 0 && (BYTE12(v47) & 1) != 0 && (*(_BYTE *)(*a1 + 48LL) & 1) == 0 )
        {
          if ( (*(_BYTE *)(v1 + 76) & 0x20) != 0 )
            v45 = 1;
          else
            DrawFocusRect((HDC)a1[10], &rcSrc2);
        }
        if ( rcSrc2.right < v46 )
        {
          rcSrc2.left = rcSrc2.right;
          v40 = *((_DWORD *)a1 + 33);
          rcSrc2.right = v46;
          SHDrawText((HDC)a1[10], (WCHAR *)&c_szNULL, &rcSrc2, 0, v29 & 0x80, *(_DWORD *)(v1 + 128), v34, color, v40);
        }
        if ( v30 )
          SelectObject((HDC)a1[10], v30);
      }
    }
    if ( (v43 & 0x10) != 0 )
      CICustomDrawNotify(*a1, 196610, a1 + 6);
    v9 = v44;
LABEL_80:
    v6 = v45;
    v7 = ++v41;
  }
  if ( v6 )
    DrawFocusRect((HDC)a1[10], &rcDst);
  return 1;
}

```

## disassembly

```asm
0x1800784c0  push    rbp
0x1800784c2  push    rbx
0x1800784c3  push    rsi
0x1800784c4  push    rdi
0x1800784c5  push    r12
0x1800784c7  push    r13
0x1800784c9  push    r14
0x1800784cb  push    r15
0x1800784cd  lea     rbp, [rsp-2A8h]
0x1800784d5  sub     rsp, 3A8h
0x1800784dc  mov     rax, cs:__security_cookie
0x1800784e3  xor     rax, rsp
0x1800784e6  mov     [rbp+2E0h+var_50], rax
0x1800784ed  mov     rsi, [rcx]
0x1800784f0  xorps   xmm0, xmm0
0x1800784f3  xor     eax, eax
0x1800784f5  xorps   xmm1, xmm1
0x1800784f8  mov     rdi, rcx
0x1800784fb  mov     [rbp+2E0h+var_348], rax
0x1800784ff  xor     edx, edx; Val
0x180078501  lea     rcx, [rbp+2E0h+lParam]; void *
0x180078505  movups  xmmword ptr [rbp+2E0h+rc.left], xmm0
0x180078509  lea     r8d, [rax+40h]; Size
0x18007850d  movups  xmmword ptr [rbp+2E0h+rcSrc2.left], xmm1
0x180078511  movups  xmmword ptr [rbp+2E0h+rcSrc1.left], xmm0
0x180078515  movups  xmmword ptr [rbp+2E0h+rcDst.left], xmm1
0x180078519  movups  [rsp+3E0h+var_378], xmm0
0x18007851e  movups  xmmword ptr [rsp+3E0h+lpString], xmm0
0x180078523  movups  [rbp+2E0h+var_358], xmm0
0x180078527  call    memset
0x18007852c  mov     edx, [rdi+68h]
0x18007852f  lea     rax, [rbp+2E0h+rcSrc1]
0x180078533  mov     qword ptr [rsp+3E0h+var_3B8], 0
0x18007853c  xor     r9d, r9d
0x18007853f  xor     r8d, r8d
0x180078542  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x180078547  mov     rcx, rsi
0x18007854a  call    ListView_RGetRects
0x18007854f  mov     eax, [rsi+1C0h]
0x180078555  cmp     [rbp+2E0h+rcSrc1.bottom], eax
0x180078558  jle     loc_180078B8C
0x18007855e  mov     r8, [rdi+10h]; lprcSrc2
0x180078562  test    r8, r8
0x180078565  jz      short loc_180078586
0x180078567  mov     eax, [r8+0Ch]
0x18007856b  cmp     [rbp+2E0h+rcSrc1.top], eax
0x18007856e  jge     short loc_180078591
0x180078570  lea     rdx, [rbp+2E0h+rcSrc1]; lprcSrc1
0x180078574  lea     rcx, [rbp+2E0h+rcDst]; lprcDst
0x180078578  call    cs:__imp_IntersectRect
0x18007857e  test    eax, eax
0x180078580  jz      loc_180078B8C
0x180078586  mov     ecx, [rbp+2E0h+rcSrc1.top]
0x180078589  cmp     ecx, [rsi+0A8h]
0x18007858f  jl      short loc_180078598
0x180078591  xor     eax, eax
0x180078593  jmp     loc_180078B91
0x180078598  mov     rax, [rdi+8]
0x18007859c  xor     r12d, r12d
0x18007859f  xor     ebx, ebx
0x1800785a1  mov     [rsp+3E0h+var_380], r12d
0x1800785a6  xor     r15d, r15d
0x1800785a9  mov     [rsp+3E0h+var_390], ebx
0x1800785ad  test    rax, rax
0x1800785b0  jz      short loc_1800785DC
0x1800785b2  mov     r13d, [rax]
0x1800785b5  sub     r13d, [rbp+2E0h+rcSrc1.left]
0x1800785b9  mov     r14d, [rax+4]
0x1800785bd  mov     edx, r13d; dx
0x1800785c0  sub     r14d, ecx
0x1800785c3  mov     [rsp+3E0h+var_384], r13d
0x1800785c8  mov     r8d, r14d; dy
0x1800785cb  mov     [rsp+3E0h+dy], r14d
0x1800785d0  lea     rcx, [rbp+2E0h+rcSrc1]; lprc
0x1800785d4  call    cs:__imp_OffsetRect
0x1800785da  jmp     short loc_1800785E8
0x1800785dc  xor     r13d, r13d
0x1800785df  mov     [rsp+3E0h+dy], ebx
0x1800785e3  mov     [rsp+3E0h+var_384], r13d
0x1800785e8  test    dword ptr [rsi+10h], 400h
0x1800785ef  mov     eax, [rdi+68h]
0x1800785f2  mov     dword ptr [rsp+3E0h+var_378+4], eax
0x1800785f6  mov     dword ptr [rsp+3E0h+lpString], 0FFFFh
0x1800785fe  mov     dword ptr [rsp+3E0h+var_378+0Ch], ebx
0x180078602  jnz     short loc_180078613
0x180078604  lea     rcx, [rbp+2E0h+rcDst]; lprc
0x180078608  call    cs:__imp_SetRectEmpty
0x18007860e  jmp     loc_180078AAF
0x180078613  mov     eax, r15d
0x180078616  mov     dword ptr [rbp+2E0h+var_358+4], 0FFFFFFFFh
0x18007861d  neg     eax
0x18007861f  mov     dword ptr [rsp+3E0h+var_378+8], r15d
0x180078624  lea     rax, [rbp+2E0h+var_260]
0x18007862b  mov     dword ptr [rbp+2E0h+var_358], 104h
0x180078632  sbb     ecx, ecx
0x180078634  mov     [rbp+2E0h+lpString+8], rax
0x180078638  and     ecx, 0FFFFFFF0h
0x18007863b  lea     rdx, [rsp+3E0h+var_378]
0x180078640  add     ecx, 1Bh
0x180078643  mov     dword ptr [rsp+3E0h+var_378], ecx
0x180078647  mov     rcx, rsi
0x18007864a  call    ListView_OnGetItem
0x18007864f  test    r15d, r15d
0x180078652  jnz     short loc_180078661
0x180078654  test    dword ptr [rsi+10h], 400h
0x18007865b  jnz     loc_180078ADB
0x180078661  mov     r14d, [rdi+18h]
0x180078665  lea     r9, [rbp+2E0h+lParam]; lParam
0x180078669  mov     dword ptr [rbp+2E0h+lParam], 5
0x180078670  mov     edx, 120Bh; Msg
0x180078675  mov     rcx, [rsi+1B8h]; hWnd
0x18007867c  movsxd  r12, r15d
0x18007867f  mov     r8, r12; wParam
0x180078682  call    cs:__imp_SendMessageW
0x180078688  mov     edx, [rdi+68h]
0x18007868b  lea     rax, [rbp+2E0h+rcSrc2]
0x18007868f  lea     r9, [rbp+2E0h+rc]
0x180078693  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x180078698  mov     r8d, r15d
0x18007869b  mov     rcx, rsi
0x18007869e  call    ListView_RGetRectsEx
0x1800786a3  mov     r8d, [rsp+3E0h+dy]; dy
0x1800786a8  lea     rcx, [rbp+2E0h+rc]; lprc
0x1800786ac  mov     edx, r13d; dx
0x1800786af  call    cs:__imp_OffsetRect
0x1800786b5  mov     r8d, [rsp+3E0h+dy]; dy
0x1800786ba  lea     rcx, [rbp+2E0h+rcSrc2]; lprc
0x1800786be  mov     edx, r13d; dx
0x1800786c1  call    cs:__imp_OffsetRect
0x1800786c7  test    byte ptr [rdi+28h], 20h
0x1800786cb  jz      loc_180078775
0x1800786d1  mov     rcx, [rsi+1B8h]; hWnd
0x1800786d8  lea     r9, [rbp+2E0h+var_2A0]; lParam
0x1800786dc  mov     ebx, [rdi+70h]
0x1800786df  xorps   xmm0, xmm0
0x1800786e2  mov     r8, r12; wParam
0x1800786e5  mov     edx, 1207h; Msg
0x1800786ea  movups  xmmword ptr [rbp+2E0h+var_2A0], xmm0
0x1800786ee  call    cs:__imp_SendMessageW
0x1800786f4  mov     eax, dword ptr [rbp+2E0h+var_2A0]
0x1800786f7  lea     r8, [rdi+30h]
0x1800786fb  mov     rcx, [rdi]
0x1800786fe  mov     edx, 30001h
0x180078703  mov     [rdi+58h], eax
0x180078706  mov     eax, dword ptr [rbp+2E0h+var_2A0+8]
0x180078709  mov     [rdi+60h], eax
0x18007870c  mov     [rdi+88h], r15d
0x180078713  call    CICustomDrawNotify
0x180078718  mov     r8d, [rdi+70h]
0x18007871c  mov     [rdi+70h], ebx
0x18007871f  mov     [rsp+3E0h+var_388], eax
0x180078723  test    al, 4
0x180078725  jnz     loc_180078AA0
0x18007872b  mov     ebx, [rsp+3E0h+var_390]
0x18007872f  and     r14d, 0FFFFFF87h
0x180078733  mov     edx, r14d
0x180078736  or      edx, 8
0x180078739  test    r8b, 10h
0x18007873d  cmovz   edx, r14d
0x180078741  test    r8b, 1
0x180078745  jz      short loc_180078770
0x180078747  mov     rcx, [rdi]
0x18007874a  mov     eax, [rdi+68h]
0x18007874d  mov     r14d, [rcx+48h]
0x180078751  not     r14d
0x180078754  and     r14d, 1
0x180078758  inc     r14d
0x18007875b  shl     r14d, 4
0x18007875f  or      r14d, edx
0x180078762  cmp     [rcx+214h], eax
0x180078768  jnz     short loc_18007877D
0x18007876a  or      r14d, 40h
0x18007876e  jmp     short loc_18007877D
0x180078770  mov     r14d, edx
0x180078773  jmp     short loc_18007877D
0x180078775  mov     [rsp+3E0h+var_388], 0
0x18007877d  test    r15d, r15d
0x180078780  jz      short loc_180078791
0x180078782  cmp     dword ptr [rbp+2E0h+var_358+4], 0FFFFFFFFh
0x180078786  jz      short loc_1800787DF
0x180078788  mov     eax, [rsi+0F0h]
0x18007878e  add     [rbp+2E0h+rcSrc2.left], eax
0x180078791  cmp     dword ptr [rbp+2E0h+var_358+4], 0FFFFFFFFh
0x180078795  jz      short loc_1800787DF
0x180078797  test    byte ptr [rsi+4Ch], 20h
0x18007879b  jz      short loc_1800787DF
0x18007879d  test    ebx, ebx
0x18007879f  jz      short loc_1800787DF
0x1800787a1  mov     ebx, [rbp+2E0h+rc.left]
0x1800787a4  mov     r12d, [rbp+2E0h+rc.right]
0x1800787a8  test    r15d, r15d
0x1800787ab  jnz     short loc_1800787BE
0x1800787ad  mov     eax, ebx
0x1800787af  sub     eax, [rsi+1E8h]
0x1800787b5  sub     eax, cs:g_cxEdge
0x1800787bb  mov     [rbp+2E0h+rc.left], eax
0x1800787be  mov     eax, [rbp+2E0h+rcSrc2.right]
0x1800787c1  lea     rdx, [rbp+2E0h+rc]; lprc
0x1800787c5  mov     rcx, [rdi+50h]; hDC
0x1800787c9  mov     [rbp+2E0h+rc.right], eax
0x1800787cc  mov     r8, [rsi+70h]; hbr
0x1800787d0  call    cs:__imp_FillRect
0x1800787d6  mov     [rbp+2E0h+rc.left], ebx
0x1800787d9  mov     [rbp+2E0h+rc.right], r12d
0x1800787dd  jmp     short loc_1800787E2
0x1800787df  mov     ebx, [rbp+2E0h+rc.left]
0x1800787e2  mov     eax, [rbp+2E0h+rcSrc2.right]
0x1800787e5  lea     rdx, [rsp+3E0h+var_378]
0x1800787ea  mov     r8, [rdi+50h]
0x1800787ee  mov     r9d, ebx
0x1800787f1  mov     [rsp+3E0h+var_3B0], eax
0x1800787f5  mov     rcx, rsi
0x1800787f8  mov     eax, [rbp+2E0h+rc.top]
0x1800787fb  mov     [rsp+3E0h+var_3B8], r14d
0x180078800  mov     [rsp+3E0h+var_3C0], eax
0x180078804  call    ListView_DrawImageEx
0x180078809  test    byte ptr [rsi+4Ch], 20h
0x18007880d  mov     r13d, eax
0x180078810  jz      short loc_18007882A
0x180078812  test    r14b, 8
0x180078816  jz      short loc_18007882A
0x180078818  lea     r8, [rbp+2E0h+rcSrc2]; lprcSrc2
0x18007881c  lea     rdx, [rbp+2E0h+rcDst]; lprcSrc1
0x180078820  lea     rcx, [rbp+2E0h+rcDst]; lprcDst
0x180078824  call    cs:__imp_UnionRect
0x18007882a  mov     rcx, [rbp+2E0h+lpString+8]
0x18007882e  test    rcx, rcx
0x180078831  jz      loc_180078A83
0x180078837  mov     eax, [rbp+2E0h+rcSrc2.right]
0x18007883a  mov     [rsp+3E0h+var_37C], eax
0x18007883e  mov     eax, r15d
0x180078841  neg     eax
0x180078843  sbb     r12d, r12d
0x180078846  and     r12d, 40h
0x18007884a  add     r12d, 2
0x18007884e  test    byte ptr [rsi+4Ch], 20h
0x180078852  jnz     short loc_1800788D3
0x180078854  test    r13d, 108h
0x18007885b  jnz     short loc_180078864
0x18007885d  test    byte ptr [rsp+3E0h+var_378+0Ch], 1
0x180078862  jz      short loc_1800788D3
0x180078864  test    r15d, r15d
0x180078867  jnz     short loc_1800788A7
0x180078869  xor     edx, edx; Val
0x18007886b  lea     r8d, [r15+48h]; Size
0x18007886f  lea     rcx, [rbp+2E0h+var_300]; void *
0x180078873  call    memset
0x180078878  mov     r8, [rdi+20h]
0x18007887c  test    r8, r8
0x18007887f  jnz     short loc_18007888D
0x180078881  mov     rax, [rbp+2E0h+lpString+8]
0x180078885  lea     r8, [rbp+2E0h+var_300]
0x180078889  mov     [rbp+2E0h+var_300], rax
0x18007888d  mov     r9, [rdi+50h]
0x180078891  mov     rcx, rsi
0x180078894  mov     edx, [rdi+68h]
0x180078897  mov     [rsp+3E0h+var_3C0], 1
0x18007889f  call    ListView_RGetCXLabel
0x1800788a4  cwde
0x1800788a5  jmp     short loc_1800788C3
0x1800788a7  mov     eax, cs:g_cxLabelMargin
0x1800788ad  mov     rdx, rcx
0x1800788b0  mov     r8, [rdi+50h]
0x1800788b4  mov     rcx, rsi
0x1800788b7  lea     ebx, [rax+rax*2]
0x1800788ba  add     ebx, ebx
0x1800788bc  call    ListView_OnGetStringWidth
0x1800788c1  add     eax, ebx
0x1800788c3  mov     edx, [rbp+2E0h+rcSrc2.left]
0x1800788c6  add     edx, eax
0x1800788c8  mov     eax, [rbp+2E0h+rcSrc2.right]
0x1800788cb  cmp     eax, edx
0x1800788cd  cmovg   eax, edx
0x1800788d0  mov     [rbp+2E0h+rcSrc2.right], eax
0x1800788d3  test    r15d, r15d
0x1800788d6  jnz     short loc_1800788E7
0x1800788d8  mov     eax, [rdi+68h]
0x1800788db  cmp     [rsi+150h], eax
0x1800788e1  jz      loc_180078A83
0x1800788e7  mov     ebx, [rdi+80h]
0x1800788ed  or      r12d, r13d
0x1800788f0  xor     r13d, r13d
0x1800788f3  lea     ecx, [r13+1Ah]; nIndex
0x1800788f7  call    cs:__imp_GetSysColor
0x1800788fd  cmp     ebx, eax
0x1800788ff  jz      short loc_180078929
0x180078901  test    dword ptr [rsi+4Ch], 800h
0x180078908  jz      short loc_180078964
0x18007890a  test    byte ptr [rsi+4Ch], 40h
0x18007890e  jnz     short loc_180078929
0x180078910  mov     rcx, [rdi]
0x180078913  test    byte ptr [rcx+4Ch], 80h
0x180078917  jz      short loc_180078964
0x180078919  mov     edx, [rdi+68h]
0x18007891c  lea     r8d, [r13+2]
0x180078920  call    ListView_OnGetItemState
0x180078925  test    eax, eax
0x180078927  jz      short loc_180078964
0x180078929  test    r15d, r15d
0x18007892c  jz      short loc_180078964
  ... truncated ...
```
