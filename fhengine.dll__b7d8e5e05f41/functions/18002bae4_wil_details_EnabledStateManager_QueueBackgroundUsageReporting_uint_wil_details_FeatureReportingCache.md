# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002bae4`
- end: `0x18002bbbd`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002ccf4`

## callees

- `0x1800277e4`
- `0x180027a6c`
- `0x180027dd8`
- `0x1800289e4`
- `0x18002b9b8`
- `0x18002bae4`
- `0x18002e58c`
- `0x18002e69c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18002bb16`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002bb16`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002bb78`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002bb78`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = (RTL_SRWLOCK *)(pv + 8);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18002bae4  mov     [rsp+arg_8], rbx
0x18002bae9  push    rbp
0x18002baea  push    rsi
0x18002baeb  push    rdi
0x18002baec  sub     rsp, 30h
0x18002baf0  mov     rsi, r8
0x18002baf3  mov     ebp, edx
0x18002baf5  mov     rdi, rcx
0x18002baf8  mov     eax, [rcx]
0x18002bafa  test    eax, eax
0x18002bafc  jz      loc_18002BBB0
0x18002bb02  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002bb07  test    al, al
0x18002bb09  jnz     loc_18002BBB0
0x18002bb0f  lea     rbx, [rdi+8]
0x18002bb13  mov     rcx, rbx; SRWLock
0x18002bb16  call    cs:__imp_AcquireSRWLockExclusive
0x18002bb1c  mov     [rsp+48h+arg_18], rbx
0x18002bb21  mov     eax, [rdi]
0x18002bb23  test    eax, eax
0x18002bb25  jz      short loc_18002BBA5
0x18002bb27  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002bb2c  test    al, al
0x18002bb2e  jnz     short loc_18002BBA5
0x18002bb30  mov     [rsp+48h+var_28], ebp
0x18002bb34  xor     eax, eax
0x18002bb36  mov     [rsp+48h+var_24], eax
0x18002bb3a  mov     [rsp+48h+var_20], rsi
0x18002bb3f  lea     rcx, [rdi+20h]; this
0x18002bb43  lea     r8d, [rax+10h]; unsigned __int64
0x18002bb47  lea     rdx, [rsp+48h+var_28]; void *
0x18002bb4c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002bb51  cmp     byte ptr [rdi+18h], 0
0x18002bb55  jnz     short loc_18002BBA5
0x18002bb57  lea     rbx, [rdi+10h]
0x18002bb5b  cmp     qword ptr [rbx], 0
0x18002bb5f  jnz     short loc_18002BB93
0x18002bb61  lea     rcx, [rsp+48h+arg_0]; this
0x18002bb66  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002bb6b  xor     r8d, r8d; pcbe
0x18002bb6e  mov     rdx, rdi; pv
0x18002bb71  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002bb78  call    cs:__imp_CreateThreadpoolTimer
0x18002bb7e  mov     rdx, rax
0x18002bb81  mov     rcx, rbx
0x18002bb84  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002bb89  lea     rcx, [rsp+48h+arg_0]; this
0x18002bb8e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002bb93  mov     r8d, 493E0h
0x18002bb99  lea     rdx, [rdi+18h]
0x18002bb9d  mov     rcx, rbx
0x18002bba0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002bba5  lea     rcx, [rsp+48h+arg_18]
0x18002bbaa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bbaf  nop
0x18002bbb0  mov     rbx, [rsp+48h+arg_8]
0x18002bbb5  add     rsp, 30h
0x18002bbb9  pop     rdi
0x18002bbba  pop     rsi
0x18002bbbb  pop     rbp
0x18002bbbc  retn
```
