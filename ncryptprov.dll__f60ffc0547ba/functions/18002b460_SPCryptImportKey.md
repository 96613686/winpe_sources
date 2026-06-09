# SPCryptImportKey

- ea: `0x18002b460`
- end: `0x18002c7a2`
- name: `SPCryptImportKey`
- size: `4930`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, __int64, _QWORD *, void *Src, DWORD cbInput, unsigned int)`
- caller_count: `0`
- callee_count: `40`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004400`
- `0x180005290`
- `0x180006e80`
- `0x1800096e0`
- `0x180009f60`
- `0x18000af80`
- `0x18000afd0`
- `0x18000d3d0`
- `0x18000dab0`
- `0x18000eb0c`
- `0x1800115b0`
- `0x180014160`
- `0x180017580`
- `0x180017a80`
- `0x1800194d0`
- `0x180019d90`
- `0x180019dd0`
- `0x180019ed0`
- `0x18001a564`
- `0x18001b634`
- `0x180023338`
- `0x1800248ac`
- `0x180027778`
- `0x180028114`
- `0x180028a70`
- `0x180029004`
- `0x18002b460`
- `0x180033a10`
- `0x1800362fc`
- `0x1800489c8`
- `0x1800491d4`
- `0x18004d354`
- `0x18005100c`
- `0x1800523f4`
- `0x18005b338`
- `0x18005bbcc`
- `0x18005d3f4`
- `0x18005e958`
- `0x1800622e0`
- `0x180062310`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18002c773`
- `ntdll!RtlReleaseResource` at `0x18002c773`
- `ntdll!RtlDllShutdownInProgress` at `0x18002bb41`
- `ntdll!RtlDllShutdownInProgress` at `0x18002bb41`
- `bcrypt!BCryptImportKeyPair` at `0x18002c68a`
- `bcrypt!BCryptImportKeyPair` at `0x18002c68a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002c759`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002c759`
- `bcrypt!BCryptGetProperty` at `0x18002b7d2`
- `bcrypt!BCryptGetProperty` at `0x18002b7d2`

## string_xrefs

- `0x18002b506`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002c6d4`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002bb19`: `COMPMLKEMPUBLICBLOB`
- `0x18002ba12`: `COMPMLKEMPRIVATELAMPSBLOB`
- `0x18002baeb`: `COMPMLKEMPRIVATELAMPSBLOB`
- `0x18002ba25`: `COMPMLKEMPRIVATEIRTFSEEDBLOB`
- `0x18002bb02`: `COMPMLKEMPRIVATEIRTFSEEDBLOB`

## pseudocode

```c
__int64 __fastcall SPCryptImportKey(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        __int64 a4,
        _QWORD *a5,
        void *Src,
        DWORD cbInput,
        unsigned int a8)
{
  _QWORD *v8; // r12
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rcx
  PVOID *v14; // rdx
  __int64 v15; // r14
  __int64 v16; // rdi
  int v17; // ebx
  BOOL v18; // esi
  unsigned int v19; // edi
  int v20; // edi
  int UserStorageArea; // eax
  __int64 v22; // r9
  __int64 v23; // rcx
  _DWORD *v24; // rcx
  _DWORD *v25; // rcx
  NTSTATUS Property; // eax
  void *v27; // r14
  __int64 v28; // r8
  UCHAR *v29; // r9
  __int64 v30; // rsi
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // ecx
  __int64 v34; // rsi
  unsigned int v35; // edi
  unsigned int v36; // eax
  bool v37; // zf
  __int64 v38; // rdx
  int *v39; // rcx
  int v40; // edi
  __int64 v41; // rsi
  __int64 v42; // rdx
  __int64 v43; // r8
  unsigned int v44; // eax
  void *v45; // rax
  BCRYPT_KEY_HANDLE *v46; // r9
  BCRYPT_ALG_HANDLE v47; // rcx
  ULONG *pcbResult; // [rsp+20h] [rbp-E0h]
  ULONG dwFlags[2]; // [rsp+28h] [rbp-D8h]
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  void *v52; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v53; // [rsp+70h] [rbp-90h]
  int v54[2]; // [rsp+78h] [rbp-88h]
  int v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+84h] [rbp-7Ch] BYREF
  int v57; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v58; // [rsp+8Ch] [rbp-74h] BYREF
  ULONG KGRunningInProdMode; // [rsp+90h] [rbp-70h] BYREF
  int v60[2]; // [rsp+98h] [rbp-68h]
  void *v61; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h] BYREF
  int v63; // [rsp+B0h] [rbp-50h] BYREF
  int v64; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v65; // [rsp+B8h] [rbp-48h]
  __int64 v66; // [rsp+C0h] [rbp-40h] BYREF
  int *v67; // [rsp+C8h] [rbp-38h] BYREF
  int v68[2]; // [rsp+D0h] [rbp-30h] BYREF
  PUCHAR pbInput; // [rsp+D8h] [rbp-28h] BYREF
  ULONG v70; // [rsp+E0h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+E8h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v72; // [rsp+F0h] [rbp-10h] BYREF
  PUCHAR *p_pbInput; // [rsp+110h] [rbp+10h]
  __int64 v74; // [rsp+118h] [rbp+18h]
  int *v75; // [rsp+120h] [rbp+20h]
  __int64 v76; // [rsp+128h] [rbp+28h]
  __int64 *v77; // [rsp+130h] [rbp+30h]
  __int64 v78; // [rsp+138h] [rbp+38h]
  ULONG *p_KGRunningInProdMode; // [rsp+140h] [rbp+40h]
  __int64 v80; // [rsp+148h] [rbp+48h]
  __int64 *v81; // [rsp+150h] [rbp+50h]
  __int64 v82; // [rsp+158h] [rbp+58h]

  v8 = a5;
  v52 = 0;
  v70 = 0;
  v56 = 0;
  v65 = 0;
  v62 = 0;
  v58 = 0;
  v57 = 0;
  v67 = 0;
  v55 = 0;
  v66 = 0;
  hAlgorithm = 0;
  v51 = 0;
  v63 = 0;
  v64 = 0;
  LODWORD(v61) = 0;
  *(_QWORD *)v60 = a4;
  *(_QWORD *)v68 = a1;
  v53 = a5;
  pbInput = (PUCHAR)Src;
  *(_QWORD *)v54 = KspValidateAndLockProvider(a1, 0);
  if ( *(_QWORD *)v54 )
  {
    if ( !a5 )
    {
      v11 = 4160;
LABEL_7:
      v12 = -2146893785;
      v13 = 2148073511LL;
      goto LABEL_4;
    }
    if ( !Src || !cbInput )
    {
      v12 = -2146893785;
      v23 = 2148073511LL;
      v22 = 4167;
      goto LABEL_283;
    }
    if ( (a8 & 0xFFF89917) != 0 )
    {
      v11 = 4180;
LABEL_12:
      v12 = -2146893815;
      v13 = 2148073481LL;
      goto LABEL_4;
    }
    LODWORD(v16) = 0;
    if ( a2 )
    {
      v16 = KspValidateKeyHandle(a2);
      if ( !v16 )
      {
        v11 = 4190;
        goto LABEL_3;
      }
      if ( !wcscmp_0(a3, L"ISOLATED_KEY_ENVELOPE") )
      {
        if ( !*(_DWORD *)(v16 + 144) )
        {
          v11 = 4199;
LABEL_19:
          v12 = -2146893783;
          v13 = 2148073513LL;
          goto LABEL_4;
        }
        if ( (*(_BYTE *)(v16 + 40) & 8) == 0 )
        {
          v11 = 4206;
LABEL_22:
          v12 = -2146893808;
          v13 = 2148073488LL;
          goto LABEL_4;
        }
      }
      else if ( !wcscmp_0(a3, L"PKCS11RsaAesWrapBlob") && (*(_DWORD *)(v16 + 40) & 0x28) == 0 )
      {
        v11 = 4215;
        goto LABEL_12;
      }
    }
    v17 = *(_DWORD *)(*(_QWORD *)v54 + 48LL);
    if ( v17 && (a8 & 0x20) != 0 )
    {
      v11 = 4230;
      goto LABEL_22;
    }
    KGRunningInProdMode = a8 & 8;
    if ( wcscmp_0(a3, L"PUBLICBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") )
    {
      v18 = 0;
      if ( !wcscmp_0(a3, L"RSAPUBLICBLOB") )
      {
LABEL_32:
        v19 = 196609;
        goto LABEL_86;
      }
      if ( !wcscmp_0(a3, L"DSAPUBLICBLOB") )
        goto LABEL_34;
      if ( !wcscmp_0(a3, L"DHPUBLICBLOB") )
        goto LABEL_36;
      if ( wcscmp_0(a3, L"ECCPUBLICBLOB")
        && wcscmp_0(a3, L"ECCPRIVATEBLOB")
        && wcscmp_0(a3, L"ECCFULLPUBLICBLOB")
        && wcscmp_0(a3, L"ECCFULLPRIVATEBLOB") )
      {
        if ( !wcscmp_0(a3, L"CipherKeyBlob") )
        {
          v20 = 1;
LABEL_45:
          UserStorageArea = KspImportCipherOrKDFBlob(v54[0], (unsigned int)&v52, v60[0], (_DWORD)Src, cbInput, a8);
          v12 = UserStorageArea;
          if ( UserStorageArea )
          {
            v22 = 4650;
LABEL_47:
            v8 = v53;
            v23 = (unsigned int)UserStorageArea;
LABEL_283:
            v15 = v51;
LABEL_284:
            DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v22);
            if ( v12 )
            {
              if ( v12 == -2146893778 )
                goto LABEL_289;
              goto LABEL_287;
            }
LABEL_285:
            KspCryptAuditKeyMigrationOperation(1, (_DWORD)v14, *v8, 2465, 0);
            goto LABEL_289;
          }
          v15 = v51;
          if ( v20 || v18 )
            goto LABEL_266;
LABEL_50:
          v24 = v52;
LABEL_51:
          v24[7] = 0;
          v25 = v52;
          if ( !*(_DWORD *)(*((_QWORD *)v52 + 8) + 96LL) )
          {
LABEL_265:
            v25[11] = (a8 & 0x400) == 0;
            goto LABEL_266;
          }
          Property = BCryptGetProperty(*((BCRYPT_HANDLE *)v52 + 13), L"KeyStrength", (PUCHAR)v52 + 28, 4u, &v70, 0);
          v12 = Property;
          if ( !Property )
            goto LABEL_281;
          v22 = 5236;
LABEL_106:
          v8 = v53;
          v23 = (unsigned int)Property;
          goto LABEL_284;
        }
        if ( !wcscmp_0(a3, L"KDFKeyBlob") )
        {
          v20 = 0;
          v18 = 1;
          goto LABEL_45;
        }
        if ( !wcscmp_0(a3, L"OpaqueTransport") )
        {
          if ( (a8 & 0x70000) != 0 )
          {
            v11 = 4971;
            goto LABEL_12;
          }
          v30 = *(_QWORD *)v54;
          UserStorageArea = InitializeNewKeyObject(
                              0,
                              0,
                              a8,
                              v17,
                              *(_DWORD *)(*(_QWORD *)v54 + 52LL),
                              *(_DWORD *)(*(_QWORD *)v54 + 56LL),
                              *(_DWORD *)(*(_QWORD *)v54 + 60LL),
                              *(void **)(*(_QWORD *)v54 + 40LL),
                              (__int64)&v52);
          v12 = UserStorageArea;
          if ( UserStorageArea )
          {
            v22 = 4989;
            goto LABEL_47;
          }
          UserStorageArea = GetUserStorageArea(
                              *((unsigned int *)v52 + 8),
                              v31,
                              *((unsigned int *)v52 + 132),
                              *(_QWORD *)(v30 + 40),
                              (char *)v52 + 72);
          v12 = UserStorageArea;
          if ( UserStorageArea )
          {
            v22 = 5002;
            goto LABEL_47;
          }
          UserStorageArea = KspProcessOpaqueBlob(v32, v52, Src, cbInput);
          v12 = UserStorageArea;
          if ( UserStorageArea )
          {
            v22 = 5014;
            goto LABEL_47;
          }
          Property = KspReadKey(
                       v30,
                       0,
                       *((_QWORD *)v52 + 9),
                       (unsigned int)&v61,
                       (__int64)&v64,
                       (__int64)&v57,
                       (__int64)&v51,
                       (__int64)&v63,
                       (__int64)v52);
          v15 = v51;
          v12 = Property;
          if ( Property )
          {
            v22 = 5032;
            goto LABEL_106;
          }
          Property = KspParseKey(v33, (_DWORD)v61, v64, v57, v51, v63, (__int64)v52);
          v12 = Property;
          if ( Property )
          {
            v22 = 5048;
            goto LABEL_106;
          }
          Property = CheckIfLegacyStorageRequired(v52, a8, &v56);
          v12 = Property;
          if ( Property )
          {
            v22 = 5058;
            goto LABEL_106;
          }
          if ( !v56 )
            goto LABEL_51;
          if ( (unsigned int)ReadLegacyKeyFile(v30, v24, 0, *((_QWORD *)v24 + 9), &v57, &v62, &v58) )
          {
            v34 = 0;
            v35 = 0;
          }
          else
          {
            v34 = v62;
            v35 = v58;
          }
          v65 = v34;
          Property = KspCheckStrongKeyAndUnprotect(v52, a8);
          v12 = Property;
          if ( Property < 0 )
          {
            v22 = 5095;
            goto LABEL_106;
          }
          v24 = v52;
          if ( *(_DWORD *)(*((_QWORD *)v52 + 8) + 32LL) == 196609 )
          {
            v36 = WriteRsaKeyToLegacyStore(v52, v34, v35);
            if ( v36 )
            {
              v14 = &WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids, v36);
            }
          }
          else
          {
            v14 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_51;
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids);
          }
          goto LABEL_50;
        }
        if ( !wcscmp_0(a3, L"ProtectedKeyBlob") )
        {
          Property = KspImportProtectedBlob(v54[0], (unsigned int)&v52, v60[0], (_DWORD)Src, cbInput, a8);
          v15 = v51;
          v12 = Property;
          if ( Property )
          {
            v22 = 4666;
            goto LABEL_106;
          }
        }
        else if ( !wcscmp_0(a3, L"PKCS7_ENVELOPE") )
        {
          Property = KspImportPKCS7Blob(*(_QWORD *)v54, &v52, *(_QWORD *)v60, Src, cbInput, a8);
          v15 = v51;
          v12 = Property;
          if ( Property )
          {
            v22 = 4682;
            goto LABEL_106;
          }
        }
        else if ( !wcscmp_0(a3, L"PKCS8_PRIVATEKEY") )
        {
          Property = SPPkcs8ImportKey(v68[0], (int)&v52, v60[0], (int)Src, cbInput, a8);
          v15 = v51;
          v12 = Property;
          if ( Property < 0 )
          {
            v22 = 4699;
            goto LABEL_106;
          }
        }
        else
        {
          if ( !wcscmp_0(a3, L"RSAPRIVATEBLOB")
            || !wcscmp_0(a3, L"RSAFULLPRIVATEBLOB")
            || !wcscmp_0(a3, L"CAPIPRIVATEBLOB") )
          {
            v19 = 196609;
            goto LABEL_83;
          }
          if ( !wcscmp_0(a3, L"DSAPRIVATEBLOB")
            || !wcscmp_0(a3, L"CAPIDSAPRIVATEBLOB")
            || !wcscmp_0(a3, L"V2CAPIDSAPRIVATEBLOB") )
          {
            v19 = 196611;
            goto LABEL_83;
          }
          if ( !wcscmp_0(a3, L"DHPRIVATEBLOB") || !wcscmp_0(a3, L"CAPIDHPRIVATEBLOB") )
          {
            v19 = 196610;
            goto LABEL_83;
          }
          if ( wcscmp_0(a3, L"ISOLATED_KEY_ENVELOPE") )
          {
            if ( !wcscmp_0(a3, L"PKCS11RsaAesWrapBlob") )
            {
              if ( !RtlDllShutdownInProgress()
                && dword_1800790F0
                && (unsigned __int8)tlgKeywordOn(&dword_1800790F0, 0x800000000000LL, v28, 0) )
              {
                pbInput = v29;
                p_pbInput = &pbInput;
                v74 = 8;
                v75 = v68;
                v77 = &v66;
                *(_QWORD *)v68 = v29;
                v76 = 8;
                v66 = 1;
                v78 = 8;
                KGRunningInProdMode = BCryptIsoGetKGRunningInProdMode(&g_VbsRegistryData);
                v80 = 4;
                p_KGRunningInProdMode = &KGRunningInProdMode;
                v62 = 2048;
                v81 = &v62;
                v82 = 8;
                tlgWriteAgg((int)&dword_1800790F0, (int)&byte_180070427, 0, 7, &v72);
              }
              dwFlags[0] = cbInput;
              Property = SPPkcs11ImportKey(v54[0], v16, (int)&v52, v60[0], Src, *(size_t *)dwFlags, a8);
              v15 = v51;
              v12 = Property;
              if ( Property >= 0 )
                goto LABEL_266;
              v22 = 4735;
              goto LABEL_106;
            }
            if ( !wcscmp_0(a3, L"PQDSAPRIVATEBLOB") || !wcscmp_0(a3, L"PQDSAPRIVATESEEDBLOB") )
              goto LABEL_91;
            if ( !wcscmp_0(a3, L"PQDSAPUBLICBLOB") )
            {
LABEL_71:
              v19 = 196620;
              goto LABEL_86;
            }
            if ( !wcscmp_0(a3, L"PQPrivateKeyBlob") )
            {
              LODWORD(v61) = 0;
              UserStorageArea = GetPqBlobLength(Src, cbInput, &v61);
              v12 = UserStorageArea;
              if ( UserStorageArea )
              {
                v22 = 4578;
                goto LABEL_47;
              }
              if ( wcscmp_0((const wchar_t *)Src + 6, L"PQDSAPRIVATEBLOB")
                && wcscmp_0((const wchar_t *)Src + 6, L"PQDSAPRIVATESEEDBLOB") )
              {
                if ( wcscmp_0((const wchar_t *)Src + 6, L"MLKEMPRIVATEBLOB")
                  && wcscmp_0((const wchar_t *)Src + 6, L"MLKEMPRIVATESEEDBLOB") )
                {
                  if ( wcscmp_0((const wchar_t *)Src + 6, L"COMPMLKEMPRIVATELAMPSBLOB")
                    && wcscmp_0((const wchar_t *)Src + 6, L"COMPMLKEMPRIVATEIRTFSEEDBLOB") )
                  {
                    v11 = 4606;
                    goto LABEL_19;
                  }
                  goto LABEL_82;
                }
                goto LABEL_84;
              }
LABEL_91:
              v19 = 196620;
              goto LABEL_83;
            }
            if ( !wcscmp_0(a3, L"MLKEMPRIVATEBLOB") || !wcscmp_0(a3, L"MLKEMPRIVATESEEDBLOB") )
            {
LABEL_84:
              v18 = 1;
LABEL_85:
              v19 = 458753;
              goto LABEL_86;
            }
            if ( !wcscmp_0(a3, L"MLKEMPUBLICBLOB") )
              goto LABEL_85;
            if ( !wcscmp_0(a3, L"COMPMLKEMPRIVATELAMPSBLOB") || !wcscmp_0(a3, L"COMPMLKEMPRIVATEIRTFSEEDBLOB") )
            {
LABEL_82:
              v19 = 458754;
LABEL_83:
              v18 = 1;
              goto LABEL_86;
            }
            if ( wcscmp_0(a3, L"COMPMLKEMPUBLICBLOB") )
            {
              v11 = 4634;
              goto LABEL_19;
            }
            goto LABEL_98;
          }
          dwFlags[0] = cbInput;
          Property = SPImportIsolatedKey(v54[0], v16, (int)&v52, v60[0], Src, *(size_t *)dwFlags, a8);
          v15 = v51;
          v12 = Property;
          if ( Property < 0 )
          {
            v22 = 4716;
            goto LABEL_106;
          }
        }
LABEL_266:
        v45 = v52;
        v12 = 0;
        v8 = v53;
        v52 = 0;
        *v53 = v45;
        goto LABEL_285;
      }
      if ( cbInput < 4 )
      {
        v11 = 4420;
        goto LABEL_7;
      }
      if ( !wcscmp_0(a3, L"ECCPRIVATEBLOB") || !wcscmp_0(a3, L"ECCFULLPRIVATEBLOB") )
        v18 = 1;
      if ( *(_DWORD *)Src <= 0x354B4345u )
      {
        if ( *(_DWORD *)Src != 894124869 )
        {
          if ( *(_DWORD *)Src == 827016005 )
            goto LABEL_163;
          if ( *(_DWORD *)Src != 827540293 )
          {
            if ( *(_DWORD *)Src != 843793221 )
            {
              if ( *(_DWORD *)Src != 844317509 )
              {
                if ( *(_DWORD *)Src != 860570437 )
                {
                  if ( *(_DWORD *)Src == 861094725 )
                  {
LABEL_161:
                    v19 = 196613;
                    goto LABEL_86;
                  }
                  if ( *(_DWORD *)Src != 877347653 )
                  {
                    if ( *(_DWORD *)Src == 877871941 )
                      goto LABEL_161;
LABEL_173:
                    v11 = 4502;
                    goto LABEL_7;
                  }
                }
                goto LABEL_162;
              }
              goto LABEL_164;
            }
LABEL_163:
            v19 = 196615;
            goto LABEL_86;
          }
LABEL_164:
          v19 = 196612;
          goto LABEL_86;
        }
        goto LABEL_165;
      }
      if ( *(_DWORD *)Src == 894649157 )
        goto LABEL_176;
      if ( *(_DWORD *)Src != 910902085 )
      {
        if ( *(_DWORD *)Src != 911426373 )
        {
          if ( *(_DWORD *)Src != 1346650949 )
          {
            if ( *(_DWORD *)Src != 1347109701 )
            {
              if ( *(_DWORD *)Src != 1447314245 )
              {
                if ( *(_DWORD *)Src != 1447772997 )
                  goto LABEL_173;
                goto LABEL_174;
              }
              goto LABEL_175;
            }
LABEL_174:
            v19 = 196618;
            goto LABEL_86;
          }
LABEL_175:
          v19 = 196619;
          goto LABEL_86;
        }
LABEL_176:
        v19 = 196614;
LABEL_86:
        v27 = 0;
        v61 = 0;
        if ( (a8 & 0x2000) != 0 )
        {
          if ( v19 - 196612 <= 2 )
          {
            v19 = 196619;
          }
          else if ( v19 - 196615 <= 2 )
          {
            v19 = 196618;
          }
          else if ( v19 - 196618 > 1 )
          {
            v11 = 4765;
            goto LABEL_12;
          }
        }
        if ( v18 )
        {
          UserStorageArea = KspGetKeyNameFromParameters(*(_QWORD *)v60, &v61);
          v12 = UserStorageArea;
          if ( UserStorageArea < 0 )
          {
            v22 = 4781;
            goto LABEL_47;
          }
          v27 = v61;
        }
        if ( !KspFindSupportedAlgById(v19) )
        {
          v11 = 4794;
          goto LABEL_19;
        }
        UserStorageArea = CreateNewKeyObject(v27, a8, (__int64)&v52);
        v12 = UserStorageArea;
        if ( UserStorageArea )
        {
          v22 = 4808;
          goto LABEL_47;
        }
        if ( v19 - 196618 > 1 )
        {
          v40 = v55;
        }
        else
        {
          UserStorageArea = KspGetCurveFromParameters(*(_QWORD *)v60, &v67, &v55, &v66);
          v12 = UserStorageArea;
          if ( UserStorageArea )
          {
            v22 = 4838;
            goto LABEL_47;
          }
          v39 = v67;
          v40 = v55;
          if ( !v67 )
          {
LABEL_237:
            if ( v18 )
            {
              v41 = *(_QWORD *)v54;
              if ( v27 )
              {
                UserStorageArea = GetUserStorageArea(
                                    *((unsigned int *)v52 + 8),
                                    v38,
                                    *((unsigned int *)v52 + 132),
                                    *(_QWORD *)(*(_QWORD *)v54 + 40LL),
                                    (char *)v52 + 72);
                v12 = UserStorageArea;
                if ( UserStorageArea )
                {
                  v22 = 4878;
                  goto LABEL_47;
                }
                if ( (a8 & 0x80u) == 0 )
                {
                  UserStorageArea = KspCheckKeyDoesNotExist(v52);
                  v12 = UserStorageArea;
                  if ( UserStorageArea )
                  {
                    v22 = 4893;
                    goto LABEL_47;
                  }
                }
              }
              if ( (unsigned int)SetPrivateKeyProperty((__int64)v52, a3, (__int64)pbInput, cbInput) )
              {
                v11 = 4910;
                goto LABEL_19;
              }
              if ( (a8 & 0x400) == 0 )
              {
                if ( (unsigned int)ImportKey(v52, KGRunningInProdMode) )
                {
                  v11 = 5138;
                  goto LABEL_19;
                }
                UserStorageArea = CheckIfLegacyStorageRequired(v52, a8, &v56);
                v12 = UserStorageArea;
                if ( UserStorageArea < 0 )
                {
                  v22 = 5148;
                  goto LABEL_47;
                }
                if ( v25[142] )
                  goto LABEL_264;
                UserStorageArea = WriteKeyToStore(v25, 1, 5);
                v12 = UserStorageArea;
                if ( UserStorageArea )
                {
                  v22 = 5166;
                  goto LABEL_47;
                }
                if ( v56 )
                {
                  if ( (unsigned int)ReadLegacyKeyFile(v41, v52, 0, *((_QWORD *)v52 + 9), &v57, &v62, &v58) )
                  {
                    v42 = 0;
                    v43 = 0;
                  }
                  else
                  {
                    v42 = v62;
                    v43 = v58;
                  }
                  v25 = v52;
                  v65 = v42;
                  if ( *(_DWORD *)(*((_QWORD *)v52 + 8) + 32LL) != 196609 )
                  {
                    v14 = &WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                      goto LABEL_264;
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids);
LABEL_263:
                    v25 = v52;
LABEL_264:
                    v15 = v51;
                    goto LABEL_265;
                  }
                  v44 = WriteRsaKeyToLegacyStore(v52, v42, v43);
                  if ( v44 )
                  {
                    v14 = &WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        27,
                        &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids,
                        v44);
                      goto LABEL_263;
                    }
                  }
                }
              }
              v15 = v51;
LABEL_281:
              v25 = v52;
              goto LABEL_265;
            }
            if ( (a8 & 0x706A0) != 0 )
            {
              v11 = 4926;
              goto LABEL_12;
            }
            if ( !v39 )
              goto LABEL_277;
            UserStorageArea = OpenAndSetPropertyOnBCryptHandle(
                                (unsigned int)&hAlgorithm,
                                **((_QWORD **)v52 + 8),
                                v66,
                                (_DWORD)v39,
                                v40,
                                0);
            v12 = UserStorageArea;
            if ( UserStorageArea )
            {
              v22 = 4939;
              goto LABEL_47;
            }
            if ( hAlgorithm )
            {
              v46 = (BCRYPT_KEY_HANDLE *)v52;
              v47 = hAlgorithm;
            }
            else
            {
LABEL_277:
              v46 = (BCRYPT_KEY_HANDLE *)v52;
              v47 = (BCRYPT_ALG_HANDLE)*((_QWORD *)v52 + 11);
            }
            Property = BCryptImportKeyPair(v47, 0, a3, v46 + 13, pbInput, cbInput, KGRunningInProdMode);
            v15 = v51;
            v12 = Property;
            if ( Property )
            {
              v22 = 4955;
              goto LABEL_106;
            }
            goto LABEL_50;
          }
          LODWORD(pcbResult) = v55;
          UserStorageArea = SPCryptSetKeyProperty(
                              *(__int64 *)v68,
                              (__int64)v52,
                              v66,
                              v67,
                              (size_t)pcbResult,
                              0x80000000);
          v12 = UserStorageArea;
          if ( UserStorageArea )
          {
            v22 = 4853;
            goto LABEL_47;
          }
        }
        v39 = v67;
        goto LABEL_237;
      }
      goto LABEL_165;
    }
    if ( cbInput < 4 )
    {
      v11 = 4253;
      goto LABEL_7;
    }
    v18 = wcscmp_0(a3, L"PRIVATEBLOB") == 0;
    if ( *(_DWORD *)Src <= 0x42504844u )
    {
      if ( *(_DWORD *)Src != 1112557636 )
      {
        if ( *(_DWORD *)Src <= 0x334B4345u )
        {
          if ( *(_DWORD *)Src != 860570437 )
          {
            switch ( *(_DWORD *)Src )
            {
              case 0x31415352:
                goto LABEL_32;
              case 0x314B4345:
                goto LABEL_163;
              case 0x31534345:
                goto LABEL_164;
              case 0x32415352:
                goto LABEL_32;
              case 0x32425044:
                goto LABEL_34;
              case 0x324B4345:
                goto LABEL_163;
              case 0x32534345:
                goto LABEL_164;
            }
            v37 = *(_DWORD *)Src == 844517444;
LABEL_217:
            if ( !v37 )
              goto LABEL_218;
LABEL_34:
            v19 = 196611;
            goto LABEL_86;
          }
LABEL_162:
          v19 = 196616;
          goto LABEL_86;
        }
        switch ( *(_DWORD *)Src )
        {
          case 0x33534345:
            goto LABEL_161;
          case 0x344B4345:
            goto LABEL_162;
          case 0x34534345:
            goto LABEL_161;
          case 0x354B4345:
            goto LABEL_165;
          case 0x35534345:
            goto LABEL_176;
          case 0x364B4345:
LABEL_165:
            v19 = 196617;
            goto LABEL_86;
          case 0x36534345:
            goto LABEL_176;
        }
LABEL_218:
        v11 = 4395;
        goto LABEL_7;
      }
LABEL_36:
      v19 = 196610;
      goto LABEL_86;
    }
    if ( *(_DWORD *)Src > 0x524B4D43u )
    {
      if ( *(_DWORD *)Src == 1397443661 )
        goto LABEL_85;
      if ( *(_DWORD *)Src != 1397443907 )
      {
        switch ( *(_DWORD *)Src )
        {
          case 0x53535344:
            goto LABEL_71;
          case 0x56444345:
            goto LABEL_175;
          case 0x564B4345:
            goto LABEL_174;
        }
        if ( *(_DWORD *)Src != 1448101956 )
        {
          v37 = *(_DWORD *)Src == 1448104772;
          goto LABEL_217;
        }
        goto LABEL_36;
      }
    }
    else if ( *(_DWORD *)Src != 1380666691 )
    {
      switch ( *(_DWORD *)Src )
      {
        case 0x42505344:
          goto LABEL_34;
        case 0x4B505344:
        case 0x4B535344:
          goto LABEL_71;
        case 0x50444345:
          goto LABEL_175;
        case 0x504B4345:
          goto LABEL_174;
        case 0x504B4C4D:
          goto LABEL_85;
      }
      if ( *(_DWORD *)Src != 1347112259 )
      {
        if ( *(_DWORD *)Src == 1380666445 )
          goto LABEL_85;
        goto LABEL_218;
      }
    }
LABEL_98:
    v19 = 458754;
    goto LABEL_86;
  }
  v11 = 4153;
LABEL_3:
  v12 = -2146893786;
  v13 = 2148073510LL;
LABEL_4:
  DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v11);
  v15 = v51;
LABEL_287:
  if ( v52 )
    KspCryptAuditKeyMigrationOperation(0, (_DWORD)v14, (_DWORD)v52, 2465, v12);
LABEL_289:
  if ( v65 )
    ((void (*)(void))MSCryptFree)();
  if ( v15 )
    MSCryptFree(v15);
  if ( v52 )
    DeleteKeyObject(v52);
  if ( hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( *(_QWORD *)v54 )
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)v54 + 64LL));
  return v12;
}

```

## disassembly

```asm
0x18002b460  push    rbp
0x18002b462  push    rbx
0x18002b463  push    rsi
0x18002b464  push    rdi
0x18002b465  push    r12
0x18002b467  push    r13
0x18002b469  push    r14
0x18002b46b  push    r15
0x18002b46d  lea     rbp, [rsp-78h]
0x18002b472  sub     rsp, 178h
0x18002b479  mov     rax, cs:__security_cookie
0x18002b480  xor     rax, rsp
0x18002b483  mov     [rbp+0B0h+var_50], rax
0x18002b487  mov     r12, [rbp+0B0h+arg_20]
0x18002b48e  mov     rbx, rdx
0x18002b491  mov     r14, [rbp+0B0h+Src]
0x18002b498  xor     edx, edx
0x18002b49a  mov     [rsp+1B0h+var_148], rdx
0x18002b49f  mov     r15, r8
0x18002b4a2  mov     [rbp+0B0h+var_D0], edx
0x18002b4a5  mov     [rbp+0B0h+var_12C], edx
0x18002b4a8  mov     [rbp+0B0h+var_F8], rdx
0x18002b4ac  mov     [rbp+0B0h+var_108], rdx
0x18002b4b0  mov     [rbp+0B0h+var_124], edx
0x18002b4b3  mov     [rbp+0B0h+var_128], edx
0x18002b4b6  mov     [rbp+0B0h+var_E8], rdx
0x18002b4ba  mov     [rbp+0B0h+var_130], edx
0x18002b4bd  mov     [rbp+0B0h+var_F0], rdx
0x18002b4c1  mov     [rbp+0B0h+hAlgorithm], rdx
0x18002b4c5  mov     [rsp+1B0h+var_150], rdx
0x18002b4ca  mov     [rbp+0B0h+var_100], edx
0x18002b4cd  mov     [rbp+0B0h+var_FC], edx
0x18002b4d0  mov     dword ptr [rbp+0B0h+var_110], edx
0x18002b4d3  mov     qword ptr [rbp+0B0h+var_118], r9
0x18002b4d7  mov     qword ptr [rbp+0B0h+var_E0], rcx
0x18002b4db  mov     [rsp+1B0h+var_140], r12
0x18002b4e0  mov     [rbp+0B0h+pbInput], r14
0x18002b4e4  call    KspValidateAndLockProvider
0x18002b4e9  mov     qword ptr [rsp+1B0h+var_138], rax
0x18002b4ee  mov     rsi, rax
0x18002b4f1  test    rax, rax
0x18002b4f4  jnz     short loc_18002B523
0x18002b4f6  mov     r9d, 1039h
0x18002b4fc  mov     ebx, 80090026h
0x18002b501  mov     ecx, 80090026h
0x18002b506  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002b50d  lea     rdx, aStatus; "Status"
0x18002b514  call    DebugTraceError
0x18002b519  mov     r14, [rsp+1B0h+var_150]
0x18002b51e  jmp     loc_18002C706
0x18002b523  test    r12, r12
0x18002b526  jnz     short loc_18002B53A
0x18002b528  mov     r9d, 1040h
0x18002b52e  mov     ebx, 80090027h
0x18002b533  mov     ecx, 80090027h
0x18002b538  jmp     short loc_18002B506
0x18002b53a  test    r14, r14
0x18002b53d  jz      loc_18002C6BF
0x18002b543  mov     r13d, [rbp+0B0h+cbInput]
0x18002b54a  test    r13d, r13d
0x18002b54d  jz      loc_18002C6BF
0x18002b553  mov     r12d, [rbp+0B0h+arg_38]
0x18002b55a  test    r12d, 0FFF89917h
0x18002b561  jz      short loc_18002B575
0x18002b563  mov     r9d, 1054h
0x18002b569  mov     ebx, 80090009h
0x18002b56e  mov     ecx, 80090009h
0x18002b573  jmp     short loc_18002B506
0x18002b575  xor     edi, edi
0x18002b577  test    rbx, rbx
0x18002b57a  jz      loc_18002B60B
0x18002b580  mov     rcx, rbx
0x18002b583  call    KspValidateKeyHandle
0x18002b588  mov     rdi, rax
0x18002b58b  test    rax, rax
0x18002b58e  jnz     short loc_18002B59B
0x18002b590  mov     r9d, 105Eh
0x18002b596  jmp     loc_18002B4FC
0x18002b59b  lea     rdx, aIsolatedKeyEnv; "ISOLATED_KEY_ENVELOPE"
0x18002b5a2  mov     rcx, r15; String1
0x18002b5a5  call    wcscmp_0
0x18002b5aa  test    eax, eax
0x18002b5ac  jnz     short loc_18002B5E6
0x18002b5ae  cmp     [rdi+90h], eax
0x18002b5b4  jnz     short loc_18002B5CB
0x18002b5b6  mov     r9d, 1067h
0x18002b5bc  mov     ebx, 80090029h
0x18002b5c1  mov     ecx, 80090029h
0x18002b5c6  jmp     loc_18002B506
0x18002b5cb  test    byte ptr [rdi+28h], 8
0x18002b5cf  jnz     short loc_18002B60B
0x18002b5d1  mov     r9d, 106Eh
0x18002b5d7  mov     ebx, 80090010h
0x18002b5dc  mov     ecx, 80090010h
0x18002b5e1  jmp     loc_18002B506
0x18002b5e6  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18002b5ed  mov     rcx, r15; String1
0x18002b5f0  call    wcscmp_0
0x18002b5f5  test    eax, eax
0x18002b5f7  jnz     short loc_18002B60B
0x18002b5f9  mov     eax, [rdi+28h]
0x18002b5fc  test    al, 28h
0x18002b5fe  jnz     short loc_18002B60B
0x18002b600  mov     r9d, 1077h
0x18002b606  jmp     loc_18002B569
0x18002b60b  mov     ebx, [rsi+30h]
0x18002b60e  test    ebx, ebx
0x18002b610  jz      short loc_18002B620
0x18002b612  test    r12b, 20h
0x18002b616  jz      short loc_18002B620
0x18002b618  mov     r9d, 1086h
0x18002b61e  jmp     short loc_18002B5D7
0x18002b620  mov     eax, r12d
0x18002b623  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18002b62a  and     eax, 8
0x18002b62d  mov     rcx, r15; String1
0x18002b630  mov     [rbp+0B0h+var_120], eax
0x18002b633  call    wcscmp_0
0x18002b638  test    eax, eax
0x18002b63a  jz      loc_18002C10D
0x18002b640  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18002b647  mov     rcx, r15; String1
0x18002b64a  call    wcscmp_0
0x18002b64f  test    eax, eax
0x18002b651  jz      loc_18002C10D
0x18002b657  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x18002b65e  mov     rcx, r15; String1
0x18002b661  xor     esi, esi
0x18002b663  call    wcscmp_0
0x18002b668  test    eax, eax
0x18002b66a  jnz     short loc_18002B676
0x18002b66c  mov     edi, 30001h
0x18002b671  jmp     loc_18002BA59
0x18002b676  lea     rdx, aDsapublicblob; "DSAPUBLICBLOB"
0x18002b67d  mov     rcx, r15; String1
0x18002b680  call    wcscmp_0
0x18002b685  test    eax, eax
0x18002b687  jnz     short loc_18002B693
0x18002b689  mov     edi, 30003h
0x18002b68e  jmp     loc_18002BA59
0x18002b693  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x18002b69a  mov     rcx, r15; String1
0x18002b69d  call    wcscmp_0
0x18002b6a2  test    eax, eax
0x18002b6a4  jnz     short loc_18002B6B0
0x18002b6a6  mov     edi, 30002h
0x18002b6ab  jmp     loc_18002BA59
0x18002b6b0  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x18002b6b7  mov     rcx, r15; String1
0x18002b6ba  call    wcscmp_0
0x18002b6bf  test    eax, eax
0x18002b6c1  jz      loc_18002BFE2
0x18002b6c7  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x18002b6ce  mov     rcx, r15; String1
0x18002b6d1  call    wcscmp_0
0x18002b6d6  test    eax, eax
0x18002b6d8  jz      loc_18002BFE2
0x18002b6de  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x18002b6e5  mov     rcx, r15; String1
0x18002b6e8  call    wcscmp_0
0x18002b6ed  test    eax, eax
0x18002b6ef  jz      loc_18002BFE2
0x18002b6f5  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x18002b6fc  mov     rcx, r15; String1
0x18002b6ff  call    wcscmp_0
0x18002b704  test    eax, eax
0x18002b706  jz      loc_18002BFE2
0x18002b70c  lea     rdx, aCipherkeyblob; "CipherKeyBlob"
0x18002b713  mov     rcx, r15; String1
0x18002b716  call    wcscmp_0
0x18002b71b  test    eax, eax
0x18002b71d  jnz     short loc_18002B724
0x18002b71f  lea     edi, [rax+1]
0x18002b722  jmp     short loc_18002B740
0x18002b724  lea     rdx, aKdfkeyblob; "KDFKeyBlob"
0x18002b72b  mov     rcx, r15; String1
0x18002b72e  call    wcscmp_0
0x18002b733  test    eax, eax
0x18002b735  jnz     loc_18002B7F3
0x18002b73b  xor     edi, edi
0x18002b73d  lea     esi, [rax+1]
0x18002b740  mov     r8, qword ptr [rbp+0B0h+var_118]
0x18002b744  lea     rdx, [rsp+1B0h+var_148]
0x18002b749  mov     rcx, qword ptr [rsp+1B0h+var_138]
0x18002b74e  mov     r9, r14
0x18002b751  mov     [rsp+1B0h+dwFlags], r12d
0x18002b756  mov     dword ptr [rsp+1B0h+pcbResult], r13d
0x18002b75b  call    KspImportCipherOrKDFBlob
0x18002b760  mov     ebx, eax
0x18002b762  test    eax, eax
0x18002b764  jz      short loc_18002B778
0x18002b766  mov     r9d, 122Ah
0x18002b76c  mov     r12, [rsp+1B0h+var_140]
0x18002b771  mov     ecx, eax
0x18002b773  jmp     loc_18002C6CF
0x18002b778  mov     r14, [rsp+1B0h+var_150]
0x18002b77d  test    edi, edi
0x18002b77f  jnz     loc_18002C5B0
0x18002b785  test    esi, esi
0x18002b787  jnz     loc_18002C5B0
0x18002b78d  mov     rcx, [rsp+1B0h+var_148]
0x18002b792  mov     dword ptr [rcx+1Ch], 0
0x18002b799  mov     rcx, [rsp+1B0h+var_148]
0x18002b79e  mov     rax, [rcx+40h]
0x18002b7a2  cmp     dword ptr [rax+60h], 0
0x18002b7a6  jz      loc_18002C5A1
0x18002b7ac  lea     r8, [rcx+1Ch]; pbOutput
0x18002b7b0  mov     [rsp+1B0h+dwFlags], 0; dwFlags
0x18002b7b8  mov     rcx, [rcx+68h]; hObject
0x18002b7bc  lea     rax, [rbp+0B0h+var_D0]
0x18002b7c0  mov     r9d, 4; cbOutput
0x18002b7c6  mov     [rsp+1B0h+pcbResult], rax; pcbResult
0x18002b7cb  lea     rdx, aKeystrength; "KeyStrength"
0x18002b7d2  call    cs:__imp_BCryptGetProperty
0x18002b7d9  nop     dword ptr [rax+rax+00h]
0x18002b7de  mov     ebx, eax
0x18002b7e0  test    eax, eax
0x18002b7e2  jz      loc_18002C6B5
0x18002b7e8  mov     r9d, 1474h
0x18002b7ee  jmp     loc_18002BC5A
0x18002b7f3  lea     rdx, aOpaquetranspor; "OpaqueTransport"
0x18002b7fa  mov     rcx, r15; String1
0x18002b7fd  call    wcscmp_0
0x18002b802  test    eax, eax
0x18002b804  jz      loc_18002BD6D
0x18002b80a  lea     rdx, aProtectedkeybl; "ProtectedKeyBlob"
0x18002b811  mov     rcx, r15; String1
0x18002b814  call    wcscmp_0
0x18002b819  test    eax, eax
0x18002b81b  jz      loc_18002BD33
0x18002b821  lea     rdx, aPkcs7Envelope; "PKCS7_ENVELOPE"
0x18002b828  mov     rcx, r15; String1
0x18002b82b  call    wcscmp_0
0x18002b830  test    eax, eax
0x18002b832  jz      loc_18002BCF9
0x18002b838  lea     rdx, aPkcs8Privateke; "PKCS8_PRIVATEKEY"
0x18002b83f  mov     rcx, r15; String1
0x18002b842  call    wcscmp_0
0x18002b847  test    eax, eax
0x18002b849  jz      loc_18002BCC0
0x18002b84f  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18002b856  mov     rcx, r15; String1
0x18002b859  call    wcscmp_0
0x18002b85e  test    eax, eax
0x18002b860  jz      loc_18002BCB6
0x18002b866  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18002b86d  mov     rcx, r15; String1
0x18002b870  call    wcscmp_0
0x18002b875  test    eax, eax
0x18002b877  jz      loc_18002BCB6
0x18002b87d  lea     rdx, aCapiprivateblo; "CAPIPRIVATEBLOB"
0x18002b884  mov     rcx, r15; String1
0x18002b887  call    wcscmp_0
0x18002b88c  test    eax, eax
0x18002b88e  jz      loc_18002BCB6
0x18002b894  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18002b89b  mov     rcx, r15; String1
0x18002b89e  call    wcscmp_0
0x18002b8a3  test    eax, eax
0x18002b8a5  jz      loc_18002BCAC
0x18002b8ab  lea     rdx, aCapidsaprivate; "CAPIDSAPRIVATEBLOB"
0x18002b8b2  mov     rcx, r15; String1
0x18002b8b5  call    wcscmp_0
0x18002b8ba  test    eax, eax
0x18002b8bc  jz      loc_18002BCAC
0x18002b8c2  lea     rdx, aV2capidsapriva; "V2CAPIDSAPRIVATEBLOB"
0x18002b8c9  mov     rcx, r15; String1
0x18002b8cc  call    wcscmp_0
0x18002b8d1  test    eax, eax
0x18002b8d3  jz      loc_18002BCAC
0x18002b8d9  lea     rdx, aDhprivateblob; "DHPRIVATEBLOB"
0x18002b8e0  mov     rcx, r15; String1
0x18002b8e3  call    wcscmp_0
0x18002b8e8  test    eax, eax
0x18002b8ea  jz      loc_18002BCA2
0x18002b8f0  lea     rdx, aCapidhprivateb; "CAPIDHPRIVATEBLOB"
0x18002b8f7  mov     rcx, r15; String1
0x18002b8fa  call    wcscmp_0
0x18002b8ff  test    eax, eax
0x18002b901  jz      loc_18002BCA2
0x18002b907  lea     rdx, aIsolatedKeyEnv; "ISOLATED_KEY_ENVELOPE"
0x18002b90e  mov     rcx, r15; String1
0x18002b911  call    wcscmp_0
0x18002b916  test    eax, eax
0x18002b918  jz      loc_18002BC66
0x18002b91e  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18002b925  mov     rcx, r15; String1
0x18002b928  call    wcscmp_0
0x18002b92d  test    eax, eax
0x18002b92f  jz      loc_18002BB41
0x18002b935  lea     rdx, aPqdsaprivatebl; "PQDSAPRIVATEBLOB"
0x18002b93c  mov     rcx, r15; String1
0x18002b93f  call    wcscmp_0
0x18002b944  test    eax, eax
0x18002b946  jz      loc_18002BAA3
0x18002b94c  lea     rdx, aPqdsaprivatese; "PQDSAPRIVATESEEDBLOB"
0x18002b953  mov     rcx, r15; String1
0x18002b956  call    wcscmp_0
0x18002b95b  test    eax, eax
0x18002b95d  jz      loc_18002BAA3
  ... truncated ...
```
