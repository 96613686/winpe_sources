# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18003c0ac`
- end: `0x18003c168`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180063600`

## callees

- `0x18003c0ac`
- `0x18003c170`
- `0x18003c1ec`
- `0x18003c298`
- `0x18003d080`
- `0x18003d700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c109`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c109`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c0f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c0f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c126`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c14e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c14e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003c13b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003c13b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax

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
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        SetLastError(LastError);
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
0x18003c0ac  push    rbx
0x18003c0ae  push    rbp
0x18003c0af  push    rsi
0x18003c0b0  push    rdi
0x18003c0b1  push    r14
0x18003c0b3  sub     rsp, 20h
0x18003c0b7  mov     rbx, r9
0x18003c0ba  mov     esi, r8d
0x18003c0bd  mov     ebp, edx
0x18003c0bf  mov     rdi, rcx
0x18003c0c2  cmp     byte ptr [rcx], 0
0x18003c0c5  jz      short loc_18003C110
0x18003c0c7  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18003c0cc  test    al, al
0x18003c0ce  jz      short loc_18003C110
0x18003c0d0  mov     r9, rbx
0x18003c0d3  mov     r8d, esi
0x18003c0d6  mov     edx, ebp
0x18003c0d8  mov     rcx, [rdi+18h]
0x18003c0dc  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18003c0e1  test    al, al
0x18003c0e3  jz      short loc_18003C110
0x18003c0e5  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003c0ea  test    al, al
0x18003c0ec  jnz     short loc_18003C110
0x18003c0ee  lea     rsi, [rdi+20h]
0x18003c0f2  mov     rcx, rsi; SRWLock
0x18003c0f5  call    cs:__imp_AcquireSRWLockExclusive
0x18003c0fb  cmp     byte ptr [rdi+41h], 0
0x18003c0ff  jz      short loc_18003C11B
0x18003c101  test    rsi, rsi
0x18003c104  jz      short loc_18003C110
0x18003c106  mov     rcx, rsi; SRWLock
0x18003c109  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c10f  nop
0x18003c110  add     rsp, 20h
0x18003c114  pop     r14
0x18003c116  pop     rdi
0x18003c117  pop     rsi
0x18003c118  pop     rbp
0x18003c119  pop     rbx
0x18003c11a  retn
0x18003c11b  lea     rbp, [rdi+30h]
0x18003c11f  cmp     qword ptr [rbp+0], 0
0x18003c124  jnz     short loc_18003C154
0x18003c126  call    cs:__imp_GetLastError
0x18003c12c  mov     ebx, eax
0x18003c12e  xor     r8d, r8d; pcbe
0x18003c131  mov     rdx, rdi; pv
0x18003c134  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003c13b  call    cs:__imp_CreateThreadpoolTimer
0x18003c141  mov     rdx, rax
0x18003c144  mov     rcx, rbp
0x18003c147  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003c14c  mov     ecx, ebx; dwErrCode
0x18003c14e  call    cs:__imp_SetLastError
0x18003c154  mov     r8d, 493E0h
0x18003c15a  lea     rdx, [rdi+41h]
0x18003c15e  mov     rcx, rbp
0x18003c161  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003c166  jmp     short loc_18003C101
```
