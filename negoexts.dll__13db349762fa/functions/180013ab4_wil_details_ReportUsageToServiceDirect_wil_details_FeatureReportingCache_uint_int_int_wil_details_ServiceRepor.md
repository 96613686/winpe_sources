# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180013ab4`
- end: `0x180013bcb`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001397c`

## callees

- `0x1800111ac`
- `0x180012fe0`
- `0x180013ab4`
- `0x180014dc8`
- `0x180016458`
- `0x180020010`

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
0x180013ab4  mov     [rsp+arg_0], rbx
0x180013ab9  mov     [rsp+arg_18], r9d
0x180013abe  push    rbp
0x180013abf  push    rsi
0x180013ac0  push    rdi
0x180013ac1  push    r12
0x180013ac3  push    r13
0x180013ac5  push    r14
0x180013ac7  push    r15
0x180013ac9  sub     rsp, 50h
0x180013acd  mov     ebx, [rsp+88h+arg_20]
0x180013ad4  mov     edi, edx
0x180013ad6  mov     rdx, rcx
0x180013ad9  mov     r13d, r8d
0x180013adc  mov     r15, rcx
0x180013adf  mov     r8d, ebx
0x180013ae2  lea     rcx, [rsp+88h+var_58]
0x180013ae7  call    wil_details_FeatureReporting_RecordUsageInCache
0x180013aec  mov     esi, 1
0x180013af1  mov     ecx, [rax+8]
0x180013af4  mov     r12d, [rax]
0x180013af7  mov     r14d, [rax+4]
0x180013afb  mov     ebp, [rax+10h]
0x180013afe  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180013b05  mov     [rsp+88h+arg_10], ecx
0x180013b0c  test    rax, rax
0x180013b0f  jz      short loc_180013B29
0x180013b11  test    ebx, ebx
0x180013b13  jz      short loc_180013B1D
0x180013b15  lea     ecx, [rbx-64h]
0x180013b18  cmp     ecx, 31h ; '1'
0x180013b1b  ja      short loc_180013B29
0x180013b1d  mov     r8d, esi
0x180013b20  mov     edx, ebx
0x180013b22  mov     ecx, edi
0x180013b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b29  test    r12d, r12d
0x180013b2c  jz      short loc_180013B3F
0x180013b2e  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180013b31  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180013b38  mov     edx, edi; unsigned int
0x180013b3a  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180013b3f  test    r14d, r14d
0x180013b42  jz      short loc_180013B55
0x180013b44  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180013b4b  mov     r8d, r14d; unsigned int
0x180013b4e  mov     ecx, edi; this
0x180013b50  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180013b55  test    ebp, ebp
0x180013b57  jnz     short loc_180013B6C
0x180013b59  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180013b60  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180013b67  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180013b6c  test    r13d, r13d
0x180013b6f  jz      short loc_180013B8C
0x180013b71  mov     edx, ebx
0x180013b73  mov     ecx, edi; this
0x180013b75  bts     edx, 1Fh
0x180013b79  cmp     [rsp+88h+arg_18], 0
0x180013b81  cmovz   edx, ebx; unsigned int
0x180013b84  xor     r8d, r8d; unsigned int
0x180013b87  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180013b8c  test    ebp, ebp
0x180013b8e  jnz     short loc_180013BAF
0x180013b90  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180013b97  test    rax, rax
0x180013b9a  jz      short loc_180013BB1
0x180013b9c  mov     r8b, [rsp+88h+arg_38]
0x180013ba4  mov     edx, ebx
0x180013ba6  mov     ecx, edi
0x180013ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bad  jmp     short loc_180013BB1
0x180013baf  xor     esi, esi
0x180013bb1  mov     rbx, [rsp+88h+arg_0]
0x180013bb9  mov     eax, esi
0x180013bbb  add     rsp, 50h
0x180013bbf  pop     r15
0x180013bc1  pop     r14
0x180013bc3  pop     r13
0x180013bc5  pop     r12
0x180013bc7  pop     rdi
0x180013bc8  pop     rsi
0x180013bc9  pop     rbp
0x180013bca  retn
```
