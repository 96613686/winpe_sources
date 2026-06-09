# CLVDragDropManager::LVGenerateDragImage(SHDRAGIMAGE *)

- ea: `0x1800634bc`
- end: `0x180063a6b`
- name: `?LVGenerateDragImage@CLVDragDropManager@@QEAA_JPEAUSHDRAGIMAGE@@@Z`
- size: `1455`
- prototype: `__int64 __fastcall(CLVDragDropManager *__hidden this, struct SHDRAGIMAGE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005fe40`

## callees

- `0x1800303a0`
- `0x1800634bc`
- `0x1800936d4`
- `0x1800e441c`
- `0x180114520`
- `0x180114ebc`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800636ab`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800636c4`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800636ab`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800636c4`
- `GDI32!SetBkMode` at `0x18006367a`
- `GDI32!SetBkMode` at `0x18006367a`
- `GDI32!SelectObject` at `0x180063854`
- `GDI32!SelectObject` at `0x18006399c`
- `GDI32!SelectObject` at `0x180063854`
- `GDI32!SelectObject` at `0x18006399c`
- `GDI32!DeleteDC` at `0x1800639a5`
- `GDI32!DeleteDC` at `0x1800639a5`
- `GDI32!CreateCompatibleDC` at `0x180063618`
- `GDI32!CreateCompatibleDC` at `0x180063618`
- `GDI32!SetLayout` at `0x18006366f`
- `GDI32!SetLayout` at `0x18006366f`
- `GDI32!CreateDIBSection` at `0x180063826`
- `GDI32!CreateDIBSection` at `0x180063826`
- `USER32!IntersectRect` at `0x1800635c4`
- `USER32!IntersectRect` at `0x1800635c4`
- `USER32!UnionRect` at `0x1800635da`
- `USER32!UnionRect` at `0x1800635da`
- `USER32!GetClientRect` at `0x180063547`
- `USER32!GetClientRect` at `0x180063547`

## pseudocode

```c
__int64 __fastcall CLVDragDropManager::LVGenerateDragImage(CLVDragDropManager *this, struct SHDRAGIMAGE *a2)
{
  _DWORD *v3; // rcx
  int v5; // r12d
  __int64 v6; // r13
  __int64 v7; // rcx
  int NextItem; // eax
  int v9; // r15d
  __int64 v10; // rcx
  int v11; // ebx
  HDC CompatibleDC; // rsi
  __int64 v13; // rax
  struct CLVDrawState *DrawStateForItem; // rbx
  int v15; // r15d
  int v16; // eax
  LONG right; // ebx
  int left; // r11d
  __int64 v19; // r9
  LONG v20; // edx
  int v21; // r8d
  int v22; // ecx
  int v23; // r9d
  LONG bottom; // r10d
  LONG top; // r8d
  __int64 v26; // r15
  LONG v27; // edx
  int v28; // r9d
  LONG v29; // ecx
  __int64 v30; // rax
  int v31; // r10d
  int v32; // ebx
  HBITMAP v33; // rax
  HBITMAP v34; // rbx
  HGDIOBJ v35; // r15
  __int64 v36; // rdx
  __int64 v37; // rcx
  LONG v38; // eax
  __int64 v39; // rax
  CLVItemStore *v40; // rcx
  int iItem; // edx
  unsigned int v42; // edx
  int i; // r8d
  __int64 result; // rax
  unsigned int v45; // ebx
  __int64 v46; // r8
  __int64 v47; // rax
  struct tagLVITEMINDEX v48; // [rsp+30h] [rbp-D0h] BYREF
  int v49; // [rsp+38h] [rbp-C8h]
  _QWORD v50[5]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h]
  HDC v52; // [rsp+98h] [rbp-68h]
  RECT rcSrc1; // [rsp+100h] [rbp+0h] BYREF
  int v54; // [rsp+110h] [rbp+10h] BYREF
  struct tagRECT rcDst; // [rsp+118h] [rbp+18h] BYREF
  RECT rcSrc2; // [rsp+128h] [rbp+28h] BYREF
  struct tagRECT Rect; // [rsp+138h] [rbp+38h] BYREF
  BITMAPINFO pbmi; // [rsp+148h] [rbp+48h] BYREF

  v3 = (_DWORD *)*((_QWORD *)this + 2);
  rcSrc1 = 0;
  Rect = 0;
  v5 = v3[44];
  v54 = 0;
  if ( (*(int (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v3 + 624LL))(v3, &v54) < 0 || !v54 )
    return 0;
  v6 = 0;
  *(_DWORD *)(*((_QWORD *)this + 2) + 168LL) |= 0x20000u;
  GetClientRect(*(HWND *)(*((_QWORD *)this + 2) + 96LL), &Rect);
  v7 = *((_QWORD *)this + 2);
  v48.iGroup = 0;
  v48.iItem = -1;
  NextItem = CLVItemStore::OnGetNextItem(*(CLVItemStore **)(v7 + 512), -1, 0, 2u, &v48.iGroup);
  v9 = NextItem;
  while ( 1 )
  {
    v48.iItem = NextItem;
    v11 = NextItem;
    if ( NextItem == -1 )
      break;
    v10 = *((_QWORD *)this + 2);
    rcSrc2 = 0;
    if ( (*(int (__fastcall **)(__int64, struct tagLVITEMINDEX, __int64, RECT *))(*(_QWORD *)v10 + 280LL))(
           v10,
           v48,
           3,
           &rcSrc2) >= 0 )
    {
      rcDst = 0;
      if ( IntersectRect(&rcDst, &Rect, &rcSrc2) )
        UnionRect(&rcSrc1, &rcSrc1, &rcSrc2);
    }
    NextItem = CLVItemStore::OnGetNextItem(
                 *(CLVItemStore **)(*((_QWORD *)this + 2) + 512LL),
                 v11,
                 v48.iGroup,
                 2u,
                 &v48.iGroup);
  }
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    v13 = *((_QWORD *)this + 2);
    *(_QWORD *)&rcDst.left = 0;
    memset(&pbmi, 0, sizeof(pbmi));
    v49 = v5 & 0x8000;
    *(_DWORD *)(v13 + 176) &= ~0x8000u;
    if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 128LL) & 0x400000) != 0 )
      SetLayout(CompatibleDC, 1u);
    SetBkMode(CompatibleDC, 1);
    DrawStateForItem = CLVItemStore::GetDrawStateForItem(*(CLVItemStore **)(*((_QWORD *)this + 2) + 512LL), v9);
    v15 = MulDiv(300, **((_DWORD **)DrawStateForItem + 10), 96);
    v16 = MulDiv(300, *(_DWORD *)(*((_QWORD *)DrawStateForItem + 10) + 4LL), 96);
    right = rcSrc1.right;
    left = rcSrc1.left;
    if ( rcSrc1.right - rcSrc1.left > v15 )
    {
      v19 = *((_QWORD *)this + 2);
      v20 = rcSrc1.left;
      v21 = v15 / 2;
      v22 = *(_DWORD *)(*(_QWORD *)(v19 + 440) + 96LL) - v15 / 2;
      if ( rcSrc1.left >= v22 )
      {
        v22 = rcSrc1.left;
        v21 = rcSrc1.left + 2 * v21 - *(_DWORD *)(*(_QWORD *)(v19 + 440) + 96LL);
      }
      else
      {
        left = *(_DWORD *)(*(_QWORD *)(v19 + 440) + 96LL) - v15 / 2;
        rcSrc1.left = left;
      }
      v23 = *(_DWORD *)(*(_QWORD *)(v19 + 440) + 96LL);
      if ( rcSrc1.right <= v21 + v23 )
      {
        if ( v22 > v20 )
        {
          left = v22 - v21 - v23 + rcSrc1.right;
          if ( left < v20 )
            left = v20;
          rcSrc1.left = left;
        }
      }
      else
      {
        right = v21 + v23;
        rcSrc1.right = v21 + v23;
      }
    }
    bottom = rcSrc1.bottom;
    top = rcSrc1.top;
    if ( rcSrc1.bottom - rcSrc1.top > v16 )
    {
      v26 = *((_QWORD *)this + 2);
      v27 = rcSrc1.top;
      v28 = v16 / 2;
      v29 = HIDWORD(*(_QWORD *)(*(_QWORD *)(v26 + 440) + 96LL)) - v16 / 2;
      if ( rcSrc1.top >= v29 )
      {
        v29 = rcSrc1.top;
        v28 = rcSrc1.top + 2 * v28 - HIDWORD(*(_QWORD *)(*(_QWORD *)(v26 + 440) + 96LL));
      }
      else
      {
        top = HIDWORD(*(_QWORD *)(*(_QWORD *)(v26 + 440) + 96LL)) - v16 / 2;
        rcSrc1.top = top;
      }
      v30 = HIDWORD(*(_QWORD *)(*(_QWORD *)(v26 + 440) + 96LL));
      if ( rcSrc1.bottom <= (int)v30 + v28 )
      {
        if ( v29 > v27 )
        {
          top = v29 - v30 - v28 + rcSrc1.bottom;
          if ( top < v27 )
            top = v27;
          rcSrc1.top = top;
        }
      }
      else
      {
        bottom = v30 + v28;
        rcSrc1.bottom = v30 + v28;
      }
    }
    v31 = bottom - top;
    pbmi.bmiHeader.biSize = 40;
    v32 = right - left;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    a2->sizeDragImage.cy = v31 + 1;
    a2->sizeDragImage.cx = v32 + 1;
    pbmi.bmiHeader.biWidth = v32 + 1;
    pbmi.bmiHeader.biHeight = -(v31 + 1);
    v33 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)&rcDst, 0, 0);
    a2->hbmpDragImage = v33;
    v34 = v33;
    if ( v33 )
    {
      memset_0(v50, 0, 0xC0u);
      v35 = SelectObject(CompatibleDC, v34);
      memset_0(*(void **)&rcDst.left, 0, a2->sizeDragImage.cy * a2->sizeDragImage.cx);
      a2->crColorKey = -1;
      v36 = *((_QWORD *)this + 2);
      v37 = *(_QWORD *)(v36 + 440);
      if ( (*(_DWORD *)(v36 + 128) & 0x400000) != 0 )
        v38 = rcSrc1.right - *(_DWORD *)(v37 + 96);
      else
        v38 = *(_DWORD *)(v37 + 96) - rcSrc1.left;
      a2->ptOffset.x = v38;
      a2->ptOffset.y = HIDWORD(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 440LL) + 96LL)) - rcSrc1.top;
      v39 = *((_QWORD *)this + 2);
      v50[3] = 0;
      v50[0] = v39;
      v52 = CompatibleDC;
      v51 = 0;
      if ( (*(_DWORD *)(v39 + 112) & 0x1000) != 0 )
      {
        v40 = *(CLVItemStore **)(v39 + 512);
        v48.iItem = -1;
        iItem = -1;
        while ( 1 )
        {
          v48.iItem = CLVItemStore::OnGetNextItem(v40, iItem, v48.iGroup, 2u, &v48.iGroup);
          if ( v48.iItem == -1 )
            break;
          v51 = 0;
          CLVDragDropManager::_DrawDragImage(this, &v48, &Rect, &rcSrc1, (struct LVDRAWITEM *)v50);
          iItem = v48.iItem;
          v40 = *(CLVItemStore **)(*((_QWORD *)this + 2) + 512LL);
        }
      }
      else
      {
        v45 = **(_DWORD **)(v39 + 512);
        while ( (--v45 & 0x80000000) == 0 )
        {
          v46 = *((_QWORD *)this + 2);
          v47 = *(_QWORD *)(v46 + 512);
          v48.iItem = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v46 + 608) + 16LL) + 72LL) + 8LL)
                                + 8LL * v45);
          v51 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v47 + 8) + 8LL) + 8LL * v48.iItem);
          if ( (*(_BYTE *)(v51 + 18) & 2) != 0 )
            CLVDragDropManager::_DrawDragImage(this, &v48, &Rect, &rcSrc1, (struct LVDRAWITEM *)v50);
        }
      }
      v42 = 0;
      for ( i = pbmi.bmiHeader.biWidth * pbmi.bmiHeader.biHeight; (int)v42 < i; ++v42 )
      {
        if ( !*(_BYTE *)(*(_QWORD *)&rcDst.left + 4LL * v42 + 3)
          && (*(_BYTE *)(*(_QWORD *)&rcDst.left + 4LL * v42 + 2)
           || *(_BYTE *)(*(_QWORD *)&rcDst.left + 4LL * v42 + 1)
           || *(_BYTE *)(*(_QWORD *)&rcDst.left + 4LL * v42)) )
        {
          *(_BYTE *)(*(_QWORD *)&rcDst.left + 4LL * v42 + 3) = -1;
        }
      }
      SelectObject(CompatibleDC, v35);
      DeleteDC(CompatibleDC);
      v6 = 1;
    }
    if ( v49 )
      *(_DWORD *)(*((_QWORD *)this + 2) + 176LL) |= 0x8000u;
  }
  result = v6;
  *(_DWORD *)(*((_QWORD *)this + 2) + 168LL) &= ~0x20000u;
  return result;
}

```

## disassembly

```asm
0x1800634bc  mov     [rsp-8+arg_10], rbx
0x1800634c1  push    rbp
0x1800634c2  push    rsi
0x1800634c3  push    rdi
0x1800634c4  push    r12
0x1800634c6  push    r13
0x1800634c8  push    r14
0x1800634ca  push    r15
0x1800634cc  lea     rbp, [rsp-80h]
0x1800634d1  sub     rsp, 180h
0x1800634d8  mov     rax, cs:__security_cookie
0x1800634df  xor     rax, rsp
0x1800634e2  mov     [rbp+0B0h+var_38], rax
0x1800634e6  xorps   xmm0, xmm0
0x1800634e9  mov     rdi, rcx
0x1800634ec  mov     rcx, [rcx+10h]
0x1800634f0  mov     r14, rdx
0x1800634f3  movdqu  xmmword ptr [rbp+0B0h+rcSrc1.left], xmm0
0x1800634f8  xor     esi, esi
0x1800634fa  lea     rdx, [rbp+0B0h+var_A0]
0x1800634fe  movups  xmmword ptr [rbp+0B0h+Rect.left], xmm0
0x180063502  mov     r12d, [rcx+0B0h]
0x180063509  mov     [rbp+0B0h+var_A0], esi
0x18006350c  mov     rax, [rcx]
0x18006350f  mov     rax, [rax+270h]
0x180063516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006351b  test    eax, eax
0x18006351d  js      loc_180063A42
0x180063523  cmp     [rbp+0B0h+var_A0], esi
0x180063526  jz      loc_180063A42
0x18006352c  mov     rax, [rdi+10h]
0x180063530  lea     rdx, [rbp+0B0h+Rect]; lpRect
0x180063534  mov     r13d, esi
0x180063537  bts     dword ptr [rax+0A8h], 11h
0x18006353f  mov     rcx, [rdi+10h]
0x180063543  mov     rcx, [rcx+60h]; hWnd
0x180063547  call    cs:__imp_GetClientRect
0x18006354d  mov     rcx, [rdi+10h]
0x180063551  lea     rax, [rsp+1B0h+var_180.iGroup]
0x180063556  mov     [rsp+30h], rsi
0x18006355b  lea     r9d, [rsi+2]; unsigned int
0x18006355f  mov     r8d, [rsp+1B0h+var_180.iGroup]; int
0x180063564  or      edx, 0FFFFFFFFh; int
0x180063567  mov     [rsp+1B0h+var_180.iItem], edx
0x18006356b  mov     rcx, [rcx+200h]; this
0x180063572  mov     [rsp+1B0h+hSection], rax; int *
0x180063577  call    ?OnGetNextItem@CLVItemStore@@QEAAHHHIPEAH@Z; CLVItemStore::OnGetNextItem(int,int,uint,int *)
0x18006357c  mov     r15d, eax
0x18006357f  jmp     loc_180063607
0x180063584  mov     rcx, [rdi+10h]
0x180063588  lea     r9, [rbp+0B0h+rcSrc2]
0x18006358c  xorps   xmm0, xmm0
0x18006358f  mov     r8d, 3
0x180063595  movups  xmmword ptr [rbp+0B0h+rcSrc2.left], xmm0
0x180063599  mov     rdx, [rcx]
0x18006359c  mov     rax, [rdx+118h]
0x1800635a3  mov     rdx, qword ptr [rsp+1B0h+var_180.iItem]
0x1800635a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635ad  test    eax, eax
0x1800635af  js      short loc_1800635E0
0x1800635b1  xorps   xmm0, xmm0
0x1800635b4  lea     r8, [rbp+0B0h+rcSrc2]; lprcSrc2
0x1800635b8  lea     rdx, [rbp+0B0h+Rect]; lprcSrc1
0x1800635bc  lea     rcx, [rbp+0B0h+rcDst]; lprcDst
0x1800635c0  movups  xmmword ptr [rbp+0B0h+rcDst.left], xmm0
0x1800635c4  call    cs:__imp_IntersectRect
0x1800635ca  test    eax, eax
0x1800635cc  jz      short loc_1800635E0
0x1800635ce  lea     r8, [rbp+0B0h+rcSrc2]; lprcSrc2
0x1800635d2  lea     rdx, [rbp+0B0h+rcSrc1]; lprcSrc1
0x1800635d6  lea     rcx, [rbp+0B0h+rcSrc1]; lprcDst
0x1800635da  call    cs:__imp_UnionRect
0x1800635e0  mov     rcx, [rdi+10h]
0x1800635e4  lea     rax, [rsp+1B0h+var_180.iGroup]
0x1800635e9  mov     r8d, [rsp+1B0h+var_180.iGroup]; int
0x1800635ee  mov     r9d, 2; unsigned int
0x1800635f4  mov     edx, ebx; int
0x1800635f6  mov     [rsp+1B0h+hSection], rax; int *
0x1800635fb  mov     rcx, [rcx+200h]; this
0x180063602  call    ?OnGetNextItem@CLVItemStore@@QEAAHHHIPEAH@Z; CLVItemStore::OnGetNextItem(int,int,uint,int *)
0x180063607  mov     [rsp+1B0h+var_180.iItem], eax
0x18006360b  mov     ebx, eax
0x18006360d  cmp     eax, 0FFFFFFFFh
0x180063610  jnz     loc_180063584
0x180063616  xor     ecx, ecx; hdc
0x180063618  call    cs:__imp_CreateCompatibleDC
0x18006361e  mov     rsi, rax
0x180063621  test    rax, rax
0x180063624  jz      loc_1800639C1
0x18006362a  mov     rax, [rdi+10h]
0x18006362e  xorps   xmm0, xmm0
0x180063631  movups  xmmword ptr [rbp+0B0h+pbmi.bmiHeader.biCompression], xmm0
0x180063635  mov     qword ptr [rbp+0B0h+rcDst.left], r13
0x180063639  and     r12d, 8000h
0x180063640  movups  xmmword ptr [rbp+0B0h+pbmi.bmiHeader.biSize], xmm0
0x180063644  mov     [rsp+1B0h+var_178], r12d
0x180063649  mov     ebx, 1
0x18006364e  movups  xmmword ptr [rbp+0B0h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x180063652  btr     dword ptr [rax+0B0h], 0Fh
0x18006365a  mov     rax, [rdi+10h]
0x18006365e  test    dword ptr [rax+80h], 400000h
0x180063668  jz      short loc_180063675
0x18006366a  mov     edx, ebx; l
0x18006366c  mov     rcx, rsi; hdc
0x18006366f  call    cs:__imp_SetLayout
0x180063675  mov     edx, ebx; mode
0x180063677  mov     rcx, rsi; hdc
0x18006367a  call    cs:__imp_SetBkMode
0x180063680  mov     rcx, [rdi+10h]
0x180063684  mov     edx, r15d; int
0x180063687  mov     rcx, [rcx+200h]; this
0x18006368e  call    ?GetDrawStateForItem@CLVItemStore@@QEAAPEAVCLVDrawState@@H@Z; CLVItemStore::GetDrawStateForItem(int)
0x180063693  mov     r12d, 12Ch
0x180063699  mov     r8d, 60h ; '`'; nDenominator
0x18006369f  mov     ecx, r12d; nNumber
0x1800636a2  mov     rbx, rax
0x1800636a5  mov     rdx, [rax+50h]
0x1800636a9  mov     edx, [rdx]; nNumerator
0x1800636ab  call    cs:__imp_MulDiv
0x1800636b1  mov     rdx, [rbx+50h]
0x1800636b5  mov     r8d, 60h ; '`'; nDenominator
0x1800636bb  mov     ecx, r12d; nNumber
0x1800636be  mov     r15d, eax
0x1800636c1  mov     edx, [rdx+4]; nNumerator
0x1800636c4  call    cs:__imp_MulDiv
0x1800636ca  mov     ebx, [rbp+0B0h+rcSrc1.right]
0x1800636cd  mov     ecx, ebx
0x1800636cf  mov     r11d, [rbp+0B0h+rcSrc1.left]
0x1800636d3  mov     r12d, eax
0x1800636d6  sub     ecx, r11d
0x1800636d9  cmp     ecx, r15d
0x1800636dc  jle     short loc_180063751
0x1800636de  mov     r9, [rdi+10h]
0x1800636e2  mov     eax, r15d
0x1800636e5  cdq
0x1800636e6  mov     r15d, 2
0x1800636ec  idiv    r15d
0x1800636ef  mov     rcx, [r9+1B8h]
0x1800636f6  mov     edx, r11d
0x1800636f9  mov     r8d, eax
0x1800636fc  mov     eax, [rcx+60h]
0x1800636ff  mov     ecx, eax
0x180063701  sub     ecx, r8d
0x180063704  cmp     r11d, ecx
0x180063707  jge     short loc_180063711
0x180063709  mov     r11d, ecx
0x18006370c  mov     [rbp+0B0h+rcSrc1.left], ecx
0x18006370f  jmp     short loc_18006371C
0x180063711  add     r8d, r8d
0x180063714  mov     ecx, edx
0x180063716  sub     r8d, eax
0x180063719  add     r8d, edx
0x18006371c  mov     rax, [r9+1B8h]
0x180063723  mov     r9d, [rax+60h]
0x180063727  lea     eax, [r8+r9]
0x18006372b  cmp     ebx, eax
0x18006372d  jle     short loc_180063736
0x18006372f  mov     ebx, eax
0x180063731  mov     [rbp+0B0h+rcSrc1.right], eax
0x180063734  jmp     short loc_180063757
0x180063736  cmp     ecx, edx
0x180063738  jle     short loc_180063757
0x18006373a  sub     ecx, r8d
0x18006373d  sub     ecx, r9d
0x180063740  lea     r11d, [rcx+rbx]
0x180063744  cmp     r11d, edx
0x180063747  cmovl   r11d, edx
0x18006374b  mov     [rbp+0B0h+rcSrc1.left], r11d
0x18006374f  jmp     short loc_180063757
0x180063751  mov     r15d, 2
0x180063757  mov     r10d, [rbp+0B0h+rcSrc1.bottom]
0x18006375b  mov     eax, r10d
0x18006375e  mov     r8d, [rbp+0B0h+rcSrc1.top]
0x180063762  sub     eax, r8d
0x180063765  cmp     eax, r12d
0x180063768  jle     short loc_1800637E0
0x18006376a  mov     eax, r12d
0x18006376d  cdq
0x18006376e  idiv    r15d
0x180063771  mov     r15, [rdi+10h]
0x180063775  mov     edx, r8d
0x180063778  mov     r9d, eax
0x18006377b  mov     rcx, [r15+1B8h]
0x180063782  mov     rax, [rcx+60h]
0x180063786  shr     rax, 20h
0x18006378a  mov     ecx, eax
0x18006378c  sub     ecx, r9d
0x18006378f  cmp     r8d, ecx
0x180063792  jge     short loc_18006379C
0x180063794  mov     r8d, ecx
0x180063797  mov     [rbp+0B0h+rcSrc1.top], ecx
0x18006379a  jmp     short loc_1800637A7
0x18006379c  add     r9d, r9d
0x18006379f  mov     ecx, edx
0x1800637a1  sub     r9d, eax
0x1800637a4  add     r9d, edx
0x1800637a7  mov     rax, [r15+1B8h]
0x1800637ae  mov     rax, [rax+60h]
0x1800637b2  shr     rax, 20h
0x1800637b6  lea     r15d, [rax+r9]
0x1800637ba  cmp     r10d, r15d
0x1800637bd  jle     short loc_1800637C8
0x1800637bf  mov     r10d, r15d
0x1800637c2  mov     [rbp+0B0h+rcSrc1.bottom], r15d
0x1800637c6  jmp     short loc_1800637E0
0x1800637c8  cmp     ecx, edx
0x1800637ca  jle     short loc_1800637E0
0x1800637cc  sub     ecx, eax
0x1800637ce  sub     ecx, r9d
0x1800637d1  lea     r8d, [rcx+r10]
0x1800637d5  cmp     r8d, edx
0x1800637d8  cmovl   r8d, edx
0x1800637dc  mov     [rbp+0B0h+rcSrc1.top], r8d
0x1800637e0  sub     r10d, r8d
0x1800637e3  mov     [rbp+0B0h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800637ea  sub     ebx, r11d
0x1800637ed  mov     qword ptr [rbp+0B0h+pbmi.bmiHeader.biPlanes], 200001h
0x1800637f5  xor     r12d, r12d
0x1800637f8  lea     r9, [rbp+0B0h+rcDst]; ppvBits
0x1800637fc  mov     [rsp+1B0h+offset], r12d; offset
0x180063801  lea     rdx, [rbp+0B0h+pbmi]; pbmi
0x180063805  lea     eax, [r10+1]
0x180063809  mov     [rsp+1B0h+hSection], r12; hSection
0x18006380e  lea     ecx, [rbx+1]
0x180063811  mov     [r14+4], eax
0x180063815  neg     eax
0x180063817  mov     [r14], ecx
0x18006381a  mov     [rbp+0B0h+pbmi.bmiHeader.biWidth], ecx
0x18006381d  xor     r8d, r8d; usage
0x180063820  mov     rcx, rsi; hdc
0x180063823  mov     [rbp+0B0h+pbmi.bmiHeader.biHeight], eax
0x180063826  call    cs:__imp_CreateDIBSection
0x18006382c  mov     [r14+10h], rax
0x180063830  mov     rbx, rax
0x180063833  test    rax, rax
0x180063836  jz      loc_1800639AE
0x18006383c  xor     edx, edx; Val
0x18006383e  lea     rcx, [rsp+1B0h+var_170]; void *
0x180063843  mov     r8d, 0C0h; Size
0x180063849  call    memset_0
0x18006384e  mov     rdx, rbx; h
0x180063851  mov     rcx, rsi; hdc
0x180063854  call    cs:__imp_SelectObject
0x18006385a  mov     ecx, [r14]
0x18006385d  xor     edx, edx; Val
0x18006385f  imul    ecx, [r14+4]
0x180063864  mov     r15, rax
0x180063867  movsxd  r8, ecx; Size
0x18006386a  mov     rcx, qword ptr [rbp+0B0h+rcDst.left]; void *
0x18006386e  call    memset_0
0x180063873  mov     dword ptr [r14+18h], 0FFFFFFFFh
0x18006387b  mov     rdx, [rdi+10h]
0x18006387f  test    dword ptr [rdx+80h], 400000h
0x180063889  mov     rcx, [rdx+1B8h]
0x180063890  jz      short loc_18006389A
0x180063892  mov     eax, [rbp+0B0h+rcSrc1.right]
0x180063895  sub     eax, [rcx+60h]
0x180063898  jmp     short loc_1800638A0
0x18006389a  mov     eax, [rcx+60h]
0x18006389d  sub     eax, [rbp+0B0h+rcSrc1.left]
0x1800638a0  mov     [r14+8], eax
0x1800638a4  mov     rax, [rdi+10h]
0x1800638a8  mov     rcx, [rax+1B8h]
0x1800638af  mov     rax, [rcx+60h]
0x1800638b3  shr     rax, 20h
0x1800638b7  sub     eax, [rbp+0B0h+rcSrc1.top]
0x1800638ba  mov     [r14+0Ch], eax
0x1800638be  mov     rax, [rdi+10h]
0x1800638c2  mov     [rsp+1B0h+var_158], r12
0x1800638c7  mov     [rsp+1B0h+var_170], rax
0x1800638cc  mov     [rbp+0B0h+var_118], rsi
0x1800638d0  mov     [rsp+1B0h+var_148], r12
0x1800638d5  test    dword ptr [rax+70h], 1000h
0x1800638dc  mov     rbx, [rax+200h]
0x1800638e3  jz      loc_1800639D2
0x1800638e9  or      r14d, 0FFFFFFFFh
0x1800638ed  mov     rcx, rbx
0x1800638f0  mov     [rsp+1B0h+var_180.iItem], r14d
0x1800638f5  mov     edx, r14d
0x1800638f8  lea     r13d, [r14+3]
0x1800638fc  jmp     short loc_180063931
0x1800638fe  lea     rax, [rsp+1B0h+var_170]
0x180063903  mov     [rsp+1B0h+var_148], r12
0x180063908  lea     r9, [rbp+0B0h+rcSrc1]; struct tagRECT *
0x18006390c  mov     [rsp+1B0h+hSection], rax; struct LVDRAWITEM *
0x180063911  lea     r8, [rbp+0B0h+Rect]; struct tagRECT *
0x180063915  mov     rcx, rdi; this
0x180063918  lea     rdx, [rsp+1B0h+var_180]; struct tagLVITEMINDEX *
0x18006391d  call    ?_DrawDragImage@CLVDragDropManager@@IEAAXPEBUtagLVITEMINDEX@@PEBUtagRECT@@1PEAULVDRAWITEM@@@Z; CLVDragDropManager::_DrawDragImage(tagLVITEMINDEX const *,tagRECT const *,tagRECT const *,LVDRAWITEM *)
0x180063922  mov     rcx, [rdi+10h]
0x180063926  mov     edx, [rsp+1B0h+var_180.iItem]; int
0x18006392a  mov     rcx, [rcx+200h]; this
0x180063931  mov     r8d, [rsp+1B0h+var_180.iGroup]; int
0x180063936  lea     rax, [rsp+1B0h+var_180.iGroup]
0x18006393b  mov     r9d, r13d; unsigned int
0x18006393e  mov     [rsp+1B0h+hSection], rax; int *
0x180063943  call    ?OnGetNextItem@CLVItemStore@@QEAAHHHIPEAH@Z; CLVItemStore::OnGetNextItem(int,int,uint,int *)
0x180063948  mov     [rsp+1B0h+var_180.iItem], eax
0x18006394c  cmp     eax, r14d
0x18006394f  jnz     short loc_1800638FE
  ... truncated ...
```
