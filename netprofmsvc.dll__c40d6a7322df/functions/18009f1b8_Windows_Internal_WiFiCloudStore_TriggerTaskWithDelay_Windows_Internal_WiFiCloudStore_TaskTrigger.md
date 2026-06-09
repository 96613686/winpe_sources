# Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay(Windows::Internal::WiFiCloudStore::TaskTrigger)

- ea: `0x18009f1b8`
- end: `0x18009f2da`
- name: `?TriggerTaskWithDelay@WiFiCloudStore@Internal@Windows@@YAJW4TaskTrigger@123@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009ed64`

## callees

- `0x18007eeec`
- `0x180083108`
- `0x18008c9bc`
- `0x18009f1b8`
- `0x1801290c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009f1e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009f1e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009f2a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009f2a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009f218`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009f218`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009f251`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009f251`

## string_xrefs

- `0x18009f1f4`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x18009f22e`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
__int64 Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay()
{
  const char *v0; // r9
  unsigned int LastError; // ebx
  const char *v2; // r9
  struct _TP_TIMER *v3; // rbx
  struct _FILETIME v4; // rdi
  __int64 v5; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HMODULE phModule; // [rsp+48h] [rbp+28h] BYREF
  PTP_TIMER ThreadpoolTimer; // [rsp+50h] [rbp+30h] BYREF
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+38h] BYREF

  phModule = 0;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &phModule,
    0);
  if ( GetModuleHandleExW(4u, L"\\Microsoft\\Windows\\WlanSvc", &phModule) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(
                        Windows::Internal::WiFiCloudStore::TriggerTaskTimerCallbackNetprofm,
                        phModule,
                        0);
    v3 = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v4 = (struct _FILETIME)-600000000LL;
      v5 = (__int64)GetTickCount64() / 60000;
      if ( (int)v5 < 15 )
        v4 = (struct _FILETIME)(-600000000LL * (15 - (int)v5));
      pftDueTime = v4;
      SetThreadpoolTimer(v3, &pftDueTime, 0, 0x989680u);
      phModule = 0;
      ThreadpoolTimer = 0;
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&ThreadpoolTimer);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x73,
                    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                    v2);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&ThreadpoolTimer);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6E,
                  (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                  v0);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
  return LastError;
}

```

## disassembly

```asm
0x18009f1b8  push    rbp
0x18009f1ba  push    rbx
0x18009f1bb  push    rdi
0x18009f1bc  mov     rbp, rsp
0x18009f1bf  sub     rsp, 20h
0x18009f1c3  xor     edx, edx
0x18009f1c5  mov     [rbp+phModule], 0
0x18009f1cd  lea     rcx, [rbp+phModule]
0x18009f1d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18009f1d6  lea     r8, [rbp+phModule]; phModule
0x18009f1da  mov     ecx, 4; dwFlags
0x18009f1df  lea     rdx, psz; "\\Microsoft\\Windows\\WlanSvc"
0x18009f1e6  call    cs:__imp_GetModuleHandleExW
0x18009f1ec  test    eax, eax
0x18009f1ee  jnz     short loc_18009F20A
0x18009f1f0  mov     rcx, [rbp+18h]; this
0x18009f1f4  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18009f1fb  lea     edx, [rax+6Eh]; void *
0x18009f1fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009f203  mov     ebx, eax
0x18009f205  jmp     loc_18009F2C7
0x18009f20a  mov     rdx, [rbp+phModule]; pv
0x18009f20e  lea     rcx, ?TriggerTaskTimerCallbackNetprofm@WiFiCloudStore@Internal@Windows@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18009f215  xor     r8d, r8d; pcbe
0x18009f218  call    cs:__imp_CreateThreadpoolTimer
0x18009f21e  mov     [rbp+arg_10], rax
0x18009f222  mov     rbx, rax
0x18009f225  test    rax, rax
0x18009f228  jnz     short loc_18009F24A
0x18009f22a  mov     rcx, [rbp+18h]; this
0x18009f22e  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18009f235  lea     edx, [rax+73h]; void *
0x18009f238  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009f23d  lea     rcx, [rbp+arg_10]
0x18009f241  mov     ebx, eax
0x18009f243  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18009f248  jmp     short loc_18009F2C7
0x18009f24a  mov     rdi, 0FFFFFFFFDC3CBA00h
0x18009f251  call    cs:__imp_GetTickCount64
0x18009f257  mov     rcx, rax
0x18009f25a  mov     rax, 45E7B272F608770Fh
0x18009f264  imul    rcx
0x18009f267  sar     rdx, 0Eh
0x18009f26b  mov     rax, rdx
0x18009f26e  shr     rax, 3Fh
0x18009f272  add     rdx, rax
0x18009f275  mov     eax, 0Fh
0x18009f27a  cmp     edx, eax
0x18009f27c  jge     short loc_18009F289
0x18009f27e  sub     eax, edx
0x18009f280  cdqe
0x18009f282  imul    rdi, rax, 0FFFFFFFFDC3CBA00h
0x18009f289  mov     rax, rdi
0x18009f28c  mov     [rbp+pftDueTime.dwLowDateTime], edi
0x18009f28f  shr     rax, 20h
0x18009f293  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18009f297  mov     r9d, 989680h; msWindowLength
0x18009f29d  mov     [rbp+pftDueTime.dwHighDateTime], eax
0x18009f2a0  xor     r8d, r8d; msPeriod
0x18009f2a3  mov     rcx, rbx; pti
0x18009f2a6  call    cs:__imp_SetThreadpoolTimer
0x18009f2ac  lea     rcx, [rbp+arg_10]
0x18009f2b0  mov     [rbp+phModule], 0
0x18009f2b8  mov     [rbp+arg_10], 0
0x18009f2c0  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18009f2c5  xor     ebx, ebx
0x18009f2c7  lea     rcx, [rbp+phModule]
0x18009f2cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18009f2d0  mov     eax, ebx
0x18009f2d2  add     rsp, 20h
0x18009f2d6  pop     rdi
0x18009f2d7  pop     rbx
0x18009f2d8  pop     rbp
0x18009f2d9  retn
```
