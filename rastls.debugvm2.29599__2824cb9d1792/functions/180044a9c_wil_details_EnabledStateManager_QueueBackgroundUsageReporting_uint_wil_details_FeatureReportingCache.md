# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180044a9c`
- end: `0x180044b75`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800180a0`
- `0x18001e5e0`

## callees

- `0x18001efe0`
- `0x18001f0d4`
- `0x18002a490`
- `0x18002a4b0`
- `0x18002a4f4`
- `0x18002a514`
- `0x18003bc14`
- `0x180044a9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044ace`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044ace`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180044b30`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180044b30`

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
0x180044a9c  mov     [rsp+arg_8], rbx
0x180044aa1  push    rbp
0x180044aa2  push    rsi
0x180044aa3  push    rdi
0x180044aa4  sub     rsp, 30h
0x180044aa8  mov     rsi, r8
0x180044aab  mov     ebp, edx
0x180044aad  mov     rdi, rcx
0x180044ab0  mov     eax, [rcx]
0x180044ab2  test    eax, eax
0x180044ab4  jz      loc_180044B68
0x180044aba  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180044abf  test    al, al
0x180044ac1  jnz     loc_180044B68
0x180044ac7  lea     rbx, [rdi+8]
0x180044acb  mov     rcx, rbx; SRWLock
0x180044ace  call    cs:__imp_AcquireSRWLockExclusive
0x180044ad4  mov     [rsp+48h+arg_18], rbx
0x180044ad9  mov     eax, [rdi]
0x180044adb  test    eax, eax
0x180044add  jz      short loc_180044B5D
0x180044adf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180044ae4  test    al, al
0x180044ae6  jnz     short loc_180044B5D
0x180044ae8  mov     [rsp+48h+var_28], ebp
0x180044aec  xor     eax, eax
0x180044aee  mov     [rsp+48h+var_24], eax
0x180044af2  mov     [rsp+48h+var_20], rsi
0x180044af7  lea     rcx, [rdi+20h]; this
0x180044afb  lea     r8d, [rax+10h]; unsigned __int64
0x180044aff  lea     rdx, [rsp+48h+var_28]; void *
0x180044b04  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180044b09  cmp     byte ptr [rdi+18h], 0
0x180044b0d  jnz     short loc_180044B5D
0x180044b0f  lea     rbx, [rdi+10h]
0x180044b13  cmp     qword ptr [rbx], 0
0x180044b17  jnz     short loc_180044B4B
0x180044b19  lea     rcx, [rsp+48h+arg_0]; this
0x180044b1e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180044b23  xor     r8d, r8d; pcbe
0x180044b26  mov     rdx, rdi; pv
0x180044b29  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180044b30  call    cs:__imp_CreateThreadpoolTimer
0x180044b36  mov     rdx, rax
0x180044b39  mov     rcx, rbx
0x180044b3c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180044b41  lea     rcx, [rsp+48h+arg_0]; this
0x180044b46  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180044b4b  mov     r8d, 493E0h
0x180044b51  lea     rdx, [rdi+18h]
0x180044b55  mov     rcx, rbx
0x180044b58  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180044b5d  lea     rcx, [rsp+48h+arg_18]
0x180044b62  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180044b67  nop
0x180044b68  mov     rbx, [rsp+48h+arg_8]
0x180044b6d  add     rsp, 30h
0x180044b71  pop     rdi
0x180044b72  pop     rsi
0x180044b73  pop     rbp
0x180044b74  retn
```
