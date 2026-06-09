# RpcSrvQueryLeaseInfov6

- ea: `0x18000aaa0`
- end: `0x18000b1cc`
- name: `RpcSrvQueryLeaseInfov6`
- size: `1836`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a5c0`

## callees

- `0x18000aaa0`
- `0x18000b310`
- `0x18000b350`
- `0x18000b380`
- `0x18000b5d0`
- `0x18000bb2c`
- `0x18000bc88`
- `0x180019ad0`
- `0x18001a3ee`
- `0x1800269d4`
- `0x18002db90`
- `0x18002dbe0`
- `0x1800337d0`
- `0x180033830`
- `0x1800338c0`
- `0x180033900`
- `0x180033920`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000ab55`
- `RPCRT4!RpcImpersonateClient` at `0x18000ab55`
- `RPCRT4!RpcRevertToSelf` at `0x18000abc7`
- `RPCRT4!RpcRevertToSelf` at `0x18000abc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b067`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b09a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b0bb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b0dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b09a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b0bb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b0dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ae7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ae7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aca7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aca7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000adc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000adc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b048`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000adfd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000adfd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000aba9`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000aba9`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000ac8c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000ac8c`

## pseudocode

```c
__int64 __fastcall RpcSrvQueryLeaseInfov6(
        _WORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7)
{
  int v9; // esi
  DWORD LastError; // ebx
  int v11; // edx
  int v12; // ecx
  int v13; // r8d
  unsigned int v14; // r8d
  BOOL v15; // ecx
  bool v16; // zf
  __int64 Dhcpv6ContextOnNicList; // rax
  __int64 v18; // rdi
  int v19; // edi
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  unsigned int v23; // r8d
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int64 UnbiasedTime[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-90h] BYREF
  DWORD PrivilegeSetLength; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+80h] [rbp-80h] BYREF

  v34 = a3;
  v27 = 0;
  v9 = 0;
  v28 = 0;
  *(_OWORD *)UnbiasedTime = 0;
  v31 = 0;
  if ( a1 && *a1 )
  {
    LastError = 50;
    goto LABEL_77;
  }
  GrantedAccess = 0;
  AccessStatus = 0;
  memset_0(&PrivilegeSet, 0, 0x1F4u);
  PrivilegeSetLength = 500;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 14, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids);
  LastError = RpcImpersonateClient(0);
  if ( !LastError
    && (!AccessCheck(
           qword_180038290,
           (HANDLE)0xFFFFFFFFFFFFFFFBLL,
           1u,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus)
     || !AccessStatus) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
  }
  RpcRevertToSelf();
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 15, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids, LastError);
  if ( LastError )
    goto LABEL_77;
  if ( **(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
  {
    LastError = 65;
    if ( (xmmword_1800423E0 & 2) != 0 )
    {
      WPP_SF_D(1025, 10, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, 65);
LABEL_77:
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_D(1025, 11, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, LastError);
    }
LABEL_45:
    v19 = 0;
    goto LABEL_46;
  }
  if ( !a2 || !v34 || !a4 || !a5 || !a6 || !a7 )
  {
    LastError = 87;
    goto LABEL_45;
  }
  UnbiasedTime[0] = (unsigned __int64)RpcSrvQueryLeaseInfov6;
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 14, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, UnbiasedTime, RpcSrvQueryLeaseInfov6);
  if ( dword_18004271C && QueryUnbiasedInterruptTime(&UnbiasedTime[1]) )
  {
    EnterCriticalSection(&CriticalSection);
    v15 = *(unsigned int **)&qword_1800426D8 == &qword_1800426D8 && (__int64 *)qword_1800426C8 == &qword_1800426C8;
    if ( *(unsigned int **)qword_1800426E0 != &qword_1800426D8 )
      goto LABEL_74;
    *(_QWORD *)&v31 = &qword_1800426D8;
    *((_QWORD *)&v31 + 1) = qword_1800426E0;
    *(_QWORD *)qword_1800426E0 = &v31;
    qword_1800426E0 = (__int64)&v31;
    if ( v15 )
      WxSetThreadpoolTimer(g_RpcWatchDog, &stru_180042710, v14, 0x7530u);
    LeaveCriticalSection(&CriticalSection);
  }
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qql(v12, v11, v13, (unsigned int)UnbiasedTime, UnbiasedTime[0]);
  v16 = g_fVelocityAddUserClassTracing == 0;
  *(_OWORD *)a5 = 0;
  v9 = 1;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)a6 = 0;
  *(_OWORD *)(a6 + 16) = 0;
  *(_OWORD *)(a6 + 32) = 0;
  *(_OWORD *)(a6 + 48) = 0;
  if ( v16 )
  {
    EnterCriticalSection(&Dhcpv6GlobalNicListCritSect);
    Dhcpv6ContextOnNicList = FindDhcpv6ContextOnNicList(a2);
    v18 = Dhcpv6ContextOnNicList;
    if ( Dhcpv6ContextOnNicList )
    {
      LastError = 0;
      _InterlockedIncrement((volatile signed __int32 *)(Dhcpv6ContextOnNicList + 16));
      LeaveCriticalSection(&Dhcpv6GlobalNicListCritSect);
      v27 = v18;
    }
    else
    {
      LeaveCriticalSection(&Dhcpv6GlobalNicListCritSect);
      LastError = 2;
    }
  }
  else
  {
    LastError = Dhcpv6FindAndRefContext_New(a2, &v27);
  }
  if ( LastError )
  {
    v19 = v28;
    goto LABEL_46;
  }
  if ( dword_180042658 )
  {
    if ( dword_180042658 != 1 )
      goto LABEL_37;
  }
  else
  {
    if ( !(unsigned int)DhcpIsContainerSystem() || !(unsigned int)DhcpIsFSEFlagEnabledInRegistry() )
    {
      dword_180042658 = 2;
      goto LABEL_37;
    }
    dword_180042658 = 1;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 43, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids);
  RefillDhcpv6Context(v27);
LABEL_37:
  AcquireSRWLockShared((PSRWLOCK)(v27 + 608));
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 44, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, *(_QWORD *)(v27 + 56));
  v19 = 1;
  LastError = QueryBasicLeaseInfov6(v27, v34, a4, a5);
  if ( !LastError )
  {
    LastError = QueryDNSParamv6(v27, a6);
    if ( !LastError )
    {
      *a7 = *(_DWORD *)(v27 + 136);
LABEL_42:
      ReleaseSRWLockShared((PSRWLOCK)(v27 + 608));
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_S(1028, 45, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, *(_QWORD *)(v27 + 56));
      goto LABEL_53;
    }
  }
LABEL_46:
  v20 = *(void **)(a5 + 8);
  if ( v20 )
  {
    LocalFree(v20);
    *(_QWORD *)(a5 + 8) = 0;
    *(_WORD *)a5 = 0;
  }
  v21 = *(void **)(a4 + 8);
  if ( v21 )
  {
    LocalFree(v21);
    *(_QWORD *)(a4 + 8) = 0;
    *(_WORD *)a4 = 0;
  }
  v22 = *(void **)(a6 + 56);
  if ( v22 )
  {
    LocalFree(v22);
    *(_QWORD *)(a6 + 56) = 0;
    *(_DWORD *)(a6 + 48) = 0;
  }
  if ( v19 )
    goto LABEL_42;
LABEL_53:
  if ( !v9 )
    goto LABEL_63;
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 16, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, UnbiasedTime, UnbiasedTime[0]);
  if ( dword_18004271C )
  {
    EnterCriticalSection(&CriticalSection);
    v24 = v31;
    if ( *(__int128 **)(v31 + 8) == &v31 )
    {
      v25 = *((_QWORD *)&v31 + 1);
      if ( **((__int128 ***)&v31 + 1) == &v31 )
      {
        **((_QWORD **)&v31 + 1) = v31;
        *(_QWORD *)(v24 + 8) = v25;
        *((_QWORD *)&v31 + 1) = &v31;
        *(_QWORD *)&v31 = &v31;
        if ( (__int64 *)qword_1800426C8 == &qword_1800426C8 && *(unsigned int **)&qword_1800426D8 == &qword_1800426D8 )
          WxSetThreadpoolTimer(g_RpcWatchDog, 0, v23, 0);
        LeaveCriticalSection(&CriticalSection);
        goto LABEL_61;
      }
    }
LABEL_74:
    __fastfail(3u);
  }
LABEL_61:
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 17, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, UnbiasedTime, UnbiasedTime[0]);
LABEL_63:
  if ( v27 && _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 16), 0xFFFFFFFF) == 1 )
    Dhcpv6DestroyContextEx(v27);
  return LastError;
}

```

## disassembly

```asm
0x18000aaa0  mov     [rsp-8+arg_0], rbx
0x18000aaa5  push    rbp
0x18000aaa6  push    rsi
0x18000aaa7  push    rdi
0x18000aaa8  push    r12
0x18000aaaa  push    r13
0x18000aaac  push    r14
0x18000aaae  push    r15
0x18000aab0  lea     rbp, [rsp-190h]
0x18000aab8  sub     rsp, 290h
0x18000aabf  mov     rax, cs:__security_cookie
0x18000aac6  xor     rax, rsp
0x18000aac9  mov     [rbp+1C0h+var_40], rax
0x18000aad0  mov     r15, [rbp+1C0h+arg_20]
0x18000aad7  xor     eax, eax
0x18000aad9  mov     r14, [rbp+1C0h+arg_28]
0x18000aae0  xorps   xmm0, xmm0
0x18000aae3  mov     r13, [rbp+1C0h+arg_30]
0x18000aaea  mov     r12, r9
0x18000aaed  mov     [rsp+2C0h+var_248], r8
0x18000aaf2  mov     rdi, rdx
0x18000aaf5  mov     [rsp+2C0h+var_280], rax
0x18000aafa  mov     esi, eax
0x18000aafc  mov     [rsp+2C0h+var_278], eax
0x18000ab00  movups  xmmword ptr [rsp+2C0h+UnbiasedTime], xmm0
0x18000ab05  movups  [rsp+2C0h+var_260], xmm0
0x18000ab0a  test    rcx, rcx
0x18000ab0d  jnz     loc_18000B0FB
0x18000ab13  xor     edx, edx; Val
0x18000ab15  mov     [rsp+2C0h+var_250], eax
0x18000ab19  mov     r8d, 1F4h; Size
0x18000ab1f  mov     [rsp+2C0h+var_274], eax
0x18000ab23  lea     rcx, [rbp+1C0h+var_240]; void *
0x18000ab27  call    memset_0
0x18000ab2c  mov     [rsp+2C0h+var_24C], 1F4h
0x18000ab34  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000ab3b  jz      short loc_18000AB53
0x18000ab3d  mov     edx, 0Eh
0x18000ab42  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000ab49  mov     ecx, 404h
0x18000ab4e  call    WPP_SF_
0x18000ab53  xor     ecx, ecx; BindingHandle
0x18000ab55  call    cs:__imp_RpcImpersonateClient
0x18000ab5c  nop     dword ptr [rax+rax+00h]
0x18000ab61  mov     ebx, eax
0x18000ab63  test    eax, eax
0x18000ab65  jnz     short loc_18000ABC7
0x18000ab67  lea     rax, [rsp+2C0h+var_274]
0x18000ab6c  mov     rdx, 0FFFFFFFFFFFFFFFBh; ClientToken
0x18000ab73  mov     [rsp+2C0h+AccessStatus], rax; AccessStatus
0x18000ab78  lea     r9, GenericMapping; GenericMapping
0x18000ab7f  lea     rax, [rsp+2C0h+var_250]
0x18000ab84  mov     r8d, 1; DesiredAccess
0x18000ab8a  mov     [rsp+2C0h+GrantedAccess], rax; GrantedAccess
0x18000ab8f  lea     rcx, qword_180038290; pSecurityDescriptor
0x18000ab96  lea     rax, [rsp+2C0h+var_24C]
0x18000ab9b  mov     [rsp+2C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000aba0  lea     rax, [rbp+1C0h+var_240]
0x18000aba4  mov     [rsp+2C0h+PrivilegeSet], rax; PrivilegeSet
0x18000aba9  call    cs:__imp_AccessCheck
0x18000abb0  nop     dword ptr [rax+rax+00h]
0x18000abb5  test    eax, eax
0x18000abb7  jz      loc_18000B067
0x18000abbd  cmp     [rsp+2C0h+var_274], esi
0x18000abc1  jz      loc_18000B067
0x18000abc7  call    cs:__imp_RpcRevertToSelf
0x18000abce  nop     dword ptr [rax+rax+00h]
0x18000abd3  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000abda  jz      short loc_18000ABF5
0x18000abdc  mov     edx, 0Fh
0x18000abe1  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000abe8  mov     ecx, 404h
0x18000abed  mov     r9d, ebx
0x18000abf0  call    WPP_SF_D
0x18000abf5  test    ebx, ebx
0x18000abf7  jnz     loc_18000B109
0x18000abfd  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18000ac04  cmp     [rax], esi
0x18000ac06  jnz     loc_18000B138
0x18000ac0c  test    rdi, rdi
0x18000ac0f  jz      loc_18000AEB2
0x18000ac15  cmp     [rsp+2C0h+var_248], rsi
0x18000ac1a  jz      loc_18000AEB2
0x18000ac20  test    r12, r12
0x18000ac23  jz      loc_18000AEB2
0x18000ac29  test    r15, r15
0x18000ac2c  jz      loc_18000AEB2
0x18000ac32  test    r14, r14
0x18000ac35  jz      loc_18000AEB2
0x18000ac3b  test    r13, r13
0x18000ac3e  jz      loc_18000AEB2
0x18000ac44  lea     rax, RpcSrvQueryLeaseInfov6
0x18000ac4b  xor     ebx, ebx
0x18000ac4d  mov     [rsp+2C0h+UnbiasedTime], rax
0x18000ac52  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000ac59  jz      short loc_18000AC7B
0x18000ac5b  mov     edx, 0Eh
0x18000ac60  mov     [rsp+2C0h+PrivilegeSet], rax
0x18000ac65  mov     ecx, 40Eh
0x18000ac6a  lea     r9, [rsp+2C0h+UnbiasedTime]
0x18000ac6f  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000ac76  call    WPP_SF_qq
0x18000ac7b  cmp     cs:dword_18004271C, ebx
0x18000ac81  jz      loc_18000AD3F
0x18000ac87  lea     rcx, [rsp+2C0h+UnbiasedTime+8]; UnbiasedTime
0x18000ac8c  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000ac93  nop     dword ptr [rax+rax+00h]
0x18000ac98  test    eax, eax
0x18000ac9a  jz      loc_18000AD3F
0x18000aca0  lea     rcx, CriticalSection; lpCriticalSection
0x18000aca7  call    cs:__imp_EnterCriticalSection
0x18000acae  nop     dword ptr [rax+rax+00h]
0x18000acb3  lea     rdx, qword_1800426D8
0x18000acba  cmp     cs:qword_1800426D8, rdx
0x18000acc1  lea     rax, qword_1800426C8
0x18000acc8  jnz     short loc_18000ACD3
0x18000acca  cmp     cs:qword_1800426C8, rax
0x18000acd1  jz      short loc_18000ACD7
0x18000acd3  xor     ecx, ecx
0x18000acd5  jmp     short loc_18000ACDC
0x18000acd7  mov     ecx, 1
0x18000acdc  mov     rax, cs:qword_1800426E0
0x18000ace3  cmp     [rax], rdx
0x18000ace6  jnz     loc_18000B084
0x18000acec  mov     qword ptr [rsp+2C0h+var_260], rdx
0x18000acf1  lea     rdx, [rsp+2C0h+var_260]
0x18000acf6  mov     qword ptr [rsp+2C0h+var_260+8], rax
0x18000acfb  mov     [rax], rdx
0x18000acfe  lea     rax, [rsp+2C0h+var_260]
0x18000ad03  mov     cs:qword_1800426E0, rax
0x18000ad0a  test    ecx, ecx
0x18000ad0c  jz      short loc_18000AD27
0x18000ad0e  mov     rcx, cs:?g_RpcWatchDog@@3VCRpcWatchDog@@A; struct _TP_TIMER *
0x18000ad15  lea     rdx, stru_180042710; struct _FILETIME *
0x18000ad1c  mov     r9d, 7530h; unsigned int
0x18000ad22  call    ?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x18000ad27  lea     rcx, CriticalSection; lpCriticalSection
0x18000ad2e  call    cs:__imp_LeaveCriticalSection
0x18000ad35  nop     dword ptr [rax+rax+00h]
0x18000ad3a  mov     ebx, 1
0x18000ad3f  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000ad46  jz      short loc_18000AD60
0x18000ad48  mov     rax, [rsp+2C0h+UnbiasedTime]
0x18000ad4d  lea     r9, [rsp+2C0h+UnbiasedTime]
0x18000ad52  mov     dword ptr [rsp+2C0h+PrivilegeSetLength], ebx
0x18000ad56  mov     [rsp+2C0h+PrivilegeSet], rax
0x18000ad5b  call    WPP_SF_qql
0x18000ad60  cmp     cs:g_fVelocityAddUserClassTracing, 0
0x18000ad67  xorps   xmm0, xmm0
0x18000ad6a  movups  xmmword ptr [r15], xmm0
0x18000ad6e  mov     esi, 1
0x18000ad73  xorps   xmm1, xmm1
0x18000ad76  movups  xmmword ptr [r12], xmm1
0x18000ad7b  movups  xmmword ptr [r14], xmm0
0x18000ad7f  movups  xmmword ptr [r14+10h], xmm0
0x18000ad84  movups  xmmword ptr [r14+20h], xmm0
0x18000ad89  movups  xmmword ptr [r14+30h], xmm0
0x18000ad8e  jnz     loc_18000B18F
0x18000ad94  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18000ad9b  call    cs:__imp_EnterCriticalSection
0x18000ada2  nop     dword ptr [rax+rax+00h]
0x18000ada7  mov     rcx, rdi
0x18000adaa  call    FindDhcpv6ContextOnNicList
0x18000adaf  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18000adb6  mov     rdi, rax
0x18000adb9  test    rax, rax
0x18000adbc  jnz     loc_18000B042
0x18000adc2  call    cs:__imp_LeaveCriticalSection
0x18000adc9  nop     dword ptr [rax+rax+00h]
0x18000adce  mov     ebx, 2
0x18000add3  test    ebx, ebx
0x18000add5  jnz     loc_18000B05E
0x18000addb  mov     eax, cs:dword_180042658
0x18000ade1  test    eax, eax
0x18000ade3  jz      loc_18000B1A3
0x18000ade9  cmp     eax, esi
0x18000adeb  jz      loc_18000B161
0x18000adf1  mov     rcx, [rsp+2C0h+var_280]
0x18000adf6  add     rcx, 260h; SRWLock
0x18000adfd  call    cs:__imp_AcquireSRWLockShared
0x18000ae04  nop     dword ptr [rax+rax+00h]
0x18000ae09  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000ae10  jz      short loc_18000AE31
0x18000ae12  mov     r9, [rsp+2C0h+var_280]
0x18000ae17  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x18000ae1e  mov     edx, 2Ch ; ','
0x18000ae23  mov     ecx, 404h
0x18000ae28  mov     r9, [r9+38h]
0x18000ae2c  call    WPP_SF_S
0x18000ae31  mov     rdx, [rsp+2C0h+var_248]
0x18000ae36  mov     r9, r15
0x18000ae39  mov     rcx, [rsp+2C0h+var_280]
0x18000ae3e  mov     r8, r12
0x18000ae41  mov     edi, esi
0x18000ae43  call    QueryBasicLeaseInfov6
0x18000ae48  mov     ebx, eax
0x18000ae4a  test    eax, eax
0x18000ae4c  jnz     short loc_18000AEB9
0x18000ae4e  mov     rcx, [rsp+2C0h+var_280]
0x18000ae53  mov     rdx, r14
0x18000ae56  call    QueryDNSParamv6
0x18000ae5b  mov     ebx, eax
0x18000ae5d  test    eax, eax
0x18000ae5f  jnz     short loc_18000AEB9
0x18000ae61  mov     rax, [rsp+2C0h+var_280]
0x18000ae66  mov     ecx, [rax+88h]
0x18000ae6c  mov     [r13+0], ecx
0x18000ae70  mov     rcx, [rsp+2C0h+var_280]
0x18000ae75  add     rcx, 260h; SRWLock
0x18000ae7c  call    cs:__imp_ReleaseSRWLockShared
0x18000ae83  nop     dword ptr [rax+rax+00h]
0x18000ae88  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000ae8f  jz      short loc_18000AEE5
0x18000ae91  mov     r9, [rsp+2C0h+var_280]
0x18000ae96  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x18000ae9d  mov     edx, 2Dh ; '-'
0x18000aea2  mov     ecx, 404h
0x18000aea7  mov     r9, [r9+38h]
0x18000aeab  call    WPP_SF_S
0x18000aeb0  jmp     short loc_18000AEE5
0x18000aeb2  mov     ebx, 57h ; 'W'
0x18000aeb7  mov     edi, esi
0x18000aeb9  mov     rcx, [r15+8]; hMem
0x18000aebd  test    rcx, rcx
0x18000aec0  jnz     loc_18000B0DC
0x18000aec6  mov     rcx, [r12+8]; hMem
0x18000aecb  test    rcx, rcx
0x18000aece  jnz     loc_18000B09A
0x18000aed4  mov     rcx, [r14+38h]; hMem
0x18000aed8  test    rcx, rcx
0x18000aedb  jnz     loc_18000B0BB
0x18000aee1  test    edi, edi
0x18000aee3  jnz     short loc_18000AE70
0x18000aee5  test    esi, esi
0x18000aee7  jz      loc_18000AFCE
0x18000aeed  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000aef4  jz      short loc_18000AF1B
0x18000aef6  mov     rax, [rsp+2C0h+UnbiasedTime]
0x18000aefb  lea     r9, [rsp+2C0h+UnbiasedTime]
0x18000af00  mov     edx, 10h
0x18000af05  mov     [rsp+2C0h+PrivilegeSet], rax
0x18000af0a  mov     ecx, 40Eh
0x18000af0f  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000af16  call    WPP_SF_qq
0x18000af1b  cmp     cs:dword_18004271C, 0
0x18000af22  jz      short loc_18000AFA0
0x18000af24  lea     rcx, CriticalSection; lpCriticalSection
0x18000af2b  call    cs:__imp_EnterCriticalSection
0x18000af32  nop     dword ptr [rax+rax+00h]
0x18000af37  mov     rcx, qword ptr [rsp+2C0h+var_260]
0x18000af3c  lea     rax, [rsp+2C0h+var_260]
0x18000af41  cmp     [rcx+8], rax
0x18000af45  jnz     loc_18000B084
0x18000af4b  mov     rax, qword ptr [rsp+2C0h+var_260+8]
0x18000af50  lea     rdx, [rsp+2C0h+var_260]
0x18000af55  cmp     [rax], rdx
0x18000af58  jnz     loc_18000B084
0x18000af5e  mov     [rax], rcx
0x18000af61  mov     [rcx+8], rax
0x18000af65  lea     rax, [rsp+2C0h+var_260]
0x18000af6a  mov     qword ptr [rsp+2C0h+var_260+8], rax
0x18000af6f  lea     rax, [rsp+2C0h+var_260]
0x18000af74  mov     qword ptr [rsp+2C0h+var_260], rax
0x18000af79  lea     rax, qword_1800426C8
0x18000af80  cmp     cs:qword_1800426C8, rax
0x18000af87  jz      loc_18000B018
0x18000af8d  lea     rcx, CriticalSection; lpCriticalSection
0x18000af94  call    cs:__imp_LeaveCriticalSection
0x18000af9b  nop     dword ptr [rax+rax+00h]
0x18000afa0  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x18000afa7  jz      short loc_18000AFCE
0x18000afa9  mov     rax, [rsp+2C0h+UnbiasedTime]
0x18000afae  lea     r9, [rsp+2C0h+UnbiasedTime]
0x18000afb3  mov     edx, 11h
0x18000afb8  mov     [rsp+2C0h+PrivilegeSet], rax
0x18000afbd  mov     ecx, 40Eh
0x18000afc2  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18000afc9  call    WPP_SF_qq
0x18000afce  mov     rcx, [rsp+2C0h+var_280]
0x18000afd3  test    rcx, rcx
0x18000afd6  jz      short loc_18000AFEB
0x18000afd8  mov     eax, 0FFFFFFFFh
0x18000afdd  lock xadd [rcx+10h], eax
0x18000afe2  cmp     eax, 1
0x18000afe5  jz      loc_18000B08B
0x18000afeb  mov     eax, ebx
0x18000afed  mov     rcx, [rbp+1C0h+var_40]
0x18000aff4  xor     rcx, rsp; StackCookie
0x18000aff7  call    __security_check_cookie
0x18000affc  mov     rbx, [rsp+2C0h+arg_0]
0x18000b004  add     rsp, 290h
0x18000b00b  pop     r15
0x18000b00d  pop     r14
0x18000b00f  pop     r13
0x18000b011  pop     r12
0x18000b013  pop     rdi
0x18000b014  pop     rsi
0x18000b015  pop     rbp
0x18000b016  retn
0x18000b018  lea     rax, qword_1800426D8
  ... truncated ...
```
