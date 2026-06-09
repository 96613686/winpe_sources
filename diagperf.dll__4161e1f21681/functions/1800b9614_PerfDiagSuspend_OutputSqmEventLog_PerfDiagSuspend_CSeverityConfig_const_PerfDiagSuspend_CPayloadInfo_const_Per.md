# PerfDiagSuspend::OutputSqmEventLog(PerfDiagSuspend::CSeverityConfig const &,PerfDiagSuspend::CPayloadInfo const &,PerfDiagSuspend::CPayloadDegradation const &)

- ea: `0x1800b9614`
- end: `0x1800b9ad0`
- name: `?OutputSqmEventLog@PerfDiagSuspend@@YAJAEBVCSeverityConfig@1@AEBUCPayloadInfo@1@AEBUCPayloadDegradation@1@@Z`
- size: `1212`
- prototype: `__int64 __fastcall(PerfDiagSuspend *__hidden this, const struct PerfDiagSuspend::CSeverityConfig *, const struct PerfDiagSuspend::CPayloadInfo *, const struct PerfDiagSuspend::CPayloadDegradation *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x1800b94a4`

## callees

- `0x180039814`
- `0x18004311c`
- `0x1800441b4`
- `0x1800b1f74`
- `0x1800b1fe8`
- `0x1800b2490`
- `0x1800b6e98`
- `0x1800b70b4`
- `0x1800b72f4`
- `0x1800b89d0`
- `0x1800b93c4`
- `0x1800b9614`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800b9671`
- `ntdll!EtwEventActivityIdControl` at `0x1800b9671`
- `ntdll!EtwEventUnregister` at `0x1800b96e2`
- `ntdll!EtwEventUnregister` at `0x1800b974f`
- `ntdll!EtwEventUnregister` at `0x1800b97a1`
- `ntdll!EtwEventUnregister` at `0x1800b97f3`
- `ntdll!EtwEventUnregister` at `0x1800b9830`
- `ntdll!EtwEventUnregister` at `0x1800b986d`
- `ntdll!EtwEventUnregister` at `0x1800b98ad`
- `ntdll!EtwEventUnregister` at `0x1800b98ed`
- `ntdll!EtwEventUnregister` at `0x1800b992d`
- `ntdll!EtwEventUnregister` at `0x1800b996d`
- `ntdll!EtwEventUnregister` at `0x1800b99ad`
- `ntdll!EtwEventUnregister` at `0x1800b99ed`
- `ntdll!EtwEventUnregister` at `0x1800b9a2d`
- `ntdll!EtwEventUnregister` at `0x1800b9aa4`
- `ntdll!EtwEventUnregister` at `0x1800b96e2`
- `ntdll!EtwEventUnregister` at `0x1800b974f`
- `ntdll!EtwEventUnregister` at `0x1800b97a1`
- `ntdll!EtwEventUnregister` at `0x1800b97f3`
- `ntdll!EtwEventUnregister` at `0x1800b9830`
- `ntdll!EtwEventUnregister` at `0x1800b986d`
- `ntdll!EtwEventUnregister` at `0x1800b98ad`
- `ntdll!EtwEventUnregister` at `0x1800b98ed`
- `ntdll!EtwEventUnregister` at `0x1800b992d`
- `ntdll!EtwEventUnregister` at `0x1800b996d`
- `ntdll!EtwEventUnregister` at `0x1800b99ad`
- `ntdll!EtwEventUnregister` at `0x1800b99ed`
- `ntdll!EtwEventUnregister` at `0x1800b9a2d`
- `ntdll!EtwEventUnregister` at `0x1800b9aa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall PerfDiagSuspend::OutputSqmEventLog(
        PerfDiagSuspend *this,
        struct _GUID *a2,
        const struct PerfDiagSuspend::CPayloadInfo *a3,
        const struct PerfDiagSuspend::CPayloadDegradation *a4)
{
  const struct PerfDiagSuspend::CSeverityConfig *v7; // r8
  int v8; // ebx
  unsigned int v9; // ecx
  unsigned int v11; // ecx
  int v12; // ebx
  __int64 v13; // [rsp+20h] [rbp-68h] BYREF
  unsigned int v14; // [rsp+28h] [rbp-60h] BYREF
  unsigned int v15; // [rsp+2Ch] [rbp-5Ch]
  _BYTE v16[24]; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DESCRIPTOR v17; // [rsp+48h] [rbp-40h] BYREF
  __int128 v18; // [rsp+58h] [rbp-30h] BYREF

  PerfDiagOutput::CEtwRegHandle::CEtwRegHandle((PerfDiagOutput::CEtwRegHandle *)&v13, a2);
  PerfDiagOutput::CSqmSession::CSqmSession((PerfDiagOutput::CSqmSession *)v16, &stru_1800E8088, 0x22D02u);
  v18 = 0;
  v17 = 0;
  EtwEventActivityIdControl(5, &v18);
  *(_DWORD *)&v17.Id = PerfDiagStandbyInfoEvent;
  v17.Level = 4;
  *(_QWORD *)&v17.Opcode = 0x100000FA324LL;
  HIDWORD(v17.Keyword) = 0x80000000;
  v17.Level = PerfDiagSuspend::GetInfoEventLevel((PerfDiagSuspend *)a2, this, v7);
  PerfDiagSuspend::CPayloadInfo::_send_to_sqm<PerfDiagOutput::CSqmSession>(a2, v16);
  v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWrite<PerfDiagSuspend::CPayloadInfo>(
         (PerfDiagOutput::CEtwRegHandle *)&v13,
         &v17,
         (__int64)a2);
  if ( v8 < 0 )
    goto LABEL_20;
  v9 = a2[2].Data1 - a2[9].Data1 - *(_DWORD *)&a2[2].Data2;
  v14 = v9 / 3;
  v15 = v9;
  PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(
    v16,
    qword_1800E8198,
    a3);
  v8 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>((PerfDiagOutput::CEtwRegHandle *)&v13);
  if ( v8 < 0 )
    goto LABEL_20;
  PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(
    v16,
    qword_1800E80F8,
    (char *)a3 + 24);
  v8 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>((PerfDiagOutput::CEtwRegHandle *)&v13);
  if ( v8 < 0 )
    goto LABEL_20;
  PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCauseDriver::SqmMap const,3,PerfDiagOutput::CRootCauseDriver>(
    v16,
    qword_1800E8140,
    (char *)a3 + 48);
  v8 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCauseDriver,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
         (PerfDiagOutput::CEtwRegHandle *)&v13,
         (struct _EVENT_DESCRIPTOR *)PerfDiagStandbyDriversDegradationEvent,
         (__int64 *)a3 + 6,
         &v14);
  if ( v8 < 0 )
    goto LABEL_20;
  v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
         (__int64)&v13,
         (struct _EVENT_DESCRIPTOR *)PerfDiagStandbySuspendShowUIDegradationEvent,
         (__int64)a3 + 96,
         &v14);
  if ( v8 < 0 )
    goto LABEL_20;
  v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
         (__int64)&v13,
         (struct _EVENT_DESCRIPTOR *)PerfDiagStandbySuspendWinlogonDegradationEvent,
         (__int64)a3 + 120,
         &v14);
  if ( v8 < 0 )
    goto LABEL_20;
  v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
         (__int64)&v13,
         (struct _EVENT_DESCRIPTOR *)PerfDiagStandbyLockPageableSectionsDegradationEvent,
         (__int64)a3 + 144,
         &v14);
  if ( v8 >= 0
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v13,
               (struct _EVENT_DESCRIPTOR *)PerfDiagStandbyPreSleepCallbacksDegradationEvent,
               (__int64)a3 + 168,
               &v14),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v13,
               (struct _EVENT_DESCRIPTOR *)PerfDiagStandbySwapInWorkerThreadsDegradationEvent,
               (__int64)a3 + 192,
               &v14),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v13,
               (struct _EVENT_DESCRIPTOR *)PerfDiagStandbyFlushVolumesDegradationEvent,
               (__int64)a3 + 216,
               &v14),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v13,
               (struct _EVENT_DESCRIPTOR *)PerfDiagStandbyHiberFileDegradationEvent,
               (__int64)a3 + 240,
               &v14),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v13,
               (struct _EVENT_DESCRIPTOR *)PerfDiagResumeHiberFileDegradationEvent,
               (__int64)a3 + 264,
               &v14),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v13,
               (struct _EVENT_DESCRIPTOR *)PerfDiagResumeBiosInitDegradationEvent,
               (__int64)a3 + 288,
               &v14),
        v8 >= 0) )
  {
    v11 = *(_DWORD *)a2[10].Data4 - *(_DWORD *)a2[11].Data4 - a2[11].Data1 - *(_DWORD *)&a2[10].Data4[4];
    v14 = v11 / 3;
    v15 = v11;
    PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCauseDriver::SqmMap const,3,PerfDiagOutput::CRootCauseDriver>(
      v16,
      qword_1800E80A0,
      (char *)a3 + 72);
    v12 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCauseDriver,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
            (PerfDiagOutput::CEtwRegHandle *)&v13,
            (struct _EVENT_DESCRIPTOR *)PerfDiagResumeDriversDegradationEvent,
            (__int64 *)a3 + 9,
            &v14);
    PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v16);
    EtwEventUnregister(v13);
    if ( v12 >= 0 )
      return 0;
    else
      return (unsigned int)v12;
  }
  else
  {
LABEL_20:
    PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v16);
    EtwEventUnregister(v13);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1800b9614  push    rbx
0x1800b9616  push    rsi
0x1800b9617  push    rdi
0x1800b9618  sub     rsp, 70h
0x1800b961c  mov     rax, cs:__security_cookie
0x1800b9623  xor     rax, rsp
0x1800b9626  mov     [rsp+88h+var_20], rax
0x1800b962b  mov     rdi, r8
0x1800b962e  mov     rsi, rdx
0x1800b9631  mov     rbx, rcx
0x1800b9634  lea     rcx, [rsp+88h+var_68]; this
0x1800b9639  call    ??0CEtwRegHandle@PerfDiagOutput@@QEAA@AEBU_GUID@@@Z; PerfDiagOutput::CEtwRegHandle::CEtwRegHandle(_GUID const &)
0x1800b963e  nop
0x1800b963f  mov     r8d, 22D02h; unsigned int
0x1800b9645  lea     rdx, stru_1800E8088; struct _GUID *
0x1800b964c  lea     rcx, [rsp+88h+var_58]; this
0x1800b9651  call    ??0CSqmSession@PerfDiagOutput@@QEAA@PEBU_GUID@@K@Z; PerfDiagOutput::CSqmSession::CSqmSession(_GUID const *,ulong)
0x1800b9656  nop
0x1800b9657  xorps   xmm0, xmm0
0x1800b965a  movups  [rsp+88h+var_30], xmm0
0x1800b965f  xorps   xmm1, xmm1
0x1800b9662  movups  xmmword ptr [rsp+88h+var_40.Id], xmm1
0x1800b9667  lea     rdx, [rsp+88h+var_30]
0x1800b966c  mov     ecx, 5
0x1800b9671  call    cs:__imp_EtwEventActivityIdControl
0x1800b9677  mov     eax, cs:PerfDiagStandbyInfoEvent
0x1800b967d  mov     dword ptr [rsp+88h+var_40.Id], eax
0x1800b9681  mov     [rsp+88h+var_40.Level], 4
0x1800b9686  movsd   xmm0, cs:qword_1800E68F5
0x1800b968e  movsd   qword ptr [rsp+88h+var_40.Opcode], xmm0
0x1800b9694  mov     eax, dword ptr cs:qword_1800E68F5+7
0x1800b969a  mov     dword ptr [rsp+88h+var_40.Keyword+4], eax
0x1800b969e  mov     rdx, rbx; struct PerfDiagSuspend::CPayloadInfo *
0x1800b96a1  mov     rcx, rsi; this
0x1800b96a4  call    ?GetInfoEventLevel@PerfDiagSuspend@@YAEAEBUCPayloadInfo@1@AEBVCSeverityConfig@1@@Z; PerfDiagSuspend::GetInfoEventLevel(PerfDiagSuspend::CPayloadInfo const &,PerfDiagSuspend::CSeverityConfig const &)
0x1800b96a9  mov     [rsp+88h+var_40.Level], al
0x1800b96ad  lea     rdx, [rsp+88h+var_58]
0x1800b96b2  mov     rcx, rsi
0x1800b96b5  call    ??$_send_to_sqm@VCSqmSession@PerfDiagOutput@@@CPayloadInfo@PerfDiagSuspend@@QEBAXAEAVCSqmSession@PerfDiagOutput@@AEBUSqmMap@01@@Z; PerfDiagSuspend::CPayloadInfo::_send_to_sqm<PerfDiagOutput::CSqmSession>(PerfDiagOutput::CSqmSession &,PerfDiagSuspend::CPayloadInfo::SqmMap const &)
0x1800b96ba  mov     r8, rsi
0x1800b96bd  lea     rdx, [rsp+88h+var_40]; struct _EVENT_DESCRIPTOR *
0x1800b96c2  lea     rcx, [rsp+88h+var_68]; this
0x1800b96c7  call    ??$EtwEventWrite@UCPayloadInfo@PerfDiagSuspend@@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBUCPayloadInfo@PerfDiagSuspend@@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWrite<PerfDiagSuspend::CPayloadInfo>(_EVENT_DESCRIPTOR const *,PerfDiagSuspend::CPayloadInfo const &)
0x1800b96cc  mov     ebx, eax
0x1800b96ce  test    eax, eax
0x1800b96d0  jns     short loc_1800B96EF
0x1800b96d2  lea     rcx, [rsp+88h+var_58]; this
0x1800b96d7  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b96dc  nop
0x1800b96dd  mov     rcx, [rsp+88h+var_68]
0x1800b96e2  call    cs:__imp_EtwEventUnregister
0x1800b96e8  mov     eax, ebx
0x1800b96ea  jmp     loc_1800B9ABA
0x1800b96ef  mov     ecx, [rsi+20h]
0x1800b96f2  sub     ecx, [rsi+90h]
0x1800b96f8  sub     ecx, [rsi+24h]
0x1800b96fb  mov     eax, 0AAAAAAABh
0x1800b9700  mul     ecx
0x1800b9702  shr     edx, 1
0x1800b9704  mov     [rsp+88h+var_60], edx
0x1800b9708  mov     [rsp+88h+var_5C], ecx
0x1800b970c  mov     r8, rdi
0x1800b970f  lea     rdx, qword_1800E8198
0x1800b9716  lea     rcx, [rsp+88h+var_58]
0x1800b971b  call    ??$Log@$$CBUSqmMap@CRootCause@PerfDiagOutput@@$02V23@@CSqmSession@PerfDiagOutput@@QEAAXAEAY02$$CBUSqmMap@CRootCause@1@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@PEBD@Z; PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(PerfDiagOutput::CRootCause::SqmMap const (&)[3],std::vector<PerfDiagOutput::CRootCause> const &,char const *)
0x1800b9720  lea     r9, [rsp+88h+var_60]
0x1800b9725  mov     r8, rdi
0x1800b9728  lea     rdx, PerfDiagStandbyAppsDegradationEvent
0x1800b972f  lea     rcx, [rsp+88h+var_68]; this
0x1800b9734  call    ??$EventWriteBatchEx@VCRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCause> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9739  mov     ebx, eax
0x1800b973b  test    eax, eax
0x1800b973d  jns     short loc_1800B975C
0x1800b973f  lea     rcx, [rsp+88h+var_58]; this
0x1800b9744  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b9749  nop
0x1800b974a  mov     rcx, [rsp+88h+var_68]
0x1800b974f  call    cs:__imp_EtwEventUnregister
0x1800b9755  mov     eax, ebx
0x1800b9757  jmp     loc_1800B9ABA
0x1800b975c  lea     r8, [rdi+18h]
0x1800b9760  lea     rdx, qword_1800E80F8
0x1800b9767  lea     rcx, [rsp+88h+var_58]
0x1800b976c  call    ??$Log@$$CBUSqmMap@CRootCause@PerfDiagOutput@@$02V23@@CSqmSession@PerfDiagOutput@@QEAAXAEAY02$$CBUSqmMap@CRootCause@1@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@PEBD@Z; PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(PerfDiagOutput::CRootCause::SqmMap const (&)[3],std::vector<PerfDiagOutput::CRootCause> const &,char const *)
0x1800b9771  lea     r9, [rsp+88h+var_60]
0x1800b9776  lea     r8, [rdi+18h]
0x1800b977a  lea     rdx, PerfDiagStandbyServicesDegradationEvent
0x1800b9781  lea     rcx, [rsp+88h+var_68]; this
0x1800b9786  call    ??$EventWriteBatchEx@VCRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCause> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b978b  mov     ebx, eax
0x1800b978d  test    eax, eax
0x1800b978f  jns     short loc_1800B97AE
0x1800b9791  lea     rcx, [rsp+88h+var_58]; this
0x1800b9796  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b979b  nop
0x1800b979c  mov     rcx, [rsp+88h+var_68]
0x1800b97a1  call    cs:__imp_EtwEventUnregister
0x1800b97a7  mov     eax, ebx
0x1800b97a9  jmp     loc_1800B9ABA
0x1800b97ae  lea     r8, [rdi+30h]
0x1800b97b2  lea     rdx, qword_1800E8140
0x1800b97b9  lea     rcx, [rsp+88h+var_58]
0x1800b97be  call    ??$Log@$$CBUSqmMap@CRootCauseDriver@PerfDiagOutput@@$02U23@@CSqmSession@PerfDiagOutput@@QEAAXAEAY02$$CBUSqmMap@CRootCauseDriver@1@AEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@PEBD@Z; PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCauseDriver::SqmMap const,3,PerfDiagOutput::CRootCauseDriver>(PerfDiagOutput::CRootCauseDriver::SqmMap const (&)[3],std::vector<PerfDiagOutput::CRootCauseDriver> const &,char const *)
0x1800b97c3  lea     r9, [rsp+88h+var_60]
0x1800b97c8  lea     r8, [rdi+30h]
0x1800b97cc  lea     rdx, PerfDiagStandbyDriversDegradationEvent
0x1800b97d3  lea     rcx, [rsp+88h+var_68]; this
0x1800b97d8  call    ??$EventWriteBatchEx@UCRootCauseDriver@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCauseDriver,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCauseDriver> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b97dd  mov     ebx, eax
0x1800b97df  test    eax, eax
0x1800b97e1  jns     short loc_1800B9800
0x1800b97e3  lea     rcx, [rsp+88h+var_58]; this
0x1800b97e8  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b97ed  nop
0x1800b97ee  mov     rcx, [rsp+88h+var_68]
0x1800b97f3  call    cs:__imp_EtwEventUnregister
0x1800b97f9  mov     eax, ebx
0x1800b97fb  jmp     loc_1800B9ABA
0x1800b9800  lea     r8, [rdi+60h]
0x1800b9804  lea     r9, [rsp+88h+var_60]
0x1800b9809  lea     rdx, PerfDiagStandbySuspendShowUIDegradationEvent
0x1800b9810  lea     rcx, [rsp+88h+var_68]
0x1800b9815  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b981a  mov     ebx, eax
0x1800b981c  test    eax, eax
0x1800b981e  jns     short loc_1800B983D
0x1800b9820  lea     rcx, [rsp+88h+var_58]; this
0x1800b9825  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b982a  nop
0x1800b982b  mov     rcx, [rsp+88h+var_68]
0x1800b9830  call    cs:__imp_EtwEventUnregister
0x1800b9836  mov     eax, ebx
0x1800b9838  jmp     loc_1800B9ABA
0x1800b983d  lea     r8, [rdi+78h]
0x1800b9841  lea     r9, [rsp+88h+var_60]
0x1800b9846  lea     rdx, PerfDiagStandbySuspendWinlogonDegradationEvent
0x1800b984d  lea     rcx, [rsp+88h+var_68]
0x1800b9852  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9857  mov     ebx, eax
0x1800b9859  test    eax, eax
0x1800b985b  jns     short loc_1800B987A
0x1800b985d  lea     rcx, [rsp+88h+var_58]; this
0x1800b9862  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b9867  nop
0x1800b9868  mov     rcx, [rsp+88h+var_68]
0x1800b986d  call    cs:__imp_EtwEventUnregister
0x1800b9873  mov     eax, ebx
0x1800b9875  jmp     loc_1800B9ABA
0x1800b987a  lea     r8, [rdi+90h]
0x1800b9881  lea     r9, [rsp+88h+var_60]
0x1800b9886  lea     rdx, PerfDiagStandbyLockPageableSectionsDegradationEvent
0x1800b988d  lea     rcx, [rsp+88h+var_68]
0x1800b9892  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9897  mov     ebx, eax
0x1800b9899  test    eax, eax
0x1800b989b  jns     short loc_1800B98BA
0x1800b989d  lea     rcx, [rsp+88h+var_58]; this
0x1800b98a2  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b98a7  nop
0x1800b98a8  mov     rcx, [rsp+88h+var_68]
0x1800b98ad  call    cs:__imp_EtwEventUnregister
0x1800b98b3  mov     eax, ebx
0x1800b98b5  jmp     loc_1800B9ABA
0x1800b98ba  lea     r8, [rdi+0A8h]
0x1800b98c1  lea     r9, [rsp+88h+var_60]
0x1800b98c6  lea     rdx, PerfDiagStandbyPreSleepCallbacksDegradationEvent
0x1800b98cd  lea     rcx, [rsp+88h+var_68]
0x1800b98d2  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b98d7  mov     ebx, eax
0x1800b98d9  test    eax, eax
0x1800b98db  jns     short loc_1800B98FA
0x1800b98dd  lea     rcx, [rsp+88h+var_58]; this
0x1800b98e2  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b98e7  nop
0x1800b98e8  mov     rcx, [rsp+88h+var_68]
0x1800b98ed  call    cs:__imp_EtwEventUnregister
0x1800b98f3  mov     eax, ebx
0x1800b98f5  jmp     loc_1800B9ABA
0x1800b98fa  lea     r8, [rdi+0C0h]
0x1800b9901  lea     r9, [rsp+88h+var_60]
0x1800b9906  lea     rdx, PerfDiagStandbySwapInWorkerThreadsDegradationEvent
0x1800b990d  lea     rcx, [rsp+88h+var_68]
0x1800b9912  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9917  mov     ebx, eax
0x1800b9919  test    eax, eax
0x1800b991b  jns     short loc_1800B993A
0x1800b991d  lea     rcx, [rsp+88h+var_58]; this
0x1800b9922  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b9927  nop
0x1800b9928  mov     rcx, [rsp+88h+var_68]
0x1800b992d  call    cs:__imp_EtwEventUnregister
0x1800b9933  mov     eax, ebx
0x1800b9935  jmp     loc_1800B9ABA
0x1800b993a  lea     r8, [rdi+0D8h]
0x1800b9941  lea     r9, [rsp+88h+var_60]
0x1800b9946  lea     rdx, PerfDiagStandbyFlushVolumesDegradationEvent
0x1800b994d  lea     rcx, [rsp+88h+var_68]
0x1800b9952  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9957  mov     ebx, eax
0x1800b9959  test    eax, eax
0x1800b995b  jns     short loc_1800B997A
0x1800b995d  lea     rcx, [rsp+88h+var_58]; this
0x1800b9962  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b9967  nop
0x1800b9968  mov     rcx, [rsp+88h+var_68]
0x1800b996d  call    cs:__imp_EtwEventUnregister
0x1800b9973  mov     eax, ebx
0x1800b9975  jmp     loc_1800B9ABA
0x1800b997a  lea     r8, [rdi+0F0h]
0x1800b9981  lea     r9, [rsp+88h+var_60]
0x1800b9986  lea     rdx, PerfDiagStandbyHiberFileDegradationEvent
0x1800b998d  lea     rcx, [rsp+88h+var_68]
0x1800b9992  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9997  mov     ebx, eax
0x1800b9999  test    eax, eax
0x1800b999b  jns     short loc_1800B99BA
0x1800b999d  lea     rcx, [rsp+88h+var_58]; this
0x1800b99a2  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b99a7  nop
0x1800b99a8  mov     rcx, [rsp+88h+var_68]
0x1800b99ad  call    cs:__imp_EtwEventUnregister
0x1800b99b3  mov     eax, ebx
0x1800b99b5  jmp     loc_1800B9ABA
0x1800b99ba  lea     r8, [rdi+108h]
0x1800b99c1  lea     r9, [rsp+88h+var_60]
0x1800b99c6  lea     rdx, PerfDiagResumeHiberFileDegradationEvent
0x1800b99cd  lea     rcx, [rsp+88h+var_68]
0x1800b99d2  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b99d7  mov     ebx, eax
0x1800b99d9  test    eax, eax
0x1800b99db  jns     short loc_1800B99FA
0x1800b99dd  lea     rcx, [rsp+88h+var_58]; this
0x1800b99e2  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b99e7  nop
0x1800b99e8  mov     rcx, [rsp+88h+var_68]
0x1800b99ed  call    cs:__imp_EtwEventUnregister
0x1800b99f3  mov     eax, ebx
0x1800b99f5  jmp     loc_1800B9ABA
0x1800b99fa  lea     r8, [rdi+120h]
0x1800b9a01  lea     r9, [rsp+88h+var_60]
0x1800b9a06  lea     rdx, PerfDiagResumeBiosInitDegradationEvent
0x1800b9a0d  lea     rcx, [rsp+88h+var_68]
0x1800b9a12  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9a17  mov     ebx, eax
0x1800b9a19  test    eax, eax
0x1800b9a1b  jns     short loc_1800B9A3A
0x1800b9a1d  lea     rcx, [rsp+88h+var_58]; this
0x1800b9a22  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b9a27  nop
0x1800b9a28  mov     rcx, [rsp+88h+var_68]
0x1800b9a2d  call    cs:__imp_EtwEventUnregister
0x1800b9a33  mov     eax, ebx
0x1800b9a35  jmp     loc_1800B9ABA
0x1800b9a3a  mov     ecx, [rsi+0A8h]
0x1800b9a40  sub     ecx, [rsi+0B8h]
0x1800b9a46  sub     ecx, [rsi+0B0h]
0x1800b9a4c  sub     ecx, [rsi+0ACh]
0x1800b9a52  mov     eax, 0AAAAAAABh
0x1800b9a57  mul     ecx
0x1800b9a59  shr     edx, 1
0x1800b9a5b  mov     [rsp+88h+var_60], edx
0x1800b9a5f  mov     [rsp+88h+var_5C], ecx
0x1800b9a63  lea     r8, [rdi+48h]
0x1800b9a67  lea     rdx, qword_1800E80A0
0x1800b9a6e  lea     rcx, [rsp+88h+var_58]
0x1800b9a73  call    ??$Log@$$CBUSqmMap@CRootCauseDriver@PerfDiagOutput@@$02U23@@CSqmSession@PerfDiagOutput@@QEAAXAEAY02$$CBUSqmMap@CRootCauseDriver@1@AEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@PEBD@Z; PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCauseDriver::SqmMap const,3,PerfDiagOutput::CRootCauseDriver>(PerfDiagOutput::CRootCauseDriver::SqmMap const (&)[3],std::vector<PerfDiagOutput::CRootCauseDriver> const &,char const *)
0x1800b9a78  lea     r9, [rsp+88h+var_60]
0x1800b9a7d  lea     r8, [rdi+48h]
0x1800b9a81  lea     rdx, PerfDiagResumeDriversDegradationEvent
0x1800b9a88  lea     rcx, [rsp+88h+var_68]; this
0x1800b9a8d  call    ??$EventWriteBatchEx@UCRootCauseDriver@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCauseDriver,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCauseDriver> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b9a92  mov     ebx, eax
0x1800b9a94  lea     rcx, [rsp+88h+var_58]; this
0x1800b9a99  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b9a9e  nop
0x1800b9a9f  mov     rcx, [rsp+88h+var_68]
0x1800b9aa4  call    cs:__imp_EtwEventUnregister
0x1800b9aaa  test    ebx, ebx
0x1800b9aac  jns     short loc_1800B9AB2
0x1800b9aae  mov     eax, ebx
0x1800b9ab0  jmp     short loc_1800B9ABA
0x1800b9ab2  xor     eax, eax
0x1800b9ab4  jmp     short loc_1800B9ABA
0x1800b9ab6  mov     eax, dword ptr [rsp+88h+var_68]
0x1800b9aba  mov     rcx, [rsp+88h+var_20]
0x1800b9abf  xor     rcx, rsp; StackCookie
0x1800b9ac2  call    __security_check_cookie
0x1800b9ac7  add     rsp, 70h
0x1800b9acb  pop     rdi
0x1800b9acc  pop     rsi
0x1800b9acd  pop     rbx
0x1800b9ace  retn
```
