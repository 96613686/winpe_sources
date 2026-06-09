# ServiceClient::Init(wchar_t const *,std::function<void (void)> &&,std::function<void (void)> &&)

- ea: `0x18008c6f0`
- end: `0x18008c7fb`
- name: `?Init@ServiceClient@@QEAAXPEB_W$$QEAV?$function@$$A6AXXZ@std@@1@Z`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800803c8`
- `0x1800dab44`
- `0x1801067f4`

## callees

- `0x1800307cc`
- `0x18008c6f0`
- `0x18008c804`
- `0x18008c99c`
- `0x18008ca6c`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008c748`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008c748`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008c70e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008c70e`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18008c7b5`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18008c7b5`

## string_xrefs

- `0x18008c728`: `onecore\net\netprofiles\service\src\common\serviceclient.cpp`
- `0x18008c765`: `onecore\net\netprofiles\service\src\common\serviceclient.cpp`
- `0x18008c7c7`: `onecore\net\netprofiles\service\src\common\serviceclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceClient::Init(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbx
  const char *v10; // r9
  unsigned int v11; // eax
  __int64 result; // rax
  wil *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+20h] [rbp-48h]
  SC_HANDLE v20; // [rsp+30h] [rbp-38h] BYREF
  SC_HANDLE v21[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = OpenSCManagerW(0, 0, 1u);
  try
  {
    v21[0] = v8;
    if ( !v8 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xA,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\serviceclient.cpp",
        (const char *)retaddr);
    v9 = OpenServiceW(v8, a2, 4u);
    v20 = v9;
    if ( !v9 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\serviceclient.cpp",
        v10);
    std::function<void (void)>::operator=(a1, a3);
    std::function<void (void)>::operator=(a1 + 64, a4);
    wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
      a1 + 128,
      0);
    v11 = SubscribeServiceChangeNotifications(v9, 2, ServiceClient::Init_::_3_::_lambda_1_::_lambda_invoker_cdecl_, a1);
    if ( v11 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\serviceclient.cpp",
        (const char *)v11,
        a1 + 128);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
    result = wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v21);
  }
  catch ( ... )
  {
    v16 = wil::ResultFromCaughtException(v13);
    if ( v16 != -2147023836 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v17, v18);
    return wil::details::in1diag3::Log_Hr(
             retaddr,
             (void *)0x32,
             (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\serviceclient.cpp",
             (const char *)v16,
             v19);
  }
  return result;
}

```

## disassembly

```asm
0x18008c6f0  push    rbx
0x18008c6f2  push    rsi
0x18008c6f3  push    rdi
0x18008c6f4  push    r14
0x18008c6f6  sub     rsp, 48h
0x18008c6fa  mov     r14, r9
0x18008c6fd  mov     rdi, r8
0x18008c700  mov     rbx, rdx
0x18008c703  mov     rsi, rcx
0x18008c706  xor     edx, edx; lpDatabaseName
0x18008c708  xor     ecx, ecx; lpMachineName
0x18008c70a  lea     r8d, [rdx+1]; dwDesiredAccess
0x18008c70e  call    cs:__imp_OpenSCManagerW
0x18008c714  mov     [rsp+68h+var_30], rax
0x18008c719  test    rax, rax
0x18008c71c  setz    cl
0x18008c71f  mov     r9, [rsp+68h]; char *
0x18008c724  test    cl, cl
0x18008c726  jz      short loc_18008C73C
0x18008c728  lea     r8, aOnecoreNetNetp_8; "onecore\\net\\netprofiles\\service\\src"...
0x18008c72f  mov     edx, 0Ah; void *
0x18008c734  mov     rcx, r9; this
0x18008c737  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008c73c  mov     r8d, 4; dwDesiredAccess
0x18008c742  mov     rdx, rbx; lpServiceName
0x18008c745  mov     rcx, rax; hSCManager
0x18008c748  call    cs:__imp_OpenServiceW
0x18008c74e  mov     rbx, rax
0x18008c751  mov     [rsp+68h+var_38], rax
0x18008c756  test    rax, rax
0x18008c759  setz    al
0x18008c75c  mov     rcx, [rsp+68h]; this
0x18008c761  test    al, al
0x18008c763  jz      short loc_18008C776
0x18008c765  lea     r8, aOnecoreNetNetp_8; "onecore\\net\\netprofiles\\service\\src"...
0x18008c76c  mov     edx, 0Dh; void *
0x18008c771  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008c776  mov     rdx, rdi
0x18008c779  mov     rcx, rsi
0x18008c77c  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18008c781  lea     rcx, [rsi+40h]
0x18008c785  mov     rdx, r14
0x18008c788  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18008c78d  lea     rdi, [rsi+80h]
0x18008c794  xor     edx, edx
0x18008c796  mov     rcx, rdi
0x18008c799  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x18008c79e  mov     qword ptr [rsp+68h+var_48], rdi; unsigned int
0x18008c7a3  mov     r9, rsi
0x18008c7a6  lea     r8, _ServiceClient__Init____3____lambda_1____lambda_invoker_cdecl_
0x18008c7ad  mov     edx, 2
0x18008c7b2  mov     rcx, rbx
0x18008c7b5  call    cs:__imp_SubscribeServiceChangeNotifications
0x18008c7bb  mov     rcx, [rsp+68h]; this
0x18008c7c0  test    eax, eax
0x18008c7c2  jz      short loc_18008C7D9
0x18008c7c4  mov     r9d, eax; char *
0x18008c7c7  lea     r8, aOnecoreNetNetp_8; "onecore\\net\\netprofiles\\service\\src"...
0x18008c7ce  mov     edx, 2Bh ; '+'; void *
0x18008c7d3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18008c7d8  nop
0x18008c7d9  lea     rcx, [rsp+68h+var_38]
0x18008c7de  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c7e3  nop
0x18008c7e4  lea     rcx, [rsp+68h+var_30]
0x18008c7e9  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c7ee  nop
0x18008c7ef  jmp     short $+2
0x18008c7f1  add     rsp, 48h
0x18008c7f5  pop     r14
0x18008c7f7  pop     rdi
0x18008c7f8  pop     rsi
0x18008c7f9  pop     rbx
0x18008c7fa  retn
```
