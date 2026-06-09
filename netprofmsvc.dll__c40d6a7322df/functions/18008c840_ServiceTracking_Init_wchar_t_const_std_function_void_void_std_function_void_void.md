# ServiceTracking::Init(wchar_t const *,std::function<void (void)> &&,std::function<void (void)> &&)

- ea: `0x18008c840`
- end: `0x18008c98a`
- name: `?Init@ServiceTracking@@QEAAJPEB_W$$QEAV?$function@$$A6AXXZ@std@@1@Z`
- size: `330`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18010432c`

## callees

- `0x18005530c`
- `0x18008c804`
- `0x18008c840`
- `0x18008c99c`
- `0x18008c9bc`
- `0x18008ca6c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008c8a5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008c8a5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008c85e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008c85e`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18008c922`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18008c922`

## string_xrefs

- `0x18008c873`: `onecore\net\inc\ServiceTracking.h`
- `0x18008c8bd`: `onecore\net\inc\ServiceTracking.h`
- `0x18008c934`: `onecore\net\inc\ServiceTracking.h`

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
  unsigned int v15; // ebx
  SC_HANDLE v16; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v17[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v7 = OpenSCManagerW(0, 0, 1u);
  v16 = v7;
  if ( v7 )
  {
    v11 = OpenServiceW(v7, L"nsi", 4u);
    v17[0] = v11;
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
              a1);
      if ( v14 )
      {
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x37,
                (unsigned int)"onecore\\net\\inc\\ServiceTracking.h",
                (const char *)v14,
                a1);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v17);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
        return v15;
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v17);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
        return 0;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x19,
                    (unsigned int)"onecore\\net\\inc\\ServiceTracking.h",
                    v12);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v17);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
      return LastError;
    }
  }
  else
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x16,
           (unsigned int)"onecore\\net\\inc\\ServiceTracking.h",
           v8);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
    return v9;
  }
}

```

## disassembly

```asm
0x18008c840  mov     [rsp+arg_8], rbx
0x18008c845  push    rsi
0x18008c846  push    rdi
0x18008c847  push    r14
0x18008c849  sub     rsp, 40h
0x18008c84d  mov     r14, r9
0x18008c850  mov     rsi, r8
0x18008c853  mov     rdi, rcx
0x18008c856  xor     edx, edx; lpDatabaseName
0x18008c858  xor     ecx, ecx; lpMachineName
0x18008c85a  lea     r8d, [rdx+1]; dwDesiredAccess
0x18008c85e  call    cs:__imp_OpenSCManagerW
0x18008c864  mov     [rsp+58h+var_28], rax
0x18008c869  test    rax, rax
0x18008c86c  jnz     short loc_18008C895
0x18008c86e  mov     rcx, [rsp+58h]; this
0x18008c873  lea     r8, aOnecoreNetIncS; "onecore\\net\\inc\\ServiceTracking.h"
0x18008c87a  lea     edx, [rax+16h]; void *
0x18008c87d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008c882  mov     ebx, eax
0x18008c884  lea     rcx, [rsp+58h+var_28]
0x18008c889  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c88e  mov     eax, ebx
0x18008c890  jmp     loc_18008C97B
0x18008c895  mov     r8d, 4; dwDesiredAccess
0x18008c89b  lea     rdx, aNsi; "nsi"
0x18008c8a2  mov     rcx, rax; hSCManager
0x18008c8a5  call    cs:__imp_OpenServiceW
0x18008c8ab  mov     rbx, rax
0x18008c8ae  mov     [rsp+58h+var_20], rax
0x18008c8b3  test    rax, rax
0x18008c8b6  jnz     short loc_18008C8E9
0x18008c8b8  mov     rcx, [rsp+58h]; this
0x18008c8bd  lea     r8, aOnecoreNetIncS; "onecore\\net\\inc\\ServiceTracking.h"
0x18008c8c4  lea     edx, [rax+19h]; void *
0x18008c8c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008c8cc  mov     ebx, eax
0x18008c8ce  lea     rcx, [rsp+58h+var_20]
0x18008c8d3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c8d8  lea     rcx, [rsp+58h+var_28]
0x18008c8dd  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c8e2  mov     eax, ebx
0x18008c8e4  jmp     loc_18008C97B
0x18008c8e9  lea     rcx, [rdi+8]
0x18008c8ed  mov     rdx, rsi
0x18008c8f0  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18008c8f5  lea     rcx, [rdi+48h]
0x18008c8f9  mov     rdx, r14
0x18008c8fc  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18008c901  xor     edx, edx
0x18008c903  mov     rcx, rdi
0x18008c906  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x18008c90b  mov     qword ptr [rsp+58h+var_38], rdi; unsigned int
0x18008c910  mov     r9, rdi
0x18008c913  lea     r8, ?_lambda_invoker_cdecl_@_lambda_1_@?P@??Init@ServiceTracking@@QEAAJPEB_W$$QEAV?$function@$$A6AXXZ@std@@1@Z@SA@KPEAX@Z; `ServiceTracking::Init(wchar_t const *,std::function<void (void)> &&,std::function<void (void)> &&)'::`15'::_lambda_1_::_lambda_invoker_cdecl_(ulong,void *)
0x18008c91a  mov     edx, 2
0x18008c91f  mov     rcx, rbx
0x18008c922  call    cs:__imp_SubscribeServiceChangeNotifications
0x18008c928  test    eax, eax
0x18008c92a  jz      short loc_18008C95F
0x18008c92c  mov     rcx, [rsp+58h]; this
0x18008c931  mov     r9d, eax; char *
0x18008c934  lea     r8, aOnecoreNetIncS; "onecore\\net\\inc\\ServiceTracking.h"
0x18008c93b  mov     edx, 37h ; '7'; void *
0x18008c940  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008c945  mov     ebx, eax
0x18008c947  lea     rcx, [rsp+58h+var_20]
0x18008c94c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c951  lea     rcx, [rsp+58h+var_28]
0x18008c956  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c95b  mov     eax, ebx
0x18008c95d  jmp     short loc_18008C97B
0x18008c95f  lea     rcx, [rsp+58h+var_20]
0x18008c964  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c969  lea     rcx, [rsp+58h+var_28]
0x18008c96e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008c973  xor     eax, eax
0x18008c975  jmp     short loc_18008C97B
0x18008c977  mov     eax, dword ptr [rsp+58h+var_28]
0x18008c97b  mov     rbx, [rsp+58h+arg_8]
0x18008c980  add     rsp, 40h
0x18008c984  pop     r14
0x18008c986  pop     rdi
0x18008c987  pop     rsi
0x18008c988  retn
```
