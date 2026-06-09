# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140009328`
- end: `0x14000943f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140009284`

## callees

- `0x140007644`
- `0x140008670`
- `0x140009328`
- `0x140009c88`
- `0x14000b0b8`
- `0x140018010`

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
0x140009328  mov     [rsp+arg_0], rbx
0x14000932d  mov     [rsp+arg_18], r9d
0x140009332  push    rbp
0x140009333  push    rsi
0x140009334  push    rdi
0x140009335  push    r12
0x140009337  push    r13
0x140009339  push    r14
0x14000933b  push    r15
0x14000933d  sub     rsp, 50h
0x140009341  mov     ebx, [rsp+88h+arg_20]
0x140009348  mov     edi, edx
0x14000934a  mov     rdx, rcx
0x14000934d  mov     r13d, r8d
0x140009350  mov     r15, rcx
0x140009353  mov     r8d, ebx
0x140009356  lea     rcx, [rsp+88h+var_58]
0x14000935b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140009360  mov     esi, 1
0x140009365  mov     ecx, [rax+8]
0x140009368  mov     r12d, [rax]
0x14000936b  mov     r14d, [rax+4]
0x14000936f  mov     ebp, [rax+10h]
0x140009372  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140009379  mov     [rsp+88h+arg_10], ecx
0x140009380  test    rax, rax
0x140009383  jz      short loc_14000939D
0x140009385  test    ebx, ebx
0x140009387  jz      short loc_140009391
0x140009389  lea     ecx, [rbx-64h]
0x14000938c  cmp     ecx, 31h ; '1'
0x14000938f  ja      short loc_14000939D
0x140009391  mov     r8d, esi
0x140009394  mov     edx, ebx
0x140009396  mov     ecx, edi
0x140009398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000939d  test    r12d, r12d
0x1400093a0  jz      short loc_1400093B3
0x1400093a2  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1400093a5  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1400093ac  mov     edx, edi; unsigned int
0x1400093ae  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1400093b3  test    r14d, r14d
0x1400093b6  jz      short loc_1400093C9
0x1400093b8  mov     edx, [rsp+88h+arg_10]; unsigned int
0x1400093bf  mov     r8d, r14d; unsigned int
0x1400093c2  mov     ecx, edi; this
0x1400093c4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1400093c9  test    ebp, ebp
0x1400093cb  jnz     short loc_1400093E0
0x1400093cd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1400093d4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1400093db  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1400093e0  test    r13d, r13d
0x1400093e3  jz      short loc_140009400
0x1400093e5  mov     edx, ebx
0x1400093e7  mov     ecx, edi; this
0x1400093e9  bts     edx, 1Fh
0x1400093ed  cmp     [rsp+88h+arg_18], 0
0x1400093f5  cmovz   edx, ebx; unsigned int
0x1400093f8  xor     r8d, r8d; unsigned int
0x1400093fb  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140009400  test    ebp, ebp
0x140009402  jnz     short loc_140009423
0x140009404  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000940b  test    rax, rax
0x14000940e  jz      short loc_140009425
0x140009410  mov     r8b, [rsp+88h+arg_38]
0x140009418  mov     edx, ebx
0x14000941a  mov     ecx, edi
0x14000941c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009421  jmp     short loc_140009425
0x140009423  xor     esi, esi
0x140009425  mov     rbx, [rsp+88h+arg_0]
0x14000942d  mov     eax, esi
0x14000942f  add     rsp, 50h
0x140009433  pop     r15
0x140009435  pop     r14
0x140009437  pop     r13
0x140009439  pop     r12
0x14000943b  pop     rdi
0x14000943c  pop     rsi
0x14000943d  pop     rbp
0x14000943e  retn
```
