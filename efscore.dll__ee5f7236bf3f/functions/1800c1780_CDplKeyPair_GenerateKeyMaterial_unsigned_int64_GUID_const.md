# CDplKeyPair::GenerateKeyMaterial(unsigned __int64,_GUID const &)

- ea: `0x1800c1780`
- end: `0x1800c281e`
- name: `?GenerateKeyMaterial@CDplKeyPair@@AEAAJ_KAEBU_GUID@@@Z`
- size: `4254`
- prototype: `__int64 __fastcall(CDplKeyPair *__hidden this, unsigned __int64, const struct _GUID *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a6cf0`
- `0x1800b0088`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180087d68`
- `0x1800b0e7c`
- `0x1800b494c`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800c0854`
- `0x1800c1780`
- `0x1800c55bc`
- `0x1800c8038`
- `0x1800d5af8`
- `0x1800d6064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c209d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c248c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c209d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c248c`
- `CRYPT32!CryptProtectMemory` at `0x1800c2093`
- `CRYPT32!CryptProtectMemory` at `0x1800c2480`
- `CRYPT32!CryptProtectMemory` at `0x1800c2093`
- `CRYPT32!CryptProtectMemory` at `0x1800c2480`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c26e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c26e1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c2290`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c22a9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c22c2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c2290`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c22a9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c22c2`
- `bcrypt!BCryptGetProperty` at `0x1800c1ad7`
- `bcrypt!BCryptGetProperty` at `0x1800c1b99`
- `bcrypt!BCryptGetProperty` at `0x1800c1c87`
- `bcrypt!BCryptGetProperty` at `0x1800c2345`
- `bcrypt!BCryptGetProperty` at `0x1800c1ad7`
- `bcrypt!BCryptGetProperty` at `0x1800c1b99`
- `bcrypt!BCryptGetProperty` at `0x1800c1c87`
- `bcrypt!BCryptGetProperty` at `0x1800c2345`
- `bcrypt!BCryptSetProperty` at `0x1800c1a6e`
- `bcrypt!BCryptSetProperty` at `0x1800c1a6e`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800c1d6b`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800c1d6b`
- `bcrypt!BCryptGenerateKeyPair` at `0x1800c1d1c`
- `bcrypt!BCryptGenerateKeyPair` at `0x1800c1d1c`
- `bcrypt!BCryptExportKey` at `0x1800c1dd7`
- `bcrypt!BCryptExportKey` at `0x1800c1eb7`
- `bcrypt!BCryptExportKey` at `0x1800c1f23`
- `bcrypt!BCryptExportKey` at `0x1800c2043`
- `bcrypt!BCryptExportKey` at `0x1800c1dd7`
- `bcrypt!BCryptExportKey` at `0x1800c1eb7`
- `bcrypt!BCryptExportKey` at `0x1800c1f23`
- `bcrypt!BCryptExportKey` at `0x1800c2043`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c19ff`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c1b31`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c2193`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c19ff`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c1b31`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c2193`
- `bcrypt!BCryptDestroyKey` at `0x1800c2277`
- `bcrypt!BCryptDestroyKey` at `0x1800c2277`
- `bcrypt!BCryptGenRandom` at `0x1800c242d`
- `bcrypt!BCryptGenRandom` at `0x1800c242d`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1a13`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1a82`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1aeb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1b45`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1bad`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1c9b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1d30`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1d7f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1deb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1ecb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1f37`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2055`
- `ntdll!RtlNtStatusToDosError` at `0x1800c21ab`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2359`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2441`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1a13`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1a82`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1aeb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1b45`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1bad`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1c9b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1d30`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1d7f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1deb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1ecb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c1f37`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2055`
- `ntdll!RtlNtStatusToDosError` at `0x1800c21ab`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2359`
- `ntdll!RtlNtStatusToDosError` at `0x1800c2441`

## pseudocode

```c
__int64 __fastcall CDplKeyPair::GenerateKeyMaterial(CDplKeyPair *this, unsigned __int64 a2, const struct _GUID *a3)
{
  PUCHAR v6; // r15
  PUCHAR v7; // r13
  PUCHAR v8; // r12
  int v9; // ecx
  unsigned int CreateDuck; // ebx
  int v11; // r8d
  CDplDuck *v12; // rsi
  PUCHAR v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  int v16; // esi
  signed int v17; // eax
  int v18; // eax
  int v19; // esi
  signed int v20; // eax
  int Property; // eax
  int v22; // esi
  signed int v23; // eax
  int v24; // eax
  int v25; // esi
  signed int v26; // eax
  int v27; // eax
  int v28; // ecx
  int v29; // esi
  signed int v30; // eax
  int v31; // eax
  int v32; // esi
  signed int v33; // eax
  int v34; // r8d
  int v35; // eax
  int v36; // esi
  signed int v37; // eax
  int v38; // eax
  int v39; // esi
  signed int v40; // eax
  int v41; // eax
  int v42; // ecx
  int v43; // esi
  signed int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // esi
  signed int v48; // eax
  int v49; // eax
  int v50; // ecx
  int v51; // esi
  signed int v52; // eax
  DWORD v53; // r14d
  __int64 v54; // rax
  _BOOL8 v55; // r8
  int v56; // eax
  int v57; // eax
  int v58; // esi
  signed int v59; // eax
  int v60; // ecx
  signed int LastError; // eax
  unsigned int v62; // r15d
  __int64 v63; // rax
  int v64; // eax
  int v65; // esi
  signed int v66; // eax
  int v67; // r8d
  int v69; // eax
  int v70; // ecx
  int v71; // esi
  signed int v72; // eax
  __int64 v73; // rax
  __int64 v74; // r8
  int v75; // eax
  int v76; // eax
  int v77; // esi
  signed int v78; // eax
  int v79; // ecx
  signed int v80; // eax
  int v81; // esi
  __int64 v82; // rax
  _QWORD *v83; // rcx
  _QWORD *v84; // rax
  _DWORD *v85; // rax
  void *v86; // rcx
  struct _GUID v87; // xmm0
  unsigned __int8 *v88; // rax
  DWORD dwHighDateTime; // ecx
  __int64 v90; // rax
  int v91; // eax
  char dwFlags; // [rsp+20h] [rbp-99h]
  char dwFlagsa; // [rsp+20h] [rbp-99h]
  char dwFlagsb; // [rsp+20h] [rbp-99h]
  CDplDuck *v95; // [rsp+40h] [rbp-79h] BYREF
  void *v96; // [rsp+48h] [rbp-71h]
  PUCHAR v97; // [rsp+50h] [rbp-69h] BYREF
  ULONG v98; // [rsp+58h] [rbp-61h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-59h] BYREF
  BCRYPT_ALG_HANDLE hObject; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int8 *v101; // [rsp+70h] [rbp-49h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int8 *v103; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int8 *v104; // [rsp+88h] [rbp-31h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+90h] [rbp-29h] BYREF
  unsigned int v106; // [rsp+98h] [rbp-21h] BYREF
  ULONG pcbResult; // [rsp+9Ch] [rbp-1Dh] BYREF
  unsigned int v108; // [rsp+A0h] [rbp-19h] BYREF
  UCHAR v109[4]; // [rsp+A4h] [rbp-15h] BYREF
  unsigned int v110; // [rsp+A8h] [rbp-11h] BYREF
  UCHAR pbOutput[4]; // [rsp+ACh] [rbp-Dh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-9h] BYREF
  PUCHAR pbBuffer; // [rsp+B8h] [rbp-1h] BYREF
  PUCHAR v114; // [rsp+C0h] [rbp+7h] BYREF
  PUCHAR v115[9]; // [rsp+C8h] [rbp+Fh] BYREF
  ULONG cbOutput; // [rsp+120h] [rbp+67h] BYREF
  unsigned __int64 v117; // [rsp+128h] [rbp+6Fh]
  const struct _GUID *v118; // [rsp+130h] [rbp+77h]
  ULONG v119; // [rsp+138h] [rbp+7Fh] BYREF

  v118 = a3;
  v117 = a2;
  hObject = 0;
  phKey = 0;
  cbOutput = 0;
  v115[0] = 0;
  v98 = 0;
  v97 = 0;
  v6 = 0;
  v119 = 0;
  v7 = 0;
  v114 = 0;
  v108 = 0;
  v8 = 0;
  v101 = 0;
  v95 = 0;
  hAlgorithm = 0;
  pbBuffer = 0;
  v103 = 0;
  v110 = 0;
  *(_DWORD *)v109 = 0;
  pcbResult = 0;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  v104 = 0;
  v106 = 0;
  SystemTimeAsFileTime = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 222);
  if ( !(unsigned int)CDplUser::IsCurrentLockOwner(*(CDplUser **)(*((_QWORD *)this + 3) + 56LL)) )
  {
    dwFlags = -26;
LABEL_3:
    CreateDuck = -2147418113;
    v11 = -2147418113;
LABEL_4:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 39, dwFlags);
LABEL_5:
    v12 = v95;
    v13 = 0;
    goto LABEL_156;
  }
  if ( *((_QWORD *)this + 12) )
  {
    dwFlags = -25;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 13) )
  {
    dwFlags = -24;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 15) )
  {
    dwFlags = -23;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 17) )
  {
    dwFlags = -22;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 19) )
  {
    dwFlags = -21;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 21) )
  {
    dwFlags = -20;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 23) )
  {
    dwFlags = -19;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 25) )
  {
    dwFlags = -18;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 8) )
  {
    dwFlags = -17;
    goto LABEL_3;
  }
  if ( *((_DWORD *)this + 18) )
  {
    dwFlags = -16;
    goto LABEL_3;
  }
  v14 = *((_QWORD *)this + 3);
  if ( *(_DWORD *)(v14 + 136) || *(_DWORD *)(v14 + 204) )
  {
    fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 254);
    CreateDuck = CDplUser::GetCreateDuck(
                   *(CDplUser **)(*((_QWORD *)this + 3) + 56LL),
                   1,
                   *(_DWORD *)(*((_QWORD *)this + 3) + 204LL),
                   &v95);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                CreateDuck,
                39,
                254) < 0 )
      goto LABEL_5;
  }
  fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 8);
  CreateDuck = CDplKeyPair::GenerateAuthData(this, a2, a3, &v104, &v106);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              CreateDuck,
              39,
              8) < 0 )
    goto LABEL_5;
  v15 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  v16 = v15;
  if ( v15 )
  {
    CreateDuck = 0;
    if ( v15 < 0 )
    {
      v17 = RtlNtStatusToDosError(v15);
      CreateDuck = v17;
      if ( !v17 || v17 == 317 )
      {
        CreateDuck = v16 | 0x10000000;
      }
      else if ( v17 > 0 )
      {
        CreateDuck = (unsigned __int16)v17 | 0x80070000;
      }
    }
    dwFlags = 21;
LABEL_28:
    v11 = CreateDuck;
    goto LABEL_4;
  }
  v18 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  v19 = v18;
  if ( v18 )
  {
    CreateDuck = 0;
    if ( v18 < 0 )
    {
      v20 = RtlNtStatusToDosError(v18);
      CreateDuck = v20;
      if ( !v20 || v20 == 317 )
      {
        CreateDuck = v19 | 0x10000000;
      }
      else if ( v20 > 0 )
      {
        CreateDuck = (unsigned __int16)v20 | 0x80070000;
      }
    }
    dwFlags = 32;
    goto LABEL_28;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  v22 = Property;
  if ( Property )
  {
    CreateDuck = 0;
    if ( Property < 0 )
    {
      v23 = RtlNtStatusToDosError(Property);
      CreateDuck = v23;
      if ( !v23 || v23 == 317 )
      {
        CreateDuck = v22 | 0x10000000;
      }
      else if ( v23 > 0 )
      {
        CreateDuck = (unsigned __int16)v23 | 0x80070000;
      }
    }
    dwFlags = 44;
    goto LABEL_28;
  }
  v24 = BCryptOpenAlgorithmProvider(&hObject, L"RSA", 0, 0);
  v25 = v24;
  if ( v24 )
  {
    CreateDuck = 0;
    if ( v24 < 0 )
    {
      v26 = RtlNtStatusToDosError(v24);
      CreateDuck = v26;
      if ( !v26 || v26 == 317 )
      {
        CreateDuck = v25 | 0x10000000;
      }
      else if ( v26 > 0 )
      {
        CreateDuck = (unsigned __int16)v26 | 0x80070000;
      }
    }
    dwFlags = 55;
    goto LABEL_28;
  }
  v27 = BCryptGetProperty(hObject, L"AlgorithmName", 0, 0, &cbOutput, 0);
  v29 = v27;
  if ( v27 )
  {
    CreateDuck = 0;
    if ( v27 < 0 )
    {
      v30 = RtlNtStatusToDosError(v27);
      CreateDuck = v30;
      if ( !v30 || v30 == 317 )
      {
        CreateDuck = v29 | 0x10000000;
      }
      else if ( v30 > 0 )
      {
        CreateDuck = (unsigned __int16)v30 | 0x80070000;
      }
    }
    dwFlags = 71;
    goto LABEL_28;
  }
  if ( !cbOutput )
  {
    dwFlags = 76;
    goto LABEL_3;
  }
  fnEfsLogTrace1Strings(v28, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 82);
  CreateDuck = DplibpMemAllocEx(cbOutput, 0, 0, v115);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              CreateDuck,
              39,
              82) < 0 )
  {
    v13 = v115[0];
    v12 = v95;
  }
  else
  {
    v96 = v115[0];
    v31 = BCryptGetProperty(hObject, L"AlgorithmName", v115[0], cbOutput, &cbOutput, 0);
    v32 = v31;
    if ( v31 )
    {
      CreateDuck = 0;
      if ( v31 < 0 )
      {
        v33 = RtlNtStatusToDosError(v31);
        CreateDuck = v33;
        if ( !v33 || v33 == 317 )
        {
          CreateDuck = v32 | 0x10000000;
        }
        else if ( v33 > 0 )
        {
          CreateDuck = (unsigned __int16)v33 | 0x80070000;
        }
      }
      dwFlagsa = 93;
LABEL_72:
      v34 = CreateDuck;
LABEL_73:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v34, 39, dwFlagsa);
LABEL_74:
      v12 = v95;
LABEL_155:
      v13 = (PUCHAR)v96;
      goto LABEL_156;
    }
    if ( !cbOutput )
    {
      dwFlagsa = 98;
LABEL_77:
      CreateDuck = -2147418113;
      v34 = -2147418113;
      goto LABEL_73;
    }
    v35 = BCryptGenerateKeyPair(hObject, &phKey, 0x800u, 0);
    v36 = v35;
    if ( v35 )
    {
      CreateDuck = 0;
      if ( v35 < 0 )
      {
        v37 = RtlNtStatusToDosError(v35);
        CreateDuck = v37;
        if ( !v37 || v37 == 317 )
        {
          CreateDuck = v36 | 0x10000000;
        }
        else if ( v37 > 0 )
        {
          CreateDuck = (unsigned __int16)v37 | 0x80070000;
        }
      }
      dwFlagsa = 109;
      goto LABEL_72;
    }
    v38 = BCryptFinalizeKeyPair(phKey, 0);
    v39 = v38;
    if ( v38 )
    {
      CreateDuck = 0;
      if ( v38 < 0 )
      {
        v40 = RtlNtStatusToDosError(v38);
        CreateDuck = v40;
        if ( !v40 || v40 == 317 )
        {
          CreateDuck = v39 | 0x10000000;
        }
        else if ( v40 > 0 )
        {
          CreateDuck = (unsigned __int16)v40 | 0x80070000;
        }
      }
      dwFlagsa = 116;
      goto LABEL_72;
    }
    v41 = BCryptExportKey(phKey, 0, L"RSAPUBLICBLOB", 0, 0, &v98, 0);
    v43 = v41;
    if ( v41 )
    {
      CreateDuck = 0;
      if ( v41 < 0 )
      {
        v44 = RtlNtStatusToDosError(v41);
        CreateDuck = v44;
        if ( !v44 || v44 == 317 )
        {
          CreateDuck = v43 | 0x10000000;
        }
        else if ( v44 > 0 )
        {
          CreateDuck = (unsigned __int16)v44 | 0x80070000;
        }
      }
      dwFlagsa = -123;
      goto LABEL_72;
    }
    fnEfsLogTrace1Strings(v42, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 139);
    CreateDuck = DplibpMemAllocEx(v98, 0, 0, &v97);
    v45 = fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            CreateDuck,
            39,
            139);
    v6 = v97;
    if ( v45 < 0 )
      goto LABEL_74;
    v46 = BCryptExportKey(phKey, 0, L"RSAPUBLICBLOB", v97, v98, &v98, 0);
    v47 = v46;
    if ( v46 )
    {
      CreateDuck = 0;
      if ( v46 < 0 )
      {
        v48 = RtlNtStatusToDosError(v46);
        CreateDuck = v48;
        if ( !v48 || v48 == 317 )
        {
          CreateDuck = v47 | 0x10000000;
        }
        else if ( v48 > 0 )
        {
          CreateDuck = (unsigned __int16)v48 | 0x80070000;
        }
      }
      dwFlagsa = -105;
      goto LABEL_72;
    }
    v49 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", 0, 0, &v119, 0);
    v51 = v49;
    if ( v49 )
    {
      CreateDuck = 0;
      if ( v49 < 0 )
      {
        v52 = RtlNtStatusToDosError(v49);
        CreateDuck = v52;
        if ( !v52 || v52 == 317 )
        {
          CreateDuck = v51 | 0x10000000;
        }
        else if ( v52 > 0 )
        {
          CreateDuck = (unsigned __int16)v52 | 0x80070000;
        }
      }
      dwFlagsa = -88;
      goto LABEL_72;
    }
    v53 = (v119 + 15) & 0xFFFFFFF0;
    if ( v53 < v119 )
    {
      dwFlagsa = -80;
      goto LABEL_77;
    }
    fnEfsLogTrace1Strings(v50, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 183);
    v54 = *((_QWORD *)this + 3);
    v55 = *(_DWORD *)(v54 + 136) || *(_DWORD *)(v54 + 204);
    CreateDuck = DplibpMemAllocEx(v53, 1, v55, &v114);
    v56 = fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            CreateDuck,
            39,
            183);
    v7 = v114;
    if ( v56 < 0 )
      goto LABEL_74;
    CreateDuck = 0;
    v57 = BCryptExportKey(phKey, 0, L"RSAPRIVATEBLOB", v114, v119, &v119, 0);
    v58 = v57;
    if ( v57 )
    {
      if ( v57 < 0 )
      {
        v59 = RtlNtStatusToDosError(v57);
        CreateDuck = v59;
        if ( !v59 || v59 == 317 )
        {
          CreateDuck = v58 | 0x10000000;
        }
        else if ( v59 > 0 )
        {
          CreateDuck = (unsigned __int16)v59 | 0x80070000;
        }
      }
      dwFlagsa = -61;
      goto LABEL_72;
    }
    if ( !CryptProtectMemory(v7, v53, 0) )
    {
      LastError = GetLastError();
      CreateDuck = LastError;
      if ( LastError > 0 )
        CreateDuck = (unsigned __int16)LastError | 0x80070000;
      dwFlagsa = -54;
      goto LABEL_72;
    }
    v12 = v95;
    v62 = v106;
    if ( v95 )
    {
      fnEfsLogTrace1Strings(v60, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 213);
      CreateDuck = CDplDuck::Protect(v12, v7, v53, v119, v104, v62, &v101, &v108);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  CreateDuck,
                  39,
                  213) < 0 )
      {
LABEL_154:
        v6 = v97;
        goto LABEL_155;
      }
    }
    v63 = *((_QWORD *)this + 3);
    if ( (*(_DWORD *)(v63 + 136) || *(_DWORD *)(v63 + 140)) && !v101 )
    {
      CreateDuck = -2147418113;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 39, 220);
      goto LABEL_154;
    }
    v64 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"SP800_108_CTR_HMAC", 0, 0);
    v65 = v64;
    if ( v64 )
    {
      CreateDuck = 0;
      if ( v64 < 0 )
      {
        v66 = RtlNtStatusToDosError(v64);
        CreateDuck = v66;
        if ( !v66 || v66 == 317 )
        {
          CreateDuck = v65 | 0x10000000;
        }
        else if ( v66 > 0 )
        {
          CreateDuck = (unsigned __int16)v66 | 0x80070000;
        }
      }
      dwFlagsb = -22;
LABEL_151:
      v67 = CreateDuck;
LABEL_152:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v67, 39, dwFlagsb);
LABEL_153:
      v12 = v95;
      goto LABEL_154;
    }
    v69 = BCryptGetProperty(hAlgorithm, L"ObjectLength", v109, 4u, &pcbResult, 0);
    v71 = v69;
    if ( v69 )
    {
      CreateDuck = 0;
      if ( v69 < 0 )
      {
        v72 = RtlNtStatusToDosError(v69);
        CreateDuck = v72;
        if ( !v72 || v72 == 317 )
        {
          CreateDuck = v71 | 0x10000000;
        }
        else if ( v72 > 0 )
        {
          CreateDuck = (unsigned __int16)v72 | 0x80070000;
        }
      }
      dwFlagsb = -10;
      goto LABEL_151;
    }
    fnEfsLogTrace1Strings(v70, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 1);
    v73 = *((_QWORD *)this + 3);
    if ( *(_DWORD *)(v73 + 136) || (v74 = 0, *(_DWORD *)(v73 + 204)) )
      v74 = 1;
    CreateDuck = DplibpMemAllocEx(32, 1, v74, &pbBuffer);
    v75 = fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            CreateDuck,
            39,
            1);
    v8 = pbBuffer;
    if ( v75 < 0 )
      goto LABEL_153;
    v76 = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
    v77 = v76;
    if ( v76 )
    {
      CreateDuck = 0;
      if ( v76 < 0 )
      {
        v78 = RtlNtStatusToDosError(v76);
        CreateDuck = v78;
        if ( !v78 || v78 == 317 )
        {
          CreateDuck = v77 | 0x10000000;
        }
        else if ( v78 > 0 )
        {
          CreateDuck = (unsigned __int16)v78 | 0x80070000;
        }
      }
      dwFlagsb = 10;
      goto LABEL_151;
    }
    if ( !CryptProtectMemory(v8, 0x20u, 0) )
    {
      v80 = GetLastError();
      CreateDuck = v80;
      if ( v80 > 0 )
        CreateDuck = (unsigned __int16)v80 | 0x80070000;
      dwFlagsb = 17;
      goto LABEL_151;
    }
    v81 = 0;
    if ( v95 )
    {
      fnEfsLogTrace1Strings(v79, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 28);
      CreateDuck = CDplDuck::Protect(v95, v8, 0x20u, 0x20u, v104, v62, &v103, &v110);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  CreateDuck,
                  39,
                  28) < 0 )
        goto LABEL_153;
      v82 = *((_QWORD *)this + 3);
      if ( *(_DWORD *)(v82 + 204) && !*(_DWORD *)(v82 + 140) )
      {
        v83 = (_QWORD *)(v82 + 104);
        v84 = *(_QWORD **)(v82 + 104);
        v81 = 1;
        while ( v84 != v83 )
        {
          if ( !v84[9] || !v84[15] )
          {
            v81 = 0;
            break;
          }
          v84 = (_QWORD *)*v84;
        }
      }
    }
    v85 = (_DWORD *)*((_QWORD *)this + 3);
    if ( (v85[34] || v85[35]) && !v103 )
    {
      dwFlagsb = 67;
      goto LABEL_221;
    }
    if ( v85[51] && v81 )
    {
      if ( !v103 )
      {
        dwFlagsb = 74;
        goto LABEL_221;
      }
      if ( !v101 )
      {
        dwFlagsb = 77;
LABEL_221:
        CreateDuck = -2147418113;
        v67 = -2147418113;
        goto LABEL_152;
      }
    }
    CDplKeyPair::ReleaseKeyMaterial(this);
    v86 = v96;
    v87 = *v118;
    *((_QWORD *)this + 7) = v117;
    *((_QWORD *)this + 12) = hObject;
    *((_DWORD *)this + 28) = cbOutput;
    *((_QWORD *)this + 15) = v97;
    *((_DWORD *)this + 32) = v98;
    *((_DWORD *)this + 37) = v119;
    *((_QWORD *)this + 19) = v101;
    *((_DWORD *)this + 40) = v108;
    *((_WORD *)this + 82) = 0;
    *((_QWORD *)this + 21) = hAlgorithm;
    *((_DWORD *)this + 44) = *(_DWORD *)v109;
    *((_QWORD *)this + 25) = v103;
    *((_DWORD *)this + 52) = v110;
    *((_QWORD *)this + 27) = phAlgorithm;
    *((_DWORD *)this + 56) = *(_DWORD *)pbOutput;
    v88 = v104;
    *((_QWORD *)this + 17) = v7;
    v7 = 0;
    *((_QWORD *)this + 23) = v8;
    v8 = 0;
    *((_QWORD *)this + 13) = v86;
    *((_QWORD *)this + 8) = v88;
    *(struct _GUID *)((char *)this + 40) = v87;
    hObject = 0;
    *((_DWORD *)this + 36) = v53;
    v101 = 0;
    hAlgorithm = 0;
    *((_DWORD *)this + 48) = 32;
    *((_DWORD *)this + 49) = 32;
    v103 = 0;
    phAlgorithm = 0;
    v104 = 0;
    *((_DWORD *)this + 18) = v62;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
    *((_DWORD *)this + 8) = SystemTimeAsFileTime.dwLowDateTime;
    v90 = *((_QWORD *)this + 3);
    *((_DWORD *)this + 9) = dwHighDateTime;
    if ( *(_DWORD *)(v90 + 204) )
      *(_DWORD *)(v90 + 140) = v81;
    v91 = CDplUser::UserSvcLock(*(CDplUser **)(*((_QWORD *)this + 3) + 56LL));
    *(_DWORD *)(*((_QWORD *)this + 3) + 160LL) = 1;
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 56LL) + 284LL) = 1;
    CDplUser::UserSvcUnlock(*(CDplUser **)(*((_QWORD *)this + 3) + 56LL), v91);
    v12 = v95;
    v13 = 0;
    v6 = 0;
  }
LABEL_156:
  if ( v13 )
    DplibMemFree(v13);
  if ( v6 )
    DplibMemFree(v6);
  if ( v7 )
    DplibMemFree(v7);
  if ( v101 )
    DplibMemFree(v101);
  v101 = 0;
  if ( v8 )
    DplibMemFree(v8);
  if ( v103 )
    DplibMemFree(v103);
  v103 = 0;
  if ( v104 )
    DplibMemFree(v104);
  if ( phKey )
  {
    BCryptDestroyKey(phKey);
    phKey = 0;
  }
  if ( hObject )
  {
    BCryptCloseAlgorithmProvider(hObject, 0);
    hObject = 0;
  }
  if ( hAlgorithm )
  {
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  ReleaseIf<CDplKeyPair>(v12);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    CreateDuck,
    39,
    197);
  return CreateDuck;
}

```

## disassembly

```asm
0x1800c1780  mov     [rsp-8+arg_10], r8
0x1800c1785  mov     [rsp-8+arg_8], rdx
0x1800c178a  push    rbp
0x1800c178b  push    rbx
0x1800c178c  push    rsi
0x1800c178d  push    rdi
0x1800c178e  push    r12
0x1800c1790  push    r13
0x1800c1792  push    r14
0x1800c1794  push    r15
0x1800c1796  lea     rbp, [rsp-1Fh]
0x1800c179b  sub     rsp, 0D8h
0x1800c17a2  xor     ebx, ebx
0x1800c17a4  mov     [rsp+110h+dwFlags], 1DEh
0x1800c17ac  mov     rsi, r8
0x1800c17af  mov     [rbp+57h+hObject], rbx
0x1800c17b3  mov     r14, rdx
0x1800c17b6  mov     [rbp+57h+phKey], rbx
0x1800c17ba  lea     r8, sourceString
0x1800c17c1  mov     [rbp+57h+cbOutput], ebx
0x1800c17c4  lea     r9d, [rbx+27h]
0x1800c17c8  mov     [rbp+57h+var_48], rbx
0x1800c17cc  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800c17d3  mov     [rbp+57h+var_B8], ebx
0x1800c17d6  mov     rdi, rcx
0x1800c17d9  mov     [rbp+57h+var_C0], rbx
0x1800c17dd  mov     r15d, ebx
0x1800c17e0  mov     [rbp+57h+arg_18], ebx
0x1800c17e3  mov     r13d, ebx
0x1800c17e6  mov     [rbp+57h+var_50], rbx
0x1800c17ea  mov     [rbp+57h+var_70], ebx
0x1800c17ed  mov     r12d, ebx
0x1800c17f0  mov     [rbp+57h+var_A0], rbx
0x1800c17f4  mov     [rbp+57h+var_D0], rbx
0x1800c17f8  mov     [rbp+57h+hAlgorithm], rbx
0x1800c17fc  mov     [rbp+57h+pbBuffer], rbx
0x1800c1800  mov     [rbp+57h+var_90], rbx
0x1800c1804  mov     [rbp+57h+var_68], ebx
0x1800c1807  mov     dword ptr [rbp+57h+var_6C], ebx
0x1800c180a  mov     [rbp+57h+pcbResult], ebx
0x1800c180d  mov     [rbp+57h+phAlgorithm], rbx
0x1800c1811  mov     dword ptr [rbp+57h+pbOutput], ebx
0x1800c1814  mov     [rbp+57h+var_88], rbx
0x1800c1818  mov     [rbp+57h+var_78], ebx
0x1800c181b  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800c181f  call    fnEfsLogTrace1Strings
0x1800c1824  mov     rcx, [rdi+18h]
0x1800c1828  mov     rcx, [rcx+38h]; this
0x1800c182c  call    ?IsCurrentLockOwner@CDplUser@@AEAAHXZ; CDplUser::IsCurrentLockOwner(void)
0x1800c1831  test    eax, eax
0x1800c1833  jnz     short loc_1800C186D
0x1800c1835  mov     [rsp+110h+dwFlags], 1E6h
0x1800c183d  mov     r9d, 27h ; '''
0x1800c1843  mov     ebx, 8000FFFFh
0x1800c1848  mov     r8d, 8000FFFFh
0x1800c184e  mov     rcx, cs:g_hPublisher
0x1800c1855  lea     rdx, EFS_TRACE_ERROR
0x1800c185c  call    fnEfsLogTrace1
0x1800c1861  mov     rsi, [rbp+57h+var_D0]
0x1800c1865  mov     rcx, r12
0x1800c1868  jmp     loc_1800C2203
0x1800c186d  cmp     [rdi+60h], rbx
0x1800c1871  jnz     loc_1800C2811
0x1800c1877  cmp     [rdi+68h], rbx
0x1800c187b  jnz     loc_1800C2804
0x1800c1881  cmp     [rdi+78h], rbx
0x1800c1885  jnz     loc_1800C27F7
0x1800c188b  cmp     [rdi+88h], rbx
0x1800c1892  jnz     loc_1800C27EA
0x1800c1898  cmp     [rdi+98h], rbx
0x1800c189f  jnz     loc_1800C27DD
0x1800c18a5  cmp     [rdi+0A8h], rbx
0x1800c18ac  jnz     loc_1800C27D0
0x1800c18b2  cmp     [rdi+0B8h], rbx
0x1800c18b9  jnz     loc_1800C27C3
0x1800c18bf  cmp     [rdi+0C8h], rbx
0x1800c18c6  jnz     loc_1800C27B6
0x1800c18cc  cmp     [rdi+40h], rbx
0x1800c18d0  jnz     loc_1800C27A9
0x1800c18d6  cmp     [rdi+48h], ebx
0x1800c18d9  jnz     loc_1800C279C
0x1800c18df  mov     rax, [rdi+18h]
0x1800c18e3  cmp     [rax+88h], ebx
0x1800c18e9  jnz     short loc_1800C18F3
0x1800c18eb  cmp     [rax+0CCh], ebx
0x1800c18f1  jz      short loc_1800C1970
0x1800c18f3  mov     r9d, 27h ; '''
0x1800c18f9  mov     [rsp+110h+dwFlags], 1FEh
0x1800c1901  lea     r8, sourceString
0x1800c1908  lea     rdx, EFS_TRACE_START_EVENT
0x1800c190f  call    fnEfsLogTrace1Strings
0x1800c1914  mov     rcx, [rdi+18h]
0x1800c1918  lea     r9, [rbp+57h+var_D0]; struct CDplDuck **
0x1800c191c  mov     edx, 1; int
0x1800c1921  mov     r8d, [rcx+0CCh]; int
0x1800c1928  mov     rcx, [rcx+38h]; this
0x1800c192c  call    ?GetCreateDuck@CDplUser@@AEAAJHHPEAPEAVCDplDuck@@@Z; CDplUser::GetCreateDuck(int,int,CDplDuck * *)
0x1800c1931  mov     rcx, cs:g_hPublisher
0x1800c1938  lea     r9, sourceString
0x1800c193f  mov     [rsp+110h+var_E0], 1FEh
0x1800c1947  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c194e  mov     [rsp+110h+var_E8], 27h ; '''
0x1800c1956  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c195d  mov     [rsp+110h+dwFlags], eax
0x1800c1961  mov     ebx, eax
0x1800c1963  call    fnEfsLogTrace1String1Dword
0x1800c1968  test    eax, eax
0x1800c196a  js      loc_1800C1861
0x1800c1970  mov     r9d, 27h ; '''
0x1800c1976  mov     [rsp+110h+dwFlags], 208h
0x1800c197e  lea     r8, sourceString
0x1800c1985  lea     rdx, EFS_TRACE_START_EVENT
0x1800c198c  call    fnEfsLogTrace1Strings
0x1800c1991  lea     rax, [rbp+57h+var_78]
0x1800c1995  mov     r8, rsi; struct _GUID *
0x1800c1998  lea     r9, [rbp+57h+var_88]; unsigned __int8 **
0x1800c199c  mov     qword ptr [rsp+110h+dwFlags], rax; unsigned int *
0x1800c19a1  mov     rdx, r14; unsigned __int64
0x1800c19a4  mov     rcx, rdi; this
0x1800c19a7  call    ?GenerateAuthData@CDplKeyPair@@AEAAJ_KAEBU_GUID@@PEAPEAEPEAK@Z; CDplKeyPair::GenerateAuthData(unsigned __int64,_GUID const &,uchar * *,ulong *)
0x1800c19ac  mov     rcx, cs:g_hPublisher
0x1800c19b3  lea     r14, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c19ba  mov     [rsp+110h+var_E0], 208h
0x1800c19c2  lea     r9, sourceString
0x1800c19c9  mov     r8, r14
0x1800c19cc  mov     [rsp+110h+var_E8], 27h ; '''
0x1800c19d4  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c19db  mov     [rsp+110h+dwFlags], eax
0x1800c19df  mov     ebx, eax
0x1800c19e1  call    fnEfsLogTrace1String1Dword
0x1800c19e6  test    eax, eax
0x1800c19e8  js      loc_1800C1861
0x1800c19ee  xor     r9d, r9d; dwFlags
0x1800c19f1  lea     rdx, pszAlgId; "AES"
0x1800c19f8  xor     r8d, r8d; pszImplementation
0x1800c19fb  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800c19ff  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c1a05  mov     esi, eax
0x1800c1a07  test    eax, eax
0x1800c1a09  jz      short loc_1800C1A51
0x1800c1a0b  xor     ebx, ebx
0x1800c1a0d  test    eax, eax
0x1800c1a0f  jns     short loc_1800C1A3B
0x1800c1a11  mov     ecx, eax; Status
0x1800c1a13  call    cs:__imp_RtlNtStatusToDosError
0x1800c1a19  mov     ebx, eax
0x1800c1a1b  test    eax, eax
0x1800c1a1d  jz      short loc_1800C1A35
0x1800c1a1f  cmp     eax, 13Dh
0x1800c1a24  jz      short loc_1800C1A35
0x1800c1a26  test    eax, eax
0x1800c1a28  jle     short loc_1800C1A3B
0x1800c1a2a  movzx   ebx, ax
0x1800c1a2d  or      ebx, 80070000h
0x1800c1a33  jmp     short loc_1800C1A3B
0x1800c1a35  mov     ebx, esi
0x1800c1a37  bts     ebx, 1Ch
0x1800c1a3b  mov     [rsp+110h+dwFlags], 215h
0x1800c1a43  mov     r9d, 27h ; '''
0x1800c1a49  mov     r8d, ebx
0x1800c1a4c  jmp     loc_1800C184E
0x1800c1a51  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800c1a55  lea     r8, pbInput; "ChainingModeCBC"
0x1800c1a5c  mov     r9d, 20h ; ' '; cbInput
0x1800c1a62  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x1800c1a67  lea     rdx, aChainingmode; "ChainingMode"
0x1800c1a6e  call    cs:__imp_BCryptSetProperty
0x1800c1a74  mov     esi, eax
0x1800c1a76  test    eax, eax
0x1800c1a78  jz      short loc_1800C1AB4
0x1800c1a7a  xor     ebx, ebx
0x1800c1a7c  test    eax, eax
0x1800c1a7e  jns     short loc_1800C1AAA
0x1800c1a80  mov     ecx, eax; Status
0x1800c1a82  call    cs:__imp_RtlNtStatusToDosError
0x1800c1a88  mov     ebx, eax
0x1800c1a8a  test    eax, eax
0x1800c1a8c  jz      short loc_1800C1AA4
0x1800c1a8e  cmp     eax, 13Dh
0x1800c1a93  jz      short loc_1800C1AA4
0x1800c1a95  test    eax, eax
0x1800c1a97  jle     short loc_1800C1AAA
0x1800c1a99  movzx   ebx, ax
0x1800c1a9c  or      ebx, 80070000h
0x1800c1aa2  jmp     short loc_1800C1AAA
0x1800c1aa4  mov     ebx, esi
0x1800c1aa6  bts     ebx, 1Ch
0x1800c1aaa  mov     [rsp+110h+dwFlags], 220h
0x1800c1ab2  jmp     short loc_1800C1A43
0x1800c1ab4  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800c1ab8  lea     rax, [rbp+57h+pcbResult]
0x1800c1abc  mov     [rsp+110h+var_E8], r12d; dwFlags
0x1800c1ac1  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800c1ac5  mov     r9d, 4; cbOutput
0x1800c1acb  mov     qword ptr [rsp+110h+dwFlags], rax; pcbResult
0x1800c1ad0  lea     rdx, aObjectlength; "ObjectLength"
0x1800c1ad7  call    cs:__imp_BCryptGetProperty
0x1800c1add  mov     esi, eax
0x1800c1adf  test    eax, eax
0x1800c1ae1  jz      short loc_1800C1B20
0x1800c1ae3  xor     ebx, ebx
0x1800c1ae5  test    eax, eax
0x1800c1ae7  jns     short loc_1800C1B13
0x1800c1ae9  mov     ecx, eax; Status
0x1800c1aeb  call    cs:__imp_RtlNtStatusToDosError
0x1800c1af1  mov     ebx, eax
0x1800c1af3  test    eax, eax
0x1800c1af5  jz      short loc_1800C1B0D
0x1800c1af7  cmp     eax, 13Dh
0x1800c1afc  jz      short loc_1800C1B0D
0x1800c1afe  test    eax, eax
0x1800c1b00  jle     short loc_1800C1B13
0x1800c1b02  movzx   ebx, ax
0x1800c1b05  or      ebx, 80070000h
0x1800c1b0b  jmp     short loc_1800C1B13
0x1800c1b0d  mov     ebx, esi
0x1800c1b0f  bts     ebx, 1Ch
0x1800c1b13  mov     [rsp+110h+dwFlags], 22Ch
0x1800c1b1b  jmp     loc_1800C1A43
0x1800c1b20  xor     r9d, r9d; dwFlags
0x1800c1b23  lea     rdx, aRsa; "RSA"
0x1800c1b2a  xor     r8d, r8d; pszImplementation
0x1800c1b2d  lea     rcx, [rbp+57h+hObject]; phAlgorithm
0x1800c1b31  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c1b37  mov     esi, eax
0x1800c1b39  test    eax, eax
0x1800c1b3b  jz      short loc_1800C1B7A
0x1800c1b3d  xor     ebx, ebx
0x1800c1b3f  test    eax, eax
0x1800c1b41  jns     short loc_1800C1B6D
0x1800c1b43  mov     ecx, eax; Status
0x1800c1b45  call    cs:__imp_RtlNtStatusToDosError
0x1800c1b4b  mov     ebx, eax
0x1800c1b4d  test    eax, eax
0x1800c1b4f  jz      short loc_1800C1B67
0x1800c1b51  cmp     eax, 13Dh
0x1800c1b56  jz      short loc_1800C1B67
0x1800c1b58  test    eax, eax
0x1800c1b5a  jle     short loc_1800C1B6D
0x1800c1b5c  movzx   ebx, ax
0x1800c1b5f  or      ebx, 80070000h
0x1800c1b65  jmp     short loc_1800C1B6D
0x1800c1b67  mov     ebx, esi
0x1800c1b69  bts     ebx, 1Ch
0x1800c1b6d  mov     [rsp+110h+dwFlags], 237h
0x1800c1b75  jmp     loc_1800C1A43
0x1800c1b7a  mov     rcx, [rbp+57h+hObject]; hObject
0x1800c1b7e  lea     rax, [rbp+57h+cbOutput]
0x1800c1b82  mov     [rsp+110h+var_E8], r12d; dwFlags
0x1800c1b87  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800c1b8e  xor     r9d, r9d; cbOutput
0x1800c1b91  mov     qword ptr [rsp+110h+dwFlags], rax; pcbResult
0x1800c1b96  xor     r8d, r8d; pbOutput
0x1800c1b99  call    cs:__imp_BCryptGetProperty
0x1800c1b9f  mov     esi, eax
0x1800c1ba1  test    eax, eax
0x1800c1ba3  jz      short loc_1800C1BE2
0x1800c1ba5  xor     ebx, ebx
0x1800c1ba7  test    eax, eax
0x1800c1ba9  jns     short loc_1800C1BD5
0x1800c1bab  mov     ecx, eax; Status
0x1800c1bad  call    cs:__imp_RtlNtStatusToDosError
0x1800c1bb3  mov     ebx, eax
0x1800c1bb5  test    eax, eax
0x1800c1bb7  jz      short loc_1800C1BCF
0x1800c1bb9  cmp     eax, 13Dh
0x1800c1bbe  jz      short loc_1800C1BCF
0x1800c1bc0  test    eax, eax
0x1800c1bc2  jle     short loc_1800C1BD5
0x1800c1bc4  movzx   ebx, ax
0x1800c1bc7  or      ebx, 80070000h
0x1800c1bcd  jmp     short loc_1800C1BD5
0x1800c1bcf  mov     ebx, esi
0x1800c1bd1  bts     ebx, 1Ch
0x1800c1bd5  mov     [rsp+110h+dwFlags], 247h
0x1800c1bdd  jmp     loc_1800C1A43
0x1800c1be2  mov     r9d, 27h ; '''
0x1800c1be8  cmp     [rbp+57h+cbOutput], r12d
0x1800c1bec  jnz     short loc_1800C1BFB
0x1800c1bee  mov     [rsp+110h+dwFlags], 24Ch
0x1800c1bf6  jmp     loc_1800C1843
0x1800c1bfb  mov     esi, 252h
0x1800c1c00  lea     r8, sourceString
0x1800c1c07  lea     rdx, EFS_TRACE_START_EVENT
0x1800c1c0e  mov     [rsp+110h+dwFlags], esi
0x1800c1c12  call    fnEfsLogTrace1Strings
0x1800c1c17  mov     ecx, [rbp+57h+cbOutput]
0x1800c1c1a  lea     r9, [rbp+57h+var_48]
0x1800c1c1e  xor     r8d, r8d
0x1800c1c21  xor     edx, edx
0x1800c1c23  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800c1c28  mov     rcx, cs:g_hPublisher
0x1800c1c2f  lea     r9, sourceString
0x1800c1c36  mov     [rsp+110h+var_E0], esi
0x1800c1c3a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c1c41  mov     [rsp+110h+var_E8], 27h ; '''
0x1800c1c49  mov     r8, r14
0x1800c1c4c  mov     [rsp+110h+dwFlags], eax
0x1800c1c50  mov     ebx, eax
0x1800c1c52  call    fnEfsLogTrace1String1Dword
  ... truncated ...
```
