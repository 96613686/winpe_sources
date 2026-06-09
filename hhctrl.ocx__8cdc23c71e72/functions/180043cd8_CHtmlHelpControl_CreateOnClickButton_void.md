# CHtmlHelpControl::CreateOnClickButton(void)

- ea: `0x180043cd8`
- end: `0x1800441d2`
- name: `?CreateOnClickButton@CHtmlHelpControl@@QEAAHXZ`
- size: `1274`
- prototype: `__int64 __fastcall(CHtmlHelpControl *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002efa0`

## callees

- `0x180005a4c`
- `0x18000c02c`
- `0x180011490`
- `0x1800128a8`
- `0x18002fb58`
- `0x18003a9e0`
- `0x180043cd8`
- `0x180044dd0`
- `0x180064c98`
- `0x180069430`
- `0x180075c90`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004406f`
- `KERNEL32!lstrlenW` at `0x18004406f`
- `USER32!MoveWindow` at `0x180043ed0`
- `USER32!MoveWindow` at `0x180043fd2`
- `USER32!MoveWindow` at `0x1800440dd`
- `USER32!MoveWindow` at `0x180043ed0`
- `USER32!MoveWindow` at `0x180043fd2`
- `USER32!MoveWindow` at `0x1800440dd`
- `USER32!SetClassLongPtrA` at `0x180044129`
- `USER32!SetClassLongPtrA` at `0x180044129`
- `USER32!LoadImageA` at `0x180043f1d`
- `USER32!LoadImageA` at `0x180043f1d`
- `USER32!ReleaseDC` at `0x1800440aa`
- `USER32!ReleaseDC` at `0x1800440aa`
- `USER32!GetDC` at `0x180044031`
- `USER32!GetDC` at `0x180044031`
- `USER32!SetWindowLongPtrA` at `0x180043de6`
- `USER32!SetWindowLongPtrA` at `0x180043dfc`
- `USER32!SetWindowLongPtrA` at `0x180043de6`
- `USER32!SetWindowLongPtrA` at `0x180043dfc`
- `USER32!LoadBitmapA` at `0x180043e90`
- `USER32!LoadBitmapA` at `0x180043f37`
- `USER32!LoadBitmapA` at `0x180043e90`
- `USER32!LoadBitmapA` at `0x180043f37`
- `USER32!GetWindowRect` at `0x1800440f1`
- `USER32!GetWindowRect` at `0x1800440f1`
- `USER32!EnableWindow` at `0x180044187`
- `USER32!EnableWindow` at `0x180044187`
- `USER32!SendMessageA` at `0x18004400b`
- `USER32!SendMessageA` at `0x18004400b`
- `USER32!GetWindowLongPtrA` at `0x180043dcc`
- `USER32!GetWindowLongPtrA` at `0x180043dcc`
- `USER32!LoadCursorA` at `0x180044114`
- `USER32!LoadCursorA` at `0x180044114`
- `GDI32!GetObjectA` at `0x180043fa8`
- `GDI32!GetObjectA` at `0x180043fa8`
- `GDI32!SelectObject` at `0x18004405a`
- `GDI32!SelectObject` at `0x18004409a`
- `GDI32!SelectObject` at `0x18004405a`
- `GDI32!SelectObject` at `0x18004409a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CHtmlHelpControl::CreateOnClickButton(CHtmlHelpControl *this)
{
  const CHAR *v2; // rbx
  HWND Window; // rax
  LONG_PTR WindowLongPtrA; // rax
  HWND v5; // rcx
  CResourceCache *v6; // rcx
  const CHAR *v7; // rbx
  _DWORD *v8; // r14
  HINSTANCE v9; // rax
  void *BitmapA; // rax
  int v11; // ecx
  bool v12; // zf
  HWND v13; // rcx
  LPARAM v14; // r9
  UINT v15; // edx
  WPARAM v16; // r8
  UINT v17; // ebx
  HINSTANCE v18; // rax
  HINSTANCE ResourceInstance; // rax
  HFONT UIFont; // rax
  _WORD *v21; // rax
  CResourceCache *v22; // rcx
  HDC DC; // rbx
  HFONT v24; // rax
  HGDIOBJ v25; // rax
  const WCHAR *v26; // rcx
  void *v27; // r14
  int v28; // eax
  LONG cy; // eax
  LONG cx; // r9d
  HINSTANCE v31; // rax
  HCURSOR CursorA; // rax
  int v33; // ecx
  unsigned int *nHeight; // [rsp+20h] [rbp-E0h]
  struct tagSIZE psizl; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD pv[2]; // [rsp+68h] [rbp-98h] BYREF
  CHAR WindowName[272]; // [rsp+90h] [rbp-70h] BYREF
  CHAR name[272]; // [rsp+1A0h] [rbp+A0h] BYREF

  if ( *((_DWORD *)this + 91) == 4 )
  {
    v2 = "button";
    HHWideCharToMultiByte(
      *((_DWORD *)this + 301),
      0,
      *((const unsigned __int16 **)this + 72),
      -1,
      WindowName,
      260,
      0,
      0);
  }
  else
  {
    v2 = "static";
    WindowName[0] = 0;
  }
  Window = (HWND)IsolationAwareCreateWindowExA(
                   0,
                   v2,
                   WindowName,
                   *((_DWORD *)this + 101) | 0x50004000u,
                   0,
                   0,
                   12,
                   12,
                   *((HWND *)this + 28),
                   (HMENU)0xBBE,
                   hInstance,
                   0);
  *((_QWORD *)this + 57) = Window;
  if ( !Window )
    return 0;
  WindowLongPtrA = GetWindowLongPtrA(Window, -4);
  v5 = (HWND)*((_QWORD *)this + 57);
  *((_QWORD *)this + 85) = WindowLongPtrA;
  SetWindowLongPtrA(v5, -21, (LONG_PTR)this);
  SetWindowLongPtrA(*((HWND *)this + 57), -4, (LONG_PTR)CHtmlHelpControl::StaticTextControlSubWndProc);
  v7 = (const CHAR *)*((_QWORD *)this + 48);
  if ( !v7 )
  {
    UIFont = (HFONT)*((_QWORD *)this + 152);
    if ( !UIFont )
      UIFont = CResourceCache::GetUIFont(v6);
    v14 = 0;
    v16 = (WPARAM)UIFont;
    v15 = 48;
    goto LABEL_23;
  }
  if ( (unsigned int)IsSamePrefix(*((const char **)this + 48), "shortcut", -2) )
  {
    ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    BitmapA = LoadBitmapA(ResourceInstance, v7);
    v8 = (_DWORD *)((char *)this + 616);
LABEL_15:
    *((_QWORD *)this + 54) = BitmapA;
    if ( !BitmapA )
    {
      AuthorMsg(0x1D805u, *((char **)this + 48));
      goto LABEL_25;
    }
    goto LABEL_10;
  }
  v8 = (_DWORD *)((char *)this + 616);
  if ( (unsigned int)CHtmlHelpControl::ConvertToCacheFile(this, v7, name, 0x104u) )
  {
    v17 = *v8 != 0;
    v18 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    BitmapA = LoadImageA(v18, name, v17, 0, 0, 0x10u);
    goto LABEL_15;
  }
  AuthorMsg(0x1D805u, *((char **)this + 48));
  if ( *v8 )
    goto LABEL_25;
  v9 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
  BitmapA = LoadBitmapA(v9, "shortcut");
  *((_QWORD *)this + 54) = BitmapA;
LABEL_10:
  v11 = *((_DWORD *)this + 91);
  if ( *v8 )
  {
    v12 = v11 == 4;
    v13 = (HWND)*((_QWORD *)this + 57);
    if ( !v12 )
    {
      v14 = (LPARAM)BitmapA;
      v15 = 370;
      v16 = 2;
LABEL_24:
      SendMessageA(v13, v15, v16, v14);
      goto LABEL_25;
    }
    MoveWindow(v13, 0, 0, 40, 40, 0);
    v14 = *((_QWORD *)this + 54);
    v15 = 247;
    v16 = 1;
LABEL_23:
    v13 = (HWND)*((_QWORD *)this + 57);
    goto LABEL_24;
  }
  if ( v11 == 4 )
  {
    memset(pv, 0, sizeof(pv));
    GetObjectA(BitmapA, 32, pv);
    MoveWindow(*((HWND *)this + 57), 0, 0, DWORD1(pv[0]) + 8, DWORD2(pv[0]) + 8, 0);
    v14 = *((_QWORD *)this + 54);
    v16 = 0;
    v15 = 247;
    goto LABEL_23;
  }
LABEL_25:
  v21 = (_WORD *)*((_QWORD *)this + 72);
  if ( v21 && *v21 )
  {
    DC = GetDC(*((HWND *)this + 57));
    if ( DC )
    {
      v24 = (HFONT)*((_QWORD *)this + 152);
      if ( !v24 )
        v24 = CResourceCache::GetUIFont(v22);
      v25 = SelectObject(DC, v24);
      v26 = (const WCHAR *)*((_QWORD *)this + 72);
      v27 = v25;
      psizl = 0;
      v28 = lstrlenW(v26);
      if ( (unsigned int)IntlGetTextExtentPoint32W(DC, *((const unsigned __int16 **)this + 72), v28, &psizl, nHeight) )
      {
        SelectObject(DC, v27);
        ReleaseDC(*((HWND *)this + 57), DC);
        cy = psizl.cy;
        cx = psizl.cx;
        if ( *((_DWORD *)this + 91) != 2 )
        {
          cy = psizl.cy + 8;
          cx = psizl.cx + 8;
        }
        MoveWindow(*((HWND *)this + 57), 0, 0, cx, cy, 0);
        goto LABEL_34;
      }
    }
    return 0;
  }
LABEL_34:
  GetWindowRect(*((HWND *)this + 57), (LPRECT)((char *)this + 584));
  if ( *((_DWORD *)this + 91) == 2 )
  {
    v31 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    CursorA = LoadCursorA(v31, (LPCSTR)0x69);
    SetClassLongPtrA(*((HWND *)this + 57), -12, (LONG_PTR)CursorA);
    if ( *((_DWORD *)this + 91) == 2 && *((_DWORD *)this + 106) == -1 )
      *((_DWORD *)this + 106) = *((_DWORD *)this + 167);
  }
  v33 = *((_DWORD *)this + 90);
  if ( (unsigned int)(v33 - 16) <= 1
    && *((_DWORD *)this + 102) == 1
    && !(unsigned int)CHtmlHelpControl::OnAKLink(this, v33 == 16, 1) )
  {
    EnableWindow(*((HWND *)this + 57), 0);
    if ( *((_DWORD *)this + 91) == 2 )
      *((_DWORD *)this + 106) = *((_DWORD *)this + 166);
  }
  return 1;
}

```

## disassembly

```asm
0x180043cd8  mov     [rsp-8+arg_8], rbx
0x180043cdd  mov     [rsp-8+arg_10], rsi
0x180043ce2  push    rbp
0x180043ce3  push    rdi
0x180043ce4  push    r14
0x180043ce6  lea     rbp, [rsp-1C0h]
0x180043cee  sub     rsp, 2C0h
0x180043cf5  mov     rax, cs:__security_cookie
0x180043cfc  xor     rax, rsp
0x180043cff  mov     [rbp+1D0h+var_20], rax
0x180043d06  xor     esi, esi
0x180043d08  mov     rdi, rcx
0x180043d0b  cmp     dword ptr [rcx+16Ch], 4
0x180043d12  jnz     short loc_180043D50
0x180043d14  mov     r8, [rcx+240h]; unsigned __int16 *
0x180043d1b  lea     rax, [rbp+1D0h+WindowName]
0x180043d1f  mov     ecx, [rcx+4B4h]; unsigned int
0x180043d25  lea     rbx, aButton_1; "button"
0x180043d2c  mov     [rsp+2D0h+var_298], rsi; LPBOOL
0x180043d31  or      r9d, 0FFFFFFFFh; int
0x180043d35  mov     [rsp+2D0h+var_2A0], rsi; LPCCH
0x180043d3a  xor     edx, edx; unsigned int
0x180043d3c  mov     [rsp+2D0h+bRepaint], 104h; int
0x180043d44  mov     qword ptr [rsp+2D0h+nHeight], rax; LPSTR
0x180043d49  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180043d4e  jmp     short loc_180043D5B
0x180043d50  lea     rbx, aStatic_0; "static"
0x180043d57  mov     [rbp+1D0h+WindowName], sil
0x180043d5b  mov     rax, cs:hInstance
0x180043d62  lea     r8, [rbp+1D0h+WindowName]; lpWindowName
0x180043d66  mov     r9d, [rdi+194h]
0x180043d6d  mov     rdx, rbx; lpClassName
0x180043d70  mov     [rsp+2D0h+var_278], rsi; LPVOID
0x180043d75  or      r9d, 50004000h; dwStyle
0x180043d7c  mov     [rsp+2D0h+var_280], rax; HINSTANCE
0x180043d81  xor     ecx, ecx; dwExStyle
0x180043d83  mov     rax, [rdi+0E0h]
0x180043d8a  mov     [rsp+2D0h+var_288], 0BBEh; HMENU
0x180043d93  mov     [rsp+2D0h+var_290], rax; HWND
0x180043d98  mov     eax, 0Ch
0x180043d9d  mov     dword ptr [rsp+2D0h+var_298], eax; int
0x180043da1  mov     dword ptr [rsp+2D0h+var_2A0], eax; int
0x180043da5  mov     [rsp+2D0h+bRepaint], esi; int
0x180043da9  mov     [rsp+2D0h+nHeight], esi; unsigned int *
0x180043dad  call    IsolationAwareCreateWindowExA
0x180043db2  mov     [rdi+1C8h], rax
0x180043db9  test    rax, rax
0x180043dbc  jz      loc_1800441A9
0x180043dc2  mov     ebx, 0FFFFFFFCh
0x180043dc7  mov     rcx, rax; hWnd
0x180043dca  mov     edx, ebx; nIndex
0x180043dcc  call    cs:__imp_GetWindowLongPtrA
0x180043dd2  mov     rcx, [rdi+1C8h]; hWnd
0x180043dd9  lea     edx, [rbx-11h]; nIndex
0x180043ddc  mov     r8, rdi; dwNewLong
0x180043ddf  mov     [rdi+2A8h], rax
0x180043de6  call    cs:__imp_SetWindowLongPtrA
0x180043dec  mov     rcx, [rdi+1C8h]; hWnd
0x180043df3  lea     r8, ?StaticTextControlSubWndProc@CHtmlHelpControl@@CA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180043dfa  mov     edx, ebx; nIndex
0x180043dfc  call    cs:__imp_SetWindowLongPtrA
0x180043e02  mov     rbx, [rdi+180h]
0x180043e09  test    rbx, rbx
0x180043e0c  jz      loc_180043FE9
0x180043e12  mov     r8d, 0FFFFFFFEh; int
0x180043e18  lea     rdx, aShortcut_1; "shortcut"
0x180043e1f  mov     rcx, rbx; char *
0x180043e22  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x180043e27  test    eax, eax
0x180043e29  jnz     loc_180043F25
0x180043e2f  mov     r9d, 104h; unsigned __int64
0x180043e35  lea     r8, [rbp+1D0h+name]; char *
0x180043e3c  mov     rdx, rbx; char *
0x180043e3f  lea     r14, [rdi+268h]
0x180043e46  mov     rcx, rdi; this
0x180043e49  call    ?ConvertToCacheFile@CHtmlHelpControl@@QEAAHPEBDPEAD_K@Z; CHtmlHelpControl::ConvertToCacheFile(char const *,char *,unsigned __int64)
0x180043e4e  test    eax, eax
0x180043e50  jnz     loc_180043EED
0x180043e56  mov     r8, [rdi+0E8h]
0x180043e5d  mov     r9, rdi
0x180043e60  mov     rdx, [rdi+180h]; char *
0x180043e67  mov     ecx, 1D805h; unsigned int
0x180043e6c  call    AuthorMsg
0x180043e71  cmp     [r14], esi
0x180043e74  jnz     loc_180044011
0x180043e7a  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180043e81  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x180043e86  mov     rcx, rax; hInstance
0x180043e89  lea     rdx, aShortcut_1; "shortcut"
0x180043e90  call    cs:__imp_LoadBitmapA
0x180043e96  mov     [rdi+1B0h], rax
0x180043e9d  mov     ecx, [rdi+16Ch]
0x180043ea3  cmp     [r14], esi
0x180043ea6  jz      loc_180043F87
0x180043eac  cmp     ecx, 4
0x180043eaf  mov     rcx, [rdi+1C8h]; hWnd
0x180043eb6  jnz     loc_180043F74
0x180043ebc  mov     r9d, 28h ; '('; nWidth
0x180043ec2  mov     [rsp+2D0h+bRepaint], esi; bRepaint
0x180043ec6  xor     r8d, r8d; Y
0x180043ec9  mov     [rsp+2D0h+nHeight], r9d; nHeight
0x180043ece  xor     edx, edx; X
0x180043ed0  call    cs:__imp_MoveWindow
0x180043ed6  mov     r9, [rdi+1B0h]
0x180043edd  mov     edx, 0F7h
0x180043ee2  mov     r8d, 1
0x180043ee8  jmp     loc_180044004
0x180043eed  cmp     [r14], esi
0x180043ef0  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180043ef7  mov     ebx, esi
0x180043ef9  setnz   bl
0x180043efc  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x180043f01  mov     rcx, rax; hInst
0x180043f04  mov     [rsp+2D0h+bRepaint], 10h; fuLoad
0x180043f0c  xor     r9d, r9d; cx
0x180043f0f  mov     [rsp+2D0h+nHeight], esi; cy
0x180043f13  mov     r8d, ebx; type
0x180043f16  lea     rdx, [rbp+1D0h+name]; name
0x180043f1d  call    cs:__imp_LoadImageA
0x180043f23  jmp     short loc_180043F44
0x180043f25  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180043f2c  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x180043f31  mov     rdx, rbx; lpBitmapName
0x180043f34  mov     rcx, rax; hInstance
0x180043f37  call    cs:__imp_LoadBitmapA
0x180043f3d  lea     r14, [rdi+268h]
0x180043f44  mov     [rdi+1B0h], rax
0x180043f4b  test    rax, rax
0x180043f4e  jnz     loc_180043E9D
0x180043f54  mov     r8, [rdi+0E8h]
0x180043f5b  mov     r9, rdi
0x180043f5e  mov     rdx, [rdi+180h]; char *
0x180043f65  mov     ecx, 1D805h; unsigned int
0x180043f6a  call    AuthorMsg
0x180043f6f  jmp     loc_180044011
0x180043f74  mov     r9, rax
0x180043f77  mov     edx, 172h
0x180043f7c  mov     r8d, 2
0x180043f82  jmp     loc_18004400B
0x180043f87  cmp     ecx, 4
0x180043f8a  jnz     loc_180044011
0x180043f90  xorps   xmm0, xmm0
0x180043f93  lea     edx, [rcx+1Ch]; c
0x180043f96  mov     rcx, rax; h
0x180043f99  lea     r8, [rsp+2D0h+pv]; pv
0x180043f9e  movups  [rsp+2D0h+pv], xmm0
0x180043fa3  movups  [rsp+2D0h+var_258], xmm0
0x180043fa8  call    cs:__imp_GetObjectA
0x180043fae  mov     eax, dword ptr [rsp+2D0h+pv+8]
0x180043fb2  xor     r8d, r8d; Y
0x180043fb5  mov     r9d, dword ptr [rsp+2D0h+pv+4]
0x180043fba  add     eax, 8
0x180043fbd  mov     rcx, [rdi+1C8h]; hWnd
0x180043fc4  add     r9d, 8; nWidth
0x180043fc8  mov     [rsp+2D0h+bRepaint], esi; bRepaint
0x180043fcc  xor     edx, edx; X
0x180043fce  mov     [rsp+2D0h+nHeight], eax; nHeight
0x180043fd2  call    cs:__imp_MoveWindow
0x180043fd8  mov     r9, [rdi+1B0h]
0x180043fdf  xor     r8d, r8d
0x180043fe2  mov     edx, 0F7h
0x180043fe7  jmp     short loc_180044004
0x180043fe9  mov     rax, [rdi+4C0h]
0x180043ff0  test    rax, rax
0x180043ff3  jnz     short loc_180043FFA
0x180043ff5  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x180043ffa  xor     r9d, r9d; lParam
0x180043ffd  mov     r8, rax; wParam
0x180044000  lea     edx, [r9+30h]; Msg
0x180044004  mov     rcx, [rdi+1C8h]; hWnd
0x18004400b  call    cs:__imp_SendMessageA
0x180044011  mov     rax, [rdi+240h]
0x180044018  test    rax, rax
0x18004401b  jz      loc_1800440E3
0x180044021  cmp     [rax], si
0x180044024  jz      loc_1800440E3
0x18004402a  mov     rcx, [rdi+1C8h]; hWnd
0x180044031  call    cs:__imp_GetDC
0x180044037  mov     rbx, rax
0x18004403a  test    rax, rax
0x18004403d  jz      loc_1800441A9
0x180044043  mov     rax, [rdi+4C0h]
0x18004404a  test    rax, rax
0x18004404d  jnz     short loc_180044054
0x18004404f  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x180044054  mov     rdx, rax; h
0x180044057  mov     rcx, rbx; hdc
0x18004405a  call    cs:__imp_SelectObject
0x180044060  mov     rcx, [rdi+240h]; lpString
0x180044067  mov     r14, rax
0x18004406a  mov     qword ptr [rsp+2D0h+psizl.cx], rsi
0x18004406f  call    cs:__imp_lstrlenW
0x180044075  mov     rdx, [rdi+240h]; unsigned __int16 *
0x18004407c  lea     r9, [rsp+2D0h+psizl]; psizl
0x180044081  mov     r8d, eax; int
0x180044084  mov     rcx, rbx; HDC
0x180044087  call    ?IntlGetTextExtentPoint32W@@YAHPEAUHDC__@@PEBGHPEAUtagSIZE@@PEAI@Z; IntlGetTextExtentPoint32W(HDC__ *,ushort const *,int,tagSIZE *,uint *)
0x18004408c  test    eax, eax
0x18004408e  jz      loc_1800441A9
0x180044094  mov     rdx, r14; h
0x180044097  mov     rcx, rbx; hdc
0x18004409a  call    cs:__imp_SelectObject
0x1800440a0  mov     rcx, [rdi+1C8h]; hWnd
0x1800440a7  mov     rdx, rbx; hDC
0x1800440aa  call    cs:__imp_ReleaseDC
0x1800440b0  mov     rcx, [rdi+1C8h]; hWnd
0x1800440b7  xor     r8d, r8d; Y
0x1800440ba  mov     eax, [rsp+2D0h+psizl.cy]
0x1800440be  xor     edx, edx; X
0x1800440c0  cmp     dword ptr [rdi+16Ch], 2
0x1800440c7  mov     r9d, [rsp+2D0h+psizl.cx]
0x1800440cc  mov     [rsp+2D0h+bRepaint], esi; bRepaint
0x1800440d0  jz      short loc_1800440D9
0x1800440d2  add     eax, 8
0x1800440d5  add     r9d, 8; nWidth
0x1800440d9  mov     [rsp+2D0h+nHeight], eax; nHeight
0x1800440dd  call    cs:__imp_MoveWindow
0x1800440e3  mov     rcx, [rdi+1C8h]; hWnd
0x1800440ea  lea     rdx, [rdi+248h]; lpRect
0x1800440f1  call    cs:__imp_GetWindowRect
0x1800440f7  cmp     dword ptr [rdi+16Ch], 2
0x1800440fe  jnz     short loc_18004414D
0x180044100  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180044107  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004410c  mov     rcx, rax; hInstance
0x18004410f  mov     edx, 69h ; 'i'; lpCursorName
0x180044114  call    cs:__imp_LoadCursorA
0x18004411a  mov     rcx, [rdi+1C8h]; hWnd
0x180044121  mov     edx, 0FFFFFFF4h; nIndex
0x180044126  mov     r8, rax; dwNewLong
0x180044129  call    cs:__imp_SetClassLongPtrA
0x18004412f  cmp     dword ptr [rdi+16Ch], 2
0x180044136  jnz     short loc_18004414D
0x180044138  cmp     dword ptr [rdi+1A8h], 0FFFFFFFFh
0x18004413f  jnz     short loc_18004414D
0x180044141  mov     eax, [rdi+29Ch]
0x180044147  mov     [rdi+1A8h], eax
0x18004414d  mov     ecx, [rdi+168h]
0x180044153  lea     eax, [rcx-10h]
0x180044156  cmp     eax, 1
0x180044159  ja      short loc_1800441A2
0x18004415b  cmp     dword ptr [rdi+198h], 1
0x180044162  jnz     short loc_1800441A2
0x180044164  cmp     ecx, 10h
0x180044167  mov     edx, esi
0x180044169  mov     r8d, 1; int
0x18004416f  mov     rcx, rdi; this
0x180044172  setz    dl; int
0x180044175  call    ?OnAKLink@CHtmlHelpControl@@QEAAHHH@Z; CHtmlHelpControl::OnAKLink(int,int)
0x18004417a  test    eax, eax
0x18004417c  jnz     short loc_1800441A2
0x18004417e  mov     rcx, [rdi+1C8h]; hWnd
0x180044185  xor     edx, edx; bEnable
0x180044187  call    cs:__imp_EnableWindow
0x18004418d  cmp     dword ptr [rdi+16Ch], 2
0x180044194  jnz     short loc_1800441A2
0x180044196  mov     ecx, [rdi+298h]
0x18004419c  mov     [rdi+1A8h], ecx
0x1800441a2  mov     eax, 1
0x1800441a7  jmp     short loc_1800441AB
0x1800441a9  xor     eax, eax
0x1800441ab  mov     rcx, [rbp+1D0h+var_20]
0x1800441b2  xor     rcx, rsp; StackCookie
0x1800441b5  call    __security_check_cookie
0x1800441ba  lea     r11, [rsp+2D0h+var_10]
0x1800441c2  mov     rbx, [r11+28h]
0x1800441c6  mov     rsi, [r11+30h]
0x1800441ca  mov     rsp, r11
0x1800441cd  pop     r14
0x1800441cf  pop     rdi
0x1800441d0  pop     rbp
0x1800441d1  retn
```
