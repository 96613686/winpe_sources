# AddCloudAPCacheNode(_CloudAPCache *,ulong,ulong,uchar *,ulong,_CREDENTIAL_KEY *,_AP_BLOB *,_SCARD_PIN *,_tagCacheNodeIdentifier *)

- ea: `0x180024bb0`
- end: `0x180026afb`
- name: `?AddCloudAPCacheNode@@YAJPEAU_CloudAPCache@@KKPEAEKPEAU_CREDENTIAL_KEY@@PEAU_AP_BLOB@@PEAU_SCARD_PIN@@PEAU_tagCacheNodeIdentifier@@@Z`
- size: `8011`
- prototype: `__int64 __fastcall(struct _CloudAPCache *, int, unsigned int, unsigned __int8 *, unsigned int, struct _CREDENTIAL_KEY *Source, struct _AP_BLOB *, struct _SCARD_PIN *, struct _tagCacheNodeIdentifier *)`
- caller_count: `4`
- callee_count: `23`
- tags: ``

## callers

- `0x18000e1ec`
- `0x180037240`
- `0x180048530`
- `0x18005f95c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180022bc0`
- `0x180022f40`
- `0x180024bb0`
- `0x1800293c0`
- `0x18002d4b8`
- `0x18002f59c`
- `0x18002f910`
- `0x180033b7c`
- `0x180035fa4`
- `0x18003c220`
- `0x18003c598`
- `0x18003c840`
- `0x18003d41c`
- `0x18003e6f4`
- `0x18003e934`
- `0x18003f220`
- `0x180043158`
- `0x180063b54`
- `0x180064104`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x1800255c4`
- `bcrypt!BCryptEncrypt` at `0x1800256ce`
- `bcrypt!BCryptEncrypt` at `0x180025d19`
- `bcrypt!BCryptEncrypt` at `0x180025e0e`
- `bcrypt!BCryptEncrypt` at `0x1800255c4`
- `bcrypt!BCryptEncrypt` at `0x1800256ce`
- `bcrypt!BCryptEncrypt` at `0x180025d19`
- `bcrypt!BCryptEncrypt` at `0x180025e0e`
- `bcrypt!BCryptDestroyKey` at `0x180025989`
- `bcrypt!BCryptDestroyKey` at `0x180026085`
- `bcrypt!BCryptDestroyKey` at `0x180025989`
- `bcrypt!BCryptDestroyKey` at `0x180026085`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026136`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002615c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026abc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026acb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026136`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002615c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026abc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026acb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024dd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024dd3`
- `cryptngc!NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold` at `0x1800261a7`
- `cryptngc!NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold` at `0x1800261a7`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x1800261c1`
- `cryptngc!NgcGetUserIdKeyPublicKey` at `0x1800261c1`
- `cryptngc!NgcUnpackCredData` at `0x180025b76`
- `cryptngc!NgcUnpackCredData` at `0x180025b76`

## string_xrefs

- `0x180024caa`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180024d05`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180024d51`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180024de1`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180024e68`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002695f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180026841`: `GetCloudAPCacheNode`
- `0x180024f6a`: `CreateCacheNodeDataBuffer`
- `0x180025311`: `FIDOCreateCacheData`
- `0x18002537c`: `FIDOGetCredentialIDFromCacheData`
- `0x18002621a`: `RemoveCloudAPCacheNode`
- `0x180026551`: `The cache has no room for more nodes`
- `0x1800266fc`: `cache nodes == 0`
- `0x180026322`: `_ValidateSCardCacheData`

## pseudocode

```c
__int64 __fastcall AddCloudAPCacheNode(
        struct _CloudAPCache *a1,
        int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct _CREDENTIAL_KEY *Source,
        struct _AP_BLOB *a7,
        struct _SCARD_PIN *a8,
        struct _tagCacheNodeIdentifier *a9)
{
  unsigned __int8 *v9; // rsi
  unsigned int SupportedKeyLengths; // edi
  const char *v13; // r9
  UCHAR *v14; // rsi
  const char *v15; // r9
  int v16; // ecx
  rsize_t v17; // rdi
  const char *v18; // r9
  void *v19; // rcx
  unsigned int v20; // r15d
  __int64 v21; // rbx
  const char *v22; // rax
  char *v23; // r12
  const char *v24; // rax
  __int64 v25; // r8
  const char *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r10
  const char *v29; // r11
  int v30; // ecx
  const char *v31; // r9
  char *v32; // rax
  const char *v33; // rbx
  char v34; // al
  const char *v35; // rcx
  bool v36; // zf
  char *v37; // rdi
  const unsigned __int16 *v38; // rcx
  unsigned __int8 *v39; // r12
  const char *v40; // rbx
  int v41; // edx
  unsigned int v42; // r14d
  char v43; // al
  const char *v44; // rcx
  bool v45; // zf
  UCHAR *v46; // r14
  char v47; // al
  __int64 v48; // rax
  char v49; // al
  const unsigned __int16 *v50; // rcx
  char v51; // al
  unsigned __int8 *v52; // rsi
  const unsigned __int16 *v53; // rcx
  char v54; // al
  const char *v55; // rcx
  bool v56; // zf
  char v57; // al
  const char *v58; // rcx
  bool v59; // zf
  HLOCAL v60; // rbx
  unsigned int v61; // r12d
  char v62; // al
  char v63; // al
  const char *v64; // rcx
  bool v65; // zf
  HLOCAL v66; // r12
  HLOCAL v67; // r8
  unsigned int v68; // r14d
  char v69; // al
  const char *v70; // r14
  char v71; // al
  const char *v72; // rcx
  bool v73; // zf
  unsigned int v74; // r14d
  const char *v75; // r14
  char v76; // al
  const char *v77; // rcx
  bool v78; // zf
  HLOCAL v79; // r14
  HLOCAL v80; // r12
  char v81; // al
  const char *v82; // r14
  char v83; // cl
  const char *v84; // rdx
  bool v85; // zf
  char v86; // al
  const unsigned __int16 *v87; // rcx
  char v88; // al
  char v89; // al
  size_t v90; // r12
  size_t v91; // rdi
  size_t v92; // r14
  unsigned int v93; // esi
  _DWORD *Memory; // rax
  const char *v95; // r14
  char v96; // al
  const char *v97; // rcx
  bool v98; // zf
  void *v99; // rdx
  _DWORD *v100; // rsi
  _DWORD *v101; // rcx
  char *v102; // rsi
  HLOCAL v103; // rdx
  unsigned int v104; // eax
  __int64 v105; // rdi
  _DWORD *v106; // rcx
  char *v107; // rsi
  const void *v108; // rdx
  char *v109; // rcx
  size_t v110; // r8
  unsigned __int8 *v111; // r12
  int v112; // eax
  HLOCAL v113; // rdx
  HLOCAL v114; // rcx
  __int64 v115; // rdx
  _BYTE *v116; // rax
  char v117; // al
  char v118; // al
  int v119; // eax
  unsigned int v120; // eax
  char v121; // al
  unsigned int v122; // esi
  const char *v123; // r14
  const char *v124; // r9
  char v125; // al
  const char *v126; // rcx
  bool v127; // zf
  char v128; // al
  const char *v129; // r9
  char v130; // cl
  const char *v131; // rdx
  bool v132; // zf
  char v133; // al
  const unsigned __int16 *v134; // rcx
  char v135; // al
  char v136; // al
  size_t v137; // rdi
  unsigned int v138; // esi
  _DWORD *v139; // rax
  char v140; // al
  const void *v141; // rdx
  _DWORD *v142; // rsi
  _DWORD *v143; // rcx
  char *v144; // rsi
  void *v145; // rdx
  unsigned int v146; // eax
  __int64 v147; // rdi
  _DWORD *v148; // rcx
  char *v149; // rsi
  const void *v150; // rdx
  unsigned int v151; // eax
  __int64 v152; // rdi
  HLOCAL v153; // rdx
  char *v154; // rcx
  unsigned __int8 *v155; // rdi
  size_t v156; // r8
  HLOCAL v157; // rcx
  __int64 v158; // rdx
  _BYTE *v159; // rax
  int LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold; // eax
  int UserIdKeyPublicKey; // eax
  unsigned int v162; // eax
  char v163; // al
  __int64 v164; // r8
  const char *v165; // r9
  unsigned int v166; // eax
  char v167; // al
  const char *v168; // rcx
  bool v169; // zf
  unsigned int v170; // eax
  char v171; // al
  unsigned __int8 *v172; // rsi
  char v173; // al
  const char *v174; // rcx
  int v175; // eax
  void *v176; // rax
  char v177; // al
  const char *v178; // r8
  char v179; // al
  int v180; // esi
  unsigned int v181; // edi
  unsigned int v182; // r14d
  unsigned int i; // eax
  __int64 v184; // r8
  __int64 v185; // rcx
  __int64 v186; // rdx
  _OWORD *v187; // rsi
  unsigned int v188; // r8d
  __int64 v189; // r9
  unsigned int v190; // edi
  unsigned int v191; // ecx
  int v192; // edx
  char v193; // al
  unsigned int v194; // eax
  unsigned int j; // edi
  __int64 v196; // r8
  __int64 v197; // rcx
  __int64 v198; // rdx
  unsigned int v199; // edi
  UCHAR *v200; // rax
  char v201; // cl
  const char *v202; // rdx
  bool v203; // zf
  char v204; // al
  const char *v205; // rcx
  bool v206; // zf
  void *v207; // rcx
  char v208; // al
  const char *v209; // rcx
  bool v210; // zf
  void *v211; // rax
  char v212; // al
  const char *v213; // rcx
  bool v214; // zf
  __int128 v215; // xmm1
  char v216; // al
  const char *v217; // r14
  char v218; // al
  const char *v219; // rcx
  bool v220; // zf
  char v221; // al
  char v222; // al
  char v223; // al
  unsigned __int8 *v224; // rcx
  __int64 v225; // rdx
  unsigned __int8 *v226; // rax
  __int64 v227; // rdx
  UCHAR *v228; // rax
  UCHAR *v229; // rax
  __int64 k; // rdx
  PUCHAR pbIV; // [rsp+20h] [rbp-E0h]
  PUCHAR pbIVa; // [rsp+20h] [rbp-E0h]
  PUCHAR pbIVb; // [rsp+20h] [rbp-E0h]
  int pbIVc; // [rsp+20h] [rbp-E0h]
  const char *cbIV; // [rsp+28h] [rbp-D8h]
  const char *cbIVa; // [rsp+28h] [rbp-D8h]
  const char *cbIVb; // [rsp+28h] [rbp-D8h]
  const char *cbIVc; // [rsp+28h] [rbp-D8h]
  const char *cbIVd; // [rsp+28h] [rbp-D8h]
  UCHAR *pbInput; // [rsp+50h] [rbp-B0h]
  HLOCAL v242; // [rsp+58h] [rbp-A8h]
  unsigned int v243; // [rsp+60h] [rbp-A0h] BYREF
  void *v244; // [rsp+68h] [rbp-98h]
  ULONG pcbResult; // [rsp+70h] [rbp-90h] BYREF
  unsigned int SourceSize[3]; // [rsp+74h] [rbp-8Ch] BYREF
  HLOCAL v247; // [rsp+80h] [rbp-80h] BYREF
  size_t Size; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v249; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v250; // [rsp+98h] [rbp-68h]
  HLOCAL pbOutput; // [rsp+A0h] [rbp-60h] BYREF
  void *Src; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v253; // [rsp+B0h] [rbp-50h]
  HLOCAL hMem; // [rsp+B8h] [rbp-48h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+C0h] [rbp-40h] BYREF
  size_t v256; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v257[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v258[2]; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL v259; // [rsp+F0h] [rbp-10h] BYREF
  struct __BCRYPT_KEY_LENGTHS_STRUCT v260; // [rsp+F8h] [rbp-8h] BYREF
  const char *v261; // [rsp+108h] [rbp+8h]
  unsigned int v262; // [rsp+110h] [rbp+10h]
  unsigned int v263; // [rsp+114h] [rbp+14h] BYREF
  HLOCAL v264; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int8 *v265; // [rsp+120h] [rbp+20h] BYREF
  HLOCAL v266; // [rsp+128h] [rbp+28h] BYREF
  HLOCAL v267; // [rsp+130h] [rbp+30h] BYREF
  __int64 v268; // [rsp+138h] [rbp+38h] BYREF
  _OWORD *v269; // [rsp+140h] [rbp+40h] BYREF
  HLOCAL v270; // [rsp+148h] [rbp+48h] BYREF
  __int64 v271; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int8 *v272; // [rsp+158h] [rbp+58h]
  __int128 v273; // [rsp+160h] [rbp+60h] BYREF
  ULONG cbInput; // [rsp+1B0h] [rbp+B0h]

  v269 = 0;
  v244 = 0;
  v247 = 0;
  *(_QWORD *)&SourceSize[1] = 0;
  v9 = a4;
  v262 = 0;
  *(_QWORD *)&v260.dwMinLength = 0;
  v260.dwIncrement = 0;
  v265 = 0;
  v253 = 0;
  cbInput = 0;
  v242 = 0;
  pbOutput = 0;
  v249 = 0;
  HIDWORD(Size) = 0;
  v270 = 0;
  v264 = 0;
  v271 = 0;
  v268 = 0;
  v266 = 0;
  v267 = 0;
  v263 = 0;
  v243 = 0;
  v273 = 0;
  *(_OWORD *)v257 = 0;
  *(_OWORD *)v258 = 0;
  if ( !a1 || !a4 || !Source || !a7 || !*((_QWORD *)a7 + 1) )
  {
    SupportedKeyLengths = -1073741811;
    v33 = "";
    while ( 1 )
    {
      v223 = *(v33 - 1);
      v35 = v33--;
      v36 = v223 == 92;
      if ( v223 == 92 )
        break;
      if ( v33 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v36 = v223 == 92;
        break;
      }
    }
    cbIV = "InvalidArgs";
    LODWORD(pbIV) = 1591;
    goto LABEL_435;
  }
  if ( a9 )
    *(_OWORD *)a9 = 0;
  if ( *(_DWORD *)Source < 0x20u )
  {
    SupportedKeyLengths = -1073741811;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v13, 1602, "InvalidArg:pCredKeyCurrent", &Class);
LABEL_10:
    v14 = 0;
LABEL_438:
    v46 = v14;
    goto LABEL_439;
  }
  SupportedKeyLengths = ValidateCredType(a3);
  if ( SupportedKeyLengths )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v15, 1606, "ValidateCredType", &Class);
    goto LABEL_10;
  }
  v16 = *((_DWORD *)Source + 2);
  v17 = *(unsigned int *)Source;
  LODWORD(v250) = *((_DWORD *)Source + 3);
  LODWORD(v257[0]) = a3;
  LODWORD(Size) = v16;
  if ( v16 + (int)v250 > (unsigned int)v17 )
  {
    SupportedKeyLengths = -1073741811;
    v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v18, 1615, "InvalidArg:pCredKeyCurrent", &Class);
    goto LABEL_10;
  }
  v19 = (void *)*((_QWORD *)a7 + 1);
  cbInput = 0;
  v20 = *(_DWORD *)a7 + v17;
  SourceSize[0] = *(_DWORD *)a7;
  v21 = v20 + 16;
  Src = v19;
  LODWORD(v256) = v20;
  if ( g_pLsaFunctionTable )
    v22 = (const char *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v20 + 16);
  else
    v22 = (const char *)LocalAlloc(0x40u, v20 + 16);
  v23 = (char *)v22;
  if ( !v22 )
  {
    SupportedKeyLengths = -1073741801;
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v24, 769, v25, &Class);
    goto LABEL_27;
  }
  *((_DWORD *)v22 + 2) = a2;
  *((_DWORD *)v22 + 3) = v17;
  *(_DWORD *)v22 = 0;
  *((_DWORD *)v22 + 1) = 1;
  v261 = v22 + 16;
  if ( memcpy_s_0((void *const)(v22 + 16), v20, Source, v17) )
  {
    SupportedKeyLengths = -1073741595;
    v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v30 = 801;
    v31 = "memcpy_s";
LABEL_24:
    WPPTraceLogA(v28, v29, v27, v26, v30, v31, &Class);
    v32 = v23;
    if ( v20 != -16 )
    {
      do
      {
        *v32++ = 0;
        --v21;
      }
      while ( v21 );
    }
    FreeMemory(v23);
LABEL_27:
    v33 = "";
    while ( 1 )
    {
      v34 = *(v33 - 1);
      v35 = v33--;
      v36 = v34 == 92;
      if ( v34 == 92 )
        break;
      if ( v33 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v36 = v34 == 92;
        break;
      }
    }
    cbIV = "CreateCacheNodeDataBuffer";
    LODWORD(pbIV) = 1629;
LABEL_435:
    if ( v36 )
      v33 = v35;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v33, pbIV, cbIV, &Class);
    v14 = *(UCHAR **)&SourceSize[1];
    goto LABEL_438;
  }
  if ( memcpy_s_0((void *const)&v261[v17], SourceSize[0], Src, SourceSize[0]) )
  {
    SupportedKeyLengths = -1073741595;
    v261 = (const char *)&Class;
    v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v30 = 815;
    goto LABEL_24;
  }
  v37 = v23;
  pbInput = (UCHAR *)v23;
  v38 = (const unsigned __int16 *)(unsigned int)(v256 + 16);
  cbInput = v256 + 16;
  v39 = (unsigned __int8 *)Source + (unsigned int)Size;
  v261 = "AllocateMemory";
  v40 = "";
  v272 = v39;
  if ( a3 <= 6 )
  {
    v41 = 74;
    if ( _bittest(&v41, a3) )
    {
      v42 = a5;
      Src = 0;
      goto LABEL_51;
    }
  }
  if ( a3 != 7 )
  {
    if ( a3 == 4 )
    {
      if ( a5 != 24 )
      {
        SupportedKeyLengths = -1073741582;
        while ( 1 )
        {
          v69 = *(v40 - 1);
          v44 = v40--;
          v45 = v69 == 92;
          if ( v69 == 92 )
            break;
          if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
          {
            v45 = v69 == 92;
            break;
          }
        }
        cbIVa = "Invalid Size";
        LODWORD(pbIV) = 1727;
        goto LABEL_41;
      }
      pcbResult = 0;
      v243 = 0;
      Size = 0;
      SourceSize[0] = 0;
      LODWORD(v256) = 0;
      hKey = 0;
      hMem = 0;
      v259 = 0;
      *(_QWORD *)&v260.dwMinLength = 0;
      v247 = 0;
      Src = 0;
      if ( !*(_QWORD *)v9 )
      {
        SupportedKeyLengths = -1073741811;
        v70 = "";
        do
        {
          v71 = *(v70 - 1);
          v72 = v70--;
          v73 = v71 == 92;
          if ( v71 == 92 )
            goto LABEL_102;
        }
        while ( v70 > "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" );
        v73 = v71 == 92;
LABEL_102:
        pbIVc = 1181;
        goto LABEL_195;
      }
      if ( !v39 || (v74 = (unsigned int)v250) == 0 || !v37 || !(_DWORD)v38 )
      {
        SupportedKeyLengths = -1073741811;
        v70 = "";
        do
        {
          v117 = *(v70 - 1);
          v72 = v70--;
          v73 = v117 == 92;
          if ( v117 == 92 )
            goto LABEL_194;
        }
        while ( v70 > "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" );
        v73 = v117 == 92;
LABEL_194:
        pbIVc = 1205;
LABEL_195:
        if ( v73 )
          v70 = v72;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v70, pbIVc, "Null Arg(s)", &Class);
        goto LABEL_198;
      }
      pbOutput = 0;
      v250 = 0;
      v257[1] = 0;
      v258[1] = 0;
      HIDWORD(v257[0]) = 0;
      LODWORD(v258[0]) = 0;
      SupportedKeyLengths = _GenerateAesKey(
                              &hKey,
                              (unsigned __int8 **)&hMem,
                              &v243,
                              (unsigned __int8 **)&v259,
                              (unsigned int *)&Size);
      if ( SupportedKeyLengths )
      {
        v75 = "";
        while ( 1 )
        {
          v76 = *(v75 - 1);
          v77 = v75--;
          v78 = v76 == 92;
          if ( v76 == 92 )
            break;
          if ( v75 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
          {
            v78 = v76 == 92;
            break;
          }
        }
        cbIVb = "_GenerateAesKey";
        LODWORD(pbIV) = 1218;
      }
      else
      {
        SupportedKeyLengths = BCryptEncrypt(hKey, pbInput, cbInput, 0, 0, 0, 0, 0, &pcbResult, 1u);
        if ( SupportedKeyLengths )
        {
          v75 = "";
          while ( 1 )
          {
            v81 = *(v75 - 1);
            v77 = v75--;
            v78 = v81 == 92;
            if ( v81 == 92 )
              break;
            if ( v75 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
            {
              v78 = v81 == 92;
              break;
            }
          }
          cbIVb = "BCryptEncrypt";
          LODWORD(pbIV) = 1232;
        }
        else
        {
          pbOutput = AllocateMemory(pcbResult);
          if ( !pbOutput )
          {
            SupportedKeyLengths = -1073741801;
            v82 = "";
            while ( 1 )
            {
              v83 = *(v82 - 1);
              v84 = v82--;
              v85 = v83 == 92;
              if ( v83 == 92 )
                break;
              if ( v82 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
              {
                v85 = v83 == 92;
                break;
              }
            }
            if ( v85 )
              v82 = v84;
            LODWORD(pbIV) = 1238;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v82, pbIV, "AllocateMemory", &Class);
            goto LABEL_116;
          }
          SupportedKeyLengths = BCryptEncrypt(
                                  hKey,
                                  pbInput,
                                  cbInput,
                                  0,
                                  0,
                                  0,
                                  (PUCHAR)pbOutput,
                                  pcbResult,
                                  &pcbResult,
                                  1u);
          if ( SupportedKeyLengths )
          {
            v75 = "";
            while ( 1 )
            {
              v86 = *(v75 - 1);
              v77 = v75--;
              v78 = v86 == 92;
              if ( v86 == 92 )
                break;
              if ( v75 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
              {
                v78 = v86 == 92;
                break;
              }
            }
            cbIVb = "BCryptEncrypt";
            LODWORD(pbIV) = 1252;
          }
          else
          {
            SupportedKeyLengths = _EncryptWithSCard(
                                    (struct _SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA *)v9,
                                    (unsigned __int8 *)hMem,
                                    v243,
                                    a8,
                                    (unsigned __int8 **)&v260,
                                    SourceSize,
                                    (unsigned __int8 **)&Src,
                                    (unsigned int *)&Size + 1);
            if ( SupportedKeyLengths )
            {
              v75 = "";
              while ( 1 )
              {
                v88 = *(v75 - 1);
                v77 = v75--;
                v78 = v88 == 92;
                if ( v88 == 92 )
                  break;
                if ( v75 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                {
                  v78 = v88 == 92;
                  break;
                }
              }
              cbIVb = "_EncryptWithSCard";
              LODWORD(pbIV) = 1267;
            }
            else
            {
              SupportedKeyLengths = EncryptBufferWithSecret(
                                      v87,
                                      (unsigned __int8 *)hMem,
                                      v243,
                                      v39,
                                      v74,
                                      (unsigned __int8 **)&v247,
                                      (unsigned int *)&v256);
              if ( !SupportedKeyLengths )
              {
                v90 = SourceSize[0];
                v91 = HIDWORD(Size);
                v92 = (unsigned int)v256;
                v93 = SourceSize[0] + HIDWORD(Size) + v256 + Size + 40;
                SourceSize[0] = v93;
                Memory = AllocateMemory(v93);
                v250 = Memory;
                if ( Memory )
                {
                  v99 = Src;
                  Memory[1] = v93;
                  v100 = Memory + 10;
                  *Memory = 0;
                  Memory[3] = v91;
                  Memory[2] = 40;
                  memcpy_0(Memory + 10, v99, v91);
                  v101 = v250;
                  v102 = (char *)v100 + v91;
                  v103 = v259;
                  *((_DWORD *)v250 + 4) = (_DWORD)v102 - (_DWORD)v250;
                  v104 = Size;
                  v101[5] = Size;
                  v105 = v104;
                  memcpy_0(v102, v103, v104);
                  v106 = v250;
                  v107 = &v102[v105];
                  v108 = *(const void **)&v260.dwMinLength;
                  *((_DWORD *)v250 + 6) = (_DWORD)v107 - (_DWORD)v250;
                  v106[7] = v90;
                  memcpy_0(v107, v108, v90);
                  v109 = &v107[v90];
                  v110 = v92;
                  v111 = (unsigned __int8 *)v250;
                  v112 = (_DWORD)v109 - (_DWORD)v250;
                  *((_DWORD *)v250 + 9) = v92;
                  v79 = v247;
                  v113 = v247;
                  *((_DWORD *)v111 + 8) = v112;
                  memcpy_0(v109, v113, v110);
                  v258[1] = (unsigned __int8 *)pbOutput;
                  pbOutput = 0;
                  v257[1] = v111;
                  v80 = 0;
                  LODWORD(v258[0]) = pcbResult;
                  SupportedKeyLengths = 0;
                  HIDWORD(v257[0]) = SourceSize[0];
LABEL_158:
                  if ( hKey )
                    BCryptDestroyKey(hKey);
                  v114 = hMem;
                  if ( hMem )
                  {
                    v115 = v243;
                    v116 = hMem;
                    if ( v243 )
                    {
                      do
                      {
                        *v116++ = 0;
                        --v115;
                      }
                      while ( v115 );
                    }
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(v114);
                  }
                  if ( v259 )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(v259);
                  }
                  if ( pbOutput )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(pbOutput);
                  }
                  if ( *(_QWORD *)&v260.dwMinLength )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(*(HLOCAL *)&v260.dwMinLength);
                  }
                  if ( v79 )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (__fastcall *)(HLOCAL))g_pLsaFunctionTable->FreeLsaHeap)(v79);
                    else
                      LocalFree(v79);
                  }
                  if ( v80 )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (__fastcall *)(HLOCAL))g_pLsaFunctionTable->FreeLsaHeap)(v80);
                    else
                      LocalFree(v80);
                  }
                  if ( Src )
                    LocalFree(Src);
                  if ( SupportedKeyLengths )
                  {
LABEL_198:
                    while ( 1 )
                    {
                      v118 = *(v40 - 1);
                      v44 = v40--;
                      v45 = v118 == 92;
                      if ( v118 == 92 )
                        break;
                      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
                      {
                        v45 = v118 == 92;
                        break;
                      }
                    }
                    cbIVa = "PKEncryptData";
                    LODWORD(pbIV) = 1746;
                    goto LABEL_41;
                  }
                  goto LABEL_341;
                }
                SupportedKeyLengths = -1073741801;
                v95 = "";
                while ( 1 )
                {
                  v96 = *(v95 - 1);
                  v97 = v95--;
                  v98 = v96 == 92;
                  if ( v96 == 92 )
                    break;
                  if ( v95 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                  {
                    v98 = v96 == 92;
                    break;
                  }
                }
                if ( v98 )
                  v95 = v97;
                LODWORD(pbIV) = 1307;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v95, pbIV, "AllocateMemory", &Class);
LABEL_116:
                v79 = v247;
                v80 = v250;
                goto LABEL_158;
              }
              v75 = "";
              while ( 1 )
              {
                v89 = *(v75 - 1);
                v77 = v75--;
                v78 = v89 == 92;
                if ( v89 == 92 )
                  break;
                if ( v75 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                {
                  v78 = v89 == 92;
                  break;
                }
              }
              cbIVb = "EncryptBufferWithSecret";
              LODWORD(pbIV) = 1293;
            }
          }
        }
      }
      if ( v78 )
        v75 = v77;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v75, pbIV, cbIVb, &Class);
      goto LABEL_116;
    }
    v119 = NgcUnpackCredData(v9, a5, &v270, &v271, &v264, &v268);
    if ( v119 < 0 )
    {
      SupportedKeyLengths = (unsigned __int16)v119;
      v120 = (unsigned __int16)v119 | 0xC0070000;
      if ( SupportedKeyLengths )
        SupportedKeyLengths = v120;
      while ( 1 )
      {
        v121 = *(v40 - 1);
        v44 = v40--;
        v45 = v121 == 92;
        if ( v121 == 92 )
          break;
        if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v45 = v121 == 92;
          break;
        }
      }
      cbIVa = "NgcUnpackCredData";
      LODWORD(pbIV) = 1761;
      goto LABEL_41;
    }
    *(_QWORD *)&v273 = v264;
    *((_QWORD *)&v273 + 1) = v268;
    v243 = 0;
    Size = 0;
    pcbResult = 0;
    v249 = 0;
    SourceSize[0] = 0;
    pbOutput = 0;
    hMem = 0;
    Src = 0;
    *(_QWORD *)&v260.dwMinLength = 0;
    v259 = 0;
    v256 = 0;
    if ( v264 )
    {
      if ( v39 )
      {
        v122 = (unsigned int)v250;
        if ( (_DWORD)v250 )
        {
          if ( v37 && cbInput )
          {
            hKey = 0;
            v247 = 0;
            v257[1] = 0;
            v258[1] = 0;
            HIDWORD(v257[0]) = 0;
            LODWORD(v258[0]) = 0;
            v123 = "";
            SupportedKeyLengths = _GenerateAesKey(
                                    &pbOutput,
                                    (unsigned __int8 **)&hMem,
                                    &v243,
                                    (unsigned __int8 **)&Src,
                                    (unsigned int *)&Size);
            if ( SupportedKeyLengths )
            {
              v124 = "";
              while ( 1 )
              {
                v125 = *(v124 - 1);
                v126 = v124--;
                v127 = v125 == 92;
                if ( v125 == 92 )
                  break;
                if ( v124 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                {
                  v127 = v125 == 92;
                  break;
                }
              }
              cbIVc = "_GenerateAesKey";
              LODWORD(pbIV) = 1218;
            }
            else
            {
              SupportedKeyLengths = BCryptEncrypt(pbOutput, pbInput, cbInput, 0, 0, 0, 0, 0, &pcbResult, 1u);
              if ( SupportedKeyLengths )
              {
                v124 = "";
                while ( 1 )
                {
                  v128 = *(v124 - 1);
                  v126 = v124--;
                  v127 = v128 == 92;
                  if ( v128 == 92 )
                    break;
                  if ( v124 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                  {
                    v127 = v128 == 92;
                    break;
                  }
                }
                cbIVc = "BCryptEncrypt";
                LODWORD(pbIV) = 1232;
              }
              else
              {
                hKey = AllocateMemory(pcbResult);
                if ( !hKey )
                {
                  SupportedKeyLengths = -1073741801;
                  v129 = "";
                  while ( 1 )
                  {
                    v130 = *(v129 - 1);
                    v131 = v129--;
                    v132 = v130 == 92;
                    if ( v130 == 92 )
                      break;
                    if ( v129 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                    {
                      v132 = v130 == 92;
                      break;
                    }
                  }
                  if ( v132 )
                    v129 = v131;
                  LODWORD(pbIV) = 1238;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v129, pbIV, "AllocateMemory", &Class);
LABEL_262:
                  if ( pbOutput )
                    BCryptDestroyKey(pbOutput);
                  v157 = hMem;
                  if ( hMem )
                  {
                    v158 = v243;
                    v159 = hMem;
                    if ( v243 )
                    {
                      do
                      {
                        *v159++ = 0;
                        --v158;
                      }
                      while ( v158 );
                    }
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(v157);
                  }
                  if ( Src )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(Src);
                  }
                  if ( hKey )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(hKey);
                  }
                  if ( *(_QWORD *)&v260.dwMinLength )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(*(HLOCAL *)&v260.dwMinLength);
                  }
                  if ( v259 )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(v259);
                  }
                  if ( v247 )
                  {
                    if ( g_pLsaFunctionTable )
                      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
                    else
                      LocalFree(v247);
                  }
                  if ( v256 )
                    LocalFree((HLOCAL)v256);
                  if ( SupportedKeyLengths )
                    goto LABEL_426;
                  LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold = NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold(
                                                                                   v264,
                                                                                   &v266);
                  if ( LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold )
                  {
                    v164 = (unsigned __int16)LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold;
                    v165 = "";
                    v170 = (unsigned __int16)LogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold | 0xC0070000;
                    if ( (_DWORD)v164 )
                      v164 = v170;
                    while ( 1 )
                    {
                      v171 = *(v165 - 1);
                      v168 = v165--;
                      v169 = v171 == 92;
                      if ( v171 == 92 )
                        break;
                      if ( v165 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
                      {
                        v169 = v171 == 92;
                        break;
                      }
                    }
                    cbIVd = "NgcGetLogonDecryptionKeyNameForFirstLogonAfterUpgradeFromThreshold";
                    LODWORD(pbIV) = 1816;
                  }
                  else
                  {
                    UserIdKeyPublicKey = NgcGetUserIdKeyPublicKey(v266, &v267, &v263);
                    if ( !UserIdKeyPublicKey )
                    {
                      v162 = RemoveCloudAPCacheNode(a1, 2u, (unsigned __int8 *)v267, v263);
                      SupportedKeyLengths = v162;
                      if ( v162 && v162 != -1073741275 )
                      {
                        while ( 1 )
                        {
                          v163 = *(v40 - 1);
                          v44 = v40--;
                          v45 = v163 == 92;
                          if ( v163 == 92 )
                            break;
                          if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
                          {
                            v45 = v163 == 92;
                            break;
                          }
                        }
                        cbIVa = "RemoveCloudAPCacheNode";
                        LODWORD(pbIV) = 1804;
                        goto LABEL_41;
                      }
LABEL_316:
                      v172 = v257[1];
                      v242 = 0;
                      SupportedKeyLengths = _ValidateSCardCacheData(v257[1], HIDWORD(v257[0]));
                      if ( SupportedKeyLengths )
                      {
                        do
                        {
                          v173 = *(v123 - 1);
                          v174 = v123--;
                        }
                        while ( v173 != 92
                             && v123 > "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" );
                        v36 = v173 == 92;
                        v175 = 1919;
                        if ( v36 )
                          v123 = v174;
                        v261 = "_ValidateSCardCacheData";
                      }
                      else
                      {
                        v176 = AllocateMemory(*((unsigned int *)v172 + 3));
                        v242 = v176;
                        if ( v176 )
                        {
                          memcpy_0(v176, &v172[*((unsigned int *)v172 + 2)], *((unsigned int *)v172 + 3));
                          v68 = *((_DWORD *)v172 + 3);
                          v180 = 0;
                          v181 = *((_DWORD *)a1 + 5);
                          v249 = v68;
                          if ( !v181 )
                          {
LABEL_342:
                            v61 = a3;
                            goto LABEL_343;
                          }
                          do
                          {
                            v182 = v181 - 1;
                            if ( *(_DWORD *)(*((_QWORD *)a1 + 3) + 32LL * (v181 - 1)) == 5 )
                            {
                              if ( (unsigned int)(v180 + 1) <= 1 )
                              {
                                ++v180;
                              }
                              else
                              {
                                ((void (*)(void))FreeCloudAPCacheNodeContents)();
                                for ( i = *((_DWORD *)a1 + 5); v181 < i; i = *((_DWORD *)a1 + 5) )
                                {
                                  v184 = *((_QWORD *)a1 + 3);
                                  v185 = 32LL * (v181 - 1);
                                  v186 = v181++;
                                  v186 *= 32;
                                  *(_OWORD *)(v185 + v184) = *(_OWORD *)(v186 + v184);
                                  *(_OWORD *)(v185 + v184 + 16) = *(_OWORD *)(v186 + v184 + 16);
                                }
                                *((_DWORD *)a1 + 5) = i - 1;
                              }
                            }
                            v181 = v182;
                          }
                          while ( v182 );
LABEL_341:
                          v68 = v249;
                          goto LABEL_342;
                        }
                        SupportedKeyLengths = -1073741801;
                        do
                        {
                          v177 = *(v123 - 1);
                          v178 = v123--;
                        }
                        while ( v177 != 92
                             && v123 > "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" );
                        v36 = v177 == 92;
                        v175 = 1934;
                        if ( v36 )
                          v123 = v178;
                      }
                      LODWORD(pbIV) = v175;
                      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v123, pbIV, v261, &Class);
                      while ( 1 )
                      {
                        v179 = *(v40 - 1);
                        v44 = v40--;
                        v45 = v179 == 92;
                        if ( v179 == 92 )
                          break;
                        if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
                        {
                          v45 = v179 == 92;
                          break;
                        }
                      }
                      cbIVa = "PKGetPublicKey";
                      LODWORD(pbIV) = 1825;
                      goto LABEL_41;
                    }
                    v164 = (unsigned __int16)UserIdKeyPublicKey;
                    v165 = "";
                    v166 = (unsigned __int16)UserIdKeyPublicKey | 0xC0070000;
                    if ( (_DWORD)v164 )
                      v164 = v166;
                    while ( 1 )
                    {
                      v167 = *(v165 - 1);
                      v168 = v165--;
                      v169 = v167 == 92;
                      if ( v167 == 92 )
                        break;
                      if ( v165 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
                      {
                        v169 = v167 == 92;
                        break;
                      }
                    }
                    cbIVd = "NgcGetUserIdKeyPublicKey";
                    LODWORD(pbIV) = 1810;
                  }
                  if ( v169 )
                    v165 = v168;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v164, v165, pbIV, cbIVd, &Class);
                  goto LABEL_316;
                }
                SupportedKeyLengths = BCryptEncrypt(
                                        pbOutput,
                                        pbInput,
                                        cbInput,
                                        0,
                                        0,
                                        0,
                                        (PUCHAR)hKey,
                                        pcbResult,
                                        &pcbResult,
                                        1u);
                if ( SupportedKeyLengths )
                {
                  v124 = "";
                  while ( 1 )
                  {
                    v133 = *(v124 - 1);
                    v126 = v124--;
                    v127 = v133 == 92;
                    if ( v133 == 92 )
                      break;
                    if ( v124 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                    {
                      v127 = v133 == 92;
                      break;
                    }
                  }
                  cbIVc = "BCryptEncrypt";
                  LODWORD(pbIV) = 1252;
                }
                else
                {
                  SupportedKeyLengths = _EncryptWithNgc(
                                          (struct _tagNGC_CONTEXTS_DATA *)&v273,
                                          (unsigned __int8 *)hMem,
                                          v243,
                                          (unsigned __int8 **)&v260,
                                          &v249,
                                          (unsigned __int8 **)&v256,
                                          SourceSize);
                  if ( SupportedKeyLengths )
                  {
                    v124 = "";
                    while ( 1 )
                    {
                      v135 = *(v124 - 1);
                      v126 = v124--;
                      v127 = v135 == 92;
                      if ( v135 == 92 )
                        break;
                      if ( v124 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                      {
                        v127 = v135 == 92;
                        break;
                      }
                    }
                    cbIVc = "_EncryptWithNgc";
                    LODWORD(pbIV) = 1279;
                  }
                  else
                  {
                    SupportedKeyLengths = EncryptBufferWithSecret(
                                            v134,
                                            (unsigned __int8 *)hMem,
                                            v243,
                                            v272,
                                            v122,
                                            (unsigned __int8 **)&v259,
                                            (unsigned int *)&Size + 1);
                    if ( SupportedKeyLengths )
                    {
                      v124 = "";
                      while ( 1 )
                      {
                        v136 = *(v124 - 1);
                        v126 = v124--;
                        v127 = v136 == 92;
                        if ( v136 == 92 )
                          break;
                        if ( v124 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                        {
                          v127 = v136 == 92;
                          break;
                        }
                      }
                      cbIVc = "EncryptBufferWithSecret";
                      LODWORD(pbIV) = 1293;
                    }
                    else
                    {
                      v137 = SourceSize[0];
                      v138 = v249 + SourceSize[0] + HIDWORD(Size) + Size + 40;
                      SourceSize[0] = v138;
                      v139 = AllocateMemory(v138);
                      v247 = v139;
                      if ( v139 )
                      {
                        v141 = (const void *)v256;
                        v139[1] = v138;
                        v142 = v139 + 10;
                        *v139 = 0;
                        v139[3] = v137;
                        v139[2] = 40;
                        memcpy_0(v139 + 10, v141, v137);
                        v143 = v247;
                        v144 = (char *)v142 + v137;
                        v145 = Src;
                        *((_DWORD *)v247 + 4) = (_DWORD)v144 - (_DWORD)v247;
                        v146 = Size;
                        v143[5] = Size;
                        v147 = v146;
                        memcpy_0(v144, v145, v146);
                        v148 = v247;
                        v149 = &v144[v147];
                        v150 = *(const void **)&v260.dwMinLength;
                        *((_DWORD *)v247 + 6) = (_DWORD)v149 - (_DWORD)v247;
                        v151 = v249;
                        v148[7] = v249;
                        v152 = v151;
                        memcpy_0(v149, v150, v151);
                        v153 = v259;
                        v154 = &v149[v152];
                        v155 = (unsigned __int8 *)v247;
                        *((_DWORD *)v247 + 8) = (_DWORD)v154 - (_DWORD)v247;
                        v156 = HIDWORD(Size);
                        *((_DWORD *)v155 + 9) = HIDWORD(Size);
                        memcpy_0(v154, v153, v156);
                        v258[1] = (unsigned __int8 *)hKey;
                        hKey = 0;
                        v257[1] = v155;
                        SupportedKeyLengths = 0;
                        LODWORD(v258[0]) = pcbResult;
                        HIDWORD(v257[0]) = SourceSize[0];
                        v247 = 0;
                        goto LABEL_262;
                      }
                      SupportedKeyLengths = -1073741801;
                      v124 = "";
                      while ( 1 )
                      {
                        v140 = *(v124 - 1);
                        v126 = v124--;
                        v127 = v140 == 92;
                        if ( v140 == 92 )
                          break;
                        if ( v124 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
                        {
                          v127 = v140 == 92;
                          break;
                        }
                      }
                      cbIVc = "AllocateMemory";
                      LODWORD(pbIV) = 1307;
                    }
                  }
                }
              }
            }
            if ( v127 )
              v124 = v126;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v124, pbIV, cbIVc, &Class);
            goto LABEL_262;
          }
        }
      }
      SupportedKeyLengths = -1073741811;
      v217 = "";
      while ( 1 )
      {
        v218 = *(v217 - 1);
        v219 = v217--;
        v220 = v218 == 92;
        if ( v218 == 92 )
          break;
        if ( v217 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
        {
          v220 = v218 == 92;
          break;
        }
      }
      LODWORD(pbIV) = 1205;
    }
    else
    {
      SupportedKeyLengths = -1073741811;
      v217 = "";
      while ( 1 )
      {
        v221 = *(v217 - 1);
        v219 = v217--;
        v220 = v221 == 92;
        if ( v221 == 92 )
          break;
        if ( v217 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
        {
          v220 = v221 == 92;
          break;
        }
      }
      LODWORD(pbIV) = 1191;
    }
    if ( v220 )
      v217 = v219;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v217, pbIV, "Null Arg(s)", &Class);
LABEL_426:
    while ( 1 )
    {
      v222 = *(v40 - 1);
      v44 = v40--;
      v45 = v222 == 92;
      if ( v222 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v45 = v222 == 92;
        break;
      }
    }
    cbIVa = "PKEncryptData";
    LODWORD(pbIV) = 1781;
    goto LABEL_41;
  }
  SupportedKeyLengths = FIDOValidateAuthData(v9, a5);
  if ( SupportedKeyLengths )
  {
    while ( 1 )
    {
      v43 = *(v40 - 1);
      v44 = v40--;
      v45 = v43 == 92;
      if ( v43 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v45 = v43 == 92;
        break;
      }
    }
    cbIVa = "ValidateFIDOAuthData";
    LODWORD(pbIV) = 1639;
    goto LABEL_41;
  }
  v42 = *((_DWORD *)v9 + 9);
  if ( !v42 )
  {
    SupportedKeyLengths = -1073741811;
    while ( 1 )
    {
      v47 = *(v40 - 1);
      v44 = v40--;
      v45 = v47 == 92;
      if ( v47 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v45 = v47 == 92;
        break;
      }
    }
    cbIVa = "InvalidArgs";
    LODWORD(pbIV) = 1649;
    goto LABEL_41;
  }
  v48 = *((unsigned int *)v9 + 8);
  Src = v9;
  v9 += v48;
LABEL_51:
  SupportedKeyLengths = GetSupportedKeyLengths(v38, &v260, 0);
  if ( SupportedKeyLengths )
  {
    while ( 1 )
    {
      v49 = *(v40 - 1);
      v44 = v40--;
      v45 = v49 == 92;
      if ( v49 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v45 = v49 == 92;
        break;
      }
    }
    cbIVa = "GetSupportedKeyLengths";
    LODWORD(pbIV) = 1662;
LABEL_41:
    if ( v45 )
      v40 = v44;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v40, pbIV, cbIVa, &Class);
    v14 = *(UCHAR **)&SourceSize[1];
    v46 = pbInput;
    goto LABEL_439;
  }
  v253 = v260.dwMaxLength >> 3;
  SupportedKeyLengths = DeriveKeyFromSecret((const unsigned __int16 *)&v265, v9, v42, v260.dwMaxLength >> 3, &v265);
  if ( SupportedKeyLengths )
  {
    while ( 1 )
    {
      v51 = *(v40 - 1);
      v44 = v40--;
      v45 = v51 == 92;
      if ( v51 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v45 = v51 == 92;
        break;
      }
    }
    cbIVa = "DeriveKeyFromSecret";
    LODWORD(pbIV) = 1673;
    goto LABEL_41;
  }
  v52 = v265;
  v46 = pbInput;
  SupportedKeyLengths = EncryptBufferWithKey(v50, pbInput, cbInput, v265, v253, &v258[1], (unsigned int *)v258);
  if ( SupportedKeyLengths )
  {
    while ( 1 )
    {
      v54 = *(v40 - 1);
      v55 = v40--;
      v56 = v54 == 92;
      if ( v54 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v56 = v54 == 92;
        break;
      }
    }
    if ( v56 )
      v40 = v55;
    LODWORD(pbIVa) = 1684;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v40, pbIVa, "EncryptBufferWithKey", &Class);
    v14 = *(UCHAR **)&SourceSize[1];
    goto LABEL_439;
  }
  SupportedKeyLengths = EncryptBufferWithSecret(
                          v53,
                          v52,
                          v253,
                          v39,
                          (unsigned int)v250,
                          (unsigned __int8 **)&v247,
                          &v243);
  if ( SupportedKeyLengths )
  {
    while ( 1 )
    {
      v57 = *(v40 - 1);
      v58 = v40--;
      v59 = v57 == 92;
      if ( v57 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v59 = v57 == 92;
        break;
      }
    }
    if ( v59 )
      v40 = v58;
    LODWORD(pbIVb) = 1695;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v40, pbIVb, "EncryptBufferWithSecret", &Class);
    v60 = v247;
    v14 = *(UCHAR **)&SourceSize[1];
    v46 = pbInput;
    goto LABEL_440;
  }
  v61 = a3;
  if ( a3 != 7 )
  {
    v68 = v249;
    v257[1] = (unsigned __int8 *)v247;
    HIDWORD(v257[0]) = v243;
    v244 = 0;
LABEL_343:
    v67 = v242;
    goto LABEL_344;
  }
  v244 = v247;
  SupportedKeyLengths = FIDOCreateCacheData(
                          (struct _FIDO_AUTH_DATA *)Src,
                          (unsigned __int8 *)v247,
                          v243,
                          &v257[1],
                          (unsigned int *)v257 + 1);
  if ( SupportedKeyLengths )
  {
    while ( 1 )
    {
      v62 = *(v40 - 1);
      v44 = v40--;
      v45 = v62 == 92;
      if ( v62 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v45 = v62 == 92;
        break;
      }
    }
    cbIVa = "FIDOCreateCacheData";
    LODWORD(pbIV) = 1705;
    goto LABEL_41;
  }
  SupportedKeyLengths = FIDOGetCredentialIDFromCacheData(
                          v257[1],
                          HIDWORD(v257[0]),
                          (unsigned __int8 **)&pbOutput,
                          (unsigned int *)&Size + 1);
  if ( SupportedKeyLengths )
  {
    while ( 1 )
    {
      v63 = *(v40 - 1);
      v64 = v40--;
      v65 = v63 == 92;
      if ( v63 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v65 = v63 == 92;
        break;
      }
    }
    if ( v65 )
      v40 = v64;
    LODWORD(pbIV) = 1712;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", SupportedKeyLengths, v40, pbIV, "FIDOGetCredentialIDFromCacheData", &Class);
    v66 = pbOutput;
    v14 = *(UCHAR **)&SourceSize[1];
    v46 = pbInput;
    v60 = v244;
    goto LABEL_441;
  }
  v67 = pbOutput;
  v68 = HIDWORD(Size);
  v242 = pbOutput;
LABEL_344:
  SupportedKeyLengths = GetCloudAPCacheNode(a1, v61, v67, v68, &v269);
  if ( (SupportedKeyLengths & 0x80000000) == 0 )
  {
    v187 = v269;
    FreeCloudAPCacheNodeContents(v269);
    goto LABEL_395;
  }
  if ( SupportedKeyLengths != -1073741275 )
  {
    while ( 1 )
    {
      v216 = *(v40 - 1);
      v44 = v40--;
      v45 = v216 == 92;
      if ( v216 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v45 = v216 == 92;
        break;
      }
    }
    cbIVa = "GetCloudAPCacheNode";
    LODWORD(pbIV) = 1961;
    goto LABEL_41;
  }
  v188 = *((_DWORD *)a1 + 5);
  if ( v188 >= 0x11 )
  {
    v189 = *((_QWORD *)a1 + 3);
    v190 = 18;
    v191 = 0;
    while ( 1 )
    {
      v192 = *(_DWORD *)(32LL * v191 + v189);
      if ( ((v192 - 1) & 0xFFFFFFFC) != 0 || v192 == 2 )
      {
        if ( v190 == 18 )
          v190 = v191;
        if ( v192 == v61 )
          break;
      }
      if ( ++v191 >= v188 )
        goto LABEL_357;
    }
    v190 = v191;
LABEL_357:
    if ( v190 > 0x11 )
    {
      SupportedKeyLengths = -1073741789;
      while ( 1 )
      {
        v193 = *(v40 - 1);
        v44 = v40--;
        v45 = v193 == 92;
        if ( v193 == 92 )
          break;
        if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v45 = v193 == 92;
          break;
        }
      }
      cbIVa = "The cache has no room for more nodes";
      LODWORD(pbIV) = 1899;
      goto LABEL_41;
    }
    FreeCloudAPCacheNodeContents(v189 + 32LL * v190);
    v194 = *((_DWORD *)a1 + 5);
    for ( j = v190 + 1; j < v194; v194 = *((_DWORD *)a1 + 5) )
    {
      v196 = *((_QWORD *)a1 + 3);
      v197 = 32LL * (j - 1);
      v198 = j++;
      v198 *= 32;
      *(_OWORD *)(v197 + v196) = *(_OWORD *)(v198 + v196);
      *(_OWORD *)(v197 + v196 + 16) = *(_OWORD *)(v198 + v196 + 16);
    }
    goto LABEL_386;
  }
  v199 = v188 + 1;
  v262 = v188 + 1;
  v200 = (UCHAR *)AllocateMemory(32 * (v188 + 1));
  v14 = v200;
  if ( !v200 )
  {
    SupportedKeyLengths = -1073741801;
    while ( 1 )
    {
      v201 = *(v40 - 1);
      v202 = v40--;
      v203 = v201 == 92;
      if ( v201 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v203 = v201 == 92;
        break;
      }
    }
    if ( v203 )
      v40 = v202;
    LODWORD(pbIV) = 1923;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v40, pbIV, "AllocateMemory", &Class);
LABEL_374:
    v46 = pbInput;
LABEL_439:
    v60 = v244;
LABEL_440:
    v66 = v242;
    goto LABEL_441;
  }
  if ( memcpy_s_0(v200, 32LL * v199, *((const void *const *)a1 + 3), 32LL * *((unsigned int *)a1 + 5)) )
  {
    SupportedKeyLengths = -1073741595;
    while ( 1 )
    {
      v204 = *(v40 - 1);
      v205 = v40--;
      v206 = v204 == 92;
      if ( v204 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v206 = v204 == 92;
        break;
      }
    }
    if ( v206 )
      v40 = v205;
    LODWORD(pbIV) = 1934;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v40, pbIV, "memcpy_s", &Class);
    goto LABEL_374;
  }
  v207 = (void *)*((_QWORD *)a1 + 3);
  if ( v207 )
    FreeMemory(v207);
  *((_QWORD *)a1 + 3) = v14;
  v194 = v199;
  *((_DWORD *)a1 + 5) = v199;
LABEL_386:
  if ( !v194 )
  {
    SupportedKeyLengths = -1073741595;
    while ( 1 )
    {
      v208 = *(v40 - 1);
      v209 = v40--;
      v210 = v208 == 92;
      if ( v208 == 92 )
        break;
      if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v210 = v208 == 92;
        break;
      }
    }
    if ( v210 )
      v40 = v209;
    LODWORD(pbIV) = 1952;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v40, pbIV, "cache nodes == 0", &Class);
    v46 = pbInput;
    v14 = 0;
    goto LABEL_439;
  }
  v187 = (_OWORD *)(*((_QWORD *)a1 + 3) + 32LL * (v194 - 1));
  SupportedKeyLengths = 0;
LABEL_395:
  if ( !a9 )
  {
    v66 = v242;
    goto LABEL_408;
  }
  *(_DWORD *)a9 = v61;
  v66 = v242;
  if ( !v242 || !v68 )
    goto LABEL_408;
  *((_DWORD *)a9 + 1) = v68;
  v211 = AllocateMemory(v68);
  *((_QWORD *)a9 + 1) = v211;
  if ( v211 )
  {
    memcpy_0(v211, v242, v68);
LABEL_408:
    v46 = pbInput;
    v215 = *(_OWORD *)v258;
    v60 = v244;
    *v187 = *(_OWORD *)v257;
    v187[1] = v215;
    v14 = 0;
    goto LABEL_441;
  }
  SupportedKeyLengths = -1073741801;
  while ( 1 )
  {
    v212 = *(v40 - 1);
    v213 = v40--;
    v214 = v212 == 92;
    if ( v212 == 92 )
      break;
    if ( v40 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
    {
      v214 = v212 == 92;
      break;
    }
  }
  if ( v214 )
    v40 = v213;
  LODWORD(pbIV) = 1978;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v40, pbIV, "AllocateMemory", &Class);
  v46 = pbInput;
  v14 = 0;
  v60 = v244;
LABEL_441:
  if ( v270 )
    LocalFree(v270);
  if ( v264 )
    LocalFree(v264);
  if ( (SupportedKeyLengths & 0x80000000) != 0 )
  {
    if ( v257[1] )
      FreeMemory(v257[1]);
    if ( v258[1] )
      FreeMemory(v258[1]);
  }
  v224 = v265;
  if ( v265 )
  {
    v225 = v253;
    v226 = v265;
    if ( v253 )
    {
      do
      {
        *v226++ = 0;
        --v225;
      }
      while ( v225 );
    }
    FreeMemory(v224);
  }
  if ( v46 )
  {
    v227 = cbInput;
    v228 = v46;
    if ( cbInput )
    {
      do
      {
        *v228++ = 0;
        --v227;
      }
      while ( v227 );
    }
    if ( g_pLsaFunctionTable )
      ((void (__fastcall *)(UCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v46);
    else
      LocalFree(v46);
  }
  if ( v14 )
  {
    v229 = v14;
    for ( k = 32LL * v262; k; --k )
      *v229++ = 0;
    FreeMemory(v14);
  }
  if ( v66 )
    FreeMemory(v66);
  if ( v266 )
    LocalFree(v266);
  if ( v267 )
    LocalFree(v267);
  if ( v60 )
    FreeMemory(v60);
  return SupportedKeyLengths;
}

```

## disassembly

```asm
0x180024bb0  mov     [rsp-8+arg_18], rbx
0x180024bb5  mov     [rsp-8+arg_10], r8d
0x180024bba  mov     [rsp-8+arg_8], edx
0x180024bbe  push    rbp
0x180024bbf  push    rsi
0x180024bc0  push    rdi
0x180024bc1  push    r12
0x180024bc3  push    r13
0x180024bc5  push    r14
0x180024bc7  push    r15
0x180024bc9  lea     rbp, [rsp-70h]
0x180024bce  sub     rsp, 170h
0x180024bd5  xor     r15d, r15d
0x180024bd8  xor     eax, eax
0x180024bda  mov     [rbp+0A0h+var_60], r15
0x180024bde  mov     edx, r15d
0x180024be1  mov     [rsp+1A0h+var_138], rdx
0x180024be6  xorps   xmm1, xmm1
0x180024be9  mov     [rbp+0A0h+var_120], rdx
0x180024bed  xorps   xmm0, xmm0
0x180024bf0  mov     qword ptr [rsp+1A0h+SourceSize+4], r15
0x180024bf5  mov     rsi, r9
0x180024bf8  mov     [rbp+0A0h+var_90], r15d
0x180024bfc  mov     r12d, r8d
0x180024bff  mov     [rbp+0A0h+var_A8], rax
0x180024c03  mov     r13, rcx
0x180024c06  mov     [rbp+0A0h+var_A0], eax
0x180024c09  mov     [rbp+0A0h+var_80], r15
0x180024c0d  mov     [rbp+0A0h+var_F0], r15d
0x180024c11  mov     [rsp+1A0h+pbInput], r15
0x180024c16  mov     [rbp+0A0h+cbInput], r15d
0x180024c1d  mov     [rsp+1A0h+var_148], rax
0x180024c22  mov     [rbp+0A0h+var_100], rax
0x180024c26  mov     [rbp+0A0h+var_110], eax
0x180024c29  mov     dword ptr [rbp+0A0h+Size+4], eax
0x180024c2c  mov     [rbp+0A0h+var_58], r15
0x180024c30  mov     [rbp+0A0h+var_88], r15
0x180024c34  mov     [rbp+0A0h+var_50], r15
0x180024c38  mov     [rbp+0A0h+var_68], r15
0x180024c3c  mov     [rbp+0A0h+var_78], r15
0x180024c40  mov     [rbp+0A0h+var_70], r15
0x180024c44  mov     [rbp+0A0h+var_8C], r15d
0x180024c48  mov     [rsp+1A0h+var_140], r15d
0x180024c4d  movups  [rbp+0A0h+var_40], xmm0
0x180024c51  movups  xmmword ptr [rbp+0A0h+var_D0], xmm1
0x180024c55  movups  xmmword ptr [rbp+0A0h+var_C0], xmm1
0x180024c59  test    rcx, rcx
0x180024c5c  jz      loc_180026953
0x180024c62  test    r9, r9
0x180024c65  jz      loc_180026953
0x180024c6b  mov     r14, [rbp+0A0h+Source]
0x180024c72  test    r14, r14
0x180024c75  jz      loc_180026953
0x180024c7b  mov     rbx, [rbp+0A0h+arg_30]
0x180024c82  test    rbx, rbx
0x180024c85  jz      loc_180026953
0x180024c8b  cmp     [rbx+8], rax
0x180024c8f  jz      loc_180026953
0x180024c95  mov     rax, [rbp+0A0h+arg_40]
0x180024c9c  test    rax, rax
0x180024c9f  jz      short loc_180024CA4
0x180024ca1  movups  xmmword ptr [rax], xmm0
0x180024ca4  cmp     dword ptr [r14], 20h ; ' '
0x180024ca8  jnb     short loc_180024CF7
0x180024caa  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180024cb1  mov     edi, 0C000000Dh
0x180024cb6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024cbb  mov     r9, rax
0x180024cbe  lea     rax, Class
0x180024cc5  mov     [rsp+1A0h+pbOutput], rax
0x180024cca  lea     rax, aInvalidargPcre_0; "InvalidArg:pCredKeyCurrent"
0x180024cd1  mov     qword ptr [rsp+1A0h+cbIV], rax
0x180024cd6  mov     dword ptr [rsp+1A0h+pbIV], 642h
0x180024cde  mov     r8d, edi
0x180024ce1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180024ce8  xor     ecx, ecx
0x180024cea  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180024cef  mov     rsi, r15
0x180024cf2  jmp     loc_1800269C2
0x180024cf7  mov     ecx, r12d
0x180024cfa  call    ValidateCredType
0x180024cff  mov     edi, eax
0x180024d01  test    eax, eax
0x180024d03  jz      short loc_180024D36
0x180024d05  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180024d0c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024d11  mov     r9, rax
0x180024d14  lea     rax, Class
0x180024d1b  mov     [rsp+1A0h+pbOutput], rax
0x180024d20  lea     rax, aValidatecredty; "ValidateCredType"
0x180024d27  mov     qword ptr [rsp+1A0h+cbIV], rax
0x180024d2c  mov     dword ptr [rsp+1A0h+pbIV], 646h
0x180024d34  jmp     short loc_180024CDE
0x180024d36  mov     eax, [r14+0Ch]
0x180024d3a  mov     ecx, [r14+8]
0x180024d3e  mov     edi, [r14]
0x180024d41  mov     dword ptr [rbp+0A0h+var_108], eax
0x180024d44  add     eax, ecx
0x180024d46  mov     dword ptr [rbp+0A0h+var_D0], r12d
0x180024d4a  mov     dword ptr [rbp+0A0h+Size], ecx
0x180024d4d  cmp     eax, edi
0x180024d4f  jbe     short loc_180024D8A
0x180024d51  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180024d58  mov     edi, 0C000000Dh
0x180024d5d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024d62  mov     r9, rax
0x180024d65  lea     rax, Class
0x180024d6c  mov     [rsp+1A0h+pbOutput], rax
0x180024d71  lea     rax, aInvalidargPcre_0; "InvalidArg:pCredKeyCurrent"
0x180024d78  mov     qword ptr [rsp+1A0h+cbIV], rax
0x180024d7d  mov     dword ptr [rsp+1A0h+pbIV], 64Fh
0x180024d85  jmp     loc_180024CDE
0x180024d8a  mov     eax, [rbx]
0x180024d8c  mov     rcx, [rbx+8]
0x180024d90  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180024d97  mov     [rsp+1A0h+pbInput], r15
0x180024d9c  mov     [rbp+0A0h+cbInput], r15d
0x180024da3  lea     r15d, [rax+rdi]
0x180024da7  mov     dword ptr [rsp+1A0h+SourceSize], eax
0x180024dab  lea     eax, [r15+10h]
0x180024daf  mov     ebx, eax
0x180024db1  mov     [rbp+0A0h+Src], rcx
0x180024db5  mov     dword ptr [rbp+0A0h+var_D8], r15d
0x180024db9  test    rdx, rdx
0x180024dbc  jz      short loc_180024DCB
0x180024dbe  mov     ecx, eax
0x180024dc0  mov     rax, [rdx+28h]
0x180024dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dc9  jmp     short loc_180024DD9
0x180024dcb  mov     rdx, rbx; uBytes
0x180024dce  mov     ecx, 40h ; '@'; uFlags
0x180024dd3  call    cs:__imp_LocalAlloc
0x180024dd9  mov     r12, rax
0x180024ddc  test    rax, rax
0x180024ddf  jnz     short loc_180024E2E
0x180024de1  lea     r15, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180024de8  mov     edi, 0C0000017h
0x180024ded  mov     rcx, r15; char *
0x180024df0  lea     r8, aAllocatememory; "AllocateMemory"
0x180024df7  lea     rsi, Class
0x180024dfe  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024e03  mov     [rsp+1A0h+pbOutput], rsi
0x180024e08  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180024e0f  mov     qword ptr [rsp+1A0h+cbIV], r8
0x180024e14  mov     r9, rax
0x180024e17  mov     r8d, edi
0x180024e1a  mov     dword ptr [rsp+1A0h+pbIV], 301h
0x180024e22  xor     ecx, ecx
0x180024e24  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180024e29  jmp     loc_180024F40
0x180024e2e  mov     ecx, [rbp+0A0h+arg_8]
0x180024e34  lea     rax, [r12+8]
0x180024e39  mov     [rax], ecx
0x180024e3b  mov     r9, rdi; SourceSize
0x180024e3e  mov     [rax+4], edi
0x180024e41  mov     r8, r14; Source
0x180024e44  add     rax, 8
0x180024e48  mov     edx, r15d; DestinationSize
0x180024e4b  mov     rcx, rax; Destination
0x180024e4e  mov     dword ptr [r12], 0
0x180024e56  mov     dword ptr [r12+4], 1
0x180024e5f  mov     [rbp+0A0h+var_98], rax
0x180024e63  call    memcpy_s_0
0x180024e68  lea     r15, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180024e6f  test    eax, eax
0x180024e71  jz      short loc_180024EA2
0x180024e73  mov     edi, 0C00000E5h
0x180024e78  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180024e7f  xor     r10d, r10d
0x180024e82  mov     rcx, r15; char *
0x180024e85  mov     r8d, edi
0x180024e88  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024e8d  lea     rdx, Class
0x180024e94  mov     ecx, 321h
0x180024e99  lea     r9, aMemcpyS; "memcpy_s"
0x180024ea0  jmp     short loc_180024EF6
0x180024ea2  mov     edx, dword ptr [rsp+1A0h+SourceSize]; DestinationSize
0x180024ea6  mov     rcx, [rbp+0A0h+var_98]
0x180024eaa  mov     r9d, edx; SourceSize
0x180024ead  mov     r8, [rbp+0A0h+Src]; Source
0x180024eb1  add     rcx, rdi; Destination
0x180024eb4  call    memcpy_s_0
0x180024eb9  test    eax, eax
0x180024ebb  jz      loc_180024F83
0x180024ec1  lea     rdx, Class
0x180024ec8  mov     edi, 0C00000E5h
0x180024ecd  xor     r10d, r10d
0x180024ed0  mov     [rbp+0A0h+var_98], rdx
0x180024ed4  mov     rcx, r15; char *
0x180024ed7  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180024ede  mov     r8d, edi
0x180024ee1  lea     r9, aMemcpyS; "memcpy_s"
0x180024ee8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024eed  mov     rdx, [rbp+0A0h+var_98]
0x180024ef1  mov     ecx, 32Fh
0x180024ef6  mov     [rsp+1A0h+pbOutput], rdx
0x180024efb  mov     rdx, r11
0x180024efe  mov     qword ptr [rsp+1A0h+cbIV], r9
0x180024f03  mov     r9, rax
0x180024f06  mov     dword ptr [rsp+1A0h+pbIV], ecx
0x180024f0a  mov     rcx, r10
0x180024f0d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180024f12  mov     rax, r12
0x180024f15  test    rbx, rbx
0x180024f18  jz      short loc_180024F2D
0x180024f1a  nop     word ptr [rax+rax+00h]
0x180024f20  mov     byte ptr [rax], 0
0x180024f23  lea     rax, [rax+1]
0x180024f27  sub     rbx, 1
0x180024f2b  jnz     short loc_180024F20
0x180024f2d  mov     rcx, r12; void *
0x180024f30  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x180024f35  test    edi, edi
0x180024f37  jz      short loc_180024F9B
0x180024f39  lea     rsi, Class
0x180024f40  lea     rbx, aOnecoreDsExtCl_2+3Dh; ""
0x180024f47  nop     word ptr [rax+rax+00000000h]
0x180024f50  movzx   eax, byte ptr [rbx-1]
0x180024f54  mov     rcx, rbx
0x180024f57  dec     rbx
0x180024f5a  cmp     al, 5Ch ; '\'
0x180024f5c  jz      short loc_180024F65
0x180024f5e  cmp     rbx, r15
0x180024f61  ja      short loc_180024F50
0x180024f63  cmp     al, 5Ch ; '\'
0x180024f65  mov     [rsp+1A0h+pbOutput], rsi
0x180024f6a  lea     rax, aCreatecachenod; "CreateCacheNodeDataBuffer"
0x180024f71  mov     qword ptr [rsp+1A0h+cbIV], rax
0x180024f76  mov     dword ptr [rsp+1A0h+pbIV], 65Dh
0x180024f7e  jmp     loc_1800269A5
0x180024f83  mov     eax, dword ptr [rbp+0A0h+var_D8]
0x180024f86  mov     rdi, r12
0x180024f89  add     eax, 10h
0x180024f8c  mov     [rsp+1A0h+pbInput], r12
0x180024f91  mov     ecx, eax
0x180024f93  mov     [rbp+0A0h+cbInput], eax
0x180024f99  jmp     short loc_180024FA2
0x180024f9b  mov     rdi, [rsp+1A0h+pbInput]
0x180024fa0  mov     ecx, edi
0x180024fa2  mov     r12d, dword ptr [rbp+0A0h+Size]
0x180024fa6  lea     rax, aAllocatememory; "AllocateMemory"
0x180024fad  add     r12, r14
0x180024fb0  mov     [rbp+0A0h+var_98], rax
0x180024fb4  mov     eax, [rbp+0A0h+arg_10]
0x180024fba  lea     rbx, aOnecoreDsExtCl_2+3Dh; ""
0x180024fc1  mov     [rbp+0A0h+var_48], r12
0x180024fc5  cmp     eax, 6
0x180024fc8  ja      short loc_180024FE8
0x180024fca  mov     edx, 4Ah ; 'J'
0x180024fcf  bt      edx, eax
0x180024fd2  jnb     short loc_180024FE8
0x180024fd4  mov     r14d, [rbp+0A0h+arg_20]
0x180024fdb  mov     [rbp+0A0h+Src], 0
0x180024fe3  jmp     loc_1800250C1
0x180024fe8  cmp     eax, 7
0x180024feb  jnz     loc_1800253E6
0x180024ff1  mov     edx, [rbp+0A0h+arg_20]; unsigned int
0x180024ff7  mov     rcx, rsi; unsigned __int8 *
0x180024ffa  call    ?FIDOValidateAuthData@@YAJPEAEK@Z; FIDOValidateAuthData(uchar *,ulong)
0x180024fff  mov     edi, eax
0x180025001  test    eax, eax
0x180025003  jz      short loc_18002506C
0x180025005  nop     word ptr [rax+rax+00000000h]
0x180025010  movzx   eax, byte ptr [rbx-1]
0x180025014  mov     rcx, rbx
0x180025017  dec     rbx
0x18002501a  cmp     al, 5Ch ; '\'
0x18002501c  jz      short loc_180025025
0x18002501e  cmp     rbx, r15
0x180025021  ja      short loc_180025010
0x180025023  cmp     al, 5Ch ; '\'
0x180025025  lea     rax, Class
0x18002502c  mov     [rsp+1A0h+pbOutput], rax
0x180025031  lea     rax, aValidatefidoau; "ValidateFIDOAuthData"
0x180025038  mov     qword ptr [rsp+1A0h+cbIV], rax
0x18002503d  mov     dword ptr [rsp+1A0h+pbIV], 667h
0x180025045  cmovz   rbx, rcx
0x180025049  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180025050  mov     r9, rbx
0x180025053  mov     r8d, edi
0x180025056  xor     ecx, ecx
0x180025058  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002505d  mov     rsi, qword ptr [rsp+1A0h+SourceSize+4]
0x180025062  mov     r14, [rsp+1A0h+pbInput]
0x180025067  jmp     loc_1800269C5
0x18002506c  mov     r14d, [rsi+24h]
0x180025070  test    r14d, r14d
0x180025073  jnz     short loc_1800250B7
0x180025075  mov     edi, 0C000000Dh
0x18002507a  nop     word ptr [rax+rax+00h]
0x180025080  movzx   eax, byte ptr [rbx-1]
0x180025084  mov     rcx, rbx
0x180025087  dec     rbx
0x18002508a  cmp     al, 5Ch ; '\'
0x18002508c  jz      short loc_180025095
0x18002508e  cmp     rbx, r15
0x180025091  ja      short loc_180025080
0x180025093  cmp     al, 5Ch ; '\'
0x180025095  lea     rax, Class
0x18002509c  mov     [rsp+1A0h+pbOutput], rax
  ... truncated ...
```
