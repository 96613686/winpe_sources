# CNovInterDlg::InitSpecialControls(HWND__ *)

- ea: `0x14001fca0`
- end: `0x14001ffb0`
- name: `?InitSpecialControls@CNovInterDlg@@AEAAHPEAUHWND__@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(CNovInterDlg *__hidden this, HWND hWndParent)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140021e00`

## callees

- `0x140002463`
- `0x14001fca0`
- `0x140023f14`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `USER32!SendMessageW` at `0x14001ff27`
- `USER32!SendMessageW` at `0x14001ff69`
- `USER32!SendMessageW` at `0x14001ff27`
- `USER32!SendMessageW` at `0x14001ff69`
- `USER32!ShowWindow` at `0x14001fd9b`
- `USER32!ShowWindow` at `0x14001fe4d`
- `USER32!ShowWindow` at `0x14001fd9b`
- `USER32!ShowWindow` at `0x14001fe4d`
- `USER32!CreateWindowExW` at `0x14001fd54`
- `USER32!CreateWindowExW` at `0x14001fdef`
- `USER32!CreateWindowExW` at `0x14001fea8`
- `USER32!CreateWindowExW` at `0x14001fd54`
- `USER32!CreateWindowExW` at `0x14001fdef`
- `USER32!CreateWindowExW` at `0x14001fea8`
- `USER32!GetDlgItem` at `0x14001fefc`
- `USER32!GetDlgItem` at `0x14001ff4f`
- `USER32!GetDlgItem` at `0x14001fefc`
- `USER32!GetDlgItem` at `0x14001ff4f`
- `USER32!MapDialogRect` at `0x14001fcea`
- `USER32!MapDialogRect` at `0x14001fcea`
- `USER32!GetSysColor` at `0x14001ff38`
- `USER32!GetSysColor` at `0x14001ff38`
- `USER32!GetClientRect` at `0x14001fcfe`
- `USER32!GetClientRect` at `0x14001fcfe`

## pseudocode

```c
_BOOL8 __fastcall CNovInterDlg::InitSpecialControls(CNovInterDlg *this, HWND hWndParent)
{
  HWND v4; // rcx
  HWND Window; // rax
  CEventLogger *v6; // rcx
  HWND v7; // rax
  CEventLogger *v8; // rcx
  HWND v9; // rax
  HWND v10; // rcx
  HWND DlgItem; // rax
  HWND v12; // rcx
  DWORD SysColor; // ebx
  HWND v14; // rax
  LPARAM lParam[10]; // [rsp+60h] [rbp-39h] BYREF
  struct tagRECT Rect; // [rsp+B0h] [rbp+17h] BYREF
  struct tagRECT v18; // [rsp+C0h] [rbp+27h] BYREF

  v4 = (HWND)*((_QWORD *)this + 1);
  v18 = 0;
  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  MapDialogRect(v4, &Rect);
  GetClientRect(*((HWND *)this + 1), &v18);
  Window = CreateWindowExW(
             0,
             L"ToolbarWindow32",
             0,
             0x44011141u,
             0,
             0,
             0,
             0,
             hWndParent,
             (HMENU)0x401,
             *((HINSTANCE *)_AtlModule + 76),
             0);
  *((_QWORD *)this + 9) = Window;
  if ( !Window )
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0xA2Du,
      L"CNovInterDlg::InitSpecialControls",
      0);
  ShowWindow(*((HWND *)this + 9), 5);
  v7 = CreateWindowExW(
         0,
         L"msctls_statusbar32",
         0,
         0x40000100u,
         0,
         0,
         0,
         0,
         hWndParent,
         (HMENU)0x413,
         *((HINSTANCE *)_AtlModule + 76),
         0);
  *((_QWORD *)this + 22) = v7;
  if ( v7 )
  {
    CNovInterDlg::RefreshStatusBar(this, 511, 4013, 0);
    ShowWindow(*((HWND *)this + 22), 5);
  }
  else
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0xA46u,
      L"CNovInterDlg::InitSpecialControls",
      0);
  }
  v9 = CreateWindowExW(
         8u,
         L"tooltips_class32",
         0,
         0x80000003,
         0x80000000,
         0x80000000,
         0x80000000,
         0x80000000,
         *((HWND *)this + 1),
         0,
         *((HINSTANCE *)_AtlModule + 76),
         0);
  *((_QWORD *)this + 23) = v9;
  if ( v9 )
  {
    memset_0(lParam, 0, 0x48u);
    v10 = (HWND)*((_QWORD *)this + 1);
    lParam[0] = 0x1300000048LL;
    lParam[5] = *((_QWORD *)_AtlModule + 76);
    lParam[1] = (LPARAM)v10;
    DlgItem = GetDlgItem(v10, 1042);
    v12 = (HWND)*((_QWORD *)this + 23);
    lParam[2] = (LPARAM)DlgItem;
    lParam[6] = -1;
    SendMessageW(v12, 0x432u, 0, (LPARAM)lParam);
  }
  SysColor = GetSysColor(15);
  v14 = GetDlgItem(*((HWND *)this + 1), 1042);
  SendMessageW(v14, 0x443u, 0, SysColor);
  return *((_QWORD *)this + 9) && *((_QWORD *)this + 22) != 0;
}

```

## disassembly

```asm
0x14001fca0  mov     [rsp-8+arg_10], rbx
0x14001fca5  mov     [rsp-8+arg_18], rsi
0x14001fcaa  push    rbp
0x14001fcab  push    rdi
0x14001fcac  push    r15
0x14001fcae  lea     rbp, [rsp-47h]
0x14001fcb3  sub     rsp, 0E0h
0x14001fcba  mov     rax, cs:__security_cookie
0x14001fcc1  xor     rax, rsp
0x14001fcc4  mov     [rbp+57h+var_20], rax
0x14001fcc8  movdqa  xmm1, cs:__xmm@00000001000000010000000000000000
0x14001fcd0  mov     rbx, rdx
0x14001fcd3  mov     rdi, rcx
0x14001fcd6  lea     rdx, [rbp+57h+Rect]; lpRect
0x14001fcda  mov     rcx, [rcx+8]; hDlg
0x14001fcde  xorps   xmm0, xmm0
0x14001fce1  movups  xmmword ptr [rbp+57h+var_30.left], xmm0
0x14001fce5  movdqu  xmmword ptr [rbp+57h+Rect.left], xmm1
0x14001fcea  call    cs:__imp_MapDialogRect
0x14001fcf1  nop     dword ptr [rax+rax+00h]
0x14001fcf6  mov     rcx, [rdi+8]; hWnd
0x14001fcfa  lea     rdx, [rbp+57h+var_30]; lpRect
0x14001fcfe  call    cs:__imp_GetClientRect
0x14001fd05  nop     dword ptr [rax+rax+00h]
0x14001fd0a  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001fd11  lea     rdx, aToolbarwindow3; "ToolbarWindow32"
0x14001fd18  xor     esi, esi
0x14001fd1a  mov     r9d, 44011141h; dwStyle
0x14001fd20  mov     [rsp+0F0h+lpParam], rsi; lpParam
0x14001fd25  xor     r8d, r8d; lpWindowName
0x14001fd28  mov     rcx, [rax+260h]
0x14001fd2f  mov     [rsp+0F0h+hInstance], rcx; hInstance
0x14001fd34  xor     ecx, ecx; dwExStyle
0x14001fd36  mov     [rsp+0F0h+hMenu], 401h; hMenu
0x14001fd3f  mov     [rsp+0F0h+hWndParent], rbx; hWndParent
0x14001fd44  mov     [rsp+0F0h+nHeight], esi; nHeight
0x14001fd48  mov     [rsp+0F0h+nWidth], esi; nWidth
0x14001fd4c  mov     [rsp+0F0h+Y], esi; Y
0x14001fd50  mov     [rsp+0F0h+X], esi; X
0x14001fd54  call    cs:__imp_CreateWindowExW
0x14001fd5b  nop     dword ptr [rax+rax+00h]
0x14001fd60  mov     [rdi+48h], rax
0x14001fd64  lea     r15, aCnovinterdlgIn; "CNovInterDlg::InitSpecialControls"
0x14001fd6b  test    rax, rax
0x14001fd6e  jnz     short loc_14001FD92
0x14001fd70  mov     [rsp+0F0h+Y], esi; unsigned int
0x14001fd74  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14001fd7b  mov     r9d, 0A2Dh; unsigned int
0x14001fd81  mov     qword ptr [rsp+0F0h+X], r15; unsigned __int16 *
0x14001fd86  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001fd8d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001fd92  mov     rcx, [rdi+48h]; hWnd
0x14001fd96  mov     edx, 5; nCmdShow
0x14001fd9b  call    cs:__imp_ShowWindow
0x14001fda2  nop     dword ptr [rax+rax+00h]
0x14001fda7  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001fdae  lea     rdx, aMsctlsStatusba; "msctls_statusbar32"
0x14001fdb5  mov     [rsp+0F0h+lpParam], rsi; lpParam
0x14001fdba  mov     r9d, 40000100h; dwStyle
0x14001fdc0  xor     r8d, r8d; lpWindowName
0x14001fdc3  mov     rcx, [rax+260h]
0x14001fdca  mov     [rsp+0F0h+hInstance], rcx; hInstance
0x14001fdcf  xor     ecx, ecx; dwExStyle
0x14001fdd1  mov     [rsp+0F0h+hMenu], 413h; hMenu
0x14001fdda  mov     [rsp+0F0h+hWndParent], rbx; hWndParent
0x14001fddf  mov     [rsp+0F0h+nHeight], esi; nHeight
0x14001fde3  mov     [rsp+0F0h+nWidth], esi; nWidth
0x14001fde7  mov     [rsp+0F0h+Y], esi; Y
0x14001fdeb  mov     [rsp+0F0h+X], esi; X
0x14001fdef  call    cs:__imp_CreateWindowExW
0x14001fdf6  nop     dword ptr [rax+rax+00h]
0x14001fdfb  mov     [rdi+0B0h], rax
0x14001fe02  test    rax, rax
0x14001fe05  jnz     short loc_14001FE2B
0x14001fe07  mov     [rsp+0F0h+Y], esi; unsigned int
0x14001fe0b  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14001fe12  mov     r9d, 0A46h; unsigned int
0x14001fe18  mov     qword ptr [rsp+0F0h+X], r15; unsigned __int16 *
0x14001fe1d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001fe24  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001fe29  jmp     short loc_14001FE59
0x14001fe2b  xor     r9d, r9d; unsigned int
0x14001fe2e  mov     edx, 1FFh; int
0x14001fe33  mov     r8d, 0FADh; int
0x14001fe39  mov     rcx, rdi; this
0x14001fe3c  call    ?RefreshStatusBar@CNovInterDlg@@AEAAJHHI@Z; CNovInterDlg::RefreshStatusBar(int,int,uint)
0x14001fe41  mov     rcx, [rdi+0B0h]; hWnd
0x14001fe48  mov     edx, 5; nCmdShow
0x14001fe4d  call    cs:__imp_ShowWindow
0x14001fe54  nop     dword ptr [rax+rax+00h]
0x14001fe59  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001fe60  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x14001fe67  mov     [rsp+0F0h+lpParam], rsi; lpParam
0x14001fe6c  xor     r8d, r8d; lpWindowName
0x14001fe6f  mov     r9d, 80000003h; dwStyle
0x14001fe75  mov     rcx, [rax+260h]
0x14001fe7c  mov     rax, [rdi+8]
0x14001fe80  mov     [rsp+0F0h+hInstance], rcx; hInstance
0x14001fe85  lea     ecx, [r8+8]; dwExStyle
0x14001fe89  mov     [rsp+0F0h+hMenu], rsi; hMenu
0x14001fe8e  mov     [rsp+0F0h+hWndParent], rax; hWndParent
0x14001fe93  mov     eax, 80000000h
0x14001fe98  mov     [rsp+0F0h+nHeight], eax; nHeight
0x14001fe9c  mov     [rsp+0F0h+nWidth], eax; nWidth
0x14001fea0  mov     [rsp+0F0h+Y], eax; Y
0x14001fea4  mov     [rsp+0F0h+X], eax; X
0x14001fea8  call    cs:__imp_CreateWindowExW
0x14001feaf  nop     dword ptr [rax+rax+00h]
0x14001feb4  mov     [rdi+0B8h], rax
0x14001febb  test    rax, rax
0x14001febe  jz      short loc_14001FF33
0x14001fec0  mov     ebx, 48h ; 'H'
0x14001fec5  lea     rcx, [rbp+57h+lParam]; void *
0x14001fec9  mov     r8d, ebx; Size
0x14001fecc  xor     edx, edx; Val
0x14001fece  call    memset_0
0x14001fed3  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001feda  mov     rcx, [rdi+8]; hDlg
0x14001fede  mov     dword ptr [rbp+57h+lParam], ebx
0x14001fee1  mov     dword ptr [rbp+57h+lParam+4], 13h
0x14001fee8  mov     rdx, [rax+260h]
0x14001feef  mov     [rbp+57h+var_68], rdx
0x14001fef3  mov     edx, 412h; nIDDlgItem
0x14001fef8  mov     [rbp+57h+var_88], rcx
0x14001fefc  call    cs:__imp_GetDlgItem
0x14001ff03  nop     dword ptr [rax+rax+00h]
0x14001ff08  mov     rcx, [rdi+0B8h]; hWnd
0x14001ff0f  lea     r9, [rbp+57h+lParam]; lParam
0x14001ff13  xor     r8d, r8d; wParam
0x14001ff16  mov     [rbp+57h+var_80], rax
0x14001ff1a  mov     edx, 432h; Msg
0x14001ff1f  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x14001ff27  call    cs:__imp_SendMessageW
0x14001ff2e  nop     dword ptr [rax+rax+00h]
0x14001ff33  mov     ecx, 0Fh; nIndex
0x14001ff38  call    cs:__imp_GetSysColor
0x14001ff3f  nop     dword ptr [rax+rax+00h]
0x14001ff44  mov     rcx, [rdi+8]; hDlg
0x14001ff48  mov     edx, 412h; nIDDlgItem
0x14001ff4d  mov     ebx, eax
0x14001ff4f  call    cs:__imp_GetDlgItem
0x14001ff56  nop     dword ptr [rax+rax+00h]
0x14001ff5b  mov     r9d, ebx; lParam
0x14001ff5e  xor     r8d, r8d; wParam
0x14001ff61  mov     rcx, rax; hWnd
0x14001ff64  mov     edx, 443h; Msg
0x14001ff69  call    cs:__imp_SendMessageW
0x14001ff70  nop     dword ptr [rax+rax+00h]
0x14001ff75  cmp     [rdi+48h], rsi
0x14001ff79  jz      short loc_14001FF89
0x14001ff7b  cmp     [rdi+0B0h], rsi
0x14001ff82  mov     eax, esi
0x14001ff84  setnz   al
0x14001ff87  jmp     short loc_14001FF8B
0x14001ff89  xor     eax, eax
0x14001ff8b  mov     rcx, [rbp+57h+var_20]
0x14001ff8f  xor     rcx, rsp; StackCookie
0x14001ff92  call    __security_check_cookie
0x14001ff97  lea     r11, [rsp+0F0h+var_10]
0x14001ff9f  mov     rbx, [r11+30h]
0x14001ffa3  mov     rsi, [r11+38h]
0x14001ffa7  mov     rsp, r11
0x14001ffaa  pop     r15
0x14001ffac  pop     rdi
0x14001ffad  pop     rbp
0x14001ffae  retn
```
