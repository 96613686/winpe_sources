# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18004776c`
- end: `0x180047856`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180019900`
- `0x180020390`

## callees

- `0x18001fdf4`
- `0x180020d40`
- `0x18002c88c`
- `0x18002c8b0`
- `0x18002c8f8`
- `0x18002c91c`
- `0x18003eaac`
- `0x18004776c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004779e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004779e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004780a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004780a`

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
0x18004776c  mov     [rsp+arg_8], rbx
0x180047771  push    rbp
0x180047772  push    rsi
0x180047773  push    rdi
0x180047774  sub     rsp, 30h
0x180047778  mov     rsi, r8
0x18004777b  mov     ebp, edx
0x18004777d  mov     rdi, rcx
0x180047780  mov     eax, [rcx]
0x180047782  test    eax, eax
0x180047784  jz      loc_180047848
0x18004778a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004778f  test    al, al
0x180047791  jnz     loc_180047848
0x180047797  lea     rbx, [rdi+8]
0x18004779b  mov     rcx, rbx; SRWLock
0x18004779e  call    cs:__imp_AcquireSRWLockExclusive
0x1800477a5  nop     dword ptr [rax+rax+00h]
0x1800477aa  mov     [rsp+48h+arg_18], rbx
0x1800477af  mov     eax, [rdi]
0x1800477b1  test    eax, eax
0x1800477b3  jz      loc_18004783D
0x1800477b9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800477be  test    al, al
0x1800477c0  jnz     short loc_18004783D
0x1800477c2  mov     [rsp+48h+var_28], ebp
0x1800477c6  xor     eax, eax
0x1800477c8  mov     [rsp+48h+var_24], eax
0x1800477cc  mov     [rsp+48h+var_20], rsi
0x1800477d1  lea     rcx, [rdi+30h]; this
0x1800477d5  lea     r8d, [rax+10h]; unsigned __int64
0x1800477d9  lea     rdx, [rsp+48h+var_28]; void *
0x1800477de  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800477e3  cmp     byte ptr [rdi+18h], 0
0x1800477e7  jnz     short loc_18004783D
0x1800477e9  lea     rbx, [rdi+10h]
0x1800477ed  cmp     qword ptr [rbx], 0
0x1800477f1  jnz     short loc_18004782B
0x1800477f3  lea     rcx, [rsp+48h+arg_0]; this
0x1800477f8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800477fd  xor     r8d, r8d; pcbe
0x180047800  mov     rdx, rdi; pv
0x180047803  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004780a  call    cs:__imp_CreateThreadpoolTimer
0x180047811  nop     dword ptr [rax+rax+00h]
0x180047816  mov     rdx, rax
0x180047819  mov     rcx, rbx
0x18004781c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180047821  lea     rcx, [rsp+48h+arg_0]; this
0x180047826  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004782b  mov     r8d, 493E0h
0x180047831  lea     rdx, [rdi+18h]
0x180047835  mov     rcx, rbx
0x180047838  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004783d  lea     rcx, [rsp+48h+arg_18]
0x180047842  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180047847  nop
0x180047848  mov     rbx, [rsp+48h+arg_8]
0x18004784d  add     rsp, 30h
0x180047851  pop     rdi
0x180047852  pop     rsi
0x180047853  pop     rbp
0x180047854  retn
```
