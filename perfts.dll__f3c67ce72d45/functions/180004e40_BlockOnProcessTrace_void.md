# BlockOnProcessTrace(void *)

- ea: `0x180004e40`
- end: `0x18000536f`
- name: `?BlockOnProcessTrace@@YAKPEAX@Z`
- size: `1327`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180001098`
- `0x180001da8`
- `0x1800047fc`
- `0x180004d5c`
- `0x180004e40`
- `0x180006c50`
- `0x18000823c`
- `0x1800098f6`
- `0x180009930`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000530b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005315`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005322`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000532c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005339`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005343`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000534e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000530b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005315`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005322`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000532c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005339`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005343`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000534e`
- `KERNEL32!SetEvent` at `0x18000526f`
- `KERNEL32!SetEvent` at `0x18000526f`
- `KERNEL32!GetLastError` at `0x18000512d`
- `KERNEL32!GetLastError` at `0x180005163`
- `KERNEL32!GetLastError` at `0x180005178`
- `KERNEL32!GetLastError` at `0x1800051ae`
- `KERNEL32!GetLastError` at `0x1800051c5`
- `KERNEL32!GetLastError` at `0x1800051fb`
- `KERNEL32!GetLastError` at `0x180005218`
- `KERNEL32!GetLastError` at `0x18000512d`
- `KERNEL32!GetLastError` at `0x180005163`
- `KERNEL32!GetLastError` at `0x180005178`
- `KERNEL32!GetLastError` at `0x1800051ae`
- `KERNEL32!GetLastError` at `0x1800051c5`
- `KERNEL32!GetLastError` at `0x1800051fb`
- `KERNEL32!GetLastError` at `0x180005218`
- `ADVAPI32!StartTraceW` at `0x180004ef6`
- `ADVAPI32!StartTraceW` at `0x180004ef6`
- `ADVAPI32!EnableTraceEx2` at `0x180004fd1`
- `ADVAPI32!EnableTraceEx2` at `0x180005037`
- `ADVAPI32!EnableTraceEx2` at `0x18000509d`
- `ADVAPI32!EnableTraceEx2` at `0x180004fd1`
- `ADVAPI32!EnableTraceEx2` at `0x180005037`
- `ADVAPI32!EnableTraceEx2` at `0x18000509d`
- `ADVAPI32!OpenTraceW` at `0x18000510c`
- `ADVAPI32!OpenTraceW` at `0x18000510c`
- `ADVAPI32!ProcessTrace` at `0x1800052b9`
- `ADVAPI32!ProcessTrace` at `0x1800052b9`

## string_xrefs

- `0x18000513e`: `OpenTrace failed in Lag Counter`
- `0x180005189`: `OpenTrace failed with Invalid parameter in Lag Counter`
- `0x1800051d6`: `OpenTrace failed with bad path in Lag Counter`
- `0x180005229`: `OpenTrace failed access denied in Lag Counter`

## pseudocode

```c
__int64 __fastcall BlockOnProcessTrace(PVOID Parameter)
{
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  ULONG started; // eax
  int v5; // r8d
  int v6; // r9d
  ULONG v7; // eax
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  void *v11; // rdx
  const char *v12; // rax
  ULONG v13; // eax
  ULONG v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  CounterHelper *v24; // rax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  ULONG v28; // eax
  unsigned __int16 v30[4]; // [rsp+40h] [rbp-C0h] BYREF
  const char *v31; // [rsp+48h] [rbp-B8h] BYREF
  ULONG64 TraceHandle; // [rsp+50h] [rbp-B0h] BYREF
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+58h] [rbp-A8h] BYREF
  struct _ENABLE_TRACE_PARAMETERS EnableParameters; // [rsp+60h] [rbp-A0h] BYREF
  struct _ENABLE_TRACE_PARAMETERS v35; // [rsp+90h] [rbp-70h] BYREF
  struct _ENABLE_TRACE_PARAMETERS v36; // [rsp+C0h] [rbp-40h] BYREF

  TraceHandle = 0;
  Properties = 0;
  memset(&EnableParameters, 0, sizeof(EnableParameters));
  memset(&v35, 0, sizeof(v35));
  memset(&v36, 0, sizeof(v36));
  ResetStateOfTrace();
  if ( !MakeBufferForControl(&Properties) )
    goto LABEL_39;
  if ( (unsigned int)dword_180012020 > 4 )
  {
    *(_QWORD *)v30 = "Starting Session Lag Trace";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v1,
      (unsigned int)&unk_18000F2E6,
      v2,
      v3,
      (__int64)v30);
  }
  started = StartTraceW(&TraceHandle, LagCounterManager::EtwSessionName, Properties);
  if ( !started )
  {
    v30[0] = 63;
    AddEventFilter(&EnableParameters, v30, 1u);
    *(_DWORD *)v30 = 1376279;
    AddEventFilter(&v35, v30, 2u);
    v30[0] = 2;
    AddEventFilter(&v36, v30, 1u);
    v7 = EnableTraceEx2(
           TraceHandle,
           &ProviderId,
           1u,
           5u,
           0x400000040400000uLL,
           0x400000040400000uLL,
           0,
           &EnableParameters);
    if ( v7 )
    {
      v10 = dword_180012020;
      if ( (unsigned int)dword_180012020 > 2 )
      {
        *(_DWORD *)v30 = v7;
        v11 = &unk_18000F0EE;
        v12 = "EnableTrace() failed in Lag Counter for ApplicationLagEvent";
LABEL_37:
        v31 = v12;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (_DWORD)v11,
          v8,
          v9,
          (__int64)&v31,
          (__int64)v30);
      }
    }
    else
    {
      v13 = EnableTraceEx2(TraceHandle, &stru_18000EA80, 1u, 4u, 0x8000000000000010uLL, 0x8000000000000010uLL, 0, &v36);
      if ( v13 )
      {
        v10 = dword_180012020;
        if ( (unsigned int)dword_180012020 > 2 )
        {
          *(_DWORD *)v30 = v13;
          v11 = &unk_18000F157;
          v12 = "EnableTrace() failed in Lag Counter for ProcessExitEvent";
          goto LABEL_37;
        }
      }
      else
      {
        v14 = EnableTraceEx2(
                TraceHandle,
                &stru_18000EA90,
                1u,
                4u,
                0x1000000000000000uLL,
                0x1000000000000000uLL,
                0,
                &v35);
        if ( !v14 )
        {
          memset_0(&Logfile, 0, sizeof(Logfile));
          Logfile.LoggerName = LagCounterManager::EtwSessionName;
          Logfile.EventCallback = (PEVENT_CALLBACK)ProcessRecordCallback;
          Logfile.LogFileMode = 268439808;
          Logfile.IsKernelTrace = 1;
          LagCounterManager::hTrace = OpenTraceW(&Logfile);
          if ( LagCounterManager::hTrace == -1 )
          {
            if ( (unsigned int)dword_180012020 > 2 )
            {
              *(_DWORD *)v30 = GetLastError();
              v31 = "OpenTrace failed in Lag Counter";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v15,
                (unsigned int)&unk_18000F441,
                v16,
                v17,
                (__int64)&v31,
                (__int64)v30);
            }
            if ( GetLastError() == 87 && (unsigned int)dword_180012020 > 2 )
            {
              *(_DWORD *)v30 = GetLastError();
              v31 = "OpenTrace failed with Invalid parameter in Lag Counter";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v18,
                (unsigned int)&unk_18000F472,
                v19,
                v20,
                (__int64)&v31,
                (__int64)v30);
            }
            if ( GetLastError() == 161 && (unsigned int)dword_180012020 > 2 )
            {
              *(_DWORD *)v30 = GetLastError();
              v31 = "OpenTrace failed with bad path in Lag Counter";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v21,
                (unsigned int)&unk_18000EE99,
                v22,
                v23,
                (__int64)&v31,
                (__int64)v30);
            }
            if ( GetLastError() != 5 || (unsigned int)dword_180012020 <= 2 )
              goto LABEL_38;
            *(_DWORD *)v30 = GetLastError();
            v11 = &unk_18000EFFB;
            v12 = "OpenTrace failed access denied in Lag Counter";
          }
          else
          {
            v24 = (CounterHelper *)operator new(0x1B0u);
            v31 = (const char *)v24;
            if ( v24 )
              v24 = (CounterHelper *)CounterHelper::CounterHelper(v24, 0, 2);
            CounterHelper::MachineCounter = v24;
            if ( !SetEvent(LagCounterManager::hStartedEvent) )
              goto LABEL_38;
            if ( (unsigned int)dword_180012020 > 4 )
            {
              v31 = "Getting traces now";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v25,
                (unsigned int)&unk_18000F4D4,
                v26,
                v27,
                (__int64)&v31);
            }
            v28 = ProcessTrace(&LagCounterManager::hTrace, 1u, 0, 0);
            if ( !v28 )
              goto LABEL_38;
            if ( v28 == 1223 )
              goto LABEL_38;
            v10 = dword_180012020;
            if ( (unsigned int)dword_180012020 <= 2 )
              goto LABEL_38;
            *(_DWORD *)v30 = v28;
            v11 = &unk_18000F306;
            v12 = "ProcessTrace failed in Lag Counter";
          }
          goto LABEL_37;
        }
        v10 = dword_180012020;
        if ( (unsigned int)dword_180012020 > 2 )
        {
          *(_DWORD *)v30 = v14;
          v11 = &unk_18000EFA1;
          v12 = "EnableTrace() failed in Lag Counter for LogOffEvent";
          goto LABEL_37;
        }
      }
    }
LABEL_38:
    operator delete((void *)EnableParameters.EnableFilterDesc->Ptr);
    operator delete(EnableParameters.EnableFilterDesc);
    operator delete((void *)v35.EnableFilterDesc->Ptr);
    operator delete(v35.EnableFilterDesc);
    operator delete((void *)v36.EnableFilterDesc->Ptr);
    operator delete(v36.EnableFilterDesc);
    goto LABEL_39;
  }
  if ( (unsigned int)dword_180012020 > 2 )
  {
    *(_DWORD *)v30 = started;
    v31 = "StartTrace() failed with";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_180012020,
      (unsigned int)&unk_18000F1EC,
      v5,
      v6,
      (__int64)&v31,
      (__int64)v30);
  }
LABEL_39:
  operator delete(Properties);
  return 0;
}

```

## disassembly

```asm
0x180004e40  push    rbp
0x180004e42  push    rbx
0x180004e43  push    rsi
0x180004e44  push    r14
0x180004e46  lea     rbp, [rsp-8]
0x180004e4b  sub     rsp, 108h
0x180004e52  mov     rax, cs:__security_cookie
0x180004e59  xor     rax, rsp
0x180004e5c  mov     [rbp+20h+var_30], rax
0x180004e60  xorps   xmm0, xmm0
0x180004e63  mov     [rsp+120h+TraceHandle], 0
0x180004e6c  xorps   xmm1, xmm1
0x180004e6f  mov     [rsp+120h+Properties], 0
0x180004e78  movups  xmmword ptr [rsp+120h+var_C0.Version], xmm0
0x180004e7d  movups  xmmword ptr [rsp+120h+var_C0.SourceId.Data2], xmm0
0x180004e82  movups  xmmword ptr [rbp+20h+var_C0.EnableFilterDesc], xmm0
0x180004e86  movups  xmmword ptr [rbp+20h+var_90.Version], xmm1
0x180004e8a  movups  xmmword ptr [rbp+20h+var_90.SourceId.Data2], xmm1
0x180004e8e  movups  xmmword ptr [rbp+20h+var_90.EnableFilterDesc], xmm1
0x180004e92  movups  xmmword ptr [rbp+20h+var_60.Version], xmm0
0x180004e96  movups  xmmword ptr [rbp+20h+var_60.SourceId.Data2], xmm0
0x180004e9a  movups  xmmword ptr [rbp+20h+var_60.EnableFilterDesc], xmm0
0x180004e9e  call    ?ResetStateOfTrace@@YAHXZ; ResetStateOfTrace(void)
0x180004ea3  lea     rcx, [rsp+120h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180004ea8  call    ?MakeBufferForControl@@YA_NPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; MakeBufferForControl(_EVENT_TRACE_PROPERTIES * *)
0x180004ead  test    al, al
0x180004eaf  jz      loc_180005349
0x180004eb5  mov     eax, cs:dword_180012020
0x180004ebb  cmp     eax, 4
0x180004ebe  jbe     short loc_180004EE2
0x180004ec0  lea     rax, aStartingSessio; "Starting Session Lag Trace"
0x180004ec7  mov     qword ptr [rsp+120h+var_E0], rax
0x180004ecc  lea     rdx, unk_18000F2E6
0x180004ed3  lea     rax, [rsp+120h+var_E0]
0x180004ed8  mov     [rsp+120h+MatchAnyKeyword], rax
0x180004edd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180004ee2  mov     r8, [rsp+120h+Properties]; Properties
0x180004ee7  lea     r14, ?EtwSessionName@LagCounterManager@@2PAGA; ushort near * LagCounterManager::EtwSessionName
0x180004eee  mov     rdx, r14; InstanceName
0x180004ef1  lea     rcx, [rsp+120h+TraceHandle]; TraceHandle
0x180004ef6  call    cs:__imp_StartTraceW
0x180004efc  test    eax, eax
0x180004efe  jz      short loc_180004F48
0x180004f00  mov     ecx, cs:dword_180012020
0x180004f06  mov     ebx, 2
0x180004f0b  cmp     ecx, ebx
0x180004f0d  jbe     loc_180005349
0x180004f13  mov     dword ptr [rsp+120h+var_E0], eax
0x180004f17  lea     rdx, unk_18000F1EC
0x180004f1e  lea     rax, aStarttraceFail; "StartTrace() failed with"
0x180004f25  mov     [rsp+120h+var_D8], rax
0x180004f2a  lea     rax, [rsp+120h+var_E0]
0x180004f2f  mov     [rsp+120h+MatchAllKeyword], rax
0x180004f34  lea     rax, [rsp+120h+var_D8]
0x180004f39  mov     [rsp+120h+MatchAnyKeyword], rax
0x180004f3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180004f43  jmp     loc_180005349
0x180004f48  mov     eax, 3Fh ; '?'
0x180004f4d  lea     rdx, [rsp+120h+var_E0]; unsigned __int16 *
0x180004f52  lea     rcx, [rsp+120h+var_C0]; struct _ENABLE_TRACE_PARAMETERS *
0x180004f57  mov     [rsp+120h+var_E0], ax
0x180004f5c  lea     esi, [rax-3Eh]
0x180004f5f  mov     r8d, esi; unsigned __int16
0x180004f62  call    ?AddEventFilter@@YAKPEAU_ENABLE_TRACE_PARAMETERS@@PEAGG@Z; AddEventFilter(_ENABLE_TRACE_PARAMETERS *,ushort *,ushort)
0x180004f67  lea     ebx, [rsi+1]
0x180004f6a  mov     dword ptr [rsp+120h+var_E0], 150017h
0x180004f72  mov     r8d, ebx; unsigned __int16
0x180004f75  lea     rdx, [rsp+120h+var_E0]; unsigned __int16 *
0x180004f7a  lea     rcx, [rbp+20h+var_90]; struct _ENABLE_TRACE_PARAMETERS *
0x180004f7e  call    ?AddEventFilter@@YAKPEAU_ENABLE_TRACE_PARAMETERS@@PEAGG@Z; AddEventFilter(_ENABLE_TRACE_PARAMETERS *,ushort *,ushort)
0x180004f83  mov     r8d, esi; unsigned __int16
0x180004f86  mov     [rsp+120h+var_E0], bx
0x180004f8b  lea     rdx, [rsp+120h+var_E0]; unsigned __int16 *
0x180004f90  lea     rcx, [rbp+20h+var_60]; struct _ENABLE_TRACE_PARAMETERS *
0x180004f94  call    ?AddEventFilter@@YAKPEAU_ENABLE_TRACE_PARAMETERS@@PEAGG@Z; AddEventFilter(_ENABLE_TRACE_PARAMETERS *,ushort *,ushort)
0x180004f99  mov     rcx, [rsp+120h+TraceHandle]; TraceHandle
0x180004f9e  lea     rax, [rsp+120h+var_C0]
0x180004fa3  mov     [rsp+120h+EnableParameters], rax; EnableParameters
0x180004fa8  lea     rdx, ProviderId; ProviderId
0x180004faf  mov     rax, 400000040400000h
0x180004fb9  mov     [rsp+120h+Timeout], 0; Timeout
0x180004fc1  mov     [rsp+120h+MatchAllKeyword], rax; MatchAllKeyword
0x180004fc6  mov     r9b, 5; Level
0x180004fc9  mov     r8d, esi; ControlCode
0x180004fcc  mov     [rsp+120h+MatchAnyKeyword], rax; MatchAnyKeyword
0x180004fd1  call    cs:__imp_EnableTraceEx2
0x180004fd7  test    eax, eax
0x180004fd9  jz      short loc_180005000
0x180004fdb  mov     ecx, cs:dword_180012020
0x180004fe1  cmp     ecx, ebx
0x180004fe3  jbe     loc_180005304
0x180004fe9  mov     dword ptr [rsp+120h+var_E0], eax
0x180004fed  lea     rdx, unk_18000F0EE
0x180004ff4  lea     rax, aEnabletraceFai_1; "EnableTrace() failed in Lag Counter for"...
0x180004ffb  jmp     loc_1800052E6
0x180005000  mov     rcx, [rsp+120h+TraceHandle]; TraceHandle
0x180005005  lea     rax, [rbp+20h+var_60]
0x180005009  mov     [rsp+120h+EnableParameters], rax; EnableParameters
0x18000500e  lea     rdx, stru_18000EA80; ProviderId
0x180005015  mov     rax, 8000000000000010h
0x18000501f  mov     [rsp+120h+Timeout], 0; Timeout
0x180005027  mov     [rsp+120h+MatchAllKeyword], rax; MatchAllKeyword
0x18000502c  mov     r9b, 4; Level
0x18000502f  mov     r8d, esi; ControlCode
0x180005032  mov     [rsp+120h+MatchAnyKeyword], rax; MatchAnyKeyword
0x180005037  call    cs:__imp_EnableTraceEx2
0x18000503d  test    eax, eax
0x18000503f  jz      short loc_180005066
0x180005041  mov     ecx, cs:dword_180012020
0x180005047  cmp     ecx, ebx
0x180005049  jbe     loc_180005304
0x18000504f  mov     dword ptr [rsp+120h+var_E0], eax
0x180005053  lea     rdx, unk_18000F157
0x18000505a  lea     rax, aEnabletraceFai; "EnableTrace() failed in Lag Counter for"...
0x180005061  jmp     loc_1800052E6
0x180005066  mov     rcx, [rsp+120h+TraceHandle]; TraceHandle
0x18000506b  lea     rax, [rbp+20h+var_90]
0x18000506f  mov     [rsp+120h+EnableParameters], rax; EnableParameters
0x180005074  lea     rdx, stru_18000EA90; ProviderId
0x18000507b  mov     rax, 1000000000000000h
0x180005085  mov     [rsp+120h+Timeout], 0; Timeout
0x18000508d  mov     [rsp+120h+MatchAllKeyword], rax; MatchAllKeyword
0x180005092  mov     r9b, 4; Level
0x180005095  mov     r8d, esi; ControlCode
0x180005098  mov     [rsp+120h+MatchAnyKeyword], rax; MatchAnyKeyword
0x18000509d  call    cs:__imp_EnableTraceEx2
0x1800050a3  test    eax, eax
0x1800050a5  jz      short loc_1800050CC
0x1800050a7  mov     ecx, cs:dword_180012020
0x1800050ad  cmp     ecx, ebx
0x1800050af  jbe     loc_180005304
0x1800050b5  mov     dword ptr [rsp+120h+var_E0], eax
0x1800050b9  lea     rdx, unk_18000EFA1
0x1800050c0  lea     rax, aEnabletraceFai_0; "EnableTrace() failed in Lag Counter for"...
0x1800050c7  jmp     loc_1800052E6
0x1800050cc  xor     edx, edx; Val
0x1800050ce  lea     rcx, Logfile; void *
0x1800050d5  mov     r8d, 1C0h; Size
0x1800050db  call    memset_0
0x1800050e0  lea     rax, ?ProcessRecordCallback@@YAKPEAU_EVENT_RECORD@@@Z; ProcessRecordCallback(_EVENT_RECORD *)
0x1800050e7  mov     cs:Logfile.LoggerName, r14
0x1800050ee  lea     rcx, Logfile; Logfile
0x1800050f5  mov     qword ptr cs:Logfile.1A8h, rax
0x1800050fc  mov     dword ptr cs:Logfile.1Ch, 10001100h
0x180005106  mov     cs:Logfile.IsKernelTrace, esi
0x18000510c  call    cs:__imp_OpenTraceW
0x180005112  mov     cs:?hTrace@LagCounterManager@@2_KA, rax; unsigned __int64 LagCounterManager::hTrace
0x180005119  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000511d  jnz     loc_180005235
0x180005123  mov     eax, cs:dword_180012020
0x180005129  cmp     eax, ebx
0x18000512b  jbe     short loc_180005163
0x18000512d  call    cs:__imp_GetLastError
0x180005133  mov     dword ptr [rsp+120h+var_E0], eax
0x180005137  lea     rdx, unk_18000F441
0x18000513e  lea     rax, aOpentraceFaile; "OpenTrace failed in Lag Counter"
0x180005145  mov     [rsp+120h+var_D8], rax
0x18000514a  lea     rax, [rsp+120h+var_E0]
0x18000514f  mov     [rsp+120h+MatchAllKeyword], rax
0x180005154  lea     rax, [rsp+120h+var_D8]
0x180005159  mov     [rsp+120h+MatchAnyKeyword], rax
0x18000515e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005163  call    cs:__imp_GetLastError
0x180005169  cmp     eax, 57h ; 'W'
0x18000516c  jnz     short loc_1800051AE
0x18000516e  mov     eax, cs:dword_180012020
0x180005174  cmp     eax, ebx
0x180005176  jbe     short loc_1800051AE
0x180005178  call    cs:__imp_GetLastError
0x18000517e  mov     dword ptr [rsp+120h+var_E0], eax
0x180005182  lea     rdx, unk_18000F472
0x180005189  lea     rax, aOpentraceFaile_0; "OpenTrace failed with Invalid parameter"...
0x180005190  mov     [rsp+120h+var_D8], rax
0x180005195  lea     rax, [rsp+120h+var_E0]
0x18000519a  mov     [rsp+120h+MatchAllKeyword], rax
0x18000519f  lea     rax, [rsp+120h+var_D8]
0x1800051a4  mov     [rsp+120h+MatchAnyKeyword], rax
0x1800051a9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800051ae  call    cs:__imp_GetLastError
0x1800051b4  cmp     eax, 0A1h
0x1800051b9  jnz     short loc_1800051FB
0x1800051bb  mov     eax, cs:dword_180012020
0x1800051c1  cmp     eax, ebx
0x1800051c3  jbe     short loc_1800051FB
0x1800051c5  call    cs:__imp_GetLastError
0x1800051cb  mov     dword ptr [rsp+120h+var_E0], eax
0x1800051cf  lea     rdx, unk_18000EE99
0x1800051d6  lea     rax, aOpentraceFaile_1; "OpenTrace failed with bad path in Lag C"...
0x1800051dd  mov     [rsp+120h+var_D8], rax
0x1800051e2  lea     rax, [rsp+120h+var_E0]
0x1800051e7  mov     [rsp+120h+MatchAllKeyword], rax
0x1800051ec  lea     rax, [rsp+120h+var_D8]
0x1800051f1  mov     [rsp+120h+MatchAnyKeyword], rax
0x1800051f6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800051fb  call    cs:__imp_GetLastError
0x180005201  cmp     eax, 5
0x180005204  jnz     loc_180005304
0x18000520a  mov     eax, cs:dword_180012020
0x180005210  cmp     eax, ebx
0x180005212  jbe     loc_180005304
0x180005218  call    cs:__imp_GetLastError
0x18000521e  mov     dword ptr [rsp+120h+var_E0], eax
0x180005222  lea     rdx, unk_18000EFFB
0x180005229  lea     rax, aOpentraceFaile_2; "OpenTrace failed access denied in Lag C"...
0x180005230  jmp     loc_1800052E6
0x180005235  mov     ecx, 1B0h; Size
0x18000523a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000523f  mov     [rsp+120h+var_D8], rax
0x180005244  test    rax, rax
0x180005247  jz      short loc_180005261
0x180005249  xor     r9d, r9d
0x18000524c  mov     dword ptr [rsp+120h+MatchAnyKeyword], 0
0x180005254  mov     r8d, ebx
0x180005257  xor     edx, edx
0x180005259  mov     rcx, rax
0x18000525c  call    ??0CounterHelper@@QEAA@PEAGW4COUNTER_HELPER_TYPE@@KK@Z; CounterHelper::CounterHelper(ushort *,COUNTER_HELPER_TYPE,ulong,ulong)
0x180005261  mov     rcx, cs:?hStartedEvent@LagCounterManager@@2PEAXEA; hEvent
0x180005268  mov     cs:?MachineCounter@CounterHelper@@2PEAV1@EA, rax; CounterHelper * CounterHelper::MachineCounter
0x18000526f  call    cs:__imp_SetEvent
0x180005275  test    eax, eax
0x180005277  jz      loc_180005304
0x18000527d  mov     eax, cs:dword_180012020
0x180005283  cmp     eax, 4
0x180005286  jbe     short loc_1800052AA
0x180005288  lea     rax, aGettingTracesN; "Getting traces now"
0x18000528f  mov     [rsp+120h+var_D8], rax
0x180005294  lea     rdx, unk_18000F4D4
0x18000529b  lea     rax, [rsp+120h+var_D8]
0x1800052a0  mov     [rsp+120h+MatchAnyKeyword], rax
0x1800052a5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800052aa  xor     r9d, r9d; EndTime
0x1800052ad  lea     rcx, ?hTrace@LagCounterManager@@2_KA; HandleArray
0x1800052b4  xor     r8d, r8d; StartTime
0x1800052b7  mov     edx, esi; HandleCount
0x1800052b9  call    cs:__imp_ProcessTrace
0x1800052bf  test    eax, eax
0x1800052c1  jz      short loc_180005304
0x1800052c3  cmp     eax, 4C7h
0x1800052c8  jz      short loc_180005304
0x1800052ca  mov     ecx, cs:dword_180012020
0x1800052d0  cmp     ecx, ebx
0x1800052d2  jbe     short loc_180005304
0x1800052d4  mov     dword ptr [rsp+120h+var_E0], eax
0x1800052d8  lea     rdx, unk_18000F306
0x1800052df  lea     rax, aProcesstraceFa; "ProcessTrace failed in Lag Counter"
0x1800052e6  mov     [rsp+120h+var_D8], rax
0x1800052eb  lea     rax, [rsp+120h+var_E0]
0x1800052f0  mov     [rsp+120h+MatchAllKeyword], rax
0x1800052f5  lea     rax, [rsp+120h+var_D8]
0x1800052fa  mov     [rsp+120h+MatchAnyKeyword], rax
0x1800052ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005304  mov     rcx, [rbp+20h+var_C0.EnableFilterDesc]
0x180005308  mov     rcx, [rcx]
0x18000530b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005311  mov     rcx, [rbp+20h+var_C0.EnableFilterDesc]
0x180005315  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000531b  mov     rcx, [rbp+20h+var_90.EnableFilterDesc]
0x18000531f  mov     rcx, [rcx]
0x180005322  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005328  mov     rcx, [rbp+20h+var_90.EnableFilterDesc]
0x18000532c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005332  mov     rcx, [rbp+20h+var_60.EnableFilterDesc]
0x180005336  mov     rcx, [rcx]
0x180005339  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000533f  mov     rcx, [rbp+20h+var_60.EnableFilterDesc]
0x180005343  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005349  mov     rcx, [rsp+120h+Properties]
0x18000534e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005354  xor     eax, eax
0x180005356  mov     rcx, [rbp+20h+var_30]
0x18000535a  xor     rcx, rsp; StackCookie
0x18000535d  call    __security_check_cookie
0x180005362  add     rsp, 108h
0x180005369  pop     r14
0x18000536b  pop     rsi
0x18000536c  pop     rbx
0x18000536d  pop     rbp
0x18000536e  retn
```
