# ServiceTracking::Init(wchar_t const *,std::function<void (void)> &&,std::function<void (void)> &&)

- ea: `0x180033ba4`
- end: `0x180033ce2`
- name: `?Init@ServiceTracking@@QEAAJPEB_W$$QEAV?$function@$$A6AXXZ@std@@1@Z`
- size: `318`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800328e8`

## callees

- `0x18000c444`
- `0x1800303a0`
- `0x1800327bc`
- `0x180033ba4`
- `0x1800355b0`
- `0x18003672c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180033c09`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180033c09`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180033bc2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180033bc2`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180033c86`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180033c86`

## string_xrefs

- `0x180033bd7`: `OneCore\Private\Net\inc\ServiceTracking.h`
- `0x180033c21`: `OneCore\Private\Net\inc\ServiceTracking.h`

## pseudocode

```c
__int64 __fastcall ServiceTracking::Init(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  SC_HANDLE v7; // rax
  const char *v8; // r9
  unsigned int v9; // ebx
  SC_HANDLE v11; // rbx
  const char *v12; // r9
  unsigned int LastError; // ebx
  unsigned int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  unsigned int v18; // [rsp+20h] [rbp-38h]
  SC_HANDLE v19; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v20[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v7 = OpenSCManagerW(0, 0, 1u);
  v19 = v7;
  if ( v7 )
  {
    v11 = OpenServiceW(v7, L"nsi", 4u);
    v20[0] = v11;
    if ( v11 )
    {
      std::function<void (void)>::operator=(a1 + 8, a3);
      std::function<void (void)>::operator=(a1 + 72, a4);
      wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
        a1,
        0);
      v14 = SubscribeServiceChangeNotifications(
              v11,
              2,
              `ServiceTracking::Init'::`15'::_lambda_1_::_lambda_invoker_cdecl_,
              a1,
              a1);
      if ( v14 )
      {
        v17 = wil::details::in1diag3::Return_Win32(retaddr, v15, v16, (const char *)v14, v18);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v20);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
        return v17;
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v20);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
        return 0;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x19,
                    (unsigned int)"OneCore\\Private\\Net\\inc\\ServiceTracking.h",
                    v12);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v20);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
      return LastError;
    }
  }
  else
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x16,
           (unsigned int)"OneCore\\Private\\Net\\inc\\ServiceTracking.h",
           v8);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
    return v9;
  }
}

```

## disassembly

```asm
0x180033ba4  mov     [rsp+arg_8], rbx
0x180033ba9  push    rsi
0x180033baa  push    rdi
0x180033bab  push    r14
0x180033bad  sub     rsp, 40h
0x180033bb1  mov     r14, r9
0x180033bb4  mov     rsi, r8
0x180033bb7  mov     rdi, rcx
0x180033bba  xor     edx, edx; lpDatabaseName
0x180033bbc  xor     ecx, ecx; lpMachineName
0x180033bbe  lea     r8d, [rdx+1]; dwDesiredAccess
0x180033bc2  call    cs:__imp_OpenSCManagerW
0x180033bc8  mov     [rsp+58h+var_28], rax
0x180033bcd  test    rax, rax
0x180033bd0  jnz     short loc_180033BF9
0x180033bd2  mov     rcx, [rsp+58h]; this
0x180033bd7  lea     r8, aOnecorePrivate; "OneCore\\Private\\Net\\inc\\ServiceTrac"...
0x180033bde  lea     edx, [rax+16h]; void *
0x180033be1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033be6  mov     ebx, eax
0x180033be8  lea     rcx, [rsp+58h+var_28]
0x180033bed  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180033bf2  mov     eax, ebx
0x180033bf4  jmp     loc_180033CD3
0x180033bf9  mov     r8d, 4; dwDesiredAccess
0x180033bff  lea     rdx, aNsi; "nsi"
0x180033c06  mov     rcx, rax; hSCManager
0x180033c09  call    cs:__imp_OpenServiceW
0x180033c0f  mov     rbx, rax
0x180033c12  mov     [rsp+58h+var_20], rax
0x180033c17  test    rax, rax
0x180033c1a  jnz     short loc_180033C4D
0x180033c1c  mov     rcx, [rsp+58h]; this
0x180033c21  lea     r8, aOnecorePrivate; "OneCore\\Private\\Net\\inc\\ServiceTrac"...
0x180033c28  lea     edx, [rax+19h]; void *
0x180033c2b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033c30  mov     ebx, eax
0x180033c32  lea     rcx, [rsp+58h+var_20]
0x180033c37  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180033c3c  lea     rcx, [rsp+58h+var_28]
0x180033c41  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180033c46  mov     eax, ebx
0x180033c48  jmp     loc_180033CD3
0x180033c4d  lea     rcx, [rdi+8]
0x180033c51  mov     rdx, rsi
0x180033c54  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x180033c59  lea     rcx, [rdi+48h]
0x180033c5d  mov     rdx, r14
0x180033c60  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x180033c65  xor     edx, edx
0x180033c67  mov     rcx, rdi
0x180033c6a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x180033c6f  mov     qword ptr [rsp+58h+var_38], rdi; unsigned int
0x180033c74  mov     r9, rdi
0x180033c77  lea     r8, ?_lambda_invoker_cdecl_@_lambda_1_@?P@??Init@ServiceTracking@@QEAAJPEB_W$$QEAV?$function@$$A6AXXZ@std@@1@Z@SA@KPEAX@Z; `ServiceTracking::Init(wchar_t const *,std::function<void (void)> &&,std::function<void (void)> &&)'::`15'::_lambda_1_::_lambda_invoker_cdecl_(ulong,void *)
0x180033c7e  mov     edx, 2
0x180033c83  mov     rcx, rbx
0x180033c86  call    cs:__imp_SubscribeServiceChangeNotifications
0x180033c8c  test    eax, eax
0x180033c8e  jz      short loc_180033CB7
0x180033c90  mov     rcx, [rsp+58h]; this
0x180033c95  mov     r9d, eax; char *
0x180033c98  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033c9d  mov     ebx, eax
0x180033c9f  lea     rcx, [rsp+58h+var_20]
0x180033ca4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180033ca9  lea     rcx, [rsp+58h+var_28]
0x180033cae  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180033cb3  mov     eax, ebx
0x180033cb5  jmp     short loc_180033CD3
0x180033cb7  lea     rcx, [rsp+58h+var_20]
0x180033cbc  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180033cc1  lea     rcx, [rsp+58h+var_28]
0x180033cc6  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180033ccb  xor     eax, eax
0x180033ccd  jmp     short loc_180033CD3
0x180033ccf  mov     eax, dword ptr [rsp+58h+var_28]
0x180033cd3  mov     rbx, [rsp+58h+arg_8]
0x180033cd8  add     rsp, 40h
0x180033cdc  pop     r14
0x180033cde  pop     rdi
0x180033cdf  pop     rsi
0x180033ce0  retn
```
