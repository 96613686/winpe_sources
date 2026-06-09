# _HttpsProbes::PerformHttpsGetRequest_::_3_::_lambda_1_::operator()

- ea: `0x1801272d8`
- end: `0x180127b58`
- name: `_HttpsProbes::PerformHttpsGetRequest_::_3_::_lambda_1_::operator()`
- size: `2176`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180128c80`

## callees

- `0x1800050d8`
- `0x180005378`
- `0x1800055f8`
- `0x18000572c`
- `0x180009990`
- `0x180015608`
- `0x18001b8e8`
- `0x180049ba8`
- `0x18005fb58`
- `0x1800801ac`
- `0x18009a2c4`
- `0x1800a88a0`
- `0x1800baf04`
- `0x180126950`
- `0x1801270fc`
- `0x180127228`
- `0x1801272d8`
- `0x180128a58`
- `0x180128d7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012766d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801277b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012766d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801277b7`
- `WINHTTP!WinHttpSetOption` at `0x180127471`
- `WINHTTP!WinHttpSetOption` at `0x180127471`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180127441`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180127441`
- `WINHTTP!WinHttpConnect` at `0x1801274ca`
- `WINHTTP!WinHttpConnect` at `0x1801274ca`
- `WINHTTP!WinHttpOpenRequest` at `0x180127516`
- `WINHTTP!WinHttpOpenRequest` at `0x180127516`
- `WINHTTP!WinHttpSendRequest` at `0x18012777a`
- `WINHTTP!WinHttpSendRequest` at `0x18012777a`
- `WINHTTP!WinHttpOpen` at `0x18012740c`
- `WINHTTP!WinHttpOpen` at `0x18012740c`

## string_xrefs

- `0x180127a7c`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127a99`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127ab9`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127ad9`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127af6`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127b13`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127b27`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127b45`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180127b07`: `WinHttpOpenRequest`
- `0x180127a70`: `WinHttpOpen`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall HttpsProbes::PerformHttpsGetRequest_::_3_::_lambda_1_::operator()(_QWORD *a1)
{
  const wchar_t *v3; // r12
  struct _RTL_CRITICAL_SECTION *v4; // rax
  void *v5; // rax
  const char *v6; // r9
  void *v7; // r13
  const char *v8; // r9
  const char *v9; // r9
  int v10; // eax
  const WCHAR **v11; // rsi
  const WCHAR *v12; // rdx
  WCHAR *v13; // rax
  const char *v14; // r9
  const WCHAR **v15; // r14
  const WCHAR *v16; // r8
  void *v17; // rax
  const char *v18; // r9
  int v19; // eax
  const char *v20; // r9
  void *v21; // r13
  void *v22; // rdx
  __int64 v23; // r11
  const char *v24; // r9
  const wchar_t *v25; // rax
  const WCHAR *v26; // rax
  WCHAR *v27; // rax
  int dwFlags; // [rsp+20h] [rbp-138h]
  int dwFlagsa; // [rsp+20h] [rbp-138h]
  _DWORD *v30; // [rsp+68h] [rbp-F0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-D8h] BYREF
  HINTERNET hRequest; // [rsp+88h] [rbp-D0h]
  const WCHAR *v33; // [rsp+90h] [rbp-C8h]
  __int64 v34; // [rsp+98h] [rbp-C0h]
  __int64 v35; // [rsp+A0h] [rbp-B8h]
  const wchar_t *v36; // [rsp+A8h] [rbp-B0h]
  const wchar_t *v37; // [rsp+B0h] [rbp-A8h]
  const wchar_t *v38; // [rsp+B8h] [rbp-A0h]
  _QWORD *v39; // [rsp+C0h] [rbp-98h]
  __int64 Buffer; // [rsp+C8h] [rbp-90h] BYREF
  __int128 v41; // [rsp+D0h] [rbp-88h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-78h] BYREF
  _BYTE v43[32]; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v44; // [rsp+108h] [rbp-50h]
  __int64 v45; // [rsp+110h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v39 = a1;
  v37 = (const wchar_t *)a1;
  if ( (unsigned int)dword_1801BD288 <= 4 )
  {
    v3 = L"Global";
  }
  else
  {
    v3 = L"Global";
    v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 7);
    if ( a1[10] > 7u )
      v4 = (struct _RTL_CRITICAL_SECTION *)v4->DebugInfo;
    lpCriticalSection = v4;
    v36 = (const wchar_t *)*((unsigned int *)a1 + 4);
    Buffer = a1[1];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
      a1,
      word_18019952A);
  }
  v5 = WinHttpOpen(L"Microsoft NetworkListManager", 1u, 0, 0, 0x10000000u);
  try
  {
    v7 = v5;
    if ( !v5 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
        v6);
    if ( WinHttpSetStatusCallback(v5, HttpsProbes::HttpsRequestStatusCallback, 0x630000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
        v8);
    Buffer = *a1;
    if ( !WinHttpSetOption(v7, 0x2Du, &Buffer, 8u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
        v9);
    v30 = a1 + 11;
    v10 = SetOptionsOnWinhttpSessionHandle(v7);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
        (const char *)(unsigned int)v10,
        dwFlags);
    v11 = (const WCHAR **)(a1 + 3);
    if ( a1[6] <= 7u )
      v12 = (const WCHAR *)(a1 + 3);
    else
      v12 = *v11;
    v13 = (WCHAR *)WinHttpConnect(v7, v12, 0, 0);
    v33 = v13;
    if ( !v13 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x16B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
        v14);
    v15 = (const WCHAR **)(a1 + 7);
    if ( a1[10] <= 7u )
      v16 = (const WCHAR *)(a1 + 7);
    else
      v16 = *v15;
    v17 = WinHttpOpenRequest(v13, 0, v16, 0, 0, 0, 0x800104u);
    hRequest = v17;
    if ( !v17 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x177,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
        v18);
    v19 = SetOptionsOnRequestHandle(v17);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
        (const char *)(unsigned int)v19,
        dwFlagsa);
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, *a1);
    if ( a1[12] >= *(_QWORD *)(*a1 + 112LL) )
    {
      v41 = 0u;
      v42 = 0;
      std::wstring::wstring(v43);
      v44 = 0;
      v45 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v41,
        v7);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        (char *)&v41 + 8,
        v33);
      v21 = hRequest;
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v42,
        hRequest);
      std::wstring::operator=(v43, a1 + 3);
      LODWORD(v45) = *v30;
      v44 = a1[12];
      if ( *(_QWORD *)(*a1 + 48LL) == *(_QWORD *)(*a1 + 56LL) )
      {
        std::vector<HttpsProbes::HttpsRequest>::_Emplace_reallocate<HttpsProbes::HttpsRequest>(
          *a1 + 40LL,
          *(_QWORD *)(*a1 + 48LL),
          &v41);
      }
      else
      {
        HttpsProbes::HttpsRequest::HttpsRequest(*(_QWORD *)(*a1 + 48LL), &v41);
        *(_QWORD *)(v23 + 48) += 72LL;
      }
      wil::details::ResetEvent(*(wil::details **)(*a1 + 88LL), v22);
      if ( !WinHttpSendRequest(v21, 0, 0, 0, 0, 0, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x19D,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
          v24);
      HttpsProbes::HttpsRequest::~HttpsRequest((HttpsProbes::HttpsRequest *)&v41);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      if ( (unsigned int)dword_1801BD288 > 4 )
      {
        v38 = L"No failure";
        LODWORD(lpCriticalSection) = 0;
        v25 = L"Global";
        if ( *v30 != 1 )
          v25 = L"PerInterface";
        v37 = v25;
        if ( a1[10] <= 7u )
          v26 = (const WCHAR *)(a1 + 7);
        else
          v26 = *v15;
        v33 = v26;
        if ( a1[6] <= 7u )
          v27 = (WCHAR *)(a1 + 3);
        else
          v27 = (WCHAR *)*v11;
        hRequest = v27;
        v35 = a1[12];
        v34 = *((unsigned int *)a1 + 4);
        Buffer = a1[1];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          L"PerInterface",
          word_180199302);
      }
      _InterlockedIncrement64((volatile signed __int64 *)(*a1 + 128LL));
    }
    else
    {
      if ( (unsigned int)dword_1801BD288 > 4 )
      {
        if ( *v30 != 1 )
          v3 = L"PerInterface";
        v36 = v3;
        v34 = *(_QWORD *)(*a1 + 112LL);
        v35 = a1[12];
        hRequest = (HINTERNET)*((unsigned int *)a1 + 4);
        v33 = (const WCHAR *)a1[1];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
          v34,
          &byte_180199067);
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
      v20);
  }
}

```

## disassembly

```asm
0x1801272d8  mov     [rsp+arg_8], rbx
0x1801272dd  mov     [rsp+arg_10], rsi
0x1801272e2  push    rdi
0x1801272e3  push    r12
0x1801272e5  push    r13
0x1801272e7  push    r14
0x1801272e9  push    r15
0x1801272eb  sub     rsp, 130h
0x1801272f2  mov     rax, cs:__security_cookie
0x1801272f9  xor     rax, rsp
0x1801272fc  mov     [rsp+158h+var_38], rax
0x180127304  mov     r15, rcx
0x180127307  mov     rdi, rcx
0x18012730a  mov     [rsp+158h+var_98], rcx
0x180127312  mov     [rsp+158h+var_A8], rcx
0x18012731a  mov     eax, cs:dword_1801BD288
0x180127320  cmp     eax, 4
0x180127323  jbe     loc_1801273E3
0x180127329  mov     rax, [rcx+60h]
0x18012732d  mov     [rsp+158h+var_F0], rax
0x180127332  lea     rsi, aPerinterface; "PerInterface"
0x180127339  lea     r12, aGlobal; "Global"
0x180127340  mov     rax, r12
0x180127343  cmp     dword ptr [rcx+58h], 1
0x180127347  cmovnz  rax, rsi
0x18012734b  mov     [rsp+158h+var_E8], rax
0x180127350  lea     rax, [rcx+38h]
0x180127354  cmp     qword ptr [rax+18h], 7
0x180127359  jbe     short loc_18012735E
0x18012735b  mov     rax, [rax]
0x18012735e  mov     [rsp+158h+lpCriticalSection], rax
0x180127366  lea     rax, [rcx+18h]
0x18012736a  cmp     qword ptr [rax+18h], 7
0x18012736f  jbe     short loc_180127374
0x180127371  mov     rax, [rax]
0x180127374  mov     [rsp+158h+var_E0], rax
0x180127379  mov     eax, [rcx+10h]
0x18012737c  mov     [rsp+158h+var_B0], rax
0x180127384  mov     rax, [rcx+8]
0x180127388  mov     [rsp+158h+Buffer], rax
0x180127390  lea     rax, [rsp+158h+var_F0]
0x180127395  mov     [rsp+158h+var_110], rax
0x18012739a  lea     rax, [rsp+158h+var_E8]
0x18012739f  mov     [rsp+158h+var_118], rax
0x1801273a4  lea     rax, [rsp+158h+lpCriticalSection]
0x1801273ac  mov     [rsp+158h+var_120], rax
0x1801273b1  lea     rax, [rsp+158h+var_E0]
0x1801273b6  mov     qword ptr [rsp+158h+var_128], rax
0x1801273bb  lea     rax, [rsp+158h+var_B0]
0x1801273c3  mov     [rsp+158h+ppwszAcceptTypes], rax
0x1801273c8  lea     rax, [rsp+158h+Buffer]
0x1801273d0  mov     qword ptr [rsp+158h+dwFlags], rax
0x1801273d5  lea     rdx, word_18019952A
0x1801273dc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@_W@@U2@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@_W@@443@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x1801273e1  jmp     short loc_1801273EA
0x1801273e3  lea     r12, aGlobal; "Global"
0x1801273ea  xor     ebx, ebx
0x1801273ec  mov     dword ptr [rsp+158h+var_E0], ebx
0x1801273f0  mov     [rsp+158h+var_F8], bl
0x1801273f4  mov     [rsp+158h+dwFlags], 10000000h; int
0x1801273fc  xor     r9d, r9d; pszProxyBypassW
0x1801273ff  xor     r8d, r8d; pszProxyW
0x180127402  lea     edx, [rbx+1]; dwAccessType
0x180127405  lea     rcx, pszAgentW; "Microsoft NetworkListManager"
0x18012740c  call    cs:__imp_WinHttpOpen
0x180127412  mov     r13, rax
0x180127415  mov     rcx, [rsp+158h]; this
0x18012741d  test    rax, rax
0x180127420  jz      loc_180127A70
0x180127426  mov     rsi, [rsp+158h]
0x18012742e  xor     r9d, r9d; dwReserved
0x180127431  mov     r8d, 630000h; dwNotificationFlags
0x180127437  lea     rdx, ?HttpsRequestStatusCallback@HttpsProbes@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18012743e  mov     rcx, r13; hInternet
0x180127441  call    cs:__imp_WinHttpSetStatusCallback
0x180127447  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012744b  jz      loc_180127A8D
0x180127451  mov     rax, [r15]
0x180127454  mov     [rsp+158h+Buffer], rax
0x18012745c  mov     r9d, 8; dwBufferLength
0x180127462  lea     r8, [rsp+158h+Buffer]; lpBuffer
0x18012746a  lea     edx, [r9+25h]; dwOption
0x18012746e  mov     rcx, r13; hInternet
0x180127471  call    cs:__imp_WinHttpSetOption
0x180127477  mov     rcx, [rsp+158h]; this
0x18012747f  test    eax, eax
0x180127481  jz      loc_180127AAD
0x180127487  lea     rax, [r15+58h]
0x18012748b  mov     [rsp+158h+var_F0], rax
0x180127490  mov     r8d, [r15+10h]
0x180127494  mov     edx, [rax]
0x180127496  mov     rcx, r13; hInternet
0x180127499  call    SetOptionsOnWinhttpSessionHandle
0x18012749e  mov     rcx, [rsp+158h]; this
0x1801274a6  test    eax, eax
0x1801274a8  js      loc_180127ACA
0x1801274ae  lea     rsi, [r15+18h]
0x1801274b2  cmp     qword ptr [rsi+18h], 7
0x1801274b7  jbe     short loc_1801274BE
0x1801274b9  mov     rdx, [rsi]
0x1801274bc  jmp     short loc_1801274C1
0x1801274be  mov     rdx, rsi; pswzServerName
0x1801274c1  xor     r8d, r8d; nServerPort
0x1801274c4  xor     r9d, r9d; dwReserved
0x1801274c7  mov     rcx, r13; hSession
0x1801274ca  call    cs:__imp_WinHttpConnect
0x1801274d0  mov     [rsp+158h+var_C8], rax
0x1801274d8  mov     rcx, [rsp+158h]; this
0x1801274e0  test    rax, rax
0x1801274e3  jz      loc_180127AEA
0x1801274e9  lea     r14, [r15+38h]
0x1801274ed  cmp     qword ptr [r14+18h], 7
0x1801274f2  jbe     short loc_1801274F9
0x1801274f4  mov     r8, [r14]
0x1801274f7  jmp     short loc_1801274FC
0x1801274f9  mov     r8, r14; pwszObjectName
0x1801274fc  mov     [rsp+158h+var_128], 800104h; dwFlags
0x180127504  mov     [rsp+158h+ppwszAcceptTypes], rbx; ppwszAcceptTypes
0x180127509  mov     qword ptr [rsp+158h+dwFlags], rbx; int
0x18012750e  xor     r9d, r9d; pwszVersion
0x180127511  xor     edx, edx; pwszVerb
0x180127513  mov     rcx, rax; hConnect
0x180127516  call    cs:__imp_WinHttpOpenRequest
0x18012751c  mov     [rsp+158h+hRequest], rax
0x180127524  mov     rcx, [rsp+158h]; this
0x18012752c  test    rax, rax
0x18012752f  jz      loc_180127B07
0x180127535  lea     rcx, aSetoptionsonre; "SetOptionsOnRequestHandle"
0x18012753c  mov     [rsp+158h+var_E8], rcx
0x180127541  mov     rcx, rax; hInternet
0x180127544  call    SetOptionsOnRequestHandle
0x180127549  mov     rcx, [rsp+158h]; this
0x180127551  test    eax, eax
0x180127553  js      loc_180127B24
0x180127559  mov     [rsp+158h+lpCriticalSection], rbx
0x180127561  mov     rdx, [r15]
0x180127564  lea     rcx, [rsp+158h+lpCriticalSection]
0x18012756c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180127571  nop
0x180127572  mov     rax, [r15]
0x180127575  mov     rcx, [rax+70h]
0x180127579  cmp     [r15+60h], rcx
0x18012757d  jnb     loc_180127679
0x180127583  mov     eax, cs:dword_1801BD288
0x180127589  cmp     eax, 4
0x18012758c  jbe     loc_180127660
0x180127592  mov     rax, [rsp+158h+var_F0]
0x180127597  cmp     dword ptr [rax], 1
0x18012759a  lea     rax, aPerinterface; "PerInterface"
0x1801275a1  cmovnz  r12, rax
0x1801275a5  mov     [rsp+158h+var_B0], r12
0x1801275ad  cmp     qword ptr [r14+18h], 7
0x1801275b2  jbe     short loc_1801275B7
0x1801275b4  mov     r14, [r14]
0x1801275b7  mov     [rsp+158h+var_F0], r14
0x1801275bc  cmp     qword ptr [rsi+18h], 7
0x1801275c1  jbe     short loc_1801275C6
0x1801275c3  mov     rsi, [rsi]
0x1801275c6  mov     [rsp+158h+var_E0], rsi
0x1801275cb  mov     rax, [r15]
0x1801275ce  mov     rcx, [rax+70h]
0x1801275d2  mov     [rsp+158h+var_C0], rcx
0x1801275da  mov     rax, [r15+60h]
0x1801275de  mov     [rsp+158h+var_B8], rax
0x1801275e6  mov     eax, [r15+10h]
0x1801275ea  mov     [rsp+158h+hRequest], rax
0x1801275f2  mov     rax, [r15+8]
0x1801275f6  mov     [rsp+158h+var_C8], rax
0x1801275fe  lea     rax, [rsp+158h+var_B0]
0x180127606  mov     [rsp+158h+var_108], rax
0x18012760b  lea     rax, [rsp+158h+var_F0]
0x180127610  mov     [rsp+158h+var_110], rax
0x180127615  lea     rax, [rsp+158h+var_E0]
0x18012761a  mov     [rsp+158h+var_118], rax
0x18012761f  lea     rax, [rsp+158h+var_C0]
0x180127627  mov     [rsp+158h+var_120], rax
0x18012762c  lea     rax, [rsp+158h+var_B8]
0x180127634  mov     qword ptr [rsp+158h+var_128], rax
0x180127639  lea     rax, [rsp+158h+hRequest]
0x180127641  mov     [rsp+158h+ppwszAcceptTypes], rax
0x180127646  lea     rax, [rsp+158h+var_C8]
0x18012764e  mov     qword ptr [rsp+158h+dwFlags], rax
0x180127653  lea     rdx, byte_180199067
0x18012765a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapSz@_W@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@333AEBU?$_tlgWrapSz@_W@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18012765f  nop
0x180127660  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x180127668  test    rcx, rcx
0x18012766b  jz      short loc_180127674
0x18012766d  call    cs:__imp_LeaveCriticalSection
0x180127673  nop
0x180127674  jmp     loc_180127A43
0x180127679  xorps   xmm0, xmm0
0x18012767c  movdqa  [rsp+158h+var_88], xmm0
0x180127685  mov     qword ptr [rsp+158h+var_88+8], rbx
0x18012768d  mov     [rsp+158h+var_78], rbx
0x180127695  lea     rcx, [rsp+158h+var_70]
0x18012769d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801276a2  mov     [rsp+158h+var_50], rbx
0x1801276aa  mov     [rsp+158h+var_48], rbx
0x1801276b2  mov     rdx, r13
0x1801276b5  lea     rcx, [rsp+158h+var_88]
0x1801276bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801276c2  mov     rdx, [rsp+158h+var_C8]
0x1801276ca  lea     rcx, [rsp+158h+var_88+8]
0x1801276d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801276d7  mov     r13, [rsp+158h+hRequest]
0x1801276df  mov     rdx, r13
0x1801276e2  lea     rcx, [rsp+158h+var_78]
0x1801276ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801276ef  mov     rdx, rsi
0x1801276f2  lea     rcx, [rsp+158h+var_70]
0x1801276fa  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801276ff  mov     rax, [rsp+158h+var_F0]
0x180127704  mov     eax, [rax]
0x180127706  mov     dword ptr [rsp+158h+var_48], eax
0x18012770d  mov     rax, [r15+60h]
0x180127711  mov     [rsp+158h+var_50], rax
0x180127719  mov     r11, [r15]
0x18012771c  mov     rax, [r11+30h]
0x180127720  cmp     rax, [r11+38h]
0x180127724  jz      short loc_18012773D
0x180127726  lea     rdx, [rsp+158h+var_88]
0x18012772e  mov     rcx, rax
0x180127731  call    ??0HttpsRequest@HttpsProbes@@QEAA@$$QEAU01@@Z; HttpsProbes::HttpsRequest::HttpsRequest(HttpsProbes::HttpsRequest &&)
0x180127736  add     qword ptr [r11+30h], 48h ; 'H'
0x18012773b  jmp     short loc_180127751
0x18012773d  lea     r8, [rsp+158h+var_88]
0x180127745  mov     rdx, rax
0x180127748  lea     rcx, [r11+28h]
0x18012774c  call    ??$_Emplace_reallocate@UHttpsRequest@HttpsProbes@@@?$vector@UHttpsRequest@HttpsProbes@@V?$allocator@UHttpsRequest@HttpsProbes@@@std@@@std@@AEAAPEAUHttpsRequest@HttpsProbes@@QEAU23@$$QEAU23@@Z; std::vector<HttpsProbes::HttpsRequest>::_Emplace_reallocate<HttpsProbes::HttpsRequest>(HttpsProbes::HttpsRequest * const,HttpsProbes::HttpsRequest &&)
0x180127751  mov     [rsp+158h+var_F8], 1
0x180127756  mov     rcx, [r15]
0x180127759  mov     rcx, [rcx+58h]; this
0x18012775d  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x180127762  mov     qword ptr [rsp+158h+var_128], rbx; dwContext
0x180127767  mov     dword ptr [rsp+158h+ppwszAcceptTypes], ebx; dwTotalLength
0x18012776b  mov     [rsp+158h+dwFlags], ebx; dwOptionalLength
0x18012776f  xor     r9d, r9d; lpOptional
0x180127772  xor     r8d, r8d; dwHeadersLength
0x180127775  xor     edx, edx; lpszHeaders
0x180127777  mov     rcx, r13; hRequest
0x18012777a  call    cs:__imp_WinHttpSendRequest
0x180127780  mov     rcx, [rsp+158h]; this
0x180127788  test    eax, eax
0x18012778a  jz      loc_180127B39
0x180127790  lea     rax, aNoFailure; "No failure"
0x180127797  mov     [rsp+158h+var_E8], rax
0x18012779c  lea     rcx, [rsp+158h+var_88]; this
0x1801277a4  call    ??1HttpsRequest@HttpsProbes@@QEAA@XZ; HttpsProbes::HttpsRequest::~HttpsRequest(void)
0x1801277a9  nop
0x1801277aa  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x1801277b2  test    rcx, rcx
0x1801277b5  jz      short loc_1801277BE
0x1801277b7  call    cs:__imp_LeaveCriticalSection
0x1801277bd  nop
0x1801277be  mov     rdx, [rsp+158h+var_F0]
0x1801277c3  mov     r8d, dword ptr [rsp+158h+var_E0]
0x1801277c8  jmp     short loc_180127801
0x1801277ca  jmp     loc_180127A43
0x1801277cf  mov     rax, [rsp+158h+var_A8]
0x1801277d7  lea     rdx, [rax+58h]
0x1801277db  mov     [rsp+158h+var_F0], rdx
0x1801277e0  lea     r14, [rax+38h]
0x1801277e4  lea     rsi, [rax+18h]
0x1801277e8  lea     r12, aGlobal; "Global"
0x1801277ef  xor     ebx, ebx
0x1801277f1  mov     r8d, dword ptr [rsp+158h+var_E0]
0x1801277f6  mov     dword ptr [rsp+158h+var_E0], r8d
0x1801277fb  mov     r15, rax
0x1801277fe  mov     rdi, rax
0x180127801  lea     rcx, aPerinterface; "PerInterface"
0x180127808  mov     eax, cs:dword_1801BD288
0x18012780e  cmp     eax, 4
0x180127811  jbe     loc_180127903
0x180127817  mov     rax, [rsp+158h+var_E8]
0x18012781c  mov     [rsp+158h+var_A0], rax
0x180127824  mov     dword ptr [rsp+158h+lpCriticalSection], r8d
0x18012782c  mov     rax, r12
0x18012782f  cmp     dword ptr [rdx], 1
0x180127832  cmovnz  rax, rcx
0x180127836  mov     [rsp+158h+var_A8], rax
0x18012783e  cmp     qword ptr [r14+18h], 7
0x180127843  jbe     short loc_18012784A
0x180127845  mov     rax, [r14]
0x180127848  jmp     short loc_18012784D
0x18012784a  mov     rax, r14
0x18012784d  mov     [rsp+158h+var_C8], rax
0x180127855  cmp     qword ptr [rsi+18h], 7
0x18012785a  jbe     short loc_180127861
0x18012785c  mov     rax, [rsi]
0x18012785f  jmp     short loc_180127864
0x180127861  mov     rax, rsi
0x180127864  mov     [rsp+158h+hRequest], rax
0x18012786c  mov     rax, [rdi+60h]
0x180127870  mov     [rsp+158h+var_B8], rax
0x180127878  mov     eax, [rdi+10h]
0x18012787b  mov     [rsp+158h+var_C0], rax
0x180127883  mov     rax, [rdi+8]
0x180127887  mov     [rsp+158h+Buffer], rax
0x18012788f  lea     rax, [rsp+158h+var_A0]
  ... truncated ...
```
