# SetMappedAadAccountLocalSid(_GUID *,ushort const *,void *)

- ea: `0x18005ea48`
- end: `0x18005ee1b`
- name: `?SetMappedAadAccountLocalSid@@YAJPEAU_GUID@@PEBGPEAX@Z`
- size: `979`
- prototype: `int(struct _GUID *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800571b0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x180042410`
- `0x18004317c`
- `0x18005ea48`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ed9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eda8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ed9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eda8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005eb07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ec12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005eb07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ec12`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005ecb4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005ecb4`
- `ntdll!RtlReleaseResource` at `0x18005ed6b`
- `ntdll!RtlReleaseResource` at `0x18005ed6b`
- `ntdll!NtQueryInformationToken` at `0x18005ebbe`
- `ntdll!NtQueryInformationToken` at `0x18005ebbe`
- `ntdll!RtlLengthSid` at `0x18005ec03`
- `ntdll!RtlLengthSid` at `0x18005ec03`
- `ntdll!RtlCopySid` at `0x18005ec6b`
- `ntdll!RtlCopySid` at `0x18005ec6b`

## string_xrefs

- `0x18005eaba`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005eb1b`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005eb6e`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005ebca`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005ec2a`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005ec77`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005ecfc`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005edb0`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18005ec92`: `RtlCopySid`
- `0x18005ebe5`: `NtQueryInformationToken`

## pseudocode

```c
__int64 __fastcall SetMappedAadAccountLocalSid(struct _GUID *a1, const unsigned __int16 *a2, void *a3)
{
  unsigned int HashString; // edi
  char *v6; // rbx
  const char *v7; // r9
  HLOCAL v8; // rax
  const char *v9; // r9
  __int64 v10; // r8
  const WCHAR *v11; // rcx
  ULONG v12; // edi
  HLOCAL v13; // rax
  const char *v14; // r9
  __int64 v15; // r8
  _QWORD *v16; // rdx
  HLOCAL *i; // rcx
  unsigned __int16 *v18; // rax
  int v19; // r9d
  int v20; // r8d
  const char *v21; // rax
  void *v22; // rcx
  const char *v23; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-B8h]
  const char *v26; // [rsp+28h] [rbp-B0h]
  LPCWSTR lpSrcStr; // [rsp+40h] [rbp-98h] BYREF
  ULONG v28; // [rsp+48h] [rbp-90h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-88h] BYREF

  lpSrcStr = 0;
  memset_0(TokenInformation, 0, 0x58u);
  v28 = 0;
  if ( !a2 || !a3 )
  {
    HashString = -1073741811;
    v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v23, 287, "Invalid Arg(s)", &Class);
    return HashString;
  }
  HashString = DuplicateString(a2, 0, (unsigned __int16 **)&lpSrcStr);
  if ( HashString )
  {
    v6 = 0;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
    v26 = "DuplicateString";
    LODWORD(ReturnLength) = 294;
LABEL_5:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v7, ReturnLength, v26, &Class);
    goto LABEL_29;
  }
  v8 = LocalAlloc(0x40u, 0xA0u);
  v6 = (char *)v8;
  if ( v8 )
  {
    v11 = lpSrcStr;
    *((_QWORD *)v8 + 19) = 0;
    HashString = GetHashString(v11, (unsigned __int16 *const)v8 + 8);
    if ( HashString )
    {
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
      v26 = "GetHashString";
      LODWORD(ReturnLength) = 308;
      goto LABEL_5;
    }
    HashString = NtQueryInformationToken(a3, TokenUser, TokenInformation, 0x58u, &v28);
    if ( HashString )
    {
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
      v26 = "NtQueryInformationToken";
      LODWORD(ReturnLength) = 317;
      goto LABEL_5;
    }
    v12 = RtlLengthSid(TokenInformation[0]);
    v13 = LocalAlloc(0x40u, v12);
    *((_QWORD *)v6 + 19) = v13;
    if ( v13 )
    {
      HashString = RtlCopySid(v12, v13, TokenInformation[0]);
      if ( !HashString )
      {
        RtlAcquireResourceExclusive(&g_AadConnectMapLock, 1u);
        v16 = g_MappedUserNameHashList;
        for ( i = (HLOCAL *)g_MappedUserNameHashList; i != &g_MappedUserNameHashList; i = (HLOCAL *)*i )
        {
          v18 = (unsigned __int16 *)(i + 2);
          do
          {
            v19 = *(unsigned __int16 *)((char *)v18 + v6 - (char *)i);
            v20 = *v18 - v19;
            if ( v20 )
              break;
            ++v18;
          }
          while ( v19 );
          if ( !v20 )
          {
            HashString = -1073741635;
            v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
            LODWORD(ReturnLength) = 341;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225661LL, v21, ReturnLength, "DuplicatedRequest", &Class);
            goto LABEL_28;
          }
        }
        if ( *((HLOCAL **)g_MappedUserNameHashList + 1) != &g_MappedUserNameHashList )
          __fastfail(3u);
        *(_QWORD *)v6 = g_MappedUserNameHashList;
        *((_QWORD *)v6 + 1) = &g_MappedUserNameHashList;
        v16[1] = v6;
        g_MappedUserNameHashList = v6;
        v6 = 0;
LABEL_28:
        RtlReleaseResource(&g_AadConnectMapLock);
        goto LABEL_29;
      }
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
      v26 = "RtlCopySid";
      LODWORD(ReturnLength) = 328;
      goto LABEL_5;
    }
    HashString = -1073741801;
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
    LODWORD(ReturnLength) = 324;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v14, ReturnLength, "LocalAlloc", &Class);
  }
  else
  {
    HashString = -1073741801;
    v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v9, 300, "LocalAlloc", &Class);
  }
LABEL_29:
  if ( lpSrcStr )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(lpSrcStr);
  if ( v6 )
  {
    v22 = (void *)*((_QWORD *)v6 + 19);
    if ( v22 )
      LocalFree(v22);
    LocalFree(v6);
  }
  return HashString;
}

```

## disassembly

```asm
0x18005ea48  mov     [rsp+arg_0], rbx
0x18005ea4d  push    rsi
0x18005ea4e  push    rdi
0x18005ea4f  push    r14
0x18005ea51  sub     rsp, 0C0h
0x18005ea58  mov     rax, cs:__security_cookie
0x18005ea5f  xor     rax, rsp
0x18005ea62  mov     [rsp+0D8h+var_28], rax
0x18005ea6a  mov     rbx, rdx
0x18005ea6d  mov     [rsp+0D8h+lpSrcStr], 0
0x18005ea76  xor     edx, edx; Val
0x18005ea78  lea     rcx, [rsp+0D8h+TokenInformation]; void *
0x18005ea7d  mov     rsi, r8
0x18005ea80  lea     r8d, [rdx+58h]; Size
0x18005ea84  call    memset_0
0x18005ea89  mov     [rsp+0D8h+var_90], 0
0x18005ea91  test    rbx, rbx
0x18005ea94  jz      loc_18005EDB0
0x18005ea9a  test    rsi, rsi
0x18005ea9d  jz      loc_18005EDB0
0x18005eaa3  lea     r8, [rsp+0D8h+lpSrcStr]; unsigned __int16 **
0x18005eaa8  xor     edx, edx; int
0x18005eaaa  mov     rcx, rbx; Src
0x18005eaad  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18005eab2  mov     edi, eax
0x18005eab4  test    eax, eax
0x18005eab6  jz      short loc_18005EAFF
0x18005eab8  xor     ebx, ebx
0x18005eaba  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005eac1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005eac6  mov     r9, rax
0x18005eac9  lea     rax, Class
0x18005ead0  mov     [rsp+0D8h+var_A8], rax
0x18005ead5  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x18005eadc  mov     [rsp+0D8h+var_B0], rax
0x18005eae1  mov     dword ptr [rsp+0D8h+ReturnLength], 126h
0x18005eae9  mov     r8d, edi
0x18005eaec  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005eaf3  xor     ecx, ecx
0x18005eaf5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005eafa  jmp     loc_18005ED71
0x18005eaff  mov     edx, 0A0h; uBytes
0x18005eb04  lea     ecx, [rdx-60h]; uFlags
0x18005eb07  call    cs:__imp_LocalAlloc
0x18005eb0d  mov     rbx, rax
0x18005eb10  test    rax, rax
0x18005eb13  jnz     short loc_18005EB4F
0x18005eb15  mov     r8d, 0C0000017h
0x18005eb1b  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005eb22  mov     edi, r8d
0x18005eb25  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005eb2a  mov     r9, rax
0x18005eb2d  lea     rax, Class
0x18005eb34  mov     [rsp+0D8h+var_A8], rax
0x18005eb39  lea     rax, aLocalalloc; "LocalAlloc"
0x18005eb40  mov     [rsp+0D8h+var_B0], rax
0x18005eb45  mov     dword ptr [rsp+0D8h+ReturnLength], 12Ch
0x18005eb4d  jmp     short loc_18005EAEC
0x18005eb4f  mov     rcx, [rsp+0D8h+lpSrcStr]; lpSrcStr
0x18005eb54  lea     rdx, [rax+10h]; unsigned __int16 *
0x18005eb58  mov     qword ptr [rax+98h], 0
0x18005eb63  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18005eb68  mov     edi, eax
0x18005eb6a  test    eax, eax
0x18005eb6c  jz      short loc_18005EBA2
0x18005eb6e  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005eb75  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005eb7a  mov     r9, rax
0x18005eb7d  lea     rax, Class
0x18005eb84  mov     [rsp+0D8h+var_A8], rax
0x18005eb89  lea     rax, aGethashstring; "GetHashString"
0x18005eb90  mov     [rsp+0D8h+var_B0], rax
0x18005eb95  mov     dword ptr [rsp+0D8h+ReturnLength], 134h
0x18005eb9d  jmp     loc_18005EAE9
0x18005eba2  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18005eba8  lea     rax, [rsp+0D8h+var_90]
0x18005ebad  lea     r8, [rsp+0D8h+TokenInformation]; TokenInformation
0x18005ebb2  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x18005ebb7  mov     rcx, rsi; TokenHandle
0x18005ebba  lea     edx, [r9-57h]; TokenInformationClass
0x18005ebbe  call    cs:__imp_NtQueryInformationToken
0x18005ebc4  mov     edi, eax
0x18005ebc6  test    eax, eax
0x18005ebc8  jz      short loc_18005EBFE
0x18005ebca  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005ebd1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ebd6  mov     r9, rax
0x18005ebd9  lea     rax, Class
0x18005ebe0  mov     [rsp+0D8h+var_A8], rax
0x18005ebe5  lea     rax, aNtqueryinforma_1; "NtQueryInformationToken"
0x18005ebec  mov     [rsp+0D8h+var_B0], rax
0x18005ebf1  mov     dword ptr [rsp+0D8h+ReturnLength], 13Dh
0x18005ebf9  jmp     loc_18005EAE9
0x18005ebfe  mov     rcx, [rsp+0D8h+TokenInformation]; Sid
0x18005ec03  call    cs:__imp_RtlLengthSid
0x18005ec09  mov     edx, eax; uBytes
0x18005ec0b  mov     ecx, 40h ; '@'; uFlags
0x18005ec10  mov     edi, eax
0x18005ec12  call    cs:__imp_LocalAlloc
0x18005ec18  mov     [rbx+98h], rax
0x18005ec1f  test    rax, rax
0x18005ec22  jnz     short loc_18005EC61
0x18005ec24  mov     r8d, 0C0000017h
0x18005ec2a  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005ec31  mov     edi, r8d
0x18005ec34  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ec39  mov     r9, rax
0x18005ec3c  lea     rax, Class
0x18005ec43  mov     [rsp+0D8h+var_A8], rax
0x18005ec48  lea     rax, aLocalalloc; "LocalAlloc"
0x18005ec4f  mov     [rsp+0D8h+var_B0], rax
0x18005ec54  mov     dword ptr [rsp+0D8h+ReturnLength], 144h
0x18005ec5c  jmp     loc_18005EAEC
0x18005ec61  mov     r8, [rsp+0D8h+TokenInformation]; SourceSid
0x18005ec66  mov     rdx, rax; DestinationSid
0x18005ec69  mov     ecx, edi; DestinationSidLength
0x18005ec6b  call    cs:__imp_RtlCopySid
0x18005ec71  mov     edi, eax
0x18005ec73  test    eax, eax
0x18005ec75  jz      short loc_18005ECAB
0x18005ec77  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005ec7e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ec83  mov     r9, rax
0x18005ec86  lea     rax, Class
0x18005ec8d  mov     [rsp+0D8h+var_A8], rax
0x18005ec92  lea     rax, aRtlcopysid; "RtlCopySid"
0x18005ec99  mov     [rsp+0D8h+var_B0], rax
0x18005ec9e  mov     dword ptr [rsp+0D8h+ReturnLength], 148h
0x18005eca6  jmp     loc_18005EAE9
0x18005ecab  mov     dl, 1; Wait
0x18005ecad  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18005ecb4  call    cs:__imp_RtlAcquireResourceExclusive
0x18005ecba  mov     rdx, cs:?g_MappedUserNameHashList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedUserNameHashList
0x18005ecc1  lea     r11, ?g_MappedUserNameHashList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedUserNameHashList
0x18005ecc8  mov     rcx, rdx
0x18005eccb  cmp     rcx, r11
0x18005ecce  jz      short loc_18005ED43
0x18005ecd0  lea     rax, [rcx+10h]
0x18005ecd4  lea     r10, [rbx+10h]
0x18005ecd8  sub     r10, rax
0x18005ecdb  movzx   r8d, word ptr [rax]
0x18005ecdf  movzx   r9d, word ptr [rax+r10]
0x18005ece4  sub     r8d, r9d
0x18005ece7  jnz     short loc_18005ECF2
0x18005ece9  add     rax, 2
0x18005eced  test    r9d, r9d
0x18005ecf0  jnz     short loc_18005ECDB
0x18005ecf2  test    r8d, r8d
0x18005ecf5  jz      short loc_18005ECFC
0x18005ecf7  mov     rcx, [rcx]
0x18005ecfa  jmp     short loc_18005ECCB
0x18005ecfc  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005ed03  mov     edi, 0C00000BDh
0x18005ed08  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ed0d  mov     r9, rax
0x18005ed10  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005ed17  lea     rax, Class
0x18005ed1e  mov     r8d, edi
0x18005ed21  mov     [rsp+0D8h+var_A8], rax
0x18005ed26  xor     ecx, ecx
0x18005ed28  lea     rax, aDuplicatedrequ; "DuplicatedRequest"
0x18005ed2f  mov     [rsp+0D8h+var_B0], rax
0x18005ed34  mov     dword ptr [rsp+0D8h+ReturnLength], 155h
0x18005ed3c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005ed41  jmp     short loc_18005ED64
0x18005ed43  cmp     [rdx+8], r11
0x18005ed47  jz      short loc_18005ED50
0x18005ed49  mov     ecx, 3
0x18005ed4e  int     29h; Win8: RtlFailFast(ecx)
0x18005ed50  mov     [rbx], rdx
0x18005ed53  mov     [rbx+8], r11
0x18005ed57  mov     [rdx+8], rbx
0x18005ed5b  mov     cs:?g_MappedUserNameHashList@@3U_LIST_ENTRY@@A, rbx; _LIST_ENTRY g_MappedUserNameHashList
0x18005ed62  xor     ebx, ebx
0x18005ed64  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18005ed6b  call    cs:__imp_RtlReleaseResource
0x18005ed71  cmp     [rsp+0D8h+lpSrcStr], 0
0x18005ed77  jz      short loc_18005ED8E
0x18005ed79  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005ed80  mov     rcx, [rsp+0D8h+lpSrcStr]
0x18005ed85  mov     rax, [rax+30h]
0x18005ed89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed8e  test    rbx, rbx
0x18005ed91  jz      short loc_18005EDF5
0x18005ed93  mov     rcx, [rbx+98h]; hMem
0x18005ed9a  test    rcx, rcx
0x18005ed9d  jz      short loc_18005EDA5
0x18005ed9f  call    cs:__imp_LocalFree
0x18005eda5  mov     rcx, rbx; hMem
0x18005eda8  call    cs:__imp_LocalFree
0x18005edae  jmp     short loc_18005EDF5
0x18005edb0  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18005edb7  mov     edi, 0C000000Dh
0x18005edbc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005edc1  mov     r9, rax
0x18005edc4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005edcb  lea     rax, Class
0x18005edd2  mov     r8d, edi
0x18005edd5  mov     [rsp+0D8h+var_A8], rax
0x18005edda  xor     ecx, ecx
0x18005eddc  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18005ede3  mov     [rsp+0D8h+var_B0], rax
0x18005ede8  mov     dword ptr [rsp+0D8h+ReturnLength], 11Fh
0x18005edf0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005edf5  mov     eax, edi
0x18005edf7  mov     rcx, [rsp+0D8h+var_28]
0x18005edff  xor     rcx, rsp; StackCookie
0x18005ee02  call    __security_check_cookie
0x18005ee07  mov     rbx, [rsp+0D8h+arg_0]
0x18005ee0f  add     rsp, 0C0h
0x18005ee16  pop     r14
0x18005ee18  pop     rdi
0x18005ee19  pop     rsi
0x18005ee1a  retn
```
