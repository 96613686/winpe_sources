# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180009ddc`
- end: `0x180009ee4`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180009d00`

## callees

- `0x18000869c`
- `0x1800092c8`
- `0x180009ddc`
- `0x18000a6d4`
- `0x18000b1e8`
- `0x18001c010`

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
    g_wil_details_RecordSRUMFeatureUsage(39833203, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x25FCE73, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x25FCE73, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(39833203, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x180009ddc  mov     [rsp+arg_18], r9d
0x180009de1  push    rbx
0x180009de2  push    rbp
0x180009de3  push    rsi
0x180009de4  push    rdi
0x180009de5  push    r12
0x180009de7  push    r13
0x180009de9  push    r14
0x180009deb  push    r15
0x180009ded  sub     rsp, 58h
0x180009df1  mov     ebx, [rsp+98h+arg_20]
0x180009df8  mov     r12d, r8d
0x180009dfb  mov     r14, rcx
0x180009dfe  mov     rdx, rcx
0x180009e01  mov     r8d, ebx
0x180009e04  lea     rcx, [rsp+98h+var_68]
0x180009e09  call    wil_details_FeatureReporting_RecordUsageInCache
0x180009e0e  mov     edi, 1
0x180009e13  mov     r15d, [rax]
0x180009e16  mov     ebp, [rax+4]
0x180009e19  mov     r13d, [rax+8]
0x180009e1d  mov     esi, [rax+10h]
0x180009e20  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180009e27  test    rax, rax
0x180009e2a  jz      short loc_180009E47
0x180009e2c  test    ebx, ebx
0x180009e2e  jz      short loc_180009E38
0x180009e30  lea     ecx, [rbx-64h]
0x180009e33  cmp     ecx, 31h ; '1'
0x180009e36  ja      short loc_180009E47
0x180009e38  mov     r8d, edi
0x180009e3b  mov     edx, ebx
0x180009e3d  mov     ecx, 25FCE73h
0x180009e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e47  test    r15d, r15d
0x180009e4a  jz      short loc_180009E5B
0x180009e4c  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180009e4f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180009e56  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180009e5b  test    ebp, ebp
0x180009e5d  jz      short loc_180009E6F
0x180009e5f  mov     r8d, ebp; unsigned int
0x180009e62  mov     edx, r13d; unsigned int
0x180009e65  mov     ecx, 25FCE73h; this
0x180009e6a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180009e6f  test    esi, esi
0x180009e71  jnz     short loc_180009E86
0x180009e73  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180009e7a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180009e81  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180009e86  test    r12d, r12d
0x180009e89  jz      short loc_180009EA9
0x180009e8b  mov     edx, ebx
0x180009e8d  mov     ecx, 25FCE73h; this
0x180009e92  bts     edx, 1Fh
0x180009e96  cmp     [rsp+98h+arg_18], 0
0x180009e9e  cmovz   edx, ebx; unsigned int
0x180009ea1  xor     r8d, r8d; unsigned int
0x180009ea4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180009ea9  test    esi, esi
0x180009eab  jnz     short loc_180009ECF
0x180009ead  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180009eb4  test    rax, rax
0x180009eb7  jz      short loc_180009ED1
0x180009eb9  mov     r8b, [rsp+98h+arg_38]
0x180009ec1  mov     edx, ebx
0x180009ec3  mov     ecx, 25FCE73h
0x180009ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ecd  jmp     short loc_180009ED1
0x180009ecf  xor     edi, edi
0x180009ed1  mov     eax, edi
0x180009ed3  add     rsp, 58h
0x180009ed7  pop     r15
0x180009ed9  pop     r14
0x180009edb  pop     r13
0x180009edd  pop     r12
0x180009edf  pop     rdi
0x180009ee0  pop     rsi
0x180009ee1  pop     rbp
0x180009ee2  pop     rbx
0x180009ee3  retn
```
