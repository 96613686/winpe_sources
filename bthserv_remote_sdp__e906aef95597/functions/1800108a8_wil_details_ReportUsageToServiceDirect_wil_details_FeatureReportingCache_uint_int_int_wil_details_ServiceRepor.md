# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800108a8`
- end: `0x180010a73`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010804`

## callees

- `0x1800106a0`
- `0x1800108a8`
- `0x180012b80`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001099a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001099a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v12; // rax
  __m128i v13; // xmm1
  unsigned int v14; // ebp
  __int64 v15; // r8
  void (__fastcall *v16)(_QWORD, _QWORD, __int64, _QWORD); // rax
  void (__fastcall *v17)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v18; // rdx
  void (__fastcall *v19)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __m128i v21; // [rsp+30h] [rbp-58h]
  __int64 v22; // [rsp+50h] [rbp-38h]
  __int64 v23; // [rsp+58h] [rbp-30h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(&v23, a1, a5, 0);
  v13 = *(__m128i *)v12;
  v21 = *(__m128i *)v12;
  v22 = *(_QWORD *)(v12 + 16);
  v14 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
  {
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
    v13 = v21;
  }
  if ( _mm_cvtsi128_si32(v13) )
  {
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
    v13 = v21;
  }
  v15 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 4));
  if ( (_DWORD)v15 )
  {
    v16 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v16 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v16(a2, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 8)), v15, 0);
    }
  }
  if ( !(_DWORD)v22 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180046510 )
    {
      qword_180046510 = 0;
      v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v17(&qword_180046510, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v18 = a5;
    LODWORD(v18) = a5 | 0x80000000;
    if ( !a4 )
      v18 = a5;
    v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(a2, v18, 0, 0);
    }
  }
  if ( (_DWORD)v22 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v15) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v15);
  }
  return v14;
}

```

## disassembly

```asm
0x1800108a8  mov     rax, rsp
0x1800108ab  mov     [rax+8], rbx
0x1800108af  mov     [rax+10h], rbp
0x1800108b3  mov     [rax+18h], rsi
0x1800108b7  push    rdi
0x1800108b8  push    r14
0x1800108ba  push    r15
0x1800108bc  sub     rsp, 70h
0x1800108c0  mov     r15d, r9d
0x1800108c3  mov     r14d, r8d
0x1800108c6  mov     ebx, edx
0x1800108c8  mov     rsi, rcx
0x1800108cb  mov     edi, [rsp+88h+arg_20]
0x1800108d2  xor     r9d, r9d
0x1800108d5  mov     r8d, edi
0x1800108d8  mov     rdx, rcx
0x1800108db  lea     rcx, [rax-30h]
0x1800108df  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800108e4  movups  xmm1, xmmword ptr [rax]
0x1800108e7  movups  [rsp+88h+var_58], xmm1
0x1800108ec  movsd   xmm0, qword ptr [rax+10h]
0x1800108f1  movsd   [rsp+88h+var_38], xmm0
0x1800108f7  mov     ebp, 1
0x1800108fc  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180010903  test    rax, rax
0x180010906  jz      short loc_180010925
0x180010908  test    edi, edi
0x18001090a  jz      short loc_180010914
0x18001090c  lea     ecx, [rdi-64h]
0x18001090f  cmp     ecx, 31h ; '1'
0x180010912  ja      short loc_180010925
0x180010914  mov     r8d, ebp
0x180010917  mov     edx, edi
0x180010919  mov     ecx, ebx
0x18001091b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010920  movups  xmm1, [rsp+88h+var_58]
0x180010925  movd    eax, xmm1
0x180010929  test    eax, eax
0x18001092b  jz      short loc_180010943
0x18001092d  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x180010930  mov     edx, ebx; unsigned int
0x180010932  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180010939  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001093e  movups  xmm1, [rsp+88h+var_58]
0x180010943  movdqa  xmm0, xmm1
0x180010947  psrldq  xmm0, 4
0x18001094c  movd    r8d, xmm0
0x180010951  test    r8d, r8d
0x180010954  jz      short loc_180010981
0x180010956  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001095d  test    rax, rax
0x180010960  jnz     short loc_18001096E
0x180010962  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180010969  test    rax, rax
0x18001096c  jz      short loc_180010981
0x18001096e  psrldq  xmm1, 8
0x180010973  xor     r9d, r9d
0x180010976  movd    edx, xmm1
0x18001097a  mov     ecx, ebx
0x18001097c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010981  mov     esi, dword ptr [rsp+88h+var_38]
0x180010985  test    esi, esi
0x180010987  jnz     short loc_1800109FB
0x180010989  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001098f  test    eax, eax
0x180010991  jz      short loc_1800109FB
0x180010993  lea     rcx, SRWLock; SRWLock
0x18001099a  call    cs:__imp_AcquireSRWLockExclusive
0x1800109a1  nop     dword ptr [rax+rax+00h]
0x1800109a6  cmp     cs:qword_180046510, 0
0x1800109ae  jnz     short loc_1800109E7
0x1800109b0  and     cs:qword_180046510, 0
0x1800109b8  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800109bf  test    rax, rax
0x1800109c2  jnz     short loc_1800109D0
0x1800109c4  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800109cb  test    rax, rax
0x1800109ce  jz      short loc_1800109E7
0x1800109d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800109d4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800109db  lea     rcx, qword_180046510
0x1800109e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109e7  lea     rcx, SRWLock; SRWLock
0x1800109ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1800109f5  nop     dword ptr [rax+rax+00h]
0x1800109fa  nop
0x1800109fb  test    r14d, r14d
0x1800109fe  jz      short loc_180010A31
0x180010a00  mov     edx, edi
0x180010a02  bts     edx, 1Fh
0x180010a06  test    r15d, r15d
0x180010a09  cmovz   edx, edi
0x180010a0c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180010a13  test    rax, rax
0x180010a16  jnz     short loc_180010A24
0x180010a18  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180010a1f  test    rax, rax
0x180010a22  jz      short loc_180010A31
0x180010a24  xor     r9d, r9d
0x180010a27  xor     r8d, r8d
0x180010a2a  mov     ecx, ebx
0x180010a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a31  test    esi, esi
0x180010a33  jnz     short loc_180010A54
0x180010a35  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180010a3c  test    rax, rax
0x180010a3f  jz      short loc_180010A56
0x180010a41  mov     r8b, [rsp+88h+arg_38]
0x180010a49  mov     edx, edi
0x180010a4b  mov     ecx, ebx
0x180010a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a52  jmp     short loc_180010A56
0x180010a54  xor     ebp, ebp
0x180010a56  mov     eax, ebp
0x180010a58  lea     r11, [rsp+88h+var_18]
0x180010a5d  mov     rbx, [r11+20h]
0x180010a61  mov     rbp, [r11+28h]
0x180010a65  mov     rsi, [r11+30h]
0x180010a69  mov     rsp, r11
0x180010a6c  pop     r15
0x180010a6e  pop     r14
0x180010a70  pop     rdi
0x180010a71  retn
```
