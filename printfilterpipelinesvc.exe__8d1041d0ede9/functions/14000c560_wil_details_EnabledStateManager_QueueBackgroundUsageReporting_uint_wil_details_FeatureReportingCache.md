# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000c560`
- end: `0x14000c639`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000d374`

## callees

- `0x140009174`
- `0x1400094d4`
- `0x140009828`
- `0x140009f64`
- `0x14000c440`
- `0x14000c560`
- `0x14000ec48`
- `0x14000ed50`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14000c5f4`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000c5f4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c592`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c592`

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
0x14000c560  mov     [rsp+arg_8], rbx
0x14000c565  push    rbp
0x14000c566  push    rsi
0x14000c567  push    rdi
0x14000c568  sub     rsp, 30h
0x14000c56c  mov     rsi, r8
0x14000c56f  mov     ebp, edx
0x14000c571  mov     rdi, rcx
0x14000c574  mov     eax, [rcx]
0x14000c576  test    eax, eax
0x14000c578  jz      loc_14000C62C
0x14000c57e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000c583  test    al, al
0x14000c585  jnz     loc_14000C62C
0x14000c58b  lea     rbx, [rdi+8]
0x14000c58f  mov     rcx, rbx; SRWLock
0x14000c592  call    cs:__imp_AcquireSRWLockExclusive
0x14000c598  mov     [rsp+48h+arg_18], rbx
0x14000c59d  mov     eax, [rdi]
0x14000c59f  test    eax, eax
0x14000c5a1  jz      short loc_14000C621
0x14000c5a3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000c5a8  test    al, al
0x14000c5aa  jnz     short loc_14000C621
0x14000c5ac  mov     [rsp+48h+var_28], ebp
0x14000c5b0  xor     eax, eax
0x14000c5b2  mov     [rsp+48h+var_24], eax
0x14000c5b6  mov     [rsp+48h+var_20], rsi
0x14000c5bb  lea     rcx, [rdi+20h]; this
0x14000c5bf  lea     r8d, [rax+10h]; unsigned __int64
0x14000c5c3  lea     rdx, [rsp+48h+var_28]; void *
0x14000c5c8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000c5cd  cmp     byte ptr [rdi+18h], 0
0x14000c5d1  jnz     short loc_14000C621
0x14000c5d3  lea     rbx, [rdi+10h]
0x14000c5d7  cmp     qword ptr [rbx], 0
0x14000c5db  jnz     short loc_14000C60F
0x14000c5dd  lea     rcx, [rsp+48h+arg_0]; this
0x14000c5e2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000c5e7  xor     r8d, r8d; pcbe
0x14000c5ea  mov     rdx, rdi; pv
0x14000c5ed  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000c5f4  call    cs:__imp_CreateThreadpoolTimer
0x14000c5fa  mov     rdx, rax
0x14000c5fd  mov     rcx, rbx
0x14000c600  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000c605  lea     rcx, [rsp+48h+arg_0]; this
0x14000c60a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000c60f  mov     r8d, 493E0h
0x14000c615  lea     rdx, [rdi+18h]
0x14000c619  mov     rcx, rbx
0x14000c61c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000c621  lea     rcx, [rsp+48h+arg_18]
0x14000c626  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000c62b  nop
0x14000c62c  mov     rbx, [rsp+48h+arg_8]
0x14000c631  add     rsp, 30h
0x14000c635  pop     rdi
0x14000c636  pop     rsi
0x14000c637  pop     rbp
0x14000c638  retn
```
