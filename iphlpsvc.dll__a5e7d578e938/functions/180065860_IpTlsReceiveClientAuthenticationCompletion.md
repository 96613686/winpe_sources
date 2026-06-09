# IpTlsReceiveClientAuthenticationCompletion

- ea: `0x180065860`
- end: `0x180065d2b`
- name: `IpTlsReceiveClientAuthenticationCompletion`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180064a40`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800159d4`
- `0x180040d90`
- `0x1800496f0`
- `0x18004c188`
- `0x1800616b4`
- `0x180065860`
- `0x180066148`
- `0x180066818`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065cfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065cfb`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180065b7b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180065b7b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180065998`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180065998`
- `CRYPT32!CertGetNameStringW` at `0x180065aa8`
- `CRYPT32!CertGetNameStringW` at `0x180065b26`
- `CRYPT32!CertGetNameStringW` at `0x180065aa8`
- `CRYPT32!CertGetNameStringW` at `0x180065b26`
- `CRYPT32!CertFreeCertificateContext` at `0x180065ce2`
- `CRYPT32!CertFreeCertificateContext` at `0x180065ce2`
- `CRYPT32!CertCreateCertificateContext` at `0x180065a5f`
- `CRYPT32!CertCreateCertificateContext` at `0x180065a5f`
- `HTTPAPI!HttpSendHttpResponse` at `0x180065c74`
- `HTTPAPI!HttpSendHttpResponse` at `0x180065c74`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x1800659e8`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x1800659e8`

## string_xrefs

- `0x180065aea`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180065bcf`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
0x180065860  mov     [rsp-8+arg_8], rbx
0x180065865  push    rbp
0x180065866  push    rsi
0x180065867  push    rdi
0x180065868  push    r12
0x18006586a  push    r13
0x18006586c  push    r14
0x18006586e  push    r15
0x180065870  lea     rbp, [rsp-1B0h]
0x180065878  sub     rsp, 2B0h
0x18006587f  mov     r13, r8
0x180065882  mov     r12, rdx
0x180065885  mov     ebx, ecx
0x180065887  mov     r14d, 238h
0x18006588d  mov     r8d, r14d; Size
0x180065890  lea     rcx, [rsp+2E0h+HttpResponse]; void *
0x180065895  xor     edx, edx; Val
0x180065897  call    memset_0
0x18006589c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800658a3  lea     rdi, [r13+28h]
0x1800658a7  mov     [rbp+1E0h+BytesSent], 0
0x1800658b1  jz      short loc_1800658DB
0x1800658b3  mov     rax, [rdi]
0x1800658b6  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_CLIENT_CERT
0x1800658bd  mov     r9d, ebx
0x1800658c0  mov     rcx, [rax+28h]
0x1800658c4  mov     r8, [rcx+120h]
0x1800658cb  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800658d2  add     r8, 38h ; '8'
0x1800658d6  call    McTemplateU0zq_EventWriteTransfer
0x1800658db  mov     rcx, [rdi]
0x1800658de  mov     rcx, [rcx+28h]
0x1800658e2  call    IpTlsServerDereferenceHttpQueue
0x1800658e7  mov     rsi, [r13+38h]
0x1800658eb  cmp     qword ptr [rsi+10h], 0
0x1800658f0  jz      short loc_18006591F
0x1800658f2  mov     r8d, [rsi]
0x1800658f5  lea     rdx, aIptlsisvalidcl; "IpTlsIsValidClientCertificate. CertFlag"...
0x1800658fc  mov     ecx, 10000000h
0x180065901  call    EventWrite0
0x180065906  cmp     dword ptr [rsi], 0
0x180065909  jz      loc_180065A1B
0x18006590f  cmp     dword ptr [rsi], 80092013h
0x180065915  jz      loc_180065A1B
0x18006591b  mov     rsi, [r13+38h]
0x18006591f  xor     r15d, r15d
0x180065922  cmp     ebx, 0EAh
0x180065928  jnz     loc_180065BFA
0x18006592e  lea     ecx, [r12+40h]
0x180065933  mov     eax, ecx
0x180065935  cmp     rax, r12
0x180065938  jb      loc_180065CD2
0x18006593e  mov     eax, [rsi+4]
0x180065941  lea     edx, [rax+rcx]
0x180065944  cmp     edx, eax
0x180065946  jb      loc_180065CD2
0x18006594c  mov     ecx, edx; dwBytes
0x18006594e  call    MALLOC
0x180065953  mov     r14, rax
0x180065956  test    rax, rax
0x180065959  jz      loc_180065BC2
0x18006595f  lea     r8, [r12+40h]; Size
0x180065964  xor     edx, edx; Val
0x180065966  mov     rcx, rax; void *
0x180065969  call    memset_0
0x18006596e  mov     rcx, [rdi]
0x180065971  mov     [r14+28h], rcx
0x180065975  lea     rcx, [r14+40h]
0x180065979  mov     [r14+38h], rcx
0x18006597d  mov     dword ptr [r14+20h], 0E477h
0x180065985  mov     rax, [r13+30h]
0x180065989  mov     [r14+30h], rax
0x18006598d  mov     rax, [rdi]
0x180065990  mov     rcx, [rax+28h]
0x180065994  mov     rcx, [rcx+60h]; pio
0x180065998  call    cs:__imp_StartThreadpoolIo
0x18006599f  nop     dword ptr [rax+rax+00h]
0x1800659a4  mov     rax, [r14+28h]
0x1800659a8  mov     rcx, [rax+28h]
0x1800659ac  add     rcx, 50h ; 'P'
0x1800659b0  call    RoReferenceEx
0x1800659b5  test    al, al
0x1800659b7  jz      loc_180065B64
0x1800659bd  mov     edx, [rsi+4]
0x1800659c0  xor     r8d, r8d; Flags
0x1800659c3  mov     rax, [r14+28h]
0x1800659c7  add     edx, r12d
0x1800659ca  mov     r9, [r14+38h]; SslClientCertInfo
0x1800659ce  mov     [rsp+2E0h+Overlapped], r14; Overlapped
0x1800659d3  mov     [rsp+2E0h+BytesReceived], r15; BytesReceived
0x1800659d8  mov     rcx, [rax+28h]
0x1800659dc  mov     [rsp+2E0h+SslClientCertInfoSize], edx; SslClientCertInfoSize
0x1800659e0  mov     rdx, [r14+30h]; ConnectionId
0x1800659e4  mov     rcx, [rcx+48h]; RequestQueueHandle
0x1800659e8  call    cs:__imp_HttpReceiveClientCertificate
0x1800659ef  nop     dword ptr [rax+rax+00h]
0x1800659f4  mov     ebx, eax
0x1800659f6  cmp     eax, 3E5h
0x1800659fb  jz      loc_180065CEE
0x180065a01  test    eax, eax
0x180065a03  jz      loc_180065BED
0x180065a09  mov     rcx, [r14+28h]
0x180065a0d  mov     rcx, [rcx+28h]
0x180065a11  call    IpTlsServerDereferenceHttpQueue
0x180065a16  jmp     loc_180065B69
0x180065a1b  mov     rdx, [r13+38h]
0x180065a1f  mov     esi, 6
0x180065a24  mov     [rbp+1E0h+pvTypePara], 2000001h
0x180065a2e  mov     ecx, 10001h; dwCertEncodingType
0x180065a33  mov     [rsp+2E0h+dwType], 4
0x180065a3b  mov     [rsp+2E0h+var_28C], 1
0x180065a43  mov     r8d, [rdx+4]; cbCertEncoded
0x180065a47  mov     rdx, [rdx+8]; pbCertEncoded
0x180065a4b  mov     [rsp+2E0h+var_288], esi
0x180065a4f  mov     [rsp+2E0h+var_284], 8
0x180065a57  mov     [rsp+2E0h+var_280], 7
0x180065a5f  call    cs:__imp_CertCreateCertificateContext
0x180065a66  nop     dword ptr [rax+rax+00h]
0x180065a6b  mov     r15, rax
0x180065a6e  test    rax, rax
0x180065a71  jz      loc_180065B53
0x180065a77  xor     ebx, ebx
0x180065a79  cmp     ebx, 5
0x180065a7c  jnb     loc_180065B38
0x180065a82  mov     r14d, [rsp+rbx*4+2E0h+dwType]
0x180065a87  lea     r9, [rbp+1E0h+pvTypePara]; pvTypePara
0x180065a8e  mov     edx, r14d; dwType
0x180065a91  mov     dword ptr [rsp+2E0h+BytesReceived], 0; cchNameString
0x180065a99  xor     r8d, r8d; dwFlags
0x180065a9c  mov     qword ptr [rsp+2E0h+SslClientCertInfoSize], 0; pszNameString
0x180065aa5  mov     rcx, r15; pCertContext
0x180065aa8  call    cs:__imp_CertGetNameStringW
0x180065aaf  nop     dword ptr [rax+rax+00h]
0x180065ab4  mov     esi, eax
0x180065ab6  cmp     eax, 1
0x180065ab9  ja      short loc_180065ABF
0x180065abb  inc     ebx
0x180065abd  jmp     short loc_180065A79
0x180065abf  mov     rbx, [rdi]
0x180065ac2  mov     rcx, rsi
0x180065ac5  add     rcx, rcx; dwBytes
0x180065ac8  call    MALLOC
0x180065acd  mov     [rbx+70h], rax
0x180065ad1  mov     rax, [rdi]
0x180065ad4  mov     rcx, [rax+70h]
0x180065ad8  test    rcx, rcx
0x180065adb  jnz     short loc_180065B0D
0x180065add  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180065ae4  jz      loc_180065CD2
0x180065aea  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180065af1  mov     [rsp+2E0h+SslClientCertInfoSize], 9D3h
0x180065af9  xor     r8d, r8d
0x180065afc  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180065b03  call    McTemplateU0psq_EventWriteTransfer
0x180065b08  jmp     loc_180065CD2
0x180065b0d  mov     dword ptr [rsp+2E0h+BytesReceived], esi; cchNameString
0x180065b11  lea     r9, [rbp+1E0h+pvTypePara]; pvTypePara
0x180065b18  mov     qword ptr [rsp+2E0h+SslClientCertInfoSize], rcx; pszNameString
0x180065b1d  xor     r8d, r8d; dwFlags
0x180065b20  mov     rcx, r15; pCertContext
0x180065b23  mov     edx, r14d; dwType
0x180065b26  call    cs:__imp_CertGetNameStringW
0x180065b2d  nop     dword ptr [rax+rax+00h]
0x180065b32  mov     rcx, [rdi]
0x180065b35  mov     [rcx+78h], eax
0x180065b38  mov     rax, [rdi]
0x180065b3b  lea     rdx, [rbp+1E0h+arg_18]
0x180065b42  mov     r8b, 1
0x180065b45  and     dword ptr [rax+50h], 0FFFFFFFBh
0x180065b49  mov     rcx, [rdi]
0x180065b4c  call    PostReceiveEntityOnServer
0x180065b51  mov     ebx, eax
0x180065b53  cmp     ebx, 3E5h
0x180065b59  jz      loc_180065CDA
0x180065b5f  jmp     loc_180065BED
0x180065b64  mov     ebx, 6
0x180065b69  inc     cs:g_IpTlsGlobalStatsAuthErrors
0x180065b70  mov     rax, [rdi]
0x180065b73  mov     rcx, [rax+28h]
0x180065b77  mov     rcx, [rcx+60h]; pio
0x180065b7b  call    cs:__imp_CancelThreadpoolIo
0x180065b82  nop     dword ptr [rax+rax+00h]
0x180065b87  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180065b8e  jz      short loc_180065BB8
0x180065b90  mov     rax, [rdi]
0x180065b93  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_RECEIVE_CLIENT_CERT
0x180065b9a  mov     r9d, ebx
0x180065b9d  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180065ba4  mov     r8, [rax+28h]
0x180065ba8  mov     r8, [r8+120h]
0x180065baf  add     r8, 38h ; '8'
0x180065bb3  call    McTemplateU0zq_EventWriteTransfer
0x180065bb8  mov     rcx, r14
0x180065bbb  call    FREE
0x180065bc0  jmp     short loc_180065BED
0x180065bc2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180065bc9  jz      loc_180065CD2
0x180065bcf  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180065bd6  mov     [rsp+2E0h+SslClientCertInfoSize], 0A32h
0x180065bde  xor     r8d, r8d
0x180065be1  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180065be8  call    McTemplateU0psq_EventWriteTransfer
0x180065bed  test    ebx, ebx
0x180065bef  jz      loc_180065CDA
0x180065bf5  jmp     loc_180065CD2
0x180065bfa  mov     r8, r14; Size
0x180065bfd  lea     rcx, [rsp+2E0h+HttpResponse]; void *
0x180065c02  xor     edx, edx; Val
0x180065c04  call    memset_0
0x180065c09  lea     rax, IpTlsServer403ResponseString; "Client Certficate required"
0x180065c10  mov     dword ptr [rsp+2E0h+HttpResponse.StatusCode], 1A0193h
0x180065c18  mov     [rbp+1E0h+HttpResponse.pReason], rax
0x180065c1c  mov     ebx, 193h
0x180065c21  mov     rax, [rdi]
0x180065c24  mov     rcx, [rax+28h]
0x180065c28  add     rcx, 50h ; 'P'
0x180065c2c  call    RoReferenceEx
0x180065c31  test    al, al
0x180065c33  jz      short loc_180065C90
0x180065c35  mov     rdx, [rdi]
0x180065c38  lea     rax, [rbp+1E0h+BytesSent]
0x180065c3f  mov     [rsp+2E0h+LogData], r15; LogData
0x180065c44  lea     r9, [rsp+2E0h+HttpResponse]; HttpResponse
0x180065c49  mov     [rsp+2E0h+var_2A0], r15; Overlapped
0x180065c4e  mov     r8d, 4; Flags
0x180065c54  mov     [rsp+2E0h+Reserved2], r15d; Reserved2
0x180065c59  mov     rcx, [rdx+28h]
0x180065c5d  mov     rdx, [rdx+30h]; RequestId
0x180065c61  mov     [rsp+2E0h+Overlapped], r15; Reserved1
0x180065c66  mov     [rsp+2E0h+BytesReceived], rax; BytesSent
0x180065c6b  mov     rcx, [rcx+48h]; RequestQueueHandle
0x180065c6f  mov     qword ptr [rsp+2E0h+SslClientCertInfoSize], r15; CachePolicy
0x180065c74  call    cs:__imp_HttpSendHttpResponse
0x180065c7b  nop     dword ptr [rax+rax+00h]
0x180065c80  mov     rcx, [rdi]
0x180065c83  mov     esi, eax
0x180065c85  mov     rcx, [rcx+28h]
0x180065c89  call    IpTlsServerDereferenceHttpQueue
0x180065c8e  jmp     short loc_180065C95
0x180065c90  mov     esi, 6
0x180065c95  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180065c9c  jz      short loc_180065CCB
0x180065c9e  mov     rax, [rdi]
0x180065ca1  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180065ca8  test    esi, esi
0x180065caa  cmovz   esi, ebx
0x180065cad  mov     rdx, [rax+28h]
0x180065cb1  mov     r9d, esi
0x180065cb4  mov     r8, [rdx+120h]
0x180065cbb  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_SEND_RESPONSE
0x180065cc2  add     r8, 38h ; '8'
0x180065cc6  call    McTemplateU0zq_EventWriteTransfer
0x180065ccb  inc     cs:g_IpTlsGlobalStatsAuthErrors
0x180065cd2  mov     rcx, [rdi]
0x180065cd5  call    ShutdownClientContext
0x180065cda  test    r15, r15
0x180065cdd  jz      short loc_180065CEE
0x180065cdf  mov     rcx, r15; pCertContext
0x180065ce2  call    cs:__imp_CertFreeCertificateContext
0x180065ce9  nop     dword ptr [rax+rax+00h]
0x180065cee  mov     rax, [r13+38h]
0x180065cf2  mov     rcx, [rax+10h]; hObject
0x180065cf6  test    rcx, rcx
0x180065cf9  jz      short loc_180065D07
0x180065cfb  call    cs:__imp_CloseHandle
0x180065d02  nop     dword ptr [rax+rax+00h]
0x180065d07  mov     rcx, r13
0x180065d0a  call    FREE
0x180065d0f  mov     rbx, [rsp+2E0h+arg_8]
0x180065d17  add     rsp, 2B0h
0x180065d1e  pop     r15
0x180065d20  pop     r14
0x180065d22  pop     r13
0x180065d24  pop     r12
0x180065d26  pop     rdi
0x180065d27  pop     rsi
0x180065d28  pop     rbp
0x180065d29  retn
```
