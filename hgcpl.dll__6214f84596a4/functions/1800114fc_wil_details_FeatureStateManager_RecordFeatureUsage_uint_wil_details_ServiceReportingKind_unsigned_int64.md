# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800114fc`
- end: `0x1800115bd`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800121a0`

## callees

- `0x180004728`
- `0x1800049c0`
- `0x180005f3c`
- `0x1800070ac`
- `0x180010538`
- `0x18001057c`
- `0x180011454`
- `0x1800114fc`
- `0x18001267c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001154b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001154b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001157d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001157d`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  bool v9; // zf
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF
  char v12; // [rsp+60h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v9 = BYTE1(a1[8].Ptr) == 0;
    v11 = a1 + 4;
    if ( v9 )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x1800114fc  push    rbx
0x1800114fe  push    rbp
0x1800114ff  push    rsi
0x180011500  push    rdi
0x180011501  sub     rsp, 38h
0x180011505  cmp     byte ptr [rcx], 0
0x180011508  mov     rbx, r9
0x18001150b  mov     esi, r8d
0x18001150e  mov     ebp, edx
0x180011510  mov     rdi, rcx
0x180011513  jz      loc_1800115B4
0x180011519  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001151e  test    al, al
0x180011520  jz      loc_1800115B4
0x180011526  mov     rcx, [rdi+18h]
0x18001152a  mov     r9, rbx
0x18001152d  mov     r8d, esi
0x180011530  mov     edx, ebp
0x180011532  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180011537  test    al, al
0x180011539  jz      short loc_1800115B4
0x18001153b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180011540  test    al, al
0x180011542  jnz     short loc_1800115B4
0x180011544  lea     rbx, [rdi+20h]
0x180011548  mov     rcx, rbx; SRWLock
0x18001154b  call    cs:__imp_AcquireSRWLockExclusive
0x180011551  cmp     byte ptr [rdi+41h], 0
0x180011555  mov     [rsp+58h+var_38], rbx
0x18001155a  jnz     short loc_1800115AA
0x18001155c  lea     rbx, [rdi+30h]
0x180011560  cmp     qword ptr [rbx], 0
0x180011564  jnz     short loc_180011598
0x180011566  lea     rcx, [rsp+58h+arg_0]; this
0x18001156b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011570  xor     r8d, r8d; pcbe
0x180011573  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001157a  mov     rdx, rdi; pv
0x18001157d  call    cs:__imp_CreateThreadpoolTimer
0x180011583  mov     rdx, rax
0x180011586  mov     rcx, rbx
0x180011589  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001158e  lea     rcx, [rsp+58h+arg_0]; this
0x180011593  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011598  mov     r8d, 493E0h
0x18001159e  lea     rdx, [rdi+41h]
0x1800115a2  mov     rcx, rbx
0x1800115a5  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800115aa  lea     rcx, [rsp+58h+var_38]
0x1800115af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800115b4  add     rsp, 38h
0x1800115b8  pop     rdi
0x1800115b9  pop     rsi
0x1800115ba  pop     rbp
0x1800115bb  pop     rbx
0x1800115bc  retn
```
