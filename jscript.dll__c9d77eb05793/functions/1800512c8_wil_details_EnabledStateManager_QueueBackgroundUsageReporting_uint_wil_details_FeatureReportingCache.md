# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800512c8`
- end: `0x1800513a0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180072fdc`

## callees

- `0x180045674`
- `0x1800496c0`
- `0x18004a510`
- `0x18004ac54`
- `0x1800512c8`
- `0x180053730`
- `0x180058bd8`
- `0x180058dc4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800512fa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800512fa`
- `KERNEL32!CreateThreadpoolTimer` at `0x18005135c`
- `KERNEL32!CreateThreadpoolTimer` at `0x18005135c`

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
0x1800512c8  mov     [rsp+arg_8], rbx
0x1800512cd  push    rbp
0x1800512ce  push    rsi
0x1800512cf  push    rdi
0x1800512d0  sub     rsp, 30h
0x1800512d4  mov     eax, [rcx]
0x1800512d6  mov     rsi, r8
0x1800512d9  mov     ebp, edx
0x1800512db  mov     rdi, rcx
0x1800512de  test    eax, eax
0x1800512e0  jz      loc_180051393
0x1800512e6  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800512eb  test    al, al
0x1800512ed  jnz     loc_180051393
0x1800512f3  lea     rbx, [rdi+8]
0x1800512f7  mov     rcx, rbx; SRWLock
0x1800512fa  call    cs:__imp_AcquireSRWLockExclusive
0x180051300  mov     eax, [rdi]
0x180051302  mov     [rsp+48h+arg_18], rbx
0x180051307  test    eax, eax
0x180051309  jz      short loc_180051389
0x18005130b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180051310  test    al, al
0x180051312  jnz     short loc_180051389
0x180051314  xor     eax, eax
0x180051316  mov     [rsp+48h+var_28], ebp
0x18005131a  lea     rcx, [rdi+20h]; this
0x18005131e  mov     [rsp+48h+var_24], eax
0x180051322  lea     rdx, [rsp+48h+var_28]; void *
0x180051327  mov     [rsp+48h+var_20], rsi
0x18005132c  lea     r8d, [rax+10h]; unsigned __int64
0x180051330  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180051335  cmp     byte ptr [rdi+18h], 0
0x180051339  jnz     short loc_180051389
0x18005133b  lea     rbx, [rdi+10h]
0x18005133f  cmp     qword ptr [rbx], 0
0x180051343  jnz     short loc_180051377
0x180051345  lea     rcx, [rsp+48h+arg_0]; this
0x18005134a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005134f  xor     r8d, r8d; pcbe
0x180051352  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180051359  mov     rdx, rdi; pv
0x18005135c  call    cs:__imp_CreateThreadpoolTimer
0x180051362  mov     rdx, rax
0x180051365  mov     rcx, rbx
0x180051368  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005136d  lea     rcx, [rsp+48h+arg_0]; this
0x180051372  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180051377  mov     r8d, 493E0h
0x18005137d  lea     rdx, [rdi+18h]
0x180051381  mov     rcx, rbx
0x180051384  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180051389  lea     rcx, [rsp+48h+arg_18]
0x18005138e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180051393  mov     rbx, [rsp+48h+arg_8]
0x180051398  add     rsp, 30h
0x18005139c  pop     rdi
0x18005139d  pop     rsi
0x18005139e  pop     rbp
0x18005139f  retn
```
