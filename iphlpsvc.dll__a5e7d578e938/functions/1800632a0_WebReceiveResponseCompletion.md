# WebReceiveResponseCompletion

- ea: `0x1800632a0`
- end: `0x18006366f`
- name: `WebReceiveResponseCompletion`
- size: `975`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180063680`

## callees

- `0x18000d7c0`
- `0x180030d34`
- `0x1800311e0`
- `0x180031698`
- `0x180031868`
- `0x180031aa8`
- `0x180031b0c`
- `0x180031e38`
- `0x180040d90`
- `0x180047cfc`
- `0x18004901c`
- `0x1800492cc`
- `0x1800606b8`
- `0x1800616b4`
- `0x180062418`
- `0x1800632a0`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x1800635a7`
- `ntdll!WinSqmIncrementDWORD` at `0x1800635a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800633b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800633b9`
- `webio!__imp_WebQueryHttpResponseStatusCode` at `0x180063331`
- `webio!__imp_WebQueryHttpResponseStatusCode` at `0x180063331`

## string_xrefs

- `0x1800634c0`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180063613`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180063641`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x1800632d3`: `%s:WebReceiveHttpResponse completed:%d`
- `0x180063344`: `%s:WebQueryHttpResponseStatusCode completed:%d, HTTP Status Code:%d`
- `0x180063501`: `%s:WebReceiveResponseCompletion:Got 403. Restartign with next cert`
- `0x180063555`: `%s:WebReceiveResponseCompletion:Got 407`
- `0x180063586`: `%s:WebReceiveResponseCompletion: handle proxy auth failed: %d`
- `0x1800633e2`: `%s:WebReceiveResponseCompletion:IpTlsInterfaceIndicateConnect failed`
- `0x180063408`: `%s:WebReceiveResponseCompletion:Rescheduling connect due toIpTlsInterfaceIndicateConnect failure.`
- `0x1800635e9`: `%s:WebReceiveResponseCompletion: Invalid state :%d`

## pseudocode

```c
__int64 __fastcall WebReceiveResponseCompletion(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // r8
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // r9
  int v9; // ebx
  DWORD TickCount; // eax
  DWORD v11; // ebx
  unsigned int v12; // ebx
  __int64 v13; // rbx
  __int64 v14; // rcx
  unsigned int v15; // eax
  int v16; // ecx
  __int64 v18; // [rsp+20h] [rbp-20h]
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 v20; // [rsp+70h] [rbp+30h] BYREF
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF

  v21 = a3;
  v3 = *(_QWORD *)(a1 + 128);
  v19 = 0;
  EventWrite0(0x10000000, L"%s:WebReceiveHttpResponse completed:%d", v3 + 56, a2);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_RECEIVE_HTTP_RESPONSE,
      *(_QWORD *)(a1 + 128) + 56LL,
      a2);
  if ( *(_DWORD *)(a1 + 120) != 1 )
  {
    EventWrite0(0x10000000, L"%s:WebReceiveResponseCompletion: Invalid state :%d", *(_QWORD *)(a1 + 128) + 56LL);
LABEL_32:
    ShutdownClientInternal(a1);
    goto LABEL_33;
  }
  if ( a2 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1196LL) = a2;
    goto LABEL_30;
  }
  v6 = *(_QWORD *)a1;
  v20 = 0;
  v7 = (unsigned int)WebQueryHttpResponseStatusCode(v6, &v20);
  EventWrite0(
    0x10000000,
    L"%s:WebQueryHttpResponseStatusCode completed:%d, HTTP Status Code:%d",
    *(_QWORD *)(a1 + 128) + 56LL,
    v7,
    v20);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
  {
    v8 = v20;
    if ( (_DWORD)v7 )
      v8 = (unsigned int)v7;
    McTemplateU0zq_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_HTTP_STATUS_CODE,
      *(_QWORD *)(a1 + 128) + 56LL,
      v8);
  }
  if ( (_DWORD)v7 || v20 != 200 )
  {
    if ( v20 == 403 )
    {
      EventWrite0(
        0x10000000,
        L"%s:WebReceiveResponseCompletion:Got 403. Restartign with next cert",
        *(_QWORD *)(a1 + 128) + 56LL);
      if ( (unsigned __int8)IpTlsClientReferenceIO(a1) )
        IpTlsClientScheduleWorkItem(a1, 0, (__int64)IpTlsClientRestartClientWorker);
    }
    else
    {
      v14 = *(_QWORD *)(a1 + 128);
      if ( v20 != 407 )
      {
        if ( v20 != 200 )
          LODWORD(v7) = v20 | 0x80190000;
        *(_DWORD *)(v14 + 1196) = v7;
        goto LABEL_30;
      }
      *(_DWORD *)(v14 + 1196) = -2145844841;
      EventWrite0(0x10000000, L"%s:WebReceiveResponseCompletion:Got 407", *(_QWORD *)(a1 + 128) + 56LL);
      v15 = IpTlsHandleProxyAuthentication(a1);
      if ( v15 )
      {
        EventWrite0(
          0x10000000,
          L"%s:WebReceiveResponseCompletion: handle proxy auth failed: %d",
          *(_QWORD *)(a1 + 128) + 56LL,
          v15);
        WinSqmIncrementDWORD(0, 6751, 1);
      }
    }
  }
  else
  {
    v9 = *(_DWORD *)(a1 + 220);
    TickCount = GetTickCount();
    v11 = IpTlsInterfaceIndicateConnect(*(_QWORD *)(a1 + 128), TickCount - v9);
    if ( v11 )
    {
      EventWrite0(
        0x10000000,
        L"%s:WebReceiveResponseCompletion:IpTlsInterfaceIndicateConnect failed",
        *(_QWORD *)(a1 + 128) + 56LL);
      if ( v11 != 5023 )
      {
        EventWrite0(
          0x10000000,
          L"%s:WebReceiveResponseCompletion:Rescheduling connect due toIpTlsInterfaceIndicateConnect failure.",
          *(_QWORD *)(a1 + 128) + 56LL);
LABEL_30:
        IpTlsClientScheduleReconnect(a1);
        goto LABEL_33;
      }
      goto LABEL_32;
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 120), 3, 1) == 1 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1192LL) = 9;
      *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1196LL) = 0;
      IpTlsStoreInterfacePersistentValues(*(const BYTE **)(a1 + 128), *(_DWORD *)(*(_QWORD *)(a1 + 128) + 1024LL), 12);
      *(_QWORD *)(a1 + 168) = 0;
      v12 = PostReceiveEntityOnClient(a1, &v21, &v19);
      if ( v12 != 997 )
      {
        if ( (unsigned __int8)IpTlsClientReferenceIO(a1) )
        {
          ClientReceiveEntityCompletion(v19, v12, v21);
        }
        else
        {
          v13 = v19;
          if ( v19 )
          {
            LODWORD(v18) = 2285;
            EventWrite0(
              0x20000000,
              L"(Dereference IPTLS Buffer(%p)%S:%d",
              v19,
              "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
              v18);
            IpTlsDereferenceBufferEx(v13);
          }
        }
      }
    }
  }
LABEL_33:
  IpTlsClientDereferenceIO(a1);
  LODWORD(v18) = 2308;
  EventWrite0(
    0x20000000,
    L"(%s: Dereference IPTLS client interface %S:%d",
    *(_QWORD *)(a1 + 128) + 56LL,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
    v18);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v16,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE,
      a1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
      4);
  return DereferenceInterfaceEx((__int64 *)a1);
}

```

## disassembly

```asm
0x1800632a0  mov     [rsp-28h+arg_10], r8
0x1800632a5  push    rbp
0x1800632a6  push    rbx
0x1800632a7  push    rsi
0x1800632a8  push    rdi
0x1800632a9  push    r12
0x1800632ab  mov     rbp, rsp
0x1800632ae  sub     rsp, 40h
0x1800632b2  mov     r8, [rcx+80h]
0x1800632b9  mov     ebx, edx
0x1800632bb  mov     rdi, rcx
0x1800632be  mov     [rbp+var_10], 0
0x1800632c6  mov     r9d, edx
0x1800632c9  mov     r12d, 10000000h
0x1800632cf  add     r8, 38h ; '8'
0x1800632d3  lea     rdx, aSWebreceivehtt_1; "%s:WebReceiveHttpResponse completed:%d"
0x1800632da  mov     ecx, r12d
0x1800632dd  xor     esi, esi
0x1800632df  call    EventWrite0
0x1800632e4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800632eb  jz      short loc_18006330E
0x1800632ed  mov     r8, [rdi+80h]
0x1800632f4  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_RECEIVE_HTTP_RESPONSE
0x1800632fb  add     r8, 38h ; '8'
0x1800632ff  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180063306  mov     r9d, ebx
0x180063309  call    McTemplateU0zq_EventWriteTransfer
0x18006330e  mov     r9d, [rdi+78h]
0x180063312  cmp     r9d, 1
0x180063316  jnz     loc_1800635E2
0x18006331c  test    ebx, ebx
0x18006331e  jnz     loc_1800635CB
0x180063324  mov     rcx, [rdi]
0x180063327  lea     rdx, [rbp+arg_0]
0x18006332b  xor     eax, eax
0x18006332d  mov     [rbp+arg_0], ax
0x180063331  call    cs:__imp_WebQueryHttpResponseStatusCode
0x180063338  nop     dword ptr [rax+rax+00h]
0x18006333d  mov     r8, [rdi+80h]
0x180063344  lea     rdx, aSWebqueryhttpr_0; "%s:WebQueryHttpResponseStatusCode compl"...
0x18006334b  mov     ebx, eax
0x18006334d  add     r8, 38h ; '8'
0x180063351  movzx   eax, [rbp+arg_0]
0x180063355  mov     r9d, ebx
0x180063358  mov     ecx, r12d
0x18006335b  mov     [rsp+40h+var_20], eax
0x18006335f  call    EventWrite0
0x180063364  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18006336b  jz      short loc_180063397
0x18006336d  movzx   r9d, [rbp+arg_0]
0x180063372  test    ebx, ebx
0x180063374  jz      short loc_180063379
0x180063376  mov     r9d, ebx
0x180063379  mov     r8, [rdi+80h]
0x180063380  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_HTTP_STATUS_CODE
0x180063387  add     r8, 38h ; '8'
0x18006338b  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180063392  call    McTemplateU0zq_EventWriteTransfer
0x180063397  movzx   eax, [rbp+arg_0]
0x18006339b  mov     r8d, 0C8h
0x1800633a1  test    ebx, ebx
0x1800633a3  jnz     loc_1800634F0
0x1800633a9  cmp     ax, r8w
0x1800633ad  jnz     loc_1800634F0
0x1800633b3  mov     ebx, [rdi+0DCh]
0x1800633b9  call    cs:__imp_GetTickCount
0x1800633c0  nop     dword ptr [rax+rax+00h]
0x1800633c5  mov     rcx, [rdi+80h]
0x1800633cc  sub     eax, ebx
0x1800633ce  mov     edx, eax
0x1800633d0  call    IpTlsInterfaceIndicateConnect
0x1800633d5  mov     ebx, eax
0x1800633d7  test    eax, eax
0x1800633d9  jz      short loc_180063420
0x1800633db  mov     r8, [rdi+80h]
0x1800633e2  lea     rdx, aSWebreceiveres_0; "%s:WebReceiveResponseCompletion:IpTlsIn"...
0x1800633e9  add     r8, 38h ; '8'
0x1800633ed  mov     ecx, r12d
0x1800633f0  call    EventWrite0
0x1800633f5  cmp     ebx, 139Fh
0x1800633fb  jz      loc_1800635FC
0x180063401  mov     r8, [rdi+80h]
0x180063408  lea     rdx, aSWebreceiveres; "%s:WebReceiveResponseCompletion:Resched"...
0x18006340f  add     r8, 38h ; '8'
0x180063413  mov     ecx, r12d
0x180063416  call    EventWrite0
0x18006341b  jmp     loc_1800635D8
0x180063420  mov     ecx, 3
0x180063425  lea     eax, [rcx-2]
0x180063428  lock cmpxchg [rdi+78h], ecx
0x18006342d  jnz     loc_180063604
0x180063433  mov     rax, [rdi+80h]
0x18006343a  mov     dword ptr [rax+4A8h], 9
0x180063444  mov     rax, [rdi+80h]
0x18006344b  mov     [rax+4ACh], esi
0x180063451  or      si, 0Ch
0x180063455  mov     rcx, [rdi+80h]
0x18006345c  movzx   r8d, si
0x180063460  mov     edx, [rcx+400h]
0x180063466  call    IpTlsStoreInterfacePersistentValues
0x18006346b  lea     r8, [rbp+var_10]
0x18006346f  mov     qword ptr [rdi+0A8h], 0
0x18006347a  lea     rdx, [rbp+arg_10]
0x18006347e  mov     rcx, rdi
0x180063481  call    PostReceiveEntityOnClient
0x180063486  mov     ebx, eax
0x180063488  cmp     eax, 3E5h
0x18006348d  jz      loc_180063604
0x180063493  mov     rcx, rdi
0x180063496  call    IpTlsClientReferenceIO
0x18006349b  test    al, al
0x18006349d  jz      short loc_1800634B3
0x18006349f  mov     r8, [rbp+arg_10]
0x1800634a3  mov     edx, ebx
0x1800634a5  mov     rcx, [rbp+var_10]
0x1800634a9  call    ClientReceiveEntityCompletion
0x1800634ae  jmp     loc_180063604
0x1800634b3  mov     rbx, [rbp+var_10]
0x1800634b7  test    rbx, rbx
0x1800634ba  jz      loc_180063604
0x1800634c0  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800634c7  mov     [rsp+40h+var_20], 8EDh
0x1800634cf  mov     r8, rbx
0x1800634d2  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x1800634d9  mov     ecx, 20000000h
0x1800634de  call    EventWrite0
0x1800634e3  mov     rcx, rbx
0x1800634e6  call    IpTlsDereferenceBufferEx
0x1800634eb  jmp     loc_180063604
0x1800634f0  mov     ecx, 193h
0x1800634f5  cmp     ax, cx
0x1800634f8  jnz     short loc_18006353A
0x1800634fa  mov     r8, [rdi+80h]
0x180063501  lea     rdx, aSWebreceiveres_2; "%s:WebReceiveResponseCompletion:Got 403"...
0x180063508  add     r8, 38h ; '8'
0x18006350c  mov     ecx, r12d
0x18006350f  call    EventWrite0
0x180063514  mov     rcx, rdi
0x180063517  call    IpTlsClientReferenceIO
0x18006351c  test    al, al
0x18006351e  jz      loc_180063604
0x180063524  lea     r8, IpTlsClientRestartClientWorker
0x18006352b  xor     edx, edx
0x18006352d  mov     rcx, rdi
0x180063530  call    IpTlsClientScheduleWorkItem
0x180063535  jmp     loc_180063604
0x18006353a  mov     rcx, [rdi+80h]
0x180063541  mov     edx, 197h
0x180063546  cmp     ax, dx
0x180063549  jnz     short loc_1800635B5
0x18006354b  mov     dword ptr [rcx+4ACh], 80190197h
0x180063555  lea     rdx, aSWebreceiveres_1; "%s:WebReceiveResponseCompletion:Got 407"
0x18006355c  mov     r8, [rdi+80h]
0x180063563  mov     ecx, r12d
0x180063566  add     r8, 38h ; '8'
0x18006356a  call    EventWrite0
0x18006356f  mov     rcx, rdi
0x180063572  call    IpTlsHandleProxyAuthentication
0x180063577  test    eax, eax
0x180063579  jz      loc_180063604
0x18006357f  mov     r8, [rdi+80h]
0x180063586  lea     rdx, aSWebreceiveres_4; "%s:WebReceiveResponseCompletion: handle"...
0x18006358d  add     r8, 38h ; '8'
0x180063591  mov     r9d, eax
0x180063594  mov     ecx, r12d
0x180063597  call    EventWrite0
0x18006359c  xor     ecx, ecx
0x18006359e  mov     edx, 1A5Fh
0x1800635a3  lea     r8d, [rcx+1]
0x1800635a7  call    cs:__imp_WinSqmIncrementDWORD
0x1800635ae  nop     dword ptr [rax+rax+00h]
0x1800635b3  jmp     short loc_180063604
0x1800635b5  cmp     ax, r8w
0x1800635b9  jz      short loc_1800635C3
0x1800635bb  mov     ebx, eax
0x1800635bd  or      ebx, 80190000h
0x1800635c3  mov     [rcx+4ACh], ebx
0x1800635c9  jmp     short loc_1800635D8
0x1800635cb  mov     rax, [rdi+80h]
0x1800635d2  mov     [rax+4ACh], ebx
0x1800635d8  mov     rcx, rdi
0x1800635db  call    IpTlsClientScheduleReconnect
0x1800635e0  jmp     short loc_180063604
0x1800635e2  mov     r8, [rdi+80h]
0x1800635e9  lea     rdx, aSWebreceiveres_3; "%s:WebReceiveResponseCompletion: Invali"...
0x1800635f0  add     r8, 38h ; '8'
0x1800635f4  mov     ecx, r12d
0x1800635f7  call    EventWrite0
0x1800635fc  mov     rcx, rdi
0x1800635ff  call    ShutdownClientInternal
0x180063604  mov     rcx, rdi
0x180063607  call    IpTlsClientDereferenceIO
0x18006360c  mov     r8, [rdi+80h]
0x180063613  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006361a  mov     ebx, 904h
0x18006361f  lea     rdx, aSDereferenceIp; "(%s: Dereference IPTLS client interface"...
0x180063626  add     r8, 38h ; '8'
0x18006362a  mov     [rsp+40h+var_20], ebx
0x18006362e  mov     ecx, 20000000h
0x180063633  call    EventWrite0
0x180063638  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006363f  jz      short loc_18006365B
0x180063641  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063648  mov     [rsp+40h+var_20], ebx
0x18006364c  mov     r8, rdi
0x18006364f  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE
0x180063656  call    McTemplateU0psq_EventWriteTransfer
0x18006365b  mov     rcx, rdi
0x18006365e  call    DereferenceInterfaceEx
0x180063663  add     rsp, 40h
0x180063667  pop     r12
0x180063669  pop     rdi
0x18006366a  pop     rsi
0x18006366b  pop     rbx
0x18006366c  pop     rbp
0x18006366d  retn
```
