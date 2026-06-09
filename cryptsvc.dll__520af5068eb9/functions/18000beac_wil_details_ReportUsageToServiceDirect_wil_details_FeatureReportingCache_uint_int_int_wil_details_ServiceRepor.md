# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000beac`
- end: `0x18000bfc3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000be08`

## callees

- `0x18000beac`
- `0x18000c884`
- `0x18000cd18`
- `0x1800126e0`
- `0x180016008`
- `0x180018010`

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
      (char *)&wil::details::g_enabledStateManager,
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
0x18000beac  mov     [rsp+arg_0], rbx
0x18000beb1  mov     [rsp+arg_18], r9d
0x18000beb6  push    rbp
0x18000beb7  push    rsi
0x18000beb8  push    rdi
0x18000beb9  push    r12
0x18000bebb  push    r13
0x18000bebd  push    r14
0x18000bebf  push    r15
0x18000bec1  sub     rsp, 50h
0x18000bec5  mov     ebx, [rsp+88h+arg_20]
0x18000becc  mov     edi, edx
0x18000bece  mov     rdx, rcx
0x18000bed1  mov     r13d, r8d
0x18000bed4  mov     r15, rcx
0x18000bed7  mov     r8d, ebx
0x18000beda  lea     rcx, [rsp+88h+var_58]
0x18000bedf  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000bee4  mov     esi, 1
0x18000bee9  mov     ecx, [rax+8]
0x18000beec  mov     r12d, [rax]
0x18000beef  mov     r14d, [rax+4]
0x18000bef3  mov     ebp, [rax+10h]
0x18000bef6  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000befd  mov     [rsp+88h+arg_10], ecx
0x18000bf04  test    rax, rax
0x18000bf07  jz      short loc_18000BF21
0x18000bf09  test    ebx, ebx
0x18000bf0b  jz      short loc_18000BF15
0x18000bf0d  lea     ecx, [rbx-64h]
0x18000bf10  cmp     ecx, 31h ; '1'
0x18000bf13  ja      short loc_18000BF21
0x18000bf15  mov     r8d, esi
0x18000bf18  mov     edx, ebx
0x18000bf1a  mov     ecx, edi
0x18000bf1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf21  test    r12d, r12d
0x18000bf24  jz      short loc_18000BF37
0x18000bf26  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18000bf29  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000bf30  mov     edx, edi; unsigned int
0x18000bf32  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000bf37  test    r14d, r14d
0x18000bf3a  jz      short loc_18000BF4D
0x18000bf3c  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18000bf43  mov     r8d, r14d; unsigned int
0x18000bf46  mov     ecx, edi; this
0x18000bf48  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000bf4d  test    ebp, ebp
0x18000bf4f  jnz     short loc_18000BF64
0x18000bf51  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000bf58  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000bf5f  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000bf64  test    r13d, r13d
0x18000bf67  jz      short loc_18000BF84
0x18000bf69  mov     edx, ebx
0x18000bf6b  mov     ecx, edi; this
0x18000bf6d  bts     edx, 1Fh
0x18000bf71  cmp     [rsp+88h+arg_18], 0
0x18000bf79  cmovz   edx, ebx; unsigned int
0x18000bf7c  xor     r8d, r8d; unsigned int
0x18000bf7f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000bf84  test    ebp, ebp
0x18000bf86  jnz     short loc_18000BFA7
0x18000bf88  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000bf8f  test    rax, rax
0x18000bf92  jz      short loc_18000BFA9
0x18000bf94  mov     r8b, [rsp+88h+arg_38]
0x18000bf9c  mov     edx, ebx
0x18000bf9e  mov     ecx, edi
0x18000bfa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa5  jmp     short loc_18000BFA9
0x18000bfa7  xor     esi, esi
0x18000bfa9  mov     rbx, [rsp+88h+arg_0]
0x18000bfb1  mov     eax, esi
0x18000bfb3  add     rsp, 50h
0x18000bfb7  pop     r15
0x18000bfb9  pop     r14
0x18000bfbb  pop     r13
0x18000bfbd  pop     r12
0x18000bfbf  pop     rdi
0x18000bfc0  pop     rsi
0x18000bfc1  pop     rbp
0x18000bfc2  retn
```
