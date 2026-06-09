# CTray::_RunDlg(void)

- ea: `0x140131140`
- end: `0x140131486`
- name: `?_RunDlg@CTray@@IEAAXXZ`
- size: `838`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400abc30`
- `0x14012f214`

## callees

- `0x14000bb20`
- `0x14000e160`
- `0x140010fb4`
- `0x1400a3364`
- `0x1400bbf98`
- `0x1400e1758`
- `0x1400e1790`
- `0x14010e160`
- `0x14010e4c4`
- `0x140116088`
- `0x140120448`
- `0x140130b20`
- `0x140131140`
- `0x140131f20`
- `0x140132014`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14013130e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14013130e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140131358`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140131358`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140131213`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140131258`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140131213`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140131258`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x140131417`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x140131417`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1401313d5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1401313d5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x14013136d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x14013136d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x1401313f8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x1401313f8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140131380`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140131380`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!FindWindowW` at `0x140131324`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!FindWindowW` at `0x140131324`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x14013134c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x14013134c`

## string_xrefs

- `0x14013124a`: `Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced\TaskbarDeveloperSettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTray::_RunDlg(HWND *this, __int64 a2, __int64 a3)
{
  int v4; // eax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  HWND WindowW; // rax
  HWND v8; // rbx
  struct tagRECT *v9; // rax
  struct tagPOINT *v10; // rbx
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwProcessId; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[272]; // [rsp+70h] [rbp-90h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_StartMenu_RunDialog_Start,
      a3,
      1,
      v14);
  if ( !(unsigned int)_Restricted(g_hinstCabinet, this[1], &POLID_NoRun) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57156807>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57156807>::GetImpl'::`2'::impl) )
    {
      pvData = -1;
      dwProcessId = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows\\Run",
             L"ModernRunEnabled",
             0x10u,
             0,
             &pvData,
             &dwProcessId) )
      {
        RegGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced\\TaskbarDeveloperSettings",
          L"Run",
          0x10u,
          0,
          &pvData,
          &dwProcessId);
      }
      v4 = pvData;
      if ( pvData )
      {
        if ( pvData == 1 )
        {
LABEL_13:
          v5 = wil::details::heap_allocator::allocate(0x110u);
          v14[0] = v5;
          v5[33] = this;
          *v5 = CTray::_LaunchRunDialog__ResumeCoro_1;
          *((_DWORD *)v5 + 2) = 65538;
          *((_BYTE *)v5 + 256) = 0;
          CTray::_LaunchRunDialog__ResumeCoro_1(v5);
          return;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60846336>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60846336>::GetImpl'::`2'::impl) )
        {
          pvData = 1;
          goto LABEL_13;
        }
        v4 = 0;
        pvData = 0;
      }
      if ( v4 == 1 )
        goto LABEL_13;
    }
    v13 = 0;
    v6 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::ensure_data(&v13);
    tip2::details::shared_data<1,0,0>::start(*v6 + 8LL, v14);
    LoadStringW(g_hinstCabinet, 0x2D2u, Buffer, 260);
    WindowW = FindWindowW((LPCWSTR)0x8002, Buffer);
    v8 = WindowW;
    if ( WindowW
      && (dwProcessId = 0, GetWindowThreadProcessId(WindowW, &dwProcessId), dwProcessId == GetCurrentProcessId())
      && IsWindowVisible(v8) )
    {
      SetForegroundWindow(v8);
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::operator->(
                              &v13,
                              &pvData)
               + 273LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>(&pvData);
      tip2::tip_test<tip2::details::merged_data<_tip_GenericLogonTasksStartToUxShownTest,_tip_GenericLogonTasksStartToUxShownTest>>::complete(&v13);
    }
    else
    {
      v9 = (struct tagRECT *)wil::details::heap_allocator::allocate(0x10u);
      v10 = (struct tagPOINT *)v9;
      if ( v9 )
      {
        SetRectEmpty(v9);
        v10[1].x += 40;
        v10[1].y += 40;
        MapWindowPoints(this[1], 0, v10, 2u);
        if ( !SHCreateThread(CTray::RunDlgThreadProc, v10, 0x2008u, 0) )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::operator->(
                                  &v13,
                                  &dwProcessId)
                   + 274LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>(&dwProcessId);
          tip2::tip_test<tip2::details::merged_data<_tip_GenericLogonTasksStartToUxShownTest,_tip_GenericLogonTasksStartToUxShownTest>>::complete(&v13);
          operator delete(v10, 0x10u);
        }
      }
    }
    wil::com_ptr_t<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>,wil::err_returncode_policy>(&v13);
  }
}

```

## disassembly

```asm
0x140131140  push    rbp
0x140131142  push    rbx
0x140131143  push    rdi
0x140131144  push    r15
0x140131146  lea     rbp, [rsp-1A8h]
0x14013114e  sub     rsp, 2A8h
0x140131155  mov     rax, cs:__security_cookie
0x14013115c  xor     rax, rsp
0x14013115f  mov     [rbp+1C0h+var_30], rax
0x140131166  mov     rdi, rcx
0x140131169  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x140131170  jz      short loc_140131195
0x140131172  lea     rax, [rsp+2C0h+var_268]
0x140131177  mov     [rsp+2C0h+pdwType], rax
0x14013117c  mov     r9d, 1
0x140131182  lea     rdx, Explorer_StartMenu_RunDialog_Start
0x140131189  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140131190  call    McGenEventWrite_EventWriteTransfer
0x140131195  lea     r8, POLID_NoRun; struct _GUID *
0x14013119c  mov     rdx, [rdi+8]; HWND
0x1401311a0  mov     rcx, cs:g_hinstCabinet; HINSTANCE
0x1401311a7  call    ?_Restricted@@YAHPEAUHINSTANCE__@@PEAUHWND__@@AEBU_GUID@@@Z; _Restricted(HINSTANCE__ *,HWND__ *,_GUID const &)
0x1401311ac  test    eax, eax
0x1401311ae  jnz     loc_140131469
0x1401311b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57156807@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57156807@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57156807> `wil::Feature<__WilFeatureTraits_Feature_57156807>::GetImpl(void)'::`2'::impl
0x1401311bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57156807@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57156807>::__private_IsEnabled(void)
0x1401311c0  mov     r15d, 10h
0x1401311c6  test    al, al
0x1401311c8  jz      loc_1401312D3
0x1401311ce  mov     [rsp+2C0h+var_280], 0FFFFFFFFh
0x1401311d6  mov     [rsp+2C0h+dwProcessId], 4
0x1401311de  lea     rax, [rsp+2C0h+dwProcessId]
0x1401311e3  mov     [rsp+2C0h+pcbData], rax; pcbData
0x1401311e8  lea     rax, [rsp+2C0h+var_280]
0x1401311ed  mov     [rsp+2C0h+pvData], rax; pvData
0x1401311f2  mov     [rsp+2C0h+pdwType], 0; pdwType
0x1401311fb  mov     r9d, r15d; dwFlags
0x1401311fe  lea     r8, aModernrunenabl; "ModernRunEnabled"
0x140131205  lea     rdx, aSoftwarePolici_8; "Software\\Policies\\Microsoft\\Windows"...
0x14013120c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140131213  call    cs:__imp_RegGetValueW
0x14013121a  nop     dword ptr [rax+rax+00h]
0x14013121f  test    eax, eax
0x140131221  jz      short loc_140131264
0x140131223  lea     rax, [rsp+2C0h+dwProcessId]
0x140131228  mov     [rsp+2C0h+pcbData], rax; pcbData
0x14013122d  lea     rax, [rsp+2C0h+var_280]
0x140131232  mov     [rsp+2C0h+pvData], rax; pvData
0x140131237  mov     [rsp+2C0h+pdwType], 0; pdwType
0x140131240  mov     r9d, r15d; dwFlags
0x140131243  lea     r8, aRun; "Run"
0x14013124a  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140131251  mov     rcx, 0FFFFFFFF80000001h; hkey
0x140131258  call    cs:__imp_RegGetValueW
0x14013125f  nop     dword ptr [rax+rax+00h]
0x140131264  mov     eax, [rsp+2C0h+var_280]
0x140131268  test    eax, eax
0x14013126a  jz      short loc_140131291
0x14013126c  cmp     eax, 1
0x14013126f  jz      short loc_140131296
0x140131271  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60846336@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60846336@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60846336> `wil::Feature<__WilFeatureTraits_Feature_60846336>::GetImpl(void)'::`2'::impl
0x140131278  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60846336@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60846336>::__private_IsEnabled(void)
0x14013127d  test    al, al
0x14013127f  jz      short loc_14013128B
0x140131281  mov     [rsp+2C0h+var_280], 1
0x140131289  jmp     short loc_140131296
0x14013128b  xor     eax, eax
0x14013128d  mov     [rsp+2C0h+var_280], eax
0x140131291  cmp     eax, 1
0x140131294  jnz     short loc_1401312D3
0x140131296  mov     ecx, 110h; unsigned __int64
0x14013129b  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1401312a0  mov     [rsp+2C0h+var_268], rax
0x1401312a5  mov     [rax+108h], rdi
0x1401312ac  lea     rcx, CTray___LaunchRunDialog$_ResumeCoro$1
0x1401312b3  mov     [rax], rcx
0x1401312b6  mov     dword ptr [rax+8], 10002h
0x1401312bd  xor     ecx, ecx
0x1401312bf  mov     [rax+100h], cl
0x1401312c5  mov     rcx, rax; void *
0x1401312c8  call    CTray___LaunchRunDialog$_ResumeCoro$1
0x1401312cd  nop
0x1401312ce  jmp     loc_140131469
0x1401312d3  mov     [rsp+2C0h+var_270], 0
0x1401312dc  lea     rcx, [rsp+2C0h+var_270]
0x1401312e1  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::ensure_data(void)
0x1401312e6  mov     rcx, [rax]
0x1401312e9  add     rcx, 8
0x1401312ed  lea     rdx, [rsp+2C0h+var_268]
0x1401312f2  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1401312f7  mov     r9d, 104h; cchBufferMax
0x1401312fd  lea     r8, [rsp+2C0h+Buffer]; lpBuffer
0x140131302  mov     edx, 2D2h; uID
0x140131307  mov     rcx, cs:g_hinstCabinet; hInstance
0x14013130e  call    cs:__imp_LoadStringW
0x140131315  nop     dword ptr [rax+rax+00h]
0x14013131a  lea     rdx, [rsp+2C0h+Buffer]; lpWindowName
0x14013131f  mov     ecx, 8002h; lpClassName
0x140131324  call    cs:__imp_FindWindowW
0x14013132b  nop     dword ptr [rax+rax+00h]
0x140131330  mov     rbx, rax
0x140131333  test    rax, rax
0x140131336  jz      loc_1401313BE
0x14013133c  mov     [rsp+2C0h+dwProcessId], 0
0x140131344  lea     rdx, [rsp+2C0h+dwProcessId]; lpdwProcessId
0x140131349  mov     rcx, rax; hWnd
0x14013134c  call    cs:__imp_GetWindowThreadProcessId
0x140131353  nop     dword ptr [rax+rax+00h]
0x140131358  call    cs:__imp_GetCurrentProcessId
0x14013135f  nop     dword ptr [rax+rax+00h]
0x140131364  cmp     [rsp+2C0h+dwProcessId], eax
0x140131368  jnz     short loc_1401313BE
0x14013136a  mov     rcx, rbx; hWnd
0x14013136d  call    cs:__imp_IsWindowVisible
0x140131374  nop     dword ptr [rax+rax+00h]
0x140131379  test    eax, eax
0x14013137b  jz      short loc_1401313BE
0x14013137d  mov     rcx, rbx; hWnd
0x140131380  call    cs:__imp_SetForegroundWindow
0x140131387  nop     dword ptr [rax+rax+00h]
0x14013138c  lea     rdx, [rsp+2C0h+var_280]
0x140131391  lea     rcx, [rsp+2C0h+var_270]
0x140131396  call    ??C?$tip_test@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::operator->(void)
0x14013139b  mov     rcx, [rax]
0x14013139e  mov     byte ptr [rcx+111h], 1
0x1401313a5  lea     rcx, [rsp+2C0h+var_280]
0x1401313aa  call    ??1?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>(void)
0x1401313af  lea     rcx, [rsp+2C0h+var_270]
0x1401313b4  call    ?complete@?$tip_test@V?$merged_data@U_tip_GenericLogonTasksStartToUxShownTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_GenericLogonTasksStartToUxShownTest,_tip_GenericLogonTasksStartToUxShownTest>>::complete(void)
0x1401313b9  jmp     loc_14013145F
0x1401313be  mov     rcx, r15; unsigned __int64
0x1401313c1  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1401313c6  mov     rbx, rax
0x1401313c9  test    rax, rax
0x1401313cc  jz      loc_14013145F
0x1401313d2  mov     rcx, rax; lprc
0x1401313d5  call    cs:__imp_SetRectEmpty
0x1401313dc  nop     dword ptr [rax+rax+00h]
0x1401313e1  add     dword ptr [rbx+8], 28h ; '('
0x1401313e5  add     dword ptr [rbx+0Ch], 28h ; '('
0x1401313e9  mov     r9d, 2; cPoints
0x1401313ef  mov     r8, rbx; lpPoints
0x1401313f2  xor     edx, edx; hWndTo
0x1401313f4  mov     rcx, [rdi+8]; hWndFrom
0x1401313f8  call    cs:__imp_MapWindowPoints
0x1401313ff  nop     dword ptr [rax+rax+00h]
0x140131404  xor     r9d, r9d; pfnCallback
0x140131407  mov     r8d, 2008h; flags
0x14013140d  mov     rdx, rbx; pData
0x140131410  lea     rcx, ?RunDlgThreadProc@CTray@@KAKPEAX@Z; pfnThreadProc
0x140131417  call    cs:__imp_SHCreateThread
0x14013141e  nop     dword ptr [rax+rax+00h]
0x140131423  test    eax, eax
0x140131425  jnz     short loc_14013145F
0x140131427  lea     rdx, [rsp+2C0h+dwProcessId]
0x14013142c  lea     rcx, [rsp+2C0h+var_270]
0x140131431  call    ??C?$tip_test@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::operator->(void)
0x140131436  mov     rcx, [rax]
0x140131439  mov     byte ptr [rcx+112h], 1
0x140131440  lea     rcx, [rsp+2C0h+dwProcessId]
0x140131445  call    ??1?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>(void)
0x14013144a  lea     rcx, [rsp+2C0h+var_270]
0x14013144f  call    ?complete@?$tip_test@V?$merged_data@U_tip_GenericLogonTasksStartToUxShownTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_GenericLogonTasksStartToUxShownTest,_tip_GenericLogonTasksStartToUxShownTest>>::complete(void)
0x140131454  mov     rdx, r15; unsigned __int64
0x140131457  mov     rcx, rbx; void *
0x14013145a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14013145f  lea     rcx, [rsp+2C0h+var_270]
0x140131464  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>,wil::err_returncode_policy>(void)
0x140131469  mov     rcx, [rbp+1C0h+var_30]
0x140131470  xor     rcx, rsp; StackCookie
0x140131473  call    __security_check_cookie
0x140131478  add     rsp, 2A8h
0x14013147f  pop     r15
0x140131481  pop     rdi
0x140131482  pop     rbx
0x140131483  pop     rbp
0x140131484  retn
```
