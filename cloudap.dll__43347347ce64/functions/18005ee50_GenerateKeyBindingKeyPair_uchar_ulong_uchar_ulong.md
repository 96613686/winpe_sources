# GenerateKeyBindingKeyPair(uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x18005ee50`
- end: `0x18005f202`
- name: `?GenerateKeyBindingKeyPair@@YAJPEAPEAEPEAK01@Z`
- size: `946`
- prototype: `__int64 __fastcall(unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180034b64`
- `0x18005ee50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f02d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f02d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0f3`
- `bcrypt!BCryptImportKeyPair` at `0x18005efb4`
- `bcrypt!BCryptImportKeyPair` at `0x18005efb4`
- `bcrypt!BCryptDestroyKey` at `0x18005f1ea`
- `bcrypt!BCryptDestroyKey` at `0x18005f1ea`
- `RPCRT4!NdrClientCall3` at `0x18005eefb`
- `RPCRT4!NdrClientCall3` at `0x18005eefb`
- `RPCRT4!RpcExceptionFilter` at `0x18007fc0a`
- `RPCRT4!RpcExceptionFilter` at `0x18007fc0a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18005ef11`
- `RPCRT4!I_RpcMapWin32Status` at `0x18005ef11`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18005f014`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18005f0da`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18005f014`
- `CRYPT32!CryptExportPublicKeyInfoFromBCryptKeyHandle` at `0x18005f0da`

## string_xrefs

- `0x18005ef46`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x18005efc0`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x18005f01e`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x18005f083`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x18005f0e4`: `onecore\ds\ext\cloudap\dll\crediso.cpp`

## pseudocode

```c
__int64 __fastcall GenerateKeyBindingKeyPair(
        unsigned __int8 **a1,
        unsigned int *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  _DWORD *v8; // rdx
  _QWORD *v9; // rcx
  _QWORD *v10; // r8
  _DWORD *v11; // r9
  CLIENT_CALL_RETURN v13; // rbx
  unsigned __int8 *v14; // r14
  const char *v15; // r9
  __int64 Pointer_low; // r8
  const char *v17; // rdi
  DWORD LastError; // eax
  const char *v19; // r9
  __int64 v20; // r8
  PUCHAR v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned __int8 *v24; // rcx
  unsigned __int8 *v25; // rax
  __int64 v26; // rcx
  PUCHAR pbInput; // [rsp+20h] [rbp-88h]
  const char *cbInput; // [rsp+28h] [rbp-80h]
  DWORD pcbInfo; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-64h] BYREF
  ULONG v31[2]; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int8 *v32; // [rsp+50h] [rbp-58h] BYREF
  PUCHAR v33; // [rsp+58h] [rbp-50h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-48h] BYREF
  CLIENT_CALL_RETURN v35; // [rsp+68h] [rbp-40h]

  if ( !IsCredentialIsolationEnabled() )
    return 3221225659LL;
  phKey = 0;
  v33 = 0;
  v31[0] = 0;
  v32 = 0;
  v30 = 0;
  pcbInfo = 0;
  *v9 = 0;
  *v8 = 0;
  *v10 = 0;
  *v11 = 0;
  v35.Simple = 0;
  v13.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&CloudApIumRpc::CloudApIum_ProxyInfo,
                  1u,
                  0,
                  g_cloudApIumContext,
                  v31,
                  &v33,
                  &v30,
                  &v32).Pointer;
  v35.Pointer = v13.Pointer;
  v31[1] = (ULONG)v13.Pointer;
  v14 = 0;
  if ( LODWORD(v13.Pointer) )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
    cbInput = "CloudApIumGenerateKeyBindingKeyPair";
    LODWORD(pbInput) = 125;
LABEL_5:
    Pointer_low = LODWORD(v13.Pointer);
    goto LABEL_6;
  }
  LODWORD(v13.Pointer) = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0xE1, 0, L"RSAPUBLICBLOB", &phKey, v33, v31[0], 0);
  if ( LODWORD(v13.Pointer) )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
    cbInput = "BCryptImportKeyPair";
    LODWORD(pbInput) = 130;
    goto LABEL_5;
  }
  if ( CryptExportPublicKeyInfoFromBCryptKeyHandle(phKey, 1u, 0, 0, 0, 0, &pcbInfo) )
  {
    v14 = (unsigned __int8 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(pcbInfo);
    if ( !v14 )
    {
      LODWORD(v13.Pointer) = -1073741801;
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
      LODWORD(pbInput) = 141;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, pbInput, "AllocateLsaHeap for PublicKeyInfo", &Class);
      goto LABEL_17;
    }
    if ( CryptExportPublicKeyInfoFromBCryptKeyHandle(phKey, 1u, 0, 0, 0, (PCERT_PUBLIC_KEY_INFO)v14, &pcbInfo) )
    {
      *a1 = v14;
      v14 = 0;
      *a2 = pcbInfo;
      pcbInfo = 0;
      *a3 = v32;
      v32 = 0;
      *a4 = v30;
      v30 = 0;
      goto LABEL_17;
    }
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
    LastError = GetLastError();
    cbInput = "CryptExportPublicKeyInfoFromBCryptHandle failed";
    LODWORD(pbInput) = 146;
  }
  else
  {
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
    LastError = GetLastError();
    cbInput = "CryptExportPublicKeyInfoFromBCryptKeyHandle (size only) failed";
    LODWORD(pbInput) = 134;
  }
  v15 = v17;
  Pointer_low = LastError;
LABEL_6:
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Pointer_low, v15, pbInput, cbInput, &Class);
LABEL_17:
  v21 = v33;
  if ( v33 )
  {
    v22 = v31[0];
    if ( v31[0] )
    {
      do
      {
        *v21++ = 0;
        --v22;
      }
      while ( v22 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( v14 )
  {
    v23 = pcbInfo;
    v24 = v14;
    if ( pcbInfo )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    ((void (__fastcall *)(unsigned __int8 *))g_pLsaFunctionTable->FreeLsaHeap)(v14);
  }
  v25 = v32;
  if ( v32 )
  {
    v26 = v30;
    if ( v30 )
    {
      do
      {
        *v25++ = 0;
        --v26;
      }
      while ( v26 );
    }
    ((void (__fastcall *)(unsigned __int8 *))g_pLsaFunctionTable->FreeLsaHeap)(v32);
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  return LODWORD(v13.Pointer);
}

```

## disassembly

```asm
0x18005ee50  mov     rax, rsp
0x18005ee53  mov     [rax+20h], r9
0x18005ee57  mov     [rax+18h], r8
0x18005ee5b  mov     [rax+10h], rdx
0x18005ee5f  mov     [rax+8], rcx
0x18005ee63  push    rbx
0x18005ee64  push    rsi
0x18005ee65  push    rdi
0x18005ee66  push    r12
0x18005ee68  push    r13
0x18005ee6a  push    r14
0x18005ee6c  push    r15
0x18005ee6e  sub     rsp, 70h
0x18005ee72  mov     rdi, r9
0x18005ee75  mov     r15, r8
0x18005ee78  mov     r12, rdx
0x18005ee7b  mov     r13, rcx
0x18005ee7e  call    ?IsCredentialIsolationEnabled@@YA_NXZ; IsCredentialIsolationEnabled(void)
0x18005ee83  xor     esi, esi
0x18005ee85  test    al, al
0x18005ee87  jnz     short loc_18005EE93
0x18005ee89  mov     eax, 0C00000BBh
0x18005ee8e  jmp     loc_18005F1F2
0x18005ee93  mov     [rsp+0A8h+phKey], rsi
0x18005ee98  mov     [rsp+0A8h+var_50], rsi
0x18005ee9d  mov     [rsp+0A8h+var_60], esi
0x18005eea1  mov     [rsp+0A8h+var_58], rsi
0x18005eea6  mov     [rsp+0A8h+var_64], esi
0x18005eeaa  mov     [rsp+0A8h+pcbInfo], esi
0x18005eeae  mov     [rcx], rsi
0x18005eeb1  mov     [rdx], esi
0x18005eeb3  mov     [r8], rsi
0x18005eeb6  mov     [r9], esi
0x18005eeb9  mov     [rsp+0A8h+var_40], rsi
0x18005eebe  lea     rax, [rsp+0A8h+var_58]
0x18005eec3  mov     [rsp+0A8h+var_70], rax
0x18005eec8  lea     rax, [rsp+0A8h+var_64]
0x18005eecd  mov     qword ptr [rsp+0A8h+dwFlags], rax
0x18005eed2  lea     rax, [rsp+0A8h+var_50]
0x18005eed7  mov     qword ptr [rsp+0A8h+cbInput], rax
0x18005eedc  lea     rax, [rsp+0A8h+var_60]
0x18005eee1  mov     [rsp+0A8h+pbInput], rax
0x18005eee6  mov     r9, cs:?g_cloudApIumContext@@3PEAXEA; void * g_cloudApIumContext
0x18005eeed  xor     r8d, r8d; pReturnValue
0x18005eef0  lea     edx, [r8+1]; nProcNum
0x18005eef4  lea     rcx, ?CloudApIum_ProxyInfo@CloudApIumRpc@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18005eefb  call    cs:__imp_NdrClientCall3
0x18005ef01  mov     rbx, rax
0x18005ef04  mov     [rsp+0A8h+var_40], rax
0x18005ef09  mov     [rsp+0A8h+var_5C], eax
0x18005ef0d  jmp     short loc_18005EF3F
0x18005ef0f  mov     ecx, eax; Status
0x18005ef11  call    cs:__imp_I_RpcMapWin32Status
0x18005ef17  mov     ebx, eax
0x18005ef19  mov     [rsp+0A8h+var_5C], eax
0x18005ef1d  xor     esi, esi
0x18005ef1f  mov     rdi, [rsp+0A8h+arg_18]
0x18005ef27  mov     r15, [rsp+0A8h+arg_10]
0x18005ef2f  mov     r12, [rsp+0A8h+arg_8]
0x18005ef37  mov     r13, [rsp+0A8h+arg_0]
0x18005ef3f  mov     r14, rsi
0x18005ef42  test    ebx, ebx
0x18005ef44  jz      short loc_18005EF8B
0x18005ef46  lea     rcx, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18005ef4d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ef52  mov     r9, rax
0x18005ef55  lea     rcx, Class
0x18005ef5c  mov     qword ptr [rsp+0A8h+dwFlags], rcx
0x18005ef61  lea     rax, aCloudapiumgene; "CloudApIumGenerateKeyBindingKeyPair"
0x18005ef68  mov     qword ptr [rsp+0A8h+cbInput], rax
0x18005ef6d  mov     dword ptr [rsp+0A8h+pbInput], 7Dh ; '}'
0x18005ef75  mov     r8d, ebx
0x18005ef78  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005ef7f  xor     ecx, ecx
0x18005ef81  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005ef86  jmp     loc_18005F148
0x18005ef8b  mov     [rsp+0A8h+dwFlags], esi; dwFlags
0x18005ef8f  mov     eax, [rsp+0A8h+var_60]
0x18005ef93  mov     [rsp+0A8h+cbInput], eax; cbInput
0x18005ef97  mov     rax, [rsp+0A8h+var_50]
0x18005ef9c  mov     [rsp+0A8h+pbInput], rax; pbInput
0x18005efa1  lea     r9, [rsp+0A8h+phKey]; phKey
0x18005efa6  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x18005efad  xor     edx, edx; hImportKey
0x18005efaf  mov     ecx, 0E1h; hAlgorithm
0x18005efb4  call    cs:__imp_BCryptImportKeyPair
0x18005efba  mov     ebx, eax
0x18005efbc  test    eax, eax
0x18005efbe  jz      short loc_18005EFF1
0x18005efc0  lea     rcx, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18005efc7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005efcc  mov     r9, rax
0x18005efcf  lea     rcx, Class
0x18005efd6  mov     qword ptr [rsp+0A8h+dwFlags], rcx
0x18005efdb  lea     rax, aBcryptimportke; "BCryptImportKeyPair"
0x18005efe2  mov     qword ptr [rsp+0A8h+cbInput], rax
0x18005efe7  mov     dword ptr [rsp+0A8h+pbInput], 82h
0x18005efef  jmp     short loc_18005EF75
0x18005eff1  lea     rax, [rsp+0A8h+pcbInfo]
0x18005eff6  mov     qword ptr [rsp+0A8h+dwFlags], rax; pcbInfo
0x18005effb  mov     qword ptr [rsp+0A8h+cbInput], rsi; pInfo
0x18005f000  mov     [rsp+0A8h+pbInput], rsi; pvAuxInfo
0x18005f005  xor     r9d, r9d; dwFlags
0x18005f008  xor     r8d, r8d; pszPublicKeyObjId
0x18005f00b  lea     edx, [r9+1]; dwCertEncodingType
0x18005f00f  mov     rcx, [rsp+0A8h+phKey]; hBCryptKey
0x18005f014  call    cs:__imp_CryptExportPublicKeyInfoFromBCryptKeyHandle
0x18005f01a  test    eax, eax
0x18005f01c  jnz     short loc_18005F05E
0x18005f01e  lea     rcx, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18005f025  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f02a  mov     rdi, rax
0x18005f02d  call    cs:__imp_GetLastError
0x18005f033  lea     rcx, Class
0x18005f03a  mov     qword ptr [rsp+0A8h+dwFlags], rcx
0x18005f03f  lea     rcx, aCryptexportpub; "CryptExportPublicKeyInfoFromBCryptKeyHa"...
0x18005f046  mov     qword ptr [rsp+0A8h+cbInput], rcx
0x18005f04b  mov     dword ptr [rsp+0A8h+pbInput], 86h
0x18005f053  mov     r9, rdi
0x18005f056  mov     r8d, eax
0x18005f059  jmp     loc_18005EF78
0x18005f05e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005f065  mov     ecx, [rsp+0A8h+pcbInfo]
0x18005f069  mov     rax, [rax+28h]
0x18005f06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f072  mov     r14, rax
0x18005f075  test    rax, rax
0x18005f078  jnz     short loc_18005F0B7
0x18005f07a  mov     r8d, 0C0000017h
0x18005f080  mov     ebx, r8d
0x18005f083  lea     rcx, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18005f08a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f08f  mov     r9, rax
0x18005f092  lea     rcx, Class
0x18005f099  mov     qword ptr [rsp+0A8h+dwFlags], rcx
0x18005f09e  lea     rax, aAllocatelsahea_0; "AllocateLsaHeap for PublicKeyInfo"
0x18005f0a5  mov     qword ptr [rsp+0A8h+cbInput], rax
0x18005f0aa  mov     dword ptr [rsp+0A8h+pbInput], 8Dh
0x18005f0b2  jmp     loc_18005EF78
0x18005f0b7  lea     rax, [rsp+0A8h+pcbInfo]
0x18005f0bc  mov     qword ptr [rsp+0A8h+dwFlags], rax; pcbInfo
0x18005f0c1  mov     qword ptr [rsp+0A8h+cbInput], r14; pInfo
0x18005f0c6  mov     [rsp+0A8h+pbInput], rsi; pvAuxInfo
0x18005f0cb  xor     r9d, r9d; dwFlags
0x18005f0ce  xor     r8d, r8d; pszPublicKeyObjId
0x18005f0d1  lea     edx, [r9+1]; dwCertEncodingType
0x18005f0d5  mov     rcx, [rsp+0A8h+phKey]; hBCryptKey
0x18005f0da  call    cs:__imp_CryptExportPublicKeyInfoFromBCryptKeyHandle
0x18005f0e0  test    eax, eax
0x18005f0e2  jnz     short loc_18005F11E
0x18005f0e4  lea     rcx, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18005f0eb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f0f0  mov     rdi, rax
0x18005f0f3  call    cs:__imp_GetLastError
0x18005f0f9  lea     rcx, Class
0x18005f100  mov     qword ptr [rsp+0A8h+dwFlags], rcx
0x18005f105  lea     rcx, aCryptexportpub_0; "CryptExportPublicKeyInfoFromBCryptHandl"...
0x18005f10c  mov     qword ptr [rsp+0A8h+cbInput], rcx
0x18005f111  mov     dword ptr [rsp+0A8h+pbInput], 92h
0x18005f119  jmp     loc_18005F053
0x18005f11e  mov     [r13+0], r14
0x18005f122  mov     r14, rsi
0x18005f125  mov     eax, [rsp+0A8h+pcbInfo]
0x18005f129  mov     [r12], eax
0x18005f12d  mov     [rsp+0A8h+pcbInfo], esi
0x18005f131  mov     rax, [rsp+0A8h+var_58]
0x18005f136  mov     [r15], rax
0x18005f139  mov     [rsp+0A8h+var_58], rsi
0x18005f13e  mov     eax, [rsp+0A8h+var_64]
0x18005f142  mov     [rdi], eax
0x18005f144  mov     [rsp+0A8h+var_64], esi
0x18005f148  mov     rcx, [rsp+0A8h+var_50]
0x18005f14d  test    rcx, rcx
0x18005f150  jz      short loc_18005F17C
0x18005f152  mov     eax, [rsp+0A8h+var_60]
0x18005f156  test    rax, rax
0x18005f159  jz      short loc_18005F16C
0x18005f15b  mov     [rcx], sil
0x18005f15e  inc     rcx
0x18005f161  sub     rax, 1
0x18005f165  jnz     short loc_18005F15B
0x18005f167  mov     rcx, [rsp+0A8h+var_50]
0x18005f16c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005f173  mov     rax, [rax+30h]
0x18005f177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f17c  test    r14, r14
0x18005f17f  jz      short loc_18005F1AC
0x18005f181  mov     eax, [rsp+0A8h+pcbInfo]
0x18005f185  mov     rcx, r14
0x18005f188  test    rax, rax
0x18005f18b  jz      short loc_18005F199
0x18005f18d  mov     [rcx], sil
0x18005f190  inc     rcx
0x18005f193  sub     rax, 1
0x18005f197  jnz     short loc_18005F18D
0x18005f199  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005f1a0  mov     rcx, r14
0x18005f1a3  mov     rax, [rax+30h]
0x18005f1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f1ac  mov     rax, [rsp+0A8h+var_58]
0x18005f1b1  test    rax, rax
0x18005f1b4  jz      short loc_18005F1E0
0x18005f1b6  mov     ecx, [rsp+0A8h+var_64]
0x18005f1ba  test    rcx, rcx
0x18005f1bd  jz      short loc_18005F1CB
0x18005f1bf  mov     [rax], sil
0x18005f1c2  inc     rax
0x18005f1c5  sub     rcx, 1
0x18005f1c9  jnz     short loc_18005F1BF
0x18005f1cb  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005f1d2  mov     rcx, [rsp+0A8h+var_58]
0x18005f1d7  mov     rax, [rax+30h]
0x18005f1db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f1e0  mov     rcx, [rsp+0A8h+phKey]; hKey
0x18005f1e5  test    rcx, rcx
0x18005f1e8  jz      short loc_18005F1F0
0x18005f1ea  call    cs:__imp_BCryptDestroyKey
0x18005f1f0  mov     eax, ebx
0x18005f1f2  add     rsp, 70h
0x18005f1f6  pop     r15
0x18005f1f8  pop     r14
0x18005f1fa  pop     r13
0x18005f1fc  pop     r12
0x18005f1fe  pop     rdi
0x18005f1ff  pop     rsi
0x18005f200  pop     rbx
0x18005f201  retn
0x18007fbfc  push    rbp
0x18007fbfe  sub     rsp, 40h
0x18007fc02  mov     rbp, rdx
0x18007fc05  mov     rcx, [rcx]
0x18007fc08  mov     ecx, [rcx]; ExceptionCode
0x18007fc0a  call    cs:__imp_RpcExceptionFilter
0x18007fc10  nop
0x18007fc11  add     rsp, 40h
0x18007fc15  pop     rbp
0x18007fc16  retn
```
