# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800bb700`
- end: `0x1800bb7d2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `210`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, wil_details_ServiceReportingKind kind, unsigned __int64 addend)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800d2500`

## callees

- `0x180094ec4`
- `0x180094f9c`
- `0x1800bb700`
- `0x1800bb7d8`
- `0x1800bb7fc`
- `0x1800bb844`
- `0x1800bb868`
- `0x1800cf98c`
- `0x1800d15d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb753`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb753`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb78b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb78b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        wil::details::FeatureStateManager *this,
        unsigned int featureId,
        wil_details_ServiceReportingKind kind,
        unsigned __int64 addend)
{
  bool v8; // zf
  _TP_TIMER *ThreadpoolTimer; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+20h] [rbp-38h] BYREF
  wil::last_error_context v11; // [rsp+60h] [rbp+8h] BYREF

  if ( this->m_fInitialized
    && wil::details::FeatureStateManager::EnsureStateData(this)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(this->m_data, featureId, kind, addend)
    && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    v8 = !this->m_timerSet;
    lock.m_ptr = &this->m_lock.m_lock;
    if ( v8 )
    {
      if ( !this->m_timer.m_ptr )
      {
        wil::last_error_context::last_error_context(&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            this,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &this->m_timer,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context(&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&this->m_timer, &this->m_timerSet, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x1800bb700  push    rbx
0x1800bb702  push    rbp
0x1800bb703  push    rsi
0x1800bb704  push    rdi
0x1800bb705  sub     rsp, 38h
0x1800bb709  cmp     byte ptr [this], 0
0x1800bb70c  mov     rbx, addend
0x1800bb70f  mov     esi, kind
0x1800bb712  mov     ebp, featureId
0x1800bb714  mov     rdi, this
0x1800bb717  jz      loc_1800BB7C8
0x1800bb71d  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800bb722  test    al, al
0x1800bb724  jz      loc_1800BB7C8
0x1800bb72a  mov     this, [rdi+18h]; this
0x1800bb72e  mov     addend, rbx; addend
0x1800bb731  mov     kind, esi; kind
0x1800bb734  mov     featureId, ebp; featureId
0x1800bb736  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800bb73b  test    al, al
0x1800bb73d  jz      loc_1800BB7C8
0x1800bb743  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800bb748  test    al, al
0x1800bb74a  jnz     short loc_1800BB7C8
0x1800bb74c  lea     rbx, [rdi+20h]
0x1800bb750  mov     this, rbx; SRWLock
0x1800bb753  call    cs:__imp_AcquireSRWLockExclusive
0x1800bb75a  nop     dword ptr [rax+rax+00h]
0x1800bb75f  cmp     byte ptr [rdi+41h], 0
0x1800bb763  mov     [rsp+58h+lock.m_ptr], rbx
0x1800bb768  jnz     short loc_1800BB7BE
0x1800bb76a  lea     rbx, [rdi+30h]
0x1800bb76e  cmp     qword ptr [rbx], 0
0x1800bb772  jnz     short loc_1800BB7AC
0x1800bb774  lea     this, [rsp+58h+arg_0]; this
0x1800bb779  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800bb77e  xor     kind, kind; pcbe
0x1800bb781  lea     this, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800bb788  mov     rdx, rdi; pv
0x1800bb78b  call    cs:__imp_CreateThreadpoolTimer
0x1800bb792  nop     dword ptr [rax+rax+00h]
0x1800bb797  mov     rdx, rax; ptr
0x1800bb79a  mov     this, rbx; this
0x1800bb79d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800bb7a2  lea     this, [rsp+58h+arg_0]; this
0x1800bb7a7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800bb7ac  mov     kind, 493E0h; delay
0x1800bb7b2  lea     rdx, [rdi+41h]; timerSet
0x1800bb7b6  mov     this, rbx; timer
0x1800bb7b9  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800bb7be  lea     this, [rsp+58h+lock]; this
0x1800bb7c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800bb7c8  add     rsp, 38h
0x1800bb7cc  pop     rdi
0x1800bb7cd  pop     rsi
0x1800bb7ce  pop     rbp
0x1800bb7cf  pop     rbx
0x1800bb7d0  retn
```
