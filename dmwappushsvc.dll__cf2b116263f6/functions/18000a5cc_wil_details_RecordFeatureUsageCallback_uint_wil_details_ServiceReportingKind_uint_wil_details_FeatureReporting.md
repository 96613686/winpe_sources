# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x18000a5cc`
- end: `0x18000a6af`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `227`
- prototype: `void __fastcall(__int64, __int64, __int64, struct wil_details_FeatureReportingCache *, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000ae24`

## callees

- `0x180007984`
- `0x180009ec4`
- `0x18000a5cc`
- `0x18000bfd0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a64a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a64a`

## pseudocode

```c
void __fastcall wil::details::RecordFeatureUsageCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct wil_details_FeatureReportingCache *a4,
        RTL_SRWLOCK *a5)
{
  RTL_SRWLOCK *v6; // rbx
  unsigned int Ptr_high; // r8d
  void (__fastcall *v8)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  const char *v9; // [rsp+20h] [rbp-8h]

  if ( g_wil_details_RecordSRUMFeatureUsage && (!(_DWORD)a2 || (unsigned int)(a2 - 100) <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(23806551, a2, 1);
  v6 = a5;
  if ( LODWORD(a5->Ptr) )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      a2,
      a4);
  Ptr_high = HIDWORD(v6->Ptr);
  if ( Ptr_high )
    wil::details::WilApi_RecordFeatureUsage(
      (wil::details *)0x16B4257,
      (unsigned int)v6[1].Ptr,
      Ptr_high,
      (unsigned int)a4,
      v9);
  if ( !LODWORD(v6[2].Ptr) && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    a5 = &SRWLock;
    if ( !qword_18001C608 )
    {
      qword_18001C608 = 0;
      v8 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v8 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v8(&qword_18001C608, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  }
}

```

## disassembly

```asm
0x18000a5cc  mov     [rsp+arg_0], rbx
0x18000a5d1  push    rdi; char *
0x18000a5d2  sub     rsp, 20h
0x18000a5d6  mov     rdi, r9
0x18000a5d9  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000a5e0  test    rax, rax
0x18000a5e3  jz      short loc_18000A601
0x18000a5e5  test    edx, edx
0x18000a5e7  jz      short loc_18000A5F1
0x18000a5e9  lea     ecx, [rdx-64h]
0x18000a5ec  cmp     ecx, 31h ; '1'
0x18000a5ef  ja      short loc_18000A601
0x18000a5f1  mov     ecx, 16B4257h
0x18000a5f6  mov     r8d, 1
0x18000a5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a601  mov     rbx, [rsp+28h+arg_20]
0x18000a606  cmp     dword ptr [rbx], 0
0x18000a609  jz      short loc_18000A61A
0x18000a60b  mov     r8, rdi; struct wil_details_FeatureReportingCache *
0x18000a60e  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000a615  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000a61a  mov     r8d, [rbx+4]; unsigned int
0x18000a61e  test    r8d, r8d
0x18000a621  jz      short loc_18000A630
0x18000a623  mov     edx, [rbx+8]; unsigned int
0x18000a626  mov     ecx, 16B4257h; this
0x18000a62b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000a630  cmp     dword ptr [rbx+10h], 0
0x18000a634  jnz     short loc_18000A6A4
0x18000a636  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000a63c  test    eax, eax
0x18000a63e  jz      short loc_18000A6A4
0x18000a640  lea     rbx, SRWLock
0x18000a647  mov     rcx, rbx; SRWLock
0x18000a64a  call    cs:__imp_AcquireSRWLockExclusive
0x18000a650  mov     [rsp+28h+arg_20], rbx
0x18000a655  cmp     cs:qword_18001C608, 0
0x18000a65d  jnz     short loc_18000A699
0x18000a65f  mov     cs:qword_18001C608, 0
0x18000a66a  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000a671  test    rax, rax
0x18000a674  jnz     short loc_18000A682
0x18000a676  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000a67d  test    rax, rax
0x18000a680  jz      short loc_18000A699
0x18000a682  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a686  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000a68d  lea     rcx, qword_18001C608
0x18000a694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a699  lea     rcx, [rsp+28h+arg_20]
0x18000a69e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a6a3  nop
0x18000a6a4  mov     rbx, [rsp+28h+arg_0]
0x18000a6a9  add     rsp, 20h
0x18000a6ad  pop     rdi
0x18000a6ae  retn
```
