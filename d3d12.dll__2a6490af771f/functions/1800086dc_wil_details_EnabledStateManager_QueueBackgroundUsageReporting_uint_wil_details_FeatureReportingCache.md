# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800086dc`
- end: `0x1800087ba`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `222`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008374`

## callees

- `0x180002f4c`
- `0x1800045a8`
- `0x180004758`
- `0x18000490c`
- `0x18000492c`
- `0x1800086dc`
- `0x18000a1e4`
- `0x18000a204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000870f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000870f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008772`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008772`

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
        v7[0] = 39847774;
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
0x1800086dc  mov     [rsp+arg_8], rbx
0x1800086e1  mov     [rsp+arg_10], rsi
0x1800086e6  push    rdi
0x1800086e7  sub     rsp, 30h
0x1800086eb  mov     rsi, r8
0x1800086ee  mov     rdi, rcx
0x1800086f1  mov     eax, [rcx]
0x1800086f3  test    eax, eax
0x1800086f5  jz      loc_1800087AA
0x1800086fb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180008700  test    al, al
0x180008702  jnz     loc_1800087AA
0x180008708  lea     rbx, [rdi+8]
0x18000870c  mov     rcx, rbx; SRWLock
0x18000870f  call    cs:__imp_AcquireSRWLockExclusive
0x180008715  mov     [rsp+38h+arg_18], rbx
0x18000871a  mov     eax, [rdi]
0x18000871c  test    eax, eax
0x18000871e  jz      short loc_18000879F
0x180008720  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180008725  test    al, al
0x180008727  jnz     short loc_18000879F
0x180008729  mov     [rsp+38h+var_18], 260075Eh
0x180008732  mov     [rsp+38h+var_10], rsi
0x180008737  lea     rcx, [rdi+20h]; this
0x18000873b  mov     r8d, 10h; unsigned __int64
0x180008741  lea     rdx, [rsp+38h+var_18]; void *
0x180008746  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000874b  cmp     byte ptr [rdi+18h], 0
0x18000874f  jnz     short loc_18000879F
0x180008751  lea     rbx, [rdi+10h]
0x180008755  cmp     qword ptr [rbx], 0
0x180008759  jnz     short loc_18000878D
0x18000875b  lea     rcx, [rsp+38h+arg_0]; this
0x180008760  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008765  xor     r8d, r8d; pcbe
0x180008768  mov     rdx, rdi; pv
0x18000876b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008772  call    cs:__imp_CreateThreadpoolTimer
0x180008778  mov     rdx, rax
0x18000877b  mov     rcx, rbx
0x18000877e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008783  lea     rcx, [rsp+38h+arg_0]; this
0x180008788  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000878d  mov     r8d, 493E0h
0x180008793  lea     rdx, [rdi+18h]
0x180008797  mov     rcx, rbx
0x18000879a  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000879f  lea     rcx, [rsp+38h+arg_18]
0x1800087a4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800087a9  nop
0x1800087aa  mov     rbx, [rsp+38h+arg_8]
0x1800087af  mov     rsi, [rsp+38h+arg_10]
0x1800087b4  add     rsp, 30h
0x1800087b8  pop     rdi
0x1800087b9  retn
```
