# DusmWlan::RegisterServiceNotifications(void)

- ea: `0x18003840c`
- end: `0x180038512`
- name: `?RegisterServiceNotifications@DusmWlan@@AEAAKXZ`
- size: `262`
- prototype: `unsigned int __fastcall(DusmWlan *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800378cc`

## callees

- `0x180007c90`
- `0x180030cf4`
- `0x18003840c`
- `0x18003870c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003845a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003845a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180038476`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180038476`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003843f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003843f`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800384a7`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800384a7`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800384cb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800384cb`

## pseudocode

```c
unsigned int __fastcall DusmWlan::RegisterServiceNotifications(DusmWlan *this)
{
  LPCRITICAL_SECTION v1; // rdi
  SC_HANDLE v2; // rax
  SC_HANDLE OwningThread; // rcx
  unsigned int result; // eax
  SC_HANDLE v5; // rax
  unsigned int v6; // ebx
  wil *v7; // rcx
  wil *v8; // rcx
  const wil::ResultException *v9; // rdi
  _DWORD *v10; // r8
  __int64 v11; // r9
  unsigned int v12; // eax
  unsigned int v13; // edi
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // [rsp+54h] [rbp-54h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-50h] BYREF
  int v19; // [rsp+5Ch] [rbp-4Ch] BYREF
  const WCHAR *v20; // [rsp+60h] [rbp-48h] BYREF
  const wchar_t *v21; // [rsp+68h] [rbp-40h] BYREF
  const wil::ResultException *v22; // [rsp+70h] [rbp-38h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+78h] [rbp-30h] BYREF

  v1 = DusmWlan::s_pInstance;
  v2 = OpenSCManagerW(0, 0, 5u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    &v1[1].OwningThread,
    v2);
  OwningThread = (SC_HANDLE)v1[1].OwningThread;
  if ( !OwningThread )
    return GetLastError();
  v5 = OpenServiceW(OwningThread, L"wlansvc", 4u);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    &v1[1].LockSemaphore,
    v5);
  if ( !v1[1].LockSemaphore )
    return GetLastError();
  result = SubscribeServiceChangeNotifications(
             v1[1].LockSemaphore,
             2,
             DusmWlan::ServiceNotificationCallback,
             v1,
             &v1[1].SpinCount);
  v6 = result;
  if ( !result )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus((SC_HANDLE)v1[1].LockSemaphore, &ServiceStatus) && ServiceStatus.dwCurrentState == 4 )
    {
      try
      {
        DusmWlan::Start((DusmWlan *)v1);
      }
      catch ( const wil::ResultException *v22 )
      {
        if ( (wil::ResultFromCaughtException(v7) & 0x1FFF0000) == 0x70000 )
          v6 = (unsigned __int16)wil::ResultFromCaughtException(v8);
        else
          v6 = wil::ResultFromCaughtException(v8);
        v9 = v22;
        v10 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
        if ( *v10 > 5u )
        {
          v20 = (const WCHAR *)*((_QWORD *)v9 + 6);
          v19 = *((_DWORD *)v9 + 22);
          v21 = (const wchar_t *)*((_QWORD *)v9 + 10);
          v17 = *((_DWORD *)v9 + 8);
          v18 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
            (int)v10,
            (int)&dword_18005980C,
            (__int64)v10,
            v11,
            (__int64)&v18,
            (__int64)&v17,
            &v21,
            (__int64)&v19,
            &v20);
        }
        return v6;
      }
      catch ( ... )
      {
        v12 = wil::ResultFromCaughtException(v7);
        v13 = v12;
        v6 = (unsigned __int16)v12;
        if ( (v12 & 0x1FFF0000) != 0x70000 )
          v6 = v12;
        v14 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
        if ( *v14 > 5u )
        {
          v18 = v13;
          v17 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (int)v14,
            (int)&dword_180059794,
            v15,
            v16,
            (__int64)&v17,
            (__int64)&v18);
        }
      }
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18003840c  mov     [rsp+arg_0], rbx
0x180038411  mov     [rsp+arg_8], rsi
0x180038416  push    rdi
0x180038417  sub     rsp, 0A0h
0x18003841e  mov     rax, cs:__security_cookie
0x180038425  xor     rax, rsp
0x180038428  mov     [rsp+0A8h+var_10], rax
0x180038430  mov     rdi, cs:?s_pInstance@DusmWlan@@0PEAV1@EA; DusmWlan * DusmWlan::s_pInstance
0x180038437  xor     edx, edx; lpDatabaseName
0x180038439  xor     ecx, ecx; lpMachineName
0x18003843b  lea     r8d, [rdx+5]; dwDesiredAccess
0x18003843f  call    cs:__imp_OpenSCManagerW
0x180038445  mov     rdx, rax
0x180038448  lea     rcx, [rdi+38h]
0x18003844c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180038451  mov     rcx, [rdi+38h]; hSCManager
0x180038455  test    rcx, rcx
0x180038458  jnz     short loc_180038465
0x18003845a  call    cs:__imp_GetLastError
0x180038460  jmp     loc_1800384ED
0x180038465  lea     rsi, [rdi+40h]
0x180038469  mov     r8d, 4; dwDesiredAccess
0x18003846f  lea     rdx, aWlansvc; "wlansvc"
0x180038476  call    cs:__imp_OpenServiceW
0x18003847c  mov     rdx, rax
0x18003847f  mov     rcx, rsi
0x180038482  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180038487  mov     rcx, [rsi]
0x18003848a  test    rcx, rcx
0x18003848d  jz      short loc_18003845A
0x18003848f  lea     rax, [rdi+48h]
0x180038493  mov     [rsp+0A8h+var_88], rax
0x180038498  mov     r9, rdi
0x18003849b  lea     r8, ?ServiceNotificationCallback@DusmWlan@@CAXKPEAX@Z; DusmWlan::ServiceNotificationCallback(ulong,void *)
0x1800384a2  mov     edx, 2
0x1800384a7  call    cs:__imp_SubscribeServiceChangeNotifications
0x1800384ad  mov     ebx, eax
0x1800384af  test    eax, eax
0x1800384b1  jnz     short loc_1800384ED
0x1800384b3  xorps   xmm0, xmm0
0x1800384b6  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1800384bb  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800384c3  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800384c8  mov     rcx, [rsi]; hService
0x1800384cb  call    cs:__imp_QueryServiceStatus
0x1800384d1  test    eax, eax
0x1800384d3  jz      short loc_1800384EB
0x1800384d5  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 4
0x1800384da  jnz     short loc_1800384EB
0x1800384dc  mov     rcx, rdi; this
0x1800384df  call    ?Start@DusmWlan@@AEAAXXZ; DusmWlan::Start(void)
0x1800384e4  nop
0x1800384e5  jmp     short loc_1800384EB
0x1800384e7  mov     ebx, [rsp+0A8h+var_58]
0x1800384eb  mov     eax, ebx
0x1800384ed  mov     rcx, [rsp+0A8h+var_10]
0x1800384f5  xor     rcx, rsp; StackCookie
0x1800384f8  call    __security_check_cookie
0x1800384fd  lea     r11, [rsp+0A8h+var_8]
0x180038505  mov     rbx, [r11+10h]
0x180038509  mov     rsi, [r11+18h]
0x18003850d  mov     rsp, r11
0x180038510  pop     rdi
0x180038511  retn
```
