# DsrCmdJoinHelper::PurgeKerbCache(bool,bool,bool)

- ea: `0x1800b1dac`
- end: `0x1800b2155`
- name: `?PurgeKerbCache@DsrCmdJoinHelper@@SAJ_N00@Z`
- size: `937`
- prototype: `__int64 __fastcall(bool, bool, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ae820`
- `0x1800aee10`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x18001c9b4`
- `0x180031a78`
- `0x1800420f0`
- `0x180042628`
- `0x180044300`
- `0x180044d30`
- `0x1800b1dac`

## import_xrefs

- `SspiCli!LsaConnectUntrusted` at `0x1800b1e53`
- `SspiCli!LsaConnectUntrusted` at `0x1800b1e53`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800b1f4b`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800b1f4b`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800b1fd7`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800b205f`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800b20f5`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800b1fd7`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800b205f`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800b20f5`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800b1ea5`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800b1ea5`

## string_xrefs

- `0x1800b1ee8`: `GetCurrentUserTokenInfo`
- `0x1800b1de8`: `DsrCmdJoinHelper::PurgeKerbCache`
- `0x1800b2076`: `%s: LsaCallAuthenticationPackage(KerbPurgeKdcProxyCacheMessage) failed with NTSTATUS: 0x%08x; SUBSTATUS: 0x%08x.`
- `0x1800b208c`: `KerbPurgeKdcProxyCacheMessage`
- `0x1800b1ff1`: `%s: LsaCallAuthenticationPackage(KerbPurgeTicketCacheExMessage) failed with NTSTATUS: 0x%08x; SUBSTATUS: 0x%08x.`
- `0x1800b2004`: `KerbPurgeTicketCacheExMessage`

## pseudocode

```c
__int64 __fastcall DsrCmdJoinHelper::PurgeKerbCache(__int64 a1, __int64 a2, char a3)
{
  const wchar_t *v4; // rax
  NTSTATUS v5; // eax
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  unsigned int *v8; // r8
  int CurrentUserTokenInfo; // eax
  void *v10; // rsi
  unsigned int v11; // edi
  __int64 v12; // rbx
  int v13; // eax
  NTSTATUS v14; // edi
  NTSTATUS v15; // eax
  NTSTATUS v17; // eax
  int v18; // r14d
  unsigned int v19; // edi
  unsigned int v20; // edi
  unsigned int v21; // r9d
  int ProtocolStatus; // [rsp+40h] [rbp-99h] BYREF
  ULONG AuthenticationPackage; // [rsp+44h] [rbp-95h] BYREF
  void *LsaHandle; // [rsp+48h] [rbp-91h] BYREF
  struct _LSA_STRING PackageName; // [rsp+50h] [rbp-89h] BYREF
  __int64 v26; // [rsp+60h] [rbp-79h] BYREF
  void *lpMem; // [rsp+68h] [rbp-71h] BYREF
  int ProtocolSubmitBuffer; // [rsp+70h] [rbp-69h] BYREF
  __int64 v29; // [rsp+74h] [rbp-65h]
  int v30; // [rsp+7Ch] [rbp-5Dh]
  __int128 v31; // [rsp+E0h] [rbp+7h] BYREF

  v4 = L"TRUE";
  if ( !a3 )
    v4 = L"FALSE";
  Logger::TraceVerbose(
    (wchar_t *)L"%s started. Tickets: %s. Proxy: %s. Policy: %s.",
    L"DsrCmdJoinHelper::PurgeKerbCache",
    L"TRUE",
    L"TRUE",
    v4);
  ProtocolStatus = 0;
  LsaHandle = 0;
  AuthenticationPackage = 0;
  PackageName = 0;
  memset_0(&ProtocolSubmitBuffer, 0, 0x70u);
  v26 = 0;
  v31 = 0;
  v5 = LsaConnectUntrusted(&LsaHandle);
  v6 = v5;
  if ( v5 < 0 )
  {
    Logger::WriteLsaConnectFailureEvent(v5);
    Logger::TraceError(
      L"%s: LsaConnectUntrusted failed with NTSTATUS: 0x%08x.",
      L"DsrCmdJoinHelper::PurgeKerbCache",
      (unsigned int)v6);
    goto LABEL_37;
  }
  PackageName.Buffer = "Kerberos";
  *(_DWORD *)&PackageName.Length = 524296;
  v7 = LsaLookupAuthenticationPackage(LsaHandle, &PackageName, &AuthenticationPackage);
  v6 = v7;
  if ( v7 < 0 )
  {
    Logger::WriteLsaLookupAuthPackageFailureEvent(PackageName.Buffer, v7);
    Logger::TraceError(
      L"%s: LsaLookupAuthenticationPackage failed with NTSTATUS: 0x%08x.",
      L"DsrCmdJoinHelper::PurgeKerbCache",
      (unsigned int)v6);
LABEL_37:
    v14 = v6;
    goto LABEL_15;
  }
  lpMem = 0;
  CurrentUserTokenInfo = GetCurrentUserTokenInfo(TokenStatistics, &lpMem, v8);
  v10 = lpMem;
  v11 = CurrentUserTokenInfo;
  if ( CurrentUserTokenInfo >= 0 )
  {
    v12 = *((_QWORD *)lpMem + 1);
  }
  else
  {
    v12 = 0;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"GetCurrentUserLogonId",
      L"GetCurrentUserTokenInfo",
      (unsigned int)CurrentUserTokenInfo);
  }
  SafeFree(v10);
  if ( (v11 & 0x80000000) == 0 )
  {
    ProtocolSubmitBuffer = 15;
    v29 = v12;
    v30 = 1;
    v17 = LsaCallAuthenticationPackage(
            LsaHandle,
            AuthenticationPackage,
            &ProtocolSubmitBuffer,
            0x70u,
            0,
            0,
            &ProtocolStatus);
    v18 = v17;
    if ( v17 < 0 || ProtocolStatus < 0 )
    {
      Logger::TraceError(
        L"%s: LsaCallAuthenticationPackage(KerbPurgeTicketCacheExMessage) failed with NTSTATUS: 0x%08x; SUBSTATUS: 0x%08x.",
        L"DsrCmdJoinHelper::PurgeKerbCache",
        (unsigned int)v17,
        (unsigned int)ProtocolStatus);
      v19 = ProtocolStatus;
      if ( v18 < 0 )
        v19 = v18;
      Logger::WriteLsaAuthFailureEvent(AuthenticationPackage, PackageName.Buffer, L"KerbPurgeTicketCacheExMessage", v19);
      v11 = v19 | 0x10000000;
    }
    LODWORD(v31) = 24;
    *((_QWORD *)&v31 + 1) = v12;
    v6 = LsaCallAuthenticationPackage(LsaHandle, AuthenticationPackage, &v31, 0x10u, 0, 0, &ProtocolStatus);
    v13 = ProtocolStatus;
    if ( v6 < 0 || ProtocolStatus < 0 )
    {
      Logger::TraceError(
        L"%s: LsaCallAuthenticationPackage(KerbPurgeKdcProxyCacheMessage) failed with NTSTATUS: 0x%08x; SUBSTATUS: 0x%08x.",
        L"DsrCmdJoinHelper::PurgeKerbCache",
        (unsigned int)v6,
        (unsigned int)ProtocolStatus);
      v20 = ProtocolStatus;
      if ( v6 < 0 )
        v20 = v6;
      Logger::WriteLsaAuthFailureEvent(AuthenticationPackage, PackageName.Buffer, L"KerbPurgeKdcProxyCacheMessage", v20);
      v13 = ProtocolStatus;
      v11 = v20 | 0x10000000;
    }
    if ( a3 )
    {
      v26 = 0x100000023LL;
      v6 = LsaCallAuthenticationPackage(LsaHandle, AuthenticationPackage, &v26, 8u, 0, 0, &ProtocolStatus);
      if ( v6 >= 0 && ProtocolStatus >= 0 )
        goto LABEL_16;
      Logger::TraceError(
        L"%s: LsaCallAuthenticationPackage(KerbRefreshPolicyMessage) failed with NTSTATUS: 0x%08x; SUBSTATUS: 0x%08x.",
        L"DsrCmdJoinHelper::PurgeKerbCache",
        (unsigned int)v6,
        (unsigned int)ProtocolStatus);
      v21 = ProtocolStatus;
      if ( v6 < 0 )
        v21 = v6;
      Logger::WriteLsaAuthFailureEvent(AuthenticationPackage, PackageName.Buffer, L"KerbRefreshPolicyMessage", v21);
      v13 = ProtocolStatus;
    }
    if ( v6 < 0 )
      goto LABEL_37;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrCmdJoinHelper::PurgeKerbCache",
      L"GetCurrentUserLogonId",
      v11);
    v13 = ProtocolStatus;
  }
  if ( v13 < 0 )
  {
    v14 = v13;
LABEL_15:
    v11 = v14 | 0x10000000;
  }
LABEL_16:
  if ( LsaHandle )
  {
    v15 = LsaDeregisterLogonProcess(LsaHandle);
    if ( v15 < 0 )
      Logger::TraceWarning(
        (wchar_t *)L"%s: LsaDeregisterLogonProcess failed with NTSTATUS: 0x%08x.",
        L"DsrCmdJoinHelper::PurgeKerbCache",
        (unsigned int)v15);
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DsrCmdJoinHelper::PurgeKerbCache", v11);
  return v11;
}

```

## disassembly

```asm
0x1800b1dac  push    rbp
0x1800b1dae  push    rbx
0x1800b1daf  push    rsi
0x1800b1db0  push    rdi
0x1800b1db1  push    r13
0x1800b1db3  push    r14
0x1800b1db5  push    r15
0x1800b1db7  lea     rbp, [rsp-27h]
0x1800b1dbc  sub     rsp, 100h
0x1800b1dc3  mov     rax, cs:__security_cookie
0x1800b1dca  xor     rax, rsp
0x1800b1dcd  mov     [rbp+57h+var_40], rax
0x1800b1dd1  mov     r15b, r8b
0x1800b1dd4  lea     rcx, aFalse_0; "FALSE"
0x1800b1ddb  lea     r8, aTrue_0; "TRUE"
0x1800b1de2  test    r15b, r15b
0x1800b1de5  mov     rax, r8
0x1800b1de8  lea     r13, aDsrcmdjoinhelp_2; "DsrCmdJoinHelper::PurgeKerbCache"
0x1800b1def  cmovz   rax, rcx
0x1800b1df3  mov     r9, r8
0x1800b1df6  lea     rcx, aSStartedTicket; "%s started. Tickets: %s. Proxy: %s. Pol"...
0x1800b1dfd  mov     [rsp+130h+ProtocolReturnBuffer], rax
0x1800b1e02  mov     rdx, r13
0x1800b1e05  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b1e0a  xorps   xmm0, xmm0
0x1800b1e0d  mov     [rsp+130h+var_F0], 0
0x1800b1e15  mov     r14d, 70h ; 'p'
0x1800b1e1b  mov     [rsp+130h+LsaHandle], 0
0x1800b1e24  mov     r8d, r14d; Size
0x1800b1e27  mov     [rsp+130h+AuthenticationPackage], 0
0x1800b1e2f  xor     edx, edx; Val
0x1800b1e31  lea     rcx, [rbp+57h+ProtocolSubmitBuffer]; void *
0x1800b1e35  movups  xmmword ptr [rsp+130h+PackageName.Length], xmm0
0x1800b1e3a  call    memset_0
0x1800b1e3f  xorps   xmm0, xmm0
0x1800b1e42  mov     [rbp+57h+var_D0], 0
0x1800b1e4a  lea     rcx, [rsp+130h+LsaHandle]; LsaHandle
0x1800b1e4f  movups  [rbp+57h+var_50], xmm0
0x1800b1e53  call    cs:__imp_LsaConnectUntrusted
0x1800b1e59  mov     ebx, eax
0x1800b1e5b  mov     esi, 10000000h
0x1800b1e60  test    eax, eax
0x1800b1e62  jns     short loc_1800B1E82
0x1800b1e64  mov     ecx, eax; unsigned int
0x1800b1e66  call    ?WriteLsaConnectFailureEvent@Logger@@SAJK@Z; Logger::WriteLsaConnectFailureEvent(ulong)
0x1800b1e6b  lea     rcx, aSLsaconnectunt; "%s: LsaConnectUntrusted failed with NTS"...
0x1800b1e72  mov     rdx, r13
0x1800b1e75  mov     r8d, ebx
0x1800b1e78  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b1e7d  jmp     loc_1800B214E
0x1800b1e82  mov     rcx, [rsp+130h+LsaHandle]; LsaHandle
0x1800b1e87  lea     rax, aKerberos_0; "Kerberos"
0x1800b1e8e  lea     r8, [rsp+130h+AuthenticationPackage]; AuthenticationPackage
0x1800b1e93  mov     [rsp+130h+PackageName.Buffer], rax
0x1800b1e98  lea     rdx, [rsp+130h+PackageName]; PackageName
0x1800b1e9d  mov     dword ptr [rsp+130h+PackageName.Length], 80008h
0x1800b1ea5  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800b1eab  mov     ebx, eax
0x1800b1ead  test    eax, eax
0x1800b1eaf  jns     short loc_1800B1EC6
0x1800b1eb1  mov     rcx, [rsp+130h+PackageName.Buffer]; char *
0x1800b1eb6  mov     edx, eax; unsigned int
0x1800b1eb8  call    ?WriteLsaLookupAuthPackageFailureEvent@Logger@@SAJPEBDK@Z; Logger::WriteLsaLookupAuthPackageFailureEvent(char const *,ulong)
0x1800b1ebd  lea     rcx, aSLsalookupauth; "%s: LsaLookupAuthenticationPackage fail"...
0x1800b1ec4  jmp     short loc_1800B1E72
0x1800b1ec6  lea     rdx, [rbp+57h+lpMem]; void **
0x1800b1eca  mov     [rbp+57h+lpMem], 0
0x1800b1ed2  mov     ecx, 0Ah; TokenInformationClass
0x1800b1ed7  call    ?GetCurrentUserTokenInfo@@YAJW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z; GetCurrentUserTokenInfo(_TOKEN_INFORMATION_CLASS,void * *,ulong *)
0x1800b1edc  mov     rsi, [rbp+57h+lpMem]
0x1800b1ee0  mov     edi, eax
0x1800b1ee2  test    eax, eax
0x1800b1ee4  jns     short loc_1800B1F07
0x1800b1ee6  xor     ebx, ebx
0x1800b1ee8  lea     r8, aGetcurrentuser_1; "GetCurrentUserTokenInfo"
0x1800b1eef  mov     r9d, eax
0x1800b1ef2  lea     rdx, aGetcurrentuser; "GetCurrentUserLogonId"
0x1800b1ef9  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b1f00  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b1f05  jmp     short loc_1800B1F0B
0x1800b1f07  mov     rbx, [rsi+8]
0x1800b1f0b  mov     rcx, rsi; lpMem
0x1800b1f0e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800b1f13  mov     esi, 10000000h
0x1800b1f18  test    edi, edi
0x1800b1f1a  jns     short loc_1800B1F99
0x1800b1f1c  mov     r9d, edi
0x1800b1f1f  lea     r8, aGetcurrentuser; "GetCurrentUserLogonId"
0x1800b1f26  mov     rdx, r13
0x1800b1f29  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b1f30  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b1f35  mov     eax, [rsp+130h+var_F0]
0x1800b1f39  test    eax, eax
0x1800b1f3b  jns     short loc_1800B1F41
0x1800b1f3d  mov     edi, eax
0x1800b1f3f  or      edi, esi
0x1800b1f41  mov     rcx, [rsp+130h+LsaHandle]; LsaHandle
0x1800b1f46  test    rcx, rcx
0x1800b1f49  jz      short loc_1800B1F67
0x1800b1f4b  call    cs:__imp_LsaDeregisterLogonProcess
0x1800b1f51  test    eax, eax
0x1800b1f53  jns     short loc_1800B1F67
0x1800b1f55  mov     r8d, eax
0x1800b1f58  lea     rcx, aSLsaderegister_1; "%s: LsaDeregisterLogonProcess failed wi"...
0x1800b1f5f  mov     rdx, r13
0x1800b1f62  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800b1f67  mov     r8d, edi
0x1800b1f6a  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800b1f71  mov     rdx, r13
0x1800b1f74  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b1f79  mov     eax, edi
0x1800b1f7b  mov     rcx, [rbp+57h+var_40]
0x1800b1f7f  xor     rcx, rsp; StackCookie
0x1800b1f82  call    __security_check_cookie
0x1800b1f87  add     rsp, 100h
0x1800b1f8e  pop     r15
0x1800b1f90  pop     r14
0x1800b1f92  pop     r13
0x1800b1f94  pop     rdi
0x1800b1f95  pop     rsi
0x1800b1f96  pop     rbx
0x1800b1f97  pop     rbp
0x1800b1f98  retn
0x1800b1f99  mov     edx, [rsp+130h+AuthenticationPackage]; AuthenticationPackage
0x1800b1f9d  lea     rax, [rsp+130h+var_F0]
0x1800b1fa2  mov     rcx, [rsp+130h+LsaHandle]; LsaHandle
0x1800b1fa7  lea     r8, [rbp+57h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x1800b1fab  mov     [rsp+130h+ProtocolStatus], rax; ProtocolStatus
0x1800b1fb0  mov     r9d, r14d; SubmitBufferLength
0x1800b1fb3  mov     [rsp+130h+ReturnBufferLength], 0; ReturnBufferLength
0x1800b1fbc  mov     [rsp+130h+ProtocolReturnBuffer], 0; ProtocolReturnBuffer
0x1800b1fc5  mov     [rbp+57h+ProtocolSubmitBuffer], 0Fh
0x1800b1fcc  mov     [rbp+57h+var_BC], rbx
0x1800b1fd0  mov     [rbp+57h+var_B4], 1
0x1800b1fd7  call    cs:__imp_LsaCallAuthenticationPackage
0x1800b1fdd  mov     r9d, [rsp+130h+var_F0]
0x1800b1fe2  mov     r14d, eax
0x1800b1fe5  test    eax, eax
0x1800b1fe7  js      short loc_1800B1FEE
0x1800b1fe9  test    r9d, r9d
0x1800b1fec  jns     short loc_1800B2025
0x1800b1fee  mov     r8d, r14d
0x1800b1ff1  lea     rcx, aSLsacallauthen_7; "%s: LsaCallAuthenticationPackage(KerbPu"...
0x1800b1ff8  mov     rdx, r13
0x1800b1ffb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b2000  mov     edi, [rsp+130h+var_F0]
0x1800b2004  lea     r8, aKerbpurgeticke; "KerbPurgeTicketCacheExMessage"
0x1800b200b  mov     rdx, [rsp+130h+PackageName.Buffer]; char *
0x1800b2010  test    r14d, r14d
0x1800b2013  mov     ecx, [rsp+130h+AuthenticationPackage]; unsigned int
0x1800b2017  cmovs   edi, r14d
0x1800b201b  mov     r9d, edi; unsigned int
0x1800b201e  call    ?WriteLsaAuthFailureEvent@Logger@@SAJKPEBDPEBGK@Z; Logger::WriteLsaAuthFailureEvent(ulong,char const *,ushort const *,ulong)
0x1800b2023  or      edi, esi
0x1800b2025  mov     edx, [rsp+130h+AuthenticationPackage]; AuthenticationPackage
0x1800b2029  lea     rax, [rsp+130h+var_F0]
0x1800b202e  mov     rcx, [rsp+130h+LsaHandle]; LsaHandle
0x1800b2033  lea     r8, [rbp+57h+var_50]; ProtocolSubmitBuffer
0x1800b2037  mov     [rsp+130h+ProtocolStatus], rax; ProtocolStatus
0x1800b203c  mov     r9d, 10h; SubmitBufferLength
0x1800b2042  mov     [rsp+130h+ReturnBufferLength], 0; ReturnBufferLength
0x1800b204b  mov     [rsp+130h+ProtocolReturnBuffer], 0; ProtocolReturnBuffer
0x1800b2054  mov     dword ptr [rbp+57h+var_50], 18h
0x1800b205b  mov     qword ptr [rbp+57h+var_50+8], rbx
0x1800b205f  call    cs:__imp_LsaCallAuthenticationPackage
0x1800b2065  mov     ebx, eax
0x1800b2067  mov     eax, [rsp+130h+var_F0]
0x1800b206b  test    ebx, ebx
0x1800b206d  js      short loc_1800B2073
0x1800b206f  test    eax, eax
0x1800b2071  jns     short loc_1800B20AF
0x1800b2073  mov     r9d, eax
0x1800b2076  lea     rcx, aSLsacallauthen_4; "%s: LsaCallAuthenticationPackage(KerbPu"...
0x1800b207d  mov     r8d, ebx
0x1800b2080  mov     rdx, r13
0x1800b2083  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b2088  mov     edi, [rsp+130h+var_F0]
0x1800b208c  lea     r8, aKerbpurgekdcpr; "KerbPurgeKdcProxyCacheMessage"
0x1800b2093  mov     rdx, [rsp+130h+PackageName.Buffer]; char *
0x1800b2098  test    ebx, ebx
0x1800b209a  mov     ecx, [rsp+130h+AuthenticationPackage]; unsigned int
0x1800b209e  cmovs   edi, ebx
0x1800b20a1  mov     r9d, edi; unsigned int
0x1800b20a4  call    ?WriteLsaAuthFailureEvent@Logger@@SAJKPEBDPEBGK@Z; Logger::WriteLsaAuthFailureEvent(ulong,char const *,ushort const *,ulong)
0x1800b20a9  mov     eax, [rsp+130h+var_F0]
0x1800b20ad  or      edi, esi
0x1800b20af  test    r15b, r15b
0x1800b20b2  jz      loc_1800B2146
0x1800b20b8  mov     edx, [rsp+130h+AuthenticationPackage]; AuthenticationPackage
0x1800b20bc  lea     rax, [rsp+130h+var_F0]
0x1800b20c1  mov     rcx, [rsp+130h+LsaHandle]; LsaHandle
0x1800b20c6  lea     r8, [rbp+57h+var_D0]; ProtocolSubmitBuffer
0x1800b20ca  mov     [rsp+130h+ProtocolStatus], rax; ProtocolStatus
0x1800b20cf  mov     r9d, 8; SubmitBufferLength
0x1800b20d5  mov     [rsp+130h+ReturnBufferLength], 0; ReturnBufferLength
0x1800b20de  mov     [rsp+130h+ProtocolReturnBuffer], 0; ProtocolReturnBuffer
0x1800b20e7  mov     dword ptr [rbp+57h+var_D0], 23h ; '#'
0x1800b20ee  mov     dword ptr [rbp+57h+var_D0+4], 1
0x1800b20f5  call    cs:__imp_LsaCallAuthenticationPackage
0x1800b20fb  mov     ebx, eax
0x1800b20fd  mov     eax, [rsp+130h+var_F0]
0x1800b2101  test    ebx, ebx
0x1800b2103  js      short loc_1800B210D
0x1800b2105  test    eax, eax
0x1800b2107  jns     loc_1800B1F41
0x1800b210d  mov     r9d, eax
0x1800b2110  lea     rcx, aSLsacallauthen_2; "%s: LsaCallAuthenticationPackage(KerbRe"...
0x1800b2117  mov     r8d, ebx
0x1800b211a  mov     rdx, r13
0x1800b211d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b2122  mov     r9d, [rsp+130h+var_F0]
0x1800b2127  lea     r8, aKerbrefreshpol; "KerbRefreshPolicyMessage"
0x1800b212e  mov     rdx, [rsp+130h+PackageName.Buffer]; char *
0x1800b2133  test    ebx, ebx
0x1800b2135  mov     ecx, [rsp+130h+AuthenticationPackage]; unsigned int
0x1800b2139  cmovs   r9d, ebx; unsigned int
0x1800b213d  call    ?WriteLsaAuthFailureEvent@Logger@@SAJKPEBDPEBGK@Z; Logger::WriteLsaAuthFailureEvent(ulong,char const *,ushort const *,ulong)
0x1800b2142  mov     eax, [rsp+130h+var_F0]
0x1800b2146  test    ebx, ebx
0x1800b2148  jns     loc_1800B1F39
0x1800b214e  mov     edi, ebx
0x1800b2150  jmp     loc_1800B1F3F
```
