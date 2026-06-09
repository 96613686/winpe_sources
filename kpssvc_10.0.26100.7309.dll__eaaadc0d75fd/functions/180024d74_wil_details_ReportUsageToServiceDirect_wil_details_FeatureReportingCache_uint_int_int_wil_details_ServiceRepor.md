# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180024d74`
- end: `0x180024f3f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180024c98`

## callees

- `0x18002372c`
- `0x180024d74`
- `0x1800270e4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024eba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024eba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e66`

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
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // esi
  __m128i v14; // xmm1
  __int64 v15; // xmm0_8
  __int64 v16; // r8
  void (__fastcall *v17)(__int64, _QWORD, __int64, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v19)(__int64, __int64, _QWORD, _QWORD); // rax
  __int64 v20; // rdx
  __m128i v22; // [rsp+30h] [rbp-58h]
  __int64 v23; // [rsp+58h] [rbp-30h] BYREF

  v11 = wil_details_FeatureReporting_RecordUsageInCache(&v23, a1, a5);
  v13 = 1;
  v14 = *(__m128i *)v11;
  v15 = *(_QWORD *)(v11 + 16);
  v22 = *(__m128i *)v11;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(55623657, a5, 1);
  if ( _mm_cvtsi128_si32(v14) )
  {
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v12,
      a1);
    v14 = v22;
  }
  v16 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v14, 4));
  if ( (_DWORD)v16 )
  {
    v17 = (void (__fastcall *)(__int64, _QWORD, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(__int64, _QWORD, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(55623657, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v14, 8)), v16, 0);
    }
  }
  if ( !(_DWORD)v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18003A370 )
    {
      qword_18003A370 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18003A370, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(55623657, v20, 0, 0);
    }
  }
  if ( (_DWORD)v15 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v16) = a8;
    g_wil_details_realtimeFeatureUsageHook(55623657, a5, v16);
  }
  return v13;
}

```

## disassembly

```asm
0x180024d74  mov     rax, rsp
0x180024d77  mov     [rax+8], rbx
0x180024d7b  mov     [rax+10h], rbp
0x180024d7f  mov     [rax+18h], rsi
0x180024d83  push    rdi
0x180024d84  push    r12
0x180024d86  push    r14
0x180024d88  sub     rsp, 70h
0x180024d8c  mov     ebx, [rsp+88h+arg_20]
0x180024d93  mov     ebp, r8d
0x180024d96  mov     rdi, rcx
0x180024d99  mov     rdx, rcx
0x180024d9c  mov     r8d, ebx
0x180024d9f  lea     rcx, [rax-30h]
0x180024da3  mov     r14d, r9d
0x180024da6  call    wil_details_FeatureReporting_RecordUsageInCache
0x180024dab  mov     esi, 1
0x180024db0  mov     r12d, 350BFE9h
0x180024db6  movups  xmm1, xmmword ptr [rax]
0x180024db9  movsd   xmm0, qword ptr [rax+10h]
0x180024dbe  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180024dc5  movsd   [rsp+88h+var_38], xmm0
0x180024dcb  movups  [rsp+88h+var_58], xmm1
0x180024dd0  test    rax, rax
0x180024dd3  jz      short loc_180024DF3
0x180024dd5  test    ebx, ebx
0x180024dd7  jz      short loc_180024DE1
0x180024dd9  lea     ecx, [rbx-64h]
0x180024ddc  cmp     ecx, 31h ; '1'
0x180024ddf  ja      short loc_180024DF3
0x180024de1  mov     r8d, esi
0x180024de4  mov     edx, ebx
0x180024de6  mov     ecx, r12d
0x180024de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dee  movups  xmm1, [rsp+88h+var_58]
0x180024df3  movd    eax, xmm1
0x180024df7  test    eax, eax
0x180024df9  jz      short loc_180024E0F
0x180024dfb  mov     r8, rdi; struct wil_details_FeatureReportingCache *
0x180024dfe  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180024e05  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180024e0a  movups  xmm1, [rsp+88h+var_58]
0x180024e0f  movdqa  xmm0, xmm1
0x180024e13  psrldq  xmm0, 4
0x180024e18  movd    r8d, xmm0
0x180024e1d  test    r8d, r8d
0x180024e20  jz      short loc_180024E4E
0x180024e22  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180024e29  test    rax, rax
0x180024e2c  jnz     short loc_180024E3A
0x180024e2e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180024e35  test    rax, rax
0x180024e38  jz      short loc_180024E4E
0x180024e3a  psrldq  xmm1, 8
0x180024e3f  xor     r9d, r9d
0x180024e42  movd    edx, xmm1
0x180024e46  mov     ecx, r12d
0x180024e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e4e  mov     edi, dword ptr [rsp+88h+var_38]
0x180024e52  test    edi, edi
0x180024e54  jnz     short loc_180024EC6
0x180024e56  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, dil; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180024e5d  jz      short loc_180024EC6
0x180024e5f  lea     rcx, SRWLock; SRWLock
0x180024e66  call    cs:__imp_AcquireSRWLockExclusive
0x180024e6d  nop     dword ptr [rax+rax+00h]
0x180024e72  cmp     cs:qword_18003A370, 0
0x180024e7a  jnz     short loc_180024EB3
0x180024e7c  and     cs:qword_18003A370, 0
0x180024e84  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180024e8b  test    rax, rax
0x180024e8e  jnz     short loc_180024E9C
0x180024e90  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180024e97  test    rax, rax
0x180024e9a  jz      short loc_180024EB3
0x180024e9c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024ea0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180024ea7  lea     rcx, qword_18003A370
0x180024eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eb3  lea     rcx, SRWLock; SRWLock
0x180024eba  call    cs:__imp_ReleaseSRWLockExclusive
0x180024ec1  nop     dword ptr [rax+rax+00h]
0x180024ec6  test    ebp, ebp
0x180024ec8  jz      short loc_180024EFC
0x180024eca  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180024ed1  mov     edx, ebx
0x180024ed3  bts     edx, 1Fh
0x180024ed7  test    r14d, r14d
0x180024eda  cmovz   edx, ebx
0x180024edd  test    rax, rax
0x180024ee0  jnz     short loc_180024EEE
0x180024ee2  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180024ee9  test    rax, rax
0x180024eec  jz      short loc_180024EFC
0x180024eee  xor     r9d, r9d
0x180024ef1  xor     r8d, r8d
0x180024ef4  mov     ecx, r12d
0x180024ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024efc  test    edi, edi
0x180024efe  jnz     short loc_180024F20
0x180024f00  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180024f07  test    rax, rax
0x180024f0a  jz      short loc_180024F22
0x180024f0c  mov     r8b, [rsp+88h+arg_38]
0x180024f14  mov     edx, ebx
0x180024f16  mov     ecx, r12d
0x180024f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f1e  jmp     short loc_180024F22
0x180024f20  xor     esi, esi
0x180024f22  lea     r11, [rsp+88h+var_18]
0x180024f27  mov     eax, esi
0x180024f29  mov     rbx, [r11+20h]
0x180024f2d  mov     rbp, [r11+28h]
0x180024f31  mov     rsi, [r11+30h]
0x180024f35  mov     rsp, r11
0x180024f38  pop     r14
0x180024f3a  pop     r12
0x180024f3c  pop     rdi
0x180024f3d  retn
```
