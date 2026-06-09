# CExpInterDlg::CreateToolbarCtl(HWND__ *)

- ea: `0x14001a978`
- end: `0x14001ac14`
- name: `?CreateToolbarCtl@CExpInterDlg@@AEAAHPEAUHWND__@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(CExpInterDlg *__hidden this, HWND hWndParent)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14001c458`

## callees

- `0x140002463`
- `0x14001a978`
- `0x14001e68c`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001aa4a`
- `KERNEL32!GetLastError` at `0x14001aa5e`
- `KERNEL32!GetLastError` at `0x14001aa4a`
- `KERNEL32!GetLastError` at `0x14001aa5e`
- `USER32!SendMessageW` at `0x14001ab7c`
- `USER32!SendMessageW` at `0x14001ab7c`
- `USER32!ShowWindow` at `0x14001aa8a`
- `USER32!ShowWindow` at `0x14001ab91`
- `USER32!ShowWindow` at `0x14001aa8a`
- `USER32!ShowWindow` at `0x14001ab91`
- `USER32!CreateWindowExW` at `0x14001aa2d`
- `USER32!CreateWindowExW` at `0x14001ab5d`
- `USER32!CreateWindowExW` at `0x14001aa2d`
- `USER32!CreateWindowExW` at `0x14001ab5d`
- `USER32!LoadStringW` at `0x14001aab4`
- `USER32!LoadStringW` at `0x14001aab4`
- `USER32!UpdateWindow` at `0x14001abab`
- `USER32!UpdateWindow` at `0x14001abab`
- `USER32!GetClientRect` at `0x14001a9c5`
- `USER32!GetClientRect` at `0x14001a9c5`

## string_xrefs

- `0x14001aacf`: `CExpInterDlg::CreateToolbarCtl`
- `0x14001abbe`: `CExpInterDlg::CreateToolbarCtl`

## pseudocode

```c
_BOOL8 __fastcall CExpInterDlg::CreateToolbarCtl(HWND *this, HWND hWndParent)
{
  HWND Window; // rax
  int v5; // ebx
  CEventLogger *v6; // rcx
  signed int LastError; // eax
  CEventLogger *v8; // rcx
  HWND v9; // rax
  struct tagRECT Rect; // [rsp+60h] [rbp-828h] BYREF
  WCHAR Buffer[1024]; // [rsp+70h] [rbp-818h] BYREF

  Rect = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  GetClientRect(this[1], &Rect);
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
             (HMENU)0xDF,
             *((HINSTANCE *)_AtlModule + 76),
             0);
  this[10] = Window;
  if ( !Window || (v5 = 0, Window == HWND_MESSAGE|0x2LL) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        goto LABEL_7;
    }
    else
    {
      v5 = -2147467259;
    }
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\expinterdialog.cpp",
      0x63Du,
      L"CExpInterDlg::CreateToolbarCtl",
      v5);
    return v5 >= 0;
  }
LABEL_7:
  ShowWindow(this[10], 5);
  if ( !LoadStringW(*((HINSTANCE *)_AtlModule + 76), 0x234u, Buffer, 1024) )
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\expinterdialog.cpp",
      0x649u,
      L"CExpInterDlg::CreateToolbarCtl",
      0);
    memset_0(Buffer, 0, sizeof(Buffer));
  }
  v9 = CreateWindowExW(
         0,
         L"msctls_statusbar32",
         Buffer,
         0x54000100u,
         0,
         0,
         0,
         0,
         hWndParent,
         (HMENU)0x3EB,
         *((HINSTANCE *)_AtlModule + 76),
         0);
  this[11] = v9;
  SendMessageW(v9, 0x408u, 0x1Au, 0);
  ShowWindow(this[11], 5);
  CExpInterDlg::SetStatusText((CExpInterDlg *)this, 0);
  UpdateWindow(this[11]);
  return v5 >= 0;
}

```

## disassembly

```asm
0x14001a978  mov     [rsp+arg_10], rbx
0x14001a97d  mov     [rsp+arg_18], rsi
0x14001a982  push    rdi
0x14001a983  sub     rsp, 880h
0x14001a98a  mov     rax, cs:__security_cookie
0x14001a991  xor     rax, rsp
0x14001a994  mov     [rsp+888h+var_18], rax
0x14001a99c  mov     rsi, rdx
0x14001a99f  mov     rdi, rcx
0x14001a9a2  xorps   xmm0, xmm0
0x14001a9a5  lea     rcx, [rsp+888h+Buffer]; void *
0x14001a9aa  xor     edx, edx; Val
0x14001a9ac  mov     r8d, 800h; Size
0x14001a9b2  movups  xmmword ptr [rsp+888h+Rect.left], xmm0
0x14001a9b7  call    memset_0
0x14001a9bc  mov     rcx, [rdi+8]; hWnd
0x14001a9c0  lea     rdx, [rsp+888h+Rect]; lpRect
0x14001a9c5  call    cs:__imp_GetClientRect
0x14001a9cc  nop     dword ptr [rax+rax+00h]
0x14001a9d1  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001a9d8  lea     rdx, aToolbarwindow3; "ToolbarWindow32"
0x14001a9df  mov     [rsp+888h+lpParam], 0; lpParam
0x14001a9e8  mov     r9d, 44011141h; dwStyle
0x14001a9ee  xor     r8d, r8d; lpWindowName
0x14001a9f1  mov     rcx, [rax+260h]
0x14001a9f8  mov     [rsp+888h+hInstance], rcx; hInstance
0x14001a9fd  xor     ecx, ecx; dwExStyle
0x14001a9ff  mov     [rsp+888h+hMenu], 0DFh; hMenu
0x14001aa08  mov     [rsp+888h+hWndParent], rsi; hWndParent
0x14001aa0d  mov     [rsp+888h+nHeight], 0; nHeight
0x14001aa15  mov     [rsp+888h+nWidth], 0; nWidth
0x14001aa1d  mov     [rsp+888h+Y], 0; Y
0x14001aa25  mov     [rsp+888h+X], 0; X
0x14001aa2d  call    cs:__imp_CreateWindowExW
0x14001aa34  nop     dword ptr [rax+rax+00h]
0x14001aa39  mov     [rdi+50h], rax
0x14001aa3d  test    rax, rax
0x14001aa40  jz      short loc_14001AA4A
0x14001aa42  xor     ebx, ebx
0x14001aa44  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001aa48  jnz     short loc_14001AA81
0x14001aa4a  call    cs:__imp_GetLastError
0x14001aa51  nop     dword ptr [rax+rax+00h]
0x14001aa56  test    eax, eax
0x14001aa58  jz      loc_14001ABB9
0x14001aa5e  call    cs:__imp_GetLastError
0x14001aa65  nop     dword ptr [rax+rax+00h]
0x14001aa6a  mov     ebx, eax
0x14001aa6c  test    eax, eax
0x14001aa6e  jle     short loc_14001AA79
0x14001aa70  movzx   ebx, ax
0x14001aa73  or      ebx, 80070000h
0x14001aa79  test    ebx, ebx
0x14001aa7b  js      loc_14001ABBE
0x14001aa81  mov     rcx, [rdi+50h]; hWnd
0x14001aa85  mov     edx, 5; nCmdShow
0x14001aa8a  call    cs:__imp_ShowWindow
0x14001aa91  nop     dword ptr [rax+rax+00h]
0x14001aa96  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001aa9d  lea     r8, [rsp+888h+Buffer]; lpBuffer
0x14001aaa2  mov     r9d, 400h; cchBufferMax
0x14001aaa8  mov     edx, 234h; uID
0x14001aaad  mov     rcx, [rcx+260h]; hInstance
0x14001aab4  call    cs:__imp_LoadStringW
0x14001aabb  nop     dword ptr [rax+rax+00h]
0x14001aac0  test    eax, eax
0x14001aac2  jnz     short loc_14001AAFF
0x14001aac4  mov     [rsp+888h+Y], eax; unsigned int
0x14001aac8  lea     r8, aBaseDiagnosisR_27; "base\\diagnosis\\ra\\ui\\expinterdialog"...
0x14001aacf  lea     rax, aCexpinterdlgCr; "CExpInterDlg::CreateToolbarCtl"
0x14001aad6  mov     r9d, 649h; unsigned int
0x14001aadc  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001aae3  mov     qword ptr [rsp+888h+X], rax; unsigned __int16 *
0x14001aae8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001aaed  xor     edx, edx; Val
0x14001aaef  lea     rcx, [rsp+888h+Buffer]; void *
0x14001aaf4  mov     r8d, 800h; Size
0x14001aafa  call    memset_0
0x14001aaff  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001ab06  lea     r8, [rsp+888h+Buffer]; lpWindowName
0x14001ab0b  mov     [rsp+888h+lpParam], 0; lpParam
0x14001ab14  lea     rdx, aMsctlsStatusba; "msctls_statusbar32"
0x14001ab1b  mov     r9d, 54000100h; dwStyle
0x14001ab21  mov     rcx, [rax+260h]
0x14001ab28  mov     [rsp+888h+hInstance], rcx; hInstance
0x14001ab2d  xor     ecx, ecx; dwExStyle
0x14001ab2f  mov     [rsp+888h+hMenu], 3EBh; hMenu
0x14001ab38  mov     [rsp+888h+hWndParent], rsi; hWndParent
0x14001ab3d  mov     [rsp+888h+nHeight], 0; nHeight
0x14001ab45  mov     [rsp+888h+nWidth], 0; nWidth
0x14001ab4d  mov     [rsp+888h+Y], 0; Y
0x14001ab55  mov     [rsp+888h+X], 0; X
0x14001ab5d  call    cs:__imp_CreateWindowExW
0x14001ab64  nop     dword ptr [rax+rax+00h]
0x14001ab69  xor     r9d, r9d; lParam
0x14001ab6c  mov     edx, 408h; Msg
0x14001ab71  mov     rcx, rax; hWnd
0x14001ab74  mov     [rdi+58h], rax
0x14001ab78  lea     r8d, [r9+1Ah]; wParam
0x14001ab7c  call    cs:__imp_SendMessageW
0x14001ab83  nop     dword ptr [rax+rax+00h]
0x14001ab88  mov     rcx, [rdi+58h]; hWnd
0x14001ab8c  mov     edx, 5; nCmdShow
0x14001ab91  call    cs:__imp_ShowWindow
0x14001ab98  nop     dword ptr [rax+rax+00h]
0x14001ab9d  xor     edx, edx; unsigned int
0x14001ab9f  mov     rcx, rdi; this
0x14001aba2  call    ?SetStatusText@CExpInterDlg@@QEAAJI@Z; CExpInterDlg::SetStatusText(uint)
0x14001aba7  mov     rcx, [rdi+58h]; hWnd
0x14001abab  call    cs:__imp_UpdateWindow
0x14001abb2  nop     dword ptr [rax+rax+00h]
0x14001abb7  jmp     short loc_14001ABE7
0x14001abb9  mov     ebx, 80004005h
0x14001abbe  lea     rax, aCexpinterdlgCr; "CExpInterDlg::CreateToolbarCtl"
0x14001abc5  mov     [rsp+888h+Y], ebx; unsigned int
0x14001abc9  mov     r9d, 63Dh; unsigned int
0x14001abcf  mov     qword ptr [rsp+888h+X], rax; unsigned __int16 *
0x14001abd4  lea     r8, aBaseDiagnosisR_27; "base\\diagnosis\\ra\\ui\\expinterdialog"...
0x14001abdb  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001abe2  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001abe7  not     ebx
0x14001abe9  shr     ebx, 1Fh
0x14001abec  mov     eax, ebx
0x14001abee  mov     rcx, [rsp+888h+var_18]
0x14001abf6  xor     rcx, rsp; StackCookie
0x14001abf9  call    __security_check_cookie
0x14001abfe  lea     r11, [rsp+888h+var_8]
0x14001ac06  mov     rbx, [r11+20h]
0x14001ac0a  mov     rsi, [r11+28h]
0x14001ac0e  mov     rsp, r11
0x14001ac11  pop     rdi
0x14001ac12  retn
```
