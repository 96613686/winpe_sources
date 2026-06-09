# CloudAPGetUnlockKeyType(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180007920`
- end: `0x180007edc`
- name: `?CloudAPGetUnlockKeyType@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `1468`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007920`
- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000f100`
- `0x180041770`
- `0x18007f9f0`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180007b47`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007b47`
- `ntdll!RtlReleaseResource` at `0x180007b1c`
- `ntdll!RtlReleaseResource` at `0x180007b6e`
- `ntdll!RtlReleaseResource` at `0x180007b96`
- `ntdll!RtlReleaseResource` at `0x180007da2`
- `ntdll!RtlReleaseResource` at `0x180007b1c`
- `ntdll!RtlReleaseResource` at `0x180007b6e`
- `ntdll!RtlReleaseResource` at `0x180007b96`
- `ntdll!RtlReleaseResource` at `0x180007da2`
- `ntdll!RtlAcquireResourceShared` at `0x1800079aa`
- `ntdll!RtlAcquireResourceShared` at `0x180007a08`
- `ntdll!RtlAcquireResourceShared` at `0x1800079aa`
- `ntdll!RtlAcquireResourceShared` at `0x180007a08`
- `ntdll!RtlEnterCriticalSection` at `0x180007a12`
- `ntdll!RtlEnterCriticalSection` at `0x180007a12`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a86`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a86`

## string_xrefs

- `0x180007b9c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180007c28`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180007c86`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180007d19`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180007dce`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180007e58`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180007e73`: `CopyToClientBuffer`

## pseudocode

```c
__int64 __fastcall CloudAPGetUnlockKeyType(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned int *a7)
{
  _QWORD *v7; // r12
  struct _LOGON_SESSION *v8; // rsi
  bool v9; // cf
  void **v10; // rbp
  unsigned int *v11; // r15
  unsigned int v12; // ebx
  struct _ApPluginPkg *v13; // rbp
  unsigned int v14; // edi
  char *v15; // r13
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // eax
  _QWORD *v21; // rax
  const char *v23; // rax
  const char *v24; // r9
  char v25; // al
  const char *v26; // rdx
  bool v27; // zf
  const char *v28; // r9
  char v29; // al
  const char *v30; // rdx
  bool v31; // zf
  const char *v32; // r9
  char v33; // al
  const char *v34; // rdx
  bool v35; // zf
  __int64 v36; // rax
  struct _LOGON_SESSION **v37; // rdx
  struct _USER_CACHE_ENTRY *v38; // rax
  const char *v39; // rax
  const char *v40; // r9
  struct _LOGON_SESSION *v41; // [rsp+40h] [rbp-48h] BYREF
  int v43; // [rsp+A0h] [rbp+18h] BYREF

  v7 = a6;
  v8 = 0;
  v9 = a5 < 8;
  v10 = a1;
  v11 = a7;
  *a6 = 0;
  v43 = 0;
  v41 = 0;
  *v11 = 0;
  if ( v9 || !a3 )
  {
    v12 = -1073741811;
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
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v24, 3946, "Invalid Arg(s)", &Class);
  }
  else
  {
    if ( a2->HasTcbPrivilege )
      a2 = (struct _SECPKG_CLIENT_INFO *)(a3 + 4);
    v12 = _AcquireLogonSession(1, &a2->LogonId, &v41);
    if ( v12 )
    {
      v39 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v39, 3959, "AcquireLogonSession", &Class);
      v8 = v41;
    }
    else
    {
      RtlAcquireResourceShared(&g_PackageListLock, 1u);
      v13 = g_pPlugins;
      v8 = v41;
      if ( g_pPlugins )
      {
        v14 = g_cPlugins;
        while ( v12 < v14 )
        {
          v15 = (char *)v13 + 392 * v12;
          if ( !memcmp_0((char *)v8 + 36, v15 + 68, 0x10u) )
          {
            v16 = *((_QWORD *)v8 + 7);
            RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v16 + 24) + 24LL), 1u);
            RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v16 + 32));
            if ( !*(_DWORD *)(v16 + 76) )
            {
              v17 = *(_QWORD *)(v16 + 288);
              if ( v17 )
                ((void (__fastcall *)(__int64, _QWORD))g_pLsaFunctionTable->LsaUnprotectMemory)(
                  v17,
                  *(unsigned int *)(v16 + 280));
              v18 = *(_QWORD *)(v16 + 264);
              if ( v18 && *(_DWORD *)(v18 + 12) )
                ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v18 + *(unsigned int *)(v18 + 8));
              v19 = *(_QWORD *)(v16 + 272);
              if ( v19 && *(_DWORD *)(v19 + 12) )
                ((void (__fastcall *)(__int64))g_pLsaFunctionTable->LsaUnprotectMemory)(v19 + *(unsigned int *)(v19 + 8));
            }
            ++*(_DWORD *)(v16 + 76);
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v16 + 32));
            v20 = *(_DWORD *)(v16 + 344);
            if ( v20 == 5 )
            {
LABEL_18:
              v43 = 2;
LABEL_19:
              v10 = a1;
              v12 = ((__int64 (__fastcall *)(void **, __int64, _QWORD *))g_pLsaFunctionTable->AllocateClientBuffer)(
                      a1,
                      4,
                      v7);
              if ( v12 )
              {
                v28 = "";
                while ( 1 )
                {
                  v29 = *(v28 - 1);
                  v30 = v28--;
                  v31 = v29 == 92;
                  if ( v29 == 92 )
                    break;
                  if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                  {
                    v31 = v29 == 92;
                    break;
                  }
                }
                if ( v31 )
                  v28 = v30;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v28, 4006, "AllocateClientBuffer", &Class);
              }
              else
              {
                v12 = ((__int64 (__fastcall *)(void **, __int64, _QWORD, int *))g_pLsaFunctionTable->CopyToClientBuffer)(
                        a1,
                        4,
                        *v7,
                        &v43);
                if ( v12 )
                {
                  v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v40, 4013, "CopyToClientBuffer", &Class);
                }
                else
                {
                  *v11 = 4;
                }
              }
            }
            else
            {
              switch ( v20 )
              {
                case 1:
                  v43 = 1;
                  goto LABEL_19;
                case 2:
                  goto LABEL_18;
                case 3:
                  v43 = 3;
                  goto LABEL_19;
                case 4:
                  v43 = 4;
                  goto LABEL_19;
                case 6:
                  v43 = 5;
                  goto LABEL_19;
                case 7:
                  v43 = 6;
                  goto LABEL_19;
                default:
                  v32 = "";
                  v12 = -1073741557;
                  break;
              }
              while ( 1 )
              {
                v33 = *(v32 - 1);
                v34 = v32--;
                v35 = v33 == 92;
                if ( v33 == 92 )
                  break;
                if ( v32 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                {
                  v35 = v33 == 92;
                  break;
                }
              }
              if ( v35 )
                v32 = v34;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%u",
                -1073741557,
                v32,
                3999,
                "Invalid Logon Type",
                *(_DWORD *)(v16 + 296));
              v10 = a1;
            }
            UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v16);
            if ( v15 )
              RtlReleaseResource(&g_PackageListLock);
            goto LABEL_24;
          }
          ++v12;
        }
      }
      RtlReleaseResource(&g_PackageListLock);
      v12 = -2146893039;
      v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v23, 3964, "RefPackage", &Class);
      v10 = a1;
    }
  }
LABEL_24:
  if ( v8 )
  {
    RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
    v21 = *(_QWORD **)((char *)v8 + 28);
    _InterlockedDecrement((volatile signed __int32 *)v8 + 4);
    v27 = *((_DWORD *)v8 + 4) == 0;
    a6 = v21;
    if ( v27 )
    {
      v36 = *(_QWORD *)v8;
      if ( *(struct _LOGON_SESSION **)(*(_QWORD *)v8 + 8LL) != v8
        || (v37 = (struct _LOGON_SESSION **)*((_QWORD *)v8 + 1), *v37 != v8) )
      {
        __fastfail(3u);
      }
      *v37 = (struct _LOGON_SESSION *)v36;
      *(_QWORD *)(v36 + 8) = v37;
      RtlReleaseResource(&g_LogonSessionListLock);
      v38 = _FreeLogonSession(v8);
      if ( v38 )
        _ReleaseUserCacheEntry((struct _LUID *)&a6, v38);
    }
    else
    {
      RtlReleaseResource(&g_LogonSessionListLock);
    }
  }
  if ( (v12 & 0x80000000) != 0 && *v7 )
  {
    ((void (__fastcall *)(void **))g_pLsaFunctionTable->FreeClientBuffer)(v10);
    *v7 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x180007920  mov     rax, rsp
0x180007923  mov     [rax+8], rcx
0x180007927  push    rbx
0x180007928  push    rbp
0x180007929  push    rsi
0x18000792a  push    r12
0x18000792c  sub     rsp, 68h
0x180007930  mov     r12, qword ptr [rsp+88h+arg_28.LowPart]
0x180007938  xor     esi, esi
0x18000793a  cmp     [rsp+88h+arg_20], 8
0x180007942  mov     rbp, rcx
0x180007945  mov     [rax+10h], rdi
0x180007949  mov     [rax-28h], r13
0x18000794d  mov     [rax-30h], r14
0x180007951  mov     [rax-38h], r15
0x180007955  mov     r15, [rsp+88h+arg_30]
0x18000795d  mov     [r12], rsi
0x180007961  mov     dword ptr [rax+18h], 0
0x180007968  mov     [rax-48h], rsi
0x18000796c  mov     [r15], esi
0x18000796f  jb      loc_180007C1C
0x180007975  test    r8, r8
0x180007978  jz      loc_180007C1C
0x18000797e  cmp     [rdx+10h], sil
0x180007982  jnz     loc_180007D71
0x180007988  lea     r8, [rsp+88h+var_48]; struct _LOGON_SESSION **
0x18000798d  mov     ecx, 1; int
0x180007992  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x180007997  mov     ebx, eax
0x180007999  test    eax, eax
0x18000799b  jnz     loc_180007DCE
0x1800079a1  mov     dl, 1; Wait
0x1800079a3  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x1800079aa  call    cs:__imp_RtlAcquireResourceShared
0x1800079b0  mov     rbp, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x1800079b7  mov     rsi, [rsp+88h+var_48]
0x1800079bc  test    rbp, rbp
0x1800079bf  jz      loc_180007B8F
0x1800079c5  mov     edi, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x1800079cb  cmp     ebx, edi
0x1800079cd  jnb     loc_180007B8F
0x1800079d3  mov     eax, ebx
0x1800079d5  lea     rcx, [rsi+24h]; Buf1
0x1800079d9  imul    r13, rax, 188h
0x1800079e0  mov     r8d, 10h; Size
0x1800079e6  add     r13, rbp
0x1800079e9  lea     rdx, [r13+44h]; Buf2
0x1800079ed  call    memcmp_0
0x1800079f2  test    eax, eax
0x1800079f4  jnz     loc_180007B88
0x1800079fa  mov     rdi, [rsi+38h]
0x1800079fe  mov     dl, 1; Wait
0x180007a00  mov     rcx, [rdi+18h]
0x180007a04  add     rcx, 18h; Resource
0x180007a08  call    cs:__imp_RtlAcquireResourceShared
0x180007a0e  lea     rcx, [rdi+20h]; CriticalSection
0x180007a12  call    cs:__imp_RtlEnterCriticalSection
0x180007a18  cmp     dword ptr [rdi+4Ch], 0
0x180007a1c  jnz     short loc_180007A7F
0x180007a1e  mov     rcx, [rdi+120h]
0x180007a25  test    rcx, rcx
0x180007a28  jz      short loc_180007A43
0x180007a2a  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180007a31  mov     edx, [rdi+118h]
0x180007a37  mov     rax, [rax+168h]
0x180007a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a43  mov     rax, [rdi+108h]
0x180007a4a  test    rax, rax
0x180007a4d  jz      short loc_180007A6F
0x180007a4f  mov     edx, [rax+0Ch]
0x180007a52  test    edx, edx
0x180007a54  jz      short loc_180007A6F
0x180007a56  mov     ecx, [rax+8]
0x180007a59  add     rcx, rax
0x180007a5c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180007a63  mov     rax, [rax+168h]
0x180007a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a6f  mov     rax, [rdi+110h]
0x180007a76  test    rax, rax
0x180007a79  jnz     loc_180007CDD
0x180007a7f  inc     dword ptr [rdi+4Ch]
0x180007a82  lea     rcx, [rdi+20h]; CriticalSection
0x180007a86  call    cs:__imp_RtlLeaveCriticalSection
0x180007a8c  mov     eax, [rdi+158h]
0x180007a92  cmp     eax, 5
0x180007a95  jnz     loc_180007BEE
0x180007a9b  mov     [rsp+88h+arg_10], 2; jumptable 0000000180007C0A case 2
0x180007aa6  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180007aad  mov     r8, r12
0x180007ab0  mov     rbp, [rsp+88h+arg_0]
0x180007ab8  mov     edx, 4
0x180007abd  mov     rcx, rbp
0x180007ac0  mov     rax, [rax+38h]
0x180007ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac9  mov     ebx, eax
0x180007acb  test    eax, eax
0x180007acd  jnz     loc_180007C7F
0x180007ad3  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180007ada  lea     r9, [rsp+88h+arg_10]
0x180007ae2  mov     r8, [r12]
0x180007ae6  mov     edx, 4
0x180007aeb  mov     rcx, rbp
0x180007aee  mov     rax, [rax+48h]
0x180007af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af7  mov     ebx, eax
0x180007af9  test    eax, eax
0x180007afb  jnz     loc_180007E58
0x180007b01  mov     dword ptr [r15], 4
0x180007b08  mov     rcx, rdi; struct _USER_CACHE_ENTRY *
0x180007b0b  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180007b10  test    r13, r13
0x180007b13  jz      short loc_180007B22
0x180007b15  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x180007b1c  call    cs:__imp_RtlReleaseResource
0x180007b22  mov     r15, [rsp+88h+var_38]
0x180007b27  mov     r14, [rsp+88h+var_30]
0x180007b2c  mov     r13, [rsp+88h+var_28]
0x180007b31  mov     rdi, [rsp+88h+arg_8]
0x180007b39  test    rsi, rsi
0x180007b3c  jz      short loc_180007B74
0x180007b3e  mov     dl, 1; Wait
0x180007b40  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180007b47  call    cs:__imp_RtlAcquireResourceExclusive
0x180007b4d  mov     rax, [rsi+1Ch]
0x180007b51  lock dec dword ptr [rsi+10h]
0x180007b55  cmp     dword ptr [rsi+10h], 0
0x180007b59  mov     qword ptr [rsp+88h+arg_28.LowPart], rax
0x180007b61  jz      loc_180007D7A
0x180007b67  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180007b6e  call    cs:__imp_RtlReleaseResource
0x180007b74  test    ebx, ebx
0x180007b76  js      loc_180007E93
0x180007b7c  mov     eax, ebx
0x180007b7e  add     rsp, 68h
0x180007b82  pop     r12
0x180007b84  pop     rsi
0x180007b85  pop     rbp
0x180007b86  pop     rbx
0x180007b87  retn
0x180007b88  inc     ebx
0x180007b8a  jmp     loc_1800079CB
0x180007b8f  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x180007b96  call    cs:__imp_RtlReleaseResource
0x180007b9c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180007ba3  mov     ebx, 80090311h
0x180007ba8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007bad  mov     r9, rax
0x180007bb0  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180007bb7  lea     rax, Class
0x180007bbe  mov     r8d, ebx
0x180007bc1  mov     [rsp+88h+var_58], rax
0x180007bc6  xor     ecx, ecx
0x180007bc8  lea     rax, aRefpackage; "RefPackage"
0x180007bcf  mov     [rsp+88h+var_60], rax
0x180007bd4  mov     [rsp+88h+var_68], 0F7Ch
0x180007bdc  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180007be1  mov     rbp, [rsp+88h+arg_0]
0x180007be9  jmp     loc_180007B22
0x180007bee  dec     eax; switch 7 cases
0x180007bf0  cmp     eax, 6
0x180007bf3  ja      def_180007C0A; jumptable 0000000180007C0A default case, case 5
0x180007bf9  lea     rcx, __ImageBase
0x180007c00  mov     eax, ds:(jpt_180007C0A - 180000000h)[rcx+rax*4]
0x180007c07  add     rax, rcx
0x180007c0a  jmp     rax; switch jump
0x180007c0c  mov     [rsp+88h+arg_10], 1; jumptable 0000000180007C0A case 1
0x180007c17  jmp     loc_180007AA6
0x180007c1c  mov     ebx, 0C000000Dh
0x180007c21  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x180007c28  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180007c2f  movzx   eax, byte ptr [r9-1]
0x180007c34  mov     rdx, r9
0x180007c37  dec     r9
0x180007c3a  cmp     al, 5Ch ; '\'
0x180007c3c  jz      short loc_180007C45
0x180007c3e  cmp     r9, rcx
0x180007c41  ja      short loc_180007C2F
0x180007c43  cmp     al, 5Ch ; '\'
0x180007c45  cmovz   r9, rdx
0x180007c49  lea     rax, Class
0x180007c50  mov     [rsp+88h+var_58], rax
0x180007c55  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180007c5c  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x180007c63  mov     r8d, ebx
0x180007c66  mov     [rsp+88h+var_60], rax
0x180007c6b  xor     ecx, ecx
0x180007c6d  mov     [rsp+88h+var_68], 0F6Ah
0x180007c75  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180007c7a  jmp     loc_180007B22
0x180007c7f  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x180007c86  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180007c8d  movzx   eax, byte ptr [r9-1]
0x180007c92  mov     rdx, r9
0x180007c95  dec     r9
0x180007c98  cmp     al, 5Ch ; '\'
0x180007c9a  jz      short loc_180007CA3
0x180007c9c  cmp     r9, rcx
0x180007c9f  ja      short loc_180007C8D
0x180007ca1  cmp     al, 5Ch ; '\'
0x180007ca3  lea     rax, Class
0x180007caa  cmovz   r9, rdx
0x180007cae  mov     [rsp+88h+var_58], rax
0x180007cb3  lea     rax, aAllocateclient; "AllocateClientBuffer"
0x180007cba  mov     [rsp+88h+var_60], rax
0x180007cbf  mov     [rsp+88h+var_68], 0FA6h
0x180007cc7  mov     r8d, ebx
0x180007cca  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180007cd1  xor     ecx, ecx
0x180007cd3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180007cd8  jmp     loc_180007B08
0x180007cdd  mov     edx, [rax+0Ch]
0x180007ce0  test    edx, edx
0x180007ce2  jz      loc_180007A7F
0x180007ce8  mov     ecx, [rax+8]
0x180007ceb  add     rcx, rax
0x180007cee  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180007cf5  mov     rax, [rax+168h]
0x180007cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d01  jmp     loc_180007A7F
0x180007d06  mov     r8d, [rdi+128h]; jumptable 0000000180007C0A default case, case 5
0x180007d0d  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x180007d14  mov     ebx, 0C000010Bh
0x180007d19  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180007d20  movzx   eax, byte ptr [r9-1]
0x180007d25  mov     rdx, r9
0x180007d28  dec     r9
0x180007d2b  cmp     al, 5Ch ; '\'
0x180007d2d  jz      short loc_180007D36
0x180007d2f  cmp     r9, rcx
0x180007d32  ja      short loc_180007D20
0x180007d34  cmp     al, 5Ch ; '\'
0x180007d36  mov     dword ptr [rsp+88h+var_58], r8d
0x180007d3b  lea     rax, aInvalidLogonTy; "Invalid Logon Type"
0x180007d42  cmovz   r9, rdx
0x180007d46  mov     [rsp+88h+var_60], rax
0x180007d4b  mov     r8d, ebx
0x180007d4e  mov     [rsp+88h+var_68], 0F9Fh
0x180007d56  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x180007d5d  xor     ecx, ecx
0x180007d5f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180007d64  mov     rbp, [rsp+88h+arg_0]
0x180007d6c  jmp     loc_180007B08
0x180007d71  lea     rdx, [r8+4]
0x180007d75  jmp     loc_180007988
0x180007d7a  mov     rax, [rsi]
0x180007d7d  cmp     [rax+8], rsi
0x180007d81  jnz     loc_180007E8C
0x180007d87  mov     rdx, [rsi+8]
0x180007d8b  cmp     [rdx], rsi
0x180007d8e  jnz     loc_180007E8C
0x180007d94  mov     [rdx], rax
0x180007d97  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180007d9e  mov     [rax+8], rdx
0x180007da2  call    cs:__imp_RtlReleaseResource
0x180007da8  mov     rcx, rsi; struct _LOGON_SESSION *
0x180007dab  call    ?_FreeLogonSession@@YAPEAU_USER_CACHE_ENTRY@@PEAU_LOGON_SESSION@@@Z; _FreeLogonSession(_LOGON_SESSION *)
0x180007db0  test    rax, rax
0x180007db3  jz      loc_180007B74
0x180007db9  mov     rdx, rax; struct _USER_CACHE_ENTRY *
0x180007dbc  lea     rcx, [rsp+88h+arg_28]; struct _LUID *
0x180007dc4  call    ?_ReleaseUserCacheEntry@@YAXPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@@Z; _ReleaseUserCacheEntry(_LUID *,_USER_CACHE_ENTRY *)
0x180007dc9  jmp     loc_180007B74
0x180007dce  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180007dd5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007dda  mov     r9, rax
0x180007ddd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180007de4  lea     rax, Class
0x180007deb  mov     r8d, ebx
0x180007dee  mov     [rsp+88h+var_58], rax
0x180007df3  xor     ecx, ecx
0x180007df5  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x180007dfc  mov     [rsp+88h+var_60], rax
0x180007e01  mov     [rsp+88h+var_68], 0F77h
0x180007e09  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180007e0e  mov     rsi, [rsp+88h+var_48]
0x180007e13  jmp     loc_180007B22
0x180007e18  mov     [rsp+88h+arg_10], 3; jumptable 0000000180007C0A case 3
0x180007e23  jmp     loc_180007AA6
0x180007e28  mov     [rsp+88h+arg_10], 4; jumptable 0000000180007C0A case 4
0x180007e33  jmp     loc_180007AA6
0x180007e38  mov     [rsp+88h+arg_10], 5; jumptable 0000000180007C0A case 6
0x180007e43  jmp     loc_180007AA6
0x180007e48  mov     [rsp+88h+arg_10], 6; jumptable 0000000180007C0A case 7
0x180007e53  jmp     loc_180007AA6
0x180007e58  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180007e5f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007e64  mov     r9, rax
0x180007e67  lea     rax, Class
0x180007e6e  mov     [rsp+88h+var_58], rax
0x180007e73  lea     rax, aCopytoclientbu; "CopyToClientBuffer"
0x180007e7a  mov     [rsp+88h+var_60], rax
0x180007e7f  mov     [rsp+88h+var_68], 0FADh
0x180007e87  jmp     loc_180007CC7
0x180007e8c  mov     ecx, 3
0x180007e91  int     29h; Win8: RtlFailFast(ecx)
0x180007e93  mov     rdx, [r12]
0x180007e97  test    rdx, rdx
0x180007e9a  jz      loc_180007B7C
0x180007ea0  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180007ea7  mov     rcx, rbp
  ... truncated ...
```
