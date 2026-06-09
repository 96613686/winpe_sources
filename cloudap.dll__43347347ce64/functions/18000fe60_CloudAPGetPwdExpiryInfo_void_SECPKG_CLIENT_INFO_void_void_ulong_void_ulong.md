# CloudAPGetPwdExpiryInfo(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x18000fe60`
- end: `0x180010315`
- name: `?CloudAPGetPwdExpiryInfo@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `1205`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000fe60`
- `0x180010320`
- `0x1800103c0`
- `0x180081010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180010202`
- `ntdll!RtlReleaseResource` at `0x18001022c`
- `ntdll!RtlReleaseResource` at `0x180010202`
- `ntdll!RtlReleaseResource` at `0x18001022c`
- `ntdll!RtlAcquireResourceShared` at `0x18000ff26`
- `ntdll!RtlAcquireResourceShared` at `0x18000ff91`
- `ntdll!RtlAcquireResourceShared` at `0x18000ff26`
- `ntdll!RtlAcquireResourceShared` at `0x18000ff91`
- `ntdll!RtlEnterCriticalSection` at `0x18000ff9b`
- `ntdll!RtlEnterCriticalSection` at `0x18000ff9b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ffb8`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ffb8`

## string_xrefs

- `0x18000fed8`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001002d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800100a8`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001010e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180010152`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800101a1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18001023e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180010295`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800100c3`: `CopyToClientBuffer`
- `0x180010129`: `CopyToClientBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudAPGetPwdExpiryInfo(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  void **v7; // rsi
  unsigned int *v8; // r13
  bool v9; // cf
  void **v10; // rbp
  unsigned int v11; // eax
  struct _LOGON_SESSION *v12; // r15
  unsigned int v13; // edi
  const char *v14; // rax
  unsigned int i; // edx
  char *v16; // r12
  __int64 v17; // rax
  __int16 *v18; // rbx
  __int64 v19; // r14
  __int64 v20; // rax
  unsigned __int64 v21; // rsi
  unsigned int v22; // ebp
  const char *v23; // r9
  char v24; // al
  const char *v25; // rdx
  bool v26; // zf
  const char *v27; // r9
  const char *v28; // r9
  const char *v29; // r9
  const char *v30; // rax
  const char *v31; // r9
  char v32; // al
  const char *v33; // rdx
  bool v34; // zf
  struct _LOGON_SESSION *v35; // rcx
  const char *v36; // rax
  struct _LOGON_SESSION *v38; // [rsp+40h] [rbp-48h] BYREF
  __int16 v40; // [rsp+A0h] [rbp+18h] BYREF

  v7 = a6;
  v8 = a7;
  v9 = a5 < 0xC;
  v10 = a1;
  v40 = 0;
  *a6 = 0;
  *v8 = 0;
  v38 = 0;
  if ( v9 || !a3 )
  {
    v13 = -1073741811;
    v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v36, 3445, "Invalid Arg(s)", &Class);
    v35 = 0;
    goto LABEL_51;
  }
  if ( a2->HasTcbPrivilege )
    a2 = (struct _SECPKG_CLIENT_INFO *)(a3 + 4);
  v11 = _AcquireLogonSession(1, &a2->LogonId, &v38);
  v12 = v38;
  v13 = v11;
  if ( !v11 )
  {
    RtlAcquireResourceShared(&g_PackageListLock, 1u);
    if ( g_pPlugins )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= g_cPlugins )
          goto LABEL_43;
        v16 = (char *)g_pPlugins + 392 * i;
        v17 = *(_QWORD *)((char *)v12 + 36) - *(_QWORD *)(v16 + 68);
        if ( !v17 )
          v17 = *(_QWORD *)((char *)v12 + 44) - *(_QWORD *)(v16 + 76);
        if ( !v17 )
          break;
      }
      v18 = &v40;
      v19 = *((_QWORD *)v12 + 7);
      RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v19 + 24) + 24LL), 1u);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 32));
      if ( !*(_DWORD *)(v19 + 76) )
        _UnprotectUserCacheEntry((struct _USER_CACHE_ENTRY *)v19);
      ++*(_DWORD *)(v19 + 76);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 32));
      if ( *(_QWORD *)(v19 + 312) )
        v18 = *(__int16 **)(v19 + 312);
      v20 = -1;
      do
        v26 = v18[++v20] == 0;
      while ( !v26 );
      v21 = 2LL * (unsigned int)(v20 + 1);
      if ( v21 > 0xFFFFFFFF )
      {
        v13 = -1073741675;
        v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v30, 3479, "RtlDWordMult", &Class);
        goto LABEL_38;
      }
      v22 = v21 + 8;
      if ( (int)v21 + 8 < (unsigned int)v21 )
      {
        v13 = -1073741675;
        v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v29, 3483, "RtlDWordAdd", &Class);
      }
      else
      {
        v13 = ((__int64 (__fastcall *)(void **, _QWORD, void **))g_pLsaFunctionTable->AllocateClientBuffer)(a1, v22, a6);
        if ( v13 )
        {
          v23 = "";
          while ( 1 )
          {
            v24 = *(v23 - 1);
            v25 = v23--;
            v26 = v24 == 92;
            if ( v24 == 92 )
              break;
            if ( v23 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
            {
              v26 = v24 == 92;
              break;
            }
          }
          if ( v26 )
            v23 = v25;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v23, 3489, "AllocateClientBuffer", &Class);
        }
        else
        {
          v13 = ((__int64 (__fastcall *)(void **, __int64, _QWORD, __int64))g_pLsaFunctionTable->CopyToClientBuffer)(
                  a1,
                  8,
                  *a6,
                  v19 + 320);
          if ( v13 )
          {
            v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v27, 3496, "CopyToClientBuffer", &Class);
          }
          else
          {
            v13 = ((__int64 (__fastcall *)(void **, _QWORD, char *, __int16 *))g_pLsaFunctionTable->CopyToClientBuffer)(
                    a1,
                    (unsigned int)v21,
                    (char *)*a6 + 8,
                    v18);
            if ( !v13 )
            {
              *v8 = v22;
              v13 = 0;
              v10 = a1;
LABEL_38:
              UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v19);
              if ( v16 )
                RtlReleaseResource(&g_PackageListLock);
              v7 = a6;
              goto LABEL_41;
            }
            v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v28, 3504, "CopyToClientBuffer", &Class);
          }
        }
      }
      v10 = a1;
      goto LABEL_38;
    }
LABEL_43:
    RtlReleaseResource(&g_PackageListLock);
    v31 = "";
    v13 = -2146893039;
    while ( 1 )
    {
      v32 = *(v31 - 1);
      v33 = v31--;
      v34 = v32 == 92;
      if ( v32 == 92 )
        break;
      if ( v31 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v34 = v32 == 92;
        break;
      }
    }
    if ( v34 )
      v31 = v33;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v31, 3463, "RefPackage", &Class);
    v35 = v12;
LABEL_51:
    ReleaseLogonSession(v35);
LABEL_52:
    if ( *v7 )
    {
      ((void (__fastcall *)(void **))g_pLsaFunctionTable->FreeClientBuffer)(v10);
      *v7 = 0;
    }
    return v13;
  }
  v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v14, 3458, "AcquireLogonSession", &Class);
LABEL_41:
  ReleaseLogonSession(v12);
  if ( (v13 & 0x80000000) != 0 )
    goto LABEL_52;
  return v13;
}

```

## disassembly

```asm
0x18000fe60  mov     [rsp+arg_0], rcx
0x18000fe65  push    rbx
0x18000fe66  push    rbp
0x18000fe67  push    rsi
0x18000fe68  push    rdi
0x18000fe69  push    r12
0x18000fe6b  push    r13
0x18000fe6d  push    r15
0x18000fe6f  sub     rsp, 50h
0x18000fe73  mov     rsi, [rsp+88h+arg_28]
0x18000fe7b  xor     eax, eax
0x18000fe7d  mov     r13, [rsp+88h+arg_30]
0x18000fe85  xor     ebx, ebx
0x18000fe87  cmp     [rsp+88h+arg_20], 0Ch
0x18000fe8f  mov     rbp, rcx
0x18000fe92  mov     [rsp+88h+arg_10], ax
0x18000fe9a  mov     [rsi], rax
0x18000fe9d  mov     [r13+0], eax
0x18000fea1  mov     [rsp+88h+var_48], rbx
0x18000fea6  jb      loc_180010295
0x18000feac  test    r8, r8
0x18000feaf  jz      loc_180010295
0x18000feb5  cmp     [rdx+10h], al
0x18000feb8  jz      short loc_18000FEBE
0x18000feba  lea     rdx, [r8+4]; struct _LUID *
0x18000febe  lea     r8, [rsp+88h+var_48]; struct _LOGON_SESSION **
0x18000fec3  mov     ecx, 1; int
0x18000fec8  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18000fecd  mov     r15, [rsp+88h+var_48]
0x18000fed2  mov     edi, eax
0x18000fed4  test    eax, eax
0x18000fed6  jz      short loc_18000FF1D
0x18000fed8  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000fedf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000fee4  mov     r9, rax
0x18000fee7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000feee  lea     rax, Class
0x18000fef5  mov     r8d, edi
0x18000fef8  mov     [rsp+88h+var_58], rax
0x18000fefd  xor     ecx, ecx
0x18000feff  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x18000ff06  mov     [rsp+88h+var_60], rax
0x18000ff0b  mov     [rsp+88h+var_68], 0D82h
0x18000ff13  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ff18  jmp     loc_180010210
0x18000ff1d  mov     dl, 1; Wait
0x18000ff1f  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000ff26  call    cs:__imp_RtlAcquireResourceShared
0x18000ff2c  mov     r8, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x18000ff33  test    r8, r8
0x18000ff36  jz      loc_180010225
0x18000ff3c  xor     edx, edx
0x18000ff3e  cmp     edx, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18000ff44  jnb     loc_180010225
0x18000ff4a  mov     eax, edx
0x18000ff4c  imul    r12, rax, 188h
0x18000ff53  mov     rax, [r15+24h]
0x18000ff57  add     r12, r8
0x18000ff5a  sub     rax, [r12+44h]
0x18000ff5f  jnz     short loc_18000FF6A
0x18000ff61  mov     rax, [r15+2Ch]
0x18000ff65  sub     rax, [r12+4Ch]
0x18000ff6a  test    rax, rax
0x18000ff6d  jz      short loc_18000FF73
0x18000ff6f  inc     edx
0x18000ff71  jmp     short loc_18000FF3E
0x18000ff73  mov     [rsp+88h+arg_8], r14
0x18000ff7b  lea     rbx, [rsp+88h+arg_10]
0x18000ff83  mov     r14, [r15+38h]
0x18000ff87  mov     dl, 1; Wait
0x18000ff89  mov     rcx, [r14+18h]
0x18000ff8d  add     rcx, 18h; Resource
0x18000ff91  call    cs:__imp_RtlAcquireResourceShared
0x18000ff97  lea     rcx, [r14+20h]; CriticalSection
0x18000ff9b  call    cs:__imp_RtlEnterCriticalSection
0x18000ffa1  cmp     dword ptr [r14+4Ch], 0
0x18000ffa6  jnz     short loc_18000FFB0
0x18000ffa8  mov     rcx, r14; struct _USER_CACHE_ENTRY *
0x18000ffab  call    ?_UnprotectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; _UnprotectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18000ffb0  inc     dword ptr [r14+4Ch]
0x18000ffb4  lea     rcx, [r14+20h]; CriticalSection
0x18000ffb8  call    cs:__imp_RtlLeaveCriticalSection
0x18000ffbe  mov     rax, [r14+138h]
0x18000ffc5  test    rax, rax
0x18000ffc8  cmovnz  rbx, rax
0x18000ffcc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ffd3  cmp     word ptr [rbx+rax*2+2], 0
0x18000ffd9  lea     rax, [rax+1]
0x18000ffdd  jnz     short loc_18000FFD3
0x18000ffdf  lea     esi, [rax+1]
0x18000ffe2  mov     eax, 0FFFFFFFFh
0x18000ffe7  add     rsi, rsi
0x18000ffea  cmp     rsi, rax
0x18000ffed  ja      loc_1800101A1
0x18000fff3  lea     ebp, [rsi+8]
0x18000fff6  cmp     ebp, esi
0x18000fff8  jb      loc_180010152
0x18000fffe  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180010005  mov     edx, ebp
0x180010007  mov     r8, [rsp+88h+arg_28]
0x18001000f  mov     rcx, [rsp+88h+arg_0]
0x180010017  mov     rax, [rax+38h]
0x18001001b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010020  mov     edi, eax
0x180010022  test    eax, eax
0x180010024  jz      short loc_180010073
0x180010026  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18001002d  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180010034  movzx   eax, byte ptr [r9-1]
0x180010039  mov     rdx, r9
0x18001003c  dec     r9
0x18001003f  cmp     al, 5Ch ; '\'
0x180010041  jz      short loc_18001004A
0x180010043  cmp     r9, rcx
0x180010046  ja      short loc_180010034
0x180010048  cmp     al, 5Ch ; '\'
0x18001004a  lea     rax, Class
0x180010051  cmovz   r9, rdx
0x180010055  mov     [rsp+88h+var_58], rax
0x18001005a  lea     rax, aAllocateclient; "AllocateClientBuffer"
0x180010061  mov     [rsp+88h+var_60], rax
0x180010066  mov     [rsp+88h+var_68], 0DA1h
0x18001006e  jmp     loc_180010186
0x180010073  mov     rcx, [rsp+88h+arg_28]
0x18001007b  lea     r9, [r14+140h]
0x180010082  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180010089  mov     edx, 8
0x18001008e  mov     r8, [rcx]
0x180010091  mov     rcx, [rsp+88h+arg_0]
0x180010099  mov     rax, [rax+48h]
0x18001009d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100a2  mov     edi, eax
0x1800100a4  test    eax, eax
0x1800100a6  jz      short loc_1800100DC
0x1800100a8  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800100af  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800100b4  mov     r9, rax
0x1800100b7  lea     rax, Class
0x1800100be  mov     [rsp+88h+var_58], rax
0x1800100c3  lea     rax, aCopytoclientbu; "CopyToClientBuffer"
0x1800100ca  mov     [rsp+88h+var_60], rax
0x1800100cf  mov     [rsp+88h+var_68], 0DA8h
0x1800100d7  jmp     loc_180010186
0x1800100dc  mov     rax, [rsp+88h+arg_28]
0x1800100e4  mov     r9, rbx
0x1800100e7  mov     rcx, [rsp+88h+arg_0]
0x1800100ef  mov     edx, esi
0x1800100f1  mov     r8, [rax]
0x1800100f4  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800100fb  add     r8, 8
0x1800100ff  mov     rax, [rax+48h]
0x180010103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010108  mov     edi, eax
0x18001010a  test    eax, eax
0x18001010c  jz      short loc_18001013F
0x18001010e  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180010115  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001011a  mov     r9, rax
0x18001011d  lea     rax, Class
0x180010124  mov     [rsp+88h+var_58], rax
0x180010129  lea     rax, aCopytoclientbu; "CopyToClientBuffer"
0x180010130  mov     [rsp+88h+var_60], rax
0x180010135  mov     [rsp+88h+var_68], 0DB0h
0x18001013d  jmp     short loc_180010186
0x18001013f  mov     [r13+0], ebp
0x180010143  xor     edi, edi
0x180010145  mov     rbp, [rsp+88h+arg_0]
0x18001014d  jmp     loc_1800101E6
0x180010152  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180010159  mov     edi, 0C0000095h
0x18001015e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010163  mov     r9, rax
0x180010166  lea     rax, Class
0x18001016d  mov     [rsp+88h+var_58], rax
0x180010172  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x180010179  mov     [rsp+88h+var_60], rax
0x18001017e  mov     [rsp+88h+var_68], 0D9Bh
0x180010186  mov     r8d, edi
0x180010189  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010190  xor     ecx, ecx
0x180010192  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180010197  mov     rbp, [rsp+88h+arg_0]
0x18001019f  jmp     short loc_1800101E6
0x1800101a1  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800101a8  mov     edi, 0C0000095h
0x1800101ad  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800101b2  mov     r9, rax
0x1800101b5  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800101bc  lea     rax, Class
0x1800101c3  mov     r8d, edi
0x1800101c6  mov     [rsp+88h+var_58], rax
0x1800101cb  xor     ecx, ecx
0x1800101cd  lea     rax, aRtldwordmult; "RtlDWordMult"
0x1800101d4  mov     [rsp+88h+var_60], rax
0x1800101d9  mov     [rsp+88h+var_68], 0D97h
0x1800101e1  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800101e6  mov     rcx, r14; struct _USER_CACHE_ENTRY *
0x1800101e9  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x1800101ee  mov     r14, [rsp+88h+arg_8]
0x1800101f6  test    r12, r12
0x1800101f9  jz      short loc_180010208
0x1800101fb  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x180010202  call    cs:__imp_RtlReleaseResource
0x180010208  mov     rsi, [rsp+88h+arg_28]
0x180010210  mov     rcx, r15; struct _LOGON_SESSION *
0x180010213  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x180010218  test    edi, edi
0x18001021a  js      loc_1800102E2
0x180010220  jmp     loc_180010304
0x180010225  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18001022c  call    cs:__imp_RtlReleaseResource
0x180010232  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x180010239  mov     edi, 80090311h
0x18001023e  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180010245  movzx   eax, byte ptr [r9-1]
0x18001024a  mov     rdx, r9
0x18001024d  dec     r9
0x180010250  cmp     al, 5Ch ; '\'
0x180010252  jz      short loc_18001025B
0x180010254  cmp     r9, rcx
0x180010257  ja      short loc_180010245
0x180010259  cmp     al, 5Ch ; '\'
0x18001025b  cmovz   r9, rdx
0x18001025f  lea     rax, Class
0x180010266  mov     [rsp+88h+var_58], rax
0x18001026b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010272  lea     rax, aRefpackage; "RefPackage"
0x180010279  mov     r8d, edi
0x18001027c  mov     [rsp+88h+var_60], rax
0x180010281  xor     ecx, ecx
0x180010283  mov     [rsp+88h+var_68], 0D87h
0x18001028b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180010290  mov     rcx, r15
0x180010293  jmp     short loc_1800102DD
0x180010295  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18001029c  mov     edi, 0C000000Dh
0x1800102a1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800102a6  mov     r9, rax
0x1800102a9  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800102b0  lea     rax, Class
0x1800102b7  mov     r8d, edi
0x1800102ba  mov     [rsp+88h+var_58], rax
0x1800102bf  xor     ecx, ecx
0x1800102c1  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x1800102c8  mov     [rsp+88h+var_60], rax
0x1800102cd  mov     [rsp+88h+var_68], 0D75h
0x1800102d5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800102da  mov     rcx, rbx; struct _LOGON_SESSION *
0x1800102dd  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x1800102e2  mov     rdx, [rsi]
0x1800102e5  test    rdx, rdx
0x1800102e8  jz      short loc_180010304
0x1800102ea  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800102f1  mov     rcx, rbp
0x1800102f4  mov     rax, [rax+40h]
0x1800102f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102fd  mov     qword ptr [rsi], 0
0x180010304  mov     eax, edi
0x180010306  add     rsp, 50h
0x18001030a  pop     r15
0x18001030c  pop     r13
0x18001030e  pop     r12
0x180010310  pop     rdi
0x180010311  pop     rsi
0x180010312  pop     rbp
0x180010313  pop     rbx
0x180010314  retn
```
