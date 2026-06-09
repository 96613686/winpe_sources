# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180002d2c`
- end: `0x180002de8`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180009ae0`

## callees

- `0x180002d2c`
- `0x180002f4c`
- `0x180003000`
- `0x180004758`
- `0x18000490c`
- `0x18000492c`
- `0x18000a204`
- `0x18000aafc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002de0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002de0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002d73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002d73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002dae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002dae`

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
0x180002d2c  push    rbx
0x180002d2e  push    rbp
0x180002d2f  push    rsi
0x180002d30  push    rdi
0x180002d31  sub     rsp, 28h
0x180002d35  mov     rdi, r9
0x180002d38  mov     esi, r8d
0x180002d3b  mov     ebp, edx
0x180002d3d  mov     rbx, rcx
0x180002d40  cmp     byte ptr [rcx], 0
0x180002d43  jz      short loc_180002D84
0x180002d45  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180002d4a  test    al, al
0x180002d4c  jz      short loc_180002D84
0x180002d4e  mov     r9, rdi
0x180002d51  mov     r8d, esi
0x180002d54  mov     edx, ebp
0x180002d56  mov     rcx, [rbx+18h]
0x180002d5a  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180002d5f  test    al, al
0x180002d61  jz      short loc_180002D84
0x180002d63  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180002d68  test    al, al
0x180002d6a  jnz     short loc_180002D84
0x180002d6c  lea     rdi, [rbx+20h]
0x180002d70  mov     rcx, rdi; SRWLock
0x180002d73  call    cs:__imp_AcquireSRWLockExclusive
0x180002d79  cmp     byte ptr [rbx+41h], 0
0x180002d7d  jz      short loc_180002D8D
0x180002d7f  test    rdi, rdi
0x180002d82  jnz     short loc_180002DDD
0x180002d84  add     rsp, 28h
0x180002d88  pop     rdi
0x180002d89  pop     rsi
0x180002d8a  pop     rbp
0x180002d8b  pop     rbx
0x180002d8c  retn
0x180002d8d  lea     rsi, [rbx+30h]
0x180002d91  cmp     qword ptr [rsi], 0
0x180002d95  jnz     short loc_180002DC9
0x180002d97  lea     rcx, [rsp+48h+arg_0]; this
0x180002d9c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180002da1  xor     r8d, r8d; pcbe
0x180002da4  mov     rdx, rbx; pv
0x180002da7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180002dae  call    cs:__imp_CreateThreadpoolTimer
0x180002db4  mov     rdx, rax
0x180002db7  mov     rcx, rsi
0x180002dba  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180002dbf  lea     rcx, [rsp+48h+arg_0]; this
0x180002dc4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180002dc9  mov     r8d, 493E0h
0x180002dcf  lea     rdx, [rbx+41h]
0x180002dd3  mov     rcx, rsi
0x180002dd6  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180002ddb  jmp     short loc_180002D7F
0x180002ddd  mov     rcx, rdi; SRWLock
0x180002de0  call    cs:__imp_ReleaseSRWLockExclusive
0x180002de6  jmp     short loc_180002D84
```
