# Microsoft::Diagnostics::TraceSessionUsage::UpdateTraceSessionDetails(std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Microsoft::Diagnostics::TraceSessionDetails,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Microsoft::Diagnostics::TraceSessionDetails>>> &)

- ea: `0x1800a92a4`
- end: `0x1800a9c42`
- name: `?UpdateTraceSessionDetails@TraceSessionUsage@Diagnostics@Microsoft@@QEAAJAEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UTraceSessionDetails@Diagnostics@Microsoft@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UTraceSessionDetails@Diagnostics@Microsoft@@@std@@@2@@std@@@Z`
- size: `2462`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180049f14`
- `0x1800a8ef0`

## callees

- `0x18001d9a0`
- `0x18002abb4`
- `0x18002b318`
- `0x18002be90`
- `0x18002df00`
- `0x1800300c8`
- `0x1800327b4`
- `0x18006bc74`
- `0x18008abf4`
- `0x1800a8ed4`
- `0x1800a9214`
- `0x1800a9270`
- `0x1800a92a4`
- `0x1800a9c48`
- `0x1800aa07c`
- `0x1801a38f4`
- `0x1801a42f8`
- `0x1801af5f0`
- `0x18020aac0`
- `0x18020bab8`
- `0x180369010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a9c2f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a9c2f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a9402`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a9439`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a9470`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a94a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a9402`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a9439`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a9470`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a94a7`
- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterData` at `0x1800a959d`
- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterData` at `0x1800a959d`
- `api-ms-win-perf-legacy-l1-1-0!PerfAddCounters` at `0x1800a956a`
- `api-ms-win-perf-legacy-l1-1-0!PerfAddCounters` at `0x1800a956a`
- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterSetRegistrationInfo` at `0x1800a9381`
- `api-ms-win-perf-legacy-l1-1-0!PerfQueryCounterSetRegistrationInfo` at `0x1800a9381`
- `api-ms-win-perf-legacy-l1-1-0!PerfCloseQueryHandle` at `0x1800a98b1`
- `api-ms-win-perf-legacy-l1-1-0!PerfCloseQueryHandle` at `0x1800a993f`
- `api-ms-win-perf-legacy-l1-1-0!PerfCloseQueryHandle` at `0x1800a99c5`
- `api-ms-win-perf-legacy-l1-1-0!PerfCloseQueryHandle` at `0x1800a9a01`
- `api-ms-win-perf-legacy-l1-1-0!PerfCloseQueryHandle` at `0x1800a9b21`
- `api-ms-win-perf-legacy-l1-1-0!PerfCloseQueryHandle` at `0x1800a9bc3`
- `api-ms-win-perf-legacy-l1-1-0!PerfOpenQueryHandle` at `0x1800a92e9`
- `api-ms-win-perf-legacy-l1-1-0!PerfOpenQueryHandle` at `0x1800a92e9`

## string_xrefs

- `0x1800a98fd`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1800a995b`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1800a99e4`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1800a9ab2`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`
- `0x1800a9b54`: `onecore\base\telemetry\utc\service\analysis\tracesessionusage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Diagnostics::TraceSessionUsage::UpdateTraceSessionDetails(__int64 a1, __int64 *a2)
{
  ULONG v2; // eax
  LPBYTE v3; // rdi
  int i; // ebx
  ULONG CounterSetRegistrationInfo; // eax
  LPBYTE v6; // r15
  int v7; // edi
  BYTE *v8; // rbx
  BYTE *v9; // rsi
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  unsigned __int64 v15; // r14
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // r14
  __int64 v19; // r8
  __int64 v20; // rcx
  unsigned __int64 v21; // r14
  __int64 v22; // r8
  __int64 **v23; // rdx
  ULONG v24; // eax
  int v25; // ebx
  ULONG CounterData; // eax
  __int64 v27; // rbx
  LPBYTE v28; // rdi
  LPBYTE v29; // rbx
  const char *v30; // r9
  __int64 v31; // r15
  BYTE *v32; // rdi
  int v33; // r14d
  __int64 v34; // r12
  __int64 v35; // r13
  __int64 *v36; // rsi
  unsigned __int64 v37; // rax
  const void *v38; // rcx
  __int64 v39; // r10
  BYTE *v40; // rcx
  unsigned int v41; // r11d
  BYTE *v42; // rdx
  __int64 v43; // rdx
  __int64 *v44; // rcx
  __int64 *v45; // r8
  __int64 *v46; // rax
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  __int64 v50; // rax
  __int128 v51; // xmm6
  __int64 v52; // rcx
  __int64 v53; // rsi
  char *v54; // rax
  _QWORD *v55; // rcx
  __int64 v56; // r8
  const char *v57; // r9
  __int64 result; // rax
  unsigned int v59; // ebx
  unsigned int v60; // ebx
  unsigned int v61; // ebx
  __int64 v62; // rbx
  LPBYTE v63; // rdi
  BYTE *v64; // rax
  unsigned int v65; // ebx
  unsigned int v66; // ebx
  size_t v67; // rbx
  unsigned int pbRegInfo; // [rsp+20h] [rbp-148h]
  unsigned int pbRegInfoa; // [rsp+20h] [rbp-148h]
  char v70[8]; // [rsp+40h] [rbp-128h] BYREF
  LPBYTE v71[2]; // [rsp+48h] [rbp-120h] BYREF
  __int64 v72; // [rsp+58h] [rbp-110h]
  __int128 v73; // [rsp+60h] [rbp-108h] BYREF
  HANDLE phQuery; // [rsp+70h] [rbp-F8h] BYREF
  __int64 *v75; // [rsp+78h] [rbp-F0h] BYREF
  DWORD pcbCounterBlockActual[4]; // [rsp+80h] [rbp-E8h] BYREF
  _QWORD v77[2]; // [rsp+90h] [rbp-D8h] BYREF
  __int64 *v78; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-C0h]
  _OWORD v80[2]; // [rsp+B0h] [rbp-B8h] BYREF
  _OWORD v81[2]; // [rsp+D0h] [rbp-98h] BYREF
  _PERF_COUNTER_IDENTIFIER pCounters; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v83; // [rsp+118h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v75 = a2;
  phQuery = 0;
  v2 = PerfOpenQueryHandle(0, &phQuery);
  try
  {
    if ( v2 )
    {
      v61 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x5F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
              (const char *)v2,
              pbRegInfo);
      if ( phQuery )
        PerfCloseQueryHandle(phQuery);
      return v61;
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(v71);
    v3 = v71[1];
    if ( (LPBYTE)(v71[1] - v71[0]) > (LPBYTE)0x190 )
    {
      v64 = v71[0] + 400;
    }
    else
    {
      if ( (LPBYTE)(v71[1] - v71[0]) >= (LPBYTE)0x190 )
      {
LABEL_7:
        for ( i = 0; ; i = 1 )
        {
          pcbCounterBlockActual[0] = 0;
          CounterSetRegistrationInfo = PerfQueryCounterSetRegistrationInfo(
                                         0,
                                         &Microsoft::Diagnostics::TraceSessionUsage::k_EventTracingSessionCounterSetGuid,
                                         PERF_REG_COUNTER_NAME_STRINGS,
                                         0,
                                         v71[0],
                                         LODWORD(v71[1]) - LODWORD(v71[0]),
                                         pcbCounterBlockActual);
          if ( CounterSetRegistrationInfo != 8 )
          {
            if ( CounterSetRegistrationInfo )
            {
LABEL_84:
              v59 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x7F,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
                      (const char *)CounterSetRegistrationInfo,
                      pbRegInfoa);
              if ( v71[0] )
              {
                std::_Deallocate<16>(v71[0], (struct std::nothrow_t *)(v72 - (unsigned __int64)v71[0]));
                *(_OWORD *)v71 = 0;
                v72 = 0;
              }
              if ( phQuery )
                PerfCloseQueryHandle(phQuery);
              return v59;
            }
            v6 = v71[0];
            v73 = 0;
            std::_Tree<std::_Tmap_traits<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<enum OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::_Alloc_sentinel_and_proxy(&v73);
            v7 = 0;
            while ( 2 )
            {
              if ( v7 != *((_DWORD *)v6 + 1) )
              {
                v8 = &v6[8 * v7 + 8];
                if ( (v8[4] & 1) == 0 && *((_DWORD *)v8 + 1) != -1 )
                {
                  v9 = &v6[*((unsigned int *)v8 + 1)];
                  v12 = std::_WChar_traits<wchar_t>::length(v9, 33);
                  v13 = v12;
                  if ( v12 > v10 )
                    v13 = v10;
                  if ( !(unsigned int)_o__wcsnicmp(
                                        v11,
                                        Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsagePaged,
                                        v13)
                    && (_DWORD)v12 == 33 )
                  {
                    v70[0] = 0;
                    std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::Diagnostics::PerfCounterEnum,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::emplace<unsigned long const &,enum Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(
                      &v73,
                      v80,
                      &v6[8 * v7 + 8],
                      v70);
                  }
                  else
                  {
                    v15 = std::_WChar_traits<wchar_t>::length(v9);
                    v16 = v15;
                    if ( v15 > 0x25 )
                      v16 = 37;
                    if ( !(unsigned int)_o__wcsnicmp(
                                          v14,
                                          Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsageNonpaged,
                                          v16)
                      && (_DWORD)v15 == 37 )
                    {
                      v70[0] = 1;
                      v23 = &v78;
                    }
                    else
                    {
                      v18 = std::_WChar_traits<wchar_t>::length(v9);
                      v19 = v18;
                      if ( v18 > 0x15 )
                        v19 = 21;
                      if ( (unsigned int)_o__wcsnicmp(
                                           v17,
                                           Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLogged,
                                           v19)
                        || (_DWORD)v18 != 21 )
                      {
                        v21 = std::_WChar_traits<wchar_t>::length(v9);
                        v22 = v21;
                        if ( v21 > 0xB )
                          v22 = 11;
                        if ( !(unsigned int)_o__wcsnicmp(
                                              v20,
                                              Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLost,
                                              v22)
                          && (_DWORD)v21 == 11 )
                        {
                          v70[0] = 3;
                          std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::Diagnostics::PerfCounterEnum,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::_Emplace<unsigned long const &,enum Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(
                            &v73,
                            pcbCounterBlockActual,
                            &v6[8 * v7 + 8],
                            v70);
                        }
                        goto LABEL_33;
                      }
                      v70[0] = 2;
                      v23 = (__int64 **)v77;
                    }
                    std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::Diagnostics::PerfCounterEnum,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::_Emplace<unsigned long const &,enum Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(
                      &v73,
                      v23,
                      &v6[8 * v7 + 8],
                      v70);
                  }
                }
LABEL_33:
                ++v7;
                continue;
              }
              break;
            }
            pCounters.CounterSetGuid = Microsoft::Diagnostics::TraceSessionUsage::k_EventTracingSessionCounterSetGuid;
            pCounters.Status = 0;
            pCounters.Size = 48;
            *(_QWORD *)&pCounters.CounterId = -1;
            *(_QWORD *)&pCounters.Index = 0;
            v83 = 42;
            v24 = PerfAddCounters(phQuery, &pCounters, 0x30u);
            if ( v24 )
            {
              v65 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xC3,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
                      (const char *)v24,
                      pbRegInfoa);
              std::_Tree_val<std::_Tree_simple_types<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>,void *>>>(
                &v73,
                &v73,
                *(_QWORD *)(v73 + 8));
              std::_Deallocate<16>((void *)v73, (struct std::nothrow_t *)0x28);
              if ( v71[0] )
              {
                std::_Deallocate<16>(v71[0], (struct std::nothrow_t *)(v72 - (unsigned __int64)v71[0]));
                *(_OWORD *)v71 = 0;
                v72 = 0;
              }
              if ( phQuery )
              {
                v75 = (__int64 *)phQuery;
                *(_QWORD *)pcbCounterBlockActual = PerfCloseQueryHandle;
                wistd::invoke<void * (*)(void *),void * &>(pcbCounterBlockActual, &v75);
              }
              return v65;
            }
            v25 = 0;
            while ( 2 )
            {
              pcbCounterBlockActual[0] = 0;
              CounterData = PerfQueryCounterData(
                              phQuery,
                              (PPERF_DATA_HEADER)v71[0],
                              LODWORD(v71[1]) - LODWORD(v71[0]),
                              pcbCounterBlockActual);
              if ( CounterData == 8 )
              {
                if ( v25 )
                  goto LABEL_114;
                v27 = pcbCounterBlockActual[0];
                v28 = v71[0];
                if ( (LPBYTE)pcbCounterBlockActual[0] >= (LPBYTE)(v71[1] - v71[0]) )
                {
                  if ( (LPBYTE)pcbCounterBlockActual[0] <= (LPBYTE)(v71[1] - v71[0]) )
                  {
LABEL_43:
                    v25 = 1;
                    continue;
                  }
                  if ( pcbCounterBlockActual[0] > v72 - (unsigned __int64)v71[0] )
                  {
                    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v71, pcbCounterBlockActual[0]);
                    goto LABEL_43;
                  }
                  memset_0(v71[1], 0, pcbCounterBlockActual[0] - (unsigned __int64)(v71[1] - v71[0]));
                }
                v71[1] = &v28[v27];
                goto LABEL_43;
              }
              break;
            }
            if ( CounterData )
            {
LABEL_114:
              v66 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xD0,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
                      (const char *)CounterData,
                      pbRegInfoa);
              std::_Tree_val<std::_Tree_simple_types<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>,void *>>>(
                &v73,
                &v73,
                *(_QWORD *)(v73 + 8));
              std::_Deallocate<16>((void *)v73, (struct std::nothrow_t *)0x28);
              if ( v71[0] )
              {
                std::_Deallocate<16>(v71[0], (struct std::nothrow_t *)(v72 - (unsigned __int64)v71[0]));
                *(_OWORD *)v71 = 0;
                v72 = 0;
              }
              if ( phQuery )
              {
                v75 = (__int64 *)phQuery;
                v77[0] = PerfCloseQueryHandle;
                wistd::invoke<void * (*)(void *),void * &>(v77, &v75);
              }
              return v66;
            }
            v29 = v71[0];
            v30 = (const char *)*((unsigned int *)v71[0] + 12);
            if ( (_DWORD)v30 )
            {
              v60 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xE5,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
                      v30,
                      pbRegInfoa);
              std::_Tree_val<std::_Tree_simple_types<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>,void *>>>(
                &v73,
                &v73,
                *(_QWORD *)(v73 + 8));
              std::_Deallocate<16>((void *)v73, (struct std::nothrow_t *)0x28);
              if ( v71[0] )
              {
                std::_Deallocate<16>(v71[0], (struct std::nothrow_t *)(v72 - (unsigned __int64)v71[0]));
                *(_OWORD *)v71 = 0;
                v72 = 0;
              }
              if ( phQuery )
                ((void (*)(void))PerfCloseQueryHandle)();
              return v60;
            }
            else
            {
              if ( *((_DWORD *)v71[0] + 1) == 1 && *((_DWORD *)v71[0] + 13) == 6 )
              {
                v31 = *((unsigned int *)v71[0] + 16);
                v32 = &v71[0][v31 + 72];
                v33 = 0;
                v34 = v77[0];
                v35 = v77[0];
                v36 = v75;
                while ( v33 != *(_DWORD *)&v29[v31 + 68] )
                {
                  memset(v81, 0, sizeof(v81));
                  v37 = std::_WChar_traits<wchar_t>::length(v32 + 8);
                  std::wstring::_Construct<1,wchar_t *>(v81, v38, v37);
                  v32 += *(unsigned int *)v32;
                  v39 = 0;
                  if ( *((_DWORD *)v29 + 17) )
                  {
                    do
                    {
                      v40 = v32;
                      v41 = *(_DWORD *)&v29[4 * v39 + 72];
                      v42 = v32;
                      v32 += *((unsigned int *)v32 + 1);
                      if ( *(_DWORD *)v42 == 4 )
                      {
                        v43 = *((unsigned int *)v42 + 2);
                      }
                      else if ( *(_DWORD *)v40 == 8 )
                      {
                        v43 = *((_QWORD *)v42 + 1);
                      }
                      else
                      {
                        v43 = 0;
                      }
                      HIDWORD(v80[0]) = 0;
                      v44 = (__int64 *)v73;
                      v45 = *(__int64 **)(v73 + 8);
                      if ( !*((_BYTE *)v45 + 25) )
                      {
                        do
                        {
                          if ( *((_DWORD *)v45 + 7) >= v41 )
                            v44 = v45;
                          v46 = v45 + 2;
                          if ( *((_DWORD *)v45 + 7) >= v41 )
                            v46 = v45;
                          v45 = (__int64 *)*v46;
                        }
                        while ( !*(_BYTE *)(*v46 + 25) );
                      }
                      if ( *((_BYTE *)v44 + 25) || v41 < *((_DWORD *)v44 + 7) )
                        v44 = (__int64 *)v73;
                      if ( v44 != (__int64 *)v73 )
                      {
                        v47 = *((unsigned __int8 *)v44 + 32);
                        if ( v47 )
                        {
                          v48 = v47 - 1;
                          if ( v48 )
                          {
                            v49 = v48 - 1;
                            if ( v49 )
                            {
                              if ( v49 == 1 )
                                *(_QWORD *)pcbCounterBlockActual = v43;
                            }
                            else
                            {
                              v77[0] = v43;
                            }
                          }
                          else
                          {
                            v35 = v43;
                          }
                        }
                        else
                        {
                          v34 = v43;
                        }
                      }
                      v39 = (unsigned int)(v39 + 1);
                    }
                    while ( (_DWORD)v39 != *((_DWORD *)v29 + 17) );
                  }
                  v50 = std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Diagnostics::IForwarder>,std::less<void>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>,0>>::_Find_lower_bound<std::wstring>(
                          v36,
                          v80,
                          v81);
                  v51 = *(_OWORD *)v50;
                  if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                                           v52,
                                           *(_QWORD *)(v50 + 16),
                                           v81) )
                  {
                    if ( v36[1] == 0x2AAAAAAAAAAAAAALL )
                      std::_Xlength_error("map/set too long");
                    v53 = *v36;
                    v78 = v75;
                    v79 = 0;
                    v54 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x60u);
                    std::wstring::wstring(v54 + 32, v81);
                    v55[4] = v34;
                    v55[5] = v35;
                    v55[6] = v77[0];
                    v55[7] = *(_QWORD *)pcbCounterBlockActual;
                    *(_QWORD *)v56 = v53;
                    *(_QWORD *)(v56 + 8) = v53;
                    *(_QWORD *)(v56 + 16) = v53;
                    *(_WORD *)(v56 + 24) = 0;
                    v79 = 0;
                    v80[0] = v51;
                    v36 = v75;
                    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>>>::_Insert_node(
                      v75,
                      v80,
                      v56);
                  }
                  std::wstring::_Tidy_deallocate(v81);
                  ++v33;
                }
              }
              std::_Tree_val<std::_Tree_simple_types<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>,void *>>>(
                &v73,
                &v73,
                *(_QWORD *)(v73 + 8));
              std::_Deallocate<16>((void *)v73, (struct std::nothrow_t *)0x28);
              if ( v71[0] )
              {
                std::_Deallocate<16>(v71[0], (struct std::nothrow_t *)(v72 - (unsigned __int64)v71[0]));
                *(_OWORD *)v71 = 0;
                v72 = 0;
              }
              if ( phQuery )
                PerfCloseQueryHandle(phQuery);
              return 0;
            }
          }
          if ( i )
            goto LABEL_84;
          v62 = pcbCounterBlockActual[0];
          v63 = v71[0];
          if ( (LPBYTE)pcbCounterBlockActual[0] >= (LPBYTE)(v71[1] - v71[0]) )
          {
            if ( (LPBYTE)pcbCounterBlockActual[0] <= (LPBYTE)(v71[1] - v71[0]) )
              continue;
            if ( pcbCounterBlockActual[0] > v72 - (unsigned __int64)v71[0] )
            {
              std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v71, pcbCounterBlockActual[0]);
              continue;
            }
            memset_0(v71[1], 0, pcbCounterBlockActual[0] - (unsigned __int64)(v71[1] - v71[0]));
          }
          v71[1] = &v63[v62];
        }
      }
      if ( v72 - (unsigned __int64)v71[0] < 0x190 )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v71, 400);
        goto LABEL_7;
      }
      v67 = 400 - (unsigned __int64)(v71[1] - v71[0]);
      memset_0(v71[1], 0, v67);
      v64 = &v3[v67];
    }
    v71[1] = v64;
    goto LABEL_7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12D,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\tracesessionusage.cpp",
                           v57);
  }
  return result;
}

```

## disassembly

```asm
0x1800a92a4  mov     rax, rsp
0x1800a92a7  mov     [rax+8], rbx
0x1800a92ab  mov     [rax+18h], rsi
0x1800a92af  push    rdi
0x1800a92b0  push    r12
0x1800a92b2  push    r13
0x1800a92b4  push    r14
0x1800a92b6  push    r15
0x1800a92b8  sub     rsp, 140h
0x1800a92bf  movaps  xmmword ptr [rax-38h], xmm6
0x1800a92c3  mov     rax, cs:__security_cookie
0x1800a92ca  xor     rax, rsp
0x1800a92cd  mov     [rsp+168h+var_48], rax
0x1800a92d5  mov     [rsp+168h+var_F0], rdx
0x1800a92da  xor     r12d, r12d
0x1800a92dd  mov     [rsp+168h+phQuery], r12
0x1800a92e2  lea     rdx, [rsp+168h+phQuery]; phQuery
0x1800a92e7  xor     ecx, ecx; szMachine
0x1800a92e9  call    cs:__imp_PerfOpenQueryHandle
0x1800a92ef  test    eax, eax
0x1800a92f1  jnz     loc_1800A99D9
0x1800a92f7  lea     rcx, [rsp+168h+var_120]; void *
0x1800a92fc  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1800a9301  nop
0x1800a9302  mov     rdx, [rsp+168h+var_120]
0x1800a9307  mov     rdi, [rsp+168h+var_120+8]
0x1800a930c  mov     rcx, rdi
0x1800a930f  sub     rcx, rdx
0x1800a9312  mov     ebx, 190h
0x1800a9317  cmp     rcx, rbx
0x1800a931a  ja      loc_1800A9A96
0x1800a9320  jnb     short loc_1800A933F
0x1800a9322  mov     rax, [rsp+168h+var_110]
0x1800a9327  sub     rax, rdx
0x1800a932a  cmp     rax, rbx
0x1800a932d  jnb     loc_1800A9BEB
0x1800a9333  mov     edx, ebx
0x1800a9335  lea     rcx, [rsp+168h+var_120]
0x1800a933a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800a933f  mov     ebx, r12d
0x1800a9342  mov     r13d, 1
0x1800a9348  mov     [rsp+168h+pcbCounterBlockActual], r12d
0x1800a9350  mov     rcx, [rsp+168h+var_120]
0x1800a9355  mov     eax, dword ptr [rsp+168h+var_120+8]
0x1800a9359  sub     eax, ecx
0x1800a935b  lea     rdx, [rsp+168h+pcbCounterBlockActual]
0x1800a9363  mov     [rsp+168h+pcbRegInfoActual], rdx; pcbRegInfoActual
0x1800a9368  mov     [rsp+168h+cbRegInfo], eax; cbRegInfo
0x1800a936c  mov     [rsp+168h+pbRegInfo], rcx; unsigned int
0x1800a9371  xor     r9d, r9d; requestLangId
0x1800a9374  lea     r8d, [r9+5]; requestCode
0x1800a9378  lea     rdx, ?k_EventTracingSessionCounterSetGuid@TraceSessionUsage@Diagnostics@Microsoft@@0U_GUID@@B; pCounterSetId
0x1800a937f  xor     ecx, ecx; szMachine
0x1800a9381  call    cs:__imp_PerfQueryCounterSetRegistrationInfo
0x1800a9387  cmp     eax, 8
0x1800a938a  jz      loc_1800A9A15
0x1800a9390  test    eax, eax
0x1800a9392  jnz     loc_1800A98F2
0x1800a9398  mov     r15, [rsp+168h+var_120]
0x1800a939d  xorps   xmm0, xmm0
0x1800a93a0  movdqu  [rsp+168h+var_108], xmm0
0x1800a93a6  lea     rcx, [rsp+168h+var_108]
0x1800a93ab  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@W4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@U?$less@W4OneSettingsDownloadConfigBoolProperty@@@3@V?$allocator@U?$pair@$$CBW4OneSettingsDownloadConfigBoolProperty@@V?$optional@_N@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<OneSettingsDownloadConfigBoolProperty,std::optional<bool>,std::less<OneSettingsDownloadConfigBoolProperty>,std::allocator<std::pair<OneSettingsDownloadConfigBoolProperty const,std::optional<bool>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800a93b0  nop
0x1800a93b1  mov     edi, r12d
0x1800a93b4  mov     edx, 21h ; '!'
0x1800a93b9  cmp     edi, [r15+4]
0x1800a93bd  jz      loc_1800A9515
0x1800a93c3  mov     ebx, edi
0x1800a93c5  inc     rbx
0x1800a93c8  lea     rbx, [r15+rbx*8]
0x1800a93cc  test    [rbx+4], r13b
0x1800a93d0  jnz     loc_1800A94FE
0x1800a93d6  cmp     dword ptr [rbx+4], 0FFFFFFFFh
0x1800a93da  jz      loc_1800A94FE
0x1800a93e0  mov     esi, [rbx+4]
0x1800a93e3  add     rsi, r15
0x1800a93e6  mov     rcx, rsi
0x1800a93e9  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a93ee  mov     r14, rax
0x1800a93f1  mov     r8, rax
0x1800a93f4  cmp     rax, rdx
0x1800a93f7  cmova   r8, rdx
0x1800a93fb  mov     rdx, cs:?k_perfCounterName_BufferMemoryUsagePaged@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsagePaged
0x1800a9402  call    cs:__imp__o__wcsnicmp
0x1800a9408  test    eax, eax
0x1800a940a  jnz     short loc_1800A9418
0x1800a940c  lea     eax, [r14-21h]
0x1800a9410  test    eax, eax
0x1800a9412  jz      loc_1800A9C04
0x1800a9418  mov     rcx, rsi
0x1800a941b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a9420  mov     r14, rax
0x1800a9423  mov     r8, rax
0x1800a9426  mov     eax, 25h ; '%'
0x1800a942b  cmp     r8, rax
0x1800a942e  cmova   r8, rax
0x1800a9432  mov     rdx, cs:?k_perfCounterName_BufferMemoryUsageNonpaged@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_BufferMemoryUsageNonpaged
0x1800a9439  call    cs:__imp__o__wcsnicmp
0x1800a943f  test    eax, eax
0x1800a9441  jnz     short loc_1800A944F
0x1800a9443  lea     eax, [r14-25h]
0x1800a9447  test    eax, eax
0x1800a9449  jz      loc_1800A94DA
0x1800a944f  mov     rcx, rsi
0x1800a9452  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a9457  mov     r14, rax
0x1800a945a  mov     r8, rax
0x1800a945d  mov     eax, 15h
0x1800a9462  cmp     r8, rax
0x1800a9465  cmova   r8, rax
0x1800a9469  mov     rdx, cs:?k_perfCounterName_EventsLogged@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLogged
0x1800a9470  call    cs:__imp__o__wcsnicmp
0x1800a9476  test    eax, eax
0x1800a9478  jnz     short loc_1800A9486
0x1800a947a  lea     eax, [r14-15h]
0x1800a947e  test    eax, eax
0x1800a9480  jz      loc_1800A9506
0x1800a9486  mov     rcx, rsi
0x1800a9489  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a948e  mov     r14, rax
0x1800a9491  mov     r8, rax
0x1800a9494  mov     eax, 0Bh
0x1800a9499  cmp     r8, rax
0x1800a949c  cmova   r8, rax
0x1800a94a0  mov     rdx, cs:?k_perfCounterName_EventsLost@TraceSessionUsage@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::TraceSessionUsage::k_perfCounterName_EventsLost
0x1800a94a7  call    cs:__imp__o__wcsnicmp
0x1800a94ad  test    eax, eax
0x1800a94af  jnz     short loc_1800A94F9
0x1800a94b1  lea     eax, [r14-0Bh]
0x1800a94b5  test    eax, eax
0x1800a94b7  jnz     short loc_1800A94F9
0x1800a94b9  mov     [rsp+168h+var_128], 3
0x1800a94be  lea     r9, [rsp+168h+var_128]
0x1800a94c3  mov     r8, rbx
0x1800a94c6  lea     rdx, [rsp+168h+pcbCounterBlockActual]
0x1800a94ce  lea     rcx, [rsp+168h+var_108]
0x1800a94d3  call    ??$_Emplace@AEBKW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@?$_Tree@V?$_Tmap_traits@KVPerfCounterEnum@Diagnostics@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@PEAX@std@@_N@1@AEBK$$QEAW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::Diagnostics::PerfCounterEnum,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::_Emplace<ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated &&)
0x1800a94d8  jmp     short loc_1800A94F9
0x1800a94da  mov     [rsp+168h+var_128], r13b
0x1800a94df  lea     rdx, [rsp+168h+var_C8]
0x1800a94e7  mov     r8, rbx
0x1800a94ea  lea     r9, [rsp+168h+var_128]
0x1800a94ef  lea     rcx, [rsp+168h+var_108]
0x1800a94f4  call    ??$_Emplace@AEBKW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@?$_Tree@V?$_Tmap_traits@KVPerfCounterEnum@Diagnostics@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVPerfCounterEnum@Diagnostics@Microsoft@@@std@@PEAX@std@@_N@1@AEBK$$QEAW4_enumerated@PerfCounterEnum@Diagnostics@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<ulong,Microsoft::Diagnostics::PerfCounterEnum,std::less<ulong>,std::allocator<std::pair<ulong const,Microsoft::Diagnostics::PerfCounterEnum>>,0>>::_Emplace<ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated>(ulong const &,Microsoft::Diagnostics::PerfCounterEnum::_enumerated &&)
0x1800a94f9  mov     edx, 21h ; '!'
0x1800a94fe  add     edi, r13d
0x1800a9501  jmp     loc_1800A93B9
0x1800a9506  mov     [rsp+168h+var_128], 2
0x1800a950b  lea     rdx, [rsp+168h+var_D8]
0x1800a9513  jmp     short loc_1800A94E7
0x1800a9515  movups  xmm0, xmmword ptr cs:?k_EventTracingSessionCounterSetGuid@TraceSessionUsage@Diagnostics@Microsoft@@0U_GUID@@B.Data1; _GUID const Microsoft::Diagnostics::TraceSessionUsage::k_EventTracingSessionCounterSetGuid ...
0x1800a951c  movdqu  xmmword ptr [rsp+168h+pCounters.CounterSetGuid.Data1], xmm0
0x1800a9525  mov     [rsp+168h+pCounters.Status], r12d
0x1800a952d  mov     r8d, 30h ; '0'; cbCounters
0x1800a9533  mov     [rsp+168h+pCounters.Size], r8d
0x1800a953b  mov     qword ptr [rsp+168h+pCounters.CounterId], 0FFFFFFFFFFFFFFFFh
0x1800a9547  xor     eax, eax
0x1800a9549  mov     qword ptr [rsp+168h+pCounters.Index], rax
0x1800a9551  mov     [rsp+168h+var_50], 2Ah ; '*'
0x1800a955d  lea     rdx, [rsp+168h+pCounters]; pCounters
0x1800a9565  mov     rcx, [rsp+168h+phQuery]; hQuery
0x1800a956a  call    cs:__imp_PerfAddCounters
0x1800a9570  test    eax, eax
0x1800a9572  jnz     loc_1800A9AA7
0x1800a9578  mov     ebx, r12d
0x1800a957b  mov     [rsp+168h+pcbCounterBlockActual], r12d
0x1800a9583  mov     rdx, [rsp+168h+var_120]; pCounterBlock
0x1800a9588  mov     r8d, dword ptr [rsp+168h+var_120+8]
0x1800a958d  sub     r8d, edx; cbCounterBlock
0x1800a9590  lea     r9, [rsp+168h+pcbCounterBlockActual]; pcbCounterBlockActual
0x1800a9598  mov     rcx, [rsp+168h+phQuery]; hQuery
0x1800a959d  call    cs:__imp_PerfQueryCounterData
0x1800a95a3  cmp     eax, 8
0x1800a95a6  jnz     short loc_1800A95F1
0x1800a95a8  test    ebx, ebx
0x1800a95aa  jnz     loc_1800A9B49
0x1800a95b0  mov     ebx, [rsp+168h+pcbCounterBlockActual]
0x1800a95b7  mov     rdi, [rsp+168h+var_120]
0x1800a95bc  mov     rcx, [rsp+168h+var_120+8]
0x1800a95c1  sub     rcx, rdi
0x1800a95c4  cmp     rbx, rcx
0x1800a95c7  jb      loc_1800A9A88
0x1800a95cd  jbe     short loc_1800A95EC
0x1800a95cf  mov     rax, [rsp+168h+var_110]
0x1800a95d4  sub     rax, rdi
0x1800a95d7  cmp     rbx, rax
0x1800a95da  jbe     loc_1800A9A76
0x1800a95e0  mov     edx, ebx
0x1800a95e2  lea     rcx, [rsp+168h+var_120]
0x1800a95e7  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800a95ec  mov     ebx, r13d
0x1800a95ef  jmp     short loc_1800A957B
0x1800a95f1  test    eax, eax
0x1800a95f3  jnz     loc_1800A9B49
0x1800a95f9  mov     rbx, [rsp+168h+var_120]
0x1800a95fe  mov     r9d, [rbx+30h]; char *
0x1800a9602  test    r9d, r9d
0x1800a9605  jnz     loc_1800A9953
0x1800a960b  cmp     [rbx+4], r13d
0x1800a960f  jnz     loc_1800A985A
0x1800a9615  cmp     dword ptr [rbx+34h], 6
0x1800a9619  jnz     loc_1800A985A
0x1800a961f  mov     r15d, [rbx+40h]
0x1800a9623  lea     rdi, [rbx+48h]
0x1800a9627  add     rdi, r15
0x1800a962a  mov     r14d, r12d
0x1800a962d  mov     r12, [rsp+168h+var_D8]
0x1800a9635  mov     r13, [rsp+168h+var_D8]
0x1800a963d  mov     rsi, [rsp+168h+var_F0]
0x1800a9642  cmp     r14d, [r15+rbx+44h]
0x1800a9647  jz      loc_1800A9857
0x1800a964d  lea     rcx, [rdi+8]
0x1800a9651  xorps   xmm0, xmm0
0x1800a9654  movups  [rsp+168h+var_98], xmm0
0x1800a965c  xorps   xmm1, xmm1
0x1800a965f  movdqu  [rsp+168h+var_88], xmm1
0x1800a9668  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a966d  mov     r8, rax
0x1800a9670  mov     rdx, rcx
0x1800a9673  lea     rcx, [rsp+168h+var_98]
0x1800a967b  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800a9680  nop
0x1800a9681  mov     eax, [rdi]
0x1800a9683  add     rdi, rax
0x1800a9686  xor     r10d, r10d
0x1800a9689  cmp     [rbx+44h], r10d
0x1800a968d  jz      loc_1800A972C
0x1800a9693  mov     r9, qword ptr [rsp+168h+var_108]
0x1800a9698  mov     rcx, rdi
0x1800a969b  mov     r11d, [rbx+r10*4+48h]
0x1800a96a0  mov     rdx, rdi
0x1800a96a3  mov     eax, [rdi+4]
0x1800a96a6  add     rdi, rax
0x1800a96a9  cmp     dword ptr [rdx], 4
0x1800a96ac  jnz     loc_1800A981C
0x1800a96b2  mov     edx, [rdx+8]
0x1800a96b5  xor     eax, eax
0x1800a96b7  mov     dword ptr [rsp+168h+var_B8+0Ch], eax
0x1800a96be  mov     rcx, r9
0x1800a96c1  mov     r8, [r9+8]
0x1800a96c5  cmp     [r8+19h], al
0x1800a96c9  jnz     short loc_1800A96E5
0x1800a96cb  cmp     [r8+1Ch], r11d
0x1800a96cf  cmovnb  rcx, r8
0x1800a96d3  lea     rax, [r8+10h]
0x1800a96d7  cmovnb  rax, r8
0x1800a96db  mov     r8, [rax]
0x1800a96de  cmp     byte ptr [r8+19h], 0
0x1800a96e3  jz      short loc_1800A96CB
0x1800a96e5  cmp     byte ptr [rcx+19h], 0
0x1800a96e9  jnz     short loc_1800A96F1
0x1800a96eb  cmp     r11d, [rcx+1Ch]
0x1800a96ef  jnb     short loc_1800A96F4
0x1800a96f1  mov     rcx, r9
0x1800a96f4  cmp     rcx, r9
0x1800a96f7  jz      short loc_1800A971F
0x1800a96f9  movzx   ecx, byte ptr [rcx+20h]
0x1800a96fd  test    ecx, ecx
0x1800a96ff  jz      loc_1800A9848
0x1800a9705  sub     ecx, 1
0x1800a9708  jz      loc_1800A9840
0x1800a970e  sub     ecx, 1
0x1800a9711  jnz     loc_1800A982A
0x1800a9717  mov     [rsp+168h+var_D8], rdx
0x1800a971f  inc     r10d
0x1800a9722  cmp     r10d, [rbx+44h]
0x1800a9726  jnz     loc_1800A9698
0x1800a972c  lea     r8, [rsp+168h+var_98]
0x1800a9734  lea     rdx, [rsp+168h+var_B8]
0x1800a973c  mov     rcx, rsi
0x1800a973f  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Diagnostics::IForwarder>,std::less<void>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800a9744  movups  xmm6, xmmword ptr [rax]
0x1800a9747  lea     r8, [rsp+168h+var_98]
0x1800a974f  mov     rdx, [rax+10h]
0x1800a9753  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UEscalationDataRequest@Diagnostics@Microsoft@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UEscalationDataRequest@Diagnostics@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UEscalationDataRequest@Diagnostics@Microsoft@@@2@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>>,void *> * const,std::wstring const &)
0x1800a9758  test    al, al
0x1800a975a  jnz     loc_1800A9807
0x1800a9760  mov     rax, 2AAAAAAAAAAAAAAh
0x1800a976a  cmp     [rsi+8], rax
0x1800a976e  jz      loc_1800A9C28
0x1800a9774  mov     rsi, [rsi]
0x1800a9777  mov     rax, [rsp+168h+var_F0]
0x1800a977c  mov     [rsp+168h+var_C8], rax
0x1800a9784  mov     [rsp+168h+var_C0], 0
0x1800a9790  mov     ecx, 60h ; '`'
0x1800a9795  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800a979a  mov     r8, rax
0x1800a979d  lea     rcx, [rax+20h]
0x1800a97a1  lea     rdx, [rsp+168h+var_98]
0x1800a97a9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800a97ae  mov     [rcx+20h], r12
0x1800a97b2  mov     [rcx+28h], r13
0x1800a97b6  mov     rax, [rsp+168h+var_D8]
0x1800a97be  mov     [rcx+30h], rax
0x1800a97c2  mov     rax, qword ptr [rsp+168h+pcbCounterBlockActual]
0x1800a97ca  mov     [rcx+38h], rax
0x1800a97ce  mov     [r8], rsi
0x1800a97d1  mov     [r8+8], rsi
0x1800a97d5  mov     [r8+10h], rsi
  ... truncated ...
```
