# CloudAPGetTokenBlob(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x18000bda0`
- end: `0x18000c440`
- name: `?CloudAPGetTokenBlob@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `1696`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, _QWORD *, _DWORD *Sid2)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000bda0`
- `0x18000d780`
- `0x18000f100`
- `0x180041770`
- `0x18007f9f0`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000c13e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c13e`
- `ntdll!RtlReleaseResource` at `0x18000c109`
- `ntdll!RtlReleaseResource` at `0x18000c165`
- `ntdll!RtlReleaseResource` at `0x18000c17b`
- `ntdll!RtlReleaseResource` at `0x18000c2ec`
- `ntdll!RtlReleaseResource` at `0x18000c109`
- `ntdll!RtlReleaseResource` at `0x18000c165`
- `ntdll!RtlReleaseResource` at `0x18000c17b`
- `ntdll!RtlReleaseResource` at `0x18000c2ec`
- `ntdll!RtlEqualSid` at `0x18000bf79`
- `ntdll!RtlEqualSid` at `0x18000bfb4`
- `ntdll!RtlEqualSid` at `0x18000bf79`
- `ntdll!RtlEqualSid` at `0x18000bfb4`
- `ntdll!RtlAcquireResourceShared` at `0x18000be2c`
- `ntdll!RtlAcquireResourceShared` at `0x18000bff9`
- `ntdll!RtlAcquireResourceShared` at `0x18000be2c`
- `ntdll!RtlAcquireResourceShared` at `0x18000bff9`
- `ntdll!RtlEnterCriticalSection` at `0x18000c003`
- `ntdll!RtlEnterCriticalSection` at `0x18000c003`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c077`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c077`

## string_xrefs

- `0x18000be86`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000bebe`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c18d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c1ed`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c25a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000bee3`: `Caller doesnt have TCB privilege`
- `0x18000bf3e`: `CheckPkgSID`
- `0x18000c333`: `GetCallerPackageSid`
- `0x18000c381`: `Caller's SID doesnt match the one registered by the plugin`
- `0x18000c40f`: `CopyToClientBuffer`

## pseudocode

```c
__int64 __fastcall CloudAPGetTokenBlob(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        _QWORD *a6,
        _DWORD *Sid2)
{
  unsigned int v7; // ebx
  bool v8; // cf
  struct _LOGON_SESSION *v9; // rsi
  _DWORD *v10; // r12
  struct _SECPKG_CLIENT_INFO *v11; // r14
  unsigned int CallerPackageSid; // edi
  struct _ApPluginPkg *v13; // rbp
  unsigned int v14; // edi
  char *v15; // r13
  void *v16; // rdx
  PSID v17; // r15
  const WCHAR *v18; // r8
  const char *v19; // rbx
  const char *v20; // r9
  char v21; // al
  const char *v22; // rcx
  bool v23; // zf
  char v24; // al
  const char *v25; // rcx
  bool v26; // zf
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  _QWORD *v32; // r15
  _QWORD *v33; // rax
  const char *v35; // rbx
  char v36; // al
  const char *v37; // rcx
  bool v38; // zf
  const char *v39; // rbx
  char v40; // al
  const char *v41; // rcx
  bool v42; // zf
  char v43; // al
  __int64 v44; // rax
  struct _LOGON_SESSION **v45; // rdx
  struct _USER_CACHE_ENTRY *v46; // rax
  const char *v47; // rax
  const char *v48; // rax
  const char *v49; // r9
  const char *v50; // r9
  __int64 v51; // [rsp+20h] [rbp-58h]
  int v52; // [rsp+20h] [rbp-58h]
  const char *v53; // [rsp+28h] [rbp-50h]
  struct _LOGON_SESSION *v55; // [rsp+90h] [rbp+18h] BYREF

  v7 = 0;
  v8 = a5 < 0xC;
  v9 = 0;
  v10 = Sid2;
  v11 = a2;
  v55 = 0;
  *a6 = 0;
  *v10 = 0;
  if ( v8 || !a3 )
  {
    CallerPackageSid = -1073741811;
    v35 = "";
    while ( 1 )
    {
      v43 = *(v35 - 1);
      v37 = v35--;
      v38 = v43 == 92;
      if ( v43 == 92 )
        break;
      if ( v35 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v38 = v43 == 92;
        break;
      }
    }
    v53 = "Invalid Arg(s)";
    v52 = 1454;
LABEL_57:
    if ( v38 )
      v35 = v37;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CallerPackageSid, v35, v52, v53, &Class);
    goto LABEL_48;
  }
  if ( a2->HasTcbPrivilege )
    a2 = (struct _SECPKG_CLIENT_INFO *)(a3 + 4);
  CallerPackageSid = _AcquireLogonSession(1, &a2->LogonId, &v55);
  if ( !CallerPackageSid )
  {
    RtlAcquireResourceShared(&g_PackageListLock, 1u);
    v13 = g_pPlugins;
    v9 = v55;
    if ( g_pPlugins )
    {
      v14 = g_cPlugins;
      while ( 1 )
      {
        if ( v7 >= v14 )
          goto LABEL_52;
        v15 = (char *)v13 + 392 * v7;
        if ( !memcmp_0((char *)v9 + 36, v15 + 68, 0x10u) )
          break;
        ++v7;
      }
      v16 = (void *)*((_QWORD *)v15 + 19);
      v17 = 0;
      v18 = &Class;
      Sid2 = 0;
      v19 = "";
      if ( !v16 )
      {
        if ( !v11->HasTcbPrivilege )
        {
          CallerPackageSid = -1073741790;
          v20 = "";
          do
          {
            v21 = *(v20 - 1);
            v22 = v20--;
            v23 = v21 == 92;
            if ( v21 == 92 )
              goto LABEL_16;
          }
          while ( v20 > "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" );
          v23 = v21 == 92;
LABEL_16:
          if ( v23 )
            v20 = v22;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225506LL, v20, 1386, "Caller doesnt have TCB privilege", &Class);
          goto LABEL_19;
        }
        goto LABEL_29;
      }
      if ( RtlEqualSid(qword_180085590, v16) )
        goto LABEL_33;
      CallerPackageSid = GetCallerPackageSid(v11->ClientToken, (void **)&Sid2);
      if ( CallerPackageSid )
      {
        v47 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CallerPackageSid, v47, 1403, "GetCallerPackageSid", &Class);
        v17 = Sid2;
      }
      else
      {
        v17 = Sid2;
        if ( RtlEqualSid(*((PSID *)v15 + 19), Sid2) )
        {
LABEL_29:
          CallerPackageSid = 0;
          goto LABEL_30;
        }
        CallerPackageSid = -1073741790;
        v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221225506LL,
          v48,
          1408,
          "Caller's SID doesnt match the one registered by the plugin",
          &Class);
      }
LABEL_30:
      if ( v17 )
        ((void (__fastcall *)(PSID, void *, const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v17, v16, v18);
      if ( CallerPackageSid )
      {
LABEL_19:
        while ( 1 )
        {
          v24 = *(v19 - 1);
          v25 = v19--;
          v26 = v24 == 92;
          if ( v24 == 92 )
            break;
          if ( v19 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
          {
            v26 = v24 == 92;
            break;
          }
        }
        if ( v26 )
          v19 = v25;
        LODWORD(v51) = 1476;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CallerPackageSid, v19, v51, "CheckPkgSID", &Class);
        goto LABEL_47;
      }
LABEL_33:
      v27 = *((_QWORD *)v9 + 7);
      RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v27 + 24) + 24LL), 1u);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v27 + 32));
      if ( !*(_DWORD *)(v27 + 76) )
      {
        v28 = *(_QWORD *)(v27 + 288);
        if ( v28 )
          ((void (__fastcall *)(__int64, _QWORD))g_pLsaFunctionTable->LsaUnprotectMemory)(
            v28,
            *(unsigned int *)(v27 + 280));
        v29 = *(_QWORD *)(v27 + 264);
        if ( v29 && *(_DWORD *)(v29 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v29 + *(unsigned int *)(v29 + 8));
        v30 = *(_QWORD *)(v27 + 272);
        if ( v30 && *(_DWORD *)(v30 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v30 + *(unsigned int *)(v30 + 8));
      }
      ++*(_DWORD *)(v27 + 76);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v27 + 32));
      v31 = *(unsigned int *)(v27 + 280);
      if ( (_DWORD)v31 && *(_QWORD *)(v27 + 288) )
      {
        v32 = a6;
        CallerPackageSid = ((__int64 (__fastcall *)(void **, __int64, _QWORD *))g_pLsaFunctionTable->AllocateClientBuffer)(
                             a1,
                             v31,
                             a6);
        if ( CallerPackageSid )
        {
          v49 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          LODWORD(v51) = 1490;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CallerPackageSid, v49, v51, "AllocateClientBuffer", &Class);
          goto LABEL_46;
        }
        CallerPackageSid = ((__int64 (__fastcall *)(void **, _QWORD, _QWORD, _QWORD))g_pLsaFunctionTable->CopyToClientBuffer)(
                             a1,
                             *(unsigned int *)(v27 + 280),
                             *v32,
                             *(_QWORD *)(v27 + 288));
        if ( (CallerPackageSid & 0x80000000) != 0 )
        {
          ((void (__fastcall *)(void **, _QWORD))g_pLsaFunctionTable->FreeClientBuffer)(a1, *v32);
          *v32 = 0;
          v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          LODWORD(v51) = 1503;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CallerPackageSid, v50, v51, "CopyToClientBuffer", &Class);
          goto LABEL_46;
        }
        *v10 = *(_DWORD *)(v27 + 280);
      }
      CallerPackageSid = 0;
LABEL_46:
      UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v27);
LABEL_47:
      RtlReleaseResource(&g_PackageListLock);
      goto LABEL_48;
    }
LABEL_52:
    RtlReleaseResource(&g_PackageListLock);
    CallerPackageSid = -2146893039;
    v35 = "";
    while ( 1 )
    {
      v36 = *(v35 - 1);
      v37 = v35--;
      v38 = v36 == 92;
      if ( v36 == 92 )
        break;
      if ( v35 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v38 = v36 == 92;
        break;
      }
    }
    v53 = "RefPackage";
    v52 = 1472;
    goto LABEL_57;
  }
  v39 = "";
  while ( 1 )
  {
    v40 = *(v39 - 1);
    v41 = v39--;
    v42 = v40 == 92;
    if ( v40 == 92 )
      break;
    if ( v39 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
    {
      v42 = v40 == 92;
      break;
    }
  }
  if ( v42 )
    v39 = v41;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CallerPackageSid, v39, 1467, "AcquireLogonSession", &Class);
  v9 = v55;
LABEL_48:
  if ( v9 )
  {
    RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
    v33 = *(_QWORD **)((char *)v9 + 28);
    _InterlockedDecrement((volatile signed __int32 *)v9 + 4);
    v23 = *((_DWORD *)v9 + 4) == 0;
    a6 = v33;
    if ( v23 )
    {
      v44 = *(_QWORD *)v9;
      if ( *(struct _LOGON_SESSION **)(*(_QWORD *)v9 + 8LL) != v9
        || (v45 = (struct _LOGON_SESSION **)*((_QWORD *)v9 + 1), *v45 != v9) )
      {
        __fastfail(3u);
      }
      *v45 = (struct _LOGON_SESSION *)v44;
      *(_QWORD *)(v44 + 8) = v45;
      RtlReleaseResource(&g_LogonSessionListLock);
      v46 = _FreeLogonSession(v9);
      if ( v46 )
        _ReleaseUserCacheEntry((struct _LUID *)&a6, v46);
    }
    else
    {
      RtlReleaseResource(&g_LogonSessionListLock);
    }
  }
  return CallerPackageSid;
}

```

## disassembly

```asm
0x18000bda0  mov     rax, rsp
0x18000bda3  mov     [rax+8], rcx
0x18000bda7  push    rsi
0x18000bda8  push    rdi
0x18000bda9  sub     rsp, 68h
0x18000bdad  mov     [rax+10h], rbx
0x18000bdb1  xor     ebx, ebx
0x18000bdb3  cmp     [rsp+78h+arg_20], 0Ch
0x18000bdbb  mov     esi, ebx
0x18000bdbd  mov     [rax-18h], rbp
0x18000bdc1  mov     [rax-20h], r12
0x18000bdc5  mov     r12, [rsp+78h+Sid2]
0x18000bdcd  mov     [rax-28h], r13
0x18000bdd1  mov     [rax-30h], r14
0x18000bdd5  mov     r14, rdx
0x18000bdd8  mov     [rax-38h], r15
0x18000bddc  mov     [rax+18h], rbx
0x18000bde0  mov     rax, qword ptr [rsp+78h+arg_28.LowPart]
0x18000bde8  mov     [rax], rbx
0x18000bdeb  mov     [r12], ebx
0x18000bdef  jb      loc_18000C24E
0x18000bdf5  test    r8, r8
0x18000bdf8  jz      loc_18000C24E
0x18000bdfe  cmp     [rdx+10h], bl
0x18000be01  jnz     loc_18000C318
0x18000be07  lea     r8, [rsp+78h+arg_10]; struct _LOGON_SESSION **
0x18000be0f  mov     ecx, 1; int
0x18000be14  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18000be19  mov     edi, eax
0x18000be1b  test    eax, eax
0x18000be1d  jnz     loc_18000C1E6
0x18000be23  mov     dl, 1; Wait
0x18000be25  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000be2c  call    cs:__imp_RtlAcquireResourceShared
0x18000be32  mov     rbp, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x18000be39  mov     rsi, [rsp+78h+arg_10]
0x18000be41  test    rbp, rbp
0x18000be44  jz      loc_18000C174
0x18000be4a  mov     edi, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18000be50  cmp     ebx, edi
0x18000be52  jnb     loc_18000C174
0x18000be58  mov     eax, ebx
0x18000be5a  lea     rcx, [rsi+24h]; Buf1
0x18000be5e  imul    r13, rax, 188h
0x18000be65  mov     r8d, 10h; Size
0x18000be6b  add     r13, rbp
0x18000be6e  lea     rdx, [r13+44h]; Buf2
0x18000be72  call    memcmp_0
0x18000be77  test    eax, eax
0x18000be79  jnz     loc_18000BF6B
0x18000be7f  mov     rdx, [r13+98h]; Sid2
0x18000be86  lea     rbp, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000be8d  xor     r15d, r15d
0x18000be90  lea     r8, Class
0x18000be97  mov     [rsp+78h+Sid2], r15
0x18000be9f  lea     rbx, aOnecoreDsExtCl_16+26h; ""
0x18000bea6  test    rdx, rdx
0x18000bea9  jnz     loc_18000BF72
0x18000beaf  cmp     [r14+10h], r15b
0x18000beb3  jnz     loc_18000BFC2
0x18000beb9  mov     edi, 0C0000022h
0x18000bebe  lea     rbp, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000bec5  mov     r9, rbx
0x18000bec8  movzx   eax, byte ptr [r9-1]
0x18000becd  mov     rcx, r9
0x18000bed0  dec     r9
0x18000bed3  cmp     al, 5Ch ; '\'
0x18000bed5  jz      short loc_18000BEDE
0x18000bed7  cmp     r9, rbp
0x18000beda  ja      short loc_18000BEC8
0x18000bedc  cmp     al, 5Ch ; '\'
0x18000bede  mov     [rsp+78h+var_48], r8
0x18000bee3  lea     rax, aCallerDoesntHa; "Caller doesnt have TCB privilege"
0x18000beea  cmovz   r9, rcx
0x18000beee  mov     [rsp+78h+var_50], rax
0x18000bef3  mov     r8d, edi
0x18000bef6  mov     dword ptr [rsp+78h+var_58], 56Ah
0x18000befe  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000bf05  xor     ecx, ecx
0x18000bf07  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000bf0c  lea     r14, Class
0x18000bf13  nop     dword ptr [rax+00h]
0x18000bf17  nop     word ptr [rax+rax+00000000h]
0x18000bf20  movzx   eax, byte ptr [rbx-1]
0x18000bf24  mov     rcx, rbx
0x18000bf27  dec     rbx
0x18000bf2a  cmp     al, 5Ch ; '\'
0x18000bf2c  jz      short loc_18000BF35
0x18000bf2e  cmp     rbx, rbp
0x18000bf31  ja      short loc_18000BF20
0x18000bf33  cmp     al, 5Ch ; '\'
0x18000bf35  cmovz   rbx, rcx
0x18000bf39  mov     [rsp+78h+var_48], r14
0x18000bf3e  lea     rax, aCheckpkgsid; "CheckPkgSID"
0x18000bf45  mov     r9, rbx
0x18000bf48  mov     [rsp+78h+var_50], rax
0x18000bf4d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000bf54  mov     r8d, edi
0x18000bf57  mov     dword ptr [rsp+78h+var_58], 5C4h
0x18000bf5f  xor     ecx, ecx
0x18000bf61  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000bf66  jmp     loc_18000C102
0x18000bf6b  inc     ebx
0x18000bf6d  jmp     loc_18000BE50
0x18000bf72  lea     rcx, qword_180085590; Sid1
0x18000bf79  call    cs:__imp_RtlEqualSid
0x18000bf7f  test    al, al
0x18000bf81  jnz     loc_18000C3B0
0x18000bf87  mov     rcx, [r14+18h]; TokenHandle
0x18000bf8b  lea     rdx, [rsp+78h+Sid2]; void **
0x18000bf93  call    ?GetCallerPackageSid@@YAJPEAXPEAPEAX@Z; GetCallerPackageSid(void *,void * *)
0x18000bf98  mov     edi, eax
0x18000bf9a  test    eax, eax
0x18000bf9c  jnz     loc_18000C321
0x18000bfa2  mov     r15, [rsp+78h+Sid2]
0x18000bfaa  mov     rcx, [r13+98h]; Sid1
0x18000bfb1  mov     rdx, r15; Sid2
0x18000bfb4  call    cs:__imp_RtlEqualSid
0x18000bfba  test    al, al
0x18000bfbc  jz      loc_18000C36A
0x18000bfc2  xor     edi, edi
0x18000bfc4  lea     r14, Class
0x18000bfcb  test    r15, r15
0x18000bfce  jz      short loc_18000BFE3
0x18000bfd0  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000bfd7  mov     rcx, r15
0x18000bfda  mov     rax, [rax+30h]
0x18000bfde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe3  test    edi, edi
0x18000bfe5  jnz     loc_18000BF20
0x18000bfeb  mov     rbx, [rsi+38h]
0x18000bfef  mov     dl, 1; Wait
0x18000bff1  mov     rcx, [rbx+18h]
0x18000bff5  add     rcx, 18h; Resource
0x18000bff9  call    cs:__imp_RtlAcquireResourceShared
0x18000bfff  lea     rcx, [rbx+20h]; CriticalSection
0x18000c003  call    cs:__imp_RtlEnterCriticalSection
0x18000c009  cmp     dword ptr [rbx+4Ch], 0
0x18000c00d  jnz     short loc_18000C070
0x18000c00f  mov     rcx, [rbx+120h]
0x18000c016  test    rcx, rcx
0x18000c019  jz      short loc_18000C034
0x18000c01b  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c022  mov     edx, [rbx+118h]
0x18000c028  mov     rax, [rax+168h]
0x18000c02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c034  mov     rax, [rbx+108h]
0x18000c03b  test    rax, rax
0x18000c03e  jz      short loc_18000C060
0x18000c040  mov     edx, [rax+0Ch]
0x18000c043  test    edx, edx
0x18000c045  jz      short loc_18000C060
0x18000c047  mov     ecx, [rax+8]
0x18000c04a  add     rcx, rax
0x18000c04d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c054  mov     rax, [rax+168h]
0x18000c05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c060  mov     rax, [rbx+110h]
0x18000c067  test    rax, rax
0x18000c06a  jnz     loc_18000C29B
0x18000c070  inc     dword ptr [rbx+4Ch]
0x18000c073  lea     rcx, [rbx+20h]; CriticalSection
0x18000c077  call    cs:__imp_RtlLeaveCriticalSection
0x18000c07d  mov     edx, [rbx+118h]
0x18000c083  test    edx, edx
0x18000c085  jz      short loc_18000C0F8
0x18000c087  cmp     qword ptr [rbx+120h], 0
0x18000c08f  jz      short loc_18000C0F8
0x18000c091  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c098  mov     r15, qword ptr [rsp+78h+arg_28.LowPart]
0x18000c0a0  mov     r13, [rsp+78h+arg_0]
0x18000c0a8  mov     r8, r15
0x18000c0ab  mov     rcx, r13
0x18000c0ae  mov     rax, [rax+38h]
0x18000c0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0b7  mov     edi, eax
0x18000c0b9  test    eax, eax
0x18000c0bb  jnz     loc_18000C3BC
0x18000c0c1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c0c8  mov     rcx, r13
0x18000c0cb  mov     r9, [rbx+120h]
0x18000c0d2  mov     r8, [r15]
0x18000c0d5  mov     edx, [rbx+118h]
0x18000c0db  mov     rax, [rax+48h]
0x18000c0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0e4  mov     edi, eax
0x18000c0e6  test    eax, eax
0x18000c0e8  js      loc_18000C3E2
0x18000c0ee  mov     eax, [rbx+118h]
0x18000c0f4  mov     [r12], eax
0x18000c0f8  xor     edi, edi
0x18000c0fa  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x18000c0fd  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18000c102  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000c109  call    cs:__imp_RtlReleaseResource
0x18000c10f  mov     r15, [rsp+78h+var_38]
0x18000c114  mov     r14, [rsp+78h+var_30]
0x18000c119  mov     r13, [rsp+78h+var_28]
0x18000c11e  mov     r12, [rsp+78h+var_20]
0x18000c123  mov     rbp, [rsp+78h+var_18]
0x18000c128  mov     rbx, [rsp+78h+arg_8]
0x18000c130  test    rsi, rsi
0x18000c133  jz      short loc_18000C16B
0x18000c135  mov     dl, 1; Wait
0x18000c137  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000c13e  call    cs:__imp_RtlAcquireResourceExclusive
0x18000c144  mov     rax, [rsi+1Ch]
0x18000c148  lock dec dword ptr [rsi+10h]
0x18000c14c  cmp     dword ptr [rsi+10h], 0
0x18000c150  mov     qword ptr [rsp+78h+arg_28.LowPart], rax
0x18000c158  jz      loc_18000C2C4
0x18000c15e  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000c165  call    cs:__imp_RtlReleaseResource
0x18000c16b  mov     eax, edi
0x18000c16d  add     rsp, 68h
0x18000c171  pop     rdi
0x18000c172  pop     rsi
0x18000c173  retn
0x18000c174  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000c17b  call    cs:__imp_RtlReleaseResource
0x18000c181  mov     edi, 80090311h
0x18000c186  lea     rbx, aOnecoreDsExtCl_16+26h; ""
0x18000c18d  lea     rbp, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c194  movzx   eax, byte ptr [rbx-1]
0x18000c198  mov     rcx, rbx
0x18000c19b  dec     rbx
0x18000c19e  cmp     al, 5Ch ; '\'
0x18000c1a0  jz      short loc_18000C1A9
0x18000c1a2  cmp     rbx, rbp
0x18000c1a5  ja      short loc_18000C194
0x18000c1a7  cmp     al, 5Ch ; '\'
0x18000c1a9  lea     r14, Class
0x18000c1b0  mov     [rsp+78h+var_48], r14
0x18000c1b5  lea     rax, aRefpackage; "RefPackage"
0x18000c1bc  mov     [rsp+78h+var_50], rax
0x18000c1c1  mov     dword ptr [rsp+78h+var_58], 5C0h
0x18000c1c9  cmovz   rbx, rcx
0x18000c1cd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c1d4  mov     r9, rbx
0x18000c1d7  mov     r8d, edi
0x18000c1da  xor     ecx, ecx
0x18000c1dc  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000c1e1  jmp     loc_18000C10F
0x18000c1e6  lea     rbx, aOnecoreDsExtCl_16+26h; ""
0x18000c1ed  lea     rbp, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c1f4  movzx   eax, byte ptr [rbx-1]
0x18000c1f8  mov     rcx, rbx
0x18000c1fb  dec     rbx
0x18000c1fe  cmp     al, 5Ch ; '\'
0x18000c200  jz      short loc_18000C209
0x18000c202  cmp     rbx, rbp
0x18000c205  ja      short loc_18000C1F4
0x18000c207  cmp     al, 5Ch ; '\'
0x18000c209  cmovz   rbx, rcx
0x18000c20d  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x18000c214  lea     r14, Class
0x18000c21b  mov     r9, rbx
0x18000c21e  mov     [rsp+78h+var_48], r14
0x18000c223  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c22a  mov     [rsp+78h+var_50], rax
0x18000c22f  mov     r8d, edi
0x18000c232  xor     ecx, ecx
0x18000c234  mov     dword ptr [rsp+78h+var_58], 5BBh
0x18000c23c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000c241  mov     rsi, [rsp+78h+arg_10]
0x18000c249  jmp     loc_18000C10F
0x18000c24e  mov     edi, 0C000000Dh
0x18000c253  lea     rbx, aOnecoreDsExtCl_16+26h; ""
0x18000c25a  lea     rbp, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c261  movzx   eax, byte ptr [rbx-1]
0x18000c265  mov     rcx, rbx
0x18000c268  dec     rbx
0x18000c26b  cmp     al, 5Ch ; '\'
0x18000c26d  jz      short loc_18000C276
0x18000c26f  cmp     rbx, rbp
0x18000c272  ja      short loc_18000C261
0x18000c274  cmp     al, 5Ch ; '\'
0x18000c276  lea     r14, Class
0x18000c27d  mov     [rsp+78h+var_48], r14
0x18000c282  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000c289  mov     [rsp+78h+var_50], rax
0x18000c28e  mov     dword ptr [rsp+78h+var_58], 5AEh
0x18000c296  jmp     loc_18000C1C9
0x18000c29b  mov     edx, [rax+0Ch]
0x18000c29e  test    edx, edx
0x18000c2a0  jz      loc_18000C070
0x18000c2a6  mov     ecx, [rax+8]
0x18000c2a9  add     rcx, rax
0x18000c2ac  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c2b3  mov     rax, [rax+168h]
0x18000c2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2bf  jmp     loc_18000C070
0x18000c2c4  mov     rax, [rsi]
0x18000c2c7  cmp     [rax+8], rsi
0x18000c2cb  jnz     loc_18000C439
0x18000c2d1  mov     rdx, [rsi+8]
0x18000c2d5  cmp     [rdx], rsi
0x18000c2d8  jnz     loc_18000C439
0x18000c2de  mov     [rdx], rax
0x18000c2e1  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
  ... truncated ...
```
