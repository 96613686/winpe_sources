# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001a0ec`
- end: `0x18001a1b9`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18003a630`

## callees

- `0x18000d7a8`
- `0x18000d810`
- `0x18000ef90`
- `0x18001a0ec`
- `0x18001a1c0`
- `0x18001a204`
- `0x18001a36c`
- `0x1800392a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a13f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a13f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a18d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a18d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a171`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a171`

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
  DWORD dwErrCode; // [rsp+64h] [rbp+Ch]

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
        if ( !v11 )
          SetLastError(dwErrCode);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18001a0ec  push    rbx
0x18001a0ee  push    rbp
0x18001a0ef  push    rsi
0x18001a0f0  push    rdi
0x18001a0f1  sub     rsp, 38h
0x18001a0f5  mov     rbx, r9
0x18001a0f8  mov     esi, r8d
0x18001a0fb  mov     ebp, edx
0x18001a0fd  mov     rdi, rcx
0x18001a100  cmp     byte ptr [rcx], 0
0x18001a103  jz      loc_18001A1B0
0x18001a109  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001a10e  test    al, al
0x18001a110  jz      loc_18001A1B0
0x18001a116  mov     r9, rbx
0x18001a119  mov     r8d, esi
0x18001a11c  mov     edx, ebp
0x18001a11e  mov     rcx, [rdi+18h]
0x18001a122  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001a127  test    al, al
0x18001a129  jz      loc_18001A1B0
0x18001a12f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001a134  test    al, al
0x18001a136  jnz     short loc_18001A1B0
0x18001a138  lea     rbx, [rdi+20h]
0x18001a13c  mov     rcx, rbx; SRWLock
0x18001a13f  call    cs:__imp_AcquireSRWLockExclusive
0x18001a145  mov     [rsp+58h+var_38], rbx
0x18001a14a  cmp     byte ptr [rdi+41h], 0
0x18001a14e  jnz     short loc_18001A1A5
0x18001a150  lea     rbx, [rdi+30h]
0x18001a154  cmp     qword ptr [rbx], 0
0x18001a158  jnz     short loc_18001A193
0x18001a15a  lea     rcx, [rsp+58h+arg_0]; this
0x18001a15f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a164  xor     r8d, r8d; pcbe
0x18001a167  mov     rdx, rdi; pv
0x18001a16a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001a171  call    cs:__imp_CreateThreadpoolTimer
0x18001a177  mov     rdx, rax
0x18001a17a  mov     rcx, rbx
0x18001a17d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001a182  cmp     [rsp+58h+arg_0], 0
0x18001a187  jnz     short loc_18001A193
0x18001a189  mov     ecx, [rsp+58h+dwErrCode]; dwErrCode
0x18001a18d  call    cs:__imp_SetLastError
0x18001a193  mov     r8d, 493E0h
0x18001a199  lea     rdx, [rdi+41h]
0x18001a19d  mov     rcx, rbx
0x18001a1a0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001a1a5  lea     rcx, [rsp+58h+var_38]
0x18001a1aa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001a1af  nop
0x18001a1b0  add     rsp, 38h
0x18001a1b4  pop     rdi
0x18001a1b5  pop     rsi
0x18001a1b6  pop     rbp
0x18001a1b7  pop     rbx
0x18001a1b8  retn
```
