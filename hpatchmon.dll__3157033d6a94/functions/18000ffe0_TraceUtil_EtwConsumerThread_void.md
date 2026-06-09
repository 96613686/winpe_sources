# TraceUtil::EtwConsumerThread(void *)

- ea: `0x18000ffe0`
- end: `0x180010649`
- name: `?EtwConsumerThread@TraceUtil@@SAIPEAX@Z`
- size: `1641`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800011cc`
- `0x18000132c`
- `0x1800014d8`
- `0x1800017d4`
- `0x180002270`
- `0x180002be8`
- `0x18000ffe0`
- `0x180011310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010097`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800101b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800105f0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800101b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800105f0`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800104ba`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800104ba`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180010604`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180010604`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001007e`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001007e`

## string_xrefs

- `0x1800100b9`: `OpenTrace failed with error`
- `0x18001013d`: `OpenTrace`

## pseudocode

```c
__int64 __fastcall TraceUtil::EtwConsumerThread(_QWORD *a1)
{
  unsigned int v2; // eax
  _QWORD *v3; // rbx
  _QWORD *v4; // rbx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  signed int v8; // ecx
  __int16 v9; // r14
  char *v10; // rdx
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int16 v15; // ax
  __int16 v16; // ax
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  signed int v19; // ecx
  __int16 v20; // ax
  _QWORD *v21; // rax
  TRACEHANDLE v22; // rcx
  const unsigned __int16 **v24; // [rsp+38h] [rbp-C8h]
  ULONG BuffersLost; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 EventsLost; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v29; // [rsp+70h] [rbp-90h] BYREF
  __int16 v30; // [rsp+78h] [rbp-88h]
  _QWORD *v31; // [rsp+80h] [rbp-80h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v33[32]; // [rsp+250h] [rbp+150h] BYREF
  __int64 *v34; // [rsp+270h] [rbp+170h]
  __int64 v35; // [rsp+278h] [rbp+178h]
  unsigned __int64 *p_EventsLost; // [rsp+280h] [rbp+180h]
  __int64 v37; // [rsp+288h] [rbp+188h]
  ULONG *p_BuffersLost; // [rsp+290h] [rbp+190h]
  __int64 v39; // [rsp+298h] [rbp+198h]

  memset_0(&v31, 0, 0x1C8u);
  v31 = a1;
  a1[2] = -1;
  Logfile.LoggerName = (LPWSTR)L"Microsoft-Windows-Hotpatch-Monitoring";
  Logfile.EventCallback = (PEVENT_CALLBACK)TraceUtil::ProcessEventCallback;
  Logfile.Context = &v31;
  Logfile.LogFileName = 0;
  Logfile.LogFileMode = 268435712;
  *((_DWORD *)a1 + 6) = 0;
  v2 = *((_DWORD *)a1 + 7);
  v3 = v31;
  AutoRemediate = v2;
  v3[2] = OpenTraceW(&Logfile);
  v4 = v31;
  if ( v31[2] == -1 )
  {
    *((_DWORD *)v4 + 6) = GetLastError();
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      v7 = *((unsigned int *)v31 + 6);
      v28 = (__int64)"OpenTrace failed with error";
      BuffersLost = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&unk_18001A470,
        v5,
        v6,
        (const unsigned __int16 **)&v28,
        (__int64)&BuffersLost);
    }
    if ( (unsigned int)dword_18001E080 > 5
      && (qword_18001E090 & 0x800000000000LL) != 0
      && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
    {
      v8 = *((_DWORD *)v31 + 6);
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      BuffersLost = v8;
      v28 = (__int64)"OpenTrace";
      if ( (unsigned __int16)TraceUtil::RealtimeStringLength > 0x7FFFu )
        v9 = -2;
      else
        v9 = 2 * TraceUtil::RealtimeStringLength;
      v30 = v9;
      v10 = byte_18001A0D1;
      v24 = (const unsigned __int16 **)&v28;
      EventsLost = 0x80000000LL;
      v11 = (__int64 *)&EventsLost;
LABEL_50:
      v29 = L"Realtime";
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)L"Realtime",
        (__int64)v10,
        v5,
        v6,
        (__int64)v11,
        (__int64)&v27,
        (__int64 *)&v29,
        v24,
        (__int64)&BuffersLost);
    }
  }
  else
  {
    SetEvent((HANDLE)v31[1]);
    if ( Logfile.LogfileHeader.EventsLost )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        EventsLost = Logfile.LogfileHeader.EventsLost;
        v27 = (__int64)"Initial number of events lost:";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v12,
          (__int64)&dword_18001A36C,
          v13,
          v14,
          (const unsigned __int16 **)&v27,
          (__int64)&EventsLost);
      }
      if ( (unsigned int)dword_18001E080 > 5 )
      {
        v12 = qword_18001E098;
        if ( (qword_18001E090 & 0x800000000000LL) != 0 && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
        {
          BuffersLost = Logfile.LogfileHeader.EventsLost;
          EventsLost = (unsigned __int64)"InitialEventsLost";
          if ( (unsigned __int16)TraceUtil::RealtimeStringLength > 0x7FFFu )
            v15 = -2;
          else
            v15 = 2 * TraceUtil::RealtimeStringLength;
          v30 = v15;
          v29 = L"Realtime";
          v27 = 0x1000000;
          v28 = 0x80000000LL;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            qword_18001E098,
            (__int64)byte_18001A195,
            v13,
            v14,
            (__int64)&v28,
            (__int64)&v27,
            (__int64 *)&v29,
            (const unsigned __int16 **)&EventsLost,
            (__int64)&BuffersLost);
        }
      }
    }
    if ( Logfile.LogfileHeader.BuffersLost )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        EventsLost = Logfile.LogfileHeader.BuffersLost;
        v27 = (__int64)"Initial number of buffers lost:";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v12,
          (__int64)&byte_18001A077,
          v13,
          v14,
          (const unsigned __int16 **)&v27,
          (__int64)&EventsLost);
      }
      if ( (unsigned int)dword_18001E080 > 5
        && (qword_18001E090 & 0x800000000000LL) != 0
        && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
      {
        BuffersLost = Logfile.LogfileHeader.BuffersLost;
        EventsLost = (unsigned __int64)"InitialBufferLost";
        if ( (unsigned __int16)TraceUtil::RealtimeStringLength > 0x7FFFu )
          v16 = -2;
        else
          v16 = 2 * TraceUtil::RealtimeStringLength;
        v30 = v16;
        v29 = L"Realtime";
        v27 = 0x1000000;
        v28 = 0x80000000LL;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          qword_18001E098,
          (__int64)&byte_180019DD7,
          v13,
          v14,
          (__int64)&v28,
          (__int64)&v27,
          (__int64 *)&v29,
          (const unsigned __int16 **)&EventsLost,
          (__int64)&BuffersLost);
      }
    }
    TraceUtil::lastHeartbeat = *(_QWORD *)std::chrono::steady_clock::now(&EventsLost);
    if ( (unsigned int)dword_18001E080 > 5
      && (qword_18001E090 & 0x800000000000LL) != 0
      && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
    {
      BuffersLost = AutoRemediate;
      EventsLost = 0x1000000;
      p_BuffersLost = &BuffersLost;
      v27 = 0x80000000LL;
      p_EventsLost = &EventsLost;
      v39 = 4;
      v34 = &v27;
      v37 = 8;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E080, qword_18001A538, 0, 0, 5, v33);
    }
    v17 = v31;
    *((_DWORD *)v17 + 6) = ProcessTrace(v31 + 2, 1u, 0, 0);
    if ( *((_DWORD *)v31 + 6) && *((_DWORD *)v31 + 6) != 1223 )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v18 = *((unsigned int *)v31 + 6);
        v27 = (__int64)"ProcessTrace failed with:";
        EventsLost = v18;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v18,
          (__int64)&unk_180019FC8,
          v5,
          v6,
          (const unsigned __int16 **)&v27,
          (__int64)&EventsLost);
      }
      if ( (unsigned int)dword_18001E080 > 5
        && (qword_18001E090 & 0x800000000000LL) != 0
        && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
      {
        v19 = *((_DWORD *)v31 + 6);
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        BuffersLost = v19;
        EventsLost = (unsigned __int64)"ProcessTrace";
        if ( (unsigned __int16)TraceUtil::RealtimeStringLength > 0x7FFFu )
          v20 = -2;
        else
          v20 = 2 * TraceUtil::RealtimeStringLength;
        v30 = v20;
        v10 = (char *)&unk_180019D18;
        v28 = 0x80000000LL;
        v24 = (const unsigned __int16 **)&EventsLost;
        v11 = &v28;
        goto LABEL_50;
      }
    }
  }
  SetEvent((HANDLE)v31[1]);
  v21 = v31;
  v22 = v31[2];
  if ( v22 != -1 )
  {
    CloseTrace(v22);
    v31[2] = -1;
    v21 = v31;
  }
  return *((unsigned int *)v21 + 6);
}

```

## disassembly

```asm
0x18000ffe0  mov     [rsp-8+arg_8], rbx
0x18000ffe5  mov     [rsp-8+arg_10], rsi
0x18000ffea  push    rbp
0x18000ffeb  push    r12
0x18000ffed  push    r13
0x18000ffef  push    r14
0x18000fff1  push    r15
0x18000fff3  lea     rbp, [rsp-1B0h]
0x18000fffb  sub     rsp, 2B0h
0x180010002  mov     rax, cs:__security_cookie
0x180010009  xor     rax, rsp
0x18001000c  mov     [rbp+1D0h+var_30], rax
0x180010013  mov     rbx, rcx
0x180010016  xor     edx, edx; Val
0x180010018  lea     rcx, [rbp+1D0h+var_250]; void *
0x18001001c  mov     r8d, 1C8h; Size
0x180010022  call    memset_0
0x180010027  mov     [rbp+1D0h+var_250], rbx
0x18001002b  lea     rax, InstanceName; "Microsoft-Windows-Hotpatch-Monitoring"
0x180010032  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x18001003a  lea     rcx, [rbp+1D0h+Logfile]; Logfile
0x18001003e  mov     [rbp+1D0h+Logfile.LoggerName], rax
0x180010042  lea     rax, ?ProcessEventCallback@TraceUtil@@SAXPEAU_EVENT_RECORD@@@Z; TraceUtil::ProcessEventCallback(_EVENT_RECORD *)
0x180010049  mov     qword ptr [rbp+1D0h+Logfile.1A8h], rax
0x180010050  lea     rax, [rbp+1D0h+var_250]
0x180010054  mov     [rbp+1D0h+Logfile.Context], rax
0x18001005b  mov     [rbp+1D0h+Logfile.LogFileName], 0
0x180010063  mov     dword ptr [rbp+1D0h+Logfile.1Ch], 10000100h
0x18001006a  mov     dword ptr [rbx+18h], 0
0x180010071  mov     eax, [rbx+1Ch]
0x180010074  mov     rbx, [rbp+1D0h+var_250]
0x180010078  mov     cs:?AutoRemediate@@3KA, eax; ulong AutoRemediate
0x18001007e  call    cs:__imp_OpenTraceW
0x180010084  mov     [rbx+10h], rax
0x180010088  mov     rbx, [rbp+1D0h+var_250]
0x18001008c  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180010091  jnz     loc_1800101B5
0x180010097  call    cs:__imp_GetLastError
0x18001009d  mov     [rbx+18h], eax
0x1800100a0  mov     eax, cs:dword_18001E048
0x1800100a6  cmp     eax, 5
0x1800100a9  jbe     short loc_1800100E2
0x1800100ab  mov     rax, [rbp+1D0h+var_250]
0x1800100af  lea     rdx, unk_18001A470
0x1800100b6  mov     ecx, [rax+18h]
0x1800100b9  lea     rax, aOpentraceFaile; "OpenTrace failed with error"
0x1800100c0  mov     [rsp+2D0h+var_268], rax
0x1800100c5  lea     rax, [rsp+2D0h+var_280]
0x1800100ca  mov     [rsp+2D0h+var_2A8], rax
0x1800100cf  lea     rax, [rsp+2D0h+var_268]
0x1800100d4  mov     [rsp+2D0h+var_2B0], rax
0x1800100d9  mov     [rsp+2D0h+var_280], ecx
0x1800100dd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800100e2  mov     eax, cs:dword_18001E080
0x1800100e8  cmp     eax, 5
0x1800100eb  jbe     loc_1800105E8
0x1800100f1  mov     rcx, cs:qword_18001E098
0x1800100f8  mov     rsi, 800000000000h
0x180010102  mov     rax, cs:qword_18001E090
0x180010109  test    rsi, rax
0x18001010c  jz      loc_1800105E8
0x180010112  mov     rax, rcx
0x180010115  and     rax, rsi
0x180010118  cmp     rax, rcx
0x18001011b  jnz     loc_1800105E8
0x180010121  mov     rax, [rbp+1D0h+var_250]
0x180010125  mov     ecx, [rax+18h]
0x180010128  test    ecx, ecx
0x18001012a  jle     short loc_180010135
0x18001012c  movzx   ecx, cx
0x18001012f  or      ecx, 80070000h
0x180010135  movzx   r14d, cs:?RealtimeStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::RealtimeStringLength
0x18001013d  lea     rax, aOpentrace; "OpenTrace"
0x180010144  mov     r15d, 7FFFh
0x18001014a  mov     [rsp+2D0h+var_280], ecx
0x18001014e  mov     [rsp+2D0h+var_268], rax
0x180010153  cmp     r14w, r15w
0x180010157  ja      short loc_18001015F
0x180010159  add     r14w, r14w
0x18001015d  jmp     short loc_180010165
0x18001015f  mov     r14d, 0FFFEh
0x180010165  lea     rax, [rsp+2D0h+var_280]
0x18001016a  mov     [rsp+2D0h+var_258], r14w
0x180010170  mov     [rsp+2D0h+var_290], rax
0x180010175  lea     rdx, byte_18001A0D1
0x18001017c  lea     rax, [rsp+2D0h+var_268]
0x180010181  mov     r13d, 80000000h
0x180010187  mov     [rsp+2D0h+var_298], rax
0x18001018c  mov     r12d, 1000000h
0x180010192  lea     rax, [rsp+2D0h+var_260]
0x180010197  mov     [rsp+2D0h+var_278], r13
0x18001019c  mov     [rsp+2D0h+var_2A0], rax
0x1800101a1  lea     rax, [rsp+2D0h+var_270]
0x1800101a6  mov     [rsp+2D0h+var_2A8], rax
0x1800101ab  lea     rax, [rsp+2D0h+var_278]
0x1800101b0  jmp     loc_1800105CD
0x1800101b5  mov     rcx, [rbx+8]; hEvent
0x1800101b9  call    cs:__imp_SetEvent
0x1800101bf  cmp     dword ptr [rbp+1D0h+Logfile.LogfileHeader.28h+8], 0
0x1800101c3  lea     rbx, aRealtime_0; "Realtime"
0x1800101ca  mov     rsi, 800000000000h
0x1800101d4  mov     r15d, 7FFFh
0x1800101da  mov     r14d, 0FFFEh
0x1800101e0  mov     r12d, 1000000h
0x1800101e6  mov     r13d, 80000000h
0x1800101ec  jbe     loc_1800102DC
0x1800101f2  mov     eax, cs:dword_18001E048
0x1800101f8  cmp     eax, 5
0x1800101fb  jbe     short loc_180010231
0x1800101fd  mov     eax, dword ptr [rbp+1D0h+Logfile.LogfileHeader.28h+8]
0x180010200  lea     rdx, dword_18001A36C
0x180010207  mov     [rsp+2D0h+var_278], rax
0x18001020c  lea     rax, aInitialNumberO; "Initial number of events lost:"
0x180010213  mov     [rsp+2D0h+var_270], rax
0x180010218  lea     rax, [rsp+2D0h+var_278]
0x18001021d  mov     [rsp+2D0h+var_2A8], rax
0x180010222  lea     rax, [rsp+2D0h+var_270]
0x180010227  mov     [rsp+2D0h+var_2B0], rax
0x18001022c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180010231  mov     eax, cs:dword_18001E080
0x180010237  cmp     eax, 5
0x18001023a  jbe     loc_1800102DC
0x180010240  mov     rcx, cs:qword_18001E098
0x180010247  mov     rax, cs:qword_18001E090
0x18001024e  test    rsi, rax
0x180010251  jz      loc_1800102DC
0x180010257  mov     rax, rcx
0x18001025a  and     rax, rsi
0x18001025d  cmp     rax, rcx
0x180010260  jnz     short loc_1800102DC
0x180010262  mov     eax, dword ptr [rbp+1D0h+Logfile.LogfileHeader.28h+8]
0x180010265  mov     [rsp+2D0h+var_280], eax
0x180010269  lea     rax, aInitialeventsl; "InitialEventsLost"
0x180010270  mov     [rsp+2D0h+var_278], rax
0x180010275  movzx   eax, cs:?RealtimeStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::RealtimeStringLength
0x18001027c  cmp     ax, r15w
0x180010280  ja      short loc_180010287
0x180010282  add     ax, ax
0x180010285  jmp     short loc_18001028A
0x180010287  mov     eax, r14d
0x18001028a  mov     [rsp+2D0h+var_258], ax
0x18001028f  lea     rdx, byte_18001A195
0x180010296  lea     rax, [rsp+2D0h+var_280]
0x18001029b  mov     [rsp+2D0h+var_260], rbx
0x1800102a0  mov     [rsp+2D0h+var_290], rax
0x1800102a5  lea     rax, [rsp+2D0h+var_278]
0x1800102aa  mov     [rsp+2D0h+var_298], rax
0x1800102af  lea     rax, [rsp+2D0h+var_260]
0x1800102b4  mov     [rsp+2D0h+var_2A0], rax
0x1800102b9  lea     rax, [rsp+2D0h+var_270]
0x1800102be  mov     [rsp+2D0h+var_2A8], rax
0x1800102c3  lea     rax, [rsp+2D0h+var_268]
0x1800102c8  mov     [rsp+2D0h+var_2B0], rax
0x1800102cd  mov     [rsp+2D0h+var_270], r12
0x1800102d2  mov     [rsp+2D0h+var_268], r13
0x1800102d7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800102dc  cmp     [rbp+1D0h+Logfile.LogfileHeader.BuffersLost], 0
0x1800102e3  jbe     loc_1800103D9
0x1800102e9  mov     eax, cs:dword_18001E048
0x1800102ef  cmp     eax, 5
0x1800102f2  jbe     short loc_18001032B
0x1800102f4  mov     eax, [rbp+1D0h+Logfile.LogfileHeader.BuffersLost]
0x1800102fa  lea     rdx, byte_18001A077
0x180010301  mov     [rsp+2D0h+var_278], rax
0x180010306  lea     rax, aInitialNumberO_0; "Initial number of buffers lost:"
0x18001030d  mov     [rsp+2D0h+var_270], rax
0x180010312  lea     rax, [rsp+2D0h+var_278]
0x180010317  mov     [rsp+2D0h+var_2A8], rax
0x18001031c  lea     rax, [rsp+2D0h+var_270]
0x180010321  mov     [rsp+2D0h+var_2B0], rax
0x180010326  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001032b  mov     eax, cs:dword_18001E080
0x180010331  cmp     eax, 5
0x180010334  jbe     loc_1800103D9
0x18001033a  mov     rcx, cs:qword_18001E098
0x180010341  mov     rax, cs:qword_18001E090
0x180010348  test    rsi, rax
0x18001034b  jz      loc_1800103D9
0x180010351  mov     rax, rcx
0x180010354  and     rax, rsi
0x180010357  cmp     rax, rcx
0x18001035a  jnz     short loc_1800103D9
0x18001035c  mov     eax, [rbp+1D0h+Logfile.LogfileHeader.BuffersLost]
0x180010362  mov     [rsp+2D0h+var_280], eax
0x180010366  lea     rax, aInitialbufferl; "InitialBufferLost"
0x18001036d  mov     [rsp+2D0h+var_278], rax
0x180010372  movzx   eax, cs:?RealtimeStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::RealtimeStringLength
0x180010379  cmp     ax, r15w
0x18001037d  ja      short loc_180010384
0x18001037f  add     ax, ax
0x180010382  jmp     short loc_180010387
0x180010384  mov     eax, r14d
0x180010387  mov     [rsp+2D0h+var_258], ax
0x18001038c  lea     rdx, byte_180019DD7
0x180010393  lea     rax, [rsp+2D0h+var_280]
0x180010398  mov     [rsp+2D0h+var_260], rbx
0x18001039d  mov     [rsp+2D0h+var_290], rax
0x1800103a2  lea     rax, [rsp+2D0h+var_278]
0x1800103a7  mov     [rsp+2D0h+var_298], rax
0x1800103ac  lea     rax, [rsp+2D0h+var_260]
0x1800103b1  mov     [rsp+2D0h+var_2A0], rax
0x1800103b6  lea     rax, [rsp+2D0h+var_270]
0x1800103bb  mov     [rsp+2D0h+var_2A8], rax
0x1800103c0  lea     rax, [rsp+2D0h+var_268]
0x1800103c5  mov     [rsp+2D0h+var_2B0], rax
0x1800103ca  mov     [rsp+2D0h+var_270], r12
0x1800103cf  mov     [rsp+2D0h+var_268], r13
0x1800103d4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800103d9  lea     rcx, [rsp+2D0h+var_278]
0x1800103de  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800103e3  mov     rcx, [rax]
0x1800103e6  mov     eax, cs:dword_18001E080
0x1800103ec  mov     cs:?lastHeartbeat@TraceUtil@@2V?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@A, rcx; std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> TraceUtil::lastHeartbeat
0x1800103f3  cmp     eax, 5
0x1800103f6  jbe     loc_1800104A8
0x1800103fc  mov     rcx, cs:qword_18001E098
0x180010403  mov     rax, cs:qword_18001E090
0x18001040a  test    rsi, rax
0x18001040d  jz      loc_1800104A8
0x180010413  mov     rax, rcx
0x180010416  and     rax, rsi
0x180010419  cmp     rax, rcx
0x18001041c  jnz     loc_1800104A8
0x180010422  mov     eax, cs:?AutoRemediate@@3KA; ulong AutoRemediate
0x180010428  lea     rdx, qword_18001A538
0x18001042f  mov     [rsp+2D0h+var_280], eax
0x180010433  lea     rcx, dword_18001E080
0x18001043a  lea     rax, [rsp+2D0h+var_280]
0x18001043f  mov     [rsp+2D0h+var_278], r12
0x180010444  mov     [rbp+1D0h+var_40], rax
0x18001044b  xor     r9d, r9d
0x18001044e  lea     rax, [rsp+2D0h+var_278]
0x180010453  mov     [rsp+2D0h+var_270], r13
0x180010458  mov     [rbp+1D0h+var_50], rax
0x18001045f  xor     r8d, r8d
0x180010462  lea     rax, [rsp+2D0h+var_270]
0x180010467  mov     [rbp+1D0h+var_38], 4
0x180010472  mov     [rbp+1D0h+var_60], rax
0x180010479  lea     rax, [rbp+1D0h+var_80]
0x180010480  mov     [rsp+2D0h+var_2A8], rax
0x180010485  mov     dword ptr [rsp+2D0h+var_2B0], 5
0x18001048d  mov     [rbp+1D0h+var_48], 8
0x180010498  mov     [rbp+1D0h+var_58], 8
0x1800104a3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800104a8  mov     rbx, [rbp+1D0h+var_250]
0x1800104ac  xor     r9d, r9d; EndTime
0x1800104af  xor     r8d, r8d; StartTime
0x1800104b2  lea     rcx, [rbx+10h]; HandleArray
0x1800104b6  lea     edx, [r9+1]; HandleCount
0x1800104ba  call    cs:__imp_ProcessTrace
0x1800104c0  mov     [rbx+18h], eax
0x1800104c3  mov     rax, [rbp+1D0h+var_250]
0x1800104c7  cmp     dword ptr [rax+18h], 0
0x1800104cb  jz      loc_1800105E8
0x1800104d1  cmp     dword ptr [rax+18h], 4C7h
0x1800104d8  jz      loc_1800105E8
0x1800104de  mov     eax, cs:dword_18001E048
0x1800104e4  cmp     eax, 5
0x1800104e7  jbe     short loc_180010521
0x1800104e9  mov     rax, [rbp+1D0h+var_250]
0x1800104ed  lea     rdx, unk_180019FC8
0x1800104f4  mov     ecx, [rax+18h]
0x1800104f7  lea     rax, aProcesstraceFa; "ProcessTrace failed with:"
0x1800104fe  mov     [rsp+2D0h+var_270], rax
0x180010503  lea     rax, [rsp+2D0h+var_278]
0x180010508  mov     [rsp+2D0h+var_2A8], rax
0x18001050d  lea     rax, [rsp+2D0h+var_270]
0x180010512  mov     [rsp+2D0h+var_2B0], rax
0x180010517  mov     [rsp+2D0h+var_278], rcx
0x18001051c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180010521  mov     eax, cs:dword_18001E080
0x180010527  cmp     eax, 5
0x18001052a  jbe     loc_1800105E8
0x180010530  mov     rcx, cs:qword_18001E098
0x180010537  mov     rax, cs:qword_18001E090
0x18001053e  test    rsi, rax
0x180010541  jz      loc_1800105E8
0x180010547  mov     rax, rcx
0x18001054a  and     rax, rsi
0x18001054d  cmp     rax, rcx
0x180010550  jnz     loc_1800105E8
0x180010556  mov     rax, [rbp+1D0h+var_250]
0x18001055a  mov     ecx, [rax+18h]
0x18001055d  test    ecx, ecx
0x18001055f  jle     short loc_18001056A
0x180010561  movzx   ecx, cx
0x180010564  or      ecx, 80070000h
0x18001056a  lea     rax, aProcesstrace; "ProcessTrace"
0x180010571  mov     [rsp+2D0h+var_280], ecx
0x180010575  mov     [rsp+2D0h+var_278], rax
0x18001057a  movzx   eax, cs:?RealtimeStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::RealtimeStringLength
0x180010581  cmp     ax, r15w
0x180010585  ja      short loc_18001058C
0x180010587  add     ax, ax
0x18001058a  jmp     short loc_18001058F
0x18001058c  mov     eax, r14d
0x18001058f  mov     [rsp+2D0h+var_258], ax
0x180010594  lea     rdx, unk_180019D18
0x18001059b  lea     rax, [rsp+2D0h+var_280]
0x1800105a0  mov     [rsp+2D0h+var_268], r13
  ... truncated ...
```
