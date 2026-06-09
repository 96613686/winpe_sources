# DirectUI::HWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)

- ea: `0x180447454`
- end: `0x180447950`
- name: `?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z`
- size: `1276`
- prototype: `__int64 __usercall@<rax>(DirectUI::HWNDElement *__hidden this@<rcx>, HWND hWnd@<rdx>, bool@<r8b>, unsigned int@<r9d>, struct DirectUI::Element *, unsigned int *)`
- caller_count: `15`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180294990`
- `0x1802aad40`
- `0x1802b3394`
- `0x1802da370`
- `0x1802eed44`
- `0x1802eedfc`
- `0x1802fb468`
- `0x180333920`
- `0x1803349d0`
- `0x180337590`
- `0x180339e80`
- `0x180389abc`
- `0x1803cafec`
- `0x1803ddf08`
- `0x18047bf38`

## callees

- `0x18001bfa4`
- `0x18001efd8`
- `0x18005e7f0`
- `0x18006fb00`
- `0x1800baeac`
- `0x1802b7f90`
- `0x180445618`
- `0x180447454`
- `0x180448944`
- `0x180459c28`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetThreadUILanguage` at `0x18044772c`
- `KERNEL32!GetThreadUILanguage` at `0x18044772c`
- `KERNEL32!GetLocaleInfoW` at `0x180447757`
- `KERNEL32!GetLocaleInfoW` at `0x180447757`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180447734`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180447734`
- `KERNEL32!GetModuleHandleW` at `0x1804475a8`
- `KERNEL32!GetModuleHandleW` at `0x1804475dd`
- `KERNEL32!GetModuleHandleW` at `0x180447634`
- `KERNEL32!GetModuleHandleW` at `0x1804475a8`
- `KERNEL32!GetModuleHandleW` at `0x1804475dd`
- `KERNEL32!GetModuleHandleW` at `0x180447634`
- `KERNEL32!GetLastError` at `0x1804477d4`
- `KERNEL32!GetLastError` at `0x1804477d4`
- `GDI32!CreateHalftonePalette` at `0x180447833`
- `GDI32!CreateHalftonePalette` at `0x180447833`
- `GDI32!DeleteObject` at `0x180447570`
- `GDI32!DeleteObject` at `0x180447570`
- `GDI32!GetStockObject` at `0x1804475fa`
- `GDI32!GetStockObject` at `0x1804475fa`
- `USER32!DestroyWindow` at `0x180447557`
- `USER32!DestroyWindow` at `0x180447557`
- `USER32!RegisterClassExW` at `0x180447623`
- `USER32!RegisterClassExW` at `0x180447623`
- `USER32!GetClassInfoExW` at `0x1804475b8`
- `USER32!GetClassInfoExW` at `0x1804475b8`
- `USER32!SendMessageW` at `0x1804476bd`
- `USER32!SendMessageW` at `0x1804476bd`
- `USER32!ReleaseDC` at `0x180447845`
- `USER32!ReleaseDC` at `0x180447845`
- `USER32!GetDC` at `0x180447827`
- `USER32!GetDC` at `0x180447827`
- `USER32!CreateWindowExW` at `0x180447672`
- `USER32!CreateWindowExW` at `0x180447672`
- `USER32!DefWindowProcW` at `0x180447618`
- `USER32!LoadCursorW` at `0x1804475ee`
- `USER32!LoadCursorW` at `0x1804475ee`
- `USER32!GetWindowLongPtrW` at `0x1804476d8`
- `USER32!GetWindowLongPtrW` at `0x1804476f5`
- `USER32!GetWindowLongPtrW` at `0x180447796`
- `USER32!GetWindowLongPtrW` at `0x1804476d8`
- `USER32!GetWindowLongPtrW` at `0x1804476f5`
- `USER32!GetWindowLongPtrW` at `0x180447796`
- `USER32!SetWindowLongPtrW` at `0x180447697`
- `USER32!SetWindowLongPtrW` at `0x1804476a9`
- `USER32!SetWindowLongPtrW` at `0x18044770a`
- `USER32!SetWindowLongPtrW` at `0x1804477ab`
- `USER32!SetWindowLongPtrW` at `0x180447697`
- `USER32!SetWindowLongPtrW` at `0x1804476a9`
- `USER32!SetWindowLongPtrW` at `0x18044770a`
- `USER32!SetWindowLongPtrW` at `0x1804477ab`
- `IEUI!DisableContainerHwnd` at `0x180447545`
- `IEUI!DisableContainerHwnd` at `0x180447545`
- `IEUI!SetGadgetRootInfo` at `0x1804478f6`
- `IEUI!SetGadgetRootInfo` at `0x1804478f6`
- `IEUI!SetGadgetMessageFilter` at `0x1804477f0`
- `IEUI!SetGadgetMessageFilter` at `0x1804477f0`
- `IEUI!CreateGadget` at `0x1804477c5`
- `IEUI!CreateGadget` at `0x1804477c5`

## pseudocode

```c
__int64 __fastcall DirectUI::HWNDElement::Initialize(
        DirectUI::HWNDElement *this,
        HWND hWnd,
        __int64 a3,
        int a4,
        struct DirectUI::Element *a5,
        unsigned int *a6)
{
  signed int LastError; // ebx
  __int64 v10; // rax
  const WCHAR *v11; // rbx
  HWND v12; // rcx
  void *v13; // rcx
  HMODULE ModuleHandleW; // rax
  HBRUSH StockObject; // rax
  HMODULE hInstance; // rax
  HWND Window; // rax
  __int16 v19; // ax
  HWND v20; // rcx
  LONG_PTR WindowLongPtrW; // rax
  int v22; // eax
  LANGID ThreadUILanguage; // ax
  LONG_PTR v24; // rax
  __int64 Gadget; // rax
  HDC DC; // rbx
  __int64 v27; // rax
  int v28; // ecx
  int v29; // r8d
  UINT v30; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszClass; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+74h] [rbp-8Ch]
  int v34; // [rsp+7Ch] [rbp-84h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  struct tagWNDCLASSEXW wcx; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR LCData[16]; // [rsp+F0h] [rbp-10h] BYREF

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
  v10 = *(_QWORD *)this;
  wcx.cbSize = 80;
  lpszClass = 0;
  v30 = 0x4000;
  (*(void (__fastcall **)(DirectUI::HWNDElement *, LPCWSTR *, UINT *))(v10 + 456))(this, &lpszClass, &v30);
  v11 = lpszClass;
  if ( !lpszClass )
    goto LABEL_3;
  ModuleHandleW = GetModuleHandleW(0);
  if ( !GetClassInfoExW(ModuleHandleW, v11, &wcx) )
  {
    memset_0(&wcx, 0, sizeof(wcx));
    wcx.style = v30;
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
    v12 = (HWND)*((_QWORD *)this + 25);
    if ( v12 )
    {
      DestroyWindow(v12);
      *((_QWORD *)this + 25) = 0;
    }
    v13 = (void *)*((_QWORD *)this + 27);
    if ( v13 )
    {
      DeleteObject(v13);
      *((_QWORD *)this + 27) = 0;
    }
    return (unsigned int)LastError;
  }
  SetWindowLongPtrW(Window, -4, (LONG_PTR)DirectUI::HWNDElement::StaticWndProc);
  SetWindowLongPtrW(*((HWND *)this + 25), 0, (LONG_PTR)this);
  v19 = SendMessageW(hWnd, 0x129u, 0, 0);
  v20 = (HWND)*((_QWORD *)this + 25);
  *((_WORD *)this + 113) = v19;
  if ( (GetWindowLongPtrW(v20, -20) & 0x400000) != 0 )
  {
    WindowLongPtrW = GetWindowLongPtrW(*((HWND *)this + 25), -20);
    SetWindowLongPtrW(*((HWND *)this + 25), -20, WindowLongPtrW & 0xFFFFFFFFFFBFFFFFuLL);
    DirectUI::Element::SetDirection(this, 1);
  }
  v22 = DirectUI::g_RTLOS;
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
      v22 = 1;
      DirectUI::g_RTLOS = 1;
    }
    else
    {
      v22 = DirectUI::g_RTLOS;
    }
  }
  if ( v22 == 1 )
  {
    DirectUI::Element::SetDirection(this, 1);
    v24 = GetWindowLongPtrW(*((HWND *)this + 25), -20);
    SetWindowLongPtrW(*((HWND *)this + 25), -20, v24 & 0xFFFFFFFFFFBFFFFFuLL);
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
  SetGadgetStyle_0(*((_QWORD *)this + 1), 2057, 3627);
  if ( (unsigned __int8)IsPalette() )
  {
    (*(void (__fastcall **)(DirectUI::HWNDElement *))(*(_QWORD *)this + 360LL))(this);
    DC = GetDC(0);
    *((_QWORD *)this + 27) = CreateHalftonePalette(DC);
    ReleaseDC(0, DC);
    if ( !*((_QWORD *)this + 27) )
    {
      LastError = -2147221502;
      goto LABEL_4;
    }
  }
  v27 = *((_QWORD *)this + 27);
  v28 = 6;
  v33 = 6;
  v37 = v27;
  v36 = 0;
  v32 = 48;
  v34 = 0;
  v35 = 0;
  if ( (a4 & 8) != 0 )
  {
    v28 = 22;
    DWORD1(v35) = 1;
    LODWORD(v33) = 22;
  }
  if ( (a4 & 0x10) != 0 )
  {
    v28 |= 0x20u;
    DWORD2(v35) = 1;
    LODWORD(v33) = v28;
  }
  if ( (a4 & 0x20) != 0 )
  {
    v28 |= 0x40u;
    HIDWORD(v35) = 1;
    LODWORD(v33) = v28;
  }
  if ( (a4 & 0x40) != 0 )
  {
    v28 |= 0x80u;
    LODWORD(v36) = 1;
    LODWORD(v33) = v28;
  }
  if ( (a4 & 0x80) != 0 )
  {
    HIDWORD(v36) = 1;
    LODWORD(v33) = v28 | 0x100;
  }
  SetGadgetRootInfo(*((_QWORD *)this + 1), &v32);
  *((_BYTE *)this + 151) |= 8u;
  DirectUI::Element::SetAccRole(this, 10);
  if ( (unsigned int)DirectUI::GetScalingMode() == 4 )
  {
    DirectUI::Element::_SetValue(
      this,
      (const struct DirectUI::PropertyInfo *)&off_180585170,
      v29,
      (struct DirectUI::Value *)qword_1805CA838,
      0);
    DirectUI::Value::Release((DirectUI::Value *)qword_1805CA838);
    DirectUI::HWNDElement::_UpdateDesktopScaleFactor(this);
  }
  return 0;
}

```

## disassembly

```asm
0x180447454  mov     [rsp-8+arg_10], rbx
0x180447459  push    rbp
0x18044745a  push    rsi
0x18044745b  push    rdi
0x18044745c  push    r12
0x18044745e  push    r13
0x180447460  push    r14
0x180447462  push    r15
0x180447464  lea     rbp, [rsp-20h]
0x180447469  sub     rsp, 120h
0x180447470  mov     rax, cs:__security_cookie
0x180447477  xor     rax, rsp
0x18044747a  mov     [rbp+50h+var_40], rax
0x18044747e  mov     rbx, [rbp+50h+arg_28]
0x180447485  xor     r15d, r15d
0x180447488  mov     r14, rdx
0x18044748b  mov     [rcx+0C8h], r15
0x180447492  mov     rdi, rcx
0x180447495  mov     [rcx+8], r15
0x180447499  mov     [rcx+0D8h], r15
0x1804474a0  xor     edx, edx; Val
0x1804474a2  mov     [rcx+0E2h], r15w
0x1804474aa  lea     r13d, [r15+50h]
0x1804474ae  mov     r8d, r13d; Size
0x1804474b1  lea     rcx, [rbp+50h+wcx]; void *
0x1804474b5  mov     esi, r9d
0x1804474b8  call    memset_0
0x1804474bd  mov     r8, [rbp+50h+arg_20]; struct DirectUI::Element *
0x1804474c4  lea     r12d, [r15+1]
0x1804474c8  mov     edx, esi
0x1804474ca  mov     [rdi+0E8h], r15
0x1804474d1  or      edx, r12d; unsigned int
0x1804474d4  mov     [rdi+0D0h], r15
0x1804474db  mov     r9, rbx; unsigned int *
0x1804474de  mov     [rdi+0F0h], r15
0x1804474e5  mov     rcx, rdi; this
0x1804474e8  mov     [rdi+0F8h], r15w
0x1804474f0  mov     [rdi+0FCh], r15d
0x1804474f7  call    ?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x1804474fc  mov     ebx, eax
0x1804474fe  test    eax, eax
0x180447500  js      short loc_18044753E
0x180447502  mov     rax, [rdi]
0x180447505  lea     r8, [rsp+150h+var_F0]
0x18044750a  lea     rdx, [rsp+150h+lpszClass]
0x18044750f  mov     [rbp+50h+wcx.cbSize], r13d
0x180447513  mov     rcx, rdi
0x180447516  mov     [rsp+150h+lpszClass], r15
0x18044751b  mov     [rsp+150h+var_F0], 4000h
0x180447523  mov     rax, [rax+1C8h]
0x18044752a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044752f  mov     rbx, [rsp+150h+lpszClass]
0x180447534  test    rbx, rbx
0x180447537  jnz     short loc_1804475A6
0x180447539  mov     ebx, 800403E9h
0x18044753e  mov     rcx, [rdi+0C8h]
0x180447545  call    cs:__imp_DisableContainerHwnd
0x18044754b  mov     rcx, [rdi+0C8h]; hWnd
0x180447552  test    rcx, rcx
0x180447555  jz      short loc_180447564
0x180447557  call    cs:__imp_DestroyWindow
0x18044755d  mov     [rdi+0C8h], r15
0x180447564  mov     rcx, [rdi+0D8h]; ho
0x18044756b  test    rcx, rcx
0x18044756e  jz      short loc_18044757D
0x180447570  call    cs:__imp_DeleteObject
0x180447576  mov     [rdi+0D8h], r15
0x18044757d  mov     eax, ebx
0x18044757f  mov     rcx, [rbp+50h+var_40]
0x180447583  xor     rcx, rsp; StackCookie
0x180447586  call    __security_check_cookie
0x18044758b  mov     rbx, [rsp+150h+arg_10]
0x180447593  add     rsp, 120h
0x18044759a  pop     r15
0x18044759c  pop     r14
0x18044759e  pop     r13
0x1804475a0  pop     r12
0x1804475a2  pop     rdi
0x1804475a3  pop     rsi
0x1804475a4  pop     rbp
0x1804475a5  retn
0x1804475a6  xor     ecx, ecx; lpModuleName
0x1804475a8  call    cs:__imp_GetModuleHandleW
0x1804475ae  lea     r8, [rbp+50h+wcx]; lpwcx
0x1804475b2  mov     rdx, rbx; lpszClass
0x1804475b5  mov     rcx, rax; hInstance
0x1804475b8  call    cs:__imp_GetClassInfoExW
0x1804475be  test    eax, eax
0x1804475c0  jnz     short loc_180447632
0x1804475c2  mov     r8, r13; Size
0x1804475c5  lea     rcx, [rbp+50h+wcx]; void *
0x1804475c9  xor     edx, edx; Val
0x1804475cb  call    memset_0
0x1804475d0  mov     eax, [rsp+150h+var_F0]
0x1804475d4  xor     ecx, ecx; lpModuleName
0x1804475d6  mov     [rbp+50h+wcx.style], eax
0x1804475d9  mov     [rbp+50h+wcx.cbSize], r13d
0x1804475dd  call    cs:__imp_GetModuleHandleW
0x1804475e3  mov     edx, 7F00h; lpCursorName
0x1804475e8  xor     ecx, ecx; hInstance
0x1804475ea  mov     [rbp+50h+wcx.hInstance], rax
0x1804475ee  call    cs:__imp_LoadCursorW
0x1804475f4  xor     ecx, ecx; i
0x1804475f6  mov     [rbp+50h+wcx.hCursor], rax
0x1804475fa  call    cs:__imp_GetStockObject
0x180447600  lea     rcx, [rbp+50h+wcx]; WNDCLASSEXW *
0x180447604  mov     [rbp+50h+wcx.cbWndExtra], 8
0x18044760b  mov     [rbp+50h+wcx.hbrBackground], rax
0x18044760f  mov     rax, [rsp+150h+lpszClass]
0x180447614  mov     [rbp+50h+wcx.lpszClassName], rax
0x180447618  mov     rax, cs:__imp_DefWindowProcW
0x18044761f  mov     [rbp+50h+wcx.lpfnWndProc], rax
0x180447623  call    cs:__imp_RegisterClassExW
0x180447629  test    ax, ax
0x18044762c  jz      loc_180447539
0x180447632  xor     ecx, ecx; lpModuleName
0x180447634  call    cs:__imp_GetModuleHandleW
0x18044763a  mov     rdx, [rsp+150h+lpszClass]; lpClassName
0x18044763f  mov     r9d, 46000000h; dwStyle
0x180447645  mov     [rsp+150h+lpParam], r15; lpParam
0x18044764a  xor     r8d, r8d; lpWindowName
0x18044764d  mov     [rsp+150h+hInstance], rax; hInstance
0x180447652  xor     ecx, ecx; dwExStyle
0x180447654  mov     [rsp+150h+hMenu], r15; hMenu
0x180447659  mov     [rsp+150h+hWndParent], r14; hWndParent
0x18044765e  mov     [rsp+150h+nHeight], r15d; nHeight
0x180447663  mov     [rsp+150h+nWidth], r15d; nWidth
0x180447668  mov     [rsp+150h+Y], r15d; Y
0x18044766d  mov     [rsp+150h+X], r15d; X
0x180447672  call    cs:__imp_CreateWindowExW
0x180447678  mov     [rdi+0C8h], rax
0x18044767f  test    rax, rax
0x180447682  jz      loc_180447539
0x180447688  lea     r8, ?StaticWndProc@HWNDElement@DirectUI@@SA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x18044768f  mov     edx, 0FFFFFFFCh; nIndex
0x180447694  mov     rcx, rax; hWnd
0x180447697  call    cs:__imp_SetWindowLongPtrW
0x18044769d  mov     rcx, [rdi+0C8h]; hWnd
0x1804476a4  mov     r8, rdi; dwNewLong
0x1804476a7  xor     edx, edx; nIndex
0x1804476a9  call    cs:__imp_SetWindowLongPtrW
0x1804476af  xor     r9d, r9d; lParam
0x1804476b2  xor     r8d, r8d; wParam
0x1804476b5  mov     edx, 129h; Msg
0x1804476ba  mov     rcx, r14; hWnd
0x1804476bd  call    cs:__imp_SendMessageW
0x1804476c3  mov     rcx, [rdi+0C8h]; hWnd
0x1804476ca  mov     ebx, 0FFFFFFECh
0x1804476cf  mov     edx, ebx; nIndex
0x1804476d1  mov     [rdi+0E2h], ax
0x1804476d8  call    cs:__imp_GetWindowLongPtrW
0x1804476de  mov     r14, 0FFFFFFFFFFBFFFFFh
0x1804476e5  bt      rax, 16h
0x1804476ea  jnb     short loc_18044771B
0x1804476ec  mov     rcx, [rdi+0C8h]; hWnd
0x1804476f3  mov     edx, ebx; nIndex
0x1804476f5  call    cs:__imp_GetWindowLongPtrW
0x1804476fb  mov     rcx, [rdi+0C8h]; hWnd
0x180447702  mov     edx, ebx; nIndex
0x180447704  and     rax, r14
0x180447707  mov     r8, rax; dwNewLong
0x18044770a  call    cs:__imp_SetWindowLongPtrW
0x180447710  mov     edx, r12d; int
0x180447713  mov     rcx, rdi; this
0x180447716  call    ?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x18044771b  mov     eax, cs:?g_RTLOS@DirectUI@@3HA; int DirectUI::g_RTLOS
0x180447721  cmp     eax, 0FFFFFFFFh
0x180447724  jnz     short loc_18044777D
0x180447726  test    sil, 4
0x18044772a  jz      short loc_180447734
0x18044772c  call    cs:__imp_GetThreadUILanguage
0x180447732  jmp     short loc_18044773A
0x180447734  call    cs:__imp_GetUserDefaultUILanguage
0x18044773a  mov     cs:?g_RTLOS@DirectUI@@3HA, r15d; int DirectUI::g_RTLOS
0x180447741  test    ax, ax
0x180447744  jz      short loc_1804477B1
0x180447746  mov     r9d, 10h; cchData
0x18044774c  movzx   ecx, ax; Locale
0x18044774f  lea     r8, [rbp+50h+LCData]; lpLCData
0x180447753  lea     edx, [r9+48h]; LCType
0x180447757  call    cs:__imp_GetLocaleInfoW
0x18044775d  test    eax, eax
0x18044775f  jz      short loc_180447777
0x180447761  mov     eax, 800h
0x180447766  test    [rbp+50h+var_52], ax
0x18044776a  jz      short loc_180447777
0x18044776c  mov     eax, r12d
0x18044776f  mov     cs:?g_RTLOS@DirectUI@@3HA, eax; int DirectUI::g_RTLOS
0x180447775  jmp     short loc_18044777D
0x180447777  mov     eax, cs:?g_RTLOS@DirectUI@@3HA; int DirectUI::g_RTLOS
0x18044777d  cmp     eax, r12d
0x180447780  jnz     short loc_1804477B1
0x180447782  mov     edx, r12d; int
0x180447785  mov     rcx, rdi; this
0x180447788  call    ?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x18044778d  mov     rcx, [rdi+0C8h]; hWnd
0x180447794  mov     edx, ebx; nIndex
0x180447796  call    cs:__imp_GetWindowLongPtrW
0x18044779c  mov     rcx, [rdi+0C8h]; hWnd
0x1804477a3  mov     edx, ebx; nIndex
0x1804477a5  and     rax, r14
0x1804477a8  mov     r8, rax; dwNewLong
0x1804477ab  call    cs:__imp_SetWindowLongPtrW
0x1804477b1  mov     rcx, [rdi+0C8h]
0x1804477b8  lea     r8, ?_DisplayNodeCallback@Element@DirectUI@@SAJPEAUHGADGET__@@PEAXPEAUEventMsg@@@Z; DirectUI::Element::_DisplayNodeCallback(HGADGET__ *,void *,EventMsg *)
0x1804477bf  mov     r9, rdi
0x1804477c2  mov     edx, r12d
0x1804477c5  call    cs:__imp_CreateGadget
0x1804477cb  mov     [rdi+8], rax
0x1804477cf  test    rax, rax
0x1804477d2  jnz     short loc_1804477E1
0x1804477d4  call    cs:__imp_GetLastError
0x1804477da  mov     ebx, eax
0x1804477dc  jmp     loc_18044753E
0x1804477e1  mov     r9d, 0FFh
0x1804477e7  xor     edx, edx
0x1804477e9  mov     rcx, rax
0x1804477ec  lea     r8d, [r9-62h]
0x1804477f0  call    cs:__imp_SetGadgetMessageFilter
0x1804477f6  mov     rcx, [rdi+8]
0x1804477fa  mov     edx, 809h
0x1804477ff  mov     r8d, 0E2Bh
0x180447805  call    SetGadgetStyle_0
0x18044780a  call    IsPalette
0x18044780f  test    al, al
0x180447811  jz      short loc_18044785E
0x180447813  mov     rax, [rdi]
0x180447816  mov     rcx, rdi
0x180447819  mov     rax, [rax+168h]
0x180447820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180447825  xor     ecx, ecx; hWnd
0x180447827  call    cs:__imp_GetDC
0x18044782d  mov     rcx, rax; hdc
0x180447830  mov     rbx, rax
0x180447833  call    cs:__imp_CreateHalftonePalette
0x180447839  mov     rdx, rbx; hDC
0x18044783c  xor     ecx, ecx; hWnd
0x18044783e  mov     [rdi+0D8h], rax
0x180447845  call    cs:__imp_ReleaseDC
0x18044784b  cmp     [rdi+0D8h], r15
0x180447852  jnz     short loc_18044785E
0x180447854  mov     ebx, 80040002h
0x180447859  jmp     loc_18044753E
0x18044785e  mov     rax, [rdi+0D8h]
0x180447865  xorps   xmm0, xmm0
0x180447868  mov     [rsp+150h+var_DC], r15
0x18044786d  mov     ecx, 6
0x180447872  mov     dword ptr [rsp+150h+var_DC], ecx
0x180447876  mov     [rbp+50h+var_B8], rax
0x18044787a  mov     [rbp+50h+var_C0], r15
0x18044787e  mov     [rsp+150h+var_E0], 30h ; '0'
0x180447886  mov     [rsp+150h+var_D4], r15d
0x18044788b  movdqu  [rbp+50h+var_D0], xmm0
0x180447890  test    sil, 8
0x180447894  jz      short loc_1804478A3
0x180447896  mov     ecx, 16h
0x18044789b  mov     dword ptr [rbp+50h+var_D0+4], r12d
0x18044789f  mov     dword ptr [rsp+150h+var_DC], ecx
0x1804478a3  test    sil, 10h
0x1804478a7  jz      short loc_1804478B4
0x1804478a9  or      ecx, 20h
0x1804478ac  mov     dword ptr [rbp+50h+var_D0+8], r12d
0x1804478b0  mov     dword ptr [rsp+150h+var_DC], ecx
0x1804478b4  test    sil, 20h
0x1804478b8  jz      short loc_1804478C5
0x1804478ba  or      ecx, 40h
0x1804478bd  mov     dword ptr [rbp+50h+var_D0+0Ch], r12d
0x1804478c1  mov     dword ptr [rsp+150h+var_DC], ecx
0x1804478c5  mov     edx, 80h
0x1804478ca  test    sil, 40h
0x1804478ce  jz      short loc_1804478DA
0x1804478d0  or      ecx, edx
0x1804478d2  mov     dword ptr [rbp+50h+var_C0], r12d
0x1804478d6  mov     dword ptr [rsp+150h+var_DC], ecx
0x1804478da  and     esi, edx
0x1804478dc  test    sil, sil
0x1804478df  jz      short loc_1804478ED
0x1804478e1  bts     ecx, 8
0x1804478e5  mov     dword ptr [rbp+50h+var_C0+4], r12d
0x1804478e9  mov     dword ptr [rsp+150h+var_DC], ecx
0x1804478ed  mov     rcx, [rdi+8]
0x1804478f1  lea     rdx, [rsp+150h+var_E0]
0x1804478f6  call    cs:__imp_SetGadgetRootInfo
0x1804478fc  or      byte ptr [rdi+97h], 8
0x180447903  mov     edx, 0Ah; int
0x180447908  mov     rcx, rdi; this
0x18044790b  call    ?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x180447910  call    ?GetScalingMode@DirectUI@@YA?AW4THREAD_SCALING_MODE@1@XZ; DirectUI::GetScalingMode(void)
0x180447915  cmp     eax, 4
0x180447918  jnz     short loc_180447949
0x18044791a  lea     r9, qword_1805CA838; struct DirectUI::Value *
0x180447921  mov     byte ptr [rsp+150h+X], r15b; bool
0x180447926  lea     rdx, off_180585170; struct DirectUI::PropertyInfo *
0x18044792d  mov     rcx, rdi; this
0x180447930  call    ?_SetValue@Element@DirectUI@@IEAAJPEBUPropertyInfo@2@HPEAVValue@2@_N@Z; DirectUI::Element::_SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *,bool)
0x180447935  lea     rcx, qword_1805CA838; this
0x18044793c  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180447941  mov     rcx, rdi; this
0x180447944  call    ?_UpdateDesktopScaleFactor@HWNDElement@DirectUI@@AEAAHXZ; DirectUI::HWNDElement::_UpdateDesktopScaleFactor(void)
0x180447949  xor     eax, eax
  ... truncated ...
```
