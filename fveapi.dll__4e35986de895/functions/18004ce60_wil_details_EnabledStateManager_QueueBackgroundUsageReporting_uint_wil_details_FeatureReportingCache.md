# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18004ce60`
- end: `0x18004cf49`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `233`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800174a4`

## callees

- `0x18003b448`
- `0x180042824`
- `0x180044cc4`
- `0x1800457c0`
- `0x1800464d0`
- `0x180048d88`
- `0x18004ce60`
- `0x18004d054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ce92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ce92`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004cefe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004cefe`

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
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp-28h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v11 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Source, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)Source);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)Source);
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
0x18004ce60  mov     [rsp+arg_18], rbx
0x18004ce65  push    rbp
0x18004ce66  push    rsi
0x18004ce67  push    rdi
0x18004ce68  sub     rsp, 40h
0x18004ce6c  mov     eax, [rcx]
0x18004ce6e  mov     rbp, r8
0x18004ce71  mov     esi, edx
0x18004ce73  mov     rdi, rcx
0x18004ce76  test    eax, eax
0x18004ce78  jz      loc_18004CF3B
0x18004ce7e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004ce83  test    al, al
0x18004ce85  jnz     loc_18004CF3B
0x18004ce8b  lea     rbx, [rdi+8]
0x18004ce8f  mov     rcx, rbx; SRWLock
0x18004ce92  call    cs:__imp_AcquireSRWLockExclusive
0x18004ce99  nop     dword ptr [rax+rax+00h]
0x18004ce9e  mov     eax, [rdi]
0x18004cea0  mov     [rsp+58h+var_28], rbx
0x18004cea5  test    eax, eax
0x18004cea7  jz      loc_18004CF31
0x18004cead  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004ceb2  test    al, al
0x18004ceb4  jnz     short loc_18004CF31
0x18004ceb6  xor     eax, eax
0x18004ceb8  mov     [rsp+58h+Source], esi
0x18004cebc  lea     rcx, [rdi+20h]; this
0x18004cec0  mov     [rsp+58h+var_34], eax
0x18004cec4  lea     rdx, [rsp+58h+Source]; Source
0x18004cec9  mov     [rsp+58h+var_30], rbp
0x18004cece  lea     r8d, [rax+10h]; SourceSize
0x18004ced2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18004ced7  cmp     byte ptr [rdi+18h], 0
0x18004cedb  jnz     short loc_18004CF31
0x18004cedd  lea     rbx, [rdi+10h]
0x18004cee1  cmp     qword ptr [rbx], 0
0x18004cee5  jnz     short loc_18004CF1F
0x18004cee7  lea     rcx, [rsp+58h+Source]; this
0x18004ceec  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004cef1  xor     r8d, r8d; pcbe
0x18004cef4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004cefb  mov     rdx, rdi; pv
0x18004cefe  call    cs:__imp_CreateThreadpoolTimer
0x18004cf05  nop     dword ptr [rax+rax+00h]
0x18004cf0a  mov     rdx, rax
0x18004cf0d  mov     rcx, rbx
0x18004cf10  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004cf15  lea     rcx, [rsp+58h+Source]; this
0x18004cf1a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004cf1f  mov     r8d, 493E0h
0x18004cf25  lea     rdx, [rdi+18h]
0x18004cf29  mov     rcx, rbx
0x18004cf2c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004cf31  lea     rcx, [rsp+58h+var_28]
0x18004cf36  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004cf3b  mov     rbx, [rsp+58h+arg_18]
0x18004cf40  add     rsp, 40h
0x18004cf44  pop     rdi
0x18004cf45  pop     rsi
0x18004cf46  pop     rbp
0x18004cf47  retn
```
