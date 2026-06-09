# CloudAPCallPluginGeneric(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x18001b600`
- end: `0x18001bd8e`
- name: `?CloudAPCallPluginGeneric@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `1934`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x180010320`
- `0x18001b600`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x18001b907`
- `RPCRT4!UuidEqual` at `0x18001b907`
- `ntdll!RtlReleaseResource` at `0x18001b77b`
- `ntdll!RtlReleaseResource` at `0x18001bad6`
- `ntdll!RtlReleaseResource` at `0x18001bd4a`
- `ntdll!RtlReleaseResource` at `0x18001b77b`
- `ntdll!RtlReleaseResource` at `0x18001bad6`
- `ntdll!RtlReleaseResource` at `0x18001bd4a`
- `ntdll!RtlAcquireResourceShared` at `0x18001b720`
- `ntdll!RtlAcquireResourceShared` at `0x18001b923`
- `ntdll!RtlAcquireResourceShared` at `0x18001b720`
- `ntdll!RtlAcquireResourceShared` at `0x18001b923`
- `ntdll!RtlEnterCriticalSection` at `0x18001b92d`
- `ntdll!RtlEnterCriticalSection` at `0x18001ba39`
- `ntdll!RtlEnterCriticalSection` at `0x18001b92d`
- `ntdll!RtlEnterCriticalSection` at `0x18001ba39`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b9c0`
- `ntdll!RtlLeaveCriticalSection` at `0x18001bac8`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b9c0`
- `ntdll!RtlLeaveCriticalSection` at `0x18001bac8`

## string_xrefs

- `0x18001b697`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001b6cd`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001b781`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001b7c3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001b822`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001bc69`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001bc3a`: `CopyToClientBuffer`
- `0x18001b7e3`: `Plugin doesn't implement CallPkg`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudAPCallPluginGeneric(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  char v7; // bl
  __int64 v10; // r13
  _QWORD *v11; // r14
  int v12; // eax
  unsigned int v13; // eax
  int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  unsigned int v17; // edx
  __int64 v18; // rax
  _QWORD *v19; // rcx
  UUID *v20; // r14
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // rbx
  const char *v24; // r9
  char v25; // al
  const char *v26; // rcx
  bool v27; // zf
  char v28; // al
  const char *v29; // rcx
  bool v30; // zf
  struct _LOGON_SESSION *v31; // rsi
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  void *v35; // rax
  const char *v36; // r9
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  size_t *v40; // r8
  char v41; // al
  const char *v42; // rcx
  bool v43; // zf
  char v44; // al
  const char *v45; // r9
  char v46; // al
  _BYTE *v47; // rcx
  __int64 v48; // rax
  _BYTE *v49; // rcx
  __int64 v50; // rax
  __int64 v52; // [rsp+28h] [rbp-61h]
  __int64 v53; // [rsp+28h] [rbp-61h]
  const char *v54; // [rsp+30h] [rbp-59h]
  RPC_STATUS Status; // [rsp+48h] [rbp-41h] BYREF
  _QWORD *v56; // [rsp+50h] [rbp-39h]
  struct _LOGON_SESSION *v57; // [rsp+58h] [rbp-31h] BYREF
  __int128 v58; // [rsp+60h] [rbp-29h] BYREF
  size_t Size[2]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v60; // [rsp+80h] [rbp-9h] BYREF

  v7 = 0;
  v10 = 0;
  v11 = 0;
  Status = 0;
  v57 = 0;
  v60 = 0;
  *a6 = 0;
  v58 = 0;
  *(_OWORD *)Size = 0;
  *a7 = 0;
  if ( a5 < 0x1C || !a3 )
  {
    v14 = -1073741811;
    v23 = "";
    while ( 1 )
    {
      v46 = *(v23 - 1);
      v42 = v23--;
      v43 = v46 == 92;
      if ( v46 == 92 )
        break;
      if ( v23 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v43 = v46 == 92;
        break;
      }
    }
    v54 = "Invalid Arg(s)";
    LODWORD(v52) = 1558;
    goto LABEL_79;
  }
  v12 = *((_DWORD *)a3 + 5);
  if ( v12 )
  {
    v13 = v12 + 27;
    if ( v13 < 0x1B )
    {
      v14 = -1073741675;
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v16, 1565, "RtlULongAdd", &Class);
      goto LABEL_83;
    }
    if ( a5 < v13 )
    {
      v14 = -1073741811;
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v15, 1570, "Invalid length", &Class);
      goto LABEL_83;
    }
  }
  RtlAcquireResourceShared(&g_PackageListLock, 1u);
  if ( !g_pPlugins || (v17 = 0, !g_cPlugins) )
  {
LABEL_13:
    v11 = 0;
    RtlReleaseResource(&g_PackageListLock);
    v14 = -2146893039;
    v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v21, 1577, "RefPackage", &Class);
    goto LABEL_83;
  }
  while ( 1 )
  {
    v18 = *(_QWORD *)(a3 + 4);
    v19 = (_QWORD *)((char *)g_pPlugins + 392 * v17);
    v56 = v19;
    v20 = (UUID *)((char *)v19 + 68);
    if ( v18 == *(_QWORD *)((char *)v19 + 68) && *(_QWORD *)(a3 + 12) == *(_QWORD *)((char *)v19 + 76) )
      break;
    if ( ++v17 >= g_cPlugins )
      goto LABEL_13;
  }
  if ( !v19[41] )
  {
    v14 = -1073741637;
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225659LL, v22, 1582, "Plugin doesn't implement CallPkg", &Class);
LABEL_16:
    v11 = v56;
    goto LABEL_83;
  }
  v14 = _AcquireLogonSession(1, &a2->LogonId, &v57);
  v23 = "";
  if ( v14 >= 0 )
  {
    v31 = v57;
    if ( UuidEqual((UUID *)((char *)v57 + 36), v20, &Status) )
    {
      v10 = *((_QWORD *)v31 + 7);
      RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v10 + 24) + 24LL), 1u);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v10 + 32));
      if ( !*(_DWORD *)(v10 + 76) )
      {
        v32 = *(_QWORD *)(v10 + 288);
        if ( v32 )
          ((void (__fastcall *)(__int64, _QWORD))g_pLsaFunctionTable->LsaUnprotectMemory)(
            v32,
            *(unsigned int *)(v10 + 280));
        v33 = *(_QWORD *)(v10 + 264);
        if ( v33 && *(_DWORD *)(v33 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v33 + *(unsigned int *)(v33 + 8));
        v34 = *(_QWORD *)(v10 + 272);
        if ( v34 && *(_DWORD *)(v34 + 12) )
          ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v34 + *(unsigned int *)(v34 + 8));
      }
      ++*(_DWORD *)(v10 + 76);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v10 + 32));
      LODWORD(Size[0]) = *(_DWORD *)(v10 + 280);
      v35 = (void *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
      Size[1] = (size_t)v35;
      if ( !v35 )
      {
        v7 = 1;
        v14 = -1073741801;
        v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v36, 1625, "AllocateLsaHeap", &Class);
        goto LABEL_16;
      }
      memcpy_0(v35, *(const void **)(v10 + 288), LODWORD(Size[0]));
      if ( v10 )
      {
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v10 + 32));
        v27 = (*(_DWORD *)(v10 + 76))-- == 1;
        if ( v27 )
        {
          v37 = *(_QWORD *)(v10 + 288);
          if ( v37 )
            ((void (__fastcall *)(__int64, _QWORD))g_pLsaFunctionTable->LsaProtectMemory)(
              v37,
              *(unsigned int *)(v10 + 280));
          v38 = *(_QWORD *)(v10 + 264);
          if ( v38 && *(_DWORD *)(v38 + 12) )
            ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaProtectMemory)(v38 + *(unsigned int *)(v38 + 8));
          v39 = *(_QWORD *)(v10 + 272);
          if ( v39 && *(_DWORD *)(v39 + 12) )
            ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaProtectMemory)(v39 + *(unsigned int *)(v39 + 8));
        }
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v10 + 32));
        RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v10 + 24) + 24LL));
      }
    }
  }
  else
  {
    v24 = "";
    while ( 1 )
    {
      v25 = *(v24 - 1);
      v26 = v24--;
      v27 = v25 == 92;
      if ( v25 == 92 )
        break;
      if ( v24 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v27 = v25 == 92;
        break;
      }
    }
    if ( v27 )
      v24 = v26;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v14, v24, 1589, "AcquireLogonSession", &Class);
    if ( v14 == -1073741801 || v14 == -1073741670 )
    {
      while ( 1 )
      {
        v28 = *(v23 - 1);
        v29 = v23--;
        v30 = v28 == 92;
        if ( v28 == 92 )
          break;
        if ( v23 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
        {
          v30 = v28 == 92;
          break;
        }
      }
      if ( v30 )
        v23 = v29;
      LODWORD(v53) = 1593;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v14, v23, v53, "AcquireLogonSession", &Class);
      v11 = v56;
      goto LABEL_82;
    }
  }
  v40 = Size;
  v11 = v56;
  LODWORD(v60) = *((_DWORD *)a3 + 5);
  *((_QWORD *)&v60 + 1) = a3 + 24;
  if ( !Size[1] )
    v40 = 0;
  v14 = ((__int64 (__fastcall *)(_QWORD, HANDLE, size_t *, __int128 *, __int128 *))v56[41])(
          v56[1],
          a2->ClientToken,
          v40,
          &v60,
          &v58);
  if ( v14 < 0 )
  {
    LODWORD(v58) = 0;
    *((_QWORD *)&v58 + 1) = 0;
    while ( 1 )
    {
      v41 = *(v23 - 1);
      v42 = v23--;
      v43 = v41 == 92;
      if ( v41 == 92 )
        break;
      if ( v23 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v43 = v41 == 92;
        break;
      }
    }
    v54 = "CallPkg";
    LODWORD(v52) = 1649;
LABEL_79:
    if ( v43 )
      v23 = v42;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v14, v23, v52, v54, &Class);
    goto LABEL_82;
  }
  if ( !(_DWORD)v58 || !*((_QWORD *)&v58 + 1) )
    goto LABEL_73;
  v14 = ((__int64 (__fastcall *)(void **, _QWORD, void **))g_pLsaFunctionTable->AllocateClientBuffer)(
          a1,
          (unsigned int)v58,
          a6);
  if ( v14 )
  {
    while ( 1 )
    {
      v44 = *(v23 - 1);
      v42 = v23--;
      v43 = v44 == 92;
      if ( v44 == 92 )
        break;
      if ( v23 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v43 = v44 == 92;
        break;
      }
    }
    v54 = "AllocateClientBuffer";
    LODWORD(v52) = 1658;
    goto LABEL_79;
  }
  v14 = ((__int64 (__fastcall *)(void **, _QWORD, _QWORD, _QWORD))g_pLsaFunctionTable->CopyToClientBuffer)(
          a1,
          (unsigned int)v58,
          *a6,
          *((_QWORD *)&v58 + 1));
  if ( v14 >= 0 )
  {
    *a7 = v58;
LABEL_73:
    v14 = 0;
    goto LABEL_82;
  }
  ((void (__fastcall *)(void **, _QWORD))g_pLsaFunctionTable->FreeClientBuffer)(a1, *a6);
  *a6 = 0;
  v45 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  LODWORD(v52) = 1671;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v14, v45, v52, "CopyToClientBuffer", &Class);
LABEL_82:
  v7 = 0;
LABEL_83:
  v47 = (_BYTE *)Size[1];
  if ( Size[1] )
  {
    v48 = LODWORD(Size[0]);
    if ( LODWORD(Size[0]) )
    {
      do
      {
        *v47++ = 0;
        --v48;
      }
      while ( v48 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( v7 )
    UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v10);
  ReleaseLogonSession(v57);
  if ( v11 )
    RtlReleaseResource(&g_PackageListLock);
  v49 = (_BYTE *)*((_QWORD *)&v58 + 1);
  if ( *((_QWORD *)&v58 + 1) )
  {
    v50 = (unsigned int)v58;
    if ( (_DWORD)v58 )
    {
      do
      {
        *v49++ = 0;
        --v50;
      }
      while ( v50 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001b600  mov     rax, rsp
0x18001b603  mov     [rax+10h], rdx
0x18001b607  mov     [rax+8], rcx
0x18001b60b  push    rbp
0x18001b60c  push    rsi
0x18001b60d  lea     rbp, [rax-47h]
0x18001b611  sub     rsp, 0B8h
0x18001b618  mov     ecx, [rbp+3Fh+arg_20]
0x18001b61b  xor     esi, esi
0x18001b61d  mov     [rax+18h], rbx
0x18001b621  xorps   xmm0, xmm0
0x18001b624  mov     [rax-18h], rdi
0x18001b628  xor     bl, bl
0x18001b62a  mov     [rax-20h], r12
0x18001b62e  xorps   xmm1, xmm1
0x18001b631  mov     [rax-28h], r13
0x18001b635  mov     r12, r8
0x18001b638  mov     [rax-30h], r14
0x18001b63c  mov     rdi, rdx
0x18001b63f  mov     [rax-38h], r15
0x18001b643  mov     r13d, esi
0x18001b646  mov     rax, [rbp+3Fh+arg_28]
0x18001b64a  mov     r14d, esi
0x18001b64d  mov     [rbp+3Fh+Status], esi
0x18001b650  mov     [rbp+3Fh+var_70], rsi
0x18001b654  movups  [rbp+3Fh+var_48], xmm0
0x18001b658  mov     [rax], rsi
0x18001b65b  mov     rax, [rbp+3Fh+arg_30]
0x18001b65f  movups  [rbp+3Fh+var_68], xmm1
0x18001b663  movups  xmmword ptr [rbp+3Fh+Size], xmm0
0x18001b667  mov     [rax], esi
0x18001b669  cmp     ecx, 1Ch
0x18001b66c  jb      loc_18001BC5D
0x18001b672  test    r8, r8
0x18001b675  jz      loc_18001BC5D
0x18001b67b  mov     eax, [r8+14h]
0x18001b67f  test    eax, eax
0x18001b681  jz      loc_18001B717
0x18001b687  add     eax, 1Bh
0x18001b68a  cmp     eax, 1Bh
0x18001b68d  jb      short loc_18001B6CD
0x18001b68f  cmp     ecx, eax
0x18001b691  jnb     loc_18001B717
0x18001b697  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18001b69e  mov     esi, 0C000000Dh
0x18001b6a3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b6a8  mov     r9, rax
0x18001b6ab  lea     r15, Class
0x18001b6b2  mov     [rsp+30h], r15
0x18001b6b7  lea     rax, aInvalidLength; "Invalid length"
0x18001b6be  mov     [rsp+0C0h+var_98], rax
0x18001b6c3  mov     dword ptr [rsp+0C0h+var_A0], 622h
0x18001b6cb  jmp     short loc_18001B701
0x18001b6cd  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18001b6d4  mov     esi, 0C0000095h
0x18001b6d9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b6de  mov     r9, rax
0x18001b6e1  lea     r15, Class
0x18001b6e8  mov     [rsp+30h], r15
0x18001b6ed  lea     rax, aRtlulongadd; "RtlULongAdd"
0x18001b6f4  mov     [rsp+0C0h+var_98], rax
0x18001b6f9  mov     dword ptr [rsp+0C0h+var_A0], 61Dh
0x18001b701  mov     r8d, esi
0x18001b704  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001b70b  xor     ecx, ecx
0x18001b70d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001b712  jmp     loc_18001BCBF
0x18001b717  mov     dl, 1; Wait
0x18001b719  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18001b720  call    cs:__imp_RtlAcquireResourceShared
0x18001b726  mov     r9, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x18001b72d  test    r9, r9
0x18001b730  jz      short loc_18001B771
0x18001b732  mov     r8d, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18001b739  mov     edx, esi
0x18001b73b  test    r8d, r8d
0x18001b73e  jz      short loc_18001B771
0x18001b740  mov     eax, edx
0x18001b742  imul    rcx, rax, 188h
0x18001b749  mov     rax, [r12+4]
0x18001b74e  add     rcx, r9
0x18001b751  mov     [rbp+3Fh+var_78], rcx
0x18001b755  cmp     rax, [rcx+44h]
0x18001b759  lea     r14, [rcx+44h]
0x18001b75d  jnz     short loc_18001B76A
0x18001b75f  mov     rax, [r12+0Ch]
0x18001b764  cmp     rax, [r14+8]
0x18001b768  jz      short loc_18001B7BA
0x18001b76a  inc     edx
0x18001b76c  cmp     edx, r8d
0x18001b76f  jb      short loc_18001B740
0x18001b771  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18001b778  mov     r14, rsi
0x18001b77b  call    cs:__imp_RtlReleaseResource
0x18001b781  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18001b788  mov     esi, 80090311h
0x18001b78d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b792  mov     r9, rax
0x18001b795  lea     r15, Class
0x18001b79c  mov     [rsp+30h], r15
0x18001b7a1  lea     rax, aRefpackage; "RefPackage"
0x18001b7a8  mov     [rsp+0C0h+var_98], rax
0x18001b7ad  mov     dword ptr [rsp+0C0h+var_A0], 629h
0x18001b7b5  jmp     loc_18001B701
0x18001b7ba  cmp     [rcx+148h], rsi
0x18001b7c1  jnz     short loc_18001B811
0x18001b7c3  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18001b7ca  mov     esi, 0C00000BBh
0x18001b7cf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b7d4  mov     r9, rax
0x18001b7d7  lea     r15, Class
0x18001b7de  mov     [rsp+30h], r15
0x18001b7e3  lea     rax, aPluginDoesnTIm; "Plugin doesn't implement CallPkg"
0x18001b7ea  mov     [rsp+0C0h+var_98], rax
0x18001b7ef  mov     dword ptr [rsp+0C0h+var_A0], 62Eh
0x18001b7f7  mov     r8d, esi
0x18001b7fa  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001b801  xor     ecx, ecx
0x18001b803  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001b808  mov     r14, [rbp+3Fh+var_78]
0x18001b80c  jmp     loc_18001BCBF
0x18001b811  lea     r8, [rbp+3Fh+var_70]; struct _LOGON_SESSION **
0x18001b815  mov     rdx, rdi; struct _LUID *
0x18001b818  mov     ecx, 1; int
0x18001b81d  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18001b822  lea     rdi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18001b829  mov     esi, eax
0x18001b82b  lea     r15, Class
0x18001b832  lea     rbx, aOnecoreDsExtCl_16+26h; ""
0x18001b839  test    eax, eax
0x18001b83b  jns     loc_18001B8F8
0x18001b841  mov     r9, rbx
0x18001b844  nop     dword ptr [rax+00h]
0x18001b848  nop     dword ptr [rax+rax+00000000h]
0x18001b850  movzx   eax, byte ptr [r9-1]
0x18001b855  mov     rcx, r9
0x18001b858  dec     r9
0x18001b85b  cmp     al, 5Ch ; '\'
0x18001b85d  jz      short loc_18001B866
0x18001b85f  cmp     r9, rdi
0x18001b862  ja      short loc_18001B850
0x18001b864  cmp     al, 5Ch ; '\'
0x18001b866  cmovz   r9, rcx
0x18001b86a  mov     [rsp+30h], r15
0x18001b86f  lea     r14, aAcquirelogonse_0; "AcquireLogonSession"
0x18001b876  mov     r8d, esi
0x18001b879  mov     [rsp+0C0h+var_98], r14
0x18001b87e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001b885  xor     ecx, ecx
0x18001b887  mov     dword ptr [rsp+0C0h+var_A0], 635h
0x18001b88f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001b894  cmp     esi, 0C0000017h
0x18001b89a  jz      short loc_18001B8B0
0x18001b89c  cmp     esi, 0C000009Ah
0x18001b8a2  jnz     loc_18001BADC
0x18001b8a8  nop     dword ptr [rax+rax+00000000h]
0x18001b8b0  movzx   eax, byte ptr [rbx-1]
0x18001b8b4  mov     rcx, rbx
0x18001b8b7  dec     rbx
0x18001b8ba  cmp     al, 5Ch ; '\'
0x18001b8bc  jz      short loc_18001B8C5
0x18001b8be  cmp     rbx, rdi
0x18001b8c1  ja      short loc_18001B8B0
0x18001b8c3  cmp     al, 5Ch ; '\'
0x18001b8c5  cmovz   rbx, rcx
0x18001b8c9  mov     [rsp+30h], r15
0x18001b8ce  mov     r9, rbx
0x18001b8d1  mov     [rsp+0C0h+var_98], r14
0x18001b8d6  mov     r8d, esi
0x18001b8d9  mov     dword ptr [rsp+0C0h+var_A0], 639h
0x18001b8e1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001b8e8  xor     ecx, ecx
0x18001b8ea  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001b8ef  mov     r14, [rbp+3Fh+var_78]
0x18001b8f3  jmp     loc_18001BCBD
0x18001b8f8  mov     rsi, [rbp+3Fh+var_70]
0x18001b8fc  lea     r8, [rbp+3Fh+Status]; Status
0x18001b900  mov     rdx, r14; Uuid2
0x18001b903  lea     rcx, [rsi+24h]; Uuid1
0x18001b907  call    cs:__imp_UuidEqual
0x18001b90d  test    eax, eax
0x18001b90f  jz      loc_18001BADC
0x18001b915  mov     r13, [rsi+38h]
0x18001b919  mov     dl, 1; Wait
0x18001b91b  mov     rcx, [r13+18h]
0x18001b91f  add     rcx, 18h; Resource
0x18001b923  call    cs:__imp_RtlAcquireResourceShared
0x18001b929  lea     rcx, [r13+20h]; CriticalSection
0x18001b92d  call    cs:__imp_RtlEnterCriticalSection
0x18001b933  cmp     dword ptr [r13+4Ch], 0
0x18001b938  jnz     short loc_18001B9B8
0x18001b93a  mov     rcx, [r13+120h]
0x18001b941  test    rcx, rcx
0x18001b944  jz      short loc_18001B960
0x18001b946  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001b94d  mov     edx, [r13+118h]
0x18001b954  mov     rax, [rax+168h]
0x18001b95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b960  mov     rax, [r13+108h]
0x18001b967  test    rax, rax
0x18001b96a  jz      short loc_18001B98C
0x18001b96c  mov     edx, [rax+0Ch]
0x18001b96f  test    edx, edx
0x18001b971  jz      short loc_18001B98C
0x18001b973  mov     ecx, [rax+8]
0x18001b976  add     rcx, rax
0x18001b979  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001b980  mov     rax, [rax+168h]
0x18001b987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b98c  mov     rax, [r13+110h]
0x18001b993  test    rax, rax
0x18001b996  jz      short loc_18001B9B8
0x18001b998  mov     edx, [rax+0Ch]
0x18001b99b  test    edx, edx
0x18001b99d  jz      short loc_18001B9B8
0x18001b99f  mov     ecx, [rax+8]
0x18001b9a2  add     rcx, rax
0x18001b9a5  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001b9ac  mov     rax, [rax+168h]
0x18001b9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b8  inc     dword ptr [r13+4Ch]
0x18001b9bc  lea     rcx, [r13+20h]; CriticalSection
0x18001b9c0  call    cs:__imp_RtlLeaveCriticalSection
0x18001b9c6  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001b9cd  mov     ecx, [r13+118h]
0x18001b9d4  mov     dword ptr [rbp+3Fh+Size], ecx
0x18001b9d7  mov     rax, [rax+28h]
0x18001b9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9e0  mov     [rbp+3Fh+Size+8], rax
0x18001b9e4  test    rax, rax
0x18001b9e7  jnz     short loc_18001BA19
0x18001b9e9  mov     rcx, rdi; char *
0x18001b9ec  mov     bl, 1
0x18001b9ee  mov     esi, 0C0000017h
0x18001b9f3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b9f8  mov     [rsp+30h], r15
0x18001b9fd  mov     r9, rax
0x18001ba00  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18001ba07  mov     [rsp+0C0h+var_98], rax
0x18001ba0c  mov     dword ptr [rsp+0C0h+var_A0], 659h
0x18001ba14  jmp     loc_18001B7F7
0x18001ba19  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x18001ba1d  mov     rcx, rax; void *
0x18001ba20  mov     rdx, [r13+120h]; Src
0x18001ba27  call    memcpy_0
0x18001ba2c  test    r13, r13
0x18001ba2f  jz      loc_18001BADC
0x18001ba35  lea     rcx, [r13+20h]; CriticalSection
0x18001ba39  call    cs:__imp_RtlEnterCriticalSection
0x18001ba3f  add     dword ptr [r13+4Ch], 0FFFFFFFFh
0x18001ba44  jnz     short loc_18001BAC4
0x18001ba46  mov     rcx, [r13+120h]
0x18001ba4d  test    rcx, rcx
0x18001ba50  jz      short loc_18001BA6C
0x18001ba52  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001ba59  mov     edx, [r13+118h]
0x18001ba60  mov     rax, [rax+160h]
0x18001ba67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba6c  mov     rax, [r13+108h]
0x18001ba73  test    rax, rax
0x18001ba76  jz      short loc_18001BA98
0x18001ba78  mov     edx, [rax+0Ch]
0x18001ba7b  test    edx, edx
0x18001ba7d  jz      short loc_18001BA98
0x18001ba7f  mov     ecx, [rax+8]
0x18001ba82  add     rcx, rax
0x18001ba85  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001ba8c  mov     rax, [rax+160h]
0x18001ba93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba98  mov     rax, [r13+110h]
0x18001ba9f  test    rax, rax
0x18001baa2  jz      short loc_18001BAC4
0x18001baa4  mov     edx, [rax+0Ch]
0x18001baa7  test    edx, edx
0x18001baa9  jz      short loc_18001BAC4
0x18001baab  mov     ecx, [rax+8]
0x18001baae  add     rcx, rax
0x18001bab1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001bab8  mov     rax, [rax+160h]
0x18001babf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bac4  lea     rcx, [r13+20h]; CriticalSection
0x18001bac8  call    cs:__imp_RtlLeaveCriticalSection
0x18001bace  mov     rcx, [r13+18h]
0x18001bad2  add     rcx, 18h; Resource
0x18001bad6  call    cs:__imp_RtlReleaseResource
0x18001badc  mov     eax, [r12+14h]
0x18001bae1  lea     r8, [rbp+3Fh+Size]
0x18001bae5  mov     r14, [rbp+3Fh+var_78]
0x18001bae9  lea     r9, [rbp+3Fh+var_48]
0x18001baed  mov     rdx, [rbp+3Fh+arg_8]
0x18001baf1  xor     ecx, ecx
0x18001baf3  cmp     [rbp+3Fh+Size+8], rcx
0x18001baf7  mov     dword ptr [rbp+3Fh+var_48], eax
0x18001bafa  lea     rax, [r12+18h]
0x18001baff  mov     qword ptr [rbp+3Fh+var_48+8], rax
0x18001bb03  cmovz   r8, rcx
0x18001bb07  mov     rdx, [rdx+18h]
0x18001bb0b  lea     rax, [rbp+3Fh+var_68]
0x18001bb0f  mov     rcx, [r14+8]
0x18001bb13  mov     [rsp+0C0h+var_A0], rax
  ... truncated ...
```
