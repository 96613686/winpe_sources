# DevicesPage::FlashText(tagRECT,ushort const *)

- ea: `0x18000ca3c`
- end: `0x18000cc3b`
- name: `?FlashText@DevicesPage@@AEAAXUtagRECT@@PEBG@Z`
- size: `511`
- prototype: `void __fastcall(DevicesPage *this, struct tagRECT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000eb00`

## callees

- `0x18000ca3c`
- `0x18000cc44`
- `0x180017c70`
- `0x180018110`
- `0x1800184ce`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000cbda`
- `KERNEL32!DeactivateActCtx` at `0x18000cbda`
- `USER32!ReleaseDC` at `0x18000cab5`
- `USER32!ReleaseDC` at `0x18000cab5`
- `USER32!UpdateWindow` at `0x18000cbf6`
- `USER32!UpdateWindow` at `0x18000cbf6`
- `USER32!LoadCursorW` at `0x18000caea`
- `USER32!LoadCursorW` at `0x18000caea`
- `USER32!RegisterClassW` at `0x18000cb2a`
- `USER32!RegisterClassW` at `0x18000cb2a`
- `USER32!SetTimer` at `0x18000cc0c`
- `USER32!SetTimer` at `0x18000cc0c`
- `USER32!GetDC` at `0x18000ca63`
- `USER32!GetDC` at `0x18000ca63`
- `USER32!DestroyWindow` at `0x18000cc1a`
- `USER32!DestroyWindow` at `0x18000cc1a`
- `USER32!CreateWindowExW` at `0x18000cbc6`
- `USER32!CreateWindowExW` at `0x18000cbc6`
- `USER32!ShowWindow` at `0x18000cbed`
- `USER32!ShowWindow` at `0x18000cbed`
- `GDI32!DeleteObject` at `0x18000cabe`
- `GDI32!DeleteObject` at `0x18000cabe`
- `GDI32!GetTextExtentPointW` at `0x18000caa2`
- `GDI32!GetTextExtentPointW` at `0x18000caa2`
- `GDI32!SelectObject` at `0x18000ca7d`
- `GDI32!SelectObject` at `0x18000ca7d`

## pseudocode

```c
void __fastcall DevicesPage::FlashText(DevicesPage *this, struct tagRECT *a2, const unsigned __int16 *a3)
{
  HDC DC; // rbx
  HFONT BigFont; // rdi
  __int64 v8; // r8
  HCURSOR CursorW; // rax
  HINSTANCE hInstance; // r14
  LONG nHeight; // ebx
  LONG nWidth; // edi
  int v13; // kr00_4
  int X; // r15d
  HWND Window; // rbx
  WNDCLASSW WndClass; // [rsp+60h] [rbp-29h] BYREF
  tagSIZE sz; // [rsp+F0h] [rbp+67h] BYREF
  ULONG_PTR ulCookie; // [rsp+F8h] [rbp+6Fh] BYREF

  DC = GetDC(0);
  BigFont = DevicesPage::GetBigFont(a2);
  SelectObject(DC, BigFont);
  sz = 0;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( !GetTextExtentPointW(DC, a3, v8, &sz) )
    sz = 0;
  ReleaseDC(0, DC);
  DeleteObject(BigFont);
  if ( !DevicesPage::s_fFlashWindowRegistered )
  {
    memset_0(&WndClass, 0, sizeof(WndClass));
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
    WndClass.hIcon = 0;
    WndClass.hCursor = CursorW;
    WndClass.hInstance = (HINSTANCE)*((_QWORD *)this + 8);
    WndClass.lpfnWndProc = (WNDPROC)DevicesPage::BigNumberWindowProc;
    WndClass.lpszMenuName = 0;
    WndClass.lpszClassName = L"MonitorNumberWindow";
    WndClass.hbrBackground = (HBRUSH)2;
    WndClass.style = 3;
    *(_QWORD *)&WndClass.cbClsExtra = 0;
    RegisterClassW(&WndClass);
    DevicesPage::s_fFlashWindowRegistered = 1;
  }
  hInstance = (HINSTANCE)*((_QWORD *)this + 8);
  nHeight = sz.cy;
  nWidth = sz.cx;
  ulCookie = 0;
  if ( (unsigned int)SHActivateContext(&ulCookie) )
  {
    v13 = a2->top + a2->bottom - nHeight;
    X = (a2->left + a2->right - nWidth) / 2;
    if ( g_hActCtx != -3 )
      DelayLoadCC();
    Window = CreateWindowExW(
               0x88u,
               L"MonitorNumberWindow",
               a3,
               0x80000000,
               X,
               v13 / 2,
               nWidth,
               nHeight,
               0,
               0,
               hInstance,
               0);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
    if ( Window )
    {
      ShowWindow(Window, 5);
      UpdateWindow(Window);
      if ( !SetTimer(Window, 1u, 0x9C4u, 0) )
        DestroyWindow(Window);
    }
  }
}

```

## disassembly

```asm
0x18000ca3c  mov     [rsp-8+arg_10], rbx
0x18000ca41  push    rbp
0x18000ca42  push    rsi
0x18000ca43  push    rdi
0x18000ca44  push    r12
0x18000ca46  push    r13
0x18000ca48  push    r14
0x18000ca4a  push    r15
0x18000ca4c  lea     rbp, [rsp-27h]
0x18000ca51  sub     rsp, 0B0h
0x18000ca58  mov     r14, rcx
0x18000ca5b  mov     rsi, r8
0x18000ca5e  xor     ecx, ecx; hWnd
0x18000ca60  mov     r15, rdx
0x18000ca63  call    cs:__imp_GetDC
0x18000ca69  mov     rcx, r15; struct tagRECT *
0x18000ca6c  mov     rbx, rax
0x18000ca6f  call    ?GetBigFont@DevicesPage@@CAPEAUHFONT__@@PEBUtagRECT@@@Z; DevicesPage::GetBigFont(tagRECT const *)
0x18000ca74  mov     rdx, rax; h
0x18000ca77  mov     rcx, rbx; hdc
0x18000ca7a  mov     rdi, rax
0x18000ca7d  call    cs:__imp_SelectObject
0x18000ca83  xor     r13d, r13d
0x18000ca86  mov     qword ptr [rbp+57h+sz.cx], r13
0x18000ca8a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ca8e  inc     r8; c
0x18000ca91  cmp     [rsi+r8*2], r13w
0x18000ca96  jnz     short loc_18000CA8E
0x18000ca98  lea     r9, [rbp+57h+sz]; lpsz
0x18000ca9c  mov     rdx, rsi; lpString
0x18000ca9f  mov     rcx, rbx; hdc
0x18000caa2  call    cs:__imp_GetTextExtentPointW
0x18000caa8  test    eax, eax
0x18000caaa  jnz     short loc_18000CAB0
0x18000caac  mov     qword ptr [rbp+57h+sz.cx], r13
0x18000cab0  mov     rdx, rbx; hDC
0x18000cab3  xor     ecx, ecx; hWnd
0x18000cab5  call    cs:__imp_ReleaseDC
0x18000cabb  mov     rcx, rdi; ho
0x18000cabe  call    cs:__imp_DeleteObject
0x18000cac4  cmp     cs:?s_fFlashWindowRegistered@DevicesPage@@0HA, r13d; int DevicesPage::s_fFlashWindowRegistered
0x18000cacb  lea     rbx, ClassName; "MonitorNumberWindow"
0x18000cad2  jnz     short loc_18000CB3A
0x18000cad4  xor     edx, edx; Val
0x18000cad6  lea     rcx, [rbp+57h+WndClass]; void *
0x18000cada  lea     r8d, [rdx+48h]; Size
0x18000cade  call    memset_0
0x18000cae3  mov     edx, 7F00h; lpCursorName
0x18000cae8  xor     ecx, ecx; hInstance
0x18000caea  call    cs:__imp_LoadCursorW
0x18000caf0  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x18000caf4  mov     [rbp+57h+WndClass.hIcon], r13
0x18000caf8  mov     [rbp+57h+WndClass.hCursor], rax
0x18000cafc  mov     rax, [r14+40h]
0x18000cb00  mov     [rbp+57h+WndClass.hInstance], rax
0x18000cb04  lea     rax, ?BigNumberWindowProc@DevicesPage@@CA_JPEAUHWND__@@I_K_J@Z; DevicesPage::BigNumberWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000cb0b  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x18000cb0f  mov     [rbp+57h+WndClass.lpszMenuName], r13
0x18000cb13  mov     [rbp+57h+WndClass.lpszClassName], rbx
0x18000cb17  mov     [rbp+57h+WndClass.hbrBackground], 2
0x18000cb1f  mov     [rbp+57h+WndClass.style], 3
0x18000cb26  mov     qword ptr [rbp+57h+WndClass.cbClsExtra], r13
0x18000cb2a  call    cs:__imp_RegisterClassW
0x18000cb30  mov     cs:?s_fFlashWindowRegistered@DevicesPage@@0HA, 1; int DevicesPage::s_fFlashWindowRegistered
0x18000cb3a  mov     r14, [r14+40h]
0x18000cb3e  lea     rcx, [rbp+57h+ulCookie]
0x18000cb42  mov     ebx, [rbp+57h+sz.cy]
0x18000cb45  mov     edi, [rbp+57h+sz.cx]
0x18000cb48  mov     [rbp+57h+ulCookie], r13
0x18000cb4c  call    SHActivateContext
0x18000cb51  test    eax, eax
0x18000cb53  jz      loc_18000CC20
0x18000cb59  mov     eax, [r15+0Ch]
0x18000cb5d  add     eax, [r15+4]
0x18000cb61  sub     eax, ebx
0x18000cb63  cdq
0x18000cb64  sub     eax, edx
0x18000cb66  sar     eax, 1
0x18000cb68  mov     r12d, eax
0x18000cb6b  mov     eax, [r15+8]
0x18000cb6f  sub     eax, edi
0x18000cb71  add     eax, [r15]
0x18000cb74  cdq
0x18000cb75  sub     eax, edx
0x18000cb77  sar     eax, 1
0x18000cb79  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x18000cb81  mov     r15d, eax
0x18000cb84  jz      short loc_18000CB8B
0x18000cb86  call    DelayLoadCC
0x18000cb8b  mov     [rsp+0E0h+lpParam], r13; lpParam
0x18000cb90  lea     rdx, ClassName; "MonitorNumberWindow"
0x18000cb97  mov     [rsp+0E0h+hInstance], r14; hInstance
0x18000cb9c  mov     r9d, 80000000h; dwStyle
0x18000cba2  mov     [rsp+0E0h+hMenu], r13; hMenu
0x18000cba7  mov     r8, rsi; lpWindowName
0x18000cbaa  mov     [rsp+0E0h+hWndParent], r13; hWndParent
0x18000cbaf  mov     ecx, 88h; dwExStyle
0x18000cbb4  mov     [rsp+0E0h+nHeight], ebx; nHeight
0x18000cbb8  mov     [rsp+0E0h+nWidth], edi; nWidth
0x18000cbbc  mov     [rsp+0E0h+Y], r12d; Y
0x18000cbc1  mov     [rsp+0E0h+X], r15d; X
0x18000cbc6  call    cs:__imp_CreateWindowExW
0x18000cbcc  mov     rdx, [rbp+57h+ulCookie]; ulCookie
0x18000cbd0  mov     rbx, rax
0x18000cbd3  test    rdx, rdx
0x18000cbd6  jz      short loc_18000CBE0
0x18000cbd8  xor     ecx, ecx; dwFlags
0x18000cbda  call    cs:__imp_DeactivateActCtx
0x18000cbe0  test    rbx, rbx
0x18000cbe3  jz      short loc_18000CC20
0x18000cbe5  mov     edx, 5; nCmdShow
0x18000cbea  mov     rcx, rbx; hWnd
0x18000cbed  call    cs:__imp_ShowWindow
0x18000cbf3  mov     rcx, rbx; hWnd
0x18000cbf6  call    cs:__imp_UpdateWindow
0x18000cbfc  xor     r9d, r9d; lpTimerFunc
0x18000cbff  mov     r8d, 9C4h; uElapse
0x18000cc05  mov     rcx, rbx; hWnd
0x18000cc08  lea     edx, [r9+1]; nIDEvent
0x18000cc0c  call    cs:__imp_SetTimer
0x18000cc12  test    rax, rax
0x18000cc15  jnz     short loc_18000CC20
0x18000cc17  mov     rcx, rbx; hWnd
0x18000cc1a  call    cs:__imp_DestroyWindow
0x18000cc20  mov     rbx, [rsp+0E0h+arg_10]
0x18000cc28  add     rsp, 0B0h
0x18000cc2f  pop     r15
0x18000cc31  pop     r14
0x18000cc33  pop     r13
0x18000cc35  pop     r12
0x18000cc37  pop     rdi
0x18000cc38  pop     rsi
0x18000cc39  pop     rbp
0x18000cc3a  retn
```
