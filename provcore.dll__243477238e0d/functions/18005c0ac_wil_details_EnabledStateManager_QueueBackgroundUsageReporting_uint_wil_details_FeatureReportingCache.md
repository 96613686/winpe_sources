# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18005c0ac`
- end: `0x18005c185`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(wil::details::EnabledStateManager *this, unsigned int id, wil_details_FeatureReportingCache *reporting)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005d4b8`

## callees

- `0x180005580`
- `0x180005874`
- `0x180006f0c`
- `0x1800587d8`
- `0x1800598d4`
- `0x18005c0ac`
- `0x18005e420`
- `0x18005e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c0de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c0de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c140`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c140`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        wil::details::EnabledStateManager *this,
        unsigned int id,
        wil_details_FeatureReportingCache *reporting)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  wil::last_error_context data[2]; // [rsp+20h] [rbp-38h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+30h] [rbp-28h] BYREF

  if ( this->m_fInitialized && !wil::ProcessShutdownInProgress() )
  {
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    lock.m_ptr = &this->m_lock.m_lock;
    if ( this->m_fInitialized )
    {
      if ( !wil::ProcessShutdownInProgress() )
      {
        *(_DWORD *)&data[0].m_dismissed = id;
        data[0].m_error = 0;
        data[1] = (wil::last_error_context)reporting;
        wil::details_abi::heap_buffer::push_back(&this->m_cachedUsageTrackingData.m_data, data, 0x10u);
        if ( !this->m_timerSet )
        {
          if ( !this->m_timer.m_ptr )
          {
            wil::last_error_context::last_error_context(data);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                                this,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &this->m_timer,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context(data);
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
0x18005c0ac  mov     [rsp+arg_18], rbx
0x18005c0b1  push    rbp
0x18005c0b2  push    rsi
0x18005c0b3  push    rdi
0x18005c0b4  sub     rsp, 40h
0x18005c0b8  mov     rbp, reporting
0x18005c0bb  mov     esi, id
0x18005c0bd  mov     rdi, this
0x18005c0c0  mov     eax, [this]
0x18005c0c2  test    eax, eax
0x18005c0c4  jz      loc_18005C178
0x18005c0ca  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005c0cf  test    al, al
0x18005c0d1  jnz     loc_18005C178
0x18005c0d7  lea     rbx, [rdi+8]
0x18005c0db  mov     this, rbx; SRWLock
0x18005c0de  call    cs:__imp_AcquireSRWLockExclusive
0x18005c0e4  mov     [rsp+58h+lock.m_ptr], rbx
0x18005c0e9  mov     eax, [rdi]
0x18005c0eb  test    eax, eax
0x18005c0ed  jz      short loc_18005C16D
0x18005c0ef  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005c0f4  test    al, al
0x18005c0f6  jnz     short loc_18005C16D
0x18005c0f8  mov     [rsp+58h+data], esi
0x18005c0fc  xor     eax, eax
0x18005c0fe  mov     [rsp+58h+var_34], eax
0x18005c102  mov     [rsp+58h+var_30], rbp
0x18005c107  lea     this, [rdi+20h]; this
0x18005c10b  lea     r8d, [rax+10h]; appendSize
0x18005c10f  lea     rdx, [rsp+58h+data]; data
0x18005c114  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18005c119  cmp     byte ptr [rdi+18h], 0
0x18005c11d  jnz     short loc_18005C16D
0x18005c11f  lea     rbx, [rdi+10h]
0x18005c123  cmp     qword ptr [rbx], 0
0x18005c127  jnz     short loc_18005C15B
0x18005c129  lea     this, [rsp+58h+data]; this
0x18005c12e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005c133  xor     r8d, r8d; pcbe
0x18005c136  mov     rdx, rdi; pv
0x18005c139  lea     this, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005c140  call    cs:__imp_CreateThreadpoolTimer
0x18005c146  mov     rdx, rax; ptr
0x18005c149  mov     this, rbx; this
0x18005c14c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005c151  lea     this, [rsp+58h+data]; this
0x18005c156  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005c15b  mov     r8d, 493E0h; delay
0x18005c161  lea     rdx, [rdi+18h]; timerSet
0x18005c165  mov     this, rbx; timer
0x18005c168  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18005c16d  lea     this, [rsp+58h+lock]; this
0x18005c172  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005c177  nop
0x18005c178  mov     rbx, [rsp+58h+arg_18]
0x18005c17d  add     rsp, 40h
0x18005c181  pop     rdi
0x18005c182  pop     rsi
0x18005c183  pop     rbp
0x18005c184  retn
```
