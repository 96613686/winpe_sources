# CMemPropStore::_SetValueAndStateInsideLock(_tagpropertykey const &,tagPROPVARIANT *,PSC_STATE,int)

- ea: `0x180010550`
- end: `0x180011009`
- name: `?_SetValueAndStateInsideLock@CMemPropStore@@AEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@W4PSC_STATE@@H@Z`
- size: `2745`
- prototype: `int(CMemPropStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *, enum PSC_STATE, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010110`
- `0x1800113a0`
- `0x18004d0f0`
- `0x18004e270`

## callees

- `0x18000f050`
- `0x180010550`
- `0x1800113a0`
- `0x180011ca4`
- `0x18003f030`
- `0x18004db30`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001091e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010e9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001091e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800106f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800106f3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180010601`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180010601`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010c2d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010ef5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010fe4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010c2d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010ef5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010fe4`

## pseudocode

```c
__int64 __fastcall CMemPropStore::_SetValueAndStateInsideLock(
        CMemPropStore *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3,
        enum PSC_STATE a4,
        int a5)
{
  _BYTE *v5; // rdi
  struct _DSA *v10; // rcx
  HRESULT v11; // esi
  bool v12; // zf
  unsigned __int64 v13; // kr00_8
  unsigned __int64 v14; // rdi
  unsigned int v15; // edx
  __int64 v16; // rcx
  unsigned int v17; // r10d
  unsigned int v18; // r10d
  __int64 v19; // r9
  unsigned int v20; // edx
  unsigned int v21; // ecx
  unsigned int v22; // edx
  unsigned int v23; // ecx
  unsigned int v24; // edx
  unsigned int v25; // ecx
  unsigned int v26; // edx
  unsigned int v27; // ecx
  unsigned int v28; // edx
  unsigned int v29; // ecx
  unsigned int v30; // edx
  unsigned int v31; // ecx
  unsigned int v32; // edx
  unsigned int v33; // ecx
  unsigned int v34; // edx
  unsigned int v35; // ecx
  unsigned int v36; // edx
  unsigned int v37; // r8d
  int v38; // eax
  int v39; // r8d
  unsigned int k; // eax
  unsigned int v41; // edx
  __int64 v42; // rcx
  int v43; // eax
  char *v44; // rbx
  __int64 v45; // r9
  unsigned int v46; // ecx
  unsigned int v47; // edx
  unsigned int v48; // ecx
  unsigned int v49; // edx
  unsigned int v50; // ecx
  unsigned int v51; // edx
  unsigned int v52; // ecx
  unsigned int v53; // edx
  unsigned int v54; // ecx
  unsigned int v55; // edx
  unsigned int v56; // ecx
  unsigned int v57; // edx
  unsigned int v58; // ecx
  unsigned int v59; // edx
  unsigned int v60; // ecx
  unsigned int v61; // r8d
  unsigned int v62; // edx
  int v63; // r8d
  unsigned int v64; // ecx
  unsigned int v65; // edx
  unsigned int j; // eax
  __int64 v67; // rcx
  int v68; // eax
  __int64 v69; // rax
  BYTE *v70; // xmm1_8
  __int64 v71; // rcx
  int v72; // eax
  __int128 v73; // xmm1
  __int128 v75; // xmm1
  __int64 v76; // r9
  unsigned int v77; // r10d
  unsigned int v78; // edx
  unsigned int v79; // ecx
  unsigned int v80; // edx
  unsigned int v81; // ecx
  unsigned int v82; // edx
  unsigned int v83; // ecx
  unsigned int v84; // edx
  unsigned int v85; // ecx
  unsigned int v86; // edx
  unsigned int v87; // ecx
  unsigned int v88; // edx
  unsigned int v89; // ecx
  unsigned int v90; // edx
  unsigned int v91; // ecx
  unsigned int v92; // r8d
  unsigned int v93; // edx
  int v94; // r8d
  unsigned int v95; // ecx
  unsigned int v96; // edx
  unsigned int i; // eax
  unsigned int v98; // edx
  __int64 v99; // rcx
  int v100; // eax
  HLOCAL v101; // rax
  __int64 v102; // rax
  __int64 v103; // rcx
  __int64 v104; // rcx
  _DWORD *v105; // rax
  __int64 v106; // rax
  _BYTE *v107; // [rsp+20h] [rbp-A8h]
  PROPVARIANT pvarDest[4]; // [rsp+30h] [rbp-98h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-78h] BYREF
  __int128 v110; // [rsp+60h] [rbp-68h]

  v5 = (char *)this + 240;
  v107 = (char *)this + 240;
  if ( (*((_BYTE *)this + 192) & 1) != 0 )
  {
    if ( !*v5 )
      return (unsigned int)-2147287035;
  }
  else
  {
    v107 = (char *)this + 240;
  }
  v10 = (struct _DSA *)*((_QWORD *)this + 21);
  if ( v10 )
  {
    DSA_Destroy(v10);
    *((_QWORD *)this + 21) = 0;
  }
  v11 = CMemPropStore::_EnsureUnserializedInsideLock(this);
  if ( v11 >= 0 )
  {
    if ( !a3 )
    {
      v103 = *((_QWORD *)this + 15);
      if ( v103
        && (v105 = (_DWORD *)CSimpleHashTable<_tagpropertykey,CMemPropStore::CACHEDPROPERTY,CDefaultHashPolicy<_tagpropertykey>,CDefaultKeyCompare<_tagpropertykey>,CMemPropStoreResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(
                               v103,
                               *((unsigned int *)this + 27),
                               a2),
            *v105 == 1) )
      {
        v11 = 0;
        if ( v105[6] != a4 )
        {
          if ( !*v5 )
            *((_BYTE *)this + 188) = 1;
          v105[6] = a4;
        }
      }
      else
      {
        return (unsigned int)-2147319765;
      }
      return (unsigned int)v11;
    }
    if ( !*v5 && (*((_BYTE *)this + 184) & 2) == 0 )
      goto LABEL_9;
    v76 = *((_QWORD *)this + 15);
    if ( !v76 )
      goto LABEL_72;
    v77 = *((_DWORD *)this + 27);
    _mm_lfence();
    v78 = (LOBYTE(a2->fmtid.Data1) + 694790345)
        ^ 0x12B9B0A5
        ^ ((((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5u) >> 2)
         + 2080 * ((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5)
         + BYTE1(a2->fmtid.Data1));
    v79 = v78 ^ ((v78 >> 2) + 2080 * v78 + BYTE2(a2->fmtid.Data1));
    v80 = v79 ^ ((v79 >> 2) + 2080 * v79 + HIBYTE(a2->fmtid.Data1));
    v81 = v80 ^ ((v80 >> 2) + 2080 * v80 + LOBYTE(a2->fmtid.Data2));
    v82 = v81 ^ ((v81 >> 2) + 2080 * v81 + HIBYTE(a2->fmtid.Data2));
    v83 = v82 ^ ((v82 >> 2) + 2080 * v82 + LOBYTE(a2->fmtid.Data3));
    v84 = v83 ^ ((v83 >> 2) + 2080 * v83 + HIBYTE(a2->fmtid.Data3));
    v85 = v84 ^ ((v84 >> 2) + 2080 * v84 + a2->fmtid.Data4[0]);
    v86 = v85 ^ ((v85 >> 2) + 2080 * v85 + a2->fmtid.Data4[1]);
    v87 = v86 ^ (2080 * v86 + (v86 >> 2) + a2->fmtid.Data4[2]);
    v88 = v87 ^ (2080 * v87 + (v87 >> 2) + a2->fmtid.Data4[3]);
    v89 = v88 ^ (2080 * v88 + (v88 >> 2) + a2->fmtid.Data4[4]);
    v90 = v89 ^ (2080 * v89 + (v89 >> 2) + a2->fmtid.Data4[5]);
    v91 = v90 ^ (2080 * v90 + (v90 >> 2) + a2->fmtid.Data4[6]);
    v92 = v91 ^ (2080 * v91 + (v91 >> 2) + a2->fmtid.Data4[7]);
    v93 = v92 ^ (LOBYTE(a2->pid) + 2080 * v92 + (v92 >> 2));
    v94 = -1;
    v95 = v93 ^ (2080 * v93 + (v93 >> 2) + BYTE1(a2->pid));
    v96 = v95 ^ (2080 * v95 + (v95 >> 2) + BYTE2(a2->pid));
    for ( i = (v96 ^ ((v96 >> 2) + 2080 * v96 + HIBYTE(a2->pid))) & 0x7FFFFFFF; ; i = v98 + 1 )
    {
      v98 = i % v77;
      v99 = 56LL * (i % v77);
      v100 = *(_DWORD *)(v99 + v76);
      if ( v100 == 2 )
      {
        if ( v94 == -1 )
          v94 = v98;
      }
      else
      {
        if ( !v100 )
        {
          if ( v94 != -1 )
            v98 = v94;
LABEL_79:
          v104 = 56LL * v98;
          if ( *(_DWORD *)(v104 + v76) == 1 )
          {
            if ( !PropVariantCompareEx((const PROPVARIANT *const)(v76 + v104 + 32), a3, PVCU_DEFAULT, 2) )
            {
LABEL_73:
              v11 = 1;
              if ( a5 )
                PropVariantClear(a3);
              return (unsigned int)v11;
            }
LABEL_9:
            memset(pvarDest, 0, sizeof(pvarDest));
            if ( a5 )
            {
              v70 = (BYTE *)a3[2];
              *(_OWORD *)&pvarDest[1] = *(_OWORD *)a3;
              pvarDest[3] = v70;
            }
            else
            {
              v11 = PropVariantCopy(&pvarDest[1], a3);
              if ( v11 < 0 )
                return (unsigned int)v11;
            }
            v12 = *((_QWORD *)this + 15) == 0;
            *(_OWORD *)pvar = 0;
            LODWORD(pvarDest[0]) = a4;
            v110 = 0;
            if ( !v12 )
              goto LABEL_15;
            v13 = *((unsigned int *)this + 27);
            *((_QWORD *)this + 15) = 0;
            if ( is_mul_ok(v13, 0x38u) )
            {
              v101 = LocalAlloc(0x40u, 56 * v13);
              v11 = 0;
              *((_QWORD *)this + 15) = v101;
              if ( !v101 )
                v11 = -2147024882;
            }
            else
            {
              v11 = -2147024362;
            }
            if ( v11 >= 0 )
            {
LABEL_15:
              v14 = *((unsigned int *)this + 27);
              if ( 5 * *((_DWORD *)this + 26) <= (unsigned int)(4 * v14) )
              {
                if ( *((_DWORD *)this + 28) > (unsigned int)v14 >> 2 )
                {
                  if ( !is_mul_ok(v14, 0x38u) )
                  {
                    v11 = -2147024362;
                    goto LABEL_24;
                  }
                  v11 = 0;
                  v44 = (char *)LocalAlloc(0x40u, 56 * v14);
                  if ( !v44 )
                  {
                    v11 = -2147024882;
                    goto LABEL_24;
                  }
                  v17 = 0;
                  if ( !*((_DWORD *)this + 27) )
                    goto LABEL_23;
LABEL_34:
                  v45 = *((_QWORD *)this + 15) + 56LL * v17;
                  if ( *(_DWORD *)v45 != 1 )
                    goto LABEL_22;
                  _mm_lfence();
                  v46 = (*(unsigned __int8 *)(v45 + 4) + 694790345) ^ 0x12B9B0A5;
                  v47 = v46 ^ ((v46 >> 2) + 2080 * v46 + *(unsigned __int8 *)(v45 + 5));
                  v48 = v47 ^ ((v47 >> 2) + 2080 * v47 + *(unsigned __int8 *)(v45 + 6));
                  v49 = v48 ^ ((v48 >> 2) + 2080 * v48 + *(unsigned __int8 *)(v45 + 7));
                  v50 = v49 ^ ((v49 >> 2) + 2080 * v49 + *(unsigned __int8 *)(v45 + 8));
                  v51 = v50 ^ ((v50 >> 2) + 2080 * v50 + *(unsigned __int8 *)(v45 + 9));
                  v52 = v51 ^ ((v51 >> 2) + 2080 * v51 + *(unsigned __int8 *)(v45 + 10));
                  v53 = v52 ^ ((v52 >> 2) + 2080 * v52 + *(unsigned __int8 *)(v45 + 11));
                  v54 = v53 ^ ((v53 >> 2) + 2080 * v53 + *(unsigned __int8 *)(v45 + 12));
                  v55 = v54 ^ ((v54 >> 2) + 2080 * v54 + *(unsigned __int8 *)(v45 + 13));
                  v56 = v55 ^ ((v55 >> 2) + 2080 * v55 + *(unsigned __int8 *)(v45 + 14));
                  v57 = v56 ^ ((v56 >> 2) + 2080 * v56 + *(unsigned __int8 *)(v45 + 15));
                  v58 = v57 ^ (2080 * v57 + (v57 >> 2) + *(unsigned __int8 *)(v45 + 16));
                  v59 = v58 ^ (2080 * v58 + (v58 >> 2) + *(unsigned __int8 *)(v45 + 17));
                  v60 = v59 ^ (2080 * v59 + (v59 >> 2) + *(unsigned __int8 *)(v45 + 18));
                  v61 = v60 ^ (2080 * v60 + (v60 >> 2) + *(unsigned __int8 *)(v45 + 19));
                  v62 = v61 ^ (*(unsigned __int8 *)(v45 + 20) + 2080 * v61 + (v61 >> 2));
                  v63 = -1;
                  v64 = v62 ^ ((v62 >> 2) + 2080 * v62 + *(unsigned __int8 *)(v45 + 21));
                  v65 = v64 ^ ((v64 >> 2) + 2080 * v64 + *(unsigned __int8 *)(v45 + 22));
                  for ( j = (v65 ^ ((v65 >> 2) + 2080 * v65 + *(unsigned __int8 *)(v45 + 23))) & 0x7FFFFFFF; ; j = v15 + 1 )
                  {
                    v15 = j % (unsigned int)v14;
                    v67 = 56LL * (j % (unsigned int)v14);
                    v68 = *(_DWORD *)&v44[v67];
                    if ( v68 == 2 )
                    {
                      if ( v63 == -1 )
                        v63 = v15;
                    }
                    else
                    {
                      if ( !v68 )
                      {
                        if ( v63 != -1 )
                          v15 = v63;
LABEL_21:
                        v16 = 56LL * v15;
                        *(_OWORD *)&v44[v16] = *(_OWORD *)v45;
                        *(_OWORD *)&v44[v16 + 16] = *(_OWORD *)(v45 + 16);
                        *(_OWORD *)&v44[v16 + 32] = *(_OWORD *)(v45 + 32);
                        *(_QWORD *)&v44[v16 + 48] = *(_QWORD *)(v45 + 48);
LABEL_22:
                        if ( ++v17 >= *((_DWORD *)this + 27) )
                        {
LABEL_23:
                          LocalFree(*((HLOCAL *)this + 15));
                          *((_QWORD *)this + 15) = v44;
                          *((_DWORD *)this + 27) = v14;
                          *((_DWORD *)this + 28) = 0;
                          goto LABEL_24;
                        }
                        goto LABEL_34;
                      }
                      if ( v68 == 1 && *(_DWORD *)&v44[v67 + 20] == *(_DWORD *)(v45 + 20) )
                      {
                        v69 = *(_QWORD *)&v44[v67 + 4] - *(_QWORD *)(v45 + 4);
                        if ( !v69 )
                          v69 = *(_QWORD *)&v44[v67 + 12] - *(_QWORD *)(v45 + 12);
                        if ( !v69 )
                          goto LABEL_21;
                      }
                    }
                  }
                }
LABEL_25:
                v18 = *((_DWORD *)this + 27);
                v19 = *((_QWORD *)this + 15);
                _mm_lfence();
                v20 = (LOBYTE(a2->fmtid.Data1) + 694790345)
                    ^ 0x12B9B0A5
                    ^ ((((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5u) >> 2)
                     + 2080 * ((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5)
                     + BYTE1(a2->fmtid.Data1));
                v21 = v20 ^ ((v20 >> 2) + 2080 * v20 + BYTE2(a2->fmtid.Data1));
                v22 = v21 ^ ((v21 >> 2) + 2080 * v21 + HIBYTE(a2->fmtid.Data1));
                v23 = v22 ^ ((v22 >> 2) + 2080 * v22 + LOBYTE(a2->fmtid.Data2));
                v24 = v23 ^ ((v23 >> 2) + 2080 * v23 + HIBYTE(a2->fmtid.Data2));
                v25 = v24 ^ ((v24 >> 2) + 2080 * v24 + LOBYTE(a2->fmtid.Data3));
                v26 = v25 ^ ((v25 >> 2) + 2080 * v25 + HIBYTE(a2->fmtid.Data3));
                v27 = v26 ^ ((v26 >> 2) + 2080 * v26 + a2->fmtid.Data4[0]);
                v28 = v27 ^ ((v27 >> 2) + 2080 * v27 + a2->fmtid.Data4[1]);
                v29 = v28 ^ ((v28 >> 2) + 2080 * v28 + a2->fmtid.Data4[2]);
                v30 = v29 ^ ((v29 >> 2) + 2080 * v29 + a2->fmtid.Data4[3]);
                v31 = v30 ^ ((v30 >> 2) + 2080 * v30 + a2->fmtid.Data4[4]);
                v32 = v31 ^ ((v31 >> 2) + 2080 * v31 + a2->fmtid.Data4[5]);
                v33 = v32 ^ ((v32 >> 2) + 2080 * v32 + a2->fmtid.Data4[6]);
                v34 = v33 ^ ((v33 >> 2) + 2080 * v33 + a2->fmtid.Data4[7]);
                v35 = v34 ^ (LOBYTE(a2->pid) + (v34 >> 2) + 2080 * v34);
                v36 = v35 ^ ((v35 >> 2) + 2080 * v35 + BYTE1(a2->pid));
                v37 = v36 ^ ((v36 >> 2) + 2080 * v36 + BYTE2(a2->pid));
                v38 = v37 ^ ((v37 >> 2) + 2080 * v37 + HIBYTE(a2->pid));
                v39 = -1;
                for ( k = v38 & 0x7FFFFFFF; ; k = v41 + 1 )
                {
                  v41 = k % v18;
                  v42 = 56LL * (k % v18);
                  v43 = *(_DWORD *)(v42 + v19);
                  if ( v43 == 2 )
                  {
                    if ( v39 == -1 )
                      v39 = v41;
                  }
                  else
                  {
                    if ( !v43 )
                    {
                      if ( v39 != -1 )
                        v41 = v39;
LABEL_49:
                      v71 = 56LL * v41;
                      v72 = *(_DWORD *)(v71 + v19);
                      if ( v72 == 1 )
                      {
                        *(_OWORD *)pvar = *(_OWORD *)(v71 + v19 + 24);
                        v110 = *(_OWORD *)(v71 + v19 + 40);
                        v75 = *(_OWORD *)&pvarDest[2];
                        *(_OWORD *)(v71 + v19 + 24) = *(_OWORD *)pvarDest;
                        *(_OWORD *)(v71 + v19 + 40) = v75;
                      }
                      else
                      {
                        if ( v72 == 2 )
                          --*((_DWORD *)this + 28);
                        *(GUID *)(v71 + v19 + 4) = a2->fmtid;
                        *(_DWORD *)(v71 + v19 + 20) = a2->pid;
                        *(_OWORD *)(v71 + v19 + 24) = *(_OWORD *)pvarDest;
                        v73 = *(_OWORD *)&pvarDest[2];
                        *(_DWORD *)(v71 + v19) = 1;
                        *(_OWORD *)(v71 + v19 + 40) = v73;
                        ++*((_DWORD *)this + 26);
                      }
                      v11 = 0;
                      if ( !*v107 )
                        *((_BYTE *)this + 188) = 1;
                      PropVariantClear(&pvar[1]);
                      return (unsigned int)v11;
                    }
                    if ( v43 == 1 && *(_DWORD *)(v42 + v19 + 20) == a2->pid )
                    {
                      v102 = *(_QWORD *)(v42 + v19 + 4) - *(_QWORD *)&a2->fmtid.Data1;
                      if ( !v102 )
                        v102 = *(_QWORD *)(v42 + v19 + 12) - *(_QWORD *)a2->fmtid.Data4;
                      if ( !v102 )
                        goto LABEL_49;
                    }
                  }
                }
              }
              v11 = CSimpleHashTable<_tagpropertykey,CMemPropStore::CACHEDPROPERTY,CDefaultHashPolicy<_tagpropertykey>,CDefaultKeyCompare<_tagpropertykey>,CMemPropStoreResizePolicy,CDefaultRehashPolicy>::_RehashTable(
                      (char *)this + 104,
                      (unsigned int)(2 * v14 - 1));
LABEL_24:
              if ( v11 >= 0 )
                goto LABEL_25;
            }
            if ( !a5 )
              PropVariantClear(&pvarDest[1]);
            return (unsigned int)v11;
          }
LABEL_72:
          if ( !*(_WORD *)a3 )
            goto LABEL_73;
          goto LABEL_9;
        }
        if ( v100 == 1 && *(_DWORD *)(v99 + v76 + 20) == a2->pid )
        {
          v106 = *(_QWORD *)(v99 + v76 + 4) - *(_QWORD *)&a2->fmtid.Data1;
          if ( !v106 )
            v106 = *(_QWORD *)(v99 + v76 + 12) - *(_QWORD *)a2->fmtid.Data4;
          if ( !v106 )
            goto LABEL_79;
        }
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010550  push    rbx
0x180010552  push    rbp
0x180010553  push    rsi
0x180010554  push    rdi
0x180010555  push    r12
0x180010557  push    r13
0x180010559  push    r14
0x18001055b  push    r15
0x18001055d  sub     rsp, 88h
0x180010564  mov     rax, cs:__security_cookie
0x18001056b  xor     rax, rsp
0x18001056e  mov     [rsp+0C8h+var_58], rax
0x180010573  test    byte ptr [rcx+0C0h], 1
0x18001057a  lea     rdi, [rcx+0F0h]
0x180010581  mov     [rsp+0C8h+var_A8], rdi
0x180010586  mov     r14d, r9d
0x180010589  mov     rbx, r8
0x18001058c  mov     r13, rdx
0x18001058f  mov     rbp, rcx
0x180010592  jnz     loc_180010F9A
0x180010598  mov     [rsp+0C8h+var_A8], rdi
0x18001059d  mov     rcx, [rcx+0A8h]; hdsa
0x1800105a4  test    rcx, rcx
0x1800105a7  jnz     loc_180010B92
0x1800105ad  mov     rcx, rbp; this
0x1800105b0  call    ?_EnsureUnserializedInsideLock@CMemPropStore@@AEAAJXZ; CMemPropStore::_EnsureUnserializedInsideLock(void)
0x1800105b5  mov     esi, eax
0x1800105b7  test    eax, eax
0x1800105b9  js      loc_180010C33
0x1800105bf  test    rbx, rbx
0x1800105c2  jz      loc_180010F00
0x1800105c8  cmp     byte ptr [rdi], 0
0x1800105cb  jnz     loc_180010C84
0x1800105d1  test    byte ptr [rbp+0B8h], 2
0x1800105d8  jnz     loc_180010C84
0x1800105de  cmp     [rsp+0C8h+arg_20], 0
0x1800105e6  xorps   xmm0, xmm0
0x1800105e9  movups  xmmword ptr [rsp+0C8h+pvarDest], xmm0
0x1800105ee  movups  [rsp+0C8h+var_88], xmm0
0x1800105f3  jnz     loc_180010BA8
0x1800105f9  mov     rdx, rbx; pvarSrc
0x1800105fc  lea     rcx, [rsp+0C8h+pvarDest+8]; pvarDest
0x180010601  call    cs:__imp_PropVariantCopy
0x180010607  mov     esi, eax
0x180010609  test    eax, eax
0x18001060b  js      loc_180010C33
0x180010611  cmp     qword ptr [rbp+78h], 0
0x180010616  xorps   xmm0, xmm0
0x180010619  movups  xmmword ptr [rsp+0C8h+pvar], xmm0
0x18001061e  mov     dword ptr [rsp+0C8h+pvarDest], r14d
0x180010623  mov     ebx, 8007000Eh
0x180010628  movups  [rsp+0C8h+var_68], xmm0
0x18001062d  jnz     short loc_180010661
0x18001062f  mov     ecx, [rbp+6Ch]
0x180010632  mov     eax, 38h ; '8'
0x180010637  mul     rcx
0x18001063a  mov     qword ptr [rbp+78h], 0
0x180010642  mov     [rsp+0C8h+var_A0], 0
0x18001064b  test    rdx, rdx
0x18001064e  jz      loc_180010E94
0x180010654  mov     esi, 80070216h
0x180010659  test    esi, esi
0x18001065b  js      loc_180010FD1
0x180010661  mov     edi, [rbp+6Ch]
0x180010664  lea     r12, [rbp+6Ch]
0x180010668  mov     eax, [rbp+68h]
0x18001066b  lea     edx, ds:0[rdi*4]
0x180010672  lea     ecx, [rax+rax*4]
0x180010675  cmp     ecx, edx
0x180010677  ja      loc_180010B7B
0x18001067d  mov     ecx, edi
0x18001067f  shr     ecx, 2
0x180010682  cmp     [rbp+70h], ecx
0x180010685  jbe     loc_18001070F
0x18001068b  mov     eax, 38h ; '8'
0x180010690  mov     [rsp+0C8h+var_A0], 0
0x180010699  mul     rdi
0x18001069c  test    rdx, rdx
0x18001069f  jz      loc_180010916
0x1800106a5  mov     esi, 80070216h
0x1800106aa  jmp     short loc_180010707
0x1800106ac  cmp     r8d, 0FFFFFFFFh
0x1800106b0  cmovnz  edx, r8d
0x1800106b4  movups  xmm0, xmmword ptr [r9]
0x1800106b8  mov     eax, edx
0x1800106ba  imul    rcx, rax, 38h ; '8'
0x1800106be  movups  xmmword ptr [rcx+rbx], xmm0
0x1800106c2  movups  xmm1, xmmword ptr [r9+10h]
0x1800106c7  movups  xmmword ptr [rcx+rbx+10h], xmm1
0x1800106cc  movups  xmm0, xmmword ptr [r9+20h]
0x1800106d1  movups  xmmword ptr [rcx+rbx+20h], xmm0
0x1800106d6  movsd   xmm1, qword ptr [r9+30h]
0x1800106dc  movsd   qword ptr [rcx+rbx+30h], xmm1
0x1800106e2  inc     r10d
0x1800106e5  cmp     r10d, [rbp+6Ch]
0x1800106e9  jb      loc_180010950
0x1800106ef  mov     rcx, [rbp+78h]; hMem
0x1800106f3  call    cs:__imp_LocalFree
0x1800106f9  mov     [rbp+78h], rbx
0x1800106fd  mov     [rbp+6Ch], edi
0x180010700  mov     dword ptr [rbp+70h], 0
0x180010707  test    esi, esi
0x180010709  js      loc_180010FD1
0x18001070f  mov     r10d, [rbp+6Ch]
0x180010713  mov     r9, [rbp+78h]
0x180010717  lfence
0x18001071a  movzx   ecx, byte ptr [r13+0]
0x18001071f  movzx   edx, byte ptr [r13+1]
0x180010724  add     ecx, 2969A8C9h
0x18001072a  xor     ecx, 12B9B0A5h
0x180010730  imul    eax, ecx, 820h
0x180010736  add     edx, eax
0x180010738  mov     eax, ecx
0x18001073a  shr     eax, 2
0x18001073d  add     edx, eax
0x18001073f  xor     edx, ecx
0x180010741  movzx   ecx, byte ptr [r13+2]
0x180010746  imul    eax, edx, 820h
0x18001074c  add     ecx, eax
0x18001074e  mov     eax, edx
0x180010750  shr     eax, 2
0x180010753  add     ecx, eax
0x180010755  xor     ecx, edx
0x180010757  movzx   edx, byte ptr [r13+3]
0x18001075c  imul    eax, ecx, 820h
0x180010762  add     edx, eax
0x180010764  mov     eax, ecx
0x180010766  shr     eax, 2
0x180010769  add     edx, eax
0x18001076b  xor     edx, ecx
0x18001076d  movzx   ecx, byte ptr [r13+4]
0x180010772  imul    eax, edx, 820h
0x180010778  add     ecx, eax
0x18001077a  mov     eax, edx
0x18001077c  shr     eax, 2
0x18001077f  add     ecx, eax
0x180010781  xor     ecx, edx
0x180010783  movzx   edx, byte ptr [r13+5]
0x180010788  imul    eax, ecx, 820h
0x18001078e  add     edx, eax
0x180010790  mov     eax, ecx
0x180010792  shr     eax, 2
0x180010795  add     edx, eax
0x180010797  xor     edx, ecx
0x180010799  movzx   ecx, byte ptr [r13+6]
0x18001079e  imul    eax, edx, 820h
0x1800107a4  add     ecx, eax
0x1800107a6  mov     eax, edx
0x1800107a8  shr     eax, 2
0x1800107ab  add     ecx, eax
0x1800107ad  xor     ecx, edx
0x1800107af  movzx   edx, byte ptr [r13+7]
0x1800107b4  imul    eax, ecx, 820h
0x1800107ba  add     edx, eax
0x1800107bc  mov     eax, ecx
0x1800107be  shr     eax, 2
0x1800107c1  add     edx, eax
0x1800107c3  xor     edx, ecx
0x1800107c5  movzx   ecx, byte ptr [r13+8]
0x1800107ca  imul    eax, edx, 820h
0x1800107d0  add     ecx, eax
0x1800107d2  mov     eax, edx
0x1800107d4  shr     eax, 2
0x1800107d7  add     ecx, eax
0x1800107d9  xor     ecx, edx
0x1800107db  movzx   edx, byte ptr [r13+9]
0x1800107e0  imul    eax, ecx, 820h
0x1800107e6  add     edx, eax
0x1800107e8  mov     eax, ecx
0x1800107ea  shr     eax, 2
0x1800107ed  add     edx, eax
0x1800107ef  xor     edx, ecx
0x1800107f1  movzx   ecx, byte ptr [r13+0Ah]
0x1800107f6  imul    eax, edx, 820h
0x1800107fc  add     ecx, eax
0x1800107fe  mov     eax, edx
0x180010800  shr     eax, 2
0x180010803  add     ecx, eax
0x180010805  xor     ecx, edx
0x180010807  movzx   edx, byte ptr [r13+0Bh]
0x18001080c  imul    eax, ecx, 820h
0x180010812  add     edx, eax
0x180010814  mov     eax, ecx
0x180010816  shr     eax, 2
0x180010819  add     edx, eax
0x18001081b  xor     edx, ecx
0x18001081d  movzx   ecx, byte ptr [r13+0Ch]
0x180010822  movzx   r8d, byte ptr [r13+12h]
0x180010827  imul    eax, edx, 820h
0x18001082d  add     ecx, eax
0x18001082f  mov     eax, edx
0x180010831  shr     eax, 2
0x180010834  add     ecx, eax
0x180010836  xor     ecx, edx
0x180010838  movzx   edx, byte ptr [r13+0Dh]
0x18001083d  imul    eax, ecx, 820h
0x180010843  add     edx, eax
0x180010845  mov     eax, ecx
0x180010847  shr     eax, 2
0x18001084a  add     edx, eax
0x18001084c  xor     edx, ecx
0x18001084e  movzx   ecx, byte ptr [r13+0Eh]
0x180010853  imul    eax, edx, 820h
0x180010859  add     ecx, eax
0x18001085b  mov     eax, edx
0x18001085d  shr     eax, 2
0x180010860  add     ecx, eax
0x180010862  xor     ecx, edx
0x180010864  movzx   edx, byte ptr [r13+0Fh]
0x180010869  imul    eax, ecx, 820h
0x18001086f  add     edx, eax
0x180010871  mov     eax, ecx
0x180010873  shr     eax, 2
0x180010876  add     edx, eax
0x180010878  xor     edx, ecx
0x18001087a  imul    ecx, edx, 820h
0x180010880  mov     eax, edx
0x180010882  shr     eax, 2
0x180010885  add     ecx, eax
0x180010887  movzx   eax, byte ptr [r13+10h]
0x18001088c  add     ecx, eax
0x18001088e  xor     ecx, edx
0x180010890  movzx   edx, byte ptr [r13+11h]
0x180010895  imul    eax, ecx, 820h
0x18001089b  add     edx, eax
0x18001089d  mov     eax, ecx
0x18001089f  shr     eax, 2
0x1800108a2  add     edx, eax
0x1800108a4  xor     edx, ecx
0x1800108a6  imul    eax, edx, 820h
0x1800108ac  add     r8d, eax
0x1800108af  mov     eax, edx
0x1800108b1  shr     eax, 2
0x1800108b4  add     r8d, eax
0x1800108b7  movzx   eax, byte ptr [r13+13h]
0x1800108bc  xor     r8d, edx
0x1800108bf  imul    ecx, r8d, 820h
0x1800108c6  add     eax, ecx
0x1800108c8  mov     ecx, r8d
0x1800108cb  shr     ecx, 2
0x1800108ce  add     eax, ecx
0x1800108d0  xor     eax, r8d
0x1800108d3  mov     r8d, 0FFFFFFFFh
0x1800108d9  btr     eax, 1Fh
0x1800108dd  xor     edx, edx
0x1800108df  div     r10d
0x1800108e2  mov     eax, edx
0x1800108e4  imul    rcx, rax, 38h ; '8'
0x1800108e8  mov     eax, [rcx+r9]
0x1800108ec  cmp     eax, 2
0x1800108ef  jz      loc_180010FEF
0x1800108f5  test    eax, eax
0x1800108f7  jz      loc_180010BC0
0x1800108fd  cmp     eax, 1
0x180010900  jnz     short loc_180010911
0x180010902  mov     eax, [r13+10h]
0x180010906  cmp     [rcx+r9+14h], eax
0x18001090b  jz      loc_180010EB3
0x180010911  lea     eax, [rdx+1]
0x180010914  jmp     short loc_1800108DD
0x180010916  mov     rdx, rax; uBytes
0x180010919  mov     ecx, 40h ; '@'; uFlags
0x18001091e  call    cs:__imp_LocalAlloc
0x180010924  xor     esi, esi
0x180010926  mov     rbx, rax
0x180010929  test    rax, rax
0x18001092c  mov     eax, 8007000Eh
0x180010931  cmovz   esi, eax
0x180010934  test    rbx, rbx
0x180010937  jz      loc_180010707
0x18001093d  xor     r10d, r10d
0x180010940  cmp     [r12], r10d
0x180010944  jbe     loc_1800106EF
0x18001094a  nop     word ptr [rax+rax+00h]
0x180010950  mov     eax, r10d
0x180010953  imul    r9, rax, 38h ; '8'
0x180010957  add     r9, [rbp+78h]
0x18001095b  cmp     dword ptr [r9], 1
0x18001095f  jnz     loc_1800106E2
0x180010965  lfence
0x180010968  movzx   ecx, byte ptr [r9+4]
0x18001096d  movzx   edx, byte ptr [r9+5]
0x180010972  add     ecx, 2969A8C9h
0x180010978  xor     ecx, 12B9B0A5h
0x18001097e  imul    eax, ecx, 820h
0x180010984  add     edx, eax
0x180010986  mov     eax, ecx
0x180010988  shr     eax, 2
0x18001098b  add     edx, eax
0x18001098d  xor     edx, ecx
0x18001098f  movzx   ecx, byte ptr [r9+6]
0x180010994  imul    eax, edx, 820h
0x18001099a  add     ecx, eax
0x18001099c  mov     eax, edx
0x18001099e  shr     eax, 2
0x1800109a1  add     ecx, eax
0x1800109a3  xor     ecx, edx
0x1800109a5  movzx   edx, byte ptr [r9+7]
0x1800109aa  imul    eax, ecx, 820h
0x1800109b0  add     edx, eax
  ... truncated ...
```
