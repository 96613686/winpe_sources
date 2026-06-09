# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800151a4`
- end: `0x1800152af`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800150cc`

## callees

- `0x18000fd88`
- `0x180012cb4`
- `0x180014844`
- `0x1800151a4`
- `0x180016404`
- `0x180019010`

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

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5, 0);
  v14 = 1;
  v15 = *v10;
  v16 = v10[1];
  v17 = v10[2];
  v18 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(52061724, a5, 1);
  if ( v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v16 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x31A661C, v17, v16, v13, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x31A661C, v19, 0, v13, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(52061724, a5, v12);
  }
  return v14;
}

```

## disassembly

```asm
0x1800151a4  mov     [rsp+arg_18], r9d
0x1800151a9  push    rbx
0x1800151aa  push    rbp
0x1800151ab  push    rsi
0x1800151ac  push    rdi
0x1800151ad  push    r12
0x1800151af  push    r13
0x1800151b1  push    r14
0x1800151b3  push    r15
0x1800151b5  sub     rsp, 58h
0x1800151b9  mov     ebx, [rsp+98h+arg_20]
0x1800151c0  mov     r12d, r8d
0x1800151c3  mov     r14, rcx
0x1800151c6  mov     rdx, rcx
0x1800151c9  mov     r8d, ebx
0x1800151cc  lea     rcx, [rsp+98h+var_68]
0x1800151d1  xor     r9d, r9d
0x1800151d4  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800151d9  mov     edi, 1
0x1800151de  mov     r15d, [rax]
0x1800151e1  mov     ebp, [rax+4]
0x1800151e4  mov     r13d, [rax+8]
0x1800151e8  mov     esi, [rax+10h]
0x1800151eb  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800151f2  test    rax, rax
0x1800151f5  jz      short loc_180015212
0x1800151f7  test    ebx, ebx
0x1800151f9  jz      short loc_180015203
0x1800151fb  lea     ecx, [rbx-64h]
0x1800151fe  cmp     ecx, 31h ; '1'
0x180015201  ja      short loc_180015212
0x180015203  mov     r8d, edi
0x180015206  mov     edx, ebx
0x180015208  mov     ecx, 31A661Ch
0x18001520d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015212  test    r15d, r15d
0x180015215  jz      short loc_180015226
0x180015217  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001521a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180015221  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180015226  test    ebp, ebp
0x180015228  jz      short loc_18001523A
0x18001522a  mov     r8d, ebp; unsigned int
0x18001522d  mov     edx, r13d; unsigned int
0x180015230  mov     ecx, 31A661Ch; this
0x180015235  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18001523a  test    esi, esi
0x18001523c  jnz     short loc_180015251
0x18001523e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180015245  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001524c  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180015251  test    r12d, r12d
0x180015254  jz      short loc_180015274
0x180015256  mov     edx, ebx
0x180015258  mov     ecx, 31A661Ch; this
0x18001525d  bts     edx, 1Fh
0x180015261  cmp     [rsp+98h+arg_18], 0
0x180015269  cmovz   edx, ebx; unsigned int
0x18001526c  xor     r8d, r8d; unsigned int
0x18001526f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180015274  test    esi, esi
0x180015276  jnz     short loc_18001529A
0x180015278  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001527f  test    rax, rax
0x180015282  jz      short loc_18001529C
0x180015284  mov     r8b, [rsp+98h+arg_38]
0x18001528c  mov     edx, ebx
0x18001528e  mov     ecx, 31A661Ch
0x180015293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015298  jmp     short loc_18001529C
0x18001529a  xor     edi, edi
0x18001529c  mov     eax, edi
0x18001529e  add     rsp, 58h
0x1800152a2  pop     r15
0x1800152a4  pop     r14
0x1800152a6  pop     r13
0x1800152a8  pop     r12
0x1800152aa  pop     rdi
0x1800152ab  pop     rsi
0x1800152ac  pop     rbp
0x1800152ad  pop     rbx
0x1800152ae  retn
```
