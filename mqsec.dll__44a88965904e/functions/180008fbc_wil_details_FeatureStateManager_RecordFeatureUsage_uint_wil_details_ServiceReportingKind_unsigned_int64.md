# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008fbc`
- end: `0x18000907f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000a8b0`

## callees

- `0x1800059c4`
- `0x180005c6c`
- `0x180005fd4`
- `0x1800065e0`
- `0x180006624`
- `0x180008b3c`
- `0x180008f14`
- `0x180008fbc`
- `0x18000af74`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000900b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000900b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000903d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000903d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v10 = a1 + 4;
    if ( !BYTE1(a1[8].Ptr) )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180008fbc  push    rbx
0x180008fbe  push    rbp
0x180008fbf  push    rsi
0x180008fc0  push    rdi
0x180008fc1  sub     rsp, 38h
0x180008fc5  mov     rbx, r9
0x180008fc8  mov     esi, r8d
0x180008fcb  mov     ebp, edx
0x180008fcd  mov     rdi, rcx
0x180008fd0  cmp     byte ptr [rcx], 0
0x180008fd3  jz      loc_180009076
0x180008fd9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008fde  test    al, al
0x180008fe0  jz      loc_180009076
0x180008fe6  mov     r9, rbx
0x180008fe9  mov     r8d, esi
0x180008fec  mov     edx, ebp
0x180008fee  mov     rcx, [rdi+18h]
0x180008ff2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180008ff7  test    al, al
0x180008ff9  jz      short loc_180009076
0x180008ffb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180009000  test    al, al
0x180009002  jnz     short loc_180009076
0x180009004  lea     rbx, [rdi+20h]
0x180009008  mov     rcx, rbx; SRWLock
0x18000900b  call    cs:__imp_AcquireSRWLockExclusive
0x180009011  mov     [rsp+58h+var_38], rbx
0x180009016  cmp     byte ptr [rdi+41h], 0
0x18000901a  jnz     short loc_18000906B
0x18000901c  lea     rbx, [rdi+30h]
0x180009020  cmp     qword ptr [rbx], 0
0x180009024  jnz     short loc_180009058
0x180009026  lea     rcx, [rsp+58h+arg_0]; this
0x18000902b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009030  xor     r8d, r8d; pcbe
0x180009033  mov     rdx, rdi; pv
0x180009036  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000903d  call    cs:__imp_CreateThreadpoolTimer
0x180009043  mov     rdx, rax
0x180009046  mov     rcx, rbx
0x180009049  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000904e  lea     rcx, [rsp+58h+arg_0]; this
0x180009053  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009058  mov     r8d, 493E0h
0x18000905e  lea     rdx, [rdi+41h]
0x180009062  mov     rcx, rbx
0x180009065  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000906a  nop
0x18000906b  lea     rcx, [rsp+58h+var_38]
0x180009070  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009075  nop
0x180009076  add     rsp, 38h
0x18000907a  pop     rdi
0x18000907b  pop     rsi
0x18000907c  pop     rbp
0x18000907d  pop     rbx
0x18000907e  retn
```
