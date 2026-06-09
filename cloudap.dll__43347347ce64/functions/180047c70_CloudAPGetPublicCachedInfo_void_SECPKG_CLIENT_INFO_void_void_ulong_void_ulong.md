# CloudAPGetPublicCachedInfo(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180047c70`
- end: `0x1800483a7`
- name: `?CloudAPGetPublicCachedInfo@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `1847`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x18000e900`
- `0x18000ee60`
- `0x18000fb70`
- `0x18000fd50`
- `0x180029650`
- `0x18002bf5c`
- `0x18002f080`
- `0x180042410`
- `0x180047c70`
- `0x18005f6b0`
- `0x1800641e4`
- `0x180081010`

## string_xrefs

- `0x180047d1b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047da3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047dee`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047e43`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047ec1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047f0f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047f7d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180047fc4`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004801f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800480a5`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048108`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004815a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800481c7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048213`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004824d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180048002`: `PublicCacheData`
- `0x1800481e5`: `CopyToClientBuffer`
- `0x180047dc1`: `invalid cachekey length`
- `0x180048046`: `GetLogonPublicCacheForUser`
- `0x1800480cc`: `GetRawCacheNode`
- `0x180048123`: `FIDOValidatePublicCacheData`

## pseudocode

```c
__int64 __fastcall CloudAPGetPublicCachedInfo(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  __int64 v9; // rsi
  HLOCAL v10; // r12
  unsigned __int8 *v11; // r14
  unsigned int HashString; // ebx
  const char *v13; // r9
  __int64 v14; // r8
  unsigned int v15; // ecx
  unsigned int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // edx
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // rax
  __int64 v22; // rax
  const char *v23; // rax
  unsigned int v24; // edi
  const char *v25; // r9
  __int64 v26; // r8
  struct _DECRYPTED_AUTH_DATA *v28; // [rsp+20h] [rbp-E0h]
  const char *v29; // [rsp+28h] [rbp-D8h]
  unsigned int v30; // [rsp+40h] [rbp-C0h] BYREF
  struct _ApPluginPkg *v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *Src[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v33; // [rsp+60h] [rbp-A0h]
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v35; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v36; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpSrcStr[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v38; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING v39; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v40; // [rsp+A8h] [rbp-58h]
  _DWORD v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v42; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v43[72]; // [rsp+C0h] [rbp-40h] BYREF

  v40 = a7;
  v30 = 0;
  v33 = 0;
  *a6 = 0;
  v9 = 0;
  *a7 = 0;
  v10 = 0;
  v38 = 0;
  v11 = 0;
  v31 = 0;
  hMem = 0;
  v35 = 0;
  v36 = 0;
  v39 = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)lpSrcStr = 0;
  if ( a5 >= 0x28 && a3 )
  {
    if ( *((_DWORD *)a3 + 5) == 6 )
    {
      v15 = *((_DWORD *)a3 + 7);
      v41[0] = 7;
      if ( !v15 || (v15 & 1) != 0 || (v16 = v15 + *((_DWORD *)a3 + 6), v16 < v15) || v16 > a5 )
      {
        HashString = -1073741811;
        v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v26, v25, 4099, "invalid username length", &Class);
        goto LABEL_42;
      }
      v17 = *((_DWORD *)a3 + 9);
      if ( v17 )
      {
        v18 = v17 + *((_DWORD *)a3 + 8);
        if ( v18 < v17 || v18 > a5 )
        {
          HashString = -1073741811;
          v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, 4108, "invalid cachekey length", &Class);
          goto LABEL_42;
        }
      }
      HashString = RefPackage((struct _GUID *)(a3 + 4), &v31);
      if ( HashString )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v29 = "RefPackage";
        LODWORD(v28) = 4115;
      }
      else
      {
        v9 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(28);
        if ( v9 )
        {
          *(_DWORD *)v9 = 1835036;
          *(_WORD *)(v9 + 24) = 0;
          *(_DWORD *)(v9 + 20) = 28;
          *(_OWORD *)(v9 + 4) = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
          v39.Buffer = (PWSTR)&a3[*((unsigned int *)a3 + 6)];
          v39.MaximumLength = *((_WORD *)a3 + 14);
          v39.Length = v39.MaximumLength;
          HashString = DuplicateUnicodeString4(&v39, Src);
          if ( HashString )
          {
            v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            v29 = "DuplicateUnicodeString4";
            LODWORD(v28) = 4139;
          }
          else
          {
            HashString = DuplicateString(Src[0], 1, &Src[1]);
            if ( HashString )
            {
              v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
              v29 = "DuplicateString";
              LODWORD(v28) = 4145;
            }
            else
            {
              v33 = (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)v9;
              v9 = 0;
              HashString = ConvertAuthDataToAuthDataInt(
                             0,
                             v31,
                             0,
                             (struct _DECRYPTED_AUTH_DATA *)Src,
                             (struct _DECRYPTED_AUTH_DATA *)lpSrcStr,
                             &v36,
                             0);
              if ( HashString )
              {
                v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                v29 = "ConvertAuthDataToAuthDataInt";
                LODWORD(v28) = 4158;
              }
              else
              {
                HashString = GetHashString(lpSrcStr[1], v43);
                if ( HashString )
                {
                  v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  v29 = "GetHashString";
                  LODWORD(v28) = 4161;
                }
                else
                {
                  HashString = _GetLogonCacheForUser(
                                 *((const unsigned __int16 **)v31 + 43),
                                 v43,
                                 L"PublicCacheData",
                                 (struct _CloudAPCache **)&hMem);
                  if ( HashString )
                  {
                    v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                    LODWORD(v28) = 4167;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v21, v28, "GetLogonPublicCacheForUser", &Class);
                    v10 = hMem;
                    goto LABEL_42;
                  }
                  v22 = -1;
                  do
                    ++v22;
                  while ( Src[1][v22] );
                  v10 = hMem;
                  v42 = Src[1];
                  v41[1] = 2 * v22;
                  HashString = GetRawCacheNode(
                                 (struct _CloudAPCache *)hMem,
                                 (struct _tagCacheNodeIdentifier *)v41,
                                 &v35,
                                 &v30);
                  if ( HashString )
                  {
                    v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                    LODWORD(v28) = 4182;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v23, v28, "GetRawCacheNode", &Class);
                    v11 = v35;
                    goto LABEL_42;
                  }
                  v11 = v35;
                  v24 = v30;
                  HashString = FIDOValidatePublicCacheData(v35, v30);
                  if ( HashString )
                  {
                    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                    v29 = "FIDOValidatePublicCacheData";
                    LODWORD(v28) = 4187;
                  }
                  else
                  {
                    HashString = ((__int64 (__fastcall *)(void **, _QWORD, void **))g_pLsaFunctionTable->AllocateClientBuffer)(
                                   a1,
                                   v24,
                                   a6);
                    if ( HashString )
                    {
                      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                      v29 = "AllocateClientBuffer";
                      LODWORD(v28) = 4194;
                    }
                    else
                    {
                      HashString = ((__int64 (__fastcall *)(void **, _QWORD, _QWORD, unsigned __int8 *))g_pLsaFunctionTable->CopyToClientBuffer)(
                                     a1,
                                     v24,
                                     *a6,
                                     v11);
                      if ( (HashString & 0x80000000) == 0 )
                      {
                        *v40 = v24;
                        HashString = 0;
                        goto LABEL_42;
                      }
                      ((void (__fastcall *)(void **, _QWORD))g_pLsaFunctionTable->FreeClientBuffer)(a1, *a6);
                      *a6 = 0;
                      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                      v29 = "CopyToClientBuffer";
                      LODWORD(v28) = 4207;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          HashString = -1073741801;
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v29 = "AllocateLsaHeap";
          LODWORD(v28) = 4126;
        }
      }
    }
    else
    {
      HashString = -1073741637;
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v29 = "Non-FIDO key types are not currently supported";
      LODWORD(v28) = 4085;
    }
    v14 = HashString;
  }
  else
  {
    HashString = -1073741811;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v29 = "Invalid Arg(s)";
    LODWORD(v28) = 4077;
  }
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v13, v28, v29, &Class);
LABEL_42:
  DerefPackage(v31);
  if ( v9 )
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v9);
  FreePackedCreds(v33);
  if ( Src[0] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( Src[1] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  *(_OWORD *)Src = 0;
  v33 = 0;
  FreePackedCreds(v38);
  if ( lpSrcStr[0] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( lpSrcStr[1] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v38 = 0;
  *(_OWORD *)lpSrcStr = 0;
  FreeCloudAPCache(v10);
  if ( v11 )
    ((void (__fastcall *)(unsigned __int8 *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
  if ( v36 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return HashString;
}

```

## disassembly

```asm
0x180047c70  mov     [rsp-8+arg_8], rbx
0x180047c75  push    rbp
0x180047c76  push    rsi
0x180047c77  push    rdi
0x180047c78  push    r12
0x180047c7a  push    r13
0x180047c7c  push    r14
0x180047c7e  push    r15
0x180047c80  lea     rbp, [rsp-60h]
0x180047c85  sub     rsp, 160h
0x180047c8c  mov     rax, cs:__security_cookie
0x180047c93  xor     rax, rsp
0x180047c96  mov     [rbp+90h+var_40], rax
0x180047c9a  mov     rax, [rbp+90h+arg_30]
0x180047ca1  xor     r9d, r9d
0x180047ca4  mov     r15, [rbp+90h+arg_28]
0x180047cab  xorps   xmm0, xmm0
0x180047cae  mov     r13, rcx
0x180047cb1  mov     [rbp+90h+var_E8], rax
0x180047cb5  xor     ecx, ecx
0x180047cb7  mov     [rsp+190h+var_150], r9d
0x180047cbc  mov     rdi, r8
0x180047cbf  mov     [rsp+190h+var_130], rcx
0x180047cc4  mov     r8d, [rbp+90h+arg_20]
0x180047ccb  xorps   xmm1, xmm1
0x180047cce  mov     [r15], r9
0x180047cd1  mov     esi, r9d
0x180047cd4  mov     [rax], r9d
0x180047cd7  mov     r12d, r9d
0x180047cda  mov     [rbp+90h+var_100], rcx
0x180047cde  mov     r14d, r9d
0x180047ce1  mov     [rsp+190h+var_148], r9
0x180047ce6  mov     [rsp+190h+hMem], r9
0x180047ceb  mov     [rsp+190h+var_120], r9
0x180047cf0  mov     [rsp+190h+var_118], r9
0x180047cf5  movups  xmmword ptr [rbp+90h+var_F8.Length], xmm0
0x180047cf9  movups  xmmword ptr [rsp+190h+Src], xmm0
0x180047cfe  movups  xmmword ptr [rbp+90h+lpSrcStr], xmm1
0x180047d02  cmp     r8d, 28h ; '('
0x180047d06  jb      loc_180048247
0x180047d0c  test    rdi, rdi
0x180047d0f  jz      loc_180048247
0x180047d15  cmp     dword ptr [rdi+14h], 6
0x180047d19  jz      short loc_180047D57
0x180047d1b  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047d22  mov     ebx, 0C00000BBh
0x180047d27  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047d2c  mov     r9, rax
0x180047d2f  lea     rax, Class
0x180047d36  mov     [rsp+190h+var_160], rax
0x180047d3b  lea     rax, aNonFidoKeyType; "Non-FIDO key types are not currently su"...
0x180047d42  mov     [rsp+190h+var_168], rax
0x180047d47  mov     dword ptr [rsp+190h+var_170], 0FF5h
0x180047d4f  mov     r8d, ebx
0x180047d52  jmp     loc_18004827F
0x180047d57  mov     ecx, [rdi+1Ch]
0x180047d5a  mov     [rbp+90h+var_E0], 7
0x180047d61  test    ecx, ecx
0x180047d63  jz      loc_18004820D
0x180047d69  test    cl, 1
0x180047d6c  jnz     loc_18004820D
0x180047d72  mov     edx, [rdi+18h]
0x180047d75  add     edx, ecx
0x180047d77  cmp     edx, ecx
0x180047d79  jb      loc_18004820D
0x180047d7f  cmp     edx, r8d
0x180047d82  ja      loc_18004820D
0x180047d88  mov     ecx, [rdi+24h]
0x180047d8b  test    ecx, ecx
0x180047d8d  jz      short loc_180047DDA
0x180047d8f  mov     edx, [rdi+20h]
0x180047d92  add     edx, ecx
0x180047d94  cmp     edx, ecx
0x180047d96  jb      short loc_180047D9D
0x180047d98  cmp     edx, r8d
0x180047d9b  jbe     short loc_180047DDA
0x180047d9d  mov     r8d, 0C000000Dh
0x180047da3  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047daa  mov     ebx, r8d
0x180047dad  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047db2  mov     r9, rax
0x180047db5  lea     rax, Class
0x180047dbc  mov     [rsp+190h+var_160], rax
0x180047dc1  lea     rax, aInvalidCacheke; "invalid cachekey length"
0x180047dc8  mov     [rsp+190h+var_168], rax
0x180047dcd  mov     dword ptr [rsp+190h+var_170], 100Ch
0x180047dd5  jmp     loc_18004827F
0x180047dda  lea     rcx, [rdi+4]; struct _GUID *
0x180047dde  lea     rdx, [rsp+190h+var_148]; struct _ApPluginPkg **
0x180047de3  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180047de8  mov     ebx, eax
0x180047dea  test    eax, eax
0x180047dec  jz      short loc_180047E22
0x180047dee  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047df5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047dfa  mov     r9, rax
0x180047dfd  lea     rax, Class
0x180047e04  mov     [rsp+190h+var_160], rax
0x180047e09  lea     rax, aRefpackage; "RefPackage"
0x180047e10  mov     [rsp+190h+var_168], rax
0x180047e15  mov     dword ptr [rsp+190h+var_170], 1013h
0x180047e1d  jmp     loc_180047D4F
0x180047e22  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180047e29  mov     ebx, 1Ch
0x180047e2e  mov     ecx, ebx
0x180047e30  mov     rax, [rax+28h]
0x180047e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e39  mov     rsi, rax
0x180047e3c  xor     eax, eax
0x180047e3e  test    rsi, rsi
0x180047e41  jnz     short loc_180047E7C
0x180047e43  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047e4a  mov     ebx, 0C0000017h
0x180047e4f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047e54  mov     r9, rax
0x180047e57  lea     rax, Class
0x180047e5e  mov     [rsp+190h+var_160], rax
0x180047e63  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180047e6a  mov     [rsp+190h+var_168], rax
0x180047e6f  mov     dword ptr [rsp+190h+var_170], 101Eh
0x180047e77  jmp     loc_180047D4F
0x180047e7c  mov     dword ptr [rsi], 1C001Ch
0x180047e82  lea     rdx, [rsp+190h+Src]; unsigned __int16 **
0x180047e87  movups  xmm0, cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD
0x180047e8e  mov     [rsi+18h], ax
0x180047e92  lea     rcx, [rbp+90h+var_F8]; struct _UNICODE_STRING *
0x180047e96  mov     [rsi+14h], ebx
0x180047e99  movdqu  xmmword ptr [rsi+4], xmm0
0x180047e9e  mov     eax, [rdi+18h]
0x180047ea1  add     rax, rdi
0x180047ea4  mov     [rbp+90h+var_F8.Buffer], rax
0x180047ea8  movzx   eax, word ptr [rdi+1Ch]
0x180047eac  mov     [rbp+90h+var_F8.MaximumLength], ax
0x180047eb0  mov     [rbp+90h+var_F8.Length], ax
0x180047eb4  call    ?DuplicateUnicodeString4@@YAJPEAU_UNICODE_STRING@@PEAPEAG@Z; DuplicateUnicodeString4(_UNICODE_STRING *,ushort * *)
0x180047eb9  xor     edi, edi
0x180047ebb  mov     ebx, eax
0x180047ebd  test    eax, eax
0x180047ebf  jz      short loc_180047EF5
0x180047ec1  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047ec8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047ecd  mov     r9, rax
0x180047ed0  lea     rax, Class
0x180047ed7  mov     [rsp+190h+var_160], rax
0x180047edc  lea     rax, aDuplicateunico_5; "DuplicateUnicodeString4"
0x180047ee3  mov     [rsp+190h+var_168], rax
0x180047ee8  mov     dword ptr [rsp+190h+var_170], 102Bh
0x180047ef0  jmp     loc_180047D4F
0x180047ef5  mov     rcx, [rsp+190h+Src]; Src
0x180047efa  lea     r8, [rsp+190h+Src+8]; unsigned __int16 **
0x180047eff  mov     edx, 1; int
0x180047f04  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180047f09  mov     ebx, eax
0x180047f0b  test    eax, eax
0x180047f0d  jz      short loc_180047F43
0x180047f0f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047f16  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047f1b  mov     r9, rax
0x180047f1e  lea     rax, Class
0x180047f25  mov     [rsp+190h+var_160], rax
0x180047f2a  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x180047f31  mov     [rsp+190h+var_168], rax
0x180047f36  mov     dword ptr [rsp+190h+var_170], 1031h
0x180047f3e  jmp     loc_180047D4F
0x180047f43  mov     rdx, [rsp+190h+var_148]; struct _ApPluginPkg *
0x180047f48  lea     rax, [rsp+190h+var_118]
0x180047f4d  mov     [rsp+190h+var_160], rdi; struct _SCARD_PIN **
0x180047f52  lea     r9, [rsp+190h+Src]; struct _DECRYPTED_AUTH_DATA *
0x180047f57  mov     [rsp+190h+var_168], rax; unsigned __int16 **
0x180047f5c  xor     r8d, r8d; unsigned __int16 *
0x180047f5f  lea     rax, [rbp+90h+lpSrcStr]
0x180047f63  mov     [rsp+190h+var_130], rsi
0x180047f68  xor     ecx, ecx; bool
0x180047f6a  mov     [rsp+190h+var_170], rax; struct _DECRYPTED_AUTH_DATA *
0x180047f6f  mov     rsi, rdi
0x180047f72  call    ?ConvertAuthDataToAuthDataInt@@YAJ_NPEAU_ApPluginPkg@@PEBGPEAU_DECRYPTED_AUTH_DATA@@3PEAPEAGPEAPEAU_SCARD_PIN@@@Z; ConvertAuthDataToAuthDataInt(bool,_ApPluginPkg *,ushort const *,_DECRYPTED_AUTH_DATA *,_DECRYPTED_AUTH_DATA *,ushort * *,_SCARD_PIN * *)
0x180047f77  mov     ebx, eax
0x180047f79  test    eax, eax
0x180047f7b  jz      short loc_180047FB1
0x180047f7d  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047f84  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047f89  mov     r9, rax
0x180047f8c  lea     rax, Class
0x180047f93  mov     [rsp+190h+var_160], rax
0x180047f98  lea     rax, aConvertauthdat; "ConvertAuthDataToAuthDataInt"
0x180047f9f  mov     [rsp+190h+var_168], rax
0x180047fa4  mov     dword ptr [rsp+190h+var_170], 103Eh
0x180047fac  jmp     loc_180047D4F
0x180047fb1  mov     rcx, [rbp+90h+lpSrcStr+8]; lpSrcStr
0x180047fb5  lea     rdx, [rbp+90h+var_D0]; unsigned __int16 *
0x180047fb9  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x180047fbe  mov     ebx, eax
0x180047fc0  test    eax, eax
0x180047fc2  jz      short loc_180047FF8
0x180047fc4  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180047fcb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180047fd0  mov     r9, rax
0x180047fd3  lea     rax, Class
0x180047fda  mov     [rsp+190h+var_160], rax
0x180047fdf  lea     rax, aGethashstring; "GetHashString"
0x180047fe6  mov     [rsp+190h+var_168], rax
0x180047feb  mov     dword ptr [rsp+190h+var_170], 1041h
0x180047ff3  jmp     loc_180047D4F
0x180047ff8  mov     rcx, [rsp+190h+var_148]
0x180047ffd  lea     r9, [rsp+190h+hMem]; struct _CloudAPCache **
0x180048002  lea     r8, aPubliccachedat; "PublicCacheData"
0x180048009  lea     rdx, [rbp+90h+var_D0]; unsigned __int16 *
0x18004800d  mov     rcx, [rcx+158h]; unsigned __int16 *
0x180048014  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x180048019  mov     ebx, eax
0x18004801b  test    eax, eax
0x18004801d  jz      short loc_180048069
0x18004801f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180048026  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004802b  mov     r9, rax
0x18004802e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180048035  lea     rax, Class
0x18004803c  mov     r8d, ebx
0x18004803f  mov     [rsp+190h+var_160], rax
0x180048044  xor     ecx, ecx
0x180048046  lea     rax, aGetlogonpublic; "GetLogonPublicCacheForUser"
0x18004804d  mov     [rsp+190h+var_168], rax
0x180048052  mov     dword ptr [rsp+190h+var_170], 1047h
0x18004805a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004805f  mov     r12, [rsp+190h+hMem]
0x180048064  jmp     loc_18004828D
0x180048069  mov     rcx, [rsp+190h+Src+8]
0x18004806e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048072  inc     rax
0x180048075  cmp     [rcx+rax*2], di
0x180048079  jnz     short loc_180048072
0x18004807b  mov     r12, [rsp+190h+hMem]
0x180048080  lea     r9, [rsp+190h+var_150]; unsigned int *
0x180048085  add     eax, eax
0x180048087  mov     [rbp+90h+var_D8], rcx
0x18004808b  mov     rcx, r12; struct _CloudAPCache *
0x18004808e  mov     [rbp+90h+var_DC], eax
0x180048091  lea     r8, [rsp+190h+var_120]; unsigned __int8 **
0x180048096  lea     rdx, [rbp+90h+var_E0]; struct _tagCacheNodeIdentifier *
0x18004809a  call    ?GetRawCacheNode@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAPEAEPEAK@Z; GetRawCacheNode(_CloudAPCache *,_tagCacheNodeIdentifier *,uchar * *,ulong *)
0x18004809f  mov     ebx, eax
0x1800480a1  test    eax, eax
0x1800480a3  jz      short loc_1800480EF
0x1800480a5  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x1800480ac  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800480b1  mov     r9, rax
0x1800480b4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800480bb  lea     rax, Class
0x1800480c2  mov     r8d, ebx
0x1800480c5  mov     [rsp+190h+var_160], rax
0x1800480ca  xor     ecx, ecx
0x1800480cc  lea     rax, aGetrawcachenod; "GetRawCacheNode"
0x1800480d3  mov     [rsp+190h+var_168], rax
0x1800480d8  mov     dword ptr [rsp+190h+var_170], 1056h
0x1800480e0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800480e5  mov     r14, [rsp+190h+var_120]
0x1800480ea  jmp     loc_18004828D
0x1800480ef  mov     r14, [rsp+190h+var_120]
0x1800480f4  mov     edi, [rsp+190h+var_150]
0x1800480f8  mov     rcx, r14; unsigned __int8 *
0x1800480fb  mov     edx, edi; unsigned int
0x1800480fd  call    ?FIDOValidatePublicCacheData@@YAJPEAEK@Z; FIDOValidatePublicCacheData(uchar *,ulong)
0x180048102  mov     ebx, eax
0x180048104  test    eax, eax
0x180048106  jz      short loc_18004813C
0x180048108  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004810f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048114  mov     r9, rax
0x180048117  lea     rax, Class
0x18004811e  mov     [rsp+190h+var_160], rax
0x180048123  lea     rax, aFidovalidatepu; "FIDOValidatePublicCacheData"
0x18004812a  mov     [rsp+190h+var_168], rax
0x18004812f  mov     dword ptr [rsp+190h+var_170], 105Bh
0x180048137  jmp     loc_180047D4F
0x18004813c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180048143  mov     r8, r15
0x180048146  mov     edx, edi
0x180048148  mov     rcx, r13
0x18004814b  mov     rax, [rax+38h]
0x18004814f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048154  mov     ebx, eax
0x180048156  test    eax, eax
0x180048158  jz      short loc_18004818E
0x18004815a  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180048161  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180048166  mov     r9, rax
0x180048169  lea     rax, Class
0x180048170  mov     [rsp+190h+var_160], rax
0x180048175  lea     rax, aAllocateclient; "AllocateClientBuffer"
0x18004817c  mov     [rsp+190h+var_168], rax
0x180048181  mov     dword ptr [rsp+190h+var_170], 1062h
0x180048189  jmp     loc_180047D4F
0x18004818e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180048195  mov     r9, r14
0x180048198  mov     r8, [r15]
0x18004819b  mov     edx, edi
0x18004819d  mov     rcx, r13
0x1800481a0  mov     rax, [rax+48h]
0x1800481a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481a9  mov     ebx, eax
  ... truncated ...
```
