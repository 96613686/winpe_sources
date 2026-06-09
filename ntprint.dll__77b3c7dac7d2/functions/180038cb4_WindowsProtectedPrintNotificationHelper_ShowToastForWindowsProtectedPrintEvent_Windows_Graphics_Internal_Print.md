# WindowsProtectedPrintNotificationHelper::ShowToastForWindowsProtectedPrintEvent(Windows::Graphics::Internal::Printing::WindowsProtectedPrint::NotificationType)

- ea: `0x180038cb4`
- end: `0x180038dff`
- name: `?ShowToastForWindowsProtectedPrintEvent@WindowsProtectedPrintNotificationHelper@@YAJW4NotificationType@WindowsProtectedPrint@Printing@Internal@Graphics@Windows@@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014cf8`

## callees

- `0x180002300`
- `0x180007478`
- `0x180038a58`
- `0x180038abc`
- `0x180038c9c`
- `0x180038cb4`
- `0x18003a010`

## import_xrefs

- `combase!__imp_RoGetActivationFactoryAsUser` at `0x180038d78`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x180038d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038d57`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180038cd4`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180038cd4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180038dc4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180038dd8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180038dc4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180038dd8`

## pseudocode

```c
__int64 WindowsProtectedPrintNotificationHelper::ShowToastForWindowsProtectedPrintEvent()
{
  int v0; // eax
  unsigned __int64 *v1; // rdx
  unsigned int v2; // ebx
  int ActiveUserContext; // eax
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactoryAsUser; // eax
  __int64 v9; // rdx
  __int64 v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v0 = RoInitialize(1);
  v2 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"printscan\\print\\shared\\windowsprotectedprintnotificationhelper\\windowsprotectedprintnotificationhelper.cpp",
      (const char *)(unsigned int)v0,
      v10);
    return v2;
  }
  v11 = 0;
  ActiveUserContext = WindowsProtectedPrintNotificationHelper::GetActiveUserContext(
                        (WindowsProtectedPrintNotificationHelper *)&v11,
                        v1);
  v2 = ActiveUserContext;
  if ( ActiveUserContext < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"printscan\\print\\shared\\windowsprotectedprintnotificationhelper\\windowsprotectedprintnotificationhelper.cpp",
      (const char *)(unsigned int)ActiveUserContext,
      v10);
LABEL_12:
    RoUninitialize();
    return v2;
  }
  v10 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Graphics.Internal.Printing.WindowsProtectedPrint.WindowsProtectedPrintHandler",
         0x55u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    JUMPOUT(0x180038DFELL);
  }
  ActivationFactoryAsUser = RoGetActivationFactoryAsUser(string, v11, &GUID_7ac8868e_92c0_5ba4_86a4_0338dd098359, &v10);
  v2 = ActivationFactoryAsUser;
  if ( ActivationFactoryAsUser < 0 )
  {
    v9 = 77;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"printscan\\print\\shared\\windowsprotectedprintnotificationhelper\\windowsprotectedprintnotificationhelper.cpp",
      (const char *)(unsigned int)ActivationFactoryAsUser,
      v10);
    wil::com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>(&v10);
    goto LABEL_12;
  }
  ActivationFactoryAsUser = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 48LL))(v10, 0);
  v2 = ActivationFactoryAsUser;
  if ( ActivationFactoryAsUser < 0 )
  {
    v9 = 78;
    goto LABEL_11;
  }
  wil::com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>(&v10);
  RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180038cb4  mov     [rsp-8+arg_0], rbx
0x180038cb9  push    rbp
0x180038cba  mov     rbp, rsp
0x180038cbd  sub     rsp, 60h
0x180038cc1  mov     rax, cs:__security_cookie
0x180038cc8  xor     rax, rsp
0x180038ccb  mov     [rbp+var_10], rax
0x180038ccf  mov     ecx, 1
0x180038cd4  call    cs:__imp_RoInitialize
0x180038cda  mov     ebx, eax
0x180038cdc  test    eax, eax
0x180038cde  jns     short loc_180038CFF
0x180038ce0  mov     rcx, [rbp+8]; this
0x180038ce4  lea     r8, aPrintscanPrint; "printscan\\print\\shared\\windowsprotec"...
0x180038ceb  mov     r9d, eax; char *
0x180038cee  mov     edx, 40h ; '@'; void *
0x180038cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038cf8  mov     eax, ebx
0x180038cfa  jmp     loc_180038DE0
0x180038cff  lea     rcx, [rbp+var_38]; this
0x180038d03  mov     [rbp+var_38], 0
0x180038d0b  call    ?GetActiveUserContext@WindowsProtectedPrintNotificationHelper@@YAJPEA_K@Z; WindowsProtectedPrintNotificationHelper::GetActiveUserContext(unsigned __int64 *)
0x180038d10  mov     ebx, eax
0x180038d12  test    eax, eax
0x180038d14  jns     short loc_180038D33
0x180038d16  mov     rcx, [rbp+8]; this
0x180038d1a  lea     r8, aPrintscanPrint; "printscan\\print\\shared\\windowsprotec"...
0x180038d21  mov     r9d, eax; char *
0x180038d24  mov     edx, 47h ; 'G'; void *
0x180038d29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038d2e  jmp     loc_180038DC4
0x180038d33  lea     r9, [rbp+string]; string
0x180038d37  mov     [rbp+var_40], 0
0x180038d3f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180038d43  mov     [rbp+string], 0
0x180038d4b  mov     edx, 55h ; 'U'; length
0x180038d50  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_WindowsProtectedPrint_WindowsProtectedPrintHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Wind"...
0x180038d57  call    cs:__imp_WindowsCreateStringReference
0x180038d5d  test    eax, eax
0x180038d5f  js      loc_180038DF7
0x180038d65  mov     rdx, [rbp+var_38]
0x180038d69  lea     r9, [rbp+var_40]
0x180038d6d  mov     rcx, [rbp+string]
0x180038d71  lea     r8, _GUID_7ac8868e_92c0_5ba4_86a4_0338dd098359
0x180038d78  call    cs:__imp_RoGetActivationFactoryAsUser
0x180038d7e  mov     ebx, eax
0x180038d80  test    eax, eax
0x180038d82  jns     short loc_180038D8B
0x180038d84  mov     edx, 4Dh ; 'M'
0x180038d89  jmp     short loc_180038DA8
0x180038d8b  mov     rcx, [rbp+var_40]
0x180038d8f  xor     edx, edx
0x180038d91  mov     rax, [rcx]
0x180038d94  mov     rax, [rax+30h]
0x180038d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d9d  mov     ebx, eax
0x180038d9f  test    eax, eax
0x180038da1  jns     short loc_180038DCF
0x180038da3  mov     edx, 4Eh ; 'N'; void *
0x180038da8  mov     rcx, [rbp+8]; this
0x180038dac  lea     r8, aPrintscanPrint; "printscan\\print\\shared\\windowsprotec"...
0x180038db3  mov     r9d, eax; char *
0x180038db6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038dbb  lea     rcx, [rbp+var_40]
0x180038dbf  call    ??1?$com_ptr_t@UIWindowsProtectedPrintHandlerStatics@WindowsProtectedPrint@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>(void)
0x180038dc4  call    cs:__imp_RoUninitialize
0x180038dca  jmp     loc_180038CF8
0x180038dcf  lea     rcx, [rbp+var_40]
0x180038dd3  call    ??1?$com_ptr_t@UIWindowsProtectedPrintHandlerStatics@WindowsProtectedPrint@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Internal::Printing::WindowsProtectedPrint::IWindowsProtectedPrintHandlerStatics,wil::err_returncode_policy>(void)
0x180038dd8  call    cs:__imp_RoUninitialize
0x180038dde  xor     eax, eax
0x180038de0  mov     rcx, [rbp+var_10]
0x180038de4  xor     rcx, rsp; StackCookie
0x180038de7  call    __security_check_cookie
0x180038dec  mov     rbx, [rsp+60h+arg_0]
0x180038df1  add     rsp, 60h
0x180038df5  pop     rbp
0x180038df6  retn
0x180038df7  mov     ecx, eax; this
0x180038df9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
