# LampArrayDevice::ProcessLampState(LampArrayDevice::ViewClientListEntry *,bool *)

- ea: `0x180084938`
- end: `0x180085ac3`
- name: `?ProcessLampState@LampArrayDevice@@AEAAJPEAUViewClientListEntry@1@PEA_N@Z`
- size: `4491`
- prototype: `__int64 __fastcall(LampArrayDevice *__hidden this, struct LampArrayDevice::ViewClientListEntry *, bool *)`
- caller_count: `1`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c860`

## callees

- `0x180001008`
- `0x1800042b8`
- `0x18002f610`
- `0x18002f810`
- `0x18002f9b4`
- `0x18002fea0`
- `0x1800338d8`
- `0x180063334`
- `0x180063690`
- `0x180064a30`
- `0x1800698a8`
- `0x18006cca4`
- `0x180074bac`
- `0x1800766e4`
- `0x180077840`
- `0x180078114`
- `0x18007853c`
- `0x180079bbc`
- `0x18008044c`
- `0x180084938`
- `0x180088928`
- `0x180089268`
- `0x1800892c8`
- `0x1800899c8`
- `0x18008ea8c`
- `0x18008ead4`
- `0x1800f08d8`
- `0x1800f0990`
- `0x1800f2478`
- `0x1801159ec`
- `0x180125814`
- `0x18012a298`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800849a4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800849c8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800849a4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800849c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085178`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008534c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800855f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800859db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085178`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008534c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800855f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800859db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180084ac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180084ac4`

## string_xrefs

- `0x18008555b`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\lamparray\lib\hidlamprangeupdatereportbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LampArrayDevice::ProcessLampState(
        LampArrayDevice *this,
        struct LampArrayDevice::ViewClientListEntry *a2,
        bool *a3)
{
  char v5; // r12
  GUID *p_ActivityId; // r9
  PnpDevice *v7; // rbx
  int InstanceId; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // ecx
  HidLampRangeUpdateReportBuilder *StringRawBuffer; // rsi
  struct Windows::UI::Color *v13; // r8
  int v14; // r9d
  struct LampArrayDevice::ViewClientListEntry *v15; // rcx
  char v16; // bl
  int v17; // r9d
  int v18; // ecx
  int v19; // r9d
  __int32 v20; // ecx
  const char *v21; // r9
  int v22; // eax
  int v23; // r9d
  unsigned int v24; // ebx
  HidLampRangeUpdateReportBuilder *v25; // r13
  __int64 v26; // rsi
  double v27; // xmm7_8
  int i; // edi
  __int64 v29; // r15
  double v30; // xmm6_8
  int j; // esi
  __int64 v32; // rdi
  char v33; // al
  struct HidLampArrayDevice *v34; // rcx
  int v35; // eax
  unsigned int v36; // ebx
  HidLampRangeUpdateReportBuilder *v37; // rdi
  int v38; // eax
  HidLampRangeUpdateReportBuilder *v39; // rbx
  HidLampRangeUpdateReportBuilder *v40; // rax
  HidLampRangeUpdateReportBuilder *v41; // rsi
  unsigned int v42; // r12d
  unsigned int k; // r13d
  unsigned __int64 v44; // rcx
  __int64 v45; // r9
  __int64 v46; // r10
  HidLampRangeUpdateReportBuilder *v47; // rcx
  int updated; // eax
  unsigned int v49; // r15d
  unsigned int v50; // eax
  unsigned int v51; // r8d
  unsigned int v52; // edx
  unsigned int v53; // eax
  int v54; // edx
  unsigned int m; // r13d
  int v56; // eax
  int v57; // eax
  unsigned int v58; // esi
  int v59; // eax
  int v60; // r8d
  int v61; // r9d
  unsigned int v62; // ebx
  int v63; // [rsp+20h] [rbp-128h]
  int v64; // [rsp+20h] [rbp-128h]
  int v65; // [rsp+20h] [rbp-128h]
  int v66; // [rsp+20h] [rbp-128h]
  HidLampRangeUpdateReportBuilder *v67; // [rsp+40h] [rbp-108h] BYREF
  HSTRING string; // [rsp+48h] [rbp-100h] BYREF
  int v69; // [rsp+50h] [rbp-F8h] BYREF
  __int128 v70; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v71; // [rsp+68h] [rbp-E0h]
  int v72[2]; // [rsp+70h] [rbp-D8h] BYREF
  int v74; // [rsp+7Ch] [rbp-CCh] BYREF
  int v75[2]; // [rsp+80h] [rbp-C8h] BYREF
  int *v76; // [rsp+88h] [rbp-C0h] BYREF
  char v77; // [rsp+90h] [rbp-B8h]
  int v78; // [rsp+98h] [rbp-B0h]
  __int128 v79; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-98h]
  bool *v81; // [rsp+B8h] [rbp-90h] BYREF
  int v82; // [rsp+C0h] [rbp-88h] BYREF
  char v83; // [rsp+C4h] [rbp-84h]
  GUID v84; // [rsp+C8h] [rbp-80h] BYREF
  GUID ActivityId; // [rsp+D8h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v81 = a3;
  v5 = 0;
  *a3 = 0;
  v82 = 0;
  v83 = 0;
  if ( (unsigned int)dword_180241248 <= 5 )
  {
    v84 = 0;
  }
  else
  {
    EventActivityIdControl(3u, &v84);
    ActivityId = v84;
    EventActivityIdControl(4u, &ActivityId);
    v83 = 1;
  }
  v82 = 1;
  if ( (unsigned int)dword_180241248 > 5 )
  {
    if ( v83
      && (ActivityId.Data1
       || *(_DWORD *)&ActivityId.Data2
       || *(_DWORD *)ActivityId.Data4
       || *(_DWORD *)&ActivityId.Data4[4]) )
    {
      p_ActivityId = &ActivityId;
    }
    else
    {
      p_ActivityId = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180241248,
      &byte_1802074FF,
      &v84,
      p_ActivityId);
  }
  string = 0;
  v7 = (PnpDevice *)*((_QWORD *)this + 2);
  WindowsDeleteString(0);
  string = 0;
  InstanceId = PnpDevice::GetInstanceId(v7, &string);
  v9 = InstanceId;
  if ( InstanceId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparraydevice.cpp",
      (const char *)(unsigned int)InstanceId,
      v63);
    WindowsDeleteString(string);
    string = 0;
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
    return v9;
  }
  StringRawBuffer = (HidLampRangeUpdateReportBuilder *)WindowsGetStringRawBuffer(string, 0);
  v76 = &v82;
  v77 = 1;
  if ( a2 )
  {
    if ( (unsigned int)dword_180241248 > 5 )
    {
      v67 = StringRawBuffer;
      v72[0] = *((_DWORD *)a2 + 6);
      *(_QWORD *)v75 = "Updating ViewClient";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        dword_180241248,
        (unsigned int)&dword_18020752C,
        (_DWORD)v13,
        v14,
        (__int64)v75,
        (__int64)v72,
        (__int64)&v67);
    }
  }
  else if ( (unsigned int)dword_180241248 > 5 )
  {
    v67 = StringRawBuffer;
    *(_QWORD *)v72 = L"null";
    *(_QWORD *)v75 = "Updating ViewClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v11,
      (unsigned int)byte_18020757B,
      (_DWORD)v13,
      v14,
      (__int64)v75,
      (__int64)v72,
      (__int64)&v67);
  }
  try
  {
    v15 = (struct LampArrayDevice::ViewClientListEntry *)*((_QWORD *)this + 13);
    if ( a2 == v15 )
    {
      v16 = 0;
    }
    else
    {
      v16 = 1;
      if ( v15 )
      {
        _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v15 + 4) + 4208LL), 0);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 13) + 16LL) + 72LL))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL));
        if ( (unsigned int)dword_180241248 > 5 )
        {
          v67 = StringRawBuffer;
          v72[0] = *(_DWORD *)(*((_QWORD *)this + 13) + 24LL);
          *(_QWORD *)v75 = "ViewClient losing availability";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v72[0],
            (unsigned int)word_1802075CA,
            (_DWORD)v13,
            v17,
            (__int64)v75,
            (__int64)v72,
            (__int64)&v67);
        }
      }
      if ( a2 )
      {
        _InterlockedExchange((volatile __int32 *)(*((_QWORD *)a2 + 4) + 4208LL), 1);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 2) + 72LL))(*((_QWORD *)a2 + 2));
        if ( (unsigned int)dword_180241248 > 5 )
        {
          v67 = StringRawBuffer;
          v72[0] = *((_DWORD *)a2 + 6);
          *(_QWORD *)v75 = "ViewClient gaining availability";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v18,
            (unsigned int)&dword_180207644,
            (_DWORD)v13,
            v19,
            (__int64)v75,
            (__int64)v72,
            (__int64)&v67);
        }
        *((_QWORD *)this + 13) = a2;
LABEL_30:
        if ( *(_DWORD *)(*((_QWORD *)a2 + 4) + 4100LL) )
        {
          v20 = _InterlockedExchange((volatile __int32 *)(*((_QWORD *)a2 + 4) + 4096LL), 0);
          if ( v16 || v20 )
          {
            if ( *((_BYTE *)this + 152) )
              goto LABEL_40;
          }
          else if ( *((_BYTE *)this + 152) )
          {
            v77 = 0;
            lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
            WindowsDeleteString(string);
            string = 0;
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
            return 0;
          }
          v22 = HidLampArrayDevice::SetAutonomousMode(*((HidLampArrayDevice **)this + 3), 0);
          v24 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1FF,
              (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparraydevice.cpp",
              (const char *)(unsigned int)v22,
              v63);
            v77 = 0;
            lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
            WindowsDeleteString(string);
            string = 0;
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
            return v24;
          }
          if ( (unsigned int)dword_180241248 > 5 )
          {
            v67 = StringRawBuffer;
            *(_QWORD *)v72 = "LampArray leaving autonomous mode";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (unsigned int)&dword_180241248,
              (unsigned int)byte_1802076DD,
              (_DWORD)v13,
              v23,
              (__int64)v72,
              (__int64)&v67);
          }
LABEL_40:
          v25 = (HidLampRangeUpdateReportBuilder *)*(int *)(*((_QWORD *)this + 3) + 544LL);
          v26 = *((_QWORD *)a2 + 4);
          v27 = *(double *)(v26 + 4192);
          v79 = 0;
          v80 = 0;
          v67 = v25;
          if ( (_DWORD)v25 )
          {
            if ( (unsigned __int64)v25 > 0x3FFFFFFFFFFFFFFFLL )
              std::vector<Microsoft::WRL::ComPtr<InputSite>>::_Xlength();
            std::vector<unsigned long>::_Reallocate<1>(&v79, &v67);
          }
          for ( i = 0; i < (int)v25; ++i )
          {
            v13 = (struct Windows::UI::Color *)(v26 + 4 * (i + 9LL * *(int *)(v26 + 524) + 1306));
            if ( *((_QWORD *)&v79 + 1) == v80 )
            {
              std::vector<Windows::UI::Color>::_Emplace_reallocate<Windows::UI::Color const &>(
                &v79,
                *((_QWORD *)&v79 + 1),
                v13);
            }
            else
            {
              **((_DWORD **)&v79 + 1) = *(_DWORD *)v13;
              *((_QWORD *)&v79 + 1) += 4LL;
            }
          }
          v29 = *(_QWORD *)(*((_QWORD *)this + 3) + 568LL);
          v70 = 0;
          v71 = 0;
          v67 = v25;
          if ( (_DWORD)v25 )
            std::vector<LampUpdateState>::_Reallocate<0>(&v70, &v67);
          v30 = *((double *)this + 20);
          if ( v27 != v30 )
            v5 = 1;
          for ( j = 0; j < (int)v25; ++j )
          {
            v32 = *((_QWORD *)this + 21);
            if ( !*((_BYTE *)this + 152)
              || v5
              || *(_BYTE *)(v32 + 4LL * j) != *(_BYTE *)(v79 + 4LL * j)
              || *(_BYTE *)(v32 + 4LL * j + 1) != *(_BYTE *)(v79 + 4LL * j + 1)
              || *(_BYTE *)(v32 + 4LL * j + 2) != *(_BYTE *)(v79 + 4LL * j + 2)
              || *(_BYTE *)(v32 + 4LL * j + 3) != *(_BYTE *)(v79 + 4LL * j + 3) )
            {
              v69 = 0;
              v74 = 0;
              LOBYTE(v78) = (int)((double)*(unsigned __int8 *)(v79 + 4LL * j) * v27);
              BYTE1(v78) = (int)((double)*(unsigned __int8 *)(v79 + 4LL * j + 1) * v27);
              BYTE2(v78) = (int)((double)*(unsigned __int8 *)(v79 + 4LL * j + 2) * v27);
              HIBYTE(v78) = (int)((double)*(unsigned __int8 *)(v79 + 4LL * j + 3) * v27);
              v72[0] = v78;
              if ( *(_DWORD *)(v29 + 28) )
                NearestColor::GetNearestSupportedProgrammableColorAndDeviceChannels(
                  (const struct Windows::UI::Color *)v72,
                  (const struct LampAttributes *)v29,
                  v13,
                  (struct LampColor *)&v69);
              else
                NearestColor::GetNearestSupportedFixedColorAndDeviceChannels(
                  (const struct Windows::UI::Color *)v72,
                  (const struct LampAttributes *)v29,
                  v13,
                  (struct LampColor *)&v69);
              if ( !*((_BYTE *)this + 152) )
              {
                LOBYTE(v75[0]) = (int)((double)*(unsigned __int8 *)(v32 + 4LL * j) * v30);
                BYTE1(v75[0]) = (int)((double)*(unsigned __int8 *)(v32 + 4LL * j + 1) * v30);
                BYTE2(v75[0]) = (int)((double)*(unsigned __int8 *)(v32 + 4LL * j + 2) * v30);
                HIBYTE(v75[0]) = (int)((double)*(unsigned __int8 *)(v32 + 4LL * j + 3) * v30);
                v72[0] = v75[0];
                if ( *(_DWORD *)(v29 + 28) )
                  NearestColor::GetNearestSupportedProgrammableColorAndDeviceChannels(
                    (const struct Windows::UI::Color *)v72,
                    (const struct LampAttributes *)v29,
                    v13,
                    (struct LampColor *)&v74);
                else
                  NearestColor::GetNearestSupportedFixedColorAndDeviceChannels(
                    (const struct Windows::UI::Color *)v72,
                    (const struct LampAttributes *)v29,
                    v13,
                    (struct LampColor *)&v74);
                if ( !*((_BYTE *)this + 152) )
                {
                  v33 = v69;
LABEL_74:
                  LODWORD(v67) = j;
                  BYTE4(v67) = v33;
                  *(_WORD *)((char *)&v67 + 5) = *(_WORD *)((char *)&v69 + 1);
                  HIBYTE(v67) = HIBYTE(v69);
                  if ( *((_QWORD *)&v70 + 1) == v71 )
                  {
                    std::vector<LampUpdateState>::_Emplace_reallocate<LampUpdateState>(
                      &v70,
                      *((_QWORD *)&v70 + 1),
                      &v67);
                  }
                  else
                  {
                    **((_QWORD **)&v70 + 1) = v67;
                    *((_QWORD *)&v70 + 1) += 8LL;
                  }
                  continue;
                }
              }
              v33 = v69;
              if ( (_BYTE)v69 != (_BYTE)v74
                || *(_WORD *)((char *)&v69 + 1) != *(_WORD *)((char *)&v74 + 1)
                || HIBYTE(v69) != HIBYTE(v74) )
              {
                goto LABEL_74;
              }
            }
          }
          if ( *((_QWORD *)&v70 + 1) != (_QWORD)v70 )
          {
            v34 = (struct HidLampArrayDevice *)*((_QWORD *)this + 3);
            v67 = 0;
            v35 = HidLampMultiUpdateReportBuilder::CreateAndInitialize(
                    v34,
                    *(_DWORD *)(*((_QWORD *)v34 + 77) + 56LL),
                    &v67);
            v36 = v35;
            if ( v35 >= 0 )
            {
              v37 = v67;
              v67 = 0;
              v38 = HidLampRangeUpdateReportBuilder::CreateAndInitialize(
                      *((struct HidLampArrayDevice **)this + 3),
                      &v67);
              v36 = v38;
              if ( v38 >= 0 )
              {
                v39 = v67;
                v40 = (HidLampRangeUpdateReportBuilder *)operator new[](
                                                           (__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3,
                                                           (const struct std::nothrow_t *)&std::nothrow);
                v41 = v40;
                v67 = v40;
                if ( v40 )
                {
                  v42 = 0;
                  memset_0(v40, 0, (__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3);
                  for ( k = 0; ; ++k )
                  {
                    v44 = (__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3;
                    if ( k >= v44 )
                      break;
                    if ( HidLampRangeUpdateReportBuilder::CanIncludeInNextUpdate(
                           v39,
                           (struct LampUpdateState *)(v70 + 8LL * k)) )
                    {
                      if ( *((_BYTE *)v39 + 16) )
                      {
                        ++*((_DWORD *)v39 + 7);
                      }
                      else
                      {
                        *((_BYTE *)v39 + 32) = *(_BYTE *)(v46 + 8 * v45 + 4);
                        *((_BYTE *)v39 + 33) = *(_BYTE *)(v46 + 8 * v45 + 5);
                        *((_BYTE *)v39 + 34) = *(_BYTE *)(v46 + 8 * v45 + 6);
                        *((_BYTE *)v39 + 35) = *(_BYTE *)(v46 + 8 * v45 + 7);
                        *((_DWORD *)v39 + 6) = *(_DWORD *)(v46 + 8 * v45);
                        *((_DWORD *)v39 + 7) = *(_DWORD *)(v46 + 8 * v45);
                        *((_BYTE *)v39 + 16) = 1;
                      }
                      if ( v45 != ((__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3) - 1 )
                        continue;
                    }
                    if ( HidLampRangeUpdateReportBuilder::CurrentIncludedLampStates(v39) >= *((_DWORD *)v37 + 4) )
                    {
                      v42 += HidLampRangeUpdateReportBuilder::CurrentIncludedLampStates(v47);
                      if ( v42 >= (unsigned __int64)((__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3) )
                        *((_DWORD *)v39 + 5) |= 1u;
                      *v81 = 1;
                      updated = HidLampArrayDevice::SendLampRangeUpdateReport(
                                  *((HidLampArrayDevice **)v39 + 5),
                                  (HidLampRangeUpdateReportBuilder *)((char *)v39 + 20));
                      v49 = updated;
                      if ( updated < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x77,
                          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hid"
                                        "lamprangeupdatereportbuilder.cpp",
                          (const char *)(unsigned int)updated,
                          v63);
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x26F,
                          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lam"
                                        "parraydevice.cpp",
                          (const char *)v49,
                          v66);
                        VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v67);
                        InputContext::Release(v39);
                        InputContext::Release(v37);
                        if ( (_QWORD)v70 )
                        {
                          std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
                          v70 = 0;
                          v71 = 0;
                        }
LABEL_117:
                        std::vector<Windows::UI::Color>::_Tidy(&v79);
                        v77 = 0;
                        lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
                        WindowsDeleteString(string);
                        string = 0;
                        _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
                        return v49;
                      }
                      v50 = HidLampRangeUpdateReportBuilder::CurrentIncludedLampStates(v39);
                      if ( v52 > v52 - v50 )
                      {
                        do
                        {
                          *((_BYTE *)v41 + v51) = 1;
                          v53 = HidLampRangeUpdateReportBuilder::CurrentIncludedLampStates(v39);
                        }
                        while ( v51 > v54 - v53 );
                      }
                    }
                    *(_OWORD *)((char *)v39 + 20) = 0;
                    *((_BYTE *)v39 + 16) = 0;
                  }
                  if ( v42 >= v44 )
                  {
LABEL_144:
                    *((double *)this + 20) = v27;
                    if ( (__int128 *)((char *)this + 168) != &v79 )
                    {
                      std::vector<Windows::UI::Color>::_Tidy((char *)this + 168);
                      *(_OWORD *)((char *)this + 168) = v79;
                      *((_QWORD *)this + 23) = v80;
                      v79 = 0;
                      v80 = 0;
                    }
                    *((_BYTE *)this + 152) = 1;
                    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v67);
                    if ( v39 )
                      InputContext::Release(v39);
                    if ( v37 )
                      InputContext::Release(v37);
                    if ( (_QWORD)v70 )
                    {
                      std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
                      v70 = 0;
                      v71 = 0;
                    }
                    goto LABEL_81;
                  }
                  for ( m = 0; m < (unsigned __int64)((__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3); ++m )
                  {
                    if ( !*((_BYTE *)v41 + m) )
                    {
                      HidLampMultiUpdateReportBuilder::IncludeInNextUpdate(
                        v37,
                        (struct LampUpdateState *)(v70 + 8LL * m));
                      ++v42;
                      if ( *((_DWORD *)v37 + 6) >= *((_DWORD *)v37 + 4) )
                      {
                        if ( v42 >= (unsigned __int64)((__int64)(*((_QWORD *)&v70 + 1) - v70) >> 3) )
                          *((_DWORD *)v37 + 7) |= 1u;
                        *v81 = 1;
                        v56 = HidLampMultiUpdateReportBuilder::SendLampStateUpdate(v37);
                        v49 = v56;
                        if ( v56 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x293,
                            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\l"
                                          "amparraydevice.cpp",
                            (const char *)(unsigned int)v56,
                            v63);
                          VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v67);
                          if ( v39 )
                            InputContext::Release(v39);
                          InputContext::Release(v37);
                          if ( (_QWORD)v70 )
                          {
                            std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
                            v70 = 0;
                            v71 = 0;
                          }
                          goto LABEL_117;
                        }
                        HidLampMultiUpdateReportBuilder::Reset(v37);
                      }
                    }
                  }
                  if ( !*((_DWORD *)v37 + 6) )
                    goto LABEL_144;
                  *((_DWORD *)v37 + 7) |= 1u;
                  *v81 = 1;
                  v57 = HidLampMultiUpdateReportBuilder::SendLampStateUpdate(v37);
                  v58 = v57;
                  if ( v57 >= 0 )
                    goto LABEL_144;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2A1,
                    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparraydevice.cpp",
                    (const char *)(unsigned int)v57,
                    v63);
                  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v67);
                  if ( v39 )
                    InputContext::Release(v39);
                  InputContext::Release(v37);
                  if ( (_QWORD)v70 )
                  {
                    std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
                    v70 = 0;
                    v71 = 0;
                  }
                  std::vector<Windows::UI::Color>::_Tidy(&v79);
                  v77 = 0;
                  lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
                  WindowsDeleteString(string);
                  string = 0;
                  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
                  return v58;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x253,
                    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparraydevice.cpp",
                    (const char *)0x8007000ELL,
                    v63);
                  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v67);
                  if ( v39 )
                    InputContext::Release(v39);
                  if ( v37 )
                    InputContext::Release(v37);
                  if ( (_QWORD)v70 )
                  {
                    std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
                    v70 = 0;
                    v71 = 0;
                  }
                  std::vector<Windows::UI::Color>::_Tidy(&v79);
                  v77 = 0;
                  lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
                  WindowsDeleteString(string);
                  string = 0;
                  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
                  return 2147942414LL;
                }
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x409,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
                (const char *)(unsigned int)v38,
                v63);
              if ( v67 )
                InputContext::Release(v67);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x24F,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparraydevice.cpp",
                (const char *)v36,
                v65);
              if ( v37 )
                InputContext::Release(v37);
              if ( (_QWORD)v70 )
              {
                std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
                v70 = 0;
                v71 = 0;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3FA,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
                (const char *)(unsigned int)v35,
                v63);
              if ( v67 )
                InputContext::Release(v67);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x24C,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparraydevice.cpp",
                (const char *)v36,
                v64);
              if ( (_QWORD)v70 )
              {
                std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
                v70 = 0;
                v71 = 0;
              }
            }
            std::vector<Windows::UI::Color>::_Tidy(&v79);
            v77 = 0;
            lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
            WindowsDeleteString(string);
            string = 0;
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
            return v36;
          }
          if ( (_QWORD)v70 )
          {
            std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
            v70 = 0;
            v71 = 0;
          }
LABEL_81:
          std::vector<Windows::UI::Color>::_Tidy(&v79);
          v77 = 0;
          lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
          WindowsDeleteString(string);
          string = 0;
          _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
          return 0;
        }
LABEL_153:
        if ( *((_BYTE *)this + 152) )
        {
          v59 = HidLampArrayDevice::SetAutonomousMode(*((HidLampArrayDevice **)this + 3), 1);
          v62 = v59;
          if ( v59 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F2,
              (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparraydevice.cpp",
              (const char *)(unsigned int)v59,
              v63);
            v77 = 0;
            lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
            WindowsDeleteString(string);
            string = 0;
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
            return v62;
          }
          if ( (unsigned int)dword_180241248 > 5 )
          {
            v81 = (bool *)StringRawBuffer;
            v67 = (HidLampRangeUpdateReportBuilder *)"LampArray entering autonomous mode";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (unsigned int)&dword_180241248,
              (unsigned int)byte_180207693,
              v60,
              v61,
              (__int64)&v67,
              (__int64)&v81);
          }
        }
        *((_BYTE *)this + 152) = 0;
        v77 = 0;
        lambda_e1eed36a7c23502c561de1b66eca617a_::operator()(&v76);
        WindowsDeleteString(string);
        string = 0;
        _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v82);
        return 0;
      }
    }
    *((_QWORD *)this + 13) = a2;
    if ( !a2 )
      goto LABEL_153;
    goto LABEL_30;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2AB,
                           (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\la"
                                         "mparraydevice.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x180084938  mov     r11, rsp
0x18008493b  push    rbx
0x18008493c  push    rsi
0x18008493d  push    rdi
0x18008493e  push    r12
0x180084940  push    r13
0x180084942  push    r14
0x180084944  push    r15
0x180084946  sub     rsp, 110h
0x18008494d  movaps  xmmword ptr [r11-48h], xmm6
0x180084952  movaps  xmmword ptr [r11-58h], xmm7
0x180084957  mov     rax, cs:__security_cookie
0x18008495e  xor     rax, rsp
0x180084961  mov     [rsp+148h+var_60], rax
0x180084969  mov     [rsp+148h+var_90], r8
0x180084971  mov     rdi, rdx
0x180084974  mov     r14, rcx
0x180084977  xor     r12d, r12d
0x18008497a  mov     [r8], r12b
0x18008497d  mov     [r11-88h], r12d
0x180084984  mov     [r11-84h], r12b
0x18008498b  mov     eax, cs:dword_180241248
0x180084991  lea     r15d, [r12+5]
0x180084996  cmp     eax, r15d
0x180084999  jbe     short loc_1800849D8
0x18008499b  lea     rdx, [r11-80h]; ActivityId
0x18008499f  lea     ecx, [r12+3]; ControlCode
0x1800849a4  call    cs:__imp_EventActivityIdControl
0x1800849aa  movups  xmm0, [rsp+148h+var_80]
0x1800849b2  movdqu  xmmword ptr [rsp+148h+ActivityId.Data1], xmm0
0x1800849bb  lea     rdx, [rsp+148h+ActivityId]; ActivityId
0x1800849c3  lea     ecx, [r12+4]; ControlCode
0x1800849c8  call    cs:__imp_EventActivityIdControl
0x1800849ce  mov     [rsp+148h+var_84], 1
0x1800849d6  jmp     short loc_1800849E3
0x1800849d8  xorps   xmm0, xmm0
0x1800849db  movups  [rsp+148h+var_80], xmm0
0x1800849e3  mov     [rsp+148h+var_88], 1
0x1800849ee  mov     eax, cs:dword_180241248
0x1800849f4  cmp     eax, r15d
0x1800849f7  jbe     short loc_180084A53
0x1800849f9  cmp     [rsp+148h+var_84], r12b
0x180084a01  jz      short loc_180084A35
0x180084a03  cmp     [rsp+148h+ActivityId.Data1], r12d
0x180084a0b  jnz     short loc_180084A2B
0x180084a0d  cmp     dword ptr [rsp+148h+ActivityId.Data2], r12d
0x180084a15  jnz     short loc_180084A2B
0x180084a17  cmp     dword ptr [rsp+148h+ActivityId.Data4], r12d
0x180084a1f  jnz     short loc_180084A2B
0x180084a21  cmp     dword ptr [rsp+148h+ActivityId.Data4+4], r12d
0x180084a29  jz      short loc_180084A35
0x180084a2b  lea     r9, [rsp+148h+ActivityId]
0x180084a33  jmp     short loc_180084A38
0x180084a35  mov     r9, r12
0x180084a38  lea     r8, [rsp+148h+var_80]
0x180084a40  lea     rdx, byte_1802074FF
0x180084a47  lea     rcx, dword_180241248
0x180084a4e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180084a53  mov     [rsp+148h+string], r12
0x180084a58  mov     rbx, [r14+10h]
0x180084a5c  xor     ecx, ecx; string
0x180084a5e  call    cs:__imp_WindowsDeleteString
0x180084a64  mov     [rsp+148h+string], r12
0x180084a69  lea     rdx, [rsp+148h+string]; HSTRING *
0x180084a6e  mov     rcx, rbx; this
0x180084a71  call    ?GetInstanceId@PnpDevice@@QEAAJPEAPEAUHSTRING__@@@Z; PnpDevice::GetInstanceId(HSTRING__ * *)
0x180084a76  mov     ebx, eax
0x180084a78  test    eax, eax
0x180084a7a  jns     short loc_180084ABD
0x180084a7c  mov     rcx, [rsp+148h]; this
0x180084a84  mov     r9d, eax; char *
0x180084a87  lea     r8, aOnecoreuapWind_140; "onecoreuap\\windows\\moderncore\\inputv"...
0x180084a8e  mov     edx, 1B1h; void *
0x180084a93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084a98  nop
0x180084a99  mov     rcx, [rsp+148h+string]; string
0x180084a9e  call    cs:__imp_WindowsDeleteString
0x180084aa4  mov     [rsp+148h+string], r12
0x180084aa9  lea     rcx, [rsp+148h+var_88]
0x180084ab1  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hMinInputTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180084ab6  mov     eax, ebx
0x180084ab8  jmp     loc_180085A85
0x180084abd  xor     edx, edx; length
0x180084abf  mov     rcx, [rsp+148h+string]; string
0x180084ac4  call    cs:__imp_WindowsGetStringRawBuffer
0x180084aca  mov     rsi, rax
0x180084acd  lea     rax, [rsp+148h+var_88]
0x180084ad5  mov     [rsp+148h+var_C0], rax
0x180084add  mov     [rsp+148h+var_B8], 1
0x180084ae5  test    rdi, rdi
0x180084ae8  jz      short loc_180084B43
0x180084aea  mov     ecx, cs:dword_180241248
0x180084af0  cmp     ecx, r15d
0x180084af3  jbe     loc_180084B9B
0x180084af9  mov     [rsp+148h+var_108], rsi
0x180084afe  mov     eax, [rdi+18h]
0x180084b01  mov     [rsp+148h+var_D8], eax
0x180084b05  lea     rax, aUpdatingViewcl; "Updating ViewClient"
0x180084b0c  mov     qword ptr [rsp+148h+var_C8], rax
0x180084b14  lea     rax, [rsp+148h+var_108]
0x180084b19  mov     [rsp+148h+var_118], rax
0x180084b1e  lea     rax, [rsp+148h+var_D8]
0x180084b23  mov     [rsp+148h+var_120], rax
0x180084b28  lea     rax, [rsp+148h+var_C8]
0x180084b30  mov     qword ptr [rsp+148h+var_128], rax
0x180084b35  lea     rdx, dword_18020752C
0x180084b3c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180084b41  jmp     short loc_180084B9B
0x180084b43  mov     eax, cs:dword_180241248
0x180084b49  cmp     eax, r15d
0x180084b4c  jbe     short loc_180084B9B
0x180084b4e  mov     [rsp+148h+var_108], rsi
0x180084b53  lea     rax, aNull; "null"
0x180084b5a  mov     qword ptr [rsp+148h+var_D8], rax
0x180084b5f  lea     rax, aUpdatingViewcl; "Updating ViewClient"
0x180084b66  mov     qword ptr [rsp+148h+var_C8], rax
0x180084b6e  lea     rax, [rsp+148h+var_108]
0x180084b73  mov     [rsp+148h+var_118], rax
0x180084b78  lea     rax, [rsp+148h+var_D8]
0x180084b7d  mov     [rsp+148h+var_120], rax
0x180084b82  lea     rax, [rsp+148h+var_C8]
0x180084b8a  mov     qword ptr [rsp+148h+var_128], rax; int
0x180084b8f  lea     rdx, byte_18020757B
0x180084b96  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180084b9b  mov     rcx, [r14+68h]
0x180084b9f  cmp     rdi, rcx
0x180084ba2  jz      loc_180084CA4
0x180084ba8  mov     bl, 1
0x180084baa  test    rcx, rcx
0x180084bad  jz      short loc_180084C27
0x180084baf  mov     rcx, [rcx+20h]
0x180084bb3  mov     eax, r12d
0x180084bb6  xchg    eax, [rcx+1070h]
0x180084bbc  mov     rax, [r14+68h]
0x180084bc0  mov     rcx, [rax+10h]
0x180084bc4  mov     rax, [rcx]
0x180084bc7  mov     rax, [rax+48h]
0x180084bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bd0  mov     eax, cs:dword_180241248
0x180084bd6  cmp     eax, r15d
0x180084bd9  jbe     short loc_180084C27
0x180084bdb  mov     [rsp+148h+var_108], rsi
0x180084be0  mov     rax, [r14+68h]
0x180084be4  mov     ecx, [rax+18h]
0x180084be7  mov     [rsp+148h+var_D8], ecx
0x180084beb  lea     rax, aViewclientLosi; "ViewClient losing availability"
0x180084bf2  mov     qword ptr [rsp+148h+var_C8], rax
0x180084bfa  lea     rax, [rsp+148h+var_108]
0x180084bff  mov     [rsp+148h+var_118], rax
0x180084c04  lea     rax, [rsp+148h+var_D8]
0x180084c09  mov     [rsp+148h+var_120], rax
0x180084c0e  lea     rax, [rsp+148h+var_C8]
0x180084c16  mov     qword ptr [rsp+148h+var_128], rax
0x180084c1b  lea     rdx, word_1802075CA
0x180084c22  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180084c27  test    rdi, rdi
0x180084c2a  jz      short loc_180084CA7
0x180084c2c  mov     rcx, [rdi+20h]
0x180084c30  mov     eax, 1
0x180084c35  xchg    eax, [rcx+1070h]
0x180084c3b  mov     rcx, [rdi+10h]
0x180084c3f  mov     rax, [rcx]
0x180084c42  mov     rax, [rax+48h]
0x180084c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c4b  mov     eax, cs:dword_180241248
0x180084c51  cmp     eax, r15d
0x180084c54  jbe     short loc_180084C9E
0x180084c56  mov     [rsp+148h+var_108], rsi
0x180084c5b  mov     eax, [rdi+18h]
0x180084c5e  mov     [rsp+148h+var_D8], eax
0x180084c62  lea     rax, aViewclientGain; "ViewClient gaining availability"
0x180084c69  mov     qword ptr [rsp+148h+var_C8], rax
0x180084c71  lea     rax, [rsp+148h+var_108]
0x180084c76  mov     [rsp+148h+var_118], rax
0x180084c7b  lea     rax, [rsp+148h+var_D8]
0x180084c80  mov     [rsp+148h+var_120], rax
0x180084c85  lea     rax, [rsp+148h+var_C8]
0x180084c8d  mov     qword ptr [rsp+148h+var_128], rax
0x180084c92  lea     rdx, dword_180207644
0x180084c99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180084c9e  mov     [r14+68h], rdi
0x180084ca2  jmp     short loc_180084CB4
0x180084ca4  mov     bl, r12b
0x180084ca7  mov     [r14+68h], rdi
0x180084cab  test    rdi, rdi
0x180084cae  jz      loc_180085985
0x180084cb4  mov     rax, [rdi+20h]
0x180084cb8  mov     ecx, [rax+1004h]
0x180084cbe  nop
0x180084cbf  test    ecx, ecx
0x180084cc1  jz      loc_180085985
0x180084cc7  mov     rax, [rdi+20h]
0x180084ccb  mov     ecx, r12d
0x180084cce  xchg    ecx, [rax+1000h]
0x180084cd4  test    ecx, ecx
0x180084cd6  setnz   al
0x180084cd9  test    bl, bl
0x180084cdb  jnz     short loc_180084D24
0x180084cdd  test    al, al
0x180084cdf  jnz     short loc_180084D24
0x180084ce1  cmp     [r14+98h], r12b
0x180084ce8  jz      short loc_180084D31
0x180084cea  mov     [rsp+148h+var_B8], r12b
0x180084cf2  lea     rcx, [rsp+148h+var_C0]
0x180084cfa  call    _lambda_e1eed36a7c23502c561de1b66eca617a___operator__
0x180084cff  nop
0x180084d00  mov     rcx, [rsp+148h+string]; string
0x180084d05  call    cs:__imp_WindowsDeleteString
0x180084d0b  mov     [rsp+148h+string], r12
0x180084d10  lea     rcx, [rsp+148h+var_88]
0x180084d18  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hMinInputTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180084d1d  xor     eax, eax
0x180084d1f  jmp     loc_180085A85
0x180084d24  cmp     [r14+98h], r12b
0x180084d2b  jnz     loc_180084DDC
0x180084d31  xor     edx, edx; bool
0x180084d33  mov     rcx, [r14+18h]; this
0x180084d37  call    ?SetAutonomousMode@HidLampArrayDevice@@QEAAJ_N@Z; HidLampArrayDevice::SetAutonomousMode(bool)
0x180084d3c  mov     ebx, eax
0x180084d3e  test    eax, eax
0x180084d40  jns     short loc_180084D99
0x180084d42  mov     rcx, [rsp+148h]; this
0x180084d4a  mov     r9d, eax; char *
0x180084d4d  lea     r8, aOnecoreuapWind_140; "onecoreuap\\windows\\moderncore\\inputv"...
0x180084d54  mov     edx, 1FFh; void *
0x180084d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084d5e  nop
0x180084d5f  mov     [rsp+148h+var_B8], r12b
0x180084d67  lea     rcx, [rsp+148h+var_C0]
0x180084d6f  call    _lambda_e1eed36a7c23502c561de1b66eca617a___operator__
0x180084d74  nop
0x180084d75  mov     rcx, [rsp+148h+string]; string
0x180084d7a  call    cs:__imp_WindowsDeleteString
0x180084d80  mov     [rsp+148h+string], r12
0x180084d85  lea     rcx, [rsp+148h+var_88]
0x180084d8d  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hMinInputTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hMinInputTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180084d92  mov     eax, ebx
0x180084d94  jmp     loc_180085A85
0x180084d99  mov     eax, cs:dword_180241248
0x180084d9f  cmp     eax, r15d
0x180084da2  jbe     short loc_180084DDC
0x180084da4  mov     [rsp+148h+var_108], rsi
0x180084da9  lea     rax, aLamparrayLeavi; "LampArray leaving autonomous mode"
0x180084db0  mov     qword ptr [rsp+148h+var_D8], rax
0x180084db5  lea     rax, [rsp+148h+var_108]
0x180084dba  mov     [rsp+148h+var_120], rax
0x180084dbf  lea     rax, [rsp+148h+var_D8]
0x180084dc4  mov     qword ptr [rsp+148h+var_128], rax; int
0x180084dc9  lea     rdx, byte_1802076DD
0x180084dd0  lea     rcx, dword_180241248
0x180084dd7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180084ddc  mov     rax, [r14+18h]
0x180084de0  movsxd  r13, dword ptr [rax+220h]
0x180084de7  mov     rsi, [rdi+20h]
0x180084deb  movsd   xmm7, qword ptr [rsi+1060h]
0x180084df3  xorps   xmm0, xmm0
0x180084df6  movdqu  [rsp+148h+var_A8], xmm0
0x180084dff  mov     [rsp+148h+var_98], r12
0x180084e07  mov     rbx, r13
0x180084e0a  mov     [rsp+148h+var_108], rbx
0x180084e0f  test    r13d, r13d
0x180084e12  jz      short loc_180084E39
0x180084e14  mov     rax, 3FFFFFFFFFFFFFFFh
0x180084e1e  cmp     rbx, rax
0x180084e21  ja      loc_180085AB6
0x180084e27  lea     rdx, [rsp+148h+var_108]
0x180084e2c  lea     rcx, [rsp+148h+var_A8]
0x180084e34  call    ??$_Reallocate@$00@?$vector@KV?$allocator@K@std@@@std@@AEAAXAEA_K@Z; std::vector<ulong>::_Reallocate<1>(unsigned __int64 &)
0x180084e39  mov     edi, r12d
0x180084e3c  cmp     edi, r13d
0x180084e3f  jge     short loc_180084E90
0x180084e41  movsxd  rax, dword ptr [rsi+20Ch]
0x180084e48  lea     r8, [rax+rax*8]
0x180084e4c  movsxd  rax, edi
0x180084e4f  add     r8, 51Ah
0x180084e56  add     r8, rax
0x180084e59  lea     r8, [rsi+r8*4]
0x180084e5d  mov     rdx, qword ptr [rsp+148h+var_A8+8]
0x180084e65  cmp     rdx, [rsp+148h+var_98]
0x180084e6d  jz      short loc_180084E7F
0x180084e6f  mov     eax, [r8]
0x180084e72  mov     [rdx], eax
0x180084e74  add     qword ptr [rsp+148h+var_A8+8], 4
0x180084e7d  jmp     short loc_180084E8C
0x180084e7f  lea     rcx, [rsp+148h+var_A8]
0x180084e87  call    ??$_Emplace_reallocate@AEBUColor@UI@Windows@@@?$vector@UColor@UI@Windows@@V?$allocator@UColor@UI@Windows@@@std@@@std@@AEAAPEAUColor@UI@Windows@@QEAU234@AEBU234@@Z; std::vector<Windows::UI::Color>::_Emplace_reallocate<Windows::UI::Color const &>(Windows::UI::Color * const,Windows::UI::Color const &)
0x180084e8c  inc     edi
0x180084e8e  jmp     short loc_180084E3C
0x180084e90  mov     rax, [r14+18h]
0x180084e94  mov     r15, [rax+238h]
0x180084e9b  xorps   xmm0, xmm0
0x180084e9e  movdqu  [rsp+148h+var_F0], xmm0
0x180084ea4  mov     [rsp+148h+var_E0], r12
0x180084ea9  mov     [rsp+148h+var_108], rbx
0x180084eae  test    r13d, r13d
0x180084eb1  jz      short loc_180084ED5
0x180084eb3  mov     rax, 1FFFFFFFFFFFFFFFh
0x180084ebd  cmp     rbx, rax
0x180084ec0  ja      loc_180085ABC
0x180084ec6  lea     rdx, [rsp+148h+var_108]
  ... truncated ...
```
