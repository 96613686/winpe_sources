# DirectUI::HWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)

- ea: `0x1800f71ac`
- end: `0x1800f76d0`
- name: `?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z`
- size: `1316`
- prototype: `__int64 __usercall@<rax>(DirectUI::HWNDElement *__hidden this@<rcx>, HWND hWnd@<rdx>, bool@<r8b>, unsigned int@<r9d>, struct DirectUI::Element *, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18007c1bc`
- `0x18015b7ac`
- `0x18017efa0`

## callees

- `0x180085548`
- `0x180088928`
- `0x18009a208`
- `0x1800a7838`
- `0x1800f71ac`
- `0x180104f84`
- `0x180114520`
- `0x180114ebc`
- `0x18012f8e8`
- `0x180168e34`
- `0x180170618`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7307`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f733e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7395`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7307`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f733e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7535`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800f74b8`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800f74b8`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800f748d`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800f748d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800f7495`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800f7495`
- `GDI32!DeleteObject` at `0x1800f72cf`
- `GDI32!DeleteObject` at `0x1800f72cf`
- `GDI32!GetStockObject` at `0x1800f735b`
- `GDI32!GetStockObject` at `0x1800f735b`
- `GDI32!CreateHalftonePalette` at `0x1800f75b1`
- `GDI32!CreateHalftonePalette` at `0x1800f75b1`
- `USER32!DefWindowProcW` at `0x1800f7379`
- `USER32!DestroyWindow` at `0x1800f72b6`
- `USER32!DestroyWindow` at `0x1800f72b6`
- `USER32!GetDC` at `0x1800f75a5`
- `USER32!GetDC` at `0x1800f75a5`
- `USER32!SetWindowLongPtrW` at `0x1800f73f8`
- `USER32!SetWindowLongPtrW` at `0x1800f740a`
- `USER32!SetWindowLongPtrW` at `0x1800f746b`
- `USER32!SetWindowLongPtrW` at `0x1800f750c`
- `USER32!SetWindowLongPtrW` at `0x1800f73f8`
- `USER32!SetWindowLongPtrW` at `0x1800f740a`
- `USER32!SetWindowLongPtrW` at `0x1800f746b`
- `USER32!SetWindowLongPtrW` at `0x1800f750c`
- `USER32!SendMessageW` at `0x1800f741e`
- `USER32!SendMessageW` at `0x1800f741e`
- `USER32!GetWindowLongPtrW` at `0x1800f7439`
- `USER32!GetWindowLongPtrW` at `0x1800f7456`
- `USER32!GetWindowLongPtrW` at `0x1800f74f7`
- `USER32!GetWindowLongPtrW` at `0x1800f7439`
- `USER32!GetWindowLongPtrW` at `0x1800f7456`
- `USER32!GetWindowLongPtrW` at `0x1800f74f7`
- `USER32!LoadCursorW` at `0x1800f734f`
- `USER32!LoadCursorW` at `0x1800f734f`
- `USER32!ReleaseDC` at `0x1800f75c4`
- `USER32!ReleaseDC` at `0x1800f75c4`
- `USER32!GetClassInfoExW` at `0x1800f7317`
- `USER32!GetClassInfoExW` at `0x1800f7317`
- `USER32!RegisterClassExW` at `0x1800f7384`
- `USER32!RegisterClassExW` at `0x1800f7384`
- `USER32!CreateWindowExW` at `0x1800f73d3`
- `USER32!CreateWindowExW` at `0x1800f73d3`
- `USER32!__imp_IsWindowGdiScaled` at `0x1800f7594`
- `USER32!__imp_IsWindowGdiScaled` at `0x1800f7594`
- `DUser!CreateGadget` at `0x1800f7526`
- `DUser!CreateGadget` at `0x1800f7526`
- `DUser!SetGadgetMessageFilter` at `0x1800f7551`
- `DUser!SetGadgetMessageFilter` at `0x1800f7551`
- `DUser!SetGadgetStyle` at `0x1800f756d`
- `DUser!SetGadgetStyle` at `0x1800f756d`
- `DUser!DisableContainerHwnd` at `0x1800f72a4`
- `DUser!DisableContainerHwnd` at `0x1800f72a4`
- `DUser!SetGadgetRootInfo` at `0x1800f7676`
- `DUser!SetGadgetRootInfo` at `0x1800f7676`

## pseudocode

```c
__int64 __fastcall DirectUI::HWNDElement::Initialize(
        DirectUI::HWNDElement *this,
        HWND hWnd,
        unsigned __int8 a3,
        int a4,
        struct DirectUI::Element *a5,
        unsigned int *a6)
{
  int v6; // r15d
  signed int LastError; // ebx
  __int64 v11; // rax
  const WCHAR *v12; // rbx
  HWND v13; // rcx
  void *v14; // rcx
  HMODULE ModuleHandleW; // rax
  HBRUSH StockObject; // rax
  HMODULE hInstance; // rax
  HWND Window; // rax
  __int16 v20; // ax
  HWND v21; // rcx
  LONG_PTR WindowLongPtrW; // rax
  int v23; // eax
  LANGID ThreadUILanguage; // ax
  LONG_PTR v25; // rax
  __int64 Gadget; // rax
  __int64 v27; // rbx
  HWND v28; // rdi
  HDC DC; // rbx
  __int64 v30; // rax
  int v31; // ecx
  int v32; // r8d
  UINT v33; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszClass; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+74h] [rbp-8Ch]
  int v37; // [rsp+7Ch] [rbp-84h]
  __int128 v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+98h] [rbp-68h]
  tagWNDCLASSEXW wcx; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR LCData[16]; // [rsp+F0h] [rbp-10h] BYREF

  v6 = a3;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_WORD *)this + 113) = 0;
  memset_0(&wcx, 0, sizeof(wcx));
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_WORD *)this + 124) = 0;
  *((_DWORD *)this + 63) = 0;
  LastError = DirectUI::Element::Initialize(this, a4 | 1u, a5, a6);
  if ( LastError < 0 )
    goto LABEL_4;
  v11 = *(_QWORD *)this;
  wcx.cbSize = 80;
  lpszClass = 0;
  v33 = 0x4000;
  (*(void (__fastcall **)(DirectUI::HWNDElement *, LPCWSTR *, UINT *))(v11 + 456))(this, &lpszClass, &v33);
  v12 = lpszClass;
  if ( !lpszClass )
    goto LABEL_3;
  ModuleHandleW = GetModuleHandleW(0);
  if ( !GetClassInfoExW(ModuleHandleW, v12, &wcx) )
  {
    memset_0(&wcx, 0, sizeof(wcx));
    wcx.style = v33;
    wcx.cbSize = 80;
    wcx.hInstance = GetModuleHandleW(0);
    wcx.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
    StockObject = (HBRUSH)GetStockObject(0);
    wcx.cbWndExtra = 8;
    wcx.hbrBackground = StockObject;
    wcx.lpszClassName = lpszClass;
    wcx.lpfnWndProc = DefWindowProcW;
    if ( !RegisterClassExW(&wcx) )
      goto LABEL_3;
  }
  hInstance = GetModuleHandleW(0);
  Window = CreateWindowExW(0, lpszClass, 0, 0x46000000u, 0, 0, 0, 0, hWnd, 0, hInstance, 0);
  *((_QWORD *)this + 25) = Window;
  if ( !Window )
  {
LABEL_3:
    LastError = -2147220503;
LABEL_4:
    DisableContainerHwnd(*((_QWORD *)this + 25));
    v13 = (HWND)*((_QWORD *)this + 25);
    if ( v13 )
    {
      DestroyWindow(v13);
      *((_QWORD *)this + 25) = 0;
    }
    v14 = (void *)*((_QWORD *)this + 27);
    if ( v14 )
    {
      DeleteObject(v14);
      *((_QWORD *)this + 27) = 0;
    }
    return (unsigned int)LastError;
  }
  SetWindowLongPtrW(Window, -4, (LONG_PTR)DirectUI::HWNDElement::StaticWndProc);
  SetWindowLongPtrW(*((HWND *)this + 25), 0, (LONG_PTR)this);
  v20 = SendMessageW(hWnd, 0x129u, 0, 0);
  v21 = (HWND)*((_QWORD *)this + 25);
  *((_WORD *)this + 113) = v20;
  if ( (GetWindowLongPtrW(v21, -20) & 0x400000) != 0 )
  {
    WindowLongPtrW = GetWindowLongPtrW(*((HWND *)this + 25), -20);
    SetWindowLongPtrW(*((HWND *)this + 25), -20, WindowLongPtrW & 0xFFFFFFFFFFBFFFFFuLL);
    DirectUI::Element::SetDirection(this, 1);
  }
  v23 = DirectUI::g_RTLOS;
  if ( DirectUI::g_RTLOS == -1 )
  {
    if ( (a4 & 4) != 0 )
      ThreadUILanguage = GetThreadUILanguage();
    else
      ThreadUILanguage = GetUserDefaultUILanguage();
    DirectUI::g_RTLOS = 0;
    if ( !ThreadUILanguage )
      goto LABEL_25;
    if ( GetLocaleInfoW(ThreadUILanguage, 0x58u, LCData, 16) && (LCData[7] & 0x800) != 0 )
    {
      v23 = 1;
      DirectUI::g_RTLOS = 1;
    }
    else
    {
      v23 = DirectUI::g_RTLOS;
    }
  }
  if ( v23 == 1 )
  {
    DirectUI::Element::SetDirection(this, 1);
    v25 = GetWindowLongPtrW(*((HWND *)this + 25), -20);
    SetWindowLongPtrW(*((HWND *)this + 25), -20, v25 & 0xFFFFFFFFFFBFFFFFuLL);
  }
LABEL_25:
  Gadget = CreateGadget(*((_QWORD *)this + 25), 1, DirectUI::Element::_DisplayNodeCallback, this);
  *((_QWORD *)this + 1) = Gadget;
  if ( !Gadget )
  {
    LastError = GetLastError();
    goto LABEL_4;
  }
  SetGadgetMessageFilter(Gadget, 0, 157);
  SetGadgetStyle(*((_QWORD *)this + 1), (8 * v6) | 0x801u, 3627);
  if ( (unsigned __int8)IsPalette() )
  {
    v27 = (*(__int64 (__fastcall **)(DirectUI::HWNDElement *))(*(_QWORD *)this + 360LL))(this);
    v28 = (HWND)(v27 & -(__int64)((unsigned int)IsWindowGdiScaled(v27) != 0));
    DC = GetDC(v28);
    *((_QWORD *)this + 27) = CreateHalftonePalette(DC);
    ReleaseDC(v28, DC);
    if ( !*((_QWORD *)this + 27) )
    {
      LastError = -2147221502;
      goto LABEL_4;
    }
  }
  v30 = *((_QWORD *)this + 27);
  v31 = 6;
  v36 = 6;
  v40 = v30;
  v39 = 0;
  v35 = 48;
  v37 = 0;
  v38 = 0;
  if ( (a4 & 8) != 0 )
  {
    v31 = 22;
    DWORD1(v38) = 1;
    LODWORD(v36) = 22;
  }
  if ( (a4 & 0x10) != 0 )
  {
    v31 |= 0x20u;
    DWORD2(v38) = 1;
    LODWORD(v36) = v31;
  }
  if ( (a4 & 0x20) != 0 )
  {
    v31 |= 0x40u;
    HIDWORD(v38) = 1;
    LODWORD(v36) = v31;
  }
  if ( (a4 & 0x40) != 0 )
  {
    v31 |= 0x80u;
    LODWORD(v39) = 1;
    LODWORD(v36) = v31;
  }
  if ( (a4 & 0x80) != 0 )
  {
    HIDWORD(v39) = 1;
    LODWORD(v36) = v31 | 0x100;
  }
  SetGadgetRootInfo(*((_QWORD *)this + 1), &v35);
  *((_BYTE *)this + 151) |= 8u;
  DirectUI::Element::SetAccRole(this, 10);
  if ( (unsigned int)DirectUI::GetScalingMode() == 4 )
  {
    DirectUI::Element::_SetValue(
      this,
      (const struct DirectUI::PropertyInfo *)&off_1801D5CC0,
      v32,
      (struct DirectUI::Value *)&unk_1801F0D00,
      0);
    DirectUI::Value::Release((DirectUI::Value *)&unk_1801F0D00);
    DirectUI::HWNDElement::_UpdateDesktopScaleFactor(this);
  }
  return 0;
}

```

## disassembly

```asm
0x1800f71ac  mov     [rsp-8+arg_10], rbx
0x1800f71b1  push    rbp
0x1800f71b2  push    rsi
0x1800f71b3  push    rdi
0x1800f71b4  push    r12
0x1800f71b6  push    r13
0x1800f71b8  push    r14
0x1800f71ba  push    r15
0x1800f71bc  lea     rbp, [rsp-20h]
0x1800f71c1  sub     rsp, 120h
0x1800f71c8  mov     rax, cs:__security_cookie
0x1800f71cf  xor     rax, rsp
0x1800f71d2  mov     [rbp+50h+var_40], rax
0x1800f71d6  mov     rbx, [rbp+50h+arg_28]
0x1800f71dd  xor     r12d, r12d
0x1800f71e0  movzx   r15d, r8b
0x1800f71e4  mov     rdi, rdx
0x1800f71e7  mov     rsi, rcx
0x1800f71ea  mov     [rcx+0C8h], r12
0x1800f71f1  mov     [rcx+8], r12
0x1800f71f5  xor     edx, edx; Val
0x1800f71f7  mov     [rcx+0D8h], r12
0x1800f71fe  lea     r8d, [r12+50h]; Size
0x1800f7203  mov     [rcx+0E2h], r12w
0x1800f720b  mov     r14d, r9d
0x1800f720e  lea     rcx, [rbp+50h+wcx]; void *
0x1800f7212  call    memset_0
0x1800f7217  mov     r8, [rbp+50h+arg_20]; struct DirectUI::Element *
0x1800f721e  lea     r13d, [r12+1]
0x1800f7223  mov     edx, r14d
0x1800f7226  mov     [rsi+0E8h], r12
0x1800f722d  or      edx, r13d; unsigned int
0x1800f7230  mov     [rsi+0D0h], r12
0x1800f7237  mov     r9, rbx; unsigned int *
0x1800f723a  mov     [rsi+0F0h], r12
0x1800f7241  mov     rcx, rsi; this
0x1800f7244  mov     [rsi+0F8h], r12w
0x1800f724c  mov     [rsi+0FCh], r12d
0x1800f7253  call    ?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x1800f7258  mov     ebx, eax
0x1800f725a  test    eax, eax
0x1800f725c  js      short loc_1800F729D
0x1800f725e  mov     rax, [rsi]
0x1800f7261  lea     r8, [rsp+150h+var_F0]
0x1800f7266  lea     rdx, [rsp+150h+lpszClass]
0x1800f726b  mov     [rbp+50h+wcx.cbSize], 50h ; 'P'
0x1800f7272  mov     rcx, rsi
0x1800f7275  mov     [rsp+150h+lpszClass], r12
0x1800f727a  mov     [rsp+150h+var_F0], 4000h
0x1800f7282  mov     rax, [rax+1C8h]
0x1800f7289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f728e  mov     rbx, [rsp+150h+lpszClass]
0x1800f7293  test    rbx, rbx
0x1800f7296  jnz     short loc_1800F7305
0x1800f7298  mov     ebx, 800403E9h
0x1800f729d  mov     rcx, [rsi+0C8h]
0x1800f72a4  call    cs:__imp_DisableContainerHwnd
0x1800f72aa  mov     rcx, [rsi+0C8h]; hWnd
0x1800f72b1  test    rcx, rcx
0x1800f72b4  jz      short loc_1800F72C3
0x1800f72b6  call    cs:__imp_DestroyWindow
0x1800f72bc  mov     [rsi+0C8h], r12
0x1800f72c3  mov     rcx, [rsi+0D8h]; ho
0x1800f72ca  test    rcx, rcx
0x1800f72cd  jz      short loc_1800F72DC
0x1800f72cf  call    cs:__imp_DeleteObject
0x1800f72d5  mov     [rsi+0D8h], r12
0x1800f72dc  mov     eax, ebx
0x1800f72de  mov     rcx, [rbp+50h+var_40]
0x1800f72e2  xor     rcx, rsp; StackCookie
0x1800f72e5  call    __security_check_cookie
0x1800f72ea  mov     rbx, [rsp+150h+arg_10]
0x1800f72f2  add     rsp, 120h
0x1800f72f9  pop     r15
0x1800f72fb  pop     r14
0x1800f72fd  pop     r13
0x1800f72ff  pop     r12
0x1800f7301  pop     rdi
0x1800f7302  pop     rsi
0x1800f7303  pop     rbp
0x1800f7304  retn
0x1800f7305  xor     ecx, ecx; lpModuleName
0x1800f7307  call    cs:__imp_GetModuleHandleW
0x1800f730d  lea     r8, [rbp+50h+wcx]; lpwcx
0x1800f7311  mov     rdx, rbx; lpszClass
0x1800f7314  mov     rcx, rax; hInstance
0x1800f7317  call    cs:__imp_GetClassInfoExW
0x1800f731d  test    eax, eax
0x1800f731f  jnz     short loc_1800F7393
0x1800f7321  lea     ebx, [rax+50h]
0x1800f7324  xor     edx, edx; Val
0x1800f7326  mov     r8d, ebx; Size
0x1800f7329  lea     rcx, [rbp+50h+wcx]; void *
0x1800f732d  call    memset_0
0x1800f7332  mov     eax, [rsp+150h+var_F0]
0x1800f7336  xor     ecx, ecx; lpModuleName
0x1800f7338  mov     [rbp+50h+wcx.style], eax
0x1800f733b  mov     [rbp+50h+wcx.cbSize], ebx
0x1800f733e  call    cs:__imp_GetModuleHandleW
0x1800f7344  mov     edx, 7F00h; lpCursorName
0x1800f7349  xor     ecx, ecx; hInstance
0x1800f734b  mov     [rbp+50h+wcx.hInstance], rax
0x1800f734f  call    cs:__imp_LoadCursorW
0x1800f7355  xor     ecx, ecx; i
0x1800f7357  mov     [rbp+50h+wcx.hCursor], rax
0x1800f735b  call    cs:__imp_GetStockObject
0x1800f7361  lea     rcx, [rbp+50h+wcx]; WNDCLASSEXW *
0x1800f7365  mov     [rbp+50h+wcx.cbWndExtra], 8
0x1800f736c  mov     [rbp+50h+wcx.hbrBackground], rax
0x1800f7370  mov     rax, [rsp+150h+lpszClass]
0x1800f7375  mov     [rbp+50h+wcx.lpszClassName], rax
0x1800f7379  mov     rax, cs:__imp_DefWindowProcW
0x1800f7380  mov     [rbp+50h+wcx.lpfnWndProc], rax
0x1800f7384  call    cs:__imp_RegisterClassExW
0x1800f738a  test    ax, ax
0x1800f738d  jz      loc_1800F7298
0x1800f7393  xor     ecx, ecx; lpModuleName
0x1800f7395  call    cs:__imp_GetModuleHandleW
0x1800f739b  mov     rdx, [rsp+150h+lpszClass]; lpClassName
0x1800f73a0  mov     r9d, 46000000h; dwStyle
0x1800f73a6  mov     [rsp+150h+lpParam], r12; lpParam
0x1800f73ab  xor     r8d, r8d; lpWindowName
0x1800f73ae  mov     [rsp+150h+hInstance], rax; hInstance
0x1800f73b3  xor     ecx, ecx; dwExStyle
0x1800f73b5  mov     [rsp+150h+hMenu], r12; hMenu
0x1800f73ba  mov     [rsp+150h+hWndParent], rdi; hWndParent
0x1800f73bf  mov     [rsp+150h+nHeight], r12d; nHeight
0x1800f73c4  mov     [rsp+150h+nWidth], r12d; nWidth
0x1800f73c9  mov     [rsp+150h+Y], r12d; Y
0x1800f73ce  mov     [rsp+150h+X], r12d; X
0x1800f73d3  call    cs:__imp_CreateWindowExW
0x1800f73d9  mov     [rsi+0C8h], rax
0x1800f73e0  test    rax, rax
0x1800f73e3  jz      loc_1800F7298
0x1800f73e9  lea     r8, ?StaticWndProc@HWNDElement@DirectUI@@SA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x1800f73f0  mov     edx, 0FFFFFFFCh; nIndex
0x1800f73f5  mov     rcx, rax; hWnd
0x1800f73f8  call    cs:__imp_SetWindowLongPtrW
0x1800f73fe  mov     rcx, [rsi+0C8h]; hWnd
0x1800f7405  mov     r8, rsi; dwNewLong
0x1800f7408  xor     edx, edx; nIndex
0x1800f740a  call    cs:__imp_SetWindowLongPtrW
0x1800f7410  xor     r9d, r9d; lParam
0x1800f7413  xor     r8d, r8d; wParam
0x1800f7416  mov     edx, 129h; Msg
0x1800f741b  mov     rcx, rdi; hWnd
0x1800f741e  call    cs:__imp_SendMessageW
0x1800f7424  mov     rcx, [rsi+0C8h]; hWnd
0x1800f742b  mov     ebx, 0FFFFFFECh
0x1800f7430  mov     edx, ebx; nIndex
0x1800f7432  mov     [rsi+0E2h], ax
0x1800f7439  call    cs:__imp_GetWindowLongPtrW
0x1800f743f  mov     rdi, 0FFFFFFFFFFBFFFFFh
0x1800f7446  bt      rax, 16h
0x1800f744b  jnb     short loc_1800F747C
0x1800f744d  mov     rcx, [rsi+0C8h]; hWnd
0x1800f7454  mov     edx, ebx; nIndex
0x1800f7456  call    cs:__imp_GetWindowLongPtrW
0x1800f745c  mov     rcx, [rsi+0C8h]; hWnd
0x1800f7463  mov     edx, ebx; nIndex
0x1800f7465  and     rax, rdi
0x1800f7468  mov     r8, rax; dwNewLong
0x1800f746b  call    cs:__imp_SetWindowLongPtrW
0x1800f7471  mov     edx, r13d; int
0x1800f7474  mov     rcx, rsi; this
0x1800f7477  call    ?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x1800f747c  mov     eax, cs:?g_RTLOS@DirectUI@@3HA; int DirectUI::g_RTLOS
0x1800f7482  cmp     eax, 0FFFFFFFFh
0x1800f7485  jnz     short loc_1800F74DE
0x1800f7487  test    r14b, 4
0x1800f748b  jz      short loc_1800F7495
0x1800f748d  call    cs:__imp_GetThreadUILanguage
0x1800f7493  jmp     short loc_1800F749B
0x1800f7495  call    cs:__imp_GetUserDefaultUILanguage
0x1800f749b  mov     cs:?g_RTLOS@DirectUI@@3HA, r12d; int DirectUI::g_RTLOS
0x1800f74a2  test    ax, ax
0x1800f74a5  jz      short loc_1800F7512
0x1800f74a7  mov     r9d, 10h; cchData
0x1800f74ad  movzx   ecx, ax; Locale
0x1800f74b0  lea     r8, [rbp+50h+LCData]; lpLCData
0x1800f74b4  lea     edx, [r9+48h]; LCType
0x1800f74b8  call    cs:__imp_GetLocaleInfoW
0x1800f74be  test    eax, eax
0x1800f74c0  jz      short loc_1800F74D8
0x1800f74c2  mov     eax, 800h
0x1800f74c7  test    [rbp+50h+var_52], ax
0x1800f74cb  jz      short loc_1800F74D8
0x1800f74cd  mov     eax, r13d
0x1800f74d0  mov     cs:?g_RTLOS@DirectUI@@3HA, eax; int DirectUI::g_RTLOS
0x1800f74d6  jmp     short loc_1800F74DE
0x1800f74d8  mov     eax, cs:?g_RTLOS@DirectUI@@3HA; int DirectUI::g_RTLOS
0x1800f74de  cmp     eax, r13d
0x1800f74e1  jnz     short loc_1800F7512
0x1800f74e3  mov     edx, r13d; int
0x1800f74e6  mov     rcx, rsi; this
0x1800f74e9  call    ?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x1800f74ee  mov     rcx, [rsi+0C8h]; hWnd
0x1800f74f5  mov     edx, ebx; nIndex
0x1800f74f7  call    cs:__imp_GetWindowLongPtrW
0x1800f74fd  mov     rcx, [rsi+0C8h]; hWnd
0x1800f7504  mov     edx, ebx; nIndex
0x1800f7506  and     rax, rdi
0x1800f7509  mov     r8, rax; dwNewLong
0x1800f750c  call    cs:__imp_SetWindowLongPtrW
0x1800f7512  mov     rcx, [rsi+0C8h]
0x1800f7519  lea     r8, ?_DisplayNodeCallback@Element@DirectUI@@SAJPEAUHGADGET__@@PEAXPEAUEventMsg@@@Z; DirectUI::Element::_DisplayNodeCallback(HGADGET__ *,void *,EventMsg *)
0x1800f7520  mov     r9, rsi
0x1800f7523  mov     edx, r13d
0x1800f7526  call    cs:__imp_CreateGadget
0x1800f752c  mov     [rsi+8], rax
0x1800f7530  test    rax, rax
0x1800f7533  jnz     short loc_1800F7542
0x1800f7535  call    cs:__imp_GetLastError
0x1800f753b  mov     ebx, eax
0x1800f753d  jmp     loc_1800F729D
0x1800f7542  mov     r9d, 0FFh
0x1800f7548  xor     edx, edx
0x1800f754a  mov     rcx, rax
0x1800f754d  lea     r8d, [r9-62h]
0x1800f7551  call    cs:__imp_SetGadgetMessageFilter
0x1800f7557  mov     rcx, [rsi+8]
0x1800f755b  mov     edx, r15d
0x1800f755e  shl     edx, 3
0x1800f7561  mov     r8d, 0E2Bh
0x1800f7567  or      edx, 801h
0x1800f756d  call    cs:__imp_SetGadgetStyle
0x1800f7573  call    IsPalette
0x1800f7578  test    al, al
0x1800f757a  jz      short loc_1800F75DD
0x1800f757c  mov     rax, [rsi]
0x1800f757f  mov     rcx, rsi
0x1800f7582  mov     rax, [rax+168h]
0x1800f7589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f758e  mov     rcx, rax
0x1800f7591  mov     rbx, rax
0x1800f7594  call    cs:__imp_IsWindowGdiScaled
0x1800f759a  neg     eax
0x1800f759c  sbb     rdi, rdi
0x1800f759f  and     rdi, rbx
0x1800f75a2  mov     rcx, rdi; hWnd
0x1800f75a5  call    cs:__imp_GetDC
0x1800f75ab  mov     rcx, rax; hdc
0x1800f75ae  mov     rbx, rax
0x1800f75b1  call    cs:__imp_CreateHalftonePalette
0x1800f75b7  mov     rdx, rbx; hDC
0x1800f75ba  mov     rcx, rdi; hWnd
0x1800f75bd  mov     [rsi+0D8h], rax
0x1800f75c4  call    cs:__imp_ReleaseDC
0x1800f75ca  cmp     [rsi+0D8h], r12
0x1800f75d1  jnz     short loc_1800F75DD
0x1800f75d3  mov     ebx, 80040002h
0x1800f75d8  jmp     loc_1800F729D
0x1800f75dd  mov     rax, [rsi+0D8h]
0x1800f75e4  xorps   xmm0, xmm0
0x1800f75e7  mov     [rsp+150h+var_DC], r12
0x1800f75ec  mov     ecx, 6
0x1800f75f1  mov     dword ptr [rsp+150h+var_DC], ecx
0x1800f75f5  mov     [rbp+50h+var_B8], rax
0x1800f75f9  mov     [rbp+50h+var_C0], r12
0x1800f75fd  mov     [rsp+150h+var_E0], 30h ; '0'
0x1800f7605  mov     [rsp+150h+var_D4], r12d
0x1800f760a  movdqu  [rbp+50h+var_D0], xmm0
0x1800f760f  test    r14b, 8
0x1800f7613  jz      short loc_1800F7622
0x1800f7615  mov     ecx, 16h
0x1800f761a  mov     dword ptr [rbp+50h+var_D0+4], r13d
0x1800f761e  mov     dword ptr [rsp+150h+var_DC], ecx
0x1800f7622  test    r14b, 10h
0x1800f7626  jz      short loc_1800F7633
0x1800f7628  or      ecx, 20h
0x1800f762b  mov     dword ptr [rbp+50h+var_D0+8], r13d
0x1800f762f  mov     dword ptr [rsp+150h+var_DC], ecx
0x1800f7633  test    r14b, 20h
0x1800f7637  jz      short loc_1800F7644
0x1800f7639  or      ecx, 40h
0x1800f763c  mov     dword ptr [rbp+50h+var_D0+0Ch], r13d
0x1800f7640  mov     dword ptr [rsp+150h+var_DC], ecx
0x1800f7644  mov     edx, 80h
0x1800f7649  test    r14b, 40h
0x1800f764d  jz      short loc_1800F7659
0x1800f764f  or      ecx, edx
0x1800f7651  mov     dword ptr [rbp+50h+var_C0], r13d
0x1800f7655  mov     dword ptr [rsp+150h+var_DC], ecx
0x1800f7659  and     r14d, edx
0x1800f765c  test    r14b, r14b
0x1800f765f  jz      short loc_1800F766D
0x1800f7661  bts     ecx, 8
0x1800f7665  mov     dword ptr [rbp+50h+var_C0+4], r13d
0x1800f7669  mov     dword ptr [rsp+150h+var_DC], ecx
0x1800f766d  mov     rcx, [rsi+8]
0x1800f7671  lea     rdx, [rsp+150h+var_E0]
0x1800f7676  call    cs:__imp_SetGadgetRootInfo
0x1800f767c  or      byte ptr [rsi+97h], 8
0x1800f7683  mov     edx, 0Ah; int
0x1800f7688  mov     rcx, rsi; this
0x1800f768b  call    ?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x1800f7690  call    ?GetScalingMode@DirectUI@@YA?AW4THREAD_SCALING_MODE@1@XZ; DirectUI::GetScalingMode(void)
0x1800f7695  cmp     eax, 4
0x1800f7698  jnz     short loc_1800F76C9
0x1800f769a  lea     r9, unk_1801F0D00; struct DirectUI::Value *
  ... truncated ...
```
