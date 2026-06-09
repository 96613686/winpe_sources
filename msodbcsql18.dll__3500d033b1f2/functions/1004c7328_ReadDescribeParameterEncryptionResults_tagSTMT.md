# ReadDescribeParameterEncryptionResults(tagSTMT *)

- ea: `0x1004c7328`
- end: `0x1004c8658`
- name: `?ReadDescribeParameterEncryptionResults@@YAFPEAUtagSTMT@@@Z`
- size: `4912`
- prototype: `__int16 __fastcall(struct tagSTMT *)`
- caller_count: `1`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x1004c0040`

## callees

- `0x100430824`
- `0x10044b410`
- `0x10044b854`
- `0x10044b8d8`
- `0x10044c238`
- `0x10047cc4c`
- `0x10047eae0`
- `0x10047ee64`
- `0x1004b89c8`
- `0x1004bb758`
- `0x1004c7328`
- `0x1004ca97c`
- `0x1004ce468`
- `0x1004ce6ac`
- `0x1004fa5c0`
- `0x100501e1c`
- `0x100506bc0`
- `0x10050d8e4`
- `0x10050e2a0`
- `0x10051ffac`
- `0x1005212b4`
- `0x1005257d4`
- `0x100525908`
- `0x1005304d4`
- `0x100532acc`
- `0x100535e58`
- `0x100536194`
- `0x100546a7c`
- `0x100548140`
- `0x100548210`
- `0x100548310`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1004c825f`
- `KERNEL32!LocalFree` at `0x1004c84c8`
- `KERNEL32!LocalFree` at `0x1004c825f`
- `KERNEL32!LocalFree` at `0x1004c84c8`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7a40`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7a65`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7a8a`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7af1`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7a40`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7a65`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7a8a`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004c7af1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004c862f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1004c862f`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004c7e34`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004c7e34`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ReadDescribeParameterEncryptionResults(struct tagSTMT *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // r12d
  __int64 v5; // r13
  unsigned __int16 v6; // si
  __int64 v7; // rdx
  __int64 v8; // rdx
  struct tagSTMT *v9; // rdx
  struct tagSTMT *v10; // rdx
  __int64 v11; // rdi
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rax
  _BYTE *v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rsi
  unsigned __int16 *v18; // rbx
  rsize_t v19; // r9
  __int64 v20; // rax
  __int64 v21; // rdx
  struct tagSTMT *v22; // rdx
  __int16 *v23; // r8
  struct tagSTMT *v24; // rdx
  struct tagSTMT *v25; // rdx
  struct tagSTMT *v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 *v30; // rax
  __int64 *v31; // rdx
  _DWORD *v32; // rax
  _DWORD *v33; // rbx
  __int64 v34; // r8
  __int64 v35; // r9
  volatile signed __int32 *v36; // rbx
  volatile signed __int32 *v37; // rbx
  __int16 *v38; // r8
  struct tagSTMT *v39; // rdx
  unsigned __int16 v40; // r8
  __int64 v41; // rdx
  struct tagSTMT *v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r13
  __int64 v45; // rbx
  _BYTE *v46; // rdx
  __int64 v47; // r8
  __int64 *v48; // rdi
  __int64 *v49; // rbx
  __int64 v50; // rax
  _QWORD *v51; // r12
  __int64 v52; // rdx
  __int64 v53; // r8
  int v54; // eax
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // r8
  __int64 v57; // r8
  __int64 v58; // rdx
  HLOCAL v59; // rcx
  _BYTE *v60; // r9
  __int64 v61; // r10
  __int64 **v62; // rax
  __int64 *k; // rcx
  __int64 *j; // rax
  __int16 v65; // bx
  __int16 v66; // ax
  int v68; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+20h] [rbp-E0h]
  int *v70; // [rsp+28h] [rbp-D8h]
  __int64 *v71; // [rsp+30h] [rbp-D0h]
  __int64 *v72; // [rsp+30h] [rbp-D0h]
  __int64 *v73; // [rsp+30h] [rbp-D0h]
  __int64 *v74; // [rsp+30h] [rbp-D0h]
  __int64 *v75; // [rsp+30h] [rbp-D0h]
  __int64 *v76; // [rsp+30h] [rbp-D0h]
  __int64 *v77; // [rsp+30h] [rbp-D0h]
  __int64 *v78; // [rsp+30h] [rbp-D0h]
  __int64 *v79; // [rsp+30h] [rbp-D0h]
  __int64 *v80; // [rsp+30h] [rbp-D0h]
  __int64 *v81; // [rsp+30h] [rbp-D0h]
  __int64 *v82; // [rsp+30h] [rbp-D0h]
  __int64 *v83; // [rsp+30h] [rbp-D0h]
  __int64 *v84; // [rsp+30h] [rbp-D0h]
  __int64 *v85; // [rsp+30h] [rbp-D0h]
  __int64 *v86; // [rsp+30h] [rbp-D0h]
  __int64 *v87; // [rsp+30h] [rbp-D0h]
  __int16 v88; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v89[2]; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v90[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v91; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v92; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v93[2]; // [rsp+68h] [rbp-98h] BYREF
  __int16 v94[2]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v95[2]; // [rsp+74h] [rbp-8Ch] BYREF
  __int16 v96[2]; // [rsp+78h] [rbp-88h] BYREF
  rsize_t v97; // [rsp+80h] [rbp-80h] BYREF
  __int16 v98[2]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v99[2]; // [rsp+8Ch] [rbp-74h] BYREF
  __int16 v100[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v101[2]; // [rsp+94h] [rbp-6Ch] BYREF
  _DWORD *v102; // [rsp+98h] [rbp-68h] BYREF
  int v103[2]; // [rsp+A0h] [rbp-60h] BYREF
  volatile signed __int32 *v104; // [rsp+A8h] [rbp-58h]
  _QWORD *i; // [rsp+B0h] [rbp-50h]
  __int128 v106; // [rsp+B8h] [rbp-48h] BYREF
  rsize_t v107; // [rsp+C8h] [rbp-38h] BYREF
  struct ADTag *v108; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v109[4]; // [rsp+D8h] [rbp-28h] BYREF
  rsize_t SourceSize; // [rsp+E0h] [rbp-20h] BYREF
  rsize_t v111; // [rsp+E8h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v113[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v114; // [rsp+108h] [rbp+8h] BYREF
  __int64 v115; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v116[3]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v117[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v118[4]; // [rsp+140h] [rbp+40h] BYREF
  int v119[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v120; // [rsp+170h] [rbp+70h]
  unsigned __int64 v121; // [rsp+178h] [rbp+78h]
  _BYTE Source[272]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v123[136]; // [rsp+290h] [rbp+190h] BYREF
  __int16 v124[136]; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int16 v125[2]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wchar_t String[134]; // [rsp+4B4h] [rbp+3B4h] BYREF
  __int16 v127[4000]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int8 v128[8000]; // [rsp+2500h] [rbp+2400h] BYREF

  v118[3] = -2;
  memset_0(v127, 0, sizeof(v127));
  memset_0(v123, 0, 0x102u);
  memset_0(Source, 0, 0x102u);
  memset_0(v124, 0, 0x102u);
  *(_DWORD *)v90 = 0;
  *(_DWORD *)v98 = 0;
  *(_DWORD *)v94 = 0;
  *(_DWORD *)v95 = 0;
  *(_QWORD *)v109 = 0;
  LOBYTE(v88) = 0;
  v97 = 0;
  v114 = 0;
  v111 = 0;
  SourceSize = 0;
  v107 = 0;
  v115 = 0;
  v92 = 0;
  v89[0] = 0;
  *(_DWORD *)v99 = 0;
  memset_0(v125, 0, 0x102u);
  *(_DWORD *)v100 = 0;
  *(_DWORD *)v96 = 0;
  *(_DWORD *)v101 = 0;
  v2 = *((_QWORD *)a1 + 14);
  v118[0] = *(_QWORD *)(v2 + 88);
  v118[1] = v2;
  v118[2] = a1;
  v3 = *(_QWORD *)(v2 + 2512);
  v116[0] = v118;
  v116[1] = v3;
  v116[2] = HandleAEexception;
  v4 = 0;
  tagSTMT::CleanupCryptoMetaDataSet(a1);
  if ( !*((_QWORD *)a1 + 540) )
    *((_QWORD *)a1 + 540) = PlAllocEx(a1, 0x10u, 0x10u, 8u, 1);
  v106 = 0;
  *(_QWORD *)&v106 = std::_Tree_comp_alloc<std::_Tmap_traits<unsigned long,std::shared_ptr<sqlencrypt::CipherInfoEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<sqlencrypt::CipherInfoEntry>>>,0>>::_Buyheadnode(&v106);
  v5 = 0;
  v108 = 0;
  *(_QWORD *)v113 = 0;
  v6 = AllocDesc(*((struct tagDBC **)a1 + 14), (void **)&v108);
  if ( v6 == 0xFFFF )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_202;
    v7 = 2384905;
    goto LABEL_201;
  }
  v6 = ExportImp::SQLGetStmtAttrW(a1, (struct tagSTMT *)0x271A, (int)v113, 0, 0, v70);
  if ( v6 == 0xFFFF )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_202;
    v7 = 2386953;
    goto LABEL_201;
  }
  v6 = ExportImp::SQLSetStmtAttrW(a1, (struct tagSTMT *)0x271A, (int)v108, 0, v68);
  if ( v6 == 0xFFFF )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_202;
    v7 = 2389001;
    goto LABEL_201;
  }
  if ( *((_DWORD *)a1 + 520) != 1 || !*((_WORD *)a1 + 135) )
    goto LABEL_198;
  v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)1, 4u, (__int16)v90, 0, (__int64)&v92, v71);
  if ( v6 != 0xFFFF )
  {
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)2, 4u, (__int16)v98, 0, (__int64)&v92, v72);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2403337;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)3, 4u, (__int16)v94, 0, (__int64)&v92, v73);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2405385;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)4, 4u, (__int16)v95, 0, (__int64)&v92, v74);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2407433;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)5, 0xFFFEu, (__int16)v109, (void *)8, (__int64)&v114, v75);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2409481;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)6, 0xFFFEu, (__int16)v127, (void *)0x1F40, (__int64)&v97, v76);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2411529;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)7, 0xFFF8u, (__int16)v123, (void *)0x102, (__int64)&v111, v77);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2413577;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(
           a1,
           (struct tagSTMT *)8,
           0xFFF8u,
           (__int16)Source,
           (void *)0x102,
           (__int64)&SourceSize,
           v78);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2415625;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)9, 0xFFF8u, (__int16)v124, (void *)0x102, (__int64)&v107, v79);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2417673;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)0xA, 0xFFFEu, (__int16)&v88, (void *)1, (__int64)&v115, v80);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2419721;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLFetch(a1, v9);
    if ( v6 != 100 )
    {
      while ( (v6 & 0xFFFE) == 0 )
      {
        v91 = *(_DWORD *)v90;
        std::map<unsigned long,std::shared_ptr<sqlencrypt::CipherInfoEntry>>::_Try_emplace<unsigned long,>(
          &v106,
          v117,
          &v91);
        v11 = v117[0];
        v12 = *(_QWORD **)(v117[0] + 40LL);
        if ( v12 )
        {
          v5 = (__int64)(v12[1] - *v12) >> 3;
          std::vector<std::unique_ptr<sqlencrypt::EncryptionKeyInfo>>::_Resize<_lambda_51ef61388fe13ff4c6cc1ab1a913964e_>(
            v12,
            v5 + 1,
            *(_QWORD *)(v117[0] + 40LL));
        }
        else
        {
          v13 = (_QWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 48);
          i = v13;
          if ( v13 )
          {
            *v13 = 0;
            v13[1] = 0;
            v13[2] = 0;
            v13[3] = 0;
            v13[4] = 0;
            v13[5] = 0;
          }
          else
          {
            v13 = 0;
          }
          std::shared_ptr<sqlencrypt::CipherInfoEntry>::reset<sqlencrypt::CipherInfoEntry>(v11 + 40, v13);
          std::vector<std::unique_ptr<sqlencrypt::EncryptionKeyInfo>>::_Resize<_lambda_51ef61388fe13ff4c6cc1ab1a913964e_>(
            *(_QWORD *)(v11 + 40),
            1,
            *(_QWORD *)(v11 + 40));
          *(_DWORD *)(*(_QWORD *)(v11 + 40) + 24LL) = *(_DWORD *)v90;
          *(_DWORD *)(*(_QWORD *)(v11 + 40) + 32LL) = *(_DWORD *)v94;
          *(_DWORD *)(*(_QWORD *)(v11 + 40) + 36LL) = *(_DWORD *)v95;
          *(_QWORD *)(*(_QWORD *)(v11 + 40) + 40LL) = *(_QWORD *)v109;
        }
        v14 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 824);
        v15 = (_BYTE *)v14;
        i = (_QWORD *)v14;
        if ( v14 )
        {
          *(_WORD *)v14 = 0;
          *(_QWORD *)(v14 + 8) = 0;
          *(_QWORD *)(v14 + 16) = 0;
          *(_DWORD *)(v14 + 24) = 0;
          *(_QWORD *)(v14 + 32) = 0;
          *(_WORD *)(v14 + 44) = 0;
          memset_0((void *)(v14 + 46), 0, 0x102u);
          v15[304] = 0;
          memset_0(v15 + 306, 0, 0x102u);
          v15[564] = 0;
          memset_0(v15 + 566, 0, 0x102u);
        }
        else
        {
          v15 = 0;
        }
        v16 = *(_QWORD **)(v11 + 40);
        v17 = *(_QWORD *)(*v16 + 8 * v5);
        *(_QWORD *)(*v16 + 8 * v5) = v15;
        if ( v17 )
        {
          if ( *(_QWORD *)(v17 + 8) )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
          ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v17);
        }
        v18 = *(unsigned __int16 **)(**(_QWORD **)(v11 + 40) + 8 * v5);
        *((_DWORD *)v18 + 4) = *(_DWORD *)v98;
        *((_DWORD *)v18 + 5) = *(_DWORD *)v94;
        *((_DWORD *)v18 + 6) = *(_DWORD *)v95;
        *((_QWORD *)v18 + 4) = *(_QWORD *)v109;
        v18[22] = SourceSize;
        memcpy_s(v18 + 23, (unsigned __int16)SourceSize, Source, SourceSize);
        *((_BYTE *)v18 + 304) = v111;
        memcpy_s(v18 + 153, (unsigned __int8)v111, v123, v111);
        *((_BYTE *)v18 + 564) = v107;
        memcpy_s(v18 + 283, (unsigned __int8)v107, v124, v107);
        *v18 = v97;
        v19 = v97;
        if ( (_WORD)v97 )
        {
          v20 = ((__int64 (__fastcall *)(struct IMalloc *, _QWORD))g_pMO->lpVtbl[1].Free)(g_pMO, (unsigned __int16)v97);
          v21 = *((_QWORD *)v18 + 1);
          *((_QWORD *)v18 + 1) = v20;
          if ( v21 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
          v19 = v97;
        }
        memcpy_s(*((void *const *)v18 + 1), *v18, v127, v19);
        *((_DWORD *)v18 + 10) = 0;
        if ( *(_BYTE *)(*((_QWORD *)a1 + 14) + 9175LL) >= 2u && (_BYTE)v88 )
        {
          *(_QWORD *)v93 = 0;
          v6 = ExportImp::SQLGetData(
                 a1,
                 (struct tagSTMT *)0xB,
                 0xFFFEu,
                 (__int16)v128,
                 (void *)0x1F40,
                 (__int64)v93,
                 v81);
          if ( (v6 & 0xFFFE) != 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_198;
            v8 = 2473993;
            goto LABEL_17;
          }
          if ( !(unsigned int)sqlencrypt::SqlSecurityUtility::VerifyCMKSignature(
                                (unsigned __int16 *)(*((_QWORD *)a1 + 14) + 3392LL),
                                (const struct sqlencrypt::EncryptionKeyInfo *)v18,
                                v128,
                                v93[0],
                                (struct sqlencrypt::OnEncryptionError *)v116) )
          {
            PostAEv2Error(a1, 0xA19Fu);
            v6 = -1;
            goto LABEL_198;
          }
          *((_DWORD *)v18 + 10) = 1;
          v4 += v97 + 16;
        }
        v6 = ExportImp::SQLFetch(a1, v22);
        if ( v6 == 100 )
          goto LABEL_76;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2424841;
      goto LABEL_17;
    }
LABEL_76:
    v6 = ExportImp::SQLMoreResults(a1, v10);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2490377;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLNumResultCols(a1, (struct tagSTMT *)v89, v23);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2493449;
      goto LABEL_17;
    }
    if ( !v89[0] )
    {
      v6 = ExportImp::SQLMoreResults(a1, v24);
      if ( v6 == 0xFFFF )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_198;
        v8 = 2498569;
        goto LABEL_17;
      }
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)1, 4u, (__int16)v99, 0, (__int64)&v92, v81);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2502665;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)2, 0xFFF8u, (__int16)v125, (void *)0x102, 0, v82);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2504713;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)3, 4u, (__int16)v100, 0, (__int64)&v92, v83);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2506761;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)4, 4u, (__int16)v96, 0, (__int64)&v92, v84);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2508809;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)5, 4u, (__int16)v90, 0, (__int64)&v92, v85);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2510857;
      goto LABEL_17;
    }
    v6 = ExportImp::SQLBindCol(a1, (struct tagSTMT *)6, 4u, (__int16)v101, 0, (__int64)&v92, v86);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2512905;
      goto LABEL_17;
    }
    while ( 1 )
    {
      v6 = ExportImp::SQLFetch(a1, v25);
      if ( v6 == 100 )
        break;
      if ( (v6 & 0xFFFE) != 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_198;
        v8 = 2518025;
        goto LABEL_17;
      }
      v27 = _wtoi(String);
      if ( v27 )
      {
        if ( v27 <= *((_DWORD *)a1 + 199) )
        {
          v28 = *((_QWORD *)a1 + 57);
          if ( v28 )
          {
            v29 = v28 + *(_QWORD *)(v28 + 24) * (v27 - 1LL) + 32;
            if ( v29 )
            {
              if ( LOBYTE(v96[0]) )
              {
                v30 = *(__int64 **)(v106 + 8);
                v31 = (__int64 *)v106;
                while ( !*((_BYTE *)v30 + 25) )
                {
                  if ( *((_DWORD *)v30 + 8) >= *(_DWORD *)v90 )
                  {
                    v31 = v30;
                    v30 = (__int64 *)*v30;
                  }
                  else
                  {
                    v30 = (__int64 *)v30[2];
                  }
                }
                if ( v31 == (__int64 *)v106 || *(_DWORD *)v90 < *((_DWORD *)v31 + 8) )
                  v31 = (__int64 *)v106;
                std::shared_ptr<sqlencrypt::CipherInfoEntry>::shared_ptr<sqlencrypt::CipherInfoEntry>(v103, v31 + 5);
                v32 = (_DWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(
                                  g_pMO,
                                  3480);
                v33 = v32;
                i = v32;
                if ( !v32 )
                {
                  v102 = 0;
                  v6 = -1;
                  if ( (bidGblFlags & 2) != 0 )
                    bidTraceMark(0, 2546697);
                  if ( v104 )
                  {
                    if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
                    {
                      v37 = v104;
                      (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
                      if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
                    }
                  }
                  goto LABEL_198;
                }
                memset_0(v32, 0, 0xD98u);
                v33[796] = 0;
                memset_0(v33 + 797, 0, 0x102u);
                *((_WORD *)v33 + 1723) = 0;
                *((_QWORD *)v33 + 431) = 0;
                *((_QWORD *)v33 + 432) = 0;
                *((_QWORD *)v33 + 433) = 0;
                *((_QWORD *)v33 + 434) = 0;
                v102 = v33;
                std::shared_ptr<sqlencrypt::CipherInfoEntry>::operator=(v33 + 862, v103, v34, v35);
                *((_WORD *)v33 + 1592) = v99[0];
                *((_BYTE *)v33 + 3186) = v100[0];
                *((_BYTE *)v33 + 3446) = v96[0];
                *((_BYTE *)v33 + 3447) = v101[0];
                *(_QWORD *)(v29 + 120) = v102;
                *((_QWORD *)a1 + 540) = PlAddNewIEx(
                                          a1,
                                          *((struct pl **)a1 + 540),
                                          *(_QWORD *)(*((_QWORD *)a1 + 540) + 8LL) + 1LL,
                                          &v102,
                                          1);
                if ( v104 )
                {
                  if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
                  {
                    v36 = v104;
                    (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
                    if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
                  }
                }
              }
              else
              {
                *(_QWORD *)(v29 + 120) = 0;
              }
            }
          }
        }
      }
    }
    if ( !v4 || !*((_QWORD *)a1 + 531) )
    {
      do
      {
LABEL_159:
        v6 = ExportImp::SQLMoreResults(a1, v26);
        if ( v6 == 100 )
        {
          if ( *((_QWORD *)a1 + 538) )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
          *((_QWORD *)a1 + 538) = 0;
          *((_DWORD *)a1 + 1078) = 0;
          if ( v4 )
          {
            LODWORD(v44) = 56;
            v45 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v4 + 56LL);
            *(_QWORD *)v93 = v45;
            sqlencrypt::SqlSecurityUtility::RandomBytes((BYTE *)v45, 0x10u);
            *(_QWORD *)(v45 + 16) = *((_QWORD *)a1 + 537);
            v46 = (_BYTE *)(v45 + 24);
            v47 = 32;
            do
            {
              *v46 = v46[(_QWORD)a1 - v45 + 4232];
              ++v46;
              --v47;
            }
            while ( v47 );
            v48 = (__int64 *)v106;
            v49 = *(__int64 **)v106;
            while ( v49 != v48 )
            {
              v50 = v49[5];
              v51 = *(_QWORD **)v50;
              for ( i = *(_QWORD **)(v50 + 8); v51 != i; ++v51 )
              {
                *(_QWORD *)v103 = *v51;
                if ( *(_DWORD *)(*(_QWORD *)v103 + 40LL) )
                {
                  hMem[0] = 0;
                  LOWORD(v91) = 0;
                  v52 = *((_QWORD *)a1 + 14) + 3392LL;
                  v120 = 0;
                  v121 = 7;
                  LOWORD(v119[0]) = 0;
                  v53 = -1;
                  do
                    ++v53;
                  while ( *(_WORD *)(v52 + 2 * v53) );
                  std::wstring::assign(v119);
                  v54 = sqlencrypt::SqlSecurityUtility::DecryptCEK(
                          (int)v119,
                          v103[0],
                          (int)hMem,
                          (int)&v91,
                          (struct sqlencrypt::SymmetricKeyCache **)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 88LL) + 120LL),
                          *(_DWORD *)(*((_QWORD *)a1 + 14) + 2520LL),
                          (struct sqlencrypt::OnEncryptionError *)v116);
                  LODWORD(v102) = v54;
                  if ( v121 >= 8 )
                  {
                    v55 = *(_QWORD *)v119;
                    v56 = *(_QWORD *)v119;
                    if ( v121 + 1 > 0x7FFFFFFFFFFFFFFFLL
                      || 2 * (v121 + 1) >= 0x1000
                      && ((v119[0] & 0x1F) != 0
                       || (v55 = *(_QWORD *)(*(_QWORD *)v119 - 8LL), v55 >= *(_QWORD *)v119)
                       || (v56 = *(_QWORD *)v119 - v55 - 8, v56 > 0x1F)) )
                    {
                      _invalid_parameter_noinfo_noreturn();
                    }
                    if ( v55 )
                    {
                      ((void (__fastcall *)(struct IMalloc *, unsigned __int64, unsigned __int64))g_pMO->lpVtbl[1].Realloc)(
                        g_pMO,
                        v55,
                        v56);
                      v54 = (int)v102;
                    }
                  }
                  if ( v54 )
                  {
                    ((void (__fastcall *)(struct IMalloc *, _QWORD))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, *(_QWORD *)v93);
                    goto LABEL_198;
                  }
                  v57 = *(_QWORD *)v93;
                  v58 = *(_QWORD *)v103;
                  *(_DWORD *)((unsigned int)v44 + *(_QWORD *)v93) = *(_DWORD *)(*(_QWORD *)v103 + 16LL);
                  *(_QWORD *)((unsigned int)v44 + v57 + 4) = *(_QWORD *)(v58 + 32);
                  *(_WORD *)((unsigned int)v44 + v57 + 12) = *(_WORD *)(v58 + 20);
                  v44 = (unsigned int)(v44 + 14);
                  v59 = hMem[0];
                  if ( (_WORD)v91 )
                  {
                    v60 = hMem[0];
                    v61 = (unsigned __int16)v91;
                    do
                    {
                      *(_BYTE *)(v44 + v57) = *v60;
                      v44 = (unsigned int)(v44 + 1);
                      ++v60;
                      --v61;
                    }
                    while ( v61 );
                  }
                  LocalFree(v59);
                }
              }
              if ( !*((_BYTE *)v49 + 25) )
              {
                v62 = (__int64 **)v49[2];
                if ( *((_BYTE *)v62 + 25) )
                {
                  for ( j = (__int64 *)v49[1]; !*((_BYTE *)j + 25) && v49 == (__int64 *)j[2]; j = (__int64 *)j[1] )
                    v49 = j;
                  v49 = j;
                }
                else
                {
                  v49 = (__int64 *)v49[2];
                  for ( k = *v62; !*((_BYTE *)k + 25); k = (__int64 *)*k )
                    v49 = k;
                }
              }
            }
            *((_QWORD *)a1 + 538) = *(_QWORD *)v93;
            *((_DWORD *)a1 + 1078) = v44;
          }
          goto LABEL_198;
        }
      }
      while ( (v6 & 0xFFFE) == 0 );
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_198;
      v8 = 2622473;
      goto LABEL_17;
    }
    *(_QWORD *)v93 = 0;
    v6 = ExportImp::SQLMoreResults(a1, v26);
    if ( v6 )
      goto LABEL_155;
    v6 = ExportImp::SQLNumResultCols(a1, (struct tagSTMT *)v89, v38);
    if ( v6 )
      goto LABEL_155;
    if ( !v89[0] )
    {
      v6 = ExportImp::SQLMoreResults(a1, v39);
      if ( (v6 & 0xFFFE) != 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_155;
        v41 = 2585609;
        goto LABEL_143;
      }
    }
    v6 = ExportImp::SQLFreeStmt(a1, (struct tagSTMT *)2, v40);
    if ( v6 == 0xFFFF )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v41 = 2589705;
LABEL_143:
        bidTraceMark(0, v41);
      }
    }
    else
    {
      v6 = ExportImp::SQLFetch(a1, v42);
      if ( (v6 & 0xFFFE) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v41 = 2591753;
          goto LABEL_143;
        }
      }
      else
      {
        v6 = ExportImp::SQLGetData(a1, (struct tagSTMT *)1, 0xFFFEu, (__int16)v128, (void *)0x1F40, (__int64)v93, v87);
        if ( (v6 & 0xFFFE) != 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v41 = 2596873;
            goto LABEL_143;
          }
        }
        else
        {
          hMem[0] = PostEnclaveError;
          hMem[1] = a1;
          v43 = *((_QWORD *)a1 + 14);
          v69 = v43 + 3392;
          if ( !(*(unsigned int (__fastcall **)(HLOCAL *, unsigned __int8 *, _QWORD, _QWORD))(*(_QWORD *)(v43 + 3296)
                                                                                            + 32LL))(
                  hMem,
                  v128,
                  v93[0],
                  *((_QWORD *)a1 + 531)) )
          {
            PostAEv2Error(a1, 0xA1A0u);
            v6 = -1;
          }
        }
      }
    }
LABEL_155:
    LocalFree(*((HLOCAL *)a1 + 531));
    *((_QWORD *)a1 + 531) = 0;
    if ( v6 != 0xFFFF )
      goto LABEL_159;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = 2616329;
      goto LABEL_17;
    }
    goto LABEL_198;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v8 = 2401289;
LABEL_17:
    bidTraceMark(0, v8);
  }
LABEL_198:
  v65 = *((_WORD *)a1 + 12);
  *((_WORD *)a1 + 12) = v65 | 4;
  v66 = ExportImp::SQLSetStmtAttrW(a1, (struct tagSTMT *)0x271A, v113[0], 0, v69);
  *((_WORD *)a1 + 12) = v65;
  if ( v66 == -1 && (bidGblFlags & 2) != 0 )
  {
    v7 = 2697225;
LABEL_201:
    bidTraceMark(0, v7);
  }
LABEL_202:
  FreeDesc(v108, 0, 3u);
  if ( (bidGblFlags & 2) != 0 )
    v6 = _bidx_SNACOdbc_ErrCode(0, 0x293C09u, v6);
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<sqlencrypt::CipherInfoEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<sqlencrypt::CipherInfoEntry>>>,0>>::erase(
    &v106,
    v117,
    *(_QWORD *)v106);
  if ( (_QWORD)v106 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  return v6;
}

```

## disassembly

```asm
0x1004c7328  push    rbp
0x1004c732a  push    r12
0x1004c732c  push    r13
0x1004c732e  push    r14
0x1004c7330  push    r15
0x1004c7332  lea     rbp, [rsp-4350h]
0x1004c733a  mov     eax, 4450h
0x1004c733f  call    _alloca_probe
0x1004c7344  sub     rsp, rax
0x1004c7347  mov     [rbp+4370h+var_4318], 0FFFFFFFFFFFFFFFEh
0x1004c734f  mov     [rsp+4470h+arg_8], rbx
0x1004c7357  mov     [rsp+4470h+arg_10], rsi
0x1004c735f  mov     [rsp+4470h+arg_18], rdi
0x1004c7367  mov     rax, cs:__security_cookie
0x1004c736e  xor     rax, rsp
0x1004c7371  mov     [rbp+4370h+var_30], rax
0x1004c7378  mov     r14, rcx
0x1004c737b  xor     edx, edx; Val
0x1004c737d  mov     r8d, 1F40h; Size
0x1004c7383  lea     rcx, [rbp+4370h+var_3EB0]; void *
0x1004c738a  call    memset_0
0x1004c738f  mov     edi, 102h
0x1004c7394  mov     r8d, edi; Size
0x1004c7397  xor     edx, edx; Val
0x1004c7399  lea     rcx, [rbp+4370h+var_41E0]; void *
0x1004c73a0  call    memset_0
0x1004c73a5  mov     r8d, edi; Size
0x1004c73a8  xor     edx, edx; Val
0x1004c73aa  lea     rcx, [rbp+4370h+Source]; void *
0x1004c73b1  call    memset_0
0x1004c73b6  mov     r8d, edi; Size
0x1004c73b9  xor     edx, edx; Val
0x1004c73bb  lea     rcx, [rbp+4370h+var_40D0]; void *
0x1004c73c2  call    memset_0
0x1004c73c7  xor     ebx, ebx
0x1004c73c9  mov     dword ptr [rsp+4470h+var_4418], ebx
0x1004c73cd  mov     dword ptr [rbp+4370h+var_43E8], ebx
0x1004c73d0  mov     dword ptr [rsp+4470h+var_4400], ebx
0x1004c73d4  mov     dword ptr [rsp+4470h+var_43FC], ebx
0x1004c73d8  mov     qword ptr [rbp+4370h+var_4398], rbx
0x1004c73dc  mov     byte ptr [rsp+4470h+var_4420], bl
0x1004c73e0  mov     [rbp+4370h+var_43F0], rbx
0x1004c73e4  mov     [rbp+4370h+var_4368], rbx
0x1004c73e8  mov     [rbp+4370h+var_4388], rbx
0x1004c73ec  mov     [rbp+4370h+SourceSize], rbx
0x1004c73f0  mov     [rbp+4370h+var_43A8], rbx
0x1004c73f4  mov     [rbp+4370h+var_4360], rbx
0x1004c73f8  mov     [rsp+4470h+var_4410], rbx
0x1004c73fd  mov     [rsp+4470h+var_441C], bx
0x1004c7402  mov     dword ptr [rbp+4370h+var_43E4], ebx
0x1004c7405  mov     r8d, edi; Size
0x1004c7408  xor     edx, edx; Val
0x1004c740a  lea     rcx, [rbp+4370h+var_3FC0]; void *
0x1004c7411  call    memset_0
0x1004c7416  mov     dword ptr [rbp+4370h+var_43E0], ebx
0x1004c7419  mov     dword ptr [rsp+4470h+var_43F8], ebx
0x1004c741d  mov     dword ptr [rbp+4370h+var_43DC], ebx
0x1004c7420  mov     rcx, [r14+70h]
0x1004c7424  mov     rax, [rcx+58h]
0x1004c7428  mov     [rbp+4370h+var_4330], rax
0x1004c742c  mov     [rbp+4370h+var_4328], rcx
0x1004c7430  mov     [rbp+4370h+var_4320], r14
0x1004c7434  mov     rax, [rcx+9D0h]
0x1004c743b  lea     rcx, [rbp+4370h+var_4330]
0x1004c743f  mov     [rbp+4370h+var_4358], rcx
0x1004c7443  mov     [rbp+4370h+var_4350], rax
0x1004c7447  lea     rax, ?HandleAEexception@@YAXPEAXPEBGPEAPEAD@Z; HandleAEexception(void *,ushort const *,char * *)
0x1004c744e  mov     [rbp+4370h+var_4348], rax
0x1004c7452  mov     r12d, ebx
0x1004c7455  mov     rcx, r14; this
0x1004c7458  call    ?CleanupCryptoMetaDataSet@tagSTMT@@QEAAXXZ; tagSTMT::CleanupCryptoMetaDataSet(void)
0x1004c745d  lea     eax, [rbx+10h]
0x1004c7460  cmp     [r14+10E0h], rbx
0x1004c7467  jnz     short loc_1004C7489
0x1004c7469  mov     dword ptr [rsp+4470h+var_4450], 1; int
0x1004c7471  lea     r9d, [rbx+8]; unsigned __int64
0x1004c7475  mov     r8d, eax; unsigned __int64
0x1004c7478  mov     edx, eax; unsigned __int64
0x1004c747a  mov     rcx, r14; struct tagOBJBASE *
0x1004c747d  call    ?PlAllocEx@@YAPEAUpl@@PEAUtagOBJBASE@@_K11H@Z; PlAllocEx(tagOBJBASE *,unsigned __int64,unsigned __int64,unsigned __int64,int)
0x1004c7482  mov     [r14+10E0h], rax
0x1004c7489  xorps   xmm0, xmm0
0x1004c748c  movdqu  [rbp+4370h+var_43B8], xmm0
0x1004c7491  lea     rcx, [rbp+4370h+var_43B8]
0x1004c7495  call    ?_Buyheadnode@?$_Tree_comp_alloc@V?$_Tmap_traits@KV?$shared_ptr@UCipherInfoEntry@sqlencrypt@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UCipherInfoEntry@sqlencrypt@@@std@@@std@@@2@$0A@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UCipherInfoEntry@sqlencrypt@@@std@@@std@@PEAX@2@XZ; std::_Tree_comp_alloc<std::_Tmap_traits<ulong,std::shared_ptr<sqlencrypt::CipherInfoEntry>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<sqlencrypt::CipherInfoEntry>>>,0>>::_Buyheadnode(void)
0x1004c749a  mov     qword ptr [rbp+4370h+var_43B8], rax
0x1004c749e  mov     r13, rbx
0x1004c74a1  mov     [rbp+4370h+var_43A0], rbx
0x1004c74a5  mov     qword ptr [rbp+4370h+var_4370], rbx
0x1004c74a9  lea     rdx, [rbp+4370h+var_43A0]; void **
0x1004c74ad  mov     rcx, [r14+70h]; struct tagDBC *
0x1004c74b1  call    ?AllocDesc@@YAFPEAUtagDBC@@PEAPEAX@Z; AllocDesc(tagDBC *,void * *)
0x1004c74b6  movzx   esi, ax
0x1004c74b9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1004c74bd  cmp     ax, di
0x1004c74c0  jnz     short loc_1004C74DD
0x1004c74c2  lea     r15d, [rdi+3]
0x1004c74c6  test    byte ptr cs:_bidGblFlags, r15b
0x1004c74cd  jz      loc_1004C859F
0x1004c74d3  mov     edx, 246409h
0x1004c74d8  jmp     loc_1004C8598
0x1004c74dd  mov     [rsp+4470h+var_4450], rbx; int
0x1004c74e2  xor     r9d, r9d; void *
0x1004c74e5  lea     r8, [rbp+4370h+var_4370]; int
0x1004c74e9  mov     r15d, 271Ah
0x1004c74ef  mov     edx, r15d; struct tagSTMT *
0x1004c74f2  mov     rcx, r14; this
0x1004c74f5  call    ?SQLGetStmtAttrW@ExportImp@@YAFPEAUtagSTMT@@JPEAXJPEAJ@Z; ExportImp::SQLGetStmtAttrW(tagSTMT *,long,void *,long,long *)
0x1004c74fa  movzx   esi, ax
0x1004c74fd  cmp     ax, di
0x1004c7500  jnz     short loc_1004C751F
0x1004c7502  mov     r15d, 2
0x1004c7508  test    byte ptr cs:_bidGblFlags, r15b
0x1004c750f  jz      loc_1004C859F
0x1004c7515  mov     edx, 246C09h
0x1004c751a  jmp     loc_1004C8598
0x1004c751f  xor     r9d, r9d; unsigned __int64
0x1004c7522  mov     r8, [rbp+4370h+var_43A0]; int
0x1004c7526  mov     edx, r15d; struct tagSTMT *
0x1004c7529  mov     rcx, r14; this
0x1004c752c  call    ?SQLSetStmtAttrW@ExportImp@@YAFPEAUtagSTMT@@J_KJ@Z; ExportImp::SQLSetStmtAttrW(tagSTMT *,long,unsigned __int64,long)
0x1004c7531  movzx   esi, ax
0x1004c7534  mov     r15d, 2
0x1004c753a  cmp     ax, di
0x1004c753d  jnz     short loc_1004C7556
0x1004c753f  test    byte ptr cs:_bidGblFlags, r15b
0x1004c7546  jz      loc_1004C859F
0x1004c754c  mov     edx, 247409h
0x1004c7551  jmp     loc_1004C8598
0x1004c7556  mov     eax, 4
0x1004c755b  cmp     dword ptr [r14+820h], 1
0x1004c7563  jnz     loc_1004C8557
0x1004c7569  cmp     [r14+10Eh], bx
0x1004c7571  jz      loc_1004C8557
0x1004c7577  mov     r8d, eax; unsigned __int16
0x1004c757a  lea     edx, [rax-3]; struct tagSTMT *
0x1004c757d  lea     rax, [rsp+4470h+var_4410]
0x1004c7582  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c7587  mov     [rsp+4470h+var_4450], rbx; void *
0x1004c758c  lea     r9, [rsp+4470h+var_4418]; __int16
0x1004c7591  mov     rcx, r14; this
0x1004c7594  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c7599  movzx   esi, ax
0x1004c759c  cmp     ax, di
0x1004c759f  jnz     short loc_1004C75BF
0x1004c75a1  test    byte ptr cs:_bidGblFlags, r15b
0x1004c75a8  jz      loc_1004C8557
0x1004c75ae  mov     edx, 24A409h
0x1004c75b3  xor     ecx, ecx
0x1004c75b5  call    _bidTraceMark
0x1004c75ba  jmp     loc_1004C8557
0x1004c75bf  mov     r8d, 4; unsigned __int16
0x1004c75c5  mov     edx, r15d; struct tagSTMT *
0x1004c75c8  lea     rax, [rsp+4470h+var_4410]
0x1004c75cd  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c75d2  mov     [rsp+4470h+var_4450], rbx; void *
0x1004c75d7  lea     r9, [rbp+4370h+var_43E8]; __int16
0x1004c75db  mov     rcx, r14; this
0x1004c75de  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c75e3  movzx   esi, ax
0x1004c75e6  cmp     ax, di
0x1004c75e9  jnz     short loc_1004C75FF
0x1004c75eb  test    byte ptr cs:_bidGblFlags, r15b
0x1004c75f2  jz      loc_1004C8557
0x1004c75f8  mov     edx, 24AC09h
0x1004c75fd  jmp     short loc_1004C75B3
0x1004c75ff  mov     edx, 3; struct tagSTMT *
0x1004c7604  lea     r8d, [rdx+1]; unsigned __int16
0x1004c7608  lea     rax, [rsp+4470h+var_4410]
0x1004c760d  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c7612  mov     [rsp+4470h+var_4450], rbx; void *
0x1004c7617  lea     r9, [rsp+4470h+var_4400]; __int16
0x1004c761c  mov     rcx, r14; this
0x1004c761f  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c7624  movzx   esi, ax
0x1004c7627  cmp     ax, di
0x1004c762a  jnz     short loc_1004C7643
0x1004c762c  test    byte ptr cs:_bidGblFlags, r15b
0x1004c7633  jz      loc_1004C8557
0x1004c7639  mov     edx, 24B409h
0x1004c763e  jmp     loc_1004C75B3
0x1004c7643  mov     eax, 4
0x1004c7648  mov     r8d, eax; unsigned __int16
0x1004c764b  mov     edx, eax; struct tagSTMT *
0x1004c764d  lea     rax, [rsp+4470h+var_4410]
0x1004c7652  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c7657  mov     [rsp+4470h+var_4450], rbx; void *
0x1004c765c  lea     r9, [rsp+4470h+var_43FC]; __int16
0x1004c7661  mov     rcx, r14; this
0x1004c7664  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c7669  movzx   esi, ax
0x1004c766c  cmp     ax, di
0x1004c766f  jnz     short loc_1004C7688
0x1004c7671  test    byte ptr cs:_bidGblFlags, r15b
0x1004c7678  jz      loc_1004C8557
0x1004c767e  mov     edx, 24BC09h
0x1004c7683  jmp     loc_1004C75B3
0x1004c7688  mov     edx, 5; struct tagSTMT *
0x1004c768d  lea     r8d, [rdx-7]; unsigned __int16
0x1004c7691  lea     rax, [rbp+4370h+var_4368]
0x1004c7695  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c769a  mov     [rsp+4470h+var_4450], 8; void *
0x1004c76a3  lea     r9, [rbp+4370h+var_4398]; __int16
0x1004c76a7  mov     rcx, r14; this
0x1004c76aa  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c76af  movzx   esi, ax
0x1004c76b2  cmp     ax, di
0x1004c76b5  jnz     short loc_1004C76CE
0x1004c76b7  test    byte ptr cs:_bidGblFlags, r15b
0x1004c76be  jz      loc_1004C8557
0x1004c76c4  mov     edx, 24C409h
0x1004c76c9  jmp     loc_1004C75B3
0x1004c76ce  mov     edx, 6; struct tagSTMT *
0x1004c76d3  lea     r8d, [rdx-8]; unsigned __int16
0x1004c76d7  lea     rax, [rbp+4370h+var_43F0]
0x1004c76db  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c76e0  mov     [rsp+4470h+var_4450], 1F40h; void *
0x1004c76e9  lea     r9, [rbp+4370h+var_3EB0]; __int16
0x1004c76f0  mov     rcx, r14; this
0x1004c76f3  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c76f8  movzx   esi, ax
0x1004c76fb  cmp     ax, di
0x1004c76fe  jnz     short loc_1004C7717
0x1004c7700  test    byte ptr cs:_bidGblFlags, r15b
0x1004c7707  jz      loc_1004C8557
0x1004c770d  mov     edx, 24CC09h
0x1004c7712  jmp     loc_1004C75B3
0x1004c7717  mov     edx, 7; struct tagSTMT *
0x1004c771c  lea     r8d, [rdx-0Fh]; unsigned __int16
0x1004c7720  lea     rax, [rbp+4370h+var_4388]
0x1004c7724  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c7729  mov     [rsp+4470h+var_4450], 102h; void *
0x1004c7732  lea     r9, [rbp+4370h+var_41E0]; __int16
0x1004c7739  mov     rcx, r14; this
0x1004c773c  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c7741  movzx   esi, ax
0x1004c7744  cmp     ax, di
0x1004c7747  jnz     short loc_1004C7760
0x1004c7749  test    byte ptr cs:_bidGblFlags, r15b
0x1004c7750  jz      loc_1004C8557
0x1004c7756  mov     edx, 24D409h
0x1004c775b  jmp     loc_1004C75B3
0x1004c7760  mov     edx, 8; struct tagSTMT *
0x1004c7765  lea     r8d, [rdx-10h]; unsigned __int16
0x1004c7769  lea     rax, [rbp+4370h+SourceSize]
0x1004c776d  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c7772  mov     [rsp+4470h+var_4450], 102h; void *
0x1004c777b  lea     r9, [rbp+4370h+Source]; __int16
0x1004c7782  mov     rcx, r14; this
0x1004c7785  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c778a  movzx   esi, ax
0x1004c778d  cmp     ax, di
0x1004c7790  jnz     short loc_1004C77A9
0x1004c7792  test    byte ptr cs:_bidGblFlags, r15b
0x1004c7799  jz      loc_1004C8557
0x1004c779f  mov     edx, 24DC09h
0x1004c77a4  jmp     loc_1004C75B3
0x1004c77a9  mov     edx, 9; struct tagSTMT *
0x1004c77ae  lea     r8d, [rdx-11h]; unsigned __int16
0x1004c77b2  lea     rax, [rbp+4370h+var_43A8]
0x1004c77b6  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c77bb  mov     [rsp+4470h+var_4450], 102h; void *
0x1004c77c4  lea     r9, [rbp+4370h+var_40D0]; __int16
0x1004c77cb  mov     rcx, r14; this
0x1004c77ce  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c77d3  movzx   esi, ax
0x1004c77d6  cmp     ax, di
0x1004c77d9  jnz     short loc_1004C77F2
0x1004c77db  test    byte ptr cs:_bidGblFlags, r15b
0x1004c77e2  jz      loc_1004C8557
0x1004c77e8  mov     edx, 24E409h
0x1004c77ed  jmp     loc_1004C75B3
0x1004c77f2  mov     edx, 0Ah; struct tagSTMT *
0x1004c77f7  lea     r8d, [rdx-0Ch]; unsigned __int16
0x1004c77fb  lea     rax, [rbp+4370h+var_4360]
0x1004c77ff  mov     [rsp+4470h+var_4448], rax; __int64
0x1004c7804  mov     [rsp+4470h+var_4450], 1; void *
0x1004c780d  lea     r9, [rsp+4470h+var_4420]; __int16
0x1004c7812  mov     rcx, r14; this
0x1004c7815  call    ?SQLBindCol@ExportImp@@YAFPEAUtagSTMT@@GFPEAX_JPEA_J@Z; ExportImp::SQLBindCol(tagSTMT *,ushort,short,void *,__int64,__int64 *)
0x1004c781a  movzx   esi, ax
0x1004c781d  cmp     ax, di
0x1004c7820  jnz     short loc_1004C7839
0x1004c7822  test    byte ptr cs:_bidGblFlags, r15b
0x1004c7829  jz      loc_1004C8557
0x1004c782f  mov     edx, 24EC09h
0x1004c7834  jmp     loc_1004C75B3
0x1004c7839  mov     rcx, r14; this
0x1004c783c  call    ?SQLFetch@ExportImp@@YAFPEAUtagSTMT@@@Z; ExportImp::SQLFetch(tagSTMT *)
0x1004c7841  movzx   esi, ax
0x1004c7844  mov     eax, 0FFFEh
0x1004c7849  cmp     si, 64h ; 'd'
0x1004c784d  jz      loc_1004C7BF2
0x1004c7853  test    ax, si
0x1004c7856  jnz     loc_1004C7BD7
0x1004c785c  mov     eax, dword ptr [rsp+4470h+var_4418]
0x1004c7860  mov     [rsp+4470h+var_4414], eax
0x1004c7864  lea     r8, [rsp+4470h+var_4414]
0x1004c7869  lea     rdx, [rbp+4370h+var_4340]
0x1004c786d  lea     rcx, [rbp+4370h+var_43B8]
  ... truncated ...
```
