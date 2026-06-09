# NcsiHttpGet(_NET_LUID_LH const *,wil::basic_zstring_view<ushort>,wil::basic_zstring_view<ushort>,bool,bool,bool,ulong,_SOCKADDR_INET *,char * *,ulong *,ushort * *,ulong *,ulong *,bool *,bool *,_ActiveProbeType,_WINHTTP_PROXY_INFO *,_WINHTTP_SELECTED_PROXY_CONFIG_INFO *,_WINHTTP_CONNECTION_INFO *)

- ea: `0x180076430`
- end: `0x1800776b4`
- name: `?NcsiHttpGet@@YAKPEBT_NET_LUID_LH@@V?$basic_zstring_view@G@wil@@1_N22KPEAT_SOCKADDR_INET@@PEAPEADPEAKPEAPEAG55PEA_N7W4_ActiveProbeType@@PEAU_WINHTTP_PROXY_INFO@@PEAU_WINHTTP_SELECTED_PROXY_CONFIG_INFO@@PEAU_WINHTTP_CONNECTION_INFO@@@Z`
- size: `4740`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char, bool, unsigned int, __int64, __int64, __int64, __int64, int, __int64, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180037ac4`
- `0x180068518`

## callees

- `0x180001608`
- `0x180007d90`
- `0x180007e20`
- `0x180007f14`
- `0x180007fbc`
- `0x1800080ac`
- `0x1800081a0`
- `0x180008290`
- `0x18000e59c`
- `0x1800150f8`
- `0x180017fbc`
- `0x18001814c`
- `0x180018f9c`
- `0x18002103c`
- `0x1800212c8`
- `0x1800213cc`
- `0x180026790`
- `0x180027d64`
- `0x180028758`
- `0x18002a420`
- `0x18002a574`
- `0x18002aec4`
- `0x180047240`
- `0x180047f78`
- `0x18004f5f0`
- `0x180055860`
- `0x18007607c`
- `0x1800761c8`
- `0x1800762dc`
- `0x180076430`
- `0x1800776bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007720f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007720f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077142`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076efd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076efd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007686b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007687e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076a13`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076a26`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076b54`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076b67`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076c2a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076c3d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076fca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076fdd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007708e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800770a1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077280`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077293`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077345`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077358`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007686b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007687e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076a13`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076a26`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076b54`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076b67`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076c2a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076c3d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076fca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180076fdd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007708e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800770a1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077280`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077293`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077345`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180077358`
- `WINHTTP!WinHttpConnect` at `0x180076d1a`
- `WINHTTP!WinHttpConnect` at `0x180076d1a`
- `WINHTTP!WinHttpOpenRequest` at `0x180076d80`
- `WINHTTP!WinHttpOpenRequest` at `0x180076d80`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180076687`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180076687`
- `WINHTTP!WinHttpSendRequest` at `0x18007710c`
- `WINHTTP!WinHttpSendRequest` at `0x18007710c`
- `WINHTTP!WinHttpOpen` at `0x18007663d`
- `WINHTTP!WinHttpOpen` at `0x18007663d`
- `WINHTTP!WinHttpSetOption` at `0x1800766bc`
- `WINHTTP!WinHttpSetOption` at `0x180076724`
- `WINHTTP!WinHttpSetOption` at `0x1800767c1`
- `WINHTTP!WinHttpSetOption` at `0x180076eef`
- `WINHTTP!WinHttpSetOption` at `0x1800766bc`
- `WINHTTP!WinHttpSetOption` at `0x180076724`
- `WINHTTP!WinHttpSetOption` at `0x1800767c1`
- `WINHTTP!WinHttpSetOption` at `0x180076eef`
- `WINHTTP!WinHttpCloseHandle` at `0x18007688d`
- `WINHTTP!WinHttpCloseHandle` at `0x180076a35`
- `WINHTTP!WinHttpCloseHandle` at `0x180076b76`
- `WINHTTP!WinHttpCloseHandle` at `0x180076c4c`
- `WINHTTP!WinHttpCloseHandle` at `0x180076fa7`
- `WINHTTP!WinHttpCloseHandle` at `0x180076fb6`
- `WINHTTP!WinHttpCloseHandle` at `0x180076fec`
- `WINHTTP!WinHttpCloseHandle` at `0x18007706b`
- `WINHTTP!WinHttpCloseHandle` at `0x18007707a`
- `WINHTTP!WinHttpCloseHandle` at `0x1800770b0`
- `WINHTTP!WinHttpCloseHandle` at `0x18007725d`
- `WINHTTP!WinHttpCloseHandle` at `0x18007726c`
- `WINHTTP!WinHttpCloseHandle` at `0x1800772a2`
- `WINHTTP!WinHttpCloseHandle` at `0x180077322`
- `WINHTTP!WinHttpCloseHandle` at `0x180077331`
- `WINHTTP!WinHttpCloseHandle` at `0x180077367`
- `WINHTTP!WinHttpCloseHandle` at `0x18007688d`
- `WINHTTP!WinHttpCloseHandle` at `0x180076a35`
- `WINHTTP!WinHttpCloseHandle` at `0x180076b76`
- `WINHTTP!WinHttpCloseHandle` at `0x180076c4c`
- `WINHTTP!WinHttpCloseHandle` at `0x180076fa7`
- `WINHTTP!WinHttpCloseHandle` at `0x180076fb6`
- `WINHTTP!WinHttpCloseHandle` at `0x180076fec`
- `WINHTTP!WinHttpCloseHandle` at `0x18007706b`
- `WINHTTP!WinHttpCloseHandle` at `0x18007707a`
- `WINHTTP!WinHttpCloseHandle` at `0x1800770b0`
- `WINHTTP!WinHttpCloseHandle` at `0x18007725d`
- `WINHTTP!WinHttpCloseHandle` at `0x18007726c`
- `WINHTTP!WinHttpCloseHandle` at `0x1800772a2`
- `WINHTTP!WinHttpCloseHandle` at `0x180077322`
- `WINHTTP!WinHttpCloseHandle` at `0x180077331`
- `WINHTTP!WinHttpCloseHandle` at `0x180077367`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180076919`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180076ac3`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180076919`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180076ac3`

## string_xrefs

- `0x180076b03`: `Attempt to consider IE data as a proxy script URL failed`
- `0x180076bea`: `Not enough memory to copy proxy info`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NcsiHttpGet(
        NET_LUID *a1,
        LPCWSTR *a2,
        const size_t *a3,
        bool a4,
        char a5,
        bool a6,
        unsigned int a7,
        SOCKADDR *a,
        const size_t *a9,
        const size_t *a10,
        _QWORD *a11,
        int a12,
        const unsigned __int16 *a13,
        bool *a14,
        bool *a15,
        unsigned int a16,
        _OWORD *a17,
        _OWORD *a18,
        struct _WINHTTP_CONNECTION_INFO *a19)
{
  _OWORD *v21; // rdx
  _OWORD *v22; // rax
  struct _WINHTTP_CONNECTION_INFO *v23; // rcx
  WCHAR *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  wil *v27; // rcx
  __int64 result; // rax
  DWORD v29; // edx
  size_t *v30; // rbx
  const char *v31; // r9
  const char *v32; // r9
  const char *v33; // r9
  int v34; // ecx
  const char *v35; // r9
  int v36; // eax
  const char *v37; // r9
  __int64 v38; // rcx
  int v39; // edi
  __int64 v40; // r8
  __int64 v41; // r9
  DWORD LastError; // edi
  __int64 v43; // r8
  __int64 v44; // r9
  NcsiConfigData *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // r8
  const char *v48; // r9
  DWORD v49; // eax
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r9
  WCHAR *v55; // rax
  void *v56; // rdi
  const char *v57; // r9
  void *v58; // rax
  const char *v59; // r9
  int v60; // eax
  __int64 v61; // r8
  __int64 v62; // r9
  DWORD v63; // eax
  __int64 v64; // r8
  __int64 v65; // r9
  DWORD v66; // esi
  const char *v67; // r9
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // rax
  int v73; // eax
  bool v74; // bl
  size_t *v75; // rdi
  HINTERNET v76; // rax
  __int64 v77; // rax
  __int64 v78; // r8
  __int64 v79; // r9
  unsigned int v80; // ebx
  int dwFlags; // [rsp+20h] [rbp-718h]
  int dwFlagsa; // [rsp+20h] [rbp-718h]
  bool v83; // [rsp+60h] [rbp-6D8h] BYREF
  char v84[7]; // [rsp+61h] [rbp-6D7h] BYREF
  const char *v85; // [rsp+68h] [rbp-6D0h] BYREF
  void *v86; // [rsp+70h] [rbp-6C8h] BYREF
  const char *lpszProxy; // [rsp+78h] [rbp-6C0h] BYREF
  __int128 v88; // [rsp+80h] [rbp-6B8h] BYREF
  LPCWSTR *lpszProxyBypass; // [rsp+90h] [rbp-6A8h] BYREF
  size_t *p_CriticalSection; // [rsp+98h] [rbp-6A0h] BYREF
  unsigned __int16 *v91; // [rsp+A0h] [rbp-698h] BYREF
  bool *v92; // [rsp+A8h] [rbp-690h] BYREF
  const size_t *v93[3]; // [rsp+B0h] [rbp-688h] BYREF
  char v94; // [rsp+C8h] [rbp-670h]
  char *v95; // [rsp+D0h] [rbp-668h]
  _QWORD *v96; // [rsp+D8h] [rbp-660h]
  char v97; // [rsp+E0h] [rbp-658h]
  unsigned int *v98; // [rsp+E8h] [rbp-650h]
  HINTERNET *p_hInternet; // [rsp+F0h] [rbp-648h]
  _OWORD **v100; // [rsp+F8h] [rbp-640h]
  _OWORD **v101; // [rsp+100h] [rbp-638h]
  struct _WINHTTP_CONNECTION_INFO **p_lpBuffer; // [rsp+108h] [rbp-630h]
  char v103; // [rsp+110h] [rbp-628h]
  WINHTTP_PROXY_INFO hMem; // [rsp+118h] [rbp-620h] BYREF
  _OWORD *v105; // [rsp+130h] [rbp-608h] BYREF
  struct _WINHTTP_CONNECTION_INFO *lpBuffer; // [rsp+140h] [rbp-5F8h] BYREF
  _OWORD *v107; // [rsp+150h] [rbp-5E8h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+158h] [rbp-5E0h] BYREF
  _QWORD *Buffer; // [rsp+178h] [rbp-5C0h] BYREF
  char v110; // [rsp+180h] [rbp-5B8h] BYREF
  HINTERNET hInternet; // [rsp+188h] [rbp-5B0h] BYREF
  int v112[4]; // [rsp+190h] [rbp-5A8h] BYREF
  _QWORD v113[3]; // [rsp+1A0h] [rbp-598h] BYREF
  char v114[8]; // [rsp+1B8h] [rbp-580h] BYREF
  char v115[8]; // [rsp+1C0h] [rbp-578h] BYREF
  bool v116; // [rsp+1C8h] [rbp-570h]
  char v117[8]; // [rsp+1D0h] [rbp-568h] BYREF
  _OWORD v118[8]; // [rsp+1D8h] [rbp-560h]
  unsigned int v119; // [rsp+258h] [rbp-4E0h]
  __int64 v120; // [rsp+260h] [rbp-4D8h]
  int v121; // [rsp+26Ch] [rbp-4CCh]
  const unsigned __int16 *v122; // [rsp+288h] [rbp-4B0h] BYREF
  _BYTE *v123; // [rsp+290h] [rbp-4A8h]
  _BYTE *v124; // [rsp+298h] [rbp-4A0h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+2A0h] [rbp-498h] BYREF
  int v126; // [rsp+2D0h] [rbp-468h] BYREF
  char v127[524]; // [rsp+2D4h] [rbp-464h] BYREF
  WCHAR cwszUrl[264]; // [rsp+4E0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+738h] [rbp+0h]

  v83 = a4;
  lpszProxyBypass = (LPCWSTR *)a3;
  v93[0] = a9;
  p_CriticalSection = (size_t *)a10;
  v91 = (unsigned __int16 *)a13;
  v92 = a14;
  v21 = a17;
  v107 = a17;
  v105 = a18;
  lpBuffer = a19;
  *a17 = 0;
  *((_QWORD *)v21 + 2) = 0;
  v22 = v105;
  *v105 = 0;
  v22[1] = 0;
  v22[2] = 0;
  *((_QWORD *)v22 + 6) = 0;
  memset_0(cwszUrl, 0, 0x108u);
  v23 = lpBuffer;
  v24 = cwszUrl;
  v25 = 2;
  do
  {
    *(_OWORD *)v23 = *(_OWORD *)v24;
    *((_OWORD *)v23 + 1) = *((_OWORD *)v24 + 1);
    *((_OWORD *)v23 + 2) = *((_OWORD *)v24 + 2);
    *((_OWORD *)v23 + 3) = *((_OWORD *)v24 + 3);
    *((_OWORD *)v23 + 4) = *((_OWORD *)v24 + 4);
    *((_OWORD *)v23 + 5) = *((_OWORD *)v24 + 5);
    *((_OWORD *)v23 + 6) = *((_OWORD *)v24 + 6);
    *((_OWORD *)v23 + 7) = *((_OWORD *)v24 + 7);
    v23 = (struct _WINHTTP_CONNECTION_INFO *)((char *)v23 + 128);
    v24 += 64;
    --v25;
  }
  while ( v25 );
  try
  {
    *(_QWORD *)v23 = *(_QWORD *)v24;
    HttpGetRequest::HttpGetRequest((HttpGetRequest *)v113);
    if ( a10 )
      *(_DWORD *)a10 = 0;
    if ( a9 )
      *a9 = 0;
    if ( a11 )
      *a11 = 0;
    if ( !a2[1] )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v26);
      HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
      return 87;
    }
    v84[0] = 0;
    v110 = 0;
    v95 = &v110;
    v96 = v113;
    v97 = 1;
    v29 = 1;
    if ( a16 - 4 > 1 )
      v29 = 4;
    v30 = (size_t *)WinHttpOpen(c_userAgent, v29, 0, 0, 0x10000000u);
    v93[1] = v30;
    if ( !v30 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1F0,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
        v31);
    v113[0] = v30;
    if ( WinHttpSetStatusCallback(v30, HttpRequestStatusCallback, 0x97E0C0Bu, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
        v32);
    Buffer = v113;
    if ( !WinHttpSetOption(v30, 0x2Du, &Buffer, 8u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
        v33);
    v110 = 1;
    memset(&hMem, 0, sizeof(hMem));
    v93[2] = (const size_t *)&hMem;
    v94 = 1;
    v34 = a16;
    if ( a16 - 1 <= 1 )
    {
      if ( !WinHttpSetOption(v30, 0xB5u, 0, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x211,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
          v35);
      v34 = a16;
    }
    v88 = *(_OWORD *)a2;
    v36 = SetOptionsOnWinhttpSessionHandle(v30, a, a1, a5, v34);
    if ( v36 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
        (const char *)(unsigned int)v36,
        dwFlags);
    if ( a16 - 4 <= 1 )
    {
      v112[0] = 1;
      if ( !WinHttpSetOption(v30, 0x89u, v112, 4u) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x21D,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
          v37);
      memset_0(cwszUrl, 0, 0x208u);
      v39 = StringCchPrintfW(cwszUrl, 0x104u, L"http://%s", *a2);
      if ( v39 < 0 )
      {
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          LODWORD(v86) = v39;
          v85 = "Error when trying to prepare data for proxy identification";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v38,
            (int)&dword_18008DADC,
            v40,
            v41,
            (const unsigned __int16 **)&v85,
            (__int64)&v86);
        }
        if ( (v39 & 0x1FFF0000) == 0x70000 )
          v39 = (unsigned __int16)v39;
        if ( hMem.lpszProxy )
          GlobalFree(hMem.lpszProxy);
        if ( hMem.lpszProxyBypass )
          GlobalFree(hMem.lpszProxyBypass);
        WinHttpCloseHandle(v30);
        if ( !v110 )
          goto LABEL_34;
        goto LABEL_33;
      }
      memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
      if ( !byte_18009B420 )
        goto LABEL_41;
      LastError = 0;
      pAutoProxyOptions.dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      if ( !WinHttpGetProxyForUrl(v30, cwszUrl, &pAutoProxyOptions, &hMem) )
        LastError = GetLastError();
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        LODWORD(v86) = LastError;
        lpszProxy = (const char *)hMem.lpszProxy;
        LODWORD(v85) = hMem.dwAccessType;
        *(_QWORD *)&v88 = "autoProxyDetection";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          hMem.dwAccessType,
          (int)&word_18008D99E,
          v43,
          v44,
          (const unsigned __int16 **)&v88,
          (__int64)&v85,
          (const size_t **)&lpszProxy,
          (__int64)&v86);
      }
      if ( LastError )
      {
LABEL_41:
        v126 = 0;
        memset_0(v127, 0, 0x208u);
        if ( !NcsiConfigData::GetManualProxies(v45, (struct NCSI_MANUAL_PROXIES *)&v126) )
        {
          if ( (unsigned int)dword_18009A048 > 5 )
          {
            *(_QWORD *)&v88 = "GetManualProxiesFailed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v46,
              (int)&dword_18008D964,
              v47,
              (__int64)v48,
              (const unsigned __int16 **)&v88);
          }
          if ( hMem.lpszProxy )
            GlobalFree(hMem.lpszProxy);
          if ( hMem.lpszProxyBypass )
            GlobalFree(hMem.lpszProxyBypass);
          WinHttpCloseHandle(v30);
          if ( v110 )
            _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
              v115,
              0xFFFFFFFFLL);
          HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
          return 1168;
        }
        if ( !*(_WORD *)v127 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v46);
        if ( v126 == 2 )
        {
          *(_QWORD *)&pAutoProxyOptions.dwFlags = 4194306;
          pAutoProxyOptions.lpszAutoConfigUrl = (LPCWSTR)v127;
          if ( !WinHttpGetProxyForUrl(v30, cwszUrl, &pAutoProxyOptions, &hMem) )
          {
            v49 = GetLastError();
            v39 = v49;
            if ( (unsigned int)dword_18009A048 > 5 )
            {
              *(_QWORD *)&v88 = pAutoProxyOptions.lpszAutoConfigUrl;
              LODWORD(v85) = pAutoProxyOptions.dwFlags;
              LODWORD(v86) = v49;
              lpszProxy = "Attempt to consider IE data as a proxy script URL failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                pAutoProxyOptions.dwFlags,
                (int)&byte_18008D9FF,
                v50,
                v51,
                (const unsigned __int16 **)&lpszProxy,
                (__int64)&v86,
                (__int64)&v85,
                (const size_t **)&v88);
            }
            if ( hMem.lpszProxy )
              GlobalFree(hMem.lpszProxy);
            if ( hMem.lpszProxyBypass )
              GlobalFree(hMem.lpszProxyBypass);
            WinHttpCloseHandle(v30);
            if ( !v110 )
              goto LABEL_34;
LABEL_33:
            _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
              v115,
              0xFFFFFFFFLL);
LABEL_34:
            HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
            return (unsigned int)v39;
          }
        }
        else if ( v126 == 1 )
        {
          v85 = 0;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v85,
            v127,
            v47,
            v48);
          v55 = (WCHAR *)v85;
          if ( !v85 )
          {
            if ( (unsigned int)dword_18009A048 > 5 )
            {
              *(_QWORD *)&v88 = "Not enough memory to copy proxy info";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v52,
                (int)byte_18008D865,
                v53,
                v54,
                (const unsigned __int16 **)&v88);
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
            if ( hMem.lpszProxy )
              GlobalFree(hMem.lpszProxy);
            if ( hMem.lpszProxyBypass )
              GlobalFree(hMem.lpszProxyBypass);
            WinHttpCloseHandle(v30);
            if ( v110 )
              _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                v115,
                0xFFFFFFFFLL);
            HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
            return 8;
          }
          v85 = 0;
          hMem.lpszProxy = v55;
          hMem.dwAccessType = 3;
          hMem.lpszProxyBypass = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
        }
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          *(_QWORD *)&v88 = hMem.lpszProxy;
          LODWORD(v85) = hMem.dwAccessType;
          lpszProxy = "manualProxyDetection";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v46,
            (int)&unk_18008D908,
            v47,
            (__int64)v48,
            (const unsigned __int16 **)&lpszProxy,
            (__int64)&v85,
            (const size_t **)&v88);
        }
      }
    }
    v56 = WinHttpConnect(v30, *a2, 0, 0);
    v86 = v56;
    if ( !v56 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x287,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
        v57);
    v113[1] = v56;
    hInternet = 0;
    v58 = WinHttpOpenRequest(v56, 0, *lpszProxyBypass, 0, 0, 0, (!v83 << 8) | 4u);
    hInternet = v58;
    if ( !v58 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x290,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
        v59);
    v98 = &a16;
    p_hInternet = &hInternet;
    v100 = &v107;
    v101 = &v105;
    p_lpBuffer = &lpBuffer;
    v103 = 1;
    v113[2] = v58;
    v60 = SetOptionsOnRequestHandle(v58, a6, a7);
    if ( v60 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x29C,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
        (const char *)(unsigned int)v60,
        dwFlagsa);
    if ( a16 - 4 > 1 )
    {
LABEL_105:
      if ( !WinHttpSendRequest(hInternet, 0, 0xFFFFFFFF, 0, 0, 0, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\ncsihttplib\\lib\\ncsihttp.cpp",
          v67);
      if ( (unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                              v114,
                              a7) )
      {
        GetWinHttpProxyInfo(a16, hInternet, v107, v105);
        GetWinHttpConnectionInfo(hInternet, lpBuffer);
        if ( hInternet )
          WinHttpCloseHandle(hInternet);
        WinHttpCloseHandle(v56);
        if ( hMem.lpszProxy )
          GlobalFree(hMem.lpszProxy);
        if ( hMem.lpszProxyBypass )
          GlobalFree(hMem.lpszProxyBypass);
        WinHttpCloseHandle(v30);
        if ( v110 )
          _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
            v115,
            0xFFFFFFFFLL);
        if ( a15 )
          *a15 = v116;
        if ( a11 )
        {
          v72 = v120;
          v120 = 0;
          *a11 = v72;
        }
        v73 = v121;
        if ( v91 )
          *(_DWORD *)v91 = v121;
        if ( !v84[0] && a )
        {
          *a = (SOCKADDR)v118[0];
          *(SOCKADDR *)&a->sa_data[10] = *(SOCKADDR *)((char *)v118 + 12);
        }
        v74 = (unsigned int)(v73 - 300) <= 0x63;
        if ( v92 )
          *v92 = v74;
        v75 = (size_t *)v93[0];
        if ( v93[0] )
        {
          v83 = 0;
          if ( v123 == v124 )
            std::vector<unsigned char>::_Emplace_reallocate<char>(&v122, v123, &v83);
          else
            *v123++ = 0;
          hInternet = 0;
          wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&hInternet);
          v76 = hInternet;
          hInternet = 0;
          *v75 = (size_t)v76;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hInternet);
        }
        if ( p_CriticalSection )
          *(_DWORD *)p_CriticalSection = (_DWORD)v123 - (_DWORD)v122;
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          v77 = ctl::ctSockaddr::writeAddress(v117, &pAutoProxyOptions);
          if ( *(_QWORD *)(v77 + 24) > 7u )
            v77 = *(_QWORD *)v77;
          p_CriticalSection = (size_t *)v77;
          v93[0] = (const size_t *)ActiveProbeTypeToString(a16);
          LODWORD(v85) = v119;
          v92 = (bool *)(v123 - (_BYTE *)v122);
          v91 = (unsigned __int16 *)v122;
          v83 = v74;
          LODWORD(v86) = v121;
          v84[0] = v116;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (__int64)v122,
            (int)&unk_18008D700,
            v78,
            v79,
            (__int64)v84,
            (__int64)&v86,
            (__int64)&v83,
            (const unsigned __int16 **)&v91,
            (__int64)&v92,
            (__int64)&v85,
            v93,
            (const size_t **)&p_CriticalSection);
          std::wstring::_Tidy_deallocate(&pAutoProxyOptions);
        }
        v80 = v119;
        if ( (v119 & 0x1FFF0000) == 0x70000 )
          v80 = (unsigned __int16)v119;
        HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
        return v80;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        p_CriticalSection = (size_t *)&CriticalSection;
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          v68 = ctl::ctSockaddr::writeAddress(v117, &pAutoProxyOptions);
          if ( *(_QWORD *)(v68 + 24) > 7u )
            v68 = *(_QWORD *)v68;
          lpszProxyBypass = (LPCWSTR *)v68;
          v83 = v116;
          LODWORD(v85) = a7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
            v69,
            (unsigned __int8 *)byte_18008D7A9,
            v70,
            v71,
            (__int64)&v85,
            (__int64)&v83,
            (const size_t **)&lpszProxyBypass);
          std::wstring::_Tidy_deallocate(&pAutoProxyOptions);
        }
        if ( a15 )
          *a15 = v116;
        if ( !v84[0] && a )
        {
          *a = (SOCKADDR)v118[0];
          *(SOCKADDR *)&a->sa_data[10] = *(SOCKADDR *)((char *)v118 + 12);
        }
        LeaveCriticalSection(&CriticalSection);
        GetWinHttpProxyInfo(a16, hInternet, v107, v105);
        GetWinHttpConnectionInfo(hInternet, lpBuffer);
        if ( hInternet )
          WinHttpCloseHandle(hInternet);
        WinHttpCloseHandle(v56);
        if ( hMem.lpszProxy )
          GlobalFree(hMem.lpszProxy);
        if ( hMem.lpszProxyBypass )
          GlobalFree(hMem.lpszProxyBypass);
        WinHttpCloseHandle(v30);
        if ( v110 )
          _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
            v115,
            0xFFFFFFFFLL);
        HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
        return 1460;
      }
    }
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      lpszProxyBypass = (LPCWSTR *)hMem.lpszProxyBypass;
      *(_QWORD *)&v88 = hMem.lpszProxy;
      LODWORD(v85) = hMem.dwAccessType;
      lpszProxy = "Set proxy option";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)retaddr,
        (int)&dword_18008D8A4,
        v61,
        v62,
        (const unsigned __int16 **)&lpszProxy,
        (__int64)&v85,
        (const size_t **)&v88,
        (const size_t **)&lpszProxyBypass);
    }
    if ( hMem.lpszProxy )
    {
      if ( !WinHttpSetOption(hInternet, 0x26u, &hMem, 0x18u) )
      {
        v63 = GetLastError();
        v66 = v63;
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          LODWORD(v85) = v63;
          lpszProxyBypass = (LPCWSTR *)hMem.lpszProxy;
          *(_QWORD *)&v88 = "Set proxy option";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)hMem.lpszProxy,
            (int)word_18008D812,
            v64,
            v65,
            (const unsigned __int16 **)&v88,
            (const size_t **)&lpszProxyBypass,
            (__int64)&v85);
        }
        GetWinHttpProxyInfo(a16, hInternet, v107, v105);
        GetWinHttpConnectionInfo(hInternet, lpBuffer);
        if ( hInternet )
          WinHttpCloseHandle(hInternet);
        WinHttpCloseHandle(v56);
        if ( hMem.lpszProxy )
          GlobalFree(hMem.lpszProxy);
        if ( hMem.lpszProxyBypass )
          GlobalFree(hMem.lpszProxyBypass);
        WinHttpCloseHandle(v30);
        if ( v110 )
          _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
            v115,
            0xFFFFFFFFLL);
        HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
        return v66;
      }
      goto LABEL_105;
    }
    GetWinHttpProxyInfo(a16, hInternet, v107, v105);
    GetWinHttpConnectionInfo(hInternet, lpBuffer);
    if ( hInternet )
      WinHttpCloseHandle(hInternet);
    WinHttpCloseHandle(v56);
    if ( hMem.lpszProxy )
      GlobalFree(hMem.lpszProxy);
    if ( hMem.lpszProxyBypass )
      GlobalFree(hMem.lpszProxyBypass);
    WinHttpCloseHandle(v30);
    if ( v110 )
      _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
        v115,
        0xFFFFFFFFLL);
    HttpGetRequest::~HttpGetRequest((HttpGetRequest *)v113);
    result = 13;
  }
  catch ( ... )
  {
    LODWORD(result) = wil::ResultFromCaughtException(v27);
    if ( (result & 0x1FFF0000) == 0x70000 )
      LODWORD(result) = (unsigned __int16)result;
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x180076430  mov     r11, rsp
0x180076433  push    rbx
0x180076434  push    rsi
0x180076435  push    rdi
0x180076436  push    r12
0x180076438  push    r13
0x18007643a  push    r14
0x18007643c  push    r15
0x18007643e  sub     rsp, 700h
0x180076445  mov     rax, cs:__security_cookie
0x18007644c  xor     rax, rsp
0x18007644f  mov     [rsp+738h+var_48], rax
0x180076457  mov     [rsp+738h+var_6D8], r9b
0x18007645c  mov     [rsp+738h+var_6A8], r8
0x180076464  mov     r14, rdx
0x180076467  mov     r15, rcx
0x18007646a  mov     rsi, [rsp+738h+a]
0x180076472  mov     rdi, [rsp+738h+arg_40]
0x18007647a  mov     [rsp+738h+var_688], rdi
0x180076482  mov     rbx, [rsp+738h+arg_48]
0x18007648a  mov     [rsp+738h+var_6A0], rbx
0x180076492  mov     r13, [rsp+738h+arg_50]
0x18007649a  mov     rax, [rsp+738h+arg_60]
0x1800764a2  mov     [rsp+738h+var_698], rax
0x1800764aa  mov     rcx, [rsp+738h+arg_68]
0x1800764b2  mov     [rsp+738h+var_690], rcx
0x1800764ba  mov     r12, [rsp+738h+arg_70]
0x1800764c2  mov     rdx, [rsp+738h+arg_80]
0x1800764ca  mov     [r11-5E8h], rdx
0x1800764d1  mov     rax, [rsp+738h+arg_88]
0x1800764d9  mov     [r11-608h], rax
0x1800764e0  mov     rax, [rsp+738h+arg_90]
0x1800764e8  mov     [r11-5F8h], rax
0x1800764ef  xorps   xmm0, xmm0
0x1800764f2  xor     eax, eax
0x1800764f4  movups  xmmword ptr [rdx], xmm0
0x1800764f7  mov     [rdx+10h], rax
0x1800764fb  xorps   xmm1, xmm1
0x1800764fe  xor     ecx, ecx
0x180076500  mov     rax, [r11-608h]
0x180076507  movups  xmmword ptr [rax], xmm1
0x18007650a  movups  xmmword ptr [rax+10h], xmm1
0x18007650e  movups  xmmword ptr [rax+20h], xmm1
0x180076512  mov     [rax+30h], rcx
0x180076516  xor     edx, edx; Val
0x180076518  mov     r8d, 108h; Size
0x18007651e  lea     rcx, [r11-258h]; void *
0x180076525  call    memset_0
0x18007652a  mov     rcx, [rsp+738h+lpBuffer]
0x180076532  lea     rax, [rsp+738h+cwszUrl]
0x18007653a  mov     edx, 2
0x18007653f  lea     r8d, [rdx+7Eh]
0x180076543  movups  xmm0, xmmword ptr [rax]
0x180076546  movups  xmmword ptr [rcx], xmm0
0x180076549  movups  xmm1, xmmword ptr [rax+10h]
0x18007654d  movups  xmmword ptr [rcx+10h], xmm1
0x180076551  movups  xmm0, xmmword ptr [rax+20h]
0x180076555  movups  xmmword ptr [rcx+20h], xmm0
0x180076559  movups  xmm1, xmmword ptr [rax+30h]
0x18007655d  movups  xmmword ptr [rcx+30h], xmm1
0x180076561  movups  xmm0, xmmword ptr [rax+40h]
0x180076565  movups  xmmword ptr [rcx+40h], xmm0
0x180076569  movups  xmm1, xmmword ptr [rax+50h]
0x18007656d  movups  xmmword ptr [rcx+50h], xmm1
0x180076571  movups  xmm0, xmmword ptr [rax+60h]
0x180076575  movups  xmmword ptr [rcx+60h], xmm0
0x180076579  movups  xmm1, xmmword ptr [rax+70h]
0x18007657d  movups  xmmword ptr [rcx+70h], xmm1
0x180076581  add     rcx, r8
0x180076584  add     rax, r8
0x180076587  sub     rdx, 1
0x18007658b  jnz     short loc_180076543
0x18007658d  mov     rax, [rax]
0x180076590  mov     [rcx], rax
0x180076593  lea     rcx, [rsp+738h+var_598]; this
0x18007659b  call    ??0HttpGetRequest@@QEAA@XZ; HttpGetRequest::HttpGetRequest(void)
0x1800765a0  nop
0x1800765a1  xor     eax, eax
0x1800765a3  test    rbx, rbx
0x1800765a6  jz      short loc_1800765AA
0x1800765a8  mov     [rbx], eax
0x1800765aa  test    rdi, rdi
0x1800765ad  jz      short loc_1800765B2
0x1800765af  mov     [rdi], rax
0x1800765b2  test    r13, r13
0x1800765b5  jz      short loc_1800765BB
0x1800765b7  mov     [r13+0], rax
0x1800765bb  cmp     [r14+8], rax
0x1800765bf  jnz     short loc_1800765DE
0x1800765c1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800765c6  nop
0x1800765c7  lea     rcx, [rsp+738h+var_598]; this
0x1800765cf  call    ??1HttpGetRequest@@QEAA@XZ; HttpGetRequest::~HttpGetRequest(void)
0x1800765d4  mov     eax, 57h ; 'W'
0x1800765d9  jmp     loc_1800775D8
0x1800765de  mov     [rsp+738h+var_6D7], al
0x1800765e2  mov     [rsp+738h+var_5B8], al
0x1800765e9  lea     rax, [rsp+738h+var_5B8]
0x1800765f1  mov     [rsp+738h+var_668], rax
0x1800765f9  lea     rax, [rsp+738h+var_598]
0x180076601  mov     [rsp+738h+var_660], rax
0x180076609  mov     [rsp+738h+var_658], 1
0x180076611  mov     eax, [rsp+738h+arg_78]
0x180076618  add     eax, 0FFFFFFFCh
0x18007661b  mov     edx, 1
0x180076620  lea     ecx, [rdx+3]
0x180076623  cmp     eax, edx
0x180076625  cmova   edx, ecx; dwAccessType
0x180076628  mov     [rsp+738h+dwFlags], 10000000h; dwFlags
0x180076630  xor     r9d, r9d; pszProxyBypassW
0x180076633  xor     r8d, r8d; pszProxyW
0x180076636  mov     rcx, cs:?c_userAgent@@3V?$basic_zstring_view@G@wil@@B; pszAgentW
0x18007663d  call    cs:__imp_WinHttpOpen
0x180076643  mov     rbx, rax
0x180076646  mov     [rsp+738h+var_680], rax
0x18007664e  test    rax, rax
0x180076651  setz    al
0x180076654  mov     rcx, [rsp+738h]; this
0x18007665c  test    al, al
0x18007665e  jnz     loc_1800775FB
0x180076664  mov     [rsp+738h+var_598], rbx
0x18007666c  mov     rdi, [rsp+738h]
0x180076674  xor     r9d, r9d; dwReserved
0x180076677  mov     r8d, 97E0C0Bh; dwNotificationFlags
0x18007667d  lea     rdx, ?HttpRequestStatusCallback@@YAXPEAX_KK0K@Z; lpfnInternetCallback
0x180076684  mov     rcx, rbx; hInternet
0x180076687  call    cs:__imp_WinHttpSetStatusCallback
0x18007668d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180076691  jz      loc_18007760C
0x180076697  lea     rax, [rsp+738h+var_598]
0x18007669f  mov     [rsp+738h+Buffer], rax
0x1800766a7  mov     r9d, 8; dwBufferLength
0x1800766ad  lea     r8, [rsp+738h+Buffer]; lpBuffer
0x1800766b5  lea     edx, [r9+25h]; dwOption
0x1800766b9  mov     rcx, rbx; hInternet
0x1800766bc  call    cs:__imp_WinHttpSetOption
0x1800766c2  mov     rcx, [rsp+738h]; this
0x1800766ca  test    eax, eax
0x1800766cc  jz      loc_180077620
0x1800766d2  mov     [rsp+738h+var_5B8], 1
0x1800766da  xorps   xmm0, xmm0
0x1800766dd  xor     eax, eax
0x1800766df  movups  xmmword ptr [rsp+738h+hMem], xmm0
0x1800766e7  mov     [rsp+738h+var_610], rax
0x1800766ef  lea     rax, [rsp+738h+hMem]
0x1800766f7  mov     [rsp+738h+var_678], rax
0x1800766ff  mov     [rsp+738h+var_670], 1
0x180076707  mov     ecx, [rsp+738h+arg_78]
0x18007670e  lea     eax, [rcx-1]
0x180076711  cmp     eax, 1
0x180076714  ja      short loc_180076741
0x180076716  xor     r9d, r9d; dwBufferLength
0x180076719  xor     r8d, r8d; lpBuffer
0x18007671c  mov     edx, 0B5h; dwOption
0x180076721  mov     rcx, rbx; hInternet
0x180076724  call    cs:__imp_WinHttpSetOption
0x18007672a  mov     rcx, [rsp+738h]; this
0x180076732  test    eax, eax
0x180076734  jz      loc_180077632
0x18007673a  mov     ecx, [rsp+738h+arg_78]
0x180076741  movups  xmm0, xmmword ptr [r14]
0x180076745  movdqu  [rsp+738h+var_6B8], xmm0
0x18007674e  mov     [rsp+738h+var_708], ecx; int
0x180076752  mov     al, [rsp+738h+arg_20]
0x180076759  mov     byte ptr [rsp+738h+ppwszAcceptTypes], al; char
0x18007675d  mov     qword ptr [rsp+738h+dwFlags], r15; int
0x180076762  lea     r9, [rsp+738h+var_6D7]
0x180076767  lea     r8, [rsp+738h+var_6B8]
0x18007676f  mov     rdx, rsi; a
0x180076772  mov     rcx, rbx; hInternet
0x180076775  call    ?SetOptionsOnWinhttpSessionHandle@@YAJPEAXPEAT_SOCKADDR_INET@@V?$basic_zstring_view@G@wil@@PEA_NPEBT_NET_LUID_LH@@_NW4_ActiveProbeType@@@Z; SetOptionsOnWinhttpSessionHandle(void *,_SOCKADDR_INET *,wil::basic_zstring_view<ushort>,bool *,_NET_LUID_LH const *,bool,_ActiveProbeType)
0x18007677a  mov     rcx, [rsp+738h]; this
0x180076782  xor     r15d, r15d
0x180076785  test    eax, eax
0x180076787  js      loc_180077643
0x18007678d  mov     eax, [rsp+738h+arg_78]
0x180076794  add     eax, 0FFFFFFFCh
0x180076797  cmp     eax, 1
0x18007679a  ja      loc_180076D0E
0x1800767a0  mov     [rsp+738h+var_5A8], 1
0x1800767ab  mov     r9d, 4; dwBufferLength
0x1800767b1  lea     r8, [rsp+738h+var_5A8]; lpBuffer
0x1800767b9  mov     edx, 89h; dwOption
0x1800767be  mov     rcx, rbx; hInternet
0x1800767c1  call    cs:__imp_WinHttpSetOption
0x1800767c7  mov     rcx, [rsp+738h]; this
0x1800767cf  test    eax, eax
0x1800767d1  jz      loc_180077657
0x1800767d7  xor     edx, edx; Val
0x1800767d9  mov     r8d, 208h; Size
0x1800767df  lea     rcx, [rsp+738h+cwszUrl]; void *
0x1800767e7  call    memset_0
0x1800767ec  mov     r9, [r14]
0x1800767ef  lea     r8, aHttpS; "http://%s"
0x1800767f6  mov     edx, 104h; unsigned __int64
0x1800767fb  lea     rcx, [rsp+738h+cwszUrl]; unsigned __int16 *
0x180076803  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076808  mov     edi, eax
0x18007680a  test    eax, eax
0x18007680c  jns     loc_1800768C3
0x180076812  mov     eax, cs:dword_18009A048
0x180076818  cmp     eax, 5
0x18007681b  jbe     short loc_18007684D
0x18007681d  mov     dword ptr [rsp+738h+var_6C8], edi
0x180076821  lea     rax, aErrorWhenTryin; "Error when trying to prepare data for p"...
0x180076828  mov     [rsp+738h+var_6D0], rax
0x18007682d  lea     rax, [rsp+738h+var_6C8]
0x180076832  mov     [rsp+738h+ppwszAcceptTypes], rax
0x180076837  lea     rax, [rsp+738h+var_6D0]
0x18007683c  mov     qword ptr [rsp+738h+dwFlags], rax
0x180076841  lea     rdx, dword_18008DADC
0x180076848  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007684d  mov     eax, edi
0x18007684f  and     eax, 1FFF0000h
0x180076854  cmp     eax, 70000h
0x180076859  jnz     short loc_18007685E
0x18007685b  movzx   edi, di
0x18007685e  mov     rcx, [rsp+738h+hMem+8]; hMem
0x180076866  test    rcx, rcx
0x180076869  jz      short loc_180076871
0x18007686b  call    cs:__imp_GlobalFree
0x180076871  mov     rcx, [rsp+738h+var_610]; hMem
0x180076879  test    rcx, rcx
0x18007687c  jz      short loc_180076885
0x18007687e  call    cs:__imp_GlobalFree
0x180076884  nop
0x180076885  test    rbx, rbx
0x180076888  jz      short loc_180076894
0x18007688a  mov     rcx, rbx; hInternet
0x18007688d  call    cs:__imp_WinHttpCloseHandle
0x180076893  nop
0x180076894  cmp     [rsp+738h+var_5B8], r15b
0x18007689c  jz      short loc_1800768AF
0x18007689e  or      edx, 0FFFFFFFFh
0x1800768a1  lea     rcx, [rsp+738h+var_578]
0x1800768a9  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x1800768ae  nop
0x1800768af  lea     rcx, [rsp+738h+var_598]; this
0x1800768b7  call    ??1HttpGetRequest@@QEAA@XZ; HttpGetRequest::~HttpGetRequest(void)
0x1800768bc  mov     eax, edi
0x1800768be  jmp     loc_1800775D8
0x1800768c3  xorps   xmm0, xmm0
0x1800768c6  movups  xmmword ptr [rsp+738h+pAutoProxyOptions.dwFlags], xmm0
0x1800768ce  movups  xmmword ptr [rsp+738h+pAutoProxyOptions.lpvReserved], xmm0
0x1800768d6  mov     al, cs:byte_18009B420
0x1800768dc  nop
0x1800768dd  test    al, al
0x1800768df  jz      loc_1800769A0
0x1800768e5  mov     edi, r15d
0x1800768e8  mov     [rsp+738h+pAutoProxyOptions.dwFlags], 1
0x1800768f3  mov     [rsp+738h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800768fe  lea     r9, [rsp+738h+hMem]; pProxyInfo
0x180076906  lea     r8, [rsp+738h+pAutoProxyOptions]; pAutoProxyOptions
0x18007690e  lea     rdx, [rsp+738h+cwszUrl]; lpcwszUrl
0x180076916  mov     rcx, rbx; hSession
0x180076919  call    cs:__imp_WinHttpGetProxyForUrl
0x18007691f  test    eax, eax
0x180076921  jnz     short loc_18007692B
0x180076923  call    cs:__imp_GetLastError
0x180076929  mov     edi, eax
0x18007692b  mov     ecx, cs:dword_18009A048
0x180076931  cmp     ecx, 5
0x180076934  jbe     short loc_180076998
0x180076936  mov     dword ptr [rsp+738h+var_6C8], edi
0x18007693a  mov     rcx, [rsp+738h+hMem+8]
0x180076942  mov     [rsp+738h+var_6C0], rcx
0x180076947  mov     ecx, dword ptr [rsp+738h+hMem]
0x18007694e  mov     dword ptr [rsp+738h+var_6D0], ecx
0x180076952  lea     rax, aAutoproxydetec; "autoProxyDetection"
0x180076959  mov     qword ptr [rsp+738h+var_6B8], rax
0x180076961  lea     rax, [rsp+738h+var_6C8]
0x180076966  mov     [rsp+738h+var_700], rax
0x18007696b  lea     rax, [rsp+738h+var_6C0]
0x180076970  mov     qword ptr [rsp+738h+var_708], rax
0x180076975  lea     rax, [rsp+738h+var_6D0]
0x18007697a  mov     [rsp+738h+ppwszAcceptTypes], rax
0x18007697f  lea     rax, [rsp+738h+var_6B8]
0x180076987  mov     qword ptr [rsp+738h+dwFlags], rax
0x18007698c  lea     rdx, word_18008D99E
0x180076993  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180076998  test    edi, edi
0x18007699a  jz      loc_180076D0E
0x1800769a0  mov     [rsp+738h+var_468], r15d
0x1800769a8  xor     edx, edx; Val
0x1800769aa  mov     r8d, 208h; Size
0x1800769b0  lea     rcx, [rsp+738h+var_464]; void *
0x1800769b8  call    memset_0
0x1800769bd  lea     rdx, [rsp+738h+var_468]; struct NCSI_MANUAL_PROXIES *
0x1800769c5  call    ?GetManualProxies@NcsiConfigData@@QEAA_NPEAUNCSI_MANUAL_PROXIES@@@Z; NcsiConfigData::GetManualProxies(NCSI_MANUAL_PROXIES *)
0x1800769ca  test    al, al
0x1800769cc  jnz     loc_180076A6E
0x1800769d2  mov     eax, cs:dword_18009A048
0x1800769d8  cmp     eax, 5
0x1800769db  jbe     short loc_180076A06
0x1800769dd  lea     rax, aGetmanualproxi; "GetManualProxiesFailed"
0x1800769e4  mov     qword ptr [rsp+738h+var_6B8], rax
0x1800769ec  lea     rax, [rsp+738h+var_6B8]
0x1800769f4  mov     qword ptr [rsp+738h+dwFlags], rax
0x1800769f9  lea     rdx, dword_18008D964
0x180076a00  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
  ... truncated ...
```
