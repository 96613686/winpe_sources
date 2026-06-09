# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180190bd4`
- end: `0x180190cbd`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `233`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180190e7c`

## callees

- `0x18012c76c`
- `0x1801417b4`
- `0x180141980`
- `0x180141c88`
- `0x180142378`
- `0x180145eb4`
- `0x180145fd4`
- `0x180190bd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180190c06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180190c06`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180190c72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180190c72`

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
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v9, 0x10u);
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
0x180190bd4  mov     [rsp+arg_8], rbx
0x180190bd9  push    rbp
0x180190bda  push    rsi
0x180190bdb  push    rdi
0x180190bdc  sub     rsp, 30h
0x180190be0  mov     eax, [rcx]
0x180190be2  mov     rsi, r8
0x180190be5  mov     ebp, edx
0x180190be7  mov     rdi, rcx
0x180190bea  test    eax, eax
0x180190bec  jz      loc_180190CAF
0x180190bf2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180190bf7  test    al, al
0x180190bf9  jnz     loc_180190CAF
0x180190bff  lea     rbx, [rdi+8]
0x180190c03  mov     rcx, rbx; SRWLock
0x180190c06  call    cs:__imp_AcquireSRWLockExclusive
0x180190c0d  nop     dword ptr [rax+rax+00h]
0x180190c12  mov     eax, [rdi]
0x180190c14  mov     [rsp+48h+arg_18], rbx
0x180190c19  test    eax, eax
0x180190c1b  jz      loc_180190CA5
0x180190c21  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180190c26  test    al, al
0x180190c28  jnz     short loc_180190CA5
0x180190c2a  xor     eax, eax
0x180190c2c  mov     [rsp+48h+var_28], ebp
0x180190c30  lea     rcx, [rdi+30h]; this
0x180190c34  mov     [rsp+48h+var_24], eax
0x180190c38  lea     rdx, [rsp+48h+var_28]; void *
0x180190c3d  mov     [rsp+48h+var_20], rsi
0x180190c42  lea     r8d, [rax+10h]; unsigned __int64
0x180190c46  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180190c4b  cmp     byte ptr [rdi+18h], 0
0x180190c4f  jnz     short loc_180190CA5
0x180190c51  lea     rbx, [rdi+10h]
0x180190c55  cmp     qword ptr [rbx], 0
0x180190c59  jnz     short loc_180190C93
0x180190c5b  lea     rcx, [rsp+48h+arg_0]; this
0x180190c60  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180190c65  xor     r8d, r8d; pcbe
0x180190c68  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180190c6f  mov     rdx, rdi; pv
0x180190c72  call    cs:__imp_CreateThreadpoolTimer
0x180190c79  nop     dword ptr [rax+rax+00h]
0x180190c7e  mov     rdx, rax
0x180190c81  mov     rcx, rbx
0x180190c84  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180190c89  lea     rcx, [rsp+48h+arg_0]; this
0x180190c8e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180190c93  mov     r8d, 493E0h
0x180190c99  lea     rdx, [rdi+18h]
0x180190c9d  mov     rcx, rbx
0x180190ca0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180190ca5  lea     rcx, [rsp+48h+arg_18]
0x180190caa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180190caf  mov     rbx, [rsp+48h+arg_8]
0x180190cb4  add     rsp, 30h
0x180190cb8  pop     rdi
0x180190cb9  pop     rsi
0x180190cba  pop     rbp
0x180190cbb  retn
```
