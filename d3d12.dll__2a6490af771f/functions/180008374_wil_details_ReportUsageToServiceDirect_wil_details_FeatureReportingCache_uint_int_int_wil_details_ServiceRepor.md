# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180008374`
- end: `0x18000847c`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000eee8`

## callees

- `0x180008374`
- `0x180008484`
- `0x1800086dc`
- `0x1800087c0`
- `0x180008a74`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // edi
  int v15; // r15d
  unsigned int v16; // ebp
  unsigned int v17; // r13d
  int v18; // esi
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-78h]
  _BYTE v22[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v14 = 1;
  v15 = *v10;
  v16 = v10[1];
  v17 = v10[2];
  v18 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (a5 - 100 <= 0x31 || !a5) )
    g_wil_details_RecordSRUMFeatureUsage(39847774, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x260075E, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x260075E, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(39847774, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x180008374  mov     [rsp+arg_18], r9d
0x180008379  push    rbx
0x18000837a  push    rbp
0x18000837b  push    rsi
0x18000837c  push    rdi
0x18000837d  push    r12
0x18000837f  push    r13
0x180008381  push    r14
0x180008383  push    r15
0x180008385  sub     rsp, 58h
0x180008389  mov     ebx, [rsp+98h+arg_20]
0x180008390  mov     r12d, r8d
0x180008393  mov     r14, rcx
0x180008396  mov     rdx, rcx
0x180008399  mov     r8d, ebx
0x18000839c  lea     rcx, [rsp+98h+var_68]
0x1800083a1  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800083a6  mov     edi, 1
0x1800083ab  mov     r15d, [rax]
0x1800083ae  mov     ebp, [rax+4]
0x1800083b1  mov     r13d, [rax+8]
0x1800083b5  mov     esi, [rax+10h]
0x1800083b8  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800083bf  test    rax, rax
0x1800083c2  jz      short loc_1800083DF
0x1800083c4  lea     ecx, [rbx-64h]
0x1800083c7  cmp     ecx, 31h ; '1'
0x1800083ca  jbe     short loc_1800083D0
0x1800083cc  test    ebx, ebx
0x1800083ce  jnz     short loc_1800083DF
0x1800083d0  mov     r8d, edi
0x1800083d3  mov     edx, ebx
0x1800083d5  mov     ecx, 260075Eh
0x1800083da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083df  test    r15d, r15d
0x1800083e2  jz      short loc_1800083F3
0x1800083e4  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1800083e7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800083ee  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800083f3  test    ebp, ebp
0x1800083f5  jz      short loc_180008407
0x1800083f7  mov     r8d, ebp; unsigned int
0x1800083fa  mov     edx, r13d; unsigned int
0x1800083fd  mov     ecx, 260075Eh; this
0x180008402  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180008407  test    esi, esi
0x180008409  jnz     short loc_18000841E
0x18000840b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180008412  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180008419  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000841e  test    r12d, r12d
0x180008421  jz      short loc_180008441
0x180008423  mov     edx, ebx
0x180008425  mov     ecx, 260075Eh; this
0x18000842a  bts     edx, 1Fh
0x18000842e  cmp     [rsp+98h+arg_18], 0
0x180008436  cmovz   edx, ebx; unsigned int
0x180008439  xor     r8d, r8d; unsigned int
0x18000843c  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180008441  test    esi, esi
0x180008443  jnz     short loc_180008467
0x180008445  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000844c  test    rax, rax
0x18000844f  jz      short loc_180008469
0x180008451  mov     r8b, [rsp+98h+arg_38]
0x180008459  mov     edx, ebx
0x18000845b  mov     ecx, 260075Eh
0x180008460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008465  jmp     short loc_180008469
0x180008467  xor     edi, edi
0x180008469  mov     eax, edi
0x18000846b  add     rsp, 58h
0x18000846f  pop     r15
0x180008471  pop     r14
0x180008473  pop     r13
0x180008475  pop     r12
0x180008477  pop     rdi
0x180008478  pop     rsi
0x180008479  pop     rbp
0x18000847a  pop     rbx
0x18000847b  retn
```
