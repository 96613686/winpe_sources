# RpcSrvQueryLeaseInfov6Array

- ea: `0x18000a5c0`
- end: `0x18000aa8f`
- name: `RpcSrvQueryLeaseInfov6Array`
- size: `1231`
- prototype: `__int64 __fastcall(_WORD *, unsigned int *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a5c0`
- `0x18000aaa0`
- `0x18000b310`
- `0x18001907c`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180033830`
- `0x1800338c0`
- `0x180033900`
- `0x180033920`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000a778`
- `RPCRT4!RpcImpersonateClient` at `0x18000a778`
- `RPCRT4!RpcRevertToSelf` at `0x18000a7ef`
- `RPCRT4!RpcRevertToSelf` at `0x18000a7ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a681`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a8ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a681`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a8ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a6fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a94a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a6fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a94a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000a7ce`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000a7ce`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000a666`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000a666`

## pseudocode

```c
__int64 __fastcall RpcSrvQueryLeaseInfov6Array(_WORD *a1, unsigned int *a2, int a3)
{
  __int64 v3; // rsi
  unsigned int v6; // r8d
  BOOL v7; // ecx
  DWORD LastError; // r14d
  unsigned int v9; // r15d
  unsigned int i; // ebx
  __int64 v11; // rdx
  unsigned int v12; // r8d
  unsigned __int64 v13; // rcx
  unsigned __int64 *v14; // rax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall *v17)(); // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 UnbiasedTime[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 *v19; // [rsp+60h] [rbp-A0h]
  DWORD GrantedAccess; // [rsp+68h] [rbp-98h] BYREF
  DWORD PrivilegeSetLength; // [rsp+6Ch] [rbp-94h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp-90h] BYREF

  v3 = 0;
  v19 = 0;
  *(_OWORD *)UnbiasedTime = 0;
  v17 = RpcSrvQueryLeaseInfov6Array;
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 14, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, &v17, RpcSrvQueryLeaseInfov6Array);
  if ( dword_18004271C && QueryUnbiasedInterruptTime(UnbiasedTime) )
  {
    EnterCriticalSection(&CriticalSection);
    v7 = *(unsigned int **)&qword_1800426D8 == &qword_1800426D8 && (__int64 *)qword_1800426C8 == &qword_1800426C8;
    if ( *(unsigned int **)qword_1800426E0 != &qword_1800426D8 )
      goto LABEL_44;
    v19 = (unsigned __int64 *)qword_1800426E0;
    UnbiasedTime[1] = (unsigned __int64)&qword_1800426D8;
    *(_QWORD *)qword_1800426E0 = &UnbiasedTime[1];
    qword_1800426E0 = (__int64)&UnbiasedTime[1];
    if ( v7 )
      WxSetThreadpoolTimer(g_RpcWatchDog, &stru_180042710, v6, 0x7530u);
    LeaveCriticalSection(&CriticalSection);
  }
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qql((_DWORD)a1, (_DWORD)a2, a3, (unsigned int)&v17, (__int64)v17);
  if ( a1 && *a1 )
  {
    LastError = 50;
LABEL_49:
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 11, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, LastError);
    goto LABEL_29;
  }
  GrantedAccess = 0;
  AccessStatus = 0;
  memset_0(&PrivilegeSet, 0, 0x1F4u);
  PrivilegeSetLength = 500;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 14, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids);
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    if ( AccessCheck(
           qword_180038290,
           (HANDLE)0xFFFFFFFFFFFFFFFBLL,
           1u,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      if ( AccessStatus )
      {
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 1287;
      }
    }
    else
    {
      LastError = GetLastErrorOrUnknown();
    }
  }
  RpcRevertToSelf();
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 15, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids, LastError);
  if ( LastError )
    goto LABEL_49;
  if ( **(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
  {
    LastError = 65;
    if ( (xmmword_1800423E0 & 2) == 0 )
      goto LABEL_29;
    WPP_SF_D(1025, 10, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, 65);
    goto LABEL_49;
  }
  if ( a2 )
  {
    v9 = *a2;
    for ( i = 0; i < v9; ++v3 )
    {
      v11 = 56 * v3 + *((_QWORD *)a2 + 1);
      ++i;
      *(_BYTE *)v11 = (unsigned int)RpcSrvQueryLeaseInfov6(
                                      (_DWORD)a1,
                                      *(_QWORD *)(v11 + 8),
                                      *(_QWORD *)(v11 + 16),
                                      *(_QWORD *)(v11 + 24),
                                      *(_QWORD *)(v11 + 32),
                                      *(_QWORD *)(v11 + 40),
                                      v11 + 48) == 0;
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_29:
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 16, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, &v17, v17);
  if ( dword_18004271C )
  {
    EnterCriticalSection(&CriticalSection);
    v13 = UnbiasedTime[1];
    if ( *(unsigned __int64 **)(UnbiasedTime[1] + 8) == &UnbiasedTime[1] )
    {
      v14 = v19;
      if ( (unsigned __int64 *)*v19 == &UnbiasedTime[1] )
      {
        *v19 = UnbiasedTime[1];
        *(_QWORD *)(v13 + 8) = v14;
        v19 = &UnbiasedTime[1];
        UnbiasedTime[1] = (unsigned __int64)&UnbiasedTime[1];
        if ( (__int64 *)qword_1800426C8 == &qword_1800426C8 && *(unsigned int **)&qword_1800426D8 == &qword_1800426D8 )
          WxSetThreadpoolTimer(g_RpcWatchDog, 0, v12, 0);
        LeaveCriticalSection(&CriticalSection);
        goto LABEL_36;
      }
    }
LABEL_44:
    __fastfail(3u);
  }
LABEL_36:
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 17, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, &v17, v17);
  return LastError;
}

```

## disassembly

```asm
0x18000a5c0  mov     [rsp-8+arg_10], rbx
0x18000a5c5  mov     [rsp-8+arg_18], rsi
0x18000a5ca  push    rbp
0x18000a5cb  push    rdi
0x18000a5cc  push    r12
0x18000a5ce  push    r13
0x18000a5d0  push    r15
0x18000a5d2  lea     rbp, [rsp-180h]
0x18000a5da  sub     rsp, 280h
0x18000a5e1  mov     rax, cs:__security_cookie
0x18000a5e8  xor     rax, rsp
0x18000a5eb  mov     [rbp+1A0h+var_30], rax
0x18000a5f2  xor     esi, esi
0x18000a5f4  lea     rax, RpcSrvQueryLeaseInfov6Array
0x18000a5fb  xorps   xmm0, xmm0
0x18000a5fe  mov     [rsp+2A0h+var_240], rsi
0x18000a603  movdqu  xmmword ptr [rsp+2A0h+UnbiasedTime], xmm0
0x18000a609  mov     [rsp+2A0h+var_258], rax
0x18000a60e  mov     ebx, esi
0x18000a610  mov     r12, rdx
0x18000a613  mov     r13, rcx
0x18000a616  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000a61d  jz      short loc_18000A63F
0x18000a61f  mov     edx, 0Eh
0x18000a624  mov     [rsp+2A0h+PrivilegeSet], rax
0x18000a629  mov     ecx, 40Eh
0x18000a62e  lea     r9, [rsp+2A0h+var_258]
0x18000a633  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000a63a  call    WPP_SF_qq
0x18000a63f  cmp     cs:dword_18004271C, ebx
0x18000a645  lea     r15, qword_1800426C8
0x18000a64c  mov     [rsp+2A0h+arg_0], r14
0x18000a654  lea     rdi, qword_1800426D8
0x18000a65b  jz      loc_18000A70B
0x18000a661  lea     rcx, [rsp+2A0h+UnbiasedTime]; UnbiasedTime
0x18000a666  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000a66d  nop     dword ptr [rax+rax+00h]
0x18000a672  test    eax, eax
0x18000a674  jz      loc_18000A70B
0x18000a67a  lea     rcx, CriticalSection; lpCriticalSection
0x18000a681  call    cs:__imp_EnterCriticalSection
0x18000a688  nop     dword ptr [rax+rax+00h]
0x18000a68d  cmp     cs:qword_1800426D8, rdi
0x18000a694  jnz     short loc_18000A69F
0x18000a696  cmp     cs:qword_1800426C8, r15
0x18000a69d  jz      short loc_18000A6A3
0x18000a69f  mov     ecx, esi
0x18000a6a1  jmp     short loc_18000A6A8
0x18000a6a3  mov     ecx, 1
0x18000a6a8  mov     rax, cs:qword_1800426E0
0x18000a6af  cmp     [rax], rdi
0x18000a6b2  jnz     loc_18000AA05
0x18000a6b8  mov     [rsp+2A0h+var_240], rax
0x18000a6bd  lea     rdx, [rsp+2A0h+UnbiasedTime+8]
0x18000a6c2  mov     [rsp+2A0h+UnbiasedTime+8], rdi
0x18000a6c7  mov     [rax], rdx
0x18000a6ca  lea     rax, [rsp+2A0h+UnbiasedTime+8]
0x18000a6cf  mov     cs:qword_1800426E0, rax
0x18000a6d6  test    ecx, ecx
0x18000a6d8  jz      short loc_18000A6F3
0x18000a6da  mov     rcx, cs:?g_RpcWatchDog@@3VCRpcWatchDog@@A; struct _TP_TIMER *
0x18000a6e1  lea     rdx, stru_180042710; struct _FILETIME *
0x18000a6e8  mov     r9d, 7530h; unsigned int
0x18000a6ee  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x18000a6f3  lea     rcx, CriticalSection; lpCriticalSection
0x18000a6fa  call    cs:__imp_LeaveCriticalSection
0x18000a701  nop     dword ptr [rax+rax+00h]
0x18000a706  mov     ebx, 1
0x18000a70b  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000a712  jz      short loc_18000A72C
0x18000a714  mov     rax, [rsp+2A0h+var_258]
0x18000a719  lea     r9, [rsp+2A0h+var_258]
0x18000a71e  mov     dword ptr [rsp+2A0h+PrivilegeSetLength], ebx
0x18000a722  mov     [rsp+2A0h+PrivilegeSet], rax
0x18000a727  call    WPP_SF_qql
0x18000a72c  test    r13, r13
0x18000a72f  jnz     loc_18000AA24
0x18000a735  xor     edx, edx; Val
0x18000a737  mov     [rsp+2A0h+var_238], esi
0x18000a73b  mov     r8d, 1F4h; Size
0x18000a741  mov     [rsp+2A0h+var_260], esi
0x18000a745  lea     rcx, [rsp+2A0h+var_230]; void *
0x18000a74a  call    memset_0
0x18000a74f  mov     [rsp+2A0h+var_234], 1F4h
0x18000a757  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000a75e  jz      short loc_18000A776
0x18000a760  mov     edx, 0Eh
0x18000a765  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000a76c  mov     ecx, 404h
0x18000a771  call    WPP_SF_
0x18000a776  xor     ecx, ecx; BindingHandle
0x18000a778  call    cs:__imp_RpcImpersonateClient
0x18000a77f  nop     dword ptr [rax+rax+00h]
0x18000a784  mov     r14d, eax
0x18000a787  test    eax, eax
0x18000a789  jnz     short loc_18000A7EF
0x18000a78b  lea     rax, [rsp+2A0h+var_260]
0x18000a790  mov     rdx, 0FFFFFFFFFFFFFFFBh; ClientToken
0x18000a797  mov     [rsp+2A0h+AccessStatus], rax; AccessStatus
0x18000a79c  lea     r9, GenericMapping; GenericMapping
0x18000a7a3  lea     rax, [rsp+2A0h+var_238]
0x18000a7a8  mov     r8d, 1; DesiredAccess
0x18000a7ae  mov     [rsp+2A0h+GrantedAccess], rax; GrantedAccess
0x18000a7b3  lea     rcx, qword_180038290; pSecurityDescriptor
0x18000a7ba  lea     rax, [rsp+2A0h+var_234]
0x18000a7bf  mov     [rsp+2A0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000a7c4  lea     rax, [rsp+2A0h+var_230]
0x18000a7c9  mov     [rsp+2A0h+PrivilegeSet], rax; PrivilegeSet
0x18000a7ce  call    cs:__imp_AccessCheck
0x18000a7d5  nop     dword ptr [rax+rax+00h]
0x18000a7da  test    eax, eax
0x18000a7dc  jz      loc_18000AA17
0x18000a7e2  cmp     [rsp+2A0h+var_260], esi
0x18000a7e6  jz      loc_18000A9E5
0x18000a7ec  mov     r14d, esi
0x18000a7ef  call    cs:__imp_RpcRevertToSelf
0x18000a7f6  nop     dword ptr [rax+rax+00h]
0x18000a7fb  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000a802  jz      short loc_18000A81D
0x18000a804  mov     edx, 0Fh
0x18000a809  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000a810  mov     ecx, 404h
0x18000a815  mov     r9d, r14d
0x18000a818  call    WPP_SF_D
0x18000a81d  test    r14d, r14d
0x18000a820  jnz     loc_18000AA35
0x18000a826  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18000a82d  cmp     [rax], esi
0x18000a82f  jnz     loc_18000AA65
0x18000a835  test    r12, r12
0x18000a838  jz      loc_18000AA0C
0x18000a83e  mov     r15d, [r12]
0x18000a842  mov     ebx, esi
0x18000a844  test    r15d, r15d
0x18000a847  jz      short loc_18000A8A7
0x18000a849  mov     rdx, [r12+8]
0x18000a84e  mov     rcx, r13
0x18000a851  imul    rdi, rsi, 38h ; '8'
0x18000a855  add     rdx, rdi
0x18000a858  mov     r9, [rdx+18h]
0x18000a85c  lea     rax, [rdx+30h]
0x18000a860  mov     r8, [rdx+10h]
0x18000a864  mov     [rsp+2A0h+GrantedAccess], rax
0x18000a869  mov     rax, [rdx+28h]
0x18000a86d  mov     [rsp+2A0h+PrivilegeSetLength], rax
0x18000a872  mov     rax, [rdx+20h]
0x18000a876  mov     rdx, [rdx+8]
0x18000a87a  mov     [rsp+2A0h+PrivilegeSet], rax
0x18000a87f  call    RpcSrvQueryLeaseInfov6
0x18000a884  mov     rdx, [r12+8]
0x18000a889  test    eax, eax
0x18000a88b  jz      loc_18000A9BB
0x18000a891  xor     al, al
0x18000a893  inc     ebx
0x18000a895  mov     [rdx+rdi], al
0x18000a898  inc     rsi
0x18000a89b  cmp     ebx, r15d
0x18000a89e  jb      short loc_18000A849
0x18000a8a0  lea     rdi, qword_1800426D8
0x18000a8a7  lea     r15, qword_1800426C8
0x18000a8ae  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000a8b5  jz      short loc_18000A8DC
0x18000a8b7  mov     rax, [rsp+2A0h+var_258]
0x18000a8bc  lea     r9, [rsp+2A0h+var_258]
0x18000a8c1  mov     edx, 10h
0x18000a8c6  mov     [rsp+2A0h+PrivilegeSet], rax
0x18000a8cb  mov     ecx, 40Eh
0x18000a8d0  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000a8d7  call    WPP_SF_qq
0x18000a8dc  cmp     cs:dword_18004271C, 0
0x18000a8e3  jz      short loc_18000A956
0x18000a8e5  lea     rcx, CriticalSection; lpCriticalSection
0x18000a8ec  call    cs:__imp_EnterCriticalSection
0x18000a8f3  nop     dword ptr [rax+rax+00h]
0x18000a8f8  mov     rcx, [rsp+2A0h+UnbiasedTime+8]
0x18000a8fd  lea     rax, [rsp+2A0h+UnbiasedTime+8]
0x18000a902  cmp     [rcx+8], rax
0x18000a906  jnz     loc_18000AA05
0x18000a90c  mov     rax, [rsp+2A0h+var_240]
0x18000a911  lea     rdx, [rsp+2A0h+UnbiasedTime+8]
0x18000a916  cmp     [rax], rdx
0x18000a919  jnz     loc_18000AA05
0x18000a91f  mov     [rax], rcx
0x18000a922  mov     [rcx+8], rax
0x18000a926  lea     rax, [rsp+2A0h+UnbiasedTime+8]
0x18000a92b  cmp     cs:qword_1800426C8, r15
0x18000a932  mov     [rsp+2A0h+var_240], rax
0x18000a937  lea     rax, [rsp+2A0h+UnbiasedTime+8]
0x18000a93c  mov     [rsp+2A0h+UnbiasedTime+8], rax
0x18000a941  jz      short loc_18000A9C2
0x18000a943  lea     rcx, CriticalSection; lpCriticalSection
0x18000a94a  call    cs:__imp_LeaveCriticalSection
0x18000a951  nop     dword ptr [rax+rax+00h]
0x18000a956  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000a95d  jz      short loc_18000A984
0x18000a95f  mov     r9, [rsp+2A0h+var_258]
0x18000a964  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000a96b  mov     [rsp+2A0h+PrivilegeSet], r9
0x18000a970  mov     edx, 11h
0x18000a975  lea     r9, [rsp+2A0h+var_258]
0x18000a97a  mov     ecx, 40Eh
0x18000a97f  call    WPP_SF_qq
0x18000a984  mov     eax, r14d
0x18000a987  mov     r14, [rsp+2A0h+arg_0]
0x18000a98f  mov     rcx, [rbp+1A0h+var_30]
0x18000a996  xor     rcx, rsp; StackCookie
0x18000a999  call    __security_check_cookie
0x18000a99e  lea     r11, [rsp+2A0h+var_20]
0x18000a9a6  mov     rbx, [r11+40h]
0x18000a9aa  mov     rsi, [r11+48h]
0x18000a9ae  mov     rsp, r11
0x18000a9b1  pop     r15
0x18000a9b3  pop     r13
0x18000a9b5  pop     r12
0x18000a9b7  pop     rdi
0x18000a9b8  pop     rbp
0x18000a9b9  retn
0x18000a9bb  mov     al, 1
0x18000a9bd  jmp     loc_18000A893
0x18000a9c2  cmp     cs:qword_1800426D8, rdi
0x18000a9c9  jnz     loc_18000A943
0x18000a9cf  mov     rcx, cs:?g_RpcWatchDog@@3VCRpcWatchDog@@A; struct _TP_TIMER *
0x18000a9d6  xor     r9d, r9d; unsigned int
0x18000a9d9  xor     edx, edx; struct _FILETIME *
0x18000a9db  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x18000a9e0  jmp     loc_18000A943
0x18000a9e5  call    cs:__imp_GetLastError
0x18000a9ec  nop     dword ptr [rax+rax+00h]
0x18000a9f1  mov     r14d, eax
0x18000a9f4  mov     eax, 507h
0x18000a9f9  test    r14d, r14d
0x18000a9fc  cmovz   r14d, eax
0x18000aa00  jmp     loc_18000A7EF
0x18000aa05  mov     ecx, 3
0x18000aa0a  int     29h; Win8: RtlFailFast(ecx)
0x18000aa0c  mov     r14d, 57h ; 'W'
0x18000aa12  jmp     loc_18000A8AE
0x18000aa17  call    GetLastErrorOrUnknown
0x18000aa1c  mov     r14d, eax
0x18000aa1f  jmp     loc_18000A7EF
0x18000aa24  cmp     [r13+0], si
0x18000aa29  jz      loc_18000A735
0x18000aa2f  mov     r14d, 32h ; '2'
0x18000aa35  test    byte ptr cs:xmmword_1800423E0, 2
0x18000aa3c  jz      short loc_18000AA57
0x18000aa3e  mov     edx, 0Bh
0x18000aa43  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x18000aa4a  mov     ecx, 401h
0x18000aa4f  mov     r9d, r14d
0x18000aa52  call    WPP_SF_D
0x18000aa57  test    r14d, r14d
0x18000aa5a  jz      loc_18000A835
0x18000aa60  jmp     loc_18000A8AE
0x18000aa65  mov     r14d, 41h ; 'A'
0x18000aa6b  test    byte ptr cs:xmmword_1800423E0, 2
0x18000aa72  jz      short loc_18000AA57
0x18000aa74  mov     edx, 0Ah
0x18000aa79  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x18000aa80  mov     ecx, 401h
0x18000aa85  mov     r9d, r14d
0x18000aa88  call    WPP_SF_D
0x18000aa8d  jmp     short loc_18000AA35
```
