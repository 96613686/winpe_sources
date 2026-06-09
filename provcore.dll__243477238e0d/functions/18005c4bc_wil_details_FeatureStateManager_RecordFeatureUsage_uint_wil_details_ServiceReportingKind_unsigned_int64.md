# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18005c4bc`
- end: `0x18005c585`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `201`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, wil_details_ServiceReportingKind kind, unsigned __int64 addend)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18005deb0`

## callees

- `0x180005580`
- `0x180005874`
- `0x180006f0c`
- `0x1800587d8`
- `0x1800598d4`
- `0x180059934`
- `0x18005c40c`
- `0x18005c4bc`
- `0x18005e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c50e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c50e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c540`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c540`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        wil::details::FeatureStateManager *this,
        unsigned int featureId,
        wil_details_ServiceReportingKind kind,
        unsigned __int64 addend)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  wil::last_error_context v9; // [rsp+20h] [rbp-28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+28h] [rbp-20h] BYREF

  if ( this->m_fInitialized
    && wil::details::FeatureStateManager::EnsureStateData(this)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(this->m_data, featureId, kind, addend)
    && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    lock.m_ptr = &this->m_lock.m_lock;
    if ( !this->m_timerSet )
    {
      if ( !this->m_timer.m_ptr )
      {
        wil::last_error_context::last_error_context(&v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            this,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &this->m_timer,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context(&v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&this->m_timer, &this->m_timerSet, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x18005c4bc  mov     [rsp+arg_18], rbx
0x18005c4c1  push    rbp
0x18005c4c2  push    rsi
0x18005c4c3  push    rdi
0x18005c4c4  sub     rsp, 30h
0x18005c4c8  mov     rbx, addend
0x18005c4cb  mov     ebp, kind
0x18005c4ce  mov     esi, featureId
0x18005c4d0  mov     rdi, this
0x18005c4d3  cmp     byte ptr [this], 0
0x18005c4d6  jz      loc_18005C578
0x18005c4dc  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18005c4e1  test    al, al
0x18005c4e3  jz      loc_18005C578
0x18005c4e9  mov     addend, rbx; addend
0x18005c4ec  mov     kind, ebp; kind
0x18005c4ef  mov     featureId, esi; featureId
0x18005c4f1  mov     this, [rdi+18h]; this
0x18005c4f5  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18005c4fa  test    al, al
0x18005c4fc  jz      short loc_18005C578
0x18005c4fe  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005c503  test    al, al
0x18005c505  jnz     short loc_18005C578
0x18005c507  lea     rbx, [rdi+20h]
0x18005c50b  mov     this, rbx; SRWLock
0x18005c50e  call    cs:__imp_AcquireSRWLockExclusive
0x18005c514  mov     [rsp+48h+lock.m_ptr], rbx
0x18005c519  cmp     byte ptr [rdi+41h], 0
0x18005c51d  jnz     short loc_18005C56D
0x18005c51f  lea     rbx, [rdi+30h]
0x18005c523  cmp     qword ptr [rbx], 0
0x18005c527  jnz     short loc_18005C55B
0x18005c529  lea     this, [rsp+48h+var_28]; this
0x18005c52e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005c533  xor     kind, kind; pcbe
0x18005c536  mov     rdx, rdi; pv
0x18005c539  lea     this, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005c540  call    cs:__imp_CreateThreadpoolTimer
0x18005c546  mov     rdx, rax; ptr
0x18005c549  mov     this, rbx; this
0x18005c54c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005c551  lea     this, [rsp+48h+var_28]; this
0x18005c556  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005c55b  mov     kind, 493E0h; delay
0x18005c561  lea     rdx, [rdi+41h]; timerSet
0x18005c565  mov     this, rbx; timer
0x18005c568  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18005c56d  lea     this, [rsp+48h+lock]; this
0x18005c572  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005c577  nop
0x18005c578  mov     rbx, [rsp+48h+arg_18]
0x18005c57d  add     rsp, 30h
0x18005c581  pop     rdi
0x18005c582  pop     rsi
0x18005c583  pop     rbp
0x18005c584  retn
```
