# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1801d6d24`
- end: `0x1801d6dde`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1801f2be0`

## callees

- `0x1801d6d24`
- `0x1801d6e2c`
- `0x1801d6e60`
- `0x1801d6e80`
- `0x1801d6ec4`
- `0x180202578`
- `0x18021a29c`
- `0x18021bc84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d6d6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d6d6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d6d7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d6d7f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801d6daf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801d6daf`

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
0x1801d6d24  push    rbx
0x1801d6d26  push    rbp
0x1801d6d27  push    rsi
0x1801d6d28  push    rdi
0x1801d6d29  sub     rsp, 28h
0x1801d6d2d  cmp     byte ptr [rcx], 0
0x1801d6d30  mov     rdi, r9
0x1801d6d33  mov     esi, r8d
0x1801d6d36  mov     ebp, edx
0x1801d6d38  mov     rbx, rcx
0x1801d6d3b  jz      short loc_1801D6D85
0x1801d6d3d  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1801d6d42  test    al, al
0x1801d6d44  jz      short loc_1801D6D85
0x1801d6d46  mov     rcx, [rbx+18h]
0x1801d6d4a  mov     r9, rdi
0x1801d6d4d  mov     r8d, esi
0x1801d6d50  mov     edx, ebp
0x1801d6d52  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1801d6d57  test    al, al
0x1801d6d59  jz      short loc_1801D6D85
0x1801d6d5b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1801d6d60  test    al, al
0x1801d6d62  jnz     short loc_1801D6D85
0x1801d6d64  lea     rdi, [rbx+20h]
0x1801d6d68  mov     rcx, rdi; SRWLock
0x1801d6d6b  call    cs:__imp_AcquireSRWLockExclusive
0x1801d6d71  cmp     byte ptr [rbx+41h], 0
0x1801d6d75  jz      short loc_1801D6D8E
0x1801d6d77  test    rdi, rdi
0x1801d6d7a  jz      short loc_1801D6D85
0x1801d6d7c  mov     rcx, rdi; SRWLock
0x1801d6d7f  call    cs:__imp_ReleaseSRWLockExclusive
0x1801d6d85  add     rsp, 28h
0x1801d6d89  pop     rdi
0x1801d6d8a  pop     rsi
0x1801d6d8b  pop     rbp
0x1801d6d8c  pop     rbx
0x1801d6d8d  retn
0x1801d6d8e  lea     rsi, [rbx+30h]
0x1801d6d92  cmp     qword ptr [rsi], 0
0x1801d6d96  jnz     short loc_1801D6DCA
0x1801d6d98  lea     rcx, [rsp+48h+arg_0]; this
0x1801d6d9d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801d6da2  xor     r8d, r8d; pcbe
0x1801d6da5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801d6dac  mov     rdx, rbx; pv
0x1801d6daf  call    cs:__imp_CreateThreadpoolTimer
0x1801d6db5  mov     rdx, rax
0x1801d6db8  mov     rcx, rsi
0x1801d6dbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801d6dc0  lea     rcx, [rsp+48h+arg_0]; this
0x1801d6dc5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801d6dca  mov     r8d, 493E0h
0x1801d6dd0  lea     rdx, [rbx+41h]
0x1801d6dd4  mov     rcx, rsi
0x1801d6dd7  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1801d6ddc  jmp     short loc_1801D6D77
```
