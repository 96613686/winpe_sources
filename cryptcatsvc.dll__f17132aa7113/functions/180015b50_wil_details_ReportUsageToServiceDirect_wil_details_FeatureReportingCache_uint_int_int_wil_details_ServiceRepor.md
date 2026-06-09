# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180015b50`
- end: `0x180015c67`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180015aac`

## callees

- `0x180011b24`
- `0x180014b04`
- `0x1800157d8`
- `0x180015b50`
- `0x180016e38`
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
0x180015b50  mov     [rsp+arg_0], rbx
0x180015b55  mov     [rsp+arg_18], r9d
0x180015b5a  push    rbp
0x180015b5b  push    rsi
0x180015b5c  push    rdi
0x180015b5d  push    r12
0x180015b5f  push    r13
0x180015b61  push    r14
0x180015b63  push    r15
0x180015b65  sub     rsp, 50h
0x180015b69  mov     ebx, [rsp+88h+arg_20]
0x180015b70  mov     edi, edx
0x180015b72  mov     rdx, rcx
0x180015b75  mov     r13d, r8d
0x180015b78  mov     r15, rcx
0x180015b7b  mov     r8d, ebx
0x180015b7e  lea     rcx, [rsp+88h+var_58]
0x180015b83  call    wil_details_FeatureReporting_RecordUsageInCache
0x180015b88  mov     esi, 1
0x180015b8d  mov     ecx, [rax+8]
0x180015b90  mov     r12d, [rax]
0x180015b93  mov     r14d, [rax+4]
0x180015b97  mov     ebp, [rax+10h]
0x180015b9a  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180015ba1  mov     [rsp+88h+arg_10], ecx
0x180015ba8  test    rax, rax
0x180015bab  jz      short loc_180015BC5
0x180015bad  test    ebx, ebx
0x180015baf  jz      short loc_180015BB9
0x180015bb1  lea     ecx, [rbx-64h]
0x180015bb4  cmp     ecx, 31h ; '1'
0x180015bb7  ja      short loc_180015BC5
0x180015bb9  mov     r8d, esi
0x180015bbc  mov     edx, ebx
0x180015bbe  mov     ecx, edi
0x180015bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc5  test    r12d, r12d
0x180015bc8  jz      short loc_180015BDB
0x180015bca  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x180015bcd  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180015bd4  mov     edx, edi; unsigned int
0x180015bd6  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180015bdb  test    r14d, r14d
0x180015bde  jz      short loc_180015BF1
0x180015be0  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180015be7  mov     r8d, r14d; unsigned int
0x180015bea  mov     ecx, edi; this
0x180015bec  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180015bf1  test    ebp, ebp
0x180015bf3  jnz     short loc_180015C08
0x180015bf5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180015bfc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180015c03  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180015c08  test    r13d, r13d
0x180015c0b  jz      short loc_180015C28
0x180015c0d  mov     edx, ebx
0x180015c0f  mov     ecx, edi; this
0x180015c11  bts     edx, 1Fh
0x180015c15  cmp     [rsp+88h+arg_18], 0
0x180015c1d  cmovz   edx, ebx; unsigned int
0x180015c20  xor     r8d, r8d; unsigned int
0x180015c23  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180015c28  test    ebp, ebp
0x180015c2a  jnz     short loc_180015C4B
0x180015c2c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180015c33  test    rax, rax
0x180015c36  jz      short loc_180015C4D
0x180015c38  mov     r8b, [rsp+88h+arg_38]
0x180015c40  mov     edx, ebx
0x180015c42  mov     ecx, edi
0x180015c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c49  jmp     short loc_180015C4D
0x180015c4b  xor     esi, esi
0x180015c4d  mov     rbx, [rsp+88h+arg_0]
0x180015c55  mov     eax, esi
0x180015c57  add     rsp, 50h
0x180015c5b  pop     r15
0x180015c5d  pop     r14
0x180015c5f  pop     r13
0x180015c61  pop     r12
0x180015c63  pop     rdi
0x180015c64  pop     rsi
0x180015c65  pop     rbp
0x180015c66  retn
```
