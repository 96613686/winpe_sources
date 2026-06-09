# WinHttpHelper::MmpcSendRequest(ushort const *,ushort const *,char const *,ulong,ushort const * *,ulong,ulong,int *,ulong *)

- ea: `0x18001ed6c`
- end: `0x18001f58e`
- name: `?MmpcSendRequest@WinHttpHelper@@QEAAJPEBG0PEBDKPEAPEBGKKPEAHPEAK@Z`
- size: `2082`
- prototype: `int(WinHttpHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const char *, unsigned int, const unsigned __int16 **, unsigned int, unsigned int, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f594`

## callees

- `0x1800026d0`
- `0x18000b0f4`
- `0x180012f70`
- `0x18001ed6c`
- `0x180021e6c`
- `0x180041410`
- `0x180043b4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001f45b`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001f45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f27c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f47f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f27c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f47f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eeaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001eeaa`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsCertificateTrustedForMmpc` at `0x18001f188`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsCertificateTrustedForMmpc` at `0x18001f188`
- `CRYPT32!CertFreeCertificateContext` at `0x18001f1c1`
- `CRYPT32!CertFreeCertificateContext` at `0x18001f20b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001f24b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001f1c1`
- `CRYPT32!CertFreeCertificateContext` at `0x18001f20b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001f24b`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ee9c`
- `WINHTTP!WinHttpCloseHandle` at `0x18001ee9c`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001f3b1`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001f43f`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001f3b1`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001f43f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001f37a`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001f37a`
- `WINHTTP!WinHttpSendRequest` at `0x18001f0ec`
- `WINHTTP!WinHttpSendRequest` at `0x18001f0ec`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001ef50`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001ef82`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001ef50`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001ef82`
- `WINHTTP!WinHttpQueryOption` at `0x18001f132`
- `WINHTTP!WinHttpQueryOption` at `0x18001f132`
- `WINHTTP!WinHttpOpenRequest` at `0x18001ee73`
- `WINHTTP!WinHttpOpenRequest` at `0x18001ee73`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001eedd`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001f55c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001eedd`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001f55c`

## string_xrefs

- `0x18001ef77`: `Content-Type: application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinHttpHelper::MmpcSendRequest(
        HINTERNET *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char *a4,
        unsigned int a5,
        const unsigned __int16 **a6,
        unsigned int a7,
        unsigned int a8,
        int *a9,
        unsigned int *a10)
{
  __int64 v11; // rcx
  char *v12; // rax
  signed int v13; // ebx
  unsigned __int64 v14; // r12
  DWORD dwFlags; // eax
  void *v16; // rdi
  void *v17; // r14
  DWORD LastError; // ebx
  WINHTTP_STATUS_CALLBACK v19; // rax
  __int64 v20; // rdi
  int v21; // ebx
  unsigned int i; // ebx
  const WCHAR *v23; // rdx
  unsigned __int64 v24; // r8
  char v25; // al
  const wchar_t *v26; // rax
  __int64 v27; // rcx
  unsigned int v28; // ecx
  void *v29; // rbx
  int v30; // ecx
  const char *v31; // rax
  LPVOID v32; // rcx
  BOOL v33; // edi
  int IsCertificateTrustedForMmpc; // eax
  LPVOID v35; // rcx
  CEnrollmentLogger *Logger; // rax
  int v37; // edx
  LPVOID v38; // rcx
  signed int v39; // eax
  __int64 v40; // r8
  signed int v41; // edi
  int v42; // ebx
  bool v43; // sf
  _DWORD *v44; // rdi
  unsigned int *v45; // r15
  unsigned int v46; // eax
  __int64 v47; // r8
  int pwszReferrer; // [rsp+20h] [rbp-E8h]
  int pwszReferrera; // [rsp+20h] [rbp-E8h]
  DWORD dwBufferLength[2]; // [rsp+40h] [rbp-C8h] BYREF
  int v52; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID lpOptional; // [rsp+50h] [rbp-B8h] BYREF
  DWORD v54; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID lpBuffer; // [rsp+60h] [rbp-A8h]
  unsigned int *v56; // [rsp+68h] [rbp-A0h]
  const char *v57; // [rsp+70h] [rbp-98h]
  _BYTE v58[16]; // [rsp+78h] [rbp-90h] BYREF
  DWORD *v59; // [rsp+88h] [rbp-80h]
  __int64 v60; // [rsp+90h] [rbp-78h]
  const char *v61; // [rsp+98h] [rbp-70h]
  int v62; // [rsp+A0h] [rbp-68h]
  int v63; // [rsp+A4h] [rbp-64h]
  HINTERNET *Buffer; // [rsp+A8h] [rbp-60h] BYREF
  char v65; // [rsp+B0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  lpOptional = a4;
  *(_QWORD *)dwBufferLength = a6;
  lpBuffer = a9;
  v56 = a10;
  v54 = 4;
  *a9 = 200;
  Buffer = this;
  v65 = 1;
  if ( a4 )
  {
    v11 = 0x7FFFFFFF;
    v12 = a4;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    v13 = v11 == 0 ? 0x80070057 : 0;
    v14 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
    if ( !v11 )
      goto LABEL_103;
    if ( v14 > 0xFFFFFFFF )
    {
      v13 = -2147024362;
      goto LABEL_103;
    }
  }
  else
  {
    LODWORD(v14) = a5;
  }
  dwFlags = 0;
  if ( dword_1800706BC )
    dwFlags = 0x800000;
  v16 = WinHttpOpenRequest(this[1], L"POST", a2, L"HTTP/1.1", 0, 0, dwFlags);
  v17 = this[2];
  if ( v17 )
  {
    LastError = GetLastError();
    WinHttpCloseHandle(v17);
    SetLastError(LastError);
  }
  this[2] = v16;
  if ( !v16 )
  {
    if ( (int)GetLastError() > 0 )
      v13 = (unsigned __int16)GetLastError() | 0x80190000;
    else
      v13 = GetLastError();
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      dwBufferLength[0] = v13;
      v59 = dwBufferLength;
      v60 = 4;
      McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, OpenRequestFailedEvent, v47, 2, v58);
    }
    goto LABEL_103;
  }
  *((_DWORD *)this + 8) = 0;
  v19 = WinHttpSetStatusCallback(v16, SecureFailureCallback, 0x14000u, 0);
  v20 = -1;
  if ( v19 == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    if ( (int)GetLastError() > 0 )
    {
      v21 = (unsigned __int16)GetLastError();
LABEL_77:
      v13 = v21 | 0x80190000;
      goto LABEL_103;
    }
    goto LABEL_94;
  }
  for ( i = 0; i < 2; ++i )
  {
    v23 = a6[i];
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( v24 > 0xFFFFFFFF )
    {
      v13 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x357,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\winhttphelper.cpp",
        (const char *)0x80070216LL,
        pwszReferrer);
      goto LABEL_103;
    }
    if ( !WinHttpAddRequestHeaders(this[2], v23, v24, 0x20000000u) )
      goto LABEL_93;
  }
  if ( !WinHttpAddRequestHeaders(this[2], L"Content-Type: application/json", 0xFFFFFFFF, 0x20000000u) )
  {
LABEL_93:
    if ( (int)GetLastError() > 0 )
    {
      v46 = (unsigned __int16)GetLastError() | 0x80190000;
      goto LABEL_96;
    }
LABEL_94:
    v46 = GetLastError();
LABEL_96:
    v13 = v46;
    goto LABEL_103;
  }
  v25 = Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
  {
    v52 = v14;
    v59 = (DWORD *)&v52;
    v60 = 4;
    McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, HttpSendRequestDataSizeEvent, 0, 2, v58);
    v25 = Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
  }
  if ( (v25 & 2) != 0 )
  {
    v26 = **(const wchar_t ***)dwBufferLength;
    if ( **(_QWORD **)dwBufferLength )
    {
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      v28 = 2 * v27 + 2;
    }
    else
    {
      v26 = L"NULL";
      v28 = 10;
    }
    v59 = (DWORD *)v26;
    v60 = v28;
    v29 = lpOptional;
    if ( lpOptional )
    {
      do
        ++v20;
      while ( *((_BYTE *)lpOptional + v20) );
      v30 = v20 + 1;
    }
    else
    {
      v30 = 5;
    }
    v31 = (const char *)lpOptional;
    if ( !lpOptional )
      v31 = "NULL";
    v61 = v31;
    v62 = v30;
    v63 = 0;
    McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, MmpcDiscoveryRequestMessage, 0, 3, v58);
    v25 = Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
  }
  else
  {
    v29 = lpOptional;
  }
  v57 = "WinHttpSendRequest";
  if ( (v25 & 1) != 0 )
    McTemplateU0s_EventWriteTransfer("WinHttpSendRequest", EnteringScopeEvent, "WinHttpSendRequest");
  v33 = WinHttpSendRequest(this[2], 0, 0, v29, v14, v14, (DWORD_PTR)(this + 4));
  if ( v33 && dword_1800706BC )
  {
    dwBufferLength[0] = 8;
    lpOptional = 0;
    if ( !WinHttpQueryOption(this[2], 0x4Eu, &lpOptional, dwBufferLength) )
    {
      if ( (int)GetLastError() > 0 )
        v13 = (unsigned __int16)GetLastError() | 0x80190000;
      else
        v13 = GetLastError();
LABEL_50:
      v35 = lpOptional;
      if ( lpOptional )
        CertFreeCertificateContext((PCCERT_CONTEXT)lpOptional);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
        McTemplateU0s_EventWriteTransfer(v35, LeavingScopeEvent, "WinHttpSendRequest");
      goto LABEL_103;
    }
    v52 = 0;
    IsCertificateTrustedForMmpc = Mmpc_Lockdown_IsCertificateTrustedForMmpc(lpOptional, &v52);
    v13 = IsCertificateTrustedForMmpc;
    if ( IsCertificateTrustedForMmpc < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x393,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\winhttphelper.cpp",
        (const char *)(unsigned int)IsCertificateTrustedForMmpc,
        pwszReferrera);
      goto LABEL_50;
    }
    if ( !v52 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogMmpcCertificationValidationFailure(Logger, v37);
      v38 = lpOptional;
      if ( lpOptional )
        CertFreeCertificateContext((PCCERT_CONTEXT)lpOptional);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
        McTemplateU0s_EventWriteTransfer(v38, LeavingScopeEvent, "WinHttpSendRequest");
      v13 = -2146762478;
      goto LABEL_103;
    }
    v32 = lpOptional;
    if ( lpOptional )
      CertFreeCertificateContext((PCCERT_CONTEXT)lpOptional);
  }
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(v32, LeavingScopeEvent, "WinHttpSendRequest");
  if ( v33 )
  {
    if ( WinHttpReceiveResponse(this[2], 0) )
    {
      v44 = lpBuffer;
      v13 = 0;
      if ( !WinHttpQueryHeaders(this[2], 0x20000013u, 0, lpBuffer, &v54, 0) )
      {
        if ( (int)GetLastError() > 0 )
          v13 = (unsigned __int16)GetLastError() | 0x80190000;
        else
          v13 = GetLastError();
      }
      v45 = v56;
      *v56 = 0;
      if ( *v44 == 503 || *v44 == 429 )
      {
        dwBufferLength[0] = 22;
        if ( WinHttpQueryHeaders(this[2], 0x24u, 0, &Buffer, dwBufferLength, 0) )
          *v45 = _o__wtol(&Buffer);
      }
      goto LABEL_103;
    }
    goto LABEL_93;
  }
  v39 = GetLastError();
  v41 = v39;
  v42 = (unsigned __int16)v39;
  v43 = v39 < 0;
  if ( v39 > 0 )
  {
    v39 = (unsigned __int16)v39 | 0x80190000;
    v43 = 1;
  }
  if ( v43 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
  {
    dwBufferLength[0] = v39;
    v59 = dwBufferLength;
    v60 = 4;
    McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, SendingRequestFailedEvent, v40, 2, v58);
  }
  if ( v41 == 12175 )
  {
    v13 = *((_DWORD *)this + 8);
    if ( v13 )
    {
      if ( v13 == 12045 || v13 == 12057 )
      {
        v13 = -2145910766;
        goto LABEL_103;
      }
      LOWORD(v41) = *((_DWORD *)this + 8);
      if ( v13 <= 0 )
        goto LABEL_103;
    }
    v21 = (unsigned __int16)v41;
    goto LABEL_77;
  }
  if ( v41 > 0 )
    v41 = v42 | 0x80190000;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
  {
    dwBufferLength[0] = v41;
    v59 = dwBufferLength;
    v60 = 4;
    McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, SendingRequestFailedEvent, v40, 2, v58);
  }
  v13 = v41;
LABEL_103:
  WinHttpSetStatusCallback(this[2], 0, 0x14000u, 0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001ed6c  mov     r11, rsp
0x18001ed6f  push    rbx
0x18001ed70  push    rsi
0x18001ed71  push    rdi
0x18001ed72  push    r12
0x18001ed74  push    r13
0x18001ed76  push    r14
0x18001ed78  push    r15
0x18001ed7a  sub     rsp, 0D0h
0x18001ed81  mov     rax, cs:__security_cookie
0x18001ed88  xor     rax, rsp
0x18001ed8b  mov     [rsp+108h+var_48], rax
0x18001ed93  mov     [rsp+108h+lpOptional], r9
0x18001ed98  mov     r8, rdx; pwszObjectName
0x18001ed9b  mov     rsi, rcx
0x18001ed9e  mov     r15, [rsp+108h+arg_28]
0x18001eda6  mov     qword ptr [rsp+108h+dwBufferLength], r15
0x18001edab  mov     rax, [rsp+108h+arg_40]
0x18001edb3  mov     [rsp+108h+lpBuffer], rax
0x18001edb8  mov     rcx, [rsp+108h+arg_48]
0x18001edc0  mov     [rsp+108h+var_A0], rcx
0x18001edc5  mov     [rsp+108h+var_B0], 4
0x18001edcd  mov     dword ptr [rax], 0C8h
0x18001edd3  mov     [r11-60h], rsi
0x18001edd7  mov     byte ptr [r11-58h], 1
0x18001eddc  mov     r10d, 0FFFFFFFFh
0x18001ede2  xor     r13d, r13d
0x18001ede5  test    r9, r9
0x18001ede8  jz      short loc_18001EE39
0x18001edea  mov     edx, 7FFFFFFFh
0x18001edef  mov     ecx, edx
0x18001edf1  mov     rax, r9
0x18001edf4  cmp     [rax], r13b
0x18001edf7  jz      short loc_18001EE02
0x18001edf9  inc     rax
0x18001edfc  sub     rcx, 1
0x18001ee00  jnz     short loc_18001EDF4
0x18001ee02  mov     rax, rcx
0x18001ee05  neg     rax
0x18001ee08  sbb     ebx, ebx
0x18001ee0a  not     ebx
0x18001ee0c  and     ebx, 80070057h
0x18001ee12  mov     rax, rcx
0x18001ee15  sub     rdx, rcx
0x18001ee18  neg     rax
0x18001ee1b  sbb     r12, r12
0x18001ee1e  and     r12, rdx
0x18001ee21  test    rcx, rcx
0x18001ee24  jz      loc_18001F54D
0x18001ee2a  cmp     r12, r10
0x18001ee2d  jbe     short loc_18001EE41
0x18001ee2f  mov     ebx, 80070216h
0x18001ee34  jmp     loc_18001F54D
0x18001ee39  mov     r12d, [rsp+108h+arg_20]
0x18001ee41  mov     eax, r13d
0x18001ee44  mov     ecx, 800000h
0x18001ee49  cmp     cs:dword_1800706BC, r13d
0x18001ee50  cmovnz  eax, ecx
0x18001ee53  mov     [rsp+108h+dwFlags], eax; dwFlags
0x18001ee57  mov     [rsp+108h+ppwszAcceptTypes], r13; ppwszAcceptTypes
0x18001ee5c  mov     [rsp+108h+pwszReferrer], r13; int
0x18001ee61  lea     r9, pwszVersion; "HTTP/1.1"
0x18001ee68  lea     rdx, pwszVerb; "POST"
0x18001ee6f  mov     rcx, [rsi+8]; hConnect
0x18001ee73  call    cs:__imp_WinHttpOpenRequest
0x18001ee7a  nop     dword ptr [rax+rax+00h]
0x18001ee7f  mov     rdi, rax
0x18001ee82  mov     r14, [rsi+10h]
0x18001ee86  test    r14, r14
0x18001ee89  jz      short loc_18001EEB6
0x18001ee8b  call    cs:__imp_GetLastError
0x18001ee92  nop     dword ptr [rax+rax+00h]
0x18001ee97  mov     ebx, eax
0x18001ee99  mov     rcx, r14; hInternet
0x18001ee9c  call    cs:__imp_WinHttpCloseHandle
0x18001eea3  nop     dword ptr [rax+rax+00h]
0x18001eea8  mov     ecx, ebx; dwErrCode
0x18001eeaa  call    cs:__imp_SetLastError
0x18001eeb1  nop     dword ptr [rax+rax+00h]
0x18001eeb6  mov     [rsi+10h], rdi
0x18001eeba  test    rdi, rdi
0x18001eebd  jz      loc_18001F4CE
0x18001eec3  mov     [rsi+20h], r13d
0x18001eec7  xor     r9d, r9d; dwReserved
0x18001eeca  mov     r14d, 14000h
0x18001eed0  mov     r8d, r14d; dwNotificationFlags
0x18001eed3  lea     rdx, SecureFailureCallback; lpfnInternetCallback
0x18001eeda  mov     rcx, rdi; hInternet
0x18001eedd  call    cs:__imp_WinHttpSetStatusCallback
0x18001eee4  nop     dword ptr [rax+rax+00h]
0x18001eee9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001eeed  cmp     rax, rdi
0x18001eef0  jnz     short loc_18001EF1A
0x18001eef2  call    cs:__imp_GetLastError
0x18001eef9  nop     dword ptr [rax+rax+00h]
0x18001eefe  test    eax, eax
0x18001ef00  jle     loc_18001F47F
0x18001ef06  call    cs:__imp_GetLastError
0x18001ef0d  nop     dword ptr [rax+rax+00h]
0x18001ef12  movzx   ebx, ax
0x18001ef15  jmp     loc_18001F30A
0x18001ef1a  mov     ebx, r13d
0x18001ef1d  mov     r13d, 2
0x18001ef23  mov     eax, ebx
0x18001ef25  mov     rdx, [r15+rax*8]; lpszHeaders
0x18001ef29  mov     r8, rdi
0x18001ef2c  xor     eax, eax
0x18001ef2e  inc     r8; dwHeadersLength
0x18001ef31  cmp     [rdx+r8*2], ax
0x18001ef36  jnz     short loc_18001EF2E
0x18001ef38  mov     eax, 0FFFFFFFFh
0x18001ef3d  cmp     r8, rax
0x18001ef40  ja      loc_18001F4A8
0x18001ef46  mov     r9d, 20000000h; dwModifiers
0x18001ef4c  mov     rcx, [rsi+10h]; hRequest
0x18001ef50  call    cs:__imp_WinHttpAddRequestHeaders
0x18001ef57  nop     dword ptr [rax+rax+00h]
0x18001ef5c  test    eax, eax
0x18001ef5e  jz      loc_18001F46F
0x18001ef64  inc     ebx
0x18001ef66  cmp     ebx, r13d
0x18001ef69  jb      short loc_18001EF23
0x18001ef6b  mov     r9d, 20000000h; dwModifiers
0x18001ef71  mov     r8d, 0FFFFFFFFh; dwHeadersLength
0x18001ef77  lea     rdx, szHeaders; "Content-Type: application/json"
0x18001ef7e  mov     rcx, [rsi+10h]; hRequest
0x18001ef82  call    cs:__imp_WinHttpAddRequestHeaders
0x18001ef89  nop     dword ptr [rax+rax+00h]
0x18001ef8e  xor     r8d, r8d
0x18001ef91  test    eax, eax
0x18001ef93  jz      loc_18001F46F
0x18001ef99  mov     eax, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x18001ef9f  lea     r15, WP_ENROLLMENT_API_PROVIDER_Context
0x18001efa6  test    al, 1
0x18001efa8  jz      short loc_18001EFED
0x18001efaa  mov     [rsp+108h+var_C0], r12d
0x18001efaf  lea     rax, [rsp+108h+var_C0]
0x18001efb4  mov     [rsp+108h+var_80], rax
0x18001efbc  mov     [rsp+108h+var_78], 4
0x18001efc8  lea     rax, [rsp+108h+var_90]
0x18001efcd  mov     [rsp+108h+pwszReferrer], rax
0x18001efd2  mov     r9d, r13d
0x18001efd5  lea     rdx, HttpSendRequestDataSizeEvent
0x18001efdc  mov     rcx, r15
0x18001efdf  call    McGenEventWrite_EventWriteTransfer
0x18001efe4  mov     eax, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x18001efea  xor     r8d, r8d
0x18001efed  test    r13b, al
0x18001eff0  jz      loc_18001F0A8
0x18001eff6  mov     rax, qword ptr [rsp+108h+dwBufferLength]
0x18001effb  mov     rax, [rax]
0x18001effe  test    rax, rax
0x18001f001  jz      short loc_18001F019
0x18001f003  mov     rcx, rdi
0x18001f006  inc     rcx
0x18001f009  cmp     [rax+rcx*2], r8w
0x18001f00e  jnz     short loc_18001F006
0x18001f010  lea     ecx, ds:2[rcx*2]
0x18001f017  jmp     short loc_18001F025
0x18001f019  lea     rax, aNull_0; "NULL"
0x18001f020  mov     ecx, 0Ah
0x18001f025  mov     [rsp+108h+var_80], rax
0x18001f02d  mov     dword ptr [rsp+108h+var_78], ecx
0x18001f034  mov     dword ptr [rsp+108h+var_78+4], r8d
0x18001f03c  mov     rbx, [rsp+108h+lpOptional]
0x18001f041  test    rbx, rbx
0x18001f044  jz      short loc_18001F054
0x18001f046  inc     rdi
0x18001f049  cmp     [rbx+rdi], r8b
0x18001f04d  jnz     short loc_18001F046
0x18001f04f  lea     ecx, [rdi+1]
0x18001f052  jmp     short loc_18001F059
0x18001f054  mov     ecx, 5
0x18001f059  lea     rdx, aNull; "NULL"
0x18001f060  mov     rax, rbx
0x18001f063  test    rbx, rbx
0x18001f066  cmovz   rax, rdx
0x18001f06a  mov     [rsp+108h+var_70], rax
0x18001f072  mov     [rsp+108h+var_68], ecx
0x18001f079  mov     [rsp+108h+var_64], r8d
0x18001f081  lea     rax, [rsp+108h+var_90]
0x18001f086  mov     [rsp+108h+pwszReferrer], rax
0x18001f08b  mov     r9d, 3
0x18001f091  lea     rdx, MmpcDiscoveryRequestMessage
0x18001f098  mov     rcx, r15
0x18001f09b  call    McGenEventWrite_EventWriteTransfer
0x18001f0a0  mov     eax, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x18001f0a6  jmp     short loc_18001F0AD
0x18001f0a8  mov     rbx, [rsp+108h+lpOptional]
0x18001f0ad  lea     rcx, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18001f0b4  mov     [rsp+108h+var_98], rcx
0x18001f0b9  test    al, 1
0x18001f0bb  jz      short loc_18001F0CD
0x18001f0bd  mov     r8, rcx
0x18001f0c0  lea     rdx, EnteringScopeEvent
0x18001f0c7  call    McTemplateU0s_EventWriteTransfer
0x18001f0cc  nop
0x18001f0cd  lea     rax, [rsi+20h]
0x18001f0d1  mov     qword ptr [rsp+108h+dwFlags], rax; dwContext
0x18001f0d6  mov     dword ptr [rsp+108h+ppwszAcceptTypes], r12d; dwTotalLength
0x18001f0db  mov     dword ptr [rsp+108h+pwszReferrer], r12d; int
0x18001f0e0  mov     r9, rbx; lpOptional
0x18001f0e3  xor     r8d, r8d; dwHeadersLength
0x18001f0e6  xor     edx, edx; lpszHeaders
0x18001f0e8  mov     rcx, [rsi+10h]; hRequest
0x18001f0ec  call    cs:__imp_WinHttpSendRequest
0x18001f0f3  nop     dword ptr [rax+rax+00h]
0x18001f0f8  mov     edi, eax
0x18001f0fa  xor     r12d, r12d
0x18001f0fd  test    eax, eax
0x18001f0ff  jz      loc_18001F258
0x18001f105  cmp     cs:dword_1800706BC, r12d
0x18001f10c  jz      loc_18001F258
0x18001f112  mov     [rsp+108h+dwBufferLength], 8
0x18001f11a  mov     [rsp+108h+lpOptional], r12
0x18001f11f  lea     r9, [rsp+108h+dwBufferLength]; lpdwBufferLength
0x18001f124  lea     r8, [rsp+108h+lpOptional]; lpBuffer
0x18001f129  lea     edx, [r12+4Eh]; dwOption
0x18001f12e  mov     rcx, [rsi+10h]; hInternet
0x18001f132  call    cs:__imp_WinHttpQueryOption
0x18001f139  nop     dword ptr [rax+rax+00h]
0x18001f13e  test    eax, eax
0x18001f140  jnz     short loc_18001F179
0x18001f142  call    cs:__imp_GetLastError
0x18001f149  nop     dword ptr [rax+rax+00h]
0x18001f14e  test    eax, eax
0x18001f150  jg      short loc_18001F162
0x18001f152  call    cs:__imp_GetLastError
0x18001f159  nop     dword ptr [rax+rax+00h]
0x18001f15e  mov     ebx, eax
0x18001f160  jmp     short loc_18001F1B7
0x18001f162  call    cs:__imp_GetLastError
0x18001f169  nop     dword ptr [rax+rax+00h]
0x18001f16e  movzx   ebx, ax
0x18001f171  or      ebx, 80190000h
0x18001f177  jmp     short loc_18001F1B7
0x18001f179  mov     [rsp+108h+var_C0], r12d
0x18001f17e  lea     rdx, [rsp+108h+var_C0]
0x18001f183  mov     rcx, [rsp+108h+lpOptional]
0x18001f188  call    cs:__imp_Mmpc_Lockdown_IsCertificateTrustedForMmpc
0x18001f18f  nop     dword ptr [rax+rax+00h]
0x18001f194  mov     ebx, eax
0x18001f196  test    eax, eax
0x18001f198  jns     short loc_18001F1EC
0x18001f19a  mov     rcx, [rsp+108h]; this
0x18001f1a2  mov     r9d, eax; char *
0x18001f1a5  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001f1ac  mov     edx, 393h; void *
0x18001f1b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1b6  nop
0x18001f1b7  mov     rcx, [rsp+108h+lpOptional]; pCertContext
0x18001f1bc  test    rcx, rcx
0x18001f1bf  jz      short loc_18001F1CE
0x18001f1c1  call    cs:__imp_CertFreeCertificateContext
0x18001f1c8  nop     dword ptr [rax+rax+00h]
0x18001f1cd  nop
0x18001f1ce  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18001f1d5  jz      short loc_18001F239
0x18001f1d7  lea     r8, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18001f1de  lea     rdx, LeavingScopeEvent
0x18001f1e5  call    McTemplateU0s_EventWriteTransfer
0x18001f1ea  jmp     short loc_18001F239
0x18001f1ec  cmp     [rsp+108h+var_C0], r12d
0x18001f1f1  jnz     short loc_18001F241
0x18001f1f3  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001f1f8  mov     rcx, rax; this
0x18001f1fb  call    ?LogMmpcCertificationValidationFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogMmpcCertificationValidationFailure(long)
0x18001f200  nop
0x18001f201  mov     rcx, [rsp+108h+lpOptional]; pCertContext
0x18001f206  test    rcx, rcx
0x18001f209  jz      short loc_18001F218
0x18001f20b  call    cs:__imp_CertFreeCertificateContext
0x18001f212  nop     dword ptr [rax+rax+00h]
0x18001f217  nop
0x18001f218  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18001f21f  jz      short loc_18001F234
0x18001f221  lea     r8, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18001f228  lea     rdx, LeavingScopeEvent
0x18001f22f  call    McTemplateU0s_EventWriteTransfer
0x18001f234  mov     ebx, 800B0112h
0x18001f239  mov     r8d, r14d
0x18001f23c  jmp     loc_18001F553
0x18001f241  mov     rcx, [rsp+108h+lpOptional]; pCertContext
0x18001f246  test    rcx, rcx
0x18001f249  jz      short loc_18001F258
0x18001f24b  call    cs:__imp_CertFreeCertificateContext
0x18001f252  nop     dword ptr [rax+rax+00h]
0x18001f257  nop
0x18001f258  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18001f25f  jz      short loc_18001F274
0x18001f261  lea     r8, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18001f268  lea     rdx, LeavingScopeEvent
0x18001f26f  call    McTemplateU0s_EventWriteTransfer
0x18001f274  test    edi, edi
0x18001f276  jnz     loc_18001F374
0x18001f27c  call    cs:__imp_GetLastError
0x18001f283  nop     dword ptr [rax+rax+00h]
0x18001f288  mov     edi, eax
0x18001f28a  movzx   ebx, ax
0x18001f28d  test    eax, eax
  ... truncated ...
```
