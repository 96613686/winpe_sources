# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180019f10`
- end: `0x180019ff4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `228`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180039348`

## callees

- `0x18000d7a8`
- `0x18000d810`
- `0x18000ef90`
- `0x180019f10`
- `0x18001a1c0`
- `0x18001a36c`
- `0x18003aa5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019f42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019f42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fc4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019fa8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019fa8`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+54h] [rbp+Ch]
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v12 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            if ( !v10 )
              SetLastError(dwErrCode);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180019f10  mov     [rsp+arg_8], rbx
0x180019f15  push    rbp
0x180019f16  push    rsi
0x180019f17  push    rdi
0x180019f18  sub     rsp, 30h
0x180019f1c  mov     rsi, r8
0x180019f1f  mov     ebp, edx
0x180019f21  mov     rdi, rcx
0x180019f24  mov     eax, [rcx]
0x180019f26  test    eax, eax
0x180019f28  jz      loc_180019FE7
0x180019f2e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180019f33  test    al, al
0x180019f35  jnz     loc_180019FE7
0x180019f3b  lea     rbx, [rdi+8]
0x180019f3f  mov     rcx, rbx; SRWLock
0x180019f42  call    cs:__imp_AcquireSRWLockExclusive
0x180019f48  mov     [rsp+48h+arg_18], rbx
0x180019f4d  mov     eax, [rdi]
0x180019f4f  test    eax, eax
0x180019f51  jz      loc_180019FDC
0x180019f57  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180019f5c  test    al, al
0x180019f5e  jnz     short loc_180019FDC
0x180019f60  mov     [rsp+48h+var_28], ebp
0x180019f64  xor     eax, eax
0x180019f66  mov     [rsp+48h+var_24], eax
0x180019f6a  mov     [rsp+48h+var_20], rsi
0x180019f6f  lea     rcx, [rdi+20h]; this
0x180019f73  lea     r8d, [rax+10h]; unsigned __int64
0x180019f77  lea     rdx, [rsp+48h+var_28]; void *
0x180019f7c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180019f81  cmp     byte ptr [rdi+18h], 0
0x180019f85  jnz     short loc_180019FDC
0x180019f87  lea     rbx, [rdi+10h]
0x180019f8b  cmp     qword ptr [rbx], 0
0x180019f8f  jnz     short loc_180019FCA
0x180019f91  lea     rcx, [rsp+48h+arg_0]; this
0x180019f96  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180019f9b  xor     r8d, r8d; pcbe
0x180019f9e  mov     rdx, rdi; pv
0x180019fa1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019fa8  call    cs:__imp_CreateThreadpoolTimer
0x180019fae  mov     rdx, rax
0x180019fb1  mov     rcx, rbx
0x180019fb4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180019fb9  cmp     [rsp+48h+arg_0], 0
0x180019fbe  jnz     short loc_180019FCA
0x180019fc0  mov     ecx, [rsp+48h+dwErrCode]; dwErrCode
0x180019fc4  call    cs:__imp_SetLastError
0x180019fca  mov     r8d, 493E0h
0x180019fd0  lea     rdx, [rdi+18h]
0x180019fd4  mov     rcx, rbx
0x180019fd7  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180019fdc  lea     rcx, [rsp+48h+arg_18]
0x180019fe1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019fe6  nop
0x180019fe7  mov     rbx, [rsp+48h+arg_8]
0x180019fec  add     rsp, 30h
0x180019ff0  pop     rdi
0x180019ff1  pop     rsi
0x180019ff2  pop     rbp
0x180019ff3  retn
```
