# WebSendRequestCompletion

- ea: `0x180063680`
- end: `0x1800639a3`
- name: `WebSendRequestCompletion`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800620a4`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180013580`
- `0x180031698`
- `0x180031aa8`
- `0x180031b0c`
- `0x180031e38`
- `0x180040d90`
- `0x1800492cc`
- `0x1800616b4`
- `0x1800632a0`
- `0x180063680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180063913`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180063913`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063867`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063867`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063887`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063887`
- `CRYPT32!CertFreeCertificateContext` at `0x1800638df`
- `CRYPT32!CertFreeCertificateContext` at `0x1800638df`
- `webio!__imp_WebReceiveHttpResponse` at `0x18006378b`
- `webio!__imp_WebReceiveHttpResponse` at `0x18006378b`

## string_xrefs

- `0x180063710`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x18006373e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180063942`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180063970`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x1800636af`: `%s:WebSendHttpRequest completed:%d`
- `0x1800637f1`: `%s:WebSendRequestCompletion: Scheduling a reconnectInterface State: %d Status: %d`

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
0x180063680  mov     [rsp+arg_0], rbx
0x180063685  mov     [rsp+arg_10], rsi
0x18006368a  push    rdi
0x18006368b  sub     rsp, 30h
0x18006368f  mov     r8, [rcx+80h]
0x180063696  mov     ebx, edx
0x180063698  mov     rsi, rcx
0x18006369b  mov     [rsp+38h+arg_8], 0
0x1800636a3  mov     r9d, edx
0x1800636a6  mov     edi, 10000000h
0x1800636ab  add     r8, 38h ; '8'
0x1800636af  lea     rdx, aSWebsendhttpre; "%s:WebSendHttpRequest completed:%d"
0x1800636b6  mov     ecx, edi
0x1800636b8  call    EventWrite0
0x1800636bd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800636c4  jz      short loc_1800636E7
0x1800636c6  mov     r8, [rsi+80h]
0x1800636cd  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SEND_HTTP_REQUEST
0x1800636d4  add     r8, 38h ; '8'
0x1800636d8  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800636df  mov     r9d, ebx
0x1800636e2  call    McTemplateU0zq_EventWriteTransfer
0x1800636e7  test    ebx, ebx
0x1800636e9  jnz     loc_1800637EA
0x1800636ef  cmp     dword ptr [rsi+78h], 1
0x1800636f3  jnz     loc_1800637EA
0x1800636f9  mov     rcx, rsi
0x1800636fc  call    IpTlsClientReferenceIO
0x180063701  test    al, al
0x180063703  jz      loc_1800637B4
0x180063709  mov     r8, [rsi+80h]
0x180063710  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063717  mov     ebx, 6C1h
0x18006371c  lea     rdx, aSReferenceIptl; "(%s: Reference IPTLS client interface %"...
0x180063723  add     r8, 38h ; '8'
0x180063727  mov     dword ptr [rsp+38h+var_18], ebx
0x18006372b  mov     ecx, 20000000h
0x180063730  call    EventWrite0
0x180063735  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006373c  jz      short loc_180063758
0x18006373e  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063745  mov     dword ptr [rsp+38h+var_18], ebx
0x180063749  mov     r8, rsi
0x18006374c  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_REFERENCE
0x180063753  call    McTemplateU0psq_EventWriteTransfer
0x180063758  lock inc dword ptr [rsi+7Ch]
0x18006375c  mov     r8, [rsi+80h]
0x180063763  lea     rdx, aSWebreceivehtt_0; "%s:WebReceiveHttpResponse"
0x18006376a  add     r8, 38h ; '8'
0x18006376e  mov     ecx, edi
0x180063770  call    EventWrite0
0x180063775  mov     rcx, [rsi]
0x180063778  lea     r9, WebReceiveResponseCompletion
0x18006377f  lea     r8, [rsp+38h+arg_8]
0x180063784  mov     [rsp+38h+var_18], rsi
0x180063789  xor     edx, edx
0x18006378b  call    cs:__imp_WebReceiveHttpResponse
0x180063792  nop     dword ptr [rax+rax+00h]
0x180063797  cmp     eax, 3E5h
0x18006379c  jz      loc_180063933
0x1800637a2  xor     r8d, r8d
0x1800637a5  mov     edx, eax
0x1800637a7  mov     rcx, rsi
0x1800637aa  call    WebReceiveResponseCompletion
0x1800637af  jmp     loc_180063933
0x1800637b4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800637bb  jz      loc_180063933
0x1800637c1  mov     r8, [rsi+80h]
0x1800637c8  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_SEND_HTTP_REQUEST
0x1800637cf  add     r8, 38h ; '8'
0x1800637d3  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800637da  mov     r9d, 15h
0x1800637e0  call    McTemplateU0zq_EventWriteTransfer
0x1800637e5  jmp     loc_180063933
0x1800637ea  mov     r8, [rsi+80h]
0x1800637f1  lea     rdx, aSWebsendreques; "%s:WebSendRequestCompletion: Scheduling"...
0x1800637f8  mov     r9d, [rsi+78h]
0x1800637fc  add     r8, 38h ; '8'
0x180063800  mov     ecx, edi
0x180063802  mov     dword ptr [rsp+38h+var_18], ebx
0x180063806  call    EventWrite0
0x18006380b  test    ebx, ebx
0x18006380d  jz      short loc_18006381C
0x18006380f  mov     rax, [rsi+80h]
0x180063816  mov     [rax+4ACh], ebx
0x18006381c  cmp     dword ptr [rsi+78h], 1
0x180063820  jnz     loc_18006392B
0x180063826  lea     eax, [rbx+7FF6FCF3h]
0x18006382c  cmp     eax, 1
0x18006382f  jbe     loc_1800638C1
0x180063835  cmp     ebx, 800B0110h
0x18006383b  jz      loc_1800638C1
0x180063841  cmp     ebx, 80090331h
0x180063847  jz      short loc_18006385D
0x180063849  cmp     ebx, 4C9h
0x18006384f  jz      short loc_18006385D
0x180063851  cmp     ebx, 2746h
0x180063857  jnz     loc_18006392B
0x18006385d  lea     rdi, [rsi+0B0h]
0x180063864  mov     rcx, rdi; lpCriticalSection
0x180063867  call    cs:__imp_EnterCriticalSection
0x18006386e  nop     dword ptr [rax+rax+00h]
0x180063873  mov     bl, [rsi+0E0h]
0x180063879  mov     rcx, rdi; lpCriticalSection
0x18006387c  test    bl, bl
0x18006387e  setz    al
0x180063881  mov     [rsi+0E0h], al
0x180063887  call    cs:__imp_LeaveCriticalSection
0x18006388e  nop     dword ptr [rax+rax+00h]
0x180063893  test    bl, bl
0x180063895  jz      loc_18006392B
0x18006389b  mov     rcx, rsi
0x18006389e  call    IpTlsClientReferenceIO
0x1800638a3  test    al, al
0x1800638a5  jz      loc_180063933
0x1800638ab  lea     r8, IpTlsClientRestartClientWorker
0x1800638b2  mov     edx, 1
0x1800638b7  mov     rcx, rsi
0x1800638ba  call    IpTlsClientScheduleWorkItem
0x1800638bf  jmp     short loc_180063933
0x1800638c1  mov     rax, [rsi+80h]
0x1800638c8  mov     rcx, cs:g_IpTlsInterfaceListLock
0x1800638cf  mov     rbx, [rax+470h]
0x1800638d6  call    IpTlsAcquireLock
0x1800638db  mov     rcx, [rbx+10h]; pCertContext
0x1800638df  call    cs:__imp_CertFreeCertificateContext
0x1800638e6  nop     dword ptr [rax+rax+00h]
0x1800638eb  mov     rcx, [rbx]
0x1800638ee  cmp     [rcx+8], rbx
0x1800638f2  jnz     short loc_180063924
0x1800638f4  mov     rax, [rbx+8]
0x1800638f8  cmp     [rax], rbx
0x1800638fb  jnz     short loc_180063924
0x1800638fd  mov     [rax], rcx
0x180063900  mov     [rcx+8], rax
0x180063904  mov     rcx, rbx
0x180063907  call    FREE
0x18006390c  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x180063913  call    cs:__imp_ReleaseMutex
0x18006391a  nop     dword ptr [rax+rax+00h]
0x18006391f  jmp     loc_18006389B
0x180063924  mov     ecx, 3
0x180063929  int     29h; Win8: RtlFailFast(ecx)
0x18006392b  mov     rcx, rsi
0x18006392e  call    IpTlsClientScheduleReconnect
0x180063933  mov     rcx, rsi
0x180063936  call    IpTlsClientDereferenceIO
0x18006393b  mov     r8, [rsi+80h]
0x180063942  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063949  mov     ebx, 727h
0x18006394e  lea     rdx, aSDereferenceIp; "(%s: Dereference IPTLS client interface"...
0x180063955  add     r8, 38h ; '8'
0x180063959  mov     dword ptr [rsp+38h+var_18], ebx
0x18006395d  mov     ecx, 20000000h
0x180063962  call    EventWrite0
0x180063967  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006396e  jz      short loc_18006398A
0x180063970  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063977  mov     dword ptr [rsp+38h+var_18], ebx
0x18006397b  mov     r8, rsi
0x18006397e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE
0x180063985  call    McTemplateU0psq_EventWriteTransfer
0x18006398a  mov     rcx, rsi
0x18006398d  call    DereferenceInterfaceEx
0x180063992  mov     rbx, [rsp+38h+arg_0]
0x180063997  mov     rsi, [rsp+38h+arg_10]
0x18006399c  add     rsp, 30h
0x1800639a0  pop     rdi
0x1800639a1  retn
```
