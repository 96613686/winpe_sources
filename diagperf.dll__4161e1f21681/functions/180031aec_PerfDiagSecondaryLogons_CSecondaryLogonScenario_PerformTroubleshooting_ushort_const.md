# PerfDiagSecondaryLogons::CSecondaryLogonScenario::PerformTroubleshooting(ushort const *)

- ea: `0x180031aec`
- end: `0x180031e2b`
- name: `?PerformTroubleshooting@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAJPEBG@Z`
- size: `831`
- prototype: `int(PerfDiagSecondaryLogons::CSecondaryLogonScenario *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ba5f0`

## callees

- `0x180016a1c`
- `0x18001769c`
- `0x1800282a4`
- `0x180028f6c`
- `0x18002b1b0`
- `0x180031aec`
- `0x180031e34`
- `0x180031e64`
- `0x18003268c`
- `0x180032e50`
- `0x18003de84`
- `0x18003df28`
- `0x1800421b8`
- `0x1800421dc`
- `0x180043030`
- `0x1800c6530`
- `0x1800c676c`
- `0x1800c6968`
- `0x1800c6c24`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180031bbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180031bbb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180031cf9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180031cf9`
- `KERNEL32!LocalFree` at `0x180031d6a`
- `KERNEL32!LocalFree` at `0x180031d6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::PerformTroubleshooting(
        PerfDiagSecondaryLogons::CSecondaryLogonScenario *this,
        const unsigned __int16 *a2)
{
  HINSTANCE v4; // rdx
  void **v5; // r9
  int v6; // ebx
  size_t v7; // r9
  int Error; // eax
  unsigned int v10; // ebx
  unsigned int UserSIDFromTrace; // ebx
  PSID v12; // rbx
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  unsigned int v15; // r9d
  unsigned int v16; // eax
  const unsigned __int16 *v17; // r9
  int v18; // [rsp+20h] [rbp-378h] BYREF
  struct _GUID v19; // [rsp+28h] [rbp-370h] BYREF
  PSID Sid; // [rsp+38h] [rbp-360h] BYREF
  _BYTE *v21; // [rsp+40h] [rbp-358h] BYREF
  int v22; // [rsp+48h] [rbp-350h]
  PSID v23; // [rsp+50h] [rbp-348h]
  _QWORD v24[3]; // [rsp+58h] [rbp-340h] BYREF
  _BYTE v25[64]; // [rsp+70h] [rbp-328h] BYREF
  _BYTE v26[192]; // [rsp+B0h] [rbp-2E8h] BYREF
  WCHAR Buffer[264]; // [rsp+170h] [rbp-228h] BYREF

  PerfDiagDm::ThreadPriorityContext::ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v18, 0x10000);
  *(_QWORD *)&v19.Data1 = 0;
  v6 = XPerfCore::XPerfCoreCreateAddInManager((XPerfCore *)hInstance, v4, &v19, v5);
  if ( v6 < 0
    || (v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&v19.Data1 + 24LL))(*(_QWORD *)&v19.Data1, 0),
        v6 < 0)
    || ((memset_0(Buffer, 0, 0x208u), GetSystemDirectoryW(Buffer, 0x104u))
      ? (Error = StringCchCatW(Buffer, 0x104u, L"\\WDI\\LogFiles\\SecondaryLogonPerfDiagLogger.etl", v7))
      : (Error = ATL::AtlHresultFromLastError()),
        v6 = Error,
        Error < 0) )
  {
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v19);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v18);
    return (unsigned int)v6;
  }
  PerfDiagSecondaryLogons::CTraceContext::CTraceContext((PerfDiagSecondaryLogons::CTraceContext *)v26);
  v10 = PerfDiagSecondaryLogons::CTraceContext::Open(
          (PerfDiagSecondaryLogons::CTraceContext *)v26,
          *(struct XPerfCore::IAddInManager **)&v19.Data1,
          Buffer,
          a2);
  if ( v10 )
  {
    PerfDiagSecondaryLogons::CTraceContext::~CTraceContext((PerfDiagSecondaryLogons::CTraceContext *)v26);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v19);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v18);
    return v10;
  }
  v21 = 0;
  v22 = 0;
  v23 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v24);
  Sid = 0;
  *(_QWORD *)v19.Data4 = 0;
  UserSIDFromTrace = PerfDiagSecondaryLogons::CTraceContext::GetUserSIDFromTrace(
                       (PerfDiagSecondaryLogons::CTraceContext *)v26,
                       (const struct _SID **)&Sid,
                       *((_DWORD *)this + 12));
  if ( UserSIDFromTrace )
    goto LABEL_12;
  v12 = Sid;
  if ( !ConvertSidToStringSidW(Sid, (LPWSTR *)v19.Data4) )
  {
    LastError = GetLastError();
    UserSIDFromTrace = LastError;
    if ( LastError > 0 )
      UserSIDFromTrace = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
    ATL::CStringData::Release((ATL::CStringData *)(v24[0] - 24LL));
    PerfDiagSecondaryLogons::CTraceContext::~CTraceContext((PerfDiagSecondaryLogons::CTraceContext *)v26);
    ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v19);
    PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v18);
    return UserSIDFromTrace;
  }
  v23 = v12;
  ATL::CSimpleStringT<unsigned short,0>::SetString(v24, *(_QWORD *)v19.Data4);
  LocalFree(*(HLOCAL *)v19.Data4);
  PerfDiagShared::Serializer::CStringInterner::CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v25);
  v21 = v25;
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_RurAppResourceUsage_Start, v14);
  v16 = PerfDiagSecondaryLogons::RurAnalysisPerform(
          (PerfDiagSecondaryLogons *)&v21,
          (const struct PerfDiagSecondaryLogons::CAnalysisContext *)v26,
          (const struct PerfDiagSecondaryLogons::CTraceContext *)*((unsigned int *)this + 12),
          v15);
  PerfDiagOutput::StatusLog::Write(
    (PerfDiagOutput::StatusLog *)PDEvt_Boot_RurAppResourceUsage_Stop,
    (const struct _EVENT_DESCRIPTOR *)v16,
    0,
    v17);
  PerfDiagShared::Serializer::CStringInterner::~CStringInterner((PerfDiagShared::Serializer::CStringInterner *)v25);
  ATL::CStringData::Release((ATL::CStringData *)(v24[0] - 24LL));
  PerfDiagSecondaryLogons::CTraceContext::~CTraceContext((PerfDiagSecondaryLogons::CTraceContext *)v26);
  ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(&v19);
  PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext((PerfDiagDm::ThreadPriorityContext *)&v18);
  return 0;
}

```

## disassembly

```asm
0x180031aec  mov     [rsp+arg_10], rbx
0x180031af1  mov     [rsp+arg_18], rsi
0x180031af6  push    rdi
0x180031af7  sub     rsp, 390h
0x180031afe  mov     rax, cs:__security_cookie
0x180031b05  xor     rax, rsp
0x180031b08  mov     [rsp+398h+var_18], rax
0x180031b10  mov     rsi, rdx
0x180031b13  mov     rdi, rcx
0x180031b16  mov     edx, 10000h; int
0x180031b1b  lea     rcx, [rsp+398h+var_378]; this
0x180031b20  call    ??0ThreadPriorityContext@PerfDiagDm@@QEAA@H@Z; PerfDiagDm::ThreadPriorityContext::ThreadPriorityContext(int)
0x180031b25  nop
0x180031b26  mov     qword ptr [rsp+398h+var_370.Data1], 0
0x180031b2f  lea     r8, [rsp+398h+var_370]; struct _GUID *
0x180031b34  mov     rcx, cs:hInstance; this
0x180031b3b  call    ?XPerfCoreCreateAddInManager@XPerfCore@@YAJPEAUHINSTANCE__@@AEBU_GUID@@PEAPEAX@Z; XPerfCore::XPerfCoreCreateAddInManager(HINSTANCE__ *,_GUID const &,void * *)
0x180031b40  mov     ebx, eax
0x180031b42  test    eax, eax
0x180031b44  jns     short loc_180031B62
0x180031b46  lea     rcx, [rsp+398h+var_370]
0x180031b4b  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180031b50  nop
0x180031b51  lea     rcx, [rsp+398h+var_378]; this
0x180031b56  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180031b5b  mov     eax, ebx
0x180031b5d  jmp     loc_180031E05
0x180031b62  mov     rcx, qword ptr [rsp+398h+var_370.Data1]
0x180031b67  mov     rax, [rcx]
0x180031b6a  xor     edx, edx
0x180031b6c  mov     rax, [rax+18h]
0x180031b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b75  mov     ebx, eax
0x180031b77  test    eax, eax
0x180031b79  jns     short loc_180031B97
0x180031b7b  lea     rcx, [rsp+398h+var_370]
0x180031b80  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180031b85  nop
0x180031b86  lea     rcx, [rsp+398h+var_378]; this
0x180031b8b  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180031b90  mov     eax, ebx
0x180031b92  jmp     loc_180031E05
0x180031b97  xor     edx, edx; Val
0x180031b99  mov     r8d, 208h; Size
0x180031b9f  lea     rcx, [rsp+398h+Buffer]; void *
0x180031ba7  call    memset_0
0x180031bac  mov     ebx, 104h
0x180031bb1  mov     edx, ebx; uSize
0x180031bb3  lea     rcx, [rsp+398h+Buffer]; lpBuffer
0x180031bbb  call    cs:__imp_GetSystemDirectoryW
0x180031bc1  test    eax, eax
0x180031bc3  jnz     short loc_180031BCC
0x180031bc5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180031bca  jmp     short loc_180031BE3
0x180031bcc  lea     r8, aWdiLogfilesSec; "\\WDI\\LogFiles\\SecondaryLogonPerfDiag"...
0x180031bd3  mov     rdx, rbx; unsigned __int64
0x180031bd6  lea     rcx, [rsp+398h+Buffer]; unsigned __int16 *
0x180031bde  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031be3  test    eax, eax
0x180031be5  mov     ebx, eax
0x180031be7  jns     short loc_180031C05
0x180031be9  lea     rcx, [rsp+398h+var_370]
0x180031bee  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180031bf3  nop
0x180031bf4  lea     rcx, [rsp+398h+var_378]; this
0x180031bf9  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180031bfe  mov     eax, ebx
0x180031c00  jmp     loc_180031E05
0x180031c05  lea     rcx, [rsp+398h+var_2E8]; this
0x180031c0d  call    ??0CTraceContext@PerfDiagSecondaryLogons@@QEAA@XZ; PerfDiagSecondaryLogons::CTraceContext::CTraceContext(void)
0x180031c12  nop
0x180031c13  mov     r9, rsi; unsigned __int16 *
0x180031c16  lea     r8, [rsp+398h+Buffer]; unsigned __int16 *
0x180031c1e  mov     rdx, qword ptr [rsp+398h+var_370.Data1]; struct XPerfCore::IAddInManager *
0x180031c23  lea     rcx, [rsp+398h+var_2E8]; this
0x180031c2b  call    ?Open@CTraceContext@PerfDiagSecondaryLogons@@QEAAJPEAUIAddInManager@XPerfCore@@PEBG1@Z; PerfDiagSecondaryLogons::CTraceContext::Open(XPerfCore::IAddInManager *,ushort const *,ushort const *)
0x180031c30  mov     ebx, eax
0x180031c32  test    eax, eax
0x180031c34  jz      short loc_180031C60
0x180031c36  lea     rcx, [rsp+398h+var_2E8]; this
0x180031c3e  call    ??1CTraceContext@PerfDiagSecondaryLogons@@QEAA@XZ; PerfDiagSecondaryLogons::CTraceContext::~CTraceContext(void)
0x180031c43  nop
0x180031c44  lea     rcx, [rsp+398h+var_370]
0x180031c49  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180031c4e  nop
0x180031c4f  lea     rcx, [rsp+398h+var_378]; this
0x180031c54  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180031c59  mov     eax, ebx
0x180031c5b  jmp     loc_180031E05
0x180031c60  mov     [rsp+398h+var_358], 0
0x180031c69  mov     [rsp+398h+var_350], 0
0x180031c71  mov     [rsp+398h+var_348], 0
0x180031c7a  lea     rcx, [rsp+398h+var_340]
0x180031c7f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180031c84  nop
0x180031c85  mov     [rsp+398h+Sid], 0
0x180031c8e  mov     qword ptr [rsp+398h+var_370.Data4], 0
0x180031c97  mov     r8d, [rdi+30h]; unsigned int
0x180031c9b  lea     rdx, [rsp+398h+Sid]; struct _SID **
0x180031ca0  lea     rcx, [rsp+398h+var_2E8]; this
0x180031ca8  call    ?GetUserSIDFromTrace@CTraceContext@PerfDiagSecondaryLogons@@QEAAJAEAPEBU_SID@@K@Z; PerfDiagSecondaryLogons::CTraceContext::GetUserSIDFromTrace(_SID const * &,ulong)
0x180031cad  mov     ebx, eax
0x180031caf  test    eax, eax
0x180031cb1  jz      short loc_180031CEC
0x180031cb3  mov     rcx, [rsp+398h+var_340]
0x180031cb8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031cbc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031cc1  nop
0x180031cc2  lea     rcx, [rsp+398h+var_2E8]; this
0x180031cca  call    ??1CTraceContext@PerfDiagSecondaryLogons@@QEAA@XZ; PerfDiagSecondaryLogons::CTraceContext::~CTraceContext(void)
0x180031ccf  nop
0x180031cd0  lea     rcx, [rsp+398h+var_370]
0x180031cd5  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180031cda  nop
0x180031cdb  lea     rcx, [rsp+398h+var_378]; this
0x180031ce0  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180031ce5  mov     eax, ebx
0x180031ce7  jmp     loc_180031E05
0x180031cec  lea     rdx, [rsp+398h+var_370.Data4]; StringSid
0x180031cf1  mov     rbx, [rsp+398h+Sid]
0x180031cf6  mov     rcx, rbx; Sid
0x180031cf9  call    cs:__imp_ConvertSidToStringSidW
0x180031cff  test    eax, eax
0x180031d01  jnz     short loc_180031D51
0x180031d03  call    cs:__imp_GetLastError
0x180031d09  mov     ebx, eax
0x180031d0b  test    eax, eax
0x180031d0d  jle     short loc_180031D18
0x180031d0f  movzx   ebx, ax
0x180031d12  or      ebx, 80070000h
0x180031d18  mov     rcx, [rsp+398h+var_340]
0x180031d1d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031d21  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031d26  nop
0x180031d27  lea     rcx, [rsp+398h+var_2E8]; this
0x180031d2f  call    ??1CTraceContext@PerfDiagSecondaryLogons@@QEAA@XZ; PerfDiagSecondaryLogons::CTraceContext::~CTraceContext(void)
0x180031d34  nop
0x180031d35  lea     rcx, [rsp+398h+var_370]
0x180031d3a  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180031d3f  nop
0x180031d40  lea     rcx, [rsp+398h+var_378]; this
0x180031d45  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180031d4a  mov     eax, ebx
0x180031d4c  jmp     loc_180031E05
0x180031d51  mov     [rsp+398h+var_348], rbx
0x180031d56  mov     rdx, qword ptr [rsp+398h+var_370.Data4]
0x180031d5b  lea     rcx, [rsp+398h+var_340]
0x180031d60  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180031d65  mov     rcx, qword ptr [rsp+398h+var_370.Data4]; hMem
0x180031d6a  call    cs:__imp_LocalFree
0x180031d70  lea     rcx, [rsp+398h+var_328]; this
0x180031d75  call    ??0CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::CStringInterner(void)
0x180031d7a  nop
0x180031d7b  lea     rax, [rsp+398h+var_328]
0x180031d80  mov     [rsp+398h+var_358], rax
0x180031d85  lea     rcx, PDEvt_Boot_RurAppResourceUsage_Start; this
0x180031d8c  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x180031d91  mov     r8d, [rdi+30h]; struct PerfDiagSecondaryLogons::CTraceContext *
0x180031d95  lea     rdx, [rsp+398h+var_2E8]; struct PerfDiagSecondaryLogons::CAnalysisContext *
0x180031d9d  lea     rcx, [rsp+398h+var_358]; this
0x180031da2  call    ?RurAnalysisPerform@PerfDiagSecondaryLogons@@YAJAEBUCAnalysisContext@1@AEBVCTraceContext@1@K@Z; PerfDiagSecondaryLogons::RurAnalysisPerform(PerfDiagSecondaryLogons::CAnalysisContext const &,PerfDiagSecondaryLogons::CTraceContext const &,ulong)
0x180031da7  xor     r8d, r8d; unsigned int
0x180031daa  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x180031dac  lea     rcx, PDEvt_Boot_RurAppResourceUsage_Stop; this
0x180031db3  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x180031db8  nop
0x180031db9  lea     rcx, [rsp+398h+var_328]; this
0x180031dbe  call    ??1CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::~CStringInterner(void)
0x180031dc3  nop
0x180031dc4  mov     rcx, [rsp+398h+var_340]
0x180031dc9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031dcd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031dd2  nop
0x180031dd3  lea     rcx, [rsp+398h+var_2E8]; this
0x180031ddb  call    ??1CTraceContext@PerfDiagSecondaryLogons@@QEAA@XZ; PerfDiagSecondaryLogons::CTraceContext::~CTraceContext(void)
0x180031de0  nop
0x180031de1  lea     rcx, [rsp+398h+var_370]
0x180031de6  call    ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
0x180031deb  nop
0x180031dec  lea     rcx, [rsp+398h+var_378]; this
0x180031df1  call    ??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ; PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)
0x180031df6  xor     eax, eax
0x180031df8  jmp     short loc_180031E05
0x180031dfa  mov     eax, 8007000Eh
0x180031dff  jmp     short loc_180031E05
0x180031e01  mov     eax, [rsp+398h+var_378]
0x180031e05  mov     rcx, [rsp+398h+var_18]
0x180031e0d  xor     rcx, rsp; StackCookie
0x180031e10  call    __security_check_cookie
0x180031e15  lea     r11, [rsp+398h+var_8]
0x180031e1d  mov     rbx, [r11+20h]
0x180031e21  mov     rsi, [r11+28h]
0x180031e25  mov     rsp, r11
0x180031e28  pop     rdi
0x180031e29  retn
```
