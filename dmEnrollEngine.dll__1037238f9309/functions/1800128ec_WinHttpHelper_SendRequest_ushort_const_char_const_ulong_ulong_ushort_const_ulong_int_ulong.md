# WinHttpHelper::SendRequest(ushort const *,char const *,ulong,ulong,ushort const * *,ulong,int *,ulong *)

- ea: `0x1800128ec`
- end: `0x180012e5a`
- name: `?SendRequest@WinHttpHelper@@QEAAJPEBGPEBDKKPEAPEBGKPEAHPEAK@Z`
- size: `1390`
- prototype: `int(WinHttpHelper *__hidden this, const unsigned __int16 *, const char *, unsigned int, unsigned int, const unsigned __int16 **, unsigned int, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005363c`

## callees

- `0x18000dd20`
- `0x180011938`
- `0x1800128c4`
- `0x1800128ec`
- `0x1800140d0`
- `0x18001aec8`
- `0x180021368`
- `0x18002e1a0`
- `0x18003b118`
- `0x18003b170`
- `0x18004e314`
- `0x180053c5c`
- `0x180053d20`
- `0x1800708a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180012dcb`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180012dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012de7`
- `WINHTTP!WinHttpOpenRequest` at `0x180012a1f`
- `WINHTTP!WinHttpOpenRequest` at `0x180012a1f`
- `WINHTTP!WinHttpSetOption` at `0x180012a65`
- `WINHTTP!WinHttpSetOption` at `0x180012c21`
- `WINHTTP!WinHttpSetOption` at `0x180012a65`
- `WINHTTP!WinHttpSetOption` at `0x180012c21`
- `WINHTTP!WinHttpSendRequest` at `0x180012bed`
- `WINHTTP!WinHttpSendRequest` at `0x180012c66`
- `WINHTTP!WinHttpSendRequest` at `0x180012bed`
- `WINHTTP!WinHttpSendRequest` at `0x180012c66`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180012ab4`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180012e28`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180012ab4`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180012e28`
- `WINHTTP!WinHttpReceiveResponse` at `0x180012d24`
- `WINHTTP!WinHttpReceiveResponse` at `0x180012d24`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012d4e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012dbd`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012d4e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180012dbd`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180012b0c`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180012b97`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180012b0c`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180012b97`

## string_xrefs

- `0x180012b8d`: `Content-Type: application/soap+xml; charset=utf-8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinHttpHelper::SendRequest(
        HINTERNET *this,
        const unsigned __int16 *a2,
        char *a3,
        DWORD a4,
        char a5,
        const unsigned __int16 **a6,
        unsigned int a7,
        int *lpBuffer,
        unsigned int *a9)
{
  DWORD v9; // esi
  const unsigned __int16 **v13; // rbx
  int *v14; // r13
  WCHAR *ppwszAcceptTypes; // r11
  int v16; // ebx
  void *v17; // rcx
  DWORD dwFlags; // eax
  HINTERNET *v19; // rdi
  const WCHAR *v20; // rdx
  HINTERNET v21; // rax
  void *v22; // rcx
  signed int v23; // eax
  signed int *v24; // r15
  unsigned int v25; // r14d
  unsigned __int64 v26; // rcx
  int v27; // eax
  const WCHAR *v28; // r11
  unsigned int v29; // eax
  CEnrollmentLogger *Logger; // rax
  BOOL v31; // ebx
  signed int v32; // eax
  signed int v33; // eax
  signed int v34; // ebx
  __int64 v35; // r8
  __int64 v36; // r8
  __int64 *v37; // rdx
  unsigned int *v38; // rbx
  unsigned int LastError; // eax
  __int64 v40; // rdx
  int pwszReferrer; // [rsp+20h] [rbp-91h]
  int v43; // [rsp+40h] [rbp-71h] BYREF
  DWORD Buffer; // [rsp+48h] [rbp-69h] BYREF
  int v45; // [rsp+50h] [rbp-61h] BYREF
  unsigned __int64 v46; // [rsp+58h] [rbp-59h] BYREF
  DWORD dwBufferLength; // [rsp+60h] [rbp-51h] BYREF
  const unsigned __int16 **v48; // [rsp+68h] [rbp-49h]
  int *v49; // [rsp+70h] [rbp-41h]
  unsigned int *v50; // [rsp+78h] [rbp-39h]
  _QWORD v51[2]; // [rsp+80h] [rbp-31h] BYREF
  WinHttpHelper *v52; // [rsp+90h] [rbp-21h] BYREF
  char v53; // [rsp+98h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  v9 = a4;
  Buffer = a4;
  v13 = a6;
  v48 = a6;
  v14 = lpBuffer;
  v49 = lpBuffer;
  v50 = a9;
  ppwszAcceptTypes = 0;
  v43 = 0;
  dwBufferLength = 4;
  v46 = 0;
  v51[0] = "WinHttpHelper::SendRequest";
  v51[1] = &v43;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, SendingRequestToServerEvent, a2);
    ppwszAcceptTypes = 0;
  }
  *lpBuffer = 200;
  v52 = (WinHttpHelper *)this;
  v53 = 1;
  if ( a3 )
  {
    v16 = StringCchLengthA(a3, (unsigned __int64)a2, &v46);
    v43 = v16;
    if ( v16 < 0 || (v16 = ULongLongToULong(v46, &Buffer), v43 = v16, v16 < 0) )
    {
      v17 = this[2];
      goto LABEL_82;
    }
    v9 = Buffer;
    v13 = v48;
  }
  dwFlags = (unsigned int)ppwszAcceptTypes;
  if ( dword_1800AFD00 != (_DWORD)ppwszAcceptTypes )
    dwFlags = 0x800000;
  v19 = this + 2;
  v20 = L"POST";
  if ( !a3 )
    v20 = L"GET";
  v21 = WinHttpOpenRequest(this[1], v20, a2, L"HTTP/1.1", ppwszAcceptTypes, (LPCWSTR *)ppwszAcceptTypes, dwFlags);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    this + 2,
    v21);
  v22 = *v19;
  if ( !*v19 )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80190000;
    else
      LastError = GetLastError();
    v43 = LastError;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      goto LABEL_80;
    v36 = LastError;
    v37 = OpenRequestFailedEvent;
    goto LABEL_79;
  }
  v45 = 0;
  if ( dword_1800AFD00 )
  {
    if ( (a5 & 0x10) != 0 )
    {
      Buffer = 256;
      if ( !WinHttpSetOption(v22, 0x1Fu, &Buffer, 4u) )
        goto LABEL_16;
    }
  }
  v24 = (signed int *)(this + 4);
  v25 = 0;
  *v24 = 0;
  if ( WinHttpSetStatusCallback(*v19, SecureFailureCallback, 0x10000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    goto LABEL_16;
  if ( v13 )
  {
    while ( 1 )
    {
      if ( v25 >= 2 )
      {
        v14 = v49;
        goto LABEL_35;
      }
      Buffer = 0;
      v26 = -1;
      do
        ++v26;
      while ( v13[v25][v26] );
      v27 = ULongLongToULong(v26, &Buffer);
      v16 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x268,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\winhttphelper.cpp",
          (const char *)(unsigned int)v27,
          pwszReferrer);
        goto LABEL_81;
      }
      if ( !WinHttpAddRequestHeaders(*v19, v28, Buffer, 0x20000000u) )
        break;
      ++v25;
      v13 = v48;
    }
    if ( (int)GetLastError() > 0 )
      v29 = (unsigned __int16)GetLastError() | 0x80190000;
    else
      v29 = GetLastError();
    v43 = v29;
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogAddingExtraHeaderFailure(Logger, v43, v48[v25]);
    goto LABEL_80;
  }
LABEL_35:
  if ( !WinHttpAddRequestHeaders(*v19, L"Content-Type: application/soap+xml; charset=utf-8", 0xFFFFFFFF, 0x20000000u) )
    goto LABEL_16;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, HttpSendRequestDataSizeEvent, v9);
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)&v46, "WinHttpSendRequest");
  v31 = WinHttpSendRequest(*v19, 0, 0, a3, v9, v9, (DWORD_PTR)v24);
  if ( !v31 && *v24 == 12038 && (int)CheckCertSAN(*v19) >= 0 )
  {
    v45 |= 0x1000u;
    if ( !WinHttpSetOption(*v19, 0x1Fu, &v45, 4u) )
    {
      v32 = GetLastError();
      if ( v32 > 0 )
        v32 = (unsigned __int16)v32 | 0x80070000;
      v43 = v32;
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v46);
      goto LABEL_80;
    }
    v31 = WinHttpSendRequest(*v19, 0, 0, a3, v9, v9, (DWORD_PTR)v24);
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v46);
  if ( !v31 )
  {
    v33 = GetLastError();
    v34 = v33;
    if ( v33 > 0 )
      v35 = (unsigned __int16)v33 | 0x80190000;
    else
      v35 = (unsigned int)v33;
    v43 = v35;
    if ( (int)v35 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, SendingRequestFailedEvent, v35);
    if ( v34 == 12175 )
    {
      v23 = *v24;
      if ( !*v24 )
        v23 = 12175;
      if ( v23 == 12045 || v23 == 12057 )
      {
        v23 = -2145910766;
        goto LABEL_20;
      }
      if ( v23 > 0 )
        goto LABEL_19;
      goto LABEL_20;
    }
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      goto LABEL_80;
    if ( v34 > 0 )
      v34 = (unsigned __int16)v34 | 0x80190000;
    v36 = (unsigned int)v34;
    v37 = SendingRequestFailedEvent;
LABEL_79:
    McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, v37, v36);
    goto LABEL_80;
  }
  if ( !WinHttpReceiveResponse(*v19, 0) )
  {
LABEL_16:
    if ( (int)GetLastError() > 0 )
    {
      LOWORD(v23) = GetLastError();
LABEL_19:
      v23 = (unsigned __int16)v23 | 0x80190000;
      goto LABEL_20;
    }
    v23 = GetLastError();
LABEL_20:
    v43 = v23;
    goto LABEL_80;
  }
  if ( !WinHttpQueryHeaders(*v19, 0x20000013u, 0, v14, &dwBufferLength, 0) )
  {
    if ( (int)GetLastError() > 0 )
      v43 = (unsigned __int16)GetLastError() | 0x80190000;
    else
      v43 = GetLastError();
  }
  v38 = v50;
  *v50 = 0;
  if ( *v14 == 503 || *v14 == 429 )
  {
    Buffer = 22;
    if ( WinHttpQueryHeaders(*v19, 0x24u, 0, &v52, &Buffer, 0) )
      *v38 = _o__wtol(&v52);
  }
LABEL_80:
  v16 = v43;
LABEL_81:
  v17 = *v19;
LABEL_82:
  WinHttpSetStatusCallback(v17, 0, 0x10000u, 0);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v51, v40);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800128ec  push    rbp
0x1800128ee  push    rbx
0x1800128ef  push    rsi
0x1800128f0  push    rdi
0x1800128f1  push    r12
0x1800128f3  push    r13
0x1800128f5  push    r14
0x1800128f7  push    r15
0x1800128f9  lea     rbp, [rsp-7]
0x1800128fe  sub     rsp, 0B8h
0x180012905  mov     rax, cs:__security_cookie
0x18001290c  xor     rax, rsp
0x18001290f  mov     [rbp+3Fh+var_48], rax
0x180012913  mov     esi, r9d
0x180012916  mov     r12, r8
0x180012919  mov     r15, rdx
0x18001291c  mov     r14, rcx
0x18001291f  mov     [rbp+3Fh+Buffer], r9d
0x180012923  mov     rbx, [rbp+3Fh+arg_28]
0x180012927  mov     [rbp+3Fh+var_88], rbx
0x18001292b  mov     r13, [rbp+3Fh+lpBuffer]
0x180012932  mov     [rbp+3Fh+var_80], r13
0x180012936  mov     rax, [rbp+3Fh+arg_40]
0x18001293d  mov     [rbp+3Fh+var_78], rax
0x180012941  xor     r11d, r11d
0x180012944  mov     [rbp+3Fh+var_B0], r11d
0x180012948  mov     [rbp+3Fh+dwBufferLength], 4
0x18001294f  mov     [rbp+3Fh+var_98], r11
0x180012953  lea     rax, aWinhttphelperS; "WinHttpHelper::SendRequest"
0x18001295a  mov     [rbp+3Fh+var_70], rax
0x18001295e  lea     rax, [rbp+3Fh+var_B0]
0x180012962  mov     [rbp+3Fh+var_68], rax
0x180012966  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001296d  jz      short loc_180012988
0x18001296f  mov     r8, rdx
0x180012972  lea     rdx, SendingRequestToServerEvent
0x180012979  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180012980  call    McTemplateU0z_EventWriteTransfer
0x180012985  xor     r11d, r11d
0x180012988  mov     dword ptr [r13+0], 0C8h
0x180012990  mov     [rbp+3Fh+var_60], r14
0x180012994  mov     [rbp+3Fh+var_58], 1
0x180012998  test    r12, r12
0x18001299b  jz      short loc_1800129D8
0x18001299d  lea     r8, [rbp+3Fh+var_98]; unsigned __int64 *
0x1800129a1  mov     rcx, r12; char *
0x1800129a4  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800129a9  mov     ebx, eax
0x1800129ab  mov     [rbp+3Fh+var_B0], eax
0x1800129ae  test    eax, eax
0x1800129b0  js      short loc_1800129C8
0x1800129b2  lea     rdx, [rbp+3Fh+Buffer]; unsigned int *
0x1800129b6  mov     rcx, [rbp+3Fh+var_98]; unsigned __int64
0x1800129ba  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800129bf  mov     ebx, eax
0x1800129c1  mov     [rbp+3Fh+var_B0], eax
0x1800129c4  test    eax, eax
0x1800129c6  jns     short loc_1800129D1
0x1800129c8  mov     rcx, [r14+10h]
0x1800129cc  jmp     loc_180012E1D
0x1800129d1  mov     esi, [rbp+3Fh+Buffer]
0x1800129d4  mov     rbx, [rbp+3Fh+var_88]
0x1800129d8  mov     eax, r11d
0x1800129db  mov     ecx, 800000h
0x1800129e0  cmp     cs:dword_1800AFD00, r11d
0x1800129e7  cmovnz  eax, ecx
0x1800129ea  lea     rdi, [r14+10h]
0x1800129ee  lea     rcx, pwszVerb; "GET"
0x1800129f5  lea     rdx, aPost; "POST"
0x1800129fc  test    r12, r12
0x1800129ff  cmovz   rdx, rcx; pwszVerb
0x180012a03  mov     [rsp+0F0h+dwFlags], eax; dwFlags
0x180012a07  mov     [rsp+0F0h+ppwszAcceptTypes], r11; ppwszAcceptTypes
0x180012a0c  mov     [rsp+0F0h+pwszReferrer], r11; int
0x180012a11  lea     r9, pwszVersion; "HTTP/1.1"
0x180012a18  mov     r8, r15; pwszObjectName
0x180012a1b  mov     rcx, [r14+8]; hConnect
0x180012a1f  call    cs:__imp_WinHttpOpenRequest
0x180012a25  mov     rdx, rax
0x180012a28  mov     rcx, rdi
0x180012a2b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180012a30  mov     rcx, [rdi]; hInternet
0x180012a33  xor     r15d, r15d
0x180012a36  test    rcx, rcx
0x180012a39  jz      loc_180012DD5
0x180012a3f  mov     [rbp+3Fh+var_A0], r15d
0x180012a43  cmp     cs:dword_1800AFD00, r15d
0x180012a4a  jz      short loc_180012A97
0x180012a4c  test    [rbp+3Fh+arg_20], 10h
0x180012a50  jz      short loc_180012A97
0x180012a52  mov     [rbp+3Fh+Buffer], 100h
0x180012a59  lea     r9d, [r15+4]; dwBufferLength
0x180012a5d  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x180012a61  lea     edx, [r15+1Fh]; dwOption
0x180012a65  call    cs:__imp_WinHttpSetOption
0x180012a6b  test    eax, eax
0x180012a6d  jnz     short loc_180012A97
0x180012a6f  call    cs:__imp_GetLastError
0x180012a75  test    eax, eax
0x180012a77  jg      short loc_180012A81
0x180012a79  call    cs:__imp_GetLastError
0x180012a7f  jmp     short loc_180012A8F
0x180012a81  call    cs:__imp_GetLastError
0x180012a87  movzx   eax, ax
0x180012a8a  or      eax, 80190000h
0x180012a8f  mov     [rbp+3Fh+var_B0], eax
0x180012a92  jmp     loc_180012E17
0x180012a97  lea     r15, [r14+20h]
0x180012a9b  xor     r14d, r14d
0x180012a9e  mov     [r15], r14d
0x180012aa1  xor     r9d, r9d; dwReserved
0x180012aa4  mov     r8d, 10000h; dwNotificationFlags
0x180012aaa  lea     rdx, SecureFailureCallback; lpfnInternetCallback
0x180012ab1  mov     rcx, [rdi]; hInternet
0x180012ab4  call    cs:__imp_WinHttpSetStatusCallback
0x180012aba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012abe  jz      short loc_180012A6F
0x180012ac0  test    rbx, rbx
0x180012ac3  jz      loc_180012B83
0x180012ac9  cmp     r14d, 2
0x180012acd  jnb     loc_180012B7C
0x180012ad3  xor     eax, eax
0x180012ad5  mov     [rbp+3Fh+Buffer], eax
0x180012ad8  mov     r13d, r14d
0x180012adb  mov     r11, [rbx+r13*8]
0x180012adf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180012ae3  inc     rcx; unsigned __int64
0x180012ae6  cmp     [r11+rcx*2], ax
0x180012aeb  jnz     short loc_180012AE3
0x180012aed  lea     rdx, [rbp+3Fh+Buffer]; unsigned int *
0x180012af1  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180012af6  mov     ebx, eax
0x180012af8  test    eax, eax
0x180012afa  js      short loc_180012B5F
0x180012afc  mov     r9d, 20000000h; dwModifiers
0x180012b02  mov     r8d, [rbp+3Fh+Buffer]; dwHeadersLength
0x180012b06  mov     rdx, r11; lpszHeaders
0x180012b09  mov     rcx, [rdi]; hRequest
0x180012b0c  call    cs:__imp_WinHttpAddRequestHeaders
0x180012b12  test    eax, eax
0x180012b14  jz      short loc_180012B1F
0x180012b16  inc     r14d
0x180012b19  mov     rbx, [rbp+3Fh+var_88]
0x180012b1d  jmp     short loc_180012AC9
0x180012b1f  call    cs:__imp_GetLastError
0x180012b25  test    eax, eax
0x180012b27  jg      short loc_180012B31
0x180012b29  call    cs:__imp_GetLastError
0x180012b2f  jmp     short loc_180012B3F
0x180012b31  call    cs:__imp_GetLastError
0x180012b37  movzx   eax, ax
0x180012b3a  or      eax, 80190000h
0x180012b3f  mov     [rbp+3Fh+var_B0], eax
0x180012b42  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012b47  mov     r8, [rbp+3Fh+var_88]
0x180012b4b  mov     r8, [r8+r13*8]; unsigned __int16 *
0x180012b4f  mov     edx, [rbp+3Fh+var_B0]; int
0x180012b52  mov     rcx, rax; this
0x180012b55  call    ?LogAddingExtraHeaderFailure@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogAddingExtraHeaderFailure(long,ushort const *)
0x180012b5a  jmp     loc_180012E17
0x180012b5f  mov     rcx, [rbp+47h]; this
0x180012b63  mov     r9d, eax; char *
0x180012b66  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180012b6d  mov     edx, 268h; void *
0x180012b72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b77  jmp     loc_180012E1A
0x180012b7c  mov     r13, [rbp+3Fh+var_80]
0x180012b80  xor     r14d, r14d
0x180012b83  mov     r9d, 20000000h; dwModifiers
0x180012b89  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180012b8d  lea     rdx, szHeaders; "Content-Type: application/soap+xml; cha"...
0x180012b94  mov     rcx, [rdi]; hRequest
0x180012b97  call    cs:__imp_WinHttpAddRequestHeaders
0x180012b9d  test    eax, eax
0x180012b9f  jz      loc_180012A6F
0x180012ba5  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x180012bac  jz      short loc_180012BC4
0x180012bae  mov     r8d, esi
0x180012bb1  lea     rdx, HttpSendRequestDataSizeEvent
0x180012bb8  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180012bbf  call    McTemplateU0q_EventWriteTransfer
0x180012bc4  lea     rdx, aWinhttpsendreq_0; "WinHttpSendRequest"
0x180012bcb  lea     rcx, [rbp+3Fh+var_98]; this
0x180012bcf  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x180012bd4  nop
0x180012bd5  mov     qword ptr [rsp+0F0h+dwFlags], r15; dwContext
0x180012bda  mov     dword ptr [rsp+0F0h+ppwszAcceptTypes], esi; dwTotalLength
0x180012bde  mov     dword ptr [rsp+0F0h+pwszReferrer], esi; dwOptionalLength
0x180012be2  mov     r9, r12; lpOptional
0x180012be5  xor     r8d, r8d; dwHeadersLength
0x180012be8  xor     edx, edx; lpszHeaders
0x180012bea  mov     rcx, [rdi]; hRequest
0x180012bed  call    cs:__imp_WinHttpSendRequest
0x180012bf3  mov     ebx, eax
0x180012bf5  test    eax, eax
0x180012bf7  jnz     short loc_180012C6E
0x180012bf9  cmp     dword ptr [r15], 2F06h
0x180012c00  jnz     short loc_180012C6E
0x180012c02  mov     rcx, [rdi]; hInternet
0x180012c05  call    CheckCertSAN
0x180012c0a  test    eax, eax
0x180012c0c  js      short loc_180012C6E
0x180012c0e  bts     [rbp+3Fh+var_A0], 0Ch
0x180012c13  lea     r9d, [rbx+4]; dwBufferLength
0x180012c17  lea     r8, [rbp+3Fh+var_A0]; lpBuffer
0x180012c1b  lea     edx, [rbx+1Fh]; dwOption
0x180012c1e  mov     rcx, [rdi]; hInternet
0x180012c21  call    cs:__imp_WinHttpSetOption
0x180012c27  test    eax, eax
0x180012c29  jnz     short loc_180012C4E
0x180012c2b  call    cs:__imp_GetLastError
0x180012c31  test    eax, eax
0x180012c33  jle     short loc_180012C3D
0x180012c35  movzx   eax, ax
0x180012c38  or      eax, 80070000h
0x180012c3d  mov     [rbp+3Fh+var_B0], eax
0x180012c40  lea     rcx, [rbp+3Fh+var_98]; this
0x180012c44  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012c49  jmp     loc_180012E17
0x180012c4e  mov     qword ptr [rsp+0F0h+dwFlags], r15; dwContext
0x180012c53  mov     dword ptr [rsp+0F0h+ppwszAcceptTypes], esi; dwTotalLength
0x180012c57  mov     dword ptr [rsp+0F0h+pwszReferrer], esi; dwOptionalLength
0x180012c5b  mov     r9, r12; lpOptional
0x180012c5e  xor     r8d, r8d; dwHeadersLength
0x180012c61  xor     edx, edx; lpszHeaders
0x180012c63  mov     rcx, [rdi]; hRequest
0x180012c66  call    cs:__imp_WinHttpSendRequest
0x180012c6c  mov     ebx, eax
0x180012c6e  lea     rcx, [rbp+3Fh+var_98]; this
0x180012c72  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012c77  test    ebx, ebx
0x180012c79  jnz     loc_180012D1F
0x180012c7f  call    cs:__imp_GetLastError
0x180012c85  mov     ebx, eax
0x180012c87  test    eax, eax
0x180012c89  jg      short loc_180012C90
0x180012c8b  mov     r8d, eax
0x180012c8e  jmp     short loc_180012C9B
0x180012c90  movzx   r8d, bx
0x180012c94  or      r8d, 80190000h
0x180012c9b  mov     [rbp+3Fh+var_B0], r8d
0x180012c9f  test    r8d, r8d
0x180012ca2  jns     short loc_180012CC0
0x180012ca4  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180012cab  jz      short loc_180012CC0
0x180012cad  lea     rdx, SendingRequestFailedEvent
0x180012cb4  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180012cbb  call    McTemplateU0q_EventWriteTransfer
0x180012cc0  mov     ecx, 2F8Fh
0x180012cc5  cmp     ebx, ecx
0x180012cc7  jnz     short loc_180012CF6
0x180012cc9  mov     eax, [r15]
0x180012ccc  test    eax, eax
0x180012cce  cmovz   eax, ecx
0x180012cd1  cmp     eax, 2F0Dh
0x180012cd6  jz      short loc_180012CEC
0x180012cd8  cmp     eax, 2F19h
0x180012cdd  jz      short loc_180012CEC
0x180012cdf  test    eax, eax
0x180012ce1  jle     loc_180012A8F
0x180012ce7  jmp     loc_180012A87
0x180012cec  mov     eax, 80180012h
0x180012cf1  jmp     loc_180012A8F
0x180012cf6  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180012cfd  jz      loc_180012E17
0x180012d03  test    ebx, ebx
0x180012d05  jle     short loc_180012D10
0x180012d07  movzx   ebx, bx
0x180012d0a  or      ebx, 80190000h
0x180012d10  mov     r8d, ebx
0x180012d13  lea     rdx, SendingRequestFailedEvent
0x180012d1a  jmp     loc_180012E0B
0x180012d1f  xor     edx, edx; lpReserved
0x180012d21  mov     rcx, [rdi]; hRequest
0x180012d24  call    cs:__imp_WinHttpReceiveResponse
0x180012d2a  test    eax, eax
0x180012d2c  jz      loc_180012A6F
0x180012d32  mov     [rsp+0F0h+ppwszAcceptTypes], r14; lpdwIndex
0x180012d37  lea     rax, [rbp+3Fh+dwBufferLength]
0x180012d3b  mov     [rsp+0F0h+pwszReferrer], rax; lpdwBufferLength
0x180012d40  mov     r9, r13; lpBuffer
0x180012d43  xor     r8d, r8d; pwszName
0x180012d46  mov     edx, 20000013h; dwInfoLevel
0x180012d4b  mov     rcx, [rdi]; hRequest
0x180012d4e  call    cs:__imp_WinHttpQueryHeaders
0x180012d54  test    eax, eax
0x180012d56  jnz     short loc_180012D7F
0x180012d58  call    cs:__imp_GetLastError
0x180012d5e  test    eax, eax
0x180012d60  jg      short loc_180012D6D
0x180012d62  call    cs:__imp_GetLastError
0x180012d68  mov     [rbp+3Fh+var_B0], eax
0x180012d6b  jmp     short loc_180012D7F
0x180012d6d  call    cs:__imp_GetLastError
0x180012d73  movzx   ecx, ax
0x180012d76  or      ecx, 80190000h
0x180012d7c  mov     [rbp+3Fh+var_B0], ecx
0x180012d7f  mov     rbx, [rbp+3Fh+var_78]
0x180012d83  mov     [rbx], r14d
0x180012d86  cmp     dword ptr [r13+0], 1F7h
  ... truncated ...
```
