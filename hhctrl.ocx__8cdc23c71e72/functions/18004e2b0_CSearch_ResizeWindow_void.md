# CSearch::ResizeWindow(void)

- ea: `0x18004e2b0`
- end: `0x18004e5cb`
- name: `?ResizeWindow@CSearch@@UEAAXXZ`
- size: `795`
- prototype: `void __fastcall(CSearch *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800128a8`
- `0x1800437cc`
- `0x18004e2b0`
- `0x180051e48`
- `0x180065438`
- `0x180066c20`
- `0x180066f80`
- `0x1800674e0`
- `0x1800675c0`
- `0x180067798`
- `0x180075c90`

## import_xrefs

- `USER32!MoveWindow` at `0x18004e3d0`
- `USER32!MoveWindow` at `0x18004e441`
- `USER32!MoveWindow` at `0x18004e496`
- `USER32!MoveWindow` at `0x18004e4f1`
- `USER32!MoveWindow` at `0x18004e549`
- `USER32!MoveWindow` at `0x18004e5a3`
- `USER32!MoveWindow` at `0x18004e3d0`
- `USER32!MoveWindow` at `0x18004e441`
- `USER32!MoveWindow` at `0x18004e496`
- `USER32!MoveWindow` at `0x18004e4f1`
- `USER32!MoveWindow` at `0x18004e549`
- `USER32!MoveWindow` at `0x18004e5a3`
- `USER32!CopyRect` at `0x18004e31b`
- `USER32!CopyRect` at `0x18004e31b`
- `USER32!SetWindowPos` at `0x18004e573`
- `USER32!SetWindowPos` at `0x18004e573`
- `USER32!GetSystemMetrics` at `0x18004e304`
- `USER32!GetSystemMetrics` at `0x18004e40d`
- `USER32!GetSystemMetrics` at `0x18004e304`
- `USER32!GetSystemMetrics` at `0x18004e40d`

## pseudocode

```c
void __fastcall CSearch::ResizeWindow(CSearch *this)
{
  HFONT UIFont; // r14
  LONG left; // ebx
  LONG right; // edi
  const WCHAR *StringResourceW; // rax
  unsigned int StaticDimensionsW; // eax
  const char *StringResource; // rax
  int v8; // r8d
  CHHWinType *v9; // rcx
  LONG v10; // ebx
  LONG v11; // edi
  HFONT ContentFont; // rax
  unsigned int v13; // ebx
  int SystemMetrics; // eax
  HWND v15; // rcx
  const WCHAR *v16; // rax
  unsigned int ButtonDimensionsW; // eax
  HWND v18; // rcx
  LONG v19; // ebx
  LONG v20; // edi
  const WCHAR *v21; // rax
  unsigned int nHeight; // eax
  const WCHAR *v23; // rax
  unsigned int v24; // eax
  int v25; // ebx
  HWND v26; // rcx
  struct tagRECT rcDst; // [rsp+40h] [rbp-38h] BYREF
  RECT rcSrc; // [rsp+50h] [rbp-28h] BYREF

  rcSrc = 0;
  rcDst = 0;
  UIFont = CResourceCache::GetUIFont(this);
  GetParentSize(&rcSrc, *((HWND *)this + 16), *((_DWORD *)this + 30), *((_DWORD *)this + 31));
  rcSrc.top += 2 * GetSystemMetrics(33);
  CopyRect(&rcDst, &rcSrc);
  left = rcDst.left;
  right = rcDst.right;
  StringResourceW = GetStringResourceW(0x425u);
  StaticDimensionsW = GetStaticDimensionsW(*((HWND *)this + 12), UIFont, StringResourceW, right - left);
  rcDst.bottom = HIWORD(StaticDimensionsW) + rcDst.top;
  if ( g_fDBCSSystem || g_langSystem == 1 || g_langSystem == 13 )
  {
    StringResource = GetStringResource(0x434u);
    v8 = 2;
    if ( StringResource && (unsigned __int8)(*StringResource - 48) <= 9u )
      v8 = Atoi(StringResource);
    MoveWindow(*((HWND *)this + 12), rcSrc.left, rcSrc.top + v8, rcDst.right - rcDst.left, rcDst.bottom - rcDst.top, 1);
  }
  else
  {
    MoveWindow(*((HWND *)this + 12), rcSrc.left, rcSrc.top, rcDst.right - rcDst.left, HIWORD(StaticDimensionsW), 1);
  }
  v9 = (CHHWinType *)*((_QWORD *)this + 2);
  v10 = rcDst.left;
  v11 = rcDst.right;
  rcDst.top = rcDst.bottom + 10;
  ContentFont = CHHWinType::GetContentFont(v9);
  v13 = GetStaticDimensionsW(*((HWND *)this + 8), ContentFont, L"Test", v11 - v10);
  SystemMetrics = GetSystemMetrics(33);
  v13 >>= 16;
  v15 = (HWND)*((_QWORD *)this + 8);
  rcDst.bottom = rcDst.top + v13 + 2 * SystemMetrics;
  MoveWindow(v15, rcDst.left, rcDst.top, rcDst.right - rcDst.left, v13 + 2 * SystemMetrics, 1);
  rcDst.top = rcDst.bottom + 8;
  v16 = GetStringResourceW(0x409u);
  ButtonDimensionsW = GetButtonDimensionsW(*((HWND *)this + 11), UIFont, v16);
  v18 = (HWND)*((_QWORD *)this + 11);
  rcDst.bottom = rcDst.top + HIWORD(ButtonDimensionsW);
  MoveWindow(
    v18,
    rcDst.right - (unsigned __int16)ButtonDimensionsW,
    rcDst.top,
    (unsigned __int16)ButtonDimensionsW,
    HIWORD(ButtonDimensionsW),
    1);
  v19 = rcDst.left;
  v20 = rcDst.right;
  rcDst.top = rcDst.bottom + 8;
  v21 = GetStringResourceW(0x426u);
  nHeight = GetStaticDimensionsW(*((HWND *)this + 13), UIFont, v21, v20 - v19) >> 16;
  rcDst.bottom = nHeight + rcDst.top;
  MoveWindow(*((HWND *)this + 13), rcDst.left, rcDst.top, rcDst.right - rcDst.left, nHeight, 1);
  rcDst.top = rcDst.bottom + 10;
  v23 = GetStringResourceW(0x1020u);
  v24 = GetButtonDimensionsW(*((HWND *)this + 10), UIFont, v23);
  LOWORD(v20) = v24;
  v25 = HIWORD(v24);
  rcDst.bottom = rcSrc.bottom - HIWORD(v24) - 8;
  MoveWindow(*((HWND *)this + 9), rcDst.left, rcDst.top, rcDst.right - rcDst.left, rcDst.bottom - rcDst.top, 1);
  SetWindowPos(*((HWND *)this + 9), 0, 0, 0, 0, 0, 3u);
  v26 = (HWND)*((_QWORD *)this + 10);
  rcDst.bottom = rcSrc.bottom;
  rcDst.top = rcSrc.bottom - v25;
  MoveWindow(v26, rcDst.right - (unsigned __int16)v20, rcSrc.bottom - v25, (unsigned __int16)v20, v25, 1);
  CFTSListView::SizeColumns(*((CFTSListView **)this + 14));
}

```

## disassembly

```asm
0x18004e2b0  push    rbp
0x18004e2b2  push    rbx
0x18004e2b3  push    rsi
0x18004e2b4  push    rdi
0x18004e2b5  push    r14
0x18004e2b7  push    r15
0x18004e2b9  mov     rbp, rsp
0x18004e2bc  sub     rsp, 78h
0x18004e2c0  mov     rax, cs:__security_cookie
0x18004e2c7  xor     rax, rsp
0x18004e2ca  mov     [rbp+var_18], rax
0x18004e2ce  xorps   xmm0, xmm0
0x18004e2d1  xorps   xmm1, xmm1
0x18004e2d4  movups  xmmword ptr [rbp+rcSrc.left], xmm0
0x18004e2d8  mov     rsi, rcx
0x18004e2db  movups  xmmword ptr [rbp+rcDst.left], xmm1
0x18004e2df  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x18004e2e4  mov     r9d, [rsi+7Ch]; int
0x18004e2e8  lea     rcx, [rbp+rcSrc]; lprc
0x18004e2ec  mov     r8d, [rsi+78h]; int
0x18004e2f0  mov     r14, rax
0x18004e2f3  mov     rdx, [rsi+80h]; hWnd
0x18004e2fa  call    ?GetParentSize@@YAPEAUHWND__@@PEAUtagRECT@@PEAU1@HH@Z; GetParentSize(tagRECT *,HWND__ *,int,int)
0x18004e2ff  mov     ecx, 21h ; '!'; nIndex
0x18004e304  call    cs:__imp_GetSystemMetrics
0x18004e30a  mov     ecx, [rbp+rcSrc.top]
0x18004e30d  lea     edx, [rcx+rax*2]
0x18004e310  mov     [rbp+rcSrc.top], edx
0x18004e313  lea     rcx, [rbp+rcDst]; lprcDst
0x18004e317  lea     rdx, [rbp+rcSrc]; lprcSrc
0x18004e31b  call    cs:__imp_CopyRect
0x18004e321  mov     ebx, [rbp+rcDst.left]
0x18004e324  mov     ecx, 425h; uID
0x18004e329  mov     edi, [rbp+rcDst.right]
0x18004e32c  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18004e331  mov     rcx, [rsi+60h]; hWnd
0x18004e335  sub     edi, ebx
0x18004e337  mov     r9d, edi; int
0x18004e33a  mov     r8, rax; lpString
0x18004e33d  mov     rdx, r14; h
0x18004e340  call    ?GetStaticDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBGH@Z; GetStaticDimensionsW(HWND__ *,HFONT__ *,ushort const *,int)
0x18004e345  mov     edx, [rbp+rcDst.top]
0x18004e348  mov     r15d, 1
0x18004e34e  shr     eax, 10h
0x18004e351  cmp     cs:?g_fDBCSSystem@@3HA, 0; int g_fDBCSSystem
0x18004e358  lea     ecx, [rax+rdx]
0x18004e35b  mov     [rbp+rcDst.bottom], ecx
0x18004e35e  jnz     short loc_18004E384
0x18004e360  movzx   eax, cs:?g_langSystem@@3GA; ushort g_langSystem
0x18004e367  cmp     ax, r15w
0x18004e36b  jz      short loc_18004E384
0x18004e36d  cmp     ax, 0Dh
0x18004e371  jz      short loc_18004E384
0x18004e373  mov     r8d, [rbp+rcSrc.top]
0x18004e377  sub     ecx, edx
0x18004e379  mov     [rsp+78h+bRepaint], r15d
0x18004e37e  mov     [rsp+78h+nHeight], ecx
0x18004e382  jmp     short loc_18004E3C1
0x18004e384  mov     ecx, 434h; uID
0x18004e389  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18004e38e  mov     r8d, 2
0x18004e394  test    rax, rax
0x18004e397  jz      short loc_18004E3AE
0x18004e399  mov     cl, [rax]
0x18004e39b  sub     cl, 30h ; '0'
0x18004e39e  cmp     cl, 9
0x18004e3a1  ja      short loc_18004E3AE
0x18004e3a3  mov     rcx, rax; char *
0x18004e3a6  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x18004e3ab  mov     r8d, eax
0x18004e3ae  mov     edx, [rbp+rcDst.bottom]
0x18004e3b1  sub     edx, [rbp+rcDst.top]
0x18004e3b4  add     r8d, [rbp+rcSrc.top]; Y
0x18004e3b8  mov     [rsp+78h+bRepaint], r15d; bRepaint
0x18004e3bd  mov     [rsp+78h+nHeight], edx; nHeight
0x18004e3c1  mov     r9d, [rbp+rcDst.right]
0x18004e3c5  sub     r9d, [rbp+rcDst.left]; nWidth
0x18004e3c9  mov     edx, [rbp+rcSrc.left]; X
0x18004e3cc  mov     rcx, [rsi+60h]; hWnd
0x18004e3d0  call    cs:__imp_MoveWindow
0x18004e3d6  mov     eax, [rbp+rcDst.bottom]
0x18004e3d9  mov     rcx, [rsi+10h]; this
0x18004e3dd  add     eax, 0Ah
0x18004e3e0  mov     ebx, [rbp+rcDst.left]
0x18004e3e3  mov     edi, [rbp+rcDst.right]
0x18004e3e6  mov     [rbp+rcDst.top], eax
0x18004e3e9  call    ?GetContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetContentFont(void)
0x18004e3ee  mov     rcx, [rsi+40h]; hWnd
0x18004e3f2  lea     r8, aTest; "Test"
0x18004e3f9  sub     edi, ebx
0x18004e3fb  mov     rdx, rax; h
0x18004e3fe  mov     r9d, edi; int
0x18004e401  call    ?GetStaticDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBGH@Z; GetStaticDimensionsW(HWND__ *,HFONT__ *,ushort const *,int)
0x18004e406  mov     ecx, 21h ; '!'; nIndex
0x18004e40b  mov     ebx, eax
0x18004e40d  call    cs:__imp_GetSystemMetrics
0x18004e413  mov     r8d, [rbp+rcDst.top]; Y
0x18004e417  mov     r9d, [rbp+rcDst.right]
0x18004e41b  mov     edx, [rbp+rcDst.left]; X
0x18004e41e  sub     r9d, edx; nWidth
0x18004e421  shr     ebx, 10h
0x18004e424  mov     [rsp+78h+bRepaint], r15d; bRepaint
0x18004e429  lea     ecx, [r8+rbx]
0x18004e42d  lea     r10d, [rcx+rax*2]
0x18004e431  mov     rcx, [rsi+40h]; hWnd
0x18004e435  mov     [rbp+rcDst.bottom], r10d
0x18004e439  sub     r10d, r8d
0x18004e43c  mov     [rsp+78h+nHeight], r10d; nHeight
0x18004e441  call    cs:__imp_MoveWindow
0x18004e447  mov     eax, [rbp+rcDst.bottom]
0x18004e44a  mov     ecx, 409h; uID
0x18004e44f  add     eax, 8
0x18004e452  mov     [rbp+rcDst.top], eax
0x18004e455  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18004e45a  mov     rcx, [rsi+58h]; hWnd
0x18004e45e  mov     r8, rax; lpString
0x18004e461  mov     rdx, r14; h
0x18004e464  call    ?GetButtonDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBG@Z; GetButtonDimensionsW(HWND__ *,HFONT__ *,ushort const *)
0x18004e469  mov     r8d, [rbp+rcDst.top]; Y
0x18004e46d  mov     r10d, eax
0x18004e470  mov     edx, [rbp+rcDst.right]
0x18004e473  mov     rcx, [rsi+58h]; hWnd
0x18004e477  shr     r10d, 10h
0x18004e47b  add     r10d, r8d
0x18004e47e  movzx   r9d, ax; nWidth
0x18004e482  mov     [rbp+rcDst.bottom], r10d
0x18004e486  sub     edx, r9d; X
0x18004e489  sub     r10d, r8d
0x18004e48c  mov     [rsp+78h+bRepaint], r15d; bRepaint
0x18004e491  mov     [rsp+78h+nHeight], r10d; nHeight
0x18004e496  call    cs:__imp_MoveWindow
0x18004e49c  mov     eax, [rbp+rcDst.bottom]
0x18004e49f  mov     ecx, 426h; uID
0x18004e4a4  mov     ebx, [rbp+rcDst.left]
0x18004e4a7  add     eax, 8
0x18004e4aa  mov     edi, [rbp+rcDst.right]
0x18004e4ad  mov     [rbp+rcDst.top], eax
0x18004e4b0  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18004e4b5  mov     rcx, [rsi+68h]; hWnd
0x18004e4b9  sub     edi, ebx
0x18004e4bb  mov     r9d, edi; int
0x18004e4be  mov     r8, rax; lpString
0x18004e4c1  mov     rdx, r14; h
0x18004e4c4  call    ?GetStaticDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBGH@Z; GetStaticDimensionsW(HWND__ *,HFONT__ *,ushort const *,int)
0x18004e4c9  mov     r8d, [rbp+rcDst.top]; Y
0x18004e4cd  mov     r9d, [rbp+rcDst.right]
0x18004e4d1  mov     edx, [rbp+rcDst.left]; X
0x18004e4d4  sub     r9d, edx; nWidth
0x18004e4d7  shr     eax, 10h
0x18004e4da  mov     [rsp+78h+bRepaint], r15d; bRepaint
0x18004e4df  lea     ecx, [rax+r8]
0x18004e4e3  mov     [rbp+rcDst.bottom], ecx
0x18004e4e6  sub     ecx, r8d
0x18004e4e9  mov     [rsp+78h+nHeight], ecx; nHeight
0x18004e4ed  mov     rcx, [rsi+68h]; hWnd
0x18004e4f1  call    cs:__imp_MoveWindow
0x18004e4f7  mov     eax, [rbp+rcDst.bottom]
0x18004e4fa  mov     ecx, 1020h; uID
0x18004e4ff  add     eax, 0Ah
0x18004e502  mov     [rbp+rcDst.top], eax
0x18004e505  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18004e50a  mov     rcx, [rsi+50h]; hWnd
0x18004e50e  mov     r8, rax; lpString
0x18004e511  mov     rdx, r14; h
0x18004e514  call    ?GetButtonDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBG@Z; GetButtonDimensionsW(HWND__ *,HFONT__ *,ushort const *)
0x18004e519  mov     ecx, [rbp+rcSrc.bottom]
0x18004e51c  mov     ebx, eax
0x18004e51e  mov     r8d, [rbp+rcDst.top]; Y
0x18004e522  mov     edi, eax
0x18004e524  mov     r9d, [rbp+rcDst.right]
0x18004e528  mov     edx, [rbp+rcDst.left]; X
0x18004e52b  sub     r9d, edx; nWidth
0x18004e52e  shr     ebx, 10h
0x18004e531  sub     ecx, ebx
0x18004e533  mov     [rsp+78h+bRepaint], r15d; bRepaint
0x18004e538  add     ecx, 0FFFFFFF8h
0x18004e53b  mov     [rbp+rcDst.bottom], ecx
0x18004e53e  sub     ecx, r8d
0x18004e541  mov     [rsp+78h+nHeight], ecx; nHeight
0x18004e545  mov     rcx, [rsi+48h]; hWnd
0x18004e549  call    cs:__imp_MoveWindow
0x18004e54f  mov     rcx, [rsi+48h]; hWnd
0x18004e553  xor     r9d, r9d; Y
0x18004e556  mov     [rsp+78h+uFlags], 3; uFlags
0x18004e55e  xor     r8d, r8d; X
0x18004e561  mov     [rsp+78h+bRepaint], 0; cy
0x18004e569  xor     edx, edx; hWndInsertAfter
0x18004e56b  mov     [rsp+78h+nHeight], 0; cx
0x18004e573  call    cs:__imp_SetWindowPos
0x18004e579  mov     eax, [rbp+rcSrc.bottom]
0x18004e57c  mov     r8d, eax
0x18004e57f  mov     edx, [rbp+rcDst.right]
0x18004e582  sub     r8d, ebx; Y
0x18004e585  mov     rcx, [rsi+50h]; hWnd
0x18004e589  mov     [rbp+rcDst.bottom], eax
0x18004e58c  sub     eax, r8d
0x18004e58f  movzx   r9d, di; nWidth
0x18004e593  sub     edx, r9d; X
0x18004e596  mov     [rsp+78h+bRepaint], r15d; bRepaint
0x18004e59b  mov     [rsp+78h+nHeight], eax; nHeight
0x18004e59f  mov     [rbp+rcDst.top], r8d
0x18004e5a3  call    cs:__imp_MoveWindow
0x18004e5a9  mov     rcx, [rsi+70h]; this
0x18004e5ad  call    ?SizeColumns@CFTSListView@@QEAAXXZ; CFTSListView::SizeColumns(void)
0x18004e5b2  mov     rcx, [rbp+var_18]
0x18004e5b6  xor     rcx, rsp; StackCookie
0x18004e5b9  call    __security_check_cookie
0x18004e5be  add     rsp, 78h
0x18004e5c2  pop     r15
0x18004e5c4  pop     r14
0x18004e5c6  pop     rdi
0x18004e5c7  pop     rsi
0x18004e5c8  pop     rbx
0x18004e5c9  pop     rbp
0x18004e5ca  retn
```
