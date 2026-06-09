# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180028e60`
- end: `0x180028f4a`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180029c64`

## callees

- `0x180004cc8`
- `0x1800050ec`
- `0x180008b2c`
- `0x18000ac08`
- `0x18000b808`
- `0x18000dba4`
- `0x18000dcb0`
- `0x180028e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028e92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028e92`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180028efe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180028efe`

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
0x180028e60  mov     [rsp+arg_8], rbx
0x180028e65  push    rbp
0x180028e66  push    rsi
0x180028e67  push    rdi
0x180028e68  sub     rsp, 30h
0x180028e6c  mov     rsi, r8
0x180028e6f  mov     ebp, edx
0x180028e71  mov     rdi, rcx
0x180028e74  mov     eax, [rcx]
0x180028e76  test    eax, eax
0x180028e78  jz      loc_180028F3C
0x180028e7e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180028e83  test    al, al
0x180028e85  jnz     loc_180028F3C
0x180028e8b  lea     rbx, [rdi+8]
0x180028e8f  mov     rcx, rbx; SRWLock
0x180028e92  call    cs:__imp_AcquireSRWLockExclusive
0x180028e99  nop     dword ptr [rax+rax+00h]
0x180028e9e  mov     [rsp+48h+arg_18], rbx
0x180028ea3  mov     eax, [rdi]
0x180028ea5  test    eax, eax
0x180028ea7  jz      loc_180028F31
0x180028ead  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180028eb2  test    al, al
0x180028eb4  jnz     short loc_180028F31
0x180028eb6  mov     [rsp+48h+var_28], ebp
0x180028eba  xor     eax, eax
0x180028ebc  mov     [rsp+48h+var_24], eax
0x180028ec0  mov     [rsp+48h+var_20], rsi
0x180028ec5  lea     rcx, [rdi+30h]; this
0x180028ec9  lea     r8d, [rax+10h]; unsigned __int64
0x180028ecd  lea     rdx, [rsp+48h+var_28]; void *
0x180028ed2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180028ed7  cmp     byte ptr [rdi+18h], 0
0x180028edb  jnz     short loc_180028F31
0x180028edd  lea     rbx, [rdi+10h]
0x180028ee1  cmp     qword ptr [rbx], 0
0x180028ee5  jnz     short loc_180028F1F
0x180028ee7  lea     rcx, [rsp+48h+arg_0]; this
0x180028eec  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180028ef1  xor     r8d, r8d; pcbe
0x180028ef4  mov     rdx, rdi; pv
0x180028ef7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180028efe  call    cs:__imp_CreateThreadpoolTimer
0x180028f05  nop     dword ptr [rax+rax+00h]
0x180028f0a  mov     rdx, rax
0x180028f0d  mov     rcx, rbx
0x180028f10  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180028f15  lea     rcx, [rsp+48h+arg_0]; this
0x180028f1a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180028f1f  mov     r8d, 493E0h
0x180028f25  lea     rdx, [rdi+18h]
0x180028f29  mov     rcx, rbx
0x180028f2c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180028f31  lea     rcx, [rsp+48h+arg_18]
0x180028f36  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028f3b  nop
0x180028f3c  mov     rbx, [rsp+48h+arg_8]
0x180028f41  add     rsp, 30h
0x180028f45  pop     rdi
0x180028f46  pop     rsi
0x180028f47  pop     rbp
0x180028f48  retn
```
