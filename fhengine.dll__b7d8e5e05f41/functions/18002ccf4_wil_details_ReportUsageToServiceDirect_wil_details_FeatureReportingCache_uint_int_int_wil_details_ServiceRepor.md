# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18002ccf4`
- end: `0x18002ce0b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002cc50`

## callees

- `0x180028bf0`
- `0x18002bae4`
- `0x18002ccf4`
- `0x18002df58`
- `0x18002ef58`
- `0x180034010`

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
0x18002ccf4  mov     [rsp+arg_0], rbx
0x18002ccf9  mov     [rsp+arg_18], r9d
0x18002ccfe  push    rbp
0x18002ccff  push    rsi
0x18002cd00  push    rdi
0x18002cd01  push    r12
0x18002cd03  push    r13
0x18002cd05  push    r14
0x18002cd07  push    r15
0x18002cd09  sub     rsp, 50h
0x18002cd0d  mov     ebx, [rsp+88h+arg_20]
0x18002cd14  mov     edi, edx
0x18002cd16  mov     rdx, rcx
0x18002cd19  mov     r13d, r8d
0x18002cd1c  mov     r15, rcx
0x18002cd1f  mov     r8d, ebx
0x18002cd22  lea     rcx, [rsp+88h+var_58]
0x18002cd27  call    wil_details_FeatureReporting_RecordUsageInCache
0x18002cd2c  mov     esi, 1
0x18002cd31  mov     ecx, [rax+8]
0x18002cd34  mov     r12d, [rax]
0x18002cd37  mov     r14d, [rax+4]
0x18002cd3b  mov     ebp, [rax+10h]
0x18002cd3e  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18002cd45  mov     [rsp+88h+arg_10], ecx
0x18002cd4c  test    rax, rax
0x18002cd4f  jz      short loc_18002CD69
0x18002cd51  test    ebx, ebx
0x18002cd53  jz      short loc_18002CD5D
0x18002cd55  lea     ecx, [rbx-64h]
0x18002cd58  cmp     ecx, 31h ; '1'
0x18002cd5b  ja      short loc_18002CD69
0x18002cd5d  mov     r8d, esi
0x18002cd60  mov     edx, ebx
0x18002cd62  mov     ecx, edi
0x18002cd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd69  test    r12d, r12d
0x18002cd6c  jz      short loc_18002CD7F
0x18002cd6e  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x18002cd71  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18002cd78  mov     edx, edi; unsigned int
0x18002cd7a  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18002cd7f  test    r14d, r14d
0x18002cd82  jz      short loc_18002CD95
0x18002cd84  mov     edx, [rsp+88h+arg_10]; unsigned int
0x18002cd8b  mov     r8d, r14d; unsigned int
0x18002cd8e  mov     ecx, edi; this
0x18002cd90  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002cd95  test    ebp, ebp
0x18002cd97  jnz     short loc_18002CDAC
0x18002cd99  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18002cda0  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18002cda7  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18002cdac  test    r13d, r13d
0x18002cdaf  jz      short loc_18002CDCC
0x18002cdb1  mov     edx, ebx
0x18002cdb3  mov     ecx, edi; this
0x18002cdb5  bts     edx, 1Fh
0x18002cdb9  cmp     [rsp+88h+arg_18], 0
0x18002cdc1  cmovz   edx, ebx; unsigned int
0x18002cdc4  xor     r8d, r8d; unsigned int
0x18002cdc7  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18002cdcc  test    ebp, ebp
0x18002cdce  jnz     short loc_18002CDEF
0x18002cdd0  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18002cdd7  test    rax, rax
0x18002cdda  jz      short loc_18002CDF1
0x18002cddc  mov     r8b, [rsp+88h+arg_38]
0x18002cde4  mov     edx, ebx
0x18002cde6  mov     ecx, edi
0x18002cde8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cded  jmp     short loc_18002CDF1
0x18002cdef  xor     esi, esi
0x18002cdf1  mov     rbx, [rsp+88h+arg_0]
0x18002cdf9  mov     eax, esi
0x18002cdfb  add     rsp, 50h
0x18002cdff  pop     r15
0x18002ce01  pop     r14
0x18002ce03  pop     r13
0x18002ce05  pop     r12
0x18002ce07  pop     rdi
0x18002ce08  pop     rsi
0x18002ce09  pop     rbp
0x18002ce0a  retn
```
