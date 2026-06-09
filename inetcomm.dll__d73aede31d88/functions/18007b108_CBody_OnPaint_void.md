# CBody::OnPaint(void)

- ea: `0x18007b108`
- end: `0x18007b723`
- name: `?OnPaint@CBody@@AEAAJXZ`
- size: `1563`
- prototype: `__int64 __fastcall(CBody *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800290d0`

## callees

- `0x18007b108`
- `0x18007bd34`
- `0x18008159c`
- `0x180081630`
- `0x180082198`
- `0x180082948`
- `0x18008330c`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18007b24c`
- `GDI32!CreateCompatibleDC` at `0x18007b24c`
- `GDI32!SelectObject` at `0x18007b1d8`
- `GDI32!SelectObject` at `0x18007b210`
- `GDI32!SelectObject` at `0x18007b292`
- `GDI32!SelectObject` at `0x18007b32e`
- `GDI32!SelectObject` at `0x18007b655`
- `GDI32!SelectObject` at `0x18007b6ae`
- `GDI32!SelectObject` at `0x18007b6bc`
- `GDI32!SelectObject` at `0x18007b1d8`
- `GDI32!SelectObject` at `0x18007b210`
- `GDI32!SelectObject` at `0x18007b292`
- `GDI32!SelectObject` at `0x18007b32e`
- `GDI32!SelectObject` at `0x18007b655`
- `GDI32!SelectObject` at `0x18007b6ae`
- `GDI32!SelectObject` at `0x18007b6bc`
- `GDI32!BitBlt` at `0x18007b63a`
- `GDI32!BitBlt` at `0x18007b63a`
- `GDI32!DeleteDC` at `0x18007b6dc`
- `GDI32!DeleteDC` at `0x18007b6dc`
- `GDI32!DeleteObject` at `0x18007b6d3`
- `GDI32!DeleteObject` at `0x18007b6d3`
- `GDI32!SaveDC` at `0x18007b258`
- `GDI32!SaveDC` at `0x18007b258`
- `GDI32!CreateCompatibleBitmap` at `0x18007b31e`
- `GDI32!CreateCompatibleBitmap` at `0x18007b31e`
- `GDI32!SetBkMode` at `0x18007b371`
- `GDI32!SetBkMode` at `0x18007b371`
- `GDI32!SetBkColor` at `0x18007b385`
- `GDI32!SetBkColor` at `0x18007b385`
- `GDI32!SetTextColor` at `0x18007b3a0`
- `GDI32!SetTextColor` at `0x18007b3a0`
- `GDI32!RestoreDC` at `0x18007b6c9`
- `GDI32!RestoreDC` at `0x18007b6c9`
- `GDI32!PatBlt` at `0x18007b204`
- `GDI32!PatBlt` at `0x18007b6a2`
- `GDI32!PatBlt` at `0x18007b204`
- `GDI32!PatBlt` at `0x18007b6a2`
- `USER32!GetSysColorBrush` at `0x18007b1cc`
- `USER32!GetSysColorBrush` at `0x18007b34b`
- `USER32!GetSysColorBrush` at `0x18007b649`
- `USER32!GetSysColorBrush` at `0x18007b1cc`
- `USER32!GetSysColorBrush` at `0x18007b34b`
- `USER32!GetSysColorBrush` at `0x18007b649`
- `USER32!GetClientRect` at `0x18007b17b`
- `USER32!GetClientRect` at `0x18007b2a0`
- `USER32!GetClientRect` at `0x18007b2e3`
- `USER32!GetClientRect` at `0x18007b666`
- `USER32!GetClientRect` at `0x18007b17b`
- `USER32!GetClientRect` at `0x18007b2a0`
- `USER32!GetClientRect` at `0x18007b2e3`
- `USER32!GetClientRect` at `0x18007b666`
- `USER32!GetSystemMetrics` at `0x18007b2af`
- `USER32!GetSystemMetrics` at `0x18007b2af`
- `USER32!FillRect` at `0x18007b35b`
- `USER32!FillRect` at `0x18007b35b`
- `USER32!GetSysColor` at `0x18007b37a`
- `USER32!GetSysColor` at `0x18007b395`
- `USER32!GetSysColor` at `0x18007b37a`
- `USER32!GetSysColor` at `0x18007b395`
- `USER32!BeginPaint` at `0x18007b19c`
- `USER32!BeginPaint` at `0x18007b23b`
- `USER32!BeginPaint` at `0x18007b19c`
- `USER32!BeginPaint` at `0x18007b23b`
- `USER32!EndPaint` at `0x18007b21e`
- `USER32!EndPaint` at `0x18007b6ea`
- `USER32!EndPaint` at `0x18007b21e`
- `USER32!EndPaint` at `0x18007b6ea`
- `USER32!DrawEdge` at `0x18007b1c1`
- `USER32!DrawEdge` at `0x18007b1c1`

## pseudocode

```c
__int64 __fastcall CBody::OnPaint(CBody *this)
{
  int v2; // eax
  HDC v3; // rax
  HDC v4; // rdi
  HBRUSH v5; // rax
  HGDIOBJ v6; // rbx
  HDC v8; // r12
  HDC CompatibleDC; // r15
  int v10; // eax
  __int64 v11; // rcx
  LONG right; // r13d
  int v13; // r14d
  int ClientHeight; // ebx
  CCommunityRatings *v15; // rcx
  HGDIOBJ v16; // rax
  int v17; // edi
  unsigned int v18; // ebx
  HBRUSH SysColorBrush; // rax
  COLORREF SysColor; // eax
  COLORREF v21; // eax
  LONG LineHeight; // eax
  bool v23; // zf
  LONG cx; // edx
  char *v25; // rdi
  char v26; // cl
  int v27; // ebx
  const unsigned __int16 *v28; // r8
  _WORD *v29; // rax
  CCommunityRatings *v30; // rcx
  __int64 v31; // rax
  HBRUSH v32; // rax
  HGDIOBJ v33; // rbx
  CCommunityRatings *v34; // rcx
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  struct tagSIZE v36; // [rsp+58h] [rbp-A8h] BYREF
  int cy; // [rsp+60h] [rbp-A0h]
  int nSavedDC; // [rsp+64h] [rbp-9Ch]
  HGDIOBJ v39; // [rsp+68h] [rbp-98h] BYREF
  HDC v40; // [rsp+70h] [rbp-90h]
  HGDIOBJ v41; // [rsp+78h] [rbp-88h]
  HGDIOBJ ho; // [rsp+80h] [rbp-80h]
  struct tagRECT Rect; // [rsp+88h] [rbp-78h] BYREF
  struct tagRECT v44; // [rsp+98h] [rbp-68h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  v2 = *((_DWORD *)this + 81) - 1;
  v39 = 0;
  Rect = 0;
  v44 = 0;
  if ( (v2 & 0xFFFFFFFD) == 0 )
  {
    v40 = BeginPaint(*((HWND *)this + 13), &Paint);
    v8 = v40;
    CompatibleDC = CreateCompatibleDC(v40);
    v10 = SaveDC(CompatibleDC);
    v11 = *((_QWORD *)this + 68);
    nSavedDC = v10;
    if ( v11
      && !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, HGDIOBJ *))(*(_QWORD *)v11 + 32LL))(v11, 1, 0, &v39) )
    {
      SelectObject(CompatibleDC, v39);
    }
    GetClientRect(*((HWND *)this + 13), &Rect);
    right = Rect.right;
    v13 = right - (2 * GetSystemMetrics(5) + 4);
    ClientHeight = CBody::lGetClientHeight(this);
    cy = ClientHeight;
    if ( *((_DWORD *)this + 83) )
    {
      GetClientRect(*((HWND *)this + 48), &v44);
      v13 = v13 - v44.right - 4;
    }
    v15 = (CCommunityRatings *)*((_QWORD *)this + 80);
    if ( v15 )
    {
      v36 = 0;
      if ( (int)CCommunityRatings::GetSize(v15, &v36) >= 0 )
        v13 -= v36.cx;
    }
    ho = CreateCompatibleBitmap(v8, right, ClientHeight);
    v16 = SelectObject(CompatibleDC, ho);
    v17 = *((_DWORD *)this + 33);
    v41 = v16;
    v18 = v17 != 0 ? 0xFFFFFFFE : 0;
    SysColorBrush = GetSysColorBrush(v18 + 15);
    FillRect(CompatibleDC, &Rect, SysColorBrush);
    v35 = 4;
    SetBkMode(CompatibleDC, 2);
    SysColor = GetSysColor(v18 + 15);
    SetBkColor(CompatibleDC, SysColor);
    v21 = GetSysColor(v17 != 0 ? 14 : 18);
    SetTextColor(CompatibleDC, v21);
    LineHeight = CBody::lGetLineHeight(this, CompatibleDC);
    v23 = *((_DWORD *)this + 81) == 1;
    cx = LineHeight;
    v36.cx = LineHeight;
    if ( !v23 || (v25 = (char *)*((_QWORD *)this + 51), (v26 = *v25) == 0) )
    {
LABEL_53:
      BitBlt(v8, 0, 0, right, cy, CompatibleDC, 0, 0, 0xCC0020u);
      if ( !*((_QWORD *)this + 11) )
      {
        v32 = GetSysColorBrush(5);
        v33 = SelectObject(v8, v32);
        GetClientRect(*((HWND *)this + 13), &Rect);
        (*(void (__fastcall **)(CBody *, struct tagRECT *))(*(_QWORD *)this + 48LL))(this, &Rect);
        PatBlt(v8, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0xF00021u);
        SelectObject(v8, v33);
      }
      SelectObject(CompatibleDC, v41);
      RestoreDC(CompatibleDC, nSavedDC);
      DeleteObject(ho);
      DeleteDC(CompatibleDC);
      EndPaint(*((HWND *)this + 13), &Paint);
      v34 = (CCommunityRatings *)*((_QWORD *)this + 80);
      if ( v34 )
        CCommunityRatings::Refresh(v34);
      return 0;
    }
    v27 = 4;
    while ( 1 )
    {
      if ( v26 == 38 )
      {
        if ( *++v25 == 67 )
          goto LABEL_45;
        switch ( *v25 )
        {
          case 'F':
LABEL_39:
            if ( *v25 == 102 || *((_DWORD *)this + 104) )
            {
              CBody::OutputHeaderText(this, CompatibleDC, (const unsigned __int16 *)0x488, &v35, v27, v13, 3u);
              v35 += 4;
              if ( *((_DWORD *)this + 104) )
              {
                CBody::OutputHeaderText(this, CompatibleDC, *((const unsigned __int16 **)this + 53), &v35, v27, v13, 0);
                v31 = *((_QWORD *)this + 80);
                if ( v31 )
                {
                  if ( *(_DWORD *)(v31 + 328) )
                    CCommunityRatings::AddMVPImage(v30, CompatibleDC, &v35, v27);
                }
              }
            }
            goto LABEL_50;
          case 'S':
            goto LABEL_33;
          case 'T':
LABEL_28:
            if ( *v25 == 116 || *((_DWORD *)this + 112) )
            {
              CBody::OutputHeaderText(this, CompatibleDC, (const unsigned __int16 *)0x48A, &v35, v27, v13, 3u);
              v35 += 4;
              if ( *((_DWORD *)this + 112) )
              {
                v28 = (const unsigned __int16 *)*((_QWORD *)this + 57);
                goto LABEL_49;
              }
            }
            goto LABEL_50;
          case 'b':
            v35 = 4;
            v27 += cx + 2;
            break;
          case 'c':
LABEL_45:
            if ( *v25 == 99 || *((_DWORD *)this + 120) )
            {
              CBody::OutputHeaderText(this, CompatibleDC, (const unsigned __int16 *)0x48B, &v35, v27, v13, 3u);
              v35 += 4;
              if ( *((_DWORD *)this + 120) )
              {
                v28 = (const unsigned __int16 *)*((_QWORD *)this + 61);
                goto LABEL_49;
              }
            }
LABEL_50:
            cx = v36.cx;
            v35 += 8;
            break;
          case 'f':
            goto LABEL_39;
          case 's':
LABEL_33:
            if ( *v25 == 115 || (v29 = (_WORD *)*((_QWORD *)this + 64)) != 0 && *v29 )
            {
              CBody::OutputHeaderText(this, CompatibleDC, (const unsigned __int16 *)0x48D, &v35, v27, v13, 3u);
              v35 += 4;
            }
            v28 = (const unsigned __int16 *)*((_QWORD *)this + 64);
            if ( v28 )
LABEL_49:
              CBody::OutputHeaderText(this, CompatibleDC, v28, &v35, v27, v13, 0);
            goto LABEL_50;
          case 't':
            goto LABEL_28;
        }
      }
      v26 = *++v25;
      if ( !*v25 )
      {
        v8 = v40;
        goto LABEL_53;
      }
    }
  }
  if ( *((_QWORD *)this + 11) )
    return 1;
  GetClientRect(*((HWND *)this + 13), &Rect);
  (*(void (__fastcall **)(CBody *, struct tagRECT *))(*(_QWORD *)this + 48LL))(this, &Rect);
  v3 = BeginPaint(*((HWND *)this + 13), &Paint);
  v4 = v3;
  if ( (*((_BYTE *)this + 232) & 2) != 0 )
    DrawEdge(v3, &Rect, 0xAu, 0x200Fu);
  v5 = GetSysColorBrush(5);
  v6 = SelectObject(v4, v5);
  PatBlt(v4, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0xF00021u);
  SelectObject(v4, v6);
  EndPaint(*((HWND *)this + 13), &Paint);
  return 0;
}

```

## disassembly

```asm
0x18007b108  push    rbp
0x18007b10a  push    rbx
0x18007b10b  push    rsi
0x18007b10c  push    rdi
0x18007b10d  push    r12
0x18007b10f  push    r13
0x18007b111  push    r14
0x18007b113  push    r15
0x18007b115  lea     rbp, [rsp-18h]
0x18007b11a  sub     rsp, 118h
0x18007b121  mov     rax, cs:__security_cookie
0x18007b128  xor     rax, rsp
0x18007b12b  mov     [rbp+50h+var_50], rax
0x18007b12f  xor     edx, edx; Val
0x18007b131  mov     rsi, rcx
0x18007b134  lea     rcx, [rbp+50h+Paint]; void *
0x18007b138  lea     r8d, [rdx+48h]; Size
0x18007b13c  call    memset_0
0x18007b141  mov     eax, [rsi+144h]
0x18007b147  xor     edi, edi
0x18007b149  dec     eax
0x18007b14b  mov     [rsp+150h+var_E8], rdi
0x18007b150  xorps   xmm0, xmm0
0x18007b153  xorps   xmm1, xmm1
0x18007b156  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x18007b15a  movups  xmmword ptr [rbp+50h+var_B8.left], xmm1
0x18007b15e  test    eax, 0FFFFFFFDh
0x18007b163  jz      loc_18007B233
0x18007b169  cmp     [rsi+58h], rdi
0x18007b16d  jnz     loc_18007B229
0x18007b173  mov     rcx, [rsi+68h]; hWnd
0x18007b177  lea     rdx, [rbp+50h+Rect]; lpRect
0x18007b17b  call    cs:__imp_GetClientRect
0x18007b181  mov     rax, [rsi]
0x18007b184  lea     rdx, [rbp+50h+Rect]
0x18007b188  mov     rcx, rsi
0x18007b18b  mov     rax, [rax+30h]
0x18007b18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b194  mov     rcx, [rsi+68h]; hWnd
0x18007b198  lea     rdx, [rbp+50h+Paint]; lpPaint
0x18007b19c  call    cs:__imp_BeginPaint
0x18007b1a2  test    byte ptr [rsi+0E8h], 2
0x18007b1a9  mov     rdi, rax
0x18007b1ac  jz      short loc_18007B1C7
0x18007b1ae  mov     r9d, 200Fh; grfFlags
0x18007b1b4  lea     rdx, [rbp+50h+Rect]; qrc
0x18007b1b8  mov     r8d, 0Ah; edge
0x18007b1be  mov     rcx, rax; hdc
0x18007b1c1  call    cs:__imp_DrawEdge
0x18007b1c7  mov     ecx, 5; nIndex
0x18007b1cc  call    cs:__imp_GetSysColorBrush
0x18007b1d2  mov     rdx, rax; h
0x18007b1d5  mov     rcx, rdi; hdc
0x18007b1d8  call    cs:__imp_SelectObject
0x18007b1de  mov     ecx, [rbp+50h+Rect.bottom]
0x18007b1e1  mov     rbx, rax
0x18007b1e4  mov     r8d, [rbp+50h+Rect.top]; y
0x18007b1e8  sub     ecx, r8d
0x18007b1eb  mov     r9d, [rbp+50h+Rect.right]
0x18007b1ef  mov     edx, [rbp+50h+Rect.left]; x
0x18007b1f2  sub     r9d, edx; w
0x18007b1f5  mov     [rsp+150h+rop], 0F00021h; rop
0x18007b1fd  mov     [rsp+150h+h], ecx; h
0x18007b201  mov     rcx, rdi; hdc
0x18007b204  call    cs:__imp_PatBlt
0x18007b20a  mov     rdx, rbx; h
0x18007b20d  mov     rcx, rdi; hdc
0x18007b210  call    cs:__imp_SelectObject
0x18007b216  mov     rcx, [rsi+68h]; hWnd
0x18007b21a  lea     rdx, [rbp+50h+Paint]; lpPaint
0x18007b21e  call    cs:__imp_EndPaint
0x18007b224  jmp     loc_18007B701
0x18007b229  mov     eax, 1
0x18007b22e  jmp     loc_18007B703
0x18007b233  mov     rcx, [rsi+68h]; hWnd
0x18007b237  lea     rdx, [rbp+50h+Paint]; lpPaint
0x18007b23b  call    cs:__imp_BeginPaint
0x18007b241  mov     rcx, rax; hdc
0x18007b244  mov     [rsp+150h+var_E0], rax
0x18007b249  mov     r12, rax
0x18007b24c  call    cs:__imp_CreateCompatibleDC
0x18007b252  mov     rcx, rax; hdc
0x18007b255  mov     r15, rax
0x18007b258  call    cs:__imp_SaveDC
0x18007b25e  mov     rcx, [rsi+220h]
0x18007b265  mov     [rsp+150h+nSavedDC], eax
0x18007b269  test    rcx, rcx
0x18007b26c  jz      short loc_18007B298
0x18007b26e  mov     rdx, [rcx]
0x18007b271  lea     r9, [rsp+150h+var_E8]
0x18007b276  xor     r8d, r8d
0x18007b279  mov     rax, [rdx+20h]
0x18007b27d  lea     edx, [r8+1]
0x18007b281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b286  test    eax, eax
0x18007b288  jnz     short loc_18007B298
0x18007b28a  mov     rdx, [rsp+150h+var_E8]; h
0x18007b28f  mov     rcx, r15; hdc
0x18007b292  call    cs:__imp_SelectObject
0x18007b298  mov     rcx, [rsi+68h]; hWnd
0x18007b29c  lea     rdx, [rbp+50h+Rect]; lpRect
0x18007b2a0  call    cs:__imp_GetClientRect
0x18007b2a6  mov     r13d, [rbp+50h+Rect.right]
0x18007b2aa  mov     ecx, 5; nIndex
0x18007b2af  call    cs:__imp_GetSystemMetrics
0x18007b2b5  mov     r14d, r13d
0x18007b2b8  mov     rcx, rsi; this
0x18007b2bb  lea     eax, ds:4[rax*2]
0x18007b2c2  sub     r14d, eax
0x18007b2c5  call    ?lGetClientHeight@CBody@@AEAAJXZ; CBody::lGetClientHeight(void)
0x18007b2ca  mov     ebx, eax
0x18007b2cc  mov     [rsp+150h+cy], eax
0x18007b2d0  cmp     [rsi+14Ch], edi
0x18007b2d6  jz      short loc_18007B2F1
0x18007b2d8  mov     rcx, [rsi+180h]; hWnd
0x18007b2df  lea     rdx, [rbp+50h+var_B8]; lpRect
0x18007b2e3  call    cs:__imp_GetClientRect
0x18007b2e9  sub     r14d, [rbp+50h+var_B8.right]
0x18007b2ed  sub     r14d, 4
0x18007b2f1  mov     rcx, [rsi+280h]; this
0x18007b2f8  test    rcx, rcx
0x18007b2fb  jz      short loc_18007B315
0x18007b2fd  lea     rdx, [rsp+150h+var_F8]; struct tagSIZE *
0x18007b302  mov     qword ptr [rsp+150h+var_F8.cx], rdi
0x18007b307  call    ?GetSize@CCommunityRatings@@QEAAJPEAUtagSIZE@@@Z; CCommunityRatings::GetSize(tagSIZE *)
0x18007b30c  test    eax, eax
0x18007b30e  js      short loc_18007B315
0x18007b310  sub     r14d, [rsp+150h+var_F8.cx]
0x18007b315  mov     r8d, ebx; cy
0x18007b318  mov     edx, r13d; cx
0x18007b31b  mov     rcx, r12; hdc
0x18007b31e  call    cs:__imp_CreateCompatibleBitmap
0x18007b324  mov     rdx, rax; h
0x18007b327  mov     [rbp+50h+ho], rax
0x18007b32b  mov     rcx, r15; hdc
0x18007b32e  call    cs:__imp_SelectObject
0x18007b334  mov     edi, [rsi+84h]
0x18007b33a  mov     ecx, edi
0x18007b33c  neg     ecx
0x18007b33e  mov     [rsp+150h+var_D8], rax
0x18007b343  sbb     ebx, ebx
0x18007b345  and     ebx, 0FFFFFFFEh
0x18007b348  lea     ecx, [rbx+0Fh]; nIndex
0x18007b34b  call    cs:__imp_GetSysColorBrush
0x18007b351  lea     rdx, [rbp+50h+Rect]; lprc
0x18007b355  mov     rcx, r15; hDC
0x18007b358  mov     r8, rax; hbr
0x18007b35b  call    cs:__imp_FillRect
0x18007b361  mov     edx, 2; mode
0x18007b366  mov     [rsp+150h+var_100], 4
0x18007b36e  mov     rcx, r15; hdc
0x18007b371  call    cs:__imp_SetBkMode
0x18007b377  lea     ecx, [rbx+0Fh]; nIndex
0x18007b37a  call    cs:__imp_GetSysColor
0x18007b380  mov     edx, eax; color
0x18007b382  mov     rcx, r15; hdc
0x18007b385  call    cs:__imp_SetBkColor
0x18007b38b  neg     edi
0x18007b38d  sbb     ecx, ecx
0x18007b38f  and     ecx, 0FFFFFFFCh
0x18007b392  add     ecx, 12h; nIndex
0x18007b395  call    cs:__imp_GetSysColor
0x18007b39b  mov     edx, eax; color
0x18007b39d  mov     rcx, r15; hdc
0x18007b3a0  call    cs:__imp_SetTextColor
0x18007b3a6  mov     rdx, r15; HDC
0x18007b3a9  mov     rcx, rsi; this
0x18007b3ac  call    ?lGetLineHeight@CBody@@AEAAJPEAUHDC__@@@Z; CBody::lGetLineHeight(HDC__ *)
0x18007b3b1  cmp     dword ptr [rsi+144h], 1
0x18007b3b8  mov     edx, eax
0x18007b3ba  mov     [rsp+150h+var_F8.cx], eax
0x18007b3be  jnz     loc_18007B610
0x18007b3c4  mov     rdi, [rsi+198h]
0x18007b3cb  mov     cl, [rdi]
0x18007b3cd  test    cl, cl
0x18007b3cf  jz      loc_18007B610
0x18007b3d5  mov     ebx, 4
0x18007b3da  xor     r12d, r12d
0x18007b3dd  cmp     cl, 26h ; '&'
0x18007b3e0  jnz     loc_18007B5FE
0x18007b3e6  inc     rdi
0x18007b3e9  movsx   ecx, byte ptr [rdi]
0x18007b3ec  sub     ecx, 43h ; 'C'
0x18007b3ef  jz      loc_18007B58D
0x18007b3f5  sub     ecx, 3
0x18007b3f8  jz      loc_18007B4F2
0x18007b3fe  sub     ecx, 0Dh
0x18007b401  jz      loc_18007B49A
0x18007b407  sub     ecx, 1
0x18007b40a  jz      short loc_18007B431
0x18007b40c  sub     ecx, 0Eh
0x18007b40f  jz      short loc_18007B488
0x18007b411  sub     ecx, 1
0x18007b414  jz      loc_18007B58D
0x18007b41a  sub     ecx, 3
0x18007b41d  jz      loc_18007B4F2
0x18007b423  sub     ecx, 0Dh
0x18007b426  jz      short loc_18007B49A
0x18007b428  cmp     ecx, 1
0x18007b42b  jnz     loc_18007B5FE
0x18007b431  cmp     byte ptr [rdi], 74h ; 't'
0x18007b434  jz      short loc_18007B443
0x18007b436  cmp     [rsi+1C0h], r12d
0x18007b43d  jbe     loc_18007B5F5
0x18007b443  mov     [rsp+150h+x1], 3; unsigned int
0x18007b44b  lea     r9, [rsp+150h+var_100]; int *
0x18007b450  mov     [rsp+150h+rop], r14d; int
0x18007b455  mov     r8d, 48Ah; unsigned __int16 *
0x18007b45b  mov     rdx, r15; HDC
0x18007b45e  mov     [rsp+150h+h], ebx; int
0x18007b462  mov     rcx, rsi; this
0x18007b465  call    ?OutputHeaderText@CBody@@AEAAXPEAUHDC__@@PEBGPEAHHHK@Z; CBody::OutputHeaderText(HDC__ *,ushort const *,int *,int,int,ulong)
0x18007b46a  add     [rsp+150h+var_100], 4
0x18007b46f  cmp     [rsi+1C0h], r12d
0x18007b476  jbe     loc_18007B5F5
0x18007b47c  mov     r8, [rsi+1C8h]
0x18007b483  jmp     loc_18007B5D7
0x18007b488  add     ebx, 2
0x18007b48b  mov     [rsp+150h+var_100], 4
0x18007b493  add     ebx, edx
0x18007b495  jmp     loc_18007B5FE
0x18007b49a  cmp     byte ptr [rdi], 73h ; 's'
0x18007b49d  jz      short loc_18007B4B1
0x18007b49f  mov     rax, [rsi+200h]
0x18007b4a6  test    rax, rax
0x18007b4a9  jz      short loc_18007B4DD
0x18007b4ab  cmp     [rax], r12w
0x18007b4af  jz      short loc_18007B4DD
0x18007b4b1  mov     [rsp+150h+x1], 3; unsigned int
0x18007b4b9  lea     r9, [rsp+150h+var_100]; int *
0x18007b4be  mov     [rsp+150h+rop], r14d; int
0x18007b4c3  mov     r8d, 48Dh; unsigned __int16 *
0x18007b4c9  mov     rdx, r15; HDC
0x18007b4cc  mov     [rsp+150h+h], ebx; int
0x18007b4d0  mov     rcx, rsi; this
0x18007b4d3  call    ?OutputHeaderText@CBody@@AEAAXPEAUHDC__@@PEBGPEAHHHK@Z; CBody::OutputHeaderText(HDC__ *,ushort const *,int *,int,int,ulong)
0x18007b4d8  add     [rsp+150h+var_100], 4
0x18007b4dd  mov     r8, [rsi+200h]
0x18007b4e4  test    r8, r8
0x18007b4e7  jz      loc_18007B5F5
0x18007b4ed  jmp     loc_18007B5D7
0x18007b4f2  cmp     byte ptr [rdi], 66h ; 'f'
0x18007b4f5  jz      short loc_18007B504
0x18007b4f7  cmp     [rsi+1A0h], r12d
0x18007b4fe  jbe     loc_18007B5F5
0x18007b504  mov     [rsp+150h+x1], 3; unsigned int
0x18007b50c  lea     r9, [rsp+150h+var_100]; int *
0x18007b511  mov     [rsp+150h+rop], r14d; int
0x18007b516  mov     r8d, 488h; unsigned __int16 *
0x18007b51c  mov     rdx, r15; HDC
0x18007b51f  mov     [rsp+150h+h], ebx; int
0x18007b523  mov     rcx, rsi; this
0x18007b526  call    ?OutputHeaderText@CBody@@AEAAXPEAUHDC__@@PEBGPEAHHHK@Z; CBody::OutputHeaderText(HDC__ *,ushort const *,int *,int,int,ulong)
0x18007b52b  add     [rsp+150h+var_100], 4
0x18007b530  cmp     [rsi+1A0h], r12d
0x18007b537  jbe     loc_18007B5F5
0x18007b53d  mov     r8, [rsi+1A8h]; unsigned __int16 *
0x18007b544  lea     r9, [rsp+150h+var_100]; int *
0x18007b549  mov     [rsp+150h+x1], r12d; unsigned int
0x18007b54e  mov     rdx, r15; HDC
0x18007b551  mov     [rsp+150h+rop], r14d; int
0x18007b556  mov     rcx, rsi; this
0x18007b559  mov     [rsp+150h+h], ebx; int
0x18007b55d  call    ?OutputHeaderText@CBody@@AEAAXPEAUHDC__@@PEBGPEAHHHK@Z; CBody::OutputHeaderText(HDC__ *,ushort const *,int *,int,int,ulong)
0x18007b562  mov     rax, [rsi+280h]
0x18007b569  test    rax, rax
0x18007b56c  jz      loc_18007B5F5
0x18007b572  cmp     [rax+148h], r12d
0x18007b579  jz      short loc_18007B5F5
0x18007b57b  mov     r9d, ebx; int
0x18007b57e  lea     r8, [rsp+150h+var_100]; int *
0x18007b583  mov     rdx, r15; HDC
0x18007b586  call    ?AddMVPImage@CCommunityRatings@@QEAAJPEAUHDC__@@PEAHH@Z; CCommunityRatings::AddMVPImage(HDC__ *,int *,int)
0x18007b58b  jmp     short loc_18007B5F5
0x18007b58d  cmp     byte ptr [rdi], 63h ; 'c'
0x18007b590  jz      short loc_18007B59B
0x18007b592  cmp     [rsi+1E0h], r12d
0x18007b599  jbe     short loc_18007B5F5
0x18007b59b  mov     [rsp+150h+x1], 3; unsigned int
0x18007b5a3  lea     r9, [rsp+150h+var_100]; int *
0x18007b5a8  mov     [rsp+150h+rop], r14d; int
0x18007b5ad  mov     r8d, 48Bh; unsigned __int16 *
0x18007b5b3  mov     rdx, r15; HDC
0x18007b5b6  mov     [rsp+150h+h], ebx; int
0x18007b5ba  mov     rcx, rsi; this
0x18007b5bd  call    ?OutputHeaderText@CBody@@AEAAXPEAUHDC__@@PEBGPEAHHHK@Z; CBody::OutputHeaderText(HDC__ *,ushort const *,int *,int,int,ulong)
0x18007b5c2  add     [rsp+150h+var_100], 4
0x18007b5c7  cmp     [rsi+1E0h], r12d
0x18007b5ce  jbe     short loc_18007B5F5
0x18007b5d0  mov     r8, [rsi+1E8h]; unsigned __int16 *
0x18007b5d7  mov     [rsp+150h+x1], r12d; unsigned int
0x18007b5dc  lea     r9, [rsp+150h+var_100]; int *
0x18007b5e1  mov     [rsp+150h+rop], r14d; int
0x18007b5e6  mov     rdx, r15; HDC
0x18007b5e9  mov     rcx, rsi; this
0x18007b5ec  mov     [rsp+150h+h], ebx; int
0x18007b5f0  call    ?OutputHeaderText@CBody@@AEAAXPEAUHDC__@@PEBGPEAHHHK@Z; CBody::OutputHeaderText(HDC__ *,ushort const *,int *,int,int,ulong)
0x18007b5f5  mov     edx, [rsp+150h+var_F8.cx]
0x18007b5f9  add     [rsp+150h+var_100], 8
0x18007b5fe  inc     rdi
  ... truncated ...
```
