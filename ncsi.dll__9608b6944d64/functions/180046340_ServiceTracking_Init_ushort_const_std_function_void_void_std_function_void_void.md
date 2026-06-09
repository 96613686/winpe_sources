# ServiceTracking::Init(ushort const *,std::function<void (void)> &&,std::function<void (void)> &&)

- ea: `0x180046340`
- end: `0x1800464bf`
- name: `?Init@ServiceTracking@@QEAAJPEBG$$QEAV?$function@$$A6AXXZ@std@@1@Z`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180050300`

## callees

- `0x18002cd60`
- `0x18002e70c`
- `0x18003fa18`
- `0x18003fa38`
- `0x180046340`
- `0x1800464c8`
- `0x18004c500`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18004641f`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18004641f`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180046455`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180046455`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800463a4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800463a4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004635d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004635d`

## string_xrefs

- `0x180046372`: `onecore\net\inc\ServiceTracking.h`
- `0x1800463bc`: `onecore\net\inc\ServiceTracking.h`
- `0x180046467`: `onecore\net\inc\ServiceTracking.h`

## pseudocode

```c
__int64 __fastcall ServiceTracking::Init(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  SC_HANDLE v6; // rax
  const char *v7; // r9
  unsigned int v8; // ebx
  SC_HANDLE v10; // rbx
  const char *v11; // r9
  unsigned int LastError; // ebx
  __int64 v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  SC_HANDLE v16; // [rsp+30h] [rbp-28h] BYREF
  SC_HANDLE v17; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v18[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = OpenSCManagerW(0, 0, 1u);
  v16 = v6;
  if ( v6 )
  {
    v10 = OpenServiceW(v6, L"Eventlog", 4u);
    v17 = v10;
    if ( v10 )
    {
      std::function<void (void)>::operator=(qword_18009B308, a3);
      std::function<void (void)>::operator=(qword_18009B348, a4);
      v13 = g_eventLogClient;
      if ( g_eventLogClient )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v18);
        UnsubscribeServiceChangeNotifications(v13);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
      }
      g_eventLogClient = 0;
      v14 = SubscribeServiceChangeNotifications(
              v10,
              2,
              `ServiceTracking::Init'::`15'::_lambda_1_::_lambda_invoker_cdecl_);
      if ( v14 )
      {
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x37,
                (unsigned int)"onecore\\net\\inc\\ServiceTracking.h",
                (const char *)v14,
                (unsigned int)&g_eventLogClient);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v17);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
        return v15;
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v17);
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
                    v11);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v17);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
      return LastError;
    }
  }
  else
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x16,
           (unsigned int)"onecore\\net\\inc\\ServiceTracking.h",
           v7);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
    return v8;
  }
}

```

## disassembly

```asm
0x180046340  mov     [rsp+arg_0], rbx
0x180046345  mov     [rsp+arg_8], rsi
0x18004634a  push    rdi
0x18004634b  sub     rsp, 50h
0x18004634f  mov     rsi, r9
0x180046352  mov     rdi, r8
0x180046355  xor     edx, edx; lpDatabaseName
0x180046357  xor     ecx, ecx; lpMachineName
0x180046359  lea     r8d, [rdx+1]; dwDesiredAccess
0x18004635d  call    cs:__imp_OpenSCManagerW
0x180046363  mov     [rsp+58h+var_28], rax
0x180046368  test    rax, rax
0x18004636b  jnz     short loc_180046394
0x18004636d  mov     rcx, [rsp+58h]; this
0x180046372  lea     r8, aOnecoreNetIncS; "onecore\\net\\inc\\ServiceTracking.h"
0x180046379  lea     edx, [rax+16h]; void *
0x18004637c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046381  mov     ebx, eax
0x180046383  lea     rcx, [rsp+58h+var_28]
0x180046388  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004638d  mov     eax, ebx
0x18004638f  jmp     loc_1800464AE
0x180046394  mov     r8d, 4; dwDesiredAccess
0x18004639a  lea     rdx, ServiceName; "Eventlog"
0x1800463a1  mov     rcx, rax; hSCManager
0x1800463a4  call    cs:__imp_OpenServiceW
0x1800463aa  mov     rbx, rax
0x1800463ad  mov     [rsp+58h+var_20], rax
0x1800463b2  test    rax, rax
0x1800463b5  jnz     short loc_1800463E8
0x1800463b7  mov     rcx, [rsp+58h]; this
0x1800463bc  lea     r8, aOnecoreNetIncS; "onecore\\net\\inc\\ServiceTracking.h"
0x1800463c3  lea     edx, [rax+19h]; void *
0x1800463c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800463cb  mov     ebx, eax
0x1800463cd  lea     rcx, [rsp+58h+var_20]
0x1800463d2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800463d7  lea     rcx, [rsp+58h+var_28]
0x1800463dc  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800463e1  mov     eax, ebx
0x1800463e3  jmp     loc_1800464AE
0x1800463e8  mov     rdx, rdi
0x1800463eb  lea     rcx, qword_18009B308
0x1800463f2  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x1800463f7  mov     rdx, rsi
0x1800463fa  lea     rcx, qword_18009B348
0x180046401  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x180046406  mov     rdi, cs:?g_eventLogClient@@3VServiceTracking@@A; ServiceTracking g_eventLogClient
0x18004640d  test    rdi, rdi
0x180046410  jz      short loc_18004642F
0x180046412  lea     rcx, [rsp+58h+var_18]; this
0x180046417  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004641c  mov     rcx, rdi
0x18004641f  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180046425  lea     rcx, [rsp+58h+var_18]; this
0x18004642a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004642f  mov     cs:?g_eventLogClient@@3VServiceTracking@@A, 0; ServiceTracking g_eventLogClient
0x18004643a  lea     r9, ?g_eventLogClient@@3VServiceTracking@@A; ServiceTracking g_eventLogClient
0x180046441  mov     qword ptr [rsp+58h+var_38], r9; unsigned int
0x180046446  lea     r8, ?_lambda_invoker_cdecl_@_lambda_1_@?P@??Init@ServiceTracking@@QEAAJPEBG$$QEAV?$function@$$A6AXXZ@std@@1@Z@SA@KPEAX@Z; `ServiceTracking::Init(ushort const *,std::function<void (void)> &&,std::function<void (void)> &&)'::`15'::_lambda_1_::_lambda_invoker_cdecl_(ulong,void *)
0x18004644d  mov     edx, 2
0x180046452  mov     rcx, rbx
0x180046455  call    cs:__imp_SubscribeServiceChangeNotifications
0x18004645b  test    eax, eax
0x18004645d  jz      short loc_180046492
0x18004645f  mov     rcx, [rsp+58h]; this
0x180046464  mov     r9d, eax; char *
0x180046467  lea     r8, aOnecoreNetIncS; "onecore\\net\\inc\\ServiceTracking.h"
0x18004646e  mov     edx, 37h ; '7'; void *
0x180046473  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180046478  mov     ebx, eax
0x18004647a  lea     rcx, [rsp+58h+var_20]
0x18004647f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180046484  lea     rcx, [rsp+58h+var_28]
0x180046489  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004648e  mov     eax, ebx
0x180046490  jmp     short loc_1800464AE
0x180046492  lea     rcx, [rsp+58h+var_20]
0x180046497  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004649c  lea     rcx, [rsp+58h+var_28]
0x1800464a1  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800464a6  xor     eax, eax
0x1800464a8  jmp     short loc_1800464AE
0x1800464aa  mov     eax, dword ptr [rsp+58h+var_28]
0x1800464ae  mov     rbx, [rsp+58h+arg_0]
0x1800464b3  mov     rsi, [rsp+58h+arg_8]
0x1800464b8  add     rsp, 50h
0x1800464bc  pop     rdi
0x1800464bd  retn
```
