# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000d124`
- end: `0x14000d201`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `221`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000462c`

## callees

- `0x140004110`
- `0x140004330`
- `0x140004dcc`
- `0x1400074b0`
- `0x14000782c`
- `0x140007fb4`
- `0x14000ba8c`
- `0x14000d124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d157`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d157`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d1ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d1ba`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+58h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v10 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v8[0] = 24159631;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x14000d124  mov     [rsp+arg_8], rbx
0x14000d129  mov     [rsp+arg_10], rsi
0x14000d12e  push    rdi
0x14000d12f  sub     rsp, 30h
0x14000d133  mov     eax, [rcx]
0x14000d135  mov     rsi, r8
0x14000d138  mov     rdi, rcx
0x14000d13b  test    eax, eax
0x14000d13d  jz      loc_14000D1F1
0x14000d143  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000d148  test    al, al
0x14000d14a  jnz     loc_14000D1F1
0x14000d150  lea     rbx, [rdi+8]
0x14000d154  mov     rcx, rbx; SRWLock
0x14000d157  call    cs:__imp_AcquireSRWLockExclusive
0x14000d15d  mov     eax, [rdi]
0x14000d15f  mov     [rsp+38h+arg_18], rbx
0x14000d164  test    eax, eax
0x14000d166  jz      short loc_14000D1E7
0x14000d168  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000d16d  test    al, al
0x14000d16f  jnz     short loc_14000D1E7
0x14000d171  lea     rcx, [rdi+20h]; this
0x14000d175  mov     [rsp+38h+var_18], 170A58Fh
0x14000d17e  mov     r8d, 10h; unsigned __int64
0x14000d184  mov     [rsp+38h+var_10], rsi
0x14000d189  lea     rdx, [rsp+38h+var_18]; void *
0x14000d18e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000d193  cmp     byte ptr [rdi+18h], 0
0x14000d197  jnz     short loc_14000D1E7
0x14000d199  lea     rbx, [rdi+10h]
0x14000d19d  cmp     qword ptr [rbx], 0
0x14000d1a1  jnz     short loc_14000D1D5
0x14000d1a3  lea     rcx, [rsp+38h+arg_0]; this
0x14000d1a8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000d1ad  xor     r8d, r8d; pcbe
0x14000d1b0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000d1b7  mov     rdx, rdi; pv
0x14000d1ba  call    cs:__imp_CreateThreadpoolTimer
0x14000d1c0  mov     rdx, rax
0x14000d1c3  mov     rcx, rbx
0x14000d1c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000d1cb  lea     rcx, [rsp+38h+arg_0]; this
0x14000d1d0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000d1d5  mov     r8d, 493E0h
0x14000d1db  lea     rdx, [rdi+18h]
0x14000d1df  mov     rcx, rbx
0x14000d1e2  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000d1e7  lea     rcx, [rsp+38h+arg_18]
0x14000d1ec  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000d1f1  mov     rbx, [rsp+38h+arg_8]
0x14000d1f6  mov     rsi, [rsp+38h+arg_10]
0x14000d1fb  add     rsp, 30h
0x14000d1ff  pop     rdi
0x14000d200  retn
```
