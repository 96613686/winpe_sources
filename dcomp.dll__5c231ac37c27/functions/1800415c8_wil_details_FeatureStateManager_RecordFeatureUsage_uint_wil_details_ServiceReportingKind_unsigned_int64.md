# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800415c8`
- end: `0x180041683`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800dc330`

## callees

- `0x18003fe14`
- `0x18003fe68`
- `0x1800415c8`
- `0x18004168c`
- `0x180041708`
- `0x1800430cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041611`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041611`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041625`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180041625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041641`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041669`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041669`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180041656`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180041656`

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
                            `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x1800415c8  push    rbx
0x1800415ca  push    rbp
0x1800415cb  push    rsi
0x1800415cc  push    rdi
0x1800415cd  push    r14
0x1800415cf  sub     rsp, 20h
0x1800415d3  cmp     byte ptr [rcx], 0
0x1800415d6  mov     rbx, r9
0x1800415d9  mov     esi, r8d
0x1800415dc  mov     ebp, edx
0x1800415de  mov     rdi, rcx
0x1800415e1  jz      short loc_18004162B
0x1800415e3  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800415e8  test    al, al
0x1800415ea  jz      short loc_18004162B
0x1800415ec  mov     rcx, [rdi+18h]
0x1800415f0  mov     r9, rbx
0x1800415f3  mov     r8d, esi
0x1800415f6  mov     edx, ebp
0x1800415f8  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800415fd  test    al, al
0x1800415ff  jz      short loc_18004162B
0x180041601  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180041606  test    al, al
0x180041608  jnz     short loc_18004162B
0x18004160a  lea     rsi, [rdi+20h]
0x18004160e  mov     rcx, rsi; SRWLock
0x180041611  call    cs:__imp_AcquireSRWLockExclusive
0x180041617  cmp     byte ptr [rdi+41h], 0
0x18004161b  jz      short loc_180041636
0x18004161d  test    rsi, rsi
0x180041620  jz      short loc_18004162B
0x180041622  mov     rcx, rsi; SRWLock
0x180041625  call    cs:__imp_ReleaseSRWLockExclusive
0x18004162b  add     rsp, 20h
0x18004162f  pop     r14
0x180041631  pop     rdi
0x180041632  pop     rsi
0x180041633  pop     rbp
0x180041634  pop     rbx
0x180041635  retn
0x180041636  lea     rbp, [rdi+30h]
0x18004163a  cmp     qword ptr [rbp+0], 0
0x18004163f  jnz     short loc_18004166F
0x180041641  call    cs:__imp_GetLastError
0x180041647  xor     r8d, r8d; pcbe
0x18004164a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180041651  mov     rdx, rdi; pv
0x180041654  mov     ebx, eax
0x180041656  call    cs:__imp_CreateThreadpoolTimer
0x18004165c  mov     rdx, rax
0x18004165f  mov     rcx, rbp
0x180041662  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180041667  mov     ecx, ebx; dwErrCode
0x180041669  call    cs:__imp_SetLastError
0x18004166f  mov     r8d, 493E0h
0x180041675  lea     rdx, [rdi+41h]
0x180041679  mov     rcx, rbp
0x18004167c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180041681  jmp     short loc_18004161D
```
