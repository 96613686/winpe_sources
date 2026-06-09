# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001bdcc`
- end: `0x18001bee3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001bd28`

## callees

- `0x18001a334`
- `0x18001b4d0`
- `0x18001bab0`
- `0x18001bdcc`
- `0x18001c13c`
- `0x180025010`

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
0x18001bdcc  mov     [rsp+arg_0], rbx
0x18001bdd1  mov     [rsp+arg_18], r9d
0x18001bdd6  push    rbp
0x18001bdd7  push    rsi
0x18001bdd8  push    rdi
0x18001bdd9  push    r12
0x18001bddb  push    r13
0x18001bddd  push    r14
0x18001bddf  push    r15
0x18001bde1  sub     rsp, 50h
0x18001bde5  mov     ebx, [rsp+88h+arg_20]
0x18001bdec  mov     edi, edx
0x18001bdee  mov     rdx, rcx
0x18001bdf1  mov     r13d, r8d
0x18001bdf4  mov     r15, rcx
0x18001bdf7  mov     r8d, ebx
0x18001bdfa  lea     rcx, [rsp+88h+var_58]
0x18001bdff  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001be04  mov     esi, 1
0x18001be09  mov     ecx, [rax+8]
0x18001be0c  mov     r12d, [rax]
0x18001be0f  mov     r14d, [rax+4]
0x18001be13  mov     ebp, [rax+10h]
0x18001be16  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001be1d  mov     [rsp+88h+arg_10], ecx
0x18001be24  test    rax, rax
0x18001be27  jz      short loc_18001BE41
0x18001be29  test    ebx, ebx
0x18001be2b  jz      short loc_18001BE35
0x18001be2d  lea     ecx, [rbx-64h]
0x18001be30  cmp     ecx, 31h ; '1'
0x18001be33  ja      short loc_18001BE41
0x18001be35  mov     r8d, esi
0x18001be38  mov     edx, ebx
0x18001be3a  mov     ecx, edi
0x18001be3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be41  test    r12d, r12d
0x18001be44  jz      short loc_18001BE57
0x18001be46  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18001be49  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001be50  mov     edx, edi; unsigned int
0x18001be52  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001be57  test    r14d, r14d
0x18001be5a  jz      short loc_18001BE6D
0x18001be5c  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18001be63  mov     r8d, r14d; unsigned int
0x18001be66  mov     ecx, edi; this
0x18001be68  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18001be6d  test    ebp, ebp
0x18001be6f  jnz     short loc_18001BE84
0x18001be71  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18001be78  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001be7f  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18001be84  test    r13d, r13d
0x18001be87  jz      short loc_18001BEA4
0x18001be89  mov     edx, ebx
0x18001be8b  mov     ecx, edi; this
0x18001be8d  bts     edx, 1Fh
0x18001be91  cmp     [rsp+88h+arg_18], 0
0x18001be99  cmovz   edx, ebx; unsigned int
0x18001be9c  xor     r8d, r8d; unsigned int
0x18001be9f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18001bea4  test    ebp, ebp
0x18001bea6  jnz     short loc_18001BEC7
0x18001bea8  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001beaf  test    rax, rax
0x18001beb2  jz      short loc_18001BEC9
0x18001beb4  mov     r8b, [rsp+88h+arg_38]
0x18001bebc  mov     edx, ebx
0x18001bebe  mov     ecx, edi
0x18001bec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bec5  jmp     short loc_18001BEC9
0x18001bec7  xor     esi, esi
0x18001bec9  mov     rbx, [rsp+88h+arg_0]
0x18001bed1  mov     eax, esi
0x18001bed3  add     rsp, 50h
0x18001bed7  pop     r15
0x18001bed9  pop     r14
0x18001bedb  pop     r13
0x18001bedd  pop     r12
0x18001bedf  pop     rdi
0x18001bee0  pop     rsi
0x18001bee1  pop     rbp
0x18001bee2  retn
```
