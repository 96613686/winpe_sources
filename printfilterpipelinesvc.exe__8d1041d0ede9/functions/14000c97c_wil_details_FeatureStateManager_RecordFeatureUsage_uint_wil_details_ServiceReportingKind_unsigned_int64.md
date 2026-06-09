# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000c97c`
- end: `0x14000ca3e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x14000e590`

## callees

- `0x140009174`
- `0x1400094d4`
- `0x140009828`
- `0x140009f64`
- `0x140009fa8`
- `0x14000c440`
- `0x14000c8d4`
- `0x14000c97c`
- `0x14000ed50`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14000c9fd`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000c9fd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c9cb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c9cb`

## pseudocode

```c
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
0x14000c97c  push    rbx
0x14000c97e  push    rbp
0x14000c97f  push    rsi
0x14000c980  push    rdi
0x14000c981  sub     rsp, 38h
0x14000c985  mov     rbx, r9
0x14000c988  mov     esi, r8d
0x14000c98b  mov     ebp, edx
0x14000c98d  mov     rdi, rcx
0x14000c990  cmp     byte ptr [rcx], 0
0x14000c993  jz      loc_14000CA35
0x14000c999  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000c99e  test    al, al
0x14000c9a0  jz      loc_14000CA35
0x14000c9a6  mov     r9, rbx
0x14000c9a9  mov     r8d, esi
0x14000c9ac  mov     edx, ebp
0x14000c9ae  mov     rcx, [rdi+18h]
0x14000c9b2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000c9b7  test    al, al
0x14000c9b9  jz      short loc_14000CA35
0x14000c9bb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000c9c0  test    al, al
0x14000c9c2  jnz     short loc_14000CA35
0x14000c9c4  lea     rbx, [rdi+20h]
0x14000c9c8  mov     rcx, rbx; SRWLock
0x14000c9cb  call    cs:__imp_AcquireSRWLockExclusive
0x14000c9d1  mov     [rsp+58h+var_38], rbx
0x14000c9d6  cmp     byte ptr [rdi+41h], 0
0x14000c9da  jnz     short loc_14000CA2A
0x14000c9dc  lea     rbx, [rdi+30h]
0x14000c9e0  cmp     qword ptr [rbx], 0
0x14000c9e4  jnz     short loc_14000CA18
0x14000c9e6  lea     rcx, [rsp+58h+arg_0]; this
0x14000c9eb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000c9f0  xor     r8d, r8d; pcbe
0x14000c9f3  mov     rdx, rdi; pv
0x14000c9f6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000c9fd  call    cs:__imp_CreateThreadpoolTimer
0x14000ca03  mov     rdx, rax
0x14000ca06  mov     rcx, rbx
0x14000ca09  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000ca0e  lea     rcx, [rsp+58h+arg_0]; this
0x14000ca13  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000ca18  mov     r8d, 493E0h
0x14000ca1e  lea     rdx, [rdi+41h]
0x14000ca22  mov     rcx, rbx
0x14000ca25  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000ca2a  lea     rcx, [rsp+58h+var_38]
0x14000ca2f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ca34  nop
0x14000ca35  add     rsp, 38h
0x14000ca39  pop     rdi
0x14000ca3a  pop     rsi
0x14000ca3b  pop     rbp
0x14000ca3c  pop     rbx
0x14000ca3d  retn
```
