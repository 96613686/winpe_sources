# IsDefenderDisabled(void)

- ea: `0x180015688`
- end: `0x18001577d`
- name: `?IsDefenderDisabled@@YAHXZ`
- size: `245`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800095cc`

## callees

- `0x18000be40`
- `0x1800144d0`
- `0x180015688`
- `0x1800163d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015739`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015741`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800156f3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800156f3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800156cc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800156cc`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015725`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015725`

## pseudocode

```c
_BOOL8 IsDefenderDisabled(void)
{
  BOOL v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rax
  DWORD LastError; // eax
  SC_HANDLE hService; // [rsp+20h] [rbp-E0h] BYREF
  SC_HANDLE hSCManager; // [rsp+28h] [rbp-D8h] BYREF
  DWORD pcbBytesNeeded[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 1;
  hSCManager = 0;
  hService = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    &hSCManager,
    v1);
  if ( hSCManager )
  {
    v2 = OpenServiceW(hSCManager, L"wdfilter", 1u);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      &hService,
      v2);
    if ( hService )
    {
      pcbBytesNeeded[0] = 1024;
      if ( QueryServiceConfigW(hService, &ServiceConfig, 0x400u, pcbBytesNeeded) )
        v0 = ServiceConfig.dwStartType == 4;
    }
    LastError = GetLastError();
    SetLastError(LastError);
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hService);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hSCManager);
  return v0;
}

```

## disassembly

```asm
0x180015688  mov     [rsp-8+arg_0], rbx
0x18001568d  push    rbp
0x18001568e  lea     rbp, [rsp-350h]
0x180015696  sub     rsp, 450h
0x18001569d  mov     rax, cs:__security_cookie
0x1800156a4  xor     rax, rsp
0x1800156a7  mov     [rbp+350h+var_10], rax
0x1800156ae  mov     ebx, 1
0x1800156b3  mov     [rsp+450h+hSCManager], 0
0x1800156bc  mov     r8d, ebx; dwDesiredAccess
0x1800156bf  mov     [rsp+450h+hService], 0
0x1800156c8  xor     edx, edx; lpDatabaseName
0x1800156ca  xor     ecx, ecx; lpMachineName
0x1800156cc  call    cs:__imp_OpenSCManagerW
0x1800156d2  mov     rdx, rax
0x1800156d5  lea     rcx, [rsp+450h+hSCManager]
0x1800156da  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800156df  mov     rcx, [rsp+450h+hSCManager]; hSCManager
0x1800156e4  test    rcx, rcx
0x1800156e7  jz      short loc_180015747
0x1800156e9  mov     r8d, ebx; dwDesiredAccess
0x1800156ec  lea     rdx, ServiceName; "wdfilter"
0x1800156f3  call    cs:__imp_OpenServiceW
0x1800156f9  mov     rdx, rax
0x1800156fc  lea     rcx, [rsp+450h+hService]
0x180015701  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180015706  mov     rcx, [rsp+450h+hService]; hService
0x18001570b  test    rcx, rcx
0x18001570e  jz      short loc_180015739
0x180015710  mov     r8d, 400h; cbBufSize
0x180015716  lea     r9, [rsp+450h+pcbBytesNeeded]; pcbBytesNeeded
0x18001571b  lea     rdx, [rsp+450h+ServiceConfig]; lpServiceConfig
0x180015720  mov     [rsp+450h+pcbBytesNeeded], r8d
0x180015725  call    cs:__imp_QueryServiceConfigW
0x18001572b  test    eax, eax
0x18001572d  jz      short loc_180015739
0x18001572f  xor     ebx, ebx
0x180015731  cmp     [rsp+450h+ServiceConfig.dwStartType], 4
0x180015736  setz    bl
0x180015739  call    cs:__imp_GetLastError
0x18001573f  mov     ecx, eax; dwErrCode
0x180015741  call    cs:__imp_SetLastError
0x180015747  lea     rcx, [rsp+450h+hService]
0x18001574c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180015751  lea     rcx, [rsp+450h+hSCManager]
0x180015756  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18001575b  mov     eax, ebx
0x18001575d  mov     rcx, [rbp+350h+var_10]
0x180015764  xor     rcx, rsp; StackCookie
0x180015767  call    __security_check_cookie
0x18001576c  mov     rbx, [rsp+450h+arg_0]
0x180015774  add     rsp, 450h
0x18001577b  pop     rbp
0x18001577c  retn
```
