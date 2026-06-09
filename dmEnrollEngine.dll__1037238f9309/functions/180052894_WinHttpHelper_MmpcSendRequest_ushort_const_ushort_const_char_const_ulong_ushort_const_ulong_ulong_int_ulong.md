# WinHttpHelper::MmpcSendRequest(ushort const *,ushort const *,char const *,ulong,ushort const * *,ulong,ulong,int *,ulong *)

- ea: `0x180052894`
- end: `0x180052e04`
- name: `?MmpcSendRequest@WinHttpHelper@@QEAAJPEBG0PEBDKPEAPEBGKKPEAHPEAK@Z`
- size: `1392`
- prototype: `int(WinHttpHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const char *, unsigned int, const unsigned __int16 **, unsigned int, unsigned int, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052e0c`

## callees

- `0x18000dd20`
- `0x180011938`
- `0x1800128c4`
- `0x18001aec8`
- `0x1800214cc`
- `0x18002e1a0`
- `0x18003b118`
- `0x18004e314`
- `0x180051e7c`
- `0x180052894`
- `0x180053c5c`
- `0x180053d20`
- `0x180053d7c`
- `0x180072958`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180052d77`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180052d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d96`
- `WINHTTP!WinHttpOpenRequest` at `0x180052980`
- `WINHTTP!WinHttpOpenRequest` at `0x180052980`
- `WINHTTP!WinHttpSendRequest` at `0x180052b00`
- `WINHTTP!WinHttpSendRequest` at `0x180052b00`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800529b9`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180052dd3`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800529b9`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180052dd3`
- `WINHTTP!WinHttpQueryOption` at `0x180052b4c`
- `WINHTTP!WinHttpQueryOption` at `0x180052b4c`
- `WINHTTP!WinHttpReceiveResponse` at `0x180052ca7`
- `WINHTTP!WinHttpReceiveResponse` at `0x180052ca7`
- `WINHTTP!WinHttpQueryHeaders` at `0x180052cf5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180052d68`
- `WINHTTP!WinHttpQueryHeaders` at `0x180052cf5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180052d68`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180052a31`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180052a7f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180052a31`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180052a7f`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsCertificateTrustedForMmpc` at `0x180052b8a`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsCertificateTrustedForMmpc` at `0x180052b8a`

## string_xrefs

- `0x180052a75`: `Content-Type: application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinHttpHelper::MmpcSendRequest(
        HINTERNET *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char *a4,
        DWORD dwOptionalLength,
        const unsigned __int16 **a6,
        unsigned int a7,
        unsigned int a8,
        int *lpBuffer,
        unsigned int *a10)
{
  const WCHAR *v11; // r11
  int *v13; // r13
  unsigned int v14; // r15d
  signed int LastError; // ebx
  void *v16; // rcx
  DWORD dwFlags; // eax
  HINTERNET *v18; // rsi
  HINTERNET v19; // rax
  void *v20; // rcx
  unsigned __int64 v21; // rcx
  int v22; // eax
  const WCHAR *v23; // r11
  signed int v24; // r14d
  __int64 v25; // rdx
  __int64 v26; // rcx
  char v27; // al
  DWORD v28; // r14d
  BOOL v29; // r15d
  int IsCertificateTrustedForMmpc; // eax
  signed int v31; // r14d
  CEnrollmentLogger *Logger; // rax
  int v33; // edx
  signed int v34; // eax
  int v35; // r14d
  __int64 v36; // r8
  signed int v37; // eax
  int v38; // eax
  __int64 *v39; // rdx
  unsigned int *v40; // r14
  int pwszReferrer; // [rsp+20h] [rbp-A8h]
  int pwszReferrera; // [rsp+20h] [rbp-A8h]
  DWORD dwHeadersLength; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 Buffer; // [rsp+48h] [rbp-80h] BYREF
  DWORD dwBufferLength[2]; // [rsp+50h] [rbp-78h] BYREF
  DWORD v47; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v48[8]; // [rsp+60h] [rbp-68h] BYREF
  DWORD_PTR dwContext; // [rsp+68h] [rbp-60h]
  unsigned int *v50; // [rsp+70h] [rbp-58h]
  HINTERNET *v51; // [rsp+78h] [rbp-50h] BYREF
  char v52; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v11 = a2;
  *(_QWORD *)dwBufferLength = a6;
  v13 = lpBuffer;
  v50 = a10;
  v14 = 0;
  LastError = 0;
  v47 = 4;
  Buffer = 0;
  *lpBuffer = 200;
  v51 = this;
  v52 = 1;
  if ( !a4
    || (LastError = StringCchLengthA(a4, (unsigned __int64)a2, &Buffer), LastError >= 0)
    && (LastError = ULongLongToULong(Buffer, &dwOptionalLength), LastError >= 0) )
  {
    dwFlags = 0;
    if ( dword_1800AFD00 )
      dwFlags = 0x800000;
    v18 = this + 2;
    v19 = WinHttpOpenRequest(this[1], L"POST", v11, L"HTTP/1.1", 0, 0, dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      this + 2,
      v19);
    v20 = this[2];
    if ( v20 )
    {
      dwContext = (DWORD_PTR)(this + 4);
      *((_DWORD *)this + 8) = 0;
      if ( WinHttpSetStatusCallback(v20, SecureFailureCallback, 0x14000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
      {
        if ( (int)GetLastError() > 0 )
        {
          LastError = (unsigned __int16)GetLastError() | 0x80190000;
LABEL_73:
          v16 = *v18;
          goto LABEL_74;
        }
        goto LABEL_55;
      }
      while ( v14 < 2 )
      {
        dwHeadersLength = 0;
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)dwBufferLength + 8LL * v14) + 2 * v21) );
        v22 = ULongLongToULong(v21, &dwHeadersLength);
        v24 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x357,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\winhttphelper.cpp",
            (const char *)(unsigned int)v22,
            pwszReferrer);
          LastError = v24;
          goto LABEL_73;
        }
        if ( !WinHttpAddRequestHeaders(*v18, v23, dwHeadersLength, 0x20000000u) )
          goto LABEL_54;
        ++v14;
      }
      if ( WinHttpAddRequestHeaders(*v18, L"Content-Type: application/json", 0xFFFFFFFF, 0x20000000u) )
      {
        v27 = Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
        v28 = dwOptionalLength;
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
        {
          McTemplateU0q_EventWriteTransfer(
            WP_ENROLLMENT_API_PROVIDER_Context,
            HttpSendRequestDataSizeEvent,
            dwOptionalLength);
          v27 = Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
        }
        if ( (v27 & 2) != 0 )
          McTemplateU0zs_EventWriteTransfer(v26, v25, **(_QWORD **)dwBufferLength, a4);
        EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v48, "WinHttpSendRequest");
        v29 = WinHttpSendRequest(*v18, 0, 0, a4, v28, v28, dwContext);
        if ( v29 && dword_1800AFD00 )
        {
          Buffer = 0;
          dwBufferLength[0] = 8;
          wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
            &Buffer,
            0);
          if ( !WinHttpQueryOption(*v18, 0x4Eu, &Buffer, dwBufferLength) )
          {
            if ( (int)GetLastError() > 0 )
              LastError = (unsigned __int16)GetLastError() | 0x80190000;
            else
              LastError = GetLastError();
            goto LABEL_33;
          }
          dwHeadersLength = 0;
          IsCertificateTrustedForMmpc = Mmpc_Lockdown_IsCertificateTrustedForMmpc(Buffer, &dwHeadersLength);
          v31 = IsCertificateTrustedForMmpc;
          if ( IsCertificateTrustedForMmpc < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x393,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\winhttphelper.cpp",
              (const char *)(unsigned int)IsCertificateTrustedForMmpc,
              pwszReferrera);
            LastError = v31;
LABEL_33:
            wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&Buffer);
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v48);
            goto LABEL_73;
          }
          if ( !dwHeadersLength )
          {
            Logger = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogMmpcCertificationValidationFailure(Logger, v33);
            LastError = -2146762478;
            goto LABEL_33;
          }
          wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&Buffer);
        }
        EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v48);
        if ( !v29 )
        {
          v34 = GetLastError();
          LastError = v34;
          v35 = (unsigned __int16)v34;
          if ( v34 > 0 )
            v36 = (unsigned __int16)v34 | 0x80190000;
          else
            v36 = (unsigned int)v34;
          if ( (int)v36 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
            McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, SendingRequestFailedEvent, v36);
          if ( LastError == 12175 )
          {
            v37 = *(_DWORD *)dwContext;
            if ( *(_DWORD *)dwContext )
            {
              if ( v37 == 12045 || v37 == 12057 )
              {
                v37 = -2145910766;
              }
              else
              {
                LOWORD(LastError) = *(_DWORD *)dwContext;
                if ( v37 > 0 )
                  goto LABEL_47;
              }
LABEL_58:
              LastError = v37;
              goto LABEL_73;
            }
LABEL_47:
            v38 = (unsigned __int16)LastError;
            goto LABEL_57;
          }
          if ( LastError > 0 )
            LastError = v35 | 0x80190000;
          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
            goto LABEL_73;
          v39 = SendingRequestFailedEvent;
LABEL_72:
          McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, v39, (unsigned int)LastError);
          goto LABEL_73;
        }
        if ( WinHttpReceiveResponse(*v18, 0) )
        {
          if ( !WinHttpQueryHeaders(*v18, 0x20000013u, 0, v13, &v47, 0) )
          {
            if ( (int)GetLastError() > 0 )
              LastError = (unsigned __int16)GetLastError() | 0x80190000;
            else
              LastError = GetLastError();
          }
          v40 = v50;
          *v50 = 0;
          if ( *v13 == 503 || *v13 == 429 )
          {
            dwBufferLength[0] = 22;
            if ( WinHttpQueryHeaders(*v18, 0x24u, 0, &v51, dwBufferLength, 0) )
              *v40 = _o__wtol(&v51);
          }
          goto LABEL_73;
        }
      }
LABEL_54:
      if ( (int)GetLastError() <= 0 )
      {
LABEL_55:
        v37 = GetLastError();
        goto LABEL_58;
      }
      v38 = (unsigned __int16)GetLastError();
LABEL_57:
      v37 = v38 | 0x80190000;
      goto LABEL_58;
    }
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80190000;
    else
      LastError = GetLastError();
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      goto LABEL_73;
    v39 = OpenRequestFailedEvent;
    goto LABEL_72;
  }
  v16 = this[2];
LABEL_74:
  WinHttpSetStatusCallback(v16, 0, 0x14000u, 0);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180052894  mov     [rsp+arg_10], rbx
0x180052899  push    rsi
0x18005289a  push    r12
0x18005289c  push    r13
0x18005289e  push    r14
0x1800528a0  push    r15
0x1800528a2  sub     rsp, 0A0h
0x1800528a9  mov     rax, cs:__security_cookie
0x1800528b0  xor     rax, rsp
0x1800528b3  mov     [rsp+0C8h+var_38], rax
0x1800528bb  mov     r12, r9
0x1800528be  mov     r11, rdx
0x1800528c1  mov     r14, rcx
0x1800528c4  mov     rax, [rsp+0C8h+arg_28]
0x1800528cc  mov     qword ptr [rsp+0C8h+dwBufferLength], rax
0x1800528d1  mov     r13, [rsp+0C8h+lpBuffer]
0x1800528d9  mov     rax, [rsp+0C8h+arg_48]
0x1800528e1  mov     [rsp+0C8h+var_58], rax
0x1800528e6  xor     r15d, r15d
0x1800528e9  mov     ebx, r15d
0x1800528ec  mov     [rsp+0C8h+var_70], 4
0x1800528f4  mov     [rsp+0C8h+Buffer], r15
0x1800528f9  mov     dword ptr [r13+0], 0C8h
0x180052901  mov     [rsp+0C8h+var_50], rcx
0x180052906  mov     [rsp+0C8h+var_48], 1
0x18005290e  test    r9, r9
0x180052911  jz      short loc_180052947
0x180052913  lea     r8, [rsp+0C8h+Buffer]; unsigned __int64 *
0x180052918  mov     rcx, r9; char *
0x18005291b  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180052920  mov     ebx, eax
0x180052922  test    eax, eax
0x180052924  jns     short loc_18005292F
0x180052926  mov     rcx, [r14+10h]
0x18005292a  jmp     loc_180052DC8
0x18005292f  lea     rdx, [rsp+0C8h+dwOptionalLength]; unsigned int *
0x180052937  mov     rcx, [rsp+0C8h+Buffer]; unsigned __int64
0x18005293c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180052941  mov     ebx, eax
0x180052943  test    eax, eax
0x180052945  js      short loc_180052926
0x180052947  mov     eax, r15d
0x18005294a  mov     ecx, 800000h
0x18005294f  cmp     cs:dword_1800AFD00, r15d
0x180052956  cmovnz  eax, ecx
0x180052959  lea     rsi, [r14+10h]
0x18005295d  mov     [rsp+0C8h+dwFlags], eax; dwFlags
0x180052961  mov     [rsp+0C8h+ppwszAcceptTypes], r15; ppwszAcceptTypes
0x180052966  mov     [rsp+0C8h+pwszReferrer], r15; int
0x18005296b  lea     r9, pwszVersion; "HTTP/1.1"
0x180052972  mov     r8, r11; pwszObjectName
0x180052975  lea     rdx, aPost; "POST"
0x18005297c  mov     rcx, [r14+8]; hConnect
0x180052980  call    cs:__imp_WinHttpOpenRequest
0x180052986  mov     rdx, rax
0x180052989  mov     rcx, rsi
0x18005298c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180052991  mov     rcx, [rsi]; hInternet
0x180052994  test    rcx, rcx
0x180052997  jz      loc_180052D82
0x18005299d  lea     rax, [r14+20h]
0x1800529a1  mov     [rsp+0C8h+dwContext], rax
0x1800529a6  mov     [rax], r15d
0x1800529a9  xor     r9d, r9d; dwReserved
0x1800529ac  mov     r8d, 14000h; dwNotificationFlags
0x1800529b2  lea     rdx, SecureFailureCallback; lpfnInternetCallback
0x1800529b9  call    cs:__imp_WinHttpSetStatusCallback
0x1800529bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800529c3  jnz     short loc_1800529E7
0x1800529c5  call    cs:__imp_GetLastError
0x1800529cb  test    eax, eax
0x1800529cd  jle     loc_180052CBB
0x1800529d3  call    cs:__imp_GetLastError
0x1800529d9  movzx   ebx, ax
0x1800529dc  or      ebx, 80190000h
0x1800529e2  jmp     loc_180052DC5
0x1800529e7  xor     r14d, r14d
0x1800529ea  cmp     r15d, 2
0x1800529ee  jnb     short loc_180052A6B
0x1800529f0  mov     [rsp+0C8h+dwHeadersLength], r14d
0x1800529f5  mov     eax, r15d
0x1800529f8  mov     rcx, qword ptr [rsp+0C8h+dwBufferLength]
0x1800529fd  mov     r11, [rcx+rax*8]
0x180052a01  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180052a05  inc     rcx; unsigned __int64
0x180052a08  cmp     [r11+rcx*2], r14w
0x180052a0d  jnz     short loc_180052A05
0x180052a0f  lea     rdx, [rsp+0C8h+dwHeadersLength]; unsigned int *
0x180052a14  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180052a19  mov     r14d, eax
0x180052a1c  test    eax, eax
0x180052a1e  js      short loc_180052A47
0x180052a20  mov     r9d, 20000000h; dwModifiers
0x180052a26  mov     r8d, [rsp+0C8h+dwHeadersLength]; dwHeadersLength
0x180052a2b  mov     rdx, r11; lpszHeaders
0x180052a2e  mov     rcx, [rsi]; hRequest
0x180052a31  call    cs:__imp_WinHttpAddRequestHeaders
0x180052a37  xor     r14d, r14d
0x180052a3a  test    eax, eax
0x180052a3c  jz      loc_180052CB1
0x180052a42  inc     r15d
0x180052a45  jmp     short loc_1800529EA
0x180052a47  mov     rcx, [rsp+0C8h]; this
0x180052a4f  mov     r9d, r14d; char *
0x180052a52  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180052a59  mov     edx, 357h; void *
0x180052a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052a63  mov     ebx, r14d
0x180052a66  jmp     loc_180052DC5
0x180052a6b  mov     r9d, 20000000h; dwModifiers
0x180052a71  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180052a75  lea     rdx, aContentTypeApp; "Content-Type: application/json"
0x180052a7c  mov     rcx, [rsi]; hRequest
0x180052a7f  call    cs:__imp_WinHttpAddRequestHeaders
0x180052a85  test    eax, eax
0x180052a87  jz      loc_180052CB1
0x180052a8d  mov     eax, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x180052a93  mov     r14d, [rsp+0C8h+dwOptionalLength]
0x180052a9b  test    al, 1
0x180052a9d  jz      short loc_180052ABB
0x180052a9f  mov     r8d, r14d
0x180052aa2  lea     rdx, HttpSendRequestDataSizeEvent
0x180052aa9  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180052ab0  call    McTemplateU0q_EventWriteTransfer
0x180052ab5  mov     eax, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x180052abb  test    al, 2
0x180052abd  jz      short loc_180052ACF
0x180052abf  mov     r9, r12
0x180052ac2  mov     rax, qword ptr [rsp+0C8h+dwBufferLength]
0x180052ac7  mov     r8, [rax]
0x180052aca  call    McTemplateU0zs_EventWriteTransfer
0x180052acf  lea     rdx, aWinhttpsendreq_0; "WinHttpSendRequest"
0x180052ad6  lea     rcx, [rsp+0C8h+var_68]; this
0x180052adb  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x180052ae0  nop
0x180052ae1  mov     rax, [rsp+0C8h+dwContext]
0x180052ae6  mov     qword ptr [rsp+0C8h+dwFlags], rax; dwContext
0x180052aeb  mov     dword ptr [rsp+0C8h+ppwszAcceptTypes], r14d; dwTotalLength
0x180052af0  mov     dword ptr [rsp+0C8h+pwszReferrer], r14d; int
0x180052af5  mov     r9, r12; lpOptional
0x180052af8  xor     r8d, r8d; dwHeadersLength
0x180052afb  xor     edx, edx; lpszHeaders
0x180052afd  mov     rcx, [rsi]; hRequest
0x180052b00  call    cs:__imp_WinHttpSendRequest
0x180052b06  mov     r15d, eax
0x180052b09  xor     r12d, r12d
0x180052b0c  test    eax, eax
0x180052b0e  jz      loc_180052BF6
0x180052b14  cmp     cs:dword_1800AFD00, r12d
0x180052b1b  jz      loc_180052BF6
0x180052b21  mov     [rsp+0C8h+Buffer], r12
0x180052b26  mov     [rsp+0C8h+dwBufferLength], 8
0x180052b2e  xor     edx, edx
0x180052b30  lea     rcx, [rsp+0C8h+Buffer]
0x180052b35  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180052b3a  lea     r9, [rsp+0C8h+dwBufferLength]; lpdwBufferLength
0x180052b3f  lea     r8, [rsp+0C8h+Buffer]; lpBuffer
0x180052b44  lea     edx, [r12+4Eh]; dwOption
0x180052b49  mov     rcx, [rsi]; hInternet
0x180052b4c  call    cs:__imp_WinHttpQueryOption
0x180052b52  test    eax, eax
0x180052b54  jnz     short loc_180052B7B
0x180052b56  call    cs:__imp_GetLastError
0x180052b5c  test    eax, eax
0x180052b5e  jg      short loc_180052B6A
0x180052b60  call    cs:__imp_GetLastError
0x180052b66  mov     ebx, eax
0x180052b68  jmp     short loc_180052BD1
0x180052b6a  call    cs:__imp_GetLastError
0x180052b70  movzx   ebx, ax
0x180052b73  or      ebx, 80190000h
0x180052b79  jmp     short loc_180052BD1
0x180052b7b  mov     [rsp+0C8h+dwHeadersLength], r12d
0x180052b80  lea     rdx, [rsp+0C8h+dwHeadersLength]
0x180052b85  mov     rcx, [rsp+0C8h+Buffer]
0x180052b8a  call    cs:__imp_Mmpc_Lockdown_IsCertificateTrustedForMmpc
0x180052b90  mov     r14d, eax
0x180052b93  test    eax, eax
0x180052b95  jns     short loc_180052BB8
0x180052b97  mov     rcx, [rsp+0C8h]; this
0x180052b9f  mov     r9d, eax; char *
0x180052ba2  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180052ba9  mov     edx, 393h; void *
0x180052bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052bb3  mov     ebx, r14d
0x180052bb6  jmp     short loc_180052BD1
0x180052bb8  cmp     [rsp+0C8h+dwHeadersLength], r12d
0x180052bbd  jnz     short loc_180052BEB
0x180052bbf  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180052bc4  mov     rcx, rax; this
0x180052bc7  call    ?LogMmpcCertificationValidationFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogMmpcCertificationValidationFailure(long)
0x180052bcc  mov     ebx, 800B0112h
0x180052bd1  lea     rcx, [rsp+0C8h+Buffer]
0x180052bd6  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180052bdb  nop
0x180052bdc  lea     rcx, [rsp+0C8h+var_68]; this
0x180052be1  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180052be6  jmp     loc_180052DC5
0x180052beb  lea     rcx, [rsp+0C8h+Buffer]
0x180052bf0  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180052bf5  nop
0x180052bf6  lea     rcx, [rsp+0C8h+var_68]; this
0x180052bfb  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180052c00  test    r15d, r15d
0x180052c03  jnz     loc_180052CA2
0x180052c09  call    cs:__imp_GetLastError
0x180052c0f  mov     ebx, eax
0x180052c11  movzx   r14d, ax
0x180052c15  test    eax, eax
0x180052c17  jg      short loc_180052C1E
0x180052c19  mov     r8d, eax
0x180052c1c  jmp     short loc_180052C28
0x180052c1e  mov     r8d, r14d
0x180052c21  or      r8d, 80190000h
0x180052c28  test    r8d, r8d
0x180052c2b  jns     short loc_180052C49
0x180052c2d  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180052c34  jz      short loc_180052C49
0x180052c36  lea     rdx, SendingRequestFailedEvent
0x180052c3d  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180052c44  call    McTemplateU0q_EventWriteTransfer
0x180052c49  cmp     ebx, 2F8Fh
0x180052c4f  jnz     short loc_180052C7C
0x180052c51  mov     rax, [rsp+0C8h+dwContext]
0x180052c56  mov     eax, [rax]
0x180052c58  test    eax, eax
0x180052c5a  jz      short loc_180052C70
0x180052c5c  cmp     eax, 2F0Dh
0x180052c61  jz      short loc_180052C75
0x180052c63  cmp     eax, 2F19h
0x180052c68  jz      short loc_180052C75
0x180052c6a  mov     ebx, eax
0x180052c6c  test    eax, eax
0x180052c6e  jle     short loc_180052CD1
0x180052c70  movzx   eax, bx
0x180052c73  jmp     short loc_180052CCC
0x180052c75  mov     eax, 80180012h
0x180052c7a  jmp     short loc_180052CD1
0x180052c7c  test    ebx, ebx
0x180052c7e  jle     short loc_180052C89
0x180052c80  mov     ebx, r14d
0x180052c83  or      ebx, 80190000h
0x180052c89  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180052c90  jz      loc_180052DC5
0x180052c96  lea     rdx, SendingRequestFailedEvent
0x180052c9d  jmp     loc_180052DB5
0x180052ca2  xor     edx, edx; lpReserved
0x180052ca4  mov     rcx, [rsi]; hRequest
0x180052ca7  call    cs:__imp_WinHttpReceiveResponse
0x180052cad  test    eax, eax
0x180052caf  jnz     short loc_180052CD8
0x180052cb1  call    cs:__imp_GetLastError
0x180052cb7  test    eax, eax
0x180052cb9  jg      short loc_180052CC3
0x180052cbb  call    cs:__imp_GetLastError
0x180052cc1  jmp     short loc_180052CD1
0x180052cc3  call    cs:__imp_GetLastError
0x180052cc9  movzx   eax, ax
0x180052ccc  or      eax, 80190000h
0x180052cd1  mov     ebx, eax
0x180052cd3  jmp     loc_180052DC5
0x180052cd8  mov     [rsp+0C8h+ppwszAcceptTypes], r12; lpdwIndex
0x180052cdd  lea     rax, [rsp+0C8h+var_70]
0x180052ce2  mov     [rsp+0C8h+pwszReferrer], rax; lpdwBufferLength
0x180052ce7  mov     r9, r13; lpBuffer
0x180052cea  xor     r8d, r8d; pwszName
0x180052ced  mov     edx, 20000013h; dwInfoLevel
0x180052cf2  mov     rcx, [rsi]; hRequest
0x180052cf5  call    cs:__imp_WinHttpQueryHeaders
0x180052cfb  test    eax, eax
0x180052cfd  jnz     short loc_180052D22
0x180052cff  call    cs:__imp_GetLastError
0x180052d05  test    eax, eax
0x180052d07  jg      short loc_180052D13
0x180052d09  call    cs:__imp_GetLastError
0x180052d0f  mov     ebx, eax
0x180052d11  jmp     short loc_180052D22
0x180052d13  call    cs:__imp_GetLastError
0x180052d19  movzx   ebx, ax
0x180052d1c  or      ebx, 80190000h
0x180052d22  mov     r14, [rsp+0C8h+var_58]
0x180052d27  mov     [r14], r12d
0x180052d2a  cmp     dword ptr [r13+0], 1F7h
0x180052d32  jz      short loc_180052D42
0x180052d34  cmp     dword ptr [r13+0], 1ADh
0x180052d3c  jnz     loc_180052DC5
0x180052d42  mov     [rsp+0C8h+dwBufferLength], 16h
0x180052d4a  mov     [rsp+0C8h+ppwszAcceptTypes], r12; lpdwIndex
0x180052d4f  lea     rax, [rsp+0C8h+dwBufferLength]
0x180052d54  mov     [rsp+0C8h+pwszReferrer], rax; lpdwBufferLength
0x180052d59  lea     r9, [rsp+0C8h+var_50]; lpBuffer
0x180052d5e  xor     r8d, r8d; pwszName
0x180052d61  lea     edx, [r8+24h]; dwInfoLevel
0x180052d65  mov     rcx, [rsi]; hRequest
0x180052d68  call    cs:__imp_WinHttpQueryHeaders
0x180052d6e  test    eax, eax
0x180052d70  jz      short loc_180052DC5
0x180052d72  lea     rcx, [rsp+0C8h+var_50]
0x180052d77  call    cs:__imp__o__wtol
0x180052d7d  mov     [r14], eax
  ... truncated ...
```
