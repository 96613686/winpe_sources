# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003cd84`
- end: `0x18003ce5d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001f9f0`

## callees

- `0x18002d964`
- `0x18002d984`
- `0x18002d9c8`
- `0x18002d9e8`
- `0x18002da0c`
- `0x18002db34`
- `0x18003b91c`
- `0x18003cd84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cdb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cdb6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003ce18`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003ce18`

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
0x18003cd84  mov     [rsp+arg_8], rbx
0x18003cd89  push    rbp
0x18003cd8a  push    rsi
0x18003cd8b  push    rdi
0x18003cd8c  sub     rsp, 30h
0x18003cd90  mov     rsi, r8
0x18003cd93  mov     ebp, edx
0x18003cd95  mov     rdi, rcx
0x18003cd98  mov     eax, [rcx]
0x18003cd9a  test    eax, eax
0x18003cd9c  jz      loc_18003CE50
0x18003cda2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003cda7  test    al, al
0x18003cda9  jnz     loc_18003CE50
0x18003cdaf  lea     rbx, [rdi+8]
0x18003cdb3  mov     rcx, rbx; SRWLock
0x18003cdb6  call    cs:__imp_AcquireSRWLockExclusive
0x18003cdbc  mov     [rsp+48h+arg_18], rbx
0x18003cdc1  mov     eax, [rdi]
0x18003cdc3  test    eax, eax
0x18003cdc5  jz      short loc_18003CE45
0x18003cdc7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003cdcc  test    al, al
0x18003cdce  jnz     short loc_18003CE45
0x18003cdd0  mov     [rsp+48h+var_28], ebp
0x18003cdd4  xor     eax, eax
0x18003cdd6  mov     [rsp+48h+var_24], eax
0x18003cdda  mov     [rsp+48h+var_20], rsi
0x18003cddf  lea     rcx, [rdi+20h]; this
0x18003cde3  lea     r8d, [rax+10h]; unsigned __int64
0x18003cde7  lea     rdx, [rsp+48h+var_28]; void *
0x18003cdec  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003cdf1  cmp     byte ptr [rdi+18h], 0
0x18003cdf5  jnz     short loc_18003CE45
0x18003cdf7  lea     rbx, [rdi+10h]
0x18003cdfb  cmp     qword ptr [rbx], 0
0x18003cdff  jnz     short loc_18003CE33
0x18003ce01  lea     rcx, [rsp+48h+arg_0]; this
0x18003ce06  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003ce0b  xor     r8d, r8d; pcbe
0x18003ce0e  mov     rdx, rdi; pv
0x18003ce11  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003ce18  call    cs:__imp_CreateThreadpoolTimer
0x18003ce1e  mov     rdx, rax
0x18003ce21  mov     rcx, rbx
0x18003ce24  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003ce29  lea     rcx, [rsp+48h+arg_0]; this
0x18003ce2e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003ce33  mov     r8d, 493E0h
0x18003ce39  lea     rdx, [rdi+18h]
0x18003ce3d  mov     rcx, rbx
0x18003ce40  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003ce45  lea     rcx, [rsp+48h+arg_18]
0x18003ce4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003ce4f  nop
0x18003ce50  mov     rbx, [rsp+48h+arg_8]
0x18003ce55  add     rsp, 30h
0x18003ce59  pop     rdi
0x18003ce5a  pop     rsi
0x18003ce5b  pop     rbp
0x18003ce5c  retn
```
