# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180012308`
- end: `0x180012418`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800121d0`

## callees

- `0x1800106a4`
- `0x180011870`
- `0x180012030`
- `0x180012308`
- `0x1800133e8`
- `0x180017010`

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
  void (*v12)(void *); // rdx
  __int64 v13; // r8
  unsigned int v14; // r9d
  unsigned int v15; // esi
  int v16; // r12d
  unsigned int v17; // r14d
  int v18; // ebp
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-68h]
  _BYTE v22[88]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v23; // [rsp+A0h] [rbp+18h]

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v15 = 1;
  v16 = *v11;
  v17 = v11[1];
  v18 = v11[4];
  v23 = v11[2];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v16 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v17 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v23, v17, v14, v21);
  if ( !v18 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      v12);
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v19, 0, v14, v21);
  }
  if ( v18 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v13) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v13);
  }
  return v15;
}

```

## disassembly

```asm
0x180012308  mov     [rsp+arg_0], rbx
0x18001230d  mov     [rsp+arg_18], r9d
0x180012312  push    rbp
0x180012313  push    rsi
0x180012314  push    rdi
0x180012315  push    r12
0x180012317  push    r13
0x180012319  push    r14
0x18001231b  push    r15
0x18001231d  sub     rsp, 50h
0x180012321  mov     ebx, [rsp+88h+arg_20]
0x180012328  mov     edi, edx
0x18001232a  mov     rdx, rcx
0x18001232d  mov     r13d, r8d
0x180012330  mov     r15, rcx
0x180012333  mov     r8d, ebx
0x180012336  lea     rcx, [rsp+88h+var_58]
0x18001233b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180012340  mov     esi, 1
0x180012345  mov     ecx, [rax+8]
0x180012348  mov     r12d, [rax]
0x18001234b  mov     r14d, [rax+4]
0x18001234f  mov     ebp, [rax+10h]
0x180012352  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180012359  mov     [rsp+88h+arg_10], ecx
0x180012360  test    rax, rax
0x180012363  jz      short loc_18001237D
0x180012365  test    ebx, ebx
0x180012367  jz      short loc_180012371
0x180012369  lea     ecx, [rbx-64h]
0x18001236c  cmp     ecx, 31h ; '1'
0x18001236f  ja      short loc_18001237D
0x180012371  mov     r8d, esi
0x180012374  mov     edx, ebx
0x180012376  mov     ecx, edi
0x180012378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001237d  test    r12d, r12d
0x180012380  jz      short loc_180012393
0x180012382  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180012385  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001238c  mov     edx, edi; unsigned int
0x18001238e  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180012393  test    r14d, r14d
0x180012396  jz      short loc_1800123A9
0x180012398  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18001239f  mov     r8d, r14d; unsigned int
0x1800123a2  mov     ecx, edi; this
0x1800123a4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800123a9  test    ebp, ebp
0x1800123ab  jnz     short loc_1800123B9
0x1800123ad  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800123b4  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800123b9  test    r13d, r13d
0x1800123bc  jz      short loc_1800123D9
0x1800123be  mov     edx, ebx
0x1800123c0  mov     ecx, edi; this
0x1800123c2  bts     edx, 1Fh
0x1800123c6  cmp     [rsp+88h+arg_18], 0
0x1800123ce  cmovz   edx, ebx; unsigned int
0x1800123d1  xor     r8d, r8d; unsigned int
0x1800123d4  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800123d9  test    ebp, ebp
0x1800123db  jnz     short loc_1800123FC
0x1800123dd  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800123e4  test    rax, rax
0x1800123e7  jz      short loc_1800123FE
0x1800123e9  mov     r8b, [rsp+88h+arg_38]
0x1800123f1  mov     edx, ebx
0x1800123f3  mov     ecx, edi
0x1800123f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123fa  jmp     short loc_1800123FE
0x1800123fc  xor     esi, esi
0x1800123fe  mov     rbx, [rsp+88h+arg_0]
0x180012406  mov     eax, esi
0x180012408  add     rsp, 50h
0x18001240c  pop     r15
0x18001240e  pop     r14
0x180012410  pop     r13
0x180012412  pop     r12
0x180012414  pop     rdi
0x180012415  pop     rsi
0x180012416  pop     rbp
0x180012417  retn
```
