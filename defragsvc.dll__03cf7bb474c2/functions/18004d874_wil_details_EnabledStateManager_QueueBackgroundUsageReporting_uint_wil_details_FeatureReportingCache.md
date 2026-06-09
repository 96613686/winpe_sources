# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18004d874`
- end: `0x18004d94c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004dcf0`

## callees

- `0x180035a70`
- `0x180035a90`
- `0x180035ad4`
- `0x180035af4`
- `0x180035b18`
- `0x180035c40`
- `0x18004d874`
- `0x18004e28c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d8a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d8a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004d908`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004d908`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v9, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
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
0x18004d874  mov     [rsp+arg_8], rbx
0x18004d879  push    rbp
0x18004d87a  push    rsi
0x18004d87b  push    rdi
0x18004d87c  sub     rsp, 30h
0x18004d880  mov     eax, [rcx]
0x18004d882  mov     rsi, r8
0x18004d885  mov     ebp, edx
0x18004d887  mov     rdi, rcx
0x18004d88a  test    eax, eax
0x18004d88c  jz      loc_18004D93F
0x18004d892  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004d897  test    al, al
0x18004d899  jnz     loc_18004D93F
0x18004d89f  lea     rbx, [rdi+8]
0x18004d8a3  mov     rcx, rbx; SRWLock
0x18004d8a6  call    cs:__imp_AcquireSRWLockExclusive
0x18004d8ac  mov     eax, [rdi]
0x18004d8ae  mov     [rsp+48h+arg_18], rbx
0x18004d8b3  test    eax, eax
0x18004d8b5  jz      short loc_18004D935
0x18004d8b7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004d8bc  test    al, al
0x18004d8be  jnz     short loc_18004D935
0x18004d8c0  xor     eax, eax
0x18004d8c2  mov     [rsp+48h+var_28], ebp
0x18004d8c6  lea     rcx, [rdi+20h]; this
0x18004d8ca  mov     [rsp+48h+var_24], eax
0x18004d8ce  lea     rdx, [rsp+48h+var_28]; void *
0x18004d8d3  mov     [rsp+48h+var_20], rsi
0x18004d8d8  lea     r8d, [rax+10h]; unsigned __int64
0x18004d8dc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18004d8e1  cmp     byte ptr [rdi+18h], 0
0x18004d8e5  jnz     short loc_18004D935
0x18004d8e7  lea     rbx, [rdi+10h]
0x18004d8eb  cmp     qword ptr [rbx], 0
0x18004d8ef  jnz     short loc_18004D923
0x18004d8f1  lea     rcx, [rsp+48h+arg_0]; this
0x18004d8f6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004d8fb  xor     r8d, r8d; pcbe
0x18004d8fe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004d905  mov     rdx, rdi; pv
0x18004d908  call    cs:__imp_CreateThreadpoolTimer
0x18004d90e  mov     rdx, rax
0x18004d911  mov     rcx, rbx
0x18004d914  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004d919  lea     rcx, [rsp+48h+arg_0]; this
0x18004d91e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004d923  mov     r8d, 493E0h
0x18004d929  lea     rdx, [rdi+18h]
0x18004d92d  mov     rcx, rbx
0x18004d930  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004d935  lea     rcx, [rsp+48h+arg_18]
0x18004d93a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004d93f  mov     rbx, [rsp+48h+arg_8]
0x18004d944  add     rsp, 30h
0x18004d948  pop     rdi
0x18004d949  pop     rsi
0x18004d94a  pop     rbp
0x18004d94b  retn
```
