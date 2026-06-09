# CUmRdp::StartServer(void)

- ea: `0x140017340`
- end: `0x14001762a`
- name: `?StartServer@CUmRdp@@IEAAHXZ`
- size: `746`
- prototype: `__int64 __fastcall(CUmRdp *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400158a4`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140008ce0`
- `0x140017340`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400175cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400175cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001759f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001759f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x140017440`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x140017440`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140017433`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140017433`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1400174fb`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1400174fb`
- `RPCRT4!RpcServerListen` at `0x140017548`
- `RPCRT4!RpcServerListen` at `0x140017548`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140017476`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140017476`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400173d3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400173d3`

## pseudocode

```c
__int64 __fastcall CUmRdp::StartServer(PSID *this)
{
  unsigned int v1; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD CurrentProcessId; // eax
  RPC_STATUS v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  RPC_STATUS v8; // eax
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  unsigned int v11; // eax
  DWORD pSessionId; // [rsp+60h] [rbp-A0h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 Endpoint[264]; // [rsp+70h] [rbp-90h] BYREF

  v1 = 0;
  g_pUmRdpRpc = (CUmRdp *)this;
  pSessionId = -1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x50u,
          0x7814C1FAu,
          0x62BFFACDu,
          0xE553E9D8,
          0x36C5CE3Fu,
          0x932F1D58,
          0,
          0,
          this + 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    return v1;
  }
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  StringCchPrintfW(Endpoint, 0x104u, L"UMRdpEndpoint_%d", pSessionId);
  v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 1u, Endpoint, 0);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v1;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 16;
    goto LABEL_11;
  }
  v5 = RpcServerRegisterIfEx(qword_14006E8C0, 0, 0, 0, 0x4D2u, UMRDP_SecurityCallback);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v1;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 17;
    goto LABEL_11;
  }
  v8 = RpcServerListen(1u, 1u, 1u);
  v5 = v8;
  if ( v8 && v8 != 1713 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v1;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 18;
LABEL_11:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids, v6, v5);
    return v1;
  }
  EventW = CreateEventW(0, 1, 0, L"Local\\ShellDesktopSwitchEvent");
  this[2] = EventW;
  if ( !EventW
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids, v11, LastError);
  }
  return 1;
}

```

## disassembly

```asm
0x140017340  mov     [rsp-8+arg_8], rbx
0x140017345  mov     [rsp-8+arg_10], rsi
0x14001734a  push    rbp
0x14001734b  push    rdi
0x14001734c  push    r14
0x14001734e  lea     rbp, [rsp-190h]
0x140017356  sub     rsp, 290h
0x14001735d  mov     rax, cs:__security_cookie
0x140017364  xor     rax, rsp
0x140017367  mov     [rbp+1A0h+var_20], rax
0x14001736e  xor     r14d, r14d
0x140017371  mov     cs:?g_pUmRdpRpc@@3PEAVCUmRdp@@EA, rcx; CUmRdp * g_pUmRdpRpc
0x140017378  lea     rax, [rcx+8]
0x14001737c  mov     [rsp+2A0h+pSessionId], 0FFFFFFFFh
0x140017384  mov     [rsp+2A0h+pSid], rax; pSid
0x140017389  mov     rsi, rcx
0x14001738c  mov     [rsp+2A0h+nSubAuthority7], r14d; nSubAuthority7
0x140017391  lea     rcx, [rsp+2A0h+pIdentifierAuthority]; pIdentifierAuthority
0x140017396  mov     [rsp+2A0h+nSubAuthority6], r14d; nSubAuthority6
0x14001739b  lea     r8d, [r14+50h]; nSubAuthority0
0x14001739f  mov     [rsp+2A0h+nSubAuthority5], 932F1D58h; nSubAuthority5
0x1400173a7  mov     r9d, 7814C1FAh; nSubAuthority1
0x1400173ad  mov     [rsp+2A0h+nSubAuthority4], 36C5CE3Fh; nSubAuthority4
0x1400173b5  mov     dl, 6; nSubAuthorityCount
0x1400173b7  mov     [rsp+2A0h+nSubAuthority3], 0E553E9D8h; nSubAuthority3
0x1400173bf  mov     [rsp+2A0h+nSubAuthority2], 62BFFACDh; nSubAuthority2
0x1400173c7  mov     dword ptr [rsp+2A0h+pIdentifierAuthority.Value], r14d
0x1400173cc  mov     word ptr [rsp+2A0h+pIdentifierAuthority.Value+4], 500h
0x1400173d3  call    cs:__imp_AllocateAndInitializeSid
0x1400173d9  test    eax, eax
0x1400173db  jnz     short loc_140017433
0x1400173dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400173e4  lea     rax, WPP_GLOBAL_Control
0x1400173eb  cmp     rcx, rax
0x1400173ee  jz      loc_140017600
0x1400173f4  lea     edi, [r14+1]
0x1400173f8  test    [rcx+1Ch], dil
0x1400173fc  jz      loc_140017600
0x140017402  cmp     byte ptr [rcx+19h], 2
0x140017406  jb      loc_140017600
0x14001740c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140017411  mov     rcx, cs:WPP_GLOBAL_Control
0x140017418  lea     edx, [rdi+0Eh]
0x14001741b  mov     r9d, eax
0x14001741e  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x140017425  mov     rcx, [rcx+10h]
0x140017429  call    WPP_SF_d
0x14001742e  jmp     loc_140017600
0x140017433  call    cs:__imp_GetCurrentProcessId
0x140017439  mov     ecx, eax; dwProcessId
0x14001743b  lea     rdx, [rsp+2A0h+pSessionId]; pSessionId
0x140017440  call    cs:__imp_ProcessIdToSessionId
0x140017446  mov     r9d, [rsp+2A0h+pSessionId]
0x14001744b  lea     r8, aUmrdpendpointD; "UMRdpEndpoint_%d"
0x140017452  mov     edx, 104h; unsigned __int64
0x140017457  lea     rcx, [rsp+2A0h+Endpoint]; unsigned __int16 *
0x14001745c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140017461  xor     r9d, r9d; SecurityDescriptor
0x140017464  lea     r8, [rsp+2A0h+Endpoint]; Endpoint
0x140017469  lea     rcx, aNcalrpc; "ncalrpc"
0x140017470  lea     edi, [r9+1]
0x140017474  mov     edx, edi; MaxCalls
0x140017476  call    cs:__imp_RpcServerUseProtseqEpW
0x14001747c  mov     ebx, eax
0x14001747e  test    eax, eax
0x140017480  jz      short loc_1400174D8
0x140017482  mov     rcx, cs:WPP_GLOBAL_Control
0x140017489  lea     rax, WPP_GLOBAL_Control
0x140017490  cmp     rcx, rax
0x140017493  jz      loc_140017600
0x140017499  test    [rcx+1Ch], dil
0x14001749d  jz      loc_140017600
0x1400174a3  cmp     byte ptr [rcx+19h], 2
0x1400174a7  jb      loc_140017600
0x1400174ad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400174b2  lea     edx, [rdi+0Fh]
0x1400174b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174bc  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x1400174c3  mov     r9d, eax
0x1400174c6  mov     [rsp+2A0h+nSubAuthority2], ebx
0x1400174ca  mov     rcx, [rcx+10h]
0x1400174ce  call    WPP_SF_Dd
0x1400174d3  jmp     loc_140017600
0x1400174d8  lea     rax, ?UMRDP_SecurityCallback@@YAJPEAX0@Z; UMRDP_SecurityCallback(void *,void *)
0x1400174df  xor     r9d, r9d; Flags
0x1400174e2  mov     qword ptr [rsp+2A0h+nSubAuthority3], rax; IfCallback
0x1400174e7  lea     rcx, qword_14006E8C0; IfSpec
0x1400174ee  xor     r8d, r8d; MgrEpv
0x1400174f1  mov     [rsp+2A0h+nSubAuthority2], 4D2h; MaxCalls
0x1400174f9  xor     edx, edx; MgrTypeUuid
0x1400174fb  call    cs:__imp_RpcServerRegisterIfEx
0x140017501  mov     ebx, eax
0x140017503  test    eax, eax
0x140017505  jz      short loc_140017541
0x140017507  mov     rcx, cs:WPP_GLOBAL_Control
0x14001750e  lea     rax, WPP_GLOBAL_Control
0x140017515  cmp     rcx, rax
0x140017518  jz      loc_140017600
0x14001751e  test    [rcx+1Ch], dil
0x140017522  jz      loc_140017600
0x140017528  cmp     byte ptr [rcx+19h], 2
0x14001752c  jb      loc_140017600
0x140017532  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140017537  mov     edx, 11h
0x14001753c  jmp     loc_1400174B5
0x140017541  mov     r8d, edi; DontWait
0x140017544  mov     edx, edi; MaxCalls
0x140017546  mov     ecx, edi; MinimumCallThreads
0x140017548  call    cs:__imp_RpcServerListen
0x14001754e  mov     ebx, eax
0x140017550  test    eax, eax
0x140017552  jz      short loc_140017591
0x140017554  cmp     eax, 6B1h
0x140017559  jz      short loc_140017591
0x14001755b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017562  lea     rax, WPP_GLOBAL_Control
0x140017569  cmp     rcx, rax
0x14001756c  jz      loc_140017600
0x140017572  test    [rcx+1Ch], dil
0x140017576  jz      loc_140017600
0x14001757c  cmp     byte ptr [rcx+19h], 2
0x140017580  jb      short loc_140017600
0x140017582  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140017587  mov     edx, 12h
0x14001758c  jmp     loc_1400174B5
0x140017591  lea     r9, aLocalShelldesk; "Local\\ShellDesktopSwitchEvent"
0x140017598  xor     r8d, r8d; bInitialState
0x14001759b  mov     edx, edi; bManualReset
0x14001759d  xor     ecx, ecx; lpEventAttributes
0x14001759f  call    cs:__imp_CreateEventW
0x1400175a5  mov     [rsi+10h], rax
0x1400175a9  test    rax, rax
0x1400175ac  jnz     short loc_1400175FD
0x1400175ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175b5  lea     rax, WPP_GLOBAL_Control
0x1400175bc  cmp     rcx, rax
0x1400175bf  jz      short loc_1400175FD
0x1400175c1  test    [rcx+1Ch], dil
0x1400175c5  jz      short loc_1400175FD
0x1400175c7  cmp     byte ptr [rcx+19h], 2
0x1400175cb  jb      short loc_1400175FD
0x1400175cd  call    cs:__imp_GetLastError
0x1400175d3  mov     ebx, eax
0x1400175d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400175da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175e1  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x1400175e8  mov     edx, 13h
0x1400175ed  mov     [rsp+2A0h+nSubAuthority2], ebx
0x1400175f1  mov     r9d, eax
0x1400175f4  mov     rcx, [rcx+10h]
0x1400175f8  call    WPP_SF_Dd
0x1400175fd  mov     r14d, edi
0x140017600  mov     eax, r14d
0x140017603  mov     rcx, [rbp+1A0h+var_20]
0x14001760a  xor     rcx, rsp; StackCookie
0x14001760d  call    __security_check_cookie
0x140017612  lea     r11, [rsp+2A0h+var_10]
0x14001761a  mov     rbx, [r11+28h]
0x14001761e  mov     rsi, [r11+30h]
0x140017622  mov     rsp, r11
0x140017625  pop     r14
0x140017627  pop     rdi
0x140017628  pop     rbp
0x140017629  retn
```
