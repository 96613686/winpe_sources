# GetNetworkName(ushort * *,sockaddr_storage *)

- ea: `0x18006e59c`
- end: `0x18006ea3c`
- name: `?GetNetworkName@@YAHPEAPEAGPEAUsockaddr_storage@@@Z`
- size: `1184`
- prototype: `int(unsigned __int16 **, struct sockaddr_storage *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x18005ce5c`

## callees

- `0x18004e9a0`
- `0x18006e59c`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9d7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006e939`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006e939`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e854`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e98a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e854`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e98a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e9cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e9ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e9cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e9ec`
- `WS2_32!WSALookupServiceEnd` at `0x18006ea03`
- `WS2_32!WSALookupServiceEnd` at `0x18006ea03`
- `WS2_32!WSALookupServiceBeginW` at `0x18006e797`
- `WS2_32!WSALookupServiceBeginW` at `0x18006e797`
- `WS2_32!WSALookupServiceNextW` at `0x18006e81a`
- `WS2_32!WSALookupServiceNextW` at `0x18006e881`
- `WS2_32!WSALookupServiceNextW` at `0x18006e81a`
- `WS2_32!WSALookupServiceNextW` at `0x18006e881`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e7a1`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e820`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e9e1`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e7a1`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e820`
- `WS2_32!__imp_WSAGetLastError` at `0x18006e9e1`
- `WS2_32!__imp_WSAStartup` at `0x18006e6f3`
- `WS2_32!__imp_WSAStartup` at `0x18006e6f3`
- `WS2_32!__imp_WSACleanup` at `0x18006e7a9`
- `WS2_32!__imp_WSACleanup` at `0x18006ea09`
- `WS2_32!__imp_WSACleanup` at `0x18006e7a9`
- `WS2_32!__imp_WSACleanup` at `0x18006ea09`
- `IPHLPAPI!GetAdapterIndex` at `0x18006e94f`
- `IPHLPAPI!GetAdapterIndex` at `0x18006e94f`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18006e62f`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18006e62f`

## string_xrefs

- `0x18006e7c8`: `GetNetworkName:  WSALookupServiceBegin failed with 0x%x`
- `0x18006e7ee`: `GetNetworkName:  WSALookupServiceBegin failed with 0x%x`

## pseudocode

```c
__int64 __fastcall GetNetworkName(unsigned __int16 **a1, struct sockaddr *a2)
{
  DWORD BestInterface; // ebx
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v6; // rdx
  DWORD LastError; // edi
  int v9; // r14d
  int Error; // eax
  struct _WSAQuerySetW *v11; // rsi
  LPBLOB lpBlob; // rbx
  BYTE *pBlobData; // rbx
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  __int64 v16; // rcx
  WCHAR *v17; // r8
  __int64 v18; // r9
  WCHAR *v19; // rcx
  __int64 v20; // rdx
  LPWSTR lpszServiceInstanceName; // rcx
  __int64 v22; // rax
  SIZE_T v23; // rdi
  unsigned __int16 *v24; // rax
  __int64 v25; // rcx
  int v26; // ebx
  DWORD dwBufferLength; // [rsp+30h] [rbp-D0h] BYREF
  ULONG IfIndex; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pdwBestIfIndex; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hLookup; // [rsp+40h] [rbp-C0h] BYREF
  _WSAQuerySetW qsRestrictions; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v32[4]; // [rsp+D0h] [rbp-30h] BYREF
  struct WSAData WSAData; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR AdapterName[64]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&qsRestrictions, 0, sizeof(qsRestrictions));
  v32[0] = 3663125;
  v32[1] = 1245951433;
  v32[2] = 1217125050;
  v32[3] = 970095272;
  memset_0(&WSAData, 0, sizeof(WSAData));
  hLookup = 0;
  dwBufferLength = 0;
  pdwBestIfIndex = 0;
  BestInterface = GetBestInterfaceEx(a2, &pdwBestIfIndex);
  if ( BestInterface )
  {
    v5 = g_lpDebugMsg;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      return BestInterface;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"GetAdapterIndexForIPAddress: GetBestInterface failed with %d", BestInterface);
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_9:
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( !v5 )
          {
            if ( g_lpDebugMsgContextInstance )
            {
              if ( g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"GetNetworkName:  GetAdapterIndexForIPAddress failed with 0x%x", BestInterface);
            }
            return BestInterface;
          }
          v6 = L"GetNetworkName:  GetAdapterIndexForIPAddress failed with 0x%x";
LABEL_12:
          v5(2u, v6, BestInterface);
        }
        return BestInterface;
      }
      RedirectDebugMsg(2u, L"GetAdapterIndexForIPAddress: GetBestInterface failed with %d", BestInterface);
    }
    v5 = g_lpDebugMsg;
    goto LABEL_9;
  }
  LastError = WSAStartup(0x202u, &WSAData);
  if ( LastError )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GetNetworkName:  WSAStartup failed with 0x%x", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GetNetworkName:  WSAStartup failed with 0x%x", LastError);
      }
    }
    return LastError;
  }
  memset_0(&qsRestrictions, 0, sizeof(qsRestrictions));
  qsRestrictions.dwSize = 120;
  qsRestrictions.lpServiceClassId = (LPGUID)v32;
  qsRestrictions.dwNameSpace = 15;
  if ( WSALookupServiceBeginW(&qsRestrictions, 4u, &hLookup) )
  {
    BestInterface = WSAGetLastError();
    WSACleanup();
    if ( !*(_DWORD *)&g_dwDebugLevel )
      return BestInterface;
    v5 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"GetNetworkName:  WSALookupServiceBegin failed with 0x%x", BestInterface);
      return BestInterface;
    }
    v6 = L"GetNetworkName:  WSALookupServiceBegin failed with 0x%x";
    goto LABEL_12;
  }
  v9 = 0;
  while ( 1 )
  {
    if ( v9 )
      goto LABEL_64;
    dwBufferLength = 0;
    WSALookupServiceNextW(hLookup, 0, &dwBufferLength, 0);
    Error = WSAGetLastError();
    LastError = Error;
    if ( Error != 10014 && Error != 10110 )
      goto LABEL_64;
    v11 = 0;
    if ( Error == 10014 )
    {
      if ( !dwBufferLength )
        goto LABEL_39;
      v11 = (struct _WSAQuerySetW *)LocalAlloc(0x40u, dwBufferLength);
      if ( !v11 )
      {
        LastError = GetLastError();
        goto LABEL_64;
      }
    }
    if ( LastError == 10110 )
      break;
LABEL_39:
    if ( WSALookupServiceNextW(hLookup, 0, &dwBufferLength, v11) )
      break;
    if ( v11 )
    {
      lpBlob = v11->lpBlob;
      if ( lpBlob )
      {
        pBlobData = lpBlob->pBlobData;
        do
        {
          if ( *(_DWORD *)pBlobData == 1 )
          {
            IfIndex = 0;
            v14 = 64;
            v15 = L"\\DEVICE\\TCPIP_";
            v16 = 2147483646;
            v17 = AdapterName;
            v18 = 0;
            do
            {
              if ( !v16 )
                break;
              if ( !*v15 )
                break;
              *v17++ = *v15++;
              --v16;
              ++v18;
              --v14;
            }
            while ( v14 );
            v19 = v17 - 1;
            v20 = v18 - 1;
            if ( v14 )
            {
              v19 = v17;
              v20 = v18;
            }
            *v19 = 0;
            if ( !MultiByteToWideChar(0, 0, (LPCCH)pBlobData + 20, -1, &AdapterName[v20], 64 - v20) )
              goto LABEL_58;
            if ( GetAdapterIndex(AdapterName, &IfIndex) )
              goto LABEL_59;
            if ( pdwBestIfIndex != IfIndex )
              goto LABEL_59;
            lpszServiceInstanceName = v11->lpszServiceInstanceName;
            if ( !lpszServiceInstanceName )
              goto LABEL_59;
            v22 = -1;
            do
              ++v22;
            while ( lpszServiceInstanceName[v22] );
            v23 = 2 * v22 + 2;
            v24 = (unsigned __int16 *)LocalAlloc(0x40u, v23);
            *a1 = v24;
            if ( v24 )
            {
              StringCbCopyW(v24, v23, v11->lpszServiceInstanceName);
              v9 = 1;
              LastError = 0;
            }
            else
            {
LABEL_58:
              LastError = GetLastError();
            }
          }
LABEL_59:
          v25 = *((int *)pBlobData + 2);
          pBlobData += v25;
        }
        while ( (_DWORD)v25 );
      }
    }
    LocalFree(v11);
  }
  v26 = WSAGetLastError();
  LocalFree(v11);
  LastError = 0;
  if ( v26 != 10110 )
    LastError = v26;
LABEL_64:
  WSALookupServiceEnd(hLookup);
  WSACleanup();
  return LastError;
}

```

## disassembly

```asm
0x18006e59c  mov     [rsp-8+arg_10], rbx
0x18006e5a1  mov     [rsp-8+arg_18], rsi
0x18006e5a6  push    rbp
0x18006e5a7  push    rdi
0x18006e5a8  push    r12
0x18006e5aa  push    r14
0x18006e5ac  push    r15
0x18006e5ae  lea     rbp, [rsp-210h]
0x18006e5b6  sub     rsp, 310h
0x18006e5bd  mov     rax, cs:__security_cookie
0x18006e5c4  xor     rax, rsp
0x18006e5c7  mov     [rbp+230h+var_30], rax
0x18006e5ce  mov     rbx, rdx
0x18006e5d1  mov     r15, rcx
0x18006e5d4  mov     esi, 78h ; 'x'
0x18006e5d9  lea     rcx, [rsp+330h+qsRestrictions]; void *
0x18006e5de  mov     r8d, esi; Size
0x18006e5e1  xor     edx, edx; Val
0x18006e5e3  call    memset_0
0x18006e5e8  xor     edx, edx; Val
0x18006e5ea  mov     [rbp+230h+var_260], 37E515h
0x18006e5f1  mov     r8d, 198h; Size
0x18006e5f7  mov     [rbp+230h+var_25C], 4A43B5C9h
0x18006e5fe  lea     rcx, [rbp+230h+WSAData]; void *
0x18006e602  mov     [rbp+230h+var_258], 488BDABAh
0x18006e609  mov     [rbp+230h+var_254], 39D27AA8h
0x18006e610  call    memset_0
0x18006e615  xor     r12d, r12d
0x18006e618  lea     rdx, [rsp+330h+pdwBestIfIndex]; pdwBestIfIndex
0x18006e61d  mov     rcx, rbx; pDestAddr
0x18006e620  mov     [rsp+330h+hLookup], r12
0x18006e625  mov     [rsp+330h+dwBufferLength], r12d
0x18006e62a  mov     [rsp+330h+pdwBestIfIndex], r12d
0x18006e62f  call    cs:__imp_GetBestInterfaceEx
0x18006e635  mov     ebx, eax
0x18006e637  test    eax, eax
0x18006e639  jz      loc_18006E6EA
0x18006e63f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18006e646  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006e64d  jz      loc_18006E6E3
0x18006e653  test    rax, rax
0x18006e656  jz      short loc_18006E66C
0x18006e658  mov     r8d, ebx
0x18006e65b  lea     rdx, aGetadapterinde_0; "GetAdapterIndexForIPAddress: GetBestInt"...
0x18006e662  lea     ecx, [rsi-76h]
0x18006e665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e66a  jmp     short loc_18006E692
0x18006e66c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18006e673  jz      short loc_18006E699
0x18006e675  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006e67c  jz      short loc_18006E699
0x18006e67e  mov     r8d, ebx
0x18006e681  lea     rdx, aGetadapterinde_0; "GetAdapterIndexForIPAddress: GetBestInt"...
0x18006e688  mov     ecx, 2; unsigned int
0x18006e68d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006e692  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006e699  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18006e6a0  jz      short loc_18006E6E3
0x18006e6a2  test    rax, rax
0x18006e6a5  jz      short loc_18006E6BD
0x18006e6a7  lea     rdx, aGetnetworkname_1; "GetNetworkName:  GetAdapterIndexForIPAd"...
0x18006e6ae  mov     r8d, ebx
0x18006e6b1  mov     ecx, 2
0x18006e6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6bb  jmp     short loc_18006E6E3
0x18006e6bd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18006e6c4  jz      short loc_18006E6E3
0x18006e6c6  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006e6cd  jz      short loc_18006E6E3
0x18006e6cf  lea     rdx, aGetnetworkname_1; "GetNetworkName:  GetAdapterIndexForIPAd"...
0x18006e6d6  mov     r8d, ebx
0x18006e6d9  mov     ecx, 2; unsigned int
0x18006e6de  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006e6e3  mov     eax, ebx
0x18006e6e5  jmp     loc_18006EA11
0x18006e6ea  mov     ecx, 202h; wVersionRequested
0x18006e6ef  lea     rdx, [rbp+230h+WSAData]; lpWSAData
0x18006e6f3  call    cs:__imp_WSAStartup
0x18006e6f9  mov     edi, eax
0x18006e6fb  test    eax, eax
0x18006e6fd  jz      short loc_18006E764
0x18006e6ff  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18006e706  jz      loc_18006EA0F
0x18006e70c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006e713  test    rax, rax
0x18006e716  jz      short loc_18006E731
0x18006e718  mov     r8d, edi
0x18006e71b  lea     rdx, aGetnetworkname_0; "GetNetworkName:  WSAStartup failed with"...
0x18006e722  mov     ecx, 2
0x18006e727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e72c  jmp     loc_18006EA0F
0x18006e731  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18006e738  jz      loc_18006EA0F
0x18006e73e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006e745  jz      loc_18006EA0F
0x18006e74b  mov     r8d, edi
0x18006e74e  lea     rdx, aGetnetworkname_0; "GetNetworkName:  WSAStartup failed with"...
0x18006e755  mov     ecx, 2; unsigned int
0x18006e75a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006e75f  jmp     loc_18006EA0F
0x18006e764  mov     r8, rsi; Size
0x18006e767  lea     rcx, [rsp+330h+qsRestrictions]; void *
0x18006e76c  xor     edx, edx; Val
0x18006e76e  call    memset_0
0x18006e773  lea     rax, [rbp+230h+var_260]
0x18006e777  mov     [rsp+330h+qsRestrictions.dwSize], esi
0x18006e77b  lea     r8, [rsp+330h+hLookup]; lphLookup
0x18006e780  mov     [rsp+330h+qsRestrictions.lpServiceClassId], rax
0x18006e785  mov     edx, 4; dwControlFlags
0x18006e78a  mov     [rsp+330h+qsRestrictions.dwNameSpace], 0Fh
0x18006e792  lea     rcx, [rsp+330h+qsRestrictions]; lpqsRestrictions
0x18006e797  call    cs:__imp_WSALookupServiceBeginW
0x18006e79d  test    eax, eax
0x18006e79f  jz      short loc_18006E7FA
0x18006e7a1  call    cs:__imp_WSAGetLastError
0x18006e7a7  mov     ebx, eax
0x18006e7a9  call    cs:__imp_WSACleanup
0x18006e7af  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18006e7b6  jz      loc_18006E6E3
0x18006e7bc  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006e7c3  test    rax, rax
0x18006e7c6  jz      short loc_18006E7D4
0x18006e7c8  lea     rdx, aGetnetworkname; "GetNetworkName:  WSALookupServiceBegin "...
0x18006e7cf  jmp     loc_18006E6AE
0x18006e7d4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18006e7db  jz      loc_18006E6E3
0x18006e7e1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006e7e8  jz      loc_18006E6E3
0x18006e7ee  lea     rdx, aGetnetworkname; "GetNetworkName:  WSALookupServiceBegin "...
0x18006e7f5  jmp     loc_18006E6D6
0x18006e7fa  mov     r14d, r12d
0x18006e7fd  test    r14d, r14d
0x18006e800  jnz     loc_18006E9FE
0x18006e806  mov     rcx, [rsp+330h+hLookup]; hLookup
0x18006e80b  lea     r8, [rsp+330h+dwBufferLength]; lpdwBufferLength
0x18006e810  xor     r9d, r9d; lpqsResults
0x18006e813  mov     [rsp+330h+dwBufferLength], r12d
0x18006e818  xor     edx, edx; dwControlFlags
0x18006e81a  call    cs:__imp_WSALookupServiceNextW
0x18006e820  call    cs:__imp_WSAGetLastError
0x18006e826  mov     edi, eax
0x18006e828  cmp     eax, 271Eh
0x18006e82d  jz      short loc_18006E83A
0x18006e82f  cmp     eax, 277Eh
0x18006e834  jnz     loc_18006E9FE
0x18006e83a  mov     rsi, r12
0x18006e83d  cmp     edi, 271Eh
0x18006e843  jnz     short loc_18006E866
0x18006e845  mov     eax, [rsp+330h+dwBufferLength]
0x18006e849  test    eax, eax
0x18006e84b  jz      short loc_18006E872
0x18006e84d  mov     edx, eax; uBytes
0x18006e84f  mov     ecx, 40h ; '@'; uFlags
0x18006e854  call    cs:__imp_LocalAlloc
0x18006e85a  mov     rsi, rax
0x18006e85d  test    rax, rax
0x18006e860  jz      loc_18006E9D7
0x18006e866  cmp     edi, 277Eh
0x18006e86c  jz      loc_18006E9E1
0x18006e872  mov     rcx, [rsp+330h+hLookup]; hLookup
0x18006e877  lea     r8, [rsp+330h+dwBufferLength]; lpdwBufferLength
0x18006e87c  mov     r9, rsi; lpqsResults
0x18006e87f  xor     edx, edx; dwControlFlags
0x18006e881  call    cs:__imp_WSALookupServiceNextW
0x18006e887  test    eax, eax
0x18006e889  jnz     loc_18006E9E1
0x18006e88f  test    rsi, rsi
0x18006e892  jz      loc_18006E9C9
0x18006e898  mov     rbx, [rsi+70h]
0x18006e89c  test    rbx, rbx
0x18006e89f  jz      loc_18006E9C9
0x18006e8a5  mov     rbx, [rbx+8]
0x18006e8a9  cmp     dword ptr [rbx], 1
0x18006e8ac  jnz     loc_18006E9BA
0x18006e8b2  mov     r11d, 40h ; '@'
0x18006e8b8  mov     [rsp+330h+IfIndex], r12d
0x18006e8bd  mov     eax, r11d
0x18006e8c0  lea     rdx, aDeviceTcpip; "\\DEVICE\\TCPIP_"
0x18006e8c7  mov     ecx, 7FFFFFFEh
0x18006e8cc  lea     r8, [rbp+230h+AdapterName]
0x18006e8d3  mov     r9, r12
0x18006e8d6  test    rcx, rcx
0x18006e8d9  jz      short loc_18006E8FD
0x18006e8db  movzx   r10d, word ptr [rdx]
0x18006e8df  test    r10w, r10w
0x18006e8e3  jz      short loc_18006E8FD
0x18006e8e5  mov     [r8], r10w
0x18006e8e9  add     rdx, 2
0x18006e8ed  add     r8, 2
0x18006e8f1  dec     rcx
0x18006e8f4  inc     r9
0x18006e8f7  sub     rax, 1
0x18006e8fb  jnz     short loc_18006E8D6
0x18006e8fd  test    rax, rax
0x18006e900  lea     rcx, [r8-2]
0x18006e904  lea     rdx, [r9-1]
0x18006e908  cmovnz  rcx, r8
0x18006e90c  lea     rax, [rbp+230h+AdapterName]
0x18006e913  cmovnz  rdx, r9
0x18006e917  lea     r8, [rbx+14h]; lpMultiByteStr
0x18006e91b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18006e91f  mov     [rcx], r12w
0x18006e923  mov     ecx, r11d
0x18006e926  sub     ecx, edx
0x18006e928  lea     rax, [rax+rdx*2]
0x18006e92c  mov     [rsp+330h+cchWideChar], ecx; cchWideChar
0x18006e930  xor     edx, edx; dwFlags
0x18006e932  xor     ecx, ecx; CodePage
0x18006e934  mov     [rsp+330h+lpWideCharStr], rax; lpWideCharStr
0x18006e939  call    cs:__imp_MultiByteToWideChar
0x18006e93f  test    eax, eax
0x18006e941  jz      short loc_18006E9B2
0x18006e943  lea     rdx, [rsp+330h+IfIndex]; IfIndex
0x18006e948  lea     rcx, [rbp+230h+AdapterName]; AdapterName
0x18006e94f  call    cs:__imp_GetAdapterIndex
0x18006e955  test    eax, eax
0x18006e957  jnz     short loc_18006E9BA
0x18006e959  mov     eax, [rsp+330h+IfIndex]
0x18006e95d  cmp     [rsp+330h+pdwBestIfIndex], eax
0x18006e961  jnz     short loc_18006E9BA
0x18006e963  mov     rcx, [rsi+8]
0x18006e967  test    rcx, rcx
0x18006e96a  jz      short loc_18006E9BA
0x18006e96c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e970  inc     rax
0x18006e973  cmp     [rcx+rax*2], r12w
0x18006e978  jnz     short loc_18006E970
0x18006e97a  lea     rdi, ds:2[rax*2]
0x18006e982  mov     ecx, 40h ; '@'; uFlags
0x18006e987  mov     rdx, rdi; uBytes
0x18006e98a  call    cs:__imp_LocalAlloc
0x18006e990  mov     [r15], rax
0x18006e993  test    rax, rax
0x18006e996  jz      short loc_18006E9B2
0x18006e998  mov     r8, [rsi+8]; unsigned __int16 *
0x18006e99c  mov     rdx, rdi; unsigned __int64
0x18006e99f  mov     rcx, rax; unsigned __int16 *
0x18006e9a2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18006e9a7  mov     r14d, 1
0x18006e9ad  mov     edi, r12d
0x18006e9b0  jmp     short loc_18006E9BA
0x18006e9b2  call    cs:__imp_GetLastError
0x18006e9b8  mov     edi, eax
0x18006e9ba  movsxd  rcx, dword ptr [rbx+8]
0x18006e9be  add     rbx, rcx
0x18006e9c1  test    ecx, ecx
0x18006e9c3  jnz     loc_18006E8A9
0x18006e9c9  mov     rcx, rsi; hMem
0x18006e9cc  call    cs:__imp_LocalFree
0x18006e9d2  jmp     loc_18006E7FD
0x18006e9d7  call    cs:__imp_GetLastError
0x18006e9dd  mov     edi, eax
0x18006e9df  jmp     short loc_18006E9FE
0x18006e9e1  call    cs:__imp_WSAGetLastError
0x18006e9e7  mov     rcx, rsi; hMem
0x18006e9ea  mov     ebx, eax
0x18006e9ec  call    cs:__imp_LocalFree
0x18006e9f2  cmp     ebx, 277Eh
0x18006e9f8  mov     edi, r12d
0x18006e9fb  cmovnz  edi, ebx
0x18006e9fe  mov     rcx, [rsp+330h+hLookup]; hLookup
0x18006ea03  call    cs:__imp_WSALookupServiceEnd
0x18006ea09  call    cs:__imp_WSACleanup
0x18006ea0f  mov     eax, edi
0x18006ea11  mov     rcx, [rbp+230h+var_30]
0x18006ea18  xor     rcx, rsp; StackCookie
0x18006ea1b  call    __security_check_cookie
0x18006ea20  lea     r11, [rsp+330h+var_20]
0x18006ea28  mov     rbx, [r11+40h]
0x18006ea2c  mov     rsi, [r11+48h]
0x18006ea30  mov     rsp, r11
0x18006ea33  pop     r15
0x18006ea35  pop     r14
0x18006ea37  pop     r12
0x18006ea39  pop     rdi
0x18006ea3a  pop     rbp
0x18006ea3b  retn
```
