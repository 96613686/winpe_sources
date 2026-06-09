# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18011d334`
- end: `0x18011d411`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `221`
- prototype: `void __fastcall(wil::details::EnabledStateManager *this, unsigned int reporting, wil_details_FeatureReportingCache *id)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18011d4f0`

## callees

- `0x180094b10`
- `0x180094be8`
- `0x1800ba114`
- `0x1800ba134`
- `0x1800ba178`
- `0x1800ba198`
- `0x1800d0ed0`
- `0x18011d334`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011d367`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011d367`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011d3ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18011d3ca`

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
0x18011d334  mov     [rsp+arg_8], rbx
0x18011d339  mov     [rsp+arg_10], rsi
0x18011d33e  push    rdi
0x18011d33f  sub     rsp, 30h
0x18011d343  mov     eax, [this]
0x18011d345  mov     rsi, reporting
0x18011d348  mov     rdi, this
0x18011d34b  test    eax, eax
0x18011d34d  jz      loc_18011D401
0x18011d353  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18011d358  test    al, al
0x18011d35a  jnz     loc_18011D401
0x18011d360  lea     rbx, [rdi+8]
0x18011d364  mov     this, rbx; SRWLock
0x18011d367  call    cs:__imp_AcquireSRWLockExclusive
0x18011d36d  mov     eax, [rdi]
0x18011d36f  mov     [rsp+38h+lock.m_ptr], rbx
0x18011d374  test    eax, eax
0x18011d376  jz      short loc_18011D3F7
0x18011d378  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18011d37d  test    al, al
0x18011d37f  jnz     short loc_18011D3F7
0x18011d381  lea     this, [rdi+20h]; this
0x18011d385  mov     [rsp+38h+data], 1F20F4Dh
0x18011d38e  mov     r8d, 10h; appendSize
0x18011d394  mov     [rsp+38h+var_10], rsi
0x18011d399  lea     rdx, [rsp+38h+data]; data
0x18011d39e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18011d3a3  cmp     byte ptr [rdi+18h], 0
0x18011d3a7  jnz     short loc_18011D3F7
0x18011d3a9  lea     rbx, [rdi+10h]
0x18011d3ad  cmp     qword ptr [rbx], 0
0x18011d3b1  jnz     short loc_18011D3E5
0x18011d3b3  lea     this, [rsp+38h+arg_0]; this
0x18011d3b8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18011d3bd  xor     r8d, r8d; pcbe
0x18011d3c0  lea     this, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18011d3c7  mov     rdx, rdi; pv
0x18011d3ca  call    cs:__imp_CreateThreadpoolTimer
0x18011d3d0  mov     rdx, rax; ptr
0x18011d3d3  mov     this, rbx; this
0x18011d3d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18011d3db  lea     this, [rsp+38h+arg_0]; this
0x18011d3e0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18011d3e5  mov     r8d, 493E0h; delay
0x18011d3eb  lea     rdx, [rdi+18h]; timerSet
0x18011d3ef  mov     this, rbx; timer
0x18011d3f2  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18011d3f7  lea     this, [rsp+38h+lock]; this
0x18011d3fc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18011d401  mov     rbx, [rsp+38h+arg_8]
0x18011d406  mov     rsi, [rsp+38h+arg_10]
0x18011d40b  add     rsp, 30h
0x18011d40f  pop     rdi
0x18011d410  retn
```
