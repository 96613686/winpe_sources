# SpDeleteConnectedIdentity(void *,void *,void *,_LUID *,void *)

- ea: `0x1800579a0`
- end: `0x180058081`
- name: `?SpDeleteConnectedIdentity@@YAJPEAX00PEAU_LUID@@0@Z`
- size: `1761`
- prototype: `int(void *, void *, void *, struct _LUID *, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003584`
- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ee60`
- `0x18000f100`
- `0x180010320`
- `0x180015c50`
- `0x180032968`
- `0x180041770`
- `0x180042410`
- `0x180052288`
- `0x1800579a0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058052`
- `SspiCli!LsaFreeReturnBuffer` at `0x180057e44`
- `SspiCli!LsaFreeReturnBuffer` at `0x180058042`
- `SspiCli!LsaFreeReturnBuffer` at `0x180057e44`
- `SspiCli!LsaFreeReturnBuffer` at `0x180058042`
- `ntdll!RtlAcquireResourceExclusive` at `0x180057fca`
- `ntdll!RtlAcquireResourceExclusive` at `0x180057fca`
- `ntdll!RtlReleaseResource` at `0x180058013`
- `ntdll!RtlReleaseResource` at `0x180058013`
- `ntdll!NtQueryInformationToken` at `0x180057bf6`
- `ntdll!NtQueryInformationToken` at `0x180057e2c`
- `ntdll!NtQueryInformationToken` at `0x180057e70`
- `ntdll!NtQueryInformationToken` at `0x180057bf6`
- `ntdll!NtQueryInformationToken` at `0x180057e2c`
- `ntdll!NtQueryInformationToken` at `0x180057e70`
- `ntdll!RtlInitUnicodeString` at `0x180057d31`
- `ntdll!RtlInitUnicodeString` at `0x180057d31`
- `LSASRV!LsaICallPackage` at `0x180057d75`
- `LSASRV!LsaICallPackage` at `0x180057eb0`
- `LSASRV!LsaICallPackage` at `0x180057d75`
- `LSASRV!LsaICallPackage` at `0x180057eb0`

## string_xrefs

- `0x180057a92`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057ada`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057b32`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057b83`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057c02`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057c97`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057cf0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057d88`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057dcb`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057ebd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057efd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057f20`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057f65`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057f34`: `NtQueryInformationToken`
- `0x180057dbf`: `LsaICallPackage(protocolStatus`
- `0x180057c1d`: `NtQueryInformationToken(TokenStatistics)`
- `0x180057d04`: `CleanupUserCache`
- `0x180057b52`: `Not supported for this type of plugin`

## pseudocode

```c
__int64 __fastcall SpDeleteConnectedIdentity(void *a1, void *a2, void *a3, struct _LUID *a4, void *a5)
{
  struct _ApPluginPkg *v7; // rsi
  struct _LOGON_SESSION *v8; // r15
  unsigned int v9; // ebx
  const char *v10; // r9
  const char *v11; // rax
  const char *v12; // r9
  const char *v13; // rax
  const char *v14; // r9
  __int64 v15; // r14
  HANDLE v16; // r12
  unsigned int v17; // ebx
  const char *v18; // rax
  const char *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const char *v22; // rax
  __int64 v23; // r8
  int v24; // r8d
  const char *v25; // rax
  __int64 v26; // r8
  const char *v27; // rax
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  char v34; // si
  struct _LOGON_SESSION *v35; // rax
  struct _LOGON_SESSION *v36; // rdi
  __int64 v37; // rax
  struct _LOGON_SESSION **v38; // rcx
  struct _USER_CACHE_ENTRY *v39; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthc; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v46; // [rsp+44h] [rbp-BCh] BYREF
  int v47; // [rsp+48h] [rbp-B8h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-B0h] BYREF
  struct _ApPluginPkg *v49; // [rsp+58h] [rbp-A8h] BYREF
  struct _LOGON_SESSION *v50; // [rsp+60h] [rbp-A0h] BYREF
  struct _LUID v51; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v55[24]; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v56; // [rsp+A8h] [rbp-58h] BYREF
  int TokenInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v58; // [rsp+BCh] [rbp-44h]
  __int128 v59; // [rsp+CCh] [rbp-34h]
  __int128 v60; // [rsp+DCh] [rbp-24h]
  int v61; // [rsp+ECh] [rbp-14h]
  int v62; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v63; // [rsp+F4h] [rbp-Ch]
  __int128 v64; // [rsp+104h] [rbp+4h]
  __int128 v65; // [rsp+114h] [rbp+14h]
  int v66; // [rsp+124h] [rbp+24h]

  TokenHandle = a2;
  v51 = 0;
  v45 = 0;
  v47 = 0;
  v46 = 0;
  TokenInformation = 0;
  v7 = 0;
  v61 = 0;
  v8 = 0;
  v62 = 0;
  v66 = 0;
  v49 = 0;
  v50 = 0;
  Buffer = 0;
  hObject = 0;
  v56 = 0;
  DestinationString = 0;
  memset(v55, 0, sizeof(v55));
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  if ( a4 && a5 && a2 && a3 && a1 )
  {
    v9 = (*((__int64 (__fastcall **)(void *, struct _GUID *))g_pLsaIdProvHostFunctionTable + 10))(a1, &v56);
    if ( v9 )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v10, 9690, "GetProvInfo", &Class);
    }
    else
    {
      v9 = RefPackage(&v56, &v49);
      if ( v9 )
      {
        v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v11, 9693, "RefPackage", &Class);
        v7 = v49;
      }
      else
      {
        v7 = v49;
        if ( (*((_BYTE *)v49 + 160) & 4) != 0 )
        {
          v9 = -1073741637;
          v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            3221225659LL,
            v12,
            9699,
            "Not supported for this type of plugin",
            &Class);
        }
        else
        {
          v9 = _AcquireLogonSession(1, a4, &v50);
          if ( v9 )
          {
            v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v13, 9705, "AcquireLogonSession", &Class);
            v8 = v50;
          }
          else
          {
            v8 = v50;
            v51 = *(struct _LUID *)((char *)v50 + 28);
            v9 = NtQueryInformationToken(a3, TokenStatistics, &TokenInformation, 0x38u, &v46);
            if ( v9 )
            {
              v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(ReturnLength) = 9720;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                v9,
                v14,
                ReturnLength,
                "NtQueryInformationToken(TokenStatistics)",
                &Class);
            }
            else
            {
              v15 = *((_QWORD *)v8 + 7);
              LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v15, 1);
              if ( *((_QWORD *)v7 + 38) )
              {
                SCLockConvertExclusiveToShared((PRTL_RESOURCE)(*(_QWORD *)(v15 + 24) + 24LL));
                v16 = TokenHandle;
                v17 = (*((__int64 (__fastcall **)(_QWORD, HANDLE, void *, __int64))v7 + 38))(
                        *((_QWORD *)v7 + 1),
                        TokenHandle,
                        a5,
                        v15 + 280);
                SCLockConvertSharedToExclusive((PRTL_RESOURCE)(*(_QWORD *)(v15 + 24) + 24LL));
                if ( v17 )
                {
                  v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                  LODWORD(ReturnLength) = 9739;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v18, ReturnLength, "DisconnectIdentity", &Class);
                }
              }
              else
              {
                v16 = TokenHandle;
              }
              if ( (unsigned int)CleanupUserCache(v7, *(void **)(v15 + 240), 1) )
              {
                v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(ReturnLength) = 9745;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, ReturnLength, "CleanupUserCache", &Class);
              }
              RtlInitUnicodeString(&DestinationString, L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
              *(_QWORD *)&v55[4] = *(_QWORD *)((char *)&v58 + 4);
              *(struct _LUID *)&v55[12] = *a4;
              *(_DWORD *)v55 = 1026;
              v21 = LsaICallPackage(&DestinationString, v55, 24, &Buffer, &v47, &v45);
              if ( v21 )
              {
                v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(ReturnLengtha) = 9761;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v21, v22, ReturnLengtha, v23, &Class);
              }
              v24 = v45;
              if ( v45 )
              {
                v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(ReturnLengtha) = 9762;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  v26,
                  v25,
                  ReturnLengtha,
                  "LsaICallPackage(protocolStatus",
                  &Class);
                v24 = v45;
              }
              if ( v21 >= 0 && v24 >= 0 && NtQueryInformationToken(v16, TokenLinkedToken, &hObject, 8u, &v46) >= 0 )
              {
                if ( Buffer )
                {
                  LsaFreeReturnBuffer(Buffer);
                  Buffer = 0;
                }
                if ( NtQueryInformationToken(hObject, TokenStatistics, &v62, 0x38u, &v46) < 0 )
                {
                  v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                  LODWORD(ReturnLengthb) = 9803;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v32, v31, ReturnLengthb, "NtQueryInformationToken", &Class);
                }
                else
                {
                  *(_QWORD *)&v55[12] = *(_QWORD *)((char *)&v63 + 4);
                  if ( (unsigned int)LsaICallPackage(&DestinationString, v55, 24, &Buffer, &v47, &v45) )
                  {
                    v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                    LODWORD(ReturnLengthc) = 9798;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v28, v27, ReturnLengthc, "LsaICallPackage(status", &Class);
                  }
                  if ( v45 )
                  {
                    v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                    LODWORD(ReturnLengthc) = 9799;
                    WPPTraceLogA(
                      0,
                      "0x%08x %s:%u : %s:%ws",
                      v30,
                      v29,
                      ReturnLengthc,
                      "LsaICallPackage(protocolStatus",
                      &Class);
                  }
                }
              }
              v9 = 0;
              UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v15);
            }
          }
        }
      }
    }
  }
  else
  {
    v9 = -1073741811;
    v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v33, 9686, "Null Arg(s)", &Class);
  }
  ReleaseLogonSession(v8);
  DerefPackage(v7);
  if ( (v9 & 0x80000000) == 0 )
  {
    v34 = 0;
    RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
    v35 = _LocateLogonSession(&v51);
    v36 = v35;
    if ( v35 )
    {
      _InterlockedDecrement((volatile signed __int32 *)v35 + 4);
      if ( !*((_DWORD *)v35 + 4) )
      {
        v37 = *(_QWORD *)v35;
        if ( *(struct _LOGON_SESSION **)(v37 + 8) != v36
          || (v38 = (struct _LOGON_SESSION **)*((_QWORD *)v36 + 1), *v38 != v36) )
        {
          __fastfail(3u);
        }
        *v38 = (struct _LOGON_SESSION *)v37;
        v34 = 1;
        *(_QWORD *)(v37 + 8) = v38;
      }
    }
    RtlReleaseResource(&g_LogonSessionListLock);
    if ( v34 )
    {
      v39 = _FreeLogonSession(v36);
      if ( v39 )
        _ReleaseUserCacheEntry(&v51, v39);
    }
  }
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( hObject )
    CloseHandle(hObject);
  return v9;
}

```

## disassembly

```asm
0x1800579a0  push    rbp
0x1800579a2  push    rbx
0x1800579a3  push    rsi
0x1800579a4  push    rdi
0x1800579a5  push    r12
0x1800579a7  push    r13
0x1800579a9  push    r14
0x1800579ab  push    r15
0x1800579ad  lea     rbp, [rsp-38h]
0x1800579b2  sub     rsp, 138h
0x1800579b9  mov     rax, cs:__security_cookie
0x1800579c0  xor     rax, rsp
0x1800579c3  mov     [rbp+70h+var_48], rax
0x1800579c7  mov     r12, [rbp+70h+arg_20]
0x1800579ce  xor     r14d, r14d
0x1800579d1  xorps   xmm0, xmm0
0x1800579d4  mov     [rsp+170h+TokenHandle], rdx
0x1800579d9  mov     rax, rdx
0x1800579dc  mov     qword ptr [rsp+170h+var_108.LowPart], r14
0x1800579e1  xor     edx, edx
0x1800579e3  mov     [rsp+170h+var_130], r14d
0x1800579e8  mov     [rsp+170h+var_128], r14d
0x1800579ed  xorps   xmm1, xmm1
0x1800579f0  mov     [rbp+70h+var_D0], rdx
0x1800579f4  mov     r13, r9
0x1800579f7  mov     [rsp+170h+var_12C], r14d
0x1800579fc  mov     rdi, r8
0x1800579ff  mov     [rbp+70h+TokenInformation], r14d
0x180057a03  mov     esi, r14d
0x180057a06  mov     [rbp+70h+var_84], edx
0x180057a09  mov     r15d, r14d
0x180057a0c  mov     [rbp+70h+var_80], r14d
0x180057a10  mov     [rbp+70h+var_4C], edx
0x180057a13  mov     [rsp+170h+var_118], r14
0x180057a18  mov     [rsp+170h+var_110], r14
0x180057a1d  mov     [rsp+170h+Buffer], r14
0x180057a22  mov     [rsp+170h+hObject], r14
0x180057a27  movups  xmmword ptr [rbp+70h+var_C8.Data1], xmm0
0x180057a2b  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x180057a2f  movups  [rbp+70h+var_E0], xmm1
0x180057a33  movups  [rbp+70h+var_B4], xmm0
0x180057a37  movups  [rbp+70h+var_A4], xmm0
0x180057a3b  movups  [rbp+70h+var_94], xmm0
0x180057a3f  movups  [rbp+70h+var_7C], xmm0
0x180057a43  movups  [rbp+70h+var_6C], xmm0
0x180057a47  movups  [rbp+70h+var_5C], xmm0
0x180057a4b  test    r9, r9
0x180057a4e  jz      loc_180057F65
0x180057a54  test    r12, r12
0x180057a57  jz      loc_180057F65
0x180057a5d  test    rax, rax
0x180057a60  jz      loc_180057F65
0x180057a66  test    r8, r8
0x180057a69  jz      loc_180057F65
0x180057a6f  test    rcx, rcx
0x180057a72  jz      loc_180057F65
0x180057a78  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180057a7f  lea     rdx, [rbp+70h+var_C8]
0x180057a83  mov     rax, [rax+50h]
0x180057a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a8c  mov     ebx, eax
0x180057a8e  test    eax, eax
0x180057a90  jz      short loc_180057AC6
0x180057a92  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057a99  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057a9e  mov     r9, rax
0x180057aa1  lea     rdi, Class
0x180057aa8  mov     [rsp+170h+var_140], rdi
0x180057aad  lea     rax, aGetprovinfo; "GetProvInfo"
0x180057ab4  mov     [rsp+170h+var_148], rax
0x180057ab9  mov     dword ptr [rsp+170h+ReturnLength], 25DAh
0x180057ac1  jmp     loc_180057F99
0x180057ac6  lea     rdx, [rsp+170h+var_118]; struct _ApPluginPkg **
0x180057acb  lea     rcx, [rbp+70h+var_C8]; struct _GUID *
0x180057acf  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180057ad4  mov     ebx, eax
0x180057ad6  test    eax, eax
0x180057ad8  jz      short loc_180057B24
0x180057ada  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057ae1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057ae6  mov     r9, rax
0x180057ae9  lea     rdi, Class
0x180057af0  lea     rax, aRefpackage; "RefPackage"
0x180057af7  mov     [rsp+170h+var_140], rdi
0x180057afc  mov     [rsp+170h+var_148], rax
0x180057b01  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057b08  mov     r8d, ebx
0x180057b0b  mov     dword ptr [rsp+170h+ReturnLength], 25DDh
0x180057b13  xor     ecx, ecx
0x180057b15  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057b1a  mov     rsi, [rsp+170h+var_118]
0x180057b1f  jmp     loc_180057FAA
0x180057b24  mov     rsi, [rsp+170h+var_118]
0x180057b29  test    byte ptr [rsi+0A0h], 4
0x180057b30  jz      short loc_180057B6B
0x180057b32  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057b39  mov     ebx, 0C00000BBh
0x180057b3e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057b43  mov     r9, rax
0x180057b46  lea     rdi, Class
0x180057b4d  mov     [rsp+170h+var_140], rdi
0x180057b52  lea     rax, aNotSupportedFo; "Not supported for this type of plugin"
0x180057b59  mov     [rsp+170h+var_148], rax
0x180057b5e  mov     dword ptr [rsp+170h+ReturnLength], 25E3h
0x180057b66  jmp     loc_180057F99
0x180057b6b  lea     r8, [rsp+170h+var_110]; struct _LOGON_SESSION **
0x180057b70  mov     rdx, r13; struct _LUID *
0x180057b73  mov     ecx, 1; int
0x180057b78  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x180057b7d  mov     ebx, eax
0x180057b7f  test    eax, eax
0x180057b81  jz      short loc_180057BCD
0x180057b83  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057b8a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057b8f  mov     r9, rax
0x180057b92  lea     rdi, Class
0x180057b99  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x180057ba0  mov     [rsp+170h+var_140], rdi
0x180057ba5  mov     [rsp+170h+var_148], rax
0x180057baa  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057bb1  mov     r8d, ebx
0x180057bb4  mov     dword ptr [rsp+170h+ReturnLength], 25E9h
0x180057bbc  xor     ecx, ecx
0x180057bbe  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057bc3  mov     r15, [rsp+170h+var_110]
0x180057bc8  jmp     loc_180057FAA
0x180057bcd  mov     r15, [rsp+170h+var_110]
0x180057bd2  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x180057bd6  mov     r9d, 38h ; '8'; TokenInformationLength
0x180057bdc  mov     rcx, rdi; TokenHandle
0x180057bdf  mov     rax, [r15+1Ch]
0x180057be3  mov     qword ptr [rsp+170h+var_108.LowPart], rax
0x180057be8  lea     edx, [r9-2Eh]; TokenInformationClass
0x180057bec  lea     rax, [rsp+170h+var_12C]
0x180057bf1  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x180057bf6  call    cs:__imp_NtQueryInformationToken
0x180057bfc  mov     ebx, eax
0x180057bfe  test    eax, eax
0x180057c00  jz      short loc_180057C36
0x180057c02  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057c09  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057c0e  mov     r9, rax
0x180057c11  lea     rdi, Class
0x180057c18  mov     [rsp+170h+var_140], rdi
0x180057c1d  lea     rax, aNtqueryinforma_0; "NtQueryInformationToken(TokenStatistics"...
0x180057c24  mov     [rsp+170h+var_148], rax
0x180057c29  mov     dword ptr [rsp+170h+ReturnLength], 25F8h
0x180057c31  jmp     loc_180057F99
0x180057c36  mov     r14, [r15+38h]
0x180057c3a  mov     dl, 1; bool
0x180057c3c  mov     rcx, r14; struct _USER_CACHE_ENTRY *
0x180057c3f  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x180057c44  cmp     qword ptr [rsi+130h], 0
0x180057c4c  lea     rdi, Class
0x180057c53  jz      short loc_180057CD2
0x180057c55  mov     rcx, [r14+18h]
0x180057c59  add     rcx, 18h; Resource
0x180057c5d  call    SCLockConvertExclusiveToShared
0x180057c62  mov     rcx, [rsi+8]
0x180057c66  lea     r9, [r14+118h]
0x180057c6d  mov     rax, [rsi+130h]
0x180057c74  mov     r8, r12
0x180057c77  mov     r12, [rsp+170h+TokenHandle]
0x180057c7c  mov     rdx, r12
0x180057c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c84  mov     rcx, [r14+18h]
0x180057c88  mov     ebx, eax
0x180057c8a  add     rcx, 18h; Resource
0x180057c8e  call    SCLockConvertSharedToExclusive
0x180057c93  test    ebx, ebx
0x180057c95  jz      short loc_180057CD7
0x180057c97  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057c9e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057ca3  mov     r9, rax
0x180057ca6  mov     [rsp+170h+var_140], rdi
0x180057cab  lea     rax, aDisconnectiden; "DisconnectIdentity"
0x180057cb2  mov     r8d, ebx
0x180057cb5  mov     [rsp+170h+var_148], rax
0x180057cba  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057cc1  xor     ecx, ecx
0x180057cc3  mov     dword ptr [rsp+170h+ReturnLength], 260Bh
0x180057ccb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057cd0  jmp     short loc_180057CD7
0x180057cd2  mov     r12, [rsp+170h+TokenHandle]
0x180057cd7  mov     rdx, [r14+0F0h]; void *
0x180057cde  mov     r8b, 1; bool
0x180057ce1  mov     rcx, rsi; struct _ApPluginPkg *
0x180057ce4  call    ?CleanupUserCache@@YAJPEAU_ApPluginPkg@@PEAX_N@Z; CleanupUserCache(_ApPluginPkg *,void *,bool)
0x180057ce9  mov     r8d, eax
0x180057cec  test    eax, eax
0x180057cee  jz      short loc_180057D26
0x180057cf0  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057cf7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057cfc  mov     r9, rax
0x180057cff  mov     [rsp+170h+var_140], rdi
0x180057d04  lea     rax, aCleanupusercac_0; "CleanupUserCache"
0x180057d0b  xor     ecx, ecx
0x180057d0d  mov     [rsp+170h+var_148], rax
0x180057d12  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057d19  mov     dword ptr [rsp+170h+ReturnLength], 2611h
0x180057d21  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057d26  lea     rdx, SourceString; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x180057d2d  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x180057d31  call    cs:__imp_RtlInitUnicodeString
0x180057d37  mov     rax, qword ptr [rbp+70h+var_B4+4]
0x180057d3b  lea     r9, [rsp+170h+Buffer]
0x180057d40  mov     qword ptr [rbp+70h+var_E0+4], rax
0x180057d44  lea     rdx, [rbp+70h+var_E0]
0x180057d48  mov     rax, [r13+0]
0x180057d4c  lea     rcx, [rbp+70h+DestinationString]
0x180057d50  mov     qword ptr [rbp+70h+var_E0+0Ch], rax
0x180057d54  mov     r8d, 18h
0x180057d5a  lea     rax, [rsp+170h+var_130]
0x180057d5f  mov     dword ptr [rbp+70h+var_E0], 402h
0x180057d66  mov     [rsp+170h+var_148], rax
0x180057d6b  lea     rax, [rsp+170h+var_128]
0x180057d70  mov     [rsp+170h+ReturnLength], rax
0x180057d75  call    cs:__imp_LsaICallPackage
0x180057d7b  lea     r8, aLsaicallpackag; "LsaICallPackage(status"
0x180057d82  mov     ebx, eax
0x180057d84  test    eax, eax
0x180057d86  jz      short loc_180057DBA
0x180057d88  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057d8f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057d94  mov     [rsp+170h+var_140], rdi
0x180057d99  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057da0  mov     [rsp+170h+var_148], r8
0x180057da5  mov     r9, rax
0x180057da8  mov     r8d, ebx
0x180057dab  mov     dword ptr [rsp+170h+ReturnLength], 2621h
0x180057db3  xor     ecx, ecx
0x180057db5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057dba  mov     r8d, [rsp+170h+var_130]
0x180057dbf  lea     r13, aLsaicallpackag_0; "LsaICallPackage(protocolStatus"
0x180057dc6  test    r8d, r8d
0x180057dc9  jz      short loc_180057DFF
0x180057dcb  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057dd2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057dd7  mov     [rsp+170h+var_140], rdi
0x180057ddc  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057de3  mov     [rsp+170h+var_148], r13
0x180057de8  mov     r9, rax
0x180057deb  xor     ecx, ecx
0x180057ded  mov     dword ptr [rsp+170h+ReturnLength], 2622h
0x180057df5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057dfa  mov     r8d, [rsp+170h+var_130]
0x180057dff  test    ebx, ebx
0x180057e01  js      loc_180057F56
0x180057e07  test    r8d, r8d
0x180057e0a  js      loc_180057F56
0x180057e10  mov     r9d, 8; TokenInformationLength
0x180057e16  lea     rax, [rsp+170h+var_12C]
0x180057e1b  lea     r8, [rsp+170h+hObject]; TokenInformation
0x180057e20  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x180057e25  mov     rcx, r12; TokenHandle
0x180057e28  lea     edx, [r9+0Bh]; TokenInformationClass
0x180057e2c  call    cs:__imp_NtQueryInformationToken
0x180057e32  test    eax, eax
0x180057e34  js      loc_180057F56
0x180057e3a  mov     rcx, [rsp+170h+Buffer]; Buffer
0x180057e3f  test    rcx, rcx
0x180057e42  jz      short loc_180057E53
0x180057e44  call    cs:__imp_LsaFreeReturnBuffer
0x180057e4a  mov     [rsp+170h+Buffer], 0
0x180057e53  mov     rcx, [rsp+170h+hObject]; TokenHandle
0x180057e58  lea     rax, [rsp+170h+var_12C]
0x180057e5d  mov     r9d, 38h ; '8'; TokenInformationLength
0x180057e63  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x180057e68  lea     r8, [rbp+70h+var_80]; TokenInformation
0x180057e6c  lea     edx, [r9-2Eh]; TokenInformationClass
0x180057e70  call    cs:__imp_NtQueryInformationToken
0x180057e76  mov     r8d, eax
0x180057e79  test    eax, eax
0x180057e7b  js      loc_180057F20
0x180057e81  mov     rax, qword ptr [rbp+70h+var_7C+4]
0x180057e85  lea     r9, [rsp+170h+Buffer]
0x180057e8a  mov     qword ptr [rbp+70h+var_E0+0Ch], rax
0x180057e8e  lea     rdx, [rbp+70h+var_E0]
0x180057e92  lea     rax, [rsp+170h+var_130]
0x180057e97  mov     r8d, 18h
0x180057e9d  mov     [rsp+170h+var_148], rax
0x180057ea2  lea     rcx, [rbp+70h+DestinationString]
0x180057ea6  lea     rax, [rsp+170h+var_128]
0x180057eab  mov     [rsp+170h+ReturnLength], rax
0x180057eb0  call    cs:__imp_LsaICallPackage
0x180057eb6  mov     r8d, eax
0x180057eb9  test    eax, eax
0x180057ebb  jz      short loc_180057EF3
0x180057ebd  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057ec4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057ec9  mov     r9, rax
0x180057ecc  mov     [rsp+170h+var_140], rdi
0x180057ed1  lea     rax, aLsaicallpackag; "LsaICallPackage(status"
0x180057ed8  xor     ecx, ecx
0x180057eda  mov     [rsp+170h+var_148], rax
0x180057edf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057ee6  mov     dword ptr [rsp+170h+ReturnLength], 2646h
0x180057eee  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057ef3  mov     r8d, [rsp+170h+var_130]
0x180057ef8  test    r8d, r8d
  ... truncated ...
```
