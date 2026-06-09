# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800326ac`
- end: `0x180032796`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180034940`

## callees

- `0x1800232b8`
- `0x18002387c`
- `0x180023950`
- `0x1800326ac`
- `0x180032894`
- `0x1800328b8`
- `0x180032900`
- `0x180032a78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800326de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800326de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003274a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003274a`

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
0x1800326ac  mov     [rsp+arg_8], rbx
0x1800326b1  push    rbp
0x1800326b2  push    rsi
0x1800326b3  push    rdi
0x1800326b4  sub     rsp, 30h
0x1800326b8  mov     rsi, r8
0x1800326bb  mov     ebp, edx
0x1800326bd  mov     rdi, rcx
0x1800326c0  mov     eax, [rcx]
0x1800326c2  test    eax, eax
0x1800326c4  jz      loc_180032788
0x1800326ca  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800326cf  test    al, al
0x1800326d1  jnz     loc_180032788
0x1800326d7  lea     rbx, [rdi+8]
0x1800326db  mov     rcx, rbx; SRWLock
0x1800326de  call    cs:__imp_AcquireSRWLockExclusive
0x1800326e5  nop     dword ptr [rax+rax+00h]
0x1800326ea  mov     [rsp+48h+arg_18], rbx
0x1800326ef  mov     eax, [rdi]
0x1800326f1  test    eax, eax
0x1800326f3  jz      loc_18003277D
0x1800326f9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800326fe  test    al, al
0x180032700  jnz     short loc_18003277D
0x180032702  mov     [rsp+48h+var_28], ebp
0x180032706  xor     eax, eax
0x180032708  mov     [rsp+48h+var_24], eax
0x18003270c  mov     [rsp+48h+var_20], rsi
0x180032711  lea     rcx, [rdi+30h]; this
0x180032715  lea     r8d, [rax+10h]; unsigned __int64
0x180032719  lea     rdx, [rsp+48h+var_28]; void *
0x18003271e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180032723  cmp     byte ptr [rdi+18h], 0
0x180032727  jnz     short loc_18003277D
0x180032729  lea     rbx, [rdi+10h]
0x18003272d  cmp     qword ptr [rbx], 0
0x180032731  jnz     short loc_18003276B
0x180032733  lea     rcx, [rsp+48h+arg_0]; this
0x180032738  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003273d  xor     r8d, r8d; pcbe
0x180032740  mov     rdx, rdi; pv
0x180032743  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003274a  call    cs:__imp_CreateThreadpoolTimer
0x180032751  nop     dword ptr [rax+rax+00h]
0x180032756  mov     rdx, rax
0x180032759  mov     rcx, rbx
0x18003275c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180032761  lea     rcx, [rsp+48h+arg_0]; this
0x180032766  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003276b  mov     r8d, 493E0h
0x180032771  lea     rdx, [rdi+18h]
0x180032775  mov     rcx, rbx
0x180032778  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003277d  lea     rcx, [rsp+48h+arg_18]
0x180032782  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180032787  nop
0x180032788  mov     rbx, [rsp+48h+arg_8]
0x18003278d  add     rsp, 30h
0x180032791  pop     rdi
0x180032792  pop     rsi
0x180032793  pop     rbp
0x180032794  retn
```
