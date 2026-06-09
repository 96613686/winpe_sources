# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18005bfd0`
- end: `0x18005c0a3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `211`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, unsigned __int16 serviceReportingKind, unsigned int addend)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18005deb0`

## callees

- `0x180005580`
- `0x180005874`
- `0x180006f0c`
- `0x1800587d8`
- `0x1800598d4`
- `0x18005bfd0`
- `0x18005e420`
- `0x18005e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c004`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c004`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c060`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c060`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        wil::details::FeatureStateManager *this,
        unsigned int featureId,
        unsigned __int16 serviceReportingKind,
        unsigned int addend)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  wil_details_FeatureUsageSRUM properties; // [rsp+20h] [rbp-48h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+30h] [rbp-38h] BYREF

  if ( this->m_fInitialized && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_SRUMlock.m_lock);
    lock.m_ptr = &this->m_SRUMlock.m_lock;
    *(&properties.serviceReportingKind + 1) = 0;
    properties.featureId = featureId;
    properties.serviceReportingKind = serviceReportingKind;
    properties.usageCount = addend;
    wil::details_abi::heap_buffer::push_back(&this->m_cachedSRUMUsageTrackingData.m_data, &properties, 0xCu);
    if ( !this->m_SRUMtimerSet )
    {
      if ( !this->m_SRUMtimer.m_ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&properties);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            this,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &this->m_SRUMtimer,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&properties);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&this->m_SRUMtimer, &this->m_SRUMtimerSet, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x18005bfd0  push    rbx
0x18005bfd2  push    rbp
0x18005bfd3  push    rsi
0x18005bfd4  push    rdi
0x18005bfd5  push    r14
0x18005bfd7  sub     rsp, 40h
0x18005bfdb  mov     r14d, addend
0x18005bfde  movzx   ebp, serviceReportingKind
0x18005bfe2  mov     esi, featureId
0x18005bfe4  mov     rdi, this
0x18005bfe7  cmp     byte ptr [this], 0
0x18005bfea  jz      loc_18005C098
0x18005bff0  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005bff5  test    al, al
0x18005bff7  jnz     loc_18005C098
0x18005bffd  lea     rbx, [rdi+28h]
0x18005c001  mov     this, rbx; SRWLock
0x18005c004  call    cs:__imp_AcquireSRWLockExclusive
0x18005c00a  mov     [rsp+68h+lock.m_ptr], rbx
0x18005c00f  xor     eax, eax
0x18005c011  mov     word ptr [rsp+68h+properties+6], ax
0x18005c016  mov     [rsp+68h+properties.featureId], esi
0x18005c01a  mov     [rsp+68h+properties.serviceReportingKind], bp
0x18005c01f  mov     [rsp+68h+properties.usageCount], r14d
0x18005c024  lea     this, [rdi+0E8h]; this
0x18005c02b  lea     r8d, [rax+0Ch]; appendSize
0x18005c02f  lea     rdx, [rsp+68h+properties]; data
0x18005c034  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18005c039  cmp     byte ptr [rdi+40h], 0
0x18005c03d  jnz     short loc_18005C08D
0x18005c03f  lea     rbx, [rdi+38h]
0x18005c043  cmp     qword ptr [rbx], 0
0x18005c047  jnz     short loc_18005C07B
0x18005c049  lea     this, [rsp+68h+properties]; this
0x18005c04e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005c053  xor     r8d, r8d; pcbe
0x18005c056  mov     rdx, rdi; pv
0x18005c059  lea     this, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005c060  call    cs:__imp_CreateThreadpoolTimer
0x18005c066  mov     rdx, rax; ptr
0x18005c069  mov     this, rbx; this
0x18005c06c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005c071  lea     this, [rsp+68h+properties]; this
0x18005c076  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005c07b  mov     r8d, 1388h; delay
0x18005c081  lea     rdx, [rdi+40h]; timerSet
0x18005c085  mov     this, rbx; timer
0x18005c088  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18005c08d  lea     this, [rsp+68h+lock]; this
0x18005c092  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005c097  nop
0x18005c098  add     rsp, 40h
0x18005c09c  pop     r14
0x18005c09e  pop     rdi
0x18005c09f  pop     rsi
0x18005c0a0  pop     rbp
0x18005c0a1  pop     rbx
0x18005c0a2  retn
```
