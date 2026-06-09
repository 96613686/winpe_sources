# DirectUI::HWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)

- ea: `0x180482358`
- end: `0x18048290b`
- name: `?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z`
- size: `1459`
- prototype: `__int64 __usercall@<rax>(DirectUI::HWNDElement *__hidden this@<rcx>, HWND hWnd@<rdx>, bool@<r8b>, unsigned int@<r9d>, struct DirectUI::Element *, unsigned int *)`
- caller_count: `15`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1802b7670`
- `0x1802cf5e0`
- `0x1802d7e48`
- `0x180301780`
- `0x180317294`
- `0x18031734c`
- `0x180324528`
- `0x18035fb90`
- `0x180360d60`
- `0x180363938`
- `0x180366370`
- `0x1803babfc`
- `0x1803fe76c`
- `0x180412278`
- `0x1804b83c8`

## callees

- `0x18001d728`
- `0x1800207d0`
- `0x180063760`
- `0x180074da0`
- `0x1800c1bdc`
- `0x1802dcb70`
- `0x18048042c`
- `0x180482358`
- `0x1804839d8`
- `0x18049543c`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetThreadUILanguage` at `0x18048269f`
- `KERNEL32!GetThreadUILanguage` at `0x18048269f`
- `KERNEL32!GetLocaleInfoW` at `0x1804826d6`
- `KERNEL32!GetLocaleInfoW` at `0x1804826d6`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1804826ad`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1804826ad`
- `KERNEL32!GetModuleHandleW` at `0x1804824c3`
- `KERNEL32!GetModuleHandleW` at `0x180482508`
- `KERNEL32!GetModuleHandleW` at `0x180482577`
- `KERNEL32!GetModuleHandleW` at `0x1804824c3`
- `KERNEL32!GetModuleHandleW` at `0x180482508`
- `KERNEL32!GetModuleHandleW` at `0x180482577`
- `KERNEL32!GetLastError` at `0x18048276b`
- `KERNEL32!GetLastError` at `0x18048276b`
- `GDI32!CreateHalftonePalette` at `0x1804827dc`
- `GDI32!CreateHalftonePalette` at `0x1804827dc`
- `GDI32!DeleteObject` at `0x180482484`
- `GDI32!DeleteObject` at `0x180482484`
- `GDI32!GetStockObject` at `0x180482531`
- `GDI32!GetStockObject` at `0x180482531`
- `USER32!DestroyWindow` at `0x180482465`
- `USER32!DestroyWindow` at `0x180482465`
- `USER32!RegisterClassExW` at `0x180482560`
- `USER32!RegisterClassExW` at `0x180482560`
- `USER32!GetClassInfoExW` at `0x1804824d9`
- `USER32!GetClassInfoExW` at `0x1804824d9`
- `USER32!SendMessageW` at `0x180482618`
- `USER32!SendMessageW` at `0x180482618`
- `USER32!ReleaseDC` at `0x1804827f4`
- `USER32!ReleaseDC` at `0x1804827f4`
- `USER32!GetDC` at `0x1804827ca`
- `USER32!GetDC` at `0x1804827ca`
- `USER32!CreateWindowExW` at `0x1804825bb`
- `USER32!CreateWindowExW` at `0x1804825bb`
- `USER32!DefWindowProcW` at `0x180482555`
- `USER32!LoadCursorW` at `0x18048251f`
- `USER32!LoadCursorW` at `0x18048251f`
- `USER32!GetWindowLongPtrW` at `0x180482639`
- `USER32!GetWindowLongPtrW` at `0x18048265c`
- `USER32!GetWindowLongPtrW` at `0x18048271b`
- `USER32!GetWindowLongPtrW` at `0x180482639`
- `USER32!GetWindowLongPtrW` at `0x18048265c`
- `USER32!GetWindowLongPtrW` at `0x18048271b`
- `USER32!SetWindowLongPtrW` at `0x1804825e6`
- `USER32!SetWindowLongPtrW` at `0x1804825fe`
- `USER32!SetWindowLongPtrW` at `0x180482677`
- `USER32!SetWindowLongPtrW` at `0x180482736`
- `USER32!SetWindowLongPtrW` at `0x1804825e6`
- `USER32!SetWindowLongPtrW` at `0x1804825fe`
- `USER32!SetWindowLongPtrW` at `0x180482677`
- `USER32!SetWindowLongPtrW` at `0x180482736`
- `IEUI!DisableContainerHwnd` at `0x18048244d`
- `IEUI!DisableContainerHwnd` at `0x18048244d`
- `IEUI!SetGadgetRootInfo` at `0x1804828ab`
- `IEUI!SetGadgetRootInfo` at `0x1804828ab`
- `IEUI!SetGadgetMessageFilter` at `0x18048278d`
- `IEUI!SetGadgetMessageFilter` at `0x18048278d`
- `IEUI!CreateGadget` at `0x180482756`
- `IEUI!CreateGadget` at `0x180482756`

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
      (const struct DirectUI::PropertyInfo *)&off_1805C9248,
      v29,
      (struct DirectUI::Value *)qword_18060E820,
      0);
    DirectUI::Value::Release((DirectUI::Value *)qword_18060E820);
    DirectUI::HWNDElement::_UpdateDesktopScaleFactor(this);
  }
  return 0;
}

```

## disassembly

```asm
0x180482358  mov     [rsp-8+arg_10], rbx
0x18048235d  push    rbp
0x18048235e  push    rsi
0x18048235f  push    rdi
0x180482360  push    r12
0x180482362  push    r13
0x180482364  push    r14
0x180482366  push    r15
0x180482368  lea     rbp, [rsp-20h]
0x18048236d  sub     rsp, 120h
0x180482374  mov     rax, cs:__security_cookie
0x18048237b  xor     rax, rsp
0x18048237e  mov     [rbp+50h+var_40], rax
0x180482382  mov     rbx, [rbp+50h+arg_28]
0x180482389  xor     r15d, r15d
0x18048238c  mov     r14, rdx
0x18048238f  mov     [rcx+0C8h], r15
0x180482396  mov     rdi, rcx
0x180482399  mov     [rcx+8], r15
0x18048239d  mov     [rcx+0D8h], r15
0x1804823a4  xor     edx, edx; Val
0x1804823a6  mov     [rcx+0E2h], r15w
0x1804823ae  lea     r13d, [r15+50h]
0x1804823b2  mov     r8d, r13d; Size
0x1804823b5  lea     rcx, [rbp+50h+wcx]; void *
0x1804823b9  mov     esi, r9d
0x1804823bc  call    memset_0
0x1804823c1  mov     r8, [rbp+50h+arg_20]; struct DirectUI::Element *
0x1804823c8  lea     r12d, [r15+1]
0x1804823cc  mov     edx, esi
0x1804823ce  mov     [rdi+0E8h], r15
0x1804823d5  or      edx, r12d; unsigned int
0x1804823d8  mov     [rdi+0D0h], r15
0x1804823df  mov     r9, rbx; unsigned int *
0x1804823e2  mov     [rdi+0F0h], r15
0x1804823e9  mov     rcx, rdi; this
0x1804823ec  mov     [rdi+0F8h], r15w
0x1804823f4  mov     [rdi+0FCh], r15d
0x1804823fb  call    ?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x180482400  mov     ebx, eax
0x180482402  test    eax, eax
0x180482404  js      short loc_180482446
0x180482406  mov     rax, [rdi]
0x180482409  lea     r8, [rsp+150h+var_F0]
0x18048240e  lea     rdx, [rsp+150h+lpszClass]
0x180482413  mov     [rbp+50h+wcx.cbSize], r13d
0x180482417  mov     rcx, rdi
0x18048241a  mov     [rsp+150h+lpszClass], r15
0x18048241f  mov     [rsp+150h+var_F0], 4000h
0x180482427  mov     rax, [rax+1C8h]
0x18048242e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180482433  mov     rbx, [rsp+150h+lpszClass]
0x180482438  test    rbx, rbx
0x18048243b  jnz     loc_1804824C1
0x180482441  mov     ebx, 800403E9h
0x180482446  mov     rcx, [rdi+0C8h]
0x18048244d  call    cs:__imp_DisableContainerHwnd
0x180482454  nop     dword ptr [rax+rax+00h]
0x180482459  mov     rcx, [rdi+0C8h]; hWnd
0x180482460  test    rcx, rcx
0x180482463  jz      short loc_180482478
0x180482465  call    cs:__imp_DestroyWindow
0x18048246c  nop     dword ptr [rax+rax+00h]
0x180482471  mov     [rdi+0C8h], r15
0x180482478  mov     rcx, [rdi+0D8h]; ho
0x18048247f  test    rcx, rcx
0x180482482  jz      short loc_180482497
0x180482484  call    cs:__imp_DeleteObject
0x18048248b  nop     dword ptr [rax+rax+00h]
0x180482490  mov     [rdi+0D8h], r15
0x180482497  mov     eax, ebx
0x180482499  mov     rcx, [rbp+50h+var_40]
0x18048249d  xor     rcx, rsp; StackCookie
0x1804824a0  call    __security_check_cookie
0x1804824a5  mov     rbx, [rsp+150h+arg_10]
0x1804824ad  add     rsp, 120h
0x1804824b4  pop     r15
0x1804824b6  pop     r14
0x1804824b8  pop     r13
0x1804824ba  pop     r12
0x1804824bc  pop     rdi
0x1804824bd  pop     rsi
0x1804824be  pop     rbp
0x1804824bf  retn
0x1804824c1  xor     ecx, ecx; lpModuleName
0x1804824c3  call    cs:__imp_GetModuleHandleW
0x1804824ca  nop     dword ptr [rax+rax+00h]
0x1804824cf  lea     r8, [rbp+50h+wcx]; lpwcx
0x1804824d3  mov     rdx, rbx; lpszClass
0x1804824d6  mov     rcx, rax; hInstance
0x1804824d9  call    cs:__imp_GetClassInfoExW
0x1804824e0  nop     dword ptr [rax+rax+00h]
0x1804824e5  test    eax, eax
0x1804824e7  jnz     loc_180482575
0x1804824ed  mov     r8, r13; Size
0x1804824f0  lea     rcx, [rbp+50h+wcx]; void *
0x1804824f4  xor     edx, edx; Val
0x1804824f6  call    memset_0
0x1804824fb  mov     eax, [rsp+150h+var_F0]
0x1804824ff  xor     ecx, ecx; lpModuleName
0x180482501  mov     [rbp+50h+wcx.style], eax
0x180482504  mov     [rbp+50h+wcx.cbSize], r13d
0x180482508  call    cs:__imp_GetModuleHandleW
0x18048250f  nop     dword ptr [rax+rax+00h]
0x180482514  mov     edx, 7F00h; lpCursorName
0x180482519  xor     ecx, ecx; hInstance
0x18048251b  mov     [rbp+50h+wcx.hInstance], rax
0x18048251f  call    cs:__imp_LoadCursorW
0x180482526  nop     dword ptr [rax+rax+00h]
0x18048252b  xor     ecx, ecx; i
0x18048252d  mov     [rbp+50h+wcx.hCursor], rax
0x180482531  call    cs:__imp_GetStockObject
0x180482538  nop     dword ptr [rax+rax+00h]
0x18048253d  lea     rcx, [rbp+50h+wcx]; WNDCLASSEXW *
0x180482541  mov     [rbp+50h+wcx.cbWndExtra], 8
0x180482548  mov     [rbp+50h+wcx.hbrBackground], rax
0x18048254c  mov     rax, [rsp+150h+lpszClass]
0x180482551  mov     [rbp+50h+wcx.lpszClassName], rax
0x180482555  mov     rax, cs:__imp_DefWindowProcW
0x18048255c  mov     [rbp+50h+wcx.lpfnWndProc], rax
0x180482560  call    cs:__imp_RegisterClassExW
0x180482567  nop     dword ptr [rax+rax+00h]
0x18048256c  test    ax, ax
0x18048256f  jz      loc_180482441
0x180482575  xor     ecx, ecx; lpModuleName
0x180482577  call    cs:__imp_GetModuleHandleW
0x18048257e  nop     dword ptr [rax+rax+00h]
0x180482583  mov     rdx, [rsp+150h+lpszClass]; lpClassName
0x180482588  mov     r9d, 46000000h; dwStyle
0x18048258e  mov     [rsp+150h+lpParam], r15; lpParam
0x180482593  xor     r8d, r8d; lpWindowName
0x180482596  mov     [rsp+150h+hInstance], rax; hInstance
0x18048259b  xor     ecx, ecx; dwExStyle
0x18048259d  mov     [rsp+150h+hMenu], r15; hMenu
0x1804825a2  mov     [rsp+150h+hWndParent], r14; hWndParent
0x1804825a7  mov     [rsp+150h+nHeight], r15d; nHeight
0x1804825ac  mov     [rsp+150h+nWidth], r15d; nWidth
0x1804825b1  mov     [rsp+150h+Y], r15d; Y
0x1804825b6  mov     [rsp+150h+X], r15d; X
0x1804825bb  call    cs:__imp_CreateWindowExW
0x1804825c2  nop     dword ptr [rax+rax+00h]
0x1804825c7  mov     [rdi+0C8h], rax
0x1804825ce  test    rax, rax
0x1804825d1  jz      loc_180482441
0x1804825d7  lea     r8, ?StaticWndProc@HWNDElement@DirectUI@@SA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x1804825de  mov     edx, 0FFFFFFFCh; nIndex
0x1804825e3  mov     rcx, rax; hWnd
0x1804825e6  call    cs:__imp_SetWindowLongPtrW
0x1804825ed  nop     dword ptr [rax+rax+00h]
0x1804825f2  mov     rcx, [rdi+0C8h]; hWnd
0x1804825f9  mov     r8, rdi; dwNewLong
0x1804825fc  xor     edx, edx; nIndex
0x1804825fe  call    cs:__imp_SetWindowLongPtrW
0x180482605  nop     dword ptr [rax+rax+00h]
0x18048260a  xor     r9d, r9d; lParam
0x18048260d  xor     r8d, r8d; wParam
0x180482610  mov     edx, 129h; Msg
0x180482615  mov     rcx, r14; hWnd
0x180482618  call    cs:__imp_SendMessageW
0x18048261f  nop     dword ptr [rax+rax+00h]
0x180482624  mov     rcx, [rdi+0C8h]; hWnd
0x18048262b  mov     ebx, 0FFFFFFECh
0x180482630  mov     edx, ebx; nIndex
0x180482632  mov     [rdi+0E2h], ax
0x180482639  call    cs:__imp_GetWindowLongPtrW
0x180482640  nop     dword ptr [rax+rax+00h]
0x180482645  mov     r14, 0FFFFFFFFFFBFFFFFh
0x18048264c  bt      rax, 16h
0x180482651  jnb     short loc_18048268E
0x180482653  mov     rcx, [rdi+0C8h]; hWnd
0x18048265a  mov     edx, ebx; nIndex
0x18048265c  call    cs:__imp_GetWindowLongPtrW
0x180482663  nop     dword ptr [rax+rax+00h]
0x180482668  mov     rcx, [rdi+0C8h]; hWnd
0x18048266f  mov     edx, ebx; nIndex
0x180482671  and     rax, r14
0x180482674  mov     r8, rax; dwNewLong
0x180482677  call    cs:__imp_SetWindowLongPtrW
0x18048267e  nop     dword ptr [rax+rax+00h]
0x180482683  mov     edx, r12d; int
0x180482686  mov     rcx, rdi; this
0x180482689  call    ?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x18048268e  mov     eax, cs:?g_RTLOS@DirectUI@@3HA; int DirectUI::g_RTLOS
0x180482694  cmp     eax, 0FFFFFFFFh
0x180482697  jnz     short loc_180482702
0x180482699  test    sil, 4
0x18048269d  jz      short loc_1804826AD
0x18048269f  call    cs:__imp_GetThreadUILanguage
0x1804826a6  nop     dword ptr [rax+rax+00h]
0x1804826ab  jmp     short loc_1804826B9
0x1804826ad  call    cs:__imp_GetUserDefaultUILanguage
0x1804826b4  nop     dword ptr [rax+rax+00h]
0x1804826b9  mov     cs:?g_RTLOS@DirectUI@@3HA, r15d; int DirectUI::g_RTLOS
0x1804826c0  test    ax, ax
0x1804826c3  jz      short loc_180482742
0x1804826c5  mov     r9d, 10h; cchData
0x1804826cb  movzx   ecx, ax; Locale
0x1804826ce  lea     r8, [rbp+50h+LCData]; lpLCData
0x1804826d2  lea     edx, [r9+48h]; LCType
0x1804826d6  call    cs:__imp_GetLocaleInfoW
0x1804826dd  nop     dword ptr [rax+rax+00h]
0x1804826e2  test    eax, eax
0x1804826e4  jz      short loc_1804826FC
0x1804826e6  mov     eax, 800h
0x1804826eb  test    [rbp+50h+var_52], ax
0x1804826ef  jz      short loc_1804826FC
0x1804826f1  mov     eax, r12d
0x1804826f4  mov     cs:?g_RTLOS@DirectUI@@3HA, eax; int DirectUI::g_RTLOS
0x1804826fa  jmp     short loc_180482702
0x1804826fc  mov     eax, cs:?g_RTLOS@DirectUI@@3HA; int DirectUI::g_RTLOS
0x180482702  cmp     eax, r12d
0x180482705  jnz     short loc_180482742
0x180482707  mov     edx, r12d; int
0x18048270a  mov     rcx, rdi; this
0x18048270d  call    ?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x180482712  mov     rcx, [rdi+0C8h]; hWnd
0x180482719  mov     edx, ebx; nIndex
0x18048271b  call    cs:__imp_GetWindowLongPtrW
0x180482722  nop     dword ptr [rax+rax+00h]
0x180482727  mov     rcx, [rdi+0C8h]; hWnd
0x18048272e  mov     edx, ebx; nIndex
0x180482730  and     rax, r14
0x180482733  mov     r8, rax; dwNewLong
0x180482736  call    cs:__imp_SetWindowLongPtrW
0x18048273d  nop     dword ptr [rax+rax+00h]
0x180482742  mov     rcx, [rdi+0C8h]
0x180482749  lea     r8, ?_DisplayNodeCallback@Element@DirectUI@@SAJPEAUHGADGET__@@PEAXPEAUEventMsg@@@Z; DirectUI::Element::_DisplayNodeCallback(HGADGET__ *,void *,EventMsg *)
0x180482750  mov     r9, rdi
0x180482753  mov     edx, r12d
0x180482756  call    cs:__imp_CreateGadget
0x18048275d  nop     dword ptr [rax+rax+00h]
0x180482762  mov     [rdi+8], rax
0x180482766  test    rax, rax
0x180482769  jnz     short loc_18048277E
0x18048276b  call    cs:__imp_GetLastError
0x180482772  nop     dword ptr [rax+rax+00h]
0x180482777  mov     ebx, eax
0x180482779  jmp     loc_180482446
0x18048277e  mov     r9d, 0FFh
0x180482784  xor     edx, edx
0x180482786  mov     rcx, rax
0x180482789  lea     r8d, [r9-62h]
0x18048278d  call    cs:__imp_SetGadgetMessageFilter
0x180482794  nop     dword ptr [rax+rax+00h]
0x180482799  mov     rcx, [rdi+8]
0x18048279d  mov     edx, 809h
0x1804827a2  mov     r8d, 0E2Bh
0x1804827a8  call    SetGadgetStyle_0
0x1804827ad  call    IsPalette
0x1804827b2  test    al, al
0x1804827b4  jz      short loc_180482813
0x1804827b6  mov     rax, [rdi]
0x1804827b9  mov     rcx, rdi
0x1804827bc  mov     rax, [rax+168h]
0x1804827c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804827c8  xor     ecx, ecx; hWnd
0x1804827ca  call    cs:__imp_GetDC
0x1804827d1  nop     dword ptr [rax+rax+00h]
0x1804827d6  mov     rcx, rax; hdc
0x1804827d9  mov     rbx, rax
0x1804827dc  call    cs:__imp_CreateHalftonePalette
0x1804827e3  nop     dword ptr [rax+rax+00h]
0x1804827e8  mov     rdx, rbx; hDC
0x1804827eb  xor     ecx, ecx; hWnd
0x1804827ed  mov     [rdi+0D8h], rax
0x1804827f4  call    cs:__imp_ReleaseDC
0x1804827fb  nop     dword ptr [rax+rax+00h]
0x180482800  cmp     [rdi+0D8h], r15
0x180482807  jnz     short loc_180482813
0x180482809  mov     ebx, 80040002h
0x18048280e  jmp     loc_180482446
0x180482813  mov     rax, [rdi+0D8h]
0x18048281a  xorps   xmm0, xmm0
0x18048281d  mov     [rsp+150h+var_DC], r15
0x180482822  mov     ecx, 6
0x180482827  mov     dword ptr [rsp+150h+var_DC], ecx
0x18048282b  mov     [rbp+50h+var_B8], rax
0x18048282f  mov     [rbp+50h+var_C0], r15
0x180482833  mov     [rsp+150h+var_E0], 30h ; '0'
0x18048283b  mov     [rsp+150h+var_D4], r15d
0x180482840  movdqu  [rbp+50h+var_D0], xmm0
0x180482845  test    sil, 8
0x180482849  jz      short loc_180482858
0x18048284b  mov     ecx, 16h
0x180482850  mov     dword ptr [rbp+50h+var_D0+4], r12d
0x180482854  mov     dword ptr [rsp+150h+var_DC], ecx
0x180482858  test    sil, 10h
0x18048285c  jz      short loc_180482869
0x18048285e  or      ecx, 20h
0x180482861  mov     dword ptr [rbp+50h+var_D0+8], r12d
0x180482865  mov     dword ptr [rsp+150h+var_DC], ecx
0x180482869  test    sil, 20h
0x18048286d  jz      short loc_18048287A
0x18048286f  or      ecx, 40h
0x180482872  mov     dword ptr [rbp+50h+var_D0+0Ch], r12d
0x180482876  mov     dword ptr [rsp+150h+var_DC], ecx
0x18048287a  mov     edx, 80h
0x18048287f  test    sil, 40h
0x180482883  jz      short loc_18048288F
0x180482885  or      ecx, edx
  ... truncated ...
```
