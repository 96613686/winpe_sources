# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003cfac`
- end: `0x18003d096`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003d8c4`

## callees

- `0x180024ac0`
- `0x180024de0`
- `0x180025fd8`
- `0x180035498`
- `0x180036fb8`
- `0x180036fdc`
- `0x180037024`
- `0x18003cfac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cfde`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cfde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d04a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d04a`

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
0x18003cfac  mov     [rsp+arg_8], rbx
0x18003cfb1  push    rbp
0x18003cfb2  push    rsi
0x18003cfb3  push    rdi
0x18003cfb4  sub     rsp, 30h
0x18003cfb8  mov     rsi, r8
0x18003cfbb  mov     ebp, edx
0x18003cfbd  mov     rdi, rcx
0x18003cfc0  mov     eax, [rcx]
0x18003cfc2  test    eax, eax
0x18003cfc4  jz      loc_18003D088
0x18003cfca  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003cfcf  test    al, al
0x18003cfd1  jnz     loc_18003D088
0x18003cfd7  lea     rbx, [rdi+8]
0x18003cfdb  mov     rcx, rbx; SRWLock
0x18003cfde  call    cs:__imp_AcquireSRWLockExclusive
0x18003cfe5  nop     dword ptr [rax+rax+00h]
0x18003cfea  mov     [rsp+48h+arg_18], rbx
0x18003cfef  mov     eax, [rdi]
0x18003cff1  test    eax, eax
0x18003cff3  jz      loc_18003D07D
0x18003cff9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003cffe  test    al, al
0x18003d000  jnz     short loc_18003D07D
0x18003d002  mov     [rsp+48h+var_28], ebp
0x18003d006  xor     eax, eax
0x18003d008  mov     [rsp+48h+var_24], eax
0x18003d00c  mov     [rsp+48h+var_20], rsi
0x18003d011  lea     rcx, [rdi+20h]; this
0x18003d015  lea     r8d, [rax+10h]; unsigned __int64
0x18003d019  lea     rdx, [rsp+48h+var_28]; void *
0x18003d01e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003d023  cmp     byte ptr [rdi+18h], 0
0x18003d027  jnz     short loc_18003D07D
0x18003d029  lea     rbx, [rdi+10h]
0x18003d02d  cmp     qword ptr [rbx], 0
0x18003d031  jnz     short loc_18003D06B
0x18003d033  lea     rcx, [rsp+48h+arg_0]; this
0x18003d038  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003d03d  xor     r8d, r8d; pcbe
0x18003d040  mov     rdx, rdi; pv
0x18003d043  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003d04a  call    cs:__imp_CreateThreadpoolTimer
0x18003d051  nop     dword ptr [rax+rax+00h]
0x18003d056  mov     rdx, rax
0x18003d059  mov     rcx, rbx
0x18003d05c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003d061  lea     rcx, [rsp+48h+arg_0]; this
0x18003d066  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003d06b  mov     r8d, 493E0h
0x18003d071  lea     rdx, [rdi+18h]
0x18003d075  mov     rcx, rbx
0x18003d078  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003d07d  lea     rcx, [rsp+48h+arg_18]
0x18003d082  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d087  nop
0x18003d088  mov     rbx, [rsp+48h+arg_8]
0x18003d08d  add     rsp, 30h
0x18003d091  pop     rdi
0x18003d092  pop     rsi
0x18003d093  pop     rbp
0x18003d094  retn
```
