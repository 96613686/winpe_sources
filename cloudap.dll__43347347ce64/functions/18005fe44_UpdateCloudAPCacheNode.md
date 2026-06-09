# UpdateCloudAPCacheNode

- ea: `0x18005fe44`
- end: `0x1800609f3`
- name: `UpdateCloudAPCacheNode`
- size: `2991`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, ULONG, __int64, __int64)`
- caller_count: `3`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x1800223a0`
- `0x180041504`
- `0x18005fc44`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180022f40`
- `0x180029098`
- `0x1800293c0`
- `0x180029464`
- `0x180033eb8`
- `0x180034430`
- `0x180035c54`
- `0x180035fa4`
- `0x18003c598`
- `0x18003cd70`
- `0x180043158`
- `0x18005fe44`
- `0x1800609fc`
- `0x180063980`
- `0x180064024`
- `0x180064104`
- `0x18007f9f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800609af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800609af`
- `cryptngc!NgcEncryptWithAsymmetricKey` at `0x1800600f4`
- `cryptngc!NgcEncryptWithAsymmetricKey` at `0x1800600f4`

## string_xrefs

- `0x18005febf`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005ff36`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005ff7d`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060007`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18006007d`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060101`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060155`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800601a9`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060221`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800602c9`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060333`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800603c8`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060416`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060499`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060501`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800605b4`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18006065f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800606b8`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18006073d`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18006078e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18006080c`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180060868`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800608db`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18006043d`: `FIDOGetCredHashFromCacheData`
- `0x180060098`: `CreateCacheNodeDataBuffer`
- `0x180060883`: `FIDOCreateCacheData`
- `0x1800607a9`: `FIDOGetCredentialIDFromCacheData`
- `0x1800602e4`: `UpdateTokenInCacheNodeData`
- `0x18006067a`: `UpdateTokenInCacheNodeData`
- `0x18006034e`: `UpdateCredKeyInCacheNodeData`
- `0x1800606d3`: `UpdateCredKeyInCacheNodeData`
- `0x180060248`: `PKGetCacheNode`
- `0x1800603e3`: `PKUpdateCacheNode`
- `0x18006002a`: `Old Style NGC node can only be updated in whole(bug in code)`

## pseudocode

```c
__int64 __fastcall UpdateCloudAPCacheNode(
        unsigned int *a1,
        unsigned int *a2,
        unsigned int *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        ULONG a8,
        _QWORD *a9,
        _DWORD *a10)
{
  _DWORD *v10; // rsi
  unsigned __int8 *v13; // r12
  unsigned __int8 *v14; // r13
  __int64 v15; // rdx
  unsigned int updated; // ebx
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  unsigned __int8 *v21; // r15
  const char *v22; // r9
  __int64 v23; // r8
  const unsigned __int16 *v24; // rcx
  unsigned int v25; // r11d
  unsigned __int8 *v26; // r10
  const char *v27; // r9
  const char *v28; // r9
  __int64 v29; // r9
  PUCHAR v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  unsigned int v34; // eax
  const char *v35; // r9
  SIZE_T v36; // rcx
  HLOCAL Memory; // rax
  const char *v38; // r9
  const char *v39; // r9
  void **v40; // r13
  const char *v41; // rax
  const char *v42; // r9
  const char *v43; // r9
  unsigned int v44; // r9d
  unsigned int v45; // edx
  unsigned __int8 *v46; // rcx
  const char *v47; // r9
  const unsigned __int16 *v48; // rcx
  const char *v49; // rax
  const unsigned __int16 *v50; // rcx
  const char *v51; // r9
  const char *v52; // r9
  unsigned __int8 *v53; // r14
  ULONG v54; // r13d
  const char *v55; // rax
  const char *v56; // r9
  const char *v57; // r9
  int v58; // ecx
  const unsigned __int16 *v59; // rcx
  const char *v60; // r9
  void **v61; // rsi
  const char *v62; // r9
  unsigned __int8 *v63; // rcx
  const unsigned __int16 *v64; // rcx
  const char *v65; // r9
  const char *v66; // r9
  ULONG v67; // r8d
  unsigned __int8 *v68; // rdx
  const unsigned __int16 *v69; // rcx
  const char *v70; // r9
  __int64 v71; // rcx
  unsigned __int8 *v72; // rax
  __int64 v73; // rax
  unsigned __int8 *v74; // rcx
  PUCHAR v75; // rax
  __int64 v76; // rcx
  void *v77; // rcx
  PUCHAR pbInput; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputa; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputb; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputc; // [rsp+28h] [rbp-99h]
  UCHAR *pbInputn; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputd; // [rsp+28h] [rbp-99h]
  PUCHAR pbInpute; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputf; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputg; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputh; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputi; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputj; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputk; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputl; // [rsp+28h] [rbp-99h]
  PUCHAR pbInputm; // [rsp+28h] [rbp-99h]
  ULONG cbInput; // [rsp+30h] [rbp-91h]
  unsigned int v95; // [rsp+68h] [rbp-59h] BYREF
  size_t Size; // [rsp+6Ch] [rbp-55h] BYREF
  PUCHAR v97; // [rsp+78h] [rbp-49h] BYREF
  unsigned int v98; // [rsp+80h] [rbp-41h]
  unsigned __int8 *v99; // [rsp+88h] [rbp-39h] BYREF
  rsize_t SourceSize; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int8 *v101; // [rsp+98h] [rbp-29h] BYREF
  unsigned int v102; // [rsp+A0h] [rbp-21h]
  unsigned int v103[3]; // [rsp+A4h] [rbp-1Dh] BYREF
  unsigned __int8 *Src; // [rsp+B0h] [rbp-11h] BYREF
  void *Source; // [rsp+B8h] [rbp-9h] BYREF
  unsigned __int8 *v106; // [rsp+C0h] [rbp-1h]

  v10 = a3;
  Size = 0;
  v101 = 0;
  v13 = 0;
  Source = 0;
  v14 = 0;
  LODWORD(SourceSize) = 0;
  v99 = 0;
  v95 = 0;
  v97 = 0;
  a8 = 0;
  Src = 0;
  memset(v103, 0, sizeof(v103));
  if ( a10 )
    *a10 = 0;
  v15 = *a2;
  if ( (unsigned int)v15 < 0x20 )
  {
    updated = -1073741811;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v17, 2393, "InvalidArg:pCredKeyCurrent", &Class);
    goto LABEL_91;
  }
  if ( a3 )
  {
    if ( *a3 < 0x20 )
    {
      updated = -1073741811;
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v23, v22, 2418, "InvalidArg:pCredKeyLatest", &Class);
      goto LABEL_91;
    }
    v21 = (unsigned __int8 *)a3 + a3[2];
    v98 = a3[3];
  }
  else
  {
    if ( !a6 && (!a9 || !a9[1] || !a9[2] || !a9[3]) )
    {
      updated = -1073741811;
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, 2409, "Null fn ptrs", &Class);
      goto LABEL_91;
    }
    v21 = 0;
    v98 = 0;
  }
  v24 = (const unsigned __int16 *)*a1;
  v25 = a2[3];
  v26 = (unsigned __int8 *)a2 + a2[2];
  v106 = v26;
  v102 = v25;
  if ( (((_DWORD)v24 - 1) & 0xFFFFFFFD) == 0 )
    goto LABEL_48;
  if ( (_DWORD)v24 == 7 )
  {
    updated = FIDOGetCredHashFromCacheData(*((unsigned __int8 **)a1 + 1), a1[1], &v101, (unsigned int *)&Size + 1);
    if ( updated )
    {
      v49 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v49, 2451, "FIDOGetCredHashFromCacheData", &Class);
LABEL_79:
      if ( v101 )
        FreeMemory(v101);
      if ( v14 )
        FreeMemory(v14);
      goto LABEL_83;
    }
    updated = DecryptBufferWithSecret(
                v48,
                v101,
                HIDWORD(Size),
                v106,
                v102,
                (unsigned __int8 **)&v103[1],
                (unsigned int *)&Size,
                0,
                0);
    if ( updated )
    {
      v51 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      LODWORD(pbInpute) = 2464;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v51, pbInpute, "DecryptBufferWithSecret", &Class);
LABEL_50:
      v53 = *(unsigned __int8 **)&v103[1];
      v54 = Size;
      goto LABEL_74;
    }
LABEL_51:
    v54 = Size;
    v53 = *(unsigned __int8 **)&v103[1];
    if ( (_DWORD)Size == g_cbNullPwdCredHash
      && !memcmp_0(*(const void **)&v103[1], g_pNullPwdCredHash, (unsigned int)Size)
      && a10 )
    {
      *a10 = 1;
    }
    updated = DecryptBufferWithKey(v50, *((unsigned __int8 **)a1 + 3), a1[4], v53, v54, &v99, &v95);
    if ( !updated )
    {
      v13 = v99;
      if ( v21 )
      {
        updated = UpdateCredKeyInCacheNodeData((_DWORD)v99, v95, (_DWORD)v10, *v10, (__int64)&v97, (__int64)&a8);
        if ( updated )
        {
          v57 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          LODWORD(pbInputi) = 2513;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v57, pbInputi, "UpdateCredKeyInCacheNodeData", &Class);
          goto LABEL_74;
        }
        if ( *a1 <= 6 && (v58 = 74, _bittest(&v58, *a1)) )
        {
          FreeMemory(*((void **)a1 + 1));
          *((_QWORD *)a1 + 1) = 0;
          updated = EncryptBufferWithSecret(v59, v53, v54, v21, v98, (unsigned __int8 **)a1 + 1, a1 + 1);
          if ( updated )
          {
            v60 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            LODWORD(pbInputj) = 2530;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v60, pbInputj, "EncryptBufferWithSecret", &Class);
            goto LABEL_74;
          }
        }
        else
        {
          v61 = (void **)(a1 + 2);
          updated = FIDOGetCredentialIDFromCacheData(*((unsigned __int8 **)a1 + 1), a1[1], &Src, v103);
          if ( updated )
          {
            v62 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            LODWORD(pbInputi) = 2540;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v62, pbInputi, "FIDOGetCredentialIDFromCacheData", &Class);
            goto LABEL_74;
          }
          FreeMemory(*v61);
          v63 = v101;
          *v61 = 0;
          FreeMemory(v63);
          v101 = 0;
          HIDWORD(Size) = 0;
          updated = EncryptBufferWithSecret(v64, v53, v54, v21, v98, &v101, (unsigned int *)&Size + 1);
          if ( updated )
          {
            v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            LODWORD(pbInputk) = 2558;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v65, pbInputk, "EncryptBufferWithSecret", &Class);
            goto LABEL_74;
          }
          updated = FIDOCreateCacheData(Src, v103[0], v101, HIDWORD(Size), (unsigned __int8 **)a1 + 1, a1 + 1);
          if ( updated )
          {
            v66 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            LODWORD(pbInputl) = 2567;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v66, pbInputl, "FIDOCreateCacheData", &Class);
            goto LABEL_74;
          }
        }
      }
      else
      {
        updated = UpdateTokenInCacheNodeData(a6, (_DWORD)a9, a4, a5, (__int64)v99, v95, (__int64)a2, *a2, a7);
        if ( updated )
        {
          v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          LODWORD(pbInputh) = 2502;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v56, pbInputh, "UpdateTokenInCacheNodeData", &Class);
          goto LABEL_74;
        }
      }
      FreeMemory(*((void **)a1 + 3));
      v67 = a8;
      v68 = v97;
      *((_QWORD *)a1 + 3) = 0;
      a1[4] = 0;
      updated = EncryptBufferWithKey(v69, v68, v67, v53, v54, (unsigned __int8 **)a1 + 3, a1 + 4);
      if ( updated )
      {
        v70 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
        LODWORD(pbInputm) = 2585;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v70, pbInputm, "EncryptBufferWithKey", &Class);
      }
      goto LABEL_74;
    }
    v55 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    LODWORD(pbInputg) = 2485;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v55, pbInputg, "DecryptBufferWithKey", &Class);
    v13 = v99;
LABEL_74:
    if ( v53 )
    {
      v71 = v54;
      v72 = v53;
      if ( v54 )
      {
        do
        {
          *v72++ = 0;
          --v71;
        }
        while ( v71 );
      }
      FreeMemory(v53);
    }
    v14 = Src;
    goto LABEL_79;
  }
  if ( (_DWORD)v24 == 6 )
  {
LABEL_48:
    updated = DecryptBufferWithSecret(
                v24,
                *((unsigned __int8 **)a1 + 1),
                a1[1],
                v26,
                v25,
                (unsigned __int8 **)&v103[1],
                (unsigned int *)&Size,
                0,
                0);
    if ( updated )
    {
      v52 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      LODWORD(pbInputf) = 2442;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v52, pbInputf, "DecryptBufferWithSecret", &Class);
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  if ( (unsigned int)((_DWORD)v24 - 4) > 1 )
  {
    if ( !a6 )
    {
      updated = -1073283013;
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        3221684283LL,
        v27,
        2656,
        "Old Style NGC node can only be updated in whole(bug in code)",
        &Class);
      goto LABEL_91;
    }
    if ( v21 )
      v15 = *a3;
    else
      v10 = a2;
    updated = CreateCacheNodeDataBuffer(v10, v15, a7 | 1u);
    if ( updated )
    {
      v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v28, 2668, "CreateCacheNodeDataBuffer", &Class);
    }
    else
    {
      FreeMemory(*((void **)a1 + 3));
      v29 = a8;
      v30 = v97;
      v31 = a1[1];
      v32 = *((_QWORD *)a1 + 1);
      *((_QWORD *)a1 + 3) = 0;
      a1[4] = 0;
      v33 = NgcEncryptWithAsymmetricKey(v32, v31, v30, v29, &Source, &SourceSize);
      if ( v33 >= 0 )
      {
        v36 = (unsigned int)SourceSize;
        a1[4] = SourceSize;
        Memory = AllocateMemory(v36);
        *((_QWORD *)a1 + 3) = Memory;
        if ( Memory )
        {
          if ( memcpy_s_0(Memory, a1[4], Source, (unsigned int)SourceSize) )
          {
            updated = -1073741595;
            v39 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            LODWORD(pbInput) = 2706;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v39, pbInput, "memcpy_s", &Class);
          }
        }
        else
        {
          updated = -1073741801;
          v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          LODWORD(pbInput) = 2696;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v38, pbInput, "AllocateMemory", &Class);
        }
      }
      else
      {
        updated = (unsigned __int16)v33;
        v34 = (unsigned __int16)v33 | 0xC0070000;
        if ( updated )
          updated = v34;
        v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
        LODWORD(pbInput) = 2686;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v35, pbInput, "NgcEncryptWithAsymmetricKey", &Class);
      }
    }
    goto LABEL_87;
  }
  v40 = (void **)(a1 + 6);
  updated = PKGetCacheNode(
              v26,
              v25,
              *((unsigned __int8 **)a1 + 1),
              a1[1],
              *((unsigned __int8 **)a1 + 3),
              a1[4],
              &v99,
              &v95);
  if ( updated )
  {
    v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    LODWORD(pbInputa) = 2599;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v41, pbInputa, "PKGetCacheNode", &Class);
    v13 = v99;
    goto LABEL_83;
  }
  v13 = v99;
  if ( !v21 )
  {
    updated = UpdateTokenInCacheNodeData(a6, (_DWORD)a9, a4, a5, (__int64)v99, v95, (__int64)a2, *a2, a7);
    if ( updated )
    {
      v42 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      LODWORD(pbInputb) = 2616;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v42, pbInputb, "UpdateTokenInCacheNodeData", &Class);
      goto LABEL_83;
    }
LABEL_42:
    FreeMemory(*v40);
    v44 = v98;
    v45 = v102;
    a1[4] = 0;
    v46 = v106;
    cbInput = a8;
    pbInputn = v97;
    *v40 = 0;
    updated = PKUpdateCacheNode(
                v46,
                v45,
                v21,
                v44,
                pbInputn,
                cbInput,
                (unsigned __int8 **)a1 + 3,
                a1 + 4,
                (unsigned __int8 **)a1 + 1,
                a1 + 1);
    if ( updated )
    {
      v47 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      LODWORD(pbInputd) = 2646;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v47, pbInputd, "PKUpdateCacheNode", &Class);
    }
    goto LABEL_83;
  }
  updated = UpdateCredKeyInCacheNodeData((_DWORD)v99, v95, (_DWORD)v10, *v10, (__int64)&v97, (__int64)&a8);
  if ( !updated )
    goto LABEL_42;
  v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
  LODWORD(pbInputc) = 2627;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v43, pbInputc, "UpdateCredKeyInCacheNodeData", &Class);
LABEL_83:
  if ( v13 )
  {
    v73 = v95;
    v74 = v13;
    if ( v95 )
    {
      do
      {
        *v74++ = 0;
        --v73;
      }
      while ( v73 );
    }
    FreeMemory(v13);
  }
LABEL_87:
  v75 = v97;
  if ( v97 )
  {
    v76 = a8;
    if ( a8 )
    {
      do
      {
        *v75++ = 0;
        --v76;
      }
      while ( v76 );
    }
    FreeMemory(v97);
  }
LABEL_91:
  LocalFree(Source);
  if ( (updated & 0x80000000) != 0 )
  {
    v77 = (void *)*((_QWORD *)a1 + 3);
    if ( v77 )
    {
      FreeMemory(v77);
      *((_QWORD *)a1 + 3) = 0;
      a1[4] = 0;
    }
  }
  return updated;
}

```

## disassembly

```asm
0x18005fe44  mov     rax, rsp
0x18005fe47  mov     [rax+8], rbx
0x18005fe4b  mov     [rax+20h], r9
0x18005fe4f  mov     [rax+10h], rdx
0x18005fe53  push    rbp
0x18005fe54  push    rsi
0x18005fe55  push    rdi
0x18005fe56  push    r12
0x18005fe58  push    r13
0x18005fe5a  push    r14
0x18005fe5c  push    r15
0x18005fe5e  lea     rbp, [rax-3Fh]
0x18005fe62  sub     rsp, 0C0h
0x18005fe69  mov     rax, [rbp+37h+arg_48]
0x18005fe70  xor     ebx, ebx
0x18005fe72  mov     qword ptr [rbp+37h+var_54+4], rbx
0x18005fe76  mov     rsi, r8
0x18005fe79  mov     dword ptr [rbp+37h+Size], ebx
0x18005fe7c  mov     r14, rdx
0x18005fe7f  mov     [rbp+37h+var_60], rbx
0x18005fe83  mov     rdi, rcx
0x18005fe86  mov     dword ptr [rbp+37h+Size+4], ebx
0x18005fe89  mov     r12d, ebx
0x18005fe8c  mov     [rbp+37h+Source], rbx
0x18005fe90  mov     r13d, ebx
0x18005fe93  mov     dword ptr [rbp+37h+SourceSize], ebx
0x18005fe96  mov     [rbp+37h+var_70], rbx
0x18005fe9a  mov     [rbp+37h+var_90], ebx
0x18005fe9d  mov     [rbp+37h+var_80], rbx
0x18005fea1  mov     [rbp+37h+arg_38], ebx
0x18005fea4  mov     [rbp+37h+Src], rbx
0x18005fea8  mov     dword ptr [rbp+37h+var_54], ebx
0x18005feab  test    rax, rax
0x18005feae  jz      short loc_18005FEB2
0x18005feb0  mov     [rax], ebx
0x18005feb2  mov     edx, [rdx]
0x18005feb4  cmp     edx, 20h ; ' '
0x18005feb7  jnb     short loc_18005FF04
0x18005feb9  mov     r8d, 0C000000Dh
0x18005febf  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005fec6  mov     ebx, r8d
0x18005fec9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005fece  mov     r9, rax
0x18005fed1  lea     rax, Class
0x18005fed8  mov     [rsp+0F0h+var_C0], rax
0x18005fedd  lea     rax, aInvalidargPcre_0; "InvalidArg:pCredKeyCurrent"
0x18005fee4  mov     qword ptr [rsp+0F0h+cbInput], rax
0x18005fee9  mov     dword ptr [rsp+0F0h+pbInput], 959h
0x18005fef1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005fef8  xor     ecx, ecx
0x18005fefa  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005feff  jmp     loc_1800609AB
0x18005ff04  mov     r8d, [rbp+37h+arg_28]
0x18005ff08  test    rsi, rsi
0x18005ff0b  jnz     short loc_18005FF72
0x18005ff0d  test    r8d, r8d
0x18005ff10  jnz     short loc_18005FF6A
0x18005ff12  mov     rax, [rbp+37h+arg_40]
0x18005ff19  test    rax, rax
0x18005ff1c  jz      short loc_18005FF30
0x18005ff1e  cmp     [rax+8], rbx
0x18005ff22  jz      short loc_18005FF30
0x18005ff24  cmp     [rax+10h], rbx
0x18005ff28  jz      short loc_18005FF30
0x18005ff2a  cmp     [rax+18h], rbx
0x18005ff2e  jnz     short loc_18005FF6A
0x18005ff30  mov     r8d, 0C000000Dh
0x18005ff36  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005ff3d  mov     ebx, r8d
0x18005ff40  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ff45  mov     r9, rax
0x18005ff48  lea     rax, Class
0x18005ff4f  mov     [rsp+0F0h+var_C0], rax
0x18005ff54  lea     rax, aNullFnPtrs; "Null fn ptrs"
0x18005ff5b  mov     qword ptr [rsp+0F0h+cbInput], rax
0x18005ff60  mov     dword ptr [rsp+0F0h+pbInput], 969h
0x18005ff68  jmp     short loc_18005FEF1
0x18005ff6a  mov     r15, rbx
0x18005ff6d  mov     [rbp+37h+var_78], ebx
0x18005ff70  jmp     short loc_18005FFC1
0x18005ff72  cmp     dword ptr [rsi], 20h ; ' '
0x18005ff75  jnb     short loc_18005FFB4
0x18005ff77  mov     r8d, 0C000000Dh
0x18005ff7d  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005ff84  mov     ebx, r8d
0x18005ff87  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ff8c  mov     r9, rax
0x18005ff8f  lea     rax, Class
0x18005ff96  mov     [rsp+0F0h+var_C0], rax
0x18005ff9b  lea     rax, aInvalidargPcre; "InvalidArg:pCredKeyLatest"
0x18005ffa2  mov     qword ptr [rsp+0F0h+cbInput], rax
0x18005ffa7  mov     dword ptr [rsp+0F0h+pbInput], 972h
0x18005ffaf  jmp     loc_18005FEF1
0x18005ffb4  mov     r15d, [rsi+8]
0x18005ffb8  mov     eax, [rsi+0Ch]
0x18005ffbb  add     r15, rsi
0x18005ffbe  mov     [rbp+37h+var_78], eax
0x18005ffc1  mov     ecx, [rcx]; unsigned __int16 *
0x18005ffc3  mov     r10d, [r14+8]
0x18005ffc7  mov     r11d, [r14+0Ch]
0x18005ffcb  add     r10, r14
0x18005ffce  mov     [rbp+37h+var_38], r10
0x18005ffd2  lea     eax, [rcx-1]
0x18005ffd5  mov     [rbp+37h+var_58], r11d
0x18005ffd9  test    eax, 0FFFFFFFDh
0x18005ffde  jz      loc_1800604CA
0x18005ffe4  cmp     ecx, 7
0x18005ffe7  jz      loc_1800603FC
0x18005ffed  cmp     ecx, 6
0x18005fff0  jz      loc_1800604CA
0x18005fff6  lea     eax, [rcx-4]
0x18005fff9  cmp     eax, 1
0x18005fffc  jbe     loc_1800601E2
0x180060002  test    r8d, r8d
0x180060005  jnz     short loc_180060043
0x180060007  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18006000e  mov     ebx, 0C007003Bh
0x180060013  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060018  mov     r9, rax
0x18006001b  mov     r8d, ebx
0x18006001e  lea     rax, Class
0x180060025  mov     [rsp+0F0h+var_C0], rax
0x18006002a  lea     rax, aOldStyleNgcNod; "Old Style NGC node can only be updated "...
0x180060031  mov     qword ptr [rsp+0F0h+cbInput], rax
0x180060036  mov     dword ptr [rsp+0F0h+pbInput], 0A60h
0x18006003e  jmp     loc_18005FEF1
0x180060043  mov     r8d, [rbp+37h+arg_30]
0x180060047  or      r8d, 1
0x18006004b  test    r15, r15
0x18006004e  jz      short loc_180060052
0x180060050  mov     edx, [rsi]
0x180060052  lea     rax, [rbp+37h+arg_38]
0x180060056  cmovz   rsi, r14
0x18006005a  mov     [rsp+0F0h+var_C0], rax
0x18006005f  mov     rcx, rsi
0x180060062  lea     rax, [rbp+37h+var_80]
0x180060066  mov     qword ptr [rsp+0F0h+cbInput], rax
0x18006006b  mov     eax, [rbp+37h+arg_20]
0x18006006e  mov     dword ptr [rsp+0F0h+pbInput], eax
0x180060072  call    CreateCacheNodeDataBuffer
0x180060077  mov     ebx, eax
0x180060079  test    eax, eax
0x18006007b  jz      short loc_1800600C2
0x18006007d  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060084  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060089  mov     r9, rax
0x18006008c  lea     rax, Class
0x180060093  mov     [rsp+0F0h+var_C0], rax
0x180060098  lea     rax, aCreatecachenod; "CreateCacheNodeDataBuffer"
0x18006009f  mov     qword ptr [rsp+0F0h+cbInput], rax
0x1800600a4  mov     dword ptr [rsp+0F0h+pbInput], 0A6Ch
0x1800600ac  mov     r8d, ebx
0x1800600af  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800600b6  xor     ecx, ecx
0x1800600b8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800600bd  jmp     loc_180060985
0x1800600c2  mov     rcx, [rdi+18h]; void *
0x1800600c6  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x1800600cb  mov     r9d, [rbp+37h+arg_38]
0x1800600cf  lea     rax, [rbp+37h+SourceSize]
0x1800600d3  mov     r8, [rbp+37h+var_80]
0x1800600d7  mov     edx, [rdi+4]
0x1800600da  mov     rcx, [rdi+8]
0x1800600de  mov     qword ptr [rsp+0F0h+cbInput], rax
0x1800600e3  lea     rax, [rbp+37h+Source]
0x1800600e7  mov     [rsp+0F0h+pbInput], rax
0x1800600ec  mov     [rdi+18h], r12
0x1800600f0  mov     [rdi+10h], r12d
0x1800600f4  call    cs:__imp_NgcEncryptWithAsymmetricKey
0x1800600fa  test    eax, eax
0x1800600fc  jns     short loc_180060141
0x1800600fe  movzx   ebx, ax
0x180060101  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060108  mov     eax, ebx
0x18006010a  or      eax, 0C0070000h
0x18006010f  test    ebx, ebx
0x180060111  cmovnz  ebx, eax
0x180060114  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060119  mov     r9, rax
0x18006011c  lea     rax, Class
0x180060123  mov     [rsp+0F0h+var_C0], rax
0x180060128  lea     rax, aNgcencryptwith_0; "NgcEncryptWithAsymmetricKey"
0x18006012f  mov     qword ptr [rsp+0F0h+cbInput], rax
0x180060134  mov     dword ptr [rsp+0F0h+pbInput], 0A7Eh
0x18006013c  jmp     loc_1800600AC
0x180060141  mov     ecx, dword ptr [rbp+37h+SourceSize]; uBytes
0x180060144  mov     [rdi+10h], ecx
0x180060147  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x18006014c  mov     [rdi+18h], rax
0x180060150  test    rax, rax
0x180060153  jnz     short loc_18006018E
0x180060155  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18006015c  mov     ebx, 0C0000017h
0x180060161  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060166  mov     r9, rax
0x180060169  lea     rax, Class
0x180060170  mov     [rsp+0F0h+var_C0], rax
0x180060175  lea     rax, aAllocatememory; "AllocateMemory"
0x18006017c  mov     qword ptr [rsp+0F0h+cbInput], rax
0x180060181  mov     dword ptr [rsp+0F0h+pbInput], 0A88h
0x180060189  jmp     loc_1800600AC
0x18006018e  mov     r9d, dword ptr [rbp+37h+SourceSize]; SourceSize
0x180060192  mov     rcx, rax; Destination
0x180060195  mov     edx, [rdi+10h]; DestinationSize
0x180060198  mov     r8, [rbp+37h+Source]; Source
0x18006019c  call    memcpy_s_0
0x1800601a1  test    eax, eax
0x1800601a3  jz      loc_180060985
0x1800601a9  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800601b0  mov     ebx, 0C00000E5h
0x1800601b5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800601ba  mov     r9, rax
0x1800601bd  lea     rax, Class
0x1800601c4  mov     [rsp+0F0h+var_C0], rax
0x1800601c9  lea     rax, aMemcpyS; "memcpy_s"
0x1800601d0  mov     qword ptr [rsp+0F0h+cbInput], rax
0x1800601d5  mov     dword ptr [rsp+0F0h+pbInput], 0A92h
0x1800601dd  jmp     loc_1800600AC
0x1800601e2  mov     r9d, [rdi+4]; unsigned int
0x1800601e6  lea     rax, [rbp+37h+var_90]
0x1800601ea  mov     r8, [rdi+8]; unsigned __int8 *
0x1800601ee  lea     r13, [rdi+18h]
0x1800601f2  mov     [rsp+0F0h+var_B8], rax; unsigned int *
0x1800601f7  mov     edx, r11d; unsigned int
0x1800601fa  lea     rax, [rbp+37h+var_70]
0x1800601fe  mov     rcx, r10; unsigned __int8 *
0x180060201  mov     [rsp+0F0h+var_C0], rax; unsigned __int8 **
0x180060206  mov     eax, [rdi+10h]
0x180060209  mov     [rsp+0F0h+cbInput], eax; unsigned int
0x18006020d  mov     rax, [r13+0]
0x180060211  mov     [rsp+0F0h+pbInput], rax; unsigned __int8 *
0x180060216  call    ?PKGetCacheNode@@YAJPEAEK0K0KPEAPEAEPEAK@Z; PKGetCacheNode(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18006021b  mov     ebx, eax
0x18006021d  test    eax, eax
0x18006021f  jz      short loc_18006026A
0x180060221  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060228  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006022d  mov     r9, rax
0x180060230  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180060237  lea     rax, Class
0x18006023e  mov     r8d, ebx
0x180060241  mov     [rsp+0F0h+var_C0], rax
0x180060246  xor     ecx, ecx
0x180060248  lea     rax, aPkgetcachenode; "PKGetCacheNode"
0x18006024f  mov     qword ptr [rsp+0F0h+cbInput], rax
0x180060254  mov     dword ptr [rsp+0F0h+pbInput], 0A27h
0x18006025c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180060261  mov     r12, [rbp+37h+var_70]
0x180060265  jmp     loc_180060961
0x18006026a  mov     r12, [rbp+37h+var_70]
0x18006026e  lea     rax, [rbp+37h+arg_38]
0x180060272  test    r15, r15
0x180060275  jnz     loc_18006030E
0x18006027b  mov     r9d, [rbp+37h+arg_20]
0x18006027f  mov     r8, [rbp+37h+arg_18]
0x180060283  mov     rdx, [rbp+37h+arg_40]
0x18006028a  mov     ecx, [rbp+37h+arg_28]
0x18006028d  mov     [rsp+58h], rax
0x180060292  lea     rax, [rbp+37h+var_80]
0x180060296  mov     [rsp+0F0h+var_A0], rax
0x18006029b  mov     eax, [rbp+37h+arg_30]
0x18006029e  mov     dword ptr [rsp+0F0h+var_B0], eax
0x1800602a2  mov     eax, [r14]
0x1800602a5  mov     dword ptr [rsp+0F0h+var_B8], eax
0x1800602a9  mov     eax, [rbp+37h+var_90]
0x1800602ac  mov     [rsp+0F0h+var_C0], r14
0x1800602b1  mov     [rsp+0F0h+cbInput], eax
0x1800602b5  mov     [rsp+0F0h+pbInput], r12
0x1800602ba  call    UpdateTokenInCacheNodeData
0x1800602bf  mov     ebx, eax
0x1800602c1  test    eax, eax
0x1800602c3  jz      loc_180060364
0x1800602c9  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800602d0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800602d5  mov     r9, rax
0x1800602d8  lea     rax, Class
0x1800602df  mov     [rsp+0F0h+var_C0], rax
0x1800602e4  lea     rax, aUpdatetokeninc; "UpdateTokenInCacheNodeData"
0x1800602eb  mov     qword ptr [rsp+0F0h+cbInput], rax
0x1800602f0  mov     dword ptr [rsp+0F0h+pbInput], 0A38h
0x1800602f8  mov     r8d, ebx
0x1800602fb  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180060302  xor     ecx, ecx
0x180060304  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180060309  jmp     loc_180060961
0x18006030e  mov     r9d, [rsi]
0x180060311  mov     r8, rsi
0x180060314  mov     edx, [rbp+37h+var_90]
0x180060317  mov     rcx, r12
0x18006031a  mov     qword ptr [rsp+0F0h+cbInput], rax
0x18006031f  lea     rax, [rbp+37h+var_80]
0x180060323  mov     [rsp+0F0h+pbInput], rax
0x180060328  call    UpdateCredKeyInCacheNodeData
0x18006032d  mov     ebx, eax
0x18006032f  test    eax, eax
0x180060331  jz      short loc_180060364
0x180060333  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18006033a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006033f  mov     r9, rax
0x180060342  lea     rax, Class
  ... truncated ...
```
