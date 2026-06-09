# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000cd18`
- end: `0x18000cdf0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000beac`

## callees

- `0x18000ab44`
- `0x18000af7c`
- `0x18000bcdc`
- `0x18000c824`
- `0x18000cd18`
- `0x18000cfb4`
- `0x180011e6c`
- `0x1800120b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cdac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cdac`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int v7; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v7 = *(_DWORD *)pv;
    v12 = (RTL_SRWLOCK *)(pv + 8);
    if ( v7 )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((void **)pv + 4, v9, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18000cd18  mov     [rsp+arg_8], rbx
0x18000cd1d  push    rbp
0x18000cd1e  push    rsi
0x18000cd1f  push    rdi
0x18000cd20  sub     rsp, 30h
0x18000cd24  mov     eax, [rcx]
0x18000cd26  mov     rsi, r8
0x18000cd29  mov     ebp, edx
0x18000cd2b  mov     rdi, rcx
0x18000cd2e  test    eax, eax
0x18000cd30  jz      loc_18000CDE3
0x18000cd36  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000cd3b  test    al, al
0x18000cd3d  jnz     loc_18000CDE3
0x18000cd43  lea     rbx, [rdi+8]
0x18000cd47  mov     rcx, rbx; SRWLock
0x18000cd4a  call    cs:__imp_AcquireSRWLockExclusive
0x18000cd50  mov     eax, [rdi]
0x18000cd52  mov     [rsp+48h+arg_18], rbx
0x18000cd57  test    eax, eax
0x18000cd59  jz      short loc_18000CDD9
0x18000cd5b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000cd60  test    al, al
0x18000cd62  jnz     short loc_18000CDD9
0x18000cd64  xor     eax, eax
0x18000cd66  mov     [rsp+48h+var_28], ebp
0x18000cd6a  lea     rcx, [rdi+20h]; this
0x18000cd6e  mov     [rsp+48h+var_24], eax
0x18000cd72  lea     rdx, [rsp+48h+var_28]; void *
0x18000cd77  mov     [rsp+48h+var_20], rsi
0x18000cd7c  lea     r8d, [rax+10h]; unsigned __int64
0x18000cd80  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000cd85  cmp     byte ptr [rdi+18h], 0
0x18000cd89  jnz     short loc_18000CDD9
0x18000cd8b  lea     rbx, [rdi+10h]
0x18000cd8f  cmp     qword ptr [rbx], 0
0x18000cd93  jnz     short loc_18000CDC7
0x18000cd95  lea     rcx, [rsp+48h+arg_0]; this
0x18000cd9a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cd9f  xor     r8d, r8d; pcbe
0x18000cda2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000cda9  mov     rdx, rdi; pv
0x18000cdac  call    cs:__imp_CreateThreadpoolTimer
0x18000cdb2  mov     rdx, rax
0x18000cdb5  mov     rcx, rbx
0x18000cdb8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000cdbd  lea     rcx, [rsp+48h+arg_0]; this
0x18000cdc2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000cdc7  mov     r8d, 493E0h
0x18000cdcd  lea     rdx, [rdi+18h]
0x18000cdd1  mov     rcx, rbx
0x18000cdd4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000cdd9  lea     rcx, [rsp+48h+arg_18]
0x18000cdde  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000cde3  mov     rbx, [rsp+48h+arg_8]
0x18000cde8  add     rsp, 30h
0x18000cdec  pop     rdi
0x18000cded  pop     rsi
0x18000cdee  pop     rbp
0x18000cdef  retn
```
