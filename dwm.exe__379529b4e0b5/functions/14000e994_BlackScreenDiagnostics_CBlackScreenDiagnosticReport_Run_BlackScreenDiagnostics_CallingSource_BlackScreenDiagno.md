# BlackScreenDiagnostics::CBlackScreenDiagnosticReport::Run(BlackScreenDiagnostics::CallingSource,BlackScreenDiagnostics::DiagnosticFlags,_GUID const &)

- ea: `0x14000e994`
- end: `0x14000ed05`
- name: `?Run@CBlackScreenDiagnosticReport@BlackScreenDiagnostics@@AEAAXW4CallingSource@2@W4DiagnosticFlags@2@AEBU_GUID@@@Z`
- size: `881`
- prototype: `void __high(enum BlackScreenDiagnostics::CallingSource, enum BlackScreenDiagnostics::DiagnosticFlags, const struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ed0c`

## callees

- `0x140001b5c`
- `0x140001c28`
- `0x140005530`
- `0x14000dff4`
- `0x14000e1f4`
- `0x14000e324`
- `0x14000e6d8`
- `0x14000e750`
- `0x14000e994`
- `0x14000ef18`
- `0x14000f3a4`
- `0x14000f400`
- `0x14000f444`
- `0x14000f4a8`
- `0x14000f500`
- `0x14000f608`

## import_xrefs

- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x14000eaca`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x14000eaca`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x14000ec8c`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerUnregisterCustomMetadata` at `0x14000ec8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000e9eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000e9eb`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14000e9f8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14000e9f8`
- `RPCRT4!RpcStringFreeW` at `0x14000eae3`
- `RPCRT4!RpcStringFreeW` at `0x14000eae3`
- `RPCRT4!UuidToStringW` at `0x14000eaa4`
- `RPCRT4!UuidToStringW` at `0x14000eaa4`
- `ntdll!RtlPublishWnfStateData` at `0x14000ea1e`
- `ntdll!RtlPublishWnfStateData` at `0x14000ea53`
- `ntdll!RtlPublishWnfStateData` at `0x14000ea1e`
- `ntdll!RtlPublishWnfStateData` at `0x14000ea53`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x14000ec1f`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportSubmit` at `0x14000ec1f`

## pseudocode

```c
void __fastcall BlackScreenDiagnostics::CBlackScreenDiagnosticReport::Run(
        BlackScreenDiagnostics::CBlackScreenDiagnosticReport *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char v5; // si
  int v6; // ebx
  __int128 v7; // xmm0
  DWORD CurrentProcessId; // eax
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rbx
  __int64 v14; // rdx
  BlackScreenDiagnostics::CBlackScreenDiagnosticReport *v15; // rcx
  const WCHAR *v16; // r14
  HRESULT v17; // eax
  __int64 v18; // rcx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  const unsigned __int16 *VidPnOwner; // r14
  BlackScreenDiagnostics::CBlackScreenDiagnosticReport *v23; // rcx
  const unsigned __int16 *FrontBufferColorMap; // r15
  const unsigned __int16 *v25; // r8
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  HRESULT v29; // eax
  __int64 v30; // rcx
  _WER_SUBMIT_RESULT pSubmitResult[2]; // [rsp+30h] [rbp-D0h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v34[2]; // [rsp+48h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+58h] [rbp-A8h]
  __int128 v36; // [rsp+68h] [rbp-98h] BYREF
  DWORD pSessionId[2]; // [rsp+78h] [rbp-88h] BYREF
  HREPORT hReportHandle[14]; // [rsp+80h] [rbp-80h] BYREF

  v5 = (char)a3;
  v6 = (int)a2;
  if ( ((unsigned __int8)a3 & 3) == 0 )
    goto LABEL_37;
  if ( (_DWORD)a2 == 1 )
    goto LABEL_11;
  v7 = *(_OWORD *)a4;
  pSessionId[1] = 0;
  v36 = v7;
  pSessionId[0] = 1;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId[1]);
  v9 = RtlPublishWnfStateData(WNF_DWM_DUMP_REQUEST, 0, &v36, 24, 0) | 0x10000000;
  if ( v9 < 0 )
    MicrosoftTelemetryAssertTriggeredArgs(v10, (unsigned int)v9, 0);
  v11 = RtlPublishWnfStateData(WNF_DWM_DUMP_REQUEST_FOR_SERVICE, 0, &v36, 24, 0) | 0x10000000;
  if ( v11 < 0 )
    MicrosoftTelemetryAssertTriggeredArgs(v12, (unsigned int)v11, 0);
  if ( !v6 )
  {
    v13 = L"Hotkey";
    goto LABEL_12;
  }
  if ( v6 == 1 )
  {
LABEL_11:
    v13 = L"LongPowerButtonHold";
    goto LABEL_12;
  }
  v13 = L"Unknown";
LABEL_12:
  BlackScreenDiagnostics::CWatsonErrorReporting::CWatsonErrorReporting(
    (BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle,
    a2,
    a3,
    a4);
  StringUuid = 0;
  if ( !UuidToStringW((const UUID *)a4, &StringUuid) )
  {
    v16 = StringUuid;
    if ( BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(hReportHandle) )
    {
      v17 = WerRegisterCustomMetadata(L"BlackScreenInstanceGuid", v16);
      if ( v17 < 0 )
        MicrosoftTelemetryAssertTriggeredArgs(v18, (unsigned int)v17, 0);
    }
    RpcStringFreeW(&StringUuid);
  }
  if ( (v5 & 2) != 0 )
  {
    if ( (unsigned int)dword_1400180D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400180D8, 0x800000000000LL) )
    {
      *(_QWORD *)pSubmitResult = a4;
      v33 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
        v19,
        (unsigned int)&byte_140013EB7,
        v20,
        v21,
        (__int64)&v33,
        (__int64)pSubmitResult);
    }
    LOBYTE(v14) = 1;
    BlackScreenDiagnostics::TriggerGraphicsCollection(0, v14, a4);
  }
  VidPnOwner = BlackScreenDiagnostics::CBlackScreenDiagnosticReport::GetVidPnOwner(v15);
  FrontBufferColorMap = BlackScreenDiagnostics::CBlackScreenDiagnosticReport::GetFrontBufferColorMap(v23);
  if ( (v5 & 1) != 0 )
    BlackScreenDiagnostics::CWatsonErrorReporting::CollectCurrentProcessHeapDump((BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle);
  BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(
    (BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle,
    0,
    VidPnOwner);
  BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(
    (BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle,
    1u,
    L"Unknown");
  BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(
    (BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle,
    2u,
    FrontBufferColorMap);
  BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(
    (BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle,
    3u,
    v13);
  *(_OWORD *)v34 = 0;
  LOWORD(v34[0]) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  BlackScreenDiagnostics::GetCurrentProcessVersionInfo(v34);
  v25 = (const unsigned __int16 *)v34;
  if ( si128.m128i_i64[1] > 7uLL )
    v25 = v34[0];
  BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(
    (BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle,
    4u,
    v25);
  pSubmitResult[0] = WerCustomAction|WerReportFailed;
  if ( BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(hReportHandle) )
    WerReportSubmit(hReportHandle[0], WerConsentNotAsked, 4u, pSubmitResult);
  if ( (unsigned int)dword_1400180D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400180D8, 0x800000000000LL) )
  {
    v33 = (__int64)a4;
    *(_QWORD *)pSubmitResult = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      v26,
      (unsigned int)byte_140013E0B,
      v27,
      v28,
      (__int64)pSubmitResult,
      (__int64)&v33);
  }
  if ( BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(hReportHandle) )
  {
    v29 = WerUnregisterCustomMetadata(L"BlackScreenInstanceGuid");
    if ( v29 < 0 )
      MicrosoftTelemetryAssertTriggeredArgs(v30, (unsigned int)v29, 0);
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v34[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v34[0]) = 0;
  BlackScreenDiagnostics::CWatsonErrorReporting::~CWatsonErrorReporting((BlackScreenDiagnostics::CWatsonErrorReporting *)hReportHandle);
LABEL_37:
  if ( (v5 & 4) != 0 )
    BlackScreenDiagnostics::CBlackScreenDiagnosticReport::DoDisplayModeReset(a1, (const struct _GUID *)a4);
}

```

## disassembly

```asm
0x14000e994  push    rbp
0x14000e996  push    rbx
0x14000e997  push    rsi
0x14000e998  push    rdi
0x14000e999  push    r14
0x14000e99b  push    r15
0x14000e99d  lea     rbp, [rsp-8]
0x14000e9a2  sub     rsp, 108h
0x14000e9a9  mov     rax, cs:__security_cookie
0x14000e9b0  xor     rax, rsp
0x14000e9b3  mov     [rbp+30h+var_40], rax
0x14000e9b7  mov     rdi, r9
0x14000e9ba  mov     esi, r8d
0x14000e9bd  mov     ebx, edx
0x14000e9bf  test    r8b, 3
0x14000e9c3  jz      loc_14000ECDB
0x14000e9c9  cmp     edx, 1
0x14000e9cc  jz      loc_14000EA83
0x14000e9d2  movups  xmm0, xmmword ptr [r9]
0x14000e9d6  xor     eax, eax
0x14000e9d8  mov     qword ptr [rsp+130h+pSessionId], rax
0x14000e9dd  movdqu  [rsp+130h+var_C8], xmm0
0x14000e9e3  mov     [rsp+130h+pSessionId], 1
0x14000e9eb  call    cs:__imp_GetCurrentProcessId
0x14000e9f1  mov     ecx, eax; dwProcessId
0x14000e9f3  lea     rdx, [rsp+130h+pSessionId+4]; pSessionId
0x14000e9f8  call    cs:__imp_ProcessIdToSessionId
0x14000e9fe  mov     rcx, cs:WNF_DWM_DUMP_REQUEST
0x14000ea05  lea     r8, [rsp+130h+var_C8]
0x14000ea0a  mov     r14d, 18h
0x14000ea10  mov     [rsp+130h+var_110], 0
0x14000ea19  mov     r9d, r14d
0x14000ea1c  xor     edx, edx
0x14000ea1e  call    cs:__imp_RtlPublishWnfStateData
0x14000ea24  mov     r15d, 10000000h
0x14000ea2a  or      eax, r15d
0x14000ea2d  jge     short loc_14000EA39
0x14000ea2f  xor     r8d, r8d
0x14000ea32  mov     edx, eax
0x14000ea34  call    MicrosoftTelemetryAssertTriggeredArgs
0x14000ea39  mov     rcx, cs:WNF_DWM_DUMP_REQUEST_FOR_SERVICE
0x14000ea40  lea     r8, [rsp+130h+var_C8]
0x14000ea45  mov     r9d, r14d
0x14000ea48  mov     [rsp+130h+var_110], 0
0x14000ea51  xor     edx, edx
0x14000ea53  call    cs:__imp_RtlPublishWnfStateData
0x14000ea59  or      eax, r15d
0x14000ea5c  jge     short loc_14000EA68
0x14000ea5e  xor     r8d, r8d
0x14000ea61  mov     edx, eax
0x14000ea63  call    MicrosoftTelemetryAssertTriggeredArgs
0x14000ea68  test    ebx, ebx
0x14000ea6a  jz      short loc_14000EA7A
0x14000ea6c  cmp     ebx, 1
0x14000ea6f  jz      short loc_14000EA83
0x14000ea71  lea     rbx, aUnknown; "Unknown"
0x14000ea78  jmp     short loc_14000EA8A
0x14000ea7a  lea     rbx, aHotkey; "Hotkey"
0x14000ea81  jmp     short loc_14000EA8A
0x14000ea83  lea     rbx, aLongpowerbutto; "LongPowerButtonHold"
0x14000ea8a  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000ea8e  call    ??0CWatsonErrorReporting@BlackScreenDiagnostics@@QEAA@PEBG00@Z; BlackScreenDiagnostics::CWatsonErrorReporting::CWatsonErrorReporting(ushort const *,ushort const *,ushort const *)
0x14000ea93  lea     rdx, [rsp+130h+StringUuid]; StringUuid
0x14000ea98  mov     [rsp+130h+StringUuid], 0
0x14000eaa1  mov     rcx, rdi; Uuid
0x14000eaa4  call    cs:__imp_UuidToStringW
0x14000eaaa  test    eax, eax
0x14000eaac  jnz     short loc_14000EAE9
0x14000eaae  mov     r14, [rsp+130h+StringUuid]
0x14000eab3  lea     rcx, [rbp+30h+hReportHandle]; phReportHandle
0x14000eab7  call    ?TryInit@CWatsonErrorReporting@BlackScreenDiagnostics@@AEAA_NXZ; BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(void)
0x14000eabc  test    al, al
0x14000eabe  jz      short loc_14000EADE
0x14000eac0  mov     rdx, r14; value
0x14000eac3  lea     rcx, key; "BlackScreenInstanceGuid"
0x14000eaca  call    cs:__imp_WerRegisterCustomMetadata
0x14000ead0  test    eax, eax
0x14000ead2  jns     short loc_14000EADE
0x14000ead4  xor     r8d, r8d
0x14000ead7  mov     edx, eax
0x14000ead9  call    MicrosoftTelemetryAssertTriggeredArgs
0x14000eade  lea     rcx, [rsp+130h+StringUuid]; String
0x14000eae3  call    cs:__imp_RpcStringFreeW
0x14000eae9  test    sil, 2
0x14000eaed  jz      short loc_14000EB4E
0x14000eaef  mov     eax, cs:dword_1400180D8
0x14000eaf5  cmp     eax, 5
0x14000eaf8  jbe     short loc_14000EB42
0x14000eafa  mov     rdx, 800000000000h
0x14000eb04  lea     rcx, dword_1400180D8
0x14000eb0b  call    _tlgKeywordOn
0x14000eb10  test    al, al
0x14000eb12  jz      short loc_14000EB42
0x14000eb14  lea     rax, [rsp+130h+pSubmitResult]
0x14000eb19  mov     qword ptr [rsp+130h+pSubmitResult], rdi
0x14000eb1e  mov     [rsp+130h+var_108], rax
0x14000eb23  lea     rdx, byte_140013EB7
0x14000eb2a  lea     rax, [rsp+130h+var_F0]
0x14000eb2f  mov     [rsp+130h+var_F0], 1000000h
0x14000eb38  mov     [rsp+130h+var_110], rax
0x14000eb3d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x14000eb42  mov     r8, rdi
0x14000eb45  mov     dl, 1
0x14000eb47  xor     ecx, ecx
0x14000eb49  call    BlackScreenDiagnostics__TriggerGraphicsCollection
0x14000eb4e  call    ?GetVidPnOwner@CBlackScreenDiagnosticReport@BlackScreenDiagnostics@@AEAAPEBGXZ; BlackScreenDiagnostics::CBlackScreenDiagnosticReport::GetVidPnOwner(void)
0x14000eb53  mov     r14, rax
0x14000eb56  call    ?GetFrontBufferColorMap@CBlackScreenDiagnosticReport@BlackScreenDiagnostics@@AEAAPEBGXZ; BlackScreenDiagnostics::CBlackScreenDiagnosticReport::GetFrontBufferColorMap(void)
0x14000eb5b  mov     r15, rax
0x14000eb5e  test    sil, 1
0x14000eb62  jz      short loc_14000EB6D
0x14000eb64  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000eb68  call    ?CollectCurrentProcessHeapDump@CWatsonErrorReporting@BlackScreenDiagnostics@@QEAAXXZ; BlackScreenDiagnostics::CWatsonErrorReporting::CollectCurrentProcessHeapDump(void)
0x14000eb6d  mov     r8, r14; unsigned __int16 *
0x14000eb70  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000eb74  xor     edx, edx; unsigned int
0x14000eb76  call    ?SetReportParameter@CWatsonErrorReporting@BlackScreenDiagnostics@@QEAAXKPEBG@Z; BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(ulong,ushort const *)
0x14000eb7b  lea     r8, aUnknown; "Unknown"
0x14000eb82  mov     edx, 1; unsigned int
0x14000eb87  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000eb8b  call    ?SetReportParameter@CWatsonErrorReporting@BlackScreenDiagnostics@@QEAAXKPEBG@Z; BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(ulong,ushort const *)
0x14000eb90  mov     r8, r15; unsigned __int16 *
0x14000eb93  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000eb97  mov     edx, 2; unsigned int
0x14000eb9c  call    ?SetReportParameter@CWatsonErrorReporting@BlackScreenDiagnostics@@QEAAXKPEBG@Z; BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(ulong,ushort const *)
0x14000eba1  mov     r8, rbx; unsigned __int16 *
0x14000eba4  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000eba8  mov     edx, 3; unsigned int
0x14000ebad  call    ?SetReportParameter@CWatsonErrorReporting@BlackScreenDiagnostics@@QEAAXKPEBG@Z; BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(ulong,ushort const *)
0x14000ebb2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000ebba  lea     rcx, [rsp+130h+var_E8]
0x14000ebbf  xorps   xmm0, xmm0
0x14000ebc2  xor     eax, eax
0x14000ebc4  movups  xmmword ptr [rsp+130h+var_E8], xmm0
0x14000ebc9  mov     word ptr [rsp+130h+var_E8], ax
0x14000ebce  movdqu  [rsp+130h+var_D8], xmm1
0x14000ebd4  call    BlackScreenDiagnostics__GetCurrentProcessVersionInfo
0x14000ebd9  cmp     qword ptr [rsp+130h+var_D8+8], 7
0x14000ebdf  lea     r8, [rsp+130h+var_E8]
0x14000ebe4  mov     edx, 4; unsigned int
0x14000ebe9  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000ebed  cmova   r8, [rsp+130h+var_E8]; unsigned __int16 *
0x14000ebf3  call    ?SetReportParameter@CWatsonErrorReporting@BlackScreenDiagnostics@@QEAAXKPEBG@Z; BlackScreenDiagnostics::CWatsonErrorReporting::SetReportParameter(ulong,ushort const *)
0x14000ebf8  lea     rcx, [rbp+30h+hReportHandle]; phReportHandle
0x14000ebfc  mov     [rsp+130h+pSubmitResult], 0Dh
0x14000ec04  call    ?TryInit@CWatsonErrorReporting@BlackScreenDiagnostics@@AEAA_NXZ; BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(void)
0x14000ec09  test    al, al
0x14000ec0b  jz      short loc_14000EC25
0x14000ec0d  mov     rcx, [rbp+30h+hReportHandle]; hReportHandle
0x14000ec11  lea     r9, [rsp+130h+pSubmitResult]; pSubmitResult
0x14000ec16  mov     edx, 1; consent
0x14000ec1b  lea     r8d, [rdx+3]; dwFlags
0x14000ec1f  call    cs:__imp_WerReportSubmit
0x14000ec25  mov     eax, cs:dword_1400180D8
0x14000ec2b  cmp     eax, 5
0x14000ec2e  jbe     short loc_14000EC78
0x14000ec30  mov     rdx, 800000000000h
0x14000ec3a  lea     rcx, dword_1400180D8
0x14000ec41  call    _tlgKeywordOn
0x14000ec46  test    al, al
0x14000ec48  jz      short loc_14000EC78
0x14000ec4a  lea     rax, [rsp+130h+var_F0]
0x14000ec4f  mov     [rsp+130h+var_F0], rdi
0x14000ec54  mov     [rsp+130h+var_108], rax
0x14000ec59  lea     rdx, byte_140013E0B
0x14000ec60  lea     rax, [rsp+130h+pSubmitResult]
0x14000ec65  mov     qword ptr [rsp+130h+pSubmitResult], 1000000h
0x14000ec6e  mov     [rsp+130h+var_110], rax
0x14000ec73  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x14000ec78  lea     rcx, [rbp+30h+hReportHandle]; phReportHandle
0x14000ec7c  call    ?TryInit@CWatsonErrorReporting@BlackScreenDiagnostics@@AEAA_NXZ; BlackScreenDiagnostics::CWatsonErrorReporting::TryInit(void)
0x14000ec81  test    al, al
0x14000ec83  jz      short loc_14000ECA0
0x14000ec85  lea     rcx, key; "BlackScreenInstanceGuid"
0x14000ec8c  call    cs:__imp_WerUnregisterCustomMetadata
0x14000ec92  test    eax, eax
0x14000ec94  jns     short loc_14000ECA0
0x14000ec96  xor     r8d, r8d
0x14000ec99  mov     edx, eax
0x14000ec9b  call    MicrosoftTelemetryAssertTriggeredArgs
0x14000eca0  mov     rdx, qword ptr [rsp+130h+var_D8+8]
0x14000eca5  cmp     rdx, 7
0x14000eca9  jbe     short loc_14000ECBD
0x14000ecab  mov     rcx, [rsp+130h+var_E8]
0x14000ecb0  lea     rdx, ds:2[rdx*2]
0x14000ecb8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000ecbd  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14000ecc5  lea     rcx, [rbp+30h+hReportHandle]; this
0x14000ecc9  xor     eax, eax
0x14000eccb  movdqu  [rsp+130h+var_D8], xmm0
0x14000ecd1  mov     word ptr [rsp+130h+var_E8], ax
0x14000ecd6  call    ??1CWatsonErrorReporting@BlackScreenDiagnostics@@QEAA@XZ; BlackScreenDiagnostics::CWatsonErrorReporting::~CWatsonErrorReporting(void)
0x14000ecdb  test    sil, 4
0x14000ecdf  jz      short loc_14000ECE9
0x14000ece1  mov     rdx, rdi; struct _GUID *
0x14000ece4  call    ?DoDisplayModeReset@CBlackScreenDiagnosticReport@BlackScreenDiagnostics@@AEAAXAEBU_GUID@@@Z; BlackScreenDiagnostics::CBlackScreenDiagnosticReport::DoDisplayModeReset(_GUID const &)
0x14000ece9  mov     rcx, [rbp+30h+var_40]
0x14000eced  xor     rcx, rsp; StackCookie
0x14000ecf0  call    __security_check_cookie
0x14000ecf5  add     rsp, 108h
0x14000ecfc  pop     r15
0x14000ecfe  pop     r14
0x14000ed00  pop     rdi
0x14000ed01  pop     rsi
0x14000ed02  pop     rbx
0x14000ed03  pop     rbp
0x14000ed04  retn
```
