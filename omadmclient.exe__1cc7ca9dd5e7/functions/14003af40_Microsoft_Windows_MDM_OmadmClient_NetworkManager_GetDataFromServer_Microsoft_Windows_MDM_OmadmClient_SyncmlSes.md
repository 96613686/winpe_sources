# Microsoft::Windows::MDM::OmadmClient::NetworkManager::GetDataFromServer(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,IStream *)

- ea: `0x14003af40`
- end: `0x14003b839`
- name: `?GetDataFromServer@NetworkManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEAUIStream@@@Z`
- size: `2297`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::NetworkManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, struct IStream *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000e610`
- `0x140013404`
- `0x1400134a4`
- `0x14001391c`
- `0x14003a104`
- `0x14003a940`
- `0x14003af40`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b58f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b58f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b0a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b0e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b5ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b0a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b0e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003b5ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b09b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b0d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b29f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b563`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b5a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b09b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b0d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b29f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b563`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b5a0`
- `DMCmnUtils!CopyString` at `0x14003b2cb`
- `DMCmnUtils!CopyString` at `0x14003b2cb`
- `DMCmnUtils!InvStrCmpNIW` at `0x14003b222`
- `DMCmnUtils!InvStrCmpNIW` at `0x14003b246`
- `DMCmnUtils!InvStrCmpNIW` at `0x14003b26a`
- `DMCmnUtils!InvStrCmpNIW` at `0x14003b222`
- `DMCmnUtils!InvStrCmpNIW` at `0x14003b246`
- `DMCmnUtils!InvStrCmpNIW` at `0x14003b26a`

## string_xrefs

- `0x14003b217`: `application/vnd.syncml.dm+xml`
- `0x14003b23b`: `application/vnd.syncml.dm+wbxml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkManager::GetDataFromServer(
        Microsoft::Windows::MDM::OmadmClient::NetworkManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        struct IStream *a3)
{
  struct COmaDmLogger *Logger; // rax
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // ebx
  void *v9; // rdi
  DWORD LastError; // ebx
  void *v11; // rdi
  DWORD v12; // ebx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r15
  __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rax
  unsigned int v20; // r14d
  __int64 v21; // r8
  void *v22; // r13
  DWORD v23; // ebx
  int v24; // eax
  Microsoft::Windows::MDM::OmadmClient::NetworkManager *v25; // r13
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  struct COmaDmLogger *v31; // rax
  __int64 v32; // rax
  const unsigned __int16 *v33; // rcx
  unsigned __int16 *v34; // rdx
  unsigned __int16 v35; // r8
  unsigned __int16 *v36; // rcx
  int v37; // eax
  Microsoft::Windows::MDM::OmadmClient::NetworkManager *v38; // rcx
  void *v39; // rdi
  DWORD v40; // ebx
  void *v41; // rdi
  DWORD v42; // ebx
  int HmacParameters; // eax
  int v44; // eax
  unsigned int v45; // ecx
  struct IStream *v46; // rdi
  int v47; // eax
  int v48; // eax
  int *v50; // [rsp+20h] [rbp-E0h]
  Microsoft::Windows::MDM::OmadmClient::NetworkManager **v51; // [rsp+20h] [rbp-E0h]
  unsigned int v52; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v53; // [rsp+44h] [rbp-BCh] BYREF
  int v54; // [rsp+48h] [rbp-B8h] BYREF
  int v55; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v56[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v57; // [rsp+70h] [rbp-90h]
  unsigned int *v58; // [rsp+78h] [rbp-88h]
  struct IStream *v59; // [rsp+80h] [rbp-80h]
  _QWORD v60[2]; // [rsp+88h] [rbp-78h] BYREF
  int *v61; // [rsp+98h] [rbp-68h]
  __int64 v62; // [rsp+A0h] [rbp-60h]
  int v63[4]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v64; // [rsp+B8h] [rbp-48h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  Microsoft::Windows::MDM::OmadmClient::NetworkManager *v66; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v67[512]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v68[1024]; // [rsp+4E0h] [rbp+3E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+928h] [rbp+828h]

  v59 = a3;
  v66 = this;
  v52 = 0;
  Logger = COmaDmLogger::GetLogger();
  Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Logger, 2, "GetDataFromServer", 0);
  v56[0] = 0;
  v56[1] = "GetDataFromServer";
  v56[2] = COmaDmLogger::GetLogger();
  v57 = 2;
  v58 = &v52;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v54 = 12;
    v61 = &v54;
    v62 = 4;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, v6, 2);
  }
  v60[0] = this;
  v60[1] = a2;
  v61 = (int *)&v52;
  LOBYTE(v62) = 1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 8LL))(
         *((_QWORD *)this + 5),
         *((_QWORD *)a2 + 70),
         *((_QWORD *)a2 + 75));
  v8 = v7;
  v52 = v7;
  if ( v7 < 0 )
  {
    if ( v7 != -2147023888 && v7 != -2102788088 )
    {
      LODWORD(v56[0]) = 6010;
      HIDWORD(v56[0]) = v7;
      LOBYTE(v62) = 0;
      lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
      goto LABEL_77;
    }
    v52 = 0;
  }
  v9 = (void *)*((_QWORD *)a2 + 236);
  if ( v9 )
  {
    LastError = GetLastError();
    LocalFree(v9);
    SetLastError(LastError);
  }
  *((_QWORD *)a2 + 236) = 0;
  v11 = (void *)*((_QWORD *)a2 + 237);
  if ( v11 )
  {
    v12 = GetLastError();
    LocalFree(v11);
    SetLastError(v12);
  }
  *((_QWORD *)a2 + 237) = 0;
  v55 = 1024;
  v50 = (int *)v67;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 2) + 88LL))(
          *((_QWORD *)this + 2),
          *((_QWORD *)a2 + 251),
          1);
  v8 = v13;
  v52 = v13;
  if ( v13 >= 0 )
  {
    v15 = 512;
    v16 = 512;
    v17 = v67;
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    v8 = v16 == 0 ? 0x80070057 : 0;
    v52 = v8;
    if ( v16 )
    {
      v18 = -1;
      if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      {
        v19 = -1;
        do
          ++v19;
        while ( v67[v19] );
        v64 = v67;
        v65 = (unsigned int)(2 * v19 + 2);
        v50 = v63;
        McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, ContentTypeHeaderEvent, v14, 2);
      }
      v20 = 29;
      if ( InvStrCmpNIW(v67, L"application/vnd.syncml.dm+xml", 0x1Du)
        && (v20 = 31, InvStrCmpNIW(v67, L"application/vnd.syncml.dm+wbxml", 0x1Fu))
        && (v20 = 24, InvStrCmpNIW(v67, L"application/octet-stream", 0x18u)) )
      {
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) != 0 )
        {
          do
            ++v18;
          while ( v67[v18] );
          v64 = v67;
          v65 = (unsigned int)(2 * v18 + 2);
          McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, UnexpectedContentTypeHeaderEvent, v21, 2);
        }
        v56[0] = 0x82AC020100007553uLL;
        v8 = -2102656511;
        LOBYTE(v62) = 0;
        lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
      }
      else
      {
        v22 = (void *)*((_QWORD *)a2 + 94);
        if ( v22 )
        {
          v23 = GetLastError();
          LocalFree(v22);
          SetLastError(v23);
        }
        *((_QWORD *)a2 + 94) = 0;
        v24 = CopyString(v67, v20, (unsigned __int16 **)a2 + 94);
        v8 = v24;
        v52 = v24;
        if ( v24 >= 0 )
        {
          v55 = 1024;
          v25 = v66;
          v51 = (Microsoft::Windows::MDM::OmadmClient::NetworkManager **)v67;
          v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v66 + 2) + 88LL))(
                  *((_QWORD *)v66 + 2),
                  *((_QWORD *)a2 + 251),
                  5);
          v52 = v26;
          if ( v26 < 0 )
          {
            if ( v26 == -2147012746 )
            {
              if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
              {
                v51 = &v66;
                McGenEventWrite_EventWriteTransfer(
                  WP_OMADM_CLIENT_PROVIDER_Context,
                  ContentLengthHeaderNotFoundEvent,
                  v29,
                  1);
              }
              v31 = COmaDmLogger::GetLogger();
              Microsoft::Windows::TelemetryLogger::LogMeasure(v31, 1, 30005, 0);
            }
            else
            {
              if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 2) != 0 )
              {
                v54 = v26;
                v64 = (unsigned __int16 *)&v54;
                v65 = 4;
                v51 = (Microsoft::Windows::MDM::OmadmClient::NetworkManager **)v63;
                McGenEventWrite_EventWriteTransfer(
                  WP_OMADM_CLIENT_PROVIDER_Context,
                  ErrorGettingContentLengthHeaderEvent,
                  v29,
                  2);
              }
              MicrosoftTelemetryAssertTriggeredNoArgs(v28, v27, v29, v30, v51);
            }
          }
          else if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          {
            do
              ++v18;
            while ( v67[v18] );
            v64 = v67;
            v65 = (unsigned int)(2 * v18 + 2);
            v51 = (Microsoft::Windows::MDM::OmadmClient::NetworkManager **)v63;
            McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, ContentLengthHeaderEvent, v29, 2);
          }
          v32 = 2147483646;
          v33 = L"x-syncml-hmac";
          v34 = (unsigned __int16 *)v68;
          do
          {
            if ( !v32 )
              break;
            v35 = *v33;
            if ( !*v33 )
              break;
            ++v33;
            *v34++ = v35;
            --v32;
            --v15;
          }
          while ( v15 );
          v8 = v15 == 0 ? 0x8007007A : 0;
          v36 = v34 - 1;
          if ( v15 )
            v36 = v34;
          *v36 = 0;
          v52 = v15 == 0 ? 0x8007007A : 0;
          if ( v15 )
          {
            v55 = 1024;
            v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE *, unsigned __int16 *, int *))(**((_QWORD **)v25 + 2) + 88LL))(
                    *((_QWORD *)v25 + 2),
                    *((_QWORD *)a2 + 251),
                    0xFFFF,
                    v68,
                    v67,
                    &v55);
            v8 = v37;
            v52 = v37;
            if ( v37 >= 0 )
            {
              v39 = (void *)*((_QWORD *)a2 + 237);
              if ( v39 )
              {
                v40 = GetLastError();
                LocalFree(v39);
                SetLastError(v40);
              }
              *((_QWORD *)a2 + 237) = 0;
              v41 = (void *)*((_QWORD *)a2 + 236);
              if ( v41 )
              {
                v42 = GetLastError();
                LocalFree(v41);
                SetLastError(v42);
              }
              *((_QWORD *)a2 + 236) = 0;
              HmacParameters = Microsoft::Windows::MDM::OmadmClient::NetworkManager::ExtractHmacParameters(
                                 v38,
                                 v67,
                                 (unsigned __int16 **)a2 + 236,
                                 (unsigned __int16 **)a2 + 237);
              v8 = HmacParameters;
              v52 = HmacParameters;
              if ( HmacParameters < 0 )
              {
                LODWORD(v56[0]) = 18005;
                HIDWORD(v56[0]) = HmacParameters;
                LOBYTE(v62) = 0;
                lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
                goto LABEL_77;
              }
              if ( *((_DWORD *)a2 + 158) != 2 )
              {
                v56[0] = 0x82AC00050000753EuLL;
                v8 = -2102657019;
                LOBYTE(v62) = 0;
                lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
                goto LABEL_77;
              }
            }
            else if ( v37 != -2147012746 )
            {
              LODWORD(v56[0]) = 18044;
              HIDWORD(v56[0]) = v37;
              LOBYTE(v62) = 0;
              lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
              goto LABEL_77;
            }
            v53 = 0;
            v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64, unsigned int *))(**((_QWORD **)v25 + 2) + 96LL))(
                    *((_QWORD *)v25 + 2),
                    *((_QWORD *)a2 + 251),
                    v67,
                    1024,
                    &v53);
            v8 = v44;
            v52 = v44;
            if ( v44 >= 0 )
            {
              v45 = v53;
              if ( v53 )
              {
                v46 = v59;
                while ( 1 )
                {
                  v54 = 0;
                  v47 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, _QWORD, int *))(*(_QWORD *)v46 + 32LL))(
                          v46,
                          v67,
                          v45,
                          &v54);
                  v8 = v47;
                  v52 = v47;
                  if ( v47 < 0 )
                    break;
                  if ( v53 != v54 )
                  {
                    v56[0] = 0x800040050000468DuLL;
                    v8 = -2147467259;
                    LOBYTE(v62) = 0;
                    lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
                    goto LABEL_77;
                  }
                  v53 = 0;
                  v48 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64, unsigned int *))(**((_QWORD **)v25 + 2) + 96LL))(
                          *((_QWORD *)v25 + 2),
                          *((_QWORD *)a2 + 251),
                          v67,
                          1024,
                          &v53);
                  v8 = v48;
                  v52 = v48;
                  if ( v48 < 0 )
                  {
                    LODWORD(v56[0]) = 18048;
                    HIDWORD(v56[0]) = v48;
                    LOBYTE(v62) = 0;
                    lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
                    goto LABEL_77;
                  }
                  v45 = v53;
                  if ( !v53 )
                  {
                    LOBYTE(v62) = 0;
                    lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
                    goto LABEL_77;
                  }
                }
                LODWORD(v56[0]) = 18060;
                HIDWORD(v56[0]) = v47;
                LOBYTE(v62) = 0;
                lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
              }
              else
              {
                v56[0] = 0x82AC000800007534uLL;
                v8 = -2102657016;
                LOBYTE(v62) = 0;
                lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
              }
            }
            else
            {
              LODWORD(v56[0]) = 18047;
              HIDWORD(v56[0]) = v44;
              LOBYTE(v62) = 0;
              lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4EF,
              (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkmanager.cpp",
              (const char *)v8,
              (int)v51);
            LOBYTE(v62) = 0;
            lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4CD,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkmanager.cpp",
            (const char *)(unsigned int)v24,
            (int)v50);
          LOBYTE(v62) = 0;
          lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B2,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkmanager.cpp",
        (const char *)v8,
        (int)v67);
      LOBYTE(v62) = 0;
      lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
    }
  }
  else
  {
    LODWORD(v56[0]) = 18043;
    HIDWORD(v56[0]) = v13;
    LOBYTE(v62) = 0;
    lambda_458cff5539e62fd8a1288ab3cf6cc53c_::operator()(v60);
  }
LABEL_77:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v56);
  return v8;
}

```

## disassembly

```asm
0x14003af40  mov     [rsp-8+arg_18], rbx
0x14003af45  push    rbp
0x14003af46  push    rsi
0x14003af47  push    rdi
0x14003af48  push    r12
0x14003af4a  push    r13
0x14003af4c  push    r14
0x14003af4e  push    r15
0x14003af50  lea     rbp, [rsp-7F0h]
0x14003af58  sub     rsp, 8F0h
0x14003af5f  mov     rax, cs:__security_cookie
0x14003af66  xor     rax, rsp
0x14003af69  mov     [rbp+820h+var_40], rax
0x14003af70  mov     [rbp+820h+var_8A0], r8
0x14003af74  mov     rsi, rdx
0x14003af77  mov     r15, rcx
0x14003af7a  mov     [rbp+820h+var_858], rcx
0x14003af7e  xor     r12d, r12d
0x14003af81  mov     [rsp+920h+var_8E0], r12d
0x14003af86  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003af8b  xor     r9d, r9d
0x14003af8e  lea     rbx, aGetdatafromser; "GetDataFromServer"
0x14003af95  mov     r8, rbx
0x14003af98  lea     r13d, [r12+2]
0x14003af9d  mov     edx, r13d
0x14003afa0  mov     rcx, rax
0x14003afa3  call    ?LogFunctionEntryMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@PEBDPEBGZZ; Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Microsoft::Windows::TracingLevel,char const *,ushort const *,...)
0x14003afa8  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003afad  mov     [rsp+920h+var_8C8], r12
0x14003afb2  mov     [rsp+920h+var_8C0], rbx
0x14003afb7  mov     [rsp+920h+var_8B8], rax
0x14003afbc  mov     [rsp+920h+var_8B0], r13d
0x14003afc1  lea     rax, [rsp+920h+var_8E0]
0x14003afc6  mov     [rsp+920h+var_8A8], rax
0x14003afcb  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14003afd2  jz      short loc_14003B00C
0x14003afd4  mov     [rsp+920h+var_8D8], 0Ch
0x14003afdc  lea     rax, [rsp+920h+var_8D8]
0x14003afe1  mov     [rbp+820h+var_888], rax
0x14003afe5  mov     [rbp+820h+var_880], 4
0x14003afed  lea     rax, [rbp+820h+var_898]
0x14003aff1  mov     qword ptr [rsp+920h+var_900], rax
0x14003aff6  mov     r9d, r13d
0x14003aff9  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14003b000  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003b007  call    McGenEventWrite_EventWriteTransfer
0x14003b00c  mov     [rbp+820h+var_898], r15
0x14003b010  mov     [rbp+820h+var_890], rsi
0x14003b014  lea     rax, [rsp+920h+var_8E0]
0x14003b019  mov     [rbp+820h+var_888], rax
0x14003b01d  mov     byte ptr [rbp+820h+var_880], 1
0x14003b021  mov     rcx, [r15+28h]
0x14003b025  mov     rax, [rcx]
0x14003b028  mov     r8, [rsi+258h]
0x14003b02f  mov     rdx, [rsi+230h]
0x14003b036  mov     rax, [rax+8]
0x14003b03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b03f  mov     ebx, eax
0x14003b041  mov     [rsp+920h+var_8E0], eax
0x14003b045  test    eax, eax
0x14003b047  jns     short loc_14003B07B
0x14003b049  cmp     eax, 800703F0h
0x14003b04e  jz      short loc_14003B076
0x14003b050  cmp     eax, 82AA0008h
0x14003b055  jz      short loc_14003B076
0x14003b057  mov     dword ptr [rsp+920h+var_8C8], 177Ah
0x14003b05f  mov     dword ptr [rsp+920h+var_8C8+4], eax
0x14003b063  mov     byte ptr [rbp+820h+var_880], r12b
0x14003b067  lea     rcx, [rbp+820h+var_898]
0x14003b06b  call    _lambda_458cff5539e62fd8a1288ab3cf6cc53c___operator__
0x14003b070  nop
0x14003b071  jmp     loc_14003B802
0x14003b076  mov     [rsp+920h+var_8E0], r12d
0x14003b07b  lea     r14, [rsi+760h]
0x14003b082  mov     rdi, [r14]
0x14003b085  test    rdi, rdi
0x14003b088  jz      short loc_14003B0B5
0x14003b08a  call    cs:__imp_GetLastError
0x14003b091  nop     dword ptr [rax+rax+00h]
0x14003b096  mov     ebx, eax
0x14003b098  mov     rcx, rdi; hMem
0x14003b09b  call    cs:__imp_LocalFree
0x14003b0a2  nop     dword ptr [rax+rax+00h]
0x14003b0a7  mov     ecx, ebx; dwErrCode
0x14003b0a9  call    cs:__imp_SetLastError
0x14003b0b0  nop     dword ptr [rax+rax+00h]
0x14003b0b5  mov     [r14], r12
0x14003b0b8  lea     r14, [rsi+768h]
0x14003b0bf  mov     rdi, [r14]
0x14003b0c2  test    rdi, rdi
0x14003b0c5  jz      short loc_14003B0F2
0x14003b0c7  call    cs:__imp_GetLastError
0x14003b0ce  nop     dword ptr [rax+rax+00h]
0x14003b0d3  mov     ebx, eax
0x14003b0d5  mov     rcx, rdi; hMem
0x14003b0d8  call    cs:__imp_LocalFree
0x14003b0df  nop     dword ptr [rax+rax+00h]
0x14003b0e4  mov     ecx, ebx; dwErrCode
0x14003b0e6  call    cs:__imp_SetLastError
0x14003b0ed  nop     dword ptr [rax+rax+00h]
0x14003b0f2  mov     [r14], r12
0x14003b0f5  mov     [rsp+920h+var_8D0], 400h
0x14003b0fd  mov     rcx, [r15+10h]
0x14003b101  mov     rax, [rcx]
0x14003b104  lea     rdx, [rsp+920h+var_8D0]
0x14003b109  mov     [rsp+920h+var_8F8], rdx
0x14003b10e  lea     rdx, [rbp+820h+var_840]
0x14003b112  mov     qword ptr [rsp+920h+var_900], rdx; int
0x14003b117  xor     r9d, r9d
0x14003b11a  lea     r8d, [r9+1]
0x14003b11e  mov     rdx, [rsi+7D8h]
0x14003b125  mov     rax, [rax+58h]
0x14003b129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b12e  mov     ebx, eax
0x14003b130  mov     [rsp+920h+var_8E0], eax
0x14003b134  test    eax, eax
0x14003b136  jns     short loc_14003B157
0x14003b138  mov     dword ptr [rsp+920h+var_8C8], 467Bh
0x14003b140  mov     dword ptr [rsp+920h+var_8C8+4], eax
0x14003b144  mov     byte ptr [rbp+820h+var_880], r12b
0x14003b148  lea     rcx, [rbp+820h+var_898]
0x14003b14c  call    _lambda_458cff5539e62fd8a1288ab3cf6cc53c___operator__
0x14003b151  nop
0x14003b152  jmp     loc_14003B802
0x14003b157  mov     r15d, 200h
0x14003b15d  mov     ecx, r15d
0x14003b160  lea     rax, [rbp+820h+var_840]
0x14003b164  cmp     [rax], r12w
0x14003b168  jz      short loc_14003B173
0x14003b16a  add     rax, r13
0x14003b16d  sub     rcx, 1
0x14003b171  jnz     short loc_14003B164
0x14003b173  mov     rax, rcx
0x14003b176  neg     rax
0x14003b179  sbb     ebx, ebx
0x14003b17b  not     ebx
0x14003b17d  and     ebx, 80070057h
0x14003b183  mov     [rsp+920h+var_8E0], ebx
0x14003b187  test    rcx, rcx
0x14003b18a  jnz     short loc_14003B1BB
0x14003b18c  mov     rcx, [rbp+828h]; this
0x14003b193  mov     r9d, ebx; char *
0x14003b196  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003b19d  mov     edx, 4B2h; void *
0x14003b1a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b1a7  nop
0x14003b1a8  mov     byte ptr [rbp+820h+var_880], r12b
0x14003b1ac  lea     rcx, [rbp+820h+var_898]
0x14003b1b0  call    _lambda_458cff5539e62fd8a1288ab3cf6cc53c___operator__
0x14003b1b5  nop
0x14003b1b6  jmp     loc_14003B802
0x14003b1bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003b1bf  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14003b1c6  jz      short loc_14003B20E
0x14003b1c8  lea     rcx, [rbp+820h+var_840]
0x14003b1cc  mov     rax, rdi
0x14003b1cf  inc     rax
0x14003b1d2  cmp     [rcx+rax*2], r12w
0x14003b1d7  jnz     short loc_14003B1CF
0x14003b1d9  lea     eax, ds:2[rax*2]
0x14003b1e0  lea     rcx, [rbp+820h+var_840]
0x14003b1e4  mov     [rbp+820h+var_868], rcx
0x14003b1e8  mov     dword ptr [rbp+820h+var_860], eax
0x14003b1eb  mov     dword ptr [rbp+820h+var_860+4], r12d
0x14003b1ef  lea     rax, [rbp+820h+var_878]
0x14003b1f3  mov     qword ptr [rsp+920h+var_900], rax; int
0x14003b1f8  mov     r9d, r13d
0x14003b1fb  lea     rdx, ContentTypeHeaderEvent
0x14003b202  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003b209  call    McGenEventWrite_EventWriteTransfer
0x14003b20e  mov     r14d, 1Dh
0x14003b214  mov     r8d, r14d
0x14003b217  lea     rdx, aApplicationVnd_0; "application/vnd.syncml.dm+xml"
0x14003b21e  lea     rcx, [rbp+820h+var_840]
0x14003b222  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x14003b229  nop     dword ptr [rax+rax+00h]
0x14003b22e  test    eax, eax
0x14003b230  jz      short loc_14003B27E
0x14003b232  mov     r14d, 1Fh
0x14003b238  mov     r8d, r14d
0x14003b23b  lea     rdx, aApplicationVnd; "application/vnd.syncml.dm+wbxml"
0x14003b242  lea     rcx, [rbp+820h+var_840]
0x14003b246  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x14003b24d  nop     dword ptr [rax+rax+00h]
0x14003b252  test    eax, eax
0x14003b254  jz      short loc_14003B27E
0x14003b256  mov     r14d, 18h
0x14003b25c  mov     r8d, r14d
0x14003b25f  lea     rdx, aApplicationOct; "application/octet-stream"
0x14003b266  lea     rcx, [rbp+820h+var_840]
0x14003b26a  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x14003b271  nop     dword ptr [rax+rax+00h]
0x14003b276  test    eax, eax
0x14003b278  jnz     loc_14003B797
0x14003b27e  lea     r12, [rsi+2F0h]
0x14003b285  mov     r13, [r12]
0x14003b289  test    r13, r13
0x14003b28c  jz      short loc_14003B2B9
0x14003b28e  call    cs:__imp_GetLastError
0x14003b295  nop     dword ptr [rax+rax+00h]
0x14003b29a  mov     ebx, eax
0x14003b29c  mov     rcx, r13; hMem
0x14003b29f  call    cs:__imp_LocalFree
0x14003b2a6  nop     dword ptr [rax+rax+00h]
0x14003b2ab  mov     ecx, ebx; dwErrCode
0x14003b2ad  call    cs:__imp_SetLastError
0x14003b2b4  nop     dword ptr [rax+rax+00h]
0x14003b2b9  mov     qword ptr [r12], 0
0x14003b2c1  mov     r8, r12
0x14003b2c4  mov     edx, r14d
0x14003b2c7  lea     rcx, [rbp+820h+var_840]
0x14003b2cb  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14003b2d2  nop     dword ptr [rax+rax+00h]
0x14003b2d7  mov     ebx, eax
0x14003b2d9  mov     [rsp+920h+var_8E0], eax
0x14003b2dd  xor     r12d, r12d
0x14003b2e0  test    eax, eax
0x14003b2e2  jns     short loc_14003B313
0x14003b2e4  mov     rcx, [rbp+828h]; this
0x14003b2eb  mov     r9d, eax; char *
0x14003b2ee  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003b2f5  mov     edx, 4CDh; void *
0x14003b2fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b2ff  nop
0x14003b300  mov     byte ptr [rbp+820h+var_880], r12b
0x14003b304  lea     rcx, [rbp+820h+var_898]
0x14003b308  call    _lambda_458cff5539e62fd8a1288ab3cf6cc53c___operator__
0x14003b30d  nop
0x14003b30e  jmp     loc_14003B802
0x14003b313  mov     [rsp+920h+var_8D0], 400h
0x14003b31b  mov     r13, [rbp+820h+var_858]
0x14003b31f  mov     rcx, [r13+10h]
0x14003b323  mov     rax, [rcx]
0x14003b326  lea     rdx, [rsp+920h+var_8D0]
0x14003b32b  mov     [rsp+920h+var_8F8], rdx
0x14003b330  lea     rdx, [rbp+820h+var_840]
0x14003b334  mov     qword ptr [rsp+920h+var_900], rdx
0x14003b339  xor     r9d, r9d
0x14003b33c  lea     r8d, [r9+5]
0x14003b340  mov     rdx, [rsi+7D8h]
0x14003b347  mov     rax, [rax+58h]
0x14003b34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b350  mov     [rsp+920h+var_8E0], eax
0x14003b354  mov     r14d, 80072F76h
0x14003b35a  test    eax, eax
0x14003b35c  js      short loc_14003B3B6
0x14003b35e  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14003b365  jz      loc_14003B447
0x14003b36b  lea     rax, [rbp+820h+var_840]
0x14003b36f  inc     rdi
0x14003b372  cmp     [rax+rdi*2], r12w
0x14003b377  jnz     short loc_14003B36F
0x14003b379  lea     eax, ds:2[rdi*2]
0x14003b380  lea     rdx, [rbp+820h+var_840]
0x14003b384  mov     [rbp+820h+var_868], rdx
0x14003b388  mov     dword ptr [rbp+820h+var_860], eax
0x14003b38b  mov     dword ptr [rbp+820h+var_860+4], r12d
0x14003b38f  lea     rax, [rbp+820h+var_878]
0x14003b393  mov     qword ptr [rsp+920h+var_900], rax
0x14003b398  mov     r9d, 2
0x14003b39e  lea     rdx, ContentLengthHeaderEvent
0x14003b3a5  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003b3ac  call    McGenEventWrite_EventWriteTransfer
0x14003b3b1  jmp     loc_14003B447
0x14003b3b6  cmp     eax, r14d
0x14003b3b9  jnz     short loc_14003B402
0x14003b3bb  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 1
0x14003b3c2  jz      short loc_14003B3E6
0x14003b3c4  lea     rax, [rbp+820h+var_858]
0x14003b3c8  mov     qword ptr [rsp+920h+var_900], rax
0x14003b3cd  mov     r9d, 1
0x14003b3d3  lea     rdx, ContentLengthHeaderNotFoundEvent
0x14003b3da  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003b3e1  call    McGenEventWrite_EventWriteTransfer
0x14003b3e6  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003b3eb  xor     r9d, r9d
0x14003b3ee  lea     edx, [r9+1]
0x14003b3f2  mov     r8d, 7535h
0x14003b3f8  mov     rcx, rax
0x14003b3fb  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x14003b400  jmp     short loc_14003B447
0x14003b402  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 2
0x14003b409  jz      short loc_14003B442
0x14003b40b  mov     [rsp+920h+var_8D8], eax
0x14003b40f  lea     rax, [rsp+920h+var_8D8]
0x14003b414  mov     [rbp+820h+var_868], rax
0x14003b418  mov     [rbp+820h+var_860], 4
0x14003b420  lea     rax, [rbp+820h+var_878]
0x14003b424  mov     qword ptr [rsp+920h+var_900], rax; int
0x14003b429  mov     r9d, 2
0x14003b42f  lea     rdx, ErrorGettingContentLengthHeaderEvent
0x14003b436  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003b43d  call    McGenEventWrite_EventWriteTransfer
0x14003b442  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x14003b447  mov     eax, 7FFFFFFEh
0x14003b44c  lea     rcx, ?gc_szSyncmlHmacHeaderName@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "x-syncml-hmac"
0x14003b453  lea     rdx, [rbp+820h+var_440]
0x14003b45a  test    rax, rax
0x14003b45d  jz      short loc_14003B47E
0x14003b45f  movzx   r8d, word ptr [rcx]
  ... truncated ...
```
