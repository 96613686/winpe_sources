# UnlockCloudAPCacheNodeData(_CloudAPCache *,ulong,uchar *,ulong,_SCARD_PIN *,_tagCacheNodeIdentifier *,_CloudAPCacheNodeData2 * *)

- ea: `0x18001e130`
- end: `0x18001f8e0`
- name: `?UnlockCloudAPCacheNodeData@@YAJPEAU_CloudAPCache@@KPEAEKPEAU_SCARD_PIN@@PEAU_tagCacheNodeIdentifier@@PEAPEAU_CloudAPCacheNodeData2@@@Z`
- size: `6064`
- prototype: `int(struct _CloudAPCache *, unsigned int, unsigned __int8 *, unsigned int, struct _SCARD_PIN *, struct _tagCacheNodeIdentifier *, struct _CloudAPCacheNodeData2 **)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18001f8f0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18001e130`
- `0x1800219c0`
- `0x180022f40`
- `0x180023f30`
- `0x180029398`
- `0x1800293c0`
- `0x18002d4b8`
- `0x18002f910`
- `0x180033b7c`
- `0x180035c54`
- `0x18003c840`
- `0x18003cd70`
- `0x180043158`
- `0x180064024`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f71f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f821`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f71f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f7ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f821`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f15d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f4ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f15d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f4ed`
- `cryptngc!NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold` at `0x18001ea41`
- `cryptngc!NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold` at `0x18001ea41`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x18001eab2`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x18001eab2`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x18001ebc8`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x18001ebc8`

## string_xrefs

- `0x18001e201`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e2da`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e326`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e392`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e5c5`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e62d`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e6c3`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e752`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e7d9`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e85a`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e8a9`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e945`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001ee95`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001f733`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001e41e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001e4b6`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001e52e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001ed6d`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001ee38`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001f042`: `Cache node doesnt have version`
- `0x18001e3c1`: `GetCloudAPCacheNode`
- `0x18001e6ea`: `GetCloudAPCacheNode`
- `0x18001e882`: `GetCloudAPCacheNode`
- `0x18001eb4a`: `GetCloudAPCacheNode`
- `0x18001ed20`: `GetCloudAPCacheNode`
- `0x18001ef11`: `Unexpected:pCacheNodeData = NULL`
- `0x18001efe1`: `Cache node is of invalid length`
- `0x18001f0a1`: `Cache node doesnt have flags`
- `0x18001f123`: `Overflow:cbCredKey > cbCacheNodeData`
- `0x18001f351`: `FIDOGetCredHashFromCacheData`

## pseudocode

```c
__int64 __fastcall UnlockCloudAPCacheNodeData(
        struct _CloudAPCache *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        ULONG a4,
        struct _SCARD_PIN *a5,
        struct _tagCacheNodeIdentifier *a6,
        struct _CloudAPCacheNodeData2 **a7)
{
  __int64 v9; // r15
  struct _tagCacheNodeIdentifier *v11; // rax
  const char *v12; // rbx
  const char *v13; // rax
  int v14; // r10d
  unsigned int CloudAPCacheNode; // esi
  const char *v16; // r9
  char v17; // al
  const char *v18; // rcx
  bool v19; // zf
  char v20; // al
  const unsigned __int16 *v21; // rcx
  char v22; // al
  ULONG v23; // r14d
  ULONG v24; // r13d
  __int64 v25; // r12
  const char *v26; // r9
  char v27; // al
  const char *v28; // rdx
  bool v29; // zf
  unsigned int v30; // eax
  const unsigned __int16 *v31; // rcx
  unsigned __int8 *v32; // r14
  const char *v33; // r9
  char v34; // al
  const char *v35; // rdx
  unsigned int v36; // r12d
  const char *v37; // r10
  int v38; // r8d
  char v39; // al
  const char *v40; // r8
  __int64 v41; // rdx
  unsigned __int8 *v42; // rax
  char v43; // al
  unsigned __int8 *v44; // r12
  int v45; // r14d
  char v46; // al
  unsigned int v47; // r8d
  __int64 v48; // r9
  unsigned int v49; // ecx
  char v50; // al
  unsigned __int8 *v51; // r9
  unsigned int v52; // r8d
  unsigned __int8 *v53; // rdx
  char v54; // al
  char v55; // al
  const char *v56; // rcx
  bool v57; // zf
  char v58; // al
  char v59; // al
  char v60; // al
  const char *v61; // r9
  const char *v62; // rax
  char v63; // al
  __int64 v64; // r8
  int LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold; // eax
  unsigned int v66; // eax
  char v67; // al
  int UserIdKeyPublicKey; // eax
  unsigned int v69; // eax
  char v70; // al
  char v71; // al
  char v72; // al
  int v73; // eax
  char v74; // al
  rsize_t v75; // rsi
  char v76; // al
  char v77; // al
  const unsigned __int16 *v78; // rcx
  const char *v79; // r9
  const unsigned __int16 *v80; // rcx
  const char *v81; // rax
  ULONG v82; // r13d
  unsigned int v83; // eax
  const unsigned __int16 *v84; // rcx
  unsigned __int8 *v85; // r12
  const char *v86; // rax
  int v87; // r8d
  unsigned int v88; // r11d
  __int64 v89; // r10
  __int64 v90; // rdx
  unsigned __int8 *v91; // rax
  char v92; // al
  char v93; // al
  struct _CloudAPCacheNodeData2 *v94; // rax
  struct _CloudAPCacheNodeData2 *v95; // r8
  char v96; // al
  unsigned int v97; // r13d
  char v98; // al
  unsigned int *v99; // rsi
  unsigned int v100; // eax
  int v101; // ecx
  char v102; // al
  char v103; // al
  int v104; // eax
  SIZE_T v105; // rax
  char v106; // al
  HLOCAL v107; // rax
  struct _CloudAPCacheNodeData2 *v108; // r14
  char v109; // al
  rsize_t v110; // rdx
  __int64 v111; // r8
  char v112; // al
  unsigned int v113; // eax
  __int64 v114; // r9
  unsigned int *v115; // r14
  unsigned int v116; // eax
  const unsigned __int16 *v117; // rcx
  unsigned int v118; // r8d
  char v119; // al
  const unsigned __int16 *v120; // rcx
  char v121; // al
  char v122; // al
  __int64 v123; // rdx
  unsigned __int8 v124; // cl
  char v125; // al
  char v126; // al
  char v127; // al
  struct _CloudAPCacheNodeData2 *v128; // r15
  struct _LSA_SECPKG_FUNCTION_TABLE *v129; // rdx
  __int64 v130; // r14
  unsigned int v131; // eax
  HLOCAL v132; // rax
  char v133; // al
  char v134; // al
  unsigned int v135; // eax
  struct _tagCacheNodeIdentifier *v136; // r14
  SIZE_T v137; // rcx
  HLOCAL Memory; // rax
  char v139; // al
  unsigned __int8 *v140; // rdx
  size_t v141; // r8
  SIZE_T v142; // rcx
  char v143; // al
  char v144; // al
  char v145; // al
  _BYTE *v146; // rcx
  __int64 v147; // rax
  _BYTE *v148; // rax
  __int64 v149; // rcx
  void *v150; // rcx
  __int64 v151; // rdx
  _BYTE *v152; // rax
  unsigned __int8 *v153; // rcx
  __int64 v154; // rdx
  unsigned __int8 *v155; // rax
  unsigned __int8 **v157; // [rsp+28h] [rbp-E0h]
  unsigned __int8 **v158; // [rsp+28h] [rbp-E0h]
  unsigned int v159; // [rsp+28h] [rbp-E0h]
  unsigned __int8 **v160; // [rsp+28h] [rbp-E0h]
  unsigned int *v161; // [rsp+30h] [rbp-D8h]
  const char *v162; // [rsp+30h] [rbp-D8h]
  const char *v163; // [rsp+30h] [rbp-D8h]
  unsigned int v164[2]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int8 *v165; // [rsp+60h] [rbp-A8h] BYREF
  size_t Size; // [rsp+68h] [rbp-A0h] BYREF
  void *Destination; // [rsp+70h] [rbp-98h] BYREF
  rsize_t DestinationSize; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v169; // [rsp+80h] [rbp-88h] BYREF
  void *Src; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int8 *v171; // [rsp+90h] [rbp-78h] BYREF
  struct _CloudAPCacheNodeData2 *v172; // [rsp+98h] [rbp-70h]
  unsigned int v173; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v174; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int8 *v175; // [rsp+B0h] [rbp-58h]
  __BCRYPT_KEY_LENGTHS_STRUCT v176; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v177; // [rsp+C8h] [rbp-40h] BYREF
  HLOCAL v178; // [rsp+D0h] [rbp-38h] BYREF
  void *Source; // [rsp+D8h] [rbp-30h] BYREF
  void *v180; // [rsp+E0h] [rbp-28h]
  unsigned __int8 *v181; // [rsp+E8h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int8 *v183; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v184; // [rsp+100h] [rbp-8h] BYREF
  unsigned int v185; // [rsp+158h] [rbp+50h] BYREF
  unsigned int v186; // [rsp+160h] [rbp+58h]
  unsigned __int8 *v187; // [rsp+168h] [rbp+60h]

  v187 = a3;
  v186 = a2;
  v9 = 0;
  HIDWORD(v174) = 0;
  *(_QWORD *)v164 = 0;
  v172 = 0;
  hMem = 0;
  v177 = 0;
  v178 = 0;
  v165 = 0;
  v171 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  Source = 0;
  DestinationSize = 0;
  Destination = 0;
  v185 = 0;
  v180 = 0;
  v181 = 0;
  v169 = 0;
  v183 = 0;
  v173 = 0;
  v184 = 0;
  if ( !a1 || !a3 || !a7 || (v11 = a6) == 0 )
  {
    CloudAPCacheNode = -1073741811;
    v12 = "";
    while ( 1 )
    {
      v145 = *(v12 - 1);
      v18 = v12--;
      v19 = v145 == 92;
      if ( v145 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v19 = v145 == 92;
        break;
      }
    }
    v162 = "InvalidArgs";
    LODWORD(v157) = 957;
    goto LABEL_340;
  }
  *a7 = 0;
  v12 = "";
  *(_OWORD *)v11 = 0;
  if ( a2 == 6 )
    goto LABEL_169;
  if ( a2 != 1 && a2 != 3 && a2 != 4 && a2 != 5 && a2 != 7 )
  {
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", -1073741811, v13, 519, "InvalidCredType", v14);
    CloudAPCacheNode = -1073741811;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    LODWORD(v158) = 964;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v16, v158, "ValidateCredType", &Class);
    goto LABEL_343;
  }
  if ( ((a2 - 1) & 0xFFFFFFFD) == 0 )
  {
LABEL_169:
    v165 = 0;
    v45 = 0;
    CloudAPCacheNode = GetCloudAPCacheNode(a1, a2, 0, 0, v164);
    if ( CloudAPCacheNode )
    {
      v79 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      LODWORD(v160) = 976;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CloudAPCacheNode, v79, v160, "GetCloudAPCacheNode", &Class);
      goto LABEL_343;
    }
    v9 = *(_QWORD *)v164;
    v174 = 0;
    LODWORD(v175) = 0;
    v171 = 0;
    v164[0] = *(_DWORD *)(*(_QWORD *)v164 + 16LL);
    *(_QWORD *)&v176.dwMinLength = *(_QWORD *)(v9 + 24);
    CloudAPCacheNode = GetSupportedKeyLengths(v78, (struct __BCRYPT_KEY_LENGTHS_STRUCT *)&v174, 0);
    if ( CloudAPCacheNode )
    {
      v81 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      LODWORD(v160) = 213;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CloudAPCacheNode, v81, v160, "GetSupportedKeyLengths", &Class);
      goto LABEL_179;
    }
    v82 = HIDWORD(v174) >> 3;
    v83 = DeriveKeyFromSecret(v80, v187, a4, HIDWORD(v174) >> 3, &v171);
    v85 = v171;
    CloudAPCacheNode = v83;
    if ( v83
      || (CloudAPCacheNode = DecryptBufferWithKey(
                               v84,
                               *(unsigned __int8 **)&v176.dwMinLength,
                               v164[0],
                               v171,
                               v82,
                               (unsigned __int8 **)&Destination,
                               &v185)) != 0 )
    {
      v86 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      LODWORD(v157) = v87;
      WPPTraceLogA(v88, "0x%08x %s:%u : %s:%ws", CloudAPCacheNode, v86, v157, v89, &Class);
      if ( v85 )
      {
        v90 = v82;
        v91 = v85;
        if ( v82 )
        {
          do
          {
            *v91++ = 0;
            --v90;
          }
          while ( v90 );
        }
        FreeMemory(v85);
      }
LABEL_179:
      while ( 1 )
      {
        v92 = *(v12 - 1);
        v18 = v12--;
        v19 = v92 == 92;
        if ( v92 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v92 == 92;
          break;
        }
      }
      v162 = "DecryptBufferWithSecret";
      LODWORD(v157) = 989;
      goto LABEL_340;
    }
    HIDWORD(DestinationSize) = v82;
    v180 = v85;
LABEL_184:
    v44 = v165;
    goto LABEL_185;
  }
  if ( a2 == 7 )
  {
    CloudAPCacheNode = FIDOValidateAuthData(a3, a4);
    if ( CloudAPCacheNode )
    {
      while ( 1 )
      {
        v17 = *(v12 - 1);
        v18 = v12--;
        v19 = v17 == 92;
        if ( v17 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v17 == 92;
          break;
        }
      }
      v162 = "ValidateFIDOAuthData";
      LODWORD(v157) = 994;
LABEL_340:
      if ( v19 )
        v12 = v18;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CloudAPCacheNode, v12, v157, v162, &Class);
      goto LABEL_343;
    }
    if ( !*((_DWORD *)a3 + 7) )
    {
      CloudAPCacheNode = -1073741718;
      while ( 1 )
      {
        v20 = *(v12 - 1);
        v18 = v12--;
        v19 = v20 == 92;
        if ( v20 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v20 == 92;
          break;
        }
      }
      v162 = "Missing FIDO secret";
      LODWORD(v157) = 1003;
      goto LABEL_340;
    }
    CloudAPCacheNode = GetCloudAPCacheNode(a1, 7, &a3[*((unsigned int *)a3 + 4)], *((unsigned int *)a3 + 5), v164);
    if ( CloudAPCacheNode )
    {
      while ( 1 )
      {
        v22 = *(v12 - 1);
        v18 = v12--;
        v19 = v22 == 92;
        if ( v22 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v22 == 92;
          break;
        }
      }
      v162 = "GetCloudAPCacheNode";
      LODWORD(v157) = 1013;
      goto LABEL_340;
    }
    v9 = *(_QWORD *)v164;
    v23 = *((_DWORD *)a3 + 7);
    *(_QWORD *)&v176.dwMinLength = 0;
    v176.dwIncrement = 0;
    v24 = *(_DWORD *)(*(_QWORD *)v164 + 16LL);
    v171 = 0;
    v25 = *((unsigned int *)v187 + 6);
    v165 = *(unsigned __int8 **)(*(_QWORD *)v164 + 24LL);
    CloudAPCacheNode = GetSupportedKeyLengths(v21, &v176, 0);
    if ( CloudAPCacheNode )
    {
      v26 = "";
      do
      {
        v27 = *(v26 - 1);
        v28 = v26--;
        v29 = v27 == 92;
        if ( v27 == 92 )
          goto LABEL_35;
      }
      while ( v26 > "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" );
      v29 = v27 == 92;
LABEL_35:
      if ( v29 )
        v26 = v28;
      LODWORD(v157) = 213;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CloudAPCacheNode, v26, v157, "GetSupportedKeyLengths", &Class);
      goto LABEL_56;
    }
    v164[0] = v176.dwMaxLength >> 3;
    v30 = DeriveKeyFromSecret((const unsigned __int16 *)&v171, &v187[v25], v23, v176.dwMaxLength >> 3, &v171);
    v32 = v171;
    CloudAPCacheNode = v30;
    if ( v30 )
    {
      v33 = "";
      do
      {
        v34 = *(v33 - 1);
        v35 = v33--;
      }
      while ( v34 != 92 && v33 > "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" );
      v36 = v164[0];
      v37 = "DeriveKeyFromSecret";
      v38 = 224;
      if ( v34 == 92 )
        v33 = v35;
      goto LABEL_52;
    }
    v36 = v164[0];
    CloudAPCacheNode = DecryptBufferWithKey(v31, v165, v24, v171, v164[0], (unsigned __int8 **)&Destination, &v185);
    if ( CloudAPCacheNode )
    {
      v33 = "";
      do
      {
        v39 = *(v33 - 1);
        v40 = v33--;
      }
      while ( v39 != 92 && v33 > "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" );
      v37 = "DecryptBufferWithKey";
      if ( v39 == 92 )
        v33 = v40;
      v38 = 234;
LABEL_52:
      LODWORD(v157) = v38;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CloudAPCacheNode, v33, v157, v37, &Class);
      if ( v32 )
      {
        v41 = v36;
        v42 = v32;
        if ( v36 )
        {
          do
          {
            *v42++ = 0;
            --v41;
          }
          while ( v41 );
        }
        FreeMemory(v32);
      }
LABEL_56:
      while ( 1 )
      {
        v43 = *(v12 - 1);
        v18 = v12--;
        v19 = v43 == 92;
        if ( v43 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v43 == 92;
          break;
        }
      }
      v162 = "DecryptBufferWithSecret";
      LODWORD(v157) = 1026;
      goto LABEL_340;
    }
    HIDWORD(DestinationSize) = v36;
    v44 = v187;
    v180 = v32;
    v45 = 0;
    goto LABEL_185;
  }
  if ( a2 == 4 )
  {
    if ( a4 != 24 )
    {
      CloudAPCacheNode = -1073741582;
      while ( 1 )
      {
        v46 = *(v12 - 1);
        v18 = v12--;
        v19 = v46 == 92;
        if ( v46 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v46 == 92;
          break;
        }
      }
      v162 = "Invalid Size";
      LODWORD(v157) = 1034;
      goto LABEL_340;
    }
    v47 = *((_DWORD *)a1 + 5);
    if ( v47 )
    {
      v49 = 0;
      while ( 1 )
      {
        v48 = *((_QWORD *)a1 + 3);
        if ( *(_DWORD *)(v48 + 32LL * v49) == 4 )
          break;
        if ( ++v49 >= v47 )
          goto LABEL_74;
      }
      v9 = v48 + 32LL * v49;
    }
LABEL_74:
    v165 = 0;
    v45 = 0;
    if ( !v9 )
    {
      CloudAPCacheNode = -1073741275;
      while ( 1 )
      {
        v50 = *(v12 - 1);
        v18 = v12--;
        v19 = v50 == 92;
        if ( v50 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v50 == 92;
          break;
        }
      }
      v162 = "GetCloudAPCacheNode";
      LODWORD(v157) = 1046;
      goto LABEL_340;
    }
    v51 = *(unsigned __int8 **)(v9 + 24);
    v52 = *(_DWORD *)(v9 + 4);
    v53 = *(unsigned __int8 **)(v9 + 8);
    v175 = v187;
    v159 = *(_DWORD *)(v9 + 16);
    LODWORD(v174) = 0;
    CloudAPCacheNode = PKDecryptData(
                         (struct _tagPK_CONTEXTS_DATA *)&v174,
                         v53,
                         v52,
                         v51,
                         v159,
                         a5,
                         (unsigned __int8 **)&Destination,
                         &v185);
    if ( CloudAPCacheNode )
    {
      while ( 1 )
      {
        v54 = *(v12 - 1);
        v18 = v12--;
        v19 = v54 == 92;
        if ( v54 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v19 = v54 == 92;
          break;
        }
      }
      v162 = "PKDecryptData";
      LODWORD(v157) = 1060;
      goto LABEL_340;
    }
    goto LABEL_184;
  }
  CloudAPCacheNode = GetNgcAuthBufferContents(
                       a3,
                       a4,
                       (unsigned __int16 **)&hMem,
                       (unsigned __int64 *)&v165,
                       v157,
                       v161,
                       &v177,
                       (unsigned __int64 *)&v171,
                       (unsigned __int8 **)&Src,
                       (unsigned int *)&Size);
  if ( CloudAPCacheNode )
  {
    while ( 1 )
    {
      v55 = *(v12 - 1);
      v56 = v12--;
      v57 = v55 == 92;
      if ( v55 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v55 == 92;
        break;
      }
    }
    v163 = "GetNgcAuthBufferContents";
    LODWORD(v157) = 1076;
    goto LABEL_325;
  }
  if ( !Src )
  {
    CloudAPCacheNode = -1073741275;
    v61 = "";
    do
    {
      v62 = v61 - 1;
      if ( *(v61 - 1) == 92 )
        break;
      --v61;
    }
    while ( v62 > "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" );
    LODWORD(v157) = 1093;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      3221226021LL,
      v61,
      v157,
      "Decryption not found, falling back to older key",
      &Class);
    v165 = 0;
    goto LABEL_113;
  }
  CloudAPCacheNode = GetCloudAPCacheNode(a1, v186, Src, (unsigned int)Size, v164);
  v165 = 0;
  if ( CloudAPCacheNode == -1073741275 )
  {
LABEL_113:
    if ( !hMem )
    {
      while ( 1 )
      {
        v63 = *(v12 - 1);
        v56 = v12--;
        v57 = v63 == 92;
        if ( v63 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v63 == 92;
          break;
        }
      }
      v163 = "Signing key name is NULL";
      v64 = 3221226021LL;
      LODWORD(v157) = 1100;
      goto LABEL_326;
    }
    LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold = NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold(
                                                                     v177,
                                                                     &v178);
    if ( LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold < 0 )
    {
      CloudAPCacheNode = (unsigned __int16)LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold;
      v66 = (unsigned __int16)LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold | 0xC0070000;
      if ( CloudAPCacheNode )
        CloudAPCacheNode = v66;
      while ( 1 )
      {
        v67 = *(v12 - 1);
        v56 = v12--;
        v57 = v67 == 92;
        if ( v67 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v67 == 92;
          break;
        }
      }
      v163 = "NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold";
      LODWORD(v157) = 1114;
      goto LABEL_325;
    }
    if ( Src )
    {
      FreeMemory(Src);
      Src = 0;
    }
    UserIdKeyPublicKey = NgcGetUserIdKeyPublicKey(v178, &Src, &Size);
    if ( UserIdKeyPublicKey < 0 )
    {
      CloudAPCacheNode = (unsigned __int16)UserIdKeyPublicKey;
      v69 = (unsigned __int16)UserIdKeyPublicKey | 0xC0070000;
      if ( CloudAPCacheNode )
        CloudAPCacheNode = v69;
      while ( 1 )
      {
        v70 = *(v12 - 1);
        v56 = v12--;
        v57 = v70 == 92;
        if ( v70 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v70 == 92;
          break;
        }
      }
      v163 = "NgcGetUserIdKeyPublicKey";
      LODWORD(v157) = 1130;
      goto LABEL_325;
    }
    v186 = 2;
    CloudAPCacheNode = GetCloudAPCacheNode(a1, 2, Src, (unsigned int)Size, v164);
    if ( CloudAPCacheNode )
    {
      while ( 1 )
      {
        v71 = *(v12 - 1);
        v56 = v12--;
        v57 = v71 == 92;
        if ( v71 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v71 == 92;
          break;
        }
      }
      v163 = "GetCloudAPCacheNode";
      LODWORD(v157) = 1139;
      goto LABEL_325;
    }
    if ( !v171 )
    {
      CloudAPCacheNode = -1073741275;
      while ( 1 )
      {
        v72 = *(v12 - 1);
        v56 = v12--;
        v57 = v72 == 92;
        if ( v72 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v72 == 92;
          break;
        }
      }
      v163 = "NgcMissingDecryptionAuthTicket";
      LODWORD(v157) = 1146;
      goto LABEL_325;
    }
    v9 = *(_QWORD *)v164;
    v73 = NgcDecryptWithUserIdKeySilent(
            v178,
            v171,
            *(_QWORD *)(*(_QWORD *)v164 + 24LL),
            *(unsigned int *)(*(_QWORD *)v164 + 16LL),
            &Source,
            &DestinationSize);
    if ( v73 < 0 )
    {
      if ( v73 == -2146893775 )
      {
        CloudAPCacheNode = -1073740927;
      }
      else if ( v73 == -2146893773 )
      {
        CloudAPCacheNode = -1073740928;
      }
      else
      {
        CloudAPCacheNode = (unsigned __int16)v73;
        if ( (_WORD)v73 )
          CloudAPCacheNode = (unsigned __int16)v73 | 0xC0070000;
      }
      while ( 1 )
      {
        v74 = *(v12 - 1);
        v56 = v12--;
        v57 = v74 == 92;
        if ( v74 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v74 == 92;
          break;
        }
      }
      v163 = "NgcDecryptWithUserIdKeySilent";
      LODWORD(v157) = 1174;
      goto LABEL_325;
    }
    v75 = (unsigned int)DestinationSize;
    v185 = DestinationSize;
    Destination = AllocateMemory((unsigned int)DestinationSize);
    if ( !Destination )
    {
      CloudAPCacheNode = -1073741801;
      while ( 1 )
      {
        v76 = *(v12 - 1);
        v56 = v12--;
        v57 = v76 == 92;
        if ( v76 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v76 == 92;
          break;
        }
      }
      v163 = "AllocateMemory";
      LODWORD(v157) = 1183;
      goto LABEL_325;
    }
    if ( memcpy_s_0(Destination, v75, Source, (unsigned int)DestinationSize) )
    {
      CloudAPCacheNode = -1073741595;
      while ( 1 )
      {
        v77 = *(v12 - 1);
        v56 = v12--;
        v57 = v77 == 92;
        if ( v77 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v77 == 92;
          break;
        }
      }
      v163 = "memcpy_s";
      LODWORD(v157) = 1193;
      goto LABEL_325;
    }
    v45 = 1;
    goto LABEL_184;
  }
  if ( CloudAPCacheNode )
  {
    while ( 1 )
    {
      v58 = *(v12 - 1);
      v56 = v12--;
      v57 = v58 == 92;
      if ( v58 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v58 == 92;
        break;
      }
    }
    v163 = "GetCloudAPCacheNode";
    LODWORD(v157) = 1202;
    goto LABEL_325;
  }
  if ( !v171 )
  {
    CloudAPCacheNode = -1073741275;
    while ( 1 )
    {
      v59 = *(v12 - 1);
      v56 = v12--;
      v57 = v59 == 92;
      if ( v59 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v59 == 92;
        break;
      }
    }
    v163 = "NgcMissingDecryptionAuthTicket";
    LODWORD(v157) = 1209;
    goto LABEL_325;
  }
  *(_QWORD *)&v184 = v177;
  *((_QWORD *)&v184 + 1) = v171;
  v175 = (unsigned __int8 *)&v184;
  v9 = *(_QWORD *)v164;
  LODWORD(v174) = 1;
  CloudAPCacheNode = PKDecryptData(
                       (struct _tagPK_CONTEXTS_DATA *)&v174,
                       *(unsigned __int8 **)(*(_QWORD *)v164 + 8LL),
                       *(_DWORD *)(*(_QWORD *)v164 + 4LL),
                       *(unsigned __int8 **)(*(_QWORD *)v164 + 24LL),
                       *(_DWORD *)(*(_QWORD *)v164 + 16LL),
                       0,
                       (unsigned __int8 **)&Destination,
                       &v185);
  if ( CloudAPCacheNode )
  {
    while ( 1 )
    {
      v60 = *(v12 - 1);
      v56 = v12--;
      v57 = v60 == 92;
      if ( v60 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v60 == 92;
        break;
      }
    }
    v163 = "PKDecryptData";
    LODWORD(v157) = 1226;
    goto LABEL_325;
  }
  v45 = 0;
  v44 = 0;
LABEL_185:
  if ( !Destination )
  {
    CloudAPCacheNode = -1073741595;
    while ( 1 )
    {
      v93 = *(v12 - 1);
      v56 = v12--;
      v57 = v93 == 92;
      if ( v93 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v93 == 92;
        break;
      }
    }
    v163 = "Unexpected:pCacheNodeData = NULL";
    LODWORD(v157) = 1234;
LABEL_325:
    v64 = CloudAPCacheNode;
LABEL_326:
    if ( v57 )
      v12 = v56;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v64, v12, v157, v163, &Class);
    goto LABEL_329;
  }
  if ( g_pLsaFunctionTable )
    v94 = (struct _CloudAPCacheNodeData2 *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(40);
  else
    v94 = (struct _CloudAPCacheNodeData2 *)LocalAlloc(0x40u, 0x28u);
  v172 = v94;
  v95 = v94;
  if ( !v94 )
  {
    CloudAPCacheNode = -1073741801;
    while ( 1 )
    {
      v96 = *(v12 - 1);
      v56 = v12--;
      v57 = v96 == 92;
      if ( v96 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v96 == 92;
        break;
      }
    }
    v163 = "AllocateMemory";
    LODWORD(v157) = 1243;
    goto LABEL_325;
  }
  v97 = v185;
  if ( v185 < 4 )
  {
    CloudAPCacheNode = -1073281680;
    while ( 1 )
    {
      v98 = *(v12 - 1);
      v56 = v12--;
      v57 = v98 == 92;
      if ( v98 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v98 == 92;
        break;
      }
    }
    v163 = "Cache node is of invalid length";
    LODWORD(v157) = 1252;
    goto LABEL_325;
  }
  v99 = (unsigned int *)Destination;
  if ( *(_DWORD *)Destination )
  {
    v100 = 1;
    v101 = 0;
    v45 = 1;
  }
  else
  {
    if ( v185 - 4 < 4 )
    {
      CloudAPCacheNode = -1073281680;
      while ( 1 )
      {
        v102 = *(v12 - 1);
        v56 = v12--;
        v57 = v102 == 92;
        if ( v102 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v102 == 92;
          break;
        }
      }
      v163 = "Cache node doesnt have version";
      LODWORD(v157) = 1269;
      goto LABEL_325;
    }
    if ( *((_DWORD *)Destination + 1) != 1 )
      v45 = 1;
    if ( v185 - 8 < 4 )
    {
      CloudAPCacheNode = -1073281680;
      while ( 1 )
      {
        v103 = *(v12 - 1);
        v56 = v12--;
        v57 = v103 == 92;
        if ( v103 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v103 == 92;
          break;
        }
      }
      v163 = "Cache node doesnt have flags";
      LODWORD(v157) = 1284;
      goto LABEL_325;
    }
    v164[0] = *((_DWORD *)Destination + 1);
    v97 = v185 - 12;
    v101 = *((_DWORD *)Destination + 2);
    v99 = (unsigned int *)((char *)Destination + 12);
    v100 = v164[0];
  }
  *((_DWORD *)v95 + 1) = v100;
  v104 = v101 | 1;
  *(_DWORD *)v95 = 0;
  if ( !v45 )
    v104 = v101;
  *((_DWORD *)v95 + 2) = v104;
  v105 = *v99;
  *((_DWORD *)v95 + 3) = v105;
  if ( (int)v105 + 4 < (unsigned int)v105 )
  {
    CloudAPCacheNode = -1073741675;
    while ( 1 )
    {
      v144 = *(v12 - 1);
      v56 = v12--;
      v57 = v144 == 92;
      if ( v144 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v144 == 92;
        break;
      }
    }
    v163 = "RtlDWordAdd";
    LODWORD(v157) = 1306;
    goto LABEL_325;
  }
  if ( (int)v105 + 4 > v97 )
  {
    CloudAPCacheNode = -2147483643;
    while ( 1 )
    {
      v106 = *(v12 - 1);
      v56 = v12--;
      v57 = v106 == 92;
      if ( v106 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v106 == 92;
        break;
      }
    }
    v163 = "Overflow:cbCredKey > cbCacheNodeData";
    LODWORD(v157) = 1313;
    goto LABEL_325;
  }
  if ( g_pLsaFunctionTable )
    v107 = (HLOCAL)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v105);
  else
    v107 = LocalAlloc(0x40u, v105);
  v108 = v172;
  *((_QWORD *)v172 + 2) = v107;
  if ( !v107 )
  {
    CloudAPCacheNode = -1073741801;
    while ( 1 )
    {
      v109 = *(v12 - 1);
      v56 = v12--;
      v57 = v109 == 92;
      if ( v109 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v109 == 92;
        break;
      }
    }
    v163 = "AllocateMemory";
    LODWORD(v157) = 1321;
    goto LABEL_325;
  }
  v110 = *((unsigned int *)v108 + 3);
  *(_QWORD *)&v176.dwMinLength = v99 + 1;
  if ( memcpy_s_0(v107, v110, v99 + 1, (unsigned int)v110) )
  {
    CloudAPCacheNode = -1073741595;
    while ( 1 )
    {
      v112 = *(v12 - 1);
      v56 = v12--;
      v57 = v112 == 92;
      if ( v112 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v112 == 92;
        break;
      }
    }
    v163 = "memcpy_s";
    LODWORD(v157) = 1336;
    goto LABEL_325;
  }
  v113 = *(_DWORD *)v9;
  v114 = 74;
  if ( *(_DWORD *)v9 <= 6u && _bittest((const int *)&v114, v113) || (CloudAPCacheNode = 0, v113 == 7) )
  {
    v115 = (unsigned int *)*((_QWORD *)v108 + 2);
    v116 = *v115;
    if ( *v115 > *((_DWORD *)v172 + 3)
      || (v117 = (const unsigned __int16 *)v115[2], (unsigned int)v117 > v116)
      || (v118 = v115[3], v118 + (unsigned int)v117 < (unsigned int)v117)
      || v118 + (unsigned int)v117 > v116 )
    {
      CloudAPCacheNode = -1073281680;
      while ( 1 )
      {
        v127 = *(v12 - 1);
        v56 = v12--;
        v57 = v127 == 92;
        if ( v127 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v127 == 92;
          break;
        }
      }
      v163 = "DPAPI Cred key is corrupted";
      LODWORD(v157) = 1357;
      goto LABEL_325;
    }
    if ( v186 <= 6 && _bittest((const int *)&v114, v186) )
    {
      CloudAPCacheNode = DecryptBufferWithSecret(
                           v117,
                           *(unsigned __int8 **)(v9 + 8),
                           *(_DWORD *)(v9 + 4),
                           (unsigned __int8 *)v117 + (_QWORD)v115,
                           v118,
                           &v181,
                           &v169,
                           0,
                           0);
      if ( CloudAPCacheNode )
      {
        while ( 1 )
        {
          v119 = *(v12 - 1);
          v56 = v12--;
          v57 = v119 == 92;
          if ( v119 == 92 )
            break;
          if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
          {
            v57 = v119 == 92;
            break;
          }
        }
        v163 = "DecryptBufferWithSecret";
        LODWORD(v157) = 1374;
        goto LABEL_325;
      }
    }
    else
    {
      CloudAPCacheNode = FIDOGetCredHashFromCacheData(*(unsigned __int8 **)(v9 + 8), *(_DWORD *)(v9 + 4), &v183, &v173);
      if ( CloudAPCacheNode )
      {
        while ( 1 )
        {
          v121 = *(v12 - 1);
          v56 = v12--;
          v57 = v121 == 92;
          if ( v121 == 92 )
            break;
          if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
          {
            v57 = v121 == 92;
            break;
          }
        }
        v163 = "FIDOGetCredHashFromCacheData";
        LODWORD(v157) = 1385;
        goto LABEL_325;
      }
      CloudAPCacheNode = DecryptBufferWithSecret(
                           v120,
                           v183,
                           v173,
                           (unsigned __int8 *)(*((_QWORD *)v172 + 2) + v115[2]),
                           v115[3],
                           &v181,
                           &v169,
                           0,
                           0);
      if ( CloudAPCacheNode )
      {
        while ( 1 )
        {
          v122 = *(v12 - 1);
          v56 = v12--;
          v57 = v122 == 92;
          if ( v122 == 92 )
            break;
          if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
          {
            v57 = v122 == 92;
            break;
          }
        }
        v163 = "DecryptBufferWithSecret";
        LODWORD(v157) = 1399;
        goto LABEL_325;
      }
    }
    if ( v169 != HIDWORD(DestinationSize) )
      goto LABEL_276;
    LOBYTE(v111) = 0;
    v123 = 0;
    if ( v169 )
    {
      v114 = (__int64)v181;
      do
      {
        v124 = v181[v123];
        v125 = *((_BYTE *)v180 + v123);
        v123 = (unsigned int)(v123 + 1);
        LOBYTE(v111) = v125 ^ v124 | v111;
      }
      while ( (unsigned int)v123 < v169 );
      if ( (_BYTE)v111 )
      {
LABEL_276:
        CloudAPCacheNode = -1073741718;
        while ( 1 )
        {
          v126 = *(v12 - 1);
          v56 = v12--;
          v57 = v126 == 92;
          if ( v126 == 92 )
            break;
          if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
          {
            v57 = v126 == 92;
            break;
          }
        }
        v163 = "Derived key hashes do not match";
        LODWORD(v157) = 1406;
        goto LABEL_325;
      }
    }
  }
  v128 = v172;
  v129 = g_pLsaFunctionTable;
  v130 = *((unsigned int *)v172 + 3);
  v131 = v97 - v130 - 4;
  *((_DWORD *)v172 + 6) = v131;
  if ( v129 )
    v132 = (HLOCAL)((__int64 (__fastcall *)(_QWORD, struct _LSA_SECPKG_FUNCTION_TABLE *, __int64, __int64))v129->AllocateLsaHeap)(
                     v131,
                     v129,
                     v111,
                     v114);
  else
    v132 = LocalAlloc(0x40u, v131);
  *((_QWORD *)v128 + 4) = v132;
  if ( !v132 )
  {
    CloudAPCacheNode = -1073741801;
    while ( 1 )
    {
      v133 = *(v12 - 1);
      v56 = v12--;
      v57 = v133 == 92;
      if ( v133 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v133 == 92;
        break;
      }
    }
    v163 = "AllocateMemory";
    LODWORD(v157) = 1420;
    goto LABEL_325;
  }
  if ( memcpy_s_0(
         v132,
         *((unsigned int *)v128 + 6),
         (const void *const)(*(_QWORD *)&v176.dwMinLength + v130),
         *((unsigned int *)v128 + 6)) )
  {
    CloudAPCacheNode = -1073741595;
    while ( 1 )
    {
      v134 = *(v12 - 1);
      v56 = v12--;
      v57 = v134 == 92;
      if ( v134 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v57 = v134 == 92;
        break;
      }
    }
    v163 = "memcpy_s";
    LODWORD(v157) = 1430;
    goto LABEL_325;
  }
  v135 = v186;
  v136 = a6;
  *(_DWORD *)a6 = v186;
  if ( v135 == 7 )
  {
    v137 = *((unsigned int *)v44 + 5);
    *((_DWORD *)v136 + 1) = v137;
    Memory = AllocateMemory(v137);
    *((_QWORD *)v136 + 1) = Memory;
    if ( !Memory )
    {
      CloudAPCacheNode = -1073741801;
      while ( 1 )
      {
        v139 = *(v12 - 1);
        v56 = v12--;
        v57 = v139 == 92;
        if ( v139 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v139 == 92;
          break;
        }
      }
      v163 = "AllocateMemory";
      LODWORD(v157) = 1446;
      goto LABEL_325;
    }
    v140 = &v187[*((unsigned int *)v44 + 4)];
    v141 = *((unsigned int *)v44 + 5);
  }
  else
  {
    if ( !Src )
      goto LABEL_319;
    v142 = (unsigned int)Size;
    if ( !(_DWORD)Size )
      goto LABEL_319;
    *((_DWORD *)v136 + 1) = Size;
    Memory = AllocateMemory(v142);
    *((_QWORD *)v136 + 1) = Memory;
    if ( !Memory )
    {
      CloudAPCacheNode = -1073741801;
      while ( 1 )
      {
        v143 = *(v12 - 1);
        v56 = v12--;
        v57 = v143 == 92;
        if ( v143 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v57 = v143 == 92;
          break;
        }
      }
      v163 = "AllocateMemory";
      LODWORD(v157) = 1458;
      goto LABEL_325;
    }
    v141 = (unsigned int)Size;
    v140 = (unsigned __int8 *)Src;
  }
  memcpy_0(Memory, v140, v141);
LABEL_319:
  *a7 = v128;
  v172 = 0;
LABEL_329:
  if ( v177 )
    FreeMemory(v177);
  if ( hMem )
  {
    if ( g_pLsaFunctionTable )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    else
      LocalFree(hMem);
  }
LABEL_343:
  if ( v178 )
    LocalFree(v178);
  if ( Src )
  {
    if ( g_pLsaFunctionTable )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    else
      LocalFree(Src);
  }
  v146 = Source;
  if ( Source )
  {
    v147 = (unsigned int)DestinationSize;
    if ( (_DWORD)DestinationSize )
    {
      do
      {
        *v146++ = 0;
        --v147;
      }
      while ( v147 );
      v146 = Source;
    }
    LocalFree(v146);
  }
  v148 = Destination;
  if ( Destination )
  {
    v149 = v185;
    if ( v185 )
    {
      do
      {
        *v148++ = 0;
        --v149;
      }
      while ( v149 );
    }
    FreeMemory(Destination);
  }
  v150 = v180;
  if ( v180 )
  {
    v151 = HIDWORD(DestinationSize);
    v152 = v180;
    if ( HIDWORD(DestinationSize) )
    {
      do
      {
        *v152++ = 0;
        --v151;
      }
      while ( v151 );
    }
    FreeMemory(v150);
  }
  v153 = v181;
  if ( v181 )
  {
    v154 = v169;
    v155 = v181;
    if ( v169 )
    {
      do
      {
        *v155++ = 0;
        --v154;
      }
      while ( v154 );
    }
    FreeMemory(v153);
  }
  if ( v183 )
    FreeMemory(v183);
  if ( v172 )
    FreeCloudAPCacheNodeData(v172);
  return CloudAPCacheNode;
}

```

## disassembly

```asm
0x18001e130  mov     rax, rsp
0x18001e133  mov     [rax+18h], r8
0x18001e137  mov     [rax+10h], edx
0x18001e13a  push    rbp
0x18001e13b  push    rsi
0x18001e13c  lea     rbp, [rax-48h]
0x18001e140  sub     rsp, 138h
0x18001e147  xor     r11d, r11d
0x18001e14a  mov     [rax+20h], rbx
0x18001e14e  mov     [rax-18h], rdi
0x18001e152  xorps   xmm0, xmm0
0x18001e155  mov     [rax-20h], r12
0x18001e159  mov     r12d, r9d
0x18001e15c  mov     [rax-28h], r13
0x18001e160  mov     r10d, edx
0x18001e163  mov     [rax-30h], r14
0x18001e167  mov     r14, r8
0x18001e16a  mov     [rax-38h], r15
0x18001e16e  mov     r15d, r11d
0x18001e171  mov     dword ptr [rbp+40h+var_A0+4], r11d
0x18001e175  mov     r13, rcx
0x18001e178  mov     qword ptr [rsp+140h+var_F0], r11
0x18001e17d  mov     [rbp+40h+var_B0], r11
0x18001e181  mov     [rbp+40h+hMem], r11
0x18001e185  mov     [rbp+40h+var_80], r11
0x18001e189  mov     [rbp+40h+var_78], r11
0x18001e18d  mov     [rsp+140h+var_E8], r11
0x18001e192  mov     [rbp+40h+var_B8], r11
0x18001e196  mov     [rbp+40h+Src], r11
0x18001e19a  mov     dword ptr [rsp+140h+Size], r11d
0x18001e19f  mov     [rbp+40h+Source], r11
0x18001e1a3  mov     dword ptr [rsp+140h+DestinationSize], r11d
0x18001e1a8  mov     [rsp+140h+Destination], r11
0x18001e1ad  mov     [rbp+40h+arg_0], r11d
0x18001e1b1  mov     [rbp+40h+var_68], r11
0x18001e1b5  mov     dword ptr [rsp+140h+DestinationSize+4], r11d
0x18001e1ba  mov     [rbp+40h+var_60], r11
0x18001e1be  mov     [rsp+140h+var_C8], r11d
0x18001e1c3  mov     [rbp+40h+var_50], r11
0x18001e1c7  mov     [rbp+40h+var_A8], r11d
0x18001e1cb  movups  [rbp+40h+var_48], xmm0
0x18001e1cf  test    rcx, rcx
0x18001e1d2  jz      loc_18001F727
0x18001e1d8  test    r8, r8
0x18001e1db  jz      loc_18001F727
0x18001e1e1  mov     rcx, [rbp+40h+arg_30]
0x18001e1e8  test    rcx, rcx
0x18001e1eb  jz      loc_18001F727
0x18001e1f1  mov     rax, [rbp+40h+arg_28]
0x18001e1f5  test    rax, rax
0x18001e1f8  jz      loc_18001F727
0x18001e1fe  mov     [rcx], r11
0x18001e201  lea     rdi, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e208  lea     rdx, Class
0x18001e20f  lea     rbx, aOnecoreDsExtCl_2+3Dh; ""
0x18001e216  movups  xmmword ptr [rax], xmm0
0x18001e219  cmp     r10d, 6
0x18001e21d  jz      loc_18001ECE0
0x18001e223  mov     eax, r10d
0x18001e226  sub     eax, 1
0x18001e229  jz      loc_18001E2B0
0x18001e22f  sub     eax, 2
0x18001e232  jz      short loc_18001E2B0
0x18001e234  sub     eax, 1
0x18001e237  jz      short loc_18001E2B0
0x18001e239  sub     eax, 1
0x18001e23c  jz      short loc_18001E2B0
0x18001e23e  cmp     eax, 2
0x18001e241  jz      short loc_18001E2B0
0x18001e243  mov     rcx, rdi; char *
0x18001e246  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e24b  mov     dword ptr [rsp+140h+var_110], r10d
0x18001e250  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x18001e257  mov     r9, rax
0x18001e25a  mov     r8d, 0C000000Dh
0x18001e260  lea     rax, aInvalidcredtyp; "InvalidCredType"
0x18001e267  xor     ecx, ecx
0x18001e269  mov     [rsp+140h+var_118], rax
0x18001e26e  mov     dword ptr [rsp+140h+var_120], 207h
0x18001e276  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001e27b  mov     rcx, rdi; char *
0x18001e27e  mov     esi, 0C000000Dh
0x18001e283  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e288  mov     r9, rax
0x18001e28b  lea     r15, Class
0x18001e292  mov     [rsp+140h+var_110], r15
0x18001e297  lea     rax, aValidatecredty; "ValidateCredType"
0x18001e29e  mov     [rsp+140h+var_118], rax
0x18001e2a3  mov     dword ptr [rsp+140h+var_120], 3C4h
0x18001e2ab  jmp     loc_18001F77C
0x18001e2b0  lea     eax, [r10-1]
0x18001e2b4  test    eax, 0FFFFFFFDh
0x18001e2b9  jz      loc_18001ECE0
0x18001e2bf  cmp     r10d, 7
0x18001e2c3  jnz     loc_18001E618
0x18001e2c9  mov     edx, r12d; unsigned int
0x18001e2cc  mov     rcx, r14; unsigned __int8 *
0x18001e2cf  call    ?FIDOValidateAuthData@@YAJPEAEK@Z; FIDOValidateAuthData(uchar *,ulong)
0x18001e2d4  mov     esi, eax
0x18001e2d6  test    eax, eax
0x18001e2d8  jz      short loc_18001E31B
0x18001e2da  lea     rdi, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e2e1  movzx   eax, byte ptr [rbx-1]
0x18001e2e5  mov     rcx, rbx
0x18001e2e8  dec     rbx
0x18001e2eb  cmp     al, 5Ch ; '\'
0x18001e2ed  jz      short loc_18001E2F6
0x18001e2ef  cmp     rbx, rdi
0x18001e2f2  ja      short loc_18001E2E1
0x18001e2f4  cmp     al, 5Ch ; '\'
0x18001e2f6  lea     r15, Class
0x18001e2fd  mov     [rsp+140h+var_110], r15
0x18001e302  lea     rax, aValidatefidoau; "ValidateFIDOAuthData"
0x18001e309  mov     [rsp+140h+var_118], rax
0x18001e30e  mov     dword ptr [rsp+140h+var_120], 3E2h
0x18001e316  jmp     loc_18001F775
0x18001e31b  cmp     [r14+1Ch], r15d
0x18001e31f  jnz     short loc_18001E36A
0x18001e321  mov     esi, 0C000006Ah
0x18001e326  lea     rdi, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e32d  nop     dword ptr [rax]
0x18001e330  movzx   eax, byte ptr [rbx-1]
0x18001e334  mov     rcx, rbx
0x18001e337  dec     rbx
0x18001e33a  cmp     al, 5Ch ; '\'
0x18001e33c  jz      short loc_18001E345
0x18001e33e  cmp     rbx, rdi
0x18001e341  ja      short loc_18001E330
0x18001e343  cmp     al, 5Ch ; '\'
0x18001e345  lea     r15, Class
0x18001e34c  mov     [rsp+140h+var_110], r15
0x18001e351  lea     rax, aMissingFidoSec; "Missing FIDO secret"
0x18001e358  mov     [rsp+140h+var_118], rax
0x18001e35d  mov     dword ptr [rsp+140h+var_120], 3EBh
0x18001e365  jmp     loc_18001F775
0x18001e36a  mov     r8d, [r14+10h]
0x18001e36e  lea     rax, [rsp+140h+var_F0]
0x18001e373  mov     r9d, [r14+14h]
0x18001e377  add     r8, r14
0x18001e37a  mov     edx, 7
0x18001e37f  mov     [rsp+140h+var_120], rax
0x18001e384  mov     rcx, r13
0x18001e387  call    GetCloudAPCacheNode
0x18001e38c  mov     esi, eax
0x18001e38e  test    eax, eax
0x18001e390  jz      short loc_18001E3DA
0x18001e392  lea     rdi, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e399  nop     dword ptr [rax+00000000h]
0x18001e3a0  movzx   eax, byte ptr [rbx-1]
0x18001e3a4  mov     rcx, rbx
0x18001e3a7  dec     rbx
0x18001e3aa  cmp     al, 5Ch ; '\'
0x18001e3ac  jz      short loc_18001E3B5
0x18001e3ae  cmp     rbx, rdi
0x18001e3b1  ja      short loc_18001E3A0
0x18001e3b3  cmp     al, 5Ch ; '\'
0x18001e3b5  lea     r15, Class
0x18001e3bc  mov     [rsp+140h+var_110], r15
0x18001e3c1  lea     rax, aGetcloudapcach; "GetCloudAPCacheNode"
0x18001e3c8  mov     [rsp+140h+var_118], rax
0x18001e3cd  mov     dword ptr [rsp+140h+var_120], 3F5h
0x18001e3d5  jmp     loc_18001F775
0x18001e3da  mov     r15, qword ptr [rsp+140h+var_F0]
0x18001e3df  lea     rdx, [rbp+40h+var_90]; struct __BCRYPT_KEY_LENGTHS_STRUCT *
0x18001e3e3  mov     r14d, [r14+1Ch]
0x18001e3e7  xor     eax, eax
0x18001e3e9  mov     qword ptr [rbp+40h+var_90.dwMinLength], rax
0x18001e3ed  xor     r8d, r8d; unsigned int *
0x18001e3f0  mov     [rbp+40h+var_90.dwIncrement], eax
0x18001e3f3  mov     r13d, [r15+10h]
0x18001e3f7  mov     [rbp+40h+var_B8], rax
0x18001e3fb  mov     rax, [rbp+40h+arg_10]
0x18001e3ff  mov     r12d, [rax+18h]
0x18001e403  mov     rax, [r15+18h]
0x18001e407  mov     [rsp+140h+var_E8], rax
0x18001e40c  call    ?GetSupportedKeyLengths@@YAJPEBGPEAU__BCRYPT_KEY_LENGTHS_STRUCT@@PEAK@Z; GetSupportedKeyLengths(ushort const *,__BCRYPT_KEY_LENGTHS_STRUCT *,ulong *)
0x18001e411  mov     esi, eax
0x18001e413  test    eax, eax
0x18001e415  jz      short loc_18001E480
0x18001e417  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001e41e  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e425  nop     word ptr [rax+rax+00000000h]
0x18001e430  movzx   eax, byte ptr [r9-1]
0x18001e435  mov     rdx, r9
0x18001e438  dec     r9
0x18001e43b  cmp     al, 5Ch ; '\'
0x18001e43d  jz      short loc_18001E446
0x18001e43f  cmp     r9, rcx
0x18001e442  ja      short loc_18001E430
0x18001e444  cmp     al, 5Ch ; '\'
0x18001e446  cmovz   r9, rdx
0x18001e44a  lea     rax, aGetsupportedke; "GetSupportedKeyLengths"
0x18001e451  lea     r15, Class
0x18001e458  mov     r8d, esi
0x18001e45b  mov     [rsp+140h+var_110], r15
0x18001e460  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001e467  mov     [rsp+140h+var_118], rax
0x18001e46c  xor     ecx, ecx
0x18001e46e  mov     dword ptr [rsp+140h+var_120], 0D5h
0x18001e476  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001e47b  jmp     loc_18001E5C5
0x18001e480  mov     eax, [rbp+40h+var_90.dwMaxLength]
0x18001e483  lea     rcx, [rbp+40h+var_B8]; unsigned __int16 *
0x18001e487  shr     eax, 3
0x18001e48a  mov     rdx, r12
0x18001e48d  add     rdx, [rbp+40h+arg_10]; unsigned __int8 *
0x18001e491  mov     r9d, eax; unsigned int
0x18001e494  mov     r8d, r14d; unsigned int
0x18001e497  mov     [rsp+140h+var_F0], eax
0x18001e49b  mov     [rsp+140h+var_120], rcx; unsigned __int8 **
0x18001e4a0  call    ?DeriveKeyFromSecret@@YAJPEBGPEAEKKPEAPEAE@Z; DeriveKeyFromSecret(ushort const *,uchar *,ulong,ulong,uchar * *)
0x18001e4a5  mov     r14, [rbp+40h+var_B8]
0x18001e4a9  mov     esi, eax
0x18001e4ab  test    eax, eax
0x18001e4ad  jz      short loc_18001E4F0
0x18001e4af  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001e4b6  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e4bd  nop     dword ptr [rax]
0x18001e4c0  movzx   eax, byte ptr [r9-1]
0x18001e4c5  mov     rdx, r9
0x18001e4c8  dec     r9
0x18001e4cb  cmp     al, 5Ch ; '\'
0x18001e4cd  jz      short loc_18001E4D4
0x18001e4cf  cmp     r9, rcx
0x18001e4d2  ja      short loc_18001E4C0
0x18001e4d4  mov     r12d, [rsp+140h+var_F0]
0x18001e4d9  lea     r10, aDerivekeyfroms; "DeriveKeyFromSecret"
0x18001e4e0  xor     ecx, ecx
0x18001e4e2  mov     r8d, 0E0h
0x18001e4e8  cmp     al, 5Ch ; '\'
0x18001e4ea  cmovz   r9, rdx
0x18001e4ee  jmp     short loc_18001E569
0x18001e4f0  mov     r12d, [rsp+140h+var_F0]
0x18001e4f5  lea     rax, [rbp+40h+arg_0]
0x18001e4f9  mov     rdx, [rsp+140h+var_E8]; unsigned __int8 *
0x18001e4fe  mov     r9, r14; unsigned __int8 *
0x18001e501  mov     [rsp+140h+var_110], rax; unsigned int *
0x18001e506  mov     r8d, r13d; unsigned int
0x18001e509  lea     rax, [rsp+140h+Destination]
0x18001e50e  mov     [rsp+140h+var_118], rax; unsigned __int8 **
0x18001e513  mov     dword ptr [rsp+140h+var_120], r12d; unsigned int
0x18001e518  call    ?DecryptBufferWithKey@@YAJPEBGPEAEK1KPEAPEAEPEAK@Z; DecryptBufferWithKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18001e51d  mov     esi, eax
0x18001e51f  test    eax, eax
0x18001e521  jz      loc_18001E603
0x18001e527  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001e52e  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e535  nop     word ptr [rax+rax+00000000h]
0x18001e540  movzx   eax, byte ptr [r9-1]
0x18001e545  mov     r8, r9
0x18001e548  dec     r9
0x18001e54b  cmp     al, 5Ch ; '\'
0x18001e54d  jz      short loc_18001E554
0x18001e54f  cmp     r9, rcx
0x18001e552  ja      short loc_18001E540
0x18001e554  xor     ecx, ecx
0x18001e556  lea     r10, aDecryptbufferw; "DecryptBufferWithKey"
0x18001e55d  cmp     al, 5Ch ; '\'
0x18001e55f  cmovz   r9, r8
0x18001e563  mov     r8d, 0EAh
0x18001e569  lea     r15, Class
0x18001e570  mov     rax, r15
0x18001e573  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001e57a  mov     [rsp+140h+var_110], rax
0x18001e57f  mov     rdx, r11
0x18001e582  mov     [rsp+140h+var_118], r10
0x18001e587  mov     dword ptr [rsp+140h+var_120], r8d
0x18001e58c  mov     r8d, esi
0x18001e58f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001e594  test    r14, r14
0x18001e597  jz      short loc_18001E5C5
0x18001e599  mov     edx, r12d
0x18001e59c  mov     rax, r14
0x18001e59f  test    r12d, r12d
0x18001e5a2  jz      short loc_18001E5BD
0x18001e5a4  nop     dword ptr [rax+00h]
0x18001e5a8  nop     dword ptr [rax+rax+00000000h]
0x18001e5b0  mov     byte ptr [rax], 0
0x18001e5b3  lea     rax, [rax+1]
0x18001e5b7  sub     rdx, 1
0x18001e5bb  jnz     short loc_18001E5B0
0x18001e5bd  mov     rcx, r14; void *
0x18001e5c0  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18001e5c5  lea     rdi, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001e5cc  nop     dword ptr [rax+00h]
0x18001e5d0  movzx   eax, byte ptr [rbx-1]
0x18001e5d4  mov     rcx, rbx
0x18001e5d7  dec     rbx
0x18001e5da  cmp     al, 5Ch ; '\'
0x18001e5dc  jz      short loc_18001E5E5
0x18001e5de  cmp     rbx, rdi
0x18001e5e1  ja      short loc_18001E5D0
0x18001e5e3  cmp     al, 5Ch ; '\'
0x18001e5e5  mov     [rsp+140h+var_110], r15
0x18001e5ea  lea     rax, aDecryptbufferw_0; "DecryptBufferWithSecret"
0x18001e5f1  mov     [rsp+140h+var_118], rax
0x18001e5f6  mov     dword ptr [rsp+140h+var_120], 402h
0x18001e5fe  jmp     loc_18001F775
0x18001e603  mov     dword ptr [rsp+140h+DestinationSize+4], r12d
0x18001e608  mov     r12, [rbp+40h+arg_10]
  ... truncated ...
```
