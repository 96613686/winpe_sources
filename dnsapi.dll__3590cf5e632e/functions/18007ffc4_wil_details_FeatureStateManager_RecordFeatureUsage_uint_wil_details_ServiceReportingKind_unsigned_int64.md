# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18007ffc4`
- end: `0x18008009d`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800c98f0`

## callees

- `0x18007ffc4`
- `0x1800800a4`
- `0x1800800c8`
- `0x18008012c`
- `0x180080150`
- `0x18008017c`
- `0x18008041c`
- `0x1800c6f68`
- `0x1800c89d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008001a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008001a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180080052`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180080052`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  bool v9; // zf
  PTP_TIMER ThreadpoolTimer; // rax
  char v11[8]; // [rsp+20h] [rbp-28h] BYREF
  RTL_SRWLOCK *v12; // [rsp+28h] [rbp-20h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v9 = BYTE1(a1[8].Ptr) == 0;
    v12 = a1 + 4;
    if ( v9 )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18007ffc4  mov     [rsp+arg_18], rbx
0x18007ffc9  push    rbp
0x18007ffca  push    rsi
0x18007ffcb  push    rdi
0x18007ffcc  sub     rsp, 30h
0x18007ffd0  cmp     byte ptr [rcx], 0
0x18007ffd3  mov     rbx, r9
0x18007ffd6  mov     ebp, r8d
0x18007ffd9  mov     esi, edx
0x18007ffdb  mov     rdi, rcx
0x18007ffde  jz      loc_18008008F
0x18007ffe4  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18007ffe9  test    al, al
0x18007ffeb  jz      loc_18008008F
0x18007fff1  mov     rcx, [rdi+18h]
0x18007fff5  mov     r9, rbx
0x18007fff8  mov     r8d, ebp
0x18007fffb  mov     edx, esi
0x18007fffd  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180080002  test    al, al
0x180080004  jz      loc_18008008F
0x18008000a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18008000f  test    al, al
0x180080011  jnz     short loc_18008008F
0x180080013  lea     rbx, [rdi+20h]
0x180080017  mov     rcx, rbx; SRWLock
0x18008001a  call    cs:__imp_AcquireSRWLockExclusive
0x180080021  nop     dword ptr [rax+rax+00h]
0x180080026  cmp     byte ptr [rdi+41h], 0
0x18008002a  mov     [rsp+48h+var_20], rbx
0x18008002f  jnz     short loc_180080085
0x180080031  lea     rbx, [rdi+30h]
0x180080035  cmp     qword ptr [rbx], 0
0x180080039  jnz     short loc_180080073
0x18008003b  lea     rcx, [rsp+48h+var_28]; this
0x180080040  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180080045  xor     r8d, r8d; pcbe
0x180080048  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18008004f  mov     rdx, rdi; pv
0x180080052  call    cs:__imp_CreateThreadpoolTimer
0x180080059  nop     dword ptr [rax+rax+00h]
0x18008005e  mov     rdx, rax
0x180080061  mov     rcx, rbx
0x180080064  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180080069  lea     rcx, [rsp+48h+var_28]; this
0x18008006e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180080073  mov     r8d, 493E0h
0x180080079  lea     rdx, [rdi+41h]
0x18008007d  mov     rcx, rbx
0x180080080  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180080085  lea     rcx, [rsp+48h+var_20]
0x18008008a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18008008f  mov     rbx, [rsp+48h+arg_18]
0x180080094  add     rsp, 30h
0x180080098  pop     rdi
0x180080099  pop     rsi
0x18008009a  pop     rbp
0x18008009b  retn
```
