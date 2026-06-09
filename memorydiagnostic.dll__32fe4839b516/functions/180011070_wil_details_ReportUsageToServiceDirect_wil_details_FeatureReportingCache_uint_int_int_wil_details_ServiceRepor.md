# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180011070`
- end: `0x18001123b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010fcc`

## callees

- `0x18000f574`
- `0x180011070`
- `0x18001a964`
- `0x180024010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180011162`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011162`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800111b6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800111b6`

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
    if ( !qword_180030470 )
    {
      qword_180030470 = 0;
      v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v17(&qword_180030470, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x180011070  mov     rax, rsp
0x180011073  mov     [rax+8], rbx
0x180011077  mov     [rax+10h], rbp
0x18001107b  mov     [rax+18h], rsi
0x18001107f  push    rdi
0x180011080  push    r14
0x180011082  push    r15
0x180011084  sub     rsp, 70h
0x180011088  mov     r15d, r9d
0x18001108b  mov     r14d, r8d
0x18001108e  mov     ebx, edx
0x180011090  mov     rsi, rcx
0x180011093  mov     edi, [rsp+88h+arg_20]
0x18001109a  xor     r9d, r9d
0x18001109d  mov     r8d, edi
0x1800110a0  mov     rdx, rcx
0x1800110a3  lea     rcx, [rax-30h]
0x1800110a7  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800110ac  movups  xmm1, xmmword ptr [rax]
0x1800110af  movups  [rsp+88h+var_58], xmm1
0x1800110b4  movsd   xmm0, qword ptr [rax+10h]
0x1800110b9  movsd   [rsp+88h+var_38], xmm0
0x1800110bf  mov     ebp, 1
0x1800110c4  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800110cb  test    rax, rax
0x1800110ce  jz      short loc_1800110ED
0x1800110d0  test    edi, edi
0x1800110d2  jz      short loc_1800110DC
0x1800110d4  lea     ecx, [rdi-64h]
0x1800110d7  cmp     ecx, 31h ; '1'
0x1800110da  ja      short loc_1800110ED
0x1800110dc  mov     r8d, ebp
0x1800110df  mov     edx, edi
0x1800110e1  mov     ecx, ebx
0x1800110e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e8  movups  xmm1, [rsp+88h+var_58]
0x1800110ed  movd    eax, xmm1
0x1800110f1  test    eax, eax
0x1800110f3  jz      short loc_18001110B
0x1800110f5  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x1800110f8  mov     edx, ebx; unsigned int
0x1800110fa  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180011101  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180011106  movups  xmm1, [rsp+88h+var_58]
0x18001110b  movdqa  xmm0, xmm1
0x18001110f  psrldq  xmm0, 4
0x180011114  movd    r8d, xmm0
0x180011119  test    r8d, r8d
0x18001111c  jz      short loc_180011149
0x18001111e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180011125  test    rax, rax
0x180011128  jnz     short loc_180011136
0x18001112a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180011131  test    rax, rax
0x180011134  jz      short loc_180011149
0x180011136  psrldq  xmm1, 8
0x18001113b  xor     r9d, r9d
0x18001113e  movd    edx, xmm1
0x180011142  mov     ecx, ebx
0x180011144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011149  mov     esi, dword ptr [rsp+88h+var_38]
0x18001114d  test    esi, esi
0x18001114f  jnz     short loc_1800111C3
0x180011151  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011157  test    eax, eax
0x180011159  jz      short loc_1800111C3
0x18001115b  lea     rcx, SRWLock; SRWLock
0x180011162  call    cs:__imp_AcquireSRWLockExclusive
0x180011169  nop     dword ptr [rax+rax+00h]
0x18001116e  cmp     cs:qword_180030470, 0
0x180011176  jnz     short loc_1800111AF
0x180011178  and     cs:qword_180030470, 0
0x180011180  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180011187  test    rax, rax
0x18001118a  jnz     short loc_180011198
0x18001118c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180011193  test    rax, rax
0x180011196  jz      short loc_1800111AF
0x180011198  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001119c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800111a3  lea     rcx, qword_180030470
0x1800111aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111af  lea     rcx, SRWLock; SRWLock
0x1800111b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800111bd  nop     dword ptr [rax+rax+00h]
0x1800111c2  nop
0x1800111c3  test    r14d, r14d
0x1800111c6  jz      short loc_1800111F9
0x1800111c8  mov     edx, edi
0x1800111ca  bts     edx, 1Fh
0x1800111ce  test    r15d, r15d
0x1800111d1  cmovz   edx, edi
0x1800111d4  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800111db  test    rax, rax
0x1800111de  jnz     short loc_1800111EC
0x1800111e0  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800111e7  test    rax, rax
0x1800111ea  jz      short loc_1800111F9
0x1800111ec  xor     r9d, r9d
0x1800111ef  xor     r8d, r8d
0x1800111f2  mov     ecx, ebx
0x1800111f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f9  test    esi, esi
0x1800111fb  jnz     short loc_18001121C
0x1800111fd  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180011204  test    rax, rax
0x180011207  jz      short loc_18001121E
0x180011209  mov     r8b, [rsp+88h+arg_38]
0x180011211  mov     edx, edi
0x180011213  mov     ecx, ebx
0x180011215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001121a  jmp     short loc_18001121E
0x18001121c  xor     ebp, ebp
0x18001121e  mov     eax, ebp
0x180011220  lea     r11, [rsp+88h+var_18]
0x180011225  mov     rbx, [r11+20h]
0x180011229  mov     rbp, [r11+28h]
0x18001122d  mov     rsi, [r11+30h]
0x180011231  mov     rsp, r11
0x180011234  pop     r15
0x180011236  pop     r14
0x180011238  pop     rdi
0x180011239  retn
```
