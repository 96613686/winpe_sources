# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002a270`
- end: `0x18002a349`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002a990`

## callees

- `0x1800050f4`
- `0x1800054a4`
- `0x180007038`
- `0x18000d664`
- `0x18001ab30`
- `0x18001cfe0`
- `0x18001d0e8`
- `0x18002a270`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a2a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a2a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002a304`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002a304`

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
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v11 = pv + 1;
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
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18002a270  mov     [rsp+arg_8], rbx
0x18002a275  push    rbp
0x18002a276  push    rsi
0x18002a277  push    rdi
0x18002a278  sub     rsp, 30h
0x18002a27c  mov     rsi, r8
0x18002a27f  mov     ebp, edx
0x18002a281  mov     rdi, rcx
0x18002a284  mov     eax, [rcx]
0x18002a286  test    eax, eax
0x18002a288  jz      loc_18002A33C
0x18002a28e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002a293  test    al, al
0x18002a295  jnz     loc_18002A33C
0x18002a29b  lea     rbx, [rdi+8]
0x18002a29f  mov     rcx, rbx; SRWLock
0x18002a2a2  call    cs:__imp_AcquireSRWLockExclusive
0x18002a2a8  mov     [rsp+48h+arg_18], rbx
0x18002a2ad  mov     eax, [rdi]
0x18002a2af  test    eax, eax
0x18002a2b1  jz      short loc_18002A331
0x18002a2b3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002a2b8  test    al, al
0x18002a2ba  jnz     short loc_18002A331
0x18002a2bc  mov     [rsp+48h+var_28], ebp
0x18002a2c0  xor     eax, eax
0x18002a2c2  mov     [rsp+48h+var_24], eax
0x18002a2c6  mov     [rsp+48h+var_20], rsi
0x18002a2cb  lea     rcx, [rdi+20h]; this
0x18002a2cf  lea     r8d, [rax+10h]; unsigned __int64
0x18002a2d3  lea     rdx, [rsp+48h+var_28]; void *
0x18002a2d8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002a2dd  cmp     byte ptr [rdi+18h], 0
0x18002a2e1  jnz     short loc_18002A331
0x18002a2e3  lea     rbx, [rdi+10h]
0x18002a2e7  cmp     qword ptr [rbx], 0
0x18002a2eb  jnz     short loc_18002A31F
0x18002a2ed  lea     rcx, [rsp+48h+arg_0]; this
0x18002a2f2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002a2f7  xor     r8d, r8d; pcbe
0x18002a2fa  mov     rdx, rdi; pv
0x18002a2fd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002a304  call    cs:__imp_CreateThreadpoolTimer
0x18002a30a  mov     rdx, rax
0x18002a30d  mov     rcx, rbx
0x18002a310  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002a315  lea     rcx, [rsp+48h+arg_0]; this
0x18002a31a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002a31f  mov     r8d, 493E0h
0x18002a325  lea     rdx, [rdi+18h]
0x18002a329  mov     rcx, rbx
0x18002a32c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002a331  lea     rcx, [rsp+48h+arg_18]
0x18002a336  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a33b  nop
0x18002a33c  mov     rbx, [rsp+48h+arg_8]
0x18002a341  add     rsp, 30h
0x18002a345  pop     rdi
0x18002a346  pop     rsi
0x18002a347  pop     rbp
0x18002a348  retn
```
