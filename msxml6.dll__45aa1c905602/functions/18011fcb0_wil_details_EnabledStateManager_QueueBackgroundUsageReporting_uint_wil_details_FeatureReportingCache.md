# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18011fcb0`
- end: `0x18011fd9e`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `238`
- prototype: `void __fastcall(wil::details::EnabledStateManager *this, unsigned int reporting, wil_details_FeatureReportingCache *id)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18011fe84`

## callees

- `0x180094ec4`
- `0x180094f9c`
- `0x1800bb7d8`
- `0x1800bb7fc`
- `0x1800bb844`
- `0x1800bb868`
- `0x1800d2ab4`
- `0x18011fcb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011fce3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011fce3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011fd50`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011fd50`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        wil::details::EnabledStateManager *this,
        unsigned int reporting,
        wil_details_FeatureReportingCache *id)
{
  volatile int m_fInitialized; // eax
  _TP_TIMER *ThreadpoolTimer; // rax
  _QWORD data[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::last_error_context v8; // [rsp+40h] [rbp+8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+58h] [rbp+20h] BYREF

  if ( this->m_fInitialized && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    m_fInitialized = this->m_fInitialized;
    lock.m_ptr = &this->m_lock.m_lock;
    if ( m_fInitialized )
    {
      if ( !wil::ProcessShutdownInProgress() )
      {
        data[0] = 32640845;
        data[1] = id;
        wil::details_abi::heap_buffer::push_back(&this->m_cachedUsageTrackingData.m_data, data, 0x10u);
        if ( !this->m_timerSet )
        {
          if ( !this->m_timer.m_ptr )
          {
            wil::last_error_context::last_error_context(&v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                this,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &this->m_timer,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context(&v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&this->m_timer, &this->m_timerSet, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
  }
}

```

## disassembly

```asm
0x18011fcb0  mov     [rsp+arg_8], rbx
0x18011fcb5  mov     [rsp+arg_10], rsi
0x18011fcba  push    rdi
0x18011fcbb  sub     rsp, 30h
0x18011fcbf  mov     eax, [this]
0x18011fcc1  mov     rsi, reporting
0x18011fcc4  mov     rdi, this
0x18011fcc7  test    eax, eax
0x18011fcc9  jz      loc_18011FD8D
0x18011fccf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18011fcd4  test    al, al
0x18011fcd6  jnz     loc_18011FD8D
0x18011fcdc  lea     rbx, [rdi+8]
0x18011fce0  mov     this, rbx; SRWLock
0x18011fce3  call    cs:__imp_AcquireSRWLockExclusive
0x18011fcea  nop     dword ptr [rax+rax+00h]
0x18011fcef  mov     eax, [rdi]
0x18011fcf1  mov     [rsp+38h+lock.m_ptr], rbx
0x18011fcf6  test    eax, eax
0x18011fcf8  jz      loc_18011FD83
0x18011fcfe  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18011fd03  test    al, al
0x18011fd05  jnz     short loc_18011FD83
0x18011fd07  lea     this, [rdi+30h]; this
0x18011fd0b  mov     [rsp+38h+data], 1F20F4Dh
0x18011fd14  mov     r8d, 10h; appendSize
0x18011fd1a  mov     [rsp+38h+var_10], rsi
0x18011fd1f  lea     rdx, [rsp+38h+data]; data
0x18011fd24  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18011fd29  cmp     byte ptr [rdi+18h], 0
0x18011fd2d  jnz     short loc_18011FD83
0x18011fd2f  lea     rbx, [rdi+10h]
0x18011fd33  cmp     qword ptr [rbx], 0
0x18011fd37  jnz     short loc_18011FD71
0x18011fd39  lea     this, [rsp+38h+arg_0]; this
0x18011fd3e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18011fd43  xor     r8d, r8d; pcbe
0x18011fd46  lea     this, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18011fd4d  mov     rdx, rdi; pv
0x18011fd50  call    cs:__imp_CreateThreadpoolTimer
0x18011fd57  nop     dword ptr [rax+rax+00h]
0x18011fd5c  mov     rdx, rax; ptr
0x18011fd5f  mov     this, rbx; this
0x18011fd62  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18011fd67  lea     this, [rsp+38h+arg_0]; this
0x18011fd6c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18011fd71  mov     r8d, 493E0h; delay
0x18011fd77  lea     rdx, [rdi+18h]; timerSet
0x18011fd7b  mov     this, rbx; timer
0x18011fd7e  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18011fd83  lea     this, [rsp+38h+lock]; this
0x18011fd88  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011fd8d  mov     rbx, [rsp+38h+arg_8]
0x18011fd92  mov     rsi, [rsp+38h+arg_10]
0x18011fd97  add     rsp, 30h
0x18011fd9b  pop     rdi
0x18011fd9c  retn
```
