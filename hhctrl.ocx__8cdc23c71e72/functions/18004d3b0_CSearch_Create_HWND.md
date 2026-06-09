# CSearch::Create(HWND__ *)

- ea: `0x18004d3b0`
- end: `0x18004dc7b`
- name: `?Create@CSearch@@UEAAHPEAUHWND__@@@Z`
- size: `2251`
- prototype: `__int64 __fastcall(CSearch *__hidden this, HWND hWnd)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x180001728`
- `0x180006708`
- `0x1800102d4`
- `0x18001054c`
- `0x180010b14`
- `0x180010b34`
- `0x180010fcc`
- `0x1800128a8`
- `0x180042e6c`
- `0x18004d3b0`
- `0x18004dd90`
- `0x180051cfc`
- `0x180051e48`
- `0x180066c20`
- `0x180066f80`
- `0x1800673f0`
- `0x1800674e0`
- `0x1800675c0`
- `0x180067798`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!MoveWindow` at `0x18004d513`
- `USER32!MoveWindow` at `0x18004d572`
- `USER32!MoveWindow` at `0x18004d813`
- `USER32!MoveWindow` at `0x18004d885`
- `USER32!MoveWindow` at `0x18004db25`
- `USER32!MoveWindow` at `0x18004db86`
- `USER32!MoveWindow` at `0x18004d513`
- `USER32!MoveWindow` at `0x18004d572`
- `USER32!MoveWindow` at `0x18004d813`
- `USER32!MoveWindow` at `0x18004d885`
- `USER32!MoveWindow` at `0x18004db25`
- `USER32!MoveWindow` at `0x18004db86`
- `USER32!CopyRect` at `0x18004d43b`
- `USER32!CopyRect` at `0x18004d43b`
- `USER32!SetWindowTextA` at `0x18004d57f`
- `USER32!SetWindowTextA` at `0x18004d8a5`
- `USER32!SetWindowTextA` at `0x18004d57f`
- `USER32!SetWindowTextA` at `0x18004d8a5`
- `USER32!SetWindowTextW` at `0x18004d520`
- `USER32!SetWindowTextW` at `0x18004d833`
- `USER32!SetWindowTextW` at `0x18004d520`
- `USER32!SetWindowTextW` at `0x18004d833`
- `USER32!SetFocus` at `0x18004db9f`
- `USER32!SetFocus` at `0x18004db9f`
- `USER32!SetWindowLongPtrA` at `0x18004d63f`
- `USER32!SetWindowLongPtrA` at `0x18004d72a`
- `USER32!SetWindowLongPtrA` at `0x18004d9b0`
- `USER32!SetWindowLongPtrA` at `0x18004dac4`
- `USER32!SetWindowLongPtrA` at `0x18004d63f`
- `USER32!SetWindowLongPtrA` at `0x18004d72a`
- `USER32!SetWindowLongPtrA` at `0x18004d9b0`
- `USER32!SetWindowLongPtrA` at `0x18004dac4`
- `USER32!SetWindowPos` at `0x18004d9e4`
- `USER32!SetWindowPos` at `0x18004d9e4`
- `USER32!GetSystemMetrics` at `0x18004d424`
- `USER32!GetSystemMetrics` at `0x18004d424`
- `USER32!DestroyWindow` at `0x18004dbdd`
- `USER32!DestroyWindow` at `0x18004dbf4`
- `USER32!DestroyWindow` at `0x18004dc0b`
- `USER32!DestroyWindow` at `0x18004dc22`
- `USER32!DestroyWindow` at `0x18004dc39`
- `USER32!DestroyWindow` at `0x18004dc50`
- `USER32!DestroyWindow` at `0x18004dbdd`
- `USER32!DestroyWindow` at `0x18004dbf4`
- `USER32!DestroyWindow` at `0x18004dc0b`
- `USER32!DestroyWindow` at `0x18004dc22`
- `USER32!DestroyWindow` at `0x18004dc39`
- `USER32!DestroyWindow` at `0x18004dc50`
- `USER32!GetWindowRect` at `0x18004d7b8`
- `USER32!GetWindowRect` at `0x18004dae5`
- `USER32!GetWindowRect` at `0x18004db46`
- `USER32!GetWindowRect` at `0x18004d7b8`
- `USER32!GetWindowRect` at `0x18004dae5`
- `USER32!GetWindowRect` at `0x18004db46`
- `USER32!EnableWindow` at `0x18004da8b`
- `USER32!EnableWindow` at `0x18004dbb4`
- `USER32!EnableWindow` at `0x18004da8b`
- `USER32!EnableWindow` at `0x18004dbb4`
- `USER32!SendMessageA` at `0x18004d4b8`
- `USER32!SendMessageA` at `0x18004d655`
- `USER32!SendMessageA` at `0x18004d671`
- `USER32!SendMessageA` at `0x18004d826`
- `USER32!SendMessageA` at `0x18004d898`
- `USER32!SendMessageA` at `0x18004d93f`
- `USER32!SendMessageA` at `0x18004da00`
- `USER32!SendMessageA` at `0x18004dad7`
- `USER32!SendMessageA` at `0x18004db38`
- `USER32!SendMessageA` at `0x18004d4b8`
- `USER32!SendMessageA` at `0x18004d655`
- `USER32!SendMessageA` at `0x18004d671`
- `USER32!SendMessageA` at `0x18004d826`
- `USER32!SendMessageA` at `0x18004d898`
- `USER32!SendMessageA` at `0x18004d93f`
- `USER32!SendMessageA` at `0x18004da00`
- `USER32!SendMessageA` at `0x18004dad7`
- `USER32!SendMessageA` at `0x18004db38`
- `USER32!IsWindowUnicode` at `0x18004d974`
- `USER32!IsWindowUnicode` at `0x18004d974`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearch::Create(CSearch *this, HWND hWnd)
{
  HFONT UIFont; // r14
  HWND ParentSize; // rsi
  HWND Window; // rax
  const WCHAR *StringResourceW; // rbx
  unsigned int nHeight; // eax
  const char *StringResource; // rbx
  unsigned int v10; // eax
  HWND v11; // rax
  HFONT ContentFont; // rax
  HINSTANCE v13; // rbx
  const unsigned __int16 *v14; // rax
  HWND v15; // rax
  HWND v16; // rax
  const WCHAR *v17; // rbx
  unsigned int v18; // eax
  const char *v19; // rbx
  unsigned int v20; // eax
  HWND ControlWindow; // rax
  CFTSListView *v22; // rax
  BOOL v23; // ebx
  HWND v24; // rdx
  HFONT AccessableContentFont; // rax
  HINSTANCE v26; // rbx
  const unsigned __int16 *v27; // rax
  HWND v28; // rax
  const WCHAR *v29; // rax
  unsigned int ButtonDimensionsW; // eax
  const WCHAR *v31; // rax
  unsigned int v32; // eax
  int HasText; // eax
  void *v35; // [rsp+58h] [rbp-31h]
  void *v36; // [rsp+58h] [rbp-31h]
  void *v37; // [rsp+58h] [rbp-31h]
  void *v38; // [rsp+58h] [rbp-31h]
  void *v39; // [rsp+58h] [rbp-31h]
  int v40[2]; // [rsp+70h] [rbp-19h] BYREF
  struct tagRECT rcDst; // [rsp+78h] [rbp-11h] BYREF
  struct tagRECT Rect; // [rsp+88h] [rbp-1h] BYREF
  RECT rcSrc; // [rsp+98h] [rbp+Fh] BYREF
  struct tagRECT v44; // [rsp+A8h] [rbp+1Fh] BYREF

  rcSrc = 0;
  rcDst = 0;
  Rect = 0;
  v44 = 0;
  UIFont = CResourceCache::GetUIFont(this);
  v40[0] = 0;
  *((_QWORD *)this + 16) = hWnd;
  ParentSize = GetParentSize(&rcSrc, hWnd, *((_DWORD *)this + 30), *((_DWORD *)this + 31));
  rcSrc.top += 2 * GetSystemMetrics(33);
  CopyRect(&rcDst, &rcSrc);
  Window = W_CreateWindowEx(
             0x20u,
             L"STATIC",
             &psz,
             0x40000000u,
             rcDst.left,
             rcDst.top,
             rcDst.right - rcDst.left,
             17,
             ParentSize,
             (HMENU)0xBCA,
             hInstance,
             v35,
             v40);
  *((_QWORD *)this + 12) = Window;
  SendMessageA(Window, 0x30u, (WPARAM)UIFont, 0);
  if ( v40[0] )
  {
    StringResourceW = GetStringResourceW(0x425u);
    nHeight = GetStaticDimensionsW(*((HWND *)this + 12), UIFont, StringResourceW, rcDst.right - rcDst.left) >> 16;
    rcDst.bottom = nHeight + rcDst.top;
    MoveWindow(*((HWND *)this + 12), rcDst.left, rcDst.top, rcDst.right - rcDst.left, nHeight, 0);
    SetWindowTextW(*((HWND *)this + 12), StringResourceW);
  }
  else
  {
    StringResource = GetStringResource(0x425u);
    v10 = GetStaticDimensions(*((HWND *)this + 12), UIFont, StringResource, rcDst.right - rcDst.left) >> 16;
    rcDst.bottom = v10 + rcDst.top;
    MoveWindow(*((HWND *)this + 12), rcDst.left, rcDst.top, rcDst.right - rcDst.left, v10, 0);
    SetWindowTextA(*((HWND *)this + 12), StringResource);
  }
  rcDst.top = rcDst.bottom + 10;
  rcDst.bottom += 34;
  v11 = W_CreateWindowEx(
          g_RTL_Style | 0x200,
          L"EDIT",
          &psz,
          0x40810080u,
          rcDst.left,
          rcDst.top,
          rcDst.right - rcDst.left,
          24,
          ParentSize,
          (HMENU)0xBD0,
          hInstance,
          v36,
          v40);
  *((_QWORD *)this + 8) = v11;
  if ( !v11 )
    goto LABEL_32;
  CSearch::s_lpfnlComboWndProc = W_GetWndProc(v11, v40[0]);
  W_SubClassWindow(*((HWND *)this + 8), (__int64)CSearch::ComboProc, v40[0]);
  SetWindowLongPtrA(*((HWND *)this + 8), -21, (LONG_PTR)this);
  SendMessageA(*((HWND *)this + 8), 0xC5u, 0xFFu, 0);
  ContentFont = CHHWinType::GetContentFont(*((CHHWinType **)this + 2));
  SendMessageA(*((HWND *)this + 8), 0x30u, (WPARAM)ContentFont, 0);
  rcDst.top = rcDst.bottom + 8;
  rcDst.bottom += 32;
  v13 = hInstance;
  v14 = GetStringResourceW(0x409u);
  v15 = W_CreateWindowEx(
          0,
          L"BUTTON",
          v14,
          0x40010000u,
          rcDst.right - 82,
          rcDst.top,
          80,
          24,
          ParentSize,
          (HMENU)0xBC7,
          v13,
          v37,
          v40);
  *((_QWORD *)this + 11) = v15;
  if ( !v15 )
    goto LABEL_32;
  g_lpfnlSearchListBtnWndProc = W_GetWndProc(v15, v40[0]);
  W_SubClassWindow(*((HWND *)this + 11), (__int64)CSearch::ListBtnProc, v40[0]);
  SetWindowLongPtrA(*((HWND *)this + 11), -21, (LONG_PTR)this);
  rcDst.top = rcDst.bottom + 8;
  rcDst.bottom += 25;
  v16 = W_CreateWindowEx(
          0x20u,
          L"STATIC",
          &psz,
          0x40000000u,
          rcDst.left,
          rcDst.top - 17,
          rcDst.right - rcDst.left,
          17,
          ParentSize,
          (HMENU)0xBC9,
          hInstance,
          v38,
          v40);
  *((_QWORD *)this + 13) = v16;
  if ( !v16 )
    goto LABEL_32;
  GetWindowRect(v16, &Rect);
  if ( v40[0] )
  {
    v17 = GetStringResourceW(0x426u);
    v18 = GetStaticDimensionsW(*((HWND *)this + 13), UIFont, v17, Rect.right - Rect.left) >> 16;
    Rect.bottom = v18 + Rect.top;
    MoveWindow(*((HWND *)this + 13), Rect.left, Rect.top, Rect.right - Rect.left, v18, 0);
    SendMessageA(*((HWND *)this + 13), 0x30u, (WPARAM)UIFont, 0);
    SetWindowTextW(*((HWND *)this + 13), v17);
  }
  else
  {
    v19 = GetStringResource(0x426u);
    v20 = GetStaticDimensions(*((HWND *)this + 13), UIFont, v19, Rect.right - Rect.left) >> 16;
    Rect.bottom = v20 + Rect.top;
    MoveWindow(*((HWND *)this + 13), Rect.left, Rect.top, Rect.right - Rect.left, v20, 0);
    SendMessageA(*((HWND *)this + 13), 0x30u, (WPARAM)UIFont, 0);
    SetWindowTextA(*((HWND *)this + 13), v19);
  }
  rcDst.top = rcDst.bottom + 10;
  rcDst.bottom = rcSrc.bottom - 32;
  ControlWindow = (HWND)W_CreateControlWindow(
                          g_RTL_Style | 0x200,
                          1084309517,
                          0,
                          L"HH FTSearch",
                          rcDst.left,
                          rcDst.top,
                          rcDst.right - rcDst.left,
                          rcSrc.bottom - 32 - rcDst.top,
                          ParentSize,
                          3013,
                          hInstance);
  *((_QWORD *)this + 9) = ControlWindow;
  if ( !ControlWindow )
    goto LABEL_32;
  SendMessageA(ControlWindow, 0x1036u, 0, g_RTL_Style | 0x20LL);
  v22 = (CFTSListView *)operator new(0x40u);
  *(_QWORD *)v40 = v22;
  if ( v22 )
    v22 = CFTSListView::CFTSListView(v22, *((struct CExCollection **)this + 3), *((HWND *)this + 9), 0);
  *((_QWORD *)this + 14) = v22;
  v23 = IsWindowUnicode(*((HWND *)this + 9));
  v40[0] = v23;
  CSearch::s_lpfnlListViewWndProc = W_GetWndProc(*((HWND *)this + 9), v23);
  W_SubClassWindow(*((HWND *)this + 9), (__int64)CSearch::ListViewProc, v23);
  SetWindowLongPtrA(*((HWND *)this + 9), -21, (LONG_PTR)this);
  v24 = (HWND)*((_QWORD *)this + 16);
  if ( ParentSize != v24 )
    SetWindowPos(*((HWND *)this + 9), v24, 0, 0, 0, 0, 3u);
  AccessableContentFont = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 2));
  SendMessageA(*((HWND *)this + 9), 0x30u, (WPARAM)AccessableContentFont, 0);
  rcDst.bottom = rcSrc.bottom;
  rcDst.top = rcSrc.bottom - 24;
  v26 = hInstance;
  v27 = GetStringResourceW(0x1020u);
  v28 = W_CreateWindowEx(
          0,
          L"BUTTON",
          v27,
          0x40010000u,
          rcDst.right - 82,
          rcDst.top,
          80,
          24,
          ParentSize,
          (HMENU)0xBBE,
          v26,
          v39,
          v40);
  *((_QWORD *)this + 10) = v28;
  if ( v28 )
  {
    EnableWindow(v28, 0);
    g_lpfnlSearchDisplayBtnWndProc = W_GetWndProc(*((HWND *)this + 10), v40[0]);
    W_SubClassWindow(*((HWND *)this + 10), (__int64)CSearch::DisplayBtnProc, v40[0]);
    SetWindowLongPtrA(*((HWND *)this + 10), -21, (LONG_PTR)this);
    SendMessageA(*((HWND *)this + 10), 0x30u, (WPARAM)UIFont, 0);
    GetWindowRect(*((HWND *)this + 10), &v44);
    v29 = GetStringResourceW(0x1020u);
    ButtonDimensionsW = GetButtonDimensionsW(*((HWND *)this + 10), UIFont, v29);
    MoveWindow(
      *((HWND *)this + 10),
      rcDst.right - (unsigned __int16)ButtonDimensionsW,
      v44.top,
      (unsigned __int16)ButtonDimensionsW,
      HIWORD(ButtonDimensionsW),
      0);
    SendMessageA(*((HWND *)this + 11), 0x30u, (WPARAM)UIFont, 0);
    GetWindowRect(*((HWND *)this + 11), &v44);
    v31 = GetStringResourceW(0x409u);
    v32 = GetButtonDimensionsW(*((HWND *)this + 11), UIFont, v31);
    MoveWindow(
      *((HWND *)this + 11),
      rcDst.right - (unsigned __int16)v32,
      v44.top,
      (unsigned __int16)v32,
      HIWORD(v32),
      0);
    (*(void (__fastcall **)(CSearch *))(*(_QWORD *)this + 40LL))(this);
    SetFocus(*((HWND *)this + 8));
    HasText = W_HasText(*((HWND *)this + 8));
    EnableWindow(*((HWND *)this + 11), HasText);
    CSearch::InitDlgItemArray(this);
    return 1;
  }
  else
  {
LABEL_32:
    if ( (unsigned int)IsValidWindow(*((HWND *)this + 8)) )
      DestroyWindow(*((HWND *)this + 8));
    if ( (unsigned int)IsValidWindow(*((HWND *)this + 11)) )
      DestroyWindow(*((HWND *)this + 11));
    if ( (unsigned int)IsValidWindow(*((HWND *)this + 9)) )
      DestroyWindow(*((HWND *)this + 9));
    if ( (unsigned int)IsValidWindow(*((HWND *)this + 12)) )
      DestroyWindow(*((HWND *)this + 12));
    if ( (unsigned int)IsValidWindow(*((HWND *)this + 13)) )
      DestroyWindow(*((HWND *)this + 13));
    if ( (unsigned int)IsValidWindow(*((HWND *)this + 10)) )
      DestroyWindow(*((HWND *)this + 10));
    return 0;
  }
}

```

## disassembly

```asm
0x18004d3b0  mov     [rsp-8+arg_10], rbx
0x18004d3b5  push    rbp
0x18004d3b6  push    rsi
0x18004d3b7  push    rdi
0x18004d3b8  push    r12
0x18004d3ba  push    r14
0x18004d3bc  lea     rbp, [rsp-37h]
0x18004d3c1  sub     rsp, 0C0h
0x18004d3c8  mov     rax, cs:__security_cookie
0x18004d3cf  xor     rax, rsp
0x18004d3d2  mov     [rbp+57h+var_28], rax
0x18004d3d6  mov     rbx, rdx
0x18004d3d9  mov     rdi, rcx
0x18004d3dc  xorps   xmm0, xmm0
0x18004d3df  movups  xmmword ptr [rbp+57h+rcSrc.left], xmm0
0x18004d3e3  xorps   xmm1, xmm1
0x18004d3e6  movups  xmmword ptr [rbp+57h+rcDst.left], xmm1
0x18004d3ea  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18004d3ee  movups  xmmword ptr [rbp+57h+var_38.left], xmm1
0x18004d3f2  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x18004d3f7  mov     r14, rax
0x18004d3fa  mov     [rbp+57h+var_70], 0
0x18004d401  mov     [rdi+80h], rbx
0x18004d408  mov     r9d, [rdi+7Ch]; int
0x18004d40c  mov     r8d, [rdi+78h]; int
0x18004d410  mov     rdx, rbx; hWnd
0x18004d413  lea     rcx, [rbp+57h+rcSrc]; lprc
0x18004d417  call    ?GetParentSize@@YAPEAUHWND__@@PEAUtagRECT@@PEAU1@HH@Z; GetParentSize(tagRECT *,HWND__ *,int,int)
0x18004d41c  mov     rsi, rax
0x18004d41f  mov     ecx, 21h ; '!'; nIndex
0x18004d424  call    cs:__imp_GetSystemMetrics
0x18004d42a  mov     ecx, [rbp+57h+rcSrc.top]
0x18004d42d  lea     edx, [rcx+rax*2]
0x18004d430  mov     [rbp+57h+rcSrc.top], edx
0x18004d433  lea     rdx, [rbp+57h+rcSrc]; lprcSrc
0x18004d437  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18004d43b  call    cs:__imp_CopyRect
0x18004d441  mov     rcx, cs:hInstance
0x18004d448  mov     r8d, [rbp+57h+rcDst.left]
0x18004d44c  mov     edx, [rbp+57h+rcDst.right]
0x18004d44f  sub     edx, r8d
0x18004d452  lea     rax, [rbp+57h+var_70]
0x18004d456  mov     [rsp+0E0h+var_80], rax; int *
0x18004d45b  mov     [rsp+0E0h+var_90], rcx; HINSTANCE
0x18004d460  mov     [rsp+0E0h+var_98], 0BCAh; HMENU
0x18004d469  mov     [rsp+0E0h+var_A0], rsi; HWND
0x18004d46e  mov     [rsp+0E0h+var_A8], 11h; int
0x18004d476  mov     [rsp+0E0h+uFlags], edx; int
0x18004d47a  mov     eax, [rbp+57h+rcDst.top]
0x18004d47d  mov     [rsp+0E0h+bRepaint], eax; int
0x18004d481  mov     [rsp+0E0h+nHeight], r8d; int
0x18004d486  mov     r9d, 40000000h; dwStyle
0x18004d48c  lea     r8, psz; unsigned __int16 *
0x18004d493  lea     rdx, aStatic; "STATIC"
0x18004d49a  mov     ecx, 20h ; ' '; dwExStyle
0x18004d49f  call    ?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z; W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)
0x18004d4a4  mov     [rdi+60h], rax
0x18004d4a8  xor     r9d, r9d; lParam
0x18004d4ab  mov     r8, r14; wParam
0x18004d4ae  lea     r12d, [r9+30h]
0x18004d4b2  mov     edx, r12d; Msg
0x18004d4b5  mov     rcx, rax; hWnd
0x18004d4b8  call    cs:__imp_SendMessageA
0x18004d4be  mov     ecx, 425h; uID
0x18004d4c3  cmp     [rbp+57h+var_70], 0
0x18004d4c7  jz      short loc_18004D528
0x18004d4c9  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18004d4ce  mov     rbx, rax
0x18004d4d1  mov     r9d, [rbp+57h+rcDst.right]
0x18004d4d5  sub     r9d, [rbp+57h+rcDst.left]; int
0x18004d4d9  mov     r8, rax; lpString
0x18004d4dc  mov     rdx, r14; h
0x18004d4df  mov     rcx, [rdi+60h]; hWnd
0x18004d4e3  call    ?GetStaticDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBGH@Z; GetStaticDimensionsW(HWND__ *,HFONT__ *,ushort const *,int)
0x18004d4e8  shr     eax, 10h
0x18004d4eb  mov     r8d, [rbp+57h+rcDst.top]; Y
0x18004d4ef  lea     ecx, [rax+r8]
0x18004d4f3  mov     [rbp+57h+rcDst.bottom], ecx
0x18004d4f6  mov     edx, [rbp+57h+rcDst.left]; X
0x18004d4f9  mov     r9d, [rbp+57h+rcDst.right]
0x18004d4fd  sub     ecx, r8d
0x18004d500  sub     r9d, edx; nWidth
0x18004d503  mov     [rsp+0E0h+bRepaint], 0; bRepaint
0x18004d50b  mov     [rsp+0E0h+nHeight], ecx; nHeight
0x18004d50f  mov     rcx, [rdi+60h]; hWnd
0x18004d513  call    cs:__imp_MoveWindow
0x18004d519  mov     rdx, rbx; lpString
0x18004d51c  mov     rcx, [rdi+60h]; hWnd
0x18004d520  call    cs:__imp_SetWindowTextW
0x18004d526  jmp     short loc_18004D585
0x18004d528  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18004d52d  mov     rbx, rax
0x18004d530  mov     r9d, [rbp+57h+rcDst.right]
0x18004d534  sub     r9d, [rbp+57h+rcDst.left]; int
0x18004d538  mov     r8, rax; char *
0x18004d53b  mov     rdx, r14; h
0x18004d53e  mov     rcx, [rdi+60h]; hWnd
0x18004d542  call    ?GetStaticDimensions@@YAKPEAUHWND__@@PEAUHFONT__@@PEBDH@Z; GetStaticDimensions(HWND__ *,HFONT__ *,char const *,int)
0x18004d547  shr     eax, 10h
0x18004d54a  mov     r8d, [rbp+57h+rcDst.top]; Y
0x18004d54e  lea     ecx, [rax+r8]
0x18004d552  mov     [rbp+57h+rcDst.bottom], ecx
0x18004d555  mov     edx, [rbp+57h+rcDst.left]; X
0x18004d558  mov     r9d, [rbp+57h+rcDst.right]
0x18004d55c  sub     ecx, r8d
0x18004d55f  sub     r9d, edx; nWidth
0x18004d562  mov     [rsp+0E0h+bRepaint], 0; bRepaint
0x18004d56a  mov     [rsp+0E0h+nHeight], ecx; nHeight
0x18004d56e  mov     rcx, [rdi+60h]; hWnd
0x18004d572  call    cs:__imp_MoveWindow
0x18004d578  mov     rdx, rbx; lpString
0x18004d57b  mov     rcx, [rdi+60h]; hWnd
0x18004d57f  call    cs:__imp_SetWindowTextA
0x18004d585  mov     r8d, [rbp+57h+rcDst.bottom]
0x18004d589  add     r8d, 0Ah
0x18004d58d  mov     [rbp+57h+rcDst.top], r8d
0x18004d591  lea     eax, [r8+18h]
0x18004d595  mov     [rbp+57h+rcDst.bottom], eax
0x18004d598  mov     edx, [rbp+57h+rcDst.left]
0x18004d59b  mov     ecx, [rbp+57h+rcDst.right]
0x18004d59e  sub     ecx, edx
0x18004d5a0  mov     r10d, cs:?g_RTL_Style@@3KA; ulong g_RTL_Style
0x18004d5a7  bts     r10d, 9
0x18004d5ac  lea     rax, [rbp+57h+var_70]
0x18004d5b0  mov     [rsp+0E0h+var_80], rax; int *
0x18004d5b5  mov     rax, cs:hInstance
0x18004d5bc  mov     [rsp+0E0h+var_90], rax; HINSTANCE
0x18004d5c1  mov     [rsp+0E0h+var_98], 0BD0h; HMENU
0x18004d5ca  mov     [rsp+0E0h+var_A0], rsi; HWND
0x18004d5cf  mov     [rsp+0E0h+var_A8], 18h; int
0x18004d5d7  mov     [rsp+0E0h+uFlags], ecx; int
0x18004d5db  mov     [rsp+0E0h+bRepaint], r8d; int
0x18004d5e0  mov     [rsp+0E0h+nHeight], edx; int
0x18004d5e4  mov     r9d, 40810080h; dwStyle
0x18004d5ea  lea     r8, psz; unsigned __int16 *
0x18004d5f1  lea     rdx, aEdit; "EDIT"
0x18004d5f8  mov     ecx, r10d; dwExStyle
0x18004d5fb  call    ?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z; W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)
0x18004d600  mov     [rdi+40h], rax
0x18004d604  test    rax, rax
0x18004d607  jz      loc_18004DBCC
0x18004d60d  mov     edx, [rbp+57h+var_70]; int
0x18004d610  mov     rcx, rax; HWND
0x18004d613  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x18004d618  mov     cs:?s_lpfnlComboWndProc@CSearch@@0P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CSearch::s_lpfnlComboWndProc)(HWND__ *,uint,unsigned __int64,__int64)
0x18004d61f  mov     r8d, [rbp+57h+var_70]; int
0x18004d623  lea     rdx, ?ComboProc@CSearch@@CA_JPEAUHWND__@@I_K_J@Z; __int64
0x18004d62a  mov     rcx, [rdi+40h]; HWND
0x18004d62e  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18004d633  mov     r8, rdi; dwNewLong
0x18004d636  mov     edx, 0FFFFFFEBh; nIndex
0x18004d63b  mov     rcx, [rdi+40h]; hWnd
0x18004d63f  call    cs:__imp_SetWindowLongPtrA
0x18004d645  xor     r9d, r9d; lParam
0x18004d648  mov     edx, 0C5h; Msg
0x18004d64d  lea     r8d, [rdx+3Ah]; wParam
0x18004d651  mov     rcx, [rdi+40h]; hWnd
0x18004d655  call    cs:__imp_SendMessageA
0x18004d65b  mov     rcx, [rdi+10h]; this
0x18004d65f  call    ?GetContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetContentFont(void)
0x18004d664  xor     r9d, r9d; lParam
0x18004d667  mov     r8, rax; wParam
0x18004d66a  mov     edx, r12d; Msg
0x18004d66d  mov     rcx, [rdi+40h]; hWnd
0x18004d671  call    cs:__imp_SendMessageA
0x18004d677  mov     eax, [rbp+57h+rcDst.bottom]
0x18004d67a  add     eax, 8
0x18004d67d  mov     [rbp+57h+rcDst.top], eax
0x18004d680  add     eax, 18h
0x18004d683  mov     [rbp+57h+rcDst.bottom], eax
0x18004d686  mov     rbx, cs:hInstance
0x18004d68d  mov     ecx, 409h; uID
0x18004d692  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18004d697  mov     edx, [rbp+57h+rcDst.top]
0x18004d69a  mov     ecx, [rbp+57h+rcDst.right]
0x18004d69d  add     ecx, 0FFFFFFAEh
0x18004d6a0  lea     r8, [rbp+57h+var_70]
0x18004d6a4  mov     [rsp+0E0h+var_80], r8; int *
0x18004d6a9  mov     [rsp+0E0h+var_90], rbx; HINSTANCE
0x18004d6ae  mov     [rsp+0E0h+var_98], 0BC7h; HMENU
0x18004d6b7  mov     [rsp+0E0h+var_A0], rsi; HWND
0x18004d6bc  mov     [rsp+0E0h+var_A8], 18h; int
0x18004d6c4  mov     [rsp+0E0h+uFlags], 50h ; 'P'; int
0x18004d6cc  mov     [rsp+0E0h+bRepaint], edx; int
0x18004d6d0  mov     [rsp+0E0h+nHeight], ecx; int
0x18004d6d4  mov     r9d, 40010000h; dwStyle
0x18004d6da  mov     r8, rax; unsigned __int16 *
0x18004d6dd  lea     rdx, aButton; "BUTTON"
0x18004d6e4  xor     ecx, ecx; dwExStyle
0x18004d6e6  call    ?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z; W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)
0x18004d6eb  mov     [rdi+58h], rax
0x18004d6ef  test    rax, rax
0x18004d6f2  jz      loc_18004DBCC
0x18004d6f8  mov     edx, [rbp+57h+var_70]; int
0x18004d6fb  mov     rcx, rax; HWND
0x18004d6fe  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x18004d703  mov     cs:?g_lpfnlSearchListBtnWndProc@@3P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*g_lpfnlSearchListBtnWndProc)(HWND__ *,uint,unsigned __int64,__int64)
0x18004d70a  mov     r8d, [rbp+57h+var_70]; int
0x18004d70e  lea     rdx, ?ListBtnProc@CSearch@@CA_JPEAUHWND__@@I_K_J@Z; __int64
0x18004d715  mov     rcx, [rdi+58h]; HWND
0x18004d719  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18004d71e  mov     r8, rdi; dwNewLong
0x18004d721  mov     edx, 0FFFFFFEBh; nIndex
0x18004d726  mov     rcx, [rdi+58h]; hWnd
0x18004d72a  call    cs:__imp_SetWindowLongPtrA
0x18004d730  mov     ecx, [rbp+57h+rcDst.bottom]
0x18004d733  add     ecx, 8
0x18004d736  mov     [rbp+57h+rcDst.top], ecx
0x18004d739  lea     eax, [rcx+11h]
0x18004d73c  mov     [rbp+57h+rcDst.bottom], eax
0x18004d73f  mov     r11d, [rbp+57h+rcDst.left]
0x18004d743  mov     r10d, [rbp+57h+rcDst.right]
0x18004d747  sub     r10d, r11d
0x18004d74a  add     ecx, 0FFFFFFEFh
0x18004d74d  lea     rax, [rbp+57h+var_70]
0x18004d751  mov     [rsp+0E0h+var_80], rax; int *
0x18004d756  mov     rax, cs:hInstance
0x18004d75d  mov     [rsp+0E0h+var_90], rax; HINSTANCE
0x18004d762  mov     [rsp+0E0h+var_98], 0BC9h; HMENU
0x18004d76b  mov     [rsp+0E0h+var_A0], rsi; HWND
0x18004d770  mov     [rsp+0E0h+var_A8], 11h; int
0x18004d778  mov     [rsp+0E0h+uFlags], r10d; int
0x18004d77d  mov     [rsp+0E0h+bRepaint], ecx; int
0x18004d781  mov     [rsp+0E0h+nHeight], r11d; int
0x18004d786  mov     r9d, 40000000h; dwStyle
0x18004d78c  lea     r8, psz; unsigned __int16 *
0x18004d793  lea     rdx, aStatic; "STATIC"
0x18004d79a  mov     ecx, 20h ; ' '; dwExStyle
0x18004d79f  call    ?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z; W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)
0x18004d7a4  mov     [rdi+68h], rax
0x18004d7a8  test    rax, rax
0x18004d7ab  jz      loc_18004DBCC
0x18004d7b1  lea     rdx, [rbp+57h+Rect]; lpRect
0x18004d7b5  mov     rcx, rax; hWnd
0x18004d7b8  call    cs:__imp_GetWindowRect
0x18004d7be  mov     ecx, 426h; uID
0x18004d7c3  cmp     [rbp+57h+var_70], 0
0x18004d7c7  jz      short loc_18004D83B
0x18004d7c9  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18004d7ce  mov     rbx, rax
0x18004d7d1  mov     r9d, [rbp+57h+Rect.right]
0x18004d7d5  sub     r9d, [rbp+57h+Rect.left]; int
0x18004d7d9  mov     r8, rax; lpString
0x18004d7dc  mov     rdx, r14; h
0x18004d7df  mov     rcx, [rdi+68h]; hWnd
0x18004d7e3  call    ?GetStaticDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBGH@Z; GetStaticDimensionsW(HWND__ *,HFONT__ *,ushort const *,int)
0x18004d7e8  shr     eax, 10h
0x18004d7eb  mov     r8d, [rbp+57h+Rect.top]; Y
0x18004d7ef  lea     ecx, [rax+r8]
0x18004d7f3  mov     [rbp+57h+Rect.bottom], ecx
0x18004d7f6  mov     edx, [rbp+57h+Rect.left]; X
0x18004d7f9  mov     r9d, [rbp+57h+Rect.right]
0x18004d7fd  sub     ecx, r8d
0x18004d800  sub     r9d, edx; nWidth
0x18004d803  mov     [rsp+0E0h+bRepaint], 0; bRepaint
0x18004d80b  mov     [rsp+0E0h+nHeight], ecx; nHeight
0x18004d80f  mov     rcx, [rdi+68h]; hWnd
0x18004d813  call    cs:__imp_MoveWindow
0x18004d819  xor     r9d, r9d; lParam
0x18004d81c  mov     r8, r14; wParam
0x18004d81f  mov     edx, r12d; Msg
0x18004d822  mov     rcx, [rdi+68h]; hWnd
0x18004d826  call    cs:__imp_SendMessageA
0x18004d82c  mov     rdx, rbx; lpString
0x18004d82f  mov     rcx, [rdi+68h]; hWnd
0x18004d833  call    cs:__imp_SetWindowTextW
0x18004d839  jmp     short loc_18004D8AB
0x18004d83b  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18004d840  mov     rbx, rax
0x18004d843  mov     r9d, [rbp+57h+Rect.right]
0x18004d847  sub     r9d, [rbp+57h+Rect.left]; int
0x18004d84b  mov     r8, rax; char *
0x18004d84e  mov     rdx, r14; h
0x18004d851  mov     rcx, [rdi+68h]; hWnd
0x18004d855  call    ?GetStaticDimensions@@YAKPEAUHWND__@@PEAUHFONT__@@PEBDH@Z; GetStaticDimensions(HWND__ *,HFONT__ *,char const *,int)
0x18004d85a  shr     eax, 10h
0x18004d85d  mov     r8d, [rbp+57h+Rect.top]; Y
0x18004d861  lea     ecx, [rax+r8]
0x18004d865  mov     [rbp+57h+Rect.bottom], ecx
0x18004d868  mov     edx, [rbp+57h+Rect.left]; X
0x18004d86b  mov     r9d, [rbp+57h+Rect.right]
0x18004d86f  sub     ecx, r8d
0x18004d872  sub     r9d, edx; nWidth
0x18004d875  mov     [rsp+0E0h+bRepaint], 0; bRepaint
0x18004d87d  mov     [rsp+0E0h+nHeight], ecx; nHeight
0x18004d881  mov     rcx, [rdi+68h]; hWnd
0x18004d885  call    cs:__imp_MoveWindow
0x18004d88b  xor     r9d, r9d; lParam
0x18004d88e  mov     r8, r14; wParam
0x18004d891  mov     edx, r12d; Msg
0x18004d894  mov     rcx, [rdi+68h]; hWnd
0x18004d898  call    cs:__imp_SendMessageA
0x18004d89e  mov     rdx, rbx; lpString
0x18004d8a1  mov     rcx, [rdi+68h]; hWnd
0x18004d8a5  call    cs:__imp_SetWindowTextA
0x18004d8ab  mov     r9d, [rbp+57h+rcDst.bottom]
0x18004d8af  add     r9d, 0Ah
0x18004d8b3  mov     [rbp+57h+rcDst.top], r9d
0x18004d8b7  mov     edx, [rbp+57h+rcSrc.bottom]
0x18004d8ba  add     edx, 0FFFFFFE0h
  ... truncated ...
```
