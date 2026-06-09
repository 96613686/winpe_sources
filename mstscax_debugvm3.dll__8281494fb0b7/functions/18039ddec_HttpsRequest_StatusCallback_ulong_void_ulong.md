# HttpsRequest::StatusCallback(ulong,void *,ulong)

- ea: `0x18039ddec`
- end: `0x18039f4b1`
- name: `?StatusCallback@HttpsRequest@@AEAAXKPEAXK@Z`
- size: `5829`
- prototype: `void __fastcall(HttpsRequest *__hidden this, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18039f4c0`

## callees

- `0x1800011f4`
- `0x180001e8c`
- `0x1800031a8`
- `0x180003280`
- `0x1800829d4`
- `0x180082ad8`
- `0x18039d3b8`
- `0x18039d9d4`
- `0x18039ddec`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18039e314`
- `KERNEL32!GetLastError` at `0x18039e622`
- `KERNEL32!GetLastError` at `0x18039e753`
- `KERNEL32!GetLastError` at `0x18039ef98`
- `KERNEL32!GetLastError` at `0x18039e314`
- `KERNEL32!GetLastError` at `0x18039e622`
- `KERNEL32!GetLastError` at `0x18039e753`
- `KERNEL32!GetLastError` at `0x18039ef98`
- `KERNEL32!SetEvent` at `0x18039f497`
- `KERNEL32!SetEvent` at `0x18039f497`
- `WINHTTP!WinHttpReceiveResponse` at `0x18039ef8a`
- `WINHTTP!WinHttpReceiveResponse` at `0x18039ef8a`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18039e306`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18039e745`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18039e306`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18039e745`
- `WINHTTP!WinHttpQueryHeaders` at `0x18039e614`
- `WINHTTP!WinHttpQueryHeaders` at `0x18039e614`

## string_xrefs

- `0x18039e36a`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039e4fb`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039e678`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039e7a9`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039e842`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039f0b0`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039f396`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039f450`: `onecore\termsrv\rdp\win\security\simplehttpsclient.cpp`
- `0x18039e3fc`: `HttpsRequest: No more response content data to read. Completing the request.`
- `0x18039e4cc`: `ReadResponseContentAsync failed.`
- `0x18039e3cc`: `No more response content data to read. Completing the request.`
- `0x18039e565`: `No more response content data to read. Completing the request.`
- `0x18039e502`: `HttpsRequest: ReadResponseContentAsync failed. Error code: 0x%X`
- `0x18039e2bf`: `HttpsRequest: Data was successfully read from the server. %d bytes were read.`
- `0x18039e29a`: `Data was successfully read from the server. %d bytes were read.`
- `0x18039f2a3`: `An error occurred during a call to WinHttpReadData.`
- `0x18039f32e`: `HttpsRequest: An error occurred during a call to WinHttpQueryDataAvailable. Error code: 0x%X`
- `0x18039f24a`: `An error occurred during a call to WinHttpWriteData.`
- `0x18039f2d5`: `HttpsRequest: An error occurred during a call to WinHttpReadData. Error code: 0x%X`
- `0x18039f352`: `An error occurred during a call to WinHttpReceiveResponse.`
- `0x18039f2fc`: `An error occurred during a call to WinHttpQueryDataAvailable.`
- `0x18039f384`: `HttpsRequest: An error occurred during a call to WinHttpReceiveResponse. Error code: 0x%X`
- `0x18039f1ca`: `HttpsRequest: An error occurred during a call to WinHttpGetProxyForUrlEx. Error code: 0x%X`
- `0x18039f07e`: `An error occurred during a call to API: %d`
- `0x18039f1f1`: `An error occurred during a call to WinHttpSendRequest.`
- `0x18039f27c`: `HttpsRequest: An error occurred during a call to WinHttpWriteData. Error code: 0x%X`
- `0x18039f198`: `An error occurred during a call to WinHttpGetProxyForUrlEx.`
- `0x18039f223`: `HttpsRequest: An error occurred during a call to WinHttpSendRequest. Error code: 0x%X`
- `0x18039f3fb`: `An unknown error happened during HTTP request.`
- `0x18039f0c9`: `HttpsRequest: An error occurred during a call to API: %d, Error code: 0x%X`
- `0x18039f42a`: `HttpsRequest: An unknown error happened during HTTP request.`
- `0x18039ef16`: `HttpsRequest: The operation initiated by a call to WinHttpGetProxyForUrlEx is complete.`
- `0x18039eeed`: `The operation initiated by a call to WinHttpGetProxyForUrlEx is complete.`

## pseudocode

```c
void __fastcall HttpsRequest::StatusCallback(HttpsRequest *this, unsigned int a2, const wchar_t *a3, DWORD a4)
{
  const wchar_t *v5; // r14
  DWORD v6; // edi
  int v8; // r9d
  const char *v9; // rax
  char *v10; // rdx
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const char *v15; // rax
  __int16 *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // r9d
  void *v21; // rcx
  const char **v22; // rax
  __int64 v23; // rcx
  int v24; // r8d
  int v25; // r9d
  DWORD v26; // eax
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  char *v31; // rdx
  const char **v32; // rax
  int v33; // r9d
  char *v34; // rdx
  DWORD v35; // esi
  int v36; // r8d
  int v37; // r9d
  unsigned int ResponseContentAsync; // eax
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  int v42; // r9d
  void *v43; // rcx
  unsigned int *v44; // rsi
  DWORD v45; // eax
  __int64 v46; // rcx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // r8d
  int v51; // r9d
  DWORD v52; // eax
  __int64 v53; // rcx
  int v54; // ecx
  int v55; // r8d
  int v56; // r9d
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  int v60; // r14d
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  int v67; // ecx
  int v68; // r8d
  int v69; // r9d
  int v70; // ecx
  int v71; // r8d
  int v72; // r9d
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  int v76; // ecx
  int v77; // r8d
  int v78; // r9d
  int v79; // ecx
  int v80; // r8d
  int v81; // r9d
  int v82; // ecx
  int v83; // r8d
  int v84; // r9d
  __int64 v85; // rcx
  __int64 v86; // r9
  int v87; // r8d
  int v88; // r9d
  const char *v89; // rax
  int *v90; // rdx
  int v91; // r9d
  DWORD LastError; // eax
  __int64 v93; // rcx
  const char *v94; // rax
  __int64 *v95; // r10
  __int64 v96; // rcx
  void (*v97)(__int64 *, const wchar_t *, const wchar_t *, ...); // rax
  int v98; // ecx
  int v99; // r8d
  int v100; // r9d
  int v101; // ecx
  int v102; // r8d
  int v103; // r9d
  const char **v104; // [rsp+30h] [rbp-49h]
  const char **v105; // [rsp+38h] [rbp-41h]
  const char **v106; // [rsp+40h] [rbp-39h]
  int v107; // [rsp+60h] [rbp-19h] BYREF
  const char *v108; // [rsp+68h] [rbp-11h] BYREF
  const char *v109; // [rsp+70h] [rbp-9h] BYREF
  const char *v110; // [rsp+78h] [rbp-1h] BYREF
  const char *v111; // [rsp+80h] [rbp+7h] BYREF
  _QWORD v112[9]; // [rsp+88h] [rbp+Fh] BYREF
  DWORD dwBufferLength; // [rsp+E8h] [rbp+6Fh] BYREF

  v5 = a3;
  v6 = a2;
  if ( a2 <= 0x4000 )
  {
    if ( a2 == 0x4000 )
    {
      v23 = *((_QWORD *)this + 8);
      if ( !a3 )
        v5 = L"<none>";
      (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v23 + 40LL))(
        v23,
        L"HttpsRequest",
        L"Request was redirected to URL: %s.",
        v5);
      if ( (unsigned int)dword_1808B5850 <= 4 )
        return;
      v15 = "HttpsRequest: Request was redirected to URL: %s.";
      v16 = &word_18087463E;
      goto LABEL_19;
    }
    if ( a2 <= 0x40 )
    {
      switch ( a2 )
      {
        case 0x40u:
          (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"Waiting for the server to respond to a request.");
          if ( (unsigned int)dword_1808B5850 <= 4 )
            return;
          v9 = "HttpsRequest: Waiting for the server to respond to a request.";
          v10 = (char *)qword_180874710;
          goto LABEL_46;
        case 1u:
          v19 = *((_QWORD *)this + 8);
          if ( !a3 )
            v5 = L"<none>";
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v19 + 40LL))(
            v19,
            L"HttpsRequest",
            L"Looking up the IP address of a server name. Server name: %s",
            v5);
          if ( (unsigned int)dword_1808B5850 <= 4 )
            return;
          v15 = "HttpsRequest: Looking up the IP address of a server name. Server name: %s";
          v16 = &word_180874106;
          break;
        case 2u:
          v18 = *((_QWORD *)this + 8);
          if ( !a3 )
            v5 = L"<none>";
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v18 + 40LL))(
            v18,
            L"HttpsRequest",
            L"Successfully found the IP address of the server. Server IP address = %s",
            v5);
          if ( (unsigned int)dword_1808B5850 <= 4 )
            return;
          v15 = "HttpsRequest: Successfully found the IP address of the server. Server IP address = %s";
          v16 = (__int16 *)&byte_1808745E7;
          break;
        case 4u:
          v17 = *((_QWORD *)this + 8);
          if ( !a3 )
            v5 = L"<none>";
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v17 + 40LL))(
            v17,
            L"HttpsRequest",
            L"Connecting to the server. Server IP address = %s",
            v5);
          if ( (unsigned int)dword_1808B5850 <= 4 )
            return;
          v15 = "HttpsRequest: Connecting to the server. Server IP address = %s";
          v16 = &word_180874A56;
          break;
        case 8u:
          v11 = *((_QWORD *)this + 8);
          if ( !a3 )
            v5 = L"<none>";
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v11 + 40LL))(
            v11,
            L"HttpsRequest",
            L"Successfully connected to the server. Server IP address = %s",
            v5);
          if ( (unsigned int)dword_1808B5850 <= 4 )
            return;
          v15 = "HttpsRequest: Successfully connected to the server. Server IP address = %s";
          v16 = (__int16 *)&byte_1808749FF;
          break;
        case 0x10u:
          (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"Sending the information request to the server.");
          if ( (unsigned int)dword_1808B5850 <= 4 )
            return;
          v9 = "HttpsRequest: Sending the information request to the server.";
          v10 = byte_18087403D;
          goto LABEL_46;
        case 0x20u:
          (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"Successfully sent the information request to the server.");
          if ( (unsigned int)dword_1808B5850 <= 4 )
            return;
          v9 = "HttpsRequest: Successfully sent the information request to the server.";
          v10 = byte_1808740E5;
          goto LABEL_46;
        default:
LABEL_133:
          (*(void (**)(_QWORD, const wchar_t *, const wchar_t *, ...))(**((_QWORD **)this + 8) + 40LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"StatusCallback is called with internetStatus = %d",
            a2);
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            v89 = "HttpsRequest: StatusCallback is called with internetStatus = %d";
            v90 = &dword_180873D24;
LABEL_125:
            v112[0] = v89;
            dwBufferLength = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1808B5850,
              (_DWORD)v90,
              v87,
              v88,
              (__int64)v112,
              (__int64)&dwBufferLength);
            return;
          }
          return;
      }
LABEL_19:
      v108 = v15;
      v109 = (const char *)v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v12,
        (_DWORD)v16,
        v13,
        v14,
        (__int64)&v108,
        (__int64)&v109);
      return;
    }
    switch ( a2 )
    {
      case 0x80u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"Successfully received a response from the server.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v9 = "HttpsRequest: Successfully received a response from the server.";
          v10 = &byte_18087407F;
LABEL_46:
          v109 = v9;
          v22 = &v109;
LABEL_47:
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (_DWORD)v10,
            0,
            v8,
            (__int64)v22);
          return;
        }
        return;
      case 0x100u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"Closing the connection to the server.");
        if ( (unsigned int)dword_1808B5850 <= 4 )
          return;
        v9 = "HttpsRequest: Closing the connection to the server.";
        v10 = (char *)word_18087490A;
        goto LABEL_46;
      case 0x200u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"Successfully closed the connection to the server.");
        if ( (unsigned int)dword_1808B5850 <= 4 )
          return;
        v9 = "HttpsRequest: Successfully closed the connection to the server.";
        v10 = (char *)&dword_1808749AC;
        goto LABEL_46;
      case 0x400u:
        return;
    }
    if ( a2 != 2048 )
      goto LABEL_133;
    (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
      *((_QWORD *)this + 8),
      L"HttpsRequest",
      L"The request handle is closed.");
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v109 = "HttpsRequest: The request handle is closed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)word_180874752,
        0,
        v20,
        (__int64)&v109);
    }
    v21 = (void *)*((_QWORD *)this + 11);
LABEL_175:
    SetEvent(v21);
    return;
  }
  if ( a2 > 0x100000 )
  {
    switch ( a2 )
    {
      case 0x200000u:
        if ( !a3 )
        {
          *((_DWORD *)this + 24) = 13;
          (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"An unknown error happened during HTTP request.",
            2147942413LL);
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            dwBufferLength = 632;
            v110 = "HttpsRequest: An unknown error happened during HTTP request.";
            v112[0] = "StatusCallback";
            v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
            LODWORD(v109) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v101,
              (unsigned int)&dword_180874424,
              v102,
              v103,
              (__int64)&v110,
              (__int64)&v109,
              (__int64)&v111,
              (__int64)&dwBufferLength,
              (__int64)v112);
          }
          goto LABEL_174;
        }
        v95 = (__int64 *)*((_QWORD *)this + 8);
        *((_DWORD *)this + 24) = *((_DWORD *)a3 + 2);
        v96 = *v95;
        switch ( *(_QWORD *)a3 )
        {
          case 1LL:
            (*(void (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *))(v96 + 48))(
              v95,
              L"HttpsRequest",
              L"An error occurred during a call to WinHttpReceiveResponse.");
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_174;
            v31 = &byte_18087469F;
            dwBufferLength = *((_DWORD *)this + 24);
            v94 = "HttpsRequest: An error occurred during a call to WinHttpReceiveResponse. Error code: 0x%X";
            LODWORD(v109) = 590;
            break;
          case 2LL:
            (*(void (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *))(v96 + 48))(
              v95,
              L"HttpsRequest",
              L"An error occurred during a call to WinHttpQueryDataAvailable.");
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_174;
            v31 = byte_180874315;
            dwBufferLength = *((_DWORD *)this + 24);
            v94 = "HttpsRequest: An error occurred during a call to WinHttpQueryDataAvailable. Error code: 0x%X";
            LODWORD(v109) = 595;
            break;
          case 3LL:
            (*(void (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *))(v96 + 48))(
              v95,
              L"HttpsRequest",
              L"An error occurred during a call to WinHttpReadData.");
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_174;
            v31 = byte_180874365;
            dwBufferLength = *((_DWORD *)this + 24);
            v94 = "HttpsRequest: An error occurred during a call to WinHttpReadData. Error code: 0x%X";
            LODWORD(v109) = 600;
            break;
          case 4LL:
            (*(void (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *))(v96 + 48))(
              v95,
              L"HttpsRequest",
              L"An error occurred during a call to WinHttpWriteData.");
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_174;
            v31 = byte_180874275;
            dwBufferLength = *((_DWORD *)this + 24);
            v94 = "HttpsRequest: An error occurred during a call to WinHttpWriteData. Error code: 0x%X";
            LODWORD(v109) = 605;
            break;
          case 5LL:
            (*(void (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *))(v96 + 48))(
              v95,
              L"HttpsRequest",
              L"An error occurred during a call to WinHttpSendRequest.");
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_174;
            v31 = byte_1808742C5;
            dwBufferLength = *((_DWORD *)this + 24);
            v94 = "HttpsRequest: An error occurred during a call to WinHttpSendRequest. Error code: 0x%X";
            LODWORD(v109) = 610;
            break;
          case 6LL:
            (*(void (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *))(v96 + 48))(
              v95,
              L"HttpsRequest",
              L"An error occurred during a call to WinHttpGetProxyForUrlEx.");
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_174;
            v31 = byte_180874469;
            dwBufferLength = *((_DWORD *)this + 24);
            v94 = "HttpsRequest: An error occurred during a call to WinHttpGetProxyForUrlEx. Error code: 0x%X";
            LODWORD(v109) = 615;
            break;
          default:
            v97 = *(void (**)(__int64 *, const wchar_t *, const wchar_t *, ...))(v96 + 48);
            if ( *(_QWORD *)a3 != 7 )
            {
              v97(v95, L"HttpsRequest", L"An error occurred during a call to API: %d");
              if ( (unsigned int)dword_1808B5850 > 2 )
              {
                dwBufferLength = *((_DWORD *)this + 24);
                LODWORD(v109) = *(_DWORD *)v5;
                v112[0] = "StatusCallback";
                v110 = "HttpsRequest: An error occurred during a call to API: %d, Error code: 0x%X";
                LODWORD(v108) = 624;
                v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
                v107 = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v98,
                  (unsigned int)byte_1808743B5,
                  v99,
                  v100,
                  (__int64)&v110,
                  (__int64)&v107,
                  (__int64)&v111,
                  (__int64)&v108,
                  (__int64)v112,
                  (__int64)&v109,
                  (__int64)&dwBufferLength);
              }
              goto LABEL_174;
            }
            v97(v95, L"HttpsRequest", L"An error occurred trying to get proxy settings.");
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_174;
            v31 = byte_1808744B9;
            dwBufferLength = *((_DWORD *)this + 24);
            v94 = "HttpsRequest: An error occurred trying to get proxy settings. Error code: 0x%X";
            LODWORD(v109) = 620;
            break;
        }
        break;
      case 0x400000u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"The request was sent successfully. Trying to obtain response.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v112[0] = "HttpsRequest: The request was sent successfully. Trying to obtain response.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)&word_18087405E,
            0,
            v91,
            (__int64)v112);
        }
        if ( WinHttpReceiveResponse(*((HINTERNET *)this + 9), 0) )
          return;
        LastError = GetLastError();
        v93 = *((_QWORD *)this + 8);
        *((_DWORD *)this + 24) = LastError;
        (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v93 + 48LL))(
          v93,
          L"HttpsRequest",
          L"WinHttpReceiveResponse() failed.");
        if ( (unsigned int)dword_1808B5850 <= 2 )
          goto LABEL_174;
        v31 = (char *)&dword_180873FCC;
        dwBufferLength = *((_DWORD *)this + 24);
        v94 = "HttpsRequest: WinHttpReceiveResponse() failed. Error code: 0x%X";
        LODWORD(v109) = 733;
        break;
      case 0x1000000u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"The operation initiated by a call to WinHttpGetProxyForUrlEx is complete.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v112[0] = "HttpsRequest: The operation initiated by a call to WinHttpGetProxyForUrlEx is complete.";
          v10 = byte_180873D55;
          v22 = (const char **)v112;
          goto LABEL_47;
        }
        return;
      case 0x2000000u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"The connection was successfully closed via a call to WinHttpWebSocketClose.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v112[0] = "HttpsRequest: The connection was successfully closed via a call to WinHttpWebSocketClose.";
          v10 = (char *)&word_180873D76;
          v22 = (const char **)v112;
          goto LABEL_47;
        }
        return;
      case 0x4000000u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"The connection was successfully shut down via a call to WinHttpWebSocketShutdown.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v112[0] = "HttpsRequest: The connection was successfully shut down via a call to WinHttpWebSocketShutdown.";
          v10 = byte_180873D03;
          v22 = (const char **)v112;
          goto LABEL_47;
        }
        return;
      default:
        goto LABEL_133;
    }
    v110 = v94;
    v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
    v112[0] = "StatusCallback";
    v106 = (const char **)v112;
    v105 = &v109;
    v104 = &v111;
    v32 = &v110;
LABEL_171:
    LODWORD(v108) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v28,
      (_DWORD)v31,
      v29,
      v30,
      (__int64)v32,
      (__int64)&v108,
      (__int64)v104,
      (__int64)v105,
      (__int64)v106,
      (__int64)&dwBufferLength);
    goto LABEL_174;
  }
  if ( a2 == 0x100000 )
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
      *((_QWORD *)this + 8),
      L"HttpsRequest",
      L"Data was successfully written to the server.");
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v112[0] = "HttpsRequest: Data was successfully written to the server.";
      v10 = (char *)&dword_18087401C;
      v22 = (const char **)v112;
      goto LABEL_47;
    }
    return;
  }
  if ( a2 != 0x8000 )
  {
    switch ( a2 )
    {
      case 0x10000u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"One or more errors were encountered while retrieving a Secure Sockets Layer (SSL) certificate from the server.",
          2147500037LL);
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v112[0] = "StatusCallback";
          v110 = "HttpsRequest: One or more errors were encountered while retrieving a Secure Sockets Layer (SSL) certifi"
                 "cate from the server.";
          dwBufferLength = 664;
          v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
          LODWORD(v109) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v57,
            (unsigned int)qword_1808740A0,
            v58,
            v59,
            (__int64)&v110,
            (__int64)&v109,
            (__int64)&v111,
            (__int64)&dwBufferLength,
            (__int64)v112);
        }
        if ( v5 )
        {
          v60 = *(_DWORD *)v5;
          if ( (v60 & 1) != 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"HttpsRequest",
              L"Revocation check failed.",
              2147500037LL);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v112[0] = "StatusCallback";
              v110 = "HttpsRequest: Revocation check failed.";
              dwBufferLength = 674;
              v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
              LODWORD(v109) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v61,
                (unsigned int)byte_1808741EB,
                v62,
                v63,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v111,
                (__int64)&dwBufferLength,
                (__int64)v112);
            }
          }
          if ( (v60 & 2) != 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"HttpsRequest",
              L"The server certificate is invalid.",
              2147500037LL);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v112[0] = "StatusCallback";
              v110 = "HttpsRequest: The server certificate is invalid.";
              dwBufferLength = 679;
              v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
              LODWORD(v109) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v64,
                (unsigned int)qword_180874230,
                v65,
                v66,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v111,
                (__int64)&dwBufferLength,
                (__int64)v112);
            }
          }
          if ( (v60 & 4) != 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"HttpsRequest",
              L"The server certificate is revoked.",
              2147500037LL);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v112[0] = "StatusCallback";
              v110 = "HttpsRequest: The server certificate is revoked.";
              dwBufferLength = 684;
              v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
              LODWORD(v109) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v67,
                (unsigned int)byte_180874161,
                v68,
                v69,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v111,
                (__int64)&dwBufferLength,
                (__int64)v112);
            }
          }
          if ( (v60 & 8) != 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"HttpsRequest",
              L"The server certificate was issued by an unknown CA.",
              2147500037LL);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v112[0] = "StatusCallback";
              v110 = "HttpsRequest: The server certificate was issued by an unknown CA.";
              dwBufferLength = 689;
              v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
              LODWORD(v109) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v70,
                (unsigned int)&word_1808741A6,
                v71,
                v72,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v111,
                (__int64)&dwBufferLength,
                (__int64)v112);
            }
          }
          if ( (v60 & 0x10) != 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"HttpsRequest",
              L"The subject name in the server certificate does not match the specified name.",
              2147500037LL);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v112[0] = "StatusCallback";
              v110 = "HttpsRequest: The subject name in the server certificate does not match the specified name.";
              dwBufferLength = 694;
              v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
              LODWORD(v109) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v73,
                (unsigned int)word_180873F42,
                v74,
                v75,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v111,
                (__int64)&dwBufferLength,
                (__int64)v112);
            }
          }
          if ( (v60 & 0x20) != 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"HttpsRequest",
              L"The server certificate is expired or not yet valid.",
              2147500037LL);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v112[0] = "StatusCallback";
              v110 = "HttpsRequest: The server certificate is expired or not yet valid.";
              dwBufferLength = 699;
              v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
              LODWORD(v109) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v76,
                (unsigned int)&byte_180873F87,
                v77,
                v78,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v111,
                (__int64)&dwBufferLength,
                (__int64)v112);
            }
          }
          if ( v60 < 0 )
          {
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              L"HttpsRequest",
              L"An internal SChannel error has occured. Please, collect SChannel logs.",
              2147500037LL);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v112[0] = "StatusCallback";
              v110 = "HttpsRequest: An internal SChannel error has occured. Please, collect SChannel logs.";
              dwBufferLength = 704;
              v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
              LODWORD(v109) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v79,
                (unsigned int)qword_180873EB8,
                v80,
                v81,
                (__int64)&v110,
                (__int64)&v109,
                (__int64)&v111,
                (__int64)&dwBufferLength,
                (__int64)v112);
            }
          }
          HttpsRequest::LogServerCertificateInfo(this);
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)this + 8) + 48LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"Unknown error occured.",
            2147500037LL);
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            v112[0] = "StatusCallback";
            v110 = "HttpsRequest: Unknown error occured.";
            dwBufferLength = 712;
            v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
            LODWORD(v109) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v82,
              (unsigned int)byte_180873EFD,
              v83,
              v84,
              (__int64)&v110,
              (__int64)&v109,
              (__int64)&v111,
              (__int64)&dwBufferLength,
              (__int64)v112);
          }
        }
        return;
      case 0x20000u:
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"The response header is received.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v111 = "HttpsRequest: The response header is received.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)qword_180874850,
            0,
            v42,
            (__int64)&v111);
        }
        v43 = (void *)*((_QWORD *)this + 9);
        v44 = (unsigned int *)((char *)this + 120);
        dwBufferLength = 4;
        if ( WinHttpQueryHeaders(v43, 0x20000013u, 0, (char *)this + 120, &dwBufferLength, 0) )
        {
          (*(void (**)(_QWORD, const wchar_t *, const wchar_t *, ...))(**((_QWORD **)this + 8) + 40LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"The response HTTP status: %d.",
            *v44);
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            LODWORD(v109) = *v44;
            v112[0] = "HttpsRequest: The response HTTP status: %d.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1808B5850,
              (unsigned int)byte_1808747C3,
              v50,
              v51,
              (__int64)v112,
              (__int64)&v109);
          }
          if ( WinHttpQueryDataAvailable(*((HINTERNET *)this + 9), 0) )
            return;
          v52 = GetLastError();
          v53 = *((_QWORD *)this + 8);
          *((_DWORD *)this + 24) = v52;
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v53 + 48LL))(
            v53,
            L"HttpsRequest",
            L"WinHttpQueryDataAvailable failed.");
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            LODWORD(v109) = *((_DWORD *)this + 24);
            v112[0] = "StatusCallback";
            v110 = "HttpsRequest: WinHttpQueryDataAvailable failed. Error code: 0x%X";
            LODWORD(v108) = 504;
            v111 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
            v107 = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v54,
              (unsigned int)qword_180874800,
              v55,
              v56,
              (__int64)&v110,
              (__int64)&v107,
              (__int64)&v111,
              (__int64)&v108,
              (__int64)v112,
              (__int64)&v109);
          }
        }
        else
        {
          v45 = GetLastError();
          v46 = *((_QWORD *)this + 8);
          *((_DWORD *)this + 24) = v45;
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v46 + 48LL))(
            v46,
            L"HttpsRequest",
            L"WinHttpQueryHeaders failed.");
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            LODWORD(v108) = *((_DWORD *)this + 24);
            v111 = "StatusCallback";
            v112[0] = "HttpsRequest: WinHttpQueryHeaders failed. Error code: 0x%X";
            v107 = 489;
            v110 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
            LODWORD(v109) = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v47,
              (unsigned int)byte_180874871,
              v48,
              v49,
              (__int64)v112,
              (__int64)&v109,
              (__int64)&v110,
              (__int64)&v107,
              (__int64)&v111,
              (__int64)&v108);
          }
        }
        break;
      case 0x40000u:
        if ( a3 )
          v35 = *(_DWORD *)a3;
        else
          v35 = 0;
        (*(void (**)(_QWORD, const wchar_t *, const wchar_t *, ...))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"Data is available to be retrieved. %d bytes available.",
          v35);
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          dwBufferLength = v35;
          v111 = "HttpsRequest: Data is available to be retrieved. %d bytes available.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)byte_1808749CD,
            v36,
            v37,
            (__int64)&v111,
            (__int64)&dwBufferLength);
        }
        if ( v35 )
        {
          ResponseContentAsync = HttpsRequest::ReadResponseContentAsync(this, v35);
          *((_DWORD *)this + 24) = ResponseContentAsync;
          if ( !ResponseContentAsync )
            return;
          (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 48LL))(
            *((_QWORD *)this + 8),
            L"HttpsRequest",
            L"ReadResponseContentAsync failed.");
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            dwBufferLength = *((_DWORD *)this + 24);
            v111 = "StatusCallback";
            v109 = "HttpsRequest: ReadResponseContentAsync failed. Error code: 0x%X";
            LODWORD(v108) = 447;
            v110 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
            v107 = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v39,
              (unsigned int)byte_180874773,
              v40,
              v41,
              (__int64)&v109,
              (__int64)&v107,
              (__int64)&v110,
              (__int64)&v108,
              (__int64)&v111,
              (__int64)&dwBufferLength);
          }
          break;
        }
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"No more response content data to read. Completing the request.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v34 = byte_180874731;
          goto LABEL_69;
        }
        break;
      case 0x80000u:
        (*(void (**)(_QWORD, const wchar_t *, const wchar_t *, ...))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"Data was successfully read from the server. %d bytes were read.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          dwBufferLength = a4;
          v109 = "HttpsRequest: Data was successfully read from the server. %d bytes were read.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)byte_180874509,
            v24,
            v25,
            (__int64)&v109,
            (__int64)&dwBufferLength);
        }
        *((_DWORD *)this + 35) += a4;
        if ( a4 )
        {
          if ( WinHttpQueryDataAvailable(*((HINTERNET *)this + 9), 0) )
            return;
          v26 = GetLastError();
          v27 = *((_QWORD *)this + 8);
          *((_DWORD *)this + 24) = v26;
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v27 + 48LL))(
            v27,
            L"HttpsRequest",
            L"WinHttpQueryDataAvailable failed.");
          if ( (unsigned int)dword_1808B5850 <= 2 )
            break;
          dwBufferLength = *((_DWORD *)this + 24);
          v109 = "StatusCallback";
          v111 = "HttpsRequest: WinHttpQueryDataAvailable failed. Error code: 0x%X";
          v31 = byte_180874545;
          v107 = 550;
          v106 = &v109;
          v105 = (const char **)&v107;
          v104 = &v110;
          v32 = &v111;
          v110 = "onecore\\termsrv\\rdp\\win\\security\\simplehttpsclient.cpp";
          goto LABEL_171;
        }
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 8) + 40LL))(
          *((_QWORD *)this + 8),
          L"HttpsRequest",
          L"No more response content data to read. Completing the request.");
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v34 = &byte_1808746EF;
LABEL_69:
          v111 = "HttpsRequest: No more response content data to read. Completing the request.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (_DWORD)v34,
            0,
            v33,
            (__int64)&v111);
        }
        break;
      default:
        goto LABEL_133;
    }
LABEL_174:
    v21 = (void *)*((_QWORD *)this + 10);
    goto LABEL_175;
  }
  v85 = *((_QWORD *)this + 8);
  v6 = 0;
  if ( a3 )
    v86 = *(unsigned int *)a3;
  else
    v86 = 0;
  (*(void (**)(__int64, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)v85 + 40LL))(
    v85,
    L"HttpsRequest",
    L"Received an intermediate (100 level) status code message from the server. HTTP Status =  %d.",
    v86);
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    if ( v5 )
      v6 = *(_DWORD *)v5;
    v89 = "HttpsRequest: Received an intermediate (100 level) status code message from the server. HTTP Status =  %d.";
    v90 = (int *)byte_180874595;
    goto LABEL_125;
  }
}

```

## disassembly

```asm
0x18039ddec  push    rbp
0x18039ddee  push    rbx
0x18039ddef  push    rsi
0x18039ddf0  push    rdi
0x18039ddf1  push    r12
0x18039ddf3  push    r13
0x18039ddf5  push    r14
0x18039ddf7  push    r15
0x18039ddf9  lea     rbp, [rsp-1Fh]
0x18039ddfe  sub     rsp, 98h
0x18039de05  mov     eax, 4000h
0x18039de0a  mov     esi, r9d
0x18039de0d  mov     r14, r8
0x18039de10  mov     edi, edx
0x18039de12  mov     rbx, rcx
0x18039de15  mov     r13d, 4
0x18039de1b  cmp     edx, eax
0x18039de1d  ja      loc_18039E247
0x18039de23  jz      loc_18039E1F6
0x18039de29  cmp     edx, 40h ; '@'
0x18039de2c  ja      loc_18039E08C
0x18039de32  jz      loc_18039E04C
0x18039de38  mov     eax, edx
0x18039de3a  sub     eax, 1
0x18039de3d  jz      loc_18039DFFB
0x18039de43  sub     eax, 1
0x18039de46  jz      loc_18039DFAA
0x18039de4c  sub     eax, 2
0x18039de4f  jz      loc_18039DF5C
0x18039de55  sub     eax, r13d
0x18039de58  jz      loc_18039DEEC
0x18039de5e  sub     eax, 8
0x18039de61  jz      short loc_18039DEAC
0x18039de63  cmp     eax, 10h
0x18039de66  jnz     loc_18039EE16
0x18039de6c  mov     rcx, [rcx+40h]
0x18039de70  lea     r8, aSuccessfullySe; "Successfully sent the information reque"...
0x18039de77  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039de7e  mov     rax, [rcx]
0x18039de81  mov     rax, [rax+28h]
0x18039de85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039de8a  mov     eax, cs:dword_1808B5850
0x18039de90  cmp     eax, r13d
0x18039de93  jbe     loc_18039F49D
0x18039de99  lea     rax, aHttpsrequestSu_2; "HttpsRequest: Successfully sent the inf"...
0x18039dea0  lea     rdx, byte_1808740E5
0x18039dea7  jmp     loc_18039E198
0x18039deac  mov     rcx, [rcx+40h]
0x18039deb0  lea     r8, aSendingTheInfo; "Sending the information request to the "...
0x18039deb7  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039debe  mov     rax, [rcx]
0x18039dec1  mov     rax, [rax+28h]
0x18039dec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039deca  mov     eax, cs:dword_1808B5850
0x18039ded0  cmp     eax, r13d
0x18039ded3  jbe     loc_18039F49D
0x18039ded9  lea     rax, aHttpsrequestSe_0; "HttpsRequest: Sending the information r"...
0x18039dee0  lea     rdx, byte_18087403D
0x18039dee7  jmp     loc_18039E198
0x18039deec  mov     rcx, [rcx+40h]
0x18039def0  lea     rax, aNone_1; "<none>"
0x18039def7  test    r14, r14
0x18039defa  lea     r8, aSuccessfullyCo; "Successfully connected to the server. S"...
0x18039df01  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039df08  cmovz   r14, rax
0x18039df0c  mov     rax, [rcx]
0x18039df0f  mov     r9, r14
0x18039df12  mov     rax, [rax+28h]
0x18039df16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039df1b  mov     eax, cs:dword_1808B5850
0x18039df21  cmp     eax, r13d
0x18039df24  jbe     loc_18039F49D
0x18039df2a  lea     rax, aHttpsrequestSu; "HttpsRequest: Successfully connected to"...
0x18039df31  lea     rdx, byte_1808749FF
0x18039df38  mov     [rbp+57h+var_68], rax
0x18039df3c  lea     rax, [rbp+57h+var_60]
0x18039df40  mov     [rsp+0D0h+lpdwIndex], rax
0x18039df45  lea     rax, [rbp+57h+var_68]
0x18039df49  mov     [rsp+0D0h+lpdwBufferLength], rax
0x18039df4e  mov     [rbp+57h+var_60], r14
0x18039df52  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18039df57  jmp     loc_18039F49D
0x18039df5c  mov     rcx, [rcx+40h]
0x18039df60  lea     rax, aNone_1; "<none>"
0x18039df67  test    r14, r14
0x18039df6a  lea     r8, aConnectingToTh; "Connecting to the server. Server IP add"...
0x18039df71  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039df78  cmovz   r14, rax
0x18039df7c  mov     rax, [rcx]
0x18039df7f  mov     r9, r14
0x18039df82  mov     rax, [rax+28h]
0x18039df86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039df8b  mov     eax, cs:dword_1808B5850
0x18039df91  cmp     eax, r13d
0x18039df94  jbe     loc_18039F49D
0x18039df9a  lea     rax, aHttpsrequestCo; "HttpsRequest: Connecting to the server."...
0x18039dfa1  lea     rdx, word_180874A56
0x18039dfa8  jmp     short loc_18039DF38
0x18039dfaa  mov     rcx, [rcx+40h]
0x18039dfae  lea     rax, aNone_1; "<none>"
0x18039dfb5  test    r14, r14
0x18039dfb8  lea     r8, aSuccessfullyFo; "Successfully found the IP address of th"...
0x18039dfbf  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039dfc6  cmovz   r14, rax
0x18039dfca  mov     rax, [rcx]
0x18039dfcd  mov     r9, r14
0x18039dfd0  mov     rax, [rax+28h]
0x18039dfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039dfd9  mov     eax, cs:dword_1808B5850
0x18039dfdf  cmp     eax, r13d
0x18039dfe2  jbe     loc_18039F49D
0x18039dfe8  lea     rax, aHttpsrequestSu_1; "HttpsRequest: Successfully found the IP"...
0x18039dfef  lea     rdx, byte_1808745E7
0x18039dff6  jmp     loc_18039DF38
0x18039dffb  mov     rcx, [rcx+40h]
0x18039dfff  lea     rax, aNone_1; "<none>"
0x18039e006  test    r14, r14
0x18039e009  lea     r8, aLookingUpTheIp; "Looking up the IP address of a server n"...
0x18039e010  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e017  cmovz   r14, rax
0x18039e01b  mov     rax, [rcx]
0x18039e01e  mov     r9, r14
0x18039e021  mov     rax, [rax+28h]
0x18039e025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e02a  mov     eax, cs:dword_1808B5850
0x18039e030  cmp     eax, r13d
0x18039e033  jbe     loc_18039F49D
0x18039e039  lea     rax, aHttpsrequestLo; "HttpsRequest: Looking up the IP address"...
0x18039e040  lea     rdx, word_180874106
0x18039e047  jmp     loc_18039DF38
0x18039e04c  mov     rcx, [rcx+40h]
0x18039e050  lea     r8, aWaitingForTheS; "Waiting for the server to respond to a "...
0x18039e057  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e05e  mov     rax, [rcx]
0x18039e061  mov     rax, [rax+28h]
0x18039e065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e06a  mov     eax, cs:dword_1808B5850
0x18039e070  cmp     eax, r13d
0x18039e073  jbe     loc_18039F49D
0x18039e079  lea     rax, aHttpsrequestWa; "HttpsRequest: Waiting for the server to"...
0x18039e080  lea     rdx, qword_180874710
0x18039e087  jmp     loc_18039E198
0x18039e08c  cmp     edi, 80h
0x18039e092  jz      loc_18039E1B9
0x18039e098  cmp     edi, 100h
0x18039e09e  jz      loc_18039E15D
0x18039e0a4  cmp     edi, 200h
0x18039e0aa  jz      short loc_18039E120
0x18039e0ac  cmp     edi, 400h
0x18039e0b2  jz      loc_18039F49D
0x18039e0b8  cmp     edi, 800h
0x18039e0be  jnz     loc_18039EE16
0x18039e0c4  mov     rcx, [rcx+40h]
0x18039e0c8  lea     r8, aTheRequestHand; "The request handle is closed."
0x18039e0cf  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e0d6  mov     rax, [rcx]
0x18039e0d9  mov     rax, [rax+28h]
0x18039e0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e0e2  mov     eax, cs:dword_1808B5850
0x18039e0e8  cmp     eax, r13d
0x18039e0eb  jbe     short loc_18039E117
0x18039e0ed  lea     rax, aHttpsrequestTh_6; "HttpsRequest: The request handle is clo"...
0x18039e0f4  xor     r8d, r8d
0x18039e0f7  mov     [rbp+57h+var_60], rax
0x18039e0fb  lea     rdx, word_180874752
0x18039e102  lea     rax, [rbp+57h+var_60]
0x18039e106  lea     rcx, dword_1808B5850
0x18039e10d  mov     [rsp+0D0h+lpdwBufferLength], rax
0x18039e112  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18039e117  mov     rcx, [rbx+58h]
0x18039e11b  jmp     loc_18039F497
0x18039e120  mov     rcx, [rcx+40h]
0x18039e124  lea     r8, aSuccessfullyCl; "Successfully closed the connection to t"...
0x18039e12b  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e132  mov     rax, [rcx]
0x18039e135  mov     rax, [rax+28h]
0x18039e139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e13e  mov     eax, cs:dword_1808B5850
0x18039e144  cmp     eax, r13d
0x18039e147  jbe     loc_18039F49D
0x18039e14d  lea     rax, aHttpsrequestSu_0; "HttpsRequest: Successfully closed the c"...
0x18039e154  lea     rdx, dword_1808749AC
0x18039e15b  jmp     short loc_18039E198
0x18039e15d  mov     rcx, [rcx+40h]
0x18039e161  lea     r8, aClosingTheConn; "Closing the connection to the server."
0x18039e168  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e16f  mov     rax, [rcx]
0x18039e172  mov     rax, [rax+28h]
0x18039e176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e17b  mov     eax, cs:dword_1808B5850
0x18039e181  cmp     eax, r13d
0x18039e184  jbe     loc_18039F49D
0x18039e18a  lea     rax, aHttpsrequestCl; "HttpsRequest: Closing the connection to"...
0x18039e191  lea     rdx, word_18087490A
0x18039e198  mov     [rbp+57h+var_60], rax
0x18039e19c  lea     rax, [rbp+57h+var_60]
0x18039e1a0  xor     r8d, r8d
0x18039e1a3  mov     [rsp+0D0h+lpdwBufferLength], rax
0x18039e1a8  lea     rcx, dword_1808B5850
0x18039e1af  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18039e1b4  jmp     loc_18039F49D
0x18039e1b9  mov     rcx, [rcx+40h]
0x18039e1bd  lea     r8, aSuccessfullyRe_0; "Successfully received a response from t"...
0x18039e1c4  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e1cb  mov     rax, [rcx]
0x18039e1ce  mov     rax, [rax+28h]
0x18039e1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e1d7  mov     eax, cs:dword_1808B5850
0x18039e1dd  cmp     eax, r13d
0x18039e1e0  jbe     loc_18039F49D
0x18039e1e6  lea     rax, aHttpsrequestSu_3; "HttpsRequest: Successfully received a r"...
0x18039e1ed  lea     rdx, byte_18087407F
0x18039e1f4  jmp     short loc_18039E198
0x18039e1f6  mov     rcx, [rcx+40h]
0x18039e1fa  lea     rax, aNone_1; "<none>"
0x18039e201  test    r14, r14
0x18039e204  lea     r8, aRequestWasRedi; "Request was redirected to URL: %s."
0x18039e20b  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e212  cmovz   r14, rax
0x18039e216  mov     rax, [rcx]
0x18039e219  mov     r9, r14
0x18039e21c  mov     rax, [rax+28h]
0x18039e220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e225  mov     eax, cs:dword_1808B5850
0x18039e22b  cmp     eax, r13d
0x18039e22e  jbe     loc_18039F49D
0x18039e234  lea     rax, aHttpsrequestRe; "HttpsRequest: Request was redirected to"...
0x18039e23b  lea     rdx, word_18087463E
0x18039e242  jmp     loc_18039DF38
0x18039e247  mov     eax, 100000h
0x18039e24c  cmp     edi, eax
0x18039e24e  ja      loc_18039EDDE
0x18039e254  jz      loc_18039ED96
0x18039e25a  cmp     edi, 8000h
0x18039e260  jz      loc_18039ED1A
0x18039e266  cmp     edi, 10000h
0x18039e26c  jz      loc_18039E80F
0x18039e272  cmp     edi, 20000h
0x18039e278  jz      loc_18039E59A
0x18039e27e  cmp     edi, 40000h
0x18039e284  jz      loc_18039E424
0x18039e28a  cmp     edi, 80000h
0x18039e290  jnz     loc_18039EE16
0x18039e296  mov     rcx, [rcx+40h]
0x18039e29a  lea     r8, aDataWasSuccess_0; "Data was successfully read from the ser"...
0x18039e2a1  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e2a8  mov     rax, [rcx]
0x18039e2ab  mov     rax, [rax+28h]
0x18039e2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e2b4  mov     eax, cs:dword_1808B5850
0x18039e2ba  cmp     eax, r13d
0x18039e2bd  jbe     short loc_18039E2F2
0x18039e2bf  lea     rax, aHttpsrequestDa_1; "HttpsRequest: Data was successfully rea"...
0x18039e2c6  mov     [rbp+57h+dwBufferLength], esi
0x18039e2c9  mov     [rbp+57h+var_60], rax
0x18039e2cd  lea     rdx, byte_180874509
0x18039e2d4  lea     rax, [rbp+57h+dwBufferLength]
0x18039e2d8  mov     [rsp+0D0h+lpdwIndex], rax
0x18039e2dd  lea     rcx, dword_1808B5850
0x18039e2e4  lea     rax, [rbp+57h+var_60]
0x18039e2e8  mov     [rsp+0D0h+lpdwBufferLength], rax
0x18039e2ed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18039e2f2  add     [rbx+8Ch], esi
0x18039e2f8  test    esi, esi
0x18039e2fa  jz      loc_18039E3C8
0x18039e300  mov     rcx, [rbx+48h]; hRequest
0x18039e304  xor     edx, edx; lpdwNumberOfBytesAvailable
0x18039e306  call    cs:__imp_WinHttpQueryDataAvailable
0x18039e30c  test    eax, eax
0x18039e30e  jnz     loc_18039F49D
0x18039e314  call    cs:__imp_GetLastError
0x18039e31a  mov     rcx, [rbx+40h]
0x18039e31e  mov     r9d, eax
0x18039e321  mov     [rbx+60h], eax
0x18039e324  mov     rax, [rcx]
0x18039e327  test    r9d, r9d
0x18039e32a  jle     short loc_18039E337
0x18039e32c  movzx   r9d, r9w
0x18039e330  or      r9d, 80070000h
0x18039e337  mov     rax, [rax+30h]
0x18039e33b  lea     r8, aWinhttpqueryda_0; "WinHttpQueryDataAvailable failed."
0x18039e342  lea     rdx, aHttpsrequest_0; "HttpsRequest"
0x18039e349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039e34e  mov     eax, cs:dword_1808B5850
0x18039e354  cmp     eax, 2
0x18039e357  jbe     loc_18039F493
0x18039e35d  mov     eax, [rbx+60h]
0x18039e360  lea     r15, aStatuscallback; "StatusCallback"
0x18039e367  mov     [rbp+57h+dwBufferLength], eax
0x18039e36a  lea     r12, aOnecoreTermsrv_20; "onecore\\termsrv\\rdp\\win\\security\\s"...
0x18039e371  lea     rax, aHttpsrequestWi_0; "HttpsRequest: WinHttpQueryDataAvailable"...
0x18039e378  mov     [rbp+57h+var_60], r15
0x18039e37c  mov     [rbp+57h+var_50], rax
0x18039e380  lea     rdx, byte_180874545
0x18039e387  lea     rax, [rbp+57h+dwBufferLength]
0x18039e38b  mov     [rbp+57h+var_70], 226h
0x18039e392  mov     [rsp+0D0h+var_88], rax
0x18039e397  lea     rax, [rbp+57h+var_60]
0x18039e39b  mov     [rsp+0D0h+var_90], rax
0x18039e3a0  lea     rax, [rbp+57h+var_70]
  ... truncated ...
```
