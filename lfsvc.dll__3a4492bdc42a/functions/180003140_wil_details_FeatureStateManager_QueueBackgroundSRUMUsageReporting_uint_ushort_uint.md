# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180003140`
- end: `0x180003213`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `211`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009ae0`

## callees

- `0x180002c48`
- `0x180003140`
- `0x1800032ec`
- `0x18000330c`
- `0x18000336c`
- `0x18000338c`
- `0x1800033b0`
- `0x18000a03c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003174`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003174`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800031d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800031d0`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]
  int v12; // [rsp+28h] [rbp-40h]
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp-38h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v13 = (RTL_SRWLOCK *)(pv + 40);
    v11 = 0;
    v9 = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v9, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
}

```

## disassembly

```asm
0x180003140  push    rbx
0x180003142  push    rbp
0x180003143  push    rsi
0x180003144  push    rdi
0x180003145  push    r14
0x180003147  sub     rsp, 40h
0x18000314b  mov     r14d, r9d
0x18000314e  movzx   ebp, r8w
0x180003152  mov     esi, edx
0x180003154  mov     rdi, rcx
0x180003157  cmp     byte ptr [rcx], 0
0x18000315a  jz      loc_180003208
0x180003160  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180003165  test    al, al
0x180003167  jnz     loc_180003208
0x18000316d  lea     rbx, [rdi+28h]
0x180003171  mov     rcx, rbx; SRWLock
0x180003174  call    cs:__imp_AcquireSRWLockExclusive
0x18000317a  mov     [rsp+68h+var_38], rbx
0x18000317f  xor     eax, eax
0x180003181  mov     [rsp+68h+var_42], ax
0x180003186  mov     [rsp+68h+var_48], esi
0x18000318a  mov     [rsp+68h+var_44], bp
0x18000318f  mov     [rsp+68h+var_40], r14d
0x180003194  lea     rcx, [rdi+0E8h]; this
0x18000319b  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000319f  lea     rdx, [rsp+68h+var_48]; void *
0x1800031a4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800031a9  cmp     byte ptr [rdi+40h], 0
0x1800031ad  jnz     short loc_1800031FD
0x1800031af  lea     rbx, [rdi+38h]
0x1800031b3  cmp     qword ptr [rbx], 0
0x1800031b7  jnz     short loc_1800031EB
0x1800031b9  lea     rcx, [rsp+68h+var_48]; this
0x1800031be  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800031c3  xor     r8d, r8d; pcbe
0x1800031c6  mov     rdx, rdi; pv
0x1800031c9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800031d0  call    cs:__imp_CreateThreadpoolTimer
0x1800031d6  mov     rdx, rax
0x1800031d9  mov     rcx, rbx
0x1800031dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800031e1  lea     rcx, [rsp+68h+var_48]; this
0x1800031e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800031eb  mov     r8d, 1388h
0x1800031f1  lea     rdx, [rdi+40h]
0x1800031f5  mov     rcx, rbx
0x1800031f8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800031fd  lea     rcx, [rsp+68h+var_38]
0x180003202  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180003207  nop
0x180003208  add     rsp, 40h
0x18000320c  pop     r14
0x18000320e  pop     rdi
0x18000320f  pop     rsi
0x180003210  pop     rbp
0x180003211  pop     rbx
0x180003212  retn
```
