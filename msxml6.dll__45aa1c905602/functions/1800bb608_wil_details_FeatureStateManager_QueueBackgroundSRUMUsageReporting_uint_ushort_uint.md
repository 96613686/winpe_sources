# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800bb608`
- end: `0x1800bb6f7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, unsigned __int16 serviceReportingKind, unsigned int addend)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800d2500`

## callees

- `0x180094ec4`
- `0x180094f9c`
- `0x1800bb608`
- `0x1800bb7d8`
- `0x1800bb7fc`
- `0x1800bb844`
- `0x1800bb868`
- `0x1800d2ab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb644`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb644`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb6a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb6a6`

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
0x1800bb608  mov     [rsp+arg_8], rbx
0x1800bb60d  mov     [rsp+arg_10], rbp
0x1800bb612  push    rsi
0x1800bb613  push    rdi
0x1800bb614  push    r14
0x1800bb616  sub     rsp, 40h
0x1800bb61a  cmp     byte ptr [this], 0
0x1800bb61d  mov     esi, addend
0x1800bb620  movzx   ebp, serviceReportingKind
0x1800bb624  mov     r14d, featureId
0x1800bb627  mov     rdi, this
0x1800bb62a  jz      loc_1800BB6E3
0x1800bb630  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800bb635  test    al, al
0x1800bb637  jnz     loc_1800BB6E3
0x1800bb63d  lea     rbx, [rdi+28h]
0x1800bb641  mov     this, rbx; SRWLock
0x1800bb644  call    cs:__imp_AcquireSRWLockExclusive
0x1800bb64b  nop     dword ptr [rax+rax+00h]
0x1800bb650  xor     eax, eax
0x1800bb652  mov     [rsp+58h+lock.m_ptr], rbx
0x1800bb657  lea     this, [rdi+0E8h]; this
0x1800bb65e  mov     word ptr [rsp+58h+properties+6], ax
0x1800bb663  lea     rdx, [rsp+58h+properties]; data
0x1800bb668  mov     [rsp+58h+properties.featureId], r14d
0x1800bb66d  mov     [rsp+58h+properties.serviceReportingKind], bp
0x1800bb672  lea     r8d, [rax+0Ch]; appendSize
0x1800bb676  mov     [rsp+58h+properties.usageCount], esi
0x1800bb67a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800bb67f  cmp     byte ptr [rdi+40h], 0
0x1800bb683  jnz     short loc_1800BB6D9
0x1800bb685  lea     rbx, [rdi+38h]
0x1800bb689  cmp     qword ptr [rbx], 0
0x1800bb68d  jnz     short loc_1800BB6C7
0x1800bb68f  lea     this, [rsp+58h+arg_0]; this
0x1800bb694  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800bb699  xor     r8d, r8d; pcbe
0x1800bb69c  lea     this, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800bb6a3  mov     rdx, rdi; pv
0x1800bb6a6  call    cs:__imp_CreateThreadpoolTimer
0x1800bb6ad  nop     dword ptr [rax+rax+00h]
0x1800bb6b2  mov     rdx, rax; ptr
0x1800bb6b5  mov     this, rbx; this
0x1800bb6b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800bb6bd  lea     this, [rsp+58h+arg_0]; this
0x1800bb6c2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800bb6c7  mov     r8d, 1388h; delay
0x1800bb6cd  lea     rdx, [rdi+40h]; timerSet
0x1800bb6d1  mov     this, rbx; timer
0x1800bb6d4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800bb6d9  lea     this, [rsp+58h+lock]; this
0x1800bb6de  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800bb6e3  mov     rbx, [rsp+58h+arg_8]
0x1800bb6e8  mov     rbp, [rsp+58h+arg_10]
0x1800bb6ed  add     rsp, 40h
0x1800bb6f1  pop     r14
0x1800bb6f3  pop     rdi
0x1800bb6f4  pop     rsi
0x1800bb6f5  retn
```
