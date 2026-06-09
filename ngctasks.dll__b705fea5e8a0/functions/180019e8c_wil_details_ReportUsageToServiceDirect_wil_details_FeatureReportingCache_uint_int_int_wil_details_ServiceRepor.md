# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180019e8c`
- end: `0x180019fa3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180019de8`

## callees

- `0x18001805c`
- `0x1800192e0`
- `0x180019e8c`
- `0x18001a858`
- `0x18001b338`
- `0x180022010`

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
0x180019e8c  mov     [rsp+arg_0], rbx
0x180019e91  mov     [rsp+arg_18], r9d
0x180019e96  push    rbp
0x180019e97  push    rsi
0x180019e98  push    rdi
0x180019e99  push    r12
0x180019e9b  push    r13
0x180019e9d  push    r14
0x180019e9f  push    r15
0x180019ea1  sub     rsp, 50h
0x180019ea5  mov     ebx, [rsp+88h+arg_20]
0x180019eac  mov     edi, edx
0x180019eae  mov     rdx, rcx
0x180019eb1  mov     r13d, r8d
0x180019eb4  mov     r15, rcx
0x180019eb7  mov     r8d, ebx
0x180019eba  lea     rcx, [rsp+88h+var_58]
0x180019ebf  call    wil_details_FeatureReporting_RecordUsageInCache
0x180019ec4  mov     esi, 1
0x180019ec9  mov     ecx, [rax+8]
0x180019ecc  mov     r12d, [rax]
0x180019ecf  mov     r14d, [rax+4]
0x180019ed3  mov     ebp, [rax+10h]
0x180019ed6  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180019edd  mov     [rsp+88h+arg_10], ecx
0x180019ee4  test    rax, rax
0x180019ee7  jz      short loc_180019F01
0x180019ee9  test    ebx, ebx
0x180019eeb  jz      short loc_180019EF5
0x180019eed  lea     ecx, [rbx-64h]
0x180019ef0  cmp     ecx, 31h ; '1'
0x180019ef3  ja      short loc_180019F01
0x180019ef5  mov     r8d, esi
0x180019ef8  mov     edx, ebx
0x180019efa  mov     ecx, edi
0x180019efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f01  test    r12d, r12d
0x180019f04  jz      short loc_180019F17
0x180019f06  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180019f09  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180019f10  mov     edx, edi; unsigned int
0x180019f12  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180019f17  test    r14d, r14d
0x180019f1a  jz      short loc_180019F2D
0x180019f1c  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180019f23  mov     r8d, r14d; unsigned int
0x180019f26  mov     ecx, edi; this
0x180019f28  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180019f2d  test    ebp, ebp
0x180019f2f  jnz     short loc_180019F44
0x180019f31  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180019f38  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180019f3f  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180019f44  test    r13d, r13d
0x180019f47  jz      short loc_180019F64
0x180019f49  mov     edx, ebx
0x180019f4b  mov     ecx, edi; this
0x180019f4d  bts     edx, 1Fh
0x180019f51  cmp     [rsp+88h+arg_18], 0
0x180019f59  cmovz   edx, ebx; unsigned int
0x180019f5c  xor     r8d, r8d; unsigned int
0x180019f5f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180019f64  test    ebp, ebp
0x180019f66  jnz     short loc_180019F87
0x180019f68  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180019f6f  test    rax, rax
0x180019f72  jz      short loc_180019F89
0x180019f74  mov     r8b, [rsp+88h+arg_38]
0x180019f7c  mov     edx, ebx
0x180019f7e  mov     ecx, edi
0x180019f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f85  jmp     short loc_180019F89
0x180019f87  xor     esi, esi
0x180019f89  mov     rbx, [rsp+88h+arg_0]
0x180019f91  mov     eax, esi
0x180019f93  add     rsp, 50h
0x180019f97  pop     r15
0x180019f99  pop     r14
0x180019f9b  pop     r13
0x180019f9d  pop     r12
0x180019f9f  pop     rdi
0x180019fa0  pop     rsi
0x180019fa1  pop     rbp
0x180019fa2  retn
```
