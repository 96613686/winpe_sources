# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18003d114`
- end: `0x18003d22b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18003cfdc`

## callees

- `0x18003b3d0`
- `0x18003cbec`
- `0x18003d114`
- `0x18003d90c`
- `0x18003df14`
- `0x180070010`

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
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
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
0x18003d114  mov     [rsp+arg_0], rbx
0x18003d119  mov     [rsp+arg_18], r9d
0x18003d11e  push    rbp
0x18003d11f  push    rsi
0x18003d120  push    rdi
0x18003d121  push    r12
0x18003d123  push    r13
0x18003d125  push    r14
0x18003d127  push    r15
0x18003d129  sub     rsp, 50h
0x18003d12d  mov     ebx, [rsp+88h+arg_20]
0x18003d134  mov     edi, edx
0x18003d136  mov     rdx, rcx
0x18003d139  mov     r13d, r8d
0x18003d13c  mov     r15, rcx
0x18003d13f  mov     r8d, ebx
0x18003d142  lea     rcx, [rsp+88h+var_58]
0x18003d147  call    wil_details_FeatureReporting_RecordUsageInCache
0x18003d14c  mov     esi, 1
0x18003d151  mov     ecx, [rax+8]
0x18003d154  mov     r12d, [rax]
0x18003d157  mov     r14d, [rax+4]
0x18003d15b  mov     ebp, [rax+10h]
0x18003d15e  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18003d165  mov     [rsp+88h+arg_10], ecx
0x18003d16c  test    rax, rax
0x18003d16f  jz      short loc_18003D189
0x18003d171  test    ebx, ebx
0x18003d173  jz      short loc_18003D17D
0x18003d175  lea     ecx, [rbx-64h]
0x18003d178  cmp     ecx, 31h ; '1'
0x18003d17b  ja      short loc_18003D189
0x18003d17d  mov     r8d, esi
0x18003d180  mov     edx, ebx
0x18003d182  mov     ecx, edi
0x18003d184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d189  test    r12d, r12d
0x18003d18c  jz      short loc_18003D19F
0x18003d18e  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18003d191  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18003d198  mov     edx, edi; unsigned int
0x18003d19a  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18003d19f  test    r14d, r14d
0x18003d1a2  jz      short loc_18003D1B5
0x18003d1a4  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18003d1ab  mov     r8d, r14d; unsigned int
0x18003d1ae  mov     ecx, edi; this
0x18003d1b0  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18003d1b5  test    ebp, ebp
0x18003d1b7  jnz     short loc_18003D1CC
0x18003d1b9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18003d1c0  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18003d1c7  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18003d1cc  test    r13d, r13d
0x18003d1cf  jz      short loc_18003D1EC
0x18003d1d1  mov     edx, ebx
0x18003d1d3  mov     ecx, edi; this
0x18003d1d5  bts     edx, 1Fh
0x18003d1d9  cmp     [rsp+88h+arg_18], 0
0x18003d1e1  cmovz   edx, ebx; unsigned int
0x18003d1e4  xor     r8d, r8d; unsigned int
0x18003d1e7  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18003d1ec  test    ebp, ebp
0x18003d1ee  jnz     short loc_18003D20F
0x18003d1f0  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18003d1f7  test    rax, rax
0x18003d1fa  jz      short loc_18003D211
0x18003d1fc  mov     r8b, [rsp+88h+arg_38]
0x18003d204  mov     edx, ebx
0x18003d206  mov     ecx, edi
0x18003d208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d20d  jmp     short loc_18003D211
0x18003d20f  xor     esi, esi
0x18003d211  mov     rbx, [rsp+88h+arg_0]
0x18003d219  mov     eax, esi
0x18003d21b  add     rsp, 50h
0x18003d21f  pop     r15
0x18003d221  pop     r14
0x18003d223  pop     r13
0x18003d225  pop     r12
0x18003d227  pop     rdi
0x18003d228  pop     rsi
0x18003d229  pop     rbp
0x18003d22a  retn
```
