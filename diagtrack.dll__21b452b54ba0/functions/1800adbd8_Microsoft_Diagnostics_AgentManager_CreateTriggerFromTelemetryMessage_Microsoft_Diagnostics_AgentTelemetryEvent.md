# Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(Microsoft::Diagnostics::AgentTelemetryEventMessage const &,JsonBuilder &&,Microsoft::Diagnostics::AgentTransport &,bool)

- ea: `0x1800adbd8`
- end: `0x1800aeb60`
- name: `?CreateTriggerFromTelemetryMessage@AgentManager@Diagnostics@Microsoft@@CA?AV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@AEBUAgentTelemetryEventMessage@23@$$QEAVJsonBuilder@@AEAVAgentTransport@23@_N@Z`
- size: `3976`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180157214`

## callees

- `0x18002509c`
- `0x18002cae0`
- `0x18002cb04`
- `0x18002df00`
- `0x18003176c`
- `0x180035088`
- `0x180038524`
- `0x18004f874`
- `0x180054564`
- `0x180076774`
- `0x1800788cc`
- `0x1800797b4`
- `0x18007b0b8`
- `0x18007d3d8`
- `0x18007d47c`
- `0x18007dc64`
- `0x1800adb6c`
- `0x1800adbd8`
- `0x1800aece4`
- `0x1800aed9c`
- `0x1800aeee0`
- `0x1800ca190`
- `0x1801a9494`
- `0x1801b21e4`
- `0x1801b7bd0`
- `0x1801bb33c`
- `0x1801bf154`
- `0x18020aac0`
- `0x18020ba94`
- `0x1802807e8`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800ae4a1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800ae4a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800ade59`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800ade59`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ae633`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ae633`

## string_xrefs

- `0x1800ae3a7`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae3bf`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae3da`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae3f2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae40a`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae422`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae43a`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae452`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae46a`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae4ae`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae57e`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae596`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae5ae`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae5c9`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae5e4`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae5ff`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae617`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae77c`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae797`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae7e6`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae847`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae896`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1800ae8ed`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Microsoft::Diagnostics::IAsimovEvent **__fastcall Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(
        Microsoft::Diagnostics::IAsimovEvent **a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char a5)
{
  unsigned int v7; // r12d
  unsigned int v8; // eax
  __int64 v9; // rdx
  Performance *v10; // r13
  unsigned __int64 v11; // rbx
  __int64 v12; // r15
  unsigned __int64 v13; // rax
  Performance *v14; // rdi
  unsigned __int64 v15; // rax
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  char *v21; // rbx
  unsigned __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r15
  wil::details::in1diag3 *v27; // rcx
  _QWORD *v28; // r12
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rcx
  char Unchecked; // dl
  char v37; // al
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  unsigned int v55; // eax
  unsigned int v56; // r13d
  char v57; // bl
  __int64 EventTimestampFromJson; // rax
  Microsoft::Diagnostics::IAsimovEvent *v59; // rcx
  ULONGLONG TickCount64; // rax
  __int64 v62; // rcx
  char v63; // dl
  char v64; // al
  wil::details::in1diag3 *v65; // r10
  wil::details::in1diag3 *v66; // r10
  wil::details::in1diag3 *v67; // r10
  __int64 v68; // rcx
  char v69; // dl
  char v70; // al
  wil::details::in1diag3 *v71; // r10
  unsigned int v72; // eax
  wil::details::in1diag3 *v73; // r10
  unsigned int v74; // eax
  wil::details::in1diag3 *v75; // r10
  JsonValue *v76; // rcx
  void *v77; // rdx
  unsigned __int64 v78; // r8
  char v79; // al
  __int64 v80; // rax
  JsonValue *v81; // rcx
  const void *v82; // rdx
  char *v83; // r8
  char v84; // al
  wil::details::in1diag3 *v85; // r10
  __int64 v86; // rcx
  char v87; // dl
  char v88; // al
  struct _GUID *v89; // r8
  Performance *v90; // rcx
  __int64 v91; // rdi
  int v92; // r9d
  int v93; // r9d
  int v94; // r9d
  int v95; // r9d
  int v96; // r9d
  int v97; // r9d
  int v98; // [rsp+20h] [rbp-E0h]
  __int128 Buf1; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v100; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v101; // [rsp+48h] [rbp-B8h] BYREF
  int v102; // [rsp+50h] [rbp-B0h]
  int v103; // [rsp+54h] [rbp-ACh]
  int v104; // [rsp+58h] [rbp-A8h]
  __int128 v105; // [rsp+60h] [rbp-A0h] BYREF
  Microsoft::Diagnostics::IAsimovEvent **v106; // [rsp+70h] [rbp-90h]
  Performance *v107[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v108; // [rsp+98h] [rbp-68h]
  wchar_t v109[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v110[32]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v111[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v112[80]; // [rsp+E0h] [rbp-20h] BYREF
  char v113[48]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *(_QWORD *)&Buf1 = a4;
  v100 = a2;
  v106 = a1;
  v104 = 0;
  *(_QWORD *)v109 = L"a";
  *(_QWORD *)&v109[4] = 1;
  v101 = (unsigned __int64)a3;
  v102 = 0;
  v103 = HIDWORD(v107[1]);
  JsonBuilder::find<>(a3, &v105, &v101, v109);
  v7 = DWORD2(v105);
  if ( !DWORD2(v105) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x514,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v98);
  if ( *(_BYTE *)(*(_QWORD *)v105 + 4LL * DWORD2(v105) + 7) != 0xFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x515,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007070CLL,
      v98);
  *(_QWORD *)v109 = L"name";
  *(_QWORD *)&v109[4] = 4;
  if ( (_QWORD *)v105 != a3 )
    __int2c();
  v8 = JsonBuilder::Find<>(a3, DWORD2(v105), v109);
  if ( !v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x519,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v98);
  v9 = *a3 + 4LL * v8;
  if ( *(_BYTE *)(v9 + 7) != 0xF5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007070CLL,
      v98);
  v10 = (Performance *)(v9 + 4 * ((2 * (unsigned __int64)(*(_DWORD *)(v9 + 4) & 0xFFFFFF) + 15) >> 2));
  v11 = (unsigned __int64)*(unsigned int *)(v9 + 8) >> 1;
  v12 = -1;
  v13 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v10, v11, -1, 46);
  if ( v13 == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x521,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v98);
  v14 = (Performance *)v13;
  if ( v11 < v13 )
    v14 = (Performance *)v11;
  v15 = v13 + 1;
  v101 = v15;
  if ( v11 < v15 )
  {
    std::_Xout_of_range("invalid string_view position");
    goto LABEL_100;
  }
  v16 = v11 - v15;
  if ( v16 != -1 )
    v12 = v16;
  *(_QWORD *)v109 = L"ext";
  *(_QWORD *)&v109[4] = 3;
  if ( (_QWORD *)v105 != a3 )
    __int2c();
  v17 = JsonBuilder::Find<>(a3, v7, v109);
  if ( !v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x527,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v98);
  *(_QWORD *)v109 = L"container";
  *(_QWORD *)&v109[4] = 9;
  v18 = JsonBuilder::Find<>(a3, v17, v109);
  if ( !v18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v98);
  *(_QWORD *)v109 = L"type";
  *(_QWORD *)&v109[4] = 4;
  v19 = JsonBuilder::Find<>(a3, v18, v109);
  if ( !v19 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v98);
  v20 = *a3 + 4LL * v19;
  if ( *(_BYTE *)(v20 + 7) != 0xF6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007070CLL,
      v98);
  v21 = (char *)v10 + 2 * v101;
  v22 = (2 * (unsigned __int64)(*(_DWORD *)(v20 + 4) & 0xFFFFFF) + 15) >> 2;
  *(_DWORD *)(v20 + 4 * v22) |= *(_DWORD *)(Buf1 + 344) << 8;
  v23 = 18;
  if ( (unsigned __int64)v14 <= 0x12 )
    v23 = (__int64)v14;
  LODWORD(v101) = _o__wcsnicmp(v10, Microsoft::Diagnostics::SyntheticTriggerDef::k_telClientSyntheticProviderName, v23);
  if ( !(_DWORD)v101 )
    LODWORD(v101) = (_DWORD)v14 - 18;
  Buf1 = *(_OWORD *)(v100 + 48);
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    *(GUID *)v109 = GUID_NULL;
    std::wstring::wstring(v107, v10, v14);
    v90 = (Performance *)v107;
    if ( v108 > 7 )
      v90 = v107[0];
    if ( (int)Performance::NameToGuid(v90, v109, v89) >= 0 )
      Buf1 = *(_OWORD *)v109;
    std::wstring::_Tidy_deallocate(v107);
  }
  *(_QWORD *)v109 = v21;
  *(_QWORD *)&v109[4] = v12;
  v107[0] = v10;
  v107[1] = v14;
  Microsoft::Diagnostics::ETWTriggerDef::ETWTriggerDef(v111, &Buf1, v107, v109);
  std::make_shared<Microsoft::Diagnostics::ETWTriggerInst,Microsoft::Diagnostics::ETWTriggerDef &>(a1, v111);
  v104 = 1;
  std::wstring::wstring(v110);
  v107[0] = (Performance *)L"ag";
  v107[1] = (Performance *)2;
  Buf1 = (unsigned __int64)a3;
  JsonBuilder::find<>(a3, v109, &Buf1, v107);
  v26 = *(unsigned int *)&v109[4];
  if ( *(_DWORD *)&v109[4] )
  {
    v27 = retaddr;
    v28 = *(_QWORD **)v109;
    if ( *(_BYTE *)(**(_QWORD **)v109 + 4LL * *(unsigned int *)&v109[4] + 7) == 0xFF )
    {
      v107[0] = (Performance *)L"ikey";
      v107[1] = (Performance *)4;
      if ( *(_QWORD **)v109 != a3 )
        __int2c();
      v29 = JsonBuilder::Find<>(a3, *(unsigned int *)&v109[4], v107);
      if ( v29 )
      {
        v76 = (JsonValue *)(*a3 + 4LL * v29);
        if ( *((_BYTE *)v76 + 7) == 0xF5 )
        {
          LODWORD(Buf1) = 0;
          v77 = JsonValue::Data(v76, (unsigned int *)&Buf1);
          v78 = (unsigned __int64)(unsigned int)Buf1 >> 1;
          v79 = 0;
        }
        else
        {
          v77 = 0;
          v78 = 0;
          v79 = 1;
        }
        if ( v79 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x557,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        v80 = std::wstring::wstring(v107, v77, v78);
        std::wstring::operator=(v110, v80);
        std::wstring::_Tidy_deallocate(v107);
      }
      v107[0] = (Performance *)L"usid";
      v107[1] = (Performance *)4;
      if ( v28 != a3 )
        __int2c();
      v30 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v30 )
      {
        v81 = (JsonValue *)(*a3 + 4LL * v30);
        if ( *((_BYTE *)v81 + 7) == 0xF5 )
        {
          LODWORD(Buf1) = 0;
          v82 = JsonValue::Data(v81, (unsigned int *)&Buf1);
          v83 = (char *)((unsigned __int64)(unsigned int)Buf1 >> 1);
          v84 = 0;
        }
        else
        {
          v82 = 0;
          v83 = 0;
          v84 = 1;
        }
        if ( v84 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x55F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        std::wstring::_Assign<wchar_t>((char **)*a1 + 92, v82, v83);
      }
      v107[0] = (Performance *)L"irpc";
      v107[1] = (Performance *)4;
      if ( v28 != a3 )
        __int2c();
      v31 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v31 )
      {
        v35 = *a3 + 4LL * v31;
        if ( *(_BYTE *)(v35 + 7) == 0xF9 )
        {
          Unchecked = JsonImplementType<bool>::GetUnchecked(v35, v32, v33, v34);
          v37 = 0;
        }
        else
        {
          Unchecked = 0;
          v37 = 1;
        }
        if ( v37 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x567,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_BYTE *)*a1 + 698) = (16 * Unchecked) | *((_BYTE *)*a1 + 698) & 0xEF;
      }
      v107[0] = (Performance *)L"ita";
      v107[1] = (Performance *)3;
      if ( v28 != a3 )
        __int2c();
      v38 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v38 )
      {
        v62 = *a3 + 4LL * v38;
        if ( *(_BYTE *)(v62 + 7) == 0xF9 )
        {
          v63 = JsonImplementType<bool>::GetUnchecked(v62, v39, v40, v41);
          v64 = 0;
        }
        else
        {
          v63 = 0;
          v64 = 1;
        }
        if ( v64 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_BYTE *)*a1 + 697) = (v63 << 7) | *((_BYTE *)*a1 + 697) & 0x7F;
      }
      v107[0] = (Performance *)L"rxt";
      v107[1] = (Performance *)3;
      if ( v28 != a3 )
        __int2c();
      v42 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v42 )
      {
        v68 = *a3 + 4LL * v42;
        if ( *(_BYTE *)(v68 + 7) == 0xF9 )
        {
          v69 = JsonImplementType<bool>::GetUnchecked(v68, v43, v44, v45);
          v70 = 0;
        }
        else
        {
          v69 = 0;
          v70 = 1;
        }
        if ( v70 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x577,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_BYTE *)*a1 + 1064) = v69 | *((_BYTE *)*a1 + 1064) & 0xFE;
      }
      v107[0] = (Performance *)L"ei";
      v107[1] = (Performance *)2;
      if ( v28 != a3 )
        __int2c();
      v46 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v46 )
      {
        LODWORD(Buf1) = 0;
        if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_long_(*a3 + 4LL * v46, &Buf1) )
          wil::details::in1diag3::Throw_Hr(
            v71,
            (void *)0x57F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_DWORD *)*a1 + 250) = Buf1;
      }
      v107[0] = (Performance *)L"ev";
      v107[1] = (Performance *)2;
      if ( v28 != a3 )
        __int2c();
      v47 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v47 )
      {
        LODWORD(Buf1) = 0;
        if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_long_(*a3 + 4LL * v47, &Buf1) )
          wil::details::in1diag3::Throw_Hr(
            v65,
            (void *)0x587,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_DWORD *)*a1 + 251) = Buf1;
      }
      v107[0] = (Performance *)L"el";
      v107[1] = (Performance *)2;
      if ( v28 != a3 )
        __int2c();
      v48 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v48 )
      {
        LOBYTE(Buf1) = 0;
        if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_char_(*a3 + 4LL * v48, &Buf1) )
          wil::details::in1diag3::Throw_Hr(
            v66,
            (void *)0x58F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_BYTE *)*a1 + 1016) = Buf1;
      }
      v107[0] = (Performance *)L"ek";
      v107[1] = (Performance *)2;
      if ( v28 != a3 )
        __int2c();
      v49 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v49 )
      {
        *(_QWORD *)&Buf1 = 0;
        if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*a3 + 4LL * v49, &Buf1) )
          wil::details::in1diag3::Throw_Hr(
            v67,
            (void *)0x597,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_QWORD *)*a1 + 96) = Buf1;
      }
      v107[0] = (Performance *)L"kw";
      v107[1] = (Performance *)2;
      if ( v28 != a3 )
        __int2c();
      v50 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v50 )
      {
        *(_QWORD *)&Buf1 = 0;
        if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(*a3 + 4LL * v50, &Buf1) )
          wil::details::in1diag3::Throw_Hr(
            v85,
            (void *)0x59F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_QWORD *)*a1 + 126) = Buf1;
      }
      v107[0] = (Performance *)L"nw";
      v107[1] = (Performance *)2;
      if ( v28 != a3 )
        __int2c();
      v51 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      if ( v51 )
      {
        v86 = *a3 + 4LL * v51;
        if ( *(_BYTE *)(v86 + 7) == 0xF9 )
        {
          v87 = JsonImplementType<bool>::GetUnchecked(v86, v52, v53, v54);
          v88 = 0;
        }
        else
        {
          v87 = 0;
          v88 = 1;
        }
        if ( v88 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5A7,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v98);
        *((_BYTE *)*a1 + 698) = *((_BYTE *)*a1 + 698) & 0xFB | (4 * v87);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl) )
      {
        v107[0] = (Performance *)L"tpp";
        v107[1] = (Performance *)3;
        if ( v28 != a3 )
          __int2c();
        v72 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
        if ( v72 )
        {
          LOWORD(Buf1) = 0;
          if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_short_(*a3 + 4LL * v72, &Buf1) )
            wil::details::in1diag3::Throw_Hr(
              v73,
              (void *)0x5B1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
              (const char *)0x8007000DLL,
              v98);
          Microsoft::Diagnostics::IAsimovEvent::SetProduct(*a1, Buf1);
        }
        v107[0] = (Performance *)L"tpdc";
        v107[1] = (Performance *)4;
        if ( v28 != a3 )
          __int2c();
        v74 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
        if ( v74 )
        {
          LOWORD(Buf1) = 0;
          if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_short_(*a3 + 4LL * v74, &Buf1) )
            wil::details::in1diag3::Throw_Hr(
              v75,
              (void *)0x5B9,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
              (const char *)0x8007000DLL,
              v98);
          Microsoft::Diagnostics::IAsimovEvent::SetDataCategory(*a1, Buf1);
        }
      }
      v107[0] = (Performance *)L"vmd";
      v107[1] = (Performance *)3;
      if ( v28 != a3 )
        __int2c();
      v55 = JsonBuilder::Find<>(a3, (unsigned int)v26, v107);
      v56 = v55;
      if ( v55 )
      {
        v91 = (__int64)*a1 + 40;
        *(_OWORD *)v107 = *(_OWORD *)&off_180385188;
        *(_QWORD *)&Buf1 = a3;
        *((_QWORD *)&Buf1 + 1) = v55;
        LOBYTE(v25) = 1;
        Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
          (_DWORD)a3,
          (unsigned int)&Buf1,
          (unsigned int)v107,
          v25,
          v91);
        *(_OWORD *)v107 = *(_OWORD *)&off_180385198;
        *(_QWORD *)&Buf1 = a3;
        *((_QWORD *)&Buf1 + 1) = v56;
        LOBYTE(v92) = 1;
        Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
          (_DWORD)a3,
          (unsigned int)&Buf1,
          (unsigned int)v107,
          v92,
          v91 + 32);
        *(_OWORD *)v107 = *(_OWORD *)&off_1803851A8;
        *(_QWORD *)&Buf1 = a3;
        *((_QWORD *)&Buf1 + 1) = v56;
        LOBYTE(v93) = 1;
        Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
          (_DWORD)a3,
          (unsigned int)&Buf1,
          (unsigned int)v107,
          v93,
          v91 + 64);
        *(_OWORD *)v107 = *(_OWORD *)&off_180385148;
        *(_QWORD *)&Buf1 = a3;
        *((_QWORD *)&Buf1 + 1) = v56;
        LOBYTE(v94) = 1;
        Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
          (_DWORD)a3,
          (unsigned int)&Buf1,
          (unsigned int)v107,
          v94,
          v91 + 96);
        *(_OWORD *)v107 = *(_OWORD *)&off_180385158;
        *(_QWORD *)&Buf1 = a3;
        *((_QWORD *)&Buf1 + 1) = v56;
        LOBYTE(v95) = 1;
        Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
          (_DWORD)a3,
          (unsigned int)&Buf1,
          (unsigned int)v107,
          v95,
          v91 + 128);
        *(_OWORD *)v107 = *(_OWORD *)&off_180385168;
        *(_QWORD *)&Buf1 = a3;
        *((_QWORD *)&Buf1 + 1) = v56;
        LOBYTE(v96) = 1;
        Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
          (_DWORD)a3,
          (unsigned int)&Buf1,
          (unsigned int)v107,
          v96,
          v91 + 160);
        *(_OWORD *)v107 = *(_OWORD *)&off_180385178;
        *(_QWORD *)&Buf1 = a3;
        *((_QWORD *)&Buf1 + 1) = v56;
        LOBYTE(v97) = 1;
        Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
          (_DWORD)a3,
          (unsigned int)&Buf1,
          (unsigned int)v107,
          v97,
          v91 + 192);
      }
      if ( v28 != a3 )
        __int2c();
      if ( !(_DWORD)v26 )
        __int2c();
      *(_BYTE *)(*a3 + 4 * v26 + 7) = -3;
      goto LABEL_73;
    }
LABEL_100:
    wil::details::in1diag3::Throw_Hr(
      v27,
      (void *)0x551,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007070CLL,
      v98);
  }
LABEL_73:
  if ( (*(_BYTE *)v100 & 0x10) == 0 )
  {
    v57 = 0;
LABEL_75:
    LOBYTE(v25) = 0;
    goto LABEL_76;
  }
  v57 = 1;
  if ( !a5 && (_DWORD)v101 )
    goto LABEL_75;
  LOBYTE(v25) = 1;
LABEL_76:
  v100 = 0;
  *(_OWORD *)v107 = v105;
  LOBYTE(v24) = v57;
  EventTimestampFromJson = Microsoft::Diagnostics::ETWConsumer::GetEventTimestampFromJson(a3, v107, v24, v25, &v100);
  v59 = *a1;
  *((_QWORD *)v59 + 33) = EventTimestampFromJson;
  *((_BYTE *)v59 + 697) &= ~8u;
  *((_BYTE *)v59 + 697) |= 8 * (v57 ^ 1);
  Microsoft::Diagnostics::ETWTriggerInst::PopulateAgentData(*a1);
  if ( v100 )
    TickCount64 = Microsoft::Diagnostics::TimeStampManager::ConvertQpcToTicks(
                    (Microsoft::Diagnostics::TimeStampManager *)&qword_180463360,
                    v100);
  else
    TickCount64 = GetTickCount64();
  Microsoft::Diagnostics::IAsimovEvent::RecordSystemStateFlags(*a1, 1, TickCount64);
  Microsoft::Diagnostics::ETWTriggerInst::PopulateOsVersion(*a1);
  std::wstring::_Tidy_deallocate(v110);
  std::wstring::_Tidy_deallocate(v113);
  v111[0] = &Microsoft::Diagnostics::ITriggerDef::`vftable';
  std::wstring::_Tidy_deallocate(v112);
  return a1;
}

```

## disassembly

```asm
0x1800adbd8  mov     [rsp-8+arg_18], rbx
0x1800adbdd  push    rbp
0x1800adbde  push    rsi
0x1800adbdf  push    rdi
0x1800adbe0  push    r12
0x1800adbe2  push    r13
0x1800adbe4  push    r14
0x1800adbe6  push    r15
0x1800adbe8  lea     rbp, [rsp-70h]
0x1800adbed  sub     rsp, 170h
0x1800adbf4  mov     rax, cs:__security_cookie
0x1800adbfb  xor     rax, rsp
0x1800adbfe  mov     [rbp+0A0h+var_40], rax
0x1800adc02  mov     qword ptr [rsp+1A0h+Buf1], r9
0x1800adc07  mov     rsi, r8
0x1800adc0a  mov     [rsp+1A0h+var_160], rdx
0x1800adc0f  mov     r14, rcx
0x1800adc12  mov     [rsp+1A0h+var_130], rcx
0x1800adc17  mov     [rsp+1A0h+var_148], 0
0x1800adc1f  lea     rax, aA_1; "a"
0x1800adc26  mov     qword ptr [rbp+0A0h+var_100], rax
0x1800adc2a  mov     qword ptr [rbp+0A0h+var_100+8], 1
0x1800adc32  mov     [rsp+1A0h+var_158], r8
0x1800adc37  mov     [rsp+1A0h+var_150], 0
0x1800adc3f  mov     eax, dword ptr [rbp+0A0h+var_120+0Ch]
0x1800adc42  mov     [rsp+1A0h+var_14C], eax
0x1800adc46  lea     r9, [rbp+0A0h+var_100]
0x1800adc4a  lea     r8, [rsp+1A0h+var_158]
0x1800adc4f  lea     rdx, [rsp+1A0h+var_140]
0x1800adc54  mov     rcx, rsi
0x1800adc57  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800adc5c  mov     r12d, dword ptr [rsp+1A0h+var_140+8]
0x1800adc61  test    r12d, r12d
0x1800adc64  setz    al
0x1800adc67  mov     rcx, [rbp+0A8h]; this
0x1800adc6e  test    al, al
0x1800adc70  jnz     loc_1800AE3A1
0x1800adc76  mov     r10, [rbp+0A8h]
0x1800adc7d  mov     rcx, qword ptr [rsp+1A0h+var_140]
0x1800adc82  mov     rax, [rcx]
0x1800adc85  cmp     byte ptr [rax+r12*4+7], 0FFh
0x1800adc8b  jnz     loc_1800AE3B9
0x1800adc91  lea     rax, aName_3; "name"
0x1800adc98  mov     qword ptr [rbp+0A0h+var_100], rax
0x1800adc9c  mov     qword ptr [rbp+0A0h+var_100+8], 4
0x1800adca4  cmp     rcx, rsi
0x1800adca7  jnz     loc_1800AE63E
0x1800adcad  lea     r8, [rbp+0A0h+var_100]
0x1800adcb1  mov     edx, r12d
0x1800adcb4  mov     rcx, rsi
0x1800adcb7  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800adcbc  mov     rcx, [rbp+0A8h]; this
0x1800adcc3  test    eax, eax
0x1800adcc5  jz      loc_1800AE3D4
0x1800adccb  mov     ecx, eax
0x1800adccd  mov     rax, [rsi]
0x1800adcd0  lea     rdx, [rax+rcx*4]
0x1800adcd4  mov     rcx, [rbp+0A8h]; this
0x1800adcdb  cmp     byte ptr [rdx+7], 0F5h
0x1800adcdf  jnz     loc_1800AE3EC
0x1800adce5  mov     eax, [rdx+4]
0x1800adce8  and     eax, 0FFFFFFh
0x1800adced  lea     rax, ds:0Fh[rax*2]
0x1800adcf5  shr     rax, 2
0x1800adcf9  lea     r13, [rdx+rax*4]
0x1800adcfd  mov     ebx, [rdx+8]
0x1800add00  shr     rbx, 1
0x1800add03  mov     rax, [rbp+0A8h]
0x1800add0a  mov     r9d, 2Eh ; '.'
0x1800add10  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800add14  mov     r8, r15
0x1800add17  mov     rdx, rbx
0x1800add1a  mov     rcx, r13
0x1800add1d  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1800add22  mov     rcx, [rbp+0A8h]; this
0x1800add29  cmp     rax, r15
0x1800add2c  jz      loc_1800AE404
0x1800add32  mov     rdi, rax
0x1800add35  cmp     rbx, rax
0x1800add38  cmovb   rdi, rbx
0x1800add3c  inc     rax
0x1800add3f  mov     [rsp+1A0h+var_158], rax
0x1800add44  cmp     rbx, rax
0x1800add47  jb      loc_1800AE49A
0x1800add4d  sub     rbx, rax
0x1800add50  cmp     rbx, r15
0x1800add53  cmovb   r15, rbx
0x1800add57  lea     rax, aExt; "ext"
0x1800add5e  mov     qword ptr [rbp+0A0h+var_100], rax
0x1800add62  mov     qword ptr [rbp+0A0h+var_100+8], 3
0x1800add6a  cmp     qword ptr [rsp+1A0h+var_140], rsi
0x1800add6f  jnz     loc_1800AE645
0x1800add75  lea     r8, [rbp+0A0h+var_100]
0x1800add79  mov     edx, r12d
0x1800add7c  mov     rcx, rsi
0x1800add7f  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800add84  mov     rcx, [rbp+0A8h]; this
0x1800add8b  test    eax, eax
0x1800add8d  jz      loc_1800AE41C
0x1800add93  lea     rcx, aContainer; "container"
0x1800add9a  mov     qword ptr [rbp+0A0h+var_100], rcx
0x1800add9e  mov     qword ptr [rbp+0A0h+var_100+8], 9
0x1800adda6  lea     r8, [rbp+0A0h+var_100]
0x1800addaa  mov     edx, eax
0x1800addac  mov     rcx, rsi
0x1800addaf  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800addb4  mov     rcx, [rbp+0A8h]; this
0x1800addbb  test    eax, eax
0x1800addbd  jz      loc_1800AE434
0x1800addc3  lea     rcx, aType; "type"
0x1800addca  mov     qword ptr [rbp+0A0h+var_100], rcx
0x1800addce  mov     qword ptr [rbp+0A0h+var_100+8], 4
0x1800addd6  lea     r8, [rbp+0A0h+var_100]
0x1800addda  mov     edx, eax
0x1800adddc  mov     rcx, rsi
0x1800adddf  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800adde4  mov     rcx, [rbp+0A8h]; this
0x1800addeb  test    eax, eax
0x1800added  jz      loc_1800AE44C
0x1800addf3  mov     ecx, eax
0x1800addf5  mov     rax, [rsi]
0x1800addf8  lea     rdx, [rax+rcx*4]
0x1800addfc  mov     rcx, [rbp+0A8h]; this
0x1800ade03  cmp     byte ptr [rdx+7], 0F6h
0x1800ade07  jnz     loc_1800AE464
0x1800ade0d  mov     rax, [rsp+1A0h+var_158]
0x1800ade12  lea     rbx, ds:0[rax*2]
0x1800ade1a  add     rbx, r13
0x1800ade1d  mov     eax, [rdx+4]
0x1800ade20  and     eax, 0FFFFFFh
0x1800ade25  lea     rcx, ds:0Fh[rax*2]
0x1800ade2d  shr     rcx, 2
0x1800ade31  mov     rax, qword ptr [rsp+1A0h+Buf1]
0x1800ade36  mov     eax, [rax+158h]
0x1800ade3c  shl     eax, 8
0x1800ade3f  or      [rdx+rcx*4], eax
0x1800ade42  mov     r8d, 12h
0x1800ade48  cmp     rdi, r8
0x1800ade4b  cmovbe  r8, rdi
0x1800ade4f  mov     rdx, cs:?k_telClientSyntheticProviderName@SyntheticTriggerDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::SyntheticTriggerDef::k_telClientSyntheticProviderName
0x1800ade56  mov     rcx, r13
0x1800ade59  call    cs:__imp__o__wcsnicmp
0x1800ade5f  mov     dword ptr [rsp+1A0h+var_158], eax
0x1800ade63  test    eax, eax
0x1800ade65  jnz     short loc_1800ADE6E
0x1800ade67  lea     eax, [rdi-12h]
0x1800ade6a  mov     dword ptr [rsp+1A0h+var_158], eax
0x1800ade6e  mov     rax, [rsp+1A0h+var_160]
0x1800ade73  movups  xmm0, xmmword ptr [rax+30h]
0x1800ade77  movdqu  [rsp+1A0h+Buf1], xmm0
0x1800ade7d  mov     r8d, 10h; Size
0x1800ade83  lea     rdx, GUID_NULL; Buf2
0x1800ade8a  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x1800ade8f  call    memcmp_0
0x1800ade94  test    eax, eax
0x1800ade96  jz      loc_1800AE91A
0x1800ade9c  mov     qword ptr [rbp+0A0h+var_100], rbx
0x1800adea0  mov     qword ptr [rbp+0A0h+var_100+8], r15
0x1800adea4  mov     [rbp+0A0h+var_120], r13
0x1800adea8  mov     [rbp-78h], rdi
0x1800adeac  lea     r9, [rbp+0A0h+var_100]
0x1800adeb0  lea     r8, [rbp+0A0h+var_120]
0x1800adeb4  lea     rdx, [rsp+1A0h+Buf1]
0x1800adeb9  lea     rcx, [rbp+0A0h+var_D0]
0x1800adebd  call    ??0ETWTriggerDef@Diagnostics@Microsoft@@QEAA@AEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1@Z; Microsoft::Diagnostics::ETWTriggerDef::ETWTriggerDef(_GUID const &,std::wstring_view,std::wstring_view)
0x1800adec2  nop
0x1800adec3  lea     rdx, [rbp+0A0h+var_D0]
0x1800adec7  mov     rcx, r14
0x1800adeca  call    ??$make_shared@VETWTriggerInst@Diagnostics@Microsoft@@AEAVETWTriggerDef@23@@std@@YA?AV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@0@AEAVETWTriggerDef@Diagnostics@Microsoft@@@Z; std::make_shared<Microsoft::Diagnostics::ETWTriggerInst,Microsoft::Diagnostics::ETWTriggerDef &>(Microsoft::Diagnostics::ETWTriggerDef &)
0x1800adecf  mov     [rsp+1A0h+var_148], 1
0x1800aded7  lea     rcx, [rbp+0A0h+var_F0]; void *
0x1800adedb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800adee0  nop
0x1800adee1  mov     rax, cs:off_18036D030; "ag"
0x1800adee8  mov     [rbp+0A0h+var_120], rax
0x1800adeec  mov     ebx, 2
0x1800adef1  mov     [rbp-78h], rbx
0x1800adef5  mov     qword ptr [rsp+1A0h+Buf1], rsi
0x1800adefa  xor     r13d, r13d
0x1800adefd  mov     dword ptr [rsp+1A0h+Buf1+8], r13d
0x1800adf02  mov     eax, dword ptr [rbp+0A0h+var_120+0Ch]
0x1800adf05  mov     dword ptr [rsp+1A0h+Buf1+0Ch], eax
0x1800adf09  lea     r9, [rbp+0A0h+var_120]
0x1800adf0d  lea     r8, [rsp+1A0h+Buf1]
0x1800adf12  lea     rdx, [rbp+0A0h+var_100]
0x1800adf16  mov     rcx, rsi
0x1800adf19  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800adf1e  mov     r15d, dword ptr [rbp+0A0h+var_100+8]
0x1800adf22  test    r15d, r15d
0x1800adf25  jz      loc_1800AE1FC
0x1800adf2b  mov     rcx, [rbp+0A8h]
0x1800adf32  mov     r12, qword ptr [rbp+0A0h+var_100]
0x1800adf36  mov     rax, [r12]
0x1800adf3a  cmp     byte ptr [rax+r15*4+7], 0FFh
0x1800adf40  jnz     loc_1800AE4A8
0x1800adf46  mov     rax, cs:off_18036D0A0; "ikey"
0x1800adf4d  mov     [rbp+0A0h+var_120], rax
0x1800adf51  lea     edi, [rbx+2]
0x1800adf54  mov     [rbp-78h], rdi
0x1800adf58  cmp     r12, rsi
0x1800adf5b  jnz     loc_1800AE64C
0x1800adf61  lea     r8, [rbp+0A0h+var_120]
0x1800adf65  mov     edx, r15d
0x1800adf68  mov     rcx, rsi
0x1800adf6b  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800adf70  test    eax, eax
0x1800adf72  jnz     loc_1800AE7BA
0x1800adf78  mov     rax, cs:off_18036D060; "usid"
0x1800adf7f  mov     [rbp+0A0h+var_120], rax
0x1800adf83  mov     [rbp-78h], rdi
0x1800adf87  cmp     r12, rsi
0x1800adf8a  jnz     loc_1800AE653
0x1800adf90  lea     r8, [rbp+0A0h+var_120]
0x1800adf94  mov     edx, r15d
0x1800adf97  mov     rcx, rsi
0x1800adf9a  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800adf9f  test    eax, eax
0x1800adfa1  jnz     loc_1800AE81B
0x1800adfa7  mov     rax, cs:off_18036D0E0; "irpc"
0x1800adfae  mov     [rbp+0A0h+var_120], rax
0x1800adfb2  mov     [rbp-78h], rdi
0x1800adfb6  cmp     r12, rsi
0x1800adfb9  jnz     loc_1800AE65A
0x1800adfbf  lea     r8, [rbp+0A0h+var_120]
0x1800adfc3  mov     edx, r15d
0x1800adfc6  mov     rcx, rsi
0x1800adfc9  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800adfce  test    eax, eax
0x1800adfd0  jz      short loc_1800AE014
0x1800adfd2  mov     ecx, eax
0x1800adfd4  mov     rax, [rsi]
0x1800adfd7  lea     rcx, [rax+rcx*4]
0x1800adfdb  cmp     byte ptr [rcx+7], 0F9h
0x1800adfdf  jnz     loc_1800AE9AC
0x1800adfe5  call    ?GetUnchecked@?$JsonImplementType@_N@@SA_NAEBVJsonValue@@@Z; JsonImplementType<bool>::GetUnchecked(JsonValue const &)
0x1800adfea  mov     dl, al
0x1800adfec  mov     al, r13b
0x1800adfef  mov     rcx, [rbp+0A8h]; this
0x1800adff6  test    al, al
0x1800adff8  jnz     loc_1800AE590
0x1800adffe  mov     rcx, [r14]
0x1800ae001  mov     al, [rcx+2BAh]
0x1800ae007  and     al, 0EFh
0x1800ae009  shl     dl, 4
0x1800ae00c  or      al, dl
0x1800ae00e  mov     [rcx+2BAh], al
0x1800ae014  mov     rax, cs:off_18036D040; "ita"
0x1800ae01b  mov     [rbp+0A0h+var_120], rax
0x1800ae01f  mov     qword ptr [rbp-78h], 3
0x1800ae027  cmp     r12, rsi
0x1800ae02a  jnz     loc_1800AE661
0x1800ae030  lea     r8, [rbp+0A0h+var_120]
0x1800ae034  mov     edx, r15d
0x1800ae037  mov     rcx, rsi
0x1800ae03a  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800ae03f  test    eax, eax
0x1800ae041  jnz     loc_1800AE2E8
0x1800ae047  mov     rax, cs:off_18036D090; "rxt"
0x1800ae04e  mov     [rbp+0A0h+var_120], rax
0x1800ae052  mov     qword ptr [rbp-78h], 3
0x1800ae05a  cmp     r12, rsi
0x1800ae05d  jnz     loc_1800AE668
0x1800ae063  lea     r8, [rbp+0A0h+var_120]
0x1800ae067  mov     edx, r15d
0x1800ae06a  mov     rcx, rsi
0x1800ae06d  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800ae072  test    eax, eax
0x1800ae074  jnz     loc_1800AE4FB
0x1800ae07a  mov     rax, cs:off_18036D0D0; "ei"
0x1800ae081  mov     [rbp+0A0h+var_120], rax
0x1800ae085  mov     [rbp-78h], rbx
0x1800ae089  cmp     r12, rsi
0x1800ae08c  jnz     loc_1800AE679
0x1800ae092  lea     r8, [rbp+0A0h+var_120]
0x1800ae096  mov     edx, r15d
0x1800ae099  mov     rcx, rsi
0x1800ae09c  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800ae0a1  test    eax, eax
0x1800ae0a3  jnz     loc_1800AE53F
0x1800ae0a9  mov     rax, cs:off_18036D070; "ev"
0x1800ae0b0  mov     [rbp+0A0h+var_120], rax
0x1800ae0b4  mov     [rbp-78h], rbx
0x1800ae0b8  cmp     r12, rsi
0x1800ae0bb  jnz     loc_1800AE680
0x1800ae0c1  lea     r8, [rbp+0A0h+var_120]
0x1800ae0c5  mov     edx, r15d
0x1800ae0c8  mov     rcx, rsi
0x1800ae0cb  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800ae0d0  test    eax, eax
0x1800ae0d2  jnz     loc_1800AE32F
0x1800ae0d8  mov     rax, cs:off_18036D0C0; "el"
0x1800ae0df  mov     [rbp+0A0h+var_120], rax
0x1800ae0e3  mov     [rbp-78h], rbx
0x1800ae0e7  cmp     r12, rsi
0x1800ae0ea  jnz     loc_1800AE687
0x1800ae0f0  lea     r8, [rbp+0A0h+var_120]
0x1800ae0f4  mov     edx, r15d
0x1800ae0f7  mov     rcx, rsi
0x1800ae0fa  call    ??$Find@$$V@JsonBuilder@@AEBAIIAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::Find<>(uint,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800ae0ff  test    eax, eax
  ... truncated ...
```
