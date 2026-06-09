# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180013ac8`
- end: `0x180013b9b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `211`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018530`

## callees

- `0x18000717c`
- `0x18000851c`
- `0x180008a0c`
- `0x18000f60c`
- `0x180012d0c`
- `0x180013ac8`
- `0x180018e04`
- `0x180018f0c`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180013b58`
- `KERNEL32!CreateThreadpoolTimer` at `0x180013b58`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013afc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013afc`

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
0x180013ac8  push    rbx
0x180013aca  push    rbp
0x180013acb  push    rsi
0x180013acc  push    rdi
0x180013acd  push    r14
0x180013acf  sub     rsp, 40h
0x180013ad3  mov     r14d, r9d
0x180013ad6  movzx   ebp, r8w
0x180013ada  mov     esi, edx
0x180013adc  mov     rdi, rcx
0x180013adf  cmp     byte ptr [rcx], 0
0x180013ae2  jz      loc_180013B90
0x180013ae8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180013aed  test    al, al
0x180013aef  jnz     loc_180013B90
0x180013af5  lea     rbx, [rdi+28h]
0x180013af9  mov     rcx, rbx; SRWLock
0x180013afc  call    cs:__imp_AcquireSRWLockExclusive
0x180013b02  mov     [rsp+68h+var_38], rbx
0x180013b07  xor     eax, eax
0x180013b09  mov     [rsp+68h+var_42], ax
0x180013b0e  mov     [rsp+68h+var_48], esi
0x180013b12  mov     [rsp+68h+var_44], bp
0x180013b17  mov     [rsp+68h+var_40], r14d
0x180013b1c  lea     rcx, [rdi+0E8h]; this
0x180013b23  lea     r8d, [rax+0Ch]; unsigned __int64
0x180013b27  lea     rdx, [rsp+68h+var_48]; void *
0x180013b2c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013b31  cmp     byte ptr [rdi+40h], 0
0x180013b35  jnz     short loc_180013B85
0x180013b37  lea     rbx, [rdi+38h]
0x180013b3b  cmp     qword ptr [rbx], 0
0x180013b3f  jnz     short loc_180013B73
0x180013b41  lea     rcx, [rsp+68h+var_48]; this
0x180013b46  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013b4b  xor     r8d, r8d; pcbe
0x180013b4e  mov     rdx, rdi; pv
0x180013b51  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013b58  call    cs:__imp_CreateThreadpoolTimer
0x180013b5e  mov     rdx, rax
0x180013b61  mov     rcx, rbx
0x180013b64  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013b69  lea     rcx, [rsp+68h+var_48]; this
0x180013b6e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180013b73  mov     r8d, 1388h
0x180013b79  lea     rdx, [rdi+40h]
0x180013b7d  mov     rcx, rbx
0x180013b80  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180013b85  lea     rcx, [rsp+68h+var_38]
0x180013b8a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013b8f  nop
0x180013b90  add     rsp, 40h
0x180013b94  pop     r14
0x180013b96  pop     rdi
0x180013b97  pop     rsi
0x180013b98  pop     rbp
0x180013b99  pop     rbx
0x180013b9a  retn
```
