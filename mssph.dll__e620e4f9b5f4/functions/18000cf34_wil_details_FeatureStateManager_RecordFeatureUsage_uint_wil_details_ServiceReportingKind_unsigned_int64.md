# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000cf34`
- end: `0x18000d001`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800152f0`

## callees

- `0x18000b4e0`
- `0x18000c010`
- `0x18000cf34`
- `0x18000d008`
- `0x18000d04c`
- `0x18000d118`
- `0x18000d138`
- `0x180014124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cf87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cf87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfd5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cfb9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cfb9`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+64h] [rbp+Ch]

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v10 = (RTL_SRWLOCK *)(a1 + 32);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        if ( !v11 )
          SetLastError(dwErrCode);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18000cf34  push    rbx
0x18000cf36  push    rbp
0x18000cf37  push    rsi
0x18000cf38  push    rdi
0x18000cf39  sub     rsp, 38h
0x18000cf3d  mov     rbx, r9
0x18000cf40  mov     esi, r8d
0x18000cf43  mov     ebp, edx
0x18000cf45  mov     rdi, rcx
0x18000cf48  cmp     byte ptr [rcx], 0
0x18000cf4b  jz      loc_18000CFF8
0x18000cf51  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000cf56  test    al, al
0x18000cf58  jz      loc_18000CFF8
0x18000cf5e  mov     r9, rbx
0x18000cf61  mov     r8d, esi
0x18000cf64  mov     edx, ebp
0x18000cf66  mov     rcx, [rdi+18h]
0x18000cf6a  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000cf6f  test    al, al
0x18000cf71  jz      loc_18000CFF8
0x18000cf77  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000cf7c  test    al, al
0x18000cf7e  jnz     short loc_18000CFF8
0x18000cf80  lea     rbx, [rdi+20h]
0x18000cf84  mov     rcx, rbx; SRWLock
0x18000cf87  call    cs:__imp_AcquireSRWLockExclusive
0x18000cf8d  mov     [rsp+58h+var_38], rbx
0x18000cf92  cmp     byte ptr [rdi+41h], 0
0x18000cf96  jnz     short loc_18000CFED
0x18000cf98  lea     rbx, [rdi+30h]
0x18000cf9c  cmp     qword ptr [rbx], 0
0x18000cfa0  jnz     short loc_18000CFDB
0x18000cfa2  lea     rcx, [rsp+58h+arg_0]; this
0x18000cfa7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cfac  xor     r8d, r8d; pcbe
0x18000cfaf  mov     rdx, rdi; pv
0x18000cfb2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000cfb9  call    cs:__imp_CreateThreadpoolTimer
0x18000cfbf  mov     rdx, rax
0x18000cfc2  mov     rcx, rbx
0x18000cfc5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000cfca  cmp     [rsp+58h+arg_0], 0
0x18000cfcf  jnz     short loc_18000CFDB
0x18000cfd1  mov     ecx, [rsp+58h+dwErrCode]; dwErrCode
0x18000cfd5  call    cs:__imp_SetLastError
0x18000cfdb  mov     r8d, 493E0h
0x18000cfe1  lea     rdx, [rdi+41h]
0x18000cfe5  mov     rcx, rbx
0x18000cfe8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000cfed  lea     rcx, [rsp+58h+var_38]
0x18000cff2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000cff7  nop
0x18000cff8  add     rsp, 38h
0x18000cffc  pop     rdi
0x18000cffd  pop     rsi
0x18000cffe  pop     rbp
0x18000cfff  pop     rbx
0x18000d000  retn
```
