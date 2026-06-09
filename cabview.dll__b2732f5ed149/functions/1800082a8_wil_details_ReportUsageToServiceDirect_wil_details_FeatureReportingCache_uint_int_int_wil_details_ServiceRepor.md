# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800082a8`
- end: `0x1800083bf`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180008204`

## callees

- `0x1800055d4`
- `0x180007694`
- `0x1800082a8`
- `0x180009630`
- `0x18000a7d8`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v11; // rax
  __int64 v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // esi
  int v15; // r12d
  unsigned int v16; // r14d
  int v17; // ebp
  unsigned int v18; // edx
  const char *v20; // [rsp+20h] [rbp-68h]
  _BYTE v21[88]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v22; // [rsp+A0h] [rbp+18h]

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v21, a1, a5);
  v14 = 1;
  v15 = *v11;
  v16 = v11[1];
  v17 = v11[4];
  v22 = v11[2];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v22, v16, v13, v20);
  if ( !v17 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v18 = a5 | 0x80000000;
    if ( !a4 )
      v18 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v18, 0, v13, v20);
  }
  if ( v17 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x1800082a8  mov     [rsp+arg_0], rbx
0x1800082ad  mov     [rsp+arg_18], r9d
0x1800082b2  push    rbp
0x1800082b3  push    rsi
0x1800082b4  push    rdi
0x1800082b5  push    r12
0x1800082b7  push    r13
0x1800082b9  push    r14
0x1800082bb  push    r15
0x1800082bd  sub     rsp, 50h
0x1800082c1  mov     ebx, [rsp+88h+arg_20]
0x1800082c8  mov     edi, edx
0x1800082ca  mov     rdx, rcx
0x1800082cd  mov     r13d, r8d
0x1800082d0  mov     r15, rcx
0x1800082d3  mov     r8d, ebx
0x1800082d6  lea     rcx, [rsp+88h+var_58]
0x1800082db  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800082e0  mov     esi, 1
0x1800082e5  mov     ecx, [rax+8]
0x1800082e8  mov     r12d, [rax]
0x1800082eb  mov     r14d, [rax+4]
0x1800082ef  mov     ebp, [rax+10h]
0x1800082f2  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800082f9  mov     [rsp+88h+arg_10], ecx
0x180008300  test    rax, rax
0x180008303  jz      short loc_18000831D
0x180008305  test    ebx, ebx
0x180008307  jz      short loc_180008311
0x180008309  lea     ecx, [rbx-64h]
0x18000830c  cmp     ecx, 31h ; '1'
0x18000830f  ja      short loc_18000831D
0x180008311  mov     r8d, esi
0x180008314  mov     edx, ebx
0x180008316  mov     ecx, edi
0x180008318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000831d  test    r12d, r12d
0x180008320  jz      short loc_180008333
0x180008322  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180008325  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000832c  mov     edx, edi; unsigned int
0x18000832e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180008333  test    r14d, r14d
0x180008336  jz      short loc_180008349
0x180008338  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000833f  mov     r8d, r14d; unsigned int
0x180008342  mov     ecx, edi; this
0x180008344  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180008349  test    ebp, ebp
0x18000834b  jnz     short loc_180008360
0x18000834d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180008354  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000835b  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180008360  test    r13d, r13d
0x180008363  jz      short loc_180008380
0x180008365  mov     edx, ebx
0x180008367  mov     ecx, edi; this
0x180008369  bts     edx, 1Fh
0x18000836d  cmp     [rsp+88h+arg_18], 0
0x180008375  cmovz   edx, ebx; unsigned int
0x180008378  xor     r8d, r8d; unsigned int
0x18000837b  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180008380  test    ebp, ebp
0x180008382  jnz     short loc_1800083A3
0x180008384  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000838b  test    rax, rax
0x18000838e  jz      short loc_1800083A5
0x180008390  mov     r8b, [rsp+88h+arg_38]
0x180008398  mov     edx, ebx
0x18000839a  mov     ecx, edi
0x18000839c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a1  jmp     short loc_1800083A5
0x1800083a3  xor     esi, esi
0x1800083a5  mov     rbx, [rsp+88h+arg_0]
0x1800083ad  mov     eax, esi
0x1800083af  add     rsp, 50h
0x1800083b3  pop     r15
0x1800083b5  pop     r14
0x1800083b7  pop     r13
0x1800083b9  pop     r12
0x1800083bb  pop     rdi
0x1800083bc  pop     rsi
0x1800083bd  pop     rbp
0x1800083be  retn
```
