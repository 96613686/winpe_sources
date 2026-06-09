# InetSendAuthenticatedRequestAndReceiveResponse(void *,void *,ushort const *,ushort const *,uchar const *,ulong,ulong,_CRYPT_CREDENTIALS *,_CRYPT_RETRIEVE_AUX_INFO *)

- ea: `0x1800036dc`
- end: `0x180003b2c`
- name: `?InetSendAuthenticatedRequestAndReceiveResponse@@YAJPEAX0PEBG1PEBEKKPEAU_CRYPT_CREDENTIALS@@PEAU_CRYPT_RETRIEVE_AUX_INFO@@@Z`
- size: `1104`
- prototype: `__int64 __fastcall(void *, void *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, DWORD dwOptionalLength, unsigned int, struct _CRYPT_CREDENTIALS *, struct _CRYPT_RETRIEVE_AUX_INFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180003ef0`

## callees

- `0x180003314`
- `0x180003584`
- `0x1800036dc`
- `0x180019220`
- `0x18001db64`
- `0x18002656a`
- `0x1800265b0`
- `0x180026640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800038cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c8`
- `CRYPT32!I_CertDiagControl` at `0x18000382d`
- `CRYPT32!I_CertDiagControl` at `0x180003886`
- `CRYPT32!I_CertDiagControl` at `0x180003afb`
- `CRYPT32!I_CertDiagControl` at `0x18000382d`
- `CRYPT32!I_CertDiagControl` at `0x180003886`
- `CRYPT32!I_CertDiagControl` at `0x180003afb`
- `CRYPT32!CryptMemFree` at `0x18000388f`
- `CRYPT32!CryptMemFree` at `0x18000388f`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800037ac`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800037ac`
- `WINHTTP!WinHttpSendRequest` at `0x180003799`
- `WINHTTP!WinHttpSendRequest` at `0x180003799`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800037ee`
- `WINHTTP!WinHttpQueryHeaders` at `0x180003a5f`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800037ee`
- `WINHTTP!WinHttpQueryHeaders` at `0x180003a5f`
- `WINHTTP!WinHttpSetOption` at `0x180003754`
- `WINHTTP!WinHttpSetOption` at `0x180003754`

## string_xrefs

- `0x180003a72`: `CRYPTNET.DLL --> Request Headers::\n`
- `0x180003a69`: `CRYPTNET.DLL --> Response Headers::\n`

## pseudocode

```c
__int64 __fastcall InetSendAuthenticatedRequestAndReceiveResponse(
        void *a1,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5,
        DWORD dwOptionalLength,
        unsigned int a7,
        struct _CRYPT_CREDENTIALS *a8,
        struct _CRYPT_RETRIEVE_AUX_INFO *a9)
{
  struct _CRYPT_RETRIEVE_AUX_INFO *v9; // rdi
  DWORD LastError; // r12d
  int v13; // ebx
  DWORD v14; // eax
  const wchar_t *v15; // r15
  unsigned int i; // ebx
  DWORD v17; // edx
  unsigned __int16 *StringHeader; // rax
  unsigned __int16 *v19; // rsi
  DWORD v20; // r8d
  unsigned int v21; // ebx
  LPWSTR *ppwszErrorResponseHeaders; // rax
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rdx
  __int64 v26; // r8
  const wchar_t *v27; // rcx
  unsigned int j; // ebx
  DWORD v29; // edx
  const char *v30; // rcx
  const wchar_t *v31; // rax
  DWORD v32; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwIndex; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v34; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwBufferLength; // [rsp+4Ch] [rbp-B4h] BYREF
  LPVOID lpOptional; // [rsp+50h] [rbp-B0h] BYREF
  int Buffer; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h]
  __int128 v40; // [rsp+70h] [rbp-90h]
  __int128 v41; // [rsp+80h] [rbp-80h]
  struct _CRYPT_RETRIEVE_AUX_INFO *v42; // [rsp+90h] [rbp-70h]
  wchar_t v43[2048]; // [rsp+A0h] [rbp-60h] BYREF

  v9 = a9;
  v42 = a9;
  lpOptional = a5;
  v32 = 400;
  dwBufferLength = 0;
  dwIndex = 0;
  Buffer = 0;
  if ( !WinHttpSetOption(a2, 0x4Du, &Buffer, 4u) )
  {
    v27 = L"Call_WinHttpSetOption_DisableAutologon";
LABEL_40:
    v21 = -1;
    CryptDiagAddActionWithWinHttpLastError(v27);
    goto LABEL_41;
  }
  LastError = 0;
  v13 = 0;
  while ( 1 )
  {
    if ( !WinHttpSendRequest(a2, a4, -(a4 != 0), lpOptional, dwOptionalLength, dwOptionalLength, 0) )
    {
      GetLastError();
      v27 = L"Call_WinHttpSendRequest";
      goto LABEL_40;
    }
    if ( WinHttpReceiveResponse(a2, 0) )
      break;
    LastError = GetLastError();
    if ( LastError != 12032 )
    {
      v27 = L"Call_WinHttpReceiveResponse";
      goto LABEL_40;
    }
    if ( (unsigned int)++v13 > 5 )
    {
      v27 = L"Call_WinHttpSendRequest_ExceededMaxResendCount";
      goto LABEL_40;
    }
  }
  dwBufferLength = 4;
  dwIndex = 0;
  if ( !WinHttpQueryHeaders(a2, 0x20000013u, 0, &v32, &dwBufferLength, &dwIndex) )
  {
    v27 = L"Call_WinHttpQueryHeaders_WINHTTP_QUERY_STATUS_CODE";
    goto LABEL_40;
  }
  if ( v32 == 304 || v32 == 200 || (v14 = 0, v32 == 407) )
    v14 = 1;
  lpOptional = 0;
  v34 = v14;
  I_CertDiagControl(13, &v34, &lpOptional);
  v15 = (const wchar_t *)lpOptional;
  if ( lpOptional )
  {
    for ( i = 0; i < 2; ++i )
    {
      v17 = -2147483627;
      if ( i )
        v17 = 21;
      StringHeader = InetHttpQueryAndAllocateStringHeader(a2, v17);
      v19 = StringHeader;
      if ( StringHeader )
      {
        v38 = v15;
        *(_QWORD *)&v40 = StringHeader;
        v39 = i == 0;
        I_CertDiagControl(14, &v38, 0);
        CryptMemFree(v19);
      }
    }
    v9 = v42;
  }
  if ( (unsigned int)I_CryptNetIsDebugTracePrintEnabled() )
  {
    for ( j = 0; j < 2; ++j )
    {
      memset_0(v43, 0, sizeof(v43));
      v29 = -2147483626;
      v34 = 4096;
      dwIndex = 0;
      if ( j )
        v29 = 22;
      if ( WinHttpQueryHeaders(a2, v29, 0, v43, &v34, &dwIndex) )
      {
        v30 = "CRYPTNET.DLL --> Request Headers::\n";
        if ( j )
          v30 = "CRYPTNET.DLL --> Response Headers::\n";
        I_CryptNetDebugPrintfA(v30);
        I_CryptNetDebugPrintfA("%ls", v43);
      }
    }
  }
  v20 = v32;
  v21 = -1;
  if ( v32 != 200 && v32 != 304 )
  {
    if ( v9 )
    {
      if ( v9->cbSize > 0x48 )
      {
        ppwszErrorResponseHeaders = v9->ppwszErrorResponseHeaders;
        if ( ppwszErrorResponseHeaders )
        {
          if ( !*ppwszErrorResponseHeaders )
          {
            v24 = InetHttpQueryAndAllocateStringHeader(a2, 0x15u);
            v25 = v24;
            if ( v24 )
            {
              *v9->ppwszErrorResponseHeaders = v24;
              while ( v25 )
              {
                v26 = -1;
                do
                  ++v26;
                while ( v25[v26] );
                if ( !(_DWORD)v26 || !v25[(unsigned int)(v26 + 1)] )
                  break;
                v25[(unsigned int)v26] = 124;
                v25 += (unsigned int)(v26 + 1);
              }
            }
            v20 = v32;
          }
        }
      }
    }
  }
  switch ( v20 )
  {
    case 0xC8u:
      v21 = 1;
      goto LABEL_20;
    case 0x130u:
      v21 = 0;
      goto LABEL_20;
    case 0x191u:
      v31 = L"HTTP_STATUS_DENIED";
      v39 = 401;
      break;
    case 0x197u:
      v31 = L"HTTP_STATUS_PROXY_AUTH_REQ";
      v39 = 407;
      break;
    default:
      if ( v9 && v9->cbSize > 0x44 )
        v9->dwHttpStatusCode = v20;
      v31 = L"HTTP_STATUS";
      v39 = v20;
      break;
  }
  v38 = v31;
  v40 = 0;
  v41 = 0;
  I_CertDiagControl(11, &v38, 0);
  v32 |= 0x80190000;
  SetLastError(v32);
LABEL_41:
  LastError = GetLastError();
LABEL_20:
  SetLastError(LastError);
  return v21;
}

```

## disassembly

```asm
0x1800036dc  mov     [rsp-8+arg_0], rbx
0x1800036e1  push    rbp
0x1800036e2  push    rsi
0x1800036e3  push    rdi
0x1800036e4  push    r12
0x1800036e6  push    r13
0x1800036e8  push    r14
0x1800036ea  push    r15
0x1800036ec  lea     rbp, [rsp-0FB0h]
0x1800036f4  mov     eax, 10B0h
0x1800036f9  call    _alloca_probe
0x1800036fe  sub     rsp, rax
0x180003701  mov     rax, cs:__security_cookie
0x180003708  xor     rax, rsp
0x18000370b  mov     [rbp+0FE0h+var_40], rax
0x180003712  mov     rax, [rbp+0FE0h+arg_20]
0x180003719  lea     r8, [rsp+10E0h+Buffer]; lpBuffer
0x18000371e  mov     rdi, [rbp+0FE0h+arg_40]
0x180003725  xor     esi, esi
0x180003727  mov     r14, rdx
0x18000372a  mov     [rbp+0FE0h+var_1050], rdi
0x18000372e  mov     r13, r9
0x180003731  mov     [rsp+10E0h+lpOptional], rax
0x180003736  mov     rcx, r14; hInternet
0x180003739  mov     [rsp+10E0h+var_10A0], 190h
0x180003741  lea     r9d, [rsi+4]; dwBufferLength
0x180003745  mov     [rsp+10E0h+dwBufferLength], esi
0x180003749  lea     edx, [rsi+4Dh]; dwOption
0x18000374c  mov     [rsp+10E0h+dwIndex], esi
0x180003750  mov     [rsp+10E0h+Buffer], esi
0x180003754  call    cs:__imp_WinHttpSetOption
0x18000375a  test    eax, eax
0x18000375c  jz      loc_1800039F6
0x180003762  mov     r15d, [rbp+0FE0h+arg_28]
0x180003769  mov     eax, esi
0x18000376b  sub     rax, r13
0x18000376e  mov     r12d, esi
0x180003771  neg     rax
0x180003774  mov     ebx, esi
0x180003776  sbb     esi, esi
0x180003778  mov     r9, [rsp+10E0h+lpOptional]; lpOptional
0x18000377d  mov     r8d, esi; dwHeadersLength
0x180003780  mov     [rsp+10E0h+dwContext], 0; dwContext
0x180003789  mov     rdx, r13; lpszHeaders
0x18000378c  mov     [rsp+10E0h+dwTotalLength], r15d; dwTotalLength
0x180003791  mov     rcx, r14; hRequest
0x180003794  mov     [rsp+10E0h+dwOptionalLength], r15d; dwOptionalLength
0x180003799  call    cs:__imp_WinHttpSendRequest
0x18000379f  test    eax, eax
0x1800037a1  jz      loc_1800039A4
0x1800037a7  xor     edx, edx; lpReserved
0x1800037a9  mov     rcx, r14; hRequest
0x1800037ac  call    cs:__imp_WinHttpReceiveResponse
0x1800037b2  test    eax, eax
0x1800037b4  jz      loc_1800039C8
0x1800037ba  lea     rax, [rsp+10E0h+dwIndex]
0x1800037bf  mov     [rsp+10E0h+dwBufferLength], 4
0x1800037c7  mov     qword ptr [rsp+10E0h+dwTotalLength], rax; lpdwIndex
0x1800037cc  lea     r9, [rsp+10E0h+var_10A0]; lpBuffer
0x1800037d1  lea     rax, [rsp+10E0h+dwBufferLength]
0x1800037d6  xor     r13d, r13d
0x1800037d9  xor     r8d, r8d; pwszName
0x1800037dc  mov     qword ptr [rsp+10E0h+dwOptionalLength], rax; lpdwBufferLength
0x1800037e1  mov     edx, 20000013h; dwInfoLevel
0x1800037e6  mov     [rsp+10E0h+dwIndex], r13d
0x1800037eb  mov     rcx, r14; hRequest
0x1800037ee  call    cs:__imp_WinHttpQueryHeaders
0x1800037f4  test    eax, eax
0x1800037f6  jz      loc_180003A08
0x1800037fc  mov     eax, [rsp+10E0h+var_10A0]
0x180003800  mov     esi, 0C8h
0x180003805  cmp     eax, 130h
0x18000380a  jnz     loc_18000390D
0x180003810  mov     eax, 1
0x180003815  lea     r8, [rsp+10E0h+lpOptional]
0x18000381a  mov     [rsp+10E0h+lpOptional], r13
0x18000381f  lea     rdx, [rsp+10E0h+var_1098]
0x180003824  mov     [rsp+10E0h+var_1098], eax
0x180003828  mov     ecx, 0Dh
0x18000382d  call    cs:__imp_I_CertDiagControl
0x180003833  mov     r15, [rsp+10E0h+lpOptional]
0x180003838  test    r15, r15
0x18000383b  jz      short loc_1800038A5
0x18000383d  mov     ebx, r13d
0x180003840  mov     edi, 15h
0x180003845  mov     edx, 80000015h
0x18000384a  test    ebx, ebx
0x18000384c  mov     rcx, r14; hRequest
0x18000384f  cmovnz  edx, edi; dwInfoLevel
0x180003852  call    ?InetHttpQueryAndAllocateStringHeader@@YAPEAGPEAXK@Z; InetHttpQueryAndAllocateStringHeader(void *,ulong)
0x180003857  mov     rsi, rax
0x18000385a  test    rax, rax
0x18000385d  jz      short loc_180003895
0x18000385f  mov     ecx, r13d
0x180003862  mov     [rsp+10E0h+var_1080], r15
0x180003867  test    ebx, ebx
0x180003869  mov     qword ptr [rsp+10E0h+var_1070], rsi
0x18000386e  lea     rdx, [rsp+10E0h+var_1080]
0x180003873  setz    cl
0x180003876  xor     eax, eax
0x180003878  mov     dword ptr [rsp+10E0h+var_1078], ecx
0x18000387c  xor     r8d, r8d
0x18000387f  mov     dword ptr [rsp+10E0h+var_1078+4], eax
0x180003883  lea     ecx, [rax+0Eh]
0x180003886  call    cs:__imp_I_CertDiagControl
0x18000388c  mov     rcx, rsi; pv
0x18000388f  call    cs:__imp_CryptMemFree
0x180003895  inc     ebx
0x180003897  cmp     ebx, 2
0x18000389a  jb      short loc_180003845
0x18000389c  mov     rdi, [rbp+0FE0h+var_1050]
0x1800038a0  mov     esi, 0C8h
0x1800038a5  call    ?I_CryptNetIsDebugTracePrintEnabled@@YAHXZ; I_CryptNetIsDebugTracePrintEnabled(void)
0x1800038aa  test    eax, eax
0x1800038ac  jnz     loc_180003A11
0x1800038b2  mov     r8d, [rsp+10E0h+var_10A0]
0x1800038b7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800038bb  cmp     r8d, esi
0x1800038be  jnz     short loc_180003928
0x1800038c0  mov     eax, r8d
0x1800038c3  sub     eax, esi
0x1800038c5  jnz     short loc_1800038FF
0x1800038c7  lea     ebx, [rax+1]
0x1800038ca  mov     ecx, r12d; dwErrCode
0x1800038cd  call    cs:__imp_SetLastError
0x1800038d3  mov     eax, ebx
0x1800038d5  mov     rcx, [rbp+0FE0h+var_40]
0x1800038dc  xor     rcx, rsp; StackCookie
0x1800038df  call    __security_check_cookie
0x1800038e4  mov     rbx, [rsp+10E0h+arg_0]
0x1800038ec  add     rsp, 10B0h
0x1800038f3  pop     r15
0x1800038f5  pop     r14
0x1800038f7  pop     r13
0x1800038f9  pop     r12
0x1800038fb  pop     rdi
0x1800038fc  pop     rsi
0x1800038fd  pop     rbp
0x1800038fe  retn
0x1800038ff  sub     eax, 68h ; 'h'
0x180003902  jnz     loc_180003A9E
0x180003908  mov     ebx, r13d
0x18000390b  jmp     short loc_1800038CA
0x18000390d  cmp     eax, esi
0x18000390f  jz      loc_180003810
0x180003915  cmp     eax, 197h
0x18000391a  mov     eax, r13d
0x18000391d  jnz     loc_180003815
0x180003923  jmp     loc_180003810
0x180003928  cmp     r8d, 130h
0x18000392f  jz      short loc_1800038C0
0x180003931  test    rdi, rdi
0x180003934  jz      short loc_1800038C0
0x180003936  cmp     dword ptr [rdi], 48h ; 'H'
0x180003939  jbe     short loc_1800038C0
0x18000393b  mov     rax, [rdi+48h]
0x18000393f  test    rax, rax
0x180003942  jz      loc_1800038C0
0x180003948  cmp     [rax], r13
0x18000394b  jnz     loc_1800038C0
0x180003951  mov     edx, 15h; dwInfoLevel
0x180003956  mov     rcx, r14; hRequest
0x180003959  call    ?InetHttpQueryAndAllocateStringHeader@@YAPEAGPEAXK@Z; InetHttpQueryAndAllocateStringHeader(void *,ulong)
0x18000395e  mov     rdx, rax
0x180003961  test    rax, rax
0x180003964  jz      loc_1800039EC
0x18000396a  mov     rcx, [rdi+48h]
0x18000396e  mov     [rcx], rax
0x180003971  test    rdx, rdx
0x180003974  jz      short loc_1800039EC
0x180003976  mov     r8, rbx
0x180003979  inc     r8
0x18000397c  cmp     [rdx+r8*2], r13w
0x180003981  jnz     short loc_180003979
0x180003983  test    r8d, r8d
0x180003986  jz      short loc_1800039EC
0x180003988  lea     eax, [r8+1]
0x18000398c  lea     r9, [rdx+rax*2]
0x180003990  cmp     [r9], r13w
0x180003994  jz      short loc_1800039EC
0x180003996  mov     eax, r8d
0x180003999  mov     word ptr [rdx+rax*2], 7Ch ; '|'
0x18000399f  mov     rdx, r9
0x1800039a2  jmp     short loc_180003971
0x1800039a4  call    cs:__imp_GetLastError
0x1800039aa  lea     rcx, aCallWinhttpsen_0; "Call_WinHttpSendRequest"
0x1800039b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800039b5  call    CryptDiagAddActionWithWinHttpLastError
0x1800039ba  call    cs:__imp_GetLastError
0x1800039c0  mov     r12d, eax
0x1800039c3  jmp     loc_1800038CA
0x1800039c8  call    cs:__imp_GetLastError
0x1800039ce  mov     r12d, eax
0x1800039d1  cmp     eax, 2F00h
0x1800039d6  jnz     short loc_1800039FF
0x1800039d8  inc     ebx
0x1800039da  cmp     ebx, 5
0x1800039dd  jbe     loc_180003778
0x1800039e3  lea     rcx, aCallWinhttpsen; "Call_WinHttpSendRequest_ExceededMaxRese"...
0x1800039ea  jmp     short loc_1800039B1
0x1800039ec  mov     r8d, [rsp+10E0h+var_10A0]
0x1800039f1  jmp     loc_1800038C0
0x1800039f6  lea     rcx, aCallWinhttpset; "Call_WinHttpSetOption_DisableAutologon"
0x1800039fd  jmp     short loc_1800039B1
0x1800039ff  lea     rcx, aCallWinhttprec; "Call_WinHttpReceiveResponse"
0x180003a06  jmp     short loc_1800039B1
0x180003a08  lea     rcx, aCallWinhttpque; "Call_WinHttpQueryHeaders_WINHTTP_QUERY_"...
0x180003a0f  jmp     short loc_1800039B1
0x180003a11  mov     ebx, r13d
0x180003a14  mov     r15d, 1000h
0x180003a1a  mov     r8, r15; Size
0x180003a1d  lea     rcx, [rbp+0FE0h+var_1040]; void *
0x180003a21  xor     edx, edx; Val
0x180003a23  call    memset_0
0x180003a28  mov     edx, 80000016h
0x180003a2d  mov     [rsp+10E0h+var_1098], r15d
0x180003a32  mov     eax, 16h
0x180003a37  mov     [rsp+10E0h+dwIndex], r13d
0x180003a3c  test    ebx, ebx
0x180003a3e  lea     r9, [rbp+0FE0h+var_1040]; lpBuffer
0x180003a42  mov     rcx, r14; hRequest
0x180003a45  cmovnz  edx, eax; dwInfoLevel
0x180003a48  lea     rax, [rsp+10E0h+dwIndex]
0x180003a4d  mov     qword ptr [rsp+10E0h+dwTotalLength], rax; lpdwIndex
0x180003a52  xor     r8d, r8d; pwszName
0x180003a55  lea     rax, [rsp+10E0h+var_1098]
0x180003a5a  mov     qword ptr [rsp+10E0h+dwOptionalLength], rax; lpdwBufferLength
0x180003a5f  call    cs:__imp_WinHttpQueryHeaders
0x180003a65  test    eax, eax
0x180003a67  jz      short loc_180003A92
0x180003a69  lea     rax, aCryptnetDllRes; "CRYPTNET.DLL --> Response Headers::\n"
0x180003a70  test    ebx, ebx
0x180003a72  lea     rcx, aCryptnetDllReq; "CRYPTNET.DLL --> Request Headers::\n"
0x180003a79  cmovnz  rcx, rax; char *
0x180003a7d  call    ?I_CryptNetDebugPrintfA@@YAXPEBDZZ; I_CryptNetDebugPrintfA(char const *,...)
0x180003a82  lea     rdx, [rbp+0FE0h+var_1040]
0x180003a86  lea     rcx, aLs; "%ls"
0x180003a8d  call    ?I_CryptNetDebugPrintfA@@YAXPEBDZZ; I_CryptNetDebugPrintfA(char const *,...)
0x180003a92  inc     ebx
0x180003a94  cmp     ebx, 2
0x180003a97  jb      short loc_180003A1A
0x180003a99  jmp     loc_1800038B2
0x180003a9e  sub     eax, 61h ; 'a'
0x180003aa1  jz      short loc_180003AC9
0x180003aa3  cmp     eax, 6
0x180003aa6  jz      short loc_180003B1A
0x180003aa8  test    rdi, rdi
0x180003aab  jz      short loc_180003AB6
0x180003aad  cmp     dword ptr [rdi], 44h ; 'D'
0x180003ab0  jbe     short loc_180003AB6
0x180003ab2  mov     [rdi+44h], r8d
0x180003ab6  lea     rax, aHttpStatus; "HTTP_STATUS"
0x180003abd  mov     dword ptr [rsp+10E0h+var_1078], r8d
0x180003ac2  mov     dword ptr [rsp+10E0h+var_1078+4], r13d
0x180003ac7  jmp     short loc_180003AD9
0x180003ac9  lea     rax, aHttpStatusDeni; "HTTP_STATUS_DENIED"
0x180003ad0  mov     [rsp+10E0h+var_1078], 191h
0x180003ad9  xor     r8d, r8d
0x180003adc  mov     [rsp+10E0h+var_1080], rax
0x180003ae1  xorps   xmm0, xmm0
0x180003ae4  lea     rdx, [rsp+10E0h+var_1080]
0x180003ae9  xorps   xmm1, xmm1
0x180003aec  movdqu  [rsp+10E0h+var_1070], xmm0
0x180003af2  lea     ecx, [r8+0Bh]
0x180003af6  movdqu  [rbp+0FE0h+var_1060], xmm1
0x180003afb  call    cs:__imp_I_CertDiagControl
0x180003b01  mov     ecx, [rsp+10E0h+var_10A0]
0x180003b05  or      ecx, 80190000h; dwErrCode
0x180003b0b  mov     [rsp+10E0h+var_10A0], ecx
0x180003b0f  call    cs:__imp_SetLastError
0x180003b15  jmp     loc_1800039BA
0x180003b1a  lea     rax, aHttpStatusProx; "HTTP_STATUS_PROXY_AUTH_REQ"
0x180003b21  mov     [rsp+10E0h+var_1078], 197h
0x180003b2a  jmp     short loc_180003AD9
```
