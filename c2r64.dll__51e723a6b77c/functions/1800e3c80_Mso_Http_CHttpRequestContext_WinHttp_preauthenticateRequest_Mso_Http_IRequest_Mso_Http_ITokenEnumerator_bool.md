# Mso::Http::CHttpRequestContext_WinHttp::preauthenticateRequest(Mso::Http::IRequest &,Mso::Http::ITokenEnumerator &,bool &)

- ea: `0x1800e3c80`
- end: `0x1800e4d7e`
- name: `?preauthenticateRequest@CHttpRequestContext_WinHttp@Http@Mso@@UEAAXAEAVIRequest@23@AEAVITokenEnumerator@23@AEA_N@Z`
- size: `4350`
- prototype: `void __fastcall(Mso::Http::CHttpRequestContext_WinHttp *__hidden this, struct IRequest *, struct Mso::Http::ITokenEnumerator *, bool *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000adf0`
- `0x18000c5f8`
- `0x180025790`
- `0x1800258b4`
- `0x180030e64`
- `0x18003e690`
- `0x180063814`
- `0x1800d157c`
- `0x1800d1950`
- `0x1800d2200`
- `0x1800dd7e0`
- `0x1800dd8d8`
- `0x1800dea1c`
- `0x1800deab0`
- `0x1800debf4`
- `0x1800df0e4`
- `0x1800df314`
- `0x1800df81c`
- `0x1800dfbc0`
- `0x1800e0424`
- `0x1800e3c80`
- `0x1800f3d10`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e3f6e`
- `KERNEL32!GetLastError` at `0x1800e4b94`
- `KERNEL32!GetLastError` at `0x1800e4bb2`
- `KERNEL32!GetLastError` at `0x1800e4bd1`
- `KERNEL32!GetLastError` at `0x1800e4bef`
- `KERNEL32!GetLastError` at `0x1800e4c82`
- `KERNEL32!GetLastError` at `0x1800e4ca1`
- `KERNEL32!GetLastError` at `0x1800e4cbf`
- `KERNEL32!GetLastError` at `0x1800e3f6e`
- `KERNEL32!GetLastError` at `0x1800e4b94`
- `KERNEL32!GetLastError` at `0x1800e4bb2`
- `KERNEL32!GetLastError` at `0x1800e4bd1`
- `KERNEL32!GetLastError` at `0x1800e4bef`
- `KERNEL32!GetLastError` at `0x1800e4c82`
- `KERNEL32!GetLastError` at `0x1800e4ca1`
- `KERNEL32!GetLastError` at `0x1800e4cbf`
- `WINHTTP!WinHttpSetOption` at `0x1800e3f62`
- `WINHTTP!WinHttpSetOption` at `0x1800e3f62`

## string_xrefs

- `0x1800e4188`: `Authenticating with LiveId token`
- `0x1800e3d97`: `Context: Processing request token, authReason='Any'`
- `0x1800e4027`: `Processing request token`
- `0x1800e4511`: `Authenticating with ADAL token`
- `0x1800e48a3`: `Authenticating with ADAL token`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall Mso::Http::CHttpRequestContext_WinHttp::preauthenticateRequest(
        Mso::Http::CHttpRequestContext_WinHttp *this,
        struct IRequest *a2,
        struct Mso::Http::ITokenEnumerator *a3,
        bool *a4)
{
  Mso::Http::CHttpRequestContext_WinHttp *v7; // r15
  __int64 v8; // rbx
  __int64 *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rax
  int v15; // edx
  int v16; // r9d
  struct IRequestVtbl *lpVtbl; // rax
  int v18; // edi
  __int64 v19; // rax
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  struct IRequestVtbl *v23; // rax
  DWORD LastError; // eax
  __int64 v25; // rdx
  unsigned __int8 v26; // r12
  const wchar_t *v27; // rax
  __int64 v28; // rax
  int v29; // edx
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // rdi
  struct IRequestVtbl *v33; // rax
  char v34; // di
  _QWORD *v35; // r9
  __int64 v36; // rax
  int v37; // edx
  int v38; // r9d
  __int64 v39; // rax
  int v40; // r8d
  int v41; // r9d
  _QWORD *v42; // r9
  __int64 v43; // rax
  int v44; // edx
  int v45; // r9d
  Mso::Http::Flights *v46; // rcx
  void ***v47; // r9
  _QWORD *v48; // r9
  __int64 v49; // r8
  __int64 v50; // rax
  int v51; // edx
  int v52; // r9d
  __int64 (__fastcall ***v53)(); // rcx
  __int64 (__fastcall ***v54)(); // r9
  __int64 v55; // rax
  int v56; // edx
  int v57; // r9d
  Mso::Http::Flights *v58; // rcx
  _QWORD *v59; // r9
  __int64 v60; // rax
  int v61; // r8d
  int v62; // r9d
  char v63; // al
  _QWORD *v64; // r9
  __int64 v65; // r8
  __int64 v66; // rax
  int v67; // edx
  int v68; // r9d
  Mso::Http::Flights *v69; // rcx
  bool IsRetryWithNtlmEnabled; // al
  unsigned int v71; // ecx
  struct IRequestVtbl *v72; // rax
  __int64 v73; // rax
  int v74; // edx
  int v75; // r8d
  int v76; // r9d
  ULONG (__stdcall *AddRef)(IRequest *); // rdi
  DWORD v78; // eax
  __int64 v79; // rdx
  DWORD v80; // eax
  __int64 v81; // rdx
  DWORD v82; // eax
  __int64 v83; // rdx
  signed int v84; // ebx
  __int64 v85; // rax
  int v86; // r9d
  int v87; // edx
  DWORD v88; // eax
  __int64 v89; // rdx
  DWORD v90; // eax
  __int64 v91; // rdx
  signed int v92; // ebx
  __int64 v93; // rax
  int v94; // r9d
  int v95; // edx
  int v96; // [rsp+20h] [rbp-E0h]
  unsigned int v97; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v98; // [rsp+44h] [rbp-BCh] BYREF
  char v99; // [rsp+48h] [rbp-B8h] BYREF
  char v100; // [rsp+49h] [rbp-B7h] BYREF
  _BYTE v101[6]; // [rsp+4Ah] [rbp-B6h] BYREF
  const char *v102; // [rsp+50h] [rbp-B0h] BYREF
  const char *v103; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v104[6]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v105; // [rsp+78h] [rbp-88h] BYREF
  int Buffer; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v107; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v108[2]; // [rsp+88h] [rbp-78h] BYREF
  Mso::Http::CHttpRequestContext_WinHttp *v109; // [rsp+98h] [rbp-68h]
  __int64 v110; // [rsp+A0h] [rbp-60h]
  _DWORD v111[6]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall **v112)(); // [rsp+C0h] [rbp-40h] BYREF
  const char *v113; // [rsp+C8h] [rbp-38h]
  const wchar_t *v114; // [rsp+D0h] [rbp-30h]
  _BYTE v115[24]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v116; // [rsp+F0h] [rbp-10h]
  __int64 v117; // [rsp+F8h] [rbp-8h]
  _BYTE v118[32]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v119; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v120[8]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v121; // [rsp+130h] [rbp+30h]
  unsigned __int64 v122; // [rsp+138h] [rbp+38h]
  _BYTE v123[8]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v124[40]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v125[32]; // [rsp+170h] [rbp+70h] BYREF
  void **v126; // [rsp+190h] [rbp+90h] BYREF
  const wchar_t *v127; // [rsp+198h] [rbp+98h]
  __int64 v128; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v129; // [rsp+1A8h] [rbp+A8h]
  _BYTE v130[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v131[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v132[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v133[3]; // [rsp+210h] [rbp+110h] BYREF
  __int16 v134; // [rsp+228h] [rbp+128h]
  __int128 v135; // [rsp+230h] [rbp+130h] BYREF
  __int64 v136; // [rsp+240h] [rbp+140h]
  __int64 v137; // [rsp+248h] [rbp+148h]
  _QWORD v138[3]; // [rsp+250h] [rbp+150h] BYREF
  __int16 v139; // [rsp+268h] [rbp+168h]
  __int128 v140; // [rsp+270h] [rbp+170h] BYREF
  __int64 v141; // [rsp+280h] [rbp+180h]
  __int64 v142; // [rsp+288h] [rbp+188h]
  _BYTE v143[16]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v144; // [rsp+2A0h] [rbp+1A0h]
  _BYTE v145[16]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v146; // [rsp+2C0h] [rbp+1C0h]
  _BYTE v147[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v148[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v149[32]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v150[32]; // [rsp+350h] [rbp+250h] BYREF

  v7 = this;
  v109 = this;
  Mso::Http::CHttpRequestContext_WinHttp::GetIdFromRequest(v118);
  *a4 = 0;
  v8 = 0;
  v110 = 0;
  while ( 1 )
  {
    v9 = (__int64 *)(*(__int64 (__fastcall **)(struct Mso::Http::ITokenEnumerator *, _QWORD *, _QWORD))(*(_QWORD *)a3 + 16LL))(
                      a3,
                      v108,
                      0);
    v10 = *v9;
    *v9 = 0;
    v11 = v8;
    v8 = v10;
    v110 = v10;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v12 = v108[0];
    if ( v108[0] )
    {
      v108[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    }
    if ( !v10 )
      break;
    v98 = 0;
    (*(void (__fastcall **)(__int64, _DWORD *, _QWORD, unsigned int *))(*(_QWORD *)v10 + 24LL))(v10, v104, 0, &v98);
    v97 = 2;
    (*(void (__fastcall **)(__int64, _DWORD *, __int64, unsigned int *))(*(_QWORD *)v10 + 24LL))(v10, v104, 1, &v97);
    v13 = v97;
    if ( v97 == 2 )
    {
      v14 = Mso::Http::Logging::Structured::RequestId::RequestId(&v112, v118);
      v103 = "Context: Processing request token, authReason='Any'";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
        6062276,
        v15,
        50,
        v16,
        (__int64)&v103,
        v14);
      std::wstring::~wstring(&v115[8]);
      v99 = 0;
      (*(void (__fastcall **)(__int64, _DWORD *, __int64, char *))(*(_QWORD *)v10 + 40LL))(v10, v104, 9, &v99);
      if ( v99 )
      {
        lpVtbl = a2->lpVtbl;
        v112 = off_18017AD10;
        v117 = (__int64)&v112;
        ((void (__fastcall *)(struct IRequest *, _DWORD *, __int64 (__fastcall ***)()))lpVtbl[2].AddRef)(
          a2,
          v104,
          &v112);
        std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(&v112);
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
          v10,
          22321344,
          v98,
          v97,
          9);
      }
      v105 = 0;
      (*(void (__fastcall **)(__int64, _DWORD *, __int64, unsigned int *))(*(_QWORD *)v10 + 24LL))(v10, v104, 8, &v105);
      v18 = Mso::Http::ConvertAutoLogonLevel(v105);
      v113 = "WindowsAutoLogonLevel";
      LODWORD(v114) = v18;
      WORD2(v114) = 4;
      memset(v115, 0, sizeof(v115));
      v116 = 7;
      *(_WORD *)v115 = 0;
      v112 = (__int64 (__fastcall **)())&Mso::Http::Logging::Structured::WindowsEnabledHttpProtocol::`vftable';
      v19 = Mso::Http::Logging::Structured::RequestId::RequestId(&v119, v118);
      v103 = "Set AutoLogonLevel";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Proxy,Mso::Http::Logging::Structured::Url>(
        6062278,
        v20,
        v21,
        v22,
        (__int64)&v103,
        v19,
        (__int64)&v112);
      std::wstring::~wstring(v123);
      std::wstring::~wstring(v115);
      v23 = a2->lpVtbl;
      v112 = off_18017ACE0;
      LODWORD(v113) = v18;
      v117 = (__int64)&v112;
      ((void (__fastcall *)(struct IRequest *, _DWORD *, __int64 (__fastcall ***)()))v23[2].AddRef)(a2, v104, &v112);
      std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(&v112);
      Buffer = 0x40000000;
      if ( v18 == 1 && !WinHttpSetOption(*((HINTERNET *)v7 + 4), 0x53u, &Buffer, 4u) )
      {
        LastError = GetLastError();
        OExceptionLog::ThrowTag(18401353, v25, LastError, L"HttpWin Failed to set autologon level");
      }
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
        v10,
        22321345,
        v98,
        v97,
        8);
      v13 = v97;
    }
    if ( v13 == 1 )
    {
      v26 = 1;
LABEL_18:
      v113 = "AuthReason";
      v27 = L"Proxy";
      if ( !v26 )
        v27 = L"Server";
      v114 = v27;
      *(_WORD *)v115 = 4;
      *(_OWORD *)&v115[8] = 0;
      v116 = 0;
      v117 = 7;
      *(_WORD *)&v115[8] = 0;
      v112 = (__int64 (__fastcall **)())&Mso::Http::Logging::Structured::FirstScheme::`vftable';
      v28 = Mso::Http::Logging::Structured::RequestId::RequestId(&v119, v118);
      v103 = "Processing request token";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::RequestId,Mso::Http::Logging::Structured::AuthReason>(
        (unsigned int)&v112,
        v29,
        v30,
        v31,
        (__int64)&v103,
        v28,
        (__int64)&v112);
      std::wstring::~wstring(v123);
      std::wstring::~wstring(&v115[8]);
      v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 56LL))(v10, 6);
      if ( v32 )
      {
        v103 = "Setting certificate";
        Mso::Diagnostics::SendDiagnosticTrace<>(6062280, 831, 50, 2, (__int64)&v103);
        v33 = a2->lpVtbl;
        v112 = off_18017ACB0;
        v113 = (const char *)v32;
        v117 = (__int64)&v112;
        ((void (__fastcall *)(struct IRequest *, _DWORD *, __int64 (__fastcall ***)()))v33[2].AddRef)(a2, v104, &v112);
        std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(&v112);
        v96 = 6;
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(v10, 22321346, v98, v97);
      }
      (*(void (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v10 + 48LL))(v10, v131, 4);
      v34 = 0;
      if ( v131[2] )
      {
        v35 = v131;
        if ( v131[3] > 7u )
          v35 = (_QWORD *)v131[0];
        if ( *(_DWORD *)((__int64 (__fastcall *)(struct IRequest *, _DWORD *, const wchar_t *, _QWORD *))a2->lpVtbl->GetTypeInfoCount)(
                          a2,
                          v104,
                          L"Authorization",
                          v35) )
        {
          v78 = GetLastError();
          OExceptionLog::ThrowTag(18401355, v79, v78, L"HttpWin Failed to add LiveId auth header");
        }
        v36 = Mso::Http::Logging::Structured::RequestId::RequestId(&v112, v118);
        v103 = "Authenticating with LiveId token";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
          6062281,
          v37,
          50,
          v38,
          (__int64)&v103,
          v36);
        std::wstring::~wstring(&v115[8]);
        v96 = 4;
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(v10, 22321347, v98, v97);
      }
      v100 = 0;
      Storage::Configuration::ConfigurationManager::GetConfiguration<bool>(15002, &v100);
      if ( v100 )
      {
        v103 = 0;
        ((void (__fastcall *)(struct IRequest *, _DWORD *, const char **))a2->lpVtbl[1].QueryInterface)(a2, v111, &v103);
        if ( v111[0] )
        {
          v39 = Mso::Http::Logging::Structured::RequestId::RequestId(v149, v118);
          v133[1] = "Result";
          v133[2] = v111[0];
          v134 = 4;
          v135 = 0;
          v136 = 0;
          v137 = 7;
          LOWORD(v135) = 0;
          v133[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
          v102 = "Unable to get RequestSettings";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result,Mso::Http::Logging::Structured::RequestId>(
            543019804,
            (unsigned int)"Result",
            v40,
            v41,
            (__int64)&v102,
            (__int64)v133,
            v39);
          std::wstring::~wstring(&v135);
          std::wstring::~wstring(v150);
        }
        (*(void (__fastcall **)(__int64, _QWORD **, __int64))(*(_QWORD *)v10 + 48LL))(v10, &v119, 10);
        if ( v121 )
        {
          v48 = &v119;
          if ( v122 > 7 )
            v48 = v119;
          ((void (__fastcall *)(struct IRequest *, _DWORD *, const wchar_t *, _QWORD *))a2->lpVtbl->GetTypeInfoCount)(
            a2,
            v104,
            L"Authorization",
            v48);
          if ( byte_18021CBB8 )
          {
            LOBYTE(v49) = 1;
            (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v103 + 56LL))(v103, 44, v49);
          }
          if ( v104[0] )
          {
            v84 = GetLastError();
            v85 = Mso::Http::Logging::Structured::HttpResult::HttpResult(
                    (Mso::Http::Logging::Structured::HttpResult *)v147,
                    (const struct Mso::Http::Result *)v104);
            v127 = L"SH_ErrorCode";
            LODWORD(v128) = v84;
            WORD2(v128) = 0;
            v126 = &Mso::Logging::StructuredErrorCode::`vftable';
            if ( v84 > 0 )
              v84 = (unsigned __int16)v84 | 0x80070000;
            v87 = BYTE2(a2[3].lpVtbl) != 0 ? 15 : 10;
            OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredErrorCode,Mso::Http::Logging::Structured::HttpResult>(
              BYTE2(a2[3].lpVtbl) != 0 ? 19715103 : 18401357,
              v87,
              v84,
              v86,
              v96,
              v87,
              (__int64)&v126,
              v85);
          }
          v50 = Mso::Http::Logging::Structured::RequestId::RequestId(&v112, v118);
          v102 = "Authenticating with ADAL token";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
            6062283,
            v51,
            50,
            v52,
            (__int64)&v102,
            v50);
          std::wstring::~wstring(&v115[8]);
          (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
            v10,
            22321349,
            v98,
            v97,
            10);
        }
        else
        {
          (*(void (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v10 + 48LL))(v10, v132, 5);
          if ( v132[2] )
          {
            v42 = v132;
            if ( v132[3] > 7u )
              v42 = (_QWORD *)v132[0];
            if ( *(_DWORD *)((__int64 (__fastcall *)(struct IRequest *, _DWORD *, const wchar_t *, _QWORD *))a2->lpVtbl->GetTypeInfoCount)(
                              a2,
                              v104,
                              L"Cookie",
                              v42) )
            {
              v82 = GetLastError();
              OExceptionLog::ThrowTag(18401356, v83, v82, L"HttpWin Failed to add Cookie header");
            }
            v43 = Mso::Http::Logging::Structured::RequestId::RequestId(&v112, v118);
            v102 = "Authenticating with SharePoint Cookie";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
              6062282,
              v44,
              50,
              v45,
              (__int64)&v102,
              v43);
            std::wstring::~wstring(&v115[8]);
            (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
              v10,
              22321348,
              v98,
              v97,
              5);
            if ( Mso::Http::Flights::IsSpoAuthenticatorHeaderEnabled(v46) )
            {
              (*(void (__fastcall **)(__int64, void ***, __int64))(*(_QWORD *)v10 + 48LL))(v10, &v126, 12);
              if ( v128 )
              {
                v47 = &v126;
                if ( v129 > 7 )
                  v47 = (void ***)v126;
                if ( *(_DWORD *)((__int64 (__fastcall *)(struct IRequest *, _DWORD *, const wchar_t *, void ***))a2->lpVtbl->GetTypeInfoCount)(
                                  a2,
                                  v104,
                                  L"X-MS-SPO-Authenticator",
                                  v47) )
                {
                  v80 = GetLastError();
                  OExceptionLog::ThrowTag(570568974, v81, v80, L"Failed to add X-MS-SPO-Authenticator header");
                }
                v102 = "Setting X-MS-SPO-Authenticator header";
                Mso::Diagnostics::SendDiagnosticTrace<>(570568976, 831, 50, 2, (__int64)&v102);
                (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
                  v10,
                  570568975,
                  v98,
                  v97,
                  12);
              }
              std::wstring::~wstring(&v126);
            }
          }
          std::wstring::~wstring(v132);
        }
        v53 = (__int64 (__fastcall ***)())&v119;
      }
      else
      {
        (*(void (__fastcall **)(__int64, __int64 (__fastcall ***)(), __int64))(*(_QWORD *)v10 + 48LL))(v10, &v112, 5);
        if ( v114 )
        {
          v54 = &v112;
          if ( *(_QWORD *)v115 > 7u )
            v54 = (__int64 (__fastcall ***)())v112;
          if ( *(_DWORD *)((__int64 (__fastcall *)(struct IRequest *, _DWORD *, const wchar_t *, __int64 (__fastcall ***)()))a2->lpVtbl->GetTypeInfoCount)(
                            a2,
                            v104,
                            L"Cookie",
                            v54) )
          {
            v90 = GetLastError();
            OExceptionLog::ThrowTag(506869634, v91, v90, L"HttpWin Failed to add Cookie header");
          }
          v55 = Mso::Http::Logging::Structured::RequestId::RequestId(&v119, v118);
          v102 = "Authenticating with SharePoint Cookie";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
            506869636,
            v56,
            50,
            v57,
            (__int64)&v102,
            v55);
          std::wstring::~wstring(v123);
          v34 = 1;
          v96 = 5;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(v10, 506869635, v98, v97);
          if ( Mso::Http::Flights::IsSpoAuthenticatorHeaderEnabled(v58) )
          {
            (*(void (__fastcall **)(__int64, _QWORD **, __int64))(*(_QWORD *)v10 + 48LL))(v10, &v119, 12);
            if ( v121 )
            {
              v59 = &v119;
              if ( v122 > 7 )
                v59 = v119;
              if ( *(_DWORD *)((__int64 (__fastcall *)(struct IRequest *, _DWORD *, const wchar_t *, _QWORD *))a2->lpVtbl->GetTypeInfoCount)(
                                a2,
                                v104,
                                L"X-MS-SPO-Authenticator",
                                v59) )
              {
                v88 = GetLastError();
                OExceptionLog::ThrowTag(506869603, v89, v88, L"Failed to add X-MS-SPO-Authenticator header");
              }
              v102 = "Setting X-MS-SPO-Authenticator header";
              Mso::Diagnostics::SendDiagnosticTrace<>(506869633, 831, 50, 2, (__int64)&v102);
              v96 = 12;
              (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(
                v10,
                506869632,
                v98,
                v97);
            }
            std::wstring::~wstring(&v119);
          }
        }
        v107 = 0;
        ((void (__fastcall *)(struct IRequest *, _DWORD *, __int64 *))a2->lpVtbl[1].QueryInterface)(a2, v111, &v107);
        if ( v111[0] )
        {
          v60 = Mso::Http::Logging::Structured::RequestId::RequestId(v147, v118);
          v138[1] = "Result";
          v138[2] = v111[0];
          v139 = 4;
          v140 = 0;
          v141 = 0;
          v142 = 7;
          LOWORD(v140) = 0;
          v138[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
          v102 = "Unable to get RequestSettings";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result,Mso::Http::Logging::Structured::RequestId>(
            506869640,
            (unsigned int)"Result",
            v61,
            v62,
            (__int64)&v102,
            (__int64)v138,
            v60);
          std::wstring::~wstring(&v140);
          std::wstring::~wstring(v148);
        }
        v63 = 0;
        v101[0] = 0;
        if ( v107 )
        {
          (*(void (__fastcall **)(__int64, _DWORD *, __int64, _BYTE *))(*(_QWORD *)v107 + 48LL))(v107, v104, 43, v101);
          v63 = v101[0];
        }
        if ( !v34 || v63 )
        {
          (*(void (__fastcall **)(__int64, _QWORD **, __int64))(*(_QWORD *)v10 + 48LL))(v10, &v119, 10);
          if ( v121 )
          {
            v64 = &v119;
            if ( v122 > 7 )
              v64 = v119;
            ((void (__fastcall *)(struct IRequest *, _DWORD *, const wchar_t *, _QWORD *))a2->lpVtbl->GetTypeInfoCount)(
              a2,
              v104,
              L"Authorization",
              v64);
            if ( byte_18021CBB8 )
            {
              LOBYTE(v65) = 1;
              (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v107 + 56LL))(v107, 44, v65);
            }
            if ( v104[0] )
            {
              v92 = GetLastError();
              v93 = Mso::Http::Logging::Structured::HttpResult::HttpResult(
                      (Mso::Http::Logging::Structured::HttpResult *)v147,
                      (const struct Mso::Http::Result *)v104);
              v127 = L"SH_ErrorCode";
              LODWORD(v128) = v92;
              WORD2(v128) = 0;
              v126 = &Mso::Logging::StructuredErrorCode::`vftable';
              if ( v92 > 0 )
                v92 = (unsigned __int16)v92 | 0x80070000;
              v95 = BYTE2(a2[3].lpVtbl) != 0 ? 15 : 10;
              OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredErrorCode,Mso::Http::Logging::Structured::HttpResult>(
                BYTE2(a2[3].lpVtbl) != 0 ? 506869637 : 18401357,
                v95,
                v92,
                v94,
                v96,
                v95,
                (__int64)&v126,
                v93);
            }
            v66 = Mso::Http::Logging::Structured::RequestId::RequestId(&v126, v118);
            v102 = "Authenticating with ADAL token";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
              506869639,
              v67,
              50,
              v68,
              (__int64)&v102,
              v66);
            std::wstring::~wstring(v130);
            (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
              v10,
              506869638,
              v98,
              v97,
              10);
          }
          std::wstring::~wstring(&v119);
        }
        v53 = &v112;
      }
      std::wstring::~wstring(v53);
      (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v10 + 48LL))(v10, v145, 2);
      (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v10 + 48LL))(v10, v143, 3);
      IsRetryWithNtlmEnabled = Mso::Http::Flights::IsRetryWithNtlmEnabled(v69);
      v71 = v98;
      if ( IsRetryWithNtlmEnabled && v98 == 64 )
        BYTE5(a2[20].lpVtbl) = 1;
      if ( v146 || v71 == 128 || v71 == 2 || v71 == 4 )
      {
        v113 = "HasPassword";
        LOBYTE(v114) = v144 != 0;
        WORD1(v114) = 4;
        memset(v115, 0, sizeof(v115));
        v116 = 7;
        *(_WORD *)v115 = 0;
        v112 = (__int64 (__fastcall **)())&Mso::Http::Logging::Structured::IsAsync::`vftable';
        v73 = Mso::Http::Logging::Structured::RequestId::RequestId(&v119, v118);
        v102 = "Authenticating with name/password";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::RequestId,Mso::Http::Logging::Structured::HasPassword>(
          (unsigned int)&v112,
          v74,
          v75,
          v76,
          (__int64)&v102,
          v73,
          (__int64)&v112);
        std::wstring::~wstring(v123);
        std::wstring::~wstring(v115);
        AddRef = a2->lpVtbl[2].AddRef;
        LODWORD(v119) = v26;
        HIDWORD(v119) = v98;
        std::wstring::wstring(v120, v145);
        std::wstring::wstring(v124, v143);
        v124[32] = v26;
        std::wstring::wstring(v125, v118);
        v117 = 0;
        v117 = sub_1800DF314(&v119);
        ((void (__fastcall *)(struct IRequest *, _DWORD *, __int64 (__fastcall ***)()))AddRef)(a2, v104, &v112);
        std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(&v112);
        sub_1800DF81C(&v119);
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
          v10,
          22321351,
          v98,
          v97,
          2);
        std::wstring::~wstring(v143);
        std::wstring::~wstring(v145);
        std::wstring::~wstring(v131);
      }
      else
      {
        v72 = a2->lpVtbl;
        v108[1] = __PAIR64__(v71, v26);
        v112 = off_18017AC80;
        v113 = (const char *)__PAIR64__(v71, v26);
        v117 = (__int64)&v112;
        ((void (__fastcall *)(struct IRequest *, _DWORD *, __int64 (__fastcall ***)()))v72[2].AddRef)(a2, v104, &v112);
        std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(&v112);
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v10 + 64LL))(
          v10,
          22321350,
          v98,
          v97,
          2);
        std::wstring::~wstring(v143);
        std::wstring::~wstring(v145);
        std::wstring::~wstring(v131);
      }
      v7 = v109;
    }
    else if ( !v13 )
    {
      v26 = 0;
      goto LABEL_18;
    }
  }
  std::wstring::~wstring(v118);
}

```

## disassembly

```asm
0x1800e3c80  push    rbp
0x1800e3c82  push    rbx
0x1800e3c83  push    rsi
0x1800e3c84  push    rdi
0x1800e3c85  push    r12
0x1800e3c87  push    r13
0x1800e3c89  push    r14
0x1800e3c8b  push    r15
0x1800e3c8d  lea     rbp, [rsp-288h]
0x1800e3c95  sub     rsp, 388h
0x1800e3c9c  mov     rax, cs:__security_cookie
0x1800e3ca3  xor     rax, rsp
0x1800e3ca6  mov     [rbp+2C0h+var_50], rax
0x1800e3cad  mov     rbx, r9
0x1800e3cb0  mov     r13, r8
0x1800e3cb3  mov     r14, rdx
0x1800e3cb6  mov     r15, rcx
0x1800e3cb9  mov     [rbp+2C0h+var_328], rcx
0x1800e3cbd  lea     rcx, [rbp+2C0h+var_2C0]
0x1800e3cc1  call    ?GetIdFromRequest@CHttpRequestContext_WinHttp@Http@Mso@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVIRequest@23@@Z; Mso::Http::CHttpRequestContext_WinHttp::GetIdFromRequest(Mso::Http::IRequest &)
0x1800e3cc6  xor     edi, edi
0x1800e3cc8  mov     [rbx], dil
0x1800e3ccb  mov     ebx, edi
0x1800e3ccd  mov     [rbp+2C0h+var_320], rbx
0x1800e3cd1  mov     r12d, 4
0x1800e3cd7  mov     rax, [r13+0]
0x1800e3cdb  xor     r8d, r8d
0x1800e3cde  lea     rdx, [rbp+2C0h+var_338]
0x1800e3ce2  mov     rcx, r13
0x1800e3ce5  mov     rax, [rax+10h]
0x1800e3ce9  call    cs:__guard_dispatch_icall_fptr
0x1800e3cef  mov     rsi, [rax]
0x1800e3cf2  mov     [rax], rdi
0x1800e3cf5  mov     rcx, rbx
0x1800e3cf8  mov     rbx, rsi
0x1800e3cfb  mov     [rbp+2C0h+var_320], rbx
0x1800e3cff  test    rcx, rcx
0x1800e3d02  jz      short loc_1800E3D11
0x1800e3d04  mov     rax, [rcx]
0x1800e3d07  mov     rax, [rax+8]
0x1800e3d0b  call    cs:__guard_dispatch_icall_fptr
0x1800e3d11  mov     rcx, [rbp+2C0h+var_338]
0x1800e3d15  test    rcx, rcx
0x1800e3d18  jz      short loc_1800E3D2B
0x1800e3d1a  mov     [rbp+2C0h+var_338], rdi
0x1800e3d1e  mov     rax, [rcx]
0x1800e3d21  mov     rax, [rax+8]
0x1800e3d25  call    cs:__guard_dispatch_icall_fptr
0x1800e3d2b  test    rsi, rsi
0x1800e3d2e  jz      loc_1800E4D52
0x1800e3d34  mov     [rsp+3C0h+var_37C], edi
0x1800e3d38  mov     rax, [rsi]
0x1800e3d3b  lea     r9, [rsp+3C0h+var_37C]
0x1800e3d40  xor     r8d, r8d
0x1800e3d43  lea     rdx, [rsp+3C0h+var_360]
0x1800e3d48  mov     rcx, rsi
0x1800e3d4b  mov     rax, [rax+18h]
0x1800e3d4f  call    cs:__guard_dispatch_icall_fptr
0x1800e3d55  mov     [rsp+3C0h+var_380], 2
0x1800e3d5d  mov     rax, [rsi]
0x1800e3d60  lea     r9, [rsp+3C0h+var_380]
0x1800e3d65  mov     r8d, 1
0x1800e3d6b  lea     rdx, [rsp+3C0h+var_360]
0x1800e3d70  mov     rcx, rsi
0x1800e3d73  mov     rax, [rax+18h]
0x1800e3d77  call    cs:__guard_dispatch_icall_fptr
0x1800e3d7d  mov     eax, [rsp+3C0h+var_380]
0x1800e3d81  cmp     eax, 2
0x1800e3d84  jnz     loc_1800E3FB6
0x1800e3d8a  lea     rdx, [rbp+2C0h+var_2C0]
0x1800e3d8e  lea     rcx, [rbp+2C0h+var_300]
0x1800e3d92  call    ??0RequestId@Structured@Logging@Http@Mso@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Http::Logging::Structured::RequestId::RequestId(std::wstring const &)
0x1800e3d97  lea     rcx, aContextProcess; "Context: Processing request token, auth"...
0x1800e3d9e  mov     [rsp+3C0h+var_368], rcx
0x1800e3da3  mov     [rsp+3C0h+var_398], rax
0x1800e3da8  lea     rax, [rsp+3C0h+var_368]
0x1800e3dad  mov     [rsp+3C0h+var_3A0], rax
0x1800e3db2  mov     ecx, 5C80C4h
0x1800e3db7  mov     r8d, 32h ; '2'
0x1800e3dbd  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800e3dc2  lea     rcx, [rbp+2C0h+var_2E8+8]; void *
0x1800e3dc6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e3dcb  mov     [rsp+3C0h+var_378], dil
0x1800e3dd0  mov     rax, [rsi]
0x1800e3dd3  lea     r9, [rsp+3C0h+var_378]
0x1800e3dd8  mov     r8d, 9
0x1800e3dde  lea     rdx, [rsp+3C0h+var_360]
0x1800e3de3  mov     rcx, rsi
0x1800e3de6  mov     rax, [rax+28h]
0x1800e3dea  call    cs:__guard_dispatch_icall_fptr
0x1800e3df0  cmp     [rsp+3C0h+var_378], dil
0x1800e3df5  jz      short loc_1800E3E57
0x1800e3df7  mov     rax, [r14]
0x1800e3dfa  lea     rcx, off_18017AD10
0x1800e3e01  mov     [rbp+2C0h+var_300], rcx
0x1800e3e05  lea     rcx, [rbp+2C0h+var_300]
0x1800e3e09  mov     [rbp+2C0h+var_2C8], rcx
0x1800e3e0d  lea     r8, [rbp+2C0h+var_300]
0x1800e3e11  lea     rdx, [rsp+3C0h+var_360]
0x1800e3e16  mov     rcx, r14
0x1800e3e19  mov     rax, [rax+108h]
0x1800e3e20  call    cs:__guard_dispatch_icall_fptr
0x1800e3e26  nop
0x1800e3e27  lea     rcx, [rbp+2C0h+var_300]
0x1800e3e2b  call    ??1?$_Func_class@V?$unique_ptr@UIGrfMessage@GrfCommands@Telemetry@Mso@@U?$default_delete@UIGrfMessage@GrfCommands@Telemetry@Mso@@@std@@@std@@V12@@std@@QEAA@XZ; std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(void)
0x1800e3e30  mov     rax, [rsi]
0x1800e3e33  mov     dword ptr [rsp+3C0h+var_3A0], 9
0x1800e3e3b  mov     r9d, [rsp+3C0h+var_380]
0x1800e3e40  mov     r8d, [rsp+3C0h+var_37C]
0x1800e3e45  mov     edx, 15498C0h
0x1800e3e4a  mov     rcx, rsi
0x1800e3e4d  mov     rax, [rax+40h]
0x1800e3e51  call    cs:__guard_dispatch_icall_fptr
0x1800e3e57  mov     [rsp+3C0h+var_348], edi
0x1800e3e5b  mov     rax, [rsi]
0x1800e3e5e  lea     r9, [rsp+3C0h+var_348]
0x1800e3e63  mov     r8d, 8
0x1800e3e69  lea     rdx, [rsp+3C0h+var_360]
0x1800e3e6e  mov     rcx, rsi
0x1800e3e71  mov     rax, [rax+18h]
0x1800e3e75  call    cs:__guard_dispatch_icall_fptr
0x1800e3e7b  mov     ecx, [rsp+3C0h+var_348]
0x1800e3e7f  call    ?ConvertAutoLogonLevel@Http@Mso@@YAKW4AutoLogonLevel@12@@Z; Mso::Http::ConvertAutoLogonLevel(Mso::Http::AutoLogonLevel)
0x1800e3e84  mov     edi, eax
0x1800e3e86  lea     rax, aWindowsautolog; "WindowsAutoLogonLevel"
0x1800e3e8d  mov     [rbp+2C0h+var_2F8], rax
0x1800e3e91  mov     dword ptr [rbp+2C0h+var_2F0], edi
0x1800e3e94  mov     word ptr [rbp+2C0h+var_2F0+4], r12w
0x1800e3e99  xorps   xmm0, xmm0
0x1800e3e9c  movups  xmmword ptr [rbp-28h], xmm0
0x1800e3ea0  xor     eax, eax
0x1800e3ea2  mov     [rbp+2C0h+var_2D8], rax
0x1800e3ea6  mov     [rbp+2C0h+var_2D0], 7
0x1800e3eae  mov     word ptr [rbp+2C0h+var_2E8], ax
0x1800e3eb2  lea     rax, ??_7WindowsEnabledHttpProtocol@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::WindowsEnabledHttpProtocol::`vftable'
0x1800e3eb9  mov     [rbp+2C0h+var_300], rax
0x1800e3ebd  lea     rdx, [rbp+2C0h+var_2C0]
0x1800e3ec1  lea     rcx, [rbp+2C0h+var_2A0]
0x1800e3ec5  call    ??0RequestId@Structured@Logging@Http@Mso@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Http::Logging::Structured::RequestId::RequestId(std::wstring const &)
0x1800e3eca  lea     rcx, aSetAutologonle; "Set AutoLogonLevel"
0x1800e3ed1  mov     [rsp+3C0h+var_368], rcx
0x1800e3ed6  lea     rcx, [rbp+2C0h+var_300]
0x1800e3eda  mov     [rsp+3C0h+var_390], rcx
0x1800e3edf  mov     [rsp+3C0h+var_398], rax
0x1800e3ee4  lea     rax, [rsp+3C0h+var_368]
0x1800e3ee9  mov     [rsp+3C0h+var_3A0], rax
0x1800e3eee  mov     ecx, 5C80C6h
0x1800e3ef3  call    ??$SendDiagnosticTrace@UProxy@Structured@Logging@Http@Mso@@UUrl@2345@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUProxy@Structured@3Http@1@$$QEAUUrl@93Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Proxy,Mso::Http::Logging::Structured::Url>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Proxy &&,Mso::Http::Logging::Structured::Url &&)
0x1800e3ef8  lea     rcx, [rbp+2C0h+var_280]; void *
0x1800e3efc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e3f01  lea     rcx, [rbp+2C0h+var_2E8]; void *
0x1800e3f05  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e3f0a  mov     rax, [r14]
0x1800e3f0d  lea     rcx, off_18017ACE0
0x1800e3f14  mov     [rbp+2C0h+var_300], rcx
0x1800e3f18  mov     dword ptr [rbp+2C0h+var_2F8], edi
0x1800e3f1b  lea     rcx, [rbp+2C0h+var_300]
0x1800e3f1f  mov     [rbp+2C0h+var_2C8], rcx
0x1800e3f23  lea     r8, [rbp+2C0h+var_300]
0x1800e3f27  lea     rdx, [rsp+3C0h+var_360]
0x1800e3f2c  mov     rcx, r14
0x1800e3f2f  mov     rax, [rax+108h]
0x1800e3f36  call    cs:__guard_dispatch_icall_fptr
0x1800e3f3c  nop
0x1800e3f3d  lea     rcx, [rbp+2C0h+var_300]
0x1800e3f41  call    ??1?$_Func_class@V?$unique_ptr@UIGrfMessage@GrfCommands@Telemetry@Mso@@U?$default_delete@UIGrfMessage@GrfCommands@Telemetry@Mso@@@std@@@std@@V12@@std@@QEAA@XZ; std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(void)
0x1800e3f46  mov     [rsp+3C0h+Buffer], 40000000h
0x1800e3f4e  cmp     edi, 1
0x1800e3f51  jnz     short loc_1800E3F89
0x1800e3f53  mov     r9d, r12d; dwBufferLength
0x1800e3f56  lea     r8, [rsp+3C0h+Buffer]; lpBuffer
0x1800e3f5b  lea     edx, [rdi+52h]; dwOption
0x1800e3f5e  mov     rcx, [r15+20h]; hInternet
0x1800e3f62  call    cs:__imp_WinHttpSetOption
0x1800e3f68  xor     edi, edi
0x1800e3f6a  test    eax, eax
0x1800e3f6c  jnz     short loc_1800E3F8B
0x1800e3f6e  call    cs:__imp_GetLastError
0x1800e3f74  mov     r8d, eax
0x1800e3f77  lea     r9, aHttpwinFailedT_1; "HttpWin Failed to set autologon level"
0x1800e3f7e  mov     ecx, 118C849h
0x1800e3f83  call    ?ThrowTag@OExceptionLog@@YAXKW4exceptionType@et@@JPEB_WW4Category@Logging@Mso@@W4Severity@56@@Z; OExceptionLog::ThrowTag(ulong,et::exceptionType,long,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity)
0x1800e3f89  xor     edi, edi
0x1800e3f8b  mov     rax, [rsi]
0x1800e3f8e  mov     dword ptr [rsp+3C0h+var_3A0], 8
0x1800e3f96  mov     r9d, [rsp+3C0h+var_380]
0x1800e3f9b  mov     r8d, [rsp+3C0h+var_37C]
0x1800e3fa0  mov     edx, 15498C1h
0x1800e3fa5  mov     rcx, rsi
0x1800e3fa8  mov     rax, [rax+40h]
0x1800e3fac  call    cs:__guard_dispatch_icall_fptr
0x1800e3fb2  mov     eax, [rsp+3C0h+var_380]
0x1800e3fb6  cmp     eax, 1
0x1800e3fb9  jz      short loc_1800E3FC8
0x1800e3fbb  test    eax, eax
0x1800e3fbd  jnz     loc_1800E3CD7
0x1800e3fc3  mov     r12b, dil
0x1800e3fc6  jmp     short loc_1800E3FCB
0x1800e3fc8  mov     r12b, 1
0x1800e3fcb  lea     rax, aAuthreason; "AuthReason"
0x1800e3fd2  mov     [rbp+2C0h+var_2F8], rax
0x1800e3fd6  lea     rcx, aServer; "Server"
0x1800e3fdd  lea     rax, aProxy; "Proxy"
0x1800e3fe4  test    r12b, r12b
0x1800e3fe7  cmovz   rax, rcx
0x1800e3feb  mov     [rbp+2C0h+var_2F0], rax
0x1800e3fef  mov     eax, 4
0x1800e3ff4  mov     word ptr [rbp+2C0h+var_2E8], ax
0x1800e3ff8  xorps   xmm0, xmm0
0x1800e3ffb  movups  [rbp+2C0h+var_2E8+8], xmm0
0x1800e3fff  mov     [rbp+2C0h+var_2D0], rdi
0x1800e4003  lea     r15d, [rax+3]
0x1800e4007  mov     [rbp+2C0h+var_2C8], r15
0x1800e400b  mov     word ptr [rbp+2C0h+var_2E8+8], di
0x1800e400f  lea     rax, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x1800e4016  mov     [rbp+2C0h+var_300], rax
0x1800e401a  lea     rdx, [rbp+2C0h+var_2C0]
0x1800e401e  lea     rcx, [rbp+2C0h+var_2A0]
0x1800e4022  call    ??0RequestId@Structured@Logging@Http@Mso@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Http::Logging::Structured::RequestId::RequestId(std::wstring const &)
0x1800e4027  lea     rcx, aProcessingRequ; "Processing request token"
0x1800e402e  mov     [rsp+3C0h+var_368], rcx
0x1800e4033  lea     rcx, [rbp+2C0h+var_300]
0x1800e4037  mov     [rsp+3C0h+var_390], rcx
0x1800e403c  mov     [rsp+3C0h+var_398], rax
0x1800e4041  lea     rax, [rsp+3C0h+var_368]
0x1800e4046  mov     [rsp+3C0h+var_3A0], rax
0x1800e404b  call    ??$SendDiagnosticTrace@URequestId@Structured@Logging@Http@Mso@@UAuthReason@2345@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAURequestId@Structured@3Http@1@$$QEAUAuthReason@93Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::RequestId,Mso::Http::Logging::Structured::AuthReason>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::RequestId &&,Mso::Http::Logging::Structured::AuthReason &&)
0x1800e4050  lea     rcx, [rbp+2C0h+var_280]; void *
0x1800e4054  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e4059  lea     rcx, [rbp+2C0h+var_2E8+8]; void *
0x1800e405d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e4062  mov     rax, [rsi]
0x1800e4065  lea     edx, [r15-1]
0x1800e4069  mov     rcx, rsi
0x1800e406c  mov     rax, [rax+38h]
0x1800e4070  call    cs:__guard_dispatch_icall_fptr
0x1800e4076  mov     rdi, rax
0x1800e4079  test    rax, rax
0x1800e407c  jz      loc_1800E4114
0x1800e4082  lea     rax, aSettingCertifi; "Setting certificate"
0x1800e4089  mov     [rsp+3C0h+var_368], rax
0x1800e408e  lea     r9d, [r15-5]
0x1800e4092  lea     rax, [rsp+3C0h+var_368]
0x1800e4097  mov     [rsp+3C0h+var_3A0], rax
0x1800e409c  mov     edx, 33Fh
0x1800e40a1  mov     ecx, 5C80C8h
0x1800e40a6  lea     r8d, [r15+2Bh]
0x1800e40aa  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x1800e40af  mov     rax, [r14]
0x1800e40b2  lea     rcx, off_18017ACB0
0x1800e40b9  mov     [rbp+2C0h+var_300], rcx
0x1800e40bd  mov     [rbp+2C0h+var_2F8], rdi
0x1800e40c1  lea     rcx, [rbp+2C0h+var_300]
0x1800e40c5  mov     [rbp+2C0h+var_2C8], rcx
0x1800e40c9  lea     r8, [rbp+2C0h+var_300]
0x1800e40cd  lea     rdx, [rsp+3C0h+var_360]
0x1800e40d2  mov     rcx, r14
0x1800e40d5  mov     rax, [rax+108h]
0x1800e40dc  call    cs:__guard_dispatch_icall_fptr
0x1800e40e2  nop
0x1800e40e3  lea     rcx, [rbp+2C0h+var_300]
0x1800e40e7  call    ??1?$_Func_class@V?$unique_ptr@UIGrfMessage@GrfCommands@Telemetry@Mso@@U?$default_delete@UIGrfMessage@GrfCommands@Telemetry@Mso@@@std@@@std@@V12@@std@@QEAA@XZ; std::_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>::~_Func_class<std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>,std::unique_ptr<Mso::Telemetry::GrfCommands::IGrfMessage>>(void)
0x1800e40ec  mov     rax, [rsi]
0x1800e40ef  mov     dword ptr [rsp+3C0h+var_3A0], 6
0x1800e40f7  mov     r9d, [rsp+3C0h+var_380]
0x1800e40fc  mov     r8d, [rsp+3C0h+var_37C]
0x1800e4101  mov     edx, 15498C2h
0x1800e4106  mov     rcx, rsi
0x1800e4109  mov     rax, [rax+40h]
0x1800e410d  call    cs:__guard_dispatch_icall_fptr
0x1800e4113  nop
0x1800e4114  mov     rax, [rsi]
0x1800e4117  mov     r8d, 4
0x1800e411d  lea     rdx, [rbp+2C0h+var_1F0]
0x1800e4124  mov     rcx, rsi
0x1800e4127  mov     rax, [rax+30h]
0x1800e412b  call    cs:__guard_dispatch_icall_fptr
0x1800e4131  nop
0x1800e4132  xor     edi, edi
0x1800e4134  cmp     [rbp+2C0h+var_1E0], rdi
0x1800e413b  jz      loc_1800E41E1
0x1800e4141  mov     rax, [r14]
0x1800e4144  lea     r9, [rbp+2C0h+var_1F0]
0x1800e414b  cmp     [rbp+2C0h+var_1D8], r15
0x1800e4152  cmova   r9, [rbp+2C0h+var_1F0]
0x1800e415a  lea     r8, aAuthorization; "Authorization"
0x1800e4161  lea     rdx, [rsp+3C0h+var_360]
0x1800e4166  mov     rcx, r14
0x1800e4169  mov     rax, [rax+18h]
0x1800e416d  call    cs:__guard_dispatch_icall_fptr
0x1800e4173  cmp     [rax], edi
0x1800e4175  jnz     loc_1800E4B94
0x1800e417b  lea     rdx, [rbp+2C0h+var_2C0]
0x1800e417f  lea     rcx, [rbp+2C0h+var_300]
0x1800e4183  call    ??0RequestId@Structured@Logging@Http@Mso@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Http::Logging::Structured::RequestId::RequestId(std::wstring const &)
0x1800e4188  lea     rcx, aAuthenticating; "Authenticating with LiveId token"
0x1800e418f  mov     [rsp+3C0h+var_368], rcx
0x1800e4194  mov     [rsp+3C0h+var_398], rax
0x1800e4199  lea     rax, [rsp+3C0h+var_368]
0x1800e419e  mov     [rsp+3C0h+var_3A0], rax
  ... truncated ...
```
