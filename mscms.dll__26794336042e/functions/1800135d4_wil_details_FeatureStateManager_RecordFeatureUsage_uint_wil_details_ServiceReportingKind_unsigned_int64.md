# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800135d4`
- end: `0x180013695`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180024990`

## callees

- `0x180013590`
- `0x1800135d4`
- `0x18001369c`
- `0x180014288`
- `0x180014360`
- `0x180026620`
- `0x180026640`
- `0x18002ac8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013623`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013623`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013685`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013685`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013650`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013650`

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
                            (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x1800135d4  push    rbx
0x1800135d6  push    rbp
0x1800135d7  push    rsi
0x1800135d8  push    rdi
0x1800135d9  sub     rsp, 28h
0x1800135dd  mov     rdi, r9
0x1800135e0  mov     esi, r8d
0x1800135e3  mov     ebp, edx
0x1800135e5  mov     rbx, rcx
0x1800135e8  cmp     byte ptr [rcx], 0
0x1800135eb  jz      loc_18001368C
0x1800135f1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800135f6  test    al, al
0x1800135f8  jz      loc_18001368C
0x1800135fe  mov     r9, rdi
0x180013601  mov     r8d, esi
0x180013604  mov     edx, ebp
0x180013606  mov     rcx, [rbx+18h]
0x18001360a  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001360f  test    al, al
0x180013611  jz      short loc_18001368C
0x180013613  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180013618  test    al, al
0x18001361a  jnz     short loc_18001368C
0x18001361c  lea     rdi, [rbx+20h]
0x180013620  mov     rcx, rdi; SRWLock
0x180013623  call    cs:__imp_AcquireSRWLockExclusive
0x180013629  cmp     byte ptr [rbx+41h], 0
0x18001362d  jnz     short loc_18001367D
0x18001362f  lea     rsi, [rbx+30h]
0x180013633  cmp     qword ptr [rsi], 0
0x180013637  jnz     short loc_18001366B
0x180013639  lea     rcx, [rsp+48h+arg_0]; this
0x18001363e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013643  xor     r8d, r8d; pcbe
0x180013646  mov     rdx, rbx; pv
0x180013649  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013650  call    cs:__imp_CreateThreadpoolTimer
0x180013656  mov     rdx, rax
0x180013659  mov     rcx, rsi
0x18001365c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013661  lea     rcx, [rsp+48h+arg_0]; this
0x180013666  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001366b  mov     r8d, 493E0h
0x180013671  lea     rdx, [rbx+41h]
0x180013675  mov     rcx, rsi
0x180013678  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001367d  test    rdi, rdi
0x180013680  jz      short loc_18001368C
0x180013682  mov     rcx, rdi; SRWLock
0x180013685  call    cs:__imp_ReleaseSRWLockExclusive
0x18001368b  nop
0x18001368c  add     rsp, 28h
0x180013690  pop     rdi
0x180013691  pop     rsi
0x180013692  pop     rbp
0x180013693  pop     rbx
0x180013694  retn
```
