# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180011ccc`
- end: `0x180011de3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180011c28`

## callees

- `0x18000c234`
- `0x18000f9e4`
- `0x180011000`
- `0x180011ccc`
- `0x1800130f8`
- `0x180028010`

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
0x180011ccc  mov     [rsp+arg_0], rbx
0x180011cd1  mov     [rsp+arg_18], r9d
0x180011cd6  push    rbp
0x180011cd7  push    rsi
0x180011cd8  push    rdi
0x180011cd9  push    r12
0x180011cdb  push    r13
0x180011cdd  push    r14
0x180011cdf  push    r15
0x180011ce1  sub     rsp, 50h
0x180011ce5  mov     ebx, [rsp+88h+arg_20]
0x180011cec  mov     edi, edx
0x180011cee  mov     rdx, rcx
0x180011cf1  mov     r13d, r8d
0x180011cf4  mov     r15, rcx
0x180011cf7  mov     r8d, ebx
0x180011cfa  lea     rcx, [rsp+88h+var_58]
0x180011cff  call    wil_details_FeatureReporting_RecordUsageInCache
0x180011d04  mov     esi, 1
0x180011d09  mov     ecx, [rax+8]
0x180011d0c  mov     r12d, [rax]
0x180011d0f  mov     r14d, [rax+4]
0x180011d13  mov     ebp, [rax+10h]
0x180011d16  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180011d1d  mov     [rsp+88h+arg_10], ecx
0x180011d24  test    rax, rax
0x180011d27  jz      short loc_180011D41
0x180011d29  test    ebx, ebx
0x180011d2b  jz      short loc_180011D35
0x180011d2d  lea     ecx, [rbx-64h]
0x180011d30  cmp     ecx, 31h ; '1'
0x180011d33  ja      short loc_180011D41
0x180011d35  mov     r8d, esi
0x180011d38  mov     edx, ebx
0x180011d3a  mov     ecx, edi
0x180011d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d41  test    r12d, r12d
0x180011d44  jz      short loc_180011D57
0x180011d46  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180011d49  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180011d50  mov     edx, edi; unsigned int
0x180011d52  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180011d57  test    r14d, r14d
0x180011d5a  jz      short loc_180011D6D
0x180011d5c  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180011d63  mov     r8d, r14d; unsigned int
0x180011d66  mov     ecx, edi; this
0x180011d68  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180011d6d  test    ebp, ebp
0x180011d6f  jnz     short loc_180011D84
0x180011d71  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180011d78  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180011d7f  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180011d84  test    r13d, r13d
0x180011d87  jz      short loc_180011DA4
0x180011d89  mov     edx, ebx
0x180011d8b  mov     ecx, edi; this
0x180011d8d  bts     edx, 1Fh
0x180011d91  cmp     [rsp+88h+arg_18], 0
0x180011d99  cmovz   edx, ebx; unsigned int
0x180011d9c  xor     r8d, r8d; unsigned int
0x180011d9f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180011da4  test    ebp, ebp
0x180011da6  jnz     short loc_180011DC7
0x180011da8  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180011daf  test    rax, rax
0x180011db2  jz      short loc_180011DC9
0x180011db4  mov     r8b, [rsp+88h+arg_38]
0x180011dbc  mov     edx, ebx
0x180011dbe  mov     ecx, edi
0x180011dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc5  jmp     short loc_180011DC9
0x180011dc7  xor     esi, esi
0x180011dc9  mov     rbx, [rsp+88h+arg_0]
0x180011dd1  mov     eax, esi
0x180011dd3  add     rsp, 50h
0x180011dd7  pop     r15
0x180011dd9  pop     r14
0x180011ddb  pop     r13
0x180011ddd  pop     r12
0x180011ddf  pop     rdi
0x180011de0  pop     rsi
0x180011de1  pop     rbp
0x180011de2  retn
```
