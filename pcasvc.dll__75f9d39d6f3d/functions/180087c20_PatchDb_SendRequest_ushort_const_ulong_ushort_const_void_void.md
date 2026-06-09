# PatchDb_SendRequest(ushort const *,ulong,ushort const * *,void * &,void * &)

- ea: `0x180087c20`
- end: `0x180087fb0`
- name: `?PatchDb_SendRequest@@YAKPEBGKPEAPEBGAEAPEAX2@Z`
- size: `912`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, DWORD dwAccessType@<edx>, LPCWSTR *ppwszAcceptTypes@<r8>, void **@<r9>, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180086c64`

## callees

- `0x180012920`
- `0x18007a9cf`
- `0x180087c20`
- `0x180088444`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087f29`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180087ea3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180087ea3`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x180087d57`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x180087d57`
- `WINHTTP!WinHttpOpenRequest` at `0x180087e10`
- `WINHTTP!WinHttpOpenRequest` at `0x180087e10`
- `WINHTTP!WinHttpSetOption` at `0x180087e3c`
- `WINHTTP!WinHttpSetOption` at `0x180087e3c`
- `WINHTTP!WinHttpSendRequest` at `0x180087e83`
- `WINHTTP!WinHttpSendRequest` at `0x180087e83`
- `WINHTTP!WinHttpOpen` at `0x180087c9a`
- `WINHTTP!WinHttpOpen` at `0x180087c9a`
- `WINHTTP!WinHttpReceiveResponse` at `0x180087ec7`
- `WINHTTP!WinHttpReceiveResponse` at `0x180087ec7`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180087e5b`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180087e5b`
- `WINHTTP!WinHttpCloseHandle` at `0x180087e90`
- `WINHTTP!WinHttpCloseHandle` at `0x180087f5c`
- `WINHTTP!WinHttpCloseHandle` at `0x180087f71`
- `WINHTTP!WinHttpCloseHandle` at `0x180087f82`
- `WINHTTP!WinHttpCloseHandle` at `0x180087e90`
- `WINHTTP!WinHttpCloseHandle` at `0x180087f5c`
- `WINHTTP!WinHttpCloseHandle` at `0x180087f71`
- `WINHTTP!WinHttpCloseHandle` at `0x180087f82`
- `WINHTTP!WinHttpConnect` at `0x180087d9e`
- `WINHTTP!WinHttpConnect` at `0x180087d9e`
- `WINHTTP!WinHttpCrackUrl` at `0x180087cfd`
- `WINHTTP!WinHttpCrackUrl` at `0x180087cfd`

## string_xrefs

- `0x180087f33`: `Failed to open http request [%ws]: [%d].`
- `0x180087e4d`: `Accept: text/*\nUser-Agent: CloudSdb\n`

## pseudocode

```c
__int64 __fastcall PatchDb_SendRequest(
        const unsigned __int16 *a1,
        DWORD dwAccessType,
        LPCWSTR *ppwszAcceptTypes,
        void **a4,
        void **a5)
{
  void *v9; // rax
  DWORD LastError; // ebx
  const char *v11; // r9
  int v12; // r8d
  HRESULT PartW; // eax
  void *v14; // r12
  unsigned int i; // ebx
  void *v16; // rax
  BOOL v17; // eax
  void *v18; // rcx
  DWORD v19; // eax
  const char *v20; // r9
  int v21; // r8d
  DWORD ppwszAcceptTypesa; // [rsp+28h] [rbp-D8h]
  DWORD pcchOut; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer[3]; // [rsp+44h] [rbp-BCh] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszOut[264]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  *a5 = 0;
  *a4 = 0;
  pcchOut = 0;
  Buffer[0] = 0;
  v9 = WinHttpOpen(L"CloudSdb", dwAccessType, 0, 0, 0);
  *a5 = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"PatchDb_SendRequest",
      1417,
      (unsigned int)"Error starting internet session : [%d].");
    goto LABEL_28;
  }
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwUrlPathLength = 1;
  if ( !WinHttpCrackUrl(a1, 0, 0, &UrlComponents) )
  {
    ppwszAcceptTypesa = GetLastError();
    v11 = "Could not crack url [%ws]: [%d].";
    v12 = 1430;
    LastError = ppwszAcceptTypesa;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"PatchDb_SendRequest", v12, (_DWORD)v11);
    goto LABEL_28;
  }
  pcchOut = 260;
  PartW = UrlGetPartW(a1, pszOut, &pcchOut, 2u, 0);
  LastError = PartW;
  if ( PartW < 0 )
  {
    if ( (PartW & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)PartW;
    v11 = "Failed to get host name from [%ws] %x";
    v12 = 1440;
    goto LABEL_5;
  }
  v14 = WinHttpConnect(*a5, pszOut, 0x50u, 0);
  if ( v14 )
  {
    PatchSdb_SetProxyInfo(a5, a1);
    for ( i = 0; ; ++i )
    {
      v16 = WinHttpOpenRequest(v14, 0, (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, ppwszAcceptTypes, 0x100u);
      *a4 = v16;
      if ( !v16 )
        break;
      Buffer[0] = 3;
      if ( !WinHttpSetOption(v16, 0x3Fu, Buffer, 4u) )
      {
        v19 = GetLastError();
        v20 = "Failed to disable redirects and cookies %d";
        v21 = 1483;
        goto LABEL_25;
      }
      if ( !WinHttpAddRequestHeaders(*a4, L"Accept: text/*\r\nUser-Agent: CloudSdb\r\n", 0xFFFFFFFF, 0) )
      {
        v19 = GetLastError();
        v20 = "Failed to set headers  %x";
        v21 = 1489;
        goto LABEL_25;
      }
      v17 = WinHttpSendRequest(*a4, 0, 0, 0, 0, 0, 0);
      v18 = *a4;
      if ( v17 )
      {
        if ( WinHttpReceiveResponse(v18, 0) )
        {
          LastError = 0;
          goto LABEL_27;
        }
        v19 = GetLastError();
        v20 = "Failed to receive response: [%d].";
        v21 = 1518;
        goto LABEL_25;
      }
      WinHttpCloseHandle(v18);
      *a4 = 0;
      if ( i >= 2 )
      {
        v19 = GetLastError();
        v20 = "Failed to connect to the internet %d";
        v21 = 1511;
LABEL_25:
        LastError = v19;
        AslLogCallPrintf(1, (unsigned int)"PatchDb_SendRequest", v21, (_DWORD)v20);
        goto LABEL_27;
      }
      Sleep(0x1F4u);
    }
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"PatchDb_SendRequest",
      1476,
      (unsigned int)"Failed to open http request [%ws]: [%d].");
LABEL_27:
    WinHttpCloseHandle(v14);
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"PatchDb_SendRequest",
      1451,
      (unsigned int)"Failed to connect to the host [%ws] %d\n");
  }
LABEL_28:
  if ( LastError )
  {
    if ( *a5 )
    {
      WinHttpCloseHandle(*a5);
      *a5 = 0;
    }
    if ( *a4 )
    {
      WinHttpCloseHandle(*a4);
      *a4 = 0;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180087c20  push    rbp
0x180087c22  push    rbx
0x180087c23  push    rsi
0x180087c24  push    rdi
0x180087c25  push    r12
0x180087c27  push    r13
0x180087c29  push    r14
0x180087c2b  push    r15
0x180087c2d  lea     rbp, [rsp-1E8h]
0x180087c35  sub     rsp, 2E8h
0x180087c3c  mov     rax, cs:__security_cookie
0x180087c43  xor     rax, rsp
0x180087c46  mov     [rbp+220h+var_50], rax
0x180087c4d  mov     r15, [rbp+220h+arg_20]
0x180087c54  mov     r13, r8
0x180087c57  mov     ebx, edx
0x180087c59  mov     r14, rcx
0x180087c5c  mov     edi, 68h ; 'h'
0x180087c61  lea     rcx, [rsp+320h+UrlComponents]; void *
0x180087c66  mov     r8d, edi; Size
0x180087c69  xor     edx, edx; Val
0x180087c6b  mov     rsi, r9
0x180087c6e  call    memset_0
0x180087c73  xor     r12d, r12d
0x180087c76  lea     rcx, aCloudsdb; "CloudSdb"
0x180087c7d  mov     [r15], r12
0x180087c80  xor     r9d, r9d; pszProxyBypassW
0x180087c83  xor     r8d, r8d; pszProxyW
0x180087c86  mov     [rsi], r12
0x180087c89  mov     edx, ebx; dwAccessType
0x180087c8b  mov     [rsp+320h+pcchOut], r12d
0x180087c90  mov     [rsp+320h+Buffer], r12d
0x180087c95  mov     [rsp+320h+dwFlags], r12d; dwFlags
0x180087c9a  call    cs:__imp_WinHttpOpen
0x180087ca0  mov     [r15], rax
0x180087ca3  test    rax, rax
0x180087ca6  jnz     short loc_180087CD5
0x180087ca8  call    cs:__imp_GetLastError
0x180087cae  lea     r9, aErrorStartingI; "Error starting internet session : [%d]."
0x180087cb5  mov     r8d, 589h
0x180087cbb  lea     rdx, aPatchdbSendreq; "PatchDb_SendRequest"
0x180087cc2  mov     [rsp+320h+dwFlags], eax
0x180087cc6  lea     ecx, [rdi-67h]
0x180087cc9  mov     ebx, eax
0x180087ccb  call    AslLogCallPrintf
0x180087cd0  jmp     loc_180087F65
0x180087cd5  mov     r8, rdi; Size
0x180087cd8  lea     rcx, [rsp+320h+UrlComponents]; void *
0x180087cdd  xor     edx, edx; Val
0x180087cdf  call    memset_0
0x180087ce4  mov     [rsp+320h+UrlComponents.dwStructSize], edi
0x180087ce8  lea     r9, [rsp+320h+UrlComponents]; lpUrlComponents
0x180087ced  mov     edi, 1
0x180087cf2  xor     r8d, r8d; dwFlags
0x180087cf5  xor     edx, edx; dwUrlLength
0x180087cf7  mov     [rbp+220h+UrlComponents.dwUrlPathLength], edi
0x180087cfa  mov     rcx, r14; pwszUrl
0x180087cfd  call    cs:__imp_WinHttpCrackUrl
0x180087d03  test    eax, eax
0x180087d05  jnz     short loc_180087D38
0x180087d07  call    cs:__imp_GetLastError
0x180087d0d  mov     dword ptr [rsp+320h+ppwszAcceptTypes], eax
0x180087d11  lea     r9, aCouldNotCrackU; "Could not crack url [%ws]: [%d]."
0x180087d18  mov     qword ptr [rsp+320h+dwFlags], r14
0x180087d1d  mov     r8d, 596h
0x180087d23  mov     ebx, eax
0x180087d25  lea     rdx, aPatchdbSendreq; "PatchDb_SendRequest"
0x180087d2c  mov     ecx, edi
0x180087d2e  call    AslLogCallPrintf
0x180087d33  jmp     loc_180087F65
0x180087d38  mov     r9d, 2; dwPart
0x180087d3e  mov     [rsp+320h+pcchOut], 104h
0x180087d46  lea     r8, [rsp+320h+pcchOut]; pcchOut
0x180087d4b  mov     [rsp+320h+dwFlags], r12d; dwFlags
0x180087d50  lea     rdx, [rbp+220h+pszOut]; pszOut
0x180087d54  mov     rcx, r14; pszIn
0x180087d57  call    cs:__imp_UrlGetPartW
0x180087d5d  mov     ebx, eax
0x180087d5f  test    eax, eax
0x180087d61  jns     short loc_180087D8E
0x180087d63  and     eax, 1FFF0000h
0x180087d68  cmp     eax, 70000h
0x180087d6d  jnz     short loc_180087D72
0x180087d6f  movzx   ebx, bx
0x180087d72  lea     rax, [rbp+220h+pszOut]
0x180087d76  mov     dword ptr [rsp+320h+ppwszAcceptTypes], ebx
0x180087d7a  mov     qword ptr [rsp+320h+dwFlags], rax
0x180087d7f  lea     r9, aFailedToGetHos; "Failed to get host name from [%ws] %x"
0x180087d86  mov     r8d, 5A0h
0x180087d8c  jmp     short loc_180087D25
0x180087d8e  mov     rcx, [r15]; hSession
0x180087d91  lea     rdx, [rbp+220h+pszOut]; pswzServerName
0x180087d95  mov     r8d, 50h ; 'P'; nServerPort
0x180087d9b  xor     r9d, r9d; dwReserved
0x180087d9e  call    cs:__imp_WinHttpConnect
0x180087da4  mov     r12, rax
0x180087da7  test    rax, rax
0x180087daa  jnz     short loc_180087DE1
0x180087dac  call    cs:__imp_GetLastError
0x180087db2  mov     dword ptr [rsp+320h+ppwszAcceptTypes], eax
0x180087db6  lea     r9, aFailedToConnec_0; "Failed to connect to the host [%ws] %d"...
0x180087dbd  mov     r8d, 5ABh
0x180087dc3  lea     rdx, aPatchdbSendreq; "PatchDb_SendRequest"
0x180087dca  mov     ebx, eax
0x180087dcc  mov     ecx, edi
0x180087dce  lea     rax, [rbp+220h+pszOut]
0x180087dd2  mov     qword ptr [rsp+320h+dwFlags], rax
0x180087dd7  call    AslLogCallPrintf
0x180087ddc  jmp     loc_180087F62
0x180087de1  mov     rdx, r14; unsigned __int16 *
0x180087de4  mov     rcx, r15; void **
0x180087de7  call    ?PatchSdb_SetProxyInfo@@YAKAEAPEAXPEBG@Z; PatchSdb_SetProxyInfo(void * &,ushort const *)
0x180087dec  xor     r14d, r14d
0x180087def  mov     ebx, r14d
0x180087df2  mov     r8, [rbp+220h+UrlComponents.lpszUrlPath]; pwszObjectName
0x180087df6  xor     r9d, r9d; pwszVersion
0x180087df9  mov     [rsp+320h+var_2F0], 100h; dwFlags
0x180087e01  xor     edx, edx; pwszVerb
0x180087e03  mov     [rsp+320h+ppwszAcceptTypes], r13; ppwszAcceptTypes
0x180087e08  mov     rcx, r12; hConnect
0x180087e0b  mov     qword ptr [rsp+320h+dwFlags], r14; pwszReferrer
0x180087e10  call    cs:__imp_WinHttpOpenRequest
0x180087e16  mov     [rsi], rax
0x180087e19  test    rax, rax
0x180087e1c  jz      loc_180087F29
0x180087e22  mov     r9d, 4; dwBufferLength
0x180087e28  mov     [rsp+320h+Buffer], 3
0x180087e30  lea     r8, [rsp+320h+Buffer]; lpBuffer
0x180087e35  mov     rcx, rax; hInternet
0x180087e38  lea     edx, [r9+3Bh]; dwOption
0x180087e3c  call    cs:__imp_WinHttpSetOption
0x180087e42  test    eax, eax
0x180087e44  jz      loc_180087F00
0x180087e4a  mov     rcx, [rsi]; hRequest
0x180087e4d  lea     rdx, szHeaders; "Accept: text/*\r\nUser-Agent: CloudSdb"...
0x180087e54  xor     r9d, r9d; dwModifiers
0x180087e57  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180087e5b  call    cs:__imp_WinHttpAddRequestHeaders
0x180087e61  test    eax, eax
0x180087e63  jz      loc_180087EEB
0x180087e69  mov     rcx, [rsi]; hRequest
0x180087e6c  xor     r9d, r9d; lpOptional
0x180087e6f  mov     qword ptr [rsp+320h+var_2F0], r14; dwContext
0x180087e74  xor     r8d, r8d; dwHeadersLength
0x180087e77  mov     dword ptr [rsp+320h+ppwszAcceptTypes], r14d; dwTotalLength
0x180087e7c  xor     edx, edx; lpszHeaders
0x180087e7e  mov     [rsp+320h+dwFlags], r14d; dwOptionalLength
0x180087e83  call    cs:__imp_WinHttpSendRequest
0x180087e89  mov     rcx, [rsi]; hRequest
0x180087e8c  test    eax, eax
0x180087e8e  jnz     short loc_180087EC5
0x180087e90  call    cs:__imp_WinHttpCloseHandle
0x180087e96  mov     [rsi], r14
0x180087e99  cmp     ebx, 2
0x180087e9c  jnb     short loc_180087EB0
0x180087e9e  mov     ecx, 1F4h; dwMilliseconds
0x180087ea3  call    cs:__imp_Sleep
0x180087ea9  add     ebx, edi
0x180087eab  jmp     loc_180087DF2
0x180087eb0  call    cs:__imp_GetLastError
0x180087eb6  lea     r9, aFailedToConnec_1; "Failed to connect to the internet %d"
0x180087ebd  mov     r8d, 5E7h
0x180087ec3  jmp     short loc_180087F13
0x180087ec5  xor     edx, edx; lpReserved
0x180087ec7  call    cs:__imp_WinHttpReceiveResponse
0x180087ecd  test    eax, eax
0x180087ecf  jnz     short loc_180087EE6
0x180087ed1  call    cs:__imp_GetLastError
0x180087ed7  lea     r9, aFailedToReceiv; "Failed to receive response: [%d]."
0x180087ede  mov     r8d, 5EEh
0x180087ee4  jmp     short loc_180087F13
0x180087ee6  mov     ebx, r14d
0x180087ee9  jmp     short loc_180087F59
0x180087eeb  call    cs:__imp_GetLastError
0x180087ef1  lea     r9, aFailedToSetHea; "Failed to set headers  %x"
0x180087ef8  mov     r8d, 5D1h
0x180087efe  jmp     short loc_180087F13
0x180087f00  call    cs:__imp_GetLastError
0x180087f06  lea     r9, aFailedToDisabl; "Failed to disable redirects and cookies"...
0x180087f0d  mov     r8d, 5CBh
0x180087f13  lea     rdx, aPatchdbSendreq; "PatchDb_SendRequest"
0x180087f1a  mov     [rsp+320h+dwFlags], eax
0x180087f1e  mov     ecx, edi
0x180087f20  mov     ebx, eax
0x180087f22  call    AslLogCallPrintf
0x180087f27  jmp     short loc_180087F59
0x180087f29  call    cs:__imp_GetLastError
0x180087f2f  mov     dword ptr [rsp+320h+ppwszAcceptTypes], eax
0x180087f33  lea     r9, aFailedToOpenHt; "Failed to open http request [%ws]: [%d]"...
0x180087f3a  mov     r8d, 5C4h
0x180087f40  lea     rdx, aPatchdbSendreq; "PatchDb_SendRequest"
0x180087f47  mov     ebx, eax
0x180087f49  mov     ecx, edi
0x180087f4b  mov     rax, [rbp+220h+UrlComponents.lpszUrlPath]
0x180087f4f  mov     qword ptr [rsp+320h+dwFlags], rax
0x180087f54  call    AslLogCallPrintf
0x180087f59  mov     rcx, r12; hInternet
0x180087f5c  call    cs:__imp_WinHttpCloseHandle
0x180087f62  xor     r12d, r12d
0x180087f65  test    ebx, ebx
0x180087f67  jz      short loc_180087F8B
0x180087f69  mov     rcx, [r15]; hInternet
0x180087f6c  test    rcx, rcx
0x180087f6f  jz      short loc_180087F7A
0x180087f71  call    cs:__imp_WinHttpCloseHandle
0x180087f77  mov     [r15], r12
0x180087f7a  mov     rcx, [rsi]; hInternet
0x180087f7d  test    rcx, rcx
0x180087f80  jz      short loc_180087F8B
0x180087f82  call    cs:__imp_WinHttpCloseHandle
0x180087f88  mov     [rsi], r12
0x180087f8b  mov     eax, ebx
0x180087f8d  mov     rcx, [rbp+220h+var_50]
0x180087f94  xor     rcx, rsp; StackCookie
0x180087f97  call    __security_check_cookie
0x180087f9c  add     rsp, 2E8h
0x180087fa3  pop     r15
0x180087fa5  pop     r14
0x180087fa7  pop     r13
0x180087fa9  pop     r12
0x180087fab  pop     rdi
0x180087fac  pop     rsi
0x180087fad  pop     rbx
0x180087fae  pop     rbp
0x180087faf  retn
```
