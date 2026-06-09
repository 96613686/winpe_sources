# WinHttpHelper::SendRequest(ushort const *,char const *,ulong,ulong,ushort const * *,ulong,int *,ulong *)

- ea: `0x180020ccc`
- end: `0x180021451`
- name: `?SendRequest@WinHttpHelper@@QEAAJPEBGPEBDKKPEAPEBGKPEAHPEAK@Z`
- size: `1925`
- prototype: `int(WinHttpHelper *__hidden this, const unsigned __int16 *, const char *, unsigned int, unsigned int, const unsigned __int16 **, unsigned int, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021458`

## callees

- `0x1800026d0`
- `0x18000b0f4`
- `0x180012f70`
- `0x1800141b0`
- `0x180019ec0`
- `0x18001e494`
- `0x180020ccc`
- `0x180021e6c`
- `0x180041410`
- `0x180041474`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002136f`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002136f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002112b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002112b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020e59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020e59`
- `WINHTTP!WinHttpCloseHandle` at `0x180020e4b`
- `WINHTTP!WinHttpCloseHandle` at `0x180020e4b`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800212c2`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021353`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800212c2`
- `WINHTTP!WinHttpQueryHeaders` at `0x180021353`
- `WINHTTP!WinHttpReceiveResponse` at `0x18002128b`
- `WINHTTP!WinHttpReceiveResponse` at `0x18002128b`
- `WINHTTP!WinHttpSendRequest` at `0x1800210d1`
- `WINHTTP!WinHttpSendRequest` at `0x180021185`
- `WINHTTP!WinHttpSendRequest` at `0x1800210d1`
- `WINHTTP!WinHttpSendRequest` at `0x180021185`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020f7a`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180021031`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180020f7a`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180021031`
- `WINHTTP!WinHttpSetOption` at `0x180020eab`
- `WINHTTP!WinHttpSetOption` at `0x18002111b`
- `WINHTTP!WinHttpSetOption` at `0x180020eab`
- `WINHTTP!WinHttpSetOption` at `0x18002111b`
- `WINHTTP!WinHttpOpenRequest` at `0x180020e22`
- `WINHTTP!WinHttpOpenRequest` at `0x180020e22`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180020f28`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180021414`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180020f28`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180021414`

## string_xrefs

- `0x180021026`: `Content-Type: application/soap+xml; charset=utf-8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinHttpHelper::SendRequest(
        HINTERNET *this,
        const unsigned __int16 *a2,
        char *a3,
        int a4,
        char a5,
        const unsigned __int16 **a6,
        unsigned int a7,
        int *a8,
        unsigned int *a9)
{
  unsigned __int64 v9; // rsi
  __int64 v13; // rcx
  char *v14; // rax
  unsigned int v15; // ebx
  DWORD dwFlags; // eax
  const WCHAR *v17; // rdx
  void *v18; // r14
  void *v19; // r15
  DWORD LastError; // ebx
  signed int v21; // eax
  signed int *v22; // r15
  const char *v23; // rax
  int v24; // ebx
  const WCHAR *v25; // rdx
  unsigned __int64 v26; // r8
  unsigned int v27; // eax
  CEnrollmentLogger *Logger; // rax
  __int64 v29; // r8
  char v30; // al
  __int64 v31; // rcx
  BOOL v32; // ebx
  signed int v33; // eax
  __int64 v34; // rcx
  signed int v35; // eax
  __int64 v36; // r8
  signed int v37; // ebx
  __int64 *v38; // rdx
  _DWORD *v39; // rbx
  unsigned int *v40; // rsi
  unsigned int v41; // eax
  int pwszReferrer; // [rsp+20h] [rbp-E8h]
  int v44; // [rsp+40h] [rbp-C8h] BYREF
  DWORD Buffer; // [rsp+48h] [rbp-C0h] BYREF
  int v46; // [rsp+50h] [rbp-B8h] BYREF
  const char *v47; // [rsp+58h] [rbp-B0h]
  DWORD dwBufferLength; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID lpBuffer; // [rsp+68h] [rbp-A0h]
  unsigned int *v50; // [rsp+70h] [rbp-98h]
  _QWORD v51[2]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v52[16]; // [rsp+88h] [rbp-80h] BYREF
  DWORD *p_Buffer; // [rsp+98h] [rbp-70h]
  __int64 v54; // [rsp+A0h] [rbp-68h]
  HINTERNET *v55; // [rsp+A8h] [rbp-60h] BYREF
  char v56; // [rsp+B0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  LODWORD(v9) = a4;
  v47 = (const char *)a6;
  lpBuffer = a8;
  v50 = a9;
  v44 = 0;
  dwBufferLength = 4;
  v51[0] = "WinHttpHelper::SendRequest";
  v51[1] = &v44;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, SendingRequestToServerEvent, a2);
  *a8 = 200;
  v55 = this;
  v56 = 1;
  if ( !a3 )
    goto LABEL_10;
  v13 = 0x7FFFFFFF;
  v14 = a3;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = v13 == 0 ? 0x80070057 : 0;
  v9 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
  v44 = v15;
  if ( v13 )
  {
    if ( v9 > 0xFFFFFFFF )
    {
      v15 = -2147024362;
      v44 = -2147024362;
      goto LABEL_91;
    }
    v44 = 0;
LABEL_10:
    dwFlags = 0;
    if ( dword_1800706BC )
      dwFlags = 0x800000;
    v17 = L"POST";
    if ( !a3 )
      v17 = L"GET";
    v18 = WinHttpOpenRequest(this[1], v17, a2, L"HTTP/1.1", 0, 0, dwFlags);
    v19 = this[2];
    if ( v19 )
    {
      LastError = GetLastError();
      WinHttpCloseHandle(v19);
      SetLastError(LastError);
    }
    this[2] = v18;
    if ( v18 )
    {
      v46 = 0;
      if ( !dword_1800706BC || (a5 & 0x10) == 0 || (Buffer = 256, WinHttpSetOption(v18, 0x1Fu, &Buffer, 4u)) )
      {
        v22 = (signed int *)(this + 4);
        *((_DWORD *)this + 8) = 0;
        if ( WinHttpSetStatusCallback(this[2], SecureFailureCallback, 0x10000u, 0) != (WINHTTP_STATUS_CALLBACK)-1LL )
        {
          v23 = v47;
          if ( v47 )
          {
            v24 = 0;
            while ( 1 )
            {
              v25 = *(const WCHAR **)&v23[8 * v24];
              v26 = -1;
              do
                ++v26;
              while ( v25[v26] );
              if ( v26 > 0xFFFFFFFF )
              {
                v15 = -2147024362;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x268,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\winhttphelper.cpp",
                  (const char *)0x80070216LL,
                  pwszReferrer);
                goto LABEL_91;
              }
              if ( !WinHttpAddRequestHeaders(this[2], v25, v26, 0x20000000u) )
                break;
              if ( (unsigned int)++v24 >= 2 )
                goto LABEL_41;
              v23 = v47;
            }
            if ( (int)GetLastError() > 0 )
              v27 = (unsigned __int16)GetLastError() | 0x80190000;
            else
              v27 = GetLastError();
            v44 = v27;
            Logger = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogAddingExtraHeaderFailure(Logger, v44, *(const unsigned __int16 **)&v47[8 * v24]);
            goto LABEL_90;
          }
LABEL_41:
          if ( WinHttpAddRequestHeaders(
                 this[2],
                 L"Content-Type: application/soap+xml; charset=utf-8",
                 0xFFFFFFFF,
                 0x20000000u) )
          {
            v30 = Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
            {
              Buffer = v9;
              p_Buffer = &Buffer;
              v54 = 4;
              McGenEventWrite_EventWriteTransfer(
                WP_ENROLLMENT_API_PROVIDER_Context,
                HttpSendRequestDataSizeEvent,
                v29,
                2,
                v52);
              v30 = Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
            }
            v47 = "WinHttpSendRequest";
            if ( (v30 & 1) != 0 )
              McTemplateU0s_EventWriteTransfer("WinHttpSendRequest", EnteringScopeEvent, "WinHttpSendRequest");
            v32 = WinHttpSendRequest(this[2], 0, 0, a3, v9, v9, (DWORD_PTR)(this + 4));
            if ( !v32 && *v22 == 12038 && (int)CheckCertSAN(this[2]) >= 0 )
            {
              v46 |= 0x1000u;
              if ( !WinHttpSetOption(this[2], v32 + 31, &v46, v32 + 4) )
              {
                v33 = GetLastError();
                if ( v33 > 0 )
                  v33 = (unsigned __int16)v33 | 0x80070000;
                v44 = v33;
                if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
                  McTemplateU0s_EventWriteTransfer(v34, LeavingScopeEvent, "WinHttpSendRequest");
                goto LABEL_90;
              }
              v32 = WinHttpSendRequest(this[2], 0, 0, a3, v9, v9, (DWORD_PTR)(this + 4));
            }
            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
              McTemplateU0s_EventWriteTransfer(v31, LeavingScopeEvent, "WinHttpSendRequest");
            if ( !v32 )
            {
              v35 = GetLastError();
              v37 = v35;
              if ( v35 > 0 )
                v35 = (unsigned __int16)v35 | 0x80190000;
              v44 = v35;
              if ( v35 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
              {
                Buffer = v35;
                p_Buffer = &Buffer;
                v54 = 4;
                McGenEventWrite_EventWriteTransfer(
                  WP_ENROLLMENT_API_PROVIDER_Context,
                  SendingRequestFailedEvent,
                  v36,
                  2,
                  v52);
              }
              if ( v37 == 12175 )
              {
                v21 = *v22;
                if ( !*v22 )
                  v21 = 12175;
                if ( v21 == 12045 || v21 == 12057 )
                {
                  v21 = -2145910766;
                  goto LABEL_26;
                }
                if ( v21 > 0 )
                  goto LABEL_25;
                goto LABEL_26;
              }
              if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
                goto LABEL_90;
              if ( v37 > 0 )
                v37 = (unsigned __int16)v37 | 0x80190000;
              Buffer = v37;
              v38 = SendingRequestFailedEvent;
LABEL_89:
              p_Buffer = &Buffer;
              v54 = 4;
              McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, v38, v36, 2, v52);
              goto LABEL_90;
            }
            if ( WinHttpReceiveResponse(this[2], 0) )
            {
              v39 = lpBuffer;
              if ( !WinHttpQueryHeaders(this[2], 0x20000013u, 0, lpBuffer, &dwBufferLength, 0) )
              {
                if ( (int)GetLastError() > 0 )
                  v44 = (unsigned __int16)GetLastError() | 0x80190000;
                else
                  v44 = GetLastError();
              }
              v40 = v50;
              *v50 = 0;
              if ( *v39 == 503 || *v39 == 429 )
              {
                Buffer = 22;
                if ( WinHttpQueryHeaders(this[2], 0x24u, 0, &v55, &Buffer, 0) )
                  *v40 = _o__wtol(&v55);
              }
              goto LABEL_90;
            }
          }
        }
      }
      if ( (int)GetLastError() > 0 )
      {
        LOWORD(v21) = GetLastError();
LABEL_25:
        v21 = (unsigned __int16)v21 | 0x80190000;
        goto LABEL_26;
      }
      v21 = GetLastError();
LABEL_26:
      v44 = v21;
LABEL_90:
      v15 = v44;
      goto LABEL_91;
    }
    if ( (int)GetLastError() > 0 )
      v41 = (unsigned __int16)GetLastError() | 0x80190000;
    else
      v41 = GetLastError();
    v44 = v41;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      goto LABEL_90;
    Buffer = v41;
    v38 = OpenRequestFailedEvent;
    goto LABEL_89;
  }
LABEL_91:
  WinHttpSetStatusCallback(this[2], 0, 0x10000u, 0);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v51);
  return v15;
}

```

## disassembly

```asm
0x180020ccc  push    rbx
0x180020cce  push    rsi
0x180020ccf  push    rdi
0x180020cd0  push    r12
0x180020cd2  push    r13
0x180020cd4  push    r14
0x180020cd6  push    r15
0x180020cd8  sub     rsp, 0D0h
0x180020cdf  mov     rax, cs:__security_cookie
0x180020ce6  xor     rax, rsp
0x180020ce9  mov     [rsp+108h+var_48], rax
0x180020cf1  mov     esi, r9d
0x180020cf4  mov     r13, r8
0x180020cf7  mov     r14, rdx
0x180020cfa  mov     rdi, rcx
0x180020cfd  mov     r8, [rsp+108h+arg_28]
0x180020d05  mov     [rsp+108h+var_B0], r8
0x180020d0a  mov     rbx, [rsp+108h+arg_38]
0x180020d12  mov     [rsp+108h+lpBuffer], rbx
0x180020d17  mov     rax, [rsp+108h+arg_40]
0x180020d1f  mov     [rsp+108h+var_98], rax
0x180020d24  xor     r12d, r12d
0x180020d27  mov     [rsp+108h+var_C8], r12d
0x180020d2c  mov     [rsp+108h+dwBufferLength], 4
0x180020d34  lea     rax, aWinhttphelperS; "WinHttpHelper::SendRequest"
0x180020d3b  mov     [rsp+108h+var_90], rax
0x180020d40  lea     rax, [rsp+108h+var_C8]
0x180020d45  mov     [rsp+108h+var_88], rax
0x180020d4d  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x180020d54  jz      short loc_180020D6C
0x180020d56  mov     r8, rdx
0x180020d59  lea     rdx, SendingRequestToServerEvent
0x180020d60  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180020d67  call    McTemplateU0z_EventWriteTransfer
0x180020d6c  mov     dword ptr [rbx], 0C8h
0x180020d72  mov     [rsp+108h+var_60], rdi
0x180020d7a  mov     [rsp+108h+var_58], 1
0x180020d82  mov     r8d, 0FFFFFFFFh
0x180020d88  test    r13, r13
0x180020d8b  jz      short loc_180020DDF
0x180020d8d  mov     edx, 7FFFFFFFh
0x180020d92  mov     ecx, edx
0x180020d94  mov     rax, r13
0x180020d97  cmp     [rax], r12b
0x180020d9a  jz      short loc_180020DA5
0x180020d9c  inc     rax
0x180020d9f  sub     rcx, 1
0x180020da3  jnz     short loc_180020D97
0x180020da5  mov     rax, rcx
0x180020da8  neg     rax
0x180020dab  sbb     ebx, ebx
0x180020dad  not     ebx
0x180020daf  and     ebx, 80070057h
0x180020db5  mov     rax, rcx
0x180020db8  sub     rdx, rcx
0x180020dbb  neg     rax
0x180020dbe  sbb     rsi, rsi
0x180020dc1  and     rsi, rdx
0x180020dc4  mov     [rsp+108h+var_C8], ebx
0x180020dc8  test    rcx, rcx
0x180020dcb  jz      loc_180020EE5
0x180020dd1  cmp     rsi, r8
0x180020dd4  ja      loc_180020EDC
0x180020dda  mov     [rsp+108h+var_C8], r12d
0x180020ddf  mov     eax, r12d
0x180020de2  mov     ecx, 800000h
0x180020de7  cmp     cs:dword_1800706BC, r12d
0x180020dee  cmovnz  eax, ecx
0x180020df1  lea     rcx, aGet; "GET"
0x180020df8  lea     rdx, pwszVerb; "POST"
0x180020dff  test    r13, r13
0x180020e02  cmovz   rdx, rcx; pwszVerb
0x180020e06  mov     [rsp+108h+dwFlags], eax; dwFlags
0x180020e0a  mov     [rsp+108h+ppwszAcceptTypes], r12; ppwszAcceptTypes
0x180020e0f  mov     [rsp+108h+pwszReferrer], r12; int
0x180020e14  lea     r9, pwszVersion; "HTTP/1.1"
0x180020e1b  mov     r8, r14; pwszObjectName
0x180020e1e  mov     rcx, [rdi+8]; hConnect
0x180020e22  call    cs:__imp_WinHttpOpenRequest
0x180020e29  nop     dword ptr [rax+rax+00h]
0x180020e2e  mov     r14, rax
0x180020e31  mov     r15, [rdi+10h]
0x180020e35  test    r15, r15
0x180020e38  jz      short loc_180020E65
0x180020e3a  call    cs:__imp_GetLastError
0x180020e41  nop     dword ptr [rax+rax+00h]
0x180020e46  mov     ebx, eax
0x180020e48  mov     rcx, r15; hInternet
0x180020e4b  call    cs:__imp_WinHttpCloseHandle
0x180020e52  nop     dword ptr [rax+rax+00h]
0x180020e57  mov     ecx, ebx; dwErrCode
0x180020e59  call    cs:__imp_SetLastError
0x180020e60  nop     dword ptr [rax+rax+00h]
0x180020e65  mov     [rdi+10h], r14
0x180020e69  xor     ebx, ebx
0x180020e6b  mov     r12d, 10000h
0x180020e71  test    r14, r14
0x180020e74  jz      loc_180021382
0x180020e7a  mov     [rsp+108h+var_B8], ebx
0x180020e7e  cmp     cs:dword_1800706BC, ebx
0x180020e84  jz      loc_180020F0D
0x180020e8a  test    [rsp+108h+arg_20], 10h
0x180020e92  jz      short loc_180020F0D
0x180020e94  mov     [rsp+108h+Buffer], 100h
0x180020e9c  lea     r9d, [rbx+4]; dwBufferLength
0x180020ea0  lea     r8, [rsp+108h+Buffer]; lpBuffer
0x180020ea5  lea     edx, [rbx+1Fh]; dwOption
0x180020ea8  mov     rcx, r14; hInternet
0x180020eab  call    cs:__imp_WinHttpSetOption
0x180020eb2  nop     dword ptr [rax+rax+00h]
0x180020eb7  xor     r14d, r14d
0x180020eba  test    eax, eax
0x180020ebc  jnz     short loc_180020F10
0x180020ebe  call    cs:__imp_GetLastError
0x180020ec5  nop     dword ptr [rax+rax+00h]
0x180020eca  test    eax, eax
0x180020ecc  jg      short loc_180020EF0
0x180020ece  call    cs:__imp_GetLastError
0x180020ed5  nop     dword ptr [rax+rax+00h]
0x180020eda  jmp     short loc_180020F04
0x180020edc  mov     ebx, 80070216h
0x180020ee1  mov     [rsp+108h+var_C8], ebx
0x180020ee5  mov     r8d, 10000h
0x180020eeb  jmp     loc_18002140B
0x180020ef0  call    cs:__imp_GetLastError
0x180020ef7  nop     dword ptr [rax+rax+00h]
0x180020efc  movzx   eax, ax
0x180020eff  or      eax, 80190000h
0x180020f04  mov     [rsp+108h+var_C8], eax
0x180020f08  jmp     loc_180021404
0x180020f0d  xor     r14d, r14d
0x180020f10  lea     r15, [rdi+20h]
0x180020f14  mov     [r15], r14d
0x180020f17  xor     r9d, r9d; dwReserved
0x180020f1a  mov     r8d, r12d; dwNotificationFlags
0x180020f1d  lea     rdx, SecureFailureCallback; lpfnInternetCallback
0x180020f24  mov     rcx, [rdi+10h]; hInternet
0x180020f28  call    cs:__imp_WinHttpSetStatusCallback
0x180020f2f  nop     dword ptr [rax+rax+00h]
0x180020f34  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020f38  jz      short loc_180020EBE
0x180020f3a  mov     rax, [rsp+108h+var_B0]
0x180020f3f  test    rax, rax
0x180020f42  jz      loc_18002101A
0x180020f48  mov     ebx, r14d
0x180020f4b  mov     r14d, ebx
0x180020f4e  mov     rdx, [rax+r14*8]; lpszHeaders
0x180020f52  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020f56  xor     eax, eax
0x180020f58  inc     r8; dwHeadersLength
0x180020f5b  cmp     [rdx+r8*2], ax
0x180020f60  jnz     short loc_180020F58
0x180020f62  mov     eax, 0FFFFFFFFh
0x180020f67  cmp     r8, rax
0x180020f6a  ja      loc_180020FF1
0x180020f70  mov     r9d, 20000000h; dwModifiers
0x180020f76  mov     rcx, [rdi+10h]; hRequest
0x180020f7a  call    cs:__imp_WinHttpAddRequestHeaders
0x180020f81  nop     dword ptr [rax+rax+00h]
0x180020f86  test    eax, eax
0x180020f88  jz      short loc_180020F9C
0x180020f8a  inc     ebx
0x180020f8c  cmp     ebx, 2
0x180020f8f  jnb     loc_180021017
0x180020f95  mov     rax, [rsp+108h+var_B0]
0x180020f9a  jmp     short loc_180020F4B
0x180020f9c  call    cs:__imp_GetLastError
0x180020fa3  nop     dword ptr [rax+rax+00h]
0x180020fa8  test    eax, eax
0x180020faa  jg      short loc_180020FBA
0x180020fac  call    cs:__imp_GetLastError
0x180020fb3  nop     dword ptr [rax+rax+00h]
0x180020fb8  jmp     short loc_180020FCE
0x180020fba  call    cs:__imp_GetLastError
0x180020fc1  nop     dword ptr [rax+rax+00h]
0x180020fc6  movzx   eax, ax
0x180020fc9  or      eax, 80190000h
0x180020fce  mov     [rsp+108h+var_C8], eax
0x180020fd2  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180020fd7  mov     r8, [rsp+108h+var_B0]
0x180020fdc  mov     r8, [r8+r14*8]; unsigned __int16 *
0x180020fe0  mov     edx, [rsp+108h+var_C8]; int
0x180020fe4  mov     rcx, rax; this
0x180020fe7  call    ?LogAddingExtraHeaderFailure@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogAddingExtraHeaderFailure(long,ushort const *)
0x180020fec  jmp     loc_180021404
0x180020ff1  mov     rcx, [rsp+108h]; this
0x180020ff9  mov     ebx, 80070216h
0x180020ffe  mov     r9d, ebx; char *
0x180021001  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180021008  mov     edx, 268h; void *
0x18002100d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021012  jmp     loc_180021408
0x180021017  xor     r14d, r14d
0x18002101a  mov     r9d, 20000000h; dwModifiers
0x180021020  mov     r8d, 0FFFFFFFFh; dwHeadersLength
0x180021026  lea     rdx, aContentTypeApp_0; "Content-Type: application/soap+xml; cha"...
0x18002102d  mov     rcx, [rdi+10h]; hRequest
0x180021031  call    cs:__imp_WinHttpAddRequestHeaders
0x180021038  nop     dword ptr [rax+rax+00h]
0x18002103d  test    eax, eax
0x18002103f  jz      loc_180020EBE
0x180021045  mov     eax, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x18002104b  test    al, 1
0x18002104d  jz      short loc_180021098
0x18002104f  mov     [rsp+108h+Buffer], esi
0x180021053  lea     rax, [rsp+108h+Buffer]
0x180021058  mov     [rsp+108h+var_70], rax
0x180021060  mov     [rsp+108h+var_68], 4
0x18002106c  lea     rax, [rsp+108h+var_80]
0x180021074  mov     [rsp+108h+pwszReferrer], rax
0x180021079  mov     r9d, 2
0x18002107f  lea     rdx, HttpSendRequestDataSizeEvent
0x180021086  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18002108d  call    McGenEventWrite_EventWriteTransfer
0x180021092  mov     eax, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x180021098  lea     rcx, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18002109f  mov     [rsp+108h+var_B0], rcx
0x1800210a4  test    al, 1
0x1800210a6  jz      short loc_1800210B8
0x1800210a8  mov     r8, rcx
0x1800210ab  lea     rdx, EnteringScopeEvent
0x1800210b2  call    McTemplateU0s_EventWriteTransfer
0x1800210b7  nop
0x1800210b8  mov     qword ptr [rsp+108h+dwFlags], r15; dwContext
0x1800210bd  mov     dword ptr [rsp+108h+ppwszAcceptTypes], esi; dwTotalLength
0x1800210c1  mov     dword ptr [rsp+108h+pwszReferrer], esi; dwOptionalLength
0x1800210c5  mov     r9, r13; lpOptional
0x1800210c8  xor     r8d, r8d; dwHeadersLength
0x1800210cb  xor     edx, edx; lpszHeaders
0x1800210cd  mov     rcx, [rdi+10h]; hRequest
0x1800210d1  call    cs:__imp_WinHttpSendRequest
0x1800210d8  nop     dword ptr [rax+rax+00h]
0x1800210dd  mov     ebx, eax
0x1800210df  test    eax, eax
0x1800210e1  jnz     loc_180021193
0x1800210e7  cmp     dword ptr [r15], 2F06h
0x1800210ee  jnz     loc_180021193
0x1800210f4  mov     rcx, [rdi+10h]
0x1800210f8  call    CheckCertSAN
0x1800210fd  test    eax, eax
0x1800210ff  js      loc_180021193
0x180021105  bts     [rsp+108h+var_B8], 0Ch
0x18002110b  lea     r9d, [rbx+4]; dwBufferLength
0x18002110f  lea     r8, [rsp+108h+var_B8]; lpBuffer
0x180021114  lea     edx, [rbx+1Fh]; dwOption
0x180021117  mov     rcx, [rdi+10h]; hInternet
0x18002111b  call    cs:__imp_WinHttpSetOption
0x180021122  nop     dword ptr [rax+rax+00h]
0x180021127  test    eax, eax
0x180021129  jnz     short loc_18002116C
0x18002112b  call    cs:__imp_GetLastError
0x180021132  nop     dword ptr [rax+rax+00h]
0x180021137  test    eax, eax
0x180021139  jle     short loc_180021143
0x18002113b  movzx   eax, ax
0x18002113e  or      eax, 80070000h
0x180021143  mov     [rsp+108h+var_C8], eax
0x180021147  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18002114e  jz      loc_180021404
0x180021154  lea     r8, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18002115b  lea     rdx, LeavingScopeEvent
0x180021162  call    McTemplateU0s_EventWriteTransfer
0x180021167  jmp     loc_180021404
0x18002116c  mov     qword ptr [rsp+108h+dwFlags], r15; dwContext
0x180021171  mov     dword ptr [rsp+108h+ppwszAcceptTypes], esi; dwTotalLength
0x180021175  mov     dword ptr [rsp+108h+pwszReferrer], esi; dwOptionalLength
0x180021179  mov     r9, r13; lpOptional
0x18002117c  xor     r8d, r8d; dwHeadersLength
0x18002117f  xor     edx, edx; lpszHeaders
0x180021181  mov     rcx, [rdi+10h]; hRequest
0x180021185  call    cs:__imp_WinHttpSendRequest
0x18002118c  nop     dword ptr [rax+rax+00h]
0x180021191  mov     ebx, eax
0x180021193  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18002119a  jz      short loc_1800211AF
0x18002119c  lea     r8, aWinhttpsendreq_0; "WinHttpSendRequest"
0x1800211a3  lea     rdx, LeavingScopeEvent
0x1800211aa  call    McTemplateU0s_EventWriteTransfer
0x1800211af  test    ebx, ebx
0x1800211b1  jnz     loc_180021285
0x1800211b7  call    cs:__imp_GetLastError
0x1800211be  nop     dword ptr [rax+rax+00h]
0x1800211c3  mov     ebx, eax
0x1800211c5  test    eax, eax
0x1800211c7  jle     short loc_1800211D1
0x1800211c9  movzx   eax, bx
0x1800211cc  or      eax, 80190000h
0x1800211d1  mov     [rsp+108h+var_C8], eax
0x1800211d5  test    eax, eax
0x1800211d7  jns     short loc_180021225
0x1800211d9  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800211e0  jz      short loc_180021225
0x1800211e2  mov     [rsp+108h+Buffer], eax
0x1800211e6  lea     rax, [rsp+108h+Buffer]
0x1800211eb  mov     [rsp+108h+var_70], rax
0x1800211f3  mov     [rsp+108h+var_68], 4
0x1800211ff  lea     rax, [rsp+108h+var_80]
0x180021207  mov     [rsp+108h+pwszReferrer], rax
0x18002120c  mov     r9d, 2
0x180021212  lea     rdx, SendingRequestFailedEvent
  ... truncated ...
```
