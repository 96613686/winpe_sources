# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140012ee4`
- end: `0x140012ffb`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140012e34`

## callees

- `0x14000ac34`
- `0x1400103e4`
- `0x1400129d0`
- `0x140012ee4`
- `0x1400141f4`
- `0x140027010`

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
0x140012ee4  mov     [rsp+arg_0], rbx
0x140012ee9  mov     [rsp+arg_18], r9d
0x140012eee  push    rbp
0x140012eef  push    rsi
0x140012ef0  push    rdi
0x140012ef1  push    r12
0x140012ef3  push    r13
0x140012ef5  push    r14
0x140012ef7  push    r15
0x140012ef9  sub     rsp, 50h
0x140012efd  mov     ebx, [rsp+88h+arg_20]
0x140012f04  mov     edi, edx
0x140012f06  mov     rdx, rcx
0x140012f09  mov     r13d, r8d
0x140012f0c  mov     r15, rcx
0x140012f0f  mov     r8d, ebx
0x140012f12  lea     rcx, [rsp+88h+var_58]
0x140012f17  call    wil_details_FeatureReporting_RecordUsageInCache
0x140012f1c  mov     esi, 1
0x140012f21  mov     ecx, [rax+8]
0x140012f24  mov     r12d, [rax]
0x140012f27  mov     r14d, [rax+4]
0x140012f2b  mov     ebp, [rax+10h]
0x140012f2e  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x140012f35  mov     [rsp+88h+arg_10], ecx
0x140012f3c  test    rax, rax
0x140012f3f  jz      short loc_140012F59
0x140012f41  test    ebx, ebx
0x140012f43  jz      short loc_140012F4D
0x140012f45  lea     ecx, [rbx-64h]
0x140012f48  cmp     ecx, 31h ; '1'
0x140012f4b  ja      short loc_140012F59
0x140012f4d  mov     r8d, esi
0x140012f50  mov     edx, ebx
0x140012f52  mov     ecx, edi
0x140012f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f59  test    r12d, r12d
0x140012f5c  jz      short loc_140012F6F
0x140012f5e  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x140012f61  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x140012f68  mov     edx, edi; unsigned int
0x140012f6a  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x140012f6f  test    r14d, r14d
0x140012f72  jz      short loc_140012F85
0x140012f74  mov     edx, [rsp+88h+arg_10]; unsigned int
0x140012f7b  mov     r8d, r14d; unsigned int
0x140012f7e  mov     ecx, edi; this
0x140012f80  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140012f85  test    ebp, ebp
0x140012f87  jnz     short loc_140012F9C
0x140012f89  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x140012f90  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x140012f97  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x140012f9c  test    r13d, r13d
0x140012f9f  jz      short loc_140012FBC
0x140012fa1  mov     edx, ebx
0x140012fa3  mov     ecx, edi; this
0x140012fa5  bts     edx, 1Fh
0x140012fa9  cmp     [rsp+88h+arg_18], 0
0x140012fb1  cmovz   edx, ebx; unsigned int
0x140012fb4  xor     r8d, r8d; unsigned int
0x140012fb7  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140012fbc  test    ebp, ebp
0x140012fbe  jnz     short loc_140012FDF
0x140012fc0  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140012fc7  test    rax, rax
0x140012fca  jz      short loc_140012FE1
0x140012fcc  mov     r8b, [rsp+88h+arg_38]
0x140012fd4  mov     edx, ebx
0x140012fd6  mov     ecx, edi
0x140012fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fdd  jmp     short loc_140012FE1
0x140012fdf  xor     esi, esi
0x140012fe1  mov     rbx, [rsp+88h+arg_0]
0x140012fe9  mov     eax, esi
0x140012feb  add     rsp, 50h
0x140012fef  pop     r15
0x140012ff1  pop     r14
0x140012ff3  pop     r13
0x140012ff5  pop     r12
0x140012ff7  pop     rdi
0x140012ff8  pop     rsi
0x140012ff9  pop     rbp
0x140012ffa  retn
```
