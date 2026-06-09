# SessionMonitor::InstanceThreadProc(void)

- ea: `0x1800999a0`
- end: `0x180099cac`
- name: `?InstanceThreadProc@SessionMonitor@@AEAAKXZ`
- size: `780`
- prototype: `unsigned int __fastcall(SessionMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f7aa0`

## callees

- `0x180057a9c`
- `0x18008dcac`
- `0x18008e194`
- `0x1800999a0`
- `0x180099cb4`
- `0x180099cec`
- `0x180099d3c`
- `0x180099d74`
- `0x180099dd4`
- `0x180099e20`
- `0x1800f08d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800999f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180099c7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800999f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180099c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ba8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180099ae9`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180099ae9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180099c60`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180099c60`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x180099a25`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x180099a25`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180099a82`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180099a82`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x180099c8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x180099c8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x180099c73`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x180099c73`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoW` at `0x180099a17`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoW` at `0x180099a17`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180099b38`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180099b38`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSRegisterSessionNotification` at `0x180099aab`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSRegisterSessionNotification` at `0x180099b9e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSRegisterSessionNotification` at `0x180099aab`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSRegisterSessionNotification` at `0x180099b9e`

## string_xrefs

- `0x180099ad7`: `Global\TermSrvReadyEvent`

## pseudocode

```c
__int64 __fastcall SessionMonitor::InstanceThreadProc(SessionMonitor *this)
{
  struct SessionMonitor *v1; // rbx
  const char *v2; // r9
  HWND Window; // rax
  const char *v4; // r9
  HANDLE v5; // rax
  const char *v6; // r9
  DWORD v7; // eax
  signed int LastError; // ebx
  HMODULE ModuleHandleW; // rax
  int X; // [rsp+20h] [rbp-E0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-A0h] BYREF
  MSG Msg; // [rsp+70h] [rbp-90h] BYREF
  WNDCLASSW hInstance; // [rsp+A0h] [rbp-60h] BYREF
  tagWNDCLASSW WndClass; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  SessionMonitor *v17; // [rsp+170h] [rbp+70h] BYREF
  void *v18; // [rsp+178h] [rbp+78h] BYREF
  char v19; // [rsp+180h] [rbp+80h] BYREF
  __int64 v20; // [rsp+188h] [rbp+88h] BYREF

  v17 = this;
  v1 = SessionMonitor::_instance;
  v20 = 0;
  memset_0(&hInstance, 0, sizeof(hInstance));
  memset_0(&WndClass, 0, sizeof(WndClass));
  hInstance.cbWndExtra = 8;
  hInstance.lpfnWndProc = (WNDPROC)SessionMonitor::WndProc;
  hInstance.hInstance = GetModuleHandleW(0);
  hInstance.lpszClassName = L"SessionMonitorWindow";
  if ( !GetClassInfoW(hInstance.hInstance, L"SessionMonitorWindow", &WndClass) && !RegisterClassW(&hInstance) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\sessionmonitor.cpp",
      v2);
  Window = CreateWindowExW(
             0,
             hInstance.lpszClassName,
             &WindowName,
             0,
             0,
             0,
             0,
             0,
             HWND_MESSAGE,
             0,
             hInstance.hInstance,
             0);
  *(_QWORD *)v1 = Window;
  if ( !Window )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\sessionmonitor.cpp",
      v4);
  if ( WTSRegisterSessionNotification(Window, 0) )
  {
    tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>>(&v17);
    tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::complete(&v17);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>(&v17);
    goto LABEL_23;
  }
  if ( GetLastError() == 1702 || GetLastError() == 1722 )
  {
    v18 = 0;
    v5 = OpenEventW(0x100000u, 0, L"Global\\TermSrvReadyEvent");
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v18,
      v5);
    if ( !v18 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD3,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\sessionmonitor.cpp",
        v6);
    Handles[0] = v18;
    Handles[1] = *((HANDLE *)v1 + 3);
    v7 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v7 )
    {
      if ( v7 != 1 )
      {
        if ( v7 != -1 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0xFD,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\sessionmonitor.cpp",
            (const char *)0x8000FFFFLL,
            X);
        LastError = GetLastError();
        tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>>(&v17);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::operator->(
                                &v17,
                                &v19)
                 + 272LL) = 1;
        goto LABEL_18;
      }
    }
    else if ( !WTSRegisterSessionNotification(*(HWND *)v1, 0) )
    {
      LastError = GetLastError();
      tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>>(&v17);
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::operator->(
                              &v17,
                              &v19)
               + 273LL) = 1;
LABEL_18:
      tip2::test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>(&v19);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::operator->(
                               &v17,
                               &v19)
                + 276LL) = LastError;
      tip2::test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>(&v19);
      tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::complete(&v17);
      wil::com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>(&v17);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
  }
LABEL_23:
  memset(&Msg, 0, sizeof(Msg));
  while ( GetMessageW(&Msg, 0, 0, 0) )
    DispatchMessageW(&Msg);
  ModuleHandleW = GetModuleHandleW(0);
  UnregisterClassW(L"SessionMonitorWindow", ModuleHandleW);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return 0;
}

```

## disassembly

```asm
0x1800999a0  mov     [rsp-8+arg_0], rcx
0x1800999a5  push    rbp
0x1800999a6  push    rbx
0x1800999a7  push    rsi
0x1800999a8  push    r14
0x1800999aa  lea     rbp, [rsp-48h]
0x1800999af  sub     rsp, 148h
0x1800999b6  mov     rbx, cs:?_instance@SessionMonitor@@0PEAV1@EA; SessionMonitor * SessionMonitor::_instance
0x1800999bd  lea     rcx, [rbp+60h+var_C0]; void *
0x1800999c1  xor     esi, esi
0x1800999c3  xor     edx, edx; Val
0x1800999c5  mov     [rbp+60h+arg_18], rsi
0x1800999cc  lea     r8d, [rsi+48h]; Size
0x1800999d0  call    memset_0
0x1800999d5  xor     edx, edx; Val
0x1800999d7  lea     r8d, [rsi+48h]; Size
0x1800999db  lea     rcx, [rbp+60h+WndClass]; void *
0x1800999df  call    memset_0
0x1800999e4  lea     rax, ?WndProc@SessionMonitor@@CA_JPEAUHWND__@@I_K_J@Z; SessionMonitor::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800999eb  mov     [rbp+60h+var_C0.cbWndExtra], 8
0x1800999f2  xor     ecx, ecx; lpModuleName
0x1800999f4  mov     [rbp+60h+var_C0.lpfnWndProc], rax
0x1800999f8  call    cs:__imp_GetModuleHandleW
0x1800999fe  lea     r14, ClassName; "SessionMonitorWindow"
0x180099a05  mov     [rbp+60h+var_C0.hInstance], rax
0x180099a09  mov     rdx, r14; lpClassName
0x180099a0c  mov     [rbp+60h+var_C0.lpszClassName], r14
0x180099a10  mov     rcx, rax; hInstance
0x180099a13  lea     r8, [rbp+60h+WndClass]; lpWndClass
0x180099a17  call    cs:__imp_GetClassInfoW
0x180099a1d  test    eax, eax
0x180099a1f  jnz     short loc_180099A46
0x180099a21  lea     rcx, [rbp+60h+var_C0]; lpWndClass
0x180099a25  call    cs:__imp_RegisterClassW
0x180099a2b  test    ax, ax
0x180099a2e  jnz     short loc_180099A46
0x180099a30  mov     rcx, [rbp+68h]; this
0x180099a34  lea     r8, aOnecoreuapWind_159; "onecoreuap\\windows\\moderncore\\inputv"...
0x180099a3b  mov     edx, 0B8h; void *
0x180099a40  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180099a46  mov     rax, [rbp+60h+var_C0.hInstance]
0x180099a4a  lea     r8, WindowName; lpWindowName
0x180099a51  mov     rdx, [rbp+60h+var_C0.lpszClassName]; lpClassName
0x180099a55  xor     r9d, r9d; dwStyle
0x180099a58  mov     [rsp+160h+lpParam], rsi; lpParam
0x180099a5d  xor     ecx, ecx; dwExStyle
0x180099a5f  mov     [rsp+160h+hInstance], rax; hInstance
0x180099a64  mov     [rsp+160h+hMenu], rsi; hMenu
0x180099a69  mov     [rsp+160h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x180099a72  mov     [rsp+160h+nHeight], esi; nHeight
0x180099a76  mov     [rsp+160h+nWidth], esi; nWidth
0x180099a7a  mov     [rsp+160h+Y], esi; Y
0x180099a7e  mov     [rsp+160h+X], esi; int
0x180099a82  call    cs:__imp_CreateWindowExW
0x180099a88  mov     [rbx], rax
0x180099a8b  test    rax, rax
0x180099a8e  jnz     short loc_180099AA6
0x180099a90  mov     rcx, [rbp+68h]; this
0x180099a94  lea     r8, aOnecoreuapWind_159; "onecoreuap\\windows\\moderncore\\inputv"...
0x180099a9b  mov     edx, 0C7h; void *
0x180099aa0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180099aa6  xor     edx, edx; dwFlags
0x180099aa8  mov     rcx, rax; hWnd
0x180099aab  call    cs:__imp_WTSRegisterSessionNotification
0x180099ab1  test    eax, eax
0x180099ab3  jnz     loc_180099C2E
0x180099ab9  call    cs:__imp_GetLastError
0x180099abf  cmp     eax, 6A6h
0x180099ac4  jz      short loc_180099AD7
0x180099ac6  call    cs:__imp_GetLastError
0x180099acc  cmp     eax, 6BAh
0x180099ad1  jnz     loc_180099C49
0x180099ad7  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x180099ade  mov     [rbp+60h+arg_8], rsi
0x180099ae2  xor     edx, edx; bInheritHandle
0x180099ae4  mov     ecx, 100000h; dwDesiredAccess
0x180099ae9  call    cs:__imp_OpenEventW
0x180099aef  mov     rdx, rax
0x180099af2  lea     rcx, [rbp+60h+arg_8]
0x180099af6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180099afb  mov     rax, [rbp+60h+arg_8]
0x180099aff  test    rax, rax
0x180099b02  jnz     short loc_180099B1A
0x180099b04  mov     rcx, [rbp+68h]; this
0x180099b08  lea     r8, aOnecoreuapWind_159; "onecoreuap\\windows\\moderncore\\inputv"...
0x180099b0f  mov     edx, 0D3h; void *
0x180099b14  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180099b1a  xor     r8d, r8d; bWaitAll
0x180099b1d  mov     [rsp+160h+Handles], rax
0x180099b22  mov     rax, [rbx+18h]
0x180099b26  lea     rdx, [rsp+160h+Handles]; lpHandles
0x180099b2b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180099b2f  mov     [rsp+160h+var_F8], rax
0x180099b34  lea     ecx, [r8+2]; nCount
0x180099b38  call    cs:__imp_WaitForMultipleObjects
0x180099b3e  test    eax, eax
0x180099b40  jz      short loc_180099B99
0x180099b42  cmp     eax, 1
0x180099b45  jz      loc_180099C23
0x180099b4b  cmp     eax, 0FFFFFFFFh
0x180099b4e  jz      short loc_180099B6C
0x180099b50  mov     rcx, [rbp+68h]; this
0x180099b54  lea     r8, aOnecoreuapWind_159; "onecoreuap\\windows\\moderncore\\inputv"...
0x180099b5b  mov     r9d, 8000FFFFh; char *
0x180099b61  mov     edx, 0FDh; void *
0x180099b66  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180099b6c  call    cs:__imp_GetLastError
0x180099b72  lea     rcx, [rbp+60h+arg_0]
0x180099b76  mov     ebx, eax
0x180099b78  call    ??$start@V?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>>(void)
0x180099b7d  lea     rdx, [rbp+60h+arg_10]
0x180099b84  lea     rcx, [rbp+60h+arg_0]
0x180099b88  call    ??C?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::operator->(void)
0x180099b8d  mov     rcx, [rax]
0x180099b90  mov     byte ptr [rcx+110h], 1
0x180099b97  jmp     short loc_180099BD3
0x180099b99  mov     rcx, [rbx]; hWnd
0x180099b9c  xor     edx, edx; dwFlags
0x180099b9e  call    cs:__imp_WTSRegisterSessionNotification
0x180099ba4  test    eax, eax
0x180099ba6  jnz     short loc_180099C23
0x180099ba8  call    cs:__imp_GetLastError
0x180099bae  lea     rcx, [rbp+60h+arg_0]
0x180099bb2  mov     ebx, eax
0x180099bb4  call    ??$start@V?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>>(void)
0x180099bb9  lea     rdx, [rbp+60h+arg_10]
0x180099bc0  lea     rcx, [rbp+60h+arg_0]
0x180099bc4  call    ??C?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::operator->(void)
0x180099bc9  mov     rcx, [rax]
0x180099bcc  mov     byte ptr [rcx+111h], 1
0x180099bd3  lea     rcx, [rbp+60h+arg_10]
0x180099bda  call    ??1?$test_data_control@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>(void)
0x180099bdf  test    ebx, ebx
0x180099be1  jle     short loc_180099BEC
0x180099be3  movzx   ebx, bx
0x180099be6  or      ebx, 80070000h
0x180099bec  lea     rdx, [rbp+60h+arg_10]
0x180099bf3  lea     rcx, [rbp+60h+arg_0]
0x180099bf7  call    ??C?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::operator->(void)
0x180099bfc  mov     rcx, [rax]
0x180099bff  mov     [rcx+114h], ebx
0x180099c05  lea     rcx, [rbp+60h+arg_10]
0x180099c0c  call    ??1?$test_data_control@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>(void)
0x180099c11  lea     rcx, [rbp+60h+arg_0]
0x180099c15  call    ?complete@?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::complete(void)
0x180099c1a  lea     rcx, [rbp+60h+arg_0]
0x180099c1e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>(void)
0x180099c23  lea     rcx, [rbp+60h+arg_8]
0x180099c27  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180099c2c  jmp     short loc_180099C49
0x180099c2e  lea     rcx, [rbp+60h+arg_0]
0x180099c32  call    ??$start@V?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>>(void)
0x180099c37  lea     rcx, [rbp+60h+arg_0]
0x180099c3b  call    ?complete@?$tip_test@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>>::complete(void)
0x180099c40  lea     rcx, [rbp+60h+arg_0]
0x180099c44  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ISMSessionMonitorCreationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ISMSessionMonitorCreationTipTest,_tip_ISMSessionMonitorCreationTipTest>,wil::err_returncode_policy>(void)
0x180099c49  xorps   xmm0, xmm0
0x180099c4c  movups  xmmword ptr [rsp+160h+Msg.hwnd], xmm0
0x180099c51  movups  xmmword ptr [rbp+60h+Msg.wParam], xmm0
0x180099c55  movups  xmmword ptr [rbp+60h+Msg.time], xmm0
0x180099c59  jmp     short loc_180099C66
0x180099c5b  lea     rcx, [rsp+160h+Msg]; lpMsg
0x180099c60  call    cs:__imp_DispatchMessageW
0x180099c66  xor     r9d, r9d; wMsgFilterMax
0x180099c69  lea     rcx, [rsp+160h+Msg]; lpMsg
0x180099c6e  xor     r8d, r8d; wMsgFilterMin
0x180099c71  xor     edx, edx; hWnd
0x180099c73  call    cs:__imp_GetMessageW
0x180099c79  test    eax, eax
0x180099c7b  jnz     short loc_180099C5B
0x180099c7d  xor     ecx, ecx; lpModuleName
0x180099c7f  call    cs:__imp_GetModuleHandleW
0x180099c85  mov     rdx, rax; hInstance
0x180099c88  mov     rcx, r14; lpClassName
0x180099c8b  call    cs:__imp_UnregisterClassW
0x180099c91  lea     rcx, [rbp+60h+arg_18]
0x180099c98  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180099c9d  xor     eax, eax
0x180099c9f  add     rsp, 148h
0x180099ca6  pop     r14
0x180099ca8  pop     rsi
0x180099ca9  pop     rbx
0x180099caa  pop     rbp
0x180099cab  retn
```
