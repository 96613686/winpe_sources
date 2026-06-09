# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180014844`
- end: `0x180014922`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `222`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800151a4`

## callees

- `0x18000ac48`
- `0x18000ac68`
- `0x18000acac`
- `0x18000accc`
- `0x18000acf0`
- `0x18000ae18`
- `0x180014844`
- `0x1800168ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014877`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014877`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800148da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800148da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+58h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v9 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v7[0] = 52061724;
        v7[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v7, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x180014844  mov     [rsp+arg_8], rbx
0x180014849  mov     [rsp+arg_10], rsi
0x18001484e  push    rdi
0x18001484f  sub     rsp, 30h
0x180014853  mov     rsi, r8
0x180014856  mov     rdi, rcx
0x180014859  mov     eax, [rcx]
0x18001485b  test    eax, eax
0x18001485d  jz      loc_180014912
0x180014863  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180014868  test    al, al
0x18001486a  jnz     loc_180014912
0x180014870  lea     rbx, [rdi+8]
0x180014874  mov     rcx, rbx; SRWLock
0x180014877  call    cs:__imp_AcquireSRWLockExclusive
0x18001487d  mov     [rsp+38h+arg_18], rbx
0x180014882  mov     eax, [rdi]
0x180014884  test    eax, eax
0x180014886  jz      short loc_180014907
0x180014888  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001488d  test    al, al
0x18001488f  jnz     short loc_180014907
0x180014891  mov     [rsp+38h+var_18], 31A661Ch
0x18001489a  mov     [rsp+38h+var_10], rsi
0x18001489f  lea     rcx, [rdi+20h]; this
0x1800148a3  mov     r8d, 10h; unsigned __int64
0x1800148a9  lea     rdx, [rsp+38h+var_18]; void *
0x1800148ae  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800148b3  cmp     byte ptr [rdi+18h], 0
0x1800148b7  jnz     short loc_180014907
0x1800148b9  lea     rbx, [rdi+10h]
0x1800148bd  cmp     qword ptr [rbx], 0
0x1800148c1  jnz     short loc_1800148F5
0x1800148c3  lea     rcx, [rsp+38h+arg_0]; this
0x1800148c8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800148cd  xor     r8d, r8d; pcbe
0x1800148d0  mov     rdx, rdi; pv
0x1800148d3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800148da  call    cs:__imp_CreateThreadpoolTimer
0x1800148e0  mov     rdx, rax
0x1800148e3  mov     rcx, rbx
0x1800148e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800148eb  lea     rcx, [rsp+38h+arg_0]; this
0x1800148f0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800148f5  mov     r8d, 493E0h
0x1800148fb  lea     rdx, [rdi+18h]
0x1800148ff  mov     rcx, rbx
0x180014902  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180014907  lea     rcx, [rsp+38h+arg_18]
0x18001490c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014911  nop
0x180014912  mov     rbx, [rsp+38h+arg_8]
0x180014917  mov     rsi, [rsp+38h+arg_10]
0x18001491c  add     rsp, 30h
0x180014920  pop     rdi
0x180014921  retn
```
