# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800b9f64`
- end: `0x1800ba046`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `226`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, unsigned __int16 serviceReportingKind, unsigned int addend)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800d09a0`

## callees

- `0x180094b10`
- `0x180094be8`
- `0x1800b9f64`
- `0x1800ba114`
- `0x1800ba134`
- `0x1800ba178`
- `0x1800ba198`
- `0x1800d0ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9fa0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9fa0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b9ffc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b9ffc`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        wil::details::FeatureStateManager *this,
        unsigned int featureId,
        unsigned __int16 serviceReportingKind,
        unsigned int addend)
{
  _TP_TIMER *ThreadpoolTimer; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+20h] [rbp-38h] BYREF
  wil_details_FeatureUsageSRUM properties; // [rsp+28h] [rbp-30h] BYREF
  wil::last_error_context v11; // [rsp+60h] [rbp+8h] BYREF

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
        wil::last_error_context::last_error_context(&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            this,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &this->m_SRUMtimer,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context(&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&this->m_SRUMtimer, &this->m_SRUMtimerSet, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x1800b9f64  mov     [rsp+arg_8], rbx
0x1800b9f69  mov     [rsp+arg_10], rbp
0x1800b9f6e  push    rsi
0x1800b9f6f  push    rdi
0x1800b9f70  push    r14
0x1800b9f72  sub     rsp, 40h
0x1800b9f76  cmp     byte ptr [this], 0
0x1800b9f79  mov     esi, addend
0x1800b9f7c  movzx   ebp, serviceReportingKind
0x1800b9f80  mov     r14d, featureId
0x1800b9f83  mov     rdi, this
0x1800b9f86  jz      loc_1800BA033
0x1800b9f8c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800b9f91  test    al, al
0x1800b9f93  jnz     loc_1800BA033
0x1800b9f99  lea     rbx, [rdi+28h]
0x1800b9f9d  mov     this, rbx; SRWLock
0x1800b9fa0  call    cs:__imp_AcquireSRWLockExclusive
0x1800b9fa6  xor     eax, eax
0x1800b9fa8  mov     [rsp+58h+lock.m_ptr], rbx
0x1800b9fad  lea     this, [rdi+0E8h]; this
0x1800b9fb4  mov     word ptr [rsp+58h+properties+6], ax
0x1800b9fb9  lea     rdx, [rsp+58h+properties]; data
0x1800b9fbe  mov     [rsp+58h+properties.featureId], r14d
0x1800b9fc3  mov     [rsp+58h+properties.serviceReportingKind], bp
0x1800b9fc8  lea     r8d, [rax+0Ch]; appendSize
0x1800b9fcc  mov     [rsp+58h+properties.usageCount], esi
0x1800b9fd0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800b9fd5  cmp     byte ptr [rdi+40h], 0
0x1800b9fd9  jnz     short loc_1800BA029
0x1800b9fdb  lea     rbx, [rdi+38h]
0x1800b9fdf  cmp     qword ptr [rbx], 0
0x1800b9fe3  jnz     short loc_1800BA017
0x1800b9fe5  lea     this, [rsp+58h+arg_0]; this
0x1800b9fea  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800b9fef  xor     r8d, r8d; pcbe
0x1800b9ff2  lea     this, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800b9ff9  mov     rdx, rdi; pv
0x1800b9ffc  call    cs:__imp_CreateThreadpoolTimer
0x1800ba002  mov     rdx, rax; ptr
0x1800ba005  mov     this, rbx; this
0x1800ba008  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800ba00d  lea     this, [rsp+58h+arg_0]; this
0x1800ba012  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ba017  mov     r8d, 1388h; delay
0x1800ba01d  lea     rdx, [rdi+40h]; timerSet
0x1800ba021  mov     this, rbx; timer
0x1800ba024  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800ba029  lea     this, [rsp+58h+lock]; this
0x1800ba02e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ba033  mov     rbx, [rsp+58h+arg_8]
0x1800ba038  mov     rbp, [rsp+58h+arg_10]
0x1800ba03d  add     rsp, 40h
0x1800ba041  pop     r14
0x1800ba043  pop     rdi
0x1800ba044  pop     rsi
0x1800ba045  retn
```
