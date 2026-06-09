# CPropertySetStream::_FixPackedPropertySet(long *)

- ea: `0x180029f04`
- end: `0x18002aa99`
- name: `?_FixPackedPropertySet@CPropertySetStream@@AEAAXPEAJ@Z`
- size: `2965`
- prototype: `void __fastcall(CPropertySetStream *__hidden this, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800290b8`

## callees

- `0x180027488`
- `0x180029040`
- `0x180029dec`
- `0x180029f04`
- `0x18002abf4`
- `0x18002aca0`
- `0x18002faa0`
- `0x180034f64`
- `0x180042800`
- `0x180043100`
- `0x18005ab40`
- `0x18006141c`
- `0x180061428`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002a18b`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002a18b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a1b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a6bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a84a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a1b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a6bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a84a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a603`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a74b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a0f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a603`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a74b`

## pseudocode

```c
void __fastcall CPropertySetStream::_FixPackedPropertySet(CPropertySetStream *this, int *a2)
{
  int v2; // r13d
  __int64 v5; // rsi
  _QWORD *v6; // r15
  __int64 v7; // r14
  int *v8; // r12
  __int64 v9; // rcx
  unsigned int v10; // eax
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // eax
  unsigned int v14; // edx
  unsigned __int64 v15; // rsi
  __int64 v16; // r14
  struct tagPROPERTYIDOFFSET *v17; // r14
  unsigned int v18; // eax
  bool v19; // sf
  unsigned __int64 i; // rcx
  _DWORD *v21; // r15
  unsigned int v22; // ecx
  __int64 v23; // rax
  char *v24; // rsi
  unsigned __int64 v25; // rax
  char *v26; // rax
  char *v27; // r14
  size_t v28; // rdx
  unsigned int v29; // eax
  unsigned __int64 v30; // rax
  unsigned int v31; // esi
  _DWORD *v32; // rax
  _DWORD *v33; // r9
  unsigned int v34; // r13d
  char *v35; // rcx
  void *v36; // r10
  int v37; // eax
  _DWORD *v38; // rcx
  char *v39; // r8
  int v40; // ecx
  int v41; // eax
  __int64 v42; // rdx
  unsigned int v43; // esi
  struct tagSERIALIZEDPROPERTYVALUE *v44; // r15
  char v45; // r14
  int v46; // esi
  unsigned int v47; // r13d
  unsigned int v48; // ecx
  char *v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rsi
  _DWORD *v52; // r8
  struct tagSERIALIZEDPROPERTYVALUE *v53; // rdx
  unsigned int v54; // r14d
  unsigned int v55; // r9d
  int v56; // ecx
  _DWORD *v57; // rdx
  int v58; // r14d
  char *v59; // r13
  unsigned int v60; // r12d
  int v61; // esi
  struct tagPROPERTYSECTIONHEADER *v62; // r15
  int v63; // esi
  _DWORD *v64; // r9
  unsigned __int64 v65; // rax
  struct tagPROPERTYIDOFFSET *k; // rdx
  char *m; // rcx
  unsigned int v68; // esi
  __int64 v69; // rsi
  char v70; // r15
  size_t v71; // r8
  int v72; // ecx
  unsigned int v73; // eax
  _DWORD *v74; // r10
  struct tagSERIALIZEDPROPERTYVALUE *v75; // r8
  unsigned int v76; // r9d
  unsigned int v77; // r15d
  int v78; // edx
  int v79; // ecx
  __int64 v80; // r14
  int *v81; // r12
  char *v82; // rbx
  int *v83; // rsi
  _DWORD *v84; // rax
  __int64 v85; // rdx
  unsigned int *v86; // r13
  unsigned int v87; // eax
  bool v88; // zf
  unsigned int v89; // eax
  __int64 v90; // r8
  __int64 v91; // r9
  struct tagSERIALIZEDPROPERTYVALUE *v92; // rdx
  unsigned int v93; // eax
  int *v94; // r14
  char *j; // r13
  __int64 v96; // rax
  unsigned int v97; // ecx
  unsigned int v98; // eax
  signed int v99; // ebx
  char *pv; // [rsp+40h] [rbp-C0h]
  unsigned int v101; // [rsp+48h] [rbp-B8h]
  int v102; // [rsp+4Ch] [rbp-B4h]
  int v103; // [rsp+50h] [rbp-B0h]
  unsigned int v104; // [rsp+54h] [rbp-ACh]
  int v105; // [rsp+54h] [rbp-ACh]
  unsigned int v106; // [rsp+58h] [rbp-A8h] BYREF
  struct tagPROPERTYSECTIONHEADER *v107; // [rsp+60h] [rbp-A0h] BYREF
  int v108; // [rsp+68h] [rbp-98h] BYREF
  char *v109; // [rsp+70h] [rbp-90h]
  LPVOID v110; // [rsp+78h] [rbp-88h]
  LPVOID v111; // [rsp+80h] [rbp-80h]
  LPVOID v112; // [rsp+88h] [rbp-78h]
  int v113; // [rsp+90h] [rbp-70h]
  char *v114; // [rsp+98h] [rbp-68h]
  char *v115; // [rsp+A0h] [rbp-60h]
  struct tagPROPERTYIDOFFSET *v116; // [rsp+A8h] [rbp-58h] BYREF
  int *v117; // [rsp+B0h] [rbp-50h]
  struct tagPROPERTYIDOFFSET *v118; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v119; // [rsp+C0h] [rbp-40h]
  struct tagSERIALIZEDPROPERTYVALUE *v120; // [rsp+C8h] [rbp-38h]
  __int64 v121; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v122; // [rsp+D8h] [rbp-28h]
  _BYTE v123[344]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v124; // [rsp+238h] [rbp+138h]
  __int64 v125; // [rsp+240h] [rbp+140h]

  *a2 = 0;
  pv = 0;
  LOBYTE(v2) = *((_BYTE *)this + 19) & 0x18;
  v111 = 0;
  v110 = 0;
  v112 = 0;
  v113 = v2;
  if ( !*((_DWORD *)this + 3) )
    goto LABEL_111;
  v5 = *((int *)this + 2);
  v6 = (_QWORD *)((char *)this + 40);
  v7 = *(_QWORD *)this;
  v108 = 0;
  v8 = 0;
  v9 = *((_QWORD *)this + 5);
  v114 = (char *)this + 40;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 72LL))(v9, &v108);
  v11 = v108;
  if ( v108 >= 0 )
  {
    v12 = *(_DWORD *)(v7 + v5);
    if ( v12 > v10 || *((_DWORD *)this + 2) + v12 > v10 )
    {
      v11 = -1073741596;
      v108 = -1073741596;
    }
    if ( v11 >= 0 )
      v8 = (int *)(v7 + v5);
  }
  *a2 = v11;
  if ( v11 < 0 )
    goto LABEL_30;
  v13 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v6 + 72LL))(*v6, a2);
  if ( *a2 < 0 )
    goto LABEL_30;
  v14 = *((_DWORD *)this + 2);
  if ( v13 < v14 )
    goto LABEL_111;
  if ( v13 < v14 + 8 )
    goto LABEL_111;
  if ( v8[1] > (v13 - v14 - 8) >> 3 )
    goto LABEL_111;
  v15 = (unsigned __int64)(v8 + 2);
  v16 = (unsigned int)v8[1] + 1LL;
  v118 = (struct tagPROPERTYIDOFFSET *)(v8 + 2);
  v17 = (struct tagPROPERTYIDOFFSET *)&v8[2 * v16];
  v116 = v17;
  if ( !v8 )
    goto LABEL_111;
  v18 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v6 + 72LL))(*v6, a2);
  v19 = *a2 < 0;
  v106 = v18;
  if ( v19 )
    goto LABEL_30;
  for ( i = (unsigned __int64)(v8 + 2); i < (unsigned __int64)v17; i += 8LL )
  {
    if ( *(_DWORD *)(i + 4) >= (unsigned int)*v8 )
      goto LABEL_111;
  }
  *a2 = 0;
  if ( (*(_BYTE *)v8 & 3) != 0 )
  {
    v114 = (char *)this + 40;
    v21 = v8;
LABEL_25:
    *((_BYTE *)this + 19) |= 4u;
  }
  else
  {
    v21 = v8;
    while ( v15 < (unsigned __int64)v17 )
    {
      if ( (*(_BYTE *)(v15 + 4) & 3) != 0
        || (_BYTE)v2 == 8 && *((_WORD *)this + 8) != 1200 && (unsigned int)(*(_DWORD *)v15 - 12) <= 1 )
      {
        goto LABEL_25;
      }
      v15 += 8LL;
    }
  }
  v22 = v21[1];
  if ( v22 > 0x200000 || v22 > *v21 >> 3 )
  {
LABEL_111:
    *a2 = -1073741596;
    goto LABEL_30;
  }
  v23 = v22 + 1;
  if ( (unsigned int)v23 < v22 || (v25 = 8 * v23, v25 > 0xFFFFFFFF) )
  {
    *a2 = -1073741675;
    goto LABEL_30;
  }
  v26 = (char *)CoTaskMemAlloc((unsigned int)v25);
  pv = v26;
  v24 = v26;
  if ( !v26 )
    goto LABEL_150;
  memcpy_0(v26, v21 + 2, 8LL * (unsigned int)v21[1]);
  v119 = (unsigned int)v21[1];
  v27 = &v24[8 * v119];
  *(_DWORD *)v27 = -1;
  *((_DWORD *)v27 + 1) = *v21;
  v28 = (unsigned int)v21[1];
  v109 = v27;
  qsort(v24, v28, 8u, fnOffsetCompare);
  v29 = v21[1];
  if ( v29 + 1 < v29 || (v30 = 4LL * (v29 + 1), v30 > 0xFFFFFFFF) )
  {
LABEL_35:
    *a2 = -1073741675;
    goto LABEL_31;
  }
  v31 = v30;
  v111 = CoTaskMemAlloc((unsigned int)v30);
  if ( !v111 )
  {
    *a2 = -1073741801;
    goto LABEL_30;
  }
  v32 = CoTaskMemAlloc(v31);
  v24 = pv;
  v33 = v32;
  v110 = v32;
  if ( !v32 )
    goto LABEL_150;
  v34 = 0;
  v35 = pv;
  v104 = 0;
  if ( pv >= v27 )
  {
    v36 = 0;
    goto LABEL_44;
  }
  do
  {
    if ( (v35[4] & 3) != 0 && v34 < ((*((_DWORD *)v35 + 3) - *((_DWORD *)v35 + 1) + 3) & 0xFFFFFFFC) )
      v34 = (*((_DWORD *)v35 + 3) - *((_DWORD *)v35 + 1) + 3) & 0xFFFFFFFC;
    v35 += 8;
  }
  while ( v35 < v27 );
  v104 = v34;
  if ( v34 )
  {
    v89 = v34 + 4;
    if ( v34 + 4 >= v34 )
    {
      v34 += 4;
      v104 = v89;
      v112 = CoTaskMemAlloc(v89);
      v36 = v112;
      if ( v112 )
      {
        v33 = v110;
        goto LABEL_44;
      }
LABEL_150:
      *a2 = -1073741801;
      goto LABEL_31;
    }
    goto LABEL_35;
  }
  v36 = v112;
LABEL_44:
  v37 = *((_DWORD *)pv + 1);
  v38 = v111;
  v39 = pv;
  *v33 = v37;
  v115 = pv;
  v117 = (int *)((char *)this + 8);
  *v38 = v37;
  v40 = 0;
  v41 = 0;
  v103 = 0;
  v102 = 0;
  while ( v39 < v27 )
  {
    v42 = *((int *)v39 + 1);
    if ( (unsigned int)v42 >= *v21 )
      goto LABEL_111;
    v43 = *((_DWORD *)v39 + 3) - v42;
    v101 = v43;
    v44 = (struct tagSERIALIZEDPROPERTYVALUE *)(*(_QWORD *)this + v42 + *((int *)this + 2));
    v45 = 0;
    v117 = (int *)((char *)this + 8);
    v120 = v44;
    if ( (v42 & 3) != 0 )
    {
      memset_0(v36, 0, v34);
      v90 = 4 - (*((_DWORD *)v115 + 1) & 3u);
      v91 = *(_QWORD *)this + *((int *)v115 + 1) + *v117;
      if ( v90 + v91 + (unsigned __int64)v43 > *(_QWORD *)this + (unsigned __int64)v106 )
        LODWORD(v90) = v106 + *(_DWORD *)this - v91 - v43;
      v92 = v44;
      v44 = (struct tagSERIALIZEDPROPERTYVALUE *)v112;
      memcpy_0(v112, v92, v43 + (unsigned int)v90);
      v39 = v115;
      v120 = v44;
    }
    if ( !*(_DWORD *)v39 )
    {
      v73 = CPropertySetStream::_DictionaryLength(this, (const struct tagDICTIONARY *)v44, v43, a2);
      if ( *a2 < 0 )
        goto LABEL_30;
      v47 = (v73 + 3) & 0xFFFFFFFC;
      goto LABEL_54;
    }
    if ( (_BYTE)v113 == 8 && *((_WORD *)this + 8) != 1200 )
    {
      v47 = v43;
      if ( *(_DWORD *)v39 == 12 )
      {
        if ( v43 >= 8 )
        {
          if ( v44->dwType != 4108 )
            goto LABEL_104;
          v68 = *(_DWORD *)v44->rgb;
          if ( (v68 & 1) != 0 )
            goto LABEL_104;
          v69 = v68 >> 1;
          if ( (_DWORD)v69 )
          {
            if ( 4 * (unsigned __int64)(unsigned int)v69 > 0xFFFFFFFF )
              goto LABEL_104;
            v74 = CoTaskMemAlloc((unsigned int)(4 * v69));
            if ( !v74 )
              goto LABEL_104;
            v75 = v44 + 1;
            v76 = v69;
            v77 = v47 - 8;
            while ( (_DWORD)v69 )
            {
              if ( v77 < 8 )
                goto LABEL_132;
              if ( v75->dwType != 30 )
                goto LABEL_132;
              v78 = *(_DWORD *)v75->rgb + 8;
              if ( v77 < v78
                || v77 < (unsigned __int64)(unsigned int)(*(_DWORD *)v75->rgb + 12) + 4
                || *(DWORD *)((char *)&v75->dwType + v78) != 3 )
              {
                goto LABEL_132;
              }
              v69 = (unsigned int)(v69 - 1);
              v77 -= *(_DWORD *)v75->rgb + 16;
              v75 = (struct tagSERIALIZEDPROPERTYVALUE *)((char *)v75 + *(_DWORD *)v75->rgb + 16);
              v74[v69] = v78 + 8;
            }
            v77 = 0;
            v45 = 1;
            do
            {
              v79 = v74[v69];
              v69 = (unsigned int)(v69 + 1);
              v77 += (v79 + 3) & 0xFFFFFFFC;
            }
            while ( (unsigned int)v69 < v76 );
LABEL_132:
            CoTaskMemFree(v74);
            if ( !v45 )
              goto LABEL_104;
          }
          else
          {
            v77 = 0;
          }
          v47 = v77 + 8;
LABEL_108:
          v45 = 1;
        }
LABEL_109:
        v43 = v101;
        if ( v45 )
          goto LABEL_54;
        goto LABEL_50;
      }
      if ( *(_DWORD *)v39 == 13 )
      {
        if ( v43 >= 8 )
        {
          if ( v44->dwType == 4126 )
          {
            v51 = *(unsigned int *)v44->rgb;
            v107 = 0;
            if ( (int)CPropertySetStream::_GetAndValidateSectionHeader(this, &v107) >= 0 )
            {
              if ( !(_DWORD)v51 )
              {
                v54 = 0;
                goto LABEL_107;
              }
              if ( 4 * (unsigned __int64)(unsigned int)v51 <= 0xFFFFFFFF )
              {
                v52 = CoTaskMemAlloc((unsigned int)(4 * v51));
                if ( v52 )
                {
                  v53 = v44 + 1;
                  v54 = v47 - 8;
                  v55 = v51;
                  while ( (_DWORD)v51 )
                  {
                    if ( v54 < 4 || (v56 = v53->dwType + 4, v54 < v56) )
                    {
                      v70 = 0;
                      goto LABEL_106;
                    }
                    v54 -= v56;
                    v51 = (unsigned int)(v51 - 1);
                    v53 = (struct tagSERIALIZEDPROPERTYVALUE *)((char *)v53 + v56);
                    v52[v51] = v56;
                  }
                  v54 = 0;
                  v70 = 1;
                  do
                  {
                    v72 = v52[v51];
                    v51 = (unsigned int)(v51 + 1);
                    v54 += (v72 + 3) & 0xFFFFFFFC;
                  }
                  while ( (unsigned int)v51 < v55 );
LABEL_106:
                  CoTaskMemFree(v52);
                  if ( v70 )
                  {
LABEL_107:
                    v47 = v54 + 8;
                    goto LABEL_108;
                  }
                }
              }
            }
          }
LABEL_104:
          v45 = 0;
        }
        goto LABEL_109;
      }
    }
LABEL_50:
    LODWORD(v107) = 0;
    v122 = 4;
    v121 = 0;
    v125 = 0;
    memset_0(v123, 0, sizeof(v123));
    v124 = v123;
    if ( (v122 & 2) == 0 || v121 )
      v46 = DeserializeHelper::Worker(
              (DeserializeHelper *)&v121,
              v120,
              (v43 + 3) & 0xFFFFFFFC,
              0,
              0,
              0,
              0,
              (unsigned int *)&v107);
    else
      v46 = -1073741811;
    CleanupStack::Done((CleanupStack *)v123, v46);
    if ( v46 < 0 )
    {
      if ( (v122 & 2) != 0 )
      {
        MEMORY[0] = 0;
        MEMORY[0x10] = 0;
      }
      LODWORD(v107) = 0;
      *a2 = v46;
      goto LABEL_30;
    }
    v47 = (unsigned int)v107;
    *a2 = v46;
    v43 = v101;
LABEL_54:
    v48 = v43;
    v49 = v115;
    v50 = (v115 - pv) >> 3;
    if ( v47 < v43 )
      v48 = v47;
    *((_DWORD *)v111 + v50 + 1) = *((_DWORD *)v111 + v50) + v48;
    v33 = v110;
    *((_DWORD *)v110 + v50 + 1) = v47 + *((_DWORD *)v110 + v50);
    if ( v47 < v43 )
    {
      v41 = ++v102;
      goto LABEL_60;
    }
    if ( v47 <= v43 && !v45 )
    {
      v41 = v102;
LABEL_60:
      v40 = v103;
      goto LABEL_61;
    }
    v41 = v102;
    v40 = ++v103;
LABEL_61:
    v34 = v104;
    v39 = v49 + 8;
    v27 = v109;
    v21 = v8;
    v36 = v112;
    v115 = v39;
  }
  if ( v40 )
  {
    v57 = v117;
  }
  else
  {
    if ( !v41 )
      goto LABEL_30;
    v57 = (_DWORD *)((char *)this + 8);
  }
  v58 = *v8;
  v59 = v114;
  v60 = *v57 + *v8 + *((_DWORD *)this + 7);
  v61 = v33[v21[1]];
  LODWORD(v107) = v60;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, CPropertySetStream *, int *))(**(_QWORD **)v114 + 80LL))(
    *(_QWORD *)v114,
    v60,
    0,
    this,
    a2);
  if ( *a2 >= 0 )
  {
    v62 = CPropertySetStream::_LoadPropertyOffsetPointers(this, &v118, &v116, a2);
    if ( *a2 >= 0 )
    {
      v63 = v61 - v58;
      v105 = v63;
      if ( v63 > 0 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, CPropertySetStream *, int *))(**(_QWORD **)v59 + 80LL))(
          *(_QWORD *)v59,
          v63 + v60,
          0,
          this,
          a2);
        if ( *a2 < 0 )
          goto LABEL_30;
        v62 = CPropertySetStream::_LoadPropertyOffsetPointers(this, &v118, &v116, a2);
        if ( *a2 < 0 )
          goto LABEL_30;
        v93 = *((_DWORD *)this + 7);
        if ( v93 )
          memmove_0(
            (void *)(*(_QWORD *)this + (int)(v60 - v93) + v63),
            (const void *)(*(_QWORD *)this + (int)(v60 - v93)),
            v93);
      }
      if ( v102 )
      {
        v94 = (int *)v111;
        for ( j = pv; j < v109; j += 8 )
        {
          v96 = *v94++;
          if ( (_DWORD)v96 != *((_DWORD *)j + 1) )
          {
            if ( *v94 <= (unsigned int)v96 )
            {
              *a2 = -2147418113;
              goto LABEL_30;
            }
            memmove_0((char *)v62 + v96, (char *)v62 + *((int *)j + 1), (unsigned int)(*v94 - v96));
          }
        }
      }
      v64 = v110;
      if ( v103 )
      {
        v80 = (unsigned int)(v119 - 1);
        v81 = (int *)((char *)v110 + 4 * (unsigned int)(*((_DWORD *)v62 + 1) - 1));
        v65 = (unsigned __int64)v109;
        v82 = v109 - 8;
        v114 = v109 - 8;
        if ( (int)v119 - 1 >= 0 )
        {
          v83 = (int *)v111;
          do
          {
            v84 = v81 + 1;
            v85 = v83[v80];
            v86 = (unsigned int *)((char *)v62 + *v81);
            v119 = (unsigned __int64)(v81 + 1);
            if ( *v81 != (_DWORD)v85 )
            {
              v97 = *v84 - *v81;
              v98 = v83[v80 + 1] - v85;
              if ( v97 <= v98 )
                v98 = v97;
              v99 = v98;
              memmove_0(v86, (char *)v62 + v85, v98);
              memset_0((char *)v86 + v99, 0, -v99 & 3);
              v84 = (_DWORD *)v119;
              v82 = v114;
            }
            if ( (_BYTE)v113 == 8 && *((_WORD *)this + 8) != 1200 )
            {
              v87 = *v84 - *v81;
              v88 = *(_DWORD *)v82 == 12;
              v106 = v87;
              if ( v88 )
              {
                CPropertySetStream::_FixHeadingPairVector(this, 2, v86, &v106);
              }
              else if ( *(_DWORD *)v82 == 13 && v87 >= 8 )
              {
                v88 = *v86 == 4126;
                v106 = v87 - 8;
                if ( v88 )
                  CPropertySetStream::_FixDocPartsElements(this, 2, v86[1]);
              }
            }
            v82 -= 8;
            --v81;
            v80 = (unsigned int)(v80 - 1);
            v114 = v82;
          }
          while ( (int)v80 >= 0 );
          v63 = v105;
          v60 = (unsigned int)v107;
          v64 = v110;
          goto LABEL_89;
        }
        v60 = (unsigned int)v107;
      }
      else
      {
LABEL_89:
        v65 = (unsigned __int64)v109;
      }
      *(_DWORD *)v62 += v63;
      for ( k = v118; k < v116; k = (struct tagPROPERTYIDOFFSET *)((char *)k + 8) )
      {
        for ( m = pv; (unsigned __int64)m < v65; m += 8 )
        {
          if ( *(_DWORD *)k == *(_DWORD *)m )
          {
            *((_DWORD *)k + 1) = v64[(m - pv) >> 3];
            v65 = (unsigned __int64)v109;
            break;
          }
          v65 = (unsigned __int64)v109;
        }
      }
      v71 = *((unsigned int *)this + 7);
      if ( (_DWORD)v71 )
      {
        if ( v63 < 0 )
          memmove_0(
            (void *)(*(_QWORD *)this + (int)(v60 - v71) + v63),
            (const void *)(*(_QWORD *)this + (int)(v60 - v71)),
            v71);
        CPropertySetStream::_PatchSectionOffsets(this, v63);
      }
      *((_BYTE *)this + 19) &= ~4u;
    }
  }
LABEL_30:
  v24 = pv;
LABEL_31:
  CoTaskMemFree(v24);
  CoTaskMemFree(v111);
  CoTaskMemFree(v110);
  CoTaskMemFree(v112);
}

```

## disassembly

```asm
0x180029f04  mov     [rsp-8+arg_10], rbx
0x180029f09  push    rbp
0x180029f0a  push    rsi
0x180029f0b  push    rdi
0x180029f0c  push    r12
0x180029f0e  push    r13
0x180029f10  push    r14
0x180029f12  push    r15
0x180029f14  lea     rbp, [rsp-170h]
0x180029f1c  sub     rsp, 270h
0x180029f23  mov     rax, cs:__security_cookie
0x180029f2a  xor     rax, rsp
0x180029f2d  mov     [rbp+1A0h+var_40], rax
0x180029f34  mov     rdi, rcx
0x180029f37  mov     rbx, rdx
0x180029f3a  xor     ecx, ecx
0x180029f3c  mov     [rdx], ecx
0x180029f3e  mov     [rsp+2A0h+pv], rcx
0x180029f43  mov     r13b, [rdi+13h]
0x180029f47  and     r13b, 18h
0x180029f4b  mov     [rbp+1A0h+var_220], rcx
0x180029f4f  mov     [rsp+2A0h+var_228], rcx
0x180029f54  mov     [rbp+1A0h+var_218], rcx
0x180029f58  mov     [rbp+1A0h+var_210], r13d
0x180029f5c  cmp     [rdi+0Ch], ecx
0x180029f5f  jz      loc_18002A627
0x180029f65  movsxd  rsi, dword ptr [rdi+8]
0x180029f69  lea     r15, [rdi+28h]
0x180029f6d  mov     r14, [rdi]
0x180029f70  lea     rdx, [rsp+2A0h+var_238]
0x180029f75  mov     [rsp+2A0h+var_238], ecx
0x180029f79  mov     r12d, ecx
0x180029f7c  mov     rcx, [r15]
0x180029f7f  mov     [rbp+1A0h+var_208], r15
0x180029f83  mov     rax, [rcx]
0x180029f86  mov     rax, [rax+48h]
0x180029f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f8f  mov     edx, [rsp+2A0h+var_238]
0x180029f93  test    edx, edx
0x180029f95  js      short loc_180029FB7
0x180029f97  lea     r8, [r14+rsi]
0x180029f9b  mov     ecx, [r8]
0x180029f9e  cmp     ecx, eax
0x180029fa0  ja      loc_18002A866
0x180029fa6  add     ecx, [rdi+8]
0x180029fa9  cmp     ecx, eax
0x180029fab  ja      loc_18002A866
0x180029fb1  test    edx, edx
0x180029fb3  cmovns  r12, r8
0x180029fb7  mov     [rbx], edx
0x180029fb9  test    edx, edx
0x180029fbb  js      loc_18002A0C9
0x180029fc1  mov     rcx, [r15]
0x180029fc4  mov     rdx, rbx
0x180029fc7  mov     rax, [rcx]
0x180029fca  mov     rax, [rax+48h]
0x180029fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fd3  cmp     dword ptr [rbx], 0
0x180029fd6  mov     ecx, eax
0x180029fd8  jl      loc_18002A0C9
0x180029fde  mov     edx, [rdi+8]
0x180029fe1  cmp     eax, edx
0x180029fe3  jb      loc_18002A627
0x180029fe9  lea     eax, [rdx+8]
0x180029fec  cmp     ecx, eax
0x180029fee  jb      loc_18002A627
0x180029ff4  sub     ecx, edx
0x180029ff6  sub     ecx, 8
0x180029ff9  shr     ecx, 3
0x180029ffc  cmp     [r12+4], ecx
0x18002a001  ja      loc_18002A627
0x18002a007  mov     r14d, [r12+4]
0x18002a00c  lea     rsi, [r12+8]
0x18002a011  inc     r14
0x18002a014  mov     [rbp+1A0h+var_1E8], rsi
0x18002a018  lea     r14, [r12+r14*8]
0x18002a01c  mov     [rbp+1A0h+var_1F8], r14
0x18002a020  test    r12, r12
0x18002a023  jz      loc_18002A627
0x18002a029  mov     rcx, [r15]
0x18002a02c  mov     rdx, rbx
0x18002a02f  mov     rax, [rcx]
0x18002a032  mov     rax, [rax+48h]
0x18002a036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a03b  cmp     dword ptr [rbx], 0
0x18002a03e  mov     [rsp+2A0h+var_248], eax
0x18002a042  jl      loc_18002A0C9
0x18002a048  mov     rcx, rsi
0x18002a04b  cmp     rcx, r14
0x18002a04e  jnb     short loc_18002A063
0x18002a050  mov     eax, [r12]
0x18002a054  cmp     [rcx+4], eax
0x18002a057  jnb     loc_18002A627
0x18002a05d  add     rcx, 8
0x18002a061  jmp     short loc_18002A04B
0x18002a063  mov     dword ptr [rbx], 0
0x18002a069  mov     eax, 4B0h
0x18002a06e  test    byte ptr [r12], 3
0x18002a073  jnz     short loc_18002A093
0x18002a075  mov     r15, r12
0x18002a078  cmp     rsi, r14
0x18002a07b  jnb     short loc_18002A09E
0x18002a07d  test    byte ptr [rsi+4], 3
0x18002a081  jnz     short loc_18002A09A
0x18002a083  cmp     r13b, 8
0x18002a087  jz      loc_18002A48A
0x18002a08d  add     rsi, 8
0x18002a091  jmp     short loc_18002A078
0x18002a093  mov     [rbp+1A0h+var_208], r15
0x18002a097  mov     r15, r12
0x18002a09a  or      byte ptr [rdi+13h], 4
0x18002a09e  mov     ecx, [r15+4]
0x18002a0a2  cmp     ecx, 200000h
0x18002a0a8  ja      loc_18002A627
0x18002a0ae  mov     eax, [r15]
0x18002a0b1  shr     eax, 3
0x18002a0b4  cmp     ecx, eax
0x18002a0b6  ja      loc_18002A627
0x18002a0bc  lea     eax, [rcx+1]
0x18002a0bf  cmp     eax, ecx
0x18002a0c1  jnb     short loc_18002A120
0x18002a0c3  mov     dword ptr [rbx], 0C0000095h
0x18002a0c9  mov     rsi, [rsp+2A0h+pv]
0x18002a0ce  mov     rcx, rsi; pv
0x18002a0d1  call    cs:__imp_CoTaskMemFree
0x18002a0d7  mov     rcx, [rbp+1A0h+var_220]; pv
0x18002a0db  call    cs:__imp_CoTaskMemFree
0x18002a0e1  mov     rcx, [rsp+2A0h+var_228]; pv
0x18002a0e6  call    cs:__imp_CoTaskMemFree
0x18002a0ec  mov     rcx, [rbp+1A0h+var_218]; pv
0x18002a0f0  call    cs:__imp_CoTaskMemFree
0x18002a0f6  mov     rcx, [rbp+1A0h+var_40]
0x18002a0fd  xor     rcx, rsp; StackCookie
0x18002a100  call    __security_check_cookie
0x18002a105  mov     rbx, [rsp+2A0h+arg_10]
0x18002a10d  add     rsp, 270h
0x18002a114  pop     r15
0x18002a116  pop     r14
0x18002a118  pop     r13
0x18002a11a  pop     r12
0x18002a11c  pop     rdi
0x18002a11d  pop     rsi
0x18002a11e  pop     rbp
0x18002a11f  retn
0x18002a120  shl     rax, 3
0x18002a124  mov     r13d, 0FFFFFFFFh
0x18002a12a  cmp     rax, r13
0x18002a12d  ja      short loc_18002A0C3
0x18002a12f  mov     ecx, eax; cb
0x18002a131  call    cs:__imp_CoTaskMemAlloc
0x18002a137  mov     [rsp+2A0h+pv], rax
0x18002a13c  mov     rsi, rax
0x18002a13f  test    rax, rax
0x18002a142  jz      loc_18002A874
0x18002a148  mov     r8d, [r15+4]
0x18002a14c  lea     rdx, [r15+8]; Src
0x18002a150  shl     r8, 3; Size
0x18002a154  mov     rcx, rax; void *
0x18002a157  call    memcpy_0
0x18002a15c  mov     eax, [r15+4]
0x18002a160  lea     r9, ?fnOffsetCompare@@YAHPEBX0@Z; CompareFunction
0x18002a167  mov     [rbp+1A0h+var_1E0], rax
0x18002a16b  mov     rcx, rsi; Base
0x18002a16e  mov     r8d, 8; SizeOfElements
0x18002a174  lea     r14, [rsi+rax*8]
0x18002a178  mov     [r14], r13d
0x18002a17b  mov     eax, [r15]
0x18002a17e  mov     [r14+4], eax
0x18002a182  mov     edx, [r15+4]; NumOfElements
0x18002a186  mov     [rsp+2A0h+var_230], r14
0x18002a18b  call    cs:__imp_qsort
0x18002a191  mov     eax, [r15+4]
0x18002a195  lea     ecx, [rax+1]
0x18002a198  cmp     ecx, eax
0x18002a19a  jnb     short loc_18002A1A7
0x18002a19c  mov     dword ptr [rbx], 0C0000095h
0x18002a1a2  jmp     loc_18002A0CE
0x18002a1a7  mov     eax, ecx
0x18002a1a9  shl     rax, 2
0x18002a1ad  cmp     rax, r13
0x18002a1b0  ja      short loc_18002A19C
0x18002a1b2  mov     ecx, eax; cb
0x18002a1b4  mov     esi, eax
0x18002a1b6  call    cs:__imp_CoTaskMemAlloc
0x18002a1bc  mov     [rbp+1A0h+var_220], rax
0x18002a1c0  test    rax, rax
0x18002a1c3  jz      loc_18002A87F
0x18002a1c9  mov     ecx, esi; cb
0x18002a1cb  call    cs:__imp_CoTaskMemAlloc
0x18002a1d1  mov     rsi, [rsp+2A0h+pv]
0x18002a1d6  mov     r9, rax
0x18002a1d9  mov     [rsp+2A0h+var_228], rax
0x18002a1de  test    rax, rax
0x18002a1e1  jz      loc_18002A874
0x18002a1e7  xor     r13d, r13d
0x18002a1ea  mov     rcx, rsi
0x18002a1ed  mov     [rsp+2A0h+var_24C], r13d
0x18002a1f2  cmp     rsi, r14
0x18002a1f5  jnb     loc_18002A5AB
0x18002a1fb  test    byte ptr [rcx+4], 3
0x18002a1ff  jnz     loc_18002A88A
0x18002a205  add     rcx, 8
0x18002a209  cmp     rcx, r14
0x18002a20c  jb      short loc_18002A1FB
0x18002a20e  mov     [rsp+2A0h+var_24C], r13d
0x18002a213  test    r13d, r13d
0x18002a216  jnz     loc_18002A834
0x18002a21c  mov     r10, [rbp+1A0h+var_218]
0x18002a220  mov     eax, [rsi+4]
0x18002a223  lea     rdx, [rdi+8]
0x18002a227  mov     rcx, [rbp+1A0h+var_220]
0x18002a22b  mov     r8, rsi
0x18002a22e  mov     [r9], eax
0x18002a231  mov     [rbp+1A0h+var_200], rsi
0x18002a235  mov     [rbp+1A0h+var_1F0], rdx
0x18002a239  mov     [rcx], eax
0x18002a23b  xor     ecx, ecx
0x18002a23d  xor     eax, eax
0x18002a23f  mov     [rsp+2A0h+var_250], ecx
0x18002a243  mov     [rsp+2A0h+var_254], eax
0x18002a247  cmp     r8, r14
0x18002a24a  jnb     loc_18002A4C1
0x18002a250  movsxd  rdx, dword ptr [r8+4]
0x18002a254  cmp     edx, [r15]
0x18002a257  jnb     loc_18002A627
0x18002a25d  mov     esi, [r8+0Ch]
0x18002a261  lea     rax, [rdi+8]
0x18002a265  movsxd  r15, dword ptr [rax]
0x18002a268  sub     esi, edx
0x18002a26a  add     r15, rdx
0x18002a26d  mov     [rsp+2A0h+var_258], esi
0x18002a271  add     r15, [rdi]
0x18002a274  xor     r14b, r14b
0x18002a277  mov     [rbp+1A0h+var_1F0], rax
0x18002a27b  mov     [rbp+1A0h+var_1D8], r15
0x18002a27f  test    dl, 3
0x18002a282  jnz     loc_18002A8A2
0x18002a288  cmp     dword ptr [r8], 0
0x18002a28c  jz      loc_18002A68D
0x18002a292  cmp     byte ptr [rbp+1A0h+var_210], 8
0x18002a296  jz      loc_18002A3B3
0x18002a29c  xor     edx, edx; Val
0x18002a29e  mov     dword ptr [rsp+2A0h+var_240], 0
0x18002a2a6  mov     r8d, 158h; Size
0x18002a2ac  mov     [rbp+1A0h+var_1C8], 4
0x18002a2b4  lea     rcx, [rbp+1A0h+var_1C0]; void *
0x18002a2b8  mov     [rbp+1A0h+var_1D0], 0
0x18002a2c0  mov     [rbp+1A0h+var_60], 0
0x18002a2cb  call    memset_0
0x18002a2d0  test    byte ptr [rbp+1A0h+var_1C8], 2
0x18002a2d4  lea     rax, [rbp+1A0h+var_1C0]
0x18002a2d8  mov     [rbp+1A0h+var_68], rax
0x18002a2df  jnz     loc_18002A4AC
0x18002a2e5  mov     rdx, [rbp+1A0h+var_1D8]; struct tagSERIALIZEDPROPERTYVALUE *
0x18002a2e9  lea     rax, [rsp+2A0h+var_240]
0x18002a2ee  mov     [rsp+2A0h+var_268], rax; unsigned int *
0x18002a2f3  lea     r8d, [rsi+3]
0x18002a2f7  xor     eax, eax
0x18002a2f9  lea     rcx, [rbp+1A0h+var_1D0]; this
0x18002a2fd  mov     [rsp+2A0h+var_270], rax; struct tagPROPVARIANT *
0x18002a302  and     r8d, 0FFFFFFFCh; unsigned int
0x18002a306  mov     [rsp+2A0h+var_278], eax; int
0x18002a30a  xor     r9d, r9d; int
0x18002a30d  mov     [rsp+2A0h+var_280], eax; int
0x18002a311  call    ?Worker@DeserializeHelper@@QEAAJPEBUtagSERIALIZEDPROPERTYVALUE@@KHHHPEAUtagPROPVARIANT@@PEAK@Z; DeserializeHelper::Worker(tagSERIALIZEDPROPERTYVALUE const *,ulong,int,int,int,tagPROPVARIANT *,ulong *)
0x18002a316  mov     esi, eax
0x18002a318  mov     edx, esi; int
0x18002a31a  lea     rcx, [rbp+1A0h+var_1C0]; this
0x18002a31e  call    ?Done@CleanupStack@@QEAAXJ@Z; CleanupStack::Done(long)
0x18002a323  test    esi, esi
0x18002a325  js      loc_18002A927
0x18002a32b  mov     r13d, dword ptr [rsp+2A0h+var_240]
0x18002a330  mov     [rbx], esi
0x18002a332  mov     esi, [rsp+2A0h+var_258]
0x18002a336  mov     r9, [rbp+1A0h+var_220]
0x18002a33a  mov     ecx, esi
0x18002a33c  mov     r8, [rbp+1A0h+var_200]
0x18002a340  mov     rdx, r8
0x18002a343  sub     rdx, [rsp+2A0h+pv]
0x18002a348  sar     rdx, 3
0x18002a34c  cmp     r13d, esi
0x18002a34f  cmovb   ecx, r13d
0x18002a353  add     ecx, [r9+rdx*4]
0x18002a357  mov     [r9+rdx*4+4], ecx
0x18002a35c  mov     r9, [rsp+2A0h+var_228]
0x18002a361  mov     ecx, [r9+rdx*4]
0x18002a365  add     ecx, r13d
0x18002a368  mov     [r9+rdx*4+4], ecx
0x18002a36d  cmp     r13d, esi
0x18002a370  jb      short loc_18002A3A7
0x18002a372  ja      loc_18002A598
0x18002a378  test    r14b, r14b
0x18002a37b  jnz     loc_18002A598
0x18002a381  mov     eax, [rsp+2A0h+var_254]
0x18002a385  mov     ecx, [rsp+2A0h+var_250]
0x18002a389  mov     r13d, [rsp+2A0h+var_24C]
0x18002a38e  add     r8, 8
0x18002a392  mov     r14, [rsp+2A0h+var_230]
0x18002a397  mov     r15, r12
0x18002a39a  mov     r10, [rbp+1A0h+var_218]
  ... truncated ...
```
