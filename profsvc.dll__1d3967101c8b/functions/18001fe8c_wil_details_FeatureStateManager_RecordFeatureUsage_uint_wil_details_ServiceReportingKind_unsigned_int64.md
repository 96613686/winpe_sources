# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001fe8c`
- end: `0x18001ff4d`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180027e10`

## callees

- `0x18001fe8c`
- `0x18001ff54`
- `0x180020c38`
- `0x180030dd0`
- `0x180030e58`
- `0x180030e78`
- `0x180030ebc`
- `0x1800310a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fedb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fedb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ff3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ff3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ff08`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ff08`

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
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
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
0x18001fe8c  push    rbx
0x18001fe8e  push    rbp
0x18001fe8f  push    rsi
0x18001fe90  push    rdi
0x18001fe91  sub     rsp, 28h
0x18001fe95  mov     rdi, r9
0x18001fe98  mov     esi, r8d
0x18001fe9b  mov     ebp, edx
0x18001fe9d  mov     rbx, rcx
0x18001fea0  cmp     byte ptr [rcx], 0
0x18001fea3  jz      loc_18001FF44
0x18001fea9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001feae  test    al, al
0x18001feb0  jz      loc_18001FF44
0x18001feb6  mov     r9, rdi
0x18001feb9  mov     r8d, esi
0x18001febc  mov     edx, ebp
0x18001febe  mov     rcx, [rbx+18h]
0x18001fec2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001fec7  test    al, al
0x18001fec9  jz      short loc_18001FF44
0x18001fecb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001fed0  test    al, al
0x18001fed2  jnz     short loc_18001FF44
0x18001fed4  lea     rdi, [rbx+20h]
0x18001fed8  mov     rcx, rdi; SRWLock
0x18001fedb  call    cs:__imp_AcquireSRWLockExclusive
0x18001fee1  cmp     byte ptr [rbx+41h], 0
0x18001fee5  jnz     short loc_18001FF35
0x18001fee7  lea     rsi, [rbx+30h]
0x18001feeb  cmp     qword ptr [rsi], 0
0x18001feef  jnz     short loc_18001FF23
0x18001fef1  lea     rcx, [rsp+48h+arg_0]; this
0x18001fef6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001fefb  xor     r8d, r8d; pcbe
0x18001fefe  mov     rdx, rbx; pv
0x18001ff01  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ff08  call    cs:__imp_CreateThreadpoolTimer
0x18001ff0e  mov     rdx, rax
0x18001ff11  mov     rcx, rsi
0x18001ff14  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ff19  lea     rcx, [rsp+48h+arg_0]; this
0x18001ff1e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ff23  mov     r8d, 493E0h
0x18001ff29  lea     rdx, [rbx+41h]
0x18001ff2d  mov     rcx, rsi
0x18001ff30  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001ff35  test    rdi, rdi
0x18001ff38  jz      short loc_18001FF44
0x18001ff3a  mov     rcx, rdi; SRWLock
0x18001ff3d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ff43  nop
0x18001ff44  add     rsp, 28h
0x18001ff48  pop     rdi
0x18001ff49  pop     rsi
0x18001ff4a  pop     rbp
0x18001ff4b  pop     rbx
0x18001ff4c  retn
```
