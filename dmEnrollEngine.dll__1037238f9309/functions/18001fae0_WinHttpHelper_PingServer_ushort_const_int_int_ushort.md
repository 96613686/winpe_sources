# WinHttpHelper::PingServer(ushort const *,int,int *,ushort * *)

- ea: `0x18001fae0`
- end: `0x180020053`
- name: `?PingServer@WinHttpHelper@@QEAAJPEBGHPEAHPEAPEAG@Z`
- size: `1395`
- prototype: `__int64 __fastcall(WinHttpHelper *__hidden this, const unsigned __int16 *, int, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800533ec`

## callees

- `0x18000d770`
- `0x18000de50`
- `0x1800128c4`
- `0x1800140d0`
- `0x18001fae0`
- `0x18002005c`
- `0x1800200c8`
- `0x1800206a8`
- `0x180021368`
- `0x18002e1a0`
- `0x18002ec68`
- `0x18003b068`
- `0x18003b118`
- `0x18003b170`
- `0x18004e314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fde2`
- `WINHTTP!WinHttpOpenRequest` at `0x18001fba0`
- `WINHTTP!WinHttpOpenRequest` at `0x18001fba0`
- `WINHTTP!WinHttpSetOption` at `0x18001fc5d`
- `WINHTTP!WinHttpSetOption` at `0x18001fcd5`
- `WINHTTP!WinHttpSetOption` at `0x18001fd7c`
- `WINHTTP!WinHttpSetOption` at `0x18001fc5d`
- `WINHTTP!WinHttpSetOption` at `0x18001fcd5`
- `WINHTTP!WinHttpSetOption` at `0x18001fd7c`
- `WINHTTP!WinHttpSendRequest` at `0x18001fd41`
- `WINHTTP!WinHttpSendRequest` at `0x18001fdcb`
- `WINHTTP!WinHttpSendRequest` at `0x18001fd41`
- `WINHTTP!WinHttpSendRequest` at `0x18001fdcb`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001fcfb`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001fff3`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001fcfb`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18001fff3`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001fe4f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001fe4f`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001fe7e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001fef1`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001ff47`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001fe7e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001fef1`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001ff47`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinHttpHelper::PingServer(
        HINTERNET *this,
        const unsigned __int16 *a2,
        int a3,
        int *a4,
        unsigned __int16 **a5)
{
  void *v8; // rbx
  DWORD dwFlags; // eax
  void *v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v14; // eax
  _DWORD *v15; // r14
  BOOL v16; // r15d
  signed int LastError; // eax
  DWORD v18; // eax
  __int64 v19; // r8
  int v20; // ecx
  __int64 v21; // r8
  int v22; // eax
  unsigned __int64 v23; // rcx
  int v24; // eax
  char *v25; // rdi
  unsigned int v26; // edi
  __int64 v27; // rdx
  int v28; // [rsp+40h] [rbp-81h] BYREF
  HINTERNET hInternet; // [rsp+48h] [rbp-79h] BYREF
  DWORD v30; // [rsp+50h] [rbp-71h] BYREF
  int Buffer; // [rsp+54h] [rbp-6Dh] BYREF
  int v32; // [rsp+58h] [rbp-69h] BYREF
  int v33; // [rsp+5Ch] [rbp-65h] BYREF
  DWORD dwBufferLength; // [rsp+60h] [rbp-61h] BYREF
  void *v35; // [rsp+68h] [rbp-59h] BYREF
  _BYTE v36[8]; // [rsp+70h] [rbp-51h] BYREF
  _QWORD v37[2]; // [rsp+78h] [rbp-49h] BYREF
  __int128 v38; // [rsp+88h] [rbp-39h] BYREF
  __int64 v39; // [rsp+98h] [rbp-29h]
  __int64 v40; // [rsp+A0h] [rbp-21h]
  int v41; // [rsp+A8h] [rbp-19h]
  char v42; // [rsp+B0h] [rbp-11h]
  char v43; // [rsp+B2h] [rbp-Fh]
  __int64 v44; // [rsp+C0h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+C8h] [rbp+7h] BYREF

  v28 = 0;
  v8 = 0;
  v44 = 0;
  Buffer = 256;
  v33 = 0;
  dwBufferLength = 0;
  v30 = 0;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v37[0] = "WinHttpHelper::PingServer";
  v37[1] = &v28;
  *a4 = 0;
  dwFlags = 256;
  if ( a3 )
  {
    dwFlags = 8388864;
    Buffer = 8388864;
  }
  v10 = WinHttpOpenRequest(this[1], L"GET", L"EnrollmentServer/Discovery.svc", L"HTTP/1.1", 0, 0, dwFlags);
  hInternet = v10;
  if ( v10 )
  {
    v45.Ptr = (ULONGLONG)&hInternet;
    LOBYTE(v45.Size) = 1;
    Buffer = 2;
    if ( WinHttpSetOption(v10, 0x3Fu, &Buffer, 4u) )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, HttpSendRequestDataSizeEvent, 0);
      v32 = 0;
      if ( !a3
        || (Buffer = 256, WinHttpSetOption(hInternet, 0x1Fu, &v32, 4u))
        && (*((_DWORD *)this + 8) = 0,
            WinHttpSetStatusCallback(hInternet, SecureFailureCallback, 0x10000u, 0) != (WINHTTP_STATUS_CALLBACK)-1LL) )
      {
        EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v36, "WinHttpSendRequest");
        v15 = this + 4;
        v16 = WinHttpSendRequest(hInternet, 0, 0, 0, 0, 0, (DWORD_PTR)v15);
        if ( !v16 && *v15 == 12038 && (int)CheckCertSAN(hInternet) >= 0 )
        {
          v32 |= 0x1000u;
          if ( !WinHttpSetOption(hInternet, v16 + 31, &v32, 4u) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v28 = LastError;
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v36);
            goto LABEL_57;
          }
          v16 = WinHttpSendRequest(hInternet, 0, 0, 0, 0, 0, (DWORD_PTR)v15);
        }
        EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v36);
        if ( !v16 )
        {
          v18 = GetLastError();
          v19 = (unsigned int)*v15;
          if ( !(_DWORD)v19 )
            v19 = v18;
          if ( (unsigned int)(v19 - 12038) <= 0x13 && (v20 = 524417, _bittest(&v20, v19 - 12038)) )
          {
            v19 = 2149056530LL;
          }
          else if ( (int)v19 > 0 )
          {
            v19 = (unsigned __int16)v19 | 0x80190000;
          }
          v28 = v19;
          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
            McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, SendingRequestFailedEvent, v19);
          goto LABEL_57;
        }
        dwBufferLength = 4;
        if ( WinHttpReceiveResponse(hInternet, 0) )
        {
          if ( WinHttpQueryHeaders(hInternet, 0x20000013u, 0, &v33, &dwBufferLength, 0) )
          {
            v22 = v33;
            *a4 = v33;
            if ( !a5 )
              goto LABEL_57;
            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
            {
              McGenEventWrite_EventWriteTransfer(
                (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
                (const EVENT_DESCRIPTOR *)PingingServerRedirectEvent,
                v21,
                1u,
                &v45);
              v22 = v33;
            }
            *a5 = 0;
            if ( v22 != 302 )
              goto LABEL_57;
            WinHttpQueryHeaders(hInternet, 0x21u, 0, 0, &v30, 0);
            if ( !v30 || (v30 & 1) != 0 )
            {
              v28 = -2147467259;
              goto LABEL_57;
            }
            v8 = SafeHeapAlloc(v30);
            CTContainer_PolicyHeapMem::DestroyMem(0);
            if ( !v8 )
            {
LABEL_47:
              v28 = -2147024882;
LABEL_57:
              v26 = v28;
              WinHttpSetStatusCallback(hInternet, 0, 0x10000u, 0);
              wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hInternet);
              EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v37, v27);
              WinHttpHelper::~WinHttpHelper((WinHttpHelper *)&v38);
              CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v35);
              CTContainer_PolicyHeapMem::DestroyMem(v8);
              return v26;
            }
            if ( WinHttpQueryHeaders(hInternet, 0x21u, 0, v8, &v30, 0) )
            {
              v23 = v30 + 2;
              if ( (unsigned int)v23 < v30 )
              {
                v24 = -2147024362;
                v23 = 0xFFFFFFFFLL;
              }
              else
              {
                v24 = 0;
              }
              dwBufferLength = v23;
              v28 = v24;
              if ( v24 < 0 )
                goto LABEL_57;
              v25 = (char *)SafeHeapAlloc(v23);
              CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v35);
              v35 = v25;
              if ( v25 )
              {
                o_wmemcpy_s_0(
                  (wchar_t *)v25,
                  (unsigned __int64)v30 >> 1,
                  (const wchar_t *)v8,
                  (unsigned __int64)v30 >> 1);
                *(_WORD *)&v25[v30 & 0xFFFFFFFE] = 0;
                v35 = 0;
                *a5 = (unsigned __int16 *)v25;
                if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
                  McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, RedirectServerReceivedEvent, v25);
                goto LABEL_57;
              }
              goto LABEL_47;
            }
          }
        }
      }
    }
    if ( (int)GetLastError() > 0 )
      v14 = (unsigned __int16)GetLastError() | 0x80190000;
    else
      v14 = GetLastError();
    v28 = v14;
    goto LABEL_57;
  }
  if ( (int)GetLastError() > 0 )
    v11 = (unsigned __int16)GetLastError() | 0x80190000;
  else
    v11 = GetLastError();
  v28 = v11;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
  {
    McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, OpenRequestFailedEvent, v11);
    v11 = v28;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hInternet);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v37, v12);
  WinHttpHelper::~WinHttpHelper((WinHttpHelper *)&v38);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v35);
  CTContainer_PolicyHeapMem::DestroyMem(0);
  return v11;
}

```

## disassembly

```asm
0x18001fae0  mov     [rsp-8+arg_8], rbx
0x18001fae5  push    rbp
0x18001fae6  push    rsi
0x18001fae7  push    rdi
0x18001fae8  push    r12
0x18001faea  push    r13
0x18001faec  push    r14
0x18001faee  push    r15
0x18001faf0  lea     rbp, [rsp-1Fh]
0x18001faf5  sub     rsp, 0E0h
0x18001fafc  mov     rax, cs:__security_cookie
0x18001fb03  xor     rax, rsp
0x18001fb06  mov     [rbp+4Fh+var_38], rax
0x18001fb0a  mov     r13, r9
0x18001fb0d  mov     r15d, r8d
0x18001fb10  mov     r14, rcx
0x18001fb13  mov     r12, [rbp+4Fh+arg_20]
0x18001fb17  xor     esi, esi
0x18001fb19  mov     [rsp+110h+var_D0], esi
0x18001fb1d  mov     ebx, esi
0x18001fb1f  mov     [rbp+4Fh+var_50], rbx
0x18001fb23  mov     ecx, 100h
0x18001fb28  mov     [rbp+4Fh+Buffer], ecx
0x18001fb2b  mov     [rbp+4Fh+var_B4], esi
0x18001fb2e  mov     [rbp+4Fh+dwBufferLength], esi
0x18001fb31  mov     [rbp+4Fh+var_C0], esi
0x18001fb34  mov     [rbp+4Fh+var_A8], rsi
0x18001fb38  xorps   xmm0, xmm0
0x18001fb3b  movdqu  [rbp+4Fh+var_88], xmm0
0x18001fb40  mov     [rbp+4Fh+var_78], rsi
0x18001fb44  mov     [rbp+4Fh+var_70], rsi
0x18001fb48  mov     [rbp+4Fh+var_68], esi
0x18001fb4b  mov     [rbp+4Fh+var_60], sil
0x18001fb4f  mov     [rbp+4Fh+var_5E], sil
0x18001fb53  lea     rax, aWinhttphelperP; "WinHttpHelper::PingServer"
0x18001fb5a  mov     [rbp+4Fh+var_98], rax
0x18001fb5e  lea     rax, [rsp+110h+var_D0]
0x18001fb63  mov     [rbp+4Fh+var_90], rax
0x18001fb67  mov     [r9], esi
0x18001fb6a  mov     eax, ecx
0x18001fb6c  test    r8d, r8d
0x18001fb6f  jz      short loc_18001FB79
0x18001fb71  mov     eax, 800100h
0x18001fb76  mov     [rbp+4Fh+Buffer], eax
0x18001fb79  mov     [rsp+110h+dwFlags], eax; dwFlags
0x18001fb7d  mov     [rsp+110h+ppwszAcceptTypes], rsi; ppwszAcceptTypes
0x18001fb82  mov     [rsp+110h+pwszReferrer], rsi; pwszReferrer
0x18001fb87  lea     r9, pwszVersion; "HTTP/1.1"
0x18001fb8e  lea     r8, pwszObjectName; "EnrollmentServer/Discovery.svc"
0x18001fb95  lea     rdx, pwszVerb; "GET"
0x18001fb9c  mov     rcx, [r14+8]; hConnect
0x18001fba0  call    cs:__imp_WinHttpOpenRequest
0x18001fba6  mov     [rbp+4Fh+hInternet], rax
0x18001fbaa  test    rax, rax
0x18001fbad  jnz     loc_18001FC38
0x18001fbb3  call    cs:__imp_GetLastError
0x18001fbb9  test    eax, eax
0x18001fbbb  jg      short loc_18001FBC7
0x18001fbbd  call    cs:__imp_GetLastError
0x18001fbc3  mov     ebx, eax
0x18001fbc5  jmp     short loc_18001FBD6
0x18001fbc7  call    cs:__imp_GetLastError
0x18001fbcd  movzx   ebx, ax
0x18001fbd0  or      ebx, 80190000h
0x18001fbd6  mov     [rsp+110h+var_D0], ebx
0x18001fbda  mov     edi, 4
0x18001fbdf  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x18001fbe6  jz      short loc_18001FC02
0x18001fbe8  mov     r8d, ebx
0x18001fbeb  lea     rdx, OpenRequestFailedEvent
0x18001fbf2  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18001fbf9  call    McTemplateU0q_EventWriteTransfer
0x18001fbfe  mov     ebx, [rsp+110h+var_D0]
0x18001fc02  lea     rcx, [rbp+4Fh+hInternet]
0x18001fc06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001fc0b  nop
0x18001fc0c  lea     rcx, [rbp+4Fh+var_98]; this
0x18001fc10  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001fc15  nop
0x18001fc16  lea     rcx, [rbp+4Fh+var_88]; this
0x18001fc1a  call    ??1WinHttpHelper@@QEAA@XZ; WinHttpHelper::~WinHttpHelper(void)
0x18001fc1f  nop
0x18001fc20  lea     rcx, [rbp+4Fh+var_A8]
0x18001fc24  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001fc29  nop
0x18001fc2a  xor     ecx, ecx; lpMem
0x18001fc2c  call    ?DestroyMem@CTContainer_PolicyHeapMem@@SAHPEAX@Z; CTContainer_PolicyHeapMem::DestroyMem(void *)
0x18001fc31  mov     eax, ebx
0x18001fc33  jmp     loc_18002002C
0x18001fc38  lea     rcx, [rbp+4Fh+hInternet]
0x18001fc3c  mov     [rbp+4Fh+var_48], rcx
0x18001fc40  mov     [rbp+4Fh+var_40], 1
0x18001fc44  mov     [rbp+4Fh+Buffer], 2
0x18001fc4b  mov     edi, 4
0x18001fc50  mov     r9d, edi; dwBufferLength
0x18001fc53  lea     r8, [rbp+4Fh+Buffer]; lpBuffer
0x18001fc57  lea     edx, [rdi+3Bh]; dwOption
0x18001fc5a  mov     rcx, rax; hInternet
0x18001fc5d  call    cs:__imp_WinHttpSetOption
0x18001fc63  test    eax, eax
0x18001fc65  jnz     short loc_18001FC90
0x18001fc67  call    cs:__imp_GetLastError
0x18001fc6d  test    eax, eax
0x18001fc6f  jg      short loc_18001FC79
0x18001fc71  call    cs:__imp_GetLastError
0x18001fc77  jmp     short loc_18001FC87
0x18001fc79  call    cs:__imp_GetLastError
0x18001fc7f  movzx   eax, ax
0x18001fc82  or      eax, 80190000h
0x18001fc87  mov     [rsp+110h+var_D0], eax
0x18001fc8b  jmp     loc_18001FFE0
0x18001fc90  lea     rsi, WP_ENROLLMENT_API_PROVIDER_Context
0x18001fc97  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18001fc9e  jz      short loc_18001FCB2
0x18001fca0  xor     r8d, r8d
0x18001fca3  lea     rdx, HttpSendRequestDataSizeEvent
0x18001fcaa  mov     rcx, rsi
0x18001fcad  call    McTemplateU0q_EventWriteTransfer
0x18001fcb2  mov     [rbp+4Fh+var_B8], 0
0x18001fcb9  test    r15d, r15d
0x18001fcbc  jz      short loc_18001FD0B
0x18001fcbe  mov     [rbp+4Fh+Buffer], 100h
0x18001fcc5  mov     r9d, edi; dwBufferLength
0x18001fcc8  lea     r8, [rbp+4Fh+var_B8]; lpBuffer
0x18001fccc  mov     edx, 1Fh; dwOption
0x18001fcd1  mov     rcx, [rbp+4Fh+hInternet]; hInternet
0x18001fcd5  call    cs:__imp_WinHttpSetOption
0x18001fcdb  test    eax, eax
0x18001fcdd  jz      short loc_18001FC67
0x18001fcdf  mov     dword ptr [r14+20h], 0
0x18001fce7  xor     r9d, r9d; dwReserved
0x18001fcea  mov     r8d, 10000h; dwNotificationFlags
0x18001fcf0  lea     rdx, SecureFailureCallback; lpfnInternetCallback
0x18001fcf7  mov     rcx, [rbp+4Fh+hInternet]; hInternet
0x18001fcfb  call    cs:__imp_WinHttpSetStatusCallback
0x18001fd01  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001fd05  jz      loc_18001FC67
0x18001fd0b  lea     rdx, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18001fd12  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001fd16  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x18001fd1b  nop
0x18001fd1c  add     r14, 20h ; ' '
0x18001fd20  mov     qword ptr [rsp+110h+dwFlags], r14; dwContext
0x18001fd25  mov     dword ptr [rsp+110h+ppwszAcceptTypes], 0; dwTotalLength
0x18001fd2d  mov     dword ptr [rsp+110h+pwszReferrer], 0; dwOptionalLength
0x18001fd35  xor     r9d, r9d; lpOptional
0x18001fd38  xor     r8d, r8d; dwHeadersLength
0x18001fd3b  xor     edx, edx; lpszHeaders
0x18001fd3d  mov     rcx, [rbp+4Fh+hInternet]; hRequest
0x18001fd41  call    cs:__imp_WinHttpSendRequest
0x18001fd47  mov     r15d, eax
0x18001fd4a  test    eax, eax
0x18001fd4c  jnz     loc_18001FDD4
0x18001fd52  cmp     dword ptr [r14], 2F06h
0x18001fd59  jnz     short loc_18001FDD4
0x18001fd5b  mov     rcx, [rbp+4Fh+hInternet]; hInternet
0x18001fd5f  call    CheckCertSAN
0x18001fd64  test    eax, eax
0x18001fd66  js      short loc_18001FDD4
0x18001fd68  bts     [rbp+4Fh+var_B8], 0Ch
0x18001fd6d  mov     r9d, edi; dwBufferLength
0x18001fd70  lea     r8, [rbp+4Fh+var_B8]; lpBuffer
0x18001fd74  lea     edx, [r15+1Fh]; dwOption
0x18001fd78  mov     rcx, [rbp+4Fh+hInternet]; hInternet
0x18001fd7c  call    cs:__imp_WinHttpSetOption
0x18001fd82  test    eax, eax
0x18001fd84  jnz     short loc_18001FDAA
0x18001fd86  call    cs:__imp_GetLastError
0x18001fd8c  test    eax, eax
0x18001fd8e  jle     short loc_18001FD98
0x18001fd90  movzx   eax, ax
0x18001fd93  or      eax, 80070000h
0x18001fd98  mov     [rsp+110h+var_D0], eax
0x18001fd9c  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001fda0  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001fda5  jmp     loc_18001FFE0
0x18001fdaa  mov     qword ptr [rsp+110h+dwFlags], r14; dwContext
0x18001fdaf  mov     dword ptr [rsp+110h+ppwszAcceptTypes], 0; dwTotalLength
0x18001fdb7  mov     dword ptr [rsp+110h+pwszReferrer], 0; dwOptionalLength
0x18001fdbf  xor     r9d, r9d; lpOptional
0x18001fdc2  xor     r8d, r8d; dwHeadersLength
0x18001fdc5  xor     edx, edx; lpszHeaders
0x18001fdc7  mov     rcx, [rbp+4Fh+hInternet]; hRequest
0x18001fdcb  call    cs:__imp_WinHttpSendRequest
0x18001fdd1  mov     r15d, eax
0x18001fdd4  lea     rcx, [rbp+4Fh+var_A0]; this
0x18001fdd8  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001fddd  test    r15d, r15d
0x18001fde0  jnz     short loc_18001FE46
0x18001fde2  call    cs:__imp_GetLastError
0x18001fde8  mov     r8d, [r14]
0x18001fdeb  test    r8d, r8d
0x18001fdee  cmovz   r8d, eax
0x18001fdf2  lea     eax, [r8-2F06h]
0x18001fdf9  cmp     eax, 13h
0x18001fdfc  ja      short loc_18001FE10
0x18001fdfe  mov     ecx, 80081h
0x18001fe03  bt      ecx, eax
0x18001fe06  jnb     short loc_18001FE10
0x18001fe08  mov     r8d, 80180012h
0x18001fe0e  jmp     short loc_18001FE20
0x18001fe10  test    r8d, r8d
0x18001fe13  jle     short loc_18001FE20
0x18001fe15  movzx   r8d, r8w
0x18001fe19  or      r8d, 80190000h
0x18001fe20  mov     [rsp+110h+var_D0], r8d
0x18001fe25  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x18001fe2c  jz      loc_18001FFE0
0x18001fe32  lea     rdx, SendingRequestFailedEvent
0x18001fe39  mov     rcx, rsi
0x18001fe3c  call    McTemplateU0q_EventWriteTransfer
0x18001fe41  jmp     loc_18001FFE0
0x18001fe46  mov     [rbp+4Fh+dwBufferLength], edi
0x18001fe49  xor     edx, edx; lpReserved
0x18001fe4b  mov     rcx, [rbp+4Fh+hInternet]; hRequest
0x18001fe4f  call    cs:__imp_WinHttpReceiveResponse
0x18001fe55  xor     r14d, r14d
0x18001fe58  test    eax, eax
0x18001fe5a  jz      loc_18001FC67
0x18001fe60  mov     [rsp+110h+ppwszAcceptTypes], r14; lpdwIndex
0x18001fe65  lea     rax, [rbp+4Fh+dwBufferLength]
0x18001fe69  mov     [rsp+110h+pwszReferrer], rax; lpdwBufferLength
0x18001fe6e  lea     r9, [rbp+4Fh+var_B4]; lpBuffer
0x18001fe72  xor     r8d, r8d; pwszName
0x18001fe75  mov     edx, 20000013h; dwInfoLevel
0x18001fe7a  mov     rcx, [rbp+4Fh+hInternet]; hRequest
0x18001fe7e  call    cs:__imp_WinHttpQueryHeaders
0x18001fe84  test    eax, eax
0x18001fe86  jz      loc_18001FC67
0x18001fe8c  mov     eax, [rbp+4Fh+var_B4]
0x18001fe8f  mov     [r13+0], eax
0x18001fe93  test    r12, r12
0x18001fe96  jz      loc_18001FFE0
0x18001fe9c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001fea3  jz      short loc_18001FEC4
0x18001fea5  lea     rax, [rbp+4Fh+var_48]
0x18001fea9  mov     [rsp+110h+pwszReferrer], rax
0x18001feae  lea     r9d, [r14+1]
0x18001feb2  lea     rdx, PingingServerRedirectEvent
0x18001feb9  mov     rcx, rsi
0x18001febc  call    McGenEventWrite_EventWriteTransfer
0x18001fec1  mov     eax, [rbp+4Fh+var_B4]
0x18001fec4  mov     [r12], r14
0x18001fec8  cmp     eax, 12Eh
0x18001fecd  jnz     loc_18001FFE0
0x18001fed3  mov     [rsp+110h+ppwszAcceptTypes], r14; lpdwIndex
0x18001fed8  lea     rax, [rbp+4Fh+var_C0]
0x18001fedc  mov     [rsp+110h+pwszReferrer], rax; lpdwBufferLength
0x18001fee1  xor     r9d, r9d; lpBuffer
0x18001fee4  xor     r8d, r8d; pwszName
0x18001fee7  lea     edi, [r9+21h]
0x18001feeb  mov     edx, edi; dwInfoLevel
0x18001feed  mov     rcx, [rbp+4Fh+hInternet]; hRequest
0x18001fef1  call    cs:__imp_WinHttpQueryHeaders
0x18001fef7  mov     eax, [rbp+4Fh+var_C0]
0x18001fefa  test    eax, eax
0x18001fefc  jz      loc_18001FFD8
0x18001ff02  test    al, 1
0x18001ff04  jnz     loc_18001FFD8
0x18001ff0a  mov     ecx, eax; unsigned __int64
0x18001ff0c  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18001ff11  mov     rbx, rax
0x18001ff14  xor     ecx, ecx; lpMem
0x18001ff16  call    ?DestroyMem@CTContainer_PolicyHeapMem@@SAHPEAX@Z; CTContainer_PolicyHeapMem::DestroyMem(void *)
0x18001ff1b  test    rbx, rbx
0x18001ff1e  jnz     short loc_18001FF2D
0x18001ff20  mov     [rsp+110h+var_D0], 8007000Eh
0x18001ff28  jmp     loc_18001FFE0
0x18001ff2d  mov     [rsp+110h+ppwszAcceptTypes], r14; lpdwIndex
0x18001ff32  lea     rax, [rbp+4Fh+var_C0]
0x18001ff36  mov     [rsp+110h+pwszReferrer], rax; lpdwBufferLength
0x18001ff3b  mov     r9, rbx; lpBuffer
0x18001ff3e  xor     r8d, r8d; pwszName
0x18001ff41  mov     edx, edi; dwInfoLevel
0x18001ff43  mov     rcx, [rbp+4Fh+hInternet]; hRequest
0x18001ff47  call    cs:__imp_WinHttpQueryHeaders
0x18001ff4d  test    eax, eax
0x18001ff4f  jz      loc_18001FC67
0x18001ff55  mov     eax, [rbp+4Fh+var_C0]
0x18001ff58  lea     ecx, [rax+2]
0x18001ff5b  cmp     ecx, eax
0x18001ff5d  jb      short loc_18001FF64
0x18001ff5f  mov     eax, r14d
0x18001ff62  jmp     short loc_18001FF6E
0x18001ff64  mov     eax, 80070216h
0x18001ff69  mov     ecx, 0FFFFFFFFh; unsigned __int64
0x18001ff6e  mov     [rbp+4Fh+dwBufferLength], ecx
0x18001ff71  mov     [rsp+110h+var_D0], eax
0x18001ff75  test    eax, eax
0x18001ff77  js      short loc_18001FFE0
0x18001ff79  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18001ff7e  mov     rdi, rax
0x18001ff81  lea     rcx, [rbp+4Fh+var_A8]
0x18001ff85  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001ff8a  mov     [rbp+4Fh+var_A8], rdi
0x18001ff8e  test    rdi, rdi
0x18001ff91  jz      short loc_18001FF20
0x18001ff93  mov     edx, [rbp+4Fh+var_C0]
0x18001ff96  shr     rdx, 1; N1
0x18001ff99  mov     r9, rdx; N
  ... truncated ...
```
