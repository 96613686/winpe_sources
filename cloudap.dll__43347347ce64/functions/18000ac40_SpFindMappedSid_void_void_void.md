# SpFindMappedSid(void *,void *,void * *)

- ea: `0x18000ac40`
- end: `0x18000b0b8`
- name: `?SpFindMappedSid@@YAJPEAX0PEAPEAX@Z`
- size: `1144`
- prototype: `int(void *, void *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008060`
- `0x180052358`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000ac40`
- `0x18003ea9c`
- `0x180042410`
- `0x18007f9f0`
- `0x180081010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000ad68`
- `ntdll!RtlReleaseResource` at `0x18000ad75`
- `ntdll!RtlReleaseResource` at `0x18000adb4`
- `ntdll!RtlReleaseResource` at `0x18000ad68`
- `ntdll!RtlReleaseResource` at `0x18000ad75`
- `ntdll!RtlReleaseResource` at `0x18000adb4`
- `ntdll!RtlLengthSid` at `0x18000b003`
- `ntdll!RtlLengthSid` at `0x18000b003`
- `ntdll!RtlCopySid` at `0x18000b063`
- `ntdll!RtlCopySid` at `0x18000b063`
- `ntdll!RtlEqualSid` at `0x18000afd6`
- `ntdll!RtlEqualSid` at `0x18000afea`
- `ntdll!RtlEqualSid` at `0x18000afd6`
- `ntdll!RtlEqualSid` at `0x18000afea`
- `ntdll!RtlAcquireResourceShared` at `0x18000acb7`
- `ntdll!RtlAcquireResourceShared` at `0x18000ad3f`
- `ntdll!RtlAcquireResourceShared` at `0x18000acb7`
- `ntdll!RtlAcquireResourceShared` at `0x18000ad3f`

## string_xrefs

- `0x18000adc1`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000ae2c`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000ae92`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000af1c`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000af8a`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000b025`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000b073`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000b08e`: `RtlCopySid`
- `0x18000afb1`: `LoadMappedSids`

## pseudocode

```c
__int64 __fastcall SpFindMappedSid(void *a1, void *a2, void **a3)
{
  struct _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE *v5; // rax
  unsigned int MappedSids; // ebx
  struct _ApPluginPkg *v7; // r14
  unsigned int v8; // edi
  __int64 v9; // r15
  HLOCAL *v10; // rdi
  const char *v12; // r9
  char v13; // al
  const char *v14; // rdx
  bool v15; // zf
  const char *v16; // r9
  char v17; // al
  const char *v18; // rdx
  bool v19; // zf
  const char *v20; // r9
  char v21; // al
  const char *v22; // rdx
  bool v23; // zf
  const char *v24; // r9
  char v25; // al
  const char *v26; // rdx
  bool v27; // zf
  const char *v28; // rax
  BOOLEAN v29; // al
  HLOCAL v30; // r14
  __int64 v31; // rbx
  void *v32; // rax
  const char *v33; // r9
  const char *v34; // r9
  __int128 Buf1; // [rsp+40h] [rbp-48h] BYREF

  Buf1 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    MappedSids = -1073741811;
    v20 = "";
    while ( 1 )
    {
      v21 = *(v20 - 1);
      v22 = v20--;
      v23 = v21 == 92;
      if ( v21 == 92 )
        break;
      if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp" )
      {
        v23 = v21 == 92;
        break;
      }
    }
    if ( v23 )
      v20 = v22;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v20, 777, "Invalid Arg(s)", &Class);
    goto LABEL_39;
  }
  v5 = g_pLsaIdProvHostFunctionTable;
  *a3 = 0;
  MappedSids = (*((__int64 (__fastcall **)(void *, __int128 *))v5 + 10))(a1, &Buf1);
  if ( !MappedSids )
  {
    RtlAcquireResourceShared(&g_PackageListLock, 1u);
    v7 = g_pPlugins;
    if ( g_pPlugins )
    {
      v8 = g_cPlugins;
      while ( MappedSids < v8 )
      {
        v9 = 392LL * MappedSids;
        if ( !memcmp_0(&Buf1, (char *)v7 + v9 + 68, 0x10u) )
        {
          if ( *((char *)v7 + v9 + 160) >= 0 )
          {
            MappedSids = -1073741637;
            v16 = "";
            while ( 1 )
            {
              v17 = *(v16 - 1);
              v18 = v16--;
              v19 = v17 == 92;
              if ( v17 == 92 )
                break;
              if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp" )
              {
                v19 = v17 == 92;
                break;
              }
            }
            if ( v19 )
              v16 = v18;
            WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", 3221225659LL, v16, 797, "MappedAccountCaps", &Class);
          }
          else
          {
            _m_prefetchw((const void *)&g_lAccountCacheLoaded);
            if ( _InterlockedAnd(&g_lAccountCacheLoaded, 1u)
              || (MappedSids = LoadMappedSids(*(HKEY *)((char *)v7 + v9 + 352))) == 0 )
            {
              RtlAcquireResourceShared(&g_AadConnectMapLock, 1u);
              v10 = (HLOCAL *)g_MappedAccountCacheList;
              MappedSids = -1073741724;
              while ( v10 != &g_MappedAccountCacheList )
              {
                v29 = RtlEqualSid(v10[2], a2);
                v30 = v10[3];
                if ( v29 )
                  goto LABEL_55;
                if ( RtlEqualSid(v10[3], a2) )
                {
                  v30 = v10[2];
LABEL_55:
                  v31 = RtlLengthSid(v30);
                  v32 = (void *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(v31);
                  *a3 = v32;
                  if ( v32 )
                  {
                    MappedSids = RtlCopySid(v31, v32, v30);
                    if ( MappedSids )
                    {
                      v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSids, v34, 840, "RtlCopySid", &Class);
                    }
                  }
                  else
                  {
                    MappedSids = -1073741801;
                    v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v33, 836, "AllocateLsaHeap", &Class);
                  }
                  break;
                }
                v10 = (HLOCAL *)*v10;
              }
              RtlReleaseResource(&g_AadConnectMapLock);
            }
            else
            {
              v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSids, v28, 804, "LoadMappedSids", &Class);
            }
          }
          RtlReleaseResource(&g_PackageListLock);
          goto LABEL_15;
        }
        ++MappedSids;
      }
    }
    RtlReleaseResource(&g_PackageListLock);
    v12 = "";
    while ( 1 )
    {
      v13 = *(v12 - 1);
      v14 = v12--;
      v15 = v13 == 92;
      if ( v13 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp" )
      {
        v15 = v13 == 92;
        break;
      }
    }
    if ( v15 )
      v12 = v14;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v12, 789, "RefPackage", &Class);
    MappedSids = -1073741637;
LABEL_40:
    if ( *a3 )
    {
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      *a3 = 0;
    }
    return MappedSids;
  }
  v24 = "";
  while ( 1 )
  {
    v25 = *(v24 - 1);
    v26 = v24--;
    v27 = v25 == 92;
    if ( v25 == 92 )
      break;
    if ( v24 <= "onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp" )
    {
      v27 = v25 == 92;
      break;
    }
  }
  if ( v27 )
    v24 = v26;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSids, v24, 782, "GetProvInfo", &Class);
LABEL_15:
  if ( (MappedSids & 0x80000000) != 0 )
  {
LABEL_39:
    if ( !a3 )
      return MappedSids;
    goto LABEL_40;
  }
  return MappedSids;
}

```

## disassembly

```asm
0x18000ac40  mov     [rsp+arg_18], rbx
0x18000ac45  push    rbp
0x18000ac46  push    rsi
0x18000ac47  push    rdi
0x18000ac48  push    r14
0x18000ac4a  push    r15
0x18000ac4c  sub     rsp, 60h
0x18000ac50  mov     rax, cs:__security_cookie
0x18000ac57  xor     rax, rsp
0x18000ac5a  mov     [rsp+88h+var_38], rax
0x18000ac5f  xorps   xmm0, xmm0
0x18000ac62  mov     rsi, r8
0x18000ac65  mov     rbp, rdx
0x18000ac68  movups  [rsp+88h+Buf1], xmm0
0x18000ac6d  test    rcx, rcx
0x18000ac70  jz      loc_18000AE86
0x18000ac76  test    rdx, rdx
0x18000ac79  jz      loc_18000AE86
0x18000ac7f  test    r8, r8
0x18000ac82  jz      loc_18000AE86
0x18000ac88  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18000ac8f  lea     rdx, [rsp+88h+Buf1]
0x18000ac94  mov     qword ptr [r8], 0
0x18000ac9b  mov     rax, [rax+50h]
0x18000ac9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca4  mov     ebx, eax
0x18000aca6  test    eax, eax
0x18000aca8  jnz     loc_18000AF15
0x18000acae  mov     dl, 1; Wait
0x18000acb0  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000acb7  call    cs:__imp_RtlAcquireResourceShared
0x18000acbd  mov     r14, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x18000acc4  test    r14, r14
0x18000acc7  jz      loc_18000ADAD
0x18000accd  mov     edi, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18000acd3  cmp     ebx, edi
0x18000acd5  jnb     loc_18000ADAD
0x18000acdb  mov     eax, ebx
0x18000acdd  lea     rdx, [r14+44h]
0x18000ace1  imul    r15, rax, 188h
0x18000ace8  mov     r8d, 10h; Size
0x18000acee  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18000acf3  add     rdx, r15; Buf2
0x18000acf6  call    memcmp_0
0x18000acfb  test    eax, eax
0x18000acfd  jnz     loc_18000ADA6
0x18000ad03  test    byte ptr [r15+r14+0A0h], 80h
0x18000ad0c  jz      loc_18000AE20
0x18000ad12  prefetchw byte ptr cs:?g_lAccountCacheLoaded@@3JC; long volatile g_lAccountCacheLoaded
0x18000ad19  mov     eax, cs:?g_lAccountCacheLoaded@@3JC; long volatile g_lAccountCacheLoaded
0x18000ad1f  mov     edx, eax
0x18000ad21  and     edx, 1
0x18000ad24  lock cmpxchg cs:?g_lAccountCacheLoaded@@3JC, edx; long volatile g_lAccountCacheLoaded
0x18000ad2c  jnz     short loc_18000AD1F
0x18000ad2e  test    eax, eax
0x18000ad30  jz      loc_18000AF73
0x18000ad36  mov     dl, 1; Wait
0x18000ad38  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18000ad3f  call    cs:__imp_RtlAcquireResourceShared
0x18000ad45  mov     rdi, cs:?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedAccountCacheList
0x18000ad4c  lea     r15, ?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedAccountCacheList
0x18000ad53  mov     ebx, 0C0000064h
0x18000ad58  cmp     rdi, r15
0x18000ad5b  jnz     loc_18000AFCF
0x18000ad61  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18000ad68  call    cs:__imp_RtlReleaseResource
0x18000ad6e  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000ad75  call    cs:__imp_RtlReleaseResource
0x18000ad7b  test    ebx, ebx
0x18000ad7d  js      loc_18000AEE4
0x18000ad83  mov     eax, ebx
0x18000ad85  mov     rcx, [rsp+88h+var_38]
0x18000ad8a  xor     rcx, rsp; StackCookie
0x18000ad8d  call    __security_check_cookie
0x18000ad92  mov     rbx, [rsp+88h+arg_18]
0x18000ad9a  add     rsp, 60h
0x18000ad9e  pop     r15
0x18000ada0  pop     r14
0x18000ada2  pop     rdi
0x18000ada3  pop     rsi
0x18000ada4  pop     rbp
0x18000ada5  retn
0x18000ada6  inc     ebx
0x18000ada8  jmp     loc_18000ACD3
0x18000adad  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18000adb4  call    cs:__imp_RtlReleaseResource
0x18000adba  lea     r9, aOnecoreDsExtCl_9+2Ch; ""
0x18000adc1  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000adc8  movzx   eax, byte ptr [r9-1]
0x18000adcd  mov     rdx, r9
0x18000add0  dec     r9
0x18000add3  cmp     al, 5Ch ; '\'
0x18000add5  jz      short loc_18000ADDE
0x18000add7  cmp     r9, rcx
0x18000adda  ja      short loc_18000ADC8
0x18000addc  cmp     al, 5Ch ; '\'
0x18000adde  cmovz   r9, rdx
0x18000ade2  lea     rax, Class
0x18000ade9  mov     [rsp+88h+var_58], rax
0x18000adee  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000adf5  lea     rax, aRefpackage; "RefPackage"
0x18000adfc  mov     r8d, 80090311h
0x18000ae02  mov     [rsp+88h+var_60], rax
0x18000ae07  xor     ecx, ecx
0x18000ae09  mov     [rsp+88h+var_68], 315h
0x18000ae11  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ae16  mov     ebx, 0C00000BBh
0x18000ae1b  jmp     loc_18000AEED
0x18000ae20  mov     ebx, 0C00000BBh
0x18000ae25  lea     r9, aOnecoreDsExtCl_9+2Ch; ""
0x18000ae2c  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000ae33  movzx   eax, byte ptr [r9-1]
0x18000ae38  mov     rdx, r9
0x18000ae3b  dec     r9
0x18000ae3e  cmp     al, 5Ch ; '\'
0x18000ae40  jz      short loc_18000AE49
0x18000ae42  cmp     r9, rcx
0x18000ae45  ja      short loc_18000AE33
0x18000ae47  cmp     al, 5Ch ; '\'
0x18000ae49  lea     rax, Class
0x18000ae50  cmovz   r9, rdx
0x18000ae54  mov     [rsp+88h+var_58], rax
0x18000ae59  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ae60  lea     rax, aMappedaccountc; "MappedAccountCaps"
0x18000ae67  mov     r8d, ebx
0x18000ae6a  mov     [rsp+88h+var_60], rax
0x18000ae6f  mov     ecx, 2
0x18000ae74  mov     [rsp+88h+var_68], 31Dh
0x18000ae7c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ae81  jmp     loc_18000AD6E
0x18000ae86  mov     ebx, 0C000000Dh
0x18000ae8b  lea     r9, aOnecoreDsExtCl_9+2Ch; ""
0x18000ae92  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000ae99  movzx   eax, byte ptr [r9-1]
0x18000ae9e  mov     rdx, r9
0x18000aea1  dec     r9
0x18000aea4  cmp     al, 5Ch ; '\'
0x18000aea6  jz      short loc_18000AEAF
0x18000aea8  cmp     r9, rcx
0x18000aeab  ja      short loc_18000AE99
0x18000aead  cmp     al, 5Ch ; '\'
0x18000aeaf  cmovz   r9, rdx
0x18000aeb3  lea     rax, Class
0x18000aeba  mov     [rsp+88h+var_58], rax
0x18000aebf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000aec6  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000aecd  mov     r8d, ebx
0x18000aed0  mov     [rsp+88h+var_60], rax
0x18000aed5  xor     ecx, ecx
0x18000aed7  mov     [rsp+88h+var_68], 309h
0x18000aedf  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000aee4  test    rsi, rsi
0x18000aee7  jz      loc_18000AD83
0x18000aeed  mov     rcx, [rsi]
0x18000aef0  test    rcx, rcx
0x18000aef3  jz      loc_18000AD83
0x18000aef9  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000af00  mov     rax, [rax+30h]
0x18000af04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af09  mov     qword ptr [rsi], 0
0x18000af10  jmp     loc_18000AD83
0x18000af15  lea     r9, aOnecoreDsExtCl_9+2Ch; ""
0x18000af1c  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000af23  movzx   eax, byte ptr [r9-1]
0x18000af28  mov     rdx, r9
0x18000af2b  dec     r9
0x18000af2e  cmp     al, 5Ch ; '\'
0x18000af30  jz      short loc_18000AF39
0x18000af32  cmp     r9, rcx
0x18000af35  ja      short loc_18000AF23
0x18000af37  cmp     al, 5Ch ; '\'
0x18000af39  cmovz   r9, rdx
0x18000af3d  lea     rax, Class
0x18000af44  mov     [rsp+88h+var_58], rax
0x18000af49  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000af50  lea     rax, aGetprovinfo; "GetProvInfo"
0x18000af57  mov     r8d, ebx
0x18000af5a  mov     [rsp+88h+var_60], rax
0x18000af5f  xor     ecx, ecx
0x18000af61  mov     [rsp+88h+var_68], 30Eh
0x18000af69  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000af6e  jmp     loc_18000AD7B
0x18000af73  mov     rcx, [r15+r14+160h]; hKey
0x18000af7b  call    LoadMappedSids
0x18000af80  mov     ebx, eax
0x18000af82  test    eax, eax
0x18000af84  jz      loc_18000AD36
0x18000af8a  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000af91  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000af96  mov     r9, rax
0x18000af99  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000afa0  lea     rax, Class
0x18000afa7  mov     r8d, ebx
0x18000afaa  mov     [rsp+88h+var_58], rax
0x18000afaf  xor     ecx, ecx
0x18000afb1  lea     rax, aLoadmappedsids; "LoadMappedSids"
0x18000afb8  mov     [rsp+88h+var_60], rax
0x18000afbd  mov     [rsp+88h+var_68], 324h
0x18000afc5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000afca  jmp     loc_18000AD6E
0x18000afcf  mov     rcx, [rdi+10h]; Sid1
0x18000afd3  mov     rdx, rbp; Sid2
0x18000afd6  call    cs:__imp_RtlEqualSid
0x18000afdc  mov     r14, [rdi+18h]
0x18000afe0  test    al, al
0x18000afe2  jnz     short loc_18000B000
0x18000afe4  mov     rdx, rbp; Sid2
0x18000afe7  mov     rcx, r14; Sid1
0x18000afea  call    cs:__imp_RtlEqualSid
0x18000aff0  test    al, al
0x18000aff2  jnz     short loc_18000AFFC
0x18000aff4  mov     rdi, [rdi]
0x18000aff7  jmp     loc_18000AD58
0x18000affc  mov     r14, [rdi+10h]
0x18000b000  mov     rcx, r14; Sid
0x18000b003  call    cs:__imp_RtlLengthSid
0x18000b009  mov     rcx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000b010  mov     ebx, eax
0x18000b012  mov     rax, [rcx+28h]
0x18000b016  mov     ecx, ebx
0x18000b018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b01d  mov     [rsi], rax
0x18000b020  test    rax, rax
0x18000b023  jnz     short loc_18000B05B
0x18000b025  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000b02c  mov     ebx, 0C0000017h
0x18000b031  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b036  mov     r9, rax
0x18000b039  lea     rax, Class
0x18000b040  mov     [rsp+88h+var_58], rax
0x18000b045  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000b04c  mov     [rsp+88h+var_60], rax
0x18000b051  mov     [rsp+88h+var_68], 344h
0x18000b059  jmp     short loc_18000B0A2
0x18000b05b  mov     r8, r14; SourceSid
0x18000b05e  mov     rdx, rax; DestinationSid
0x18000b061  mov     ecx, ebx; DestinationSidLength
0x18000b063  call    cs:__imp_RtlCopySid
0x18000b069  mov     ebx, eax
0x18000b06b  test    eax, eax
0x18000b06d  jz      loc_18000AD61
0x18000b073  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000b07a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b07f  mov     r9, rax
0x18000b082  lea     rax, Class
0x18000b089  mov     [rsp+88h+var_58], rax
0x18000b08e  lea     rax, aRtlcopysid; "RtlCopySid"
0x18000b095  mov     [rsp+88h+var_60], rax
0x18000b09a  mov     [rsp+88h+var_68], 348h
0x18000b0a2  mov     r8d, ebx
0x18000b0a5  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000b0ac  xor     ecx, ecx
0x18000b0ae  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000b0b3  jmp     loc_18000AD61
```
