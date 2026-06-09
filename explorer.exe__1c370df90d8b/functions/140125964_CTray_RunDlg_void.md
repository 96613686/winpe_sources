# CTray::_RunDlg(void)

- ea: `0x140125964`
- end: `0x140125c79`
- name: `?_RunDlg@CTray@@IEAAXXZ`
- size: `789`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400a5b40`
- `0x140123bbc`

## callees

- `0x140007048`
- `0x1400077d4`
- `0x14000a880`
- `0x14000d890`
- `0x1400b5e98`
- `0x1400d9fa4`
- `0x1400d9fdc`
- `0x1401040e0`
- `0x140104444`
- `0x14010bd44`
- `0x140115b14`
- `0x140125380`
- `0x140125964`
- `0x14012680c`
- `0x140126900`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140125b26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140125b26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140125b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140125b5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125a37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125a76`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125a37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125a76`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x140125c08`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x140125c08`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x140125bd2`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x140125bd2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x140125b69`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x140125b69`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x140125bef`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x140125bef`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140125b76`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetForegroundWindow` at `0x140125b76`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!FindWindowW` at `0x140125b36`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!FindWindowW` at `0x140125b36`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x140125b54`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x140125b54`

## string_xrefs

- `0x140125a68`: `Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced\TaskbarDeveloperSettings`

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
  _QWORD *v14; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[272]; // [rsp+70h] [rbp-90h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_StartMenu_RunDialog_Start,
      a3,
      1);
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
          v14 = v5;
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
    tip2::details::shared_data<1,0,0>::start(*v6 + 8LL, &v14);
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
      if ( v13 )
        tip2::details::shared_data<1,0,0>::complete_without_lock(v13 + 8);
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
          if ( v13 )
            tip2::details::shared_data<1,0,0>::complete_without_lock(v13 + 8);
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
0x140125964  push    rbp
0x140125966  push    rbx
0x140125967  push    rdi
0x140125968  push    r15
0x14012596a  lea     rbp, [rsp-1A8h]
0x140125972  sub     rsp, 2A8h
0x140125979  mov     rax, cs:__security_cookie
0x140125980  xor     rax, rsp
0x140125983  mov     [rbp+1C0h+var_30], rax
0x14012598a  mov     rdi, rcx
0x14012598d  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x140125994  jz      short loc_1401259B9
0x140125996  lea     rax, [rsp+2C0h+var_268]
0x14012599b  mov     [rsp+2C0h+pdwType], rax
0x1401259a0  mov     r9d, 1
0x1401259a6  lea     rdx, Explorer_StartMenu_RunDialog_Start
0x1401259ad  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1401259b4  call    McGenEventWrite_EventWriteTransfer
0x1401259b9  lea     r8, POLID_NoRun; struct _GUID *
0x1401259c0  mov     rdx, [rdi+8]; HWND
0x1401259c4  mov     rcx, cs:g_hinstCabinet; HINSTANCE
0x1401259cb  call    ?_Restricted@@YAHPEAUHINSTANCE__@@PEAUHWND__@@AEBU_GUID@@@Z; _Restricted(HINSTANCE__ *,HWND__ *,_GUID const &)
0x1401259d0  test    eax, eax
0x1401259d2  jnz     loc_140125C5D
0x1401259d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57156807@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57156807@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57156807> `wil::Feature<__WilFeatureTraits_Feature_57156807>::GetImpl(void)'::`2'::impl
0x1401259df  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57156807@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57156807>::__private_IsEnabled(void)
0x1401259e4  mov     r15d, 10h
0x1401259ea  test    al, al
0x1401259ec  jz      loc_140125AEB
0x1401259f2  mov     [rsp+2C0h+var_280], 0FFFFFFFFh
0x1401259fa  mov     [rsp+2C0h+dwProcessId], 4
0x140125a02  lea     rax, [rsp+2C0h+dwProcessId]
0x140125a07  mov     [rsp+2C0h+pcbData], rax; pcbData
0x140125a0c  lea     rax, [rsp+2C0h+var_280]
0x140125a11  mov     [rsp+2C0h+pvData], rax; pvData
0x140125a16  mov     [rsp+2C0h+pdwType], 0; pdwType
0x140125a1f  mov     r9d, r15d; dwFlags
0x140125a22  lea     r8, aModernrunenabl; "ModernRunEnabled"
0x140125a29  lea     rdx, aSoftwarePolici_8; "Software\\Policies\\Microsoft\\Windows"...
0x140125a30  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140125a37  call    cs:__imp_RegGetValueW
0x140125a3d  test    eax, eax
0x140125a3f  jz      short loc_140125A7C
0x140125a41  lea     rax, [rsp+2C0h+dwProcessId]
0x140125a46  mov     [rsp+2C0h+pcbData], rax; pcbData
0x140125a4b  lea     rax, [rsp+2C0h+var_280]
0x140125a50  mov     [rsp+2C0h+pvData], rax; pvData
0x140125a55  mov     [rsp+2C0h+pdwType], 0; pdwType
0x140125a5e  mov     r9d, r15d; dwFlags
0x140125a61  lea     r8, aRun; "Run"
0x140125a68  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140125a6f  mov     rcx, 0FFFFFFFF80000001h; hkey
0x140125a76  call    cs:__imp_RegGetValueW
0x140125a7c  mov     eax, [rsp+2C0h+var_280]
0x140125a80  test    eax, eax
0x140125a82  jz      short loc_140125AA9
0x140125a84  cmp     eax, 1
0x140125a87  jz      short loc_140125AAE
0x140125a89  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60846336@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60846336@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60846336> `wil::Feature<__WilFeatureTraits_Feature_60846336>::GetImpl(void)'::`2'::impl
0x140125a90  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60846336@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60846336>::__private_IsEnabled(void)
0x140125a95  test    al, al
0x140125a97  jz      short loc_140125AA3
0x140125a99  mov     [rsp+2C0h+var_280], 1
0x140125aa1  jmp     short loc_140125AAE
0x140125aa3  xor     eax, eax
0x140125aa5  mov     [rsp+2C0h+var_280], eax
0x140125aa9  cmp     eax, 1
0x140125aac  jnz     short loc_140125AEB
0x140125aae  mov     ecx, 110h; unsigned __int64
0x140125ab3  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x140125ab8  mov     [rsp+2C0h+var_268], rax
0x140125abd  mov     [rax+108h], rdi
0x140125ac4  lea     rcx, CTray___LaunchRunDialog$_ResumeCoro$1
0x140125acb  mov     [rax], rcx
0x140125ace  mov     dword ptr [rax+8], 10002h
0x140125ad5  xor     ecx, ecx
0x140125ad7  mov     [rax+100h], cl
0x140125add  mov     rcx, rax; void *
0x140125ae0  call    CTray___LaunchRunDialog$_ResumeCoro$1
0x140125ae5  nop
0x140125ae6  jmp     loc_140125C5D
0x140125aeb  mov     [rsp+2C0h+var_270], 0
0x140125af4  lea     rcx, [rsp+2C0h+var_270]
0x140125af9  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::ensure_data(void)
0x140125afe  mov     rcx, [rax]
0x140125b01  add     rcx, 8
0x140125b05  lea     rdx, [rsp+2C0h+var_268]
0x140125b0a  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x140125b0f  mov     r9d, 104h; cchBufferMax
0x140125b15  lea     r8, [rsp+2C0h+Buffer]; lpBuffer
0x140125b1a  mov     edx, 2D2h; uID
0x140125b1f  mov     rcx, cs:g_hinstCabinet; hInstance
0x140125b26  call    cs:__imp_LoadStringW
0x140125b2c  lea     rdx, [rsp+2C0h+Buffer]; lpWindowName
0x140125b31  mov     ecx, 8002h; lpClassName
0x140125b36  call    cs:__imp_FindWindowW
0x140125b3c  mov     rbx, rax
0x140125b3f  test    rax, rax
0x140125b42  jz      short loc_140125BBB
0x140125b44  mov     [rsp+2C0h+dwProcessId], 0
0x140125b4c  lea     rdx, [rsp+2C0h+dwProcessId]; lpdwProcessId
0x140125b51  mov     rcx, rax; hWnd
0x140125b54  call    cs:__imp_GetWindowThreadProcessId
0x140125b5a  call    cs:__imp_GetCurrentProcessId
0x140125b60  cmp     [rsp+2C0h+dwProcessId], eax
0x140125b64  jnz     short loc_140125BBB
0x140125b66  mov     rcx, rbx; hWnd
0x140125b69  call    cs:__imp_IsWindowVisible
0x140125b6f  test    eax, eax
0x140125b71  jz      short loc_140125BBB
0x140125b73  mov     rcx, rbx; hWnd
0x140125b76  call    cs:__imp_SetForegroundWindow
0x140125b7c  lea     rdx, [rsp+2C0h+var_280]
0x140125b81  lea     rcx, [rsp+2C0h+var_270]
0x140125b86  call    ??C?$tip_test@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::operator->(void)
0x140125b8b  mov     rcx, [rax]
0x140125b8e  mov     byte ptr [rcx+111h], 1
0x140125b95  lea     rcx, [rsp+2C0h+var_280]
0x140125b9a  call    ??1?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>(void)
0x140125b9f  mov     rcx, [rsp+2C0h+var_270]
0x140125ba4  test    rcx, rcx
0x140125ba7  jz      loc_140125C53
0x140125bad  add     rcx, 8
0x140125bb1  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x140125bb6  jmp     loc_140125C53
0x140125bbb  mov     rcx, r15; unsigned __int64
0x140125bbe  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x140125bc3  mov     rbx, rax
0x140125bc6  test    rax, rax
0x140125bc9  jz      loc_140125C53
0x140125bcf  mov     rcx, rax; lprc
0x140125bd2  call    cs:__imp_SetRectEmpty
0x140125bd8  add     dword ptr [rbx+8], 28h ; '('
0x140125bdc  add     dword ptr [rbx+0Ch], 28h ; '('
0x140125be0  mov     r9d, 2; cPoints
0x140125be6  mov     r8, rbx; lpPoints
0x140125be9  xor     edx, edx; hWndTo
0x140125beb  mov     rcx, [rdi+8]; hWndFrom
0x140125bef  call    cs:__imp_MapWindowPoints
0x140125bf5  xor     r9d, r9d; pfnCallback
0x140125bf8  mov     r8d, 2008h; flags
0x140125bfe  mov     rdx, rbx; pData
0x140125c01  lea     rcx, ?RunDlgThreadProc@CTray@@KAKPEAX@Z; pfnThreadProc
0x140125c08  call    cs:__imp_SHCreateThread
0x140125c0e  test    eax, eax
0x140125c10  jnz     short loc_140125C53
0x140125c12  lea     rdx, [rsp+2C0h+dwProcessId]
0x140125c17  lea     rcx, [rsp+2C0h+var_270]
0x140125c1c  call    ??C?$tip_test@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::operator->(void)
0x140125c21  mov     rcx, [rax]
0x140125c24  mov     byte ptr [rcx+112h], 1
0x140125c2b  lea     rcx, [rsp+2C0h+dwProcessId]
0x140125c30  call    ??1?$test_data_control@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>>(void)
0x140125c35  mov     rcx, [rsp+2C0h+var_270]
0x140125c3a  test    rcx, rcx
0x140125c3d  jz      short loc_140125C48
0x140125c3f  add     rcx, 8
0x140125c43  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x140125c48  mov     rdx, r15; unsigned __int64
0x140125c4b  mov     rcx, rbx; void *
0x140125c4e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140125c53  lea     rcx, [rsp+2C0h+var_270]
0x140125c58  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RunDialogLaunchTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RunDialogLaunchTipTest,_tip_RunDialogLaunchTipTest>,wil::err_returncode_policy>(void)
0x140125c5d  mov     rcx, [rbp+1C0h+var_30]
0x140125c64  xor     rcx, rsp; StackCookie
0x140125c67  call    __security_check_cookie
0x140125c6c  add     rsp, 2A8h
0x140125c73  pop     r15
0x140125c75  pop     rdi
0x140125c76  pop     rbx
0x140125c77  pop     rbp
0x140125c78  retn
```
