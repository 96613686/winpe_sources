# CTray::_RunDlgThreadProc(tagRECT *)

- ea: `0x14007837c`
- end: `0x1400786f7`
- name: `?_RunDlgThreadProc@CTray@@IEAAKPEAUtagRECT@@@Z`
- size: `891`
- prototype: `unsigned int(CTray *__hidden this, struct tagRECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400ac870`

## callees

- `0x140024058`
- `0x14007837c`
- `0x140078700`
- `0x1401040e0`
- `0x140104444`
- `0x1401b6848`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140078539`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140078539`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400785ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140078639`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140078683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400785ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140078639`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140078683`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14007866e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14007866e`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400783ea`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400783ea`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1400783d4`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1400783d4`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1400785c5`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1400785c5`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x140078402`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x140078402`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x1400784a3`
- `api-ms-win-ntuser-rectangle-l1-1-0!OffsetRect` at `0x1400784a3`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x140078413`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x140078413`
- `SHCORE!__imp_SHLockShared` at `0x140078645`
- `SHCORE!__imp_SHLockShared` at `0x140078645`
- `SHCORE!__imp_SHUnlockShared` at `0x140078676`
- `SHCORE!__imp_SHUnlockShared` at `0x140078676`
- `SHCORE!__imp_SHFreeShared` at `0x14007868f`
- `SHCORE!__imp_SHFreeShared` at `0x14007868f`
- `SHELL32!__imp_SHRestricted` at `0x1400785ab`
- `SHELL32!__imp_SHRestricted` at `0x1400785ab`
- `USER32!LoadIconW` at `0x140078545`
- `USER32!LoadIconW` at `0x140078545`
- `USER32!IsIconic` at `0x1400785e9`
- `USER32!IsIconic` at `0x1400785e9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1400786a5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetForegroundWindow` at `0x1400786a5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x140078556`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x140078556`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x1400786c5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x1400786c5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x1400786bc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x1400786bc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14007869f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x14007869f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x14007862c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x14007862c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14007852c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetPropW` at `0x14007852c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CreateWindowExW` at `0x140078509`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CreateWindowExW` at `0x140078509`

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
  v3 = (HMONITOR)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_140254428 + 64LL))(qword_140254428);
  if ( !GetMonitorInfoW(v3, &mi) )
    SystemParametersInfoW(0x30u, 0, &mi.rcMonitor, 0);
  rcDst = 0;
  if ( !IntersectRect(&rcDst, a2, &mi.rcMonitor) || !EqualRect(&rcDst, a2) )
  {
    v4 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, ULONG_PTR *))(*(_QWORD *)qword_140254428 + 344LL))(
                      qword_140254428,
                      &dwResult)
       - g_cxFrame;
    v5 = (*(__int64 (__fastcall **)(__int64, ULONG_PTR *))(*(_QWORD *)qword_140254428 + 344LL))(
           qword_140254428,
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
    v11 = (void (__fastcall *)(HWND, LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, DWORD_PTR), _QWORD, _QWORD))qword_1402529B8;
    v12 = 0;
    dwResult = 0;
    ppidl = 0;
    if ( qword_1402529B8 == -1 )
    {
      GetProcFromComCtl32(&qword_1402529B8, 410);
      v11 = (void (__fastcall *)(HWND, LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, DWORD_PTR), _QWORD, _QWORD))qword_1402529B8;
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
0x14007837c  push    rbp
0x14007837e  push    rbx
0x14007837f  push    rsi
0x140078380  push    rdi
0x140078381  push    r12
0x140078383  push    r14
0x140078385  lea     rbp, [rsp-2Fh]
0x14007838a  sub     rsp, 0B8h
0x140078391  mov     rax, cs:__security_cookie
0x140078398  xor     rax, rsp
0x14007839b  mov     [rbp+57h+var_38], rax
0x14007839f  mov     rcx, cs:qword_140254428
0x1400783a6  xor     eax, eax
0x1400783a8  xorps   xmm0, xmm0
0x1400783ab  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rax
0x1400783af  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm0
0x1400783b3  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x1400783ba  mov     rdi, rdx
0x1400783bd  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm0
0x1400783c1  mov     rax, [rcx]
0x1400783c4  mov     rax, [rax+40h]
0x1400783c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400783cd  mov     rcx, rax; hMonitor
0x1400783d0  lea     rdx, [rbp+57h+mi]; lpmi
0x1400783d4  call    cs:__imp_GetMonitorInfoW
0x1400783da  test    eax, eax
0x1400783dc  jnz     short loc_1400783F0
0x1400783de  xor     r9d, r9d; fWinIni
0x1400783e1  lea     r8, [rbp+57h+mi.rcMonitor]; pvParam
0x1400783e5  xor     edx, edx; uiParam
0x1400783e7  lea     ecx, [rax+30h]; uiAction
0x1400783ea  call    cs:__imp_SystemParametersInfoW
0x1400783f0  xorps   xmm0, xmm0
0x1400783f3  lea     r8, [rbp+57h+mi.rcMonitor]; lprcSrc2
0x1400783f7  mov     rdx, rdi; lprcSrc1
0x1400783fa  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1400783fe  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x140078402  call    cs:__imp_IntersectRect
0x140078408  test    eax, eax
0x14007840a  jz      short loc_140078421
0x14007840c  mov     rdx, rdi; lprc2
0x14007840f  lea     rcx, [rbp+57h+rcDst]; lprc1
0x140078413  call    cs:__imp_EqualRect
0x140078419  test    eax, eax
0x14007841b  jnz     loc_1400784A9
0x140078421  mov     rcx, cs:qword_140254428
0x140078428  lea     rdx, [rbp+57h+dwResult]
0x14007842c  mov     rax, [rcx]
0x14007842f  mov     rax, [rax+158h]
0x140078436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007843b  mov     rcx, cs:qword_140254428
0x140078442  lea     rdx, [rbp+57h+dwResult]
0x140078446  mov     ebx, [rax]
0x140078448  mov     rax, [rcx]
0x14007844b  sub     ebx, cs:g_cxFrame
0x140078451  mov     rax, [rax+158h]
0x140078458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007845d  mov     ecx, [rbp+57h+mi.rcMonitor.left]
0x140078460  cmp     [rdi], ecx
0x140078462  jge     short loc_140078468
0x140078464  dec     ebx
0x140078466  jmp     short loc_14007848C
0x140078468  mov     r8d, [rax+4]
0x14007846c  sub     r8d, cs:g_cyFrame
0x140078473  mov     eax, [rbp+57h+mi.rcMonitor.top]
0x140078476  cmp     [rdi+4], eax
0x140078479  jge     short loc_140078482
0x14007847b  xor     ebx, ebx
0x14007847d  dec     r8d
0x140078480  jmp     short loc_14007849E
0x140078482  mov     eax, [rbp+57h+mi.rcMonitor.right]
0x140078485  cmp     [rdi+8], eax
0x140078488  jle     short loc_140078491
0x14007848a  neg     ebx
0x14007848c  xor     r8d, r8d
0x14007848f  jmp     short loc_14007849E
0x140078491  mov     eax, [rbp+57h+mi.rcMonitor.bottom]
0x140078494  cmp     [rdi+0Ch], eax
0x140078497  jle     short loc_14007849E
0x140078499  xor     ebx, ebx
0x14007849b  neg     r8d; dy
0x14007849e  mov     edx, ebx; dx
0x1400784a0  mov     rcx, rdi; lprc
0x1400784a3  call    cs:__imp_OffsetRect
0x1400784a9  mov     r8d, [rdi+4]
0x1400784ad  mov     esi, 80h
0x1400784b2  mov     r9d, [rdi]
0x1400784b5  mov     edx, [rdi+0Ch]
0x1400784b8  mov     rax, cs:g_hinstCabinet
0x1400784bf  sub     edx, r8d
0x1400784c2  mov     ecx, [rdi+8]
0x1400784c5  mov     [rsp+0E0h+lpParam], 0; lpParam
0x1400784ce  sub     ecx, r9d
0x1400784d1  mov     [rsp+0E0h+hInstance], rax; hInstance
0x1400784d6  mov     [rsp+0E0h+hMenu], 0; hMenu
0x1400784df  mov     [rsp+0E0h+hWndParent], 0; hWndParent
0x1400784e8  mov     [rsp+0E0h+nHeight], edx; nHeight
0x1400784ec  lea     rdx, aStatic; "static"
0x1400784f3  mov     [rsp+0E0h+nWidth], ecx; nWidth
0x1400784f7  mov     ecx, esi; dwExStyle
0x1400784f9  mov     [rsp+0E0h+Y], r8d; unsigned int
0x1400784fe  xor     r8d, r8d; lpWindowName
0x140078501  mov     [rsp+0E0h+X], r9d; unsigned int
0x140078506  xor     r9d, r9d; dwStyle
0x140078509  call    cs:__imp_CreateWindowExW
0x14007850f  lea     r12d, [rsi-7Fh]
0x140078513  mov     rbx, rax
0x140078516  test    rax, rax
0x140078519  jz      loc_1400786CB
0x14007851f  mov     r8d, r12d; hData
0x140078522  lea     rdx, aAllowconsentto; "AllowConsentToStealFocus"
0x140078529  mov     rcx, rax; hWnd
0x14007852c  call    cs:__imp_SetPropW
0x140078532  lea     rcx, aShell32; "SHELL32"
0x140078539  call    cs:__imp_GetModuleHandleW
0x14007853f  mov     rcx, rax; hInstance
0x140078542  lea     edx, [rsi+20h]; lpIconName
0x140078545  call    cs:__imp_LoadIconW
0x14007854b  mov     r8d, r12d; wParam
0x14007854e  mov     edx, esi; Msg
0x140078550  mov     r9, rax; lParam
0x140078553  mov     rcx, rbx; hWnd
0x140078556  call    cs:__imp_SendMessageW
0x14007855c  mov     rax, cs:qword_1402529B8
0x140078563  xor     r14d, r14d
0x140078566  mov     [rbp+57h+dwResult], r14
0x14007856a  mov     [rbp+57h+ppidl], r14
0x14007856e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140078572  jnz     short loc_14007858C
0x140078574  mov     edx, 19Ah
0x140078579  lea     rcx, qword_1402529B8
0x140078580  call    _GetProcFromComCtl32
0x140078585  mov     rax, cs:qword_1402529B8
0x14007858c  test    rax, rax
0x14007858f  jz      short loc_1400785A6
0x140078591  xor     r9d, r9d
0x140078594  lea     rdx, ?RunDlgStaticSubclassWndProc@@YA_JPEAUHWND__@@I_K_J11@Z; RunDlgStaticSubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x14007859b  xor     r8d, r8d
0x14007859e  mov     rcx, rbx
0x1400785a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400785a6  mov     ecx, 40000061h; rest
0x1400785ab  call    cs:__imp_SHRestricted
0x1400785b1  test    eax, eax
0x1400785b3  jnz     short loc_1400785D1
0x1400785b5  lea     r9, [rbp+57h+ppidl]; ppidl
0x1400785b9  xor     r8d, r8d; hToken
0x1400785bc  xor     edx, edx; dwFlags
0x1400785be  lea     rcx, FOLDERID_Profile; rfid
0x1400785c5  call    cs:__imp_SHGetKnownFolderIDList
0x1400785cb  test    eax, eax
0x1400785cd  cmovns  r14d, r12d
0x1400785d1  mov     rax, [rbp+57h+ppidl]
0x1400785d5  test    rax, rax
0x1400785d8  jnz     short loc_140078655
0x1400785da  mov     rsi, cs:hWnd
0x1400785e1  test    rsi, rsi
0x1400785e4  jz      short loc_140078655
0x1400785e6  mov     rcx, rsi; hWnd
0x1400785e9  call    cs:__imp_IsIconic
0x1400785ef  test    eax, eax
0x1400785f1  jnz     short loc_140078651
0x1400785f3  mov     rcx, rsi; hWnd
0x1400785f6  call    IsExplorerWindow
0x1400785fb  test    eax, eax
0x1400785fd  jz      short loc_140078651
0x1400785ff  call    cs:__imp_GetCurrentProcessId
0x140078605  mov     r8d, eax; wParam
0x140078608  xor     r9d, r9d; lParam
0x14007860b  lea     rax, [rbp+57h+dwResult]
0x14007860f  mov     edx, 40Ch; Msg
0x140078614  mov     qword ptr [rsp+0E0h+nWidth], rax; lpdwResult
0x140078619  mov     rcx, rsi; hWnd
0x14007861c  mov     [rsp+0E0h+Y], 1F4h; uTimeout
0x140078624  mov     [rsp+0E0h+X], 3; fuFlags
0x14007862c  call    cs:__imp_SendMessageTimeoutW
0x140078632  cmp     [rbp+57h+dwResult], 0
0x140078637  jz      short loc_140078651
0x140078639  call    cs:__imp_GetCurrentProcessId
0x14007863f  mov     rcx, [rbp+57h+dwResult]; hData
0x140078643  mov     edx, eax; dwProcessId
0x140078645  call    cs:__imp_SHLockShared
0x14007864b  mov     [rbp+57h+ppidl], rax
0x14007864f  jmp     short loc_140078655
0x140078651  mov     rax, [rbp+57h+ppidl]
0x140078655  mov     r8, rax; struct _ITEMIDLIST_ABSOLUTE *
0x140078658  mov     rcx, rbx; hwnd
0x14007865b  call    ?_RunFileDlg@@YAXPEAUHWND__@@IPEBU_ITEMIDLIST_ABSOLUTE@@IIK@Z; _RunFileDlg(HWND__ *,uint,_ITEMIDLIST_ABSOLUTE const *,uint,uint,ulong)
0x140078660  mov     rcx, [rbp+57h+ppidl]; pvData
0x140078664  test    rcx, rcx
0x140078667  jz      short loc_14007867C
0x140078669  test    r14d, r14d
0x14007866c  jz      short loc_140078676
0x14007866e  call    cs:__imp_ILFree
0x140078674  jmp     short loc_14007867C
0x140078676  call    cs:__imp_SHUnlockShared
0x14007867c  cmp     [rbp+57h+dwResult], 0
0x140078681  jz      short loc_140078695
0x140078683  call    cs:__imp_GetCurrentProcessId
0x140078689  mov     rcx, [rbp+57h+dwResult]; hData
0x14007868d  mov     edx, eax; dwProcessId
0x14007868f  call    cs:__imp_SHFreeShared
0x140078695  lea     rdx, aAllowconsentto; "AllowConsentToStealFocus"
0x14007869c  mov     rcx, rbx; hWnd
0x14007869f  call    cs:__imp_RemovePropW
0x1400786a5  call    cs:__imp_GetForegroundWindow
0x1400786ab  cmp     rax, rbx
0x1400786ae  jnz     short loc_1400786C2
0x1400786b0  mov     rcx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; hWnd
0x1400786b7  test    rcx, rcx
0x1400786ba  jz      short loc_1400786C2
0x1400786bc  call    cs:__imp_SetForegroundWindow
0x1400786c2  mov     rcx, rbx; hWnd
0x1400786c5  call    cs:__imp_DestroyWindow
0x1400786cb  mov     edx, 10h; unsigned __int64
0x1400786d0  mov     rcx, rdi; void *
0x1400786d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400786d8  mov     eax, r12d
0x1400786db  mov     rcx, [rbp+57h+var_38]
0x1400786df  xor     rcx, rsp; StackCookie
0x1400786e2  call    __security_check_cookie
0x1400786e7  add     rsp, 0B8h
0x1400786ee  pop     r14
0x1400786f0  pop     r12
0x1400786f2  pop     rdi
0x1400786f3  pop     rsi
0x1400786f4  pop     rbx
0x1400786f5  pop     rbp
0x1400786f6  retn
```
