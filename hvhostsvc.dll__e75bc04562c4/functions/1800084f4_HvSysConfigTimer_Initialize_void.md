# HvSysConfigTimer::Initialize(void)

- ea: `0x1800084f4`
- end: `0x1800086f4`
- name: `?Initialize@HvSysConfigTimer@@QEAAJXZ`
- size: `512`
- prototype: `__int64 __fastcall(HvSysConfigTimer *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004928`

## callees

- `0x180002100`
- `0x180002bd0`
- `0x18000658c`
- `0x180006ebc`
- `0x180007064`
- `0x180007f3c`
- `0x180008058`
- `0x180008204`
- `0x180008234`
- `0x18000828c`
- `0x180008380`
- `0x1800084f4`
- `0x180008700`
- `0x1800088b8`
- `0x180008908`
- `0x180008b80`
- `0x180008e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180008592`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180008592`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008602`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008602`

## string_xrefs

- `0x180008537`: `onecore\hv\hvhostsvc\lib\hvsysconfigtimer.cpp`
- `0x1800086d2`: `onecore\hv\hvhostsvc\lib\hvsysconfigtimer.cpp`
- `0x1800086e3`: `onecore\hv\hvhostsvc\lib\hvsysconfigtimer.cpp`

## pseudocode

```c
__int64 __fastcall HvSysConfigTimer::Initialize(HvSysConfigTimer *this)
{
  bool v1; // al
  HvServiceUtil *v2; // rax
  HvServiceUtil *v3; // rax
  __int64 v4; // rcx
  void **v5; // rdx
  HANDLE MutexW; // rbx
  const char *v7; // r9
  const char *v8; // r9
  wil *v9; // rcx
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-A8h]
  const char *v12; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-90h] BYREF
  _QWORD v14[14]; // [rsp+40h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v1 = (unsigned __int8)HviIsHypervisorVendorMicrosoft(this) != 0;
  LOBYTE(v11) = v1;
  try
  {
    wil::details::in1diag3::Throw_HrIfFalseMsg(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\hv\\hvhostsvc\\lib\\hvsysconfigtimer.cpp",
      (const char *)0x80004005LL,
      v11,
      (bool)"Hypervisor is absent.",
      v12);
    v2 = (HvServiceUtil *)operator new(8u);
    v3 = HvServiceUtil::HvServiceUtil(v2);
    v12 = 0;
    v5 = (void **)g_HypervisorSysConfigTimer;
    g_HypervisorSysConfigTimer = v3;
    if ( v5 )
      std::default_delete<HvServiceUtil>::operator()(v4, v5);
    std::unique_ptr<HvServiceUtil>::~unique_ptr<HvServiceUtil>(&v12);
    MutexW = CreateMutexW(0, 0, 0);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hObject);
    hObject = MutexW;
    v12 = 0;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)&v12);
    if ( (((unsigned __int64)hObject + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2E,
        (int)"onecore\\hv\\hvhostsvc\\lib\\hvsysconfigtimer.cpp",
        v7);
    pti = CreateThreadpoolTimer(HvSysConfigTimer::LogSysConfig, &g_HypervisorSysConfigTimer, 0);
    if ( !pti )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x32,
        (int)"onecore\\hv\\hvhostsvc\\lib\\hvsysconfigtimer.cpp",
        v8);
    HvSysConfigTimer::LogSysConfig(0, &g_HypervisorSysConfigTimer, 0);
    HvSysConfigTimer::UpdateSysConfigTimer((HvSysConfigTimer *)&g_HypervisorSysConfigTimer);
    v14[0] = off_18000B0B0;
    v14[1] = &g_HypervisorSysConfigTimer;
    v14[13] = v14;
    v12 = 0;
    wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
      (__int64)&v12,
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\Worker",
      0,
      (__int64)v13);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
      &qword_1800127C0,
      v12);
    v12 = 0;
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>((__int64 *)&v12);
    wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>((__int64)v13);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::ResultFromCaughtException(v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800084f4  push    rbx
0x1800084f6  sub     rsp, 0C0h
0x1800084fd  mov     rax, cs:__security_cookie
0x180008504  xor     rax, rsp
0x180008507  mov     [rsp+0C8h+var_18], rax
0x18000850f  call    HviIsHypervisorVendorMicrosoft
0x180008514  test    al, al
0x180008516  setnz   al
0x180008519  mov     rcx, [rsp+0C8h]; this
0x180008521  lea     rdx, aHypervisorIsAb; "Hypervisor is absent."
0x180008528  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x18000852d  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x180008531  mov     r9d, 80004005h; char *
0x180008537  lea     r8, aOnecoreHvHvhos_0; "onecore\\hv\\hvhostsvc\\lib\\hvsysconfi"...
0x18000853e  mov     edx, 28h ; '('; void *
0x180008543  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x180008548  mov     ecx, 8; Size
0x18000854d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008552  mov     [rsp+0C8h+var_98], rax
0x180008557  mov     rcx, rax; this
0x18000855a  call    ??0HvServiceUtil@@QEAA@XZ; HvServiceUtil::HvServiceUtil(void)
0x18000855f  nop
0x180008560  mov     [rsp+0C8h+var_98], 0
0x180008569  mov     rdx, cs:?g_HypervisorSysConfigTimer@@3VHvSysConfigTimer@@A; HvSysConfigTimer g_HypervisorSysConfigTimer
0x180008570  mov     cs:?g_HypervisorSysConfigTimer@@3VHvSysConfigTimer@@A, rax; HvSysConfigTimer g_HypervisorSysConfigTimer
0x180008577  test    rdx, rdx
0x18000857a  jz      short loc_180008581
0x18000857c  call    ??R?$default_delete@VHvServiceUtil@@@std@@QEBAXPEAVHvServiceUtil@@@Z; std::default_delete<HvServiceUtil>::operator()(HvServiceUtil *)
0x180008581  lea     rcx, [rsp+0C8h+var_98]
0x180008586  call    ??1?$unique_ptr@VHvServiceUtil@@U?$default_delete@VHvServiceUtil@@@std@@@std@@QEAA@XZ; std::unique_ptr<HvServiceUtil>::~unique_ptr<HvServiceUtil>(void)
0x18000858b  xor     r8d, r8d; lpName
0x18000858e  xor     edx, edx; bInitialOwner
0x180008590  xor     ecx, ecx; lpMutexAttributes
0x180008592  call    cs:__imp_CreateMutexW
0x180008598  mov     rbx, rax
0x18000859b  mov     rcx, cs:hObject; hObject
0x1800085a2  lea     rdx, [rcx-1]
0x1800085a6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800085aa  ja      short loc_1800085B1
0x1800085ac  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x1800085b1  mov     cs:hObject, rbx
0x1800085b8  mov     [rsp+0C8h+var_98], 0
0x1800085c1  lea     rcx, [rsp+0C8h+var_98]
0x1800085c6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800085cb  mov     rax, cs:hObject
0x1800085d2  inc     rax
0x1800085d5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800085db  setz    al
0x1800085de  mov     rcx, [rsp+0C8h]; this
0x1800085e6  test    al, al
0x1800085e8  jnz     loc_1800086D2
0x1800085ee  xor     r8d, r8d; pcbe
0x1800085f1  lea     rbx, ?g_HypervisorSysConfigTimer@@3VHvSysConfigTimer@@A; HvSysConfigTimer g_HypervisorSysConfigTimer
0x1800085f8  mov     rdx, rbx; pv
0x1800085fb  lea     rcx, ?LogSysConfig@HvSysConfigTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008602  call    cs:__imp_CreateThreadpoolTimer
0x180008608  mov     cs:pti, rax
0x18000860f  mov     rcx, [rsp+0C8h]; this
0x180008617  test    rax, rax
0x18000861a  jz      loc_1800086E3
0x180008620  xor     r8d, r8d; Timer
0x180008623  mov     rdx, rbx; Context
0x180008626  xor     ecx, ecx; Instance
0x180008628  call    ?LogSysConfig@HvSysConfigTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; HvSysConfigTimer::LogSysConfig(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x18000862d  mov     rcx, rbx; this
0x180008630  call    ?UpdateSysConfigTimer@HvSysConfigTimer@@AEAAXXZ; HvSysConfigTimer::UpdateSysConfigTimer(void)
0x180008635  lea     rax, off_18000B0B0
0x18000863c  mov     [rsp+0C8h+var_88], rax
0x180008641  mov     [rsp+0C8h+var_80], rbx
0x180008646  lea     rax, [rsp+0C8h+var_88]
0x18000864b  mov     [rsp+0C8h+var_20], rax
0x180008653  mov     [rsp+0C8h+var_98], 0
0x18000865c  lea     rax, [rsp+0C8h+var_90]
0x180008661  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180008666  xor     r9d, r9d
0x180008669  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180008670  mov     rdx, 0FFFFFFFF80000002h
0x180008677  lea     rcx, [rsp+0C8h+var_98]
0x18000867c  call    ?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180008681  nop
0x180008682  mov     rdx, [rsp+0C8h+var_98]
0x180008687  lea     rcx, qword_1800127C0
0x18000868e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180008693  mov     [rsp+0C8h+var_98], 0
0x18000869c  lea     rcx, [rsp+0C8h+var_98]
0x1800086a1  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x1800086a6  nop
0x1800086a7  lea     rcx, [rsp+0C8h+var_90]
0x1800086ac  call    ??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ; wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)
0x1800086b1  xor     eax, eax
0x1800086b3  jmp     short loc_1800086B9
0x1800086b5  mov     eax, dword ptr [rsp+0C8h+var_98]
0x1800086b9  mov     rcx, [rsp+0C8h+var_18]
0x1800086c1  xor     rcx, rsp; StackCookie
0x1800086c4  call    __security_check_cookie
0x1800086c9  add     rsp, 0C0h
0x1800086d0  pop     rbx
0x1800086d1  retn
0x1800086d2  lea     r8, aOnecoreHvHvhos_0; "onecore\\hv\\hvhostsvc\\lib\\hvsysconfi"...
0x1800086d9  mov     edx, 2Eh ; '.'; void *
0x1800086de  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800086e3  lea     r8, aOnecoreHvHvhos_0; "onecore\\hv\\hvhostsvc\\lib\\hvsysconfi"...
0x1800086ea  lea     edx, [rax+32h]; void *
0x1800086ed  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
