# IpTlsReceiveClientAuthenticationCompletion

- ea: `0x180065840`
- end: `0x180065d0b`
- name: `IpTlsReceiveClientAuthenticationCompletion`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180064a20`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800159c4`
- `0x180040dd0`
- `0x180049730`
- `0x18004c1c8`
- `0x180061694`
- `0x180065840`
- `0x180066128`
- `0x1800667f8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065cdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065cdb`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180065b5b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180065b5b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180065978`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180065978`
- `CRYPT32!CertGetNameStringW` at `0x180065a88`
- `CRYPT32!CertGetNameStringW` at `0x180065b06`
- `CRYPT32!CertGetNameStringW` at `0x180065a88`
- `CRYPT32!CertGetNameStringW` at `0x180065b06`
- `CRYPT32!CertFreeCertificateContext` at `0x180065cc2`
- `CRYPT32!CertFreeCertificateContext` at `0x180065cc2`
- `CRYPT32!CertCreateCertificateContext` at `0x180065a3f`
- `CRYPT32!CertCreateCertificateContext` at `0x180065a3f`
- `HTTPAPI!HttpSendHttpResponse` at `0x180065c54`
- `HTTPAPI!HttpSendHttpResponse` at `0x180065c54`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x1800659c8`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x1800659c8`

## string_xrefs

- `0x180065aca`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180065baf`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
__int64 __fastcall IpTlsReceiveClientAuthenticationCompletion(unsigned int a1, unsigned __int64 a2, _QWORD *a3)
{
  _QWORD *v6; // rdi
  unsigned int *v7; // rsi
  const CERT_CONTEXT *CertificateContext; // r15
  int v9; // ecx
  unsigned int v10; // eax
  char *v11; // rax
  int v12; // ecx
  char *Overlapped; // r14
  ULONG v14; // eax
  __int64 v15; // rdx
  DWORD v16; // r8d
  const BYTE *v17; // rdx
  __int64 v18; // r8
  __int64 i; // rbx
  DWORD v20; // r14d
  DWORD NameStringW; // eax
  DWORD v22; // esi
  __int64 v23; // rbx
  WCHAR *v24; // rcx
  ULONG v25; // esi
  void *v26; // rcx
  DWORD dwType[8]; // [rsp+50h] [rbp-B0h]
  HTTP_RESPONSE HttpResponse; // [rsp+70h] [rbp-90h] BYREF
  int pvTypePara; // [rsp+2F0h] [rbp+1F0h] BYREF
  ULONG BytesSent; // [rsp+300h] [rbp+200h] BYREF
  char v32; // [rsp+308h] [rbp+208h] BYREF

  memset_0(&HttpResponse, 0, sizeof(HttpResponse));
  v6 = a3 + 5;
  BytesSent = 0;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_CLIENT_CERT,
      *(_QWORD *)(*(_QWORD *)(*v6 + 40LL) + 288LL) + 56LL,
      a1);
  IpTlsServerDereferenceHttpQueue(*(_QWORD *)(*v6 + 40LL));
  v7 = (unsigned int *)a3[7];
  if ( !*((_QWORD *)v7 + 2) )
  {
LABEL_7:
    CertificateContext = 0;
    if ( a1 == 234 )
    {
      v9 = a2 + 64;
      if ( (unsigned int)(a2 + 64) >= a2 )
      {
        v10 = v7[1];
        if ( v10 + v9 >= v10 )
        {
          v11 = (char *)MALLOC(v10 + v9);
          Overlapped = v11;
          if ( v11 )
          {
            memset_0(v11, 0, a2 + 64);
            *((_QWORD *)Overlapped + 5) = *v6;
            *((_QWORD *)Overlapped + 7) = Overlapped + 64;
            *((_DWORD *)Overlapped + 8) = 58487;
            *((_QWORD *)Overlapped + 6) = a3[6];
            StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(*v6 + 40LL) + 96LL));
            if ( !(unsigned __int8)RoReferenceEx(*(_QWORD *)(*((_QWORD *)Overlapped + 5) + 40LL) + 80LL) )
            {
              a1 = 6;
              goto LABEL_28;
            }
            v14 = HttpReceiveClientCertificate(
                    *(HANDLE *)(*(_QWORD *)(*((_QWORD *)Overlapped + 5) + 40LL) + 72LL),
                    *((_QWORD *)Overlapped + 6),
                    0,
                    *((PHTTP_SSL_CLIENT_CERT_INFO *)Overlapped + 7),
                    a2 + v7[1],
                    0,
                    (LPOVERLAPPED)Overlapped);
            a1 = v14;
            if ( v14 == 997 )
              goto LABEL_46;
            if ( v14 )
            {
              IpTlsServerDereferenceHttpQueue(*(_QWORD *)(*((_QWORD *)Overlapped + 5) + 40LL));
LABEL_28:
              ++g_IpTlsGlobalStatsAuthErrors;
              CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)(*v6 + 40LL) + 96LL));
              if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
                McTemplateU0zq_EventWriteTransfer(
                  MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
                  EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_CLIENT_CERT,
                  *(_QWORD *)(*(_QWORD *)(*v6 + 40LL) + 288LL) + 56LL,
                  a1);
              FREE(Overlapped);
            }
LABEL_33:
            if ( !a1 )
              goto LABEL_44;
            goto LABEL_43;
          }
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
          {
            McTemplateU0psq_EventWriteTransfer(
              v12,
              (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
              0,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
              50);
            goto LABEL_33;
          }
        }
      }
    }
    else
    {
      memset_0(&HttpResponse, 0, sizeof(HttpResponse));
      *(_DWORD *)&HttpResponse.StatusCode = 1704339;
      HttpResponse.pReason = IpTlsServer403ResponseString;
      if ( (unsigned __int8)RoReferenceEx(*(_QWORD *)(*v6 + 40LL) + 80LL) )
      {
        v25 = HttpSendHttpResponse(
                *(HANDLE *)(*(_QWORD *)(*v6 + 40LL) + 72LL),
                *(_QWORD *)(*v6 + 48LL),
                4u,
                &HttpResponse,
                0,
                &BytesSent,
                0,
                0,
                0,
                0);
        IpTlsServerDereferenceHttpQueue(*(_QWORD *)(*v6 + 40LL));
      }
      else
      {
        v25 = 6;
      }
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      {
        if ( !v25 )
          v25 = 403;
        McTemplateU0zq_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_RESPONSE,
          *(_QWORD *)(*(_QWORD *)(*v6 + 40LL) + 288LL) + 56LL,
          v25);
      }
      ++g_IpTlsGlobalStatsAuthErrors;
    }
    goto LABEL_43;
  }
  EventWrite0(0x10000000, L"IpTlsIsValidClientCertificate. CertFlags = 0x%x", *v7);
  if ( *v7 && *v7 != -2146885613 )
  {
    v7 = (unsigned int *)a3[7];
    goto LABEL_7;
  }
  v15 = a3[7];
  pvTypePara = 33554433;
  dwType[0] = 4;
  dwType[1] = 1;
  v16 = *(_DWORD *)(v15 + 4);
  v17 = *(const BYTE **)(v15 + 8);
  dwType[2] = 6;
  dwType[3] = 8;
  dwType[4] = 7;
  CertificateContext = CertCreateCertificateContext(0x10001u, v17, v16);
  if ( !CertificateContext )
  {
LABEL_25:
    if ( a1 == 997 )
      goto LABEL_44;
    goto LABEL_33;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 5 )
      goto LABEL_24;
    v20 = dwType[i];
    NameStringW = CertGetNameStringW(CertificateContext, v20, 0, &pvTypePara, 0, 0);
    v22 = NameStringW;
    if ( NameStringW > 1 )
      break;
  }
  v23 = *v6;
  *(_QWORD *)(v23 + 112) = MALLOC(2LL * NameStringW);
  v24 = *(WCHAR **)(*v6 + 112LL);
  if ( v24 )
  {
    *(_DWORD *)(*v6 + 120LL) = CertGetNameStringW(CertificateContext, v20, 0, &pvTypePara, v24, v22);
LABEL_24:
    LOBYTE(v18) = 1;
    *(_DWORD *)(*v6 + 80LL) &= ~4u;
    a1 = PostReceiveEntityOnServer(*v6, &v32, v18);
    goto LABEL_25;
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      0,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
      0,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      211);
LABEL_43:
  ShutdownClientContext(*v6);
LABEL_44:
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
LABEL_46:
  v26 = *(void **)(a3[7] + 16LL);
  if ( v26 )
    CloseHandle(v26);
  return FREE(a3);
}

```

## disassembly

```asm
0x180065840  mov     [rsp-8+arg_8], rbx
0x180065845  push    rbp
0x180065846  push    rsi
0x180065847  push    rdi
0x180065848  push    r12
0x18006584a  push    r13
0x18006584c  push    r14
0x18006584e  push    r15
0x180065850  lea     rbp, [rsp-1B0h]
0x180065858  sub     rsp, 2B0h
0x18006585f  mov     r13, r8
0x180065862  mov     r12, rdx
0x180065865  mov     ebx, ecx
0x180065867  mov     r14d, 238h
0x18006586d  mov     r8d, r14d; Size
0x180065870  lea     rcx, [rsp+2E0h+HttpResponse]; void *
0x180065875  xor     edx, edx; Val
0x180065877  call    memset_0
0x18006587c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180065883  lea     rdi, [r13+28h]
0x180065887  mov     [rbp+1E0h+BytesSent], 0
0x180065891  jz      short loc_1800658BB
0x180065893  mov     rax, [rdi]
0x180065896  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_CLIENT_CERT
0x18006589d  mov     r9d, ebx
0x1800658a0  mov     rcx, [rax+28h]
0x1800658a4  mov     r8, [rcx+120h]
0x1800658ab  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800658b2  add     r8, 38h ; '8'
0x1800658b6  call    McTemplateU0zq_EventWriteTransfer
0x1800658bb  mov     rcx, [rdi]
0x1800658be  mov     rcx, [rcx+28h]
0x1800658c2  call    IpTlsServerDereferenceHttpQueue
0x1800658c7  mov     rsi, [r13+38h]
0x1800658cb  cmp     qword ptr [rsi+10h], 0
0x1800658d0  jz      short loc_1800658FF
0x1800658d2  mov     r8d, [rsi]
0x1800658d5  lea     rdx, aIptlsisvalidcl; "IpTlsIsValidClientCertificate. CertFlag"...
0x1800658dc  mov     ecx, 10000000h
0x1800658e1  call    EventWrite0
0x1800658e6  cmp     dword ptr [rsi], 0
0x1800658e9  jz      loc_1800659FB
0x1800658ef  cmp     dword ptr [rsi], 80092013h
0x1800658f5  jz      loc_1800659FB
0x1800658fb  mov     rsi, [r13+38h]
0x1800658ff  xor     r15d, r15d
0x180065902  cmp     ebx, 0EAh
0x180065908  jnz     loc_180065BDA
0x18006590e  lea     ecx, [r12+40h]
0x180065913  mov     eax, ecx
0x180065915  cmp     rax, r12
0x180065918  jb      loc_180065CB2
0x18006591e  mov     eax, [rsi+4]
0x180065921  lea     edx, [rax+rcx]
0x180065924  cmp     edx, eax
0x180065926  jb      loc_180065CB2
0x18006592c  mov     ecx, edx; dwBytes
0x18006592e  call    MALLOC
0x180065933  mov     r14, rax
0x180065936  test    rax, rax
0x180065939  jz      loc_180065BA2
0x18006593f  lea     r8, [r12+40h]; Size
0x180065944  xor     edx, edx; Val
0x180065946  mov     rcx, rax; void *
0x180065949  call    memset_0
0x18006594e  mov     rcx, [rdi]
0x180065951  mov     [r14+28h], rcx
0x180065955  lea     rcx, [r14+40h]
0x180065959  mov     [r14+38h], rcx
0x18006595d  mov     dword ptr [r14+20h], 0E477h
0x180065965  mov     rax, [r13+30h]
0x180065969  mov     [r14+30h], rax
0x18006596d  mov     rax, [rdi]
0x180065970  mov     rcx, [rax+28h]
0x180065974  mov     rcx, [rcx+60h]; pio
0x180065978  call    cs:__imp_StartThreadpoolIo
0x18006597f  nop     dword ptr [rax+rax+00h]
0x180065984  mov     rax, [r14+28h]
0x180065988  mov     rcx, [rax+28h]
0x18006598c  add     rcx, 50h ; 'P'
0x180065990  call    RoReferenceEx
0x180065995  test    al, al
0x180065997  jz      loc_180065B44
0x18006599d  mov     edx, [rsi+4]
0x1800659a0  xor     r8d, r8d; Flags
0x1800659a3  mov     rax, [r14+28h]
0x1800659a7  add     edx, r12d
0x1800659aa  mov     r9, [r14+38h]; SslClientCertInfo
0x1800659ae  mov     [rsp+2E0h+Overlapped], r14; Overlapped
0x1800659b3  mov     [rsp+2E0h+BytesReceived], r15; BytesReceived
0x1800659b8  mov     rcx, [rax+28h]
0x1800659bc  mov     [rsp+2E0h+SslClientCertInfoSize], edx; SslClientCertInfoSize
0x1800659c0  mov     rdx, [r14+30h]; ConnectionId
0x1800659c4  mov     rcx, [rcx+48h]; RequestQueueHandle
0x1800659c8  call    cs:__imp_HttpReceiveClientCertificate
0x1800659cf  nop     dword ptr [rax+rax+00h]
0x1800659d4  mov     ebx, eax
0x1800659d6  cmp     eax, 3E5h
0x1800659db  jz      loc_180065CCE
0x1800659e1  test    eax, eax
0x1800659e3  jz      loc_180065BCD
0x1800659e9  mov     rcx, [r14+28h]
0x1800659ed  mov     rcx, [rcx+28h]
0x1800659f1  call    IpTlsServerDereferenceHttpQueue
0x1800659f6  jmp     loc_180065B49
0x1800659fb  mov     rdx, [r13+38h]
0x1800659ff  mov     esi, 6
0x180065a04  mov     [rbp+1E0h+pvTypePara], 2000001h
0x180065a0e  mov     ecx, 10001h; dwCertEncodingType
0x180065a13  mov     [rsp+2E0h+dwType], 4
0x180065a1b  mov     [rsp+2E0h+var_28C], 1
0x180065a23  mov     r8d, [rdx+4]; cbCertEncoded
0x180065a27  mov     rdx, [rdx+8]; pbCertEncoded
0x180065a2b  mov     [rsp+2E0h+var_288], esi
0x180065a2f  mov     [rsp+2E0h+var_284], 8
0x180065a37  mov     [rsp+2E0h+var_280], 7
0x180065a3f  call    cs:__imp_CertCreateCertificateContext
0x180065a46  nop     dword ptr [rax+rax+00h]
0x180065a4b  mov     r15, rax
0x180065a4e  test    rax, rax
0x180065a51  jz      loc_180065B33
0x180065a57  xor     ebx, ebx
0x180065a59  cmp     ebx, 5
0x180065a5c  jnb     loc_180065B18
0x180065a62  mov     r14d, [rsp+rbx*4+2E0h+dwType]
0x180065a67  lea     r9, [rbp+1E0h+pvTypePara]; pvTypePara
0x180065a6e  mov     edx, r14d; dwType
0x180065a71  mov     dword ptr [rsp+2E0h+BytesReceived], 0; cchNameString
0x180065a79  xor     r8d, r8d; dwFlags
0x180065a7c  mov     qword ptr [rsp+2E0h+SslClientCertInfoSize], 0; pszNameString
0x180065a85  mov     rcx, r15; pCertContext
0x180065a88  call    cs:__imp_CertGetNameStringW
0x180065a8f  nop     dword ptr [rax+rax+00h]
0x180065a94  mov     esi, eax
0x180065a96  cmp     eax, 1
0x180065a99  ja      short loc_180065A9F
0x180065a9b  inc     ebx
0x180065a9d  jmp     short loc_180065A59
0x180065a9f  mov     rbx, [rdi]
0x180065aa2  mov     rcx, rsi
0x180065aa5  add     rcx, rcx; dwBytes
0x180065aa8  call    MALLOC
0x180065aad  mov     [rbx+70h], rax
0x180065ab1  mov     rax, [rdi]
0x180065ab4  mov     rcx, [rax+70h]
0x180065ab8  test    rcx, rcx
0x180065abb  jnz     short loc_180065AED
0x180065abd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180065ac4  jz      loc_180065CB2
0x180065aca  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180065ad1  mov     [rsp+2E0h+SslClientCertInfoSize], 9D3h
0x180065ad9  xor     r8d, r8d
0x180065adc  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180065ae3  call    McTemplateU0psq_EventWriteTransfer
0x180065ae8  jmp     loc_180065CB2
0x180065aed  mov     dword ptr [rsp+2E0h+BytesReceived], esi; cchNameString
0x180065af1  lea     r9, [rbp+1E0h+pvTypePara]; pvTypePara
0x180065af8  mov     qword ptr [rsp+2E0h+SslClientCertInfoSize], rcx; pszNameString
0x180065afd  xor     r8d, r8d; dwFlags
0x180065b00  mov     rcx, r15; pCertContext
0x180065b03  mov     edx, r14d; dwType
0x180065b06  call    cs:__imp_CertGetNameStringW
0x180065b0d  nop     dword ptr [rax+rax+00h]
0x180065b12  mov     rcx, [rdi]
0x180065b15  mov     [rcx+78h], eax
0x180065b18  mov     rax, [rdi]
0x180065b1b  lea     rdx, [rbp+1E0h+arg_18]
0x180065b22  mov     r8b, 1
0x180065b25  and     dword ptr [rax+50h], 0FFFFFFFBh
0x180065b29  mov     rcx, [rdi]
0x180065b2c  call    PostReceiveEntityOnServer
0x180065b31  mov     ebx, eax
0x180065b33  cmp     ebx, 3E5h
0x180065b39  jz      loc_180065CBA
0x180065b3f  jmp     loc_180065BCD
0x180065b44  mov     ebx, 6
0x180065b49  inc     cs:g_IpTlsGlobalStatsAuthErrors
0x180065b50  mov     rax, [rdi]
0x180065b53  mov     rcx, [rax+28h]
0x180065b57  mov     rcx, [rcx+60h]; pio
0x180065b5b  call    cs:__imp_CancelThreadpoolIo
0x180065b62  nop     dword ptr [rax+rax+00h]
0x180065b67  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180065b6e  jz      short loc_180065B98
0x180065b70  mov     rax, [rdi]
0x180065b73  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_CLIENT_CERT
0x180065b7a  mov     r9d, ebx
0x180065b7d  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180065b84  mov     r8, [rax+28h]
0x180065b88  mov     r8, [r8+120h]
0x180065b8f  add     r8, 38h ; '8'
0x180065b93  call    McTemplateU0zq_EventWriteTransfer
0x180065b98  mov     rcx, r14
0x180065b9b  call    FREE
0x180065ba0  jmp     short loc_180065BCD
0x180065ba2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180065ba9  jz      loc_180065CB2
0x180065baf  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180065bb6  mov     [rsp+2E0h+SslClientCertInfoSize], 0A32h
0x180065bbe  xor     r8d, r8d
0x180065bc1  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180065bc8  call    McTemplateU0psq_EventWriteTransfer
0x180065bcd  test    ebx, ebx
0x180065bcf  jz      loc_180065CBA
0x180065bd5  jmp     loc_180065CB2
0x180065bda  mov     r8, r14; Size
0x180065bdd  lea     rcx, [rsp+2E0h+HttpResponse]; void *
0x180065be2  xor     edx, edx; Val
0x180065be4  call    memset_0
0x180065be9  lea     rax, IpTlsServer403ResponseString; "Client Certficate required"
0x180065bf0  mov     dword ptr [rsp+2E0h+HttpResponse.StatusCode], 1A0193h
0x180065bf8  mov     [rbp+1E0h+HttpResponse.pReason], rax
0x180065bfc  mov     ebx, 193h
0x180065c01  mov     rax, [rdi]
0x180065c04  mov     rcx, [rax+28h]
0x180065c08  add     rcx, 50h ; 'P'
0x180065c0c  call    RoReferenceEx
0x180065c11  test    al, al
0x180065c13  jz      short loc_180065C70
0x180065c15  mov     rdx, [rdi]
0x180065c18  lea     rax, [rbp+1E0h+BytesSent]
0x180065c1f  mov     [rsp+2E0h+LogData], r15; LogData
0x180065c24  lea     r9, [rsp+2E0h+HttpResponse]; HttpResponse
0x180065c29  mov     [rsp+2E0h+var_2A0], r15; Overlapped
0x180065c2e  mov     r8d, 4; Flags
0x180065c34  mov     [rsp+2E0h+Reserved2], r15d; Reserved2
0x180065c39  mov     rcx, [rdx+28h]
0x180065c3d  mov     rdx, [rdx+30h]; RequestId
0x180065c41  mov     [rsp+2E0h+Overlapped], r15; Reserved1
0x180065c46  mov     [rsp+2E0h+BytesReceived], rax; BytesSent
0x180065c4b  mov     rcx, [rcx+48h]; RequestQueueHandle
0x180065c4f  mov     qword ptr [rsp+2E0h+SslClientCertInfoSize], r15; CachePolicy
0x180065c54  call    cs:__imp_HttpSendHttpResponse
0x180065c5b  nop     dword ptr [rax+rax+00h]
0x180065c60  mov     rcx, [rdi]
0x180065c63  mov     esi, eax
0x180065c65  mov     rcx, [rcx+28h]
0x180065c69  call    IpTlsServerDereferenceHttpQueue
0x180065c6e  jmp     short loc_180065C75
0x180065c70  mov     esi, 6
0x180065c75  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180065c7c  jz      short loc_180065CAB
0x180065c7e  mov     rax, [rdi]
0x180065c81  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180065c88  test    esi, esi
0x180065c8a  cmovz   esi, ebx
0x180065c8d  mov     rdx, [rax+28h]
0x180065c91  mov     r9d, esi
0x180065c94  mov     r8, [rdx+120h]
0x180065c9b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_RESPONSE
0x180065ca2  add     r8, 38h ; '8'
0x180065ca6  call    McTemplateU0zq_EventWriteTransfer
0x180065cab  inc     cs:g_IpTlsGlobalStatsAuthErrors
0x180065cb2  mov     rcx, [rdi]
0x180065cb5  call    ShutdownClientContext
0x180065cba  test    r15, r15
0x180065cbd  jz      short loc_180065CCE
0x180065cbf  mov     rcx, r15; pCertContext
0x180065cc2  call    cs:__imp_CertFreeCertificateContext
0x180065cc9  nop     dword ptr [rax+rax+00h]
0x180065cce  mov     rax, [r13+38h]
0x180065cd2  mov     rcx, [rax+10h]; hObject
0x180065cd6  test    rcx, rcx
0x180065cd9  jz      short loc_180065CE7
0x180065cdb  call    cs:__imp_CloseHandle
0x180065ce2  nop     dword ptr [rax+rax+00h]
0x180065ce7  mov     rcx, r13
0x180065cea  call    FREE
0x180065cef  mov     rbx, [rsp+2E0h+arg_8]
0x180065cf7  add     rsp, 2B0h
0x180065cfe  pop     r15
0x180065d00  pop     r14
0x180065d02  pop     r13
0x180065d04  pop     r12
0x180065d06  pop     rdi
0x180065d07  pop     rsi
0x180065d08  pop     rbp
0x180065d09  retn
```
