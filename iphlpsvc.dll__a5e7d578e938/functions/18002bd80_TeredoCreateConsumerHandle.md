# TeredoCreateConsumerHandle

- ea: `0x18002bd80`
- end: `0x18002c0b3`
- name: `TeredoCreateConsumerHandle`
- size: `819`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000483c`
- `0x180004de0`
- `0x180009010`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800190f0`
- `0x180024250`
- `0x18002bd80`
- `0x18002c0bc`
- `0x18002c278`
- `0x18002c5c8`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002bfc0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002bfc0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002bfad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002c03f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002bfad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002c03f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002be56`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002be56`

## string_xrefs

- `0x18002befd`: `TeredoConfigurationChangeNotification`
- `0x18002bef3`: `onecoreuap\net\netio\iphlpsvc\service\rpcinterface.c`
- `0x18002bdf3`: `TeredoCreateConsumerHandle`
- `0x18002be25`: `TeredoCreateConsumerHandle`
- `0x18002bed9`: `TeredoCreateConsumerHandle`
- `0x18002c074`: `TeredoCreateConsumerHandle`
- `0x18002bf13`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18002be78`: `TeredoCreateConsumerHandle caller not authorized 0x%x`

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
  DWORD v18; // ebx
  __int64 *v19; // rdx
  DWORD v20; // r14d
  __int64 v21; // rax
  __int64 v22; // rbx
  DWORD v23; // [rsp+30h] [rbp-D0h] BYREF
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
0x18002bd80  push    rbp
0x18002bd82  push    rbx
0x18002bd83  push    rsi
0x18002bd84  push    r12
0x18002bd86  push    r13
0x18002bd88  push    r14
0x18002bd8a  push    r15
0x18002bd8c  lea     rbp, [rsp-160h]
0x18002bd94  sub     rsp, 260h
0x18002bd9b  mov     rax, cs:__security_cookie
0x18002bda2  xor     rax, rsp
0x18002bda5  mov     [rbp+190h+var_40], rax
0x18002bdac  mov     r12, r8
0x18002bdaf  mov     r13d, edx
0x18002bdb2  mov     rsi, rcx
0x18002bdb5  xor     edx, edx; Val
0x18002bdb7  mov     r8d, 208h; Size
0x18002bdbd  lea     rcx, [rsp+290h+Source]; void *
0x18002bdc2  call    memset_0
0x18002bdc7  mov     al, cs:IpHlpSvcEtwEnabled
0x18002bdcd  mov     [rsp+290h+var_260], 104h
0x18002bdd5  mov     [rsp+290h+UnbiasedTime], 0
0x18002bdde  mov     [rsp+290h+var_25C], 0
0x18002bde6  test    al, al
0x18002bde8  jz      short loc_18002BE13
0x18002bdea  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 1
0x18002bdf1  jz      short loc_18002BE13
0x18002bdf3  lea     r8, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002bdfa  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x18002be01  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002be08  call    McTemplateU0z_EventWriteTransfer
0x18002be0d  mov     al, cs:IpHlpSvcEtwEnabled
0x18002be13  test    r12, r12
0x18002be16  jnz     short loc_18002BE49
0x18002be18  test    al, al
0x18002be1a  jz      short loc_18002BE3F
0x18002be1c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x18002be23  jz      short loc_18002BE3F
0x18002be25  lea     r8, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002be2c  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x18002be33  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002be3a  call    McTemplateU0z_EventWriteTransfer
0x18002be3f  mov     eax, 80070057h
0x18002be44  jmp     loc_18002C090
0x18002be49  lea     rcx, [rsp+290h+UnbiasedTime]; UnbiasedTime
0x18002be4e  mov     qword ptr [r12], 0
0x18002be56  call    cs:__imp_QueryUnbiasedInterruptTime
0x18002be5d  nop     dword ptr [rax+rax+00h]
0x18002be62  mov     rcx, rsi
0x18002be65  call    AuthorizeTeredoCtrlCaller
0x18002be6a  mov     ebx, eax
0x18002be6c  mov     ecx, 100000h
0x18002be71  test    eax, eax
0x18002be73  jns     short loc_18002BE8B
0x18002be75  mov     r8d, eax
0x18002be78  lea     rdx, aTeredocreateco_0; "TeredoCreateConsumerHandle caller not a"...
0x18002be7f  call    EventWriteError0
0x18002be84  mov     eax, ebx
0x18002be86  jmp     loc_18002C090
0x18002be8b  xor     r14b, r14b
0x18002be8e  mov     ebx, 1
0x18002be93  xor     r15b, r15b
0x18002be96  lock xadd cs:?SecureSocketsListeners@@3KA, ebx; ulong SecureSocketsListeners
0x18002be9e  inc     ebx
0x18002bea0  lea     rdx, aAddedSecuresoc; "Added SecureSockets listener. Count %u"
0x18002bea7  mov     r8d, ebx
0x18002beaa  call    EventWrite0
0x18002beaf  cmp     ebx, 1
0x18002beb2  jnz     loc_18002BF4F
0x18002beb8  lea     r8, [rsp+290h+var_25C]
0x18002bebd  call    SetTeredoTypeIf
0x18002bec2  mov     ebx, eax
0x18002bec4  cmp     eax, 800704DFh
0x18002bec9  jnz     short loc_18002BED0
0x18002becb  mov     r15b, 1
0x18002bece  jmp     short loc_18002BF4F
0x18002bed0  test    ebx, ebx
0x18002bed2  jns     short loc_18002BEEC
0x18002bed4  call    TeredoFwDecrementSecureSocketsListeners
0x18002bed9  lea     rdx, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002bee0  mov     ecx, 100000h
0x18002bee5  call    EventWriteLeaveEx
0x18002beea  jmp     short loc_18002BE84
0x18002beec  mov     r8d, cs:g_Reference
0x18002bef3  lea     rax, aOnecoreuapNetN_0; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002befa  shr     r8d, 1
0x18002befd  lea     r9, aTeredoconfigur; "TeredoConfigurationChangeNotification"
0x18002bf04  and     r8d, 3FFFFFFFh
0x18002bf0b  mov     [rsp+290h+var_268], 413h
0x18002bf13  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18002bf1a  mov     [rsp+290h+var_270], rax
0x18002bf1f  mov     ecx, 40000h
0x18002bf24  call    EventWrite0
0x18002bf29  mov     eax, cs:g_Reference
0x18002bf2f  test    al, 1
0x18002bf31  jnz     short loc_18002BF4C
0x18002bf33  lea     ecx, [rax+2]
0x18002bf36  lock cmpxchg cs:g_Reference, ecx
0x18002bf3e  jnz     short loc_18002BF29
0x18002bf40  mov     edx, 3; Context
0x18002bf45  xor     ecx, ecx; Instance
0x18002bf47  call    TeredoConfigurationChangeNotification
0x18002bf4c  mov     r14b, 1
0x18002bf4f  lea     r9, [rsp+290h+var_260]
0x18002bf54  mov     edx, r13d
0x18002bf57  lea     r8, [rsp+290h+Source]
0x18002bf5c  mov     rcx, rsi
0x18002bf5f  call    GetRpcCaller
0x18002bf64  mov     esi, eax
0x18002bf66  mov     ecx, 100000h
0x18002bf6b  test    eax, eax
0x18002bf6d  js      short loc_18002BF8B
0x18002bf6f  mov     r9, [rsp+290h+UnbiasedTime]
0x18002bf74  lea     r8, [rsp+290h+Source]
0x18002bf79  lea     rdx, aWsAddedAtLld; "%ws added at %lld"
0x18002bf80  call    EventWrite0
0x18002bf85  mov     ebx, [rsp+290h+var_260]
0x18002bf89  jmp     short loc_18002BFCF
0x18002bf8b  mov     r8d, esi
0x18002bf8e  lea     rdx, aIncrementFaile; "Increment failed to get Rpc caller 0x%x"
0x18002bf95  call    EventWriteError0
0x18002bf9a  mov     ebx, 104h
0x18002bf9f  lea     r8, aFailedtogetcal; "FailedToGetCaller"
0x18002bfa6  mov     edx, ebx
0x18002bfa8  lea     rcx, [rsp+290h+Source]
0x18002bfad  call    cs:__imp__o_wcscpy_s
0x18002bfb4  nop     dword ptr [rax+rax+00h]
0x18002bfb9  mov     edx, ebx; MaxCount
0x18002bfbb  lea     rcx, [rsp+290h+Source]; Source
0x18002bfc0  call    cs:__imp_wcsnlen
0x18002bfc7  nop     dword ptr [rax+rax+00h]
0x18002bfcc  lea     ebx, [rax+1]
0x18002bfcf  test    r15b, r15b
0x18002bfd2  jnz     short loc_18002C00C
0x18002bfd4  test    r14b, r14b
0x18002bfd7  jz      short loc_18002BFEB
0x18002bfd9  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 2
0x18002bfe0  jz      short loc_18002C00C
0x18002bfe2  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_API_START
0x18002bfe9  jmp     short loc_18002BFFB
0x18002bfeb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 2
0x18002bff2  jz      short loc_18002C00C
0x18002bff4  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_API_START_RUNNING
0x18002bffb  lea     r8, [rsp+290h+Source]
0x18002c000  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002c007  call    McTemplateU0z_EventWriteTransfer
0x18002c00c  mov     r14d, ebx
0x18002c00f  lea     rcx, ds:10h[r14*2]; dwBytes
0x18002c017  call    MALLOC
0x18002c01c  mov     rbx, rax
0x18002c01f  test    rax, rax
0x18002c022  jz      short loc_18002C051
0x18002c024  mov     [rax], esi
0x18002c026  lea     r8, [rsp+290h+Source]
0x18002c02b  mov     rcx, [rsp+290h+UnbiasedTime]
0x18002c030  mov     edx, r14d
0x18002c033  mov     [rax+8], rcx
0x18002c037  lea     rcx, [rax+10h]
0x18002c03b  mov     [rax+4], r15b
0x18002c03f  call    cs:__imp__o_wcscpy_s
0x18002c046  nop     dword ptr [rax+rax+00h]
0x18002c04b  mov     [r12], rbx
0x18002c04f  jmp     short loc_18002C062
0x18002c051  lea     rdx, aFailedToAlloca; "Failed to allocate client context"
0x18002c058  mov     ecx, 100000h
0x18002c05d  call    EventWriteError0
0x18002c062  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18002c069  jz      short loc_18002C08E
0x18002c06b  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x18002c072  jz      short loc_18002C08E
0x18002c074  lea     r8, aTeredocreateco; "TeredoCreateConsumerHandle"
0x18002c07b  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x18002c082  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002c089  call    McTemplateU0z_EventWriteTransfer
0x18002c08e  mov     eax, esi
0x18002c090  mov     rcx, [rbp+190h+var_40]
0x18002c097  xor     rcx, rsp; StackCookie
0x18002c09a  call    __security_check_cookie
0x18002c09f  add     rsp, 260h
0x18002c0a6  pop     r15
0x18002c0a8  pop     r14
0x18002c0aa  pop     r13
0x18002c0ac  pop     r12
0x18002c0ae  pop     rsi
0x18002c0af  pop     rbx
0x18002c0b0  pop     rbp
0x18002c0b1  retn
```
