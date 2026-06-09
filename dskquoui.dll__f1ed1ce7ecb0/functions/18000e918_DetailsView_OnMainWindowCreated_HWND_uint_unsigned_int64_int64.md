# DetailsView::OnMainWindowCreated(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000e918`
- end: `0x18000eb09`
- name: `?OnMainWindowCreated@DetailsView@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `497`
- prototype: `__int64 __fastcall(DetailsView *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180010960`

## callees

- `0x180006ec0`
- `0x18000946c`
- `0x180009b34`
- `0x18000aeb4`
- `0x18000e918`
- `0x18000f31c`
- `0x1800101b4`
- `0x180010f20`
- `0x18001c0c4`
- `0x18001c888`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000e9f5`
- `KERNEL32!DeactivateActCtx` at `0x18000e9f5`
- `USER32!UpdateWindow` at `0x18000eaa0`
- `USER32!UpdateWindow` at `0x18000eaa0`
- `USER32!CheckMenuItem` at `0x18000ea3a`
- `USER32!CheckMenuItem` at `0x18000ea3a`
- `USER32!GetMenu` at `0x18000ea29`
- `USER32!GetMenu` at `0x18000ea29`
- `USER32!CreateWindowExW` at `0x18000e9dd`
- `USER32!CreateWindowExW` at `0x18000e9dd`
- `USER32!LoadAcceleratorsW` at `0x18000e93b`
- `USER32!LoadAcceleratorsW` at `0x18000e93b`
- `USER32!ShowWindow` at `0x18000ea12`
- `USER32!ShowWindow` at `0x18000ea96`
- `USER32!ShowWindow` at `0x18000ea12`
- `USER32!ShowWindow` at `0x18000ea96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DetailsView::OnMainWindowCreated(DetailsView *this, HWND a2, __int64 a3, ULONG_PTR a4)
{
  HINSTANCE hInstance; // rbx
  HWND hWndParent; // rsi
  HWND Window; // rbx
  UINT v8; // ebx
  HMENU Menu; // rax
  struct IConnectionPoint *ConnectionPoint; // rax
  struct IConnectionPoint *v11; // rbx
  PointerList *v12; // rax
  PointerList *v13; // rsi
  __int64 v14; // rbx
  ULONG_PTR ulCookie; // [rsp+88h] [rbp+20h] BYREF

  ulCookie = a4;
  *((_QWORD *)this + 20) = LoadAcceleratorsW(g_hInstDll, (LPCWSTR)0x8C);
  DetailsView::CreateListView(this);
  hInstance = g_hInstDll;
  hWndParent = (HWND)*((_QWORD *)this + 12);
  ulCookie = 0;
  if ( (unsigned int)SHActivateContext(&ulCookie) )
  {
    if ( g_hActCtx != (HANDLE)-3LL )
      DelayLoadCC();
    Window = CreateWindowExW(
               0,
               L"msctls_statusbar32",
               &WindowName,
               0x50800010u,
               0,
               0,
               0,
               0,
               hWndParent,
               0,
               hInstance,
               0);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  else
  {
    Window = 0;
  }
  *((_QWORD *)this + 14) = Window;
  if ( Window )
  {
    if ( (*((_BYTE *)this + 588) & 2) == 0 )
      ShowWindow(Window, 0);
    v8 = 4 * (*((_WORD *)this + 294) & 2);
    Menu = GetMenu(*((HWND *)this + 12));
    CheckMenuItem(Menu, 0x9C44u, v8);
  }
  DetailsView::CreateToolBar(this);
  ConnectionPoint = DetailsView::GetConnectionPoint(this);
  v11 = ConnectionPoint;
  if ( ConnectionPoint )
  {
    ((void (__fastcall *)(struct IConnectionPoint *, unsigned __int64, char *))ConnectionPoint->lpVtbl->Advise)(
      ConnectionPoint,
      ((unsigned __int64)this + 24) & -(__int64)(this != 0),
      (char *)this + 512);
    ((void (__fastcall *)(struct IConnectionPoint *))v11->lpVtbl->Release)(v11);
  }
  ShowWindow(*((HWND *)this + 12), 1);
  UpdateWindow(*((HWND *)this + 12));
  v12 = (PointerList *)operator new(0x48u);
  v13 = v12;
  ulCookie = (ULONG_PTR)v12;
  if ( v12 )
  {
    v14 = *((_QWORD *)this + 13);
    PointerList::PointerList(v12, 0);
    *((_QWORD *)v13 + 7) = (char *)this + 40;
    *((_QWORD *)v13 + 8) = v14;
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 24) = v13;
  DetailsView::ShowItemCountInStatusBar(this);
  DetailsView::Refresh(this, 0);
  return 0;
}

```

## disassembly

```asm
0x18000e918  mov     [rsp+arg_0], rbx
0x18000e91d  mov     [rsp+arg_8], rsi
0x18000e922  mov     [rsp+ulCookie], r9
0x18000e927  push    rdi
0x18000e928  sub     rsp, 60h
0x18000e92c  mov     rdi, rcx
0x18000e92f  mov     edx, 8Ch; lpTableName
0x18000e934  mov     rcx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000e93b  call    cs:__imp_LoadAcceleratorsW
0x18000e941  mov     [rdi+0A0h], rax
0x18000e948  mov     rcx, rdi; this
0x18000e94b  call    ?CreateListView@DetailsView@@AEAAJXZ; DetailsView::CreateListView(void)
0x18000e950  mov     rbx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x18000e957  mov     rsi, [rdi+60h]
0x18000e95b  mov     [rsp+68h+ulCookie], 0
0x18000e967  lea     rcx, [rsp+68h+ulCookie]
0x18000e96f  call    SHActivateContext
0x18000e974  test    eax, eax
0x18000e976  jnz     short loc_18000E97C
0x18000e978  xor     ebx, ebx
0x18000e97a  jmp     short loc_18000E9FB
0x18000e97c  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x18000e984  jz      short loc_18000E98B
0x18000e986  call    DelayLoadCC
0x18000e98b  mov     [rsp+68h+lpParam], 0; lpParam
0x18000e994  mov     [rsp+68h+hInstance], rbx; hInstance
0x18000e999  mov     [rsp+68h+hMenu], 0; hMenu
0x18000e9a2  mov     [rsp+68h+hWndParent], rsi; hWndParent
0x18000e9a7  mov     [rsp+68h+nHeight], 0; nHeight
0x18000e9af  mov     [rsp+68h+nWidth], 0; nWidth
0x18000e9b7  mov     [rsp+68h+Y], 0; Y
0x18000e9bf  mov     [rsp+68h+X], 0; X
0x18000e9c7  mov     r9d, 50800010h; dwStyle
0x18000e9cd  lea     r8, WindowName; lpWindowName
0x18000e9d4  lea     rdx, ClassName; "msctls_statusbar32"
0x18000e9db  xor     ecx, ecx; dwExStyle
0x18000e9dd  call    cs:__imp_CreateWindowExW
0x18000e9e3  mov     rbx, rax
0x18000e9e6  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x18000e9ee  test    rdx, rdx
0x18000e9f1  jz      short loc_18000E9FB
0x18000e9f3  xor     ecx, ecx; dwFlags
0x18000e9f5  call    cs:__imp_DeactivateActCtx
0x18000e9fb  mov     [rdi+70h], rbx
0x18000e9ff  test    rbx, rbx
0x18000ea02  jz      short loc_18000EA40
0x18000ea04  test    byte ptr [rdi+24Ch], 2
0x18000ea0b  jnz     short loc_18000EA18
0x18000ea0d  xor     edx, edx; nCmdShow
0x18000ea0f  mov     rcx, rbx; hWnd
0x18000ea12  call    cs:__imp_ShowWindow
0x18000ea18  movzx   ebx, word ptr [rdi+24Ch]
0x18000ea1f  and     ebx, 2
0x18000ea22  shl     ebx, 2
0x18000ea25  mov     rcx, [rdi+60h]; hWnd
0x18000ea29  call    cs:__imp_GetMenu
0x18000ea2f  mov     r8d, ebx; uCheck
0x18000ea32  mov     edx, 9C44h; uIDCheckItem
0x18000ea37  mov     rcx, rax; hMenu
0x18000ea3a  call    cs:__imp_CheckMenuItem
0x18000ea40  mov     rcx, rdi; this
0x18000ea43  call    ?CreateToolBar@DetailsView@@AEAAJXZ; DetailsView::CreateToolBar(void)
0x18000ea48  mov     rcx, rdi; this
0x18000ea4b  call    ?GetConnectionPoint@DetailsView@@AEAAPEAUIConnectionPoint@@XZ; DetailsView::GetConnectionPoint(void)
0x18000ea50  mov     rbx, rax
0x18000ea53  test    rax, rax
0x18000ea56  jz      short loc_18000EA8D
0x18000ea58  mov     rax, [rax]
0x18000ea5b  lea     r8, [rdi+200h]
0x18000ea62  mov     rcx, rdi
0x18000ea65  lea     r9, [rdi+18h]
0x18000ea69  neg     rcx
0x18000ea6c  sbb     rdx, rdx
0x18000ea6f  and     rdx, r9
0x18000ea72  mov     rcx, rbx
0x18000ea75  mov     rax, [rax+28h]
0x18000ea79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea7e  mov     rax, [rbx]
0x18000ea81  mov     rcx, rbx
0x18000ea84  mov     rax, [rax+10h]
0x18000ea88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea8d  mov     edx, 1; nCmdShow
0x18000ea92  mov     rcx, [rdi+60h]; hWnd
0x18000ea96  call    cs:__imp_ShowWindow
0x18000ea9c  mov     rcx, [rdi+60h]; hWnd
0x18000eaa0  call    cs:__imp_UpdateWindow
0x18000eaa6  mov     ecx, 48h ; 'H'; uBytes
0x18000eaab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eab0  mov     rsi, rax
0x18000eab3  mov     [rsp+68h+ulCookie], rax
0x18000eabb  test    rax, rax
0x18000eabe  jz      short loc_18000EADC
0x18000eac0  mov     rbx, [rdi+68h]
0x18000eac4  xor     edx, edx; int
0x18000eac6  mov     rcx, rax; this
0x18000eac9  call    ??0PointerList@@QEAA@H@Z; PointerList::PointerList(int)
0x18000eace  lea     rcx, [rdi+28h]
0x18000ead2  mov     [rsi+38h], rcx
0x18000ead6  mov     [rsi+40h], rbx
0x18000eada  jmp     short loc_18000EADE
0x18000eadc  xor     esi, esi
0x18000eade  mov     [rdi+0C0h], rsi
0x18000eae5  mov     rcx, rdi; this
0x18000eae8  call    ?ShowItemCountInStatusBar@DetailsView@@AEAA_JXZ; DetailsView::ShowItemCountInStatusBar(void)
0x18000eaed  xor     edx, edx; bool
0x18000eaef  mov     rcx, rdi; this
0x18000eaf2  call    ?Refresh@DetailsView@@AEAA_J_N@Z; DetailsView::Refresh(bool)
0x18000eaf7  xor     eax, eax
0x18000eaf9  mov     rbx, [rsp+68h+arg_0]
0x18000eafe  mov     rsi, [rsp+68h+arg_8]
0x18000eb03  add     rsp, 60h
0x18000eb07  pop     rdi
0x18000eb08  retn
```
