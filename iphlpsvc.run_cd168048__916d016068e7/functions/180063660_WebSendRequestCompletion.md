# WebSendRequestCompletion

- ea: `0x180063660`
- end: `0x180063983`
- name: `WebSendRequestCompletion`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062084`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180013570`
- `0x180031688`
- `0x180031a98`
- `0x180031afc`
- `0x180031e28`
- `0x180040dd0`
- `0x18004930c`
- `0x180061694`
- `0x180063280`
- `0x180063660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800638f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800638f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063847`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063867`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063867`
- `CRYPT32!CertFreeCertificateContext` at `0x1800638bf`
- `CRYPT32!CertFreeCertificateContext` at `0x1800638bf`
- `webio!__imp_WebReceiveHttpResponse` at `0x18006376b`
- `webio!__imp_WebReceiveHttpResponse` at `0x18006376b`

## string_xrefs

- `0x1800636f0`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x18006371e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180063922`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180063950`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x18006368f`: `%s:WebSendHttpRequest completed:%d`
- `0x1800637d1`: `%s:WebSendRequestCompletion: Scheduling a reconnectInterface State: %d Status: %d`

## pseudocode

```c
__int64 __fastcall WebSendRequestCompletion(__int64 *a1, unsigned int a2)
{
  __int64 v2; // r8
  int v5; // ecx
  unsigned int v6; // eax
  char v7; // bl
  __int64 *v8; // rbx
  __int64 *v9; // rcx
  __int64 **v10; // rax
  int v11; // ecx
  __int64 v13; // [rsp+20h] [rbp-18h]
  int v14; // [rsp+48h] [rbp+10h] BYREF

  v2 = a1[16];
  v14 = 0;
  EventWrite0(0x10000000, L"%s:WebSendHttpRequest completed:%d", v2 + 56, a2);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SEND_HTTP_REQUEST,
      a1[16] + 56,
      a2);
  if ( !a2 && *((_DWORD *)a1 + 30) == 1 )
  {
    if ( (unsigned __int8)IpTlsClientReferenceIO(a1) )
    {
      EventWrite0(
        0x20000000,
        L"(%s: Reference IPTLS client interface %S:%d",
        a1[16] + 56,
        "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
        1729);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v5,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_REFERENCE,
          (_DWORD)a1,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
          193);
      _InterlockedIncrement((volatile signed __int32 *)a1 + 31);
      EventWrite0(0x10000000, L"%s:WebReceiveHttpResponse", a1[16] + 56);
      v6 = WebReceiveHttpResponse(*a1, 0, &v14, WebReceiveResponseCompletion, a1);
      if ( v6 != 997 )
        WebReceiveResponseCompletion((__int64)a1, v6, 0);
    }
    else if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SEND_HTTP_REQUEST,
        a1[16] + 56,
        21);
    }
    goto LABEL_28;
  }
  EventWrite0(
    0x10000000,
    L"%s:WebSendRequestCompletion: Scheduling a reconnectInterface State: %d Status: %d",
    a1[16] + 56,
    *((unsigned int *)a1 + 30),
    a2);
  if ( a2 )
    *(_DWORD *)(a1[16] + 1196) = a2;
  if ( *((_DWORD *)a1 + 30) != 1 )
    goto LABEL_27;
  if ( a2 + 2146893043 <= 1 || a2 == -2146762480 )
  {
    v8 = *(__int64 **)(a1[16] + 1136);
    IpTlsAcquireLock(g_IpTlsInterfaceListLock);
    CertFreeCertificateContext((PCCERT_CONTEXT)v8[2]);
    v9 = (__int64 *)*v8;
    if ( *(__int64 **)(*v8 + 8) != v8 || (v10 = (__int64 **)v8[1], *v10 != v8) )
      __fastfail(3u);
    *v10 = v9;
    v9[1] = (__int64)v10;
    FREE(v8);
    ReleaseMutex(g_IpTlsInterfaceListLock);
    goto LABEL_21;
  }
  if ( a2 != -2146893007 && a2 != 1225 && a2 != 10054
    || (EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 22)),
        v7 = *((_BYTE *)a1 + 224),
        *((_BYTE *)a1 + 224) = v7 == 0,
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 22)),
        !v7) )
  {
LABEL_27:
    IpTlsClientScheduleReconnect((__int64)a1);
    goto LABEL_28;
  }
LABEL_21:
  if ( (unsigned __int8)IpTlsClientReferenceIO(a1) )
    IpTlsClientScheduleWorkItem((__int64)a1, 1, (__int64)IpTlsClientRestartClientWorker);
LABEL_28:
  IpTlsClientDereferenceIO(a1);
  LODWORD(v13) = 1831;
  EventWrite0(
    0x20000000,
    L"(%s: Dereference IPTLS client interface %S:%d",
    a1[16] + 56,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
    v13);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v11,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE,
      (_DWORD)a1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
      39);
  return DereferenceInterfaceEx(a1);
}

```

## disassembly

```asm
0x180063660  mov     [rsp+arg_0], rbx
0x180063665  mov     [rsp+arg_10], rsi
0x18006366a  push    rdi
0x18006366b  sub     rsp, 30h
0x18006366f  mov     r8, [rcx+80h]
0x180063676  mov     ebx, edx
0x180063678  mov     rsi, rcx
0x18006367b  mov     [rsp+38h+arg_8], 0
0x180063683  mov     r9d, edx
0x180063686  mov     edi, 10000000h
0x18006368b  add     r8, 38h ; '8'
0x18006368f  lea     rdx, aSWebsendhttpre; "%s:WebSendHttpRequest completed:%d"
0x180063696  mov     ecx, edi
0x180063698  call    EventWrite0
0x18006369d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800636a4  jz      short loc_1800636C7
0x1800636a6  mov     r8, [rsi+80h]
0x1800636ad  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SEND_HTTP_REQUEST
0x1800636b4  add     r8, 38h ; '8'
0x1800636b8  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800636bf  mov     r9d, ebx
0x1800636c2  call    McTemplateU0zq_EventWriteTransfer
0x1800636c7  test    ebx, ebx
0x1800636c9  jnz     loc_1800637CA
0x1800636cf  cmp     dword ptr [rsi+78h], 1
0x1800636d3  jnz     loc_1800637CA
0x1800636d9  mov     rcx, rsi
0x1800636dc  call    IpTlsClientReferenceIO
0x1800636e1  test    al, al
0x1800636e3  jz      loc_180063794
0x1800636e9  mov     r8, [rsi+80h]
0x1800636f0  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800636f7  mov     ebx, 6C1h
0x1800636fc  lea     rdx, aSReferenceIptl; "(%s: Reference IPTLS client interface %"...
0x180063703  add     r8, 38h ; '8'
0x180063707  mov     dword ptr [rsp+38h+var_18], ebx
0x18006370b  mov     ecx, 20000000h
0x180063710  call    EventWrite0
0x180063715  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006371c  jz      short loc_180063738
0x18006371e  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063725  mov     dword ptr [rsp+38h+var_18], ebx
0x180063729  mov     r8, rsi
0x18006372c  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_REFERENCE
0x180063733  call    McTemplateU0psq_EventWriteTransfer
0x180063738  lock inc dword ptr [rsi+7Ch]
0x18006373c  mov     r8, [rsi+80h]
0x180063743  lea     rdx, aSWebreceivehtt_0; "%s:WebReceiveHttpResponse"
0x18006374a  add     r8, 38h ; '8'
0x18006374e  mov     ecx, edi
0x180063750  call    EventWrite0
0x180063755  mov     rcx, [rsi]
0x180063758  lea     r9, WebReceiveResponseCompletion
0x18006375f  lea     r8, [rsp+38h+arg_8]
0x180063764  mov     [rsp+38h+var_18], rsi
0x180063769  xor     edx, edx
0x18006376b  call    cs:__imp_WebReceiveHttpResponse
0x180063772  nop     dword ptr [rax+rax+00h]
0x180063777  cmp     eax, 3E5h
0x18006377c  jz      loc_180063913
0x180063782  xor     r8d, r8d
0x180063785  mov     edx, eax
0x180063787  mov     rcx, rsi
0x18006378a  call    WebReceiveResponseCompletion
0x18006378f  jmp     loc_180063913
0x180063794  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18006379b  jz      loc_180063913
0x1800637a1  mov     r8, [rsi+80h]
0x1800637a8  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SEND_HTTP_REQUEST
0x1800637af  add     r8, 38h ; '8'
0x1800637b3  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800637ba  mov     r9d, 15h
0x1800637c0  call    McTemplateU0zq_EventWriteTransfer
0x1800637c5  jmp     loc_180063913
0x1800637ca  mov     r8, [rsi+80h]
0x1800637d1  lea     rdx, aSWebsendreques; "%s:WebSendRequestCompletion: Scheduling"...
0x1800637d8  mov     r9d, [rsi+78h]
0x1800637dc  add     r8, 38h ; '8'
0x1800637e0  mov     ecx, edi
0x1800637e2  mov     dword ptr [rsp+38h+var_18], ebx
0x1800637e6  call    EventWrite0
0x1800637eb  test    ebx, ebx
0x1800637ed  jz      short loc_1800637FC
0x1800637ef  mov     rax, [rsi+80h]
0x1800637f6  mov     [rax+4ACh], ebx
0x1800637fc  cmp     dword ptr [rsi+78h], 1
0x180063800  jnz     loc_18006390B
0x180063806  lea     eax, [rbx+7FF6FCF3h]
0x18006380c  cmp     eax, 1
0x18006380f  jbe     loc_1800638A1
0x180063815  cmp     ebx, 800B0110h
0x18006381b  jz      loc_1800638A1
0x180063821  cmp     ebx, 80090331h
0x180063827  jz      short loc_18006383D
0x180063829  cmp     ebx, 4C9h
0x18006382f  jz      short loc_18006383D
0x180063831  cmp     ebx, 2746h
0x180063837  jnz     loc_18006390B
0x18006383d  lea     rdi, [rsi+0B0h]
0x180063844  mov     rcx, rdi; lpCriticalSection
0x180063847  call    cs:__imp_EnterCriticalSection
0x18006384e  nop     dword ptr [rax+rax+00h]
0x180063853  mov     bl, [rsi+0E0h]
0x180063859  mov     rcx, rdi; lpCriticalSection
0x18006385c  test    bl, bl
0x18006385e  setz    al
0x180063861  mov     [rsi+0E0h], al
0x180063867  call    cs:__imp_LeaveCriticalSection
0x18006386e  nop     dword ptr [rax+rax+00h]
0x180063873  test    bl, bl
0x180063875  jz      loc_18006390B
0x18006387b  mov     rcx, rsi
0x18006387e  call    IpTlsClientReferenceIO
0x180063883  test    al, al
0x180063885  jz      loc_180063913
0x18006388b  lea     r8, IpTlsClientRestartClientWorker
0x180063892  mov     edx, 1
0x180063897  mov     rcx, rsi
0x18006389a  call    IpTlsClientScheduleWorkItem
0x18006389f  jmp     short loc_180063913
0x1800638a1  mov     rax, [rsi+80h]
0x1800638a8  mov     rcx, cs:g_IpTlsInterfaceListLock
0x1800638af  mov     rbx, [rax+470h]
0x1800638b6  call    IpTlsAcquireLock
0x1800638bb  mov     rcx, [rbx+10h]; pCertContext
0x1800638bf  call    cs:__imp_CertFreeCertificateContext
0x1800638c6  nop     dword ptr [rax+rax+00h]
0x1800638cb  mov     rcx, [rbx]
0x1800638ce  cmp     [rcx+8], rbx
0x1800638d2  jnz     short loc_180063904
0x1800638d4  mov     rax, [rbx+8]
0x1800638d8  cmp     [rax], rbx
0x1800638db  jnz     short loc_180063904
0x1800638dd  mov     [rax], rcx
0x1800638e0  mov     [rcx+8], rax
0x1800638e4  mov     rcx, rbx
0x1800638e7  call    FREE
0x1800638ec  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x1800638f3  call    cs:__imp_ReleaseMutex
0x1800638fa  nop     dword ptr [rax+rax+00h]
0x1800638ff  jmp     loc_18006387B
0x180063904  mov     ecx, 3
0x180063909  int     29h; Win8: RtlFailFast(ecx)
0x18006390b  mov     rcx, rsi
0x18006390e  call    IpTlsClientScheduleReconnect
0x180063913  mov     rcx, rsi
0x180063916  call    IpTlsClientDereferenceIO
0x18006391b  mov     r8, [rsi+80h]
0x180063922  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063929  mov     ebx, 727h
0x18006392e  lea     rdx, aSDereferenceIp; "(%s: Dereference IPTLS client interface"...
0x180063935  add     r8, 38h ; '8'
0x180063939  mov     dword ptr [rsp+38h+var_18], ebx
0x18006393d  mov     ecx, 20000000h
0x180063942  call    EventWrite0
0x180063947  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006394e  jz      short loc_18006396A
0x180063950  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063957  mov     dword ptr [rsp+38h+var_18], ebx
0x18006395b  mov     r8, rsi
0x18006395e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE
0x180063965  call    McTemplateU0psq_EventWriteTransfer
0x18006396a  mov     rcx, rsi
0x18006396d  call    DereferenceInterfaceEx
0x180063972  mov     rbx, [rsp+38h+arg_0]
0x180063977  mov     rsi, [rsp+38h+arg_10]
0x18006397c  add     rsp, 30h
0x180063980  pop     rdi
0x180063981  retn
```
