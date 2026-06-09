# LsapGetClientInfoEx(_SECPKG_CLIENT_INFO_EX *,ulong)

- ea: `0x18000b7d0`
- end: `0x18000c0ea`
- name: `?LsapGetClientInfoEx@@YAJPEAU_SECPKG_CLIENT_INFO_EX@@K@Z`
- size: `2330`
- prototype: `__int64 __fastcall(struct _SECPKG_CLIENT_INFO_EX *, size_t Size)`
- caller_count: `22`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005d40`
- `0x180009734`
- `0x180009900`
- `0x18000a4f0`
- `0x18000aca0`
- `0x18000acb0`
- `0x18000d48c`
- `0x180023ec4`
- `0x1800246b0`
- `0x180024a70`
- `0x180025710`
- `0x180025a04`
- `0x18002da8c`
- `0x180056fec`
- `0x18005af80`
- `0x180073c40`
- `0x180077b00`
- `0x1800814f4`
- `0x18008dff8`
- `0x18009a340`
- `0x1800c0ec0`
- `0x1800cd0c0`

## callees

- `0x180008340`
- `0x18000b7d0`
- `0x180011278`
- `0x1800284d4`
- `0x18005608c`
- `0x1800b86d0`
- `0x1800b9304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b815`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b883`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b8da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b928`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b815`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b883`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b8da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b928`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bde8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bde8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bdd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bdd9`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18000ba51`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18000ba51`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bcc3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bfdf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bcc3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bfdf`
- `ntdll!NtClose` at `0x18000bcf8`
- `ntdll!NtClose` at `0x18000bf85`
- `ntdll!NtClose` at `0x18000c089`
- `ntdll!NtClose` at `0x18000bcf8`
- `ntdll!NtClose` at `0x18000bf85`
- `ntdll!NtClose` at `0x18000c089`
- `ntdll!RtlCapabilityCheck` at `0x18000bda5`
- `ntdll!RtlCapabilityCheck` at `0x18000bda5`
- `ntdll!RtlCheckTokenCapability` at `0x18000bb0f`
- `ntdll!RtlCheckTokenCapability` at `0x18000bb0f`
- `ntdll!RtlImpersonateSelfEx` at `0x18000bc62`
- `ntdll!RtlImpersonateSelfEx` at `0x18000bc62`
- `ntdll!NtQueryInformationProcess` at `0x18000bbd7`
- `ntdll!NtQueryInformationProcess` at `0x18000bbd7`
- `ntdll!RtlFreeSid` at `0x18000bb3a`
- `ntdll!RtlFreeSid` at `0x18000bb3a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000bac1`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000bac1`
- `ntdll!NtSetInformationThread` at `0x18000bd84`
- `ntdll!NtSetInformationThread` at `0x18000be27`
- `ntdll!NtSetInformationThread` at `0x18000bd84`
- `ntdll!NtSetInformationThread` at `0x18000be27`
- `ntdll!NtQueryInformationToken` at `0x18000b9e0`
- `ntdll!NtQueryInformationToken` at `0x18000baf0`
- `ntdll!NtQueryInformationToken` at `0x18000bcb5`
- `ntdll!NtQueryInformationToken` at `0x18000b9e0`
- `ntdll!NtQueryInformationToken` at `0x18000baf0`
- `ntdll!NtQueryInformationToken` at `0x18000bcb5`
- `ntdll!NtOpenThreadToken` at `0x18000b9a5`
- `ntdll!NtOpenThreadToken` at `0x18000bf4b`
- `ntdll!NtOpenThreadToken` at `0x18000b9a5`
- `ntdll!NtOpenThreadToken` at `0x18000bf4b`
- `RPCRT4!RpcRevertToSelf` at `0x18000b9f7`
- `RPCRT4!RpcRevertToSelf` at `0x18000bfce`
- `RPCRT4!RpcRevertToSelf` at `0x18000b9f7`
- `RPCRT4!RpcRevertToSelf` at `0x18000bfce`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b96e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c023`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b96e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c023`
- `RPCRT4!RpcImpersonateClient` at `0x18000b94c`
- `RPCRT4!RpcImpersonateClient` at `0x18000b94c`
- `RPCRT4!I_RpcOpenClientThread` at `0x18000bf26`
- `RPCRT4!I_RpcOpenClientThread` at `0x18000bf26`
- `lsass!LsaImpersonateKsecCaller` at `0x18000bc7f`
- `lsass!LsaImpersonateKsecCaller` at `0x18000bc7f`

## pseudocode

```c
__int64 __fastcall LsapGetClientInfoEx(struct _LUID *a1, size_t Size)
{
  unsigned int v2; // r14d
  struct _Session *Value; // r13
  char *v5; // rax
  HANDLE *v6; // rdi
  char *v7; // rax
  int v8; // r12d
  int v9; // r15d
  char *v10; // rsi
  _DWORD *v11; // rax
  RPC_STATUS v12; // eax
  NTSTATUS v13; // esi
  NTSTATUS v14; // eax
  void **v15; // r15
  bool v16; // zf
  LONG v17; // eax
  void *v18; // rcx
  void *v19; // r12
  bool v20; // r13
  char v21; // r14
  HANDLE v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int v28; // eax
  RPC_STATUS v29; // esi
  char v30; // [rsp+68h] [rbp-A0h] BYREF
  char v31; // [rsp+69h] [rbp-9Fh] BYREF
  int v32; // [rsp+6Ch] [rbp-9Ch] BYREF
  ULONG TokenInformationLength[2]; // [rsp+70h] [rbp-98h] BYREF
  PHANDLE TokenHandle; // [rsp+78h] [rbp-90h] BYREF
  ULONG ReturnLength; // [rsp+80h] [rbp-88h] BYREF
  HANDLE ThreadHandle; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v37[2]; // [rsp+90h] [rbp-78h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp-68h] BYREF
  __int128 TokenInformation; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v40; // [rsp+B8h] [rbp-50h]
  __int128 v41; // [rsp+C8h] [rbp-40h]
  __int64 v42; // [rsp+D8h] [rbp-30h]
  _OWORD ProcessInformation[2]; // [rsp+E0h] [rbp-28h] BYREF

  v2 = Size;
  if ( (unsigned int)(Size - 32) > 0x10 )
    return 3221225485LL;
  TokenInformationLength[0] = 56;
  Value = (struct _Session *)TlsGetValue(dwSession);
  v37[0] = 2359330;
  v42 = 0;
  ThreadHandle = 0;
  v37[1] = L"userPrincipalName";
  v31 = 0;
  TokenInformation = 0;
  v40 = 0;
  v41 = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(a1, 0, v2);
  if ( !Value )
    Value = pDefaultSession;
  v5 = (char *)TlsGetValue(dwCallInfo);
  v6 = (HANDLE *)v5;
  if ( !v5 )
  {
    a1[1].LowPart = GetCurrentProcessId();
    a1[1].HighPart = GetCurrentThreadId();
    LOWORD(a1[2].LowPart) = 1;
    a1[2].HighPart = 2;
    *a1 = SystemLogonId;
    return 0;
  }
  a1[1].LowPart = *((_DWORD *)v5 + 6);
  a1[1].HighPart = *((_DWORD *)v5 + 7);
  LOBYTE(a1[2].LowPart) = (*((_DWORD *)Value + 8) & 0x1002) != 0;
  if ( v5[62] )
  {
    *a1 = *(struct _LUID *)(v5 + 48);
    BYTE2(a1[2].LowPart) = v5[61];
    BYTE1(a1[2].LowPart) = v5[60];
    a1[2].HighPart = *((_DWORD *)v5 + 14);
    a1[3] = *(struct _LUID *)(v5 + 272);
    if ( v2 >= 0x30 )
    {
      a1[4] = *(struct _LUID *)(v5 + 464);
      a1[5] = *(struct _LUID *)(v5 + 472);
    }
    return 0;
  }
  v7 = (char *)TlsGetValue(dwCallInfo);
  if ( !v7 )
  {
    v13 = -1071513572;
    goto LABEL_72;
  }
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v10 = v7 + 272;
  TokenHandle = (PHANDLE)(v7 + 272);
  if ( *((_QWORD *)v7 + 34) )
  {
    if ( !v7[60] || *((int *)v7 + 14) >= 2 )
    {
      v14 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, v7 + 272, 8u);
      goto LABEL_17;
    }
    v13 = -1073741659;
    goto LABEL_81;
  }
  if ( *((_DWORD *)v7 + 16) )
  {
    if ( *((_QWORD *)v7 + 43) )
    {
      v13 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, v7 + 344, 8u);
      if ( v13 < 0 )
        goto LABEL_44;
      v32 = 1;
LABEL_16:
      v14 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, TokenHandle);
LABEL_17:
      v13 = v14;
      if ( v14 >= 0 )
      {
        v8 = v9;
        goto LABEL_19;
      }
      if ( v32 )
      {
        if ( v9 )
          RpcRevertToSelf();
        else
          RevertToSelf();
      }
      goto LABEL_44;
    }
LABEL_49:
    v14 = RtlImpersonateSelfEx(2, 0x2000000, v10);
    goto LABEL_17;
  }
  if ( (v7[32] & 0x20) != 0 )
  {
    v13 = -1073741558;
LABEL_72:
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_edf095b3158a35ed0e01973899680e9e_Traceguids,
        (unsigned int)v13);
    v15 = v6 + 34;
    goto LABEL_53;
  }
  v11 = TlsGetValue(dwSession);
  if ( !v11 )
    goto LABEL_49;
  if ( (v11[8] & 0x1000) != 0 && (int)LsaImpersonateKsecCaller(v10) >= 0 )
  {
    v15 = v6 + 34;
    v13 = NtQueryInformationToken(
            v6[34],
            TokenStatistics,
            &TokenInformation,
            TokenInformationLength[0],
            TokenInformationLength);
    goto LABEL_52;
  }
  v12 = RpcImpersonateClient(0);
  if ( v12 != 5 )
  {
    if ( v12 == 1765 )
    {
LABEL_45:
      HIBYTE(a1[2].LowPart) |= 2u;
      *((_DWORD *)v6 + 8) |= 0x80u;
      if ( NtQueryInformationProcess(*((HANDLE *)Value + 5), ProcessTimes, ProcessInformation, 0x20u, 0) >= 0
        && *((_QWORD *)&ProcessInformation[0] + 1) )
      {
        HIBYTE(a1[2].LowPart) |= 1u;
        *((_DWORD *)v6 + 8) |= 0x100u;
      }
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_edf095b3158a35ed0e01973899680e9e_Traceguids,
          a1[1].LowPart,
          a1[1].HighPart);
      return 0;
    }
    v13 = I_RpcMapWin32Status(v12);
    if ( v13 < 0 )
    {
LABEL_44:
      if ( v13 != -1073741281 && v13 != -1073741813 && v13 != -1073741769 )
      {
        if ( v13 != -1073741659 )
          goto LABEL_71;
        goto LABEL_81;
      }
      goto LABEL_45;
    }
    v32 = 1;
    v9 = 1;
    goto LABEL_16;
  }
  v13 = -1073741659;
LABEL_81:
  v15 = v6 + 34;
  if ( !v6[34] )
  {
    v28 = I_RpcOpenClientThread(0, 0x800u, &ThreadHandle);
    v29 = v28;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_edf095b3158a35ed0e01973899680e9e_Traceguids, v28);
      v13 = I_RpcMapWin32Status(v29);
      goto LABEL_40;
    }
    v13 = NtOpenThreadToken(ThreadHandle, 0x2000000u, 1u, v6 + 34);
  }
LABEL_71:
  if ( v13 < 0 )
    goto LABEL_72;
LABEL_19:
  v15 = v6 + 34;
  v13 = NtQueryInformationToken(
          v6[34],
          TokenStatistics,
          &TokenInformation,
          TokenInformationLength[0],
          TokenInformationLength);
  if ( !v8 )
  {
LABEL_52:
    RevertToSelf();
    goto LABEL_21;
  }
  RpcRevertToSelf();
LABEL_21:
  if ( v13 < 0 )
    goto LABEL_53;
  v16 = DWORD2(v40) == 1;
  *a1 = *(struct _LUID *)((char *)&TokenInformation + 8);
  if ( v16 )
  {
    BYTE1(a1[2].LowPart) = 0;
    a1[2].HighPart = 2;
  }
  else
  {
    v17 = HIDWORD(v40);
    BYTE1(a1[2].LowPart) = 1;
    a1[2].HighPart = v17;
    if ( v17 == 1 )
    {
      v25 = *v15;
      v6[59] = *v15;
      v6[58] = (HANDLE)*a1;
      if ( v2 >= 0x30 )
      {
        a1[4] = *a1;
        a1[5] = (struct _LUID)v25;
      }
      *a1 = LsapAnonymousLogonId;
      *v15 = 0;
      v13 = LsapOpenTokenByLogonIdEx(&LsapAnonymousLogonId, SecurityImpersonation, v15);
      if ( v13 < 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v27, v26);
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            WPP_edf095b3158a35ed0e01973899680e9e_Traceguids,
            (unsigned int)v13);
        }
        goto LABEL_53;
      }
      a1[3] = (struct _LUID)*v15;
    }
    else if ( v2 >= 0x30 )
    {
      a1[4] = LsapZeroLogonId;
      a1[5] = 0;
    }
  }
  v18 = *v15;
  BYTE2(a1[2].LowPart) = 0;
  if ( IsTokenRestricted(v18) )
    BYTE2(a1[2].LowPart) = 1;
  v19 = *v15;
  v20 = 0;
  v21 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  TokenHandle = 0;
  v32 = 0;
  ReturnLength = 0;
  v30 = 0;
  v13 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 3u, 8u, 0, 0, 0, 0, 0, 0, (PSID *)&TokenHandle);
  if ( v13 >= 0 )
  {
    v13 = NtQueryInformationToken(v19, TokenIsAppContainer, &v32, 4u, &ReturnLength);
    if ( v13 >= 0 )
    {
      v13 = RtlCheckTokenCapability(v19, TokenHandle, &v30);
      if ( v13 >= 0 )
      {
        v21 = v30;
        v20 = v32 != 0;
      }
    }
  }
  if ( TokenHandle )
    RtlFreeSid(TokenHandle);
  if ( v13 < 0 )
  {
LABEL_53:
    if ( *v15 )
    {
      NtClose(*v15);
      *v15 = 0;
    }
    v23 = v6[59];
    if ( v23 )
    {
      NtClose(v23);
      v6[59] = 0;
    }
    goto LABEL_41;
  }
  v6[6] = (HANDLE)*a1;
  *((_BYTE *)v6 + 61) = BYTE2(a1[2].LowPart);
  *((_BYTE *)v6 + 60) = BYTE1(a1[2].LowPart);
  *((_DWORD *)v6 + 14) = a1[2].HighPart;
  *((_BYTE *)v6 + 62) = 1;
  if ( v20 )
  {
    v24 = *v15;
    *((_DWORD *)v6 + 18) |= 1u;
    if ( (int)RtlCapabilityCheck(v24, v37, &v31) >= 0 && v31 == 1 )
      *((_DWORD *)v6 + 18) |= 8u;
  }
  if ( v21 )
    *((_DWORD *)v6 + 18) |= 2u;
  if ( a1[3] )
  {
LABEL_40:
    if ( v13 >= 0 )
      goto LABEL_41;
    goto LABEL_53;
  }
  a1[3] = (struct _LUID)*v15;
LABEL_41:
  if ( ThreadHandle )
    NtClose(ThreadHandle);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b7d0  mov     r11, rsp
0x18000b7d3  push    rbp
0x18000b7d4  push    rbx
0x18000b7d5  push    r14
0x18000b7d7  lea     rbp, [r11-38h]
0x18000b7db  sub     rsp, 120h
0x18000b7e2  mov     rax, cs:__security_cookie
0x18000b7e9  xor     rax, rsp
0x18000b7ec  mov     [rbp+30h+var_38], rax
0x18000b7f0  mov     r14d, edx
0x18000b7f3  mov     rbx, rcx
0x18000b7f6  lea     eax, [r14-20h]
0x18000b7fa  cmp     eax, 10h
0x18000b7fd  ja      loc_18000BF5E
0x18000b803  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x18000b809  mov     [r11+18h], rsi
0x18000b80d  mov     [r11-20h], rdi
0x18000b811  mov     [r11-30h], r13
0x18000b815  call    cs:__imp_TlsGetValue
0x18000b81c  nop     dword ptr [rax+rax+00h]
0x18000b821  xorps   xmm0, xmm0
0x18000b824  mov     [rsp+130h+TokenInformationLength], 38h ; '8'
0x18000b82c  mov     r13, rax
0x18000b82f  mov     [rbp+30h+var_A8], 240022h
0x18000b837  xor     eax, eax
0x18000b839  xor     esi, esi
0x18000b83b  mov     [rbp+30h+var_60], rax
0x18000b83f  mov     r8d, r14d; Size
0x18000b842  lea     rax, aUserprincipaln; "userPrincipalName"
0x18000b849  mov     [rbp+30h+ThreadHandle], rsi
0x18000b84d  xor     edx, edx; Val
0x18000b84f  mov     [rbp+30h+var_A0], rax
0x18000b853  mov     rcx, rbx; void *
0x18000b856  mov     byte ptr [rsp+130h+var_D0+1], sil
0x18000b85b  movups  [rbp+30h+TokenInformation], xmm0
0x18000b85f  movups  [rbp+30h+var_80], xmm0
0x18000b863  movups  [rbp+30h+var_70], xmm0
0x18000b867  movups  [rbp+30h+ProcessInformation], xmm0
0x18000b86b  movups  [rbp+30h+var_48], xmm0
0x18000b86f  call    memset_0
0x18000b874  test    r13, r13
0x18000b877  jz      loc_18000BDCD
0x18000b87d  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18000b883  call    cs:__imp_TlsGetValue
0x18000b88a  nop     dword ptr [rax+rax+00h]
0x18000b88f  mov     rdi, rax
0x18000b892  test    rax, rax
0x18000b895  jz      loc_18000BDD9
0x18000b89b  mov     eax, [rax+18h]
0x18000b89e  mov     [rbx+8], eax
0x18000b8a1  mov     eax, [rdi+1Ch]
0x18000b8a4  mov     [rbx+0Ch], eax
0x18000b8a7  test    dword ptr [r13+20h], 1002h
0x18000b8af  jz      loc_18000BE4D
0x18000b8b5  mov     al, 1
0x18000b8b7  mov     [rsp+130h+var_20], r12
0x18000b8bf  mov     [rsp+130h+var_30], r15
0x18000b8c7  mov     [rbx+10h], al
0x18000b8ca  cmp     [rdi+3Eh], sil
0x18000b8ce  jnz     loc_18000BD14
0x18000b8d4  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18000b8da  call    cs:__imp_TlsGetValue
0x18000b8e1  nop     dword ptr [rax+rax+00h]
0x18000b8e6  test    rax, rax
0x18000b8e9  jz      loc_18000BF96
0x18000b8ef  mov     r12d, esi
0x18000b8f2  mov     [rsp+130h+var_CC], esi
0x18000b8f6  mov     r15d, esi
0x18000b8f9  lea     rsi, [rax+110h]
0x18000b900  mov     [rsp+130h+TokenHandle], rsi
0x18000b905  cmp     [rsi], r12
0x18000b908  jnz     loc_18000BD5F
0x18000b90e  cmp     [rax+40h], r15d
0x18000b912  jnz     loc_18000BC45
0x18000b918  test    byte ptr [rax+20h], 20h
0x18000b91c  jnz     loc_18000BFAA
0x18000b922  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x18000b928  call    cs:__imp_TlsGetValue
0x18000b92f  nop     dword ptr [rax+rax+00h]
0x18000b934  test    rax, rax
0x18000b937  jz      loc_18000BC55
0x18000b93d  test    dword ptr [rax+20h], 1000h
0x18000b944  jnz     loc_18000BC7C
0x18000b94a  xor     ecx, ecx; BindingHandle
0x18000b94c  call    cs:__imp_RpcImpersonateClient
0x18000b953  nop     dword ptr [rax+rax+00h]
0x18000b958  cmp     eax, 5
0x18000b95b  jz      loc_18000BFB4
0x18000b961  cmp     eax, 6E5h
0x18000b966  jz      loc_18000BBB4
0x18000b96c  mov     ecx, eax; Status
0x18000b96e  call    cs:__imp_I_RpcMapWin32Status
0x18000b975  nop     dword ptr [rax+rax+00h]
0x18000b97a  mov     esi, eax
0x18000b97c  test    eax, eax
0x18000b97e  js      loc_18000BBA8
0x18000b984  mov     eax, 1
0x18000b989  mov     [rsp+130h+var_CC], eax
0x18000b98d  mov     r15d, eax
0x18000b990  movzx   r8d, al; OpenAsSelf
0x18000b994  mov     r9, [rsp+130h+TokenHandle]; TokenHandle
0x18000b999  mov     edx, 2000000h; DesiredAccess
0x18000b99e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000b9a5  call    cs:__imp_NtOpenThreadToken
0x18000b9ac  nop     dword ptr [rax+rax+00h]
0x18000b9b1  mov     esi, eax
0x18000b9b3  test    eax, eax
0x18000b9b5  js      loc_18000BFBE
0x18000b9bb  mov     r12d, r15d
0x18000b9be  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x18000b9c3  lea     rax, [rsp+130h+TokenInformationLength]
0x18000b9c8  lea     r15, [rdi+110h]
0x18000b9cf  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18000b9d4  mov     rcx, [r15]; TokenHandle
0x18000b9d7  lea     r8, [rbp+30h+TokenInformation]; TokenInformation
0x18000b9db  mov     edx, 0Ah; TokenInformationClass
0x18000b9e0  call    cs:__imp_NtQueryInformationToken
0x18000b9e7  nop     dword ptr [rax+rax+00h]
0x18000b9ec  mov     esi, eax
0x18000b9ee  test    r12d, r12d
0x18000b9f1  jz      loc_18000BCC3
0x18000b9f7  call    cs:__imp_RpcRevertToSelf
0x18000b9fe  nop     dword ptr [rax+rax+00h]
0x18000ba03  test    esi, esi
0x18000ba05  js      loc_18000BCD4
0x18000ba0b  cmp     dword ptr [rbp+30h+var_80+8], 1
0x18000ba0f  mov     rax, qword ptr [rbp+30h+TokenInformation+8]
0x18000ba13  mov     [rbx], rax
0x18000ba16  jz      loc_18000C036
0x18000ba1c  mov     eax, dword ptr [rbp+30h+var_80+0Ch]
0x18000ba1f  mov     byte ptr [rbx+11h], 1
0x18000ba23  mov     [rbx+14h], eax
0x18000ba26  cmp     eax, 1
0x18000ba29  jz      loc_18000BEA9
0x18000ba2f  cmp     r14d, 30h ; '0'
0x18000ba33  jb      loc_18000BF04
0x18000ba39  mov     rax, cs:?LsapZeroLogonId@@3U_LUID@@A; _LUID LsapZeroLogonId
0x18000ba40  xor     esi, esi
0x18000ba42  mov     [rbx+20h], rax
0x18000ba46  mov     [rbx+28h], rsi
0x18000ba4a  mov     rcx, [r15]; TokenHandle
0x18000ba4d  mov     byte ptr [rbx+12h], 0
0x18000ba51  call    cs:__imp_IsTokenRestricted
0x18000ba58  nop     dword ptr [rax+rax+00h]
0x18000ba5d  test    eax, eax
0x18000ba5f  jnz     loc_18000BC73
0x18000ba65  mov     r12, [r15]
0x18000ba68  lea     rax, [rsp+130h+TokenHandle]
0x18000ba6d  mov     [rsp+50h], rax; Sid
0x18000ba72  lea     rcx, [rbp+30h+IdentifierAuthority]; IdentifierAuthority
0x18000ba76  mov     [rsp+130h+SubAuthority7], esi; SubAuthority7
0x18000ba7a  mov     r9d, 8; SubAuthority1
0x18000ba80  mov     [rsp+130h+SubAuthority6], esi; SubAuthority6
0x18000ba84  mov     r8d, 3; SubAuthority0
0x18000ba8a  mov     [rsp+130h+SubAuthority5], esi; SubAuthority5
0x18000ba8e  mov     dl, 2; SubAuthorityCount
0x18000ba90  mov     [rsp+130h+SubAuthority4], esi; SubAuthority4
0x18000ba94  xor     r13b, r13b
0x18000ba97  mov     [rsp+130h+SubAuthority3], esi; SubAuthority3
0x18000ba9b  xor     r14b, r14b
0x18000ba9e  mov     dword ptr [rsp+130h+ReturnLength], esi; SubAuthority2
0x18000baa2  mov     dword ptr [rbp+30h+IdentifierAuthority.Value], 0
0x18000baa9  mov     word ptr [rbp+30h+IdentifierAuthority.Value+4], 0F00h
0x18000baaf  mov     [rsp+130h+TokenHandle], rsi
0x18000bab4  mov     [rsp+130h+var_CC], esi
0x18000bab8  mov     [rsp+130h+var_B8], esi
0x18000babc  mov     byte ptr [rsp+130h+var_D0], 0
0x18000bac1  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000bac8  nop     dword ptr [rax+rax+00h]
0x18000bacd  mov     esi, eax
0x18000bacf  test    eax, eax
0x18000bad1  js      short loc_18000BB30
0x18000bad3  lea     rax, [rsp+130h+var_B8]
0x18000bad8  mov     r9d, 4; TokenInformationLength
0x18000bade  lea     r8, [rsp+130h+var_CC]; TokenInformation
0x18000bae3  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18000bae8  mov     edx, 1Dh; TokenInformationClass
0x18000baed  mov     rcx, r12; TokenHandle
0x18000baf0  call    cs:__imp_NtQueryInformationToken
0x18000baf7  nop     dword ptr [rax+rax+00h]
0x18000bafc  mov     esi, eax
0x18000bafe  test    eax, eax
0x18000bb00  js      short loc_18000BB30
0x18000bb02  mov     rdx, [rsp+130h+TokenHandle]
0x18000bb07  lea     r8, [rsp+130h+var_D0]
0x18000bb0c  mov     rcx, r12
0x18000bb0f  call    cs:__imp_RtlCheckTokenCapability
0x18000bb16  nop     dword ptr [rax+rax+00h]
0x18000bb1b  mov     esi, eax
0x18000bb1d  test    eax, eax
0x18000bb1f  js      short loc_18000BB30
0x18000bb21  cmp     [rsp+130h+var_CC], 0
0x18000bb26  movzx   r14d, byte ptr [rsp+130h+var_D0]
0x18000bb2c  setnz   r13b
0x18000bb30  mov     rcx, [rsp+130h+TokenHandle]; Sid
0x18000bb35  test    rcx, rcx
0x18000bb38  jz      short loc_18000BB46
0x18000bb3a  call    cs:__imp_RtlFreeSid
0x18000bb41  nop     dword ptr [rax+rax+00h]
0x18000bb46  test    esi, esi
0x18000bb48  js      loc_18000BCD4
0x18000bb4e  mov     rax, [rbx]
0x18000bb51  mov     [rdi+30h], rax
0x18000bb55  movzx   eax, byte ptr [rbx+12h]
0x18000bb59  mov     [rdi+3Dh], al
0x18000bb5c  movzx   eax, byte ptr [rbx+11h]
0x18000bb60  mov     [rdi+3Ch], al
0x18000bb63  mov     eax, [rbx+14h]
0x18000bb66  mov     [rdi+38h], eax
0x18000bb69  mov     byte ptr [rdi+3Eh], 1
0x18000bb6d  test    r13b, r13b
0x18000bb70  jnz     loc_18000BD95
0x18000bb76  test    r14b, r14b
0x18000bb79  jz      short loc_18000BB7F
0x18000bb7b  or      dword ptr [rdi+48h], 2
0x18000bb7f  cmp     qword ptr [rbx+18h], 0
0x18000bb84  jnz     short loc_18000BB8F
0x18000bb86  mov     rax, [r15]
0x18000bb89  mov     [rbx+18h], rax
0x18000bb8d  jmp     short loc_18000BB97
0x18000bb8f  test    esi, esi
0x18000bb91  js      loc_18000BCD4
0x18000bb97  mov     rcx, [rbp+30h+ThreadHandle]; Handle
0x18000bb9b  test    rcx, rcx
0x18000bb9e  jnz     loc_18000BF85
0x18000bba4  mov     eax, esi
0x18000bba6  jmp     short loc_18000BC04
0x18000bba8  cmp     esi, 0C000021Fh
0x18000bbae  jnz     loc_18000BE54
0x18000bbb4  or      byte ptr [rbx+13h], 2
0x18000bbb8  lea     r8, [rbp+30h+ProcessInformation]; ProcessInformation
0x18000bbbc  or      dword ptr [rdi+20h], 80h
0x18000bbc3  mov     r9d, 20h ; ' '; ProcessInformationLength
0x18000bbc9  mov     rcx, [r13+28h]; ProcessHandle
0x18000bbcd  mov     edx, 4; ProcessInformationClass
0x18000bbd2  mov     [rsp+130h+ReturnLength], r12; ReturnLength
0x18000bbd7  call    cs:__imp_NtQueryInformationProcess
0x18000bbde  nop     dword ptr [rax+rax+00h]
0x18000bbe3  test    eax, eax
0x18000bbe5  jns     loc_18000C0A1
0x18000bbeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbf2  lea     r8, WPP_GLOBAL_Control
0x18000bbf9  cmp     rcx, r8
0x18000bbfc  jnz     loc_18000C0BB
0x18000bc02  xor     eax, eax
0x18000bc04  mov     r12, [rsp+130h+var_20]
0x18000bc0c  mov     r15, [rsp+130h+var_30]
0x18000bc14  mov     rdi, [rsp+118h]
0x18000bc1c  mov     rsi, [rsp+130h+arg_10]
0x18000bc24  mov     r13, [rsp+130h+var_28]
0x18000bc2c  mov     rcx, [rbp+30h+var_38]
0x18000bc30  xor     rcx, rsp; StackCookie
0x18000bc33  call    __security_check_cookie
0x18000bc38  add     rsp, 120h
0x18000bc3f  pop     r14
0x18000bc41  pop     rbx
0x18000bc42  pop     rbp
0x18000bc43  retn
0x18000bc45  lea     r8, [rax+158h]; ThreadInformation
0x18000bc4c  cmp     [r8], r12
0x18000bc4f  jnz     loc_18000BE15
0x18000bc55  mov     r8, rsi
0x18000bc58  mov     edx, 2000000h
0x18000bc5d  mov     ecx, 2
0x18000bc62  call    cs:__imp_RtlImpersonateSelfEx
0x18000bc69  nop     dword ptr [rax+rax+00h]
0x18000bc6e  jmp     loc_18000B9B1
0x18000bc73  mov     byte ptr [rbx+12h], 1
0x18000bc77  jmp     loc_18000BA65
0x18000bc7c  mov     rcx, rsi
0x18000bc7f  call    cs:__imp_LsaImpersonateKsecCaller
0x18000bc86  nop     dword ptr [rax+rax+00h]
0x18000bc8b  test    eax, eax
0x18000bc8d  js      loc_18000B94A
0x18000bc93  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x18000bc98  lea     rax, [rsp+130h+TokenInformationLength]
0x18000bc9d  lea     r15, [rdi+110h]
0x18000bca4  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18000bca9  mov     rcx, [r15]; TokenHandle
0x18000bcac  lea     r8, [rbp+30h+TokenInformation]; TokenInformation
0x18000bcb0  mov     edx, 0Ah; TokenInformationClass
0x18000bcb5  call    cs:__imp_NtQueryInformationToken
0x18000bcbc  nop     dword ptr [rax+rax+00h]
0x18000bcc1  mov     esi, eax
0x18000bcc3  call    cs:__imp_RevertToSelf
0x18000bcca  nop     dword ptr [rax+rax+00h]
0x18000bccf  jmp     loc_18000BA03
0x18000bcd4  mov     rcx, [r15]; Handle
0x18000bcd7  test    rcx, rcx
0x18000bcda  jnz     loc_18000C089
0x18000bce0  test    esi, esi
0x18000bce2  jns     loc_18000BB97
0x18000bce8  mov     rcx, [rdi+1D8h]; Handle
0x18000bcef  test    rcx, rcx
0x18000bcf2  jz      loc_18000BB97
0x18000bcf8  call    cs:__imp_NtClose
0x18000bcff  nop     dword ptr [rax+rax+00h]
0x18000bd04  mov     qword ptr [rdi+1D8h], 0
0x18000bd0f  jmp     loc_18000BB97
0x18000bd14  mov     rax, [rdi+30h]
  ... truncated ...
```
