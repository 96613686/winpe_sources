# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180009ec4`
- end: `0x180009fa2`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `222`
- prototype: `void __fastcall(char *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a5cc`

## callees

- `0x1800074a0`
- `0x180007984`
- `0x180007c98`
- `0x1800083a0`
- `0x180009da4`
- `0x180009ec4`
- `0x18000ca44`
- `0x18000cbf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ef7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ef7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009f5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009f5a`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v9 = (RTL_SRWLOCK *)(pv + 8);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v7[0] = 23806551;
        v7[1] = a3;
        wil::details_abi::heap_buffer::push_back((void **)pv + 4, v7, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x180009ec4  mov     [rsp+arg_8], rbx
0x180009ec9  mov     [rsp+arg_10], rsi
0x180009ece  push    rdi
0x180009ecf  sub     rsp, 30h
0x180009ed3  mov     rsi, r8
0x180009ed6  mov     rdi, rcx
0x180009ed9  mov     eax, [rcx]
0x180009edb  test    eax, eax
0x180009edd  jz      loc_180009F92
0x180009ee3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180009ee8  test    al, al
0x180009eea  jnz     loc_180009F92
0x180009ef0  lea     rbx, [rdi+8]
0x180009ef4  mov     rcx, rbx; SRWLock
0x180009ef7  call    cs:__imp_AcquireSRWLockExclusive
0x180009efd  mov     [rsp+38h+arg_18], rbx
0x180009f02  mov     eax, [rdi]
0x180009f04  test    eax, eax
0x180009f06  jz      short loc_180009F87
0x180009f08  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180009f0d  test    al, al
0x180009f0f  jnz     short loc_180009F87
0x180009f11  mov     [rsp+38h+var_18], 16B4257h
0x180009f1a  mov     [rsp+38h+var_10], rsi
0x180009f1f  lea     rcx, [rdi+20h]; this
0x180009f23  mov     r8d, 10h; unsigned __int64
0x180009f29  lea     rdx, [rsp+38h+var_18]; void *
0x180009f2e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180009f33  cmp     byte ptr [rdi+18h], 0
0x180009f37  jnz     short loc_180009F87
0x180009f39  lea     rbx, [rdi+10h]
0x180009f3d  cmp     qword ptr [rbx], 0
0x180009f41  jnz     short loc_180009F75
0x180009f43  lea     rcx, [rsp+38h+arg_0]; this
0x180009f48  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009f4d  xor     r8d, r8d; pcbe
0x180009f50  mov     rdx, rdi; pv
0x180009f53  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009f5a  call    cs:__imp_CreateThreadpoolTimer
0x180009f60  mov     rdx, rax
0x180009f63  mov     rcx, rbx
0x180009f66  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009f6b  lea     rcx, [rsp+38h+arg_0]; this
0x180009f70  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009f75  mov     r8d, 493E0h
0x180009f7b  lea     rdx, [rdi+18h]
0x180009f7f  mov     rcx, rbx
0x180009f82  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180009f87  lea     rcx, [rsp+38h+arg_18]
0x180009f8c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009f91  nop
0x180009f92  mov     rbx, [rsp+38h+arg_8]
0x180009f97  mov     rsi, [rsp+38h+arg_10]
0x180009f9c  add     rsp, 30h
0x180009fa0  pop     rdi
0x180009fa1  retn
```
