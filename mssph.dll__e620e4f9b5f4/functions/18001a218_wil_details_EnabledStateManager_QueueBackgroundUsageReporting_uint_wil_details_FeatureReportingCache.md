# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001a218`
- end: `0x18001a2fc`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `228`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000ee60`

## callees

- `0x18000b4e0`
- `0x18000c010`
- `0x18000d008`
- `0x18000d118`
- `0x18000d138`
- `0x180015b28`
- `0x18001a218`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a24a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a24a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a2cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a2cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a2b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a2b0`

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
  DWORD dwErrCode; // [rsp+54h] [rbp+Ch]
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v12 = (RTL_SRWLOCK *)(pv + 8);
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
            if ( !v10 )
              SetLastError(dwErrCode);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18001a218  mov     [rsp+arg_8], rbx
0x18001a21d  push    rbp
0x18001a21e  push    rsi
0x18001a21f  push    rdi
0x18001a220  sub     rsp, 30h
0x18001a224  mov     rsi, r8
0x18001a227  mov     ebp, edx
0x18001a229  mov     rdi, rcx
0x18001a22c  mov     eax, [rcx]
0x18001a22e  test    eax, eax
0x18001a230  jz      loc_18001A2EF
0x18001a236  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a23b  test    al, al
0x18001a23d  jnz     loc_18001A2EF
0x18001a243  lea     rbx, [rdi+8]
0x18001a247  mov     rcx, rbx; SRWLock
0x18001a24a  call    cs:__imp_AcquireSRWLockExclusive
0x18001a250  mov     [rsp+48h+arg_18], rbx
0x18001a255  mov     eax, [rdi]
0x18001a257  test    eax, eax
0x18001a259  jz      loc_18001A2E4
0x18001a25f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a264  test    al, al
0x18001a266  jnz     short loc_18001A2E4
0x18001a268  mov     [rsp+48h+var_28], ebp
0x18001a26c  xor     eax, eax
0x18001a26e  mov     [rsp+48h+var_24], eax
0x18001a272  mov     [rsp+48h+var_20], rsi
0x18001a277  lea     rcx, [rdi+20h]; this
0x18001a27b  lea     r8d, [rax+10h]; unsigned __int64
0x18001a27f  lea     rdx, [rsp+48h+var_28]; void *
0x18001a284  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a289  cmp     byte ptr [rdi+18h], 0
0x18001a28d  jnz     short loc_18001A2E4
0x18001a28f  lea     rbx, [rdi+10h]
0x18001a293  cmp     qword ptr [rbx], 0
0x18001a297  jnz     short loc_18001A2D2
0x18001a299  lea     rcx, [rsp+48h+arg_0]; this
0x18001a29e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a2a3  xor     r8d, r8d; pcbe
0x18001a2a6  mov     rdx, rdi; pv
0x18001a2a9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001a2b0  call    cs:__imp_CreateThreadpoolTimer
0x18001a2b6  mov     rdx, rax
0x18001a2b9  mov     rcx, rbx
0x18001a2bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001a2c1  cmp     [rsp+48h+arg_0], 0
0x18001a2c6  jnz     short loc_18001A2D2
0x18001a2c8  mov     ecx, [rsp+48h+dwErrCode]; dwErrCode
0x18001a2cc  call    cs:__imp_SetLastError
0x18001a2d2  mov     r8d, 493E0h
0x18001a2d8  lea     rdx, [rdi+18h]
0x18001a2dc  mov     rcx, rbx
0x18001a2df  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001a2e4  lea     rcx, [rsp+48h+arg_18]
0x18001a2e9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001a2ee  nop
0x18001a2ef  mov     rbx, [rsp+48h+arg_8]
0x18001a2f4  add     rsp, 30h
0x18001a2f8  pop     rdi
0x18001a2f9  pop     rsi
0x18001a2fa  pop     rbp
0x18001a2fb  retn
```
