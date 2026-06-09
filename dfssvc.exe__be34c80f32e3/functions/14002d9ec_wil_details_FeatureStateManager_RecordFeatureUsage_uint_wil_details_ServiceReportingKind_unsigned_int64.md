# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14002d9ec`
- end: `0x14002dad5`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x140031850`

## callees

- `0x1400276dc`
- `0x140027984`
- `0x140027c54`
- `0x140029f8c`
- `0x140029fd4`
- `0x14002d598`
- `0x14002d924`
- `0x14002d9ec`
- `0x140031eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002da4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002da4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14002da82`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14002da82`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  bool v9; // zf
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-18h] BYREF
  char v12; // [rsp+40h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v9 = BYTE1(a1[8].Ptr) == 0;
    v11 = a1 + 4;
    if ( v9 )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x14002d9ec  mov     [rsp+arg_8], rbx
0x14002d9f1  mov     [rsp+arg_10], rbp
0x14002d9f6  mov     [rsp+arg_18], rsi
0x14002d9fb  push    rdi
0x14002d9fc  sub     rsp, 30h
0x14002da00  cmp     byte ptr [rcx], 0
0x14002da03  mov     rbx, r9
0x14002da06  mov     esi, r8d
0x14002da09  mov     ebp, edx
0x14002da0b  mov     rdi, rcx
0x14002da0e  jz      loc_14002DABF
0x14002da14  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14002da19  test    al, al
0x14002da1b  jz      loc_14002DABF
0x14002da21  mov     rcx, [rdi+18h]
0x14002da25  mov     r9, rbx
0x14002da28  mov     r8d, esi
0x14002da2b  mov     edx, ebp
0x14002da2d  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14002da32  test    al, al
0x14002da34  jz      loc_14002DABF
0x14002da3a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14002da3f  test    al, al
0x14002da41  jnz     short loc_14002DABF
0x14002da43  lea     rbx, [rdi+20h]
0x14002da47  mov     rcx, rbx; SRWLock
0x14002da4a  call    cs:__imp_AcquireSRWLockExclusive
0x14002da51  nop     dword ptr [rax+rax+00h]
0x14002da56  cmp     byte ptr [rdi+41h], 0
0x14002da5a  mov     [rsp+38h+var_18], rbx
0x14002da5f  lea     rbx, [rdi+30h]
0x14002da63  jnz     short loc_14002DAB5
0x14002da65  cmp     qword ptr [rbx], 0
0x14002da69  jnz     short loc_14002DAA3
0x14002da6b  lea     rcx, [rsp+38h+arg_0]; this
0x14002da70  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002da75  xor     r8d, r8d; pcbe
0x14002da78  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14002da7f  mov     rdx, rdi; pv
0x14002da82  call    cs:__imp_CreateThreadpoolTimer
0x14002da89  nop     dword ptr [rax+rax+00h]
0x14002da8e  mov     rdx, rax
0x14002da91  mov     rcx, rbx
0x14002da94  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14002da99  lea     rcx, [rsp+38h+arg_0]; this
0x14002da9e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002daa3  mov     r8d, 493E0h
0x14002daa9  lea     rdx, [rdi+41h]
0x14002daad  mov     rcx, rbx
0x14002dab0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14002dab5  lea     rcx, [rsp+38h+var_18]
0x14002daba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14002dabf  mov     rbx, [rsp+38h+arg_8]
0x14002dac4  mov     rbp, [rsp+38h+arg_10]
0x14002dac9  mov     rsi, [rsp+38h+arg_18]
0x14002dace  add     rsp, 30h
0x14002dad2  pop     rdi
0x14002dad3  retn
```
