# PerfDiagBoot::OutputSqmEventLog(PerfDiagBoot::CSeverityConfig const &,PerfDiagBoot::CPayloadInfo const &,PerfDiagBoot::CPayloadDegradation const &)

- ea: `0x1800b49d4`
- end: `0x1800b4def`
- name: `?OutputSqmEventLog@PerfDiagBoot@@YAJAEBVCSeverityConfig@1@AEBUCPayloadInfo@1@AEBUCPayloadDegradation@1@@Z`
- size: `1051`
- prototype: `__int64 __fastcall(PerfDiagBoot *__hidden this, const struct PerfDiagBoot::CSeverityConfig *, const struct PerfDiagBoot::CPayloadInfo *, const struct PerfDiagBoot::CPayloadDegradation *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x1800279d8`

## callees

- `0x180039814`
- `0x1800441b4`
- `0x1800b1b38`
- `0x1800b1f74`
- `0x1800b1fe8`
- `0x1800b2084`
- `0x1800b2490`
- `0x1800b3e94`
- `0x1800b418c`
- `0x1800b48e0`
- `0x1800b49d4`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800b4a1e`
- `ntdll!EtwEventActivityIdControl` at `0x1800b4daf`
- `ntdll!EtwEventActivityIdControl` at `0x1800b4a1e`
- `ntdll!EtwEventActivityIdControl` at `0x1800b4daf`
- `ntdll!EtwEventUnregister` at `0x1800b4a84`
- `ntdll!EtwEventUnregister` at `0x1800b4aeb`
- `ntdll!EtwEventUnregister` at `0x1800b4b3d`
- `ntdll!EtwEventUnregister` at `0x1800b4bc7`
- `ntdll!EtwEventUnregister` at `0x1800b4c19`
- `ntdll!EtwEventUnregister` at `0x1800b4c56`
- `ntdll!EtwEventUnregister` at `0x1800b4c93`
- `ntdll!EtwEventUnregister` at `0x1800b4cd3`
- `ntdll!EtwEventUnregister` at `0x1800b4d13`
- `ntdll!EtwEventUnregister` at `0x1800b4d53`
- `ntdll!EtwEventUnregister` at `0x1800b4d90`
- `ntdll!EtwEventUnregister` at `0x1800b4dbb`
- `ntdll!EtwEventUnregister` at `0x1800b4a84`
- `ntdll!EtwEventUnregister` at `0x1800b4aeb`
- `ntdll!EtwEventUnregister` at `0x1800b4b3d`
- `ntdll!EtwEventUnregister` at `0x1800b4bc7`
- `ntdll!EtwEventUnregister` at `0x1800b4c19`
- `ntdll!EtwEventUnregister` at `0x1800b4c56`
- `ntdll!EtwEventUnregister` at `0x1800b4c93`
- `ntdll!EtwEventUnregister` at `0x1800b4cd3`
- `ntdll!EtwEventUnregister` at `0x1800b4d13`
- `ntdll!EtwEventUnregister` at `0x1800b4d53`
- `ntdll!EtwEventUnregister` at `0x1800b4d90`
- `ntdll!EtwEventUnregister` at `0x1800b4dbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall PerfDiagBoot::OutputSqmEventLog(
        PerfDiagBoot *this,
        const struct _GUID *a2,
        const struct PerfDiagBoot::CPayloadInfo *a3,
        const struct PerfDiagBoot::CPayloadDegradation *a4)
{
  const struct PerfDiagBoot::CPayloadInfo *v7; // r8
  int v8; // ebx
  unsigned int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // r14
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rbx
  __int64 v16; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v17[2]; // [rsp+28h] [rbp-70h] BYREF
  __int128 v18; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DESCRIPTOR v19; // [rsp+48h] [rbp-50h] BYREF
  __int128 v20; // [rsp+58h] [rbp-40h] BYREF

  v18 = 0;
  PerfDiagOutput::CEtwRegHandle::CEtwRegHandle((PerfDiagOutput::CEtwRegHandle *)&v16, a2);
  v20 = 0;
  EtwEventActivityIdControl(5, &v20);
  PerfDiagBoot::CPayloadInfo::_send_to_sqm<PerfDiagOutput::CSqmSession>(a2, &v18);
  *(_DWORD *)&v19.Id = PerfDiagBootInfoEvent;
  v19.Level = 4;
  *(_QWORD *)&v19.Opcode = 0x100000FA222LL;
  HIDWORD(v19.Keyword) = 0x80000000;
  v19.Level = PerfDiagBoot::GetInfoEventLevel(this, (const struct PerfDiagBoot::CSeverityConfig *)a2, v7);
  v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWrite<PerfDiagBoot::CPayloadInfo>(
         (PerfDiagOutput::CEtwRegHandle *)&v16,
         &v19,
         (__int64)a2);
  if ( v8 < 0 )
    goto LABEL_21;
  v9 = *(_DWORD *)&a2[1].Data4[4] - *(_DWORD *)a2[7].Data4;
  v17[0] = v9 / 3;
  v17[1] = v9;
  PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(
    &v18,
    qword_1800E71A8,
    a3);
  v8 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>((PerfDiagOutput::CEtwRegHandle *)&v16);
  if ( v8 < 0 )
    goto LABEL_21;
  PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(
    &v18,
    qword_1800E7128,
    (char *)a3 + 24);
  v8 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>((PerfDiagOutput::CEtwRegHandle *)&v16);
  if ( v8 < 0 )
    goto LABEL_21;
  v10 = *((_QWORD *)a3 + 7);
  v11 = *((_QWORD *)a3 + 6);
  if ( v11 != v10 )
  {
    v12 = (v10 - v11) >> 6;
    v13 = 3;
    v14 = 0;
    if ( v12 > 3 || (v13 = v12) != 0 )
    {
      do
      {
        PerfDiagOutput::CRootCauseDevice::_send_to_sqm<PerfDiagOutput::CSqmSession>(
          v11 + (v14 << 6),
          &v18,
          (char *)qword_1800E7168 + 20 * v14);
        ++v14;
      }
      while ( v14 < v13 );
    }
  }
  v8 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCauseDevice,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>((PerfDiagOutput::CEtwRegHandle *)&v16);
  if ( v8 < 0 )
    goto LABEL_21;
  PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(
    &v18,
    qword_1800E70E8,
    (char *)a3 + 72);
  v8 = PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>((PerfDiagOutput::CEtwRegHandle *)&v16);
  if ( v8 < 0 )
    goto LABEL_21;
  v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
         (__int64)&v16,
         (struct _EVENT_DESCRIPTOR *)PerfDiagBootKernelInitDegradationEvent,
         (__int64)a3 + 96,
         v17);
  if ( v8 >= 0
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v16,
               (struct _EVENT_DESCRIPTOR *)PerfDiagBootForegroundPrefetchDegradationEvent,
               (__int64)a3 + 120,
               v17),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v16,
               (struct _EVENT_DESCRIPTOR *)PerfDiagBootBackgroundPrefetchDegradationEvent,
               (__int64)a3 + 144,
               v17),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v16,
               (struct _EVENT_DESCRIPTOR *)PerfDiagBootMachinePolicyDegradationEvent,
               (__int64)a3 + 168,
               v17),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v16,
               (struct _EVENT_DESCRIPTOR *)PerfDiagBootSMSSInitDegradationEvent,
               (__int64)a3 + 192,
               v17),
        v8 >= 0)
    && (v8 = PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(
               (__int64)&v16,
               (struct _EVENT_DESCRIPTOR *)PerfDiagBootPreShellInitDegradationEvent,
               (__int64)a3 + 216,
               v17),
        v8 >= 0) )
  {
    EtwEventActivityIdControl(2, &v20);
    EtwEventUnregister(v16);
    PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)&v18);
    return 0;
  }
  else
  {
LABEL_21:
    EtwEventUnregister(v16);
    PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)&v18);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1800b49d4  push    rbx
0x1800b49d6  push    rsi
0x1800b49d7  push    rdi
0x1800b49d8  push    r14
0x1800b49da  push    r15
0x1800b49dc  sub     rsp, 70h
0x1800b49e0  mov     rax, cs:__security_cookie
0x1800b49e7  xor     rax, rsp
0x1800b49ea  mov     [rsp+98h+var_30], rax
0x1800b49ef  mov     rdi, r8
0x1800b49f2  mov     rsi, rdx
0x1800b49f5  mov     rbx, rcx
0x1800b49f8  xorps   xmm0, xmm0
0x1800b49fb  movdqu  [rsp+98h+var_68], xmm0
0x1800b4a01  lea     rcx, [rsp+98h+var_78]; this
0x1800b4a06  call    ??0CEtwRegHandle@PerfDiagOutput@@QEAA@AEBU_GUID@@@Z; PerfDiagOutput::CEtwRegHandle::CEtwRegHandle(_GUID const &)
0x1800b4a0b  nop
0x1800b4a0c  xorps   xmm0, xmm0
0x1800b4a0f  movups  [rsp+98h+var_40], xmm0
0x1800b4a14  lea     rdx, [rsp+98h+var_40]
0x1800b4a19  mov     ecx, 5
0x1800b4a1e  call    cs:__imp_EtwEventActivityIdControl
0x1800b4a24  lea     rdx, [rsp+98h+var_68]
0x1800b4a29  mov     rcx, rsi
0x1800b4a2c  call    ??$_send_to_sqm@VCSqmSession@PerfDiagOutput@@@CPayloadInfo@PerfDiagBoot@@QEBAXAEAVCSqmSession@PerfDiagOutput@@AEBUSqmMap@01@@Z; PerfDiagBoot::CPayloadInfo::_send_to_sqm<PerfDiagOutput::CSqmSession>(PerfDiagOutput::CSqmSession &,PerfDiagBoot::CPayloadInfo::SqmMap const &)
0x1800b4a31  mov     eax, cs:PerfDiagBootInfoEvent
0x1800b4a37  mov     dword ptr [rsp+98h+var_50.Id], eax
0x1800b4a3b  mov     [rsp+98h+var_50.Level], 4
0x1800b4a40  movsd   xmm0, cs:qword_1800E69B5
0x1800b4a48  movsd   qword ptr [rsp+98h+var_50.Opcode], xmm0
0x1800b4a4e  mov     eax, dword ptr cs:qword_1800E69B5+7
0x1800b4a54  mov     dword ptr [rsp+98h+var_50.Keyword+4], eax
0x1800b4a58  mov     rdx, rsi; struct PerfDiagBoot::CSeverityConfig *
0x1800b4a5b  mov     rcx, rbx; this
0x1800b4a5e  call    ?GetInfoEventLevel@PerfDiagBoot@@YAEAEBVCSeverityConfig@1@AEBUCPayloadInfo@1@@Z; PerfDiagBoot::GetInfoEventLevel(PerfDiagBoot::CSeverityConfig const &,PerfDiagBoot::CPayloadInfo const &)
0x1800b4a63  mov     [rsp+98h+var_50.Level], al
0x1800b4a67  mov     r8, rsi
0x1800b4a6a  lea     rdx, [rsp+98h+var_50]; struct _EVENT_DESCRIPTOR *
0x1800b4a6f  lea     rcx, [rsp+98h+var_78]; this
0x1800b4a74  call    ??$EtwEventWrite@UCPayloadInfo@PerfDiagBoot@@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBUCPayloadInfo@PerfDiagBoot@@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWrite<PerfDiagBoot::CPayloadInfo>(_EVENT_DESCRIPTOR const *,PerfDiagBoot::CPayloadInfo const &)
0x1800b4a79  mov     ebx, eax
0x1800b4a7b  test    eax, eax
0x1800b4a7d  jns     short loc_1800B4A9C
0x1800b4a7f  mov     rcx, [rsp+98h+var_78]
0x1800b4a84  call    cs:__imp_EtwEventUnregister
0x1800b4a8a  nop
0x1800b4a8b  lea     rcx, [rsp+98h+var_68]; this
0x1800b4a90  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4a95  mov     eax, ebx
0x1800b4a97  jmp     loc_1800B4DD5
0x1800b4a9c  mov     ecx, [rsi+1Ch]
0x1800b4a9f  sub     ecx, [rsi+78h]
0x1800b4aa2  mov     eax, 0AAAAAAABh
0x1800b4aa7  mul     ecx
0x1800b4aa9  shr     edx, 1
0x1800b4aab  mov     [rsp+98h+var_70], edx
0x1800b4aaf  mov     [rsp+98h+var_6C], ecx
0x1800b4ab3  mov     r8, rdi
0x1800b4ab6  lea     rdx, qword_1800E71A8
0x1800b4abd  lea     rcx, [rsp+98h+var_68]
0x1800b4ac2  call    ??$Log@$$CBUSqmMap@CRootCause@PerfDiagOutput@@$02V23@@CSqmSession@PerfDiagOutput@@QEAAXAEAY02$$CBUSqmMap@CRootCause@1@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@PEBD@Z; PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(PerfDiagOutput::CRootCause::SqmMap const (&)[3],std::vector<PerfDiagOutput::CRootCause> const &,char const *)
0x1800b4ac7  lea     r9, [rsp+98h+var_70]
0x1800b4acc  mov     r8, rdi
0x1800b4acf  lea     rdx, PerfDiagBootAppsDegradationEvent
0x1800b4ad6  lea     rcx, [rsp+98h+var_78]; this
0x1800b4adb  call    ??$EventWriteBatchEx@VCRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCause> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4ae0  mov     ebx, eax
0x1800b4ae2  test    eax, eax
0x1800b4ae4  jns     short loc_1800B4B03
0x1800b4ae6  mov     rcx, [rsp+98h+var_78]
0x1800b4aeb  call    cs:__imp_EtwEventUnregister
0x1800b4af1  nop
0x1800b4af2  lea     rcx, [rsp+98h+var_68]; this
0x1800b4af7  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4afc  mov     eax, ebx
0x1800b4afe  jmp     loc_1800B4DD5
0x1800b4b03  lea     r8, [rdi+18h]
0x1800b4b07  lea     rdx, qword_1800E7128
0x1800b4b0e  lea     rcx, [rsp+98h+var_68]
0x1800b4b13  call    ??$Log@$$CBUSqmMap@CRootCause@PerfDiagOutput@@$02V23@@CSqmSession@PerfDiagOutput@@QEAAXAEAY02$$CBUSqmMap@CRootCause@1@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@PEBD@Z; PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(PerfDiagOutput::CRootCause::SqmMap const (&)[3],std::vector<PerfDiagOutput::CRootCause> const &,char const *)
0x1800b4b18  lea     r9, [rsp+98h+var_70]
0x1800b4b1d  lea     r8, [rdi+18h]
0x1800b4b21  lea     rdx, PerfDiagBootDriversDegradationEvent
0x1800b4b28  lea     rcx, [rsp+98h+var_78]; this
0x1800b4b2d  call    ??$EventWriteBatchEx@VCRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCause> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4b32  mov     ebx, eax
0x1800b4b34  test    eax, eax
0x1800b4b36  jns     short loc_1800B4B55
0x1800b4b38  mov     rcx, [rsp+98h+var_78]
0x1800b4b3d  call    cs:__imp_EtwEventUnregister
0x1800b4b43  nop
0x1800b4b44  lea     rcx, [rsp+98h+var_68]; this
0x1800b4b49  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4b4e  mov     eax, ebx
0x1800b4b50  jmp     loc_1800B4DD5
0x1800b4b55  mov     rax, [rdi+38h]
0x1800b4b59  mov     r14, [rdi+30h]
0x1800b4b5d  cmp     r14, rax
0x1800b4b60  jz      short loc_1800B4BA9
0x1800b4b62  sub     rax, r14
0x1800b4b65  sar     rax, 6
0x1800b4b69  mov     r15d, 3
0x1800b4b6f  xor     ebx, ebx
0x1800b4b71  cmp     rax, r15
0x1800b4b74  ja      short loc_1800B4B7E
0x1800b4b76  mov     r15, rax
0x1800b4b79  test    rax, rax
0x1800b4b7c  jz      short loc_1800B4BA9
0x1800b4b7e  lea     rax, [rbx+rbx*4]
0x1800b4b82  lea     rcx, qword_1800E7168
0x1800b4b89  lea     r8, [rcx+rax*4]
0x1800b4b8d  mov     rcx, rbx
0x1800b4b90  shl     rcx, 6
0x1800b4b94  add     rcx, r14
0x1800b4b97  lea     rdx, [rsp+98h+var_68]
0x1800b4b9c  call    ??$_send_to_sqm@VCSqmSession@PerfDiagOutput@@@CRootCauseDevice@PerfDiagOutput@@QEBAXAEAVCSqmSession@1@AEBUSqmMap@CRootCause@1@@Z; PerfDiagOutput::CRootCauseDevice::_send_to_sqm<PerfDiagOutput::CSqmSession>(PerfDiagOutput::CSqmSession &,PerfDiagOutput::CRootCause::SqmMap const &)
0x1800b4ba1  inc     rbx
0x1800b4ba4  cmp     rbx, r15
0x1800b4ba7  jb      short loc_1800B4B7E
0x1800b4ba9  lea     r9, [rsp+98h+var_70]
0x1800b4bae  lea     r8, [rdi+30h]
0x1800b4bb2  lea     rcx, [rsp+98h+var_78]; this
0x1800b4bb7  call    ??$EventWriteBatchEx@VCRootCauseDevice@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@VCRootCauseDevice@PerfDiagOutput@@V?$allocator@VCRootCauseDevice@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCauseDevice,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCauseDevice> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4bbc  mov     ebx, eax
0x1800b4bbe  test    eax, eax
0x1800b4bc0  jns     short loc_1800B4BDF
0x1800b4bc2  mov     rcx, [rsp+98h+var_78]
0x1800b4bc7  call    cs:__imp_EtwEventUnregister
0x1800b4bcd  nop
0x1800b4bce  lea     rcx, [rsp+98h+var_68]; this
0x1800b4bd3  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4bd8  mov     eax, ebx
0x1800b4bda  jmp     loc_1800B4DD5
0x1800b4bdf  lea     r8, [rdi+48h]
0x1800b4be3  lea     rdx, qword_1800E70E8
0x1800b4bea  lea     rcx, [rsp+98h+var_68]
0x1800b4bef  call    ??$Log@$$CBUSqmMap@CRootCause@PerfDiagOutput@@$02V23@@CSqmSession@PerfDiagOutput@@QEAAXAEAY02$$CBUSqmMap@CRootCause@1@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@PEBD@Z; PerfDiagOutput::CSqmSession::Log<PerfDiagOutput::CRootCause::SqmMap const,3,PerfDiagOutput::CRootCause>(PerfDiagOutput::CRootCause::SqmMap const (&)[3],std::vector<PerfDiagOutput::CRootCause> const &,char const *)
0x1800b4bf4  lea     r9, [rsp+98h+var_70]
0x1800b4bf9  lea     r8, [rdi+48h]
0x1800b4bfd  lea     rdx, PerfDiagBootServicesDegradationEvent
0x1800b4c04  lea     rcx, [rsp+98h+var_78]; this
0x1800b4c09  call    ??$EventWriteBatchEx@VCRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EventWriteBatchEx<PerfDiagOutput::CRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,std::vector<PerfDiagOutput::CRootCause> const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4c0e  mov     ebx, eax
0x1800b4c10  test    eax, eax
0x1800b4c12  jns     short loc_1800B4C31
0x1800b4c14  mov     rcx, [rsp+98h+var_78]
0x1800b4c19  call    cs:__imp_EtwEventUnregister
0x1800b4c1f  nop
0x1800b4c20  lea     rcx, [rsp+98h+var_68]; this
0x1800b4c25  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4c2a  mov     eax, ebx
0x1800b4c2c  jmp     loc_1800B4DD5
0x1800b4c31  lea     r8, [rdi+60h]
0x1800b4c35  lea     r9, [rsp+98h+var_70]
0x1800b4c3a  lea     rdx, PerfDiagBootKernelInitDegradationEvent
0x1800b4c41  lea     rcx, [rsp+98h+var_78]
0x1800b4c46  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4c4b  mov     ebx, eax
0x1800b4c4d  test    eax, eax
0x1800b4c4f  jns     short loc_1800B4C6E
0x1800b4c51  mov     rcx, [rsp+98h+var_78]
0x1800b4c56  call    cs:__imp_EtwEventUnregister
0x1800b4c5c  nop
0x1800b4c5d  lea     rcx, [rsp+98h+var_68]; this
0x1800b4c62  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4c67  mov     eax, ebx
0x1800b4c69  jmp     loc_1800B4DD5
0x1800b4c6e  lea     r8, [rdi+78h]
0x1800b4c72  lea     r9, [rsp+98h+var_70]
0x1800b4c77  lea     rdx, PerfDiagBootForegroundPrefetchDegradationEvent
0x1800b4c7e  lea     rcx, [rsp+98h+var_78]
0x1800b4c83  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4c88  mov     ebx, eax
0x1800b4c8a  test    eax, eax
0x1800b4c8c  jns     short loc_1800B4CAB
0x1800b4c8e  mov     rcx, [rsp+98h+var_78]
0x1800b4c93  call    cs:__imp_EtwEventUnregister
0x1800b4c99  nop
0x1800b4c9a  lea     rcx, [rsp+98h+var_68]; this
0x1800b4c9f  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4ca4  mov     eax, ebx
0x1800b4ca6  jmp     loc_1800B4DD5
0x1800b4cab  lea     r8, [rdi+90h]
0x1800b4cb2  lea     r9, [rsp+98h+var_70]
0x1800b4cb7  lea     rdx, PerfDiagBootBackgroundPrefetchDegradationEvent
0x1800b4cbe  lea     rcx, [rsp+98h+var_78]
0x1800b4cc3  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4cc8  mov     ebx, eax
0x1800b4cca  test    eax, eax
0x1800b4ccc  jns     short loc_1800B4CEB
0x1800b4cce  mov     rcx, [rsp+98h+var_78]
0x1800b4cd3  call    cs:__imp_EtwEventUnregister
0x1800b4cd9  nop
0x1800b4cda  lea     rcx, [rsp+98h+var_68]; this
0x1800b4cdf  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4ce4  mov     eax, ebx
0x1800b4ce6  jmp     loc_1800B4DD5
0x1800b4ceb  lea     r8, [rdi+0A8h]
0x1800b4cf2  lea     r9, [rsp+98h+var_70]
0x1800b4cf7  lea     rdx, PerfDiagBootMachinePolicyDegradationEvent
0x1800b4cfe  lea     rcx, [rsp+98h+var_78]
0x1800b4d03  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4d08  mov     ebx, eax
0x1800b4d0a  test    eax, eax
0x1800b4d0c  jns     short loc_1800B4D2B
0x1800b4d0e  mov     rcx, [rsp+98h+var_78]
0x1800b4d13  call    cs:__imp_EtwEventUnregister
0x1800b4d19  nop
0x1800b4d1a  lea     rcx, [rsp+98h+var_68]; this
0x1800b4d1f  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4d24  mov     eax, ebx
0x1800b4d26  jmp     loc_1800B4DD5
0x1800b4d2b  lea     r8, [rdi+0C0h]
0x1800b4d32  lea     r9, [rsp+98h+var_70]
0x1800b4d37  lea     rdx, PerfDiagBootSMSSInitDegradationEvent
0x1800b4d3e  lea     rcx, [rsp+98h+var_78]
0x1800b4d43  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4d48  mov     ebx, eax
0x1800b4d4a  test    eax, eax
0x1800b4d4c  jns     short loc_1800B4D68
0x1800b4d4e  mov     rcx, [rsp+98h+var_78]
0x1800b4d53  call    cs:__imp_EtwEventUnregister
0x1800b4d59  nop
0x1800b4d5a  lea     rcx, [rsp+98h+var_68]; this
0x1800b4d5f  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4d64  mov     eax, ebx
0x1800b4d66  jmp     short loc_1800B4DD5
0x1800b4d68  lea     r8, [rdi+0D8h]
0x1800b4d6f  lea     r9, [rsp+98h+var_70]
0x1800b4d74  lea     rdx, PerfDiagBootPreShellInitDegradationEvent
0x1800b4d7b  lea     rcx, [rsp+98h+var_78]
0x1800b4d80  call    ??$EtwEventWriteEx@VCSystemRootCause@PerfDiagOutput@@VCSystemRootCauseSeverityLevelSelector@2@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBVCSystemRootCause@1@AEBVCSystemRootCauseSeverityLevelSelector@1@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWriteEx<PerfDiagOutput::CSystemRootCause,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector>(_EVENT_DESCRIPTOR const *,PerfDiagOutput::CSystemRootCause const &,PerfDiagOutput::CSystemRootCauseSeverityLevelSelector const &)
0x1800b4d85  mov     ebx, eax
0x1800b4d87  test    eax, eax
0x1800b4d89  jns     short loc_1800B4DA5
0x1800b4d8b  mov     rcx, [rsp+98h+var_78]
0x1800b4d90  call    cs:__imp_EtwEventUnregister
0x1800b4d96  nop
0x1800b4d97  lea     rcx, [rsp+98h+var_68]; this
0x1800b4d9c  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4da1  mov     eax, ebx
0x1800b4da3  jmp     short loc_1800B4DD5
0x1800b4da5  lea     rdx, [rsp+98h+var_40]
0x1800b4daa  mov     ecx, 2
0x1800b4daf  call    cs:__imp_EtwEventActivityIdControl
0x1800b4db5  nop
0x1800b4db6  mov     rcx, [rsp+98h+var_78]
0x1800b4dbb  call    cs:__imp_EtwEventUnregister
0x1800b4dc1  nop
0x1800b4dc2  lea     rcx, [rsp+98h+var_68]; this
0x1800b4dc7  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b4dcc  nop
0x1800b4dcd  xor     eax, eax
0x1800b4dcf  jmp     short loc_1800B4DD5
0x1800b4dd1  mov     eax, dword ptr [rsp+98h+var_78]
0x1800b4dd5  mov     rcx, [rsp+98h+var_30]
0x1800b4dda  xor     rcx, rsp; StackCookie
0x1800b4ddd  call    __security_check_cookie
0x1800b4de2  add     rsp, 70h
0x1800b4de6  pop     r15
0x1800b4de8  pop     r14
0x1800b4dea  pop     rdi
0x1800b4deb  pop     rsi
0x1800b4dec  pop     rbx
0x1800b4ded  retn
```
