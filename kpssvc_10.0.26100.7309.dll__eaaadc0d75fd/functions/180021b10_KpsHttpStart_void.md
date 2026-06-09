# KpsHttpStart(void)

- ea: `0x180021b10`
- end: `0x1800222e9`
- name: `?KpsHttpStart@@YAKXZ`
- size: `2009`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019ad0`
- `0x18002cf60`

## callees

- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae38`
- `0x18001e520`
- `0x18001eb40`
- `0x1800203ac`
- `0x180021b10`
- `0x180024be0`
- `0x1800268f0`
- `0x180026b40`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021bc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022147`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f9e`
- `WS2_32!__imp_WSAStartup` at `0x180021c8b`
- `WS2_32!__imp_WSAStartup` at `0x180021c8b`
- `WS2_32!__imp_WSACleanup` at `0x180021f78`
- `WS2_32!__imp_WSACleanup` at `0x180021f78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800221d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800221d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18002212f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18002212f`
- `ntdll!RtlLeaveCriticalSection` at `0x180022239`
- `ntdll!RtlLeaveCriticalSection` at `0x180022239`
- `ntdll!RtlInitializeCriticalSection` at `0x180021c27`
- `ntdll!RtlInitializeCriticalSection` at `0x180021c27`
- `ntdll!RtlEnterCriticalSection` at `0x1800221fe`
- `ntdll!RtlEnterCriticalSection` at `0x1800221fe`
- `ntdll!RtlDeleteCriticalSection` at `0x180021f8b`
- `ntdll!RtlDeleteCriticalSection` at `0x180021f8b`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180021f35`
- `HTTPAPI!HttpCloseUrlGroup` at `0x180021f35`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180021d89`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180021d89`
- `HTTPAPI!HttpCloseServerSession` at `0x180021f5b`
- `HTTPAPI!HttpCloseServerSession` at `0x180021f5b`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180021ea0`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180022087`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x1800220e4`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180021ea0`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180022087`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x1800220e4`
- `HTTPAPI!HttpCreateServerSession` at `0x180021d2e`
- `HTTPAPI!HttpCreateServerSession` at `0x180021d2e`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180021e4e`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180021e4e`
- `HTTPAPI!HttpCreateUrlGroup` at `0x180021ddf`
- `HTTPAPI!HttpCreateUrlGroup` at `0x180021ddf`
- `HTTPAPI!HttpInitialize` at `0x180021cdd`
- `HTTPAPI!HttpInitialize` at `0x180021cdd`
- `HTTPAPI!HttpTerminate` at `0x180021f6c`
- `HTTPAPI!HttpTerminate` at `0x180021f6c`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180021f48`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180021f48`

## pseudocode

```c
__int64 KpsHttpStart(void)
{
  DWORD LastError; // eax
  HTTPAPI_VERSION v1; // edi
  _QWORD *v2; // rbx
  NTSTATUS v3; // eax
  unsigned int v4; // eax
  ULONG v5; // eax
  ULONG ServerSession; // eax
  ULONG RequestQueue; // eax
  ULONG UrlGroup; // eax
  unsigned int v9; // ebx
  ULONG v10; // eax
  __int64 v11; // rcx
  ULONG v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int KpsIo; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  struct _KPS_IO *v21; // rbx
  _QWORD *v22; // rcx
  HTTPAPI_VERSION Version[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C8h] BYREF
  __int64 PropertyInformation; // [rsp+48h] [rbp-C0h] BYREF
  __int128 PropertyInformation_8; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE v28; // [rsp+68h] [rbp-A0h]
  WSAData WSAData; // [rsp+78h] [rbp-90h] BYREF
  struct _KPS_IO *lpMem[4]; // [rsp+218h] [rbp+110h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  Version[0] = (HTTPAPI_VERSION)2;
  v28 = 0;
  PropertyInformation_8 = 0;
  v24 = 0;
  PropertyInformation = 0;
  v27 = 0;
  lpMem[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
  h = CreateEventW(0, 1, 0, 0);
  if ( !h )
  {
    LastError = GetLastError();
    v1 = (HTTPAPI_VERSION)LastError;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_52;
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, LastError);
LABEL_51:
    v2 = WPP_GLOBAL_Control;
LABEL_52:
    memset_0(&KpsGlobalHttpState, 0, 0x70u);
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 1) != 0 )
    {
      Version[0] = v1;
      lpMem[2] = (struct _KPS_IO *)Version;
      lpMem[3] = (struct _KPS_IO *)4;
      McGenEventWrite_EventWriteTransfer(v15, HttpStartFailure, v16, 2, lpMem);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v2 + 28) & 0x10) != 0 )
      {
        WPP_SF_D(v2[2], 32, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *(unsigned int *)&v1);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
        WPP_SF_D(v2[2], 33, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *(unsigned int *)&v1);
    }
    return *(unsigned int *)&v1;
  }
  v3 = RtlInitializeCriticalSection(&stru_18003AC20);
  v1 = (HTTPAPI_VERSION)v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        (unsigned int)v3);
    goto LABEL_50;
  }
  qword_18003AC50 = (__int64)&qword_18003AC48;
  qword_18003AC48 = (__int64)&qword_18003AC48;
  v4 = WSAStartup(0x202u, &WSAData);
  v1 = (HTTPAPI_VERSION)v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v4);
    goto LABEL_49;
  }
  v5 = HttpInitialize(Version[0], 3u, 0);
  v1 = (HTTPAPI_VERSION)v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v5);
    goto LABEL_48;
  }
  ServerSession = HttpCreateServerSession(Version[0], &ServerSessionId, 0);
  v1 = (HTTPAPI_VERSION)ServerSession;
  if ( ServerSession )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, ServerSession);
    goto LABEL_47;
  }
  RequestQueue = HttpCreateRequestQueue(Version[0], 0, 0, 0, &RequestQueueHandle);
  v1 = (HTTPAPI_VERSION)RequestQueue;
  if ( RequestQueue )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, RequestQueue);
    goto LABEL_46;
  }
  UrlGroup = HttpCreateUrlGroup(ServerSessionId, &UrlGroupId, 0);
  v1 = (HTTPAPI_VERSION)UrlGroup;
  if ( UrlGroup )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, UrlGroup);
    goto LABEL_45;
  }
  v9 = 0;
  if ( *(&xmmword_18003A998 + 2) )
  {
    while ( 1 )
    {
      v10 = HttpAddUrlToUrlGroup(UrlGroupId, *(PCWSTR *)(xmmword_18003A998 + 16LL * v9 + 8), 0, 0);
      v1 = (HTTPAPI_VERSION)v10;
      if ( v10 )
        break;
      if ( ++v9 >= *(&xmmword_18003A998 + 2) )
        goto LABEL_35;
    }
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v11, HttpAddUrlFailure, *(_QWORD *)(xmmword_18003A998 + 16LL * v9 + 8), v10);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
        *(_QWORD *)(xmmword_18003A998 + 16LL * v9 + 8),
        v1.HttpApiMajorVersion);
    goto LABEL_44;
  }
LABEL_35:
  HIDWORD(v24) = dword_18003A9C4;
  DWORD1(PropertyInformation_8) = 0;
  *((_QWORD *)&PropertyInformation_8 + 1) = &v24;
  LODWORD(v24) = 1;
  v12 = HttpSetUrlGroupProperty(UrlGroupId, HttpServerQosProperty, &PropertyInformation_8, 0x10u);
  v1 = (HTTPAPI_VERSION)v12;
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v14 = 25;
LABEL_73:
    WPP_SF_D(v13[2], v14, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v12);
LABEL_44:
    HttpCloseUrlGroup(UrlGroupId);
LABEL_45:
    HttpCloseRequestQueue(RequestQueueHandle);
LABEL_46:
    HttpCloseServerSession(ServerSessionId);
LABEL_47:
    HttpTerminate(3u, 0);
LABEL_48:
    WSACleanup();
LABEL_49:
    RtlDeleteCriticalSection(&stru_18003AC20);
LABEL_50:
    CloseHandle(h);
    goto LABEL_51;
  }
  HIDWORD(PropertyInformation) = dword_18003A9C8;
  *(_QWORD *)&PropertyInformation_8 = 1;
  *((_QWORD *)&PropertyInformation_8 + 1) = &PropertyInformation;
  LODWORD(PropertyInformation) = 1;
  v12 = HttpSetUrlGroupProperty(UrlGroupId, HttpServerQosProperty, &PropertyInformation_8, 0x10u);
  v1 = (HTTPAPI_VERSION)v12;
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v14 = 26;
    goto LABEL_73;
  }
  LODWORD(v27) = v27 | 1;
  v28 = RequestQueueHandle;
  v12 = HttpSetUrlGroupProperty(UrlGroupId, HttpServerBindingProperty, &v27, 0x10u);
  v1 = (HTTPAPI_VERSION)v12;
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v14 = 27;
    goto LABEL_73;
  }
  pio = CreateThreadpoolIo(RequestQueueHandle, KpsHttpIoCompletion, 0, &pcbe);
  if ( !pio )
  {
    v12 = GetLastError();
    v1 = (HTTPAPI_VERSION)v12;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v14 = 28;
    goto LABEL_73;
  }
  KpsIo = KpsCreateKpsIo(lpMem);
  v1 = (HTTPAPI_VERSION)KpsIo;
  if ( KpsIo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, KpsIo);
    if ( lpMem[0] )
      KpsFreeKpsIo(lpMem[0]);
    CloseThreadpoolIo(pio);
    goto LABEL_44;
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)lpMem[0] + 288));
  KpsDoHttpReceiveRequest((LPOVERLAPPED *)lpMem);
  v21 = lpMem[0];
  if ( lpMem[0] && !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)lpMem) )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v21 + 288));
  KpsGlobalHttpState = 1;
  if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v19, HttpStartSuccess, v20, 1, lpMem);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
      v22 = WPP_GLOBAL_Control;
    }
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x20) != 0 )
      WPP_SF_(v22[2], 31, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180021b10  mov     rax, rsp
0x180021b13  mov     [rax+8], rbx
0x180021b17  mov     [rax+10h], rsi
0x180021b1b  mov     [rax+18h], rdi
0x180021b1f  push    rbp
0x180021b20  push    r12
0x180021b22  push    r13
0x180021b24  push    r14
0x180021b26  push    r15
0x180021b28  lea     rbp, [rax-168h]
0x180021b2f  sub     rsp, 240h
0x180021b36  mov     rax, cs:__security_cookie
0x180021b3d  xor     rax, rsp
0x180021b40  mov     [rbp+160h+var_30], rax
0x180021b47  xor     edx, edx; Val
0x180021b49  lea     rcx, [rsp+260h+WSAData]; void *
0x180021b4e  mov     r8d, 198h; Size
0x180021b54  call    memset_0
0x180021b59  xor     r15d, r15d
0x180021b5c  mov     esi, 2
0x180021b61  xor     eax, eax
0x180021b63  mov     dword ptr [rsp+260h+Version.HttpApiMajorVersion], esi
0x180021b67  xorps   xmm0, xmm0
0x180021b6a  mov     [rsp+260h+var_200], rax
0x180021b6f  movups  [rsp+260h+PropertyInformation+8], xmm0
0x180021b74  mov     [rsp+260h+var_228], r15
0x180021b79  mov     qword ptr [rsp+260h+PropertyInformation], r15
0x180021b7e  mov     [rsp+260h+var_208], r15
0x180021b83  mov     [rbp+160h+lpMem], r15
0x180021b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b91  lea     r12, WPP_GLOBAL_Control
0x180021b98  lea     r13, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180021b9f  cmp     rcx, r12
0x180021ba2  jz      short loc_180021BB9
0x180021ba4  test    byte ptr [rcx+1Ch], 20h
0x180021ba8  jz      short loc_180021BB9
0x180021baa  mov     rcx, [rcx+10h]
0x180021bae  lea     edx, [rsi+0Eh]
0x180021bb1  mov     r8, r13
0x180021bb4  call    WPP_SF_
0x180021bb9  xor     r9d, r9d; lpName
0x180021bbc  xor     r8d, r8d; bInitialState
0x180021bbf  xor     ecx, ecx; lpEventAttributes
0x180021bc1  lea     r14d, [r9+1]
0x180021bc5  mov     edx, r14d; bManualReset
0x180021bc8  call    cs:__imp_CreateEventW
0x180021bcf  nop     dword ptr [rax+rax+00h]
0x180021bd4  mov     cs:h, rax
0x180021bdb  test    rax, rax
0x180021bde  jnz     short loc_180021C20
0x180021be0  call    cs:__imp_GetLastError
0x180021be7  nop     dword ptr [rax+rax+00h]
0x180021bec  mov     edi, eax
0x180021bee  mov     rbx, cs:WPP_GLOBAL_Control
0x180021bf5  cmp     rbx, r12
0x180021bf8  jz      loc_180021FB1
0x180021bfe  test    [rbx+1Ch], r14b
0x180021c02  jz      loc_180021FB1
0x180021c08  mov     rcx, [rbx+10h]
0x180021c0c  lea     edx, [r14+10h]
0x180021c10  mov     r9d, eax
0x180021c13  mov     r8, r13
0x180021c16  call    WPP_SF_D
0x180021c1b  jmp     loc_180021FAA
0x180021c20  lea     rcx, stru_18003AC20; CriticalSection
0x180021c27  call    cs:__imp_RtlInitializeCriticalSection
0x180021c2e  nop     dword ptr [rax+rax+00h]
0x180021c33  mov     edi, eax
0x180021c35  test    eax, eax
0x180021c37  jns     short loc_180021C6C
0x180021c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c40  cmp     rcx, r12
0x180021c43  jz      loc_180021F97
0x180021c49  test    [rcx+1Ch], r14b
0x180021c4d  jz      loc_180021F97
0x180021c53  mov     rcx, [rcx+10h]
0x180021c57  mov     edx, 12h
0x180021c5c  mov     r9d, eax
0x180021c5f  mov     r8, r13
0x180021c62  call    WPP_SF_D
0x180021c67  jmp     loc_180021F97
0x180021c6c  lea     rax, qword_18003AC48
0x180021c73  mov     ecx, 202h; wVersionRequested
0x180021c78  lea     rdx, [rsp+260h+WSAData]; lpWSAData
0x180021c7d  mov     cs:qword_18003AC50, rax
0x180021c84  mov     cs:qword_18003AC48, rax
0x180021c8b  call    cs:__imp_WSAStartup
0x180021c92  nop     dword ptr [rax+rax+00h]
0x180021c97  mov     edi, eax
0x180021c99  test    eax, eax
0x180021c9b  jz      short loc_180021CD0
0x180021c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ca4  cmp     rcx, r12
0x180021ca7  jz      loc_180021F84
0x180021cad  test    [rcx+1Ch], r14b
0x180021cb1  jz      loc_180021F84
0x180021cb7  mov     rcx, [rcx+10h]
0x180021cbb  mov     edx, 13h
0x180021cc0  mov     r9d, eax
0x180021cc3  mov     r8, r13
0x180021cc6  call    WPP_SF_D
0x180021ccb  jmp     loc_180021F84
0x180021cd0  mov     ebx, dword ptr [rsp+260h+Version.HttpApiMajorVersion]
0x180021cd4  xor     r8d, r8d; pReserved
0x180021cd7  mov     ecx, ebx; Version
0x180021cd9  lea     edx, [r8+3]; Flags
0x180021cdd  call    cs:__imp_HttpInitialize
0x180021ce4  nop     dword ptr [rax+rax+00h]
0x180021ce9  mov     edi, eax
0x180021ceb  test    eax, eax
0x180021ced  jz      short loc_180021D22
0x180021cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cf6  cmp     rcx, r12
0x180021cf9  jz      loc_180021F78
0x180021cff  test    [rcx+1Ch], r14b
0x180021d03  jz      loc_180021F78
0x180021d09  mov     rcx, [rcx+10h]
0x180021d0d  mov     edx, 14h
0x180021d12  mov     r9d, eax
0x180021d15  mov     r8, r13
0x180021d18  call    WPP_SF_D
0x180021d1d  jmp     loc_180021F78
0x180021d22  xor     r8d, r8d; Reserved
0x180021d25  lea     rdx, ServerSessionId; ServerSessionId
0x180021d2c  mov     ecx, ebx; Version
0x180021d2e  call    cs:__imp_HttpCreateServerSession
0x180021d35  nop     dword ptr [rax+rax+00h]
0x180021d3a  mov     edi, eax
0x180021d3c  test    eax, eax
0x180021d3e  jz      short loc_180021D73
0x180021d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d47  cmp     rcx, r12
0x180021d4a  jz      loc_180021F67
0x180021d50  test    [rcx+1Ch], r14b
0x180021d54  jz      loc_180021F67
0x180021d5a  mov     rcx, [rcx+10h]
0x180021d5e  mov     edx, 15h
0x180021d63  mov     r9d, eax
0x180021d66  mov     r8, r13
0x180021d69  call    WPP_SF_D
0x180021d6e  jmp     loc_180021F67
0x180021d73  lea     rax, RequestQueueHandle
0x180021d7a  xor     r9d, r9d; Flags
0x180021d7d  xor     r8d, r8d; SecurityAttributes
0x180021d80  mov     [rsp+260h+RequestQueueHandle], rax; RequestQueueHandle
0x180021d85  xor     edx, edx; Name
0x180021d87  mov     ecx, ebx; Version
0x180021d89  call    cs:__imp_HttpCreateRequestQueue
0x180021d90  nop     dword ptr [rax+rax+00h]
0x180021d95  mov     edi, eax
0x180021d97  test    eax, eax
0x180021d99  jz      short loc_180021DCE
0x180021d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021da2  cmp     rcx, r12
0x180021da5  jz      loc_180021F54
0x180021dab  test    [rcx+1Ch], r14b
0x180021daf  jz      loc_180021F54
0x180021db5  mov     rcx, [rcx+10h]
0x180021db9  mov     edx, 16h
0x180021dbe  mov     r9d, eax
0x180021dc1  mov     r8, r13
0x180021dc4  call    WPP_SF_D
0x180021dc9  jmp     loc_180021F54
0x180021dce  mov     rcx, cs:ServerSessionId; ServerSessionId
0x180021dd5  lea     rdx, UrlGroupId; pUrlGroupId
0x180021ddc  xor     r8d, r8d; Reserved
0x180021ddf  call    cs:__imp_HttpCreateUrlGroup
0x180021de6  nop     dword ptr [rax+rax+00h]
0x180021deb  mov     edi, eax
0x180021ded  test    eax, eax
0x180021def  jz      short loc_180021E24
0x180021df1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021df8  cmp     rcx, r12
0x180021dfb  jz      loc_180021F41
0x180021e01  test    [rcx+1Ch], r14b
0x180021e05  jz      loc_180021F41
0x180021e0b  mov     rcx, [rcx+10h]
0x180021e0f  mov     edx, 17h
0x180021e14  mov     r9d, eax
0x180021e17  mov     r8, r13
0x180021e1a  call    WPP_SF_D
0x180021e1f  jmp     loc_180021F41
0x180021e24  cmp     dword ptr cs:xmmword_18003A998+8, r15d
0x180021e2b  mov     ebx, r15d
0x180021e2e  jbe     short loc_180021E6E
0x180021e30  mov     rdx, qword ptr cs:xmmword_18003A998
0x180021e37  xor     r9d, r9d; Reserved
0x180021e3a  mov     rcx, cs:UrlGroupId; UrlGroupId
0x180021e41  xor     r8d, r8d; UrlContext
0x180021e44  mov     esi, ebx
0x180021e46  add     rsi, rsi
0x180021e49  mov     rdx, [rdx+rsi*8+8]; pFullyQualifiedUrl
0x180021e4e  call    cs:__imp_HttpAddUrlToUrlGroup
0x180021e55  nop     dword ptr [rax+rax+00h]
0x180021e5a  mov     edi, eax
0x180021e5c  test    eax, eax
0x180021e5e  jnz     short loc_180021ED2
0x180021e60  add     ebx, r14d
0x180021e63  cmp     ebx, dword ptr cs:xmmword_18003A998+8
0x180021e69  jb      short loc_180021E30
0x180021e6b  lea     esi, [rax+2]
0x180021e6e  mov     eax, cs:dword_18003A9C4
0x180021e74  lea     r8, [rsp+260h+PropertyInformation+8]; PropertyInformation
0x180021e79  mov     rcx, cs:UrlGroupId; UrlGroupId
0x180021e80  mov     r9d, 10h; PropertyInformationLength
0x180021e86  mov     dword ptr [rsp+260h+var_228+4], eax
0x180021e8a  mov     edx, esi; Property
0x180021e8c  lea     rax, [rsp+260h+var_228]
0x180021e91  mov     dword ptr [rsp+260h+PropertyInformation+0Ch], r15d
0x180021e96  mov     [rsp+260h+var_210], rax
0x180021e9b  mov     dword ptr [rsp+260h+var_228], r14d
0x180021ea0  call    cs:__imp_HttpSetUrlGroupProperty
0x180021ea7  nop     dword ptr [rax+rax+00h]
0x180021eac  mov     edi, eax
0x180021eae  test    eax, eax
0x180021eb0  jz      loc_180022055
0x180021eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ebd  cmp     rcx, r12
0x180021ec0  jz      short loc_180021F2E
0x180021ec2  test    [rcx+1Ch], r14b
0x180021ec6  jz      short loc_180021F2E
0x180021ec8  mov     edx, 19h
0x180021ecd  jmp     loc_180022174
0x180021ed2  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, r14b
0x180021ed9  jz      short loc_180021EF6
0x180021edb  mov     r8, qword ptr cs:xmmword_18003A998
0x180021ee2  lea     rdx, HttpAddUrlFailure
0x180021ee9  mov     r9d, edi
0x180021eec  mov     r8, [r8+rsi*8+8]
0x180021ef1  call    McTemplateU0zq_EventWriteTransfer
0x180021ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180021efd  cmp     rcx, r12
0x180021f00  jz      short loc_180021F29
0x180021f02  test    [rcx+1Ch], r14b
0x180021f06  jz      short loc_180021F29
0x180021f08  mov     r9, qword ptr cs:xmmword_18003A998
0x180021f0f  mov     edx, 18h
0x180021f14  mov     rcx, [rcx+10h]
0x180021f18  mov     r8, r13
0x180021f1b  mov     dword ptr [rsp+260h+RequestQueueHandle], edi
0x180021f1f  mov     r9, [r9+rsi*8+8]
0x180021f24  call    WPP_SF_SD
0x180021f29  mov     esi, 2
0x180021f2e  mov     rcx, cs:UrlGroupId; UrlGroupId
0x180021f35  call    cs:__imp_HttpCloseUrlGroup
0x180021f3c  nop     dword ptr [rax+rax+00h]
0x180021f41  mov     rcx, cs:RequestQueueHandle; RequestQueueHandle
0x180021f48  call    cs:__imp_HttpCloseRequestQueue
0x180021f4f  nop     dword ptr [rax+rax+00h]
0x180021f54  mov     rcx, cs:ServerSessionId; ServerSessionId
0x180021f5b  call    cs:__imp_HttpCloseServerSession
0x180021f62  nop     dword ptr [rax+rax+00h]
0x180021f67  xor     edx, edx; pReserved
0x180021f69  lea     ecx, [rdx+3]; Flags
0x180021f6c  call    cs:__imp_HttpTerminate
0x180021f73  nop     dword ptr [rax+rax+00h]
0x180021f78  call    cs:__imp_WSACleanup
0x180021f7f  nop     dword ptr [rax+rax+00h]
0x180021f84  lea     rcx, stru_18003AC20; CriticalSection
0x180021f8b  call    cs:__imp_RtlDeleteCriticalSection
0x180021f92  nop     dword ptr [rax+rax+00h]
0x180021f97  mov     rcx, cs:h; hObject
0x180021f9e  call    cs:__imp_CloseHandle
0x180021fa5  nop     dword ptr [rax+rax+00h]
0x180021faa  mov     rbx, cs:WPP_GLOBAL_Control
0x180021fb1  xor     edx, edx; Val
0x180021fb3  lea     rcx, ?KpsGlobalHttpState@@3U_KPS_GLOBAL_HTTP_STATE@@A; void *
0x180021fba  lea     r8d, [rdx+70h]; Size
0x180021fbe  call    memset_0
0x180021fc3  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, r14b
0x180021fca  jz      short loc_180022009
0x180021fcc  lea     rax, [rsp+260h+Version]
0x180021fd1  mov     dword ptr [rsp+260h+Version.HttpApiMajorVersion], edi
0x180021fd5  mov     [rbp+160h+var_40], rax
0x180021fdc  lea     rdx, HttpStartFailure
0x180021fe3  lea     rax, [rbp+160h+lpMem]
0x180021fea  mov     [rbp+160h+var_38], 4
0x180021ff5  mov     r9d, esi
0x180021ff8  mov     [rsp+260h+RequestQueueHandle], rax
0x180021ffd  call    McGenEventWrite_EventWriteTransfer
0x180022002  mov     rbx, cs:WPP_GLOBAL_Control
0x180022009  cmp     rbx, r12
0x18002200c  jz      short loc_18002204E
0x18002200e  test    byte ptr [rbx+1Ch], 10h
0x180022012  jz      short loc_18002202F
0x180022014  mov     rcx, [rbx+10h]
0x180022018  mov     edx, 20h ; ' '
0x18002201d  mov     r9d, edi
0x180022020  mov     r8, r13
0x180022023  call    WPP_SF_D
0x180022028  mov     rbx, cs:WPP_GLOBAL_Control
0x18002202f  cmp     rbx, r12
0x180022032  jz      short loc_18002204E
0x180022034  test    byte ptr [rbx+1Ch], 20h
0x180022038  jz      short loc_18002204E
0x18002203a  mov     rcx, [rbx+10h]
0x18002203e  mov     edx, 21h ; '!'
0x180022043  mov     r9d, edi
0x180022046  mov     r8, r13
0x180022049  call    WPP_SF_D
  ... truncated ...
```
