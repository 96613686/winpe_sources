# TraceUtil::AutologgerProcessorThread(void *)

- ea: `0x18000fa50`
- end: `0x18000ffd7`
- name: `?AutologgerProcessorThread@TraceUtil@@SAIPEAX@Z`
- size: `1415`
- prototype: `__int64 __fastcall(void *, __int64, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800011cc`
- `0x18000132c`
- `0x1800014d8`
- `0x180002270`
- `0x18000d4b4`
- `0x18000fa50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fd51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fd51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc80`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18000fd66`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18000fd66`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000fc6c`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000fc6c`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000fefb`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000ff64`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000fefb`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000ff64`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000fc11`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000fc11`

## string_xrefs

- `0x18000fd1b`: `OpenTrace`
- `0x18000fc93`: `Autologger OpenTrace failed with error`

## pseudocode

```c
__int64 __fastcall TraceUtil::AutologgerProcessorThread(void *a1, __int64 a2, int a3, int a4)
{
  TRACEHANDLE v4; // rsi
  signed int LastError; // ebx
  LSTATUS StringValue; // eax
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // eax
  __int16 v11; // ax
  __int16 *v12; // rdx
  unsigned __int16 **v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  unsigned int v18; // eax
  __int16 v19; // ax
  int v20; // ecx
  unsigned int v21; // eax
  ULONG v22; // eax
  int v23; // r8d
  int v24; // r9d
  ULONG v25; // eax
  int v26; // r8d
  int v27; // r9d
  ULONG v28; // ebx
  unsigned __int16 **EnableParameters; // [rsp+38h] [rbp-C8h]
  unsigned int v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v32; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v35; // [rsp+70h] [rbp-90h] BYREF
  __int16 v36; // [rsp+78h] [rbp-88h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-80h] BYREF
  ULONG64 HandleArray; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v39[32]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  WCHAR InstanceName[264]; // [rsp+C0h] [rbp-40h] BYREF

  HandleArray = -1;
  v4 = -1;
  *((_DWORD *)a1 + 4) = 0;
  if ( !*(_QWORD *)a1 )
  {
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      *(_QWORD *)v31 = "Autologger properties uninitialized";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)&unk_18001A420,
        a3,
        a4,
        (__int64)v31);
    }
    LastError = 6;
    goto LABEL_49;
  }
  v31[0] = 260;
  v33 = L"AutologgerSessionName";
  StringValue = RegUtil::ReadStringValue(
                  (const WCHAR **)&RegUtil::SERVICE_KEY,
                  (LPCWSTR *)&v33,
                  (BYTE *)InstanceName,
                  v31);
  LastError = StringValue;
  if ( !StringValue )
  {
    LastError = ControlTraceW(0, InstanceName, *(PEVENT_TRACE_PROPERTIES *)a1, 0);
    if ( LastError )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v31[0] = LastError;
        v32 = "Query for autologger trace handle failed.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)&dword_18001A864,
          v15,
          v16,
          (__int64)&v32,
          (__int64)v31);
      }
      goto LABEL_49;
    }
    v4 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
    HandleArray = OpenTraceW(*((PEVENT_TRACE_LOGFILEW *)a1 + 1));
    if ( HandleArray == -1 )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v31[0] = LastError;
        v32 = "Autologger OpenTrace failed with error";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)word_18001A8C2,
          v8,
          v9,
          (__int64)&v32,
          (__int64)v31);
      }
      if ( (unsigned int)dword_18001E080 <= 5
        || (qword_18001E090 & 0x800000000000LL) == 0
        || (qword_18001E098 & 0x800000000000LL) != qword_18001E098 )
      {
        goto LABEL_49;
      }
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      else
        v18 = LastError;
      v31[0] = v18;
      v32 = "OpenTrace";
      if ( (unsigned __int16)TraceUtil::AutologgerStringLength > 0x7FFFu )
        v19 = -2;
      else
        v19 = 2 * TraceUtil::AutologgerStringLength;
      v12 = (__int16 *)&unk_18001A2A0;
    }
    else
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      LastError = ProcessTrace(&HandleArray, 1u, 0, &SystemTimeAsFileTime);
      if ( !LastError )
        goto LABEL_49;
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v31[0] = LastError;
        v32 = "Autologger ProcessTrace failed with error";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&byte_18001A137,
          v8,
          v9,
          (__int64)&v32,
          (__int64)v31);
      }
      if ( (unsigned int)dword_18001E080 <= 5
        || (qword_18001E090 & 0x800000000000LL) == 0
        || (qword_18001E098 & 0x800000000000LL) != qword_18001E098 )
      {
        goto LABEL_49;
      }
      if ( LastError > 0 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      else
        v21 = LastError;
      v31[0] = v21;
      v32 = "ProcessTrace";
      if ( (unsigned __int16)TraceUtil::AutologgerStringLength > 0x7FFFu )
        v19 = -2;
      else
        v19 = 2 * TraceUtil::AutologgerStringLength;
      v12 = &word_18001A306;
    }
    v36 = v19;
    v33 = (unsigned __int16 *)0x80000000LL;
    EnableParameters = (unsigned __int16 **)&v32;
    v13 = &v33;
LABEL_48:
    v35 = L"Autologger";
    v34 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)L"Autologger",
      (_DWORD)v12,
      v8,
      v9,
      (__int64)v13,
      (__int64)&v34,
      (__int64)&v35,
      (__int64)EnableParameters,
      (__int64)v31);
    goto LABEL_49;
  }
  if ( (unsigned int)dword_18001E048 > 5 )
  {
    v31[0] = StringValue;
    v33 = (unsigned __int16 *)"Failed to get autologger session name";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18001E048,
      (unsigned int)&word_18001A246,
      v8,
      v9,
      (__int64)&v33,
      (__int64)v31);
  }
  if ( (unsigned int)dword_18001E080 > 5
    && (qword_18001E090 & 0x800000000000LL) != 0
    && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
  {
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    else
      v10 = LastError;
    v31[0] = v10;
    v33 = (unsigned __int16 *)"CloseTrace";
    if ( (unsigned __int16)TraceUtil::AutologgerStringLength > 0x7FFFu )
      v11 = -2;
    else
      v11 = 2 * TraceUtil::AutologgerStringLength;
    v36 = v11;
    v12 = word_18001A4D2;
    v32 = (const char *)0x80000000LL;
    EnableParameters = &v33;
    v13 = (unsigned __int16 **)&v32;
    goto LABEL_48;
  }
LABEL_49:
  if ( (unsigned int)dword_18001E048 > 5 )
  {
    v31[0] = LastError;
    v40 = v31;
    v41 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_180019F41, 0, 0, 3, v39);
  }
  v22 = EnableTraceEx2(v4, &ProviderId, 0, 5u, 0, 0, 0, 0);
  if ( v22 && (unsigned int)dword_18001E048 > 5 )
  {
    v31[0] = v22;
    v32 = "Disabling Kernel LL provider failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18001E048,
      (unsigned int)&word_180019D7E,
      v23,
      v24,
      (__int64)&v32,
      (__int64)v31);
  }
  v25 = EnableTraceEx2(v4, &Buf2, 0, 5u, 0, 0, 0, 0);
  v28 = v25;
  if ( v25 && (unsigned int)dword_18001E048 > 5 )
  {
    v31[0] = v25;
    v32 = "Disabling Kernel MM provider failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18001E048,
      (unsigned int)&byte_180019CBF,
      v26,
      v27,
      (__int64)&v32,
      (__int64)v31);
  }
  *((_DWORD *)a1 + 4) = v28;
  return v28;
}

```

## disassembly

```asm
0x18000fa50  mov     [rsp-8+arg_8], rbx
0x18000fa55  mov     [rsp-8+arg_10], rsi
0x18000fa5a  push    rbp
0x18000fa5b  push    rdi
0x18000fa5c  push    r14
0x18000fa5e  lea     rbp, [rsp-1E0h]
0x18000fa66  sub     rsp, 2E0h
0x18000fa6d  mov     rax, cs:__security_cookie
0x18000fa74  xor     rax, rsp
0x18000fa77  mov     [rbp+1F0h+var_20], rax
0x18000fa7e  xor     r14d, r14d
0x18000fa81  mov     [rbp+1F0h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x18000fa89  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000fa8d  mov     [rcx+10h], r14d
0x18000fa91  mov     rdi, rcx
0x18000fa94  cmp     [rcx], r14
0x18000fa97  jnz     short loc_18000FAD0
0x18000fa99  mov     eax, cs:dword_18001E048
0x18000fa9f  cmp     eax, 5
0x18000faa2  jbe     short loc_18000FAC6
0x18000faa4  lea     rax, aAutologgerProp; "Autologger properties uninitialized"
0x18000faab  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x18000fab0  lea     rdx, unk_18001A420
0x18000fab7  lea     rax, [rsp+2F0h+var_2A0]
0x18000fabc  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000fac1  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000fac6  mov     ebx, 6
0x18000facb  jmp     loc_18000FE8D
0x18000fad0  lea     rax, aAutologgersess_0; "AutologgerSessionName"
0x18000fad7  mov     [rsp+2F0h+var_2A0], 104h
0x18000fadf  lea     r9, [rsp+2F0h+var_2A0]; unsigned int *
0x18000fae4  mov     [rsp+2F0h+var_290], rax
0x18000fae9  lea     r8, [rbp+1F0h+InstanceName]; unsigned __int16 *
0x18000faed  lea     rdx, [rsp+2F0h+var_290]; unsigned __int16 **
0x18000faf2  lea     rcx, ?SERVICE_KEY@RegUtil@@0QEBGEB; unsigned __int16 **
0x18000faf9  call    ?ReadStringValue@RegUtil@@CAJAEBQEBG0PEAGAEBK@Z; RegUtil::ReadStringValue(ushort const * const &,ushort const * const &,ushort *,ulong const &)
0x18000fafe  mov     ebx, eax
0x18000fb00  test    eax, eax
0x18000fb02  jz      loc_18000FC05
0x18000fb08  mov     ecx, cs:dword_18001E048
0x18000fb0e  cmp     ecx, 5
0x18000fb11  jbe     short loc_18000FB43
0x18000fb13  mov     [rsp+2F0h+var_2A0], eax
0x18000fb17  lea     rdx, word_18001A246
0x18000fb1e  lea     rax, aFailedToGetAut; "Failed to get autologger session name"
0x18000fb25  mov     [rsp+2F0h+var_290], rax
0x18000fb2a  lea     rax, [rsp+2F0h+var_2A0]
0x18000fb2f  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000fb34  lea     rax, [rsp+2F0h+var_290]
0x18000fb39  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000fb3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000fb43  mov     eax, cs:dword_18001E080
0x18000fb49  cmp     eax, 5
0x18000fb4c  jbe     loc_18000FE8D
0x18000fb52  mov     rdx, cs:qword_18001E098
0x18000fb59  mov     rcx, 800000000000h
0x18000fb63  mov     rax, cs:qword_18001E090
0x18000fb6a  test    rcx, rax
0x18000fb6d  jz      loc_18000FE8D
0x18000fb73  mov     rax, rdx
0x18000fb76  and     rax, rcx
0x18000fb79  cmp     rax, rdx
0x18000fb7c  jnz     loc_18000FE8D
0x18000fb82  test    ebx, ebx
0x18000fb84  jg      short loc_18000FB8A
0x18000fb86  mov     eax, ebx
0x18000fb88  jmp     short loc_18000FB92
0x18000fb8a  movzx   eax, bx
0x18000fb8d  or      eax, 80070000h
0x18000fb92  mov     [rsp+2F0h+var_2A0], eax
0x18000fb96  mov     ecx, 7FFFh
0x18000fb9b  lea     rax, aClosetrace; "CloseTrace"
0x18000fba2  mov     [rsp+2F0h+var_290], rax
0x18000fba7  movzx   eax, cs:?AutologgerStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::AutologgerStringLength
0x18000fbae  cmp     ax, cx
0x18000fbb1  ja      short loc_18000FBB8
0x18000fbb3  add     ax, ax
0x18000fbb6  jmp     short loc_18000FBBD
0x18000fbb8  mov     eax, 0FFFEh
0x18000fbbd  mov     [rsp+2F0h+var_278], ax
0x18000fbc2  lea     rdx, word_18001A4D2
0x18000fbc9  mov     eax, 80000000h
0x18000fbce  mov     [rsp+2F0h+var_298], rax
0x18000fbd3  lea     rax, [rsp+2F0h+var_2A0]
0x18000fbd8  mov     [rsp+2F0h+var_2B0], rax
0x18000fbdd  lea     rax, [rsp+2F0h+var_290]
0x18000fbe2  mov     [rsp+2F0h+EnableParameters], rax
0x18000fbe7  lea     rax, [rsp+2F0h+var_280]
0x18000fbec  mov     qword ptr [rsp+2F0h+Timeout], rax
0x18000fbf1  lea     rax, [rsp+2F0h+var_288]
0x18000fbf6  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000fbfb  lea     rax, [rsp+2F0h+var_298]
0x18000fc00  jmp     loc_18000FE6E
0x18000fc05  mov     r8, [rdi]; Properties
0x18000fc08  lea     rdx, [rbp+1F0h+InstanceName]; InstanceName
0x18000fc0c  xor     r9d, r9d; ControlCode
0x18000fc0f  xor     ecx, ecx; TraceHandle
0x18000fc11  call    cs:__imp_ControlTraceW
0x18000fc17  mov     ebx, eax
0x18000fc19  test    eax, eax
0x18000fc1b  jz      short loc_18000FC61
0x18000fc1d  mov     eax, cs:dword_18001E048
0x18000fc23  cmp     eax, 5
0x18000fc26  jbe     loc_18000FE8D
0x18000fc2c  lea     rax, aQueryForAutolo; "Query for autologger trace handle faile"...
0x18000fc33  mov     [rsp+2F0h+var_2A0], ebx
0x18000fc37  mov     [rsp+2F0h+var_298], rax
0x18000fc3c  lea     rdx, dword_18001A864
0x18000fc43  lea     rax, [rsp+2F0h+var_2A0]
0x18000fc48  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000fc4d  lea     rax, [rsp+2F0h+var_298]
0x18000fc52  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000fc57  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000fc5c  jmp     loc_18000FE8D
0x18000fc61  mov     rax, [rdi]
0x18000fc64  mov     rcx, [rdi+8]; Logfile
0x18000fc68  mov     rsi, [rax+8]
0x18000fc6c  call    cs:__imp_OpenTraceW
0x18000fc72  mov     [rbp+1F0h+HandleArray], rax
0x18000fc76  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fc7a  jnz     loc_18000FD49
0x18000fc80  call    cs:__imp_GetLastError
0x18000fc86  mov     ebx, eax
0x18000fc88  mov     eax, cs:dword_18001E048
0x18000fc8e  cmp     eax, 5
0x18000fc91  jbe     short loc_18000FCC3
0x18000fc93  lea     rax, aAutologgerOpen; "Autologger OpenTrace failed with error"
0x18000fc9a  mov     [rsp+2F0h+var_2A0], ebx
0x18000fc9e  mov     [rsp+2F0h+var_298], rax
0x18000fca3  lea     rdx, word_18001A8C2
0x18000fcaa  lea     rax, [rsp+2F0h+var_2A0]
0x18000fcaf  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000fcb4  lea     rax, [rsp+2F0h+var_298]
0x18000fcb9  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000fcbe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000fcc3  mov     eax, cs:dword_18001E080
0x18000fcc9  cmp     eax, 5
0x18000fccc  jbe     loc_18000FE8D
0x18000fcd2  mov     rdx, cs:qword_18001E098
0x18000fcd9  mov     rcx, 800000000000h
0x18000fce3  mov     rax, cs:qword_18001E090
0x18000fcea  test    rcx, rax
0x18000fced  jz      loc_18000FE8D
0x18000fcf3  mov     rax, rdx
0x18000fcf6  and     rax, rcx
0x18000fcf9  cmp     rax, rdx
0x18000fcfc  jnz     loc_18000FE8D
0x18000fd02  test    ebx, ebx
0x18000fd04  jg      short loc_18000FD0A
0x18000fd06  mov     eax, ebx
0x18000fd08  jmp     short loc_18000FD12
0x18000fd0a  movzx   eax, bx
0x18000fd0d  or      eax, 80070000h
0x18000fd12  mov     [rsp+2F0h+var_2A0], eax
0x18000fd16  mov     ecx, 7FFFh
0x18000fd1b  lea     rax, aOpentrace; "OpenTrace"
0x18000fd22  mov     [rsp+2F0h+var_298], rax
0x18000fd27  movzx   eax, cs:?AutologgerStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::AutologgerStringLength
0x18000fd2e  cmp     ax, cx
0x18000fd31  ja      short loc_18000FD38
0x18000fd33  add     ax, ax
0x18000fd36  jmp     short loc_18000FD3D
0x18000fd38  mov     eax, 0FFFEh
0x18000fd3d  lea     rdx, unk_18001A2A0
0x18000fd44  jmp     loc_18000FE32
0x18000fd49  lea     rcx, [rbp+1F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fd4d  mov     qword ptr [rbp+1F0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18000fd51  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fd57  xor     r8d, r8d; StartTime
0x18000fd5a  lea     r9, [rbp+1F0h+SystemTimeAsFileTime]; EndTime
0x18000fd5e  lea     rcx, [rbp+1F0h+HandleArray]; HandleArray
0x18000fd62  lea     edx, [r8+1]; HandleCount
0x18000fd66  call    cs:__imp_ProcessTrace
0x18000fd6c  mov     ebx, eax
0x18000fd6e  test    eax, eax
0x18000fd70  jz      loc_18000FE8D
0x18000fd76  mov     eax, cs:dword_18001E048
0x18000fd7c  cmp     eax, 5
0x18000fd7f  jbe     short loc_18000FDB1
0x18000fd81  lea     rax, aAutologgerProc; "Autologger ProcessTrace failed with err"...
0x18000fd88  mov     [rsp+2F0h+var_2A0], ebx
0x18000fd8c  mov     [rsp+2F0h+var_298], rax
0x18000fd91  lea     rdx, byte_18001A137
0x18000fd98  lea     rax, [rsp+2F0h+var_2A0]
0x18000fd9d  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000fda2  lea     rax, [rsp+2F0h+var_298]
0x18000fda7  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000fdac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000fdb1  mov     eax, cs:dword_18001E080
0x18000fdb7  cmp     eax, 5
0x18000fdba  jbe     loc_18000FE8D
0x18000fdc0  mov     rdx, cs:qword_18001E098
0x18000fdc7  mov     rcx, 800000000000h
0x18000fdd1  mov     rax, cs:qword_18001E090
0x18000fdd8  test    rcx, rax
0x18000fddb  jz      loc_18000FE8D
0x18000fde1  mov     rax, rdx
0x18000fde4  and     rax, rcx
0x18000fde7  cmp     rax, rdx
0x18000fdea  jnz     loc_18000FE8D
0x18000fdf0  test    ebx, ebx
0x18000fdf2  jg      short loc_18000FDF8
0x18000fdf4  mov     eax, ebx
0x18000fdf6  jmp     short loc_18000FE00
0x18000fdf8  movzx   eax, bx
0x18000fdfb  or      eax, 80070000h
0x18000fe00  mov     [rsp+2F0h+var_2A0], eax
0x18000fe04  mov     ecx, 7FFFh
0x18000fe09  lea     rax, aProcesstrace; "ProcessTrace"
0x18000fe10  mov     [rsp+2F0h+var_298], rax
0x18000fe15  movzx   eax, cs:?AutologgerStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::AutologgerStringLength
0x18000fe1c  cmp     ax, cx
0x18000fe1f  ja      short loc_18000FE26
0x18000fe21  add     ax, ax
0x18000fe24  jmp     short loc_18000FE2B
0x18000fe26  mov     eax, 0FFFEh
0x18000fe2b  lea     rdx, word_18001A306
0x18000fe32  mov     [rsp+2F0h+var_278], ax
0x18000fe37  mov     eax, 80000000h
0x18000fe3c  mov     [rsp+2F0h+var_290], rax
0x18000fe41  lea     rax, [rsp+2F0h+var_2A0]
0x18000fe46  mov     [rsp+2F0h+var_2B0], rax
0x18000fe4b  lea     rax, [rsp+2F0h+var_298]
0x18000fe50  mov     [rsp+2F0h+EnableParameters], rax
0x18000fe55  lea     rax, [rsp+2F0h+var_280]
0x18000fe5a  mov     qword ptr [rsp+2F0h+Timeout], rax
0x18000fe5f  lea     rax, [rsp+2F0h+var_288]
0x18000fe64  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000fe69  lea     rax, [rsp+2F0h+var_290]
0x18000fe6e  lea     rcx, aAutologger_0; "Autologger"
0x18000fe75  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000fe7a  mov     [rsp+2F0h+var_280], rcx
0x18000fe7f  mov     [rsp+2F0h+var_288], 1000000h
0x18000fe88  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000fe8d  mov     eax, cs:dword_18001E048
0x18000fe93  cmp     eax, 5
0x18000fe96  jbe     short loc_18000FED7
0x18000fe98  lea     rax, [rsp+2F0h+var_2A0]
0x18000fe9d  mov     [rsp+2F0h+var_2A0], ebx
0x18000fea1  mov     [rbp+1F0h+var_240], rax
0x18000fea5  lea     rdx, byte_180019F41
0x18000feac  lea     rax, [rbp+1F0h+var_260]
0x18000feb0  mov     [rbp+1F0h+var_238], 4
0x18000feb8  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000febd  lea     rcx, dword_18001E048
0x18000fec4  xor     r9d, r9d
0x18000fec7  mov     dword ptr [rsp+2F0h+MatchAnyKeyword], 3
0x18000fecf  xor     r8d, r8d
0x18000fed2  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fed7  mov     [rsp+2F0h+EnableParameters], r14; EnableParameters
0x18000fedc  lea     rdx, ProviderId; ProviderId
0x18000fee3  mov     [rsp+2F0h+Timeout], r14d; Timeout
0x18000fee8  mov     r9b, 5; Level
0x18000feeb  mov     [rsp+2F0h+MatchAllKeyword], r14; MatchAllKeyword
0x18000fef0  xor     r8d, r8d; ControlCode
0x18000fef3  mov     rcx, rsi; TraceHandle
0x18000fef6  mov     [rsp+2F0h+MatchAnyKeyword], r14; MatchAnyKeyword
0x18000fefb  call    cs:__imp_EnableTraceEx2
0x18000ff01  test    eax, eax
0x18000ff03  jz      short loc_18000FF40
0x18000ff05  mov     ecx, cs:dword_18001E048
0x18000ff0b  cmp     ecx, 5
0x18000ff0e  jbe     short loc_18000FF40
0x18000ff10  mov     [rsp+2F0h+var_2A0], eax
0x18000ff14  lea     rdx, word_180019D7E
0x18000ff1b  lea     rax, aDisablingKerne; "Disabling Kernel LL provider failed."
0x18000ff22  mov     [rsp+2F0h+var_298], rax
0x18000ff27  lea     rax, [rsp+2F0h+var_2A0]
0x18000ff2c  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000ff31  lea     rax, [rsp+2F0h+var_298]
0x18000ff36  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000ff3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000ff40  mov     [rsp+2F0h+EnableParameters], r14; EnableParameters
0x18000ff45  lea     rdx, Buf2; ProviderId
0x18000ff4c  mov     [rsp+2F0h+Timeout], r14d; Timeout
0x18000ff51  mov     r9b, 5; Level
0x18000ff54  mov     [rsp+2F0h+MatchAllKeyword], r14; MatchAllKeyword
0x18000ff59  xor     r8d, r8d; ControlCode
0x18000ff5c  mov     rcx, rsi; TraceHandle
0x18000ff5f  mov     [rsp+2F0h+MatchAnyKeyword], r14; MatchAnyKeyword
0x18000ff64  call    cs:__imp_EnableTraceEx2
0x18000ff6a  mov     ebx, eax
0x18000ff6c  test    eax, eax
0x18000ff6e  jz      short loc_18000FFAB
0x18000ff70  mov     ecx, cs:dword_18001E048
0x18000ff76  cmp     ecx, 5
0x18000ff79  jbe     short loc_18000FFAB
0x18000ff7b  mov     [rsp+2F0h+var_2A0], eax
0x18000ff7f  lea     rdx, byte_180019CBF
0x18000ff86  lea     rax, aDisablingKerne_0; "Disabling Kernel MM provider failed."
0x18000ff8d  mov     [rsp+2F0h+var_298], rax
0x18000ff92  lea     rax, [rsp+2F0h+var_2A0]
0x18000ff97  mov     [rsp+2F0h+MatchAllKeyword], rax
0x18000ff9c  lea     rax, [rsp+2F0h+var_298]
0x18000ffa1  mov     [rsp+2F0h+MatchAnyKeyword], rax
0x18000ffa6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000ffab  mov     [rdi+10h], ebx
0x18000ffae  mov     eax, ebx
0x18000ffb0  mov     rcx, [rbp+1F0h+var_20]
0x18000ffb7  xor     rcx, rsp; StackCookie
  ... truncated ...
```
