# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800ba04c`
- end: `0x1800ba10d`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, unsigned int featureId, wil_details_ServiceReportingKind kind, unsigned __int64 addend)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800d09a0`

## callees

- `0x180094b10`
- `0x180094be8`
- `0x1800ba04c`
- `0x1800ba114`
- `0x1800ba134`
- `0x1800ba178`
- `0x1800ba198`
- `0x1800cdf88`
- `0x1800cfb14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ba09b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ba09b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ba0cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ba0cd`

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
0x1800ba04c  push    rbx
0x1800ba04e  push    rbp
0x1800ba04f  push    rsi
0x1800ba050  push    rdi
0x1800ba051  sub     rsp, 38h
0x1800ba055  cmp     byte ptr [this], 0
0x1800ba058  mov     rbx, addend
0x1800ba05b  mov     esi, kind
0x1800ba05e  mov     ebp, featureId
0x1800ba060  mov     rdi, this
0x1800ba063  jz      loc_1800BA104
0x1800ba069  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800ba06e  test    al, al
0x1800ba070  jz      loc_1800BA104
0x1800ba076  mov     this, [rdi+18h]; this
0x1800ba07a  mov     addend, rbx; addend
0x1800ba07d  mov     kind, esi; kind
0x1800ba080  mov     featureId, ebp; featureId
0x1800ba082  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800ba087  test    al, al
0x1800ba089  jz      short loc_1800BA104
0x1800ba08b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800ba090  test    al, al
0x1800ba092  jnz     short loc_1800BA104
0x1800ba094  lea     rbx, [rdi+20h]
0x1800ba098  mov     this, rbx; SRWLock
0x1800ba09b  call    cs:__imp_AcquireSRWLockExclusive
0x1800ba0a1  cmp     byte ptr [rdi+41h], 0
0x1800ba0a5  mov     [rsp+58h+lock.m_ptr], rbx
0x1800ba0aa  jnz     short loc_1800BA0FA
0x1800ba0ac  lea     rbx, [rdi+30h]
0x1800ba0b0  cmp     qword ptr [rbx], 0
0x1800ba0b4  jnz     short loc_1800BA0E8
0x1800ba0b6  lea     this, [rsp+58h+arg_0]; this
0x1800ba0bb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800ba0c0  xor     kind, kind; pcbe
0x1800ba0c3  lea     this, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800ba0ca  mov     rdx, rdi; pv
0x1800ba0cd  call    cs:__imp_CreateThreadpoolTimer
0x1800ba0d3  mov     rdx, rax; ptr
0x1800ba0d6  mov     this, rbx; this
0x1800ba0d9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800ba0de  lea     this, [rsp+58h+arg_0]; this
0x1800ba0e3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ba0e8  mov     kind, 493E0h; delay
0x1800ba0ee  lea     rdx, [rdi+41h]; timerSet
0x1800ba0f2  mov     this, rbx; timer
0x1800ba0f5  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800ba0fa  lea     this, [rsp+58h+lock]; this
0x1800ba0ff  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ba104  add     rsp, 38h
0x1800ba108  pop     rdi
0x1800ba109  pop     rsi
0x1800ba10a  pop     rbp
0x1800ba10b  pop     rbx
0x1800ba10c  retn
```
