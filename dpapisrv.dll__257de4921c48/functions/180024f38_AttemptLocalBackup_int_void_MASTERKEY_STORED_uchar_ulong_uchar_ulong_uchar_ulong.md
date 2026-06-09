# AttemptLocalBackup(int,void *,MASTERKEY_STORED *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180024f38`
- end: `0x180025a26`
- name: `?AttemptLocalBackup@@YAKHPEAXPEAUMASTERKEY_STORED@@PEAEK2KPEAPEAEPEAK@Z`
- size: `2798`
- prototype: `__int64 __fastcall(int, void *, struct MASTERKEY_STORED *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a794`
- `0x18002d330`

## callees

- `0x1800029d0`
- `0x180002f18`
- `0x180003080`
- `0x180007f10`
- `0x18000b680`
- `0x18000c4a0`
- `0x18000dcb0`
- `0x18001d810`
- `0x18001e1b4`
- `0x180023d84`
- `0x180024f38`
- `0x18002677c`
- `0x180026dbc`
- `0x1800278c4`
- `0x180036a18`
- `0x18003b41c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800253b4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800253b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002520c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002520c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025399`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180025062`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800250f3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180025062`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800250f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002528e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002528e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025523`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025523`
- `bcrypt!BCryptEncrypt` at `0x1800257a8`
- `bcrypt!BCryptEncrypt` at `0x1800258cd`
- `bcrypt!BCryptEncrypt` at `0x180025942`
- `bcrypt!BCryptEncrypt` at `0x1800257a8`
- `bcrypt!BCryptEncrypt` at `0x1800258cd`
- `bcrypt!BCryptEncrypt` at `0x180025942`
- `bcrypt!BCryptGenRandom` at `0x1800255cc`
- `bcrypt!BCryptGenRandom` at `0x18002566b`
- `bcrypt!BCryptGenRandom` at `0x1800255cc`
- `bcrypt!BCryptGenRandom` at `0x18002566b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180025735`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180025864`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180025735`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180025864`
- `bcrypt!BCryptDestroyKey` at `0x1800252ce`
- `bcrypt!BCryptDestroyKey` at `0x1800257ba`
- `bcrypt!BCryptDestroyKey` at `0x1800258df`
- `bcrypt!BCryptDestroyKey` at `0x1800252ce`
- `bcrypt!BCryptDestroyKey` at `0x1800257ba`
- `bcrypt!BCryptDestroyKey` at `0x1800258df`
- `bcrypt!BCryptGetProperty` at `0x1800253e9`
- `bcrypt!BCryptGetProperty` at `0x1800253e9`
- `ntdll!RtlNtStatusToDosError` at `0x18002596d`
- `ntdll!RtlNtStatusToDosError` at `0x180025a13`
- `ntdll!RtlNtStatusToDosError` at `0x18002596d`
- `ntdll!RtlNtStatusToDosError` at `0x180025a13`
- `CRYPT32!CertCreateCertificateContext` at `0x1800251f0`
- `CRYPT32!CertCreateCertificateContext` at `0x1800251f0`
- `CRYPT32!CertFreeCertificateContext` at `0x180025279`
- `CRYPT32!CertFreeCertificateContext` at `0x180025279`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180025389`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180025389`

## string_xrefs

- `0x18002502b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180025047`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall AttemptLocalBackup(
        int a1,
        void *a2,
        struct MASTERKEY_STORED *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 **a8,
        unsigned int *a9)
{
  void *v9; // r13
  int v11; // edi
  int *v12; // rbx
  const CERT_CONTEXT *v13; // r12
  unsigned int LastError; // esi
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // ebx
  unsigned int v18; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  DWORD v20; // eax
  __int64 v21; // r9
  PCERT_INFO pCertInfo; // rcx
  DWORD LengthSid; // r13d
  NTSTATUS Property; // eax
  NTSTATUS v26; // ebx
  int v27; // eax
  ULONG v28; // eax
  unsigned int v29; // ecx
  unsigned int v30; // eax
  bool v31; // cf
  __int64 v32; // r9
  __int64 v33; // rcx
  unsigned int v34; // edx
  ULONG cbOutput; // r13d
  unsigned int v36; // ecx
  ULONG v37; // r12d
  __int64 v38; // r9
  __int64 v39; // rcx
  int *v40; // rax
  bool v41; // zf
  _DWORD *v42; // rdi
  void *v43; // rdx
  __int64 v44; // rax
  char *v45; // rbx
  size_t v46; // rax
  ULONG v47; // r8d
  NTSTATUS v48; // ebx
  __int64 v49; // r9
  __int64 v50; // rbx
  const void *v51; // rdx
  _DWORD *v52; // rax
  size_t v53; // r8
  char *v54; // rdi
  char *v55; // rdi
  __int64 v56; // rbx
  UCHAR *v57; // rdx
  ULONG v58; // edi
  UCHAR *v59; // rax
  UCHAR *v60; // rdi
  void *BCryptProviderHandle; // rax
  __int64 v62; // r9
  unsigned int v63; // ebx
  char *v64; // r15
  NTSTATUS SymmetricKey; // ebx
  __int64 v66; // r9
  UCHAR *v67; // rsi
  void *v68; // rax
  char *v69; // r15
  unsigned __int8 *v70; // rbx
  NTSTATUS v71; // eax
  NTSTATUS v72; // esi
  const CERT_CONTEXT *v73; // rax
  BYTE *pbData; // rcx
  unsigned __int8 **v75; // rax
  int *v76; // [rsp+50h] [rbp-B0h]
  ULONG cbInput; // [rsp+58h] [rbp-A8h] BYREF
  void *v78; // [rsp+60h] [rbp-A0h]
  DWORD cbCertEncoded; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbOutput[4]; // [rsp+6Ch] [rbp-94h] BYREF
  int v81; // [rsp+70h] [rbp-90h]
  int v82; // [rsp+74h] [rbp-8Ch]
  ULONG v83; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h] BYREF
  const CERT_CONTEXT *v85; // [rsp+88h] [rbp-78h]
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  size_t v87; // [rsp+98h] [rbp-68h]
  BYTE *pbCertEncoded; // [rsp+A0h] [rbp-60h] BYREF
  size_t Size; // [rsp+A8h] [rbp-58h]
  struct MASTERKEY_STORED *v90; // [rsp+B0h] [rbp-50h]
  ULONG pcbResult; // [rsp+B8h] [rbp-48h] BYREF
  size_t v92; // [rsp+C0h] [rbp-40h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+C8h] [rbp-38h] BYREF
  char *v94; // [rsp+D0h] [rbp-30h]
  __int64 v95; // [rsp+D8h] [rbp-28h]
  unsigned __int8 **v96; // [rsp+E0h] [rbp-20h]
  unsigned int *v97; // [rsp+E8h] [rbp-18h]
  _DWORD v98[6]; // [rsp+F0h] [rbp-10h] BYREF
  void *v99; // [rsp+108h] [rbp+8h]
  UCHAR pbIV[16]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v101[40]; // [rsp+370h] [rbp+270h] BYREF

  LODWORD(Size) = a5;
  v9 = a2;
  *(_QWORD *)pbIV = a6;
  LODWORD(v87) = a7;
  v96 = a8;
  v97 = a9;
  Src = a4;
  v90 = a3;
  v78 = a2;
  v82 = a1;
  pbCertEncoded = 0;
  cbCertEncoded = 0;
  hKey = 0;
  cbInput = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  hMem = 0;
  UpdateGlobals(a1);
  v11 = dword_18004C54C;
  v12 = 0;
  v81 = dword_18004C54C;
  v76 = 0;
  v101[0] = 0;
  v13 = 0;
  memset_0(v98, 0, 0x270u);
  if ( !(unsigned int)GetTokenUserSid(v9, &hMem) )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1711);
LABEL_30:
    if ( !v82 && LastError )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( !a1 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
    {
      LastError = 0;
    }
    else
    {
      v16 = RetrieveBackupPublicKeyFromStorage(
              v9,
              hMem,
              *((unsigned __int16 **)v90 + 1),
              &pbCertEncoded,
              &cbCertEncoded);
      LastError = v16;
      if ( v16 )
        DebugTraceError(v16, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1783);
    }
    goto LABEL_15;
  }
  if ( SetThreadToken(0, v9) )
  {
    v98[0] = 624;
    v99 = v9;
    v15 = LocalBackupRestoreData(v98, v90, (unsigned __int8 *)Src, 0, &pbCertEncoded, &cbCertEncoded, &stru_180042B98);
    LastError = v15;
    if ( v15 )
      DebugTraceError(v15, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1749);
    if ( !SetThreadToken(0, 0) && !LastError )
    {
      LastError = GetLastError();
      goto LABEL_32;
    }
LABEL_15:
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
    {
      v17 = v82;
      if ( v82 )
      {
        LOBYTE(v12) = 0;
        if ( !LastError )
          goto LABEL_26;
        v17 = v82;
      }
      v18 = RetrieveBackupPublicKeyFromStorage(
              v9,
              hMem,
              *((unsigned __int16 **)v90 + 1),
              &pbCertEncoded,
              &cbCertEncoded);
      LastError = v18;
      if ( v18 == 1901 )
      {
        if ( v17 )
        {
          LOBYTE(v12) = 1;
          LastError = 0;
          goto LABEL_26;
        }
        goto LABEL_23;
      }
      LOBYTE(v12) = 0;
      if ( v18 )
      {
LABEL_23:
        DebugTraceError(v18, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1812);
LABEL_24:
        v12 = 0;
        goto LABEL_30;
      }
    }
    else if ( LastError )
    {
      goto LABEL_24;
    }
LABEL_26:
    CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
    v85 = CertificateContext;
    v13 = CertificateContext;
    if ( !CertificateContext )
    {
      v20 = GetLastError();
      v21 = 1825;
LABEL_28:
      LastError = v20;
      DebugTraceError(v20, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v21);
LABEL_29:
      v12 = v76;
      goto LABEL_30;
    }
    if ( LastError )
      goto LABEL_29;
    pCertInfo = CertificateContext->pCertInfo;
    if ( pCertInfo->SerialNumber.cbData == 16 )
      MyGuidToStringW(pCertInfo->SerialNumber.pbData, v101);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
    {
      if ( !v82 || (_BYTE)v12 )
      {
LABEL_53:
        if ( !CryptImportPublicKeyInfoEx2(v13->dwCertEncodingType, &v13->pCertInfo->SubjectPublicKeyInfo, 0, 0, &hKey) )
        {
          v20 = GetLastError();
          v21 = 1884;
          goto LABEL_28;
        }
        LengthSid = GetLengthSid(hMem);
        LODWORD(v92) = LengthSid;
        Property = BCryptGetProperty(hKey, L"BlockLength", pbOutput, 4u, &pcbResult, 0);
        v26 = Property;
        if ( Property < 0 || pcbResult < 4 )
        {
          DebugTraceError(
            (unsigned int)Property,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
            1899);
          LastError = RtlNtStatusToDosError(v26);
          goto LABEL_70;
        }
        v27 = 40;
        if ( v11 != 2 )
          v27 = 64;
        v28 = Size + v27;
        cbInput = v28;
        if ( v11 == 3 )
        {
          if ( v28 + 11 > *(_DWORD *)pbOutput )
          {
            v81 = 2;
            cbInput = Size + 40;
            v11 = 2;
LABEL_63:
            v29 = -1;
            v30 = v87 + 28;
            v31 = (unsigned int)v87 >= 0xFFFFFFE4;
            goto LABEL_65;
          }
        }
        else
        {
          v81 = v11;
          if ( v11 == 2 )
            goto LABEL_63;
        }
        v29 = -1;
        v30 = v87 + 72;
        v31 = (unsigned int)v87 >= 0xFFFFFFB8;
LABEL_65:
        if ( !v31 )
          v29 = v30;
        LastError = v31 ? 0x80070216 : 0;
        if ( v31 )
        {
          v32 = 1934;
          v33 = LastError;
LABEL_69:
          DebugTraceError(v33, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v32);
LABEL_70:
          v9 = v78;
          goto LABEL_29;
        }
        v34 = v29 + LengthSid;
        v83 = v29 + LengthSid;
        if ( v29 + LengthSid < v29 )
        {
          v32 = 1942;
LABEL_73:
          LastError = -2147024362;
          v33 = 2147942934LL;
          goto LABEL_69;
        }
        if ( v11 == 2 )
        {
          if ( v34 + 7 < v34 )
          {
            v32 = 1954;
            goto LABEL_73;
          }
          cbOutput = (v34 + 7) & 0xFFFFFFF8;
        }
        else
        {
          if ( v34 + 15 < v34 )
          {
            v32 = 1967;
            goto LABEL_73;
          }
          cbOutput = (v34 + 15) & 0xFFFFFFF0;
        }
        v36 = *(_DWORD *)pbOutput + 28;
        if ( *(_DWORD *)pbOutput >= 0xFFFFFFE4 )
        {
          v32 = 1981;
          goto LABEL_73;
        }
        v37 = v36 + cbOutput;
        if ( v36 + cbOutput < v36 )
        {
          LastError = -2147024362;
          v38 = 1989;
          v39 = 2147942934LL;
LABEL_85:
          DebugTraceError(v39, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v38);
LABEL_86:
          v13 = v85;
          goto LABEL_70;
        }
        v40 = (int *)LocalAlloc(0, v37);
        v76 = v40;
        v12 = v40;
        LastError = 8;
        if ( !v40 )
        {
          DebugTraceError(8, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1997);
LABEL_128:
          v13 = v85;
          v9 = v78;
          goto LABEL_30;
        }
        v41 = v81 == 2;
        v42 = v40 + 7;
        v43 = Src;
        v95 = *(unsigned int *)pbOutput;
        v44 = (unsigned int)Size;
        *v42 = Size;
        v45 = (char *)v42 + v44;
        v94 = (char *)v42 + v44;
        if ( v41 )
        {
          v42[1] = 32;
          memcpy_0(v42 + 2, v43, (unsigned int)v44);
          v46 = 8;
        }
        else
        {
          v42[1] = 48;
          v42[2] = 26128;
          v42[3] = 32782;
          memcpy_0(v42 + 4, v43, (unsigned int)v44);
          v46 = 16;
        }
        v47 = v42[1];
        Size = v46;
        v48 = BCryptGenRandom(0, (PUCHAR)&v45[v46], v47, 2u);
        if ( v48 < 0 )
        {
          v49 = 2036;
LABEL_94:
          DebugTraceError(
            (unsigned int)v48,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
            v49);
          LastError = v48 | 0x10000000;
          goto LABEL_86;
        }
        v50 = (unsigned int)v87;
        v51 = *(const void **)pbIV;
        v52 = (_DWORD *)((char *)v42 + v95);
        v53 = (unsigned int)v87;
        Src = v52;
        v54 = (char *)v42 + v95 + 8;
        v52[1] = v87;
        *v52 = 1;
        memcpy_0(v54, v51, v53);
        v55 = &v54[v50];
        v56 = (unsigned int)v92;
        memcpy_0(v55, hMem, (unsigned int)v92);
        *(_QWORD *)pbIV = &v55[v56];
        if ( cbOutput <= v83 )
        {
          v59 = (UCHAR *)&v55[v56];
        }
        else
        {
          v57 = (UCHAR *)&v55[v56];
          v58 = cbOutput - v83;
          v48 = BCryptGenRandom(0, v57, cbOutput - v83, 2u);
          if ( v48 < 0 )
          {
            v49 = 2068;
            goto LABEL_94;
          }
          v59 = (UCHAR *)(*(_QWORD *)pbIV + v58);
        }
        if ( v81 == 2 )
        {
          v60 = (UCHAR *)Src;
          if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)Src, cbOutput - 20, v59) )
          {
            v38 = 2086;
LABEL_103:
            LastError = 13;
            v39 = 13;
            goto LABEL_85;
          }
          Src = 0;
          v83 = 0;
          BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6603u);
          if ( !BCryptProviderHandle )
          {
            v62 = 2134;
LABEL_106:
            v63 = 13;
            DebugTraceError(
              13,
              "ERROR_INVALID_DATA",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
              v62);
            return v63;
          }
          v64 = &v94[Size];
          SymmetricKey = BCryptGenerateSymmetricKey(BCryptProviderHandle, &Src, 0, 0, (PUCHAR)&v94[Size], 0x18u, 0);
          if ( SymmetricKey < 0 )
          {
            v66 = 2148;
LABEL_110:
            DebugTraceError(
              (unsigned int)SymmetricKey,
              "ntStatus",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
              v66);
            return SymmetricKey | 0x10000000u;
          }
          *(_QWORD *)pbIV = *((_QWORD *)v64 + 3);
          SymmetricKey = BCryptEncrypt(Src, v60, cbOutput, 0, pbIV, 8u, v60, cbOutput, &v83, 0);
          BCryptDestroyKey(Src);
          if ( SymmetricKey < 0 )
          {
            v66 = 2171;
            goto LABEL_110;
          }
        }
        else
        {
          v67 = (UCHAR *)Src;
          if ( !(unsigned int)FMyPrimitiveSHA512((PUCHAR)Src, cbOutput - 64, v59) )
          {
            v38 = 2099;
            goto LABEL_103;
          }
          v92 = 0;
          v83 = 0;
          if ( (cbOutput & 0xFFFFFFF0) != cbOutput )
          {
            v39 = 2148073475LL;
            v38 = 2191;
            LastError = -2146893821;
            goto LABEL_85;
          }
          v68 = (void *)GetBCryptProviderHandle(0x6610u);
          if ( !v68 )
          {
            v62 = 2202;
            goto LABEL_106;
          }
          v69 = &v94[Size];
          SymmetricKey = BCryptGenerateSymmetricKey(v68, (BCRYPT_KEY_HANDLE *)&v92, 0, 0, (PUCHAR)&v94[Size], 0x20u, 0);
          if ( SymmetricKey < 0 )
          {
            v66 = 2216;
            goto LABEL_110;
          }
          v60 = v67;
          *(_OWORD *)pbIV = *((_OWORD *)v69 + 2);
          SymmetricKey = BCryptEncrypt(
                           (BCRYPT_KEY_HANDLE)v92,
                           v67,
                           cbOutput & 0xFFFFFFF0,
                           0,
                           pbIV,
                           0x10u,
                           v67,
                           cbOutput & 0xFFFFFFF0,
                           &v83,
                           0);
          BCryptDestroyKey((BCRYPT_KEY_HANDLE)v92);
          if ( SymmetricKey < 0 )
          {
            v66 = 2240;
            goto LABEL_110;
          }
        }
        v70 = (unsigned __int8 *)(v76 + 7);
        v71 = BCryptEncrypt(
                hKey,
                (PUCHAR)v76 + 28,
                cbInput,
                0,
                0,
                0,
                (PUCHAR)v76 + 28,
                *(ULONG *)pbOutput,
                &cbInput,
                2u);
        v72 = v71;
        if ( v71 >= 0 )
        {
          LastError = 0;
          FMyReverseBytes(v70, cbInput);
          if ( cbInput != *(_DWORD *)pbOutput )
          {
            memcpy_0(&v70[cbInput], v60, cbOutput);
            v37 = cbInput + v37 - *(_DWORD *)pbOutput;
          }
          v12 = 0;
          *v76 = v81;
          v76[1] = cbInput;
          v73 = v85;
          v76[2] = cbOutput;
          pbData = v73->pCertInfo->SubjectUniqueId.pbData;
          v75 = v96;
          *(_OWORD *)(v76 + 3) = *(_OWORD *)pbData;
          *v75 = (unsigned __int8 *)v76;
          *v97 = v37;
        }
        else
        {
          DebugTraceError(
            (unsigned int)v71,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
            2263);
          LastError = RtlNtStatusToDosError(v72);
          v12 = v76;
        }
        goto LABEL_128;
      }
    }
    else if ( !v82 )
    {
      goto LABEL_53;
    }
    WriteBackupPublicKeyToStorage(v9, hMem, *((unsigned __int16 **)v90 + 1), pbCertEncoded, cbCertEncoded);
    goto LABEL_53;
  }
  LastError = GetLastError();
  DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 1728);
LABEL_32:
  CPSAudit(v9, 0x254u, (const unsigned __int16 *)v90 + 8, &Class, 0, v101, LastError);
LABEL_33:
  if ( v13 )
    CertFreeCertificateContext(v13);
  if ( pbCertEncoded )
    LocalFree(pbCertEncoded);
  if ( v12 )
    LocalFree(v12);
  if ( hMem )
    LocalFree(hMem);
  if ( hKey )
    BCryptDestroyKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x180024f38  mov     [rsp-8+arg_0], rbx
0x180024f3d  push    rbp
0x180024f3e  push    rsi
0x180024f3f  push    rdi
0x180024f40  push    r12
0x180024f42  push    r13
0x180024f44  push    r14
0x180024f46  push    r15
0x180024f48  lea     rbp, [rsp-2D0h]
0x180024f50  sub     rsp, 3D0h
0x180024f57  mov     rax, cs:__security_cookie
0x180024f5e  xor     rax, rsp
0x180024f61  mov     [rbp+300h+var_40], rax
0x180024f68  mov     eax, [rbp+300h+arg_20]
0x180024f6e  xor     r14d, r14d
0x180024f71  mov     dword ptr [rbp+300h+Size], eax
0x180024f74  mov     r13, rdx
0x180024f77  mov     rax, [rbp+300h+arg_28]
0x180024f7e  mov     esi, ecx
0x180024f80  mov     qword ptr [rbp+300h+pbIV], rax
0x180024f87  mov     eax, [rbp+300h+arg_30]
0x180024f8d  mov     dword ptr [rbp+300h+var_368], eax
0x180024f90  mov     rax, [rbp+300h+arg_38]
0x180024f97  mov     [rbp+300h+var_320], rax
0x180024f9b  mov     rax, [rbp+300h+arg_40]
0x180024fa2  mov     [rbp+300h+var_318], rax
0x180024fa6  mov     [rbp+300h+Src], r9
0x180024faa  mov     [rbp+300h+var_350], r8
0x180024fae  mov     [rsp+400h+var_3A0], rdx
0x180024fb3  mov     [rsp+400h+var_38C], ecx
0x180024fb7  mov     [rbp+300h+pbCertEncoded], r14
0x180024fbb  mov     [rsp+400h+cbCertEncoded], r14d
0x180024fc0  mov     [rbp+300h+hKey], r14
0x180024fc4  mov     [rsp+400h+cbInput], r14d
0x180024fc9  mov     dword ptr [rsp+400h+pbOutput], r14d
0x180024fce  mov     [rbp+300h+pcbResult], r14d
0x180024fd2  mov     [rbp+300h+hMem], r14
0x180024fd6  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x180024fdb  mov     edi, cs:dword_18004C54C
0x180024fe1  lea     rcx, [rbp+300h+var_310]; void *
0x180024fe5  mov     ebx, r14d
0x180024fe8  mov     [rsp+400h+var_390], edi
0x180024fec  xor     edx, edx; Val
0x180024fee  mov     [rsp+400h+var_3B0], rbx
0x180024ff3  mov     r8d, 270h; Size
0x180024ff9  mov     [rbp+300h+var_90], r14w
0x180025001  mov     r12d, r14d
0x180025004  call    memset_0
0x180025009  lea     rdx, [rbp+300h+hMem]
0x18002500d  mov     rcx, r13
0x180025010  call    GetTokenUserSid
0x180025015  test    eax, eax
0x180025017  jnz     short loc_180025047
0x180025019  call    cs:__imp_GetLastError
0x180025020  nop     dword ptr [rax+rax+00h]
0x180025025  mov     r9d, 6AFh
0x18002502b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180025032  mov     ecx, eax
0x180025034  lea     rdx, aDwlasterror; "dwLastError"
0x18002503b  mov     esi, eax
0x18002503d  call    DebugTraceError
0x180025042  jmp     loc_180025232
0x180025047  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002504e  lea     r15, aDwlasterror; "dwLastError"
0x180025055  test    esi, esi
0x180025057  jz      loc_18002511A
0x18002505d  mov     rdx, r13; Token
0x180025060  xor     ecx, ecx; Thread
0x180025062  call    cs:__imp_SetThreadToken
0x180025069  nop     dword ptr [rax+rax+00h]
0x18002506e  test    eax, eax
0x180025070  jnz     short loc_180025098
0x180025072  call    cs:__imp_GetLastError
0x180025079  nop     dword ptr [rax+rax+00h]
0x18002507e  mov     r9d, 6C0h
0x180025084  mov     r8, r14
0x180025087  mov     ecx, eax
0x180025089  mov     rdx, r15
0x18002508c  mov     esi, eax
0x18002508e  call    DebugTraceError
0x180025093  jmp     loc_18002523D
0x180025098  mov     r8, [rbp+300h+Src]; unsigned __int8 *
0x18002509c  lea     rax, stru_180042B98
0x1800250a3  mov     rdx, [rbp+300h+var_350]; struct MASTERKEY_STORED *
0x1800250a7  lea     rcx, [rbp+300h+var_310]; void *
0x1800250ab  mov     qword ptr [rsp+400h+var_3D0], rax; struct _GUID *
0x1800250b0  xor     r9d, r9d; unsigned int
0x1800250b3  lea     rax, [rsp+400h+cbCertEncoded]
0x1800250b8  mov     [rbp+300h+var_310], 270h
0x1800250bf  mov     qword ptr [rsp+400h+dwFlags], rax; unsigned int *
0x1800250c4  lea     rax, [rbp+300h+pbCertEncoded]
0x1800250c8  mov     [rsp+400h+phKey], rax; unsigned __int8 **
0x1800250cd  mov     [rbp+300h+var_2F8], r13
0x1800250d1  call    ?LocalBackupRestoreData@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEKPEAPEAEPEAKPEBU_GUID@@@Z; LocalBackupRestoreData(void *,MASTERKEY_STORED *,uchar *,ulong,uchar * *,ulong *,_GUID const *)
0x1800250d6  mov     esi, eax
0x1800250d8  test    eax, eax
0x1800250da  jz      short loc_1800250EF
0x1800250dc  mov     r9d, 6D5h
0x1800250e2  mov     r8, r14
0x1800250e5  mov     rdx, r15
0x1800250e8  mov     ecx, eax
0x1800250ea  call    DebugTraceError
0x1800250ef  xor     edx, edx; Token
0x1800250f1  xor     ecx, ecx; Thread
0x1800250f3  call    cs:__imp_SetThreadToken
0x1800250fa  nop     dword ptr [rax+rax+00h]
0x1800250ff  test    eax, eax
0x180025101  jnz     short loc_180025169
0x180025103  test    esi, esi
0x180025105  jnz     short loc_180025169
0x180025107  call    cs:__imp_GetLastError
0x18002510e  nop     dword ptr [rax+rax+00h]
0x180025113  mov     esi, eax
0x180025115  jmp     loc_18002523D
0x18002511a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180025121  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x180025126  test    al, al
0x180025128  jz      short loc_18002512E
0x18002512a  xor     esi, esi
0x18002512c  jmp     short loc_180025169
0x18002512e  mov     rdx, [rbp+300h+hMem]; Sid
0x180025132  lea     rax, [rsp+400h+cbCertEncoded]
0x180025137  mov     [rsp+400h+phKey], rax; unsigned int *
0x18002513c  lea     r9, [rbp+300h+pbCertEncoded]; unsigned __int8 **
0x180025140  mov     rax, [rbp+300h+var_350]
0x180025144  mov     rcx, r13; Token
0x180025147  mov     r8, [rax+8]; unsigned __int16 *
0x18002514b  call    ?RetrieveBackupPublicKeyFromStorage@@YAKPEAX0PEAGPEAPEAEPEAK@Z; RetrieveBackupPublicKeyFromStorage(void *,void *,ushort *,uchar * *,ulong *)
0x180025150  mov     esi, eax
0x180025152  test    eax, eax
0x180025154  jz      short loc_180025169
0x180025156  mov     r9d, 6F7h
0x18002515c  mov     r8, r14
0x18002515f  mov     rdx, r15
0x180025162  mov     ecx, eax
0x180025164  call    DebugTraceError
0x180025169  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180025170  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x180025175  test    al, al
0x180025177  jz      short loc_1800251DE
0x180025179  mov     ebx, [rsp+400h+var_38C]
0x18002517d  test    ebx, ebx
0x18002517f  jz      short loc_18002518B
0x180025181  xor     bl, bl
0x180025183  test    esi, esi
0x180025185  jz      short loc_1800251E2
0x180025187  mov     ebx, [rsp+400h+var_38C]
0x18002518b  mov     rdx, [rbp+300h+hMem]; Sid
0x18002518f  lea     rax, [rsp+400h+cbCertEncoded]
0x180025194  mov     [rsp+400h+phKey], rax; unsigned int *
0x180025199  lea     r9, [rbp+300h+pbCertEncoded]; unsigned __int8 **
0x18002519d  mov     rax, [rbp+300h+var_350]
0x1800251a1  mov     rcx, r13; Token
0x1800251a4  mov     r8, [rax+8]; unsigned __int16 *
0x1800251a8  call    ?RetrieveBackupPublicKeyFromStorage@@YAKPEAX0PEAGPEAPEAEPEAK@Z; RetrieveBackupPublicKeyFromStorage(void *,void *,ushort *,uchar * *,ulong *)
0x1800251ad  mov     esi, eax
0x1800251af  cmp     eax, 76Dh
0x1800251b4  jnz     short loc_1800251C0
0x1800251b6  test    ebx, ebx
0x1800251b8  jz      short loc_1800251C6
0x1800251ba  mov     bl, 1
0x1800251bc  xor     esi, esi
0x1800251be  jmp     short loc_1800251E2
0x1800251c0  xor     bl, bl
0x1800251c2  test    eax, eax
0x1800251c4  jz      short loc_1800251E2
0x1800251c6  mov     r9d, 714h
0x1800251cc  mov     r8, r14
0x1800251cf  mov     rdx, r15
0x1800251d2  mov     ecx, eax
0x1800251d4  call    DebugTraceError
0x1800251d9  mov     rbx, r12
0x1800251dc  jmp     short loc_180025232
0x1800251de  test    esi, esi
0x1800251e0  jnz     short loc_1800251D9
0x1800251e2  mov     r8d, [rsp+400h+cbCertEncoded]; cbCertEncoded
0x1800251e7  mov     ecx, 1; dwCertEncodingType
0x1800251ec  mov     rdx, [rbp+300h+pbCertEncoded]; pbCertEncoded
0x1800251f0  call    cs:__imp_CertCreateCertificateContext
0x1800251f7  nop     dword ptr [rax+rax+00h]
0x1800251fc  mov     [rbp+300h+var_378], rax
0x180025200  mov     r12, rax
0x180025203  test    rax, rax
0x180025206  jnz     loc_180025307
0x18002520c  call    cs:__imp_GetLastError
0x180025213  nop     dword ptr [rax+rax+00h]
0x180025218  mov     r9d, 721h
0x18002521e  mov     r8, r14
0x180025221  mov     rdx, r15
0x180025224  mov     ecx, eax
0x180025226  mov     esi, eax
0x180025228  call    DebugTraceError
0x18002522d  mov     rbx, [rsp+400h+var_3B0]
0x180025232  cmp     [rsp+400h+var_38C], 0
0x180025237  jnz     short loc_18002523D
0x180025239  test    esi, esi
0x18002523b  jnz     short loc_180025271
0x18002523d  mov     r8, [rbp+300h+var_350]
0x180025241  lea     rax, [rbp+300h+var_90]
0x180025248  mov     [rsp+400h+var_3D0], esi; unsigned int
0x18002524c  lea     r9, Class; unsigned __int16 *
0x180025253  mov     qword ptr [rsp+400h+dwFlags], rax; unsigned __int16 *
0x180025258  add     r8, 10h; unsigned __int16 *
0x18002525c  mov     edx, 254h; unsigned int
0x180025261  mov     dword ptr [rsp+400h+phKey], 0; unsigned int
0x180025269  mov     rcx, r13; void *
0x18002526c  call    ?CPSAudit@@YAKPEAXKPEBG1K1K@Z; CPSAudit(void *,ulong,ushort const *,ushort const *,ulong,ushort const *,ulong)
0x180025271  test    r12, r12
0x180025274  jz      short loc_180025285
0x180025276  mov     rcx, r12; pCertContext
0x180025279  call    cs:__imp_CertFreeCertificateContext
0x180025280  nop     dword ptr [rax+rax+00h]
0x180025285  mov     rcx, [rbp+300h+pbCertEncoded]; hMem
0x180025289  test    rcx, rcx
0x18002528c  jz      short loc_18002529A
0x18002528e  call    cs:__imp_LocalFree
0x180025295  nop     dword ptr [rax+rax+00h]
0x18002529a  test    rbx, rbx
0x18002529d  jz      short loc_1800252AE
0x18002529f  mov     rcx, rbx; hMem
0x1800252a2  call    cs:__imp_LocalFree
0x1800252a9  nop     dword ptr [rax+rax+00h]
0x1800252ae  cmp     [rbp+300h+hMem], 0
0x1800252b3  jz      short loc_1800252C5
0x1800252b5  mov     rcx, [rbp+300h+hMem]; hMem
0x1800252b9  call    cs:__imp_LocalFree
0x1800252c0  nop     dword ptr [rax+rax+00h]
0x1800252c5  mov     rcx, [rbp+300h+hKey]; hKey
0x1800252c9  test    rcx, rcx
0x1800252cc  jz      short loc_1800252DA
0x1800252ce  call    cs:__imp_BCryptDestroyKey
0x1800252d5  nop     dword ptr [rax+rax+00h]
0x1800252da  mov     eax, esi
0x1800252dc  mov     rcx, [rbp+300h+var_40]
0x1800252e3  xor     rcx, rsp; StackCookie
0x1800252e6  call    __security_check_cookie
0x1800252eb  mov     rbx, [rsp+400h+arg_0]
0x1800252f3  add     rsp, 3D0h
0x1800252fa  pop     r15
0x1800252fc  pop     r14
0x1800252fe  pop     r13
0x180025300  pop     r12
0x180025302  pop     rdi
0x180025303  pop     rsi
0x180025304  pop     rbp
0x180025305  retn
0x180025307  test    esi, esi
0x180025309  jnz     loc_18002522D
0x18002530f  mov     rcx, [rax+18h]
0x180025313  cmp     dword ptr [rcx+8], 10h
0x180025317  jnz     short loc_180025329
0x180025319  mov     rcx, [rcx+10h]
0x18002531d  lea     rdx, [rbp+300h+var_90]
0x180025324  call    MyGuidToStringW
0x180025329  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x180025330  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x180025335  xor     esi, esi
0x180025337  test    al, al
0x180025339  jz      short loc_180025347
0x18002533b  cmp     [rsp+400h+var_38C], esi
0x18002533f  jz      short loc_18002536D
0x180025341  test    bl, bl
0x180025343  jnz     short loc_18002536D
0x180025345  jmp     short loc_18002534D
0x180025347  cmp     [rsp+400h+var_38C], esi
0x18002534b  jz      short loc_18002536D
0x18002534d  mov     eax, [rsp+400h+cbCertEncoded]
0x180025351  mov     rcx, r13; Token
0x180025354  mov     r9, [rbp+300h+pbCertEncoded]; unsigned __int8 *
0x180025358  mov     rdx, [rbp+300h+hMem]; Sid
0x18002535c  mov     dword ptr [rsp+400h+phKey], eax; unsigned int
0x180025360  mov     rax, [rbp+300h+var_350]
0x180025364  mov     r8, [rax+8]; unsigned __int16 *
0x180025368  call    ?WriteBackupPublicKeyToStorage@@YAKPEAX0PEAGPEAEK@Z; WriteBackupPublicKeyToStorage(void *,void *,ushort *,uchar *,ulong)
0x18002536d  mov     rdx, [r12+18h]
0x180025372  lea     rax, [rbp+300h+hKey]
0x180025376  mov     ecx, [r12]; dwCertEncodingType
0x18002537a  add     rdx, 60h ; '`'; pInfo
0x18002537e  xor     r9d, r9d; pvAuxInfo
0x180025381  mov     [rsp+400h+phKey], rax; phKey
0x180025386  xor     r8d, r8d; dwFlags
0x180025389  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x180025390  nop     dword ptr [rax+rax+00h]
0x180025395  test    eax, eax
0x180025397  jnz     short loc_1800253B0
0x180025399  call    cs:__imp_GetLastError
0x1800253a0  nop     dword ptr [rax+rax+00h]
0x1800253a5  mov     r9d, 75Ch
0x1800253ab  jmp     loc_18002521E
0x1800253b0  mov     rcx, [rbp+300h+hMem]; pSid
0x1800253b4  call    cs:__imp_GetLengthSid
0x1800253bb  nop     dword ptr [rax+rax+00h]
0x1800253c0  mov     rcx, [rbp+300h+hKey]; hObject
0x1800253c4  lea     r8, [rsp+400h+pbOutput]; pbOutput
0x1800253c9  mov     r13d, eax
0x1800253cc  mov     dword ptr [rbp+300h+var_340], eax
0x1800253cf  lea     rax, [rbp+300h+pcbResult]
0x1800253d3  mov     [rsp+400h+dwFlags], esi; dwFlags
0x1800253d7  mov     r9d, 4; cbOutput
0x1800253dd  mov     [rsp+400h+phKey], rax; pcbResult
  ... truncated ...
```
