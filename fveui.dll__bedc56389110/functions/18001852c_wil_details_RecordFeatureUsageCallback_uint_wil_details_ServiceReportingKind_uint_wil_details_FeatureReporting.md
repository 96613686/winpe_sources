# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x18001852c`
- end: `0x180018617`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `235`
- prototype: `void __fastcall(__int64, __int64, __int64, struct wil_details_FeatureReportingCache *, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180018968`

## callees

- `0x18000474c`
- `0x18000c5f4`
- `0x18001844c`
- `0x18001852c`
- `0x18002d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800185ad`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800185ad`

## pseudocode

```c
void __fastcall wil::details::RecordFeatureUsageCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct wil_details_FeatureReportingCache *a4,
        RTL_SRWLOCK *a5)
{
  unsigned int v6; // edi
  RTL_SRWLOCK *v7; // rbx
  unsigned int Ptr_high; // r8d
  void (__fastcall *v9)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  const char *v10; // [rsp+20h] [rbp-8h]

  v6 = a1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!(_DWORD)a2 || (unsigned int)(a2 - 100) <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a1, a2, 1);
  v7 = a5;
  if ( LODWORD(a5->Ptr) )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      v6,
      a4);
  Ptr_high = HIDWORD(v7->Ptr);
  if ( Ptr_high )
    wil::details::WilApi_RecordFeatureUsage(
      (wil::details *)v6,
      (unsigned int)v7[1].Ptr,
      Ptr_high,
      (unsigned int)a4,
      v10);
  if ( !LODWORD(v7[2].Ptr) && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    a5 = &SRWLock;
    if ( !qword_18003DD58 )
    {
      qword_18003DD58 = 0;
      v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v9(&qword_18003DD58, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  }
}

```

## disassembly

```asm
0x18001852c  mov     [rsp+arg_0], rbx
0x180018531  mov     [rsp+arg_8], rsi
0x180018536  push    rdi; char *
0x180018537  sub     rsp, 20h
0x18001853b  mov     rsi, r9
0x18001853e  mov     edi, ecx
0x180018540  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180018547  test    rax, rax
0x18001854a  jz      short loc_180018565
0x18001854c  test    edx, edx
0x18001854e  jz      short loc_18001855A
0x180018550  lea     r8d, [rdx-64h]
0x180018554  cmp     r8d, 31h ; '1'
0x180018558  ja      short loc_180018565
0x18001855a  mov     r8d, 1
0x180018560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018565  mov     rbx, [rsp+28h+arg_20]
0x18001856a  cmp     dword ptr [rbx], 0
0x18001856d  jz      short loc_180018580
0x18001856f  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x180018572  mov     edx, edi; unsigned int
0x180018574  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001857b  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180018580  mov     r8d, [rbx+4]; unsigned int
0x180018584  test    r8d, r8d
0x180018587  jz      short loc_180018593
0x180018589  mov     edx, [rbx+8]; unsigned int
0x18001858c  mov     ecx, edi; this
0x18001858e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180018593  cmp     dword ptr [rbx+10h], 0
0x180018597  jnz     short loc_180018607
0x180018599  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001859f  test    eax, eax
0x1800185a1  jz      short loc_180018607
0x1800185a3  lea     rbx, SRWLock
0x1800185aa  mov     rcx, rbx; SRWLock
0x1800185ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800185b3  mov     [rsp+28h+arg_20], rbx
0x1800185b8  cmp     cs:qword_18003DD58, 0
0x1800185c0  jnz     short loc_1800185FC
0x1800185c2  mov     cs:qword_18003DD58, 0
0x1800185cd  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800185d4  test    rax, rax
0x1800185d7  jnz     short loc_1800185E5
0x1800185d9  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800185e0  test    rax, rax
0x1800185e3  jz      short loc_1800185FC
0x1800185e5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800185e9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800185f0  lea     rcx, qword_18003DD58
0x1800185f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fc  lea     rcx, [rsp+28h+arg_20]
0x180018601  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018606  nop
0x180018607  mov     rbx, [rsp+28h+arg_0]
0x18001860c  mov     rsi, [rsp+28h+arg_8]
0x180018611  add     rsp, 20h
0x180018615  pop     rdi
0x180018616  retn
```
