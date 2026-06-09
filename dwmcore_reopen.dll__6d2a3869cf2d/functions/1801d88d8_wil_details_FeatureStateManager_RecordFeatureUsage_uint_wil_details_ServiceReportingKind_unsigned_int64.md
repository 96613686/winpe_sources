# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1801d88d8`
- end: `0x1801d8992`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1801f2a50`

## callees

- `0x1801d88d8`
- `0x1801d89e0`
- `0x1801d8a14`
- `0x1801d8a34`
- `0x1801d8a78`
- `0x180202598`
- `0x18021a2bc`
- `0x18021bca4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d891f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d891f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d8933`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d8933`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801d8963`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801d8963`

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
  char v10; // [rsp+50h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    if ( !BYTE1(a1[8].Ptr) )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    if ( a1 != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(a1 + 4);
  }
}

```

## disassembly

```asm
0x1801d88d8  push    rbx
0x1801d88da  push    rbp
0x1801d88db  push    rsi
0x1801d88dc  push    rdi
0x1801d88dd  sub     rsp, 28h
0x1801d88e1  cmp     byte ptr [rcx], 0
0x1801d88e4  mov     rdi, r9
0x1801d88e7  mov     esi, r8d
0x1801d88ea  mov     ebp, edx
0x1801d88ec  mov     rbx, rcx
0x1801d88ef  jz      short loc_1801D8939
0x1801d88f1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1801d88f6  test    al, al
0x1801d88f8  jz      short loc_1801D8939
0x1801d88fa  mov     rcx, [rbx+18h]
0x1801d88fe  mov     r9, rdi
0x1801d8901  mov     r8d, esi
0x1801d8904  mov     edx, ebp
0x1801d8906  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1801d890b  test    al, al
0x1801d890d  jz      short loc_1801D8939
0x1801d890f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1801d8914  test    al, al
0x1801d8916  jnz     short loc_1801D8939
0x1801d8918  lea     rdi, [rbx+20h]
0x1801d891c  mov     rcx, rdi; SRWLock
0x1801d891f  call    cs:__imp_AcquireSRWLockExclusive
0x1801d8925  cmp     byte ptr [rbx+41h], 0
0x1801d8929  jz      short loc_1801D8942
0x1801d892b  test    rdi, rdi
0x1801d892e  jz      short loc_1801D8939
0x1801d8930  mov     rcx, rdi; SRWLock
0x1801d8933  call    cs:__imp_ReleaseSRWLockExclusive
0x1801d8939  add     rsp, 28h
0x1801d893d  pop     rdi
0x1801d893e  pop     rsi
0x1801d893f  pop     rbp
0x1801d8940  pop     rbx
0x1801d8941  retn
0x1801d8942  lea     rsi, [rbx+30h]
0x1801d8946  cmp     qword ptr [rsi], 0
0x1801d894a  jnz     short loc_1801D897E
0x1801d894c  lea     rcx, [rsp+48h+arg_0]; this
0x1801d8951  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801d8956  xor     r8d, r8d; pcbe
0x1801d8959  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801d8960  mov     rdx, rbx; pv
0x1801d8963  call    cs:__imp_CreateThreadpoolTimer
0x1801d8969  mov     rdx, rax
0x1801d896c  mov     rcx, rsi
0x1801d896f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801d8974  lea     rcx, [rsp+48h+arg_0]; this
0x1801d8979  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801d897e  mov     r8d, 493E0h
0x1801d8984  lea     rdx, [rbx+41h]
0x1801d8988  mov     rcx, rsi
0x1801d898b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1801d8990  jmp     short loc_1801D892B
```
