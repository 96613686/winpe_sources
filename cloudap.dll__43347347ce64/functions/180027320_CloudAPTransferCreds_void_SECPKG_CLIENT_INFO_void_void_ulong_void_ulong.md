# CloudAPTransferCreds(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180027320`
- end: `0x1800279fd`
- name: `?CloudAPTransferCreds@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `1757`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000e7e0`
- `0x18000f100`
- `0x180015b98`
- `0x180027320`
- `0x18002c130`
- `0x180041770`
- `0x180042410`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279da`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800275be`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800279bc`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800275be`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800279bc`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800278af`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002792f`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800278af`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002792f`
- `ntdll!RtlReleaseResource` at `0x1800278ef`
- `ntdll!RtlReleaseResource` at `0x180027917`
- `ntdll!RtlReleaseResource` at `0x180027967`
- `ntdll!RtlReleaseResource` at `0x180027996`
- `ntdll!RtlReleaseResource` at `0x1800278ef`
- `ntdll!RtlReleaseResource` at `0x180027917`
- `ntdll!RtlReleaseResource` at `0x180027967`
- `ntdll!RtlReleaseResource` at `0x180027996`
- `ntdll!NtQueryInformationToken` at `0x1800276b5`
- `ntdll!NtQueryInformationToken` at `0x1800276df`
- `ntdll!NtQueryInformationToken` at `0x1800276b5`
- `ntdll!NtQueryInformationToken` at `0x1800276df`
- `ntdll!RtlInitUnicodeString` at `0x1800274f0`
- `ntdll!RtlInitUnicodeString` at `0x1800274f0`
- `LSASRV!LsaICallPackage` at `0x180027516`
- `LSASRV!LsaICallPackage` at `0x18002772f`
- `LSASRV!LsaICallPackage` at `0x180027516`
- `LSASRV!LsaICallPackage` at `0x18002772f`

## string_xrefs

- `0x1800273ea`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800274ac`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18002751c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18002761e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180027660`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800277d3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180027844`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800277f3`: `No Token Blob with logon session`
- `0x1800274c7`: `CreateLogonSession`
- `0x180027569`: `LsaICallPackage(protocolStatus`
- `0x180027784`: `LsaICallPackage(protocolStatus`
- `0x180027601`: `OpenTokenByLogonId`
- `0x1800277ad`: `NtQueryInformationToken(TokenStatistics)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudAPTransferCreds(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  char v7; // r14
  struct _LOGON_SESSION *v9; // rbx
  unsigned int v10; // edi
  const char *v11; // rax
  __int64 v12; // r12
  const char *v13; // r9
  int v14; // edi
  const char *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r8
  const char *v18; // r9
  const char *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  __int64 v25; // xmm1_8
  const char *v26; // rax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  const char *v33; // r9
  char v34; // al
  const char *v35; // rcx
  bool v36; // zf
  struct _LUID v37; // rax
  __int64 v38; // rax
  struct _LOGON_SESSION **v39; // rcx
  struct _USER_CACHE_ENTRY *v40; // rax
  struct _LOGON_SESSION *v41; // rbx
  struct _LUID v42; // rax
  __int64 v43; // rax
  struct _LOGON_SESSION **v44; // rdx
  struct _USER_CACHE_ENTRY *v45; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-A1h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-A1h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-A1h]
  char v50; // [rsp+40h] [rbp-81h]
  unsigned int v51; // [rsp+44h] [rbp-7Dh] BYREF
  struct _LUID v52; // [rsp+48h] [rbp-79h] BYREF
  ULONG v53; // [rsp+50h] [rbp-71h] BYREF
  int v54; // [rsp+54h] [rbp-6Dh] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-69h] BYREF
  struct _LOGON_SESSION *v56; // [rsp+60h] [rbp-61h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-59h] BYREF
  HANDLE TokenInformation; // [rsp+70h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-49h] BYREF
  _BYTE v60[24]; // [rsp+88h] [rbp-39h] BYREF
  _OWORD v61[3]; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v62; // [rsp+D0h] [rbp+Fh]

  v7 = 0;
  *(_QWORD *)&v60[16] = 0;
  v62 = 0;
  *a6 = 0;
  v9 = 0;
  *a7 = 0;
  v51 = 0;
  v54 = 0;
  Buffer = 0;
  v53 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v52 = 0;
  v56 = 0;
  v50 = 0;
  *(_OWORD *)v60 = 0;
  DestinationString = 0;
  memset(v61, 0, sizeof(v61));
  if ( a5 < 0x18 || !a3 )
  {
    v10 = -1073741811;
    v33 = "";
    while ( 1 )
    {
      v34 = *(v33 - 1);
      v35 = v33--;
      v36 = v34 == 92;
      if ( v34 == 92 )
        break;
      if ( v33 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v36 = v34 == 92;
        break;
      }
    }
    if ( v36 )
      v33 = v35;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v33, 2934, "Invalid Arg(s)", &Class);
    goto LABEL_44;
  }
  if ( *((_DWORD *)a3 + 5) )
  {
    v10 = -1073741637;
    goto LABEL_45;
  }
  v10 = _AcquireLogonSession(1, (struct _LUID *)(a3 + 4), (struct _LOGON_SESSION **)&v52);
  if ( !v10 )
  {
    v9 = (struct _LOGON_SESSION *)v52;
    v12 = *(_QWORD *)(*(_QWORD *)&v52 + 56LL);
    LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v12, 0);
    if ( !*(_DWORD *)(v12 + 280) || !*(_QWORD *)(v12 + 288) )
    {
      v10 = -1073741729;
      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225567LL, v32, 2972, "No Token Blob with logon session", &Class);
      goto LABEL_36;
    }
    v10 = _AcquireLogonSession(1, (struct _LUID *)(a3 + 12), &v56);
    if ( v10 == -1073741729 )
    {
      v10 = CreateLogonSession(
              (struct _LUID *)(a3 + 12),
              (struct _USER_CACHE_ENTRY *)v12,
              *((struct _SCARD_PIN **)v9 + 8),
              &v56);
      if ( v10 )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v13, 2984, "CreateLogonSession", &Class);
LABEL_36:
        UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v12);
        v7 = v50;
        goto LABEL_45;
      }
      v50 = 1;
    }
    else
    {
      if ( v10 )
      {
        v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v23, 2988, "AcquireLogonSession", &Class);
        goto LABEL_36;
      }
      if ( *((_QWORD *)v56 + 7) != v12 )
      {
        v10 = -1073741788;
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221225508LL,
          v24,
          2998,
          "Dst logon session is not for the same user",
          &Class);
        goto LABEL_36;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
    v14 = LsaICallPackage(&DestinationString, a3, a5, &Buffer, &v54, &v51);
    if ( v14 )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(ReturnLength) = 3013;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v14, v15, ReturnLength, v16, &Class);
    }
    v17 = v51;
    v18 = "LsaICallPackage(protocolStatus";
    if ( v51 )
    {
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(ReturnLength) = 3014;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, ReturnLength, v21, &Class);
      v17 = v51;
    }
    if ( v14 >= 0 && (int)v17 >= 0 )
    {
      if ( Buffer )
      {
        LsaFreeReturnBuffer(Buffer);
        Buffer = 0;
      }
      v10 = ((__int64 (__fastcall *)(char *, HANDLE *, __int64, const char *))g_pLsaFunctionTable->OpenTokenByLogonId)(
              a3 + 12,
              &TokenHandle,
              v17,
              v18);
      if ( v10 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        LODWORD(ReturnLength) = 3029;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v22, ReturnLength, "OpenTokenByLogonId", &Class);
        goto LABEL_36;
      }
      if ( NtQueryInformationToken(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &v53) >= 0 )
      {
        if ( NtQueryInformationToken(TokenInformation, TokenStatistics, v61, 0x38u, &v53) < 0 )
        {
          v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          LODWORD(ReturnLengtha) = 3066;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            v31,
            v30,
            ReturnLengtha,
            "NtQueryInformationToken(TokenStatistics)",
            &Class);
        }
        else
        {
          v25 = *((_QWORD *)a3 + 2);
          *(_OWORD *)v60 = *(_OWORD *)a3;
          *(_DWORD *)&v60[20] = HIDWORD(v25);
          *(_QWORD *)&v60[12] = *((_QWORD *)&v61[0] + 1);
          if ( (unsigned int)LsaICallPackage(&DestinationString, v60, 24, &Buffer, &v54, &v51) )
          {
            v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(ReturnLengthb) = 3061;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v27, v26, ReturnLengthb, "LsaICallPackage(status", &Class);
          }
          if ( v51 )
          {
            v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(ReturnLengthb) = 3062;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v29, v28, ReturnLengthb, "LsaICallPackage(protocolStatus", &Class);
          }
        }
      }
    }
    v10 = 0;
    goto LABEL_36;
  }
  v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v11, 2959, "AcquireLogonSession", &Class);
  v9 = (struct _LOGON_SESSION *)v52;
LABEL_44:
  v7 = 0;
LABEL_45:
  if ( v9 )
  {
    RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
    v37 = *(struct _LUID *)((char *)v9 + 28);
    _InterlockedDecrement((volatile signed __int32 *)v9 + 4);
    v36 = *((_DWORD *)v9 + 4) == 0;
    v52 = v37;
    if ( v36 )
    {
      v38 = *(_QWORD *)v9;
      if ( *(struct _LOGON_SESSION **)(*(_QWORD *)v9 + 8LL) != v9 )
        goto LABEL_58;
      v39 = (struct _LOGON_SESSION **)*((_QWORD *)v9 + 1);
      if ( *v39 != v9 )
        goto LABEL_58;
      *v39 = (struct _LOGON_SESSION *)v38;
      *(_QWORD *)(v38 + 8) = v39;
      RtlReleaseResource(&g_LogonSessionListLock);
      v40 = _FreeLogonSession(v9);
      if ( v40 )
        _ReleaseUserCacheEntry(&v52, v40);
    }
    else
    {
      RtlReleaseResource(&g_LogonSessionListLock);
    }
  }
  v41 = v56;
  if ( !v56 )
    goto LABEL_60;
  RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
  v42 = *(struct _LUID *)((char *)v41 + 28);
  _InterlockedDecrement((volatile signed __int32 *)v41 + 4);
  v36 = *((_DWORD *)v41 + 4) == 0;
  v52 = v42;
  if ( !v36 )
  {
    RtlReleaseResource(&g_LogonSessionListLock);
    goto LABEL_60;
  }
  v43 = *(_QWORD *)v41;
  if ( *(struct _LOGON_SESSION **)(*(_QWORD *)v41 + 8LL) != v41
    || (v44 = (struct _LOGON_SESSION **)*((_QWORD *)v41 + 1), *v44 != v41) )
  {
LABEL_58:
    __fastfail(3u);
  }
  *v44 = (struct _LOGON_SESSION *)v43;
  *(_QWORD *)(v43 + 8) = v44;
  RtlReleaseResource(&g_LogonSessionListLock);
  v45 = _FreeLogonSession(v41);
  if ( v45 )
    _ReleaseUserCacheEntry(&v52, v45);
LABEL_60:
  if ( (v10 & 0x80000000) != 0 && a3 && v7 )
    RemoveLogonSession((struct _LUID *)(a3 + 12));
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( TokenInformation )
    CloseHandle(TokenInformation);
  return v10;
}

```

## disassembly

```asm
0x180027320  push    rbp
0x180027322  push    rbx
0x180027323  push    rdi
0x180027324  push    r14
0x180027326  push    r15
0x180027328  lea     rbp, [rsp-1Fh]
0x18002732d  sub     rsp, 0E0h
0x180027334  mov     rax, cs:__security_cookie
0x18002733b  xor     rax, rsp
0x18002733e  mov     [rbp+3Fh+var_28], rax
0x180027342  mov     rax, [rbp+3Fh+arg_28]
0x180027346  xor     edx, edx
0x180027348  mov     rcx, [rbp+3Fh+arg_30]
0x18002734c  xorps   xmm1, xmm1
0x18002734f  xor     r14b, r14b
0x180027352  mov     [rsp+100h+arg_0], rsi
0x18002735a  mov     esi, [rbp+3Fh+arg_20]
0x18002735d  xorps   xmm0, xmm0
0x180027360  mov     r15, r8
0x180027363  mov     [rbp+3Fh+var_68], rdx
0x180027367  xor     r8d, r8d
0x18002736a  mov     [rbp+3Fh+var_30], rdx
0x18002736e  mov     [rax], r8
0x180027371  mov     ebx, r8d
0x180027374  mov     [rcx], r8d
0x180027377  mov     [rbp+3Fh+var_BC], r8d
0x18002737b  mov     [rbp+3Fh+var_AC], r8d
0x18002737f  mov     [rbp+3Fh+Buffer], r8
0x180027383  mov     [rbp+3Fh+var_B0], r8d
0x180027387  mov     [rbp+3Fh+TokenHandle], r8
0x18002738b  mov     [rbp+3Fh+TokenInformation], r8
0x18002738f  mov     qword ptr [rbp+3Fh+var_B8.LowPart], rbx
0x180027393  mov     [rbp+3Fh+var_A0], r8
0x180027397  mov     [rsp+100h+var_C0], r14b
0x18002739c  movups  [rbp+3Fh+var_78], xmm0
0x1800273a0  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x1800273a4  movups  [rbp+3Fh+var_60], xmm1
0x1800273a8  movups  [rbp+3Fh+var_50], xmm1
0x1800273ac  movups  [rbp+3Fh+var_40], xmm1
0x1800273b0  cmp     esi, 18h
0x1800273b3  jb      loc_180027838
0x1800273b9  test    r15, r15
0x1800273bc  jz      loc_180027838
0x1800273c2  cmp     [r15+14h], edx
0x1800273c6  jz      short loc_1800273D2
0x1800273c8  mov     edi, 0C00000BBh
0x1800273cd  jmp     loc_180027899
0x1800273d2  lea     rdx, [r15+4]; struct _LUID *
0x1800273d6  mov     ecx, 1; int
0x1800273db  lea     r8, [rbp+3Fh+var_B8]; struct _LOGON_SESSION **
0x1800273df  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x1800273e4  mov     edi, eax
0x1800273e6  test    eax, eax
0x1800273e8  jz      short loc_180027433
0x1800273ea  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800273f1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800273f6  mov     r9, rax
0x1800273f9  lea     r14, Class
0x180027400  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x180027407  mov     [rsp+100h+var_D0], r14
0x18002740c  mov     [rsp+100h+var_D8], rax
0x180027411  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180027418  mov     r8d, edi
0x18002741b  mov     dword ptr [rsp+100h+ReturnLength], 0B8Fh
0x180027423  xor     ecx, ecx
0x180027425  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002742a  mov     rbx, qword ptr [rbp+3Fh+var_B8.LowPart]
0x18002742e  jmp     loc_180027896
0x180027433  mov     rbx, qword ptr [rbp+3Fh+var_B8.LowPart]
0x180027437  xor     edx, edx; bool
0x180027439  mov     [rsp+100h+arg_8], r12
0x180027441  mov     [rsp+100h+arg_18], r13
0x180027449  mov     r12, [rbx+38h]
0x18002744d  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x180027450  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x180027455  cmp     dword ptr [r12+118h], 0
0x18002745e  jz      loc_1800277D3
0x180027464  cmp     qword ptr [r12+120h], 0
0x18002746d  jz      loc_1800277D3
0x180027473  lea     r8, [rbp+3Fh+var_A0]; struct _LOGON_SESSION **
0x180027477  mov     ecx, 1; int
0x18002747c  lea     rdx, [r15+0Ch]; struct _LUID *
0x180027480  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x180027485  mov     edi, eax
0x180027487  cmp     eax, 0C000005Fh
0x18002748c  jnz     loc_18002761A
0x180027492  mov     r8, [rbx+40h]; struct _SCARD_PIN *
0x180027496  lea     r9, [rbp+3Fh+var_A0]; struct _LOGON_SESSION **
0x18002749a  mov     rdx, r12; struct _USER_CACHE_ENTRY *
0x18002749d  lea     rcx, [r15+0Ch]; struct _LUID *
0x1800274a1  call    ?CreateLogonSession@@YAJPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@PEAU_SCARD_PIN@@PEAPEAU_LOGON_SESSION@@@Z; CreateLogonSession(_LUID *,_USER_CACHE_ENTRY *,_SCARD_PIN *,_LOGON_SESSION * *)
0x1800274a6  mov     edi, eax
0x1800274a8  test    eax, eax
0x1800274aa  jz      short loc_1800274E0
0x1800274ac  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800274b3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800274b8  mov     r9, rax
0x1800274bb  lea     r14, Class
0x1800274c2  mov     [rsp+100h+var_D0], r14
0x1800274c7  lea     rax, aCreatelogonses; "CreateLogonSession"
0x1800274ce  mov     [rsp+100h+var_D8], rax
0x1800274d3  mov     dword ptr [rsp+100h+ReturnLength], 0BA8h
0x1800274db  jmp     loc_180027807
0x1800274e0  mov     [rsp+100h+var_C0], 1
0x1800274e5  lea     rdx, SourceString; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x1800274ec  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800274f0  call    cs:__imp_RtlInitUnicodeString
0x1800274f6  lea     rax, [rbp+3Fh+var_BC]
0x1800274fa  mov     r8d, esi
0x1800274fd  mov     [rsp+100h+var_D8], rax
0x180027502  lea     r9, [rbp+3Fh+Buffer]
0x180027506  lea     rax, [rbp+3Fh+var_AC]
0x18002750a  mov     rdx, r15
0x18002750d  lea     rcx, [rbp+3Fh+DestinationString]
0x180027511  mov     [rsp+100h+ReturnLength], rax
0x180027516  call    cs:__imp_LsaICallPackage
0x18002751c  lea     rsi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180027523  mov     edi, eax
0x180027525  lea     r14, Class
0x18002752c  lea     r8, aLsaicallpackag; "LsaICallPackage(status"
0x180027533  test    eax, eax
0x180027535  jz      short loc_180027565
0x180027537  mov     rcx, rsi; char *
0x18002753a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002753f  mov     [rsp+100h+var_D0], r14
0x180027544  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002754b  mov     [rsp+100h+var_D8], r8
0x180027550  mov     r9, rax
0x180027553  mov     r8d, edi
0x180027556  mov     dword ptr [rsp+100h+ReturnLength], 0BC5h
0x18002755e  xor     ecx, ecx
0x180027560  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180027565  mov     r8d, [rbp+3Fh+var_BC]
0x180027569  lea     r9, aLsaicallpackag_0; "LsaICallPackage(protocolStatus"
0x180027570  test    r8d, r8d
0x180027573  jz      short loc_1800275A4
0x180027575  mov     rcx, rsi; char *
0x180027578  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002757d  mov     [rsp+100h+var_D0], r14
0x180027582  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180027589  mov     [rsp+100h+var_D8], r9
0x18002758e  xor     ecx, ecx
0x180027590  mov     r9, rax
0x180027593  mov     dword ptr [rsp+100h+ReturnLength], 0BC6h
0x18002759b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800275a0  mov     r8d, [rbp+3Fh+var_BC]
0x1800275a4  test    edi, edi
0x1800275a6  js      loc_1800277CF
0x1800275ac  test    r8d, r8d
0x1800275af  js      loc_1800277CF
0x1800275b5  mov     rcx, [rbp+3Fh+Buffer]; Buffer
0x1800275b9  test    rcx, rcx
0x1800275bc  jz      short loc_1800275CC
0x1800275be  call    cs:__imp_LsaFreeReturnBuffer
0x1800275c4  mov     [rbp+3Fh+Buffer], 0
0x1800275cc  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800275d3  lea     rdx, [rbp+3Fh+TokenHandle]
0x1800275d7  lea     rcx, [r15+0Ch]
0x1800275db  mov     rax, [rax+170h]
0x1800275e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275e7  mov     edi, eax
0x1800275e9  test    eax, eax
0x1800275eb  jz      loc_180027699
0x1800275f1  mov     rcx, rsi; char *
0x1800275f4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800275f9  mov     [rsp+100h+var_D0], r14
0x1800275fe  mov     r9, rax
0x180027601  lea     rax, aOpentokenbylog; "OpenTokenByLogonId"
0x180027608  mov     [rsp+100h+var_D8], rax
0x18002760d  mov     dword ptr [rsp+100h+ReturnLength], 0BD5h
0x180027615  jmp     loc_180027807
0x18002761a  test    edi, edi
0x18002761c  jz      short loc_180027652
0x18002761e  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180027625  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002762a  mov     r9, rax
0x18002762d  lea     r14, Class
0x180027634  mov     [rsp+100h+var_D0], r14
0x180027639  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x180027640  mov     [rsp+100h+var_D8], rax
0x180027645  mov     dword ptr [rsp+100h+ReturnLength], 0BACh
0x18002764d  jmp     loc_180027807
0x180027652  mov     rax, [rbp+3Fh+var_A0]
0x180027656  cmp     [rax+38h], r12
0x18002765a  jz      loc_1800274E5
0x180027660  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180027667  mov     edi, 0C0000024h
0x18002766c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027671  mov     r9, rax
0x180027674  lea     r14, Class
0x18002767b  mov     [rsp+100h+var_D0], r14
0x180027680  lea     rax, aDstLogonSessio; "Dst logon session is not for the same u"...
0x180027687  mov     [rsp+100h+var_D8], rax
0x18002768c  mov     dword ptr [rsp+100h+ReturnLength], 0BB6h
0x180027694  jmp     loc_180027807
0x180027699  mov     rcx, [rbp+3Fh+TokenHandle]; TokenHandle
0x18002769d  lea     rax, [rbp+3Fh+var_B0]
0x1800276a1  mov     r9d, 8; TokenInformationLength
0x1800276a7  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x1800276ac  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x1800276b0  mov     edx, 13h; TokenInformationClass
0x1800276b5  call    cs:__imp_NtQueryInformationToken
0x1800276bb  test    eax, eax
0x1800276bd  js      loc_1800277CF
0x1800276c3  mov     rcx, [rbp+3Fh+TokenInformation]; TokenHandle
0x1800276c7  lea     rax, [rbp+3Fh+var_B0]
0x1800276cb  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800276d1  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x1800276d6  lea     r8, [rbp+3Fh+var_60]; TokenInformation
0x1800276da  mov     edx, 0Ah; TokenInformationClass
0x1800276df  call    cs:__imp_NtQueryInformationToken
0x1800276e5  mov     r8d, eax
0x1800276e8  test    eax, eax
0x1800276ea  js      loc_18002779D
0x1800276f0  mov     rax, qword ptr [rbp+3Fh+var_60+8]
0x1800276f4  lea     r9, [rbp+3Fh+Buffer]
0x1800276f8  movups  xmm0, xmmword ptr [r15]
0x1800276fc  lea     rdx, [rbp+3Fh+var_78]
0x180027700  mov     r8d, 18h
0x180027706  movsd   xmm1, qword ptr [r15+10h]
0x18002770c  lea     rcx, [rbp+3Fh+DestinationString]
0x180027710  movups  [rbp+3Fh+var_78], xmm0
0x180027714  movsd   [rbp+3Fh+var_68], xmm1
0x180027719  mov     qword ptr [rbp+3Fh+var_78+0Ch], rax
0x18002771d  lea     rax, [rbp+3Fh+var_BC]
0x180027721  mov     [rsp+100h+var_D8], rax
0x180027726  lea     rax, [rbp+3Fh+var_AC]
0x18002772a  mov     [rsp+100h+ReturnLength], rax
0x18002772f  call    cs:__imp_LsaICallPackage
0x180027735  mov     r8d, eax
0x180027738  test    eax, eax
0x18002773a  jz      short loc_18002776E
0x18002773c  mov     rcx, rsi; char *
0x18002773f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027744  mov     r9, rax
0x180027747  mov     [rsp+100h+var_D0], r14
0x18002774c  lea     rax, aLsaicallpackag; "LsaICallPackage(status"
0x180027753  xor     ecx, ecx
0x180027755  mov     [rsp+100h+var_D8], rax
0x18002775a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180027761  mov     dword ptr [rsp+100h+ReturnLength], 0BF5h
0x180027769  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002776e  mov     r8d, [rbp+3Fh+var_BC]
0x180027772  test    r8d, r8d
0x180027775  jz      short loc_1800277CF
0x180027777  mov     rcx, rsi; char *
0x18002777a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002777f  mov     [rsp+100h+var_D0], r14
0x180027784  lea     rcx, aLsaicallpackag_0; "LsaICallPackage(protocolStatus"
0x18002778b  mov     [rsp+100h+var_D8], rcx
0x180027790  mov     r9, rax
0x180027793  mov     dword ptr [rsp+100h+ReturnLength], 0BF6h
0x18002779b  jmp     short loc_1800277C1
0x18002779d  mov     rcx, rsi; char *
0x1800277a0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800277a5  mov     [rsp+100h+var_D0], r14
0x1800277aa  mov     r9, rax
0x1800277ad  lea     rax, aNtqueryinforma_0; "NtQueryInformationToken(TokenStatistics"...
0x1800277b4  mov     [rsp+100h+var_D8], rax
0x1800277b9  mov     dword ptr [rsp+100h+ReturnLength], 0BFAh
0x1800277c1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800277c8  xor     ecx, ecx
0x1800277ca  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800277cf  xor     edi, edi
0x1800277d1  jmp     short loc_180027818
0x1800277d3  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800277da  mov     edi, 0C000005Fh
0x1800277df  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800277e4  mov     r9, rax
0x1800277e7  lea     r14, Class
0x1800277ee  mov     [rsp+100h+var_D0], r14
0x1800277f3  lea     rax, aNoTokenBlobWit; "No Token Blob with logon session"
0x1800277fa  mov     [rsp+100h+var_D8], rax
0x1800277ff  mov     dword ptr [rsp+100h+ReturnLength], 0B9Ch
0x180027807  mov     r8d, edi
0x18002780a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180027811  xor     ecx, ecx
0x180027813  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180027818  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x18002781b  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180027820  movzx   r14d, [rsp+100h+var_C0]
0x180027826  mov     r13, [rsp+100h+arg_18]
0x18002782e  mov     r12, [rsp+100h+arg_8]
0x180027836  jmp     short loc_180027899
0x180027838  mov     edi, 0C000000Dh
0x18002783d  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x180027844  lea     rsi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18002784b  movzx   eax, byte ptr [r9-1]
0x180027850  mov     rcx, r9
0x180027853  dec     r9
0x180027856  cmp     al, 5Ch ; '\'
0x180027858  jz      short loc_180027861
0x18002785a  cmp     r9, rsi
0x18002785d  ja      short loc_18002784B
0x18002785f  cmp     al, 5Ch ; '\'
0x180027861  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x180027868  cmovz   r9, rcx
0x18002786c  lea     r14, Class
0x180027873  mov     r8d, edi
0x180027876  mov     [rsp+100h+var_D0], r14
  ... truncated ...
```
