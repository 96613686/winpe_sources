# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800ec2e8`
- end: `0x1800ec3d2`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800ed0b0`

## callees

- `0x1800e734c`
- `0x1800e7e30`
- `0x1800e8508`
- `0x1800e95f4`
- `0x1800ec210`
- `0x1800ec2e8`
- `0x1800f1a5c`
- `0x1800f1bc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ec31a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ec31a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ec386`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ec386`

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
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v8, 0x10u);
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
0x1800ec2e8  mov     [rsp+arg_8], rbx
0x1800ec2ed  push    rbp
0x1800ec2ee  push    rsi
0x1800ec2ef  push    rdi
0x1800ec2f0  sub     rsp, 30h
0x1800ec2f4  mov     rsi, r8
0x1800ec2f7  mov     ebp, edx
0x1800ec2f9  mov     rdi, rcx
0x1800ec2fc  mov     eax, [rcx]
0x1800ec2fe  test    eax, eax
0x1800ec300  jz      loc_1800EC3C4
0x1800ec306  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800ec30b  test    al, al
0x1800ec30d  jnz     loc_1800EC3C4
0x1800ec313  lea     rbx, [rdi+8]
0x1800ec317  mov     rcx, rbx; SRWLock
0x1800ec31a  call    cs:__imp_AcquireSRWLockExclusive
0x1800ec321  nop     dword ptr [rax+rax+00h]
0x1800ec326  mov     [rsp+48h+arg_18], rbx
0x1800ec32b  mov     eax, [rdi]
0x1800ec32d  test    eax, eax
0x1800ec32f  jz      loc_1800EC3B9
0x1800ec335  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800ec33a  test    al, al
0x1800ec33c  jnz     short loc_1800EC3B9
0x1800ec33e  mov     [rsp+48h+var_28], ebp
0x1800ec342  xor     eax, eax
0x1800ec344  mov     [rsp+48h+var_24], eax
0x1800ec348  mov     [rsp+48h+var_20], rsi
0x1800ec34d  lea     rcx, [rdi+30h]; this
0x1800ec351  lea     r8d, [rax+10h]; unsigned __int64
0x1800ec355  lea     rdx, [rsp+48h+var_28]; void *
0x1800ec35a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800ec35f  cmp     byte ptr [rdi+18h], 0
0x1800ec363  jnz     short loc_1800EC3B9
0x1800ec365  lea     rbx, [rdi+10h]
0x1800ec369  cmp     qword ptr [rbx], 0
0x1800ec36d  jnz     short loc_1800EC3A7
0x1800ec36f  lea     rcx, [rsp+48h+arg_0]; this
0x1800ec374  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800ec379  xor     r8d, r8d; pcbe
0x1800ec37c  mov     rdx, rdi; pv
0x1800ec37f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800ec386  call    cs:__imp_CreateThreadpoolTimer
0x1800ec38d  nop     dword ptr [rax+rax+00h]
0x1800ec392  mov     rdx, rax
0x1800ec395  mov     rcx, rbx
0x1800ec398  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800ec39d  lea     rcx, [rsp+48h+arg_0]; this
0x1800ec3a2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ec3a7  mov     r8d, 493E0h
0x1800ec3ad  lea     rdx, [rdi+18h]
0x1800ec3b1  mov     rcx, rbx
0x1800ec3b4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800ec3b9  lea     rcx, [rsp+48h+arg_18]
0x1800ec3be  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ec3c3  nop
0x1800ec3c4  mov     rbx, [rsp+48h+arg_8]
0x1800ec3c9  add     rsp, 30h
0x1800ec3cd  pop     rdi
0x1800ec3ce  pop     rsi
0x1800ec3cf  pop     rbp
0x1800ec3d0  retn
```
