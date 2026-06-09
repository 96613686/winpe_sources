# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001beb8`
- end: `0x18001bf96`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `222`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001c9d0`

## callees

- `0x180004328`
- `0x1800045d0`
- `0x180005b74`
- `0x18000ac00`
- `0x1800196a8`
- `0x18001beb8`
- `0x18001d570`
- `0x18001d67c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001beeb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001beeb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bf4e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bf4e`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+58h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v9 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v7[0] = 20516266;
        v7[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v7, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x18001beb8  mov     [rsp+arg_8], rbx
0x18001bebd  mov     [rsp+arg_10], rsi
0x18001bec2  push    rdi
0x18001bec3  sub     rsp, 30h
0x18001bec7  mov     rsi, r8
0x18001beca  mov     rdi, rcx
0x18001becd  mov     eax, [rcx]
0x18001becf  test    eax, eax
0x18001bed1  jz      loc_18001BF86
0x18001bed7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001bedc  test    al, al
0x18001bede  jnz     loc_18001BF86
0x18001bee4  lea     rbx, [rdi+8]
0x18001bee8  mov     rcx, rbx; SRWLock
0x18001beeb  call    cs:__imp_AcquireSRWLockExclusive
0x18001bef1  mov     [rsp+38h+arg_18], rbx
0x18001bef6  mov     eax, [rdi]
0x18001bef8  test    eax, eax
0x18001befa  jz      short loc_18001BF7B
0x18001befc  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001bf01  test    al, al
0x18001bf03  jnz     short loc_18001BF7B
0x18001bf05  mov     [rsp+38h+var_18], 1390DAAh
0x18001bf0e  mov     [rsp+38h+var_10], rsi
0x18001bf13  lea     rcx, [rdi+20h]; this
0x18001bf17  mov     r8d, 10h; unsigned __int64
0x18001bf1d  lea     rdx, [rsp+38h+var_18]; void *
0x18001bf22  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001bf27  cmp     byte ptr [rdi+18h], 0
0x18001bf2b  jnz     short loc_18001BF7B
0x18001bf2d  lea     rbx, [rdi+10h]
0x18001bf31  cmp     qword ptr [rbx], 0
0x18001bf35  jnz     short loc_18001BF69
0x18001bf37  lea     rcx, [rsp+38h+arg_0]; this
0x18001bf3c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001bf41  xor     r8d, r8d; pcbe
0x18001bf44  mov     rdx, rdi; pv
0x18001bf47  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001bf4e  call    cs:__imp_CreateThreadpoolTimer
0x18001bf54  mov     rdx, rax
0x18001bf57  mov     rcx, rbx
0x18001bf5a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001bf5f  lea     rcx, [rsp+38h+arg_0]; this
0x18001bf64  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001bf69  mov     r8d, 493E0h
0x18001bf6f  lea     rdx, [rdi+18h]
0x18001bf73  mov     rcx, rbx
0x18001bf76  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001bf7b  lea     rcx, [rsp+38h+arg_18]
0x18001bf80  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001bf85  nop
0x18001bf86  mov     rbx, [rsp+38h+arg_8]
0x18001bf8b  mov     rsi, [rsp+38h+arg_10]
0x18001bf90  add     rsp, 30h
0x18001bf94  pop     rdi
0x18001bf95  retn
```
