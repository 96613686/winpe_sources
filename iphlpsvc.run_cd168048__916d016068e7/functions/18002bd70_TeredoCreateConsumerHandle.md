# TeredoCreateConsumerHandle

- ea: `0x18002bd70`
- end: `0x18002c0a3`
- name: `TeredoCreateConsumerHandle`
- size: `819`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000482c`
- `0x180004dd0`
- `0x180009000`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800190e0`
- `0x180024240`
- `0x18002bd70`
- `0x18002c0ac`
- `0x18002c268`
- `0x18002c5b8`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002bfb0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002bfb0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002bf9d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002c02f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002bf9d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002c02f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002be46`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002be46`

## string_xrefs

- `0x18002beed`: `TeredoConfigurationChangeNotification`
- `0x18002bee3`: `onecoreuap\net\netio\iphlpsvc\service\rpcinterface.c`
- `0x18002bde3`: `TeredoCreateConsumerHandle`
- `0x18002be15`: `TeredoCreateConsumerHandle`
- `0x18002bec9`: `TeredoCreateConsumerHandle`
- `0x18002c064`: `TeredoCreateConsumerHandle`
- `0x18002bf03`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18002be68`: `TeredoCreateConsumerHandle caller not authorized 0x%x`

## pseudocode

```c
__int64 __fastcall TeredoCreateConsumerHandle(void *a1, int a2, __int64 *a3)
{
  char v6; // al
  int v8; // eax
  int v9; // ebx
  char v10; // r14
  char v11; // r15
  unsigned __int32 v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  int RpcCaller; // eax
  unsigned int v17; // esi
  unsigned int v18; // ebx
  __int64 *v19; // rdx
  unsigned int v20; // r14d
  __int64 v21; // rax
  __int64 v22; // rbx
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Source[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(Source, 0, 0x208u);
  v6 = IpHlpSvcEtwEnabled;
  v23 = 260;
  UnbiasedTime = 0;
  v24 = 0;
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x100) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED,
      L"TeredoCreateConsumerHandle");
    v6 = IpHlpSvcEtwEnabled;
  }
  if ( !a3 )
  {
    if ( v6 )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x200) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED,
          L"TeredoCreateConsumerHandle");
    }
    return 2147942487LL;
  }
  *a3 = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v8 = AuthorizeTeredoCtrlCaller(a1);
  v9 = v8;
  if ( v8 < 0 )
  {
    EventWriteError0(0x100000, L"TeredoCreateConsumerHandle caller not authorized 0x%x", (unsigned int)v8);
    return (unsigned int)v9;
  }
  v10 = 0;
  v11 = 0;
  v12 = _InterlockedIncrement((volatile signed __int32 *)&SecureSocketsListeners);
  EventWrite0(0x100000, L"Added SecureSockets listener. Count %u", v12);
  if ( v12 == 1 )
  {
    v9 = SetTeredoTypeIf(v14, v13, &v24);
    if ( v9 == -2147023649 )
    {
      v11 = 1;
    }
    else
    {
      if ( v9 < 0 )
      {
        TeredoFwDecrementSecureSocketsListeners();
        EventWriteLeaveEx(0x100000, L"TeredoCreateConsumerHandle");
        return (unsigned int)v9;
      }
      EventWrite0(
        0x40000,
        L"ReferenceService: ++%u (%hs) @ %ls:%u",
        ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
        "TeredoConfigurationChangeNotification",
        L"onecoreuap\\net\\netio\\iphlpsvc\\service\\rpcinterface.c",
        1043);
      while ( 1 )
      {
        v15 = g_Reference;
        if ( (g_Reference & 1) != 0 )
          break;
        if ( v15 == _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) )
        {
          TeredoConfigurationChangeNotification(0, (PVOID)3);
          break;
        }
      }
      v10 = 1;
    }
  }
  RpcCaller = GetRpcCaller(a1, a2, Source, &v23);
  v17 = RpcCaller;
  if ( RpcCaller < 0 )
  {
    EventWriteError0(0x100000, L"Increment failed to get Rpc caller 0x%x", (unsigned int)RpcCaller);
    _o_wcscpy_s(Source, 260, L"FailedToGetCaller");
    v18 = wcsnlen(Source, 0x104u) + 1;
  }
  else
  {
    EventWrite0(0x100000, L"%ws added at %lld", Source, UnbiasedTime);
    v18 = v23;
  }
  if ( !v11 )
  {
    if ( v10 )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 2) != 0 )
      {
        v19 = EVENT_IPHLPSVC_ETW_TEREDO_API_START;
LABEL_31:
        McTemplateU0z_EventWriteTransfer(MS_IPHLPSVC_ETW_PROVIDER_ID_Context, v19, Source);
      }
    }
    else if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 2) != 0 )
    {
      v19 = EVENT_IPHLPSVC_ETW_TEREDO_API_START_RUNNING;
      goto LABEL_31;
    }
  }
  v20 = v18;
  v21 = MALLOC(2LL * v18 + 16);
  v22 = v21;
  if ( v21 )
  {
    *(_DWORD *)v21 = v17;
    *(_QWORD *)(v21 + 8) = UnbiasedTime;
    *(_BYTE *)(v21 + 4) = v11;
    _o_wcscpy_s(v21 + 16, v20, Source);
    *a3 = v22;
  }
  else
  {
    EventWriteError0(0x100000, L"Failed to allocate client context");
  }
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x200) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED,
      L"TeredoCreateConsumerHandle");
  return v17;
}

```

## disassembly

```asm
0x18002bd70  push    rbp
0x18002bd72  push    rbx
0x18002bd73  push    rsi
0x18002bd74  push    r12
0x18002bd76  push    r13
0x18002bd78  push    r14
0x18002bd7a  push    r15
0x18002bd7c  lea     rbp, [rsp-160h]
0x18002bd84  sub     rsp, 260h
0x18002bd8b  mov     rax, cs:__security_cookie
0x18002bd92  xor     rax, rsp
0x18002bd95  mov     [rbp+190h+var_40], rax
0x18002bd9c  mov     r12, r8
0x18002bd9f  mov     r13d, edx
0x18002bda2  mov     rsi, rcx
0x18002bda5  xor     edx, edx; Val
0x18002bda7  mov     r8d, 208h; Size
0x18002bdad  lea     rcx, [rsp+290h+Source]; void *
0x18002bdb2  call    memset_0
0x18002bdb7  mov     al, cs:IpHlpSvcEtwEnabled
0x18002bdbd  mov     [rsp+290h+var_260], 104h
0x18002bdc5  mov     [rsp+290h+UnbiasedTime], 0
0x18002bdce  mov     [rsp+290h+var_25C], 0
0x18002bdd6  test    al, al
0x18002bdd8  jz      short loc_18002BE03
0x18002bdda  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 1
0x18002bde1  jz      short loc_18002BE03
0x18002bde3  lea     r8, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002bdea  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x18002bdf1  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002bdf8  call    McTemplateU0z_EventWriteTransfer
0x18002bdfd  mov     al, cs:IpHlpSvcEtwEnabled
0x18002be03  test    r12, r12
0x18002be06  jnz     short loc_18002BE39
0x18002be08  test    al, al
0x18002be0a  jz      short loc_18002BE2F
0x18002be0c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x18002be13  jz      short loc_18002BE2F
0x18002be15  lea     r8, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002be1c  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x18002be23  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002be2a  call    McTemplateU0z_EventWriteTransfer
0x18002be2f  mov     eax, 80070057h
0x18002be34  jmp     loc_18002C080
0x18002be39  lea     rcx, [rsp+290h+UnbiasedTime]; UnbiasedTime
0x18002be3e  mov     qword ptr [r12], 0
0x18002be46  call    cs:__imp_QueryUnbiasedInterruptTime
0x18002be4d  nop     dword ptr [rax+rax+00h]
0x18002be52  mov     rcx, rsi
0x18002be55  call    AuthorizeTeredoCtrlCaller
0x18002be5a  mov     ebx, eax
0x18002be5c  mov     ecx, 100000h
0x18002be61  test    eax, eax
0x18002be63  jns     short loc_18002BE7B
0x18002be65  mov     r8d, eax
0x18002be68  lea     rdx, aTeredocreateco_0; "TeredoCreateConsumerHandle caller not a"...
0x18002be6f  call    EventWriteError0
0x18002be74  mov     eax, ebx
0x18002be76  jmp     loc_18002C080
0x18002be7b  xor     r14b, r14b
0x18002be7e  mov     ebx, 1
0x18002be83  xor     r15b, r15b
0x18002be86  lock xadd cs:?SecureSocketsListeners@@3KA, ebx; ulong SecureSocketsListeners
0x18002be8e  inc     ebx
0x18002be90  lea     rdx, aAddedSecuresoc; "Added SecureSockets listener. Count %u"
0x18002be97  mov     r8d, ebx
0x18002be9a  call    EventWrite0
0x18002be9f  cmp     ebx, 1
0x18002bea2  jnz     loc_18002BF3F
0x18002bea8  lea     r8, [rsp+290h+var_25C]
0x18002bead  call    SetTeredoTypeIf
0x18002beb2  mov     ebx, eax
0x18002beb4  cmp     eax, 800704DFh
0x18002beb9  jnz     short loc_18002BEC0
0x18002bebb  mov     r15b, 1
0x18002bebe  jmp     short loc_18002BF3F
0x18002bec0  test    ebx, ebx
0x18002bec2  jns     short loc_18002BEDC
0x18002bec4  call    TeredoFwDecrementSecureSocketsListeners
0x18002bec9  lea     rdx, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002bed0  mov     ecx, 100000h
0x18002bed5  call    EventWriteLeaveEx
0x18002beda  jmp     short loc_18002BE74
0x18002bedc  mov     r8d, cs:g_Reference
0x18002bee3  lea     rax, aOnecoreuapNetN_0; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002beea  shr     r8d, 1
0x18002beed  lea     r9, aTeredoconfigur; "TeredoConfigurationChangeNotification"
0x18002bef4  and     r8d, 3FFFFFFFh
0x18002befb  mov     [rsp+290h+var_268], 413h
0x18002bf03  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18002bf0a  mov     [rsp+290h+var_270], rax
0x18002bf0f  mov     ecx, 40000h
0x18002bf14  call    EventWrite0
0x18002bf19  mov     eax, cs:g_Reference
0x18002bf1f  test    al, 1
0x18002bf21  jnz     short loc_18002BF3C
0x18002bf23  lea     ecx, [rax+2]
0x18002bf26  lock cmpxchg cs:g_Reference, ecx
0x18002bf2e  jnz     short loc_18002BF19
0x18002bf30  mov     edx, 3; Context
0x18002bf35  xor     ecx, ecx; Instance
0x18002bf37  call    TeredoConfigurationChangeNotification
0x18002bf3c  mov     r14b, 1
0x18002bf3f  lea     r9, [rsp+290h+var_260]
0x18002bf44  mov     edx, r13d
0x18002bf47  lea     r8, [rsp+290h+Source]
0x18002bf4c  mov     rcx, rsi
0x18002bf4f  call    GetRpcCaller
0x18002bf54  mov     esi, eax
0x18002bf56  mov     ecx, 100000h
0x18002bf5b  test    eax, eax
0x18002bf5d  js      short loc_18002BF7B
0x18002bf5f  mov     r9, [rsp+290h+UnbiasedTime]
0x18002bf64  lea     r8, [rsp+290h+Source]
0x18002bf69  lea     rdx, aWsAddedAtLld; "%ws added at %lld"
0x18002bf70  call    EventWrite0
0x18002bf75  mov     ebx, [rsp+290h+var_260]
0x18002bf79  jmp     short loc_18002BFBF
0x18002bf7b  mov     r8d, esi
0x18002bf7e  lea     rdx, aIncrementFaile; "Increment failed to get Rpc caller 0x%x"
0x18002bf85  call    EventWriteError0
0x18002bf8a  mov     ebx, 104h
0x18002bf8f  lea     r8, aFailedtogetcal; "FailedToGetCaller"
0x18002bf96  mov     edx, ebx
0x18002bf98  lea     rcx, [rsp+290h+Source]
0x18002bf9d  call    cs:__imp__o_wcscpy_s
0x18002bfa4  nop     dword ptr [rax+rax+00h]
0x18002bfa9  mov     edx, ebx; MaxCount
0x18002bfab  lea     rcx, [rsp+290h+Source]; Source
0x18002bfb0  call    cs:__imp_wcsnlen
0x18002bfb7  nop     dword ptr [rax+rax+00h]
0x18002bfbc  lea     ebx, [rax+1]
0x18002bfbf  test    r15b, r15b
0x18002bfc2  jnz     short loc_18002BFFC
0x18002bfc4  test    r14b, r14b
0x18002bfc7  jz      short loc_18002BFDB
0x18002bfc9  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 2
0x18002bfd0  jz      short loc_18002BFFC
0x18002bfd2  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_API_START
0x18002bfd9  jmp     short loc_18002BFEB
0x18002bfdb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 2
0x18002bfe2  jz      short loc_18002BFFC
0x18002bfe4  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_API_START_RUNNING
0x18002bfeb  lea     r8, [rsp+290h+Source]
0x18002bff0  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002bff7  call    McTemplateU0z_EventWriteTransfer
0x18002bffc  mov     r14d, ebx
0x18002bfff  lea     rcx, ds:10h[r14*2]; dwBytes
0x18002c007  call    MALLOC
0x18002c00c  mov     rbx, rax
0x18002c00f  test    rax, rax
0x18002c012  jz      short loc_18002C041
0x18002c014  mov     [rax], esi
0x18002c016  lea     r8, [rsp+290h+Source]
0x18002c01b  mov     rcx, [rsp+290h+UnbiasedTime]
0x18002c020  mov     edx, r14d
0x18002c023  mov     [rax+8], rcx
0x18002c027  lea     rcx, [rax+10h]
0x18002c02b  mov     [rax+4], r15b
0x18002c02f  call    cs:__imp__o_wcscpy_s
0x18002c036  nop     dword ptr [rax+rax+00h]
0x18002c03b  mov     [r12], rbx
0x18002c03f  jmp     short loc_18002C052
0x18002c041  lea     rdx, aFailedToAlloca; "Failed to allocate client context"
0x18002c048  mov     ecx, 100000h
0x18002c04d  call    EventWriteError0
0x18002c052  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18002c059  jz      short loc_18002C07E
0x18002c05b  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x18002c062  jz      short loc_18002C07E
0x18002c064  lea     r8, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002c06b  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x18002c072  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002c079  call    McTemplateU0z_EventWriteTransfer
0x18002c07e  mov     eax, esi
0x18002c080  mov     rcx, [rbp+190h+var_40]
0x18002c087  xor     rcx, rsp; StackCookie
0x18002c08a  call    __security_check_cookie
0x18002c08f  add     rsp, 260h
0x18002c096  pop     r15
0x18002c098  pop     r14
0x18002c09a  pop     r13
0x18002c09c  pop     r12
0x18002c09e  pop     rsi
0x18002c09f  pop     rbx
0x18002c0a0  pop     rbp
0x18002c0a1  retn
```
