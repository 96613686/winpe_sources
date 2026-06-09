# GetMasterKey(void *,ulong,ushort const *,void *,_LUID *,int,ushort * const,DP_KEK *,DP_KEK *,uchar * *,ulong *,ulong *)

- ea: `0x18000e9c0`
- end: `0x18000f907`
- name: `?GetMasterKey@@YAHPEAXKPEBG0PEAU_LUID@@HQEAGPEAUDP_KEK@@4PEAPEAEPEAK6@Z`
- size: `3911`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned __int16 *, void *, struct _LUID *, int, unsigned __int16 *const, struct DP_KEK *, struct DP_KEK *, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e87c`
- `0x18002e310`

## callees

- `0x1800048a4`
- `0x180004c68`
- `0x180004d80`
- `0x180005a2c`
- `0x1800063c0`
- `0x180006510`
- `0x180006c60`
- `0x180007f10`
- `0x18000a7a0`
- `0x18000abf0`
- `0x18000ad44`
- `0x18000b558`
- `0x18000b5cc`
- `0x18000b638`
- `0x18000bc70`
- `0x18000e3f0`
- `0x18000e470`
- `0x18000e9c0`
- `0x180012258`
- `0x180012da4`
- `0x180013f2c`
- `0x18001866c`
- `0x180019f40`
- `0x18001ac4c`
- `0x18001b234`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x1800244b8`
- `0x18002a794`
- `0x18002ac04`
- `0x18002ad50`
- `0x18002afc0`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f534`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f534`
- `RPCRT4!UuidFromStringW` at `0x18000f3ec`
- `RPCRT4!UuidFromStringW` at `0x18000f3ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f20e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f20e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f3c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f3c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eb26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ec97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eb26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ec97`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000ec4f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000ec4f`

## string_xrefs

- `0x18000eb78`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18000ebee`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18000f230`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18000f4c2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18000f75a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall GetMasterKey(
        unsigned __int16 *a1,
        int a2,
        unsigned __int16 *a3,
        void *a4,
        struct _LUID *a5,
        int a6,
        unsigned __int16 *const a7,
        struct DP_KEK *a8,
        struct DP_KEK *a9,
        unsigned __int8 **a10,
        unsigned int *a11,
        unsigned int *a12)
{
  int MasterKey; // r13d
  unsigned int v15; // r12d
  __int64 v16; // rbx
  __int64 v17; // rax
  SIZE_T v18; // rsi
  unsigned __int16 *v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  char LastError; // al
  void *v25; // rcx
  unsigned __int16 *v26; // rax
  unsigned __int16 *v28; // rsi
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int64 v33; // rbx
  unsigned int v34; // r14d
  unsigned int v35; // esi
  unsigned int v36; // ebx
  unsigned int v37; // r14d
  unsigned __int8 *v38; // r8
  __int64 v39; // r12
  int v40; // eax
  int MasterKeyUserEncryptionKey; // esi
  unsigned int v42; // r9d
  unsigned int v43; // r14d
  unsigned int v44; // eax
  unsigned int v45; // ebx
  BOOL v46; // edx
  struct _GUID v47; // xmm6
  unsigned int v48; // eax
  unsigned int v49; // esi
  int v50; // eax
  void *v51; // r8
  unsigned int v52; // r9d
  int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  DWORD v56; // eax
  char v57; // al
  int v58; // edx
  UCHAR *v59; // rax
  unsigned __int16 *v60; // r13
  int v61; // esi
  char v62; // al
  __int64 v63; // rcx
  unsigned __int8 *v64; // rax
  unsigned int v65; // eax
  int v66; // eax
  unsigned int *v67; // r14
  unsigned __int8 **v68; // rsi
  unsigned int v69; // eax
  unsigned int v70; // eax
  HANDLE CurrentThread; // rax
  unsigned int v72; // eax
  __int64 v73; // r9
  __int64 v74; // rcx
  int v75; // eax
  int v76; // esi
  struct _GUID v77; // xmm0
  unsigned int v78; // esi
  __int64 v79; // r9
  __m128i v80; // xmm0
  unsigned int *v81; // r14
  int v82; // eax
  int v83; // ebx
  unsigned int v84; // eax
  void *v85; // rcx
  unsigned int v86; // ebx
  UCHAR *v87; // rax
  unsigned __int16 **v88; // [rsp+28h] [rbp-E0h]
  size_t v89; // [rsp+48h] [rbp-C0h]
  int v90; // [rsp+68h] [rbp-A0h] BYREF
  int v91; // [rsp+6Ch] [rbp-9Ch]
  unsigned int v92; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v93; // [rsp+74h] [rbp-94h]
  int v94; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v95; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v96; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v97; // [rsp+84h] [rbp-84h] BYREF
  unsigned int v98; // [rsp+88h] [rbp-80h]
  unsigned int *v99; // [rsp+90h] [rbp-78h]
  unsigned int v100; // [rsp+98h] [rbp-70h]
  unsigned int *v101; // [rsp+A0h] [rbp-68h]
  unsigned __int8 **v102; // [rsp+A8h] [rbp-60h]
  unsigned int v103; // [rsp+B0h] [rbp-58h] BYREF
  void *v104; // [rsp+B8h] [rbp-50h]
  struct _LUID v105[2]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 *v106; // [rsp+D8h] [rbp-30h]
  _BYTE Buf1[20]; // [rsp+E8h] [rbp-20h] BYREF
  int v108; // [rsp+108h] [rbp+0h] BYREF
  struct DP_KEK *v109; // [rsp+110h] [rbp+8h]
  void *Src; // [rsp+118h] [rbp+10h]
  _BYTE v111[4]; // [rsp+128h] [rbp+20h] BYREF
  int v112; // [rsp+12Ch] [rbp+24h]
  unsigned __int16 *v113; // [rsp+130h] [rbp+28h] BYREF
  unsigned __int16 StringUuid[8]; // [rsp+138h] [rbp+30h] BYREF
  __int128 v115; // [rsp+148h] [rbp+40h]
  __int128 v116; // [rsp+158h] [rbp+50h]
  __int128 v117; // [rsp+168h] [rbp+60h]
  __int128 v118; // [rsp+178h] [rbp+70h]
  unsigned int v119; // [rsp+188h] [rbp+80h]
  unsigned int v120; // [rsp+18Ch] [rbp+84h]
  unsigned __int8 *v121; // [rsp+190h] [rbp+88h]
  unsigned int v122; // [rsp+1A8h] [rbp+A0h]
  __m128i *v123; // [rsp+1B0h] [rbp+A8h]
  struct _GUID v124; // [rsp+1C8h] [rbp+C0h] BYREF
  UUID Uuid; // [rsp+1D8h] [rbp+D0h] BYREF
  UCHAR pbSecret[24]; // [rsp+1E8h] [rbp+E0h] BYREF

  v109 = a9;
  *(_QWORD *)&Uuid.Data1 = a5;
  v105[0] = (struct _LUID)a8;
  v102 = a10;
  Src = a3;
  v96 = a2;
  v101 = a11;
  v104 = a4;
  v106 = a7;
  v99 = a12;
  memset_0(v111, 0, 0xA0u);
  MasterKey = 0;
  v94 = 0;
  v100 = 26128;
  v98 = 32782;
  v97 = 0;
  v108 = 0;
  v90 = 0;
  v92 = 0;
  v124 = 0;
  if ( a1 )
  {
    v15 = *((_DWORD *)a1 + 13);
    v93 = *((_DWORD *)a1 + 14);
  }
  else
  {
    v15 = 26128;
    v93 = 32782;
  }
  v95 = v15;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      81,
      (unsigned int)WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      (_DWORD)a3,
      (__int64)a7);
  *a12 = 6;
  memset_0(v111, 0, 0xA0u);
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( a3[v17] );
  v18 = (unsigned int)(2 * v17 + 2);
  v19 = (unsigned __int16 *)LocalAlloc(0, v18);
  v113 = v19;
  if ( !v19 )
  {
    SetLastError(0x46Au);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ERROR_NOT_ENOUGH_SERVER_MEMORY",
        106,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        166);
    return 0;
  }
  memcpy_0(v19, a3, v18);
  v20 = *((_OWORD *)a7 + 1);
  *(_OWORD *)StringUuid = *(_OWORD *)a7;
  v21 = *((_OWORD *)a7 + 2);
  v115 = v20;
  v22 = *((_OWORD *)a7 + 3);
  v116 = v21;
  v23 = *((_OWORD *)a7 + 4);
  v117 = v22;
  v118 = v23;
  if ( !(unsigned int)ReadMasterKey(a1, (struct MASTERKEY_STORED *)v111) )
  {
    LastError = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"GetLastError()",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        179);
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
      goto LABEL_31;
    CPSOverrideToLocalSystem(a1, 0, &v90);
    CPSQueryWellKnownAccount(v25, &v92);
    if ( v92 != 18 || v90 )
      goto LABEL_31;
    v26 = (unsigned __int16 *)LocalAlloc(0, v18);
    v113 = v26;
    if ( !v26 )
    {
      SetLastError(0x46Au);
      DebugTraceError(
        1130,
        "ERROR_NOT_ENOUGH_SERVER_MEMORY",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        3277);
      return 0;
    }
    memcpy_0(v26, Src, v18);
    v28 = v106;
    v29 = *((_OWORD *)v106 + 1);
    *(_OWORD *)StringUuid = *(_OWORD *)v106;
    v30 = *((_OWORD *)v106 + 2);
    v115 = v29;
    v31 = *((_OWORD *)v106 + 3);
    v116 = v30;
    v32 = *((_OWORD *)v106 + 4);
    v117 = v31;
    v118 = v32;
    do
      ++v16;
    while ( v113[v16] );
    if ( (unsigned int)v16 < 5
      || (v33 = (unsigned int)(v16 - 5), v113[v33] != 85)
      || (v113[v33] = 0, (MasterKey = ReadMasterKey(a1, (struct MASTERKEY_STORED *)v111)) == 0) )
    {
LABEL_31:
      SetLastError(0x80090003);
      *v99 = 3;
      return 0;
    }
    v113[v33] = 85;
    v112 = 1;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 82, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v28);
  }
  v92 = 0;
  v124 = 0;
  if ( !v120 || !v121 )
    goto LABEL_44;
  if ( *(_DWORD *)v121 > 1u )
  {
    v34 = *((_DWORD *)v121 + 6);
    v35 = *((_DWORD *)v121 + 7);
    v36 = *((_DWORD *)v121 + 5);
    if ( v36 >= GetIterationCount(v34)
      && (v35 != 26625 || v15 != 26115 && v15 != 26128)
      && (v35 != 26115 || v15 != 26128)
      && (v34 != 32777 || v93 != 32782) )
    {
      v98 = v34;
      v100 = v35;
LABEL_44:
      v37 = v93;
      goto LABEL_45;
    }
  }
  v37 = v93;
  v98 = v93;
  v100 = v15;
LABEL_45:
  v38 = 0;
  v39 = 20;
  if ( !*(_QWORD *)v105 )
  {
    MasterKeyUserEncryptionKey = 0;
LABEL_51:
    v90 = MasterKeyUserEncryptionKey;
    v91 = 0;
    v45 = -2146893821;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 86, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
      v38 = 0;
    }
    v43 = v95;
    goto LABEL_55;
  }
  v40 = ComputeMasterKeyUserEncryptionKey(
          a1,
          v104,
          (v119 >> 2) & 1,
          (unsigned __int8 *const)(*(_QWORD *)v105 + 20LL),
          (unsigned __int8 *const)(*(_QWORD *)v105 + 40LL),
          pbSecret);
  v38 = 0;
  v90 = v40;
  MasterKeyUserEncryptionKey = v40;
  if ( !v40 )
    goto LABEL_51;
  v42 = v37;
  v43 = v95;
  *(struct _GUID *)&v105[0].LowPart = v124;
  v44 = DecryptMasterKeyFromStorage(
          (struct MASTERKEY_STORED *)v111,
          0,
          v95,
          v42,
          pbSecret,
          0x14u,
          &v94,
          v102,
          v101,
          (struct _GUID *)v105,
          a1);
  v38 = 0;
  v45 = v44;
  v46 = v44 == 0;
  v91 = v46;
  if ( !v44 )
    goto LABEL_84;
LABEL_55:
  if ( (v96 & 1) == 0 )
  {
    MasterKeyUserEncryptionKey = GetMasterKeyUserEncryptionKey(a1, &v124, v104, (v119 & 4 | 8) >> 2, pbSecret, &v97);
    v90 = MasterKeyUserEncryptionKey;
    v38 = 0;
  }
  if ( !MasterKeyUserEncryptionKey )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      v56 = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 91, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v56);
    }
    if ( GetLastError() == 1364 )
    {
      v57 = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v58,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"GetLastError()",
          v57,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          166);
      FreeMasterKey((struct MASTERKEY_STORED *)v111);
      v59 = pbSecret;
      do
      {
        *v59++ = 0;
        --v39;
      }
      while ( v39 );
      return 0;
    }
    v38 = 0;
    goto LABEL_83;
  }
  v105[0].LowPart = 0;
  v103 = 0;
  v95 = 0;
  if ( v120 && (v38 = v121) != 0 )
  {
    v47 = v124;
    v48 = DecryptMasterKeyToMemoryEx(
            pbSecret,
            0x14u,
            v121,
            v120,
            (void *(*)(unsigned __int64))v88,
            v102,
            v101,
            (unsigned int *)v105,
            &v103,
            &v95);
    v45 = v48;
    if ( v48 )
    {
      *(struct _GUID *)Buf1 = v47;
      CheckFailedMasterKeyDecryption(StringUuid, (struct _GUID *)Buf1, pbSecret, a1 + 40, v48);
    }
    v49 = v93;
    v50 = CheckIfUpgradeNeeded(v43, v93, v105[0].LowPart, v103, v95);
    v38 = 0;
    v94 = v50;
    if ( !v45 )
      goto LABEL_83;
  }
  else
  {
    v49 = v93;
    v45 = -2146893821;
  }
  if ( !MasterKey )
    goto LABEL_83;
  v51 = v104;
  v52 = v119 & 4 | 8;
  *((_DWORD *)a1 + 4) = 1;
  v53 = GetMasterKeyUserEncryptionKey(a1, &v124, v51, v52 >> 2, pbSecret, &v97);
  v38 = 0;
  v90 = v53;
  *((_DWORD *)a1 + 4) = 0;
  if ( !v53
    || (*(struct _GUID *)Buf1 = v124,
        v54 = DecryptMasterKeyFromStorage(
                (struct MASTERKEY_STORED *)v111,
                0,
                v43,
                v49,
                pbSecret,
                0x14u,
                &v94,
                v102,
                v101,
                (struct _GUID *)Buf1,
                a1),
        v38 = 0,
        (v45 = v54) != 0) )
  {
LABEL_83:
    v46 = v91;
LABEL_84:
    v55 = v92;
    goto LABEL_85;
  }
  v55 = 1;
  v92 = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) == 0 )
  {
    v46 = v91;
  }
  else
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 88, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v106);
    v46 = v91;
    v55 = 1;
    v38 = 0;
  }
LABEL_85:
  v60 = (unsigned __int16 *)v38;
  v61 = v94;
  if ( v109 != (struct DP_KEK *)v38 )
    v61 = 1;
  v94 = v61;
  if ( !v61 && a6 == (_DWORD)v38 && !v46 && !v55 && !v45 )
    goto LABEL_160;
  v62 = v96;
  if ( (v96 & 0x8000000) != 0 )
  {
    v63 = 20;
    v64 = &qword_18004CCF8;
    do
    {
      *v64++ = (unsigned __int8)v38;
      --v63;
    }
    while ( v63 );
    *(struct _GUID *)Buf1 = v124;
    v65 = DecryptMasterKeyFromStorage(
            (struct MASTERKEY_STORED *)v111,
            0,
            v43,
            v93,
            &qword_18004CCF8,
            0x14u,
            &v94,
            v102,
            v101,
            (struct _GUID *)Buf1,
            a1);
    v61 = v94;
    v38 = 0;
    v45 = v65;
    if ( !v65 )
    {
      v66 = 1;
      v91 = 1;
      goto LABEL_112;
    }
    v62 = v96;
    goto LABEL_99;
  }
  if ( v45 )
  {
LABEL_99:
    if ( (v62 & 1) == 0 )
    {
      v67 = v101;
      v68 = v102;
      v69 = RestoreMasterKey(
              a1,
              v104,
              *(struct _LUID **)&Uuid.Data1,
              (struct MASTERKEY_STORED *)v111,
              v45,
              &v124,
              v102,
              v101);
      v38 = 0;
      v45 = v69;
      if ( v69 )
      {
        v105[0] = 0;
        Uuid = 0;
        v70 = CPSImpersonateClient(a1);
        v38 = 0;
        if ( !v70 )
        {
          CurrentThread = GetCurrentThread();
          if ( (unsigned int)GetThreadAuthenticationId(CurrentThread, v105)
            && !UuidFromStringW(StringUuid, &Uuid)
            && (unsigned int)SearchMasterKeyCache(v105, (const unsigned __int16 *)Src, &Uuid, v68, v67) )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 93, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
            }
            v45 = 0;
          }
          CPSRevertToSelf(a1);
          v38 = 0;
        }
      }
      v61 = 1;
    }
  }
  v66 = v91;
LABEL_112:
  if ( a6 == (_DWORD)v38 )
  {
    if ( !v66 && v109 == (struct DP_KEK *)v38 && v92 == (_DWORD)v38 || v45 )
      goto LABEL_118;
  }
  else
  {
    if ( v45 )
    {
LABEL_118:
      v75 = v90;
      goto LABEL_119;
    }
    v119 = (unsigned int)v38;
    InitializeMasterKeyPolicy(a1, (struct MASTERKEY_STORED *)v111, &v108);
    v60 = v113;
    v113 = 0;
    v72 = CPSGetUserStorageArea(a1, 0, 1u, 1, &v113);
    v45 = v72;
    if ( v72 )
    {
      v73 = 3620;
      v74 = v72;
LABEL_116:
      DebugTraceError(v74, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v73);
LABEL_117:
      LODWORD(v38) = 0;
      goto LABEL_118;
    }
    if ( !(unsigned int)_o__wcsicmp(v60, v113) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 94, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
      v45 = 87;
      v73 = 3630;
      v74 = 87;
      goto LABEL_116;
    }
    PersistMasterKeyToStorage((struct MASTERKEY_STORED *)v111, 3u, 0, 0);
    PersistMasterKeyToStorage((struct MASTERKEY_STORED *)v111, 2u, 0, 0);
  }
  if ( !v109 )
  {
    v75 = GetMasterKeyUserEncryptionKey(a1, &v124, 0, (v119 & 4 | 8) >> 2, pbSecret, &v97);
    v90 = v75;
    LODWORD(v38) = 0;
    goto LABEL_119;
  }
  v77 = *(struct _GUID *)v109;
  v97 = *((_DWORD *)v109 + 4);
  v124 = v77;
  v75 = ComputeMasterKeyUserEncryptionKey(
          a1,
          v104,
          (v119 >> 2) & 1,
          (unsigned __int8 *const)v109 + 20,
          (unsigned __int8 *const)v109 + 20,
          pbSecret);
  LODWORD(v38) = 0;
  v90 = v75;
  if ( !v75 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 95, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    goto LABEL_117;
  }
LABEL_119:
  if ( !v61 && a6 == (_DWORD)v38 && !v91 && v92 == (_DWORD)v38 )
  {
    if ( v45 )
      goto LABEL_124;
    goto LABEL_160;
  }
  if ( v45 )
  {
LABEL_124:
    v76 = (int)v38;
    if ( v45 == -2146892987 )
    {
      *v99 = 4;
    }
    else if ( v45 == 1131 )
    {
      *v99 = 5;
    }
    else
    {
      *v99 = 3;
    }
    goto LABEL_169;
  }
  if ( !v75 )
    goto LABEL_160;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 96, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v106);
  v78 = v100;
  LODWORD(v89) = *v101;
  v45 = EncryptMasterKeyToStorage((struct MASTERKEY_STORED *)v111, 0, v100, v98, pbSecret, 0x14u, v97, *v102, v89);
  if ( v45 )
  {
    v79 = 3726;
LABEL_152:
    DebugTraceError(v45, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v79);
    LODWORD(v38) = 0;
    goto LABEL_124;
  }
  if ( a6 )
  {
    v45 = BuildLocalKey(a1, (struct MASTERKEY_STORED *)v111, v78, v98);
    if ( v45 )
    {
      v79 = 3733;
      goto LABEL_152;
    }
  }
  *(struct _GUID *)Buf1 = v124;
  LogMasterKeyDescription(StringUuid, (struct _GUID *)Buf1, pbSecret, a1 + 40);
  LODWORD(v38) = 0;
  if ( v123 )
  {
    if ( v122 >= 0x14 )
    {
      v80 = *v123;
      *(_DWORD *)&Buf1[16] = v123[1].m128i_i32[0];
      *(__m128i *)Buf1 = v80;
      if ( _mm_cvtsi128_si32(v80) == 3 )
      {
        *(struct _GUID *)&Buf1[4] = v124;
        PersistMasterKeyToStorage((struct MASTERKEY_STORED *)v111, 2u, Buf1, 0x14u);
        v81 = v99;
        v96 = 0;
        goto LABEL_161;
      }
    }
  }
LABEL_160:
  v81 = v99;
  v96 = (int)v38;
  if ( v90 == (_DWORD)v38 )
    goto LABEL_166;
LABEL_161:
  v82 = IsBackupMasterKeyRequired((struct MASTERKEY_STORED *)v111, &v96);
  LODWORD(v38) = 0;
  if ( !v82
    || (v83 = v96,
        v84 = BackupMasterKey(a1, (struct MASTERKEY_STORED *)v111, *v102, *v101, v96, 1),
        LODWORD(v38) = 0,
        v84) )
  {
LABEL_166:
    if ( *v81 == 6 )
      *v81 = (unsigned int)v38;
    goto LABEL_168;
  }
  if ( !v83 )
  {
    *v81 = 1;
    goto LABEL_166;
  }
  *v81 = 2;
LABEL_168:
  v76 = 1;
LABEL_169:
  v86 = CloseMasterKey(a1, (struct MASTERKEY_STORED *)v111, v76) != 0 ? v76 : 0;
  if ( a6 && v86 )
    DeleteMasterKey(v85, v60, v106);
  if ( v60 )
    LocalFree(v60);
  v87 = pbSecret;
  do
  {
    *v87++ = 0;
    --v39;
  }
  while ( v39 );
  return v86;
}

```

## disassembly

```asm
0x18000e9c0  mov     rax, rsp
0x18000e9c3  mov     [rax+10h], rbx
0x18000e9c7  push    rbp
0x18000e9c8  push    rsi
0x18000e9c9  push    rdi
0x18000e9ca  push    r12
0x18000e9cc  push    r13
0x18000e9ce  push    r14
0x18000e9d0  push    r15
0x18000e9d2  lea     rbp, [rax-148h]
0x18000e9d9  sub     rsp, 210h
0x18000e9e0  movaps  xmmword ptr [rax-48h], xmm6
0x18000e9e4  mov     rax, cs:__security_cookie
0x18000e9eb  xor     rax, rsp
0x18000e9ee  mov     [rbp+140h+var_48], rax
0x18000e9f5  mov     rax, [rbp+140h+arg_40]
0x18000e9fc  mov     rdi, r8
0x18000e9ff  mov     r14, [rbp+140h+arg_30]
0x18000ea06  mov     r15, rcx
0x18000ea09  mov     rbx, [rbp+140h+arg_58]
0x18000ea10  lea     rcx, [rbp+140h+var_120]; void *
0x18000ea14  mov     [rbp+140h+var_138], rax
0x18000ea18  mov     esi, 0A0h
0x18000ea1d  mov     rax, [rbp+140h+arg_20]
0x18000ea24  mov     qword ptr [rbp+140h+Uuid.Data1], rax
0x18000ea2b  mov     rax, [rbp+140h+arg_38]
0x18000ea32  mov     qword ptr [rbp+140h+var_180.LowPart], rax
0x18000ea36  mov     rax, [rbp+140h+arg_48]
0x18000ea3d  mov     [rbp+140h+var_1A0], rax
0x18000ea41  mov     rax, [rbp+140h+arg_50]
0x18000ea48  mov     [rbp+140h+Src], r8
0x18000ea4c  mov     r8d, esi; Size
0x18000ea4f  mov     [rsp+240h+var_1C8], edx
0x18000ea53  xor     edx, edx; Val
0x18000ea55  mov     [rbp+140h+var_1A8], rax
0x18000ea59  mov     [rbp+140h+var_190], r9
0x18000ea5d  mov     [rbp+140h+var_170], r14
0x18000ea61  mov     [rbp+140h+var_1B8], rbx
0x18000ea65  call    memset_0
0x18000ea6a  xor     r13d, r13d
0x18000ea6d  xorps   xmm0, xmm0
0x18000ea70  mov     [rsp+240h+var_1D0], r13d
0x18000ea75  mov     eax, 6610h
0x18000ea7a  mov     [rbp+140h+var_1B0], eax
0x18000ea7d  mov     ecx, 800Eh
0x18000ea82  mov     [rbp+140h+var_1C0], ecx
0x18000ea85  mov     [rsp+240h+var_1C4], r13d
0x18000ea8a  mov     [rbp+140h+var_140], r13d
0x18000ea8e  mov     [rsp+240h+var_1E0], r13d
0x18000ea93  mov     [rsp+240h+var_1D8], r13d
0x18000ea98  movups  xmmword ptr [rbp+140h+var_80.Data1], xmm0
0x18000ea9f  test    r15, r15
0x18000eaa2  jz      short loc_18000EAB2
0x18000eaa4  mov     eax, [r15+38h]
0x18000eaa8  mov     r12d, [r15+34h]
0x18000eaac  mov     [rsp+240h+var_1D4], eax
0x18000eab0  jmp     short loc_18000EAB9
0x18000eab2  mov     r12d, eax
0x18000eab5  mov     [rsp+240h+var_1D4], ecx
0x18000eab9  mov     [rsp+240h+var_1CC], r12d
0x18000eabe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eac5  lea     rax, WPP_GLOBAL_Control
0x18000eacc  cmp     rcx, rax
0x18000eacf  jz      short loc_18000EAF4
0x18000ead1  test    byte ptr [rcx+1Ch], 4
0x18000ead5  jz      short loc_18000EAF4
0x18000ead7  mov     rcx, [rcx+10h]
0x18000eadb  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18000eae2  mov     edx, 51h ; 'Q'
0x18000eae7  mov     [rsp+240h+var_220], r14
0x18000eaec  mov     r9, rdi
0x18000eaef  call    WPP_SF_SS
0x18000eaf4  mov     r8, rsi; Size
0x18000eaf7  mov     dword ptr [rbx], 6
0x18000eafd  xor     edx, edx; Val
0x18000eaff  lea     rcx, [rbp+140h+var_120]; void *
0x18000eb03  call    memset_0
0x18000eb08  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000eb0c  mov     rax, rbx
0x18000eb0f  inc     rax
0x18000eb12  cmp     [rdi+rax*2], r13w
0x18000eb17  jnz     short loc_18000EB0F
0x18000eb19  lea     eax, ds:2[rax*2]
0x18000eb20  xor     ecx, ecx; uFlags
0x18000eb22  mov     edx, eax; uBytes
0x18000eb24  mov     esi, eax
0x18000eb26  call    cs:__imp_LocalAlloc
0x18000eb2d  nop     dword ptr [rax+rax+00h]
0x18000eb32  mov     [rbp+140h+var_118], rax
0x18000eb36  test    rax, rax
0x18000eb39  jnz     short loc_18000EBA8
0x18000eb3b  mov     ebx, 46Ah
0x18000eb40  mov     ecx, ebx; dwErrCode
0x18000eb42  call    cs:__imp_SetLastError
0x18000eb49  nop     dword ptr [rax+rax+00h]
0x18000eb4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb55  lea     rdx, WPP_GLOBAL_Control
0x18000eb5c  cmp     rcx, rdx
0x18000eb5f  jz      loc_18000ECD6
0x18000eb65  mov     edi, 1
0x18000eb6a  test    [rcx+1Ch], dil
0x18000eb6e  jz      loc_18000ECD6
0x18000eb74  mov     rcx, [rcx+10h]
0x18000eb78  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000eb7f  mov     dword ptr [rsp+240h+var_210], 0CA6h
0x18000eb87  lea     r9, aErrorNotEnough_0; "ERROR_NOT_ENOUGH_SERVER_MEMORY"
0x18000eb8e  mov     [rsp+240h+var_218], rax
0x18000eb93  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000eb9a  mov     dword ptr [rsp+240h+var_220], ebx
0x18000eb9e  call    WPP_SF_sDsd
0x18000eba3  jmp     loc_18000ECD6
0x18000eba8  mov     r8, rsi; Size
0x18000ebab  mov     rdx, rdi; Src
0x18000ebae  mov     rcx, rax; void *
0x18000ebb1  call    memcpy_0
0x18000ebb6  movups  xmm0, xmmword ptr [r14]
0x18000ebba  lea     rdx, [rbp+140h+var_120]; struct MASTERKEY_STORED *
0x18000ebbe  mov     rcx, r15; void *
0x18000ebc1  movups  xmm1, xmmword ptr [r14+10h]
0x18000ebc6  movaps  xmmword ptr [rbp+140h+StringUuid], xmm0
0x18000ebca  movups  xmm0, xmmword ptr [r14+20h]
0x18000ebcf  movaps  [rbp+140h+var_100], xmm1
0x18000ebd3  movups  xmm1, xmmword ptr [r14+30h]
0x18000ebd8  movaps  [rbp+140h+var_F0], xmm0
0x18000ebdc  movups  xmm0, xmmword ptr [r14+40h]
0x18000ebe1  movaps  [rbp+140h+var_E0], xmm1
0x18000ebe5  movaps  [rbp+140h+var_D0], xmm0
0x18000ebe9  call    ?ReadMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@@Z; ReadMasterKey(void *,MASTERKEY_STORED *)
0x18000ebee  lea     r14, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000ebf5  mov     edi, 1
0x18000ebfa  test    eax, eax
0x18000ebfc  jnz     loc_18000EDB4
0x18000ec02  call    cs:__imp_GetLastError
0x18000ec09  nop     dword ptr [rax+rax+00h]
0x18000ec0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec15  lea     rdx, WPP_GLOBAL_Control
0x18000ec1c  cmp     rcx, rdx
0x18000ec1f  jz      short loc_18000EC4F
0x18000ec21  test    [rcx+1Ch], dil
0x18000ec25  jz      short loc_18000EC4F
0x18000ec27  mov     rcx, [rcx+10h]
0x18000ec2b  lea     r9, aGetlasterror; "GetLastError()"
0x18000ec32  mov     dword ptr [rsp+240h+var_210], 0CB3h
0x18000ec3a  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000ec41  mov     [rsp+240h+var_218], r14
0x18000ec46  mov     dword ptr [rsp+240h+var_220], eax
0x18000ec4a  call    WPP_SF_sDsd
0x18000ec4f  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000ec56  nop     dword ptr [rax+rax+00h]
0x18000ec5b  test    al, al
0x18000ec5d  jz      loc_18000ED93
0x18000ec63  lea     r8, [rsp+240h+var_1E0]; int *
0x18000ec68  xor     edx, edx; int *
0x18000ec6a  mov     rcx, r15; void *
0x18000ec6d  call    ?CPSOverrideToLocalSystem@@YAKPEAXPEAH1@Z; CPSOverrideToLocalSystem(void *,int *,int *)
0x18000ec72  lea     rdx, [rsp+240h+var_1D8]; unsigned int *
0x18000ec77  call    ?CPSQueryWellKnownAccount@@YAKPEAXPEAK@Z; CPSQueryWellKnownAccount(void *,ulong *)
0x18000ec7c  cmp     [rsp+240h+var_1D8], 12h
0x18000ec81  jnz     loc_18000ED93
0x18000ec87  cmp     [rsp+240h+var_1E0], r13d
0x18000ec8c  jnz     loc_18000ED93
0x18000ec92  mov     rdx, rsi; uBytes
0x18000ec95  xor     ecx, ecx; uFlags
0x18000ec97  call    cs:__imp_LocalAlloc
0x18000ec9e  nop     dword ptr [rax+rax+00h]
0x18000eca3  mov     [rbp+140h+var_118], rax
0x18000eca7  test    rax, rax
0x18000ecaa  jnz     short loc_18000ECDD
0x18000ecac  mov     ebx, 46Ah
0x18000ecb1  mov     ecx, ebx; dwErrCode
0x18000ecb3  call    cs:__imp_SetLastError
0x18000ecba  nop     dword ptr [rax+rax+00h]
0x18000ecbf  mov     r9d, 0CCDh
0x18000ecc5  lea     rdx, aErrorNotEnough_0; "ERROR_NOT_ENOUGH_SERVER_MEMORY"
0x18000eccc  mov     r8, r14
0x18000eccf  mov     ecx, ebx
0x18000ecd1  call    DebugTraceError
0x18000ecd6  xor     eax, eax
0x18000ecd8  jmp     loc_18000F8D7
0x18000ecdd  mov     rdx, [rbp+140h+Src]; Src
0x18000ece1  mov     r8, rsi; Size
0x18000ece4  mov     rcx, rax; void *
0x18000ece7  call    memcpy_0
0x18000ecec  mov     rsi, [rbp+140h+var_170]
0x18000ecf0  xor     r14d, r14d
0x18000ecf3  mov     rcx, [rbp+140h+var_118]
0x18000ecf7  movups  xmm0, xmmword ptr [rsi]
0x18000ecfa  movups  xmm1, xmmword ptr [rsi+10h]
0x18000ecfe  movaps  xmmword ptr [rbp+140h+StringUuid], xmm0
0x18000ed02  movups  xmm0, xmmword ptr [rsi+20h]
0x18000ed06  movaps  [rbp+140h+var_100], xmm1
0x18000ed0a  movups  xmm1, xmmword ptr [rsi+30h]
0x18000ed0e  movaps  [rbp+140h+var_F0], xmm0
0x18000ed12  movups  xmm0, xmmword ptr [rsi+40h]
0x18000ed16  movaps  [rbp+140h+var_E0], xmm1
0x18000ed1a  movaps  [rbp+140h+var_D0], xmm0
0x18000ed1e  inc     rbx
0x18000ed21  cmp     [rcx+rbx*2], r14w
0x18000ed26  jnz     short loc_18000ED1E
0x18000ed28  cmp     ebx, 5
0x18000ed2b  jb      short loc_18000ED93
0x18000ed2d  add     ebx, 0FFFFFFFBh
0x18000ed30  mov     eax, 55h ; 'U'
0x18000ed35  cmp     [rcx+rbx*2], ax
0x18000ed39  jnz     short loc_18000ED93
0x18000ed3b  mov     [rcx+rbx*2], r14w
0x18000ed40  lea     rdx, [rbp+140h+var_120]; struct MASTERKEY_STORED *
0x18000ed44  mov     rcx, r15; void *
0x18000ed47  call    ?ReadMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@@Z; ReadMasterKey(void *,MASTERKEY_STORED *)
0x18000ed4c  mov     r13d, eax
0x18000ed4f  test    eax, eax
0x18000ed51  jz      short loc_18000ED93
0x18000ed53  mov     rcx, [rbp+140h+var_118]
0x18000ed57  mov     word ptr [rcx+rbx*2], 55h ; 'U'
0x18000ed5d  mov     [rbp+140h+var_11C], edi
0x18000ed60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed67  lea     rax, WPP_GLOBAL_Control
0x18000ed6e  cmp     rcx, rax
0x18000ed71  jz      short loc_18000EDB7
0x18000ed73  test    byte ptr [rcx+1Ch], 8
0x18000ed77  jz      short loc_18000EDB7
0x18000ed79  mov     rcx, [rcx+10h]
0x18000ed7d  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18000ed84  mov     edx, 52h ; 'R'
0x18000ed89  mov     r9, rsi
0x18000ed8c  call    WPP_SF_S
0x18000ed91  jmp     short loc_18000EDB7
0x18000ed93  mov     ecx, 80090003h; dwErrCode
0x18000ed98  call    cs:__imp_SetLastError
0x18000ed9f  nop     dword ptr [rax+rax+00h]
0x18000eda4  mov     r14, [rbp+140h+var_1B8]
0x18000eda8  mov     dword ptr [r14], 3
0x18000edaf  jmp     loc_18000ECD6
0x18000edb4  xor     r14d, r14d
0x18000edb7  xorps   xmm0, xmm0
0x18000edba  mov     [rsp+240h+var_1D8], r14d
0x18000edbf  movups  xmmword ptr [rbp+140h+var_80.Data1], xmm0
0x18000edc6  cmp     [rbp+140h+var_BC], r14d
0x18000edcd  jz      loc_18000EE54
0x18000edd3  mov     rbx, [rbp+140h+var_B8]
0x18000edda  test    rbx, rbx
0x18000eddd  jz      short loc_18000EE54
0x18000eddf  cmp     [rbx], edi
0x18000ede1  jbe     loc_18000EF2A
0x18000ede7  mov     r14d, [rbx+18h]
0x18000edeb  mov     ecx, r14d; unsigned int
0x18000edee  mov     esi, [rbx+1Ch]
0x18000edf1  mov     ebx, [rbx+14h]
0x18000edf4  call    ?GetIterationCount@@YAKI@Z; GetIterationCount(uint)
0x18000edf9  cmp     ebx, eax
0x18000edfb  jb      loc_18000EF2A
0x18000ee01  mov     eax, 6603h
0x18000ee06  cmp     esi, 6801h
0x18000ee0c  jnz     short loc_18000EE24
0x18000ee0e  cmp     r12d, eax
0x18000ee11  jz      loc_18000EF2A
0x18000ee17  cmp     r12d, 6610h
0x18000ee1e  jz      loc_18000EF2A
0x18000ee24  cmp     esi, eax
0x18000ee26  jnz     short loc_18000EE35
0x18000ee28  cmp     r12d, 6610h
0x18000ee2f  jz      loc_18000EF2A
0x18000ee35  cmp     r14d, 8009h
0x18000ee3c  jnz     short loc_18000EE4D
0x18000ee3e  lea     r9d, [r14+5]
0x18000ee42  cmp     [rsp+240h+var_1D4], r9d
0x18000ee47  jz      loc_18000EF2A
0x18000ee4d  mov     [rbp+140h+var_1C0], r14d
0x18000ee51  mov     [rbp+140h+var_1B0], esi
0x18000ee54  mov     r14d, [rsp+240h+var_1D4]
0x18000ee59  mov     rcx, qword ptr [rbp+140h+var_180.LowPart]
0x18000ee5d  xor     r8d, r8d
0x18000ee60  mov     r12d, 14h
0x18000ee66  test    rcx, rcx
0x18000ee69  jz      loc_18000EF3C
0x18000ee6f  mov     r8d, [rbp+140h+var_C0]
0x18000ee76  lea     rax, [rcx+28h]
0x18000ee7a  mov     rdx, [rbp+140h+var_190]; void *
0x18000ee7e  lea     r9, [rcx+14h]; unsigned __int8 *
0x18000ee82  lea     rcx, [rbp+140h+pbSecret]
0x18000ee89  shr     r8d, 2
0x18000ee8d  mov     [rsp+240h+var_218], rcx; PUCHAR
0x18000ee92  and     r8d, edi; unsigned int
0x18000ee95  mov     rcx, r15; void *
0x18000ee98  mov     [rsp+240h+var_220], rax; Src
0x18000ee9d  call    ?ComputeMasterKeyUserEncryptionKey@@YAHPEAX0KQEAE11@Z; ComputeMasterKeyUserEncryptionKey(void *,void *,ulong,uchar * const,uchar * const,uchar * const)
0x18000eea2  xor     r8d, r8d
0x18000eea5  mov     [rsp+240h+var_1E0], eax
0x18000eea9  mov     esi, eax
0x18000eeab  test    eax, eax
0x18000eead  jz      loc_18000EF3F
0x18000eeb3  movaps  xmm0, xmmword ptr [rbp+140h+var_80.Data1]
0x18000eeba  lea     rax, [rbp+140h+var_180]
0x18000eebe  mov     [rsp+240h+var_1F0], r15; void *
0x18000eec3  lea     rcx, [rbp+140h+var_120]; struct MASTERKEY_STORED *
0x18000eec7  mov     [rsp+240h+var_1F8], rax; struct _GUID
0x18000eecc  mov     r9d, r14d; unsigned int
0x18000eecf  mov     rax, [rbp+140h+var_1A8]
0x18000eed3  xor     edx, edx; unsigned int
0x18000eed5  mov     r14d, [rsp+240h+var_1CC]
  ... truncated ...
```
