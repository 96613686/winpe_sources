# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001501c`
- end: `0x180015124`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180014f44`

## callees

- `0x1800133ac`
- `0x180014394`
- `0x18001501c`
- `0x180015c34`
- `0x180017a78`
- `0x180020010`

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
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(46832940, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x2CA9D2C, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x2CA9D2C, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(46832940, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x18001501c  mov     [rsp+arg_18], r9d
0x180015021  push    rbx
0x180015022  push    rbp
0x180015023  push    rsi
0x180015024  push    rdi
0x180015025  push    r12
0x180015027  push    r13
0x180015029  push    r14
0x18001502b  push    r15
0x18001502d  sub     rsp, 58h
0x180015031  mov     ebx, [rsp+98h+arg_20]
0x180015038  mov     r12d, r8d
0x18001503b  mov     r14, rcx
0x18001503e  mov     rdx, rcx
0x180015041  mov     r8d, ebx
0x180015044  lea     rcx, [rsp+98h+var_68]
0x180015049  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001504e  mov     edi, 1
0x180015053  mov     r15d, [rax]
0x180015056  mov     ebp, [rax+4]
0x180015059  mov     r13d, [rax+8]
0x18001505d  mov     esi, [rax+10h]
0x180015060  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180015067  test    rax, rax
0x18001506a  jz      short loc_180015087
0x18001506c  test    ebx, ebx
0x18001506e  jz      short loc_180015078
0x180015070  lea     ecx, [rbx-64h]
0x180015073  cmp     ecx, 31h ; '1'
0x180015076  ja      short loc_180015087
0x180015078  mov     r8d, edi
0x18001507b  mov     edx, ebx
0x18001507d  mov     ecx, 2CA9D2Ch
0x180015082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015087  test    r15d, r15d
0x18001508a  jz      short loc_18001509B
0x18001508c  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001508f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180015096  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001509b  test    ebp, ebp
0x18001509d  jz      short loc_1800150AF
0x18001509f  mov     r8d, ebp; unsigned int
0x1800150a2  mov     edx, r13d; unsigned int
0x1800150a5  mov     ecx, 2CA9D2Ch; this
0x1800150aa  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800150af  test    esi, esi
0x1800150b1  jnz     short loc_1800150C6
0x1800150b3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800150ba  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800150c1  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800150c6  test    r12d, r12d
0x1800150c9  jz      short loc_1800150E9
0x1800150cb  mov     edx, ebx
0x1800150cd  mov     ecx, 2CA9D2Ch; this
0x1800150d2  bts     edx, 1Fh
0x1800150d6  cmp     [rsp+98h+arg_18], 0
0x1800150de  cmovz   edx, ebx; unsigned int
0x1800150e1  xor     r8d, r8d; unsigned int
0x1800150e4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800150e9  test    esi, esi
0x1800150eb  jnz     short loc_18001510F
0x1800150ed  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800150f4  test    rax, rax
0x1800150f7  jz      short loc_180015111
0x1800150f9  mov     r8b, [rsp+98h+arg_38]
0x180015101  mov     edx, ebx
0x180015103  mov     ecx, 2CA9D2Ch
0x180015108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001510d  jmp     short loc_180015111
0x18001510f  xor     edi, edi
0x180015111  mov     eax, edi
0x180015113  add     rsp, 58h
0x180015117  pop     r15
0x180015119  pop     r14
0x18001511b  pop     r13
0x18001511d  pop     r12
0x18001511f  pop     rdi
0x180015120  pop     rsi
0x180015121  pop     rbp
0x180015122  pop     rbx
0x180015123  retn
```
