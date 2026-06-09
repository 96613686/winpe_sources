# WebReceiveResponseCompletion

- ea: `0x180063280`
- end: `0x18006364f`
- name: `WebReceiveResponseCompletion`
- size: `975`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180063660`

## callees

- `0x18000d7b0`
- `0x180030d24`
- `0x1800311d0`
- `0x180031688`
- `0x180031858`
- `0x180031a98`
- `0x180031afc`
- `0x180031e28`
- `0x180040dd0`
- `0x180047d3c`
- `0x18004905c`
- `0x18004930c`
- `0x180060698`
- `0x180061694`
- `0x1800623f8`
- `0x180063280`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x180063587`
- `ntdll!WinSqmIncrementDWORD` at `0x180063587`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180063399`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180063399`
- `webio!__imp_WebQueryHttpResponseStatusCode` at `0x180063311`
- `webio!__imp_WebQueryHttpResponseStatusCode` at `0x180063311`

## string_xrefs

- `0x1800634a0`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x1800635f3`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180063621`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x1800632b3`: `%s:WebReceiveHttpResponse completed:%d`
- `0x180063324`: `%s:WebQueryHttpResponseStatusCode completed:%d, HTTP Status Code:%d`
- `0x1800634e1`: `%s:WebReceiveResponseCompletion:Got 403. Restartign with next cert`
- `0x180063535`: `%s:WebReceiveResponseCompletion:Got 407`
- `0x180063566`: `%s:WebReceiveResponseCompletion: handle proxy auth failed: %d`
- `0x1800633c2`: `%s:WebReceiveResponseCompletion:IpTlsInterfaceIndicateConnect failed`
- `0x1800633e8`: `%s:WebReceiveResponseCompletion:Rescheduling connect due toIpTlsInterfaceIndicateConnect failure.`
- `0x1800635c9`: `%s:WebReceiveResponseCompletion: Invalid state :%d`

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
  int v11; // ebx
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
0x180063280  mov     [rsp-28h+arg_10], r8
0x180063285  push    rbp
0x180063286  push    rbx
0x180063287  push    rsi
0x180063288  push    rdi
0x180063289  push    r12
0x18006328b  mov     rbp, rsp
0x18006328e  sub     rsp, 40h
0x180063292  mov     r8, [rcx+80h]
0x180063299  mov     ebx, edx
0x18006329b  mov     rdi, rcx
0x18006329e  mov     [rbp+var_10], 0
0x1800632a6  mov     r9d, edx
0x1800632a9  mov     r12d, 10000000h
0x1800632af  add     r8, 38h ; '8'
0x1800632b3  lea     rdx, aSWebreceivehtt_1; "%s:WebReceiveHttpResponse completed:%d"
0x1800632ba  mov     ecx, r12d
0x1800632bd  xor     esi, esi
0x1800632bf  call    EventWrite0
0x1800632c4  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x1800632cb  jz      short loc_1800632EE
0x1800632cd  mov     r8, [rdi+80h]
0x1800632d4  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_RECEIVE_HTTP_RESPONSE
0x1800632db  add     r8, 38h ; '8'
0x1800632df  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800632e6  mov     r9d, ebx
0x1800632e9  call    McTemplateU0zq_EventWriteTransfer
0x1800632ee  mov     r9d, [rdi+78h]
0x1800632f2  cmp     r9d, 1
0x1800632f6  jnz     loc_1800635C2
0x1800632fc  test    ebx, ebx
0x1800632fe  jnz     loc_1800635AB
0x180063304  mov     rcx, [rdi]
0x180063307  lea     rdx, [rbp+arg_0]
0x18006330b  xor     eax, eax
0x18006330d  mov     [rbp+arg_0], ax
0x180063311  call    cs:__imp_WebQueryHttpResponseStatusCode
0x180063318  nop     dword ptr [rax+rax+00h]
0x18006331d  mov     r8, [rdi+80h]
0x180063324  lea     rdx, aSWebqueryhttpr_0; "%s:WebQueryHttpResponseStatusCode compl"...
0x18006332b  mov     ebx, eax
0x18006332d  add     r8, 38h ; '8'
0x180063331  movzx   eax, [rbp+arg_0]
0x180063335  mov     r9d, ebx
0x180063338  mov     ecx, r12d
0x18006333b  mov     [rsp+40h+var_20], eax
0x18006333f  call    EventWrite0
0x180063344  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18006334b  jz      short loc_180063377
0x18006334d  movzx   r9d, [rbp+arg_0]
0x180063352  test    ebx, ebx
0x180063354  jz      short loc_180063359
0x180063356  mov     r9d, ebx
0x180063359  mov     r8, [rdi+80h]
0x180063360  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_HTTP_STATUS_CODE
0x180063367  add     r8, 38h ; '8'
0x18006336b  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180063372  call    McTemplateU0zq_EventWriteTransfer
0x180063377  movzx   eax, [rbp+arg_0]
0x18006337b  mov     r8d, 0C8h
0x180063381  test    ebx, ebx
0x180063383  jnz     loc_1800634D0
0x180063389  cmp     ax, r8w
0x18006338d  jnz     loc_1800634D0
0x180063393  mov     ebx, [rdi+0DCh]
0x180063399  call    cs:__imp_GetTickCount
0x1800633a0  nop     dword ptr [rax+rax+00h]
0x1800633a5  mov     rcx, [rdi+80h]
0x1800633ac  sub     eax, ebx
0x1800633ae  mov     edx, eax
0x1800633b0  call    IpTlsInterfaceIndicateConnect
0x1800633b5  mov     ebx, eax
0x1800633b7  test    eax, eax
0x1800633b9  jz      short loc_180063400
0x1800633bb  mov     r8, [rdi+80h]
0x1800633c2  lea     rdx, aSWebreceiveres_0; "%s:WebReceiveResponseCompletion:IpTlsIn"...
0x1800633c9  add     r8, 38h ; '8'
0x1800633cd  mov     ecx, r12d
0x1800633d0  call    EventWrite0
0x1800633d5  cmp     ebx, 139Fh
0x1800633db  jz      loc_1800635DC
0x1800633e1  mov     r8, [rdi+80h]
0x1800633e8  lea     rdx, aSWebreceiveres; "%s:WebReceiveResponseCompletion:Resched"...
0x1800633ef  add     r8, 38h ; '8'
0x1800633f3  mov     ecx, r12d
0x1800633f6  call    EventWrite0
0x1800633fb  jmp     loc_1800635B8
0x180063400  mov     ecx, 3
0x180063405  lea     eax, [rcx-2]
0x180063408  lock cmpxchg [rdi+78h], ecx
0x18006340d  jnz     loc_1800635E4
0x180063413  mov     rax, [rdi+80h]
0x18006341a  mov     dword ptr [rax+4A8h], 9
0x180063424  mov     rax, [rdi+80h]
0x18006342b  mov     [rax+4ACh], esi
0x180063431  or      si, 0Ch
0x180063435  mov     rcx, [rdi+80h]
0x18006343c  movzx   r8d, si
0x180063440  mov     edx, [rcx+400h]
0x180063446  call    IpTlsStoreInterfacePersistentValues
0x18006344b  lea     r8, [rbp+var_10]
0x18006344f  mov     qword ptr [rdi+0A8h], 0
0x18006345a  lea     rdx, [rbp+arg_10]
0x18006345e  mov     rcx, rdi
0x180063461  call    PostReceiveEntityOnClient
0x180063466  mov     ebx, eax
0x180063468  cmp     eax, 3E5h
0x18006346d  jz      loc_1800635E4
0x180063473  mov     rcx, rdi
0x180063476  call    IpTlsClientReferenceIO
0x18006347b  test    al, al
0x18006347d  jz      short loc_180063493
0x18006347f  mov     r8, [rbp+arg_10]
0x180063483  mov     edx, ebx
0x180063485  mov     rcx, [rbp+var_10]
0x180063489  call    ClientReceiveEntityCompletion
0x18006348e  jmp     loc_1800635E4
0x180063493  mov     rbx, [rbp+var_10]
0x180063497  test    rbx, rbx
0x18006349a  jz      loc_1800635E4
0x1800634a0  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800634a7  mov     [rsp+40h+var_20], 8EDh
0x1800634af  mov     r8, rbx
0x1800634b2  lea     rdx, aDereferenceIpt; "(Dereference IPTLS Buffer(%p)%S:%d"
0x1800634b9  mov     ecx, 20000000h
0x1800634be  call    EventWrite0
0x1800634c3  mov     rcx, rbx
0x1800634c6  call    IpTlsDereferenceBufferEx
0x1800634cb  jmp     loc_1800635E4
0x1800634d0  mov     ecx, 193h
0x1800634d5  cmp     ax, cx
0x1800634d8  jnz     short loc_18006351A
0x1800634da  mov     r8, [rdi+80h]
0x1800634e1  lea     rdx, aSWebreceiveres_2; "%s:WebReceiveResponseCompletion:Got 403"...
0x1800634e8  add     r8, 38h ; '8'
0x1800634ec  mov     ecx, r12d
0x1800634ef  call    EventWrite0
0x1800634f4  mov     rcx, rdi
0x1800634f7  call    IpTlsClientReferenceIO
0x1800634fc  test    al, al
0x1800634fe  jz      loc_1800635E4
0x180063504  lea     r8, IpTlsClientRestartClientWorker
0x18006350b  xor     edx, edx
0x18006350d  mov     rcx, rdi
0x180063510  call    IpTlsClientScheduleWorkItem
0x180063515  jmp     loc_1800635E4
0x18006351a  mov     rcx, [rdi+80h]
0x180063521  mov     edx, 197h
0x180063526  cmp     ax, dx
0x180063529  jnz     short loc_180063595
0x18006352b  mov     dword ptr [rcx+4ACh], 80190197h
0x180063535  lea     rdx, aSWebreceiveres_1; "%s:WebReceiveResponseCompletion:Got 407"
0x18006353c  mov     r8, [rdi+80h]
0x180063543  mov     ecx, r12d
0x180063546  add     r8, 38h ; '8'
0x18006354a  call    EventWrite0
0x18006354f  mov     rcx, rdi
0x180063552  call    IpTlsHandleProxyAuthentication
0x180063557  test    eax, eax
0x180063559  jz      loc_1800635E4
0x18006355f  mov     r8, [rdi+80h]
0x180063566  lea     rdx, aSWebreceiveres_4; "%s:WebReceiveResponseCompletion: handle"...
0x18006356d  add     r8, 38h ; '8'
0x180063571  mov     r9d, eax
0x180063574  mov     ecx, r12d
0x180063577  call    EventWrite0
0x18006357c  xor     ecx, ecx
0x18006357e  mov     edx, 1A5Fh
0x180063583  lea     r8d, [rcx+1]
0x180063587  call    cs:__imp_WinSqmIncrementDWORD
0x18006358e  nop     dword ptr [rax+rax+00h]
0x180063593  jmp     short loc_1800635E4
0x180063595  cmp     ax, r8w
0x180063599  jz      short loc_1800635A3
0x18006359b  mov     ebx, eax
0x18006359d  or      ebx, 80190000h
0x1800635a3  mov     [rcx+4ACh], ebx
0x1800635a9  jmp     short loc_1800635B8
0x1800635ab  mov     rax, [rdi+80h]
0x1800635b2  mov     [rax+4ACh], ebx
0x1800635b8  mov     rcx, rdi
0x1800635bb  call    IpTlsClientScheduleReconnect
0x1800635c0  jmp     short loc_1800635E4
0x1800635c2  mov     r8, [rdi+80h]
0x1800635c9  lea     rdx, aSWebreceiveres_3; "%s:WebReceiveResponseCompletion: Invali"...
0x1800635d0  add     r8, 38h ; '8'
0x1800635d4  mov     ecx, r12d
0x1800635d7  call    EventWrite0
0x1800635dc  mov     rcx, rdi
0x1800635df  call    ShutdownClientInternal
0x1800635e4  mov     rcx, rdi
0x1800635e7  call    IpTlsClientDereferenceIO
0x1800635ec  mov     r8, [rdi+80h]
0x1800635f3  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800635fa  mov     ebx, 904h
0x1800635ff  lea     rdx, aSDereferenceIp; "(%s: Dereference IPTLS client interface"...
0x180063606  add     r8, 38h ; '8'
0x18006360a  mov     [rsp+40h+var_20], ebx
0x18006360e  mov     ecx, 20000000h
0x180063613  call    EventWrite0
0x180063618  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006361f  jz      short loc_18006363B
0x180063621  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180063628  mov     [rsp+40h+var_20], ebx
0x18006362c  mov     r8, rdi
0x18006362f  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_CLIENT_INTERFACE_DEREFERENCE
0x180063636  call    McTemplateU0psq_EventWriteTransfer
0x18006363b  mov     rcx, rdi
0x18006363e  call    DereferenceInterfaceEx
0x180063643  add     rsp, 40h
0x180063647  pop     r12
0x180063649  pop     rdi
0x18006364a  pop     rsi
0x18006364b  pop     rbx
0x18006364c  pop     rbp
0x18006364d  retn
```
