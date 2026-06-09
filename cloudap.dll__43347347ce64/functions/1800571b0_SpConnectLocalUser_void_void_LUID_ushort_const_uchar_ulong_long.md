# SpConnectLocalUser(void *,void *,_LUID *,ushort const *,uchar *,ulong,long *)

- ea: `0x1800571b0`
- end: `0x18005798f`
- name: `?SpConnectLocalUser@@YAJPEAX0PEAU_LUID@@PEBGPEAEKPEAJ@Z`
- size: `2015`
- prototype: `int(void *, void *, struct _LUID *, const unsigned __int16 *, unsigned __int8 *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000db68`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ee60`
- `0x18000f100`
- `0x180010320`
- `0x180015b98`
- `0x18002c130`
- `0x180032998`
- `0x180040fe4`
- `0x180042410`
- `0x180055acc`
- `0x1800571b0`
- `0x18005ea48`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005792b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005793a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057959`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005792b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005793a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057959`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800577a6`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005794a`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800577a6`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005794a`
- `ntdll!NtQueryInformationToken` at `0x18005764b`
- `ntdll!NtQueryInformationToken` at `0x18005778e`
- `ntdll!NtQueryInformationToken` at `0x1800577d1`
- `ntdll!NtQueryInformationToken` at `0x18005764b`
- `ntdll!NtQueryInformationToken` at `0x18005778e`
- `ntdll!NtQueryInformationToken` at `0x1800577d1`
- `ntdll!RtlInitUnicodeString` at `0x1800576a7`
- `ntdll!RtlInitUnicodeString` at `0x1800576a7`
- `LSASRV!LsaICallPackage` at `0x1800576ed`
- `LSASRV!LsaICallPackage` at `0x18005783d`
- `LSASRV!LsaICallPackage` at `0x1800576ed`
- `LSASRV!LsaICallPackage` at `0x18005783d`

## string_xrefs

- `0x18005728f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800572d7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005732f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005739c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057414`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057478`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800574bf`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057515`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057568`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005759c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800575fb`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057657`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800576f9`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057735`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800577dd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057849`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180057882`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800577f8`: `NtQueryInformationToken`
- `0x1800573b7`: `CreateOrAcquireUserCacheEntry`
- `0x18005774d`: `LsaICallPackage(protocolStatus`
- `0x18005789a`: `LsaICallPackage(protocolStatus`
- `0x180057493`: `OpenTokenByLogonId`
- `0x180057672`: `NtQueryInformationToken(TokenStatistics)`
- `0x180057583`: `SetMappedAadAccountSidMap`
- `0x18005734f`: `Not supported for this type of plugin`
- `0x1800574da`: `SetMappedAadAccountLocalSid`
- `0x180057535`: `UserSid`

## pseudocode

```c
__int64 __fastcall SpConnectLocalUser(
        void *a1,
        void *a2,
        struct _LUID *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        int *a7)
{
  struct _USER_CACHE_ENTRY *v8; // r14
  struct _ApPluginPkg *v9; // rsi
  __int64 (__fastcall *v11)(void *, struct _GUID *); // rax
  unsigned int v12; // edi
  const char *v13; // r9
  const char *v14; // rax
  const char *v15; // r9
  const char *v16; // rax
  const char *v17; // r9
  struct _GUID *v18; // rcx
  const char *v19; // r9
  const char *v20; // r9
  void *v21; // r8
  const char *v22; // r9
  __int64 v23; // rbx
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  const char *v29; // rax
  const char *v30; // r9
  const char *v31; // r9
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthc; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthd; // [rsp+20h] [rbp-E0h]
  char v38; // [rsp+40h] [rbp-C0h]
  int v39; // [rsp+44h] [rbp-BCh] BYREF
  ULONG v40; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+4Ch] [rbp-B4h] BYREF
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-A8h] BYREF
  struct _LUID *v44; // [rsp+60h] [rbp-A0h]
  struct _ApPluginPkg *v45; // [rsp+68h] [rbp-98h] BYREF
  struct _USER_CACHE_ENTRY *v46; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  HANDLE TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v49; // [rsp+88h] [rbp-78h] BYREF
  struct _LOGON_SESSION *v50; // [rsp+90h] [rbp-70h] BYREF
  int *v51; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v53[24]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v54; // [rsp+C8h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v56; // [rsp+DCh] [rbp-24h]
  __int128 v57; // [rsp+ECh] [rbp-14h]
  __int128 v58; // [rsp+FCh] [rbp-4h]
  int v59; // [rsp+10Ch] [rbp+Ch]
  int v60; // [rsp+110h] [rbp+10h] BYREF
  __int128 v61; // [rsp+114h] [rbp+14h]
  __int128 v62; // [rsp+124h] [rbp+24h]
  __int128 v63; // [rsp+134h] [rbp+34h]
  int v64; // [rsp+144h] [rbp+44h]

  v51 = a7;
  v44 = a3;
  v40 = 0;
  v8 = 0;
  TokenInformation = 0;
  v9 = 0;
  v59 = 0;
  v60 = 0;
  v64 = 0;
  v38 = 0;
  v50 = 0;
  TokenHandle = 0;
  Buffer = 0;
  hObject = 0;
  v49 = 0;
  v41 = 0;
  v54 = 0;
  v39 = 0;
  v11 = (__int64 (__fastcall *)(void *, struct _GUID *))*((_QWORD *)g_pLsaIdProvHostFunctionTable + 10);
  v42 = 0;
  DestinationString = 0;
  v46 = 0;
  memset(v53, 0, sizeof(v53));
  v45 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v12 = v11(a1, &v54);
  if ( v12 )
  {
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v13, 9421, "GetProvInfo", &Class);
    goto LABEL_44;
  }
  v12 = RefPackage(&v54, &v45);
  if ( v12 )
  {
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v14, 9424, "RefPackage", &Class);
    v9 = v45;
    goto LABEL_44;
  }
  v9 = v45;
  if ( (*((_BYTE *)v45 + 160) & 4) == 0 )
  {
    v12 = _CreateOrAcquireUserCacheEntry(1, (struct _GUID *)((char *)v45 + 68), a4, 0, &v46);
    if ( v12 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLength) = 9444;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v16, ReturnLength, "CreateOrAcquireUserCacheEntry", &Class);
      v8 = v46;
      goto LABEL_44;
    }
    v8 = v46;
    LockAndUnProtectUserCacheEntry(v46, 1);
    v38 = 1;
    v12 = CreateLogonSession(v44, v8, 0, &v50);
    if ( v12 )
    {
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLength) = 9456;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v17, ReturnLength, "AddLogonSession", &Class);
      goto LABEL_44;
    }
    if ( *((char *)v9 + 160) < 0 )
    {
      v12 = ((__int64 (__fastcall *)(struct _LUID *, HANDLE *))g_pLsaFunctionTable->OpenTokenByLogonId)(v44, &hObject);
      if ( v12 )
      {
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLength) = 9463;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v19, ReturnLength, "OpenTokenByLogonId", &Class);
        goto LABEL_44;
      }
      v12 = SetMappedAadAccountLocalSid(v18, a4, hObject);
      if ( v12 )
      {
        v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLength) = 9471;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v20, ReturnLength, "SetMappedAadAccountLocalSid", &Class);
        goto LABEL_44;
      }
    }
    if ( *(_DWORD *)a5 == 84 )
    {
      if ( *((char *)v9 + 160) >= 0 )
      {
        v12 = -1073741822;
        v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLength) = 9492;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225474LL, v25, ReturnLength, "KerbLuidLogon", &Class);
        goto LABEL_46;
      }
      v21 = (void *)*((_QWORD *)v8 + 30);
      if ( !v21 )
      {
        v12 = -1073741595;
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLength) = 9484;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v22, ReturnLength, "UserSid", &Class);
        goto LABEL_46;
      }
      v23 = *((_QWORD *)a5 + 7);
      v12 = SetMappedAadAccountSidMap((struct _GUID *)((char *)v9 + 68), a4, v21);
      if ( v12 )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLength) = 9487;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v24, ReturnLength, "SetMappedAadAccountSidMap", &Class);
        goto LABEL_44;
      }
    }
    else
    {
      v12 = PerformLSALogonForConnection(a2, a5, a6, &TokenHandle, &v41);
      if ( v12 )
      {
        v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLengtha) = 9504;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v26, ReturnLengtha, "PerformLSALogonForConnection", &Class);
        goto LABEL_44;
      }
      v12 = NtQueryInformationToken(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &v40);
      if ( v12 )
      {
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLengthb) = 9513;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          v12,
          v27,
          ReturnLengthb,
          "NtQueryInformationToken(TokenStatistics)",
          &Class);
        goto LABEL_44;
      }
      v23 = *(_QWORD *)((char *)&v56 + 4);
    }
    UnlockAndProtectUserCacheEntry(v8);
    v38 = 0;
    RtlInitUnicodeString(&DestinationString, L"Negotiate");
    *(_QWORD *)&v53[4] = v23;
    *(_DWORD *)v53 = 1026;
    *(struct _LUID *)&v53[12] = *v44;
    v12 = LsaICallPackage(&DestinationString, v53, 24, &Buffer, &v42, &v39);
    if ( v12 )
    {
      v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLengthc) = 9537;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v28, ReturnLengthc, "LsaICallPackage(status", &Class);
      goto LABEL_44;
    }
    v12 = v39;
    if ( v39 >= 0 )
    {
      if ( *((char *)v9 + 160) >= 0 || NtQueryInformationToken(a2, TokenLinkedToken, &v49, 8u, &v40) < 0 )
        goto LABEL_45;
      if ( Buffer )
      {
        LsaFreeReturnBuffer(Buffer);
        Buffer = 0;
      }
      v12 = NtQueryInformationToken(v49, TokenStatistics, &v60, 0x38u, &v40);
      if ( v12 )
      {
        v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLengthd) = 9577;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v30, ReturnLengthd, "NtQueryInformationToken", &Class);
        goto LABEL_44;
      }
      *(_QWORD *)&v53[12] = *(_QWORD *)((char *)&v61 + 4);
      v12 = LsaICallPackage(&DestinationString, v53, 24, &Buffer, &v42, &v39);
      if ( v12 )
      {
        v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLengthc) = 9588;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v31, ReturnLengthc, "LsaICallPackage(status", &Class);
        goto LABEL_44;
      }
      v12 = v39;
      if ( v39 >= 0 )
      {
LABEL_45:
        v12 = v41;
        goto LABEL_46;
      }
      v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLengthc) = 9593;
    }
    else
    {
      v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLengthc) = 9542;
    }
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v29, ReturnLengthc, "LsaICallPackage(protocolStatus", &Class);
LABEL_44:
    if ( (v12 & 0x80000000) != 0 )
      goto LABEL_46;
    goto LABEL_45;
  }
  v12 = -1073741637;
  v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225659LL, v15, 9430, "Not supported for this type of plugin", &Class);
LABEL_46:
  *v51 = v41;
  ReleaseLogonSession(v50);
  if ( v38 )
    UnlockAndProtectUserCacheEntry(v8);
  _ReleaseUserCacheEntry(0, v8);
  if ( (v12 & 0x80000000) != 0 && v9 && *((char *)v9 + 160) < 0 && a4 )
    DeleteMappedAadAccountInfo((struct _GUID *)((char *)v9 + 68), a4);
  DerefPackage(v9);
  if ( hObject )
    CloseHandle(hObject);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v49 )
    CloseHandle(v49);
  if ( (v12 & 0x80000000) != 0 )
    RemoveLogonSession(v44);
  return v12;
}

```

## disassembly

```asm
0x1800571b0  push    rbp
0x1800571b2  push    rbx
0x1800571b3  push    rsi
0x1800571b4  push    rdi
0x1800571b5  push    r12
0x1800571b7  push    r13
0x1800571b9  push    r14
0x1800571bb  push    r15
0x1800571bd  lea     rbp, [rsp-58h]
0x1800571c2  sub     rsp, 158h
0x1800571c9  mov     rax, cs:__security_cookie
0x1800571d0  xor     rax, rsp
0x1800571d3  mov     [rbp+90h+var_48], rax
0x1800571d7  mov     rax, [rbp+90h+arg_30]
0x1800571de  xorps   xmm0, xmm0
0x1800571e1  mov     rbx, [rbp+90h+arg_20]
0x1800571e8  mov     r13, rdx
0x1800571eb  mov     [rbp+90h+var_F8], rax
0x1800571ef  lea     rdx, [rbp+90h+var_C8]
0x1800571f3  xor     eax, eax
0x1800571f5  mov     [rsp+190h+var_130], r8
0x1800571fa  mov     [rbp+90h+var_D0], rax
0x1800571fe  xorps   xmm1, xmm1
0x180057201  mov     [rsp+190h+var_148], eax
0x180057205  xor     r14d, r14d
0x180057208  mov     [rbp+90h+TokenInformation], eax
0x18005720b  xor     esi, esi
0x18005720d  mov     [rbp+90h+var_84], eax
0x180057210  mov     r12, r9
0x180057213  mov     [rbp+90h+var_80], eax
0x180057216  mov     [rbp+90h+var_4C], eax
0x180057219  mov     [rsp+190h+var_150], al
0x18005721d  mov     [rbp+90h+var_100], rax
0x180057221  mov     [rbp+90h+TokenHandle], rax
0x180057225  mov     [rsp+190h+Buffer], rax
0x18005722a  mov     [rsp+190h+hObject], rax
0x18005722f  mov     [rbp+90h+var_108], rax
0x180057233  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18005723a  mov     [rsp+190h+var_144], 0
0x180057242  movups  xmmword ptr [rbp+90h+var_C8.Data1], xmm0
0x180057246  mov     [rsp+190h+var_14C], 0
0x18005724e  mov     rax, [rax+50h]
0x180057252  mov     [rsp+190h+var_140], 0
0x18005725a  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18005725e  mov     [rsp+190h+var_120], r14
0x180057263  movups  [rbp+90h+var_E0], xmm1
0x180057267  mov     [rsp+190h+var_128], rsi
0x18005726c  movups  [rbp+90h+var_B4], xmm0
0x180057270  movups  [rbp+90h+var_A4], xmm0
0x180057274  movups  [rbp+90h+var_94], xmm0
0x180057278  movups  [rbp+90h+var_7C], xmm0
0x18005727c  movups  [rbp+90h+var_6C], xmm0
0x180057280  movups  [rbp+90h+var_5C], xmm0
0x180057284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057289  mov     edi, eax
0x18005728b  test    eax, eax
0x18005728d  jz      short loc_1800572C3
0x18005728f  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057296  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005729b  mov     r9, rax
0x18005729e  lea     rcx, Class
0x1800572a5  mov     [rsp+190h+var_160], rcx
0x1800572aa  lea     rax, aGetprovinfo; "GetProvInfo"
0x1800572b1  mov     [rsp+190h+var_168], rax
0x1800572b6  mov     dword ptr [rsp+190h+ReturnLength], 24CDh
0x1800572be  jmp     loc_1800578B1
0x1800572c3  lea     rdx, [rsp+190h+var_128]; struct _ApPluginPkg **
0x1800572c8  lea     rcx, [rbp+90h+var_C8]; struct _GUID *
0x1800572cc  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x1800572d1  mov     edi, eax
0x1800572d3  test    eax, eax
0x1800572d5  jz      short loc_180057321
0x1800572d7  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800572de  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800572e3  mov     r9, rax
0x1800572e6  lea     rcx, Class
0x1800572ed  mov     [rsp+190h+var_160], rcx
0x1800572f2  lea     rax, aRefpackage; "RefPackage"
0x1800572f9  mov     [rsp+190h+var_168], rax
0x1800572fe  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180057305  mov     r8d, edi
0x180057308  mov     dword ptr [rsp+190h+ReturnLength], 24D0h
0x180057310  xor     ecx, ecx
0x180057312  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057317  mov     rsi, [rsp+190h+var_128]
0x18005731c  jmp     loc_1800578C2
0x180057321  mov     rsi, [rsp+190h+var_128]
0x180057326  test    byte ptr [rsi+0A0h], 4
0x18005732d  jz      short loc_180057379
0x18005732f  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057336  mov     edi, 0C00000BBh
0x18005733b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057340  mov     r9, rax
0x180057343  lea     rcx, Class
0x18005734a  mov     [rsp+190h+var_160], rcx
0x18005734f  lea     rax, aNotSupportedFo; "Not supported for this type of plugin"
0x180057356  mov     [rsp+190h+var_168], rax
0x18005735b  mov     dword ptr [rsp+190h+ReturnLength], 24D6h
0x180057363  mov     r8d, edi
0x180057366  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005736d  xor     ecx, ecx
0x18005736f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180057374  jmp     loc_1800578CA
0x180057379  xor     r9d, r9d; int
0x18005737c  lea     rax, [rsp+190h+var_120]
0x180057381  mov     r8, r12; unsigned __int16 *
0x180057384  mov     [rsp+190h+ReturnLength], rax; struct _USER_CACHE_ENTRY **
0x180057389  lea     rdx, [rsi+44h]; struct _GUID *
0x18005738d  lea     ecx, [r9+1]; int
0x180057391  call    ?_CreateOrAcquireUserCacheEntry@@YAJHPEAU_GUID@@PEBGHPEAPEAU_USER_CACHE_ENTRY@@@Z; _CreateOrAcquireUserCacheEntry(int,_GUID *,ushort const *,int,_USER_CACHE_ENTRY * *)
0x180057396  mov     edi, eax
0x180057398  test    eax, eax
0x18005739a  jz      short loc_1800573E6
0x18005739c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800573a3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800573a8  mov     r9, rax
0x1800573ab  lea     rcx, Class
0x1800573b2  mov     [rsp+190h+var_160], rcx
0x1800573b7  lea     rax, aCreateoracquir_3; "CreateOrAcquireUserCacheEntry"
0x1800573be  mov     [rsp+190h+var_168], rax
0x1800573c3  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800573ca  mov     r8d, edi
0x1800573cd  mov     dword ptr [rsp+190h+ReturnLength], 24E4h
0x1800573d5  xor     ecx, ecx
0x1800573d7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800573dc  mov     r14, [rsp+190h+var_120]
0x1800573e1  jmp     loc_1800578C2
0x1800573e6  mov     r14, [rsp+190h+var_120]
0x1800573eb  mov     dl, 1; bool
0x1800573ed  mov     rcx, r14; struct _USER_CACHE_ENTRY *
0x1800573f0  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x1800573f5  mov     rcx, [rsp+190h+var_130]; struct _LUID *
0x1800573fa  lea     r9, [rbp+90h+var_100]; struct _LOGON_SESSION **
0x1800573fe  xor     r8d, r8d; struct _SCARD_PIN *
0x180057401  mov     [rsp+190h+var_150], 1
0x180057406  mov     rdx, r14; struct _USER_CACHE_ENTRY *
0x180057409  call    ?CreateLogonSession@@YAJPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@PEAU_SCARD_PIN@@PEAPEAU_LOGON_SESSION@@@Z; CreateLogonSession(_LUID *,_USER_CACHE_ENTRY *,_SCARD_PIN *,_LOGON_SESSION * *)
0x18005740e  mov     edi, eax
0x180057410  test    eax, eax
0x180057412  jz      short loc_180057448
0x180057414  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005741b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057420  mov     r9, rax
0x180057423  lea     rcx, Class
0x18005742a  mov     [rsp+190h+var_160], rcx
0x18005742f  lea     rax, aAddlogonsessio; "AddLogonSession"
0x180057436  mov     [rsp+190h+var_168], rax
0x18005743b  mov     dword ptr [rsp+190h+ReturnLength], 24F0h
0x180057443  jmp     loc_1800578B1
0x180057448  test    byte ptr [rsi+0A0h], 80h
0x18005744f  jz      loc_1800574F3
0x180057455  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005745c  lea     rdx, [rsp+190h+hObject]
0x180057461  mov     rcx, [rsp+190h+var_130]
0x180057466  mov     rax, [rax+170h]
0x18005746d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057472  mov     edi, eax
0x180057474  test    eax, eax
0x180057476  jz      short loc_1800574AC
0x180057478  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005747f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057484  mov     r9, rax
0x180057487  lea     rcx, Class
0x18005748e  mov     [rsp+190h+var_160], rcx
0x180057493  lea     rax, aOpentokenbylog; "OpenTokenByLogonId"
0x18005749a  mov     [rsp+190h+var_168], rax
0x18005749f  mov     dword ptr [rsp+190h+ReturnLength], 24F7h
0x1800574a7  jmp     loc_1800578B1
0x1800574ac  mov     r8, [rsp+190h+hObject]; void *
0x1800574b1  mov     rdx, r12; unsigned __int16 *
0x1800574b4  call    ?SetMappedAadAccountLocalSid@@YAJPEAU_GUID@@PEBGPEAX@Z; SetMappedAadAccountLocalSid(_GUID *,ushort const *,void *)
0x1800574b9  mov     edi, eax
0x1800574bb  test    eax, eax
0x1800574bd  jz      short loc_1800574F3
0x1800574bf  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800574c6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800574cb  mov     r9, rax
0x1800574ce  lea     rcx, Class
0x1800574d5  mov     [rsp+190h+var_160], rcx
0x1800574da  lea     rax, aSetmappedaadac; "SetMappedAadAccountLocalSid"
0x1800574e1  mov     [rsp+190h+var_168], rax
0x1800574e6  mov     dword ptr [rsp+190h+ReturnLength], 24FFh
0x1800574ee  jmp     loc_1800578B1
0x1800574f3  cmp     dword ptr [rbx], 54h ; 'T'
0x1800574f6  jnz     loc_1800575D5
0x1800574fc  test    byte ptr [rsi+0A0h], 80h
0x180057503  jz      loc_18005759C
0x180057509  mov     r8, [r14+0F0h]; SourceSid
0x180057510  test    r8, r8
0x180057513  jnz     short loc_18005754E
0x180057515  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005751c  mov     edi, 0C00000E5h
0x180057521  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057526  mov     r9, rax
0x180057529  lea     rcx, Class
0x180057530  mov     [rsp+190h+var_160], rcx
0x180057535  lea     rax, aUsersid; "UserSid"
0x18005753c  mov     [rsp+190h+var_168], rax
0x180057541  mov     dword ptr [rsp+190h+ReturnLength], 250Ch
0x180057549  jmp     loc_180057363
0x18005754e  mov     rbx, [rbx+38h]
0x180057552  lea     rcx, [rsi+44h]; struct _GUID *
0x180057556  mov     rdx, r12; Src
0x180057559  call    ?SetMappedAadAccountSidMap@@YAJPEAU_GUID@@PEBGPEAX@Z; SetMappedAadAccountSidMap(_GUID *,ushort const *,void *)
0x18005755e  mov     edi, eax
0x180057560  test    eax, eax
0x180057562  jz      loc_18005768F
0x180057568  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005756f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057574  mov     r9, rax
0x180057577  lea     rcx, Class
0x18005757e  mov     [rsp+190h+var_160], rcx
0x180057583  lea     rax, aSetmappedaadac_0; "SetMappedAadAccountSidMap"
0x18005758a  mov     [rsp+190h+var_168], rax
0x18005758f  mov     dword ptr [rsp+190h+ReturnLength], 250Fh
0x180057597  jmp     loc_1800578B1
0x18005759c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800575a3  mov     edi, 0C0000002h
0x1800575a8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800575ad  mov     r9, rax
0x1800575b0  lea     rcx, Class
0x1800575b7  mov     [rsp+190h+var_160], rcx
0x1800575bc  lea     rax, aKerbluidlogon; "KerbLuidLogon"
0x1800575c3  mov     [rsp+190h+var_168], rax
0x1800575c8  mov     dword ptr [rsp+190h+ReturnLength], 2514h
0x1800575d0  jmp     loc_180057363
0x1800575d5  mov     r8d, [rbp+90h+arg_28]; unsigned int
0x1800575dc  lea     rax, [rsp+190h+var_144]
0x1800575e1  lea     r9, [rbp+90h+TokenHandle]; void **
0x1800575e5  mov     [rsp+190h+ReturnLength], rax; int *
0x1800575ea  mov     rdx, rbx; unsigned __int8 *
0x1800575ed  mov     rcx, r13; void *
0x1800575f0  call    ?PerformLSALogonForConnection@@YAJPEAXPEAEKPEAPEAXPEAJ@Z; PerformLSALogonForConnection(void *,uchar *,ulong,void * *,long *)
0x1800575f5  mov     edi, eax
0x1800575f7  test    eax, eax
0x1800575f9  jz      short loc_18005762F
0x1800575fb  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057602  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057607  mov     r9, rax
0x18005760a  lea     rcx, Class
0x180057611  mov     [rsp+190h+var_160], rcx
0x180057616  lea     rax, aPerformlsalogo; "PerformLSALogonForConnection"
0x18005761d  mov     [rsp+190h+var_168], rax
0x180057622  mov     dword ptr [rsp+190h+ReturnLength], 2520h
0x18005762a  jmp     loc_1800578B1
0x18005762f  mov     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x180057633  lea     rax, [rsp+190h+var_148]
0x180057638  mov     r9d, 38h ; '8'; TokenInformationLength
0x18005763e  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x180057643  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x180057647  lea     edx, [r9-2Eh]; TokenInformationClass
0x18005764b  call    cs:__imp_NtQueryInformationToken
0x180057651  mov     edi, eax
0x180057653  test    eax, eax
0x180057655  jz      short loc_18005768B
0x180057657  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005765e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057663  mov     r9, rax
0x180057666  lea     rcx, Class
0x18005766d  mov     [rsp+190h+var_160], rcx
0x180057672  lea     rax, aNtqueryinforma_0; "NtQueryInformationToken(TokenStatistics"...
0x180057679  mov     [rsp+190h+var_168], rax
0x18005767e  mov     dword ptr [rsp+190h+ReturnLength], 2529h
0x180057686  jmp     loc_1800578B1
0x18005768b  mov     rbx, qword ptr [rbp+90h+var_B4+4]
0x18005768f  mov     rcx, r14; struct _USER_CACHE_ENTRY *
0x180057692  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180057697  lea     rdx, aNegotiate; "Negotiate"
0x18005769e  mov     [rsp+190h+var_150], 0
0x1800576a3  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800576a7  call    cs:__imp_RtlInitUnicodeString
0x1800576ad  mov     rax, [rsp+190h+var_130]
0x1800576b2  lea     r9, [rsp+190h+Buffer]
0x1800576b7  mov     qword ptr [rbp+90h+var_E0+4], rbx
0x1800576bb  lea     rdx, [rbp+90h+var_E0]
0x1800576bf  mov     ebx, 18h
0x1800576c4  mov     dword ptr [rbp+90h+var_E0], 402h
0x1800576cb  mov     r8d, ebx
0x1800576ce  lea     rcx, [rbp+90h+DestinationString]
0x1800576d2  mov     rax, [rax]
0x1800576d5  mov     qword ptr [rbp+90h+var_E0+0Ch], rax
0x1800576d9  lea     rax, [rsp+190h+var_14C]
0x1800576de  mov     [rsp+190h+var_168], rax
0x1800576e3  lea     rax, [rsp+190h+var_140]
0x1800576e8  mov     [rsp+190h+ReturnLength], rax
0x1800576ed  call    cs:__imp_LsaICallPackage
0x1800576f3  mov     edi, eax
0x1800576f5  test    eax, eax
0x1800576f7  jz      short loc_18005772D
0x1800576f9  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057700  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057705  mov     r9, rax
0x180057708  lea     rcx, Class
0x18005770f  mov     [rsp+190h+var_160], rcx
0x180057714  lea     rax, aLsaicallpackag; "LsaICallPackage(status"
0x18005771b  mov     [rsp+190h+var_168], rax
0x180057720  mov     dword ptr [rsp+190h+ReturnLength], 2541h
0x180057728  jmp     loc_1800578B1
0x18005772d  mov     edi, [rsp+190h+var_14C]
0x180057731  test    edi, edi
  ... truncated ...
```
