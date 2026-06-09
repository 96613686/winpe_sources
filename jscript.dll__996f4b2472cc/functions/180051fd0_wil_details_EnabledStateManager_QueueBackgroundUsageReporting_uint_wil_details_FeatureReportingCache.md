# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180051fd0`
- end: `0x1800520b9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `233`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007445c`

## callees

- `0x180046364`
- `0x18004a398`
- `0x18004b2a0`
- `0x18004b57c`
- `0x180051fd0`
- `0x180054540`
- `0x180059b54`
- `0x180059ce0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180052002`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180052002`
- `KERNEL32!CreateThreadpoolTimer` at `0x18005206e`
- `KERNEL32!CreateThreadpoolTimer` at `0x18005206e`

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
0x180051fd0  mov     [rsp+arg_8], rbx
0x180051fd5  push    rbp
0x180051fd6  push    rsi
0x180051fd7  push    rdi
0x180051fd8  sub     rsp, 30h
0x180051fdc  mov     eax, [rcx]
0x180051fde  mov     rsi, r8
0x180051fe1  mov     ebp, edx
0x180051fe3  mov     rdi, rcx
0x180051fe6  test    eax, eax
0x180051fe8  jz      loc_1800520AB
0x180051fee  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180051ff3  test    al, al
0x180051ff5  jnz     loc_1800520AB
0x180051ffb  lea     rbx, [rdi+8]
0x180051fff  mov     rcx, rbx; SRWLock
0x180052002  call    cs:__imp_AcquireSRWLockExclusive
0x180052009  nop     dword ptr [rax+rax+00h]
0x18005200e  mov     eax, [rdi]
0x180052010  mov     [rsp+48h+arg_18], rbx
0x180052015  test    eax, eax
0x180052017  jz      loc_1800520A1
0x18005201d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180052022  test    al, al
0x180052024  jnz     short loc_1800520A1
0x180052026  xor     eax, eax
0x180052028  mov     [rsp+48h+var_28], ebp
0x18005202c  lea     rcx, [rdi+30h]; this
0x180052030  mov     [rsp+48h+var_24], eax
0x180052034  lea     rdx, [rsp+48h+var_28]; void *
0x180052039  mov     [rsp+48h+var_20], rsi
0x18005203e  lea     r8d, [rax+10h]; unsigned __int64
0x180052042  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180052047  cmp     byte ptr [rdi+18h], 0
0x18005204b  jnz     short loc_1800520A1
0x18005204d  lea     rbx, [rdi+10h]
0x180052051  cmp     qword ptr [rbx], 0
0x180052055  jnz     short loc_18005208F
0x180052057  lea     rcx, [rsp+48h+arg_0]; this
0x18005205c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180052061  xor     r8d, r8d; pcbe
0x180052064  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005206b  mov     rdx, rdi; pv
0x18005206e  call    cs:__imp_CreateThreadpoolTimer
0x180052075  nop     dword ptr [rax+rax+00h]
0x18005207a  mov     rdx, rax
0x18005207d  mov     rcx, rbx
0x180052080  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180052085  lea     rcx, [rsp+48h+arg_0]; this
0x18005208a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005208f  mov     r8d, 493E0h
0x180052095  lea     rdx, [rdi+18h]
0x180052099  mov     rcx, rbx
0x18005209c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800520a1  lea     rcx, [rsp+48h+arg_18]
0x1800520a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800520ab  mov     rbx, [rsp+48h+arg_8]
0x1800520b0  add     rsp, 30h
0x1800520b4  pop     rdi
0x1800520b5  pop     rsi
0x1800520b6  pop     rbp
0x1800520b7  retn
```
