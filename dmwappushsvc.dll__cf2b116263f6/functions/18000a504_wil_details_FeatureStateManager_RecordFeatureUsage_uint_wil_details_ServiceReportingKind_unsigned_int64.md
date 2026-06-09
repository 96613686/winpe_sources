# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a504`
- end: `0x18000a5c6`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000be90`

## callees

- `0x1800074a0`
- `0x180007984`
- `0x180007c98`
- `0x1800083a0`
- `0x1800083e4`
- `0x180009da4`
- `0x18000a45c`
- `0x18000a504`
- `0x18000cbf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a553`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a553`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a585`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a585`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(
         *((wil::details_abi::FeatureStateData **)a1 + 3),
         a2,
         a3,
         a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v10 = (RTL_SRWLOCK *)(a1 + 32);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18000a504  push    rbx
0x18000a506  push    rbp
0x18000a507  push    rsi
0x18000a508  push    rdi
0x18000a509  sub     rsp, 38h
0x18000a50d  mov     rbx, r9
0x18000a510  mov     esi, r8d
0x18000a513  mov     ebp, edx
0x18000a515  mov     rdi, rcx
0x18000a518  cmp     byte ptr [rcx], 0
0x18000a51b  jz      loc_18000A5BD
0x18000a521  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a526  test    al, al
0x18000a528  jz      loc_18000A5BD
0x18000a52e  mov     r9, rbx
0x18000a531  mov     r8d, esi
0x18000a534  mov     edx, ebp
0x18000a536  mov     rcx, [rdi+18h]
0x18000a53a  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a53f  test    al, al
0x18000a541  jz      short loc_18000A5BD
0x18000a543  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000a548  test    al, al
0x18000a54a  jnz     short loc_18000A5BD
0x18000a54c  lea     rbx, [rdi+20h]
0x18000a550  mov     rcx, rbx; SRWLock
0x18000a553  call    cs:__imp_AcquireSRWLockExclusive
0x18000a559  mov     [rsp+58h+var_38], rbx
0x18000a55e  cmp     byte ptr [rdi+41h], 0
0x18000a562  jnz     short loc_18000A5B2
0x18000a564  lea     rbx, [rdi+30h]
0x18000a568  cmp     qword ptr [rbx], 0
0x18000a56c  jnz     short loc_18000A5A0
0x18000a56e  lea     rcx, [rsp+58h+arg_0]; this
0x18000a573  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a578  xor     r8d, r8d; pcbe
0x18000a57b  mov     rdx, rdi; pv
0x18000a57e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a585  call    cs:__imp_CreateThreadpoolTimer
0x18000a58b  mov     rdx, rax
0x18000a58e  mov     rcx, rbx
0x18000a591  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a596  lea     rcx, [rsp+58h+arg_0]; this
0x18000a59b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a5a0  mov     r8d, 493E0h
0x18000a5a6  lea     rdx, [rdi+41h]
0x18000a5aa  mov     rcx, rbx
0x18000a5ad  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000a5b2  lea     rcx, [rsp+58h+var_38]
0x18000a5b7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a5bc  nop
0x18000a5bd  add     rsp, 38h
0x18000a5c1  pop     rdi
0x18000a5c2  pop     rsi
0x18000a5c3  pop     rbp
0x18000a5c4  pop     rbx
0x18000a5c5  retn
```
