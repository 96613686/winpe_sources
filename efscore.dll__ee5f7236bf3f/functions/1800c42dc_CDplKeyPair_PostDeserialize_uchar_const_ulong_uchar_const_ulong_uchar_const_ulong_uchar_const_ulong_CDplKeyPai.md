# CDplKeyPair::PostDeserialize(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,CDplKeyPair::_DPL_KEY_PAIR_ID * const,int,ushort)

- ea: `0x1800c42dc`
- end: `0x1800c4f39`
- name: `?PostDeserialize@CDplKeyPair@@AEAAJPEBEK0K0K0KQEAU_DPL_KEY_PAIR_ID@1@HG@Z`
- size: `3165`
- prototype: `__int64 __usercall@<rax>(CDplKeyPair *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, const unsigned __int8 *@<r9>, size_t Size, const unsigned __int8 *Src, size_t, const unsigned __int8 *, size_t, struct _GUID *, int, unsigned __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c0150`

## callees

- `0x180004f86`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180089d38`
- `0x1800b494c`
- `0x1800c0854`
- `0x1800c42dc`
- `0x1800c8038`
- `0x1800d5af8`
- `0x1800d6064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4a9b`
- `CRYPT32!CryptProtectMemory` at `0x1800c495a`
- `CRYPT32!CryptProtectMemory` at `0x1800c4a8f`
- `CRYPT32!CryptProtectMemory` at `0x1800c495a`
- `CRYPT32!CryptProtectMemory` at `0x1800c4a8f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c4eb3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c4ec8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c4edd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c4eb3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c4ec8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c4edd`
- `bcrypt!BCryptGetProperty` at `0x1800c459b`
- `bcrypt!BCryptGetProperty` at `0x1800c4789`
- `bcrypt!BCryptGetProperty` at `0x1800c459b`
- `bcrypt!BCryptGetProperty` at `0x1800c4789`
- `bcrypt!BCryptSetProperty` at `0x1800c4530`
- `bcrypt!BCryptSetProperty` at `0x1800c4530`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c4499`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c46a5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c4721`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c4499`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c46a5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c4721`
- `ntdll!RtlNtStatusToDosError` at `0x1800c44ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800c4544`
- `ntdll!RtlNtStatusToDosError` at `0x1800c45b1`
- `ntdll!RtlNtStatusToDosError` at `0x1800c46bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c4735`
- `ntdll!RtlNtStatusToDosError` at `0x1800c479d`
- `ntdll!RtlNtStatusToDosError` at `0x1800c44ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800c4544`
- `ntdll!RtlNtStatusToDosError` at `0x1800c45b1`
- `ntdll!RtlNtStatusToDosError` at `0x1800c46bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800c4735`
- `ntdll!RtlNtStatusToDosError` at `0x1800c479d`

## pseudocode

```c
__int64 __fastcall CDplKeyPair::PostDeserialize(
        CDplKeyPair *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        size_t Size,
        const unsigned __int8 *Src,
        size_t a7,
        const unsigned __int8 *a8,
        size_t a9,
        struct _GUID *a10,
        int a11,
        unsigned __int16 a12)
{
  unsigned __int8 *v12; // r13
  void *v17; // rsi
  void *v18; // r12
  unsigned int v19; // ebx
  const unsigned __int8 *v20; // r12
  size_t v21; // r15
  size_t v22; // r13
  int v23; // esi
  signed int v24; // eax
  WCHAR *v25; // rcx
  void *v26; // r14
  void *v27; // r15
  void *v28; // rdi
  int v29; // esi
  signed int v30; // eax
  int Property; // eax
  int v32; // ecx
  int v33; // esi
  signed int v34; // eax
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
  unsigned int v45; // esi
  const unsigned __int8 *v46; // rdx
  int v47; // ecx
  DWORD v48; // r14d
  __int64 v49; // rax
  __int64 v50; // r8
  int v51; // eax
  int v52; // ecx
  signed int LastError; // eax
  DWORD v54; // esi
  __int64 v55; // rax
  __int64 v56; // r8
  int v57; // eax
  BOOL v58; // eax
  int v59; // ecx
  signed int v60; // eax
  int v61; // r12d
  int v62; // r15d
  int v63; // ecx
  struct _GUID *v64; // rax
  __int64 v65; // xmm1_8
  unsigned __int8 *v66; // rax
  char dwFlags; // [rsp+20h] [rbp-A9h]
  char dwFlagsa; // [rsp+20h] [rbp-A9h]
  void *v70; // [rsp+48h] [rbp-81h]
  void *v71; // [rsp+50h] [rbp-79h]
  void *v72; // [rsp+58h] [rbp-71h]
  LPCWSTR v73; // [rsp+60h] [rbp-69h]
  void *v74; // [rsp+68h] [rbp-61h]
  void *v75; // [rsp+70h] [rbp-59h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+78h] [rbp-51h] BYREF
  void *v77; // [rsp+80h] [rbp-49h] BYREF
  BCRYPT_ALG_HANDLE hObject; // [rsp+88h] [rbp-41h] BYREF
  UCHAR pbOutput[4]; // [rsp+90h] [rbp-39h] BYREF
  unsigned int v80; // [rsp+94h] [rbp-35h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+98h] [rbp-31h] BYREF
  void *pDataIn; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int8 *v83; // [rsp+A8h] [rbp-21h] BYREF
  void *v84; // [rsp+B0h] [rbp-19h] BYREF
  void *v85; // [rsp+B8h] [rbp-11h] BYREF
  void *v86; // [rsp+C0h] [rbp-9h] BYREF
  LPCWSTR pszAlgId; // [rsp+C8h] [rbp-1h] BYREF
  ULONG pcbResult; // [rsp+110h] [rbp+47h] BYREF
  int v89; // [rsp+118h] [rbp+4Fh] BYREF
  unsigned __int64 v90; // [rsp+120h] [rbp+57h]

  LODWORD(v90) = a3;
  v12 = 0;
  v75 = 0;
  v70 = 0;
  v85 = 0;
  pszAlgId = 0;
  v86 = 0;
  pDataIn = 0;
  hAlgorithm = 0;
  hObject = 0;
  v17 = 0;
  v74 = 0;
  v18 = 0;
  v77 = 0;
  v72 = 0;
  v84 = 0;
  v89 = 0;
  pcbResult = 0;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  v83 = 0;
  v80 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 23);
  if ( !a2 )
  {
    dwFlags = 29;
LABEL_3:
    v19 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 39, dwFlags);
LABEL_114:
    v26 = 0;
    v25 = 0;
    goto LABEL_115;
  }
  if ( !a4 )
  {
    dwFlags = 30;
    goto LABEL_3;
  }
  v20 = Src;
  if ( !Src )
  {
    dwFlagsa = 31;
LABEL_8:
    v19 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 39, dwFlagsa);
LABEL_113:
    v18 = 0;
    goto LABEL_114;
  }
  if ( !a8 )
  {
    dwFlagsa = 32;
    goto LABEL_8;
  }
  if ( !a10 )
  {
    dwFlagsa = 33;
    goto LABEL_8;
  }
  if ( a3 < 2 || !(_DWORD)Size || (v21 = (unsigned int)a7, !(_DWORD)a7) || (v22 = (unsigned int)a9, !(_DWORD)a9) || a12 )
  {
    v19 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 39, 41);
    goto LABEL_112;
  }
  if ( !(unsigned int)CDplUser::IsCurrentLockOwner(*(CDplUser **)(*((_QWORD *)this + 3) + 56LL)) )
  {
    v19 = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 39, 49);
LABEL_112:
    v12 = 0;
    goto LABEL_113;
  }
  v23 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( v23 )
  {
    v19 = 0;
    if ( v23 < 0 )
    {
      v24 = RtlNtStatusToDosError(v23);
      v19 = v24;
      if ( !v24 || v24 == 317 )
      {
        v19 = v23 | 0x10000000;
      }
      else if ( v24 > 0 )
      {
        v19 = (unsigned __int16)v24 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 59);
LABEL_28:
    v18 = 0;
    v25 = 0;
LABEL_29:
    v26 = 0;
    v17 = 0;
LABEL_30:
    v27 = 0;
    v28 = 0;
    v12 = 0;
    goto LABEL_117;
  }
  v29 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  if ( v29 )
  {
    v19 = 0;
    if ( v29 < 0 )
    {
      v30 = RtlNtStatusToDosError(v29);
      v19 = v30;
      if ( !v30 || v30 == 317 )
      {
        v19 = v29 | 0x10000000;
      }
      else if ( v30 > 0 )
      {
        v19 = (unsigned __int16)v30 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 70);
    goto LABEL_28;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  v33 = Property;
  if ( Property )
  {
    v28 = 0;
    v19 = 0;
    if ( Property < 0 )
    {
      v34 = RtlNtStatusToDosError(Property);
      v19 = v34;
      if ( !v34 || v34 == 317 )
      {
        v19 = v33 | 0x10000000;
      }
      else if ( v34 > 0 )
      {
        v19 = (unsigned __int16)v34 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 82);
    v25 = 0;
    goto LABEL_47;
  }
  fnEfsLogTrace1Strings(v32, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 91);
  v19 = CDplService::DuplicateSvcString(a2, 0xFFFFFFFFFFFFFFFFuLL, (unsigned int)v90, 1, (unsigned __int16 **)&pszAlgId);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v19,
              39,
              91) < 0 )
  {
    v25 = (WCHAR *)pszAlgId;
    v18 = 0;
    goto LABEL_29;
  }
  v73 = pszAlgId;
  v35 = BCryptOpenAlgorithmProvider(&hAlgorithm, pszAlgId, 0, 0);
  v19 = 0;
  v36 = v35;
  if ( v35 )
  {
    v28 = 0;
    if ( v35 < 0 )
    {
      v37 = RtlNtStatusToDosError(v35);
      v19 = v37;
      if ( !v37 || v37 == 317 )
      {
        v19 = v36 | 0x10000000;
      }
      else if ( v37 > 0 )
      {
        v19 = (unsigned __int16)v37 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 100);
LABEL_57:
    v25 = (WCHAR *)v73;
LABEL_47:
    v27 = 0;
    v26 = 0;
    v17 = 0;
    v18 = 0;
    v12 = 0;
    goto LABEL_117;
  }
  v38 = BCryptOpenAlgorithmProvider(&hObject, L"SP800_108_CTR_HMAC", 0, 0);
  v39 = v38;
  if ( v38 )
  {
    v28 = 0;
    if ( v38 < 0 )
    {
      v40 = RtlNtStatusToDosError(v38);
      v19 = v40;
      if ( !v40 || v40 == 317 )
      {
        v19 = v39 | 0x10000000;
      }
      else if ( v40 > 0 )
      {
        v19 = (unsigned __int16)v40 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 110);
    goto LABEL_57;
  }
  v41 = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&v89, 4u, &pcbResult, 0);
  v43 = v41;
  if ( v41 )
  {
    v28 = 0;
    if ( v41 < 0 )
    {
      v44 = RtlNtStatusToDosError(v41);
      v19 = v44;
      if ( !v44 || v44 == 317 )
      {
        v19 = v43 | 0x10000000;
      }
      else if ( v44 > 0 )
      {
        v19 = (unsigned __int16)v44 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 122);
    goto LABEL_57;
  }
  fnEfsLogTrace1Strings(v42, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 134);
  v45 = Size;
  v19 = DplibpMemAllocEx((unsigned int)Size, 0, 0, &v86);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v19,
              39,
              134) < 0 )
  {
    v18 = 0;
    v26 = v86;
    v17 = 0;
    goto LABEL_87;
  }
  v46 = a4;
  v26 = v86;
  v71 = v86;
  memcpy_0(v86, v46, v45);
  v17 = 0;
  if ( a11 )
  {
    v48 = (v21 + 15) & 0xFFFFFFF0;
    if ( v48 < (unsigned int)v21 )
    {
      v19 = -2147024809;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 39, 151);
      v25 = (WCHAR *)v73;
      v18 = 0;
      v26 = v71;
      v12 = 0;
LABEL_115:
      v28 = 0;
      goto LABEL_116;
    }
    fnEfsLogTrace1Strings(v47, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 158);
    v49 = *((_QWORD *)this + 3);
    if ( *(_DWORD *)(v49 + 136) || (v50 = 0, *(_DWORD *)(v49 + 204)) )
      v50 = 1;
    v19 = DplibpMemAllocEx(v48, 1, v50, &pDataIn);
    v51 = fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            v19,
            39,
            158);
    v17 = pDataIn;
    if ( v51 < 0 )
    {
      v18 = 0;
      goto LABEL_86;
    }
    v75 = pDataIn;
    memcpy_0(pDataIn, v20, v21);
    v18 = 0;
    if ( !CryptProtectMemory(v17, v48, 0) )
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 166);
      goto LABEL_86;
    }
    v54 = (v22 + 15) & 0xFFFFFFF0;
    if ( v54 < (unsigned int)v22 )
    {
      v19 = -2147024809;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 39, 180);
      v17 = v75;
LABEL_86:
      v26 = v71;
LABEL_87:
      v25 = (WCHAR *)v73;
      goto LABEL_30;
    }
    fnEfsLogTrace1Strings(v52, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 187);
    v55 = *((_QWORD *)this + 3);
    if ( *(_DWORD *)(v55 + 136) || (v56 = 0, *(_DWORD *)(v55 + 204)) )
      v56 = 1;
    v19 = DplibpMemAllocEx(v54, 1, v56, &v77);
    v57 = fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            v19,
            39,
            187);
    v18 = v77;
    if ( v57 < 0 )
    {
LABEL_98:
      v27 = 0;
      v17 = v75;
      v28 = 0;
      v26 = v71;
      v12 = 0;
      v25 = (WCHAR *)v73;
      goto LABEL_117;
    }
    v74 = v77;
    memcpy_0(v77, a8, v22);
    v58 = CryptProtectMemory(v18, v54, 0);
    v59 = 0;
    if ( !v58 )
    {
      v60 = GetLastError();
      v19 = v60;
      if ( v60 > 0 )
        v19 = (unsigned __int16)v60 | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 39, 195);
      goto LABEL_98;
    }
    LODWORD(v77) = v21;
    v61 = 0;
    v62 = 0;
  }
  else
  {
    fnEfsLogTrace1Strings(v47, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 209);
    v19 = DplibpMemAllocEx(v21, 0, 0, &v85);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v19,
                39,
                209) < 0 )
    {
      v28 = v85;
      v18 = 0;
      v25 = (WCHAR *)v73;
      v12 = 0;
LABEL_116:
      v27 = 0;
      goto LABEL_117;
    }
    v70 = v85;
    memcpy_0(v85, v20, v21);
    fnEfsLogTrace1Strings(v63, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 224);
    v19 = DplibpMemAllocEx(v22, 0, 0, &v84);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v19,
                39,
                224) < 0 )
    {
      v27 = v84;
      v17 = 0;
      v28 = v70;
      v18 = 0;
      v25 = (WCHAR *)v73;
      v12 = 0;
      goto LABEL_117;
    }
    v48 = 0;
    v54 = 0;
    LODWORD(v77) = 0;
    v61 = v21;
    v72 = v84;
    v62 = v22;
    memcpy_0(v84, a8, v22);
    LODWORD(v22) = 0;
  }
  fnEfsLogTrace1Strings(v59, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 236);
  v19 = CDplKeyPair::GenerateAuthData(this, *(_QWORD *)&a10[1].Data1, a10, &v83, &v80);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v19,
              39,
              236) < 0 )
  {
    v12 = v83;
    v18 = v74;
    v17 = v75;
    v26 = v71;
    v27 = v72;
    v25 = (WCHAR *)v73;
    v28 = v70;
  }
  else
  {
    CDplKeyPair::ReleaseKeyMaterial(this);
    *((_QWORD *)this + 12) = hAlgorithm;
    *((_QWORD *)this + 21) = hObject;
    *((_DWORD *)this + 44) = v89;
    v64 = a10;
    *((_WORD *)this + 82) = 0;
    hAlgorithm = 0;
    hObject = 0;
    *(struct _GUID *)((char *)this + 40) = *v64;
    v65 = *(_QWORD *)&v64[1].Data1;
    *((_DWORD *)this + 28) = v90;
    *((_QWORD *)this + 15) = v71;
    *((_DWORD *)this + 32) = Size;
    *((_QWORD *)this + 17) = v75;
    *((_DWORD *)this + 37) = (_DWORD)v77;
    *((_QWORD *)this + 23) = v74;
    *((_QWORD *)this + 25) = v72;
    *((_QWORD *)this + 27) = phAlgorithm;
    *((_DWORD *)this + 56) = *(_DWORD *)pbOutput;
    v66 = v83;
    *((_DWORD *)this + 36) = v48;
    *((_QWORD *)this + 13) = v73;
    v25 = 0;
    *((_QWORD *)this + 8) = v66;
    LODWORD(v66) = v80;
    *((_DWORD *)this + 40) = v61;
    v18 = 0;
    *((_DWORD *)this + 49) = v22;
    v12 = 0;
    *((_DWORD *)this + 52) = v62;
    v27 = 0;
    *((_DWORD *)this + 48) = v54;
    v17 = 0;
    *((_DWORD *)this + 18) = (_DWORD)v66;
    *((_QWORD *)this + 7) = v65;
    *((_QWORD *)this + 19) = v70;
    v28 = 0;
    phAlgorithm = 0;
    v26 = 0;
  }
LABEL_117:
  if ( v25 )
    DplibMemFree(v25);
  if ( v26 )
    DplibMemFree(v26);
  if ( v17 )
    DplibMemFree(v17);
  if ( v28 )
    DplibMemFree(v28);
  if ( v18 )
    DplibMemFree(v18);
  if ( v27 )
    DplibMemFree(v27);
  if ( v12 )
    DplibMemFree(v12);
  if ( hAlgorithm )
  {
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  if ( hObject )
  {
    BCryptCloseAlgorithmProvider(hObject, 0);
    hObject = 0;
  }
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v19,
    39,
    65);
  return v19;
}

```

## disassembly

```asm
0x1800c42dc  mov     [rsp-8+arg_18], rbx
0x1800c42e1  mov     dword ptr [rsp-8+arg_10], r8d
0x1800c42e6  push    rbp
0x1800c42e7  push    rsi
0x1800c42e8  push    rdi
0x1800c42e9  push    r12
0x1800c42eb  push    r13
0x1800c42ed  push    r14
0x1800c42ef  push    r15
0x1800c42f1  lea     rbp, [rsp-7]
0x1800c42f6  sub     rsp, 0D0h
0x1800c42fd  xor     r13d, r13d
0x1800c4300  mov     [rsp+100h+dwFlags], 717h
0x1800c4308  mov     eax, r13d
0x1800c430b  mov     [rbp+37h+var_90], r13
0x1800c430f  mov     r14, r9
0x1800c4312  mov     [rsp+100h+var_B8], rax
0x1800c4317  mov     r15d, r8d
0x1800c431a  mov     [rbp+37h+var_48], rax
0x1800c431e  mov     rbx, rdx
0x1800c4321  mov     [rbp+37h+pszAlgId], rax
0x1800c4325  lea     r9d, [r13+27h]
0x1800c4329  mov     [rbp+37h+var_40], rax
0x1800c432d  lea     r8, sourceString
0x1800c4334  mov     [rbp+37h+pDataIn], r13
0x1800c4338  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800c433f  mov     [rbp+37h+hAlgorithm], r13
0x1800c4343  mov     rdi, rcx
0x1800c4346  mov     [rbp+37h+hObject], r13
0x1800c434a  mov     esi, r13d
0x1800c434d  mov     [rbp+37h+var_98], r13
0x1800c4351  mov     r12d, r13d
0x1800c4354  mov     [rbp+37h+var_80], r13
0x1800c4358  mov     [rbp+37h+var_A8], rax
0x1800c435c  mov     [rbp+37h+var_50], rax
0x1800c4360  mov     [rbp+37h+arg_8], r13d
0x1800c4364  mov     [rbp+37h+pcbResult], r13d
0x1800c4368  mov     [rbp+37h+phAlgorithm], r13
0x1800c436c  mov     dword ptr [rbp+37h+pbOutput], r13d
0x1800c4370  mov     [rbp+37h+var_58], rax
0x1800c4374  mov     [rbp+37h+var_6C], r13d
0x1800c4378  call    fnEfsLogTrace1Strings
0x1800c437d  test    rbx, rbx
0x1800c4380  jnz     short loc_1800C43B3
0x1800c4382  mov     [rsp+100h+dwFlags], 71Dh
0x1800c438a  mov     rcx, cs:g_hPublisher
0x1800c4391  lea     rdx, EFS_TRACE_ERROR
0x1800c4398  mov     r9d, 27h ; '''
0x1800c439e  mov     r8d, 80070057h
0x1800c43a4  mov     ebx, 80070057h
0x1800c43a9  call    fnEfsLogTrace1
0x1800c43ae  jmp     loc_1800C4E41
0x1800c43b3  test    r14, r14
0x1800c43b6  jnz     short loc_1800C43C2
0x1800c43b8  mov     [rsp+100h+dwFlags], 71Eh
0x1800c43c0  jmp     short loc_1800C438A
0x1800c43c2  mov     r12, [rbp+37h+Src]
0x1800c43c6  test    r12, r12
0x1800c43c9  jnz     short loc_1800C43FC
0x1800c43cb  mov     [rsp+100h+dwFlags], 71Fh
0x1800c43d3  mov     rcx, cs:g_hPublisher
0x1800c43da  lea     rdx, EFS_TRACE_ERROR
0x1800c43e1  mov     r9d, 27h ; '''
0x1800c43e7  mov     r8d, 80070057h
0x1800c43ed  mov     ebx, 80070057h
0x1800c43f2  call    fnEfsLogTrace1
0x1800c43f7  jmp     loc_1800C4E3E
0x1800c43fc  cmp     [rbp+37h+arg_38], r13
0x1800c4400  jnz     short loc_1800C440C
0x1800c4402  mov     [rsp+100h+dwFlags], 720h
0x1800c440a  jmp     short loc_1800C43D3
0x1800c440c  cmp     [rbp+37h+arg_48], r13
0x1800c4413  jnz     short loc_1800C441F
0x1800c4415  mov     [rsp+100h+dwFlags], 721h
0x1800c441d  jmp     short loc_1800C43D3
0x1800c441f  cmp     r15d, 2
0x1800c4423  jb      loc_1800C4E0F
0x1800c4429  cmp     dword ptr [rbp+37h+Size], r13d
0x1800c442d  jz      loc_1800C4E0F
0x1800c4433  mov     r15d, dword ptr [rbp+37h+arg_30]
0x1800c4437  test    r15d, r15d
0x1800c443a  jz      loc_1800C4E0F
0x1800c4440  mov     r13d, dword ptr [rbp+37h+arg_40]
0x1800c4447  xor     eax, eax
0x1800c4449  test    r13d, r13d
0x1800c444c  jz      loc_1800C4E0F
0x1800c4452  cmp     [rbp+37h+arg_58], ax
0x1800c4459  jnz     loc_1800C4E0F
0x1800c445f  mov     rcx, [rdi+18h]
0x1800c4463  mov     rcx, [rcx+38h]; this
0x1800c4467  call    ?IsCurrentLockOwner@CDplUser@@AEAAHXZ; CDplUser::IsCurrentLockOwner(void)
0x1800c446c  test    eax, eax
0x1800c446e  jnz     short loc_1800C4488
0x1800c4470  mov     ebx, 8000FFFFh
0x1800c4475  mov     [rsp+100h+dwFlags], 731h
0x1800c447d  mov     r8d, 8000FFFFh
0x1800c4483  jmp     loc_1800C4E22
0x1800c4488  xor     r9d, r9d; dwFlags
0x1800c448b  lea     rdx, pszAlgId; "AES"
0x1800c4492  xor     r8d, r8d; pszImplementation
0x1800c4495  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x1800c4499  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c449f  mov     esi, eax
0x1800c44a1  xor     eax, eax
0x1800c44a3  test    esi, esi
0x1800c44a5  jz      short loc_1800C4514
0x1800c44a7  mov     ebx, eax
0x1800c44a9  jns     short loc_1800C44D5
0x1800c44ab  mov     ecx, esi; Status
0x1800c44ad  call    cs:__imp_RtlNtStatusToDosError
0x1800c44b3  mov     ebx, eax
0x1800c44b5  test    eax, eax
0x1800c44b7  jz      short loc_1800C44CF
0x1800c44b9  cmp     eax, 13Dh
0x1800c44be  jz      short loc_1800C44CF
0x1800c44c0  test    eax, eax
0x1800c44c2  jle     short loc_1800C44D5
0x1800c44c4  movzx   ebx, bx
0x1800c44c7  or      ebx, 80070000h
0x1800c44cd  jmp     short loc_1800C44D5
0x1800c44cf  mov     ebx, esi
0x1800c44d1  bts     ebx, 1Ch
0x1800c44d5  mov     [rsp+100h+dwFlags], 73Bh
0x1800c44dd  mov     rcx, cs:g_hPublisher
0x1800c44e4  lea     rdx, EFS_TRACE_ERROR
0x1800c44eb  mov     r9d, 27h ; '''
0x1800c44f1  mov     r8d, ebx
0x1800c44f4  call    fnEfsLogTrace1
0x1800c44f9  mov     r12, [rbp+37h+var_98]
0x1800c44fd  mov     rcx, r12
0x1800c4500  mov     r14, r12
0x1800c4503  mov     rsi, r12
0x1800c4506  mov     r15, r12
0x1800c4509  mov     rdi, r12
0x1800c450c  mov     r13, r12
0x1800c450f  jmp     loc_1800C4E4D
0x1800c4514  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x1800c4518  lea     r8, pbInput; "ChainingModeCBC"
0x1800c451f  mov     r9d, 20h ; ' '; cbInput
0x1800c4525  mov     [rsp+100h+dwFlags], eax; dwFlags
0x1800c4529  lea     rdx, aChainingmode; "ChainingMode"
0x1800c4530  call    cs:__imp_BCryptSetProperty
0x1800c4536  mov     esi, eax
0x1800c4538  xor     eax, eax
0x1800c453a  test    esi, esi
0x1800c453c  jz      short loc_1800C4579
0x1800c453e  mov     ebx, eax
0x1800c4540  jns     short loc_1800C456C
0x1800c4542  mov     ecx, esi; Status
0x1800c4544  call    cs:__imp_RtlNtStatusToDosError
0x1800c454a  mov     ebx, eax
0x1800c454c  test    eax, eax
0x1800c454e  jz      short loc_1800C4566
0x1800c4550  cmp     eax, 13Dh
0x1800c4555  jz      short loc_1800C4566
0x1800c4557  test    eax, eax
0x1800c4559  jle     short loc_1800C456C
0x1800c455b  movzx   ebx, bx
0x1800c455e  or      ebx, 80070000h
0x1800c4564  jmp     short loc_1800C456C
0x1800c4566  mov     ebx, esi
0x1800c4568  bts     ebx, 1Ch
0x1800c456c  mov     [rsp+100h+dwFlags], 746h
0x1800c4574  jmp     loc_1800C44DD
0x1800c4579  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x1800c457d  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x1800c4581  mov     [rsp+100h+var_D8], eax; dwFlags
0x1800c4585  lea     rdx, aObjectlength; "ObjectLength"
0x1800c458c  lea     rax, [rbp+37h+pcbResult]
0x1800c4590  mov     r9d, 4; cbOutput
0x1800c4596  mov     qword ptr [rsp+100h+dwFlags], rax; pcbResult
0x1800c459b  call    cs:__imp_BCryptGetProperty
0x1800c45a1  mov     esi, eax
0x1800c45a3  test    eax, eax
0x1800c45a5  jz      short loc_1800C4614
0x1800c45a7  xor     edi, edi
0x1800c45a9  mov     ebx, edi
0x1800c45ab  test    eax, eax
0x1800c45ad  jns     short loc_1800C45D9
0x1800c45af  mov     ecx, eax; Status
0x1800c45b1  call    cs:__imp_RtlNtStatusToDosError
0x1800c45b7  mov     ebx, eax
0x1800c45b9  test    eax, eax
0x1800c45bb  jz      short loc_1800C45D3
0x1800c45bd  cmp     eax, 13Dh
0x1800c45c2  jz      short loc_1800C45D3
0x1800c45c4  test    eax, eax
0x1800c45c6  jle     short loc_1800C45D9
0x1800c45c8  movzx   ebx, ax
0x1800c45cb  or      ebx, 80070000h
0x1800c45d1  jmp     short loc_1800C45D9
0x1800c45d3  mov     ebx, esi
0x1800c45d5  bts     ebx, 1Ch
0x1800c45d9  mov     rcx, cs:g_hPublisher
0x1800c45e0  lea     rdx, EFS_TRACE_ERROR
0x1800c45e7  mov     r9d, 27h ; '''
0x1800c45ed  mov     [rsp+100h+dwFlags], 752h
0x1800c45f5  mov     r8d, ebx
0x1800c45f8  call    fnEfsLogTrace1
0x1800c45fd  mov     rcx, rdi
0x1800c4600  mov     r15, rdi
0x1800c4603  mov     r14, rdi
0x1800c4606  mov     rsi, rdi
0x1800c4609  mov     r12, rdi
0x1800c460c  mov     r13, rdi
0x1800c460f  jmp     loc_1800C4E4D
0x1800c4614  mov     esi, 75Bh
0x1800c4619  lea     r8, sourceString
0x1800c4620  mov     r9d, 27h ; '''
0x1800c4626  mov     [rsp+100h+dwFlags], esi
0x1800c462a  lea     rdx, EFS_TRACE_START_EVENT
0x1800c4631  call    fnEfsLogTrace1Strings
0x1800c4636  mov     r8d, dword ptr [rbp+37h+arg_10]; unsigned __int64
0x1800c463a  lea     rax, [rbp+37h+pszAlgId]
0x1800c463e  mov     r9d, 1; int
0x1800c4644  mov     qword ptr [rsp+100h+dwFlags], rax; unsigned __int16 **
0x1800c4649  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1800c464d  mov     rcx, rbx; unsigned __int16 *
0x1800c4650  call    ?DuplicateSvcString@CDplService@@SAJPEBG_K1HPEAPEAG@Z; CDplService::DuplicateSvcString(ushort const *,unsigned __int64,unsigned __int64,int,ushort * *)
0x1800c4655  mov     rcx, cs:g_hPublisher
0x1800c465c  lea     r9, sourceString
0x1800c4663  mov     [rsp+100h+var_D0], esi
0x1800c4667  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c466e  mov     [rsp+100h+var_D8], 27h ; '''
0x1800c4676  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c467d  mov     [rsp+100h+dwFlags], eax
0x1800c4681  mov     ebx, eax
0x1800c4683  call    fnEfsLogTrace1String1Dword
0x1800c4688  test    eax, eax
0x1800c468a  js      loc_1800C4E02
0x1800c4690  mov     rax, [rbp+37h+pszAlgId]
0x1800c4694  lea     rcx, [rbp+37h+hAlgorithm]; phAlgorithm
0x1800c4698  mov     rdx, rax; pszAlgId
0x1800c469b  mov     [rbp+37h+var_A0], rax
0x1800c469f  xor     r9d, r9d; dwFlags
0x1800c46a2  xor     r8d, r8d; pszImplementation
0x1800c46a5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c46ab  xor     ebx, ebx
0x1800c46ad  mov     esi, eax
0x1800c46af  test    eax, eax
0x1800c46b1  jz      short loc_1800C4710
0x1800c46b3  xor     edi, edi
0x1800c46b5  test    eax, eax
0x1800c46b7  jns     short loc_1800C46E3
0x1800c46b9  mov     ecx, eax; Status
0x1800c46bb  call    cs:__imp_RtlNtStatusToDosError
0x1800c46c1  mov     ebx, eax
0x1800c46c3  test    eax, eax
0x1800c46c5  jz      short loc_1800C46DD
0x1800c46c7  cmp     eax, 13Dh
0x1800c46cc  jz      short loc_1800C46DD
0x1800c46ce  test    eax, eax
0x1800c46d0  jle     short loc_1800C46E3
0x1800c46d2  movzx   ebx, ax
0x1800c46d5  or      ebx, 80070000h
0x1800c46db  jmp     short loc_1800C46E3
0x1800c46dd  mov     ebx, esi
0x1800c46df  bts     ebx, 1Ch
0x1800c46e3  mov     [rsp+100h+dwFlags], 764h
0x1800c46eb  mov     rcx, cs:g_hPublisher
0x1800c46f2  lea     rdx, EFS_TRACE_ERROR
0x1800c46f9  mov     r9d, 27h ; '''
0x1800c46ff  mov     r8d, ebx
0x1800c4702  call    fnEfsLogTrace1
0x1800c4707  mov     rcx, [rbp+37h+var_A0]
0x1800c470b  jmp     loc_1800C4600
0x1800c4710  xor     r9d, r9d; dwFlags
0x1800c4713  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x1800c471a  xor     r8d, r8d; pszImplementation
0x1800c471d  lea     rcx, [rbp+37h+hObject]; phAlgorithm
0x1800c4721  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c4727  mov     esi, eax
0x1800c4729  test    eax, eax
0x1800c472b  jz      short loc_1800C4767
0x1800c472d  xor     edi, edi
0x1800c472f  test    eax, eax
0x1800c4731  jns     short loc_1800C475D
0x1800c4733  mov     ecx, eax; Status
0x1800c4735  call    cs:__imp_RtlNtStatusToDosError
0x1800c473b  mov     ebx, eax
0x1800c473d  test    eax, eax
0x1800c473f  jz      short loc_1800C4757
0x1800c4741  cmp     eax, 13Dh
0x1800c4746  jz      short loc_1800C4757
0x1800c4748  test    eax, eax
0x1800c474a  jle     short loc_1800C475D
0x1800c474c  movzx   ebx, ax
0x1800c474f  or      ebx, 80070000h
0x1800c4755  jmp     short loc_1800C475D
0x1800c4757  mov     ebx, esi
0x1800c4759  bts     ebx, 1Ch
0x1800c475d  mov     [rsp+100h+dwFlags], 76Eh
0x1800c4765  jmp     short loc_1800C46EB
0x1800c4767  mov     rcx, [rbp+37h+hObject]; hObject
0x1800c476b  lea     rax, [rbp+37h+pcbResult]
0x1800c476f  mov     [rsp+100h+var_D8], ebx; dwFlags
0x1800c4773  lea     r8, [rbp+37h+arg_8]; pbOutput
0x1800c4777  mov     r9d, 4; cbOutput
0x1800c477d  mov     qword ptr [rsp+100h+dwFlags], rax; pcbResult
0x1800c4782  lea     rdx, aObjectlength; "ObjectLength"
  ... truncated ...
```
