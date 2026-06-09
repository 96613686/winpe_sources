# PerfDiagShell::OutputSqmEventLog(ulong,ushort const *,ulong,ulong,ATL::CFileTime &,ATL::CFileTime &,PerfDiagShell::ShellTraceContext const &,ulong,ulong)

- ea: `0x1800b0880`
- end: `0x1800b0ead`
- name: `?OutputSqmEventLog@PerfDiagShell@@YAJKPEBGKKAEAVCFileTime@ATL@@1AEBVShellTraceContext@1@KK@Z`
- size: `1581`
- prototype: `__int64 __fastcall(PerfDiagShell *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, struct ATL::CFileTime *, struct ATL::CFileTime *, const struct PerfDiagShell::ShellTraceContext *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b1400`

## callees

- `0x180028f6c`
- `0x180032e50`
- `0x180039814`
- `0x18004311c`
- `0x1800441b4`
- `0x180044318`
- `0x1800576d4`
- `0x1800af088`
- `0x1800af4dc`
- `0x1800af940`
- `0x1800afcdc`
- `0x1800affd8`
- `0x1800b0580`
- `0x1800b0880`
- `0x1800c9b38`
- `0x1800cdafc`
- `0x1800cdbd4`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800b0bc3`
- `ntdll!EtwEventActivityIdControl` at `0x1800b0bc3`
- `ntdll!WinSqmSetDWORD` at `0x1800b0940`
- `ntdll!WinSqmSetDWORD` at `0x1800b0940`
- `ntdll!EtwEventUnregister` at `0x1800b0c58`
- `ntdll!EtwEventUnregister` at `0x1800b0c80`
- `ntdll!EtwEventUnregister` at `0x1800b0d45`
- `ntdll!EtwEventUnregister` at `0x1800b0e67`
- `ntdll!EtwEventUnregister` at `0x1800b0c58`
- `ntdll!EtwEventUnregister` at `0x1800b0c80`
- `ntdll!EtwEventUnregister` at `0x1800b0d45`
- `ntdll!EtwEventUnregister` at `0x1800b0e67`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b0a52`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b0b49`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b0a52`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b0b49`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800b0a6f`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800b0a87`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800b0a6f`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800b0a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0a40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0a40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0a18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0a18`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PerfDiagShell::OutputSqmEventLog(
        PerfDiagShell *this,
        FILETIME a2,
        const unsigned __int16 *a3,
        __int64 a4,
        const struct _EVENT_DESCRIPTOR **a5,
        struct ATL::CFileTime *a6,
        struct ATL::CFileTime *a7,
        const struct PerfDiagShell::ShellTraceContext *a8,
        unsigned int a9)
{
  int v9; // ebx
  unsigned int v10; // r14d
  __int64 v11; // r12
  __int64 v12; // rsi
  unsigned int v13; // r8d
  __int64 result; // rax
  unsigned __int64 i; // rdx
  int v16; // r8d
  __time64_t *v17; // rax
  int Hour; // r14d
  int v19; // r8d
  __time64_t *v20; // rax
  int v21; // eax
  int v22; // r8d
  int v23; // edx
  _QWORD *TickCount; // rax
  __int64 dwHighDateTime; // rdx
  __int64 dwLowDateTime; // rcx
  __int64 v27; // rdx
  __int128 v28; // rtt
  unsigned int v29; // r9d
  UCHAR EventLevel; // cl
  int v31; // r14d
  int v32; // edi
  const struct _EVENT_DESCRIPTOR *v33; // r9
  unsigned __int64 j; // rdx
  const struct _EVENT_DESCRIPTOR **k; // rax
  const struct _EVENT_DESCRIPTOR **m; // rax
  __int64 n; // rax
  struct _EVENT_DESCRIPTOR *v38; // [rsp+20h] [rbp-208h]
  __int64 v39; // [rsp+30h] [rbp-1F8h] BYREF
  struct _FILETIME v40; // [rsp+38h] [rbp-1F0h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+40h] [rbp-1E8h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-1E0h] BYREF
  _BYTE v43[8]; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v44; // [rsp+58h] [rbp-1D0h]
  _BYTE v45[16]; // [rsp+60h] [rbp-1C8h] BYREF
  const struct _EVENT_DESCRIPTOR *v46[6]; // [rsp+70h] [rbp-1B8h] BYREF
  FILETIME v47; // [rsp+A0h] [rbp-188h]
  int v48; // [rsp+A8h] [rbp-180h]
  int v49; // [rsp+ACh] [rbp-17Ch]
  FILETIME FileTime; // [rsp+B0h] [rbp-178h] BYREF
  ATL::CAtlException *v51; // [rsp+B8h] [rbp-170h] BYREF
  _BYTE v52[64]; // [rsp+C0h] [rbp-168h] BYREF
  struct _EVENT_DESCRIPTOR v53; // [rsp+100h] [rbp-128h] BYREF
  __int128 v54; // [rsp+110h] [rbp-118h] BYREF
  _QWORD v55[18]; // [rsp+120h] [rbp-108h] BYREF
  __int128 v56; // [rsp+1B0h] [rbp-78h]
  __int128 v57; // [rsp+1C0h] [rbp-68h]
  __int128 v58; // [rsp+1D0h] [rbp-58h]

  v40.dwLowDateTime = (unsigned int)a3;
  FileTime1 = a2;
  v9 = (int)this;
  LODWORD(v39) = (_DWORD)this;
  PerfDiagOutput::CSqmSession::CSqmSession((PerfDiagOutput::CSqmSession *)v43, &stru_180100E10, 0x22D01u);
  v10 = 0;
  v11 = (*(_QWORD *)a6 - *(unsigned int *)a5) / 10000LL;
  if ( v9 == 2 )
    WinSqmSetDWORD(v44, 287, (unsigned int)v11);
  try
  {
    v12 = *(_QWORD *)a7;
    v13 = *((_DWORD *)a7 + 20);
    if ( !v13 )
    {
      if ( !v12 )
      {
        PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v43);
        return 2147942487LL;
      }
      v10 = 0;
      for ( i = 0; i < *(_QWORD *)(v12 + 8); ++i )
        v10 |= 1 << *(_QWORD *)(v12 + 16 * i + 360);
    }
    v46[0] = *a5;
    v46[1] = *(const struct _EVENT_DESCRIPTOR **)a6;
    LODWORD(v46[4]) = 1;
    HIDWORD(v46[4]) = v40.dwLowDateTime;
    v46[3] = (const struct _EVENT_DESCRIPTOR *)__PAIR64__(v13, v10);
    v46[2] = (const struct _EVENT_DESCRIPTOR *)__PAIR64__(v11, v39);
    v47 = FileTime1;
    HIDWORD(v46[5]) = 0;
    v49 = *((_DWORD *)a7 + 22);
    v48 = *((_DWORD *)a7 + 21);
    EnterCriticalSection(StandbyScenario::g_spFileTime_CriticalSection);
    FileTime1 = StandbyScenario::g_FileTime_Resume_End;
    FileTime = StandbyScenario::g_FileTime_Suspend_End;
    LeaveCriticalSection(StandbyScenario::g_spFileTime_CriticalSection);
    LocalFileTime = 0;
    if ( CompareFileTime(&FileTime1, &PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End) == 1 )
    {
      FileTimeToLocalFileTime(&FileTime1, &LocalFileTime);
      v40 = 0;
      FileTimeToLocalFileTime(&FileTime, &v40);
      if ( *(_QWORD *)&LocalFileTime - *(_QWORD *)&v40 <= 0xC92A69C000uLL )
      {
        v17 = (__time64_t *)ATL::CTime::CTime((ATL::CTime *)v45, &v40, v16);
        Hour = ATL::CTime::GetHour(v17);
        v20 = (__time64_t *)ATL::CTime::CTime((ATL::CTime *)v45, &LocalFileTime, v19);
        v21 = ATL::CTime::GetHour(v20);
        v22 = 1 << (v21 + 1);
        v23 = 1 << Hour;
        if ( v21 < Hour )
          HIDWORD(v46[5]) = ~(v23 - v22);
        else
          HIDWORD(v46[5]) = v22 - v23;
      }
      else
      {
        HIDWORD(v46[5]) = 0xFFFFFF;
      }
      TickCount = (_QWORD *)ATL::CFileTime::GetTickCount(v45);
      dwHighDateTime = FileTime1.dwHighDateTime;
      dwLowDateTime = FileTime1.dwLowDateTime;
    }
    else
    {
      if ( !CompareFileTime(&LocalFileTime, &PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End) )
      {
        LODWORD(v46[5]) = 0;
LABEL_19:
        PerfDiagOutput::CEtwRegHandle::CEtwRegHandle((PerfDiagOutput::CEtwRegHandle *)&v39, (const struct _GUID *)v27);
        v54 = 0;
        EtwEventActivityIdControl(5, &v54);
        PerfDiagShell::CPayloadInfo::_send_to_sqm<PerfDiagOutput::CSqmSession>(v46, v43);
        EventLevel = PerfDiagOutput::GetEventLevel(
                       (PerfDiagOutput *)((unsigned int)v11 / 0x3E8),
                       (unsigned int)a8,
                       a9,
                       v29);
        if ( *((_DWORD *)a7 + 20) == 2 )
          EventLevel = 1;
        *(_DWORD *)&v53.Id = PerfDiagShellInfoEvent;
        *(_QWORD *)&v53.Opcode = 0x100000FA525LL;
        HIDWORD(v53.Keyword) = 0x80000000;
        v53.Level = EventLevel;
        v31 = PerfDiagOutput::CEtwRegHandle::EtwEventWrite<PerfDiagShell::CPayloadInfo>(
                (PerfDiagOutput::CEtwRegHandle *)&v39,
                &v53);
        if ( v31 >= 0 )
        {
          if ( LODWORD(v46[3]) )
          {
            `eh vector constructor iterator'(
              v55,
              0x18u,
              6u,
              std::vector<__int64>::vector<__int64>,
              std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned short const *>>>>>>>);
            v56 = 0;
            v57 = 0;
            v58 = 0;
            PerfDiagShared::Serializer::CStringInterner::CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v52);
            v32 = PerfDiagOutput::CRootCauseSummary::Summarize(
                    (PerfDiagOutput::CRootCauseSummary *)v55,
                    (const struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *)v12,
                    *((const struct PerfAnalyzer::IPerfAnalyzer **)a7 + 5),
                    *((struct XPerfAddIn::IProcessInfoSource **)a7 + 4),
                    *((struct XPerfCore::IPathRegistry **)a7 + 6),
                    (struct PerfDiagShared::Serializer::CStringInterner *)v52);
            if ( v32 >= 0 )
            {
              for ( j = 0; j < 6; ++j )
              {
                for ( k = (const struct _EVENT_DESCRIPTOR **)v55[3 * j];
                      k != (const struct _EVENT_DESCRIPTOR **)v55[3 * j + 1];
                      k += 10 )
                {
                  *k = *a5;
                }
              }
              for ( m = (const struct _EVENT_DESCRIPTOR **)v56;
                    m != *((const struct _EVENT_DESCRIPTOR ***)&v56 + 1);
                    m += 11 )
              {
                *m = *a5;
              }
              for ( n = *((_QWORD *)&v57 + 1); n != (_QWORD)v58; n += 24 )
                *(_QWORD *)(n + 16) = *a5;
              v46[0] = (const struct _EVENT_DESCRIPTOR *)PerfDiagShellCpuAppsDegradationEvent;
              v46[1] = (const struct _EVENT_DESCRIPTOR *)PerfDiagShellDriversDegradationEvent;
              v46[2] = (const struct _EVENT_DESCRIPTOR *)PerfDiagShellDiskAppsDegradationEvent;
              v46[3] = (const struct _EVENT_DESCRIPTOR *)PerfDiagShellDriversLongDpcDegradationEvent;
              v46[4] = (const struct _EVENT_DESCRIPTOR *)PerfDiagShellLongDiskIODegradationEvent;
              v46[5] = (const struct _EVENT_DESCRIPTOR *)PerfDiagShellFragmentationDegradationEvent;
              PerfDiagOutput::CRootCauseSummary::SendEventLog(
                (PerfDiagOutput::CRootCauseSummary *)v55,
                (struct PerfDiagOutput::CEtwRegHandle *)&v39,
                (const struct _EVENT_DESCRIPTOR *(*)[6])v46,
                v33,
                v38);
              PerfDiagOutput::CRootCauseSummary::SendSqmLog<PerfDiagOutput::CSqmSession,2,2>(v55, v43);
              PerfDiagShared::Serializer::CStringInterner::~CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v52);
              PerfDiagOutput::CRootCauseSummary::~CRootCauseSummary((PerfDiagOutput::CRootCauseSummary *)v55);
              EtwEventUnregister(v39);
              PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v43);
              return 0;
            }
            else
            {
              PerfDiagShared::Serializer::CStringInterner::~CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v52);
              PerfDiagOutput::CRootCauseSummary::~CRootCauseSummary((PerfDiagOutput::CRootCauseSummary *)v55);
              EtwEventUnregister(v39);
              PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v43);
              return (unsigned int)v32;
            }
          }
          else
          {
            EtwEventUnregister(v39);
            PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v43);
            return 0;
          }
        }
        else
        {
          EtwEventUnregister(v39);
          PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v43);
          return (unsigned int)v31;
        }
      }
      TickCount = (_QWORD *)ATL::CFileTime::GetTickCount(v45);
      dwHighDateTime = PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End.dwHighDateTime;
      dwLowDateTime = PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End.dwLowDateTime;
    }
    v28 = *TickCount - (dwLowDateTime | (dwHighDateTime << 32));
    v27 = (*TickCount - (dwLowDateTime | (dwHighDateTime << 32))) % 36000000000LL;
    LODWORD(v46[5]) = v28 / 36000000000LL;
    goto LABEL_19;
  }
  catch ( ATL::CAtlException *v51 )
  {
    LODWORD(v39) = *(_DWORD *)v51;
    PerfDiagOutput::CStdSqmSession::~CStdSqmSession((PerfDiagOutput::CStdSqmSession *)v43);
    return (unsigned int)v39;
  }
  return result;
}

```

## disassembly

```asm
0x1800b0880  push    rbx
0x1800b0882  push    rsi
0x1800b0883  push    rdi
0x1800b0884  push    r12
0x1800b0886  push    r13
0x1800b0888  push    r14
0x1800b088a  push    r15
0x1800b088c  sub     rsp, 1F0h
0x1800b0893  mov     rax, cs:__security_cookie
0x1800b089a  xor     rax, rsp
0x1800b089d  mov     [rsp+228h+var_48], rax
0x1800b08a5  mov     [rsp+228h+var_1F0.dwLowDateTime], r8d
0x1800b08aa  mov     qword ptr [rsp+228h+FileTime1.dwLowDateTime], rdx
0x1800b08af  mov     ebx, ecx
0x1800b08b1  mov     dword ptr [rsp+228h+var_1F8], ecx
0x1800b08b5  mov     rdi, [rsp+228h+arg_30]
0x1800b08bd  mov     r15, [rsp+228h+arg_20]
0x1800b08c5  mov     r13, [rsp+228h+arg_28]
0x1800b08cd  mov     r8d, 22D01h; unsigned int
0x1800b08d3  lea     rdx, stru_180100E10; struct _GUID *
0x1800b08da  lea     rcx, [rsp+228h+var_1D8]; this
0x1800b08df  call    ??0CSqmSession@PerfDiagOutput@@QEAA@PEBU_GUID@@K@Z; PerfDiagOutput::CSqmSession::CSqmSession(_GUID const *,ulong)
0x1800b08e4  nop
0x1800b08e5  xor     r14d, r14d
0x1800b08e8  mov     edx, [r13+4]
0x1800b08ec  shl     rdx, 20h
0x1800b08f0  mov     eax, [r13+0]
0x1800b08f4  or      rdx, rax
0x1800b08f7  mov     rcx, [r15]
0x1800b08fa  mov     rax, 0FFFFFFFF00000000h
0x1800b0904  and     rcx, rax
0x1800b0907  mov     eax, [r15]
0x1800b090a  or      rcx, rax
0x1800b090d  sub     rdx, rcx
0x1800b0910  mov     rax, 346DC5D63886594Bh
0x1800b091a  imul    rdx
0x1800b091d  mov     r12, rdx
0x1800b0920  sar     r12, 0Bh
0x1800b0924  mov     rax, r12
0x1800b0927  shr     rax, 3Fh
0x1800b092b  add     r12, rax
0x1800b092e  cmp     ebx, 2
0x1800b0931  jnz     short loc_1800B0947
0x1800b0933  mov     r8d, r12d
0x1800b0936  mov     edx, 11Fh
0x1800b093b  mov     rcx, [rsp+228h+var_1D0]
0x1800b0940  call    cs:__imp_WinSqmSetDWORD
0x1800b0946  nop
0x1800b0947  mov     rsi, [rdi]
0x1800b094a  mov     r8d, [rdi+50h]
0x1800b094e  test    r8d, r8d
0x1800b0951  jnz     short loc_1800B099A
0x1800b0953  test    rsi, rsi
0x1800b0956  jnz     short loc_1800B096C
0x1800b0958  lea     rcx, [rsp+228h+var_1D8]; this
0x1800b095d  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b0962  mov     eax, 80070057h
0x1800b0967  jmp     loc_1800B0E8A
0x1800b096c  xor     r14d, r14d
0x1800b096f  xor     edx, edx
0x1800b0971  cmp     [rsi+8], rdx
0x1800b0975  jbe     short loc_1800B099A
0x1800b0977  lea     ebx, [rdx+1]
0x1800b097a  mov     rcx, rdx
0x1800b097d  add     rcx, rcx
0x1800b0980  mov     rcx, [rsi+rcx*8+168h]
0x1800b0988  mov     eax, ebx
0x1800b098a  shl     eax, cl
0x1800b098c  or      r14d, eax
0x1800b098f  add     rdx, rbx
0x1800b0992  cmp     rdx, [rsi+8]
0x1800b0996  jb      short loc_1800B097A
0x1800b0998  jmp     short loc_1800B099F
0x1800b099a  mov     ebx, 1
0x1800b099f  mov     rax, [r15]
0x1800b09a2  mov     [rsp+228h+var_1B8], rax
0x1800b09a7  mov     rax, [r13+0]
0x1800b09ab  mov     [rsp+228h+var_1B8+8], rax
0x1800b09b0  mov     dword ptr [rsp+228h+var_1B8+14h], r12d
0x1800b09b8  mov     dword ptr [rsp+228h+var_1B8+20h], ebx
0x1800b09bf  mov     eax, [rsp+228h+var_1F0.dwLowDateTime]
0x1800b09c3  mov     dword ptr [rsp+228h+var_1B8+24h], eax
0x1800b09ca  mov     dword ptr [rsp+228h+var_1B8+18h], r14d
0x1800b09d2  mov     eax, dword ptr [rsp+228h+var_1F8]
0x1800b09d6  mov     dword ptr [rsp+228h+var_1B8+10h], eax
0x1800b09dd  mov     rax, qword ptr [rsp+228h+FileTime1.dwLowDateTime]
0x1800b09e2  mov     [rsp+228h+var_188], rax
0x1800b09ea  mov     dword ptr [rsp+228h+var_1B8+1Ch], r8d
0x1800b09f2  xor     r13d, r13d
0x1800b09f5  mov     dword ptr [rsp+228h+var_1B8+2Ch], r13d
0x1800b09fd  mov     eax, [rdi+58h]
0x1800b0a00  mov     [rsp+228h+var_17C], eax
0x1800b0a07  mov     eax, [rdi+54h]
0x1800b0a0a  mov     [rsp+228h+var_180], eax
0x1800b0a11  mov     rcx, cs:?g_spFileTime_CriticalSection@StandbyScenario@@2V?$CAtlGlobalPtr@VCComAutoCriticalSection@ATL@@@XPerfCore@@A; lpCriticalSection
0x1800b0a18  call    cs:__imp_EnterCriticalSection
0x1800b0a1e  mov     rax, cs:?g_FileTime_Resume_End@StandbyScenario@@2U_FILETIME@@A; _FILETIME StandbyScenario::g_FileTime_Resume_End
0x1800b0a25  mov     qword ptr [rsp+228h+FileTime1.dwLowDateTime], rax
0x1800b0a2a  mov     rax, cs:?g_FileTime_Suspend_End@StandbyScenario@@2U_FILETIME@@A; _FILETIME StandbyScenario::g_FileTime_Suspend_End
0x1800b0a31  mov     qword ptr [rsp+228h+FileTime.dwLowDateTime], rax
0x1800b0a39  mov     rcx, cs:?g_spFileTime_CriticalSection@StandbyScenario@@2V?$CAtlGlobalPtr@VCComAutoCriticalSection@ATL@@@XPerfCore@@A; lpCriticalSection
0x1800b0a40  call    cs:__imp_LeaveCriticalSection
0x1800b0a46  lea     rdx, ?g_FileTime_Boot_End@BootSharedInformation@PerfDiagDm@@2U_FILETIME@@A; lpFileTime2
0x1800b0a4d  lea     rcx, [rsp+228h+FileTime1]; lpFileTime1
0x1800b0a52  call    cs:__imp_CompareFileTime
0x1800b0a58  mov     qword ptr [rsp+228h+LocalFileTime.dwLowDateTime], r13
0x1800b0a5d  cmp     eax, ebx
0x1800b0a5f  jnz     loc_1800B0B3D
0x1800b0a65  lea     rdx, [rsp+228h+LocalFileTime]; lpLocalFileTime
0x1800b0a6a  lea     rcx, [rsp+228h+FileTime1]; lpFileTime
0x1800b0a6f  call    cs:__imp_FileTimeToLocalFileTime
0x1800b0a75  mov     qword ptr [rsp+228h+var_1F0.dwLowDateTime], r13
0x1800b0a7a  lea     rdx, [rsp+228h+var_1F0]; lpLocalFileTime
0x1800b0a7f  lea     rcx, [rsp+228h+FileTime]; lpFileTime
0x1800b0a87  call    cs:__imp_FileTimeToLocalFileTime
0x1800b0a8d  mov     edx, [rsp+228h+var_1F0.dwHighDateTime]
0x1800b0a91  shl     rdx, 20h
0x1800b0a95  mov     eax, [rsp+228h+var_1F0.dwLowDateTime]
0x1800b0a99  or      rdx, rax
0x1800b0a9c  mov     ecx, [rsp+228h+LocalFileTime.dwHighDateTime]
0x1800b0aa0  shl     rcx, 20h
0x1800b0aa4  mov     eax, [rsp+228h+LocalFileTime.dwLowDateTime]
0x1800b0aa8  or      rcx, rax
0x1800b0aab  sub     rcx, rdx
0x1800b0aae  mov     rax, 0C92A69C000h
0x1800b0ab8  cmp     rcx, rax
0x1800b0abb  jbe     short loc_1800B0ACA
0x1800b0abd  mov     dword ptr [rsp+228h+var_1B8+2Ch], 0FFFFFFh
0x1800b0ac8  jmp     short loc_1800B0B29
0x1800b0aca  lea     rdx, [rsp+228h+var_1F0]; struct _FILETIME *
0x1800b0acf  lea     rcx, [rsp+228h+var_1C8]; this
0x1800b0ad4  call    ??0CTime@ATL@@QEAA@AEBU_FILETIME@@H@Z; ATL::CTime::CTime(_FILETIME const &,int)
0x1800b0ad9  mov     rcx, rax; Time
0x1800b0adc  call    ?GetHour@CTime@ATL@@QEBAHXZ; ATL::CTime::GetHour(void)
0x1800b0ae1  mov     r14d, eax
0x1800b0ae4  lea     rdx, [rsp+228h+LocalFileTime]; struct _FILETIME *
0x1800b0ae9  lea     rcx, [rsp+228h+var_1C8]; this
0x1800b0aee  call    ??0CTime@ATL@@QEAA@AEBU_FILETIME@@H@Z; ATL::CTime::CTime(_FILETIME const &,int)
0x1800b0af3  mov     rcx, rax; Time
0x1800b0af6  call    ?GetHour@CTime@ATL@@QEBAHXZ; ATL::CTime::GetHour(void)
0x1800b0afb  lea     ecx, [rax+1]
0x1800b0afe  mov     r8d, ebx
0x1800b0b01  shl     r8d, cl
0x1800b0b04  mov     ecx, r14d
0x1800b0b07  mov     edx, ebx
0x1800b0b09  shl     edx, cl
0x1800b0b0b  cmp     eax, r14d
0x1800b0b0e  jl      short loc_1800B0B1D
0x1800b0b10  sub     r8d, edx
0x1800b0b13  mov     dword ptr [rsp+228h+var_1B8+2Ch], r8d
0x1800b0b1b  jmp     short loc_1800B0B29
0x1800b0b1d  sub     edx, r8d
0x1800b0b20  not     edx
0x1800b0b22  mov     dword ptr [rsp+228h+var_1B8+2Ch], edx
0x1800b0b29  lea     rcx, [rsp+228h+var_1C8]
0x1800b0b2e  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x1800b0b33  mov     edx, [rsp+228h+FileTime1.dwHighDateTime]
0x1800b0b37  mov     ecx, [rsp+228h+FileTime1.dwLowDateTime]
0x1800b0b3b  jmp     short loc_1800B0B73
0x1800b0b3d  lea     rdx, ?g_FileTime_Boot_End@BootSharedInformation@PerfDiagDm@@2U_FILETIME@@A; lpFileTime2
0x1800b0b44  lea     rcx, [rsp+228h+LocalFileTime]; lpFileTime1
0x1800b0b49  call    cs:__imp_CompareFileTime
0x1800b0b4f  test    eax, eax
0x1800b0b51  jnz     short loc_1800B0B5D
0x1800b0b53  mov     dword ptr [rsp+228h+var_1B8+28h], r13d
0x1800b0b5b  jmp     short loc_1800B0BA0
0x1800b0b5d  lea     rcx, [rsp+228h+var_1C8]
0x1800b0b62  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x1800b0b67  mov     edx, cs:?g_FileTime_Boot_End@BootSharedInformation@PerfDiagDm@@2U_FILETIME@@A.dwHighDateTime; _FILETIME PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End ...
0x1800b0b6d  mov     ecx, cs:?g_FileTime_Boot_End@BootSharedInformation@PerfDiagDm@@2U_FILETIME@@A.dwLowDateTime; _FILETIME PerfDiagDm::BootSharedInformation::g_FileTime_Boot_End ...
0x1800b0b73  mov     r8d, [rax+4]
0x1800b0b77  shl     rdx, 20h
0x1800b0b7b  shl     r8, 20h
0x1800b0b7f  mov     eax, [rax]
0x1800b0b81  or      rdx, rcx
0x1800b0b84  or      rax, r8
0x1800b0b87  sub     rax, rdx
0x1800b0b8a  cqo; struct _GUID *
0x1800b0b8c  mov     rcx, 861C46800h
0x1800b0b96  idiv    rcx
0x1800b0b99  mov     dword ptr [rsp+228h+var_1B8+28h], eax
0x1800b0ba0  lea     rcx, [rsp+228h+var_1F8]; this
0x1800b0ba5  call    ??0CEtwRegHandle@PerfDiagOutput@@QEAA@AEBU_GUID@@@Z; PerfDiagOutput::CEtwRegHandle::CEtwRegHandle(_GUID const &)
0x1800b0baa  nop
0x1800b0bab  xorps   xmm0, xmm0
0x1800b0bae  movups  [rsp+228h+var_118], xmm0
0x1800b0bb6  lea     rdx, [rsp+228h+var_118]
0x1800b0bbe  mov     ecx, 5
0x1800b0bc3  call    cs:__imp_EtwEventActivityIdControl
0x1800b0bc9  lea     rdx, [rsp+228h+var_1D8]
0x1800b0bce  lea     rcx, [rsp+228h+var_1B8]
0x1800b0bd3  call    ??$_send_to_sqm@VCSqmSession@PerfDiagOutput@@@CPayloadInfo@PerfDiagShell@@QEBAXAEAVCSqmSession@PerfDiagOutput@@AEBUSqmMap@01@@Z; PerfDiagShell::CPayloadInfo::_send_to_sqm<PerfDiagOutput::CSqmSession>(PerfDiagOutput::CSqmSession &,PerfDiagShell::CPayloadInfo::SqmMap const &)
0x1800b0bd8  mov     eax, 10624DD3h
0x1800b0bdd  mul     r12d
0x1800b0be0  mov     ecx, edx
0x1800b0be2  shr     ecx, 6; this
0x1800b0be5  mov     r8d, [rsp+228h+arg_40]; unsigned int
0x1800b0bed  mov     edx, dword ptr [rsp+228h+arg_38]; unsigned int
0x1800b0bf4  call    ?GetEventLevel@PerfDiagOutput@@YAEKKK@Z; PerfDiagOutput::GetEventLevel(ulong,ulong,ulong)
0x1800b0bf9  movzx   ecx, al
0x1800b0bfc  cmp     dword ptr [rdi+50h], 2
0x1800b0c00  cmovz   ecx, ebx
0x1800b0c03  mov     eax, cs:PerfDiagShellInfoEvent
0x1800b0c09  mov     dword ptr [rsp+228h+var_128.Id], eax
0x1800b0c10  movsd   xmm0, cs:qword_1800E6815
0x1800b0c18  movsd   qword ptr [rsp+228h+var_128.Opcode], xmm0
0x1800b0c21  mov     eax, dword ptr cs:qword_1800E6815+7
0x1800b0c27  mov     dword ptr [rsp+228h+var_128.Keyword+4], eax
0x1800b0c2e  mov     [rsp+228h+var_128.Level], cl
0x1800b0c35  lea     r8, [rsp+228h+var_1B8]
0x1800b0c3a  lea     rdx, [rsp+228h+var_128]; struct _EVENT_DESCRIPTOR *
0x1800b0c42  lea     rcx, [rsp+228h+var_1F8]; this
0x1800b0c47  call    ??$EtwEventWrite@UCPayloadInfo@PerfDiagShell@@@CEtwRegHandle@PerfDiagOutput@@QEAAJPEBU_EVENT_DESCRIPTOR@@AEBUCPayloadInfo@PerfDiagShell@@@Z; PerfDiagOutput::CEtwRegHandle::EtwEventWrite<PerfDiagShell::CPayloadInfo>(_EVENT_DESCRIPTOR const *,PerfDiagShell::CPayloadInfo const &)
0x1800b0c4c  mov     r14d, eax
0x1800b0c4f  test    eax, eax
0x1800b0c51  jns     short loc_1800B0C71
0x1800b0c53  mov     rcx, [rsp+228h+var_1F8]
0x1800b0c58  call    cs:__imp_EtwEventUnregister
0x1800b0c5e  nop
0x1800b0c5f  lea     rcx, [rsp+228h+var_1D8]; this
0x1800b0c64  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b0c69  mov     eax, r14d
0x1800b0c6c  jmp     loc_1800B0E8A
0x1800b0c71  cmp     dword ptr [rsp+228h+var_1B8+18h], r13d
0x1800b0c79  jnz     short loc_1800B0C98
0x1800b0c7b  mov     rcx, [rsp+228h+var_1F8]
0x1800b0c80  call    cs:__imp_EtwEventUnregister
0x1800b0c86  nop
0x1800b0c87  lea     rcx, [rsp+228h+var_1D8]; this
0x1800b0c8c  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b0c91  xor     eax, eax
0x1800b0c93  jmp     loc_1800B0E8A
0x1800b0c98  lea     rax, ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEBG@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>::~vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,ushort const *>>>>>>>(void)
0x1800b0c9f  mov     [rsp+228h+var_208], rax; void (*)(void *)
0x1800b0ca4  lea     r9, ??0?$vector@_JV?$allocator@_J@std@@@std@@QEAA@XZ; void (*)(void *)
0x1800b0cab  mov     edx, 18h; unsigned __int64
0x1800b0cb0  lea     r8d, [rdx-12h]; unsigned __int64
0x1800b0cb4  lea     rcx, [rsp+228h+var_108]; void *
0x1800b0cbc  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800b0cc1  xorps   xmm0, xmm0
0x1800b0cc4  movdqa  [rsp+228h+var_78], xmm0
0x1800b0ccd  xorps   xmm1, xmm1
0x1800b0cd0  movdqa  [rsp+228h+var_68], xmm1
0x1800b0cd9  movdqa  [rsp+228h+var_58], xmm0
0x1800b0ce2  lea     rcx, [rsp+228h+var_168]; this
0x1800b0cea  call    ??0CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::CStringInterner(void)
0x1800b0cef  nop
0x1800b0cf0  lea     rax, [rsp+228h+var_168]
0x1800b0cf8  mov     [rsp+228h+var_200], rax; struct PerfDiagShared::Serializer::CStringInterner *
0x1800b0cfd  mov     rax, [rdi+30h]
0x1800b0d01  mov     [rsp+228h+var_208], rax; struct _EVENT_DESCRIPTOR *
0x1800b0d06  mov     r9, [rdi+20h]; struct XPerfAddIn::IProcessInfoSource *
0x1800b0d0a  mov     r8, [rdi+28h]; struct PerfAnalyzer::IPerfAnalyzer *
0x1800b0d0e  mov     rdx, rsi; struct PerfAnalyzer::IPerfAnalyzer::RootCauseData *
0x1800b0d11  lea     rcx, [rsp+228h+var_108]; this
0x1800b0d19  call    ?Summarize@CRootCauseSummary@PerfDiagOutput@@QEAAJPEBURootCauseData@IPerfAnalyzer@PerfAnalyzer@@PEBU45@PEAUIProcessInfoSource@XPerfAddIn@@PEAUIPathRegistry@XPerfCore@@AEAVCStringInterner@Serializer@PerfDiagShared@@@Z; PerfDiagOutput::CRootCauseSummary::Summarize(PerfAnalyzer::IPerfAnalyzer::RootCauseData const *,PerfAnalyzer::IPerfAnalyzer const *,XPerfAddIn::IProcessInfoSource *,XPerfCore::IPathRegistry *,PerfDiagShared::Serializer::CStringInterner &)
0x1800b0d1e  mov     edi, eax
0x1800b0d20  test    eax, eax
0x1800b0d22  jns     short loc_1800B0D5D
0x1800b0d24  lea     rcx, [rsp+228h+var_168]; this
0x1800b0d2c  call    ??1CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::~CStringInterner(void)
0x1800b0d31  nop
0x1800b0d32  lea     rcx, [rsp+228h+var_108]; this
0x1800b0d3a  call    ??1CRootCauseSummary@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CRootCauseSummary::~CRootCauseSummary(void)
0x1800b0d3f  nop
0x1800b0d40  mov     rcx, [rsp+228h+var_1F8]
0x1800b0d45  call    cs:__imp_EtwEventUnregister
0x1800b0d4b  nop
0x1800b0d4c  lea     rcx, [rsp+228h+var_1D8]; this
0x1800b0d51  call    ??1CStdSqmSession@PerfDiagOutput@@QEAA@XZ; PerfDiagOutput::CStdSqmSession::~CStdSqmSession(void)
0x1800b0d56  mov     eax, edi
0x1800b0d58  jmp     loc_1800B0E8A
0x1800b0d5d  mov     rdx, r13
0x1800b0d60  lea     r8, [rdx+rdx*2]
0x1800b0d64  mov     rax, [rsp+r8*8+228h+var_108]
0x1800b0d6c  cmp     rax, [rsp+r8*8+228h+var_100]
0x1800b0d74  jz      short loc_1800B0D82
0x1800b0d76  mov     rcx, [r15]
0x1800b0d79  mov     [rax], rcx
0x1800b0d7c  add     rax, 50h ; 'P'
0x1800b0d80  jmp     short loc_1800B0D6C
0x1800b0d82  add     rdx, rbx
0x1800b0d85  cmp     rdx, 6
0x1800b0d89  jb      short loc_1800B0D60
0x1800b0d8b  mov     rax, qword ptr [rsp+228h+var_78]
0x1800b0d93  cmp     rax, qword ptr [rsp+228h+var_78+8]
0x1800b0d9b  jz      short loc_1800B0DA9
0x1800b0d9d  mov     rcx, [r15]
0x1800b0da0  mov     [rax], rcx
0x1800b0da3  add     rax, 58h ; 'X'
0x1800b0da7  jmp     short loc_1800B0D93
0x1800b0da9  mov     rax, qword ptr [rsp+228h+var_68+8]
0x1800b0db1  cmp     rax, qword ptr [rsp+228h+var_58]
0x1800b0db9  jz      short loc_1800B0DC8
0x1800b0dbb  mov     rcx, [r15]
0x1800b0dbe  mov     [rax+10h], rcx
0x1800b0dc2  add     rax, 18h
0x1800b0dc6  jmp     short loc_1800B0DB1
0x1800b0dc8  lea     rax, PerfDiagShellCpuAppsDegradationEvent
0x1800b0dcf  mov     [rsp+228h+var_1B8], rax
  ... truncated ...
```
