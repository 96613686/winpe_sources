# CIndex::Create(HWND__ *)

- ea: `0x18003b090`
- end: `0x18003b691`
- name: `?Create@CIndex@@UEAAHPEAUHWND__@@@Z`
- size: `1537`
- prototype: `__int64 __fastcall(CIndex *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update`

## callees

- `0x180001728`
- `0x1800053b4`
- `0x18001054c`
- `0x180010b14`
- `0x180010fcc`
- `0x1800128a8`
- `0x18003b090`
- `0x18003b7cc`
- `0x18003ba08`
- `0x180051cfc`
- `0x180051e00`
- `0x1800661d0`
- `0x180066c20`
- `0x180066f80`
- `0x1800674e0`
- `0x180067798`
- `0x18006c400`
- `0x18006c52c`
- `0x18006c9d0`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `msvcrt!realloc` at `0x18003b4c6`
- `msvcrt!realloc` at `0x18003b4c6`
- `msvcrt!malloc` at `0x18003b4b3`
- `msvcrt!malloc` at `0x18003b4b3`
- `msvcrt!free` at `0x18003b4dc`
- `msvcrt!free` at `0x18003b4dc`
- `USER32!MoveWindow` at `0x18003b1f7`
- `USER32!MoveWindow` at `0x18003b600`
- `USER32!MoveWindow` at `0x18003b1f7`
- `USER32!MoveWindow` at `0x18003b600`
- `USER32!CopyRect` at `0x18003b10c`
- `USER32!CopyRect` at `0x18003b20c`
- `USER32!CopyRect` at `0x18003b300`
- `USER32!CopyRect` at `0x18003b10c`
- `USER32!CopyRect` at `0x18003b20c`
- `USER32!CopyRect` at `0x18003b300`
- `USER32!SetWindowLongPtrA` at `0x18003b3e5`
- `USER32!SetWindowLongPtrA` at `0x18003b3e5`
- `USER32!GetSystemMetrics` at `0x18003b0f5`
- `USER32!GetSystemMetrics` at `0x18003b0f5`
- `USER32!DestroyWindow` at `0x18003b29f`
- `USER32!DestroyWindow` at `0x18003b395`
- `USER32!DestroyWindow` at `0x18003b46d`
- `USER32!DestroyWindow` at `0x18003b29f`
- `USER32!DestroyWindow` at `0x18003b395`
- `USER32!DestroyWindow` at `0x18003b46d`
- `USER32!SendMessageA` at `0x18003b2eb`
- `USER32!SendMessageA` at `0x18003b55f`
- `USER32!SendMessageA` at `0x18003b57a`
- `USER32!SendMessageA` at `0x18003b595`
- `USER32!SendMessageA` at `0x18003b5b0`
- `USER32!SendMessageA` at `0x18003b2eb`
- `USER32!SendMessageA` at `0x18003b55f`
- `USER32!SendMessageA` at `0x18003b57a`
- `USER32!SendMessageA` at `0x18003b595`
- `USER32!SendMessageA` at `0x18003b5b0`

## pseudocode

```c
__int64 __fastcall CIndex::Create(CIndex *this, HWND a2)
{
  int v2; // r9d
  int v4; // r8d
  HINSTANCE v5; // rdi
  LONG left; // ebx
  LONG right; // esi
  const unsigned __int16 *StringResourceW; // rax
  int *v9; // r13
  HWND Window; // rax
  LONG v12; // edi
  LONG v13; // esi
  const WCHAR *v14; // rbx
  CResourceCache *v15; // rcx
  HFONT UIFont; // rax
  unsigned int v17; // eax
  HWND v18; // rax
  LRESULT (__stdcall *WndProc)(HWND, UINT, WPARAM, LPARAM); // rax
  int v20; // r8d
  HWND v21; // rcx
  LONG bottom; // r15d
  HINSTANCE v23; // rsi
  LONG v24; // ebx
  LONG v25; // r14d
  int v26; // edi
  const unsigned __int16 *v27; // rax
  HWND v28; // rax
  LRESULT (__stdcall *v29)(HWND, UINT, WPARAM, LPARAM); // rax
  int v30; // r8d
  HWND v31; // rcx
  CVirtualListCtrl *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  unsigned int v35; // edx
  CVirtualListCtrl *v36; // rax
  HWND v37; // rax
  void *v38; // rbx
  CHHWinType *v39; // rcx
  int ContentCharset; // eax
  __int64 v41; // rcx
  HFONT AccessableContentFont; // rax
  CResourceCache *v43; // rcx
  HFONT AccessableUIFont; // rax
  CResourceCache *v45; // rcx
  HFONT v46; // rax
  CResourceCache *v47; // rcx
  HFONT v48; // rax
  const WCHAR *v49; // rbx
  CResourceCache *v50; // rcx
  HFONT v51; // rax
  unsigned int ButtonDimensionsW; // eax
  int v53; // edx
  void *v54; // [rsp+58h] [rbp-41h]
  void *v55; // [rsp+58h] [rbp-41h]
  void *v56; // [rsp+58h] [rbp-41h]
  HWND ParentSize; // [rsp+70h] [rbp-29h]
  struct tagRECT rcDst; // [rsp+78h] [rbp-21h] BYREF
  struct tagRECT v59; // [rsp+88h] [rbp-11h] BYREF
  struct tagRECT v60; // [rsp+98h] [rbp-1h] BYREF
  RECT rcSrc; // [rsp+A8h] [rbp+Fh] BYREF

  v2 = *((_DWORD *)this + 120);
  v4 = *((_DWORD *)this + 117);
  *((_QWORD *)this + 62) = a2;
  rcSrc = 0;
  rcDst = 0;
  ParentSize = GetParentSize(&rcSrc, a2, v4, v2);
  rcSrc.top += 2 * GetSystemMetrics(33);
  CopyRect(&rcDst, &rcSrc);
  v5 = hInstance;
  left = rcDst.left;
  right = rcDst.right;
  StringResourceW = GetStringResourceW(0x425u);
  v9 = (int *)((char *)this + 712);
  Window = W_CreateWindowEx(
             0x20u,
             L"STATIC",
             StringResourceW,
             0x40000000u,
             rcDst.left,
             rcDst.top,
             right - left,
             34,
             ParentSize,
             (HMENU)0xBCA,
             v5,
             v54,
             (int *)this + 178);
  *((_QWORD *)this + 57) = Window;
  if ( !Window )
    return 0;
  v12 = rcDst.left;
  v13 = rcDst.right;
  v14 = GetStringResourceW(0x425u);
  UIFont = CResourceCache::GetUIFont(v15);
  v17 = GetStaticDimensionsW(*((HWND *)this + 57), UIFont, v14, v13 - v12) >> 16;
  rcDst.bottom = v17 + rcDst.top;
  MoveWindow(*((HWND *)this + 57), rcDst.left, rcDst.top, rcDst.right - rcDst.left, v17 + 20, 0);
  v60 = 0;
  CopyRect(&v60, &rcDst);
  v60.top = rcDst.bottom + 10;
  v60.bottom = rcDst.bottom + 34;
  v18 = W_CreateWindowEx(
          g_RTL_Style | 0x200,
          L"EDIT",
          &psz,
          0x40810080u,
          v60.left,
          rcDst.bottom + 20,
          v60.right - v60.left,
          39,
          ParentSize,
          (HMENU)0xBBB,
          hInstance,
          v55,
          (int *)this + 178);
  *((_QWORD *)this + 54) = v18;
  if ( !v18 )
  {
LABEL_4:
    DestroyWindow(*((HWND *)this + 57));
    return 0;
  }
  WndProc = W_GetWndProc(v18, *v9);
  v20 = *v9;
  v21 = (HWND)*((_QWORD *)this + 54);
  g_lpfnlEditWndProc = WndProc;
  W_SubClassWindow(v21, (__int64)EditProc, v20);
  SendMessageA(*((HWND *)this + 54), 0xC5u, 0x1F0u, 0);
  v59 = 0;
  CopyRect(&v59, &rcDst);
  bottom = rcSrc.bottom;
  v23 = hInstance;
  v24 = v59.left;
  v25 = v59.right;
  v26 = rcSrc.bottom - 29;
  v59.bottom = rcSrc.bottom;
  v59.top = rcSrc.bottom - 29;
  v27 = GetStringResourceW(0x1020u);
  v28 = W_CreateWindowEx(
          0,
          L"button",
          v27,
          0x40010000u,
          v59.left,
          v59.top,
          v25 - v24,
          bottom - v26,
          ParentSize,
          (HMENU)0xBBE,
          v23,
          v56,
          (int *)this + 178);
  *((_QWORD *)this + 56) = v28;
  if ( !v28 )
  {
LABEL_6:
    DestroyWindow(*((HWND *)this + 54));
    goto LABEL_4;
  }
  if ( *((_QWORD *)this + 49) )
  {
    v29 = W_GetWndProc(v28, *v9);
    v30 = *v9;
    v31 = (HWND)*((_QWORD *)this + 56);
    g_lpfnlBtnWndProc = v29;
    W_SubClassWindow(v31, (__int64)ButtonProc, v30);
    SetWindowLongPtrA(*((HWND *)this + 56), -21, (LONG_PTR)this);
  }
  rcDst.top = v60.bottom + 8;
  rcDst.bottom = v59.top - 8;
  v32 = (CVirtualListCtrl *)operator new(0x70u);
  if ( v32 )
  {
    v33 = *((_QWORD *)this + 49);
    if ( v33 && (v34 = *(_QWORD *)(v33 + 608)) != 0 )
      v35 = *(_DWORD *)(v34 + 88);
    else
      v35 = g_lcidSystem;
    v36 = CVirtualListCtrl::CVirtualListCtrl(v32, v35);
  }
  else
  {
    v36 = 0;
  }
  *((_QWORD *)this + 64) = v36;
  v37 = CVirtualListCtrl::CreateVlistbox(v36, ParentSize, &rcDst);
  *((_QWORD *)this + 55) = v37;
  if ( !v37 )
  {
    DestroyWindow(*((HWND *)this + 56));
    goto LABEL_6;
  }
  if ( *((_QWORD *)this + 34) && !*((_DWORD *)this + 92) )
  {
    if ( ++*((_DWORD *)this + 88) == 1 )
    {
      v38 = malloc(8LL * *((int *)this + 88));
    }
    else
    {
      v38 = realloc(*((void **)this + 45), 8LL * *((int *)this + 88));
      if ( !v38 )
        free(*((void **)this + 45));
    }
    *((_QWORD *)this + 45) = v38;
    v39 = (CHHWinType *)*((_QWORD *)this + 49);
    if ( v39 )
    {
      ContentCharset = CHHWinType::GetContentCharset(v39);
    }
    else
    {
      v41 = *((_QWORD *)this + 47);
      ContentCharset = -1;
      if ( v41 )
        ContentCharset = *(_DWORD *)(v41 + 1208);
    }
    *(_QWORD *)(*((_QWORD *)this + 45) + 8LL * *((int *)this + 88) - 8) = CreateUserFont(
                                                                            *((const char **)this + 34),
                                                                            0,
                                                                            0,
                                                                            ContentCharset);
  }
  AccessableContentFont = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 49));
  SendMessageA(*((HWND *)this + 55), 0x30u, (WPARAM)AccessableContentFont, 0);
  AccessableUIFont = CResourceCache::GetAccessableUIFont(v43);
  SendMessageA(*((HWND *)this + 54), 0x30u, (WPARAM)AccessableUIFont, 0);
  v46 = CResourceCache::GetAccessableUIFont(v45);
  SendMessageA(*((HWND *)this + 56), 0x30u, (WPARAM)v46, 0);
  v48 = CResourceCache::GetAccessableUIFont(v47);
  SendMessageA(*((HWND *)this + 57), 0x30u, (WPARAM)v48, 0);
  v49 = GetStringResourceW(0x1020u);
  v51 = CResourceCache::GetAccessableUIFont(v50);
  ButtonDimensionsW = GetButtonDimensionsW(*((HWND *)this + 56), v51, v49);
  MoveWindow(
    *((HWND *)this + 56),
    v59.right - (unsigned __int16)ButtonDimensionsW,
    v59.top - 5,
    (unsigned __int16)ButtonDimensionsW,
    HIWORD(ButtonDimensionsW),
    0);
  *((_QWORD *)this + 59) = *((_QWORD *)this + 55);
  CIndex::FillListBox(this, v53);
  if ( !*((_DWORD *)this + 92) )
    CVirtualListCtrl::PaintParamsSetup(
      *((CVirtualListCtrl **)this + 64),
      *((_DWORD *)this + 65),
      *((_DWORD *)this + 66),
      *((const char **)this + 37));
  CIndex::InitDlgItemArray(this);
  (*(void (__fastcall **)(CIndex *))(*(_QWORD *)this + 40LL))(this);
  return 1;
}

```

## disassembly

```asm
0x18003b090  mov     [rsp-8+arg_10], rbx
0x18003b095  push    rbp
0x18003b096  push    rsi
0x18003b097  push    rdi
0x18003b098  push    r12
0x18003b09a  push    r13
0x18003b09c  push    r14
0x18003b09e  push    r15
0x18003b0a0  lea     rbp, [rsp-27h]
0x18003b0a5  sub     rsp, 0C0h
0x18003b0ac  mov     rax, cs:__security_cookie
0x18003b0b3  xor     rax, rsp
0x18003b0b6  mov     [rbp+57h+var_38], rax
0x18003b0ba  mov     r9d, [rcx+1E0h]; int
0x18003b0c1  mov     r12, rcx
0x18003b0c4  mov     r8d, [rcx+1D4h]; int
0x18003b0cb  xorps   xmm0, xmm0
0x18003b0ce  xorps   xmm1, xmm1
0x18003b0d1  mov     [rcx+1F0h], rdx
0x18003b0d8  lea     rcx, [rbp+57h+rcSrc]; lprc
0x18003b0dc  movups  xmmword ptr [rbp+57h+rcSrc.left], xmm0
0x18003b0e0  movups  xmmword ptr [rbp+57h+rcDst.left], xmm1
0x18003b0e4  call    ?GetParentSize@@YAPEAUHWND__@@PEAUtagRECT@@PEAU1@HH@Z; GetParentSize(tagRECT *,HWND__ *,int,int)
0x18003b0e9  mov     ecx, 21h ; '!'; nIndex
0x18003b0ee  mov     [rbp+57h+var_80], rax
0x18003b0f2  mov     r14, rax
0x18003b0f5  call    cs:__imp_GetSystemMetrics
0x18003b0fb  mov     ecx, [rbp+57h+rcSrc.top]
0x18003b0fe  lea     edx, [rcx+rax*2]
0x18003b101  mov     [rbp+57h+rcSrc.top], edx
0x18003b104  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18003b108  lea     rdx, [rbp+57h+rcSrc]; lprcSrc
0x18003b10c  call    cs:__imp_CopyRect
0x18003b112  mov     rdi, cs:hInstance
0x18003b119  mov     r15d, 425h
0x18003b11f  mov     ebx, [rbp+57h+rcDst.left]
0x18003b122  mov     ecx, r15d; uID
0x18003b125  mov     esi, [rbp+57h+rcDst.right]
0x18003b128  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18003b12d  mov     ecx, [rbp+57h+rcDst.top]
0x18003b130  lea     r13, [r12+2C8h]
0x18003b138  mov     [rsp+0F0h+var_90], r13; int *
0x18003b13d  lea     rdx, aStatic; "STATIC"
0x18003b144  mov     [rsp+0F0h+var_A0], rdi; HINSTANCE
0x18003b149  sub     esi, ebx
0x18003b14b  mov     [rsp+0F0h+var_A8], 0BCAh; HMENU
0x18003b154  mov     r9d, 40000000h; dwStyle
0x18003b15a  mov     [rsp+0F0h+var_B0], r14; HWND
0x18003b15f  mov     r8, rax; unsigned __int16 *
0x18003b162  mov     [rsp+0F0h+var_B8], 22h ; '"'; int
0x18003b16a  mov     [rsp+0F0h+var_C0], esi; int
0x18003b16e  mov     [rsp+0F0h+bRepaint], ecx; int
0x18003b172  mov     ecx, [rbp+57h+rcDst.left]
0x18003b175  mov     [rsp+0F0h+nHeight], ecx; int
0x18003b179  mov     ecx, 20h ; ' '; dwExStyle
0x18003b17e  call    ?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z; W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)
0x18003b183  mov     [r12+1C8h], rax
0x18003b18b  test    rax, rax
0x18003b18e  jnz     short loc_18003B197
0x18003b190  xor     eax, eax
0x18003b192  jmp     loc_18003B66A
0x18003b197  mov     edi, [rbp+57h+rcDst.left]
0x18003b19a  mov     ecx, r15d; uID
0x18003b19d  mov     esi, [rbp+57h+rcDst.right]
0x18003b1a0  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18003b1a5  mov     rbx, rax
0x18003b1a8  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x18003b1ad  mov     rcx, [r12+1C8h]; hWnd
0x18003b1b5  sub     esi, edi
0x18003b1b7  mov     r9d, esi; int
0x18003b1ba  mov     r8, rbx; lpString
0x18003b1bd  mov     rdx, rax; h
0x18003b1c0  call    ?GetStaticDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBGH@Z; GetStaticDimensionsW(HWND__ *,HFONT__ *,ushort const *,int)
0x18003b1c5  mov     r8d, [rbp+57h+rcDst.top]; Y
0x18003b1c9  mov     r9d, [rbp+57h+rcDst.right]
0x18003b1cd  mov     edx, [rbp+57h+rcDst.left]; X
0x18003b1d0  sub     r9d, edx; nWidth
0x18003b1d3  shr     eax, 10h
0x18003b1d6  mov     [rsp+0F0h+bRepaint], 0; bRepaint
0x18003b1de  lea     ecx, [rax+r8]
0x18003b1e2  mov     [rbp+57h+rcDst.bottom], ecx
0x18003b1e5  sub     ecx, r8d
0x18003b1e8  add     ecx, 14h
0x18003b1eb  mov     [rsp+0F0h+nHeight], ecx; nHeight
0x18003b1ef  mov     rcx, [r12+1C8h]; hWnd
0x18003b1f7  call    cs:__imp_MoveWindow
0x18003b1fd  xorps   xmm0, xmm0
0x18003b200  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x18003b204  lea     rcx, [rbp+57h+var_58]; lprcDst
0x18003b208  movups  xmmword ptr [rbp+57h+var_58.left], xmm0
0x18003b20c  call    cs:__imp_CopyRect
0x18003b212  mov     r8d, [rbp+57h+var_58.left]
0x18003b216  mov     r9d, 40810080h; dwStyle
0x18003b21c  mov     edx, [rbp+57h+var_58.right]
0x18003b21f  mov     ecx, [rbp+57h+rcDst.bottom]
0x18003b222  sub     edx, r8d
0x18003b225  mov     r10d, cs:?g_RTL_Style@@3KA; ulong g_RTL_Style
0x18003b22c  add     ecx, 0Ah
0x18003b22f  mov     [rsp+0F0h+var_90], r13; int *
0x18003b234  bts     r10d, 9
0x18003b239  mov     [rbp+57h+var_58.top], ecx
0x18003b23c  lea     eax, [rcx+18h]
0x18003b23f  add     ecx, 0Ah
0x18003b242  mov     [rbp+57h+var_58.bottom], eax
0x18003b245  mov     rax, cs:hInstance
0x18003b24c  mov     [rsp+0F0h+var_A0], rax; HINSTANCE
0x18003b251  mov     [rsp+0F0h+var_A8], 0BBBh; HMENU
0x18003b25a  mov     [rsp+0F0h+var_B0], r14; HWND
0x18003b25f  mov     [rsp+0F0h+var_B8], 27h ; '''; int
0x18003b267  mov     [rsp+0F0h+var_C0], edx; int
0x18003b26b  lea     rdx, aEdit; "EDIT"
0x18003b272  mov     [rsp+0F0h+bRepaint], ecx; int
0x18003b276  mov     ecx, r10d; dwExStyle
0x18003b279  mov     [rsp+0F0h+nHeight], r8d; int
0x18003b27e  lea     r8, psz; unsigned __int16 *
0x18003b285  call    ?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z; W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)
0x18003b28a  mov     [r12+1B0h], rax
0x18003b292  test    rax, rax
0x18003b295  jnz     short loc_18003B2AA
0x18003b297  mov     rcx, [r12+1C8h]; hWnd
0x18003b29f  call    cs:__imp_DestroyWindow
0x18003b2a5  jmp     loc_18003B190
0x18003b2aa  mov     edx, [r13+0]; int
0x18003b2ae  mov     rcx, rax; HWND
0x18003b2b1  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x18003b2b6  mov     r8d, [r13+0]; int
0x18003b2ba  lea     rdx, ?EditProc@@YA_JPEAUHWND__@@I_K_J@Z; __int64
0x18003b2c1  mov     rcx, [r12+1B0h]; HWND
0x18003b2c9  mov     cs:?g_lpfnlEditWndProc@@3P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*g_lpfnlEditWndProc)(HWND__ *,uint,unsigned __int64,__int64)
0x18003b2d0  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18003b2d5  mov     rcx, [r12+1B0h]; hWnd
0x18003b2dd  xor     r9d, r9d; lParam
0x18003b2e0  mov     edx, 0C5h; Msg
0x18003b2e5  mov     r8d, 1F0h; wParam
0x18003b2eb  call    cs:__imp_SendMessageA
0x18003b2f1  xorps   xmm0, xmm0
0x18003b2f4  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x18003b2f8  lea     rcx, [rbp+57h+var_68]; lprcDst
0x18003b2fc  movups  xmmword ptr [rbp+57h+var_68.left], xmm0
0x18003b300  call    cs:__imp_CopyRect
0x18003b306  mov     r15d, [rbp+57h+rcSrc.bottom]
0x18003b30a  mov     ecx, 1020h; uID
0x18003b30f  mov     rsi, cs:hInstance
0x18003b316  mov     ebx, [rbp+57h+var_68.left]
0x18003b319  mov     r14d, [rbp+57h+var_68.right]
0x18003b31d  lea     edi, [r15-1Dh]
0x18003b321  mov     [rbp+57h+var_68.bottom], r15d
0x18003b325  mov     [rbp+57h+var_68.top], edi
0x18003b328  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18003b32d  mov     ecx, [rbp+57h+var_68.top]
0x18003b330  sub     r14d, ebx
0x18003b333  mov     edx, [rbp+57h+var_68.left]
0x18003b336  sub     r15d, edi
0x18003b339  mov     rbx, [rbp+57h+var_80]
0x18003b33d  mov     r9d, 40010000h; dwStyle
0x18003b343  mov     [rsp+0F0h+var_90], r13; int *
0x18003b348  mov     r8, rax; unsigned __int16 *
0x18003b34b  mov     [rsp+0F0h+var_A0], rsi; HINSTANCE
0x18003b350  mov     [rsp+0F0h+var_A8], 0BBEh; HMENU
0x18003b359  mov     [rsp+0F0h+var_B0], rbx; HWND
0x18003b35e  mov     [rsp+0F0h+var_B8], r15d; int
0x18003b363  mov     [rsp+0F0h+var_C0], r14d; int
0x18003b368  mov     [rsp+0F0h+bRepaint], ecx; int
0x18003b36c  xor     ecx, ecx; dwExStyle
0x18003b36e  mov     [rsp+0F0h+nHeight], edx; int
0x18003b372  lea     rdx, aButton_0; "button"
0x18003b379  call    ?W_CreateWindowEx@@YAPEAUHWND__@@KPEBG0KHHHHPEAU1@PEAUHMENU__@@PEAUHINSTANCE__@@PEAXPEAH@Z; W_CreateWindowEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *,int *)
0x18003b37e  xor     edi, edi
0x18003b380  mov     [r12+1C0h], rax
0x18003b388  test    rax, rax
0x18003b38b  jnz     short loc_18003B3A0
0x18003b38d  mov     rcx, [r12+1B0h]; hWnd
0x18003b395  call    cs:__imp_DestroyWindow
0x18003b39b  jmp     loc_18003B297
0x18003b3a0  cmp     [r12+188h], rdi
0x18003b3a8  jz      short loc_18003B3EB
0x18003b3aa  mov     edx, [r13+0]; int
0x18003b3ae  mov     rcx, rax; HWND
0x18003b3b1  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x18003b3b6  mov     r8d, [r13+0]; int
0x18003b3ba  lea     rdx, ButtonProc; __int64
0x18003b3c1  mov     rcx, [r12+1C0h]; HWND
0x18003b3c9  mov     cs:?g_lpfnlBtnWndProc@@3P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*g_lpfnlBtnWndProc)(HWND__ *,uint,unsigned __int64,__int64)
0x18003b3d0  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18003b3d5  mov     rcx, [r12+1C0h]; hWnd
0x18003b3dd  mov     r8, r12; dwNewLong
0x18003b3e0  mov     edx, 0FFFFFFEBh; nIndex
0x18003b3e5  call    cs:__imp_SetWindowLongPtrA
0x18003b3eb  mov     eax, [rbp+57h+var_58.bottom]
0x18003b3ee  mov     ecx, 70h ; 'p'; Size
0x18003b3f3  add     eax, 8
0x18003b3f6  mov     [rbp+57h+rcDst.top], eax
0x18003b3f9  mov     eax, [rbp+57h+var_68.top]
0x18003b3fc  add     eax, 0FFFFFFF8h
0x18003b3ff  mov     [rbp+57h+rcDst.bottom], eax
0x18003b402  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b407  mov     [rbp+57h+var_80], rax
0x18003b40b  test    rax, rax
0x18003b40e  jz      short loc_18003B43E
0x18003b410  mov     rcx, [r12+188h]
0x18003b418  test    rcx, rcx
0x18003b41b  jz      short loc_18003B42E
0x18003b41d  mov     rdx, [rcx+260h]
0x18003b424  test    rdx, rdx
0x18003b427  jz      short loc_18003B42E
0x18003b429  mov     edx, [rdx+58h]
0x18003b42c  jmp     short loc_18003B434
0x18003b42e  mov     edx, cs:?g_lcidSystem@@3KA; unsigned int
0x18003b434  mov     rcx, rax; this
0x18003b437  call    ??0CVirtualListCtrl@@QEAA@K@Z; CVirtualListCtrl::CVirtualListCtrl(ulong)
0x18003b43c  jmp     short loc_18003B441
0x18003b43e  mov     rax, rdi
0x18003b441  lea     r8, [rbp+57h+rcDst]; struct tagRECT *
0x18003b445  mov     [r12+200h], rax
0x18003b44d  mov     rdx, rbx; HWND
0x18003b450  mov     rcx, rax; this
0x18003b453  call    ?CreateVlistbox@CVirtualListCtrl@@QEAAPEAUHWND__@@PEAU2@PEAUtagRECT@@@Z; CVirtualListCtrl::CreateVlistbox(HWND__ *,tagRECT *)
0x18003b458  mov     [r12+1B8h], rax
0x18003b460  test    rax, rax
0x18003b463  jnz     short loc_18003B478
0x18003b465  mov     rcx, [r12+1C0h]; hWnd
0x18003b46d  call    cs:__imp_DestroyWindow
0x18003b473  jmp     loc_18003B38D
0x18003b478  cmp     [r12+110h], rdi
0x18003b480  jz      loc_18003B53E
0x18003b486  cmp     [r12+170h], edi
0x18003b48e  jnz     loc_18003B53E
0x18003b494  inc     dword ptr [r12+160h]
0x18003b49c  movsxd  rax, dword ptr [r12+160h]
0x18003b4a4  mov     rdx, rax
0x18003b4a7  shl     rdx, 3; Size
0x18003b4ab  cmp     eax, 1
0x18003b4ae  jnz     short loc_18003B4BE
0x18003b4b0  mov     rcx, rdx; Size
0x18003b4b3  call    cs:__imp_malloc
0x18003b4b9  mov     rbx, rax
0x18003b4bc  jmp     short loc_18003B4E2
0x18003b4be  mov     rcx, [r12+168h]; Block
0x18003b4c6  call    cs:__imp_realloc
0x18003b4cc  mov     rbx, rax
0x18003b4cf  test    rax, rax
0x18003b4d2  jnz     short loc_18003B4E2
0x18003b4d4  mov     rcx, [r12+168h]; Block
0x18003b4dc  call    cs:__imp_free
0x18003b4e2  mov     [r12+168h], rbx
0x18003b4ea  mov     rcx, [r12+188h]; this
0x18003b4f2  test    rcx, rcx
0x18003b4f5  jz      short loc_18003B4FE
0x18003b4f7  call    ?GetContentCharset@CHHWinType@@QEAAHXZ; CHHWinType::GetContentCharset(void)
0x18003b4fc  jmp     short loc_18003B514
0x18003b4fe  mov     rcx, [r12+178h]
0x18003b506  or      eax, 0FFFFFFFFh
0x18003b509  test    rcx, rcx
0x18003b50c  jz      short loc_18003B514
0x18003b50e  mov     eax, [rcx+4B8h]
0x18003b514  mov     rcx, [r12+110h]; char *
0x18003b51c  mov     r9d, eax; int
0x18003b51f  xor     r8d, r8d; HDC
0x18003b522  xor     edx, edx; unsigned int *
0x18003b524  call    ?CreateUserFont@@YAPEAUHFONT__@@PEBDPEAKPEAUHDC__@@H@Z; CreateUserFont(char const *,ulong *,HDC__ *,int)
0x18003b529  movsxd  rdx, dword ptr [r12+160h]
0x18003b531  mov     rcx, [r12+168h]
0x18003b539  mov     [rcx+rdx*8-8], rax
0x18003b53e  mov     rcx, [r12+188h]; this
0x18003b546  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18003b54b  mov     rcx, [r12+1B8h]; hWnd
0x18003b553  xor     r9d, r9d; lParam
0x18003b556  mov     r8, rax; wParam
0x18003b559  lea     ebx, [r9+30h]
0x18003b55d  mov     edx, ebx; Msg
0x18003b55f  call    cs:__imp_SendMessageA
0x18003b565  call    ?GetAccessableUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetAccessableUIFont(void)
0x18003b56a  mov     rcx, [r12+1B0h]; hWnd
0x18003b572  xor     r9d, r9d; lParam
0x18003b575  mov     r8, rax; wParam
0x18003b578  mov     edx, ebx; Msg
0x18003b57a  call    cs:__imp_SendMessageA
0x18003b580  call    ?GetAccessableUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetAccessableUIFont(void)
0x18003b585  mov     rcx, [r12+1C0h]; hWnd
0x18003b58d  xor     r9d, r9d; lParam
0x18003b590  mov     r8, rax; wParam
0x18003b593  mov     edx, ebx; Msg
0x18003b595  call    cs:__imp_SendMessageA
0x18003b59b  call    ?GetAccessableUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetAccessableUIFont(void)
0x18003b5a0  mov     rcx, [r12+1C8h]; hWnd
0x18003b5a8  xor     r9d, r9d; lParam
0x18003b5ab  mov     r8, rax; wParam
0x18003b5ae  mov     edx, ebx; Msg
0x18003b5b0  call    cs:__imp_SendMessageA
0x18003b5b6  mov     ecx, 1020h; uID
0x18003b5bb  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18003b5c0  mov     rbx, rax
0x18003b5c3  call    ?GetAccessableUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetAccessableUIFont(void)
0x18003b5c8  mov     rcx, [r12+1C0h]; hWnd
0x18003b5d0  mov     r8, rbx; lpString
0x18003b5d3  mov     rdx, rax; h
0x18003b5d6  call    ?GetButtonDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBG@Z; GetButtonDimensionsW(HWND__ *,HFONT__ *,ushort const *)
0x18003b5db  mov     r8d, [rbp+57h+var_68.top]
0x18003b5df  mov     edx, [rbp+57h+var_68.right]
0x18003b5e2  add     r8d, 0FFFFFFFBh; Y
  ... truncated ...
```
