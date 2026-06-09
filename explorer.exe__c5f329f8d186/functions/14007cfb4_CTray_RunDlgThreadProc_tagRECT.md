# CTray::_RunDlgThreadProc(tagRECT *)

- ea: `0x14007cfb4`
- end: `0x14007d3ce`
- name: `?_RunDlgThreadProc@CTray@@IEAAKPEAUtagRECT@@@Z`
- size: `1050`
- prototype: `unsigned int(CTray *__hidden this, struct tagRECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400b3a10`

## callees

- `0x140021280`
- `0x14007cfb4`
- `0x14007d3d4`
- `0x14010e160`
- `0x14010e4c4`
- `0x1401b4b80`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14007d19b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14007d19b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007d28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007d2d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007d335`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007d28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007d2d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007d335`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14007d314`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14007d314`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x14007d00c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x14007d00c`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007d028`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007d028`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x14007d23f`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x14007d23f`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14007d05d`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x14007d05d`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x14007d046`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x14007d046`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x14007d0f3`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x14007d0f3`
- `SHCORE!__imp_SHLockShared` at `0x14007d2e5`
- `SHCORE!__imp_SHLockShared` at `0x14007d2e5`
- `SHCORE!__imp_SHUnlockShared` at `0x14007d322`
- `SHCORE!__imp_SHUnlockShared` at `0x14007d322`
- `SHCORE!__imp_SHFreeShared` at `0x14007d347`
- `SHCORE!__imp_SHFreeShared` at `0x14007d347`
- `SHELL32!__imp_SHRestricted` at `0x14007d21f`
- `SHELL32!__imp_SHRestricted` at `0x14007d21f`
- `USER32!LoadIconW` at `0x14007d1ad`
- `USER32!LoadIconW` at `0x14007d1ad`
- `USER32!IsIconic` at `0x14007d271`
- `USER32!IsIconic` at `0x14007d271`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x14007d369`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x14007d369`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x14007d1c4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x14007d1c4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x14007d395`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x14007d395`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x14007d386`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x14007d386`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14007d35d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14007d35d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x14007d2c0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x14007d2c0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14007d188`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14007d188`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CreateWindowExW` at `0x14007d15f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CreateWindowExW` at `0x14007d15f`

## pseudocode

```c
__int64 __fastcall CTray::_RunDlgThreadProc(CTray *this, struct tagRECT *a2)
{
  HMONITOR v3; // rax
  int v4; // ebx
  __int64 v5; // rax
  int v6; // r8d
  HWND Window; // rax
  HWND v8; // rbx
  HMODULE ModuleHandleW; // rax
  HICON IconW; // rax
  void (__fastcall *v11)(HWND, LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, DWORD_PTR), _QWORD, _QWORD); // rax
  int v12; // r14d
  unsigned int v13; // edx
  unsigned int v14; // r9d
  ITEMIDLIST *v15; // rax
  HWND v16; // rsi
  DWORD v17; // eax
  DWORD CurrentProcessId; // eax
  DWORD v19; // eax
  unsigned int X; // [rsp+20h] [rbp-69h]
  unsigned int Y; // [rsp+28h] [rbp-61h]
  ULONG_PTR dwResult; // [rsp+60h] [rbp-29h] BYREF
  LPITEMIDLIST ppidl; // [rsp+68h] [rbp-21h] BYREF
  tagMONITORINFO mi; // [rsp+70h] [rbp-19h] BYREF
  struct tagRECT rcDst; // [rsp+98h] [rbp+Fh] BYREF

  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  v3 = (HMONITOR)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_140250598 + 64LL))(qword_140250598);
  if ( !GetMonitorInfoW(v3, &mi) )
    SystemParametersInfoW(0x30u, 0, &mi.rcMonitor, 0);
  rcDst = 0;
  if ( !IntersectRect(&rcDst, a2, &mi.rcMonitor) || !EqualRect(&rcDst, a2) )
  {
    v4 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, ULONG_PTR *))(*(_QWORD *)qword_140250598 + 344LL))(
                      qword_140250598,
                      &dwResult)
       - g_cxFrame;
    v5 = (*(__int64 (__fastcall **)(__int64, ULONG_PTR *))(*(_QWORD *)qword_140250598 + 344LL))(
           qword_140250598,
           &dwResult);
    if ( a2->left >= mi.rcMonitor.left )
    {
      v6 = *(_DWORD *)(v5 + 4) - g_cyFrame;
      if ( a2->top < mi.rcMonitor.top )
      {
        v4 = 0;
        --v6;
LABEL_14:
        OffsetRect(a2, v4, v6);
        goto LABEL_15;
      }
      if ( a2->right <= mi.rcMonitor.right )
      {
        if ( a2->bottom > mi.rcMonitor.bottom )
        {
          v4 = 0;
          v6 = g_cyFrame - *(_DWORD *)(v5 + 4);
        }
        goto LABEL_14;
      }
      v4 = -v4;
    }
    else
    {
      --v4;
    }
    v6 = 0;
    goto LABEL_14;
  }
LABEL_15:
  Window = CreateWindowExW(
             0x80u,
             L"static",
             0,
             0,
             a2->left,
             a2->top,
             a2->right - a2->left,
             a2->bottom - a2->top,
             0,
             0,
             g_hinstCabinet,
             0);
  v8 = Window;
  if ( Window )
  {
    SetPropW(Window, L"AllowConsentToStealFocus", HANDLE_FLAG_INHERIT);
    ModuleHandleW = GetModuleHandleW(L"SHELL32");
    IconW = LoadIconW(ModuleHandleW, (LPCWSTR)0xA0);
    SendMessageW(v8, 0x80u, 1u, (LPARAM)IconW);
    v11 = (void (__fastcall *)(HWND, LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, DWORD_PTR), _QWORD, _QWORD))qword_14024EAC8;
    v12 = 0;
    dwResult = 0;
    ppidl = 0;
    if ( qword_14024EAC8 == -1 )
    {
      GetProcFromComCtl32(&qword_14024EAC8, 410);
      v11 = (void (__fastcall *)(HWND, LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, DWORD_PTR), _QWORD, _QWORD))qword_14024EAC8;
    }
    if ( v11 )
      v11(v8, RunDlgStaticSubclassWndProc, 0, 0);
    if ( !SHRestricted(REST_STARTRUNNOHOMEPATH) && SHGetKnownFolderIDList(&FOLDERID_Profile, 0, 0, &ppidl) >= 0 )
      v12 = 1;
    v15 = ppidl;
    if ( !ppidl )
    {
      v16 = hWnd;
      if ( hWnd )
      {
        if ( !IsIconic(hWnd)
          && (unsigned int)IsExplorerWindow(v16)
          && (v17 = GetCurrentProcessId(), SendMessageTimeoutW(v16, 0x40Cu, v17, 0, 3u, 0x1F4u, &dwResult), dwResult) )
        {
          CurrentProcessId = GetCurrentProcessId();
          v15 = (ITEMIDLIST *)SHLockShared((HANDLE)dwResult, CurrentProcessId);
          ppidl = v15;
        }
        else
        {
          v15 = ppidl;
        }
      }
    }
    _RunFileDlg(v8, v13, (const struct _ITEMIDLIST_ABSOLUTE *)v15, v14, X, Y);
    if ( ppidl )
    {
      if ( v12 )
        ILFree(ppidl);
      else
        SHUnlockShared(ppidl);
    }
    if ( dwResult )
    {
      v19 = GetCurrentProcessId();
      SHFreeShared((HANDLE)dwResult, v19);
    }
    RemovePropW(v8, L"AllowConsentToStealFocus");
    if ( GetForegroundWindow() == v8 && v_hwndDesktop )
      SetForegroundWindow(v_hwndDesktop);
    DestroyWindow(v8);
  }
  operator delete(a2, 0x10u);
  return 1;
}

```

## disassembly

```asm
0x14007cfb4  push    rbp
0x14007cfb6  push    rbx
0x14007cfb7  push    rsi
0x14007cfb8  push    rdi
0x14007cfb9  push    r12
0x14007cfbb  push    r14
0x14007cfbd  lea     rbp, [rsp-2Fh]
0x14007cfc2  sub     rsp, 0B8h
0x14007cfc9  mov     rax, cs:__security_cookie
0x14007cfd0  xor     rax, rsp
0x14007cfd3  mov     [rbp+57h+var_38], rax
0x14007cfd7  mov     rcx, cs:qword_140250598
0x14007cfde  xor     eax, eax
0x14007cfe0  xorps   xmm0, xmm0
0x14007cfe3  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rax
0x14007cfe7  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm0
0x14007cfeb  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x14007cff2  mov     rdi, rdx
0x14007cff5  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm0
0x14007cff9  mov     rax, [rcx]
0x14007cffc  mov     rax, [rax+40h]
0x14007d000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d005  mov     rcx, rax; hMonitor
0x14007d008  lea     rdx, [rbp+57h+mi]; lpmi
0x14007d00c  call    cs:__imp_GetMonitorInfoW
0x14007d013  nop     dword ptr [rax+rax+00h]
0x14007d018  test    eax, eax
0x14007d01a  jnz     short loc_14007D034
0x14007d01c  xor     r9d, r9d; fWinIni
0x14007d01f  lea     r8, [rbp+57h+mi.rcMonitor]; pvParam
0x14007d023  xor     edx, edx; uiParam
0x14007d025  lea     ecx, [rax+30h]; uiAction
0x14007d028  call    cs:__imp_SystemParametersInfoW
0x14007d02f  nop     dword ptr [rax+rax+00h]
0x14007d034  xorps   xmm0, xmm0
0x14007d037  lea     r8, [rbp+57h+mi.rcMonitor]; lprcSrc2
0x14007d03b  mov     rdx, rdi; lprcSrc1
0x14007d03e  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x14007d042  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x14007d046  call    cs:__imp_IntersectRect
0x14007d04d  nop     dword ptr [rax+rax+00h]
0x14007d052  test    eax, eax
0x14007d054  jz      short loc_14007D071
0x14007d056  mov     rdx, rdi; lprc2
0x14007d059  lea     rcx, [rbp+57h+rcDst]; lprc1
0x14007d05d  call    cs:__imp_EqualRect
0x14007d064  nop     dword ptr [rax+rax+00h]
0x14007d069  test    eax, eax
0x14007d06b  jnz     loc_14007D0FF
0x14007d071  mov     rcx, cs:qword_140250598
0x14007d078  lea     rdx, [rbp+57h+dwResult]
0x14007d07c  mov     rax, [rcx]
0x14007d07f  mov     rax, [rax+158h]
0x14007d086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d08b  mov     rcx, cs:qword_140250598
0x14007d092  lea     rdx, [rbp+57h+dwResult]
0x14007d096  mov     ebx, [rax]
0x14007d098  mov     rax, [rcx]
0x14007d09b  sub     ebx, cs:g_cxFrame
0x14007d0a1  mov     rax, [rax+158h]
0x14007d0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d0ad  mov     ecx, [rbp+57h+mi.rcMonitor.left]
0x14007d0b0  cmp     [rdi], ecx
0x14007d0b2  jge     short loc_14007D0B8
0x14007d0b4  dec     ebx
0x14007d0b6  jmp     short loc_14007D0DC
0x14007d0b8  mov     r8d, [rax+4]
0x14007d0bc  sub     r8d, cs:g_cyFrame
0x14007d0c3  mov     eax, [rbp+57h+mi.rcMonitor.top]
0x14007d0c6  cmp     [rdi+4], eax
0x14007d0c9  jge     short loc_14007D0D2
0x14007d0cb  xor     ebx, ebx
0x14007d0cd  dec     r8d
0x14007d0d0  jmp     short loc_14007D0EE
0x14007d0d2  mov     eax, [rbp+57h+mi.rcMonitor.right]
0x14007d0d5  cmp     [rdi+8], eax
0x14007d0d8  jle     short loc_14007D0E1
0x14007d0da  neg     ebx
0x14007d0dc  xor     r8d, r8d
0x14007d0df  jmp     short loc_14007D0EE
0x14007d0e1  mov     eax, [rbp+57h+mi.rcMonitor.bottom]
0x14007d0e4  cmp     [rdi+0Ch], eax
0x14007d0e7  jle     short loc_14007D0EE
0x14007d0e9  xor     ebx, ebx
0x14007d0eb  neg     r8d; dy
0x14007d0ee  mov     edx, ebx; dx
0x14007d0f0  mov     rcx, rdi; lprc
0x14007d0f3  call    cs:__imp_OffsetRect
0x14007d0fa  nop     dword ptr [rax+rax+00h]
0x14007d0ff  mov     r8d, [rdi+4]
0x14007d103  mov     esi, 80h
0x14007d108  mov     r9d, [rdi]
0x14007d10b  mov     edx, [rdi+0Ch]
0x14007d10e  mov     rax, cs:g_hinstCabinet
0x14007d115  sub     edx, r8d
0x14007d118  mov     ecx, [rdi+8]
0x14007d11b  mov     [rsp+0E0h+lpParam], 0; lpParam
0x14007d124  sub     ecx, r9d
0x14007d127  mov     [rsp+0E0h+hInstance], rax; hInstance
0x14007d12c  mov     [rsp+0E0h+hMenu], 0; hMenu
0x14007d135  mov     [rsp+0E0h+hWndParent], 0; hWndParent
0x14007d13e  mov     [rsp+0E0h+nHeight], edx; nHeight
0x14007d142  lea     rdx, aStatic; "static"
0x14007d149  mov     [rsp+0E0h+nWidth], ecx; nWidth
0x14007d14d  mov     ecx, esi; dwExStyle
0x14007d14f  mov     [rsp+0E0h+Y], r8d; unsigned int
0x14007d154  xor     r8d, r8d; lpWindowName
0x14007d157  mov     [rsp+0E0h+X], r9d; unsigned int
0x14007d15c  xor     r9d, r9d; dwStyle
0x14007d15f  call    cs:__imp_CreateWindowExW
0x14007d166  nop     dword ptr [rax+rax+00h]
0x14007d16b  lea     r12d, [rsi-7Fh]
0x14007d16f  mov     rbx, rax
0x14007d172  test    rax, rax
0x14007d175  jz      loc_14007D3A1
0x14007d17b  mov     r8d, r12d; hData
0x14007d17e  lea     rdx, aAllowconsentto; "AllowConsentToStealFocus"
0x14007d185  mov     rcx, rax; hWnd
0x14007d188  call    cs:__imp_SetPropW
0x14007d18f  nop     dword ptr [rax+rax+00h]
0x14007d194  lea     rcx, aShell32; "SHELL32"
0x14007d19b  call    cs:__imp_GetModuleHandleW
0x14007d1a2  nop     dword ptr [rax+rax+00h]
0x14007d1a7  mov     rcx, rax; hInstance
0x14007d1aa  lea     edx, [rsi+20h]; lpIconName
0x14007d1ad  call    cs:__imp_LoadIconW
0x14007d1b4  nop     dword ptr [rax+rax+00h]
0x14007d1b9  mov     r8d, r12d; wParam
0x14007d1bc  mov     edx, esi; Msg
0x14007d1be  mov     r9, rax; lParam
0x14007d1c1  mov     rcx, rbx; hWnd
0x14007d1c4  call    cs:__imp_SendMessageW
0x14007d1cb  nop     dword ptr [rax+rax+00h]
0x14007d1d0  mov     rax, cs:qword_14024EAC8
0x14007d1d7  xor     r14d, r14d
0x14007d1da  mov     [rbp+57h+dwResult], r14
0x14007d1de  mov     [rbp+57h+ppidl], r14
0x14007d1e2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007d1e6  jnz     short loc_14007D200
0x14007d1e8  mov     edx, 19Ah
0x14007d1ed  lea     rcx, qword_14024EAC8
0x14007d1f4  call    _GetProcFromComCtl32
0x14007d1f9  mov     rax, cs:qword_14024EAC8
0x14007d200  test    rax, rax
0x14007d203  jz      short loc_14007D21A
0x14007d205  xor     r9d, r9d
0x14007d208  lea     rdx, ?RunDlgStaticSubclassWndProc@@YA_JPEAUHWND__@@I_K_J11@Z; RunDlgStaticSubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x14007d20f  xor     r8d, r8d
0x14007d212  mov     rcx, rbx
0x14007d215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d21a  mov     ecx, 40000061h; rest
0x14007d21f  call    cs:__imp_SHRestricted
0x14007d226  nop     dword ptr [rax+rax+00h]
0x14007d22b  test    eax, eax
0x14007d22d  jnz     short loc_14007D251
0x14007d22f  lea     r9, [rbp+57h+ppidl]; ppidl
0x14007d233  xor     r8d, r8d; hToken
0x14007d236  xor     edx, edx; dwFlags
0x14007d238  lea     rcx, FOLDERID_Profile; rfid
0x14007d23f  call    cs:__imp_SHGetKnownFolderIDList
0x14007d246  nop     dword ptr [rax+rax+00h]
0x14007d24b  test    eax, eax
0x14007d24d  cmovns  r14d, r12d
0x14007d251  mov     rax, [rbp+57h+ppidl]
0x14007d255  test    rax, rax
0x14007d258  jnz     loc_14007D2FB
0x14007d25e  mov     rsi, cs:hWnd
0x14007d265  test    rsi, rsi
0x14007d268  jz      loc_14007D2FB
0x14007d26e  mov     rcx, rsi; hWnd
0x14007d271  call    cs:__imp_IsIconic
0x14007d278  nop     dword ptr [rax+rax+00h]
0x14007d27d  test    eax, eax
0x14007d27f  jnz     short loc_14007D2F7
0x14007d281  mov     rcx, rsi; hWnd
0x14007d284  call    IsExplorerWindow
0x14007d289  test    eax, eax
0x14007d28b  jz      short loc_14007D2F7
0x14007d28d  call    cs:__imp_GetCurrentProcessId
0x14007d294  nop     dword ptr [rax+rax+00h]
0x14007d299  mov     r8d, eax; wParam
0x14007d29c  xor     r9d, r9d; lParam
0x14007d29f  lea     rax, [rbp+57h+dwResult]
0x14007d2a3  mov     edx, 40Ch; Msg
0x14007d2a8  mov     qword ptr [rsp+0E0h+nWidth], rax; lpdwResult
0x14007d2ad  mov     rcx, rsi; hWnd
0x14007d2b0  mov     [rsp+0E0h+Y], 1F4h; uTimeout
0x14007d2b8  mov     [rsp+0E0h+X], 3; fuFlags
0x14007d2c0  call    cs:__imp_SendMessageTimeoutW
0x14007d2c7  nop     dword ptr [rax+rax+00h]
0x14007d2cc  cmp     [rbp+57h+dwResult], 0
0x14007d2d1  jz      short loc_14007D2F7
0x14007d2d3  call    cs:__imp_GetCurrentProcessId
0x14007d2da  nop     dword ptr [rax+rax+00h]
0x14007d2df  mov     rcx, [rbp+57h+dwResult]; hData
0x14007d2e3  mov     edx, eax; dwProcessId
0x14007d2e5  call    cs:__imp_SHLockShared
0x14007d2ec  nop     dword ptr [rax+rax+00h]
0x14007d2f1  mov     [rbp+57h+ppidl], rax
0x14007d2f5  jmp     short loc_14007D2FB
0x14007d2f7  mov     rax, [rbp+57h+ppidl]
0x14007d2fb  mov     r8, rax; struct _ITEMIDLIST_ABSOLUTE *
0x14007d2fe  mov     rcx, rbx; hwnd
0x14007d301  call    ?_RunFileDlg@@YAXPEAUHWND__@@IPEBU_ITEMIDLIST_ABSOLUTE@@IIK@Z; _RunFileDlg(HWND__ *,uint,_ITEMIDLIST_ABSOLUTE const *,uint,uint,ulong)
0x14007d306  mov     rcx, [rbp+57h+ppidl]; pvData
0x14007d30a  test    rcx, rcx
0x14007d30d  jz      short loc_14007D32E
0x14007d30f  test    r14d, r14d
0x14007d312  jz      short loc_14007D322
0x14007d314  call    cs:__imp_ILFree
0x14007d31b  nop     dword ptr [rax+rax+00h]
0x14007d320  jmp     short loc_14007D32E
0x14007d322  call    cs:__imp_SHUnlockShared
0x14007d329  nop     dword ptr [rax+rax+00h]
0x14007d32e  cmp     [rbp+57h+dwResult], 0
0x14007d333  jz      short loc_14007D353
0x14007d335  call    cs:__imp_GetCurrentProcessId
0x14007d33c  nop     dword ptr [rax+rax+00h]
0x14007d341  mov     rcx, [rbp+57h+dwResult]; hData
0x14007d345  mov     edx, eax; dwProcessId
0x14007d347  call    cs:__imp_SHFreeShared
0x14007d34e  nop     dword ptr [rax+rax+00h]
0x14007d353  lea     rdx, aAllowconsentto; "AllowConsentToStealFocus"
0x14007d35a  mov     rcx, rbx; hWnd
0x14007d35d  call    cs:__imp_RemovePropW
0x14007d364  nop     dword ptr [rax+rax+00h]
0x14007d369  call    cs:__imp_GetForegroundWindow
0x14007d370  nop     dword ptr [rax+rax+00h]
0x14007d375  cmp     rax, rbx
0x14007d378  jnz     short loc_14007D392
0x14007d37a  mov     rcx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; hWnd
0x14007d381  test    rcx, rcx
0x14007d384  jz      short loc_14007D392
0x14007d386  call    cs:__imp_SetForegroundWindow
0x14007d38d  nop     dword ptr [rax+rax+00h]
0x14007d392  mov     rcx, rbx; hWnd
0x14007d395  call    cs:__imp_DestroyWindow
0x14007d39c  nop     dword ptr [rax+rax+00h]
0x14007d3a1  mov     edx, 10h; unsigned __int64
0x14007d3a6  mov     rcx, rdi; void *
0x14007d3a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14007d3ae  mov     eax, r12d
0x14007d3b1  mov     rcx, [rbp+57h+var_38]
0x14007d3b5  xor     rcx, rsp; StackCookie
0x14007d3b8  call    __security_check_cookie
0x14007d3bd  add     rsp, 0B8h
0x14007d3c4  pop     r14
0x14007d3c6  pop     r12
0x14007d3c8  pop     rdi
0x14007d3c9  pop     rsi
0x14007d3ca  pop     rbx
0x14007d3cb  pop     rbp
0x14007d3cc  retn
```
