# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14001783c`
- end: `0x140017956`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14000e9c4`
- `0x14000fc90`

## callees

- `0x14000d6e4`
- `0x140014d78`
- `0x14001783c`
- `0x140017d50`
- `0x14001858c`
- `0x14001f010`

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

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v21, a1, a5, 0);
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
0x14001783c  mov     [rsp+arg_0], rbx
0x140017841  mov     [rsp+arg_18], r9d
0x140017846  push    rbp
0x140017847  push    rsi
0x140017848  push    rdi
0x140017849  push    r12
0x14001784b  push    r13
0x14001784d  push    r14
0x14001784f  push    r15
0x140017851  sub     rsp, 50h
0x140017855  mov     ebx, [rsp+88h+arg_20]
0x14001785c  mov     edi, edx
0x14001785e  mov     rdx, rcx
0x140017861  mov     r13d, r8d
0x140017864  mov     r15, rcx
0x140017867  xor     r9d, r9d
0x14001786a  lea     rcx, [rsp+88h+var_58]
0x14001786f  mov     r8d, ebx
0x140017872  call    wil_details_FeatureReporting_RecordUsageInCache
0x140017877  mov     esi, 1
0x14001787c  mov     ecx, [rax+8]
0x14001787f  mov     r12d, [rax]
0x140017882  mov     r14d, [rax+4]
0x140017886  mov     ebp, [rax+10h]
0x140017889  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140017890  mov     [rsp+88h+arg_10], ecx
0x140017897  test    rax, rax
0x14001789a  jz      short loc_1400178B4
0x14001789c  test    ebx, ebx
0x14001789e  jz      short loc_1400178A8
0x1400178a0  lea     ecx, [rbx-64h]
0x1400178a3  cmp     ecx, 31h ; '1'
0x1400178a6  ja      short loc_1400178B4
0x1400178a8  mov     r8d, esi
0x1400178ab  mov     edx, ebx
0x1400178ad  mov     ecx, edi
0x1400178af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400178b4  test    r12d, r12d
0x1400178b7  jz      short loc_1400178CA
0x1400178b9  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1400178bc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1400178c3  mov     edx, edi; unsigned int
0x1400178c5  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1400178ca  test    r14d, r14d
0x1400178cd  jz      short loc_1400178E0
0x1400178cf  mov     edx, [rsp+88h+arg_10]; unsigned int
0x1400178d6  mov     r8d, r14d; unsigned int
0x1400178d9  mov     ecx, edi; this
0x1400178db  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1400178e0  test    ebp, ebp
0x1400178e2  jnz     short loc_1400178F7
0x1400178e4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1400178eb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1400178f2  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1400178f7  test    r13d, r13d
0x1400178fa  jz      short loc_140017917
0x1400178fc  mov     edx, ebx
0x1400178fe  mov     ecx, edi; this
0x140017900  bts     edx, 1Fh
0x140017904  cmp     [rsp+88h+arg_18], 0
0x14001790c  cmovz   edx, ebx; unsigned int
0x14001790f  xor     r8d, r8d; unsigned int
0x140017912  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140017917  test    ebp, ebp
0x140017919  jnz     short loc_14001793A
0x14001791b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140017922  test    rax, rax
0x140017925  jz      short loc_14001793C
0x140017927  mov     r8b, [rsp+88h+arg_38]
0x14001792f  mov     edx, ebx
0x140017931  mov     ecx, edi
0x140017933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017938  jmp     short loc_14001793C
0x14001793a  xor     esi, esi
0x14001793c  mov     rbx, [rsp+88h+arg_0]
0x140017944  mov     eax, esi
0x140017946  add     rsp, 50h
0x14001794a  pop     r15
0x14001794c  pop     r14
0x14001794e  pop     r13
0x140017950  pop     r12
0x140017952  pop     rdi
0x140017953  pop     rsi
0x140017954  pop     rbp
0x140017955  retn
```
