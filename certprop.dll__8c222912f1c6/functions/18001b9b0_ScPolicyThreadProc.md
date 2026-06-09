# ScPolicyThreadProc

- ea: `0x18001b9b0`
- end: `0x18001be47`
- name: `ScPolicyThreadProc`
- size: `1175`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004600`
- `0x180016090`
- `0x180016a66`
- `0x180018bb4`
- `0x180018d78`
- `0x180018e7c`
- `0x18001b438`
- `0x18001b9b0`
- `0x18001be50`
- `0x180021930`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001bd3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001bd3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001babe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001babe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bb6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bdad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bb6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bdad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ba8a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ba8a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001ba5a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001ba5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bbcd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bce4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bbcd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bce4`
- `ntdll!RtlGetActiveConsoleId` at `0x18001bc39`
- `ntdll!RtlGetActiveConsoleId` at `0x18001bc39`
- `WinSCard!SCardReleaseStartedEvent` at `0x18001bbc7`
- `WinSCard!SCardReleaseStartedEvent` at `0x18001bcd7`
- `WinSCard!SCardReleaseStartedEvent` at `0x18001bbc7`
- `WinSCard!SCardReleaseStartedEvent` at `0x18001bcd7`
- `WinSCard!SCardReleaseContext` at `0x18001bb74`
- `WinSCard!SCardReleaseContext` at `0x18001bb74`
- `WinSCard!SCardEstablishContext` at `0x18001bab3`
- `WinSCard!SCardEstablishContext` at `0x18001bab3`
- `WinSCard!SCardAccessStartedEvent` at `0x18001ba73`
- `WinSCard!SCardAccessStartedEvent` at `0x18001ba73`
- `WinSCard!SCardGetStatusChangeW` at `0x18001bb45`
- `WinSCard!SCardGetStatusChangeW` at `0x18001bb45`
- `WMsgAPI!WmsgSendMessage` at `0x18001bc72`
- `WMsgAPI!WmsgSendMessage` at `0x18001bc72`
- `WTSAPI32!WTSLogoffSession` at `0x18001bc5b`
- `WTSAPI32!WTSLogoffSession` at `0x18001bc5b`
- `WTSAPI32!WTSDisconnectSession` at `0x18001bc4b`
- `WTSAPI32!WTSDisconnectSession` at `0x18001bc4b`

## pseudocode

```c
void __fastcall ScPolicyThreadProc(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  _QWORD *v3; // r13
  int v5; // r12d
  LONG v6; // r15d
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // r9d
  int PolicyOption; // edi
  HANDLE v11; // rax
  SCARDCONTEXT *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // r9d
  char v16; // r14
  __int64 v17; // rcx
  int v18; // ebx
  int v19; // r9d
  __int64 v20; // rcx
  int v21; // r9d
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // edx
  __int64 v25; // rcx
  int v26; // [rsp+40h] [rbp-39h] BYREF
  int v27; // [rsp+44h] [rbp-35h] BYREF
  PTP_WORK pwk; // [rsp+48h] [rbp-31h]
  $B80B7D01E79FADDB4AAC58DE22BC823F rgReaderStates; // [rsp+50h] [rbp-29h] BYREF

  v3 = 0;
  pwk = Work;
  v27 = 0;
  memset_0(&rgReaderStates, 0, sizeof(rgReaderStates));
  v5 = *((_DWORD *)Context + 13);
  v6 = 0;
  v26 = 0;
  WppTraceIndent(v7, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v8, v9, *((_DWORD *)Context + 13), *((_DWORD *)Context + 19));
  }
  memset_0(&rgReaderStates, 0, sizeof(rgReaderStates));
  if ( !SetThreadToken(0, *((HANDLE *)Context + 7)) )
    goto LABEL_6;
  LOBYTE(PolicyOption) = 0;
  v11 = SCardAccessStartedEvent();
  if ( !v11 )
    goto LABEL_39;
  if ( WaitForSingleObject(v11, 0xEA60u) )
    goto LABEL_21;
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 8));
  v12 = (SCARDCONTEXT *)(Context + 80);
  PolicyOption = SCardEstablishContext(0, 0, 0, (LPSCARDCONTEXT)Context + 10);
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 8));
  if ( PolicyOption )
  {
    WppTraceIndent(v13, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
        WPP_pszIndent,
        PolicyOption);
    }
LABEL_21:
    PolicyOption = ScPolicyGetPolicyOption(&v26);
    if ( !PolicyOption )
    {
      SCardReleaseStartedEvent();
      if ( !RevertToSelf() )
      {
        WppTraceIndent(v14, (unsigned int)(PolicyOption + 2));
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            PolicyOption + 12,
            (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
            v15,
            v5);
        }
LABEL_6:
        LOBYTE(PolicyOption) = GetLastError();
        goto LABEL_44;
      }
      v16 = v26;
      if ( v26 != 1 )
      {
        v17 = (unsigned int)(v26 - 2);
        if ( v26 == 2 )
        {
          WTSLogoffSession(0, *((_DWORD *)Context + 13), 0);
          goto LABEL_34;
        }
        if ( v26 != 3 )
        {
LABEL_34:
          WppTraceIndent(v17, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
          {
            WPP_SF_sddD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
              v19,
              v16,
              v5,
              rgReaderStates.dwEventState);
          }
          goto LABEL_44;
        }
        v18 = *((_DWORD *)Context + 13);
        if ( (unsigned int)RtlGetActiveConsoleId() != v18 )
        {
          WTSDisconnectSession(0, *((_DWORD *)Context + 13), 0);
          goto LABEL_34;
        }
      }
      LOBYTE(PolicyOption) = WmsgSendMessage(*((unsigned int *)Context + 13), 1027, 0, &v27);
      goto LABEL_34;
    }
    goto LABEL_38;
  }
  rgReaderStates.dwCurrentState = *((_DWORD *)Context + 19) | 0x120;
  rgReaderStates.szReader = (LPCWSTR)*((_QWORD *)Context + 8);
  do
  {
    v6 = SCardGetStatusChangeW(*v12, 0xFFFFFFFF, &rgReaderStates, 1u);
    if ( v6 )
      break;
    rgReaderStates.dwCurrentState = rgReaderStates.dwEventState;
    if ( (rgReaderStates.dwEventState & 0x20) == 0 )
      break;
  }
  while ( *((_DWORD *)Context + 19) == (rgReaderStates.dwEventState & 0xFFFF0000) );
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 8));
  SCardReleaseContext(*v12);
  *v12 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 8));
  if ( v6 != -2146435070 && v6 != -2146435054 && v6 != -2146435043 )
    goto LABEL_21;
LABEL_38:
  SCardReleaseStartedEvent();
LABEL_39:
  if ( !RevertToSelf() )
  {
    WppTraceIndent(v20, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
        v21,
        v5);
    }
  }
LABEL_44:
  if ( pwk )
    CloseThreadpoolWork(pwk);
  EnterCriticalSection(&g_csScPolicyList);
  v22 = g_pScPolicyList;
  if ( g_pScPolicyList )
  {
    while ( 1 )
    {
      v23 = *(_QWORD *)v22;
      if ( v5 == *(_DWORD *)(v22 + 52) )
        break;
      v3 = (_QWORD *)v22;
      v22 = *(_QWORD *)v22;
      if ( !v23 )
        goto LABEL_53;
    }
    if ( v3 )
      *v3 = v23;
    else
      g_pScPolicyList = *(_QWORD *)v22;
  }
LABEL_53:
  v24 = *((_DWORD *)Context + 18);
  if ( ((v24 - 2) & 0xFFFFFFFD) != 0 && (v6 != -2146435054 || v24) )
  {
    ScPolicyFreeListNode(Context);
  }
  else
  {
    EnterCriticalSection(&g_csInactiveScPolicyList);
    *(_QWORD *)Context = g_pInactiveScPolicyList;
    g_pInactiveScPolicyList = (__int64)Context;
    LeaveCriticalSection(&g_csInactiveScPolicyList);
  }
  LeaveCriticalSection(&g_csScPolicyList);
  WppTraceIndent(v25, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
      WPP_pszIndent,
      PolicyOption);
  }
}

```

## disassembly

```asm
0x18001b9b0  mov     [rsp-8+arg_0], rbx
0x18001b9b5  push    rbp
0x18001b9b6  push    rsi
0x18001b9b7  push    rdi
0x18001b9b8  push    r12
0x18001b9ba  push    r13
0x18001b9bc  push    r14
0x18001b9be  push    r15
0x18001b9c0  lea     rbp, [rsp-27h]
0x18001b9c5  sub     rsp, 0A0h
0x18001b9cc  mov     rax, cs:__security_cookie
0x18001b9d3  xor     rax, rsp
0x18001b9d6  mov     [rbp+57h+var_40], rax
0x18001b9da  xor     r13d, r13d
0x18001b9dd  mov     [rbp+57h+pwk], r8
0x18001b9e1  mov     rsi, rdx
0x18001b9e4  mov     [rbp+57h+var_8C], r13d
0x18001b9e8  xor     edx, edx; Val
0x18001b9ea  lea     rcx, [rbp+57h+rgReaderStates]; void *
0x18001b9ee  lea     ebx, [r13+40h]
0x18001b9f2  mov     r8d, ebx; Size
0x18001b9f5  call    memset_0
0x18001b9fa  mov     r12d, [rsi+34h]
0x18001b9fe  lea     edx, [rbx-3Eh]
0x18001ba01  xor     r15d, r15d
0x18001ba04  mov     [rbp+57h+var_90], r13d
0x18001ba08  call    WppTraceIndent
0x18001ba0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba14  lea     r14, WPP_GLOBAL_Control
0x18001ba1b  cmp     rcx, r14
0x18001ba1e  jz      short loc_18001BA46
0x18001ba20  test    byte ptr [rcx+1Ch], 1
0x18001ba24  jz      short loc_18001BA46
0x18001ba26  cmp     byte ptr [rcx+19h], 4
0x18001ba2a  jb      short loc_18001BA46
0x18001ba2c  mov     eax, [rsi+4Ch]
0x18001ba2f  lea     edx, [rbx-36h]
0x18001ba32  mov     rcx, [rcx+10h]
0x18001ba36  mov     [rsp+0D0h+var_A8], eax
0x18001ba3a  mov     eax, [rsi+34h]
0x18001ba3d  mov     [rsp+0D0h+var_B0], eax
0x18001ba41  call    WPP_SF_sdD
0x18001ba46  mov     r8, rbx; Size
0x18001ba49  lea     rcx, [rbp+57h+rgReaderStates]; void *
0x18001ba4d  xor     edx, edx; Val
0x18001ba4f  call    memset_0
0x18001ba54  mov     rdx, [rsi+38h]; Token
0x18001ba58  xor     ecx, ecx; Thread
0x18001ba5a  call    cs:__imp_SetThreadToken
0x18001ba60  test    eax, eax
0x18001ba62  jnz     short loc_18001BA71
0x18001ba64  call    cs:__imp_GetLastError
0x18001ba6a  mov     edi, eax
0x18001ba6c  jmp     loc_18001BD28
0x18001ba71  xor     edi, edi
0x18001ba73  call    cs:__imp_SCardAccessStartedEvent
0x18001ba79  test    rax, rax
0x18001ba7c  jz      loc_18001BCE4
0x18001ba82  mov     edx, 0EA60h; dwMilliseconds
0x18001ba87  mov     rcx, rax; hHandle
0x18001ba8a  call    cs:__imp_WaitForSingleObject
0x18001ba90  test    eax, eax
0x18001ba92  jnz     loc_18001BBB4
0x18001ba98  lea     r14, [rsi+8]
0x18001ba9c  mov     rcx, r14; lpCriticalSection
0x18001ba9f  call    cs:__imp_EnterCriticalSection
0x18001baa5  lea     rbx, [rsi+50h]
0x18001baa9  xor     r8d, r8d; pvReserved2
0x18001baac  mov     r9, rbx; phContext
0x18001baaf  xor     edx, edx; pvReserved1
0x18001bab1  xor     ecx, ecx; dwScope
0x18001bab3  call    cs:__imp_SCardEstablishContext
0x18001bab9  mov     rcx, r14; lpCriticalSection
0x18001babc  mov     edi, eax
0x18001babe  call    cs:__imp_LeaveCriticalSection
0x18001bac4  test    edi, edi
0x18001bac6  jz      short loc_18001BB22
0x18001bac8  mov     edx, 2
0x18001bacd  call    WppTraceIndent
0x18001bad2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bad9  lea     r14, WPP_GLOBAL_Control
0x18001bae0  cmp     rcx, r14
0x18001bae3  jz      loc_18001BBB4
0x18001bae9  test    byte ptr [rcx+1Ch], 1
0x18001baed  jz      loc_18001BBB4
0x18001baf3  cmp     byte ptr [rcx+19h], 4
0x18001baf7  jb      loc_18001BBB4
0x18001bafd  mov     r9, cs:WPP_pszIndent
0x18001bb04  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001bb0b  mov     rcx, [rcx+10h]
0x18001bb0f  mov     edx, 0Bh
0x18001bb14  mov     [rsp+0D0h+var_B0], edi
0x18001bb18  call    WPP_SF_sD
0x18001bb1d  jmp     loc_18001BBB4
0x18001bb22  mov     eax, [rsi+4Ch]
0x18001bb25  or      eax, 120h
0x18001bb2a  mov     [rbp+57h+rgReaderStates.dwCurrentState], eax
0x18001bb2d  mov     rax, [rsi+40h]
0x18001bb31  mov     [rbp+57h+rgReaderStates.szReader], rax
0x18001bb35  mov     rcx, [rbx]; hContext
0x18001bb38  lea     r8, [rbp+57h+rgReaderStates]; rgReaderStates
0x18001bb3c  mov     r9d, 1; cReaders
0x18001bb42  or      edx, 0FFFFFFFFh; dwTimeout
0x18001bb45  call    cs:__imp_SCardGetStatusChangeW
0x18001bb4b  mov     r15d, eax
0x18001bb4e  test    eax, eax
0x18001bb50  jnz     short loc_18001BB68
0x18001bb52  mov     ecx, [rbp+57h+rgReaderStates.dwEventState]
0x18001bb55  mov     [rbp+57h+rgReaderStates.dwCurrentState], ecx
0x18001bb58  test    cl, 20h
0x18001bb5b  jz      short loc_18001BB68
0x18001bb5d  and     ecx, 0FFFF0000h
0x18001bb63  cmp     [rsi+4Ch], ecx
0x18001bb66  jz      short loc_18001BB35
0x18001bb68  mov     rcx, r14; lpCriticalSection
0x18001bb6b  call    cs:__imp_EnterCriticalSection
0x18001bb71  mov     rcx, [rbx]; hContext
0x18001bb74  call    cs:__imp_SCardReleaseContext
0x18001bb7a  mov     rcx, r14; lpCriticalSection
0x18001bb7d  mov     [rbx], r13
0x18001bb80  call    cs:__imp_LeaveCriticalSection
0x18001bb86  cmp     r15d, 80100002h
0x18001bb8d  jz      loc_18001BCD7
0x18001bb93  cmp     r15d, 80100012h
0x18001bb9a  jz      loc_18001BCD7
0x18001bba0  cmp     r15d, 8010001Dh
0x18001bba7  jz      loc_18001BCD7
0x18001bbad  lea     r14, WPP_GLOBAL_Control
0x18001bbb4  lea     rcx, [rbp+57h+var_90]
0x18001bbb8  call    ScPolicyGetPolicyOption
0x18001bbbd  mov     edi, eax
0x18001bbbf  test    eax, eax
0x18001bbc1  jnz     loc_18001BCD7
0x18001bbc7  call    cs:__imp_SCardReleaseStartedEvent
0x18001bbcd  call    cs:__imp_RevertToSelf
0x18001bbd3  test    eax, eax
0x18001bbd5  jnz     short loc_18001BC20
0x18001bbd7  lea     edx, [rdi+2]
0x18001bbda  call    WppTraceIndent
0x18001bbdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbe6  cmp     rcx, r14
0x18001bbe9  jz      loc_18001BA64
0x18001bbef  test    byte ptr [rcx+1Ch], 1
0x18001bbf3  jz      loc_18001BA64
0x18001bbf9  cmp     byte ptr [rcx+19h], 2
0x18001bbfd  jb      loc_18001BA64
0x18001bc03  mov     rcx, [rcx+10h]
0x18001bc07  lea     edx, [rdi+0Ch]
0x18001bc0a  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001bc11  mov     [rsp+0D0h+var_B0], r12d
0x18001bc16  call    WPP_SF_sd
0x18001bc1b  jmp     loc_18001BA64
0x18001bc20  mov     r14d, [rbp+57h+var_90]
0x18001bc24  mov     ecx, r14d
0x18001bc27  sub     ecx, 1
0x18001bc2a  jz      short loc_18001BC63
0x18001bc2c  sub     ecx, 1
0x18001bc2f  jz      short loc_18001BC53
0x18001bc31  cmp     ecx, 1
0x18001bc34  jnz     short loc_18001BC7A
0x18001bc36  mov     ebx, [rsi+34h]
0x18001bc39  call    cs:__imp_RtlGetActiveConsoleId
0x18001bc3f  xor     r8d, r8d; bWait
0x18001bc42  cmp     eax, ebx
0x18001bc44  jz      short loc_18001BC66
0x18001bc46  mov     edx, [rsi+34h]; SessionId
0x18001bc49  xor     ecx, ecx; hServer
0x18001bc4b  call    cs:__imp_WTSDisconnectSession
0x18001bc51  jmp     short loc_18001BC7A
0x18001bc53  mov     edx, [rsi+34h]; SessionId
0x18001bc56  xor     r8d, r8d; bWait
0x18001bc59  xor     ecx, ecx; hServer
0x18001bc5b  call    cs:__imp_WTSLogoffSession
0x18001bc61  jmp     short loc_18001BC7A
0x18001bc63  xor     r8d, r8d
0x18001bc66  mov     ecx, [rsi+34h]
0x18001bc69  lea     r9, [rbp+57h+var_8C]
0x18001bc6d  mov     edx, 403h
0x18001bc72  call    cs:__imp_WmsgSendMessage
0x18001bc78  mov     edi, eax
0x18001bc7a  mov     edx, 2
0x18001bc7f  call    WppTraceIndent
0x18001bc84  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc8b  lea     rbx, WPP_GLOBAL_Control
0x18001bc92  cmp     rcx, rbx
0x18001bc95  jz      loc_18001BD2F
0x18001bc9b  test    byte ptr [rcx+1Ch], 1
0x18001bc9f  jz      loc_18001BD2F
0x18001bca5  cmp     byte ptr [rcx+19h], 4
0x18001bca9  jb      loc_18001BD2F
0x18001bcaf  mov     eax, [rbp+57h+rgReaderStates.dwEventState]
0x18001bcb2  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001bcb9  mov     rcx, [rcx+10h]
0x18001bcbd  mov     edx, 0Dh
0x18001bcc2  mov     [rsp+0D0h+var_A0], eax
0x18001bcc6  mov     [rsp+0D0h+var_A8], r12d
0x18001bccb  mov     [rsp+0D0h+var_B0], r14d
0x18001bcd0  call    WPP_SF_sddD
0x18001bcd5  jmp     short loc_18001BD2F
0x18001bcd7  call    cs:__imp_SCardReleaseStartedEvent
0x18001bcdd  lea     r14, WPP_GLOBAL_Control
0x18001bce4  call    cs:__imp_RevertToSelf
0x18001bcea  test    eax, eax
0x18001bcec  jnz     short loc_18001BD28
0x18001bcee  lea     edx, [rax+2]
0x18001bcf1  call    WppTraceIndent
0x18001bcf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcfd  cmp     rcx, r14
0x18001bd00  jz      short loc_18001BD28
0x18001bd02  test    byte ptr [rcx+1Ch], 1
0x18001bd06  jz      short loc_18001BD28
0x18001bd08  cmp     byte ptr [rcx+19h], 2
0x18001bd0c  jb      short loc_18001BD28
0x18001bd0e  mov     rcx, [rcx+10h]
0x18001bd12  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001bd19  mov     edx, 0Eh
0x18001bd1e  mov     [rsp+0D0h+var_B0], r12d
0x18001bd23  call    WPP_SF_sd
0x18001bd28  lea     rbx, WPP_GLOBAL_Control
0x18001bd2f  mov     rax, [rbp+57h+pwk]
0x18001bd33  test    rax, rax
0x18001bd36  jz      short loc_18001BD41
0x18001bd38  mov     rcx, rax; pwk
0x18001bd3b  call    cs:__imp_CloseThreadpoolWork
0x18001bd41  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001bd48  call    cs:__imp_EnterCriticalSection
0x18001bd4e  mov     rax, cs:g_pScPolicyList
0x18001bd55  test    rax, rax
0x18001bd58  jz      short loc_18001BD82
0x18001bd5a  mov     rcx, [rax]
0x18001bd5d  cmp     r12d, [rax+34h]
0x18001bd61  jz      short loc_18001BD70
0x18001bd63  mov     r13, rax
0x18001bd66  mov     rax, rcx
0x18001bd69  test    rcx, rcx
0x18001bd6c  jnz     short loc_18001BD5A
0x18001bd6e  jmp     short loc_18001BD82
0x18001bd70  test    r13, r13
0x18001bd73  jnz     short loc_18001BD7E
0x18001bd75  mov     cs:g_pScPolicyList, rcx
0x18001bd7c  jmp     short loc_18001BD82
0x18001bd7e  mov     [r13+0], rcx
0x18001bd82  mov     edx, [rsi+48h]
0x18001bd85  lea     eax, [rdx-2]
0x18001bd88  test    eax, 0FFFFFFFDh
0x18001bd8d  jz      short loc_18001BDA6
0x18001bd8f  cmp     r15d, 80100012h
0x18001bd96  jnz     short loc_18001BD9C
0x18001bd98  test    edx, edx
0x18001bd9a  jz      short loc_18001BDA6
0x18001bd9c  mov     rcx, rsi
0x18001bd9f  call    ScPolicyFreeListNode
0x18001bda4  jmp     short loc_18001BDD1
0x18001bda6  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001bdad  call    cs:__imp_EnterCriticalSection
0x18001bdb3  mov     rax, cs:g_pInactiveScPolicyList
0x18001bdba  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001bdc1  mov     [rsi], rax
0x18001bdc4  mov     cs:g_pInactiveScPolicyList, rsi
0x18001bdcb  call    cs:__imp_LeaveCriticalSection
0x18001bdd1  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001bdd8  call    cs:__imp_LeaveCriticalSection
0x18001bdde  mov     edx, 2
0x18001bde3  call    WppTraceIndent
0x18001bde8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdef  cmp     rcx, rbx
0x18001bdf2  jz      short loc_18001BE20
0x18001bdf4  test    byte ptr [rcx+1Ch], 1
0x18001bdf8  jz      short loc_18001BE20
0x18001bdfa  cmp     byte ptr [rcx+19h], 4
0x18001bdfe  jb      short loc_18001BE20
0x18001be00  mov     r9, cs:WPP_pszIndent
0x18001be07  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001be0e  mov     rcx, [rcx+10h]
0x18001be12  mov     edx, 0Fh
0x18001be17  mov     [rsp+0D0h+var_B0], edi
0x18001be1b  call    WPP_SF_sD
0x18001be20  mov     rcx, [rbp+57h+var_40]
0x18001be24  xor     rcx, rsp; StackCookie
0x18001be27  call    __security_check_cookie
0x18001be2c  mov     rbx, [rsp+0D0h+arg_0]
0x18001be34  add     rsp, 0A0h
0x18001be3b  pop     r15
0x18001be3d  pop     r14
0x18001be3f  pop     r13
0x18001be41  pop     r12
0x18001be43  pop     rdi
0x18001be44  pop     rsi
0x18001be45  pop     rbp
0x18001be46  retn
```
