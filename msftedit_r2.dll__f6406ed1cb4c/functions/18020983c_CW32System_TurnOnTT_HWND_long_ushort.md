# CW32System::TurnOnTT(HWND__ *,long,ushort *)

- ea: `0x18020983c`
- end: `0x180209ae9`
- name: `?TurnOnTT@CW32System@@SAPEAUHWND__@@PEAU2@JPEAG@Z`
- size: `685`
- prototype: `HWND __fastcall(HWND hWndParent, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b3790`
- `0x1800c1ce0`

## callees

- `0x180034728`
- `0x1800ad688`
- `0x1800c0744`
- `0x1800f1f94`
- `0x18013ce80`
- `0x18013dce6`
- `0x18020983c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802098e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802098e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1802098ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1802098ca`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x1802099a6`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x1802099a6`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18020996e`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18020996e`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x18020987d`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x18020987d`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180209a13`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180209a13`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x180209a56`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x180209a56`

## string_xrefs

- `0x1802098c3`: `COMCTL32.DLL`
- `0x1802098df`: `InitCommonControlsEx`

## pseudocode

```c
HWND __fastcall CW32System::TurnOnTT(HWND hWndParent, int a2, unsigned __int16 *a3)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  const unsigned __int16 *FontName; // rax
  HFONT v9; // rax
  UINT DoubleClickTime; // eax
  _DWORD v12[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13[3]; // [rsp+70h] [rbp-90h] BYREF
  struct tagRECT Rect; // [rsp+88h] [rbp-78h] BYREF
  HINSTANCE v15; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v16; // [rsp+A0h] [rbp-60h]
  LOGFONTW lf; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v13, 0, 0x48u);
  GetClientRect(hWndParent, &Rect);
  v15 = hinstRE;
  v13[0] = 0x100000002CLL;
  v13[1] = (__int64)hWndParent;
  v13[2] = 0;
  v16 = a3;
  if ( CW32System::_hwndTT )
  {
    if ( CW32System::_cpMostURL )
      CW32System::TurnOffTT();
LABEL_9:
    CW32System::SendMessage(CW32System::_hwndTT, 0x433u, 0, (__int64)v13);
    if ( a2 == -1 )
    {
      memset_0(&lf, 0, sizeof(lf));
      FontName = CFICache::GetFontName(5);
      CopyLFFontName(&lf, FontName, 0);
      v9 = CreateFontIndirectW(&lf);
      CW32System::SendMessage(CW32System::_hwndTT, 0x30u, (unsigned __int64)v9, 0);
    }
    if ( !CW32System::SendMessage(CW32System::_hwndTT, 0x432u, 0, (__int64)v13) )
      return 0;
    DoubleClickTime = GetDoubleClickTime();
    CW32System::SendMessage(CW32System::_hwndTT, 0x403u, 3u, DoubleClickTime / 5);
    CW32System::SendMessage(CW32System::_hwndTT, 0x403u, 2u, 1000);
    CW32System::SendMessage(CW32System::_hwndTT, 0x411u, 1u, (__int64)v13);
    CW32System::_cpMostURL = a2;
    return CW32System::_hwndTT;
  }
  ModuleHandleW = GetModuleHandleW(L"COMCTL32.DLL");
  if ( !ModuleHandleW )
    return 0;
  ProcAddress = GetProcAddress(ModuleHandleW, "InitCommonControlsEx");
  if ( !ProcAddress )
    return 0;
  v12[0] = 8;
  v12[1] = 4;
  if ( !((unsigned int (__fastcall *)(_DWORD *))ProcAddress)(v12) )
    return 0;
  CW32System::_hwndTT = CreateWindowExW(
                          0,
                          L"tooltips_class32",
                          &WindowName,
                          0x80000000,
                          0x80000000,
                          0x80000000,
                          0x80000000,
                          0x80000000,
                          hWndParent,
                          0,
                          hinstRE,
                          0);
  SetWindowPos(CW32System::_hwndTT, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x213u);
  if ( a2 == -1 )
    goto LABEL_9;
  return CW32System::_hwndTT;
}

```

## disassembly

```asm
0x18020983c  mov     [rsp-8+arg_8], rbx
0x180209841  push    rbp
0x180209842  push    rsi
0x180209843  push    rdi
0x180209844  lea     rbp, [rsp-30h]
0x180209849  sub     rsp, 130h
0x180209850  mov     rax, cs:__security_cookie
0x180209857  xor     rax, rsp
0x18020985a  mov     [rbp+40h+var_20], rax
0x18020985e  mov     edi, edx
0x180209860  mov     rbx, r8
0x180209863  xor     edx, edx; Val
0x180209865  mov     rsi, rcx
0x180209868  lea     rcx, [rsp+140h+var_D0]; void *
0x18020986d  lea     r8d, [rdx+48h]; Size
0x180209871  call    memset_0
0x180209876  lea     rdx, [rbp+40h+Rect]; lpRect
0x18020987a  mov     rcx, rsi; hWnd
0x18020987d  call    cs:__imp_GetClientRect
0x180209884  nop     dword ptr [rax+rax+00h]
0x180209889  cmp     cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA, 0; HWND__ * CW32System::_hwndTT
0x180209891  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x180209898  mov     [rbp+40h+var_A8], rax
0x18020989c  mov     dword ptr [rsp+140h+var_D0], 2Ch ; ','
0x1802098a4  mov     dword ptr [rsp+140h+var_D0+4], 10h
0x1802098ac  mov     [rsp+140h+var_C8], rsi
0x1802098b1  mov     [rbp+40h+var_C0], 0
0x1802098b9  mov     [rbp+40h+var_A0], rbx
0x1802098bd  jnz     loc_1802099BD
0x1802098c3  lea     rcx, aComctl32Dll; "COMCTL32.DLL"
0x1802098ca  call    cs:__imp_GetModuleHandleW
0x1802098d1  nop     dword ptr [rax+rax+00h]
0x1802098d6  test    rax, rax
0x1802098d9  jz      loc_180209A52
0x1802098df  lea     rdx, aInitcommoncont; "InitCommonControlsEx"
0x1802098e6  mov     rcx, rax; hModule
0x1802098e9  call    cs:__imp_GetProcAddress
0x1802098f0  nop     dword ptr [rax+rax+00h]
0x1802098f5  test    rax, rax
0x1802098f8  jz      loc_180209A52
0x1802098fe  lea     rcx, [rsp+140h+var_E0]
0x180209903  mov     [rsp+140h+var_E0], 8
0x18020990b  mov     [rsp+140h+var_DC], 4
0x180209913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180209918  test    eax, eax
0x18020991a  jz      loc_180209A52
0x180209920  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x180209927  lea     r8, WindowName; lpWindowName
0x18020992e  mov     [rsp+140h+lpParam], 0; lpParam
0x180209937  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x18020993e  mov     [rsp+140h+hInstance], rax; hInstance
0x180209943  mov     r9d, 80000000h; dwStyle
0x180209949  mov     [rsp+140h+hMenu], 0; hMenu
0x180209952  mov     eax, 80000000h
0x180209957  mov     [rsp+140h+hWndParent], rsi; hWndParent
0x18020995c  xor     ecx, ecx; dwExStyle
0x18020995e  mov     [rsp+140h+nHeight], eax; nHeight
0x180209962  mov     [rsp+140h+nWidth], eax; nWidth
0x180209966  mov     [rsp+140h+Y], eax; Y
0x18020996a  mov     [rsp+140h+X], eax; X
0x18020996e  call    cs:__imp_CreateWindowExW
0x180209975  nop     dword ptr [rax+rax+00h]
0x18020997a  mov     [rsp+140h+nWidth], 213h; uFlags
0x180209982  xor     r9d, r9d; Y
0x180209985  mov     rcx, rax; hWnd
0x180209988  mov     [rsp+140h+Y], 0; cy
0x180209990  xor     r8d, r8d; X
0x180209993  mov     cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA, rax; HWND__ * CW32System::_hwndTT
0x18020999a  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18020999e  mov     [rsp+140h+X], 0; cx
0x1802099a6  call    cs:__imp_SetWindowPos
0x1802099ad  nop     dword ptr [rax+rax+00h]
0x1802099b2  cmp     edi, 0FFFFFFFFh
0x1802099b5  jnz     loc_180209AC2
0x1802099bb  jmp     short loc_1802099CB
0x1802099bd  cmp     cs:?_cpMostURL@CW32System@@2JA, 0; long CW32System::_cpMostURL
0x1802099c4  jz      short loc_1802099CB
0x1802099c6  call    ?TurnOffTT@CW32System@@SAXXZ; CW32System::TurnOffTT(void)
0x1802099cb  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x1802099d2  lea     r9, [rsp+140h+var_D0]; __int64
0x1802099d7  xor     r8d, r8d; unsigned __int64
0x1802099da  mov     edx, 433h; unsigned int
0x1802099df  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x1802099e4  cmp     edi, 0FFFFFFFFh
0x1802099e7  jnz     short loc_180209A34
0x1802099e9  xor     edx, edx; Val
0x1802099eb  lea     r8d, [rdi+5Dh]; Size
0x1802099ef  lea     rcx, [rbp+40h+lf]; void *
0x1802099f3  call    memset_0
0x1802099f8  lea     ecx, [rdi+6]; __int16
0x1802099fb  call    ?GetFontName@CFICache@@SAPEBGF@Z; CFICache::GetFontName(short)
0x180209a00  mov     rdx, rax; unsigned __int16 *
0x180209a03  lea     rcx, [rbp+40h+lf]; struct tagLOGFONTW *
0x180209a07  xor     r8d, r8d; bool
0x180209a0a  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG_N@Z; CopyLFFontName(tagLOGFONTW &,ushort const *,bool)
0x180209a0f  lea     rcx, [rbp+40h+lf]; lplf
0x180209a13  call    cs:__imp_CreateFontIndirectW
0x180209a1a  nop     dword ptr [rax+rax+00h]
0x180209a1f  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x180209a26  lea     edx, [rdi+31h]; unsigned int
0x180209a29  mov     r8, rax; unsigned __int64
0x180209a2c  xor     r9d, r9d; __int64
0x180209a2f  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180209a34  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x180209a3b  lea     r9, [rsp+140h+var_D0]; __int64
0x180209a40  xor     r8d, r8d; unsigned __int64
0x180209a43  mov     edx, 432h; unsigned int
0x180209a48  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180209a4d  test    rax, rax
0x180209a50  jnz     short loc_180209A56
0x180209a52  xor     eax, eax
0x180209a54  jmp     short loc_180209AC9
0x180209a56  call    cs:__imp_GetDoubleClickTime
0x180209a5d  nop     dword ptr [rax+rax+00h]
0x180209a62  mov     ebx, 403h
0x180209a67  mov     r8d, 3; unsigned __int64
0x180209a6d  mov     ecx, eax
0x180209a6f  mov     eax, 0CCCCCCCDh
0x180209a74  mul     ecx
0x180209a76  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x180209a7d  shr     edx, 2
0x180209a80  mov     r9d, edx; __int64
0x180209a83  mov     edx, ebx; unsigned int
0x180209a85  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180209a8a  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x180209a91  lea     r9d, [rbx-1Bh]; __int64
0x180209a95  mov     r8d, 2; unsigned __int64
0x180209a9b  mov     edx, ebx; unsigned int
0x180209a9d  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180209aa2  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x180209aa9  lea     r9, [rsp+140h+var_D0]; __int64
0x180209aae  lea     edx, [rbx+0Eh]; unsigned int
0x180209ab1  mov     r8d, 1; unsigned __int64
0x180209ab7  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180209abc  mov     cs:?_cpMostURL@CW32System@@2JA, edi; long CW32System::_cpMostURL
0x180209ac2  mov     rax, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; HWND__ * CW32System::_hwndTT
0x180209ac9  mov     rcx, [rbp+40h+var_20]
0x180209acd  xor     rcx, rsp; StackCookie
0x180209ad0  call    __security_check_cookie
0x180209ad5  mov     rbx, [rsp+140h+arg_8]
0x180209add  add     rsp, 130h
0x180209ae4  pop     rdi
0x180209ae5  pop     rsi
0x180209ae6  pop     rbp
0x180209ae7  retn
```
