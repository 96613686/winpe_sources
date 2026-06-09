# SampGetGroupsForToken2

- ea: `0x1803bc644`
- end: `0x1803bd6d5`
- name: `SampGetGroupsForToken2`
- size: `4241`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18023e988`
- `0x1803bc5cc`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180166ee0`
- `0x180166f10`
- `0x180173260`
- `0x1803b8488`
- `0x1803ba6a0`
- `0x1803bc644`
- `0x1803befd8`
- `0x1803c0444`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803bc6ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803bc6ce`
- `ntdll!RtlCopySid` at `0x1803bcb28`
- `ntdll!RtlCopySid` at `0x1803bccb7`
- `ntdll!RtlCopySid` at `0x1803bcfe9`
- `ntdll!RtlCopySid` at `0x1803bd169`
- `ntdll!RtlCopySid` at `0x1803bcb28`
- `ntdll!RtlCopySid` at `0x1803bccb7`
- `ntdll!RtlCopySid` at `0x1803bcfe9`
- `ntdll!RtlCopySid` at `0x1803bd169`
- `ntdll!RtlLengthSid` at `0x1803bcafc`
- `ntdll!RtlLengthSid` at `0x1803bcc8b`
- `ntdll!RtlLengthSid` at `0x1803bcfc5`
- `ntdll!RtlLengthSid` at `0x1803bd14f`
- `ntdll!RtlLengthSid` at `0x1803bcafc`
- `ntdll!RtlLengthSid` at `0x1803bcc8b`
- `ntdll!RtlLengthSid` at `0x1803bcfc5`
- `ntdll!RtlLengthSid` at `0x1803bd14f`

## pseudocode

```c
__int64 __fastcall SampGetGroupsForToken2(
        void *a1,
        void *a2,
        int a3,
        int a4,
        _DWORD *a5,
        __int64 *a6,
        __int64 a7,
        _QWORD *a8)
{
  LPVOID Value; // rax
  int v10; // r12d
  unsigned int v11; // edi
  unsigned int v12; // r13d
  int AccountAndUniversalMemberships; // ebx
  int v14; // r8d
  unsigned int v15; // r9d
  char *v16; // r13
  unsigned int v17; // ecx
  __int64 v18; // rax
  int v19; // edx
  unsigned int v20; // r8d
  unsigned int v21; // ebx
  int v22; // r13d
  size_t v23; // rdi
  void *v24; // rax
  _QWORD *v25; // rbx
  unsigned int v26; // edi
  char *v27; // rax
  int v28; // eax
  __int64 k; // rbx
  _DWORD *v30; // rax
  ULONG v31; // eax
  _QWORD *v32; // rdx
  char *v33; // rax
  int v34; // r8d
  int v35; // r9d
  char *v36; // rbx
  __int64 m; // rbx
  _DWORD *v38; // rax
  ULONG v39; // eax
  _QWORD *v40; // rdx
  char *v41; // rax
  int v42; // r8d
  int v43; // r9d
  char *v44; // rbx
  __int64 v45; // r13
  int v46; // r8d
  int v47; // r9d
  size_t v48; // rbx
  void *v49; // rax
  __int64 v50; // rbx
  unsigned int v51; // r13d
  void *v52; // rax
  unsigned int v53; // edi
  unsigned int v54; // ebx
  _DWORD *v55; // rax
  __int64 v56; // rdi
  __int64 v57; // rbx
  ULONG v58; // eax
  _QWORD *v59; // rdx
  unsigned int v60; // edi
  char *v61; // rax
  int v62; // r8d
  int v63; // r9d
  char *v64; // rbx
  int v65; // eax
  void *v66; // rbx
  _DWORD *v67; // rdi
  __int64 v68; // rbx
  int v69; // r8d
  int v70; // r9d
  unsigned int v71; // ebx
  __int64 v72; // rax
  __int64 *v73; // r10
  unsigned int v74; // r8d
  unsigned int v75; // r9d
  _QWORD *v76; // r11
  unsigned int v77; // r8d
  _QWORD *v78; // r9
  unsigned int i; // r8d
  unsigned int v80; // r8d
  __int64 v81; // r9
  __int64 v82; // rdx
  unsigned int v83; // r8d
  __int64 v84; // r9
  unsigned int v85; // r8d
  __int64 v86; // r9
  unsigned int j; // r9d
  _QWORD *v88; // rcx
  unsigned int v89; // edi
  unsigned int n; // eax
  __int64 v91; // rdx
  _QWORD *v92; // rcx
  unsigned int v93; // edi
  unsigned int ii; // eax
  __int64 v95; // rdx
  _QWORD *v96; // rcx
  unsigned int v97; // edi
  unsigned int jj; // eax
  __int64 v99; // rdx
  __int64 *v100; // rdi
  unsigned int v102; // [rsp+7Ch] [rbp-14Ch]
  unsigned int v103; // [rsp+80h] [rbp-148h]
  _DWORD v104[3]; // [rsp+84h] [rbp-144h] BYREF
  size_t Size; // [rsp+90h] [rbp-138h]
  void *v106; // [rsp+98h] [rbp-130h]
  unsigned int v107; // [rsp+A0h] [rbp-128h]
  unsigned int v108; // [rsp+A4h] [rbp-124h]
  unsigned int v109; // [rsp+A8h] [rbp-120h]
  _DWORD v110[3]; // [rsp+ACh] [rbp-11Ch] BYREF
  __int64 v111; // [rsp+B8h] [rbp-110h] BYREF
  unsigned int v112; // [rsp+C0h] [rbp-108h]
  unsigned int v113; // [rsp+C4h] [rbp-104h]
  int v114; // [rsp+C8h] [rbp-100h]
  unsigned int v115; // [rsp+CCh] [rbp-FCh]
  int v116; // [rsp+D0h] [rbp-F8h]
  __int64 v117; // [rsp+D8h] [rbp-F0h] BYREF
  void *v118; // [rsp+E0h] [rbp-E8h]
  void *v119; // [rsp+E8h] [rbp-E0h]
  void *v120; // [rsp+F0h] [rbp-D8h]
  __int64 v121; // [rsp+F8h] [rbp-D0h] BYREF
  int v122; // [rsp+100h] [rbp-C8h]
  _DWORD v123[3]; // [rsp+104h] [rbp-C4h] BYREF
  _QWORD *v124; // [rsp+110h] [rbp-B8h]
  void *v125; // [rsp+118h] [rbp-B0h]
  int v126; // [rsp+120h] [rbp-A8h]
  unsigned int v127; // [rsp+124h] [rbp-A4h]
  __int64 *v128; // [rsp+128h] [rbp-A0h]
  void *v129; // [rsp+130h] [rbp-98h] BYREF
  void *Src; // [rsp+138h] [rbp-90h] BYREF
  __int64 v131; // [rsp+140h] [rbp-88h] BYREF
  void *v132; // [rsp+148h] [rbp-80h] BYREF
  __int64 v133; // [rsp+150h] [rbp-78h] BYREF
  void *v134; // [rsp+158h] [rbp-70h]
  LPVOID v135; // [rsp+160h] [rbp-68h]
  _DWORD *v136; // [rsp+168h] [rbp-60h]
  _DWORD Sid[4]; // [rsp+170h] [rbp-58h] BYREF

  v114 = a4;
  LODWORD(Size) = a3;
  v134 = a1;
  Src = a1;
  v129 = a2;
  v136 = a5;
  v128 = a6;
  v124 = a8;
  Value = TlsGetValue(dwTSindex);
  v10 = (int)Value;
  v135 = Value;
  LOBYTE(Value) = 0;
  v116 = (int)Value;
  v132 = 0;
  v133 = 0;
  v125 = 0;
  v106 = 0;
  v11 = 0;
  memset(v110, 0, sizeof(v110));
  v12 = 0;
  v123[0] = 0;
  v102 = 0;
  v103 = 0;
  memset(v104, 0, sizeof(v104));
  v131 = 0;
  v119 = 0;
  v118 = 0;
  v120 = 0;
  Sid[0] = 257;
  Sid[1] = 83886080;
  Sid[2] = 32;
  v121 = 0;
  v111 = 0;
  v117 = 0;
  if ( a5 )
  {
    *v128 = 0;
    *a5 = 0;
  }
  if ( v124 )
    *v124 = 0;
  AccountAndUniversalMemberships = GetAccountAndUniversalMemberships(
                                     v10,
                                     Size,
                                     0,
                                     0,
                                     1,
                                     (__int64)&Src,
                                     (unsigned __int64)&v129 & -(__int64)(a2 != 0),
                                     0,
                                     v114,
                                     (unsigned __int64)&v121 & -(__int64)(a5 != 0),
                                     (unsigned __int64)&v111
                                   & ((unsigned __int128)-(__int128)(unsigned __int64)a5 >> 64),
                                     a7,
                                     &v117);
  if ( AccountAndUniversalMemberships < 0 )
  {
    v16 = *(char **)&v104[1];
    goto LABEL_100;
  }
  UpdateLowestTTLIfNecessary(v124, 1, &v117);
  if ( !a5 )
  {
    v16 = *(char **)&v104[1];
    goto LABEL_100;
  }
  v17 = *(_DWORD *)(v121 + 4);
  v115 = v17;
  Src = *(void **)(v121 + 8);
  v102 = *(_DWORD *)(v121 + 24);
  v121 = *(_QWORD *)(v121 + 32);
  v18 = v111;
  v19 = *(_DWORD *)(v111 + 4);
  LODWORD(v111) = v19;
  v129 = *(void **)(v18 + 8);
  v20 = *(_DWORD *)(v18 + 24);
  v103 = v20;
  v117 = *(_QWORD *)(v18 + 32);
  LODWORD(v18) = *(_DWORD *)v18;
  LOBYTE(v18) = v18 & 1;
  v116 = v18;
  if ( (Size & 2) == 0 )
  {
LABEL_76:
    v71 = v104[0];
    v72 = THAlloc_(v10, 1, 8 * (v17 + v19 + v11 + v12 + v102 + v104[0] + v20), 1, 0, 522131928);
    v73 = v128;
    *v128 = v72;
    if ( v72 )
    {
      *a5 = 0;
      v74 = 0;
      v75 = v115;
      v76 = Src;
      while ( v74 < v75 )
      {
        *(_QWORD *)(*v73 + 8LL * (v74 + *a5)) = v76[v74] + 24LL;
        ++v74;
      }
      *a5 += v75;
      v77 = 0;
      v78 = v129;
      while ( v77 < (unsigned int)v111 )
      {
        *(_QWORD *)(*v73 + 8LL * (v77 + *a5)) = v78[v77] + 24LL;
        ++v77;
      }
      *a5 += v111;
      for ( i = 0; i < v11; ++i )
        *(_QWORD *)(*v73 + 8LL * (i + *a5)) = *((_QWORD *)v132 + i) + 24LL;
      *a5 += v11;
      v80 = 0;
      v81 = v133;
      while ( v80 < v12 )
      {
        *(_QWORD *)(*v73 + 8LL * (v80 + *a5)) = *(_QWORD *)(v81 + 8LL * v80) + 24LL;
        ++v80;
      }
      *a5 += v12;
      v82 = (unsigned int)*a5;
      v83 = 0;
      v84 = v121;
      while ( v83 < v102 )
      {
        *(_QWORD *)(*v73 + 8 * v82) = *(_QWORD *)(v84 + 8LL * v83);
        v82 = (unsigned int)++*a5;
        ++v83;
      }
      v85 = 0;
      v86 = v117;
      while ( v85 < v103 )
      {
        *(_QWORD *)(*v73 + 8 * v82) = *(_QWORD *)(v86 + 8LL * v85);
        v82 = (unsigned int)++*a5;
        ++v85;
      }
      for ( j = 0; j < v71; ++j )
      {
        *(_QWORD *)(*v73 + 8LL * (unsigned int)v82) = *(_QWORD *)(v131 + 8LL * j);
        LODWORD(v82) = ++*a5;
      }
      AccountAndUniversalMemberships = SampExpandShadowPrincipal(
                                         v10,
                                         (_DWORD)v134,
                                         (_DWORD)a5,
                                         (_DWORD)v73,
                                         (__int64)v124);
      v16 = *(char **)&v104[1];
    }
    else
    {
      AccountAndUniversalMemberships = -1073741670;
      v16 = *(char **)&v104[1];
    }
    goto LABEL_100;
  }
  v21 = 0;
  v122 = 0;
  v22 = v17 + 1;
  v23 = 8LL * (v17 + 1);
  v24 = (void *)THAlloc(v23);
  v125 = v24;
  if ( v24 )
  {
    v25 = v24;
    memset_0(v24, 0, v23);
    *v25 = v134;
    v122 = 1;
    v15 = v115;
    if ( v115 )
      memcpy_0(v25 + 1, Src, 8LL * v115);
    v21 = v22;
    v122 = v22;
  }
  if ( !v125 )
  {
    AccountAndUniversalMemberships = -1073741801;
    v16 = *(char **)&v104[1];
    goto LABEL_100;
  }
  v26 = 0;
  v109 = 0;
  Size = 8LL * (v21 + (unsigned int)v111);
  v27 = (char *)THAlloc(Size);
  v16 = v27;
  *(_QWORD *)&v104[1] = v27;
  if ( v27 )
  {
    memset_0(v27, 0, Size);
    if ( v21 )
      memcpy_0(v16, v125, 8LL * v21);
    v109 = v21;
    v28 = v111;
    if ( (_DWORD)v111 )
    {
      memcpy_0(&v16[8 * v21], v129, 8LL * (unsigned int)v111);
      v28 = v111;
    }
    v26 = v21 + v28;
    v109 = v21 + v28;
  }
  if ( !v16 )
  {
    AccountAndUniversalMemberships = -1073741801;
    goto LABEL_100;
  }
  if ( v102 )
  {
    v107 = 0;
    v119 = (void *)THAlloc_(v10, 1, 8 * v102, 1, 0, 522131780);
    for ( k = 0; ; k = (unsigned int)(k + 1) )
    {
      v126 = k;
      if ( (unsigned int)k >= v102 )
        break;
      v30 = (_DWORD *)THAlloc_(v10, 1, 58, 1, 0, 522131780);
      *((_QWORD *)v119 + k) = v30;
      *v30 = 58;
      v31 = RtlLengthSid(*(PSID *)(v121 + 8 * k));
      v32 = v119;
      *(_DWORD *)(*((_QWORD *)v119 + k) + 4LL) = v31;
      RtlCopySid(*(_DWORD *)(v32[k] + 4LL), (PSID)(v32[k] + 24LL), *(PSID *)(v121 + 8 * k));
    }
    v107 = 0;
    Size = 8LL * (v26 + v102);
    v33 = (char *)THAlloc(Size);
    v36 = v33;
    if ( v33 )
    {
      memset_0(v33, 0, Size);
      if ( v26 )
        memcpy_0(v36, v16, 8LL * v26);
      memcpy_0(&v36[8 * v26], v119, 8LL * v102);
      v107 = v26 + v102;
    }
    THFreeAux(v10, (_DWORD)v16, v34, v35, 522131780);
    v16 = v36;
    *(_QWORD *)&v104[1] = v36;
    v26 = v107;
    v109 = v107;
  }
  if ( !v16 )
  {
    AccountAndUniversalMemberships = -1073741801;
    goto LABEL_100;
  }
  if ( v103 )
  {
    v108 = 0;
    v118 = (void *)THAlloc_(v10, 1, 8 * v103, 1, 0, 522131792);
    for ( m = 0; ; m = (unsigned int)(m + 1) )
    {
      v123[1] = m;
      if ( (unsigned int)m >= v103 )
        break;
      v38 = (_DWORD *)THAlloc_(v10, 1, 58, 1, 0, 522131792);
      *((_QWORD *)v118 + m) = v38;
      *v38 = 58;
      v39 = RtlLengthSid(*(PSID *)(v117 + 8 * m));
      v40 = v118;
      *(_DWORD *)(*((_QWORD *)v118 + m) + 4LL) = v39;
      RtlCopySid(*(_DWORD *)(v40[m] + 4LL), (PSID)(v40[m] + 24LL), *(PSID *)(v117 + 8 * m));
    }
    v108 = 0;
    Size = 8LL * (v26 + v103);
    v41 = (char *)THAlloc(Size);
    v44 = v41;
    if ( v41 )
    {
      memset_0(v41, 0, Size);
      if ( v26 )
        memcpy_0(v44, v16, 8LL * v26);
      memcpy_0(&v44[8 * v26], v118, 8LL * v103);
      v108 = v26 + v103;
    }
    THFreeAux(v10, (_DWORD)v16, v42, v43, 522131792);
    v16 = v44;
    *(_QWORD *)&v104[1] = v44;
    v26 = v108;
    v109 = v108;
  }
  if ( !v16 )
  {
    AccountAndUniversalMemberships = -1073741801;
    goto LABEL_100;
  }
  Size = 8LL * v26;
  *(_QWORD *)&v110[1] = THAlloc_(v10, 1, 8 * v26, 1, 0, 522131799);
  AccountAndUniversalMemberships = SampGetMemberships2(
                                     (int)v16,
                                     v26,
                                     (int)qword_18052B2C0,
                                     4,
                                     v114,
                                     (__int64)v110,
                                     (__int64)&v132,
                                     0,
                                     (__int64)v104,
                                     (__int64)&v131,
                                     0,
                                     *(void **)&v110[1]);
  if ( AccountAndUniversalMemberships >= 0 )
  {
    v45 = *(_QWORD *)&v110[1];
    UpdateLowestTTLIfNecessary(v124, v26, *(_QWORD *)&v110[1]);
    if ( v45 )
      THFreeAux(v10, v45, v46, v47, 522131833);
    *(_QWORD *)&v110[1] = 0;
    v113 = 0;
    v48 = 8LL * (v26 + v110[0]);
    v49 = (void *)THAlloc(v48);
    v106 = v49;
    if ( !v49 )
      goto LABEL_55;
    memset_0(v49, 0, v48);
    v50 = v110[0];
    if ( v110[0] )
      memcpy_0(v106, v132, 8LL * v110[0]);
    v113 = v50;
    if ( v26 )
      memcpy_0((char *)v106 + 8 * v50, *(const void **)&v104[1], Size);
    v51 = v26 + v50;
    v113 = v26 + v50;
    v52 = v106;
    if ( !v106 )
    {
LABEL_55:
      AccountAndUniversalMemberships = -1073741801;
      v16 = *(char **)&v104[1];
      goto LABEL_100;
    }
    v53 = v104[0];
    if ( v104[0] )
    {
      v112 = 0;
      v120 = (void *)THAlloc_(v10, 1, 8 * v104[0], 1, 0, 522131858);
      v54 = 0;
      while ( 1 )
      {
        v127 = v54;
        if ( v54 >= v53 )
          break;
        v55 = (_DWORD *)THAlloc_(v10, 1, 58, 1, 0, 522131858);
        v56 = v54;
        *((_QWORD *)v120 + v54) = v55;
        *v55 = 58;
        v57 = v131;
        v58 = RtlLengthSid(*(PSID *)(v131 + 8 * v56));
        v59 = v120;
        *(_DWORD *)(*((_QWORD *)v120 + v56) + 4LL) = v58;
        RtlCopySid(*(_DWORD *)(v59[v56] + 4LL), (PSID)(v59[v56] + 24LL), *(PSID *)(v57 + 8 * v56));
        v54 = v127 + 1;
        v53 = v104[0];
      }
      v60 = 0;
      v112 = 0;
      Size = 8LL * (v51 + v104[0]);
      v61 = (char *)THAlloc(Size);
      v64 = v61;
      if ( v61 )
      {
        memset_0(v61, 0, Size);
        if ( v51 )
          memcpy_0(v64, v106, 8LL * v51);
        v112 = v51;
        v65 = v104[0];
        if ( v104[0] )
        {
          memcpy_0(&v64[8 * v51], v120, 8LL * v104[0]);
          v65 = v104[0];
        }
        v60 = v65 + v51;
        v112 = v65 + v51;
      }
      THFreeAux(v10, (_DWORD)v106, v62, v63, 522131858);
      v52 = v64;
      v106 = v64;
      v51 = v60;
      v113 = v60;
    }
    if ( !v52 )
    {
      AccountAndUniversalMemberships = -1073741801;
      v16 = *(char **)&v104[1];
      goto LABEL_100;
    }
    v66 = (void *)THAlloc_(v10, 1, 8 * v51, 1, 0, 522131865);
    *(_QWORD *)&v110[1] = v66;
    v67 = (_DWORD *)THAlloc_(v10, 1, 58, 1, 0, 522131874);
    *v67 = 58;
    v67[1] = RtlLengthSid(Sid);
    RtlCopySid(0x1Cu, v67 + 6, Sid);
    AccountAndUniversalMemberships = SampGetMemberships2(
                                       (int)v106,
                                       v51,
                                       (int)v67,
                                       2,
                                       v114,
                                       (__int64)v123,
                                       (__int64)&v133,
                                       0,
                                       0,
                                       0,
                                       0,
                                       v66);
    if ( v67 )
      THFreeAux(v10, (_DWORD)v67, v14, v15, 522131895);
    if ( AccountAndUniversalMemberships < 0 )
    {
      v16 = *(char **)&v104[1];
      goto LABEL_100;
    }
    v68 = *(_QWORD *)&v110[1];
    UpdateLowestTTLIfNecessary(v124, v51, *(_QWORD *)&v110[1]);
    if ( v68 )
      THFreeAux(v10, v68, v69, v70, 522131910);
    *(_QWORD *)&v110[1] = 0;
    v12 = v123[0];
    v11 = v110[0];
    v17 = v115;
    v19 = v111;
    v20 = v103;
    goto LABEL_76;
  }
LABEL_100:
  if ( v125 )
    THFreeAux(v10, (_DWORD)v125, v14, v15, 522132010);
  if ( v16 )
    THFreeAux(v10, (_DWORD)v16, v14, v15, 522132014);
  if ( v106 )
    THFreeAux(v10, (_DWORD)v106, v14, v15, 522132018);
  v88 = v119;
  if ( v119 )
  {
    v89 = 0;
    for ( n = v102; v89 < n; ++v89 )
    {
      v91 = v88[v89];
      if ( v91 )
      {
        THFreeAux(v10, v91, v14, v15, 522132022);
        n = v102;
        v88 = v119;
      }
      v88[v89] = 0;
    }
    THFreeAux(v10, (_DWORD)v88, v14, v15, 522132022);
  }
  v92 = v118;
  if ( v118 )
  {
    v93 = 0;
    for ( ii = v103; v93 < ii; ++v93 )
    {
      v95 = v92[v93];
      if ( v95 )
      {
        THFreeAux(v10, v95, v14, v15, 522132024);
        ii = v103;
        v92 = v118;
      }
      v92[v93] = 0;
    }
    THFreeAux(v10, (_DWORD)v92, v14, v15, 522132024);
  }
  v96 = v120;
  if ( v120 )
  {
    v97 = 0;
    for ( jj = v104[0]; v97 < jj; ++v97 )
    {
      v99 = v96[v97];
      if ( v99 )
      {
        THFreeAux(v10, v99, v14, v15, 522132026);
        jj = v104[0];
        v96 = v120;
      }
      v96[v97] = 0;
    }
    THFreeAux(v10, (_DWORD)v96, v14, v15, 522132026);
  }
  if ( AccountAndUniversalMemberships < 0 )
  {
    v100 = v128;
    if ( v128 )
    {
      if ( *v128 )
      {
        THFreeAux(v10, *v128, v14, v15, 522132031);
        *v100 = 0;
        if ( a5 )
          *a5 = 0;
      }
    }
  }
  if ( *(_QWORD *)&v110[1] )
    THFreeAux(v10, v110[1], v14, v15, 522132041);
  THClearErrors(v96);
  if ( (_BYTE)v116 && AccountAndUniversalMemberships >= 0 )
    return 289;
  return (unsigned int)AccountAndUniversalMemberships;
}

```

## disassembly

```asm
0x1803bc644  mov     r11, rsp
0x1803bc647  push    rbx
0x1803bc648  push    rsi
0x1803bc649  push    rdi
0x1803bc64a  push    r12
0x1803bc64c  push    r13
0x1803bc64e  push    r14
0x1803bc650  push    r15
0x1803bc652  sub     rsp, 190h
0x1803bc659  mov     rax, cs:__security_cookie
0x1803bc660  xor     rax, rsp
0x1803bc663  mov     [rsp+1C8h+var_48], rax
0x1803bc66b  mov     [rsp+1C8h+var_100], r9d
0x1803bc673  mov     dword ptr [rsp+1C8h+Size], r8d
0x1803bc67b  mov     rbx, rdx
0x1803bc67e  mov     [r11-70h], rcx
0x1803bc682  mov     [r11-90h], rcx
0x1803bc689  mov     [r11-98h], rdx
0x1803bc690  mov     r15, [rsp+1C8h+arg_20]
0x1803bc698  mov     [rsp+1C8h+var_60], r15
0x1803bc6a0  mov     rax, [rsp+1C8h+arg_28]
0x1803bc6a8  mov     [rsp+1C8h+var_A0], rax
0x1803bc6b0  mov     r14, [rsp+1C8h+arg_30]
0x1803bc6b8  mov     rax, [rsp+1C8h+arg_38]
0x1803bc6c0  mov     [rsp+1C8h+var_B8], rax
0x1803bc6c8  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1803bc6ce  call    cs:__imp_TlsGetValue
0x1803bc6d4  mov     r12, rax
0x1803bc6d7  mov     [rsp+1C8h+var_68], rax
0x1803bc6df  xor     esi, esi
0x1803bc6e1  mov     al, sil
0x1803bc6e4  mov     [rsp+1C8h+var_F8], eax
0x1803bc6eb  mov     [rsp+1C8h+var_154], al
0x1803bc6ef  mov     [rsp+1C8h+var_80], rsi
0x1803bc6f7  mov     [rsp+1C8h+var_78], rsi
0x1803bc6ff  mov     [rsp+1C8h+var_B0], rsi
0x1803bc707  mov     qword ptr [rsp+1C8h+var_144+4], rsi
0x1803bc70f  mov     [rsp+1C8h+var_130], rsi
0x1803bc717  mov     edi, esi
0x1803bc719  mov     dword ptr [rsp+1C8h+var_11C], esi
0x1803bc720  mov     r13d, esi
0x1803bc723  mov     [rsp+1C8h+var_C4], esi
0x1803bc72a  mov     [rsp+1C8h+var_14C], esi
0x1803bc72e  mov     [rsp+1C8h+var_148], esi
0x1803bc735  mov     dword ptr [rsp+1C8h+var_144], esi
0x1803bc73c  mov     [rsp+1C8h+var_88], rsi
0x1803bc744  mov     [rsp+1C8h+var_E0], rsi
0x1803bc74c  mov     [rsp+1C8h+var_E8], rsi
0x1803bc754  mov     [rsp+1C8h+var_D8], rsi
0x1803bc75c  mov     [rsp+1C8h+Sid], 101h
0x1803bc767  mov     [rsp+1C8h+var_54], 5000000h
0x1803bc772  mov     [rsp+1C8h+var_50], 20h ; ' '
0x1803bc77d  mov     [rsp+1C8h+var_D0], rsi
0x1803bc785  mov     [rsp+1C8h+var_110], rsi
0x1803bc78d  mov     [rsp+1C8h+var_F0], rsi
0x1803bc795  mov     qword ptr [rsp+1C8h+var_11C+4], rsi
0x1803bc79d  test    r15, r15
0x1803bc7a0  jz      short loc_1803BC7B0
0x1803bc7a2  mov     rax, [rsp+1C8h+var_A0]
0x1803bc7aa  mov     [rax], rsi
0x1803bc7ad  mov     [r15], esi
0x1803bc7b0  mov     rax, [rsp+1C8h+var_B8]
0x1803bc7b8  test    rax, rax
0x1803bc7bb  jz      short loc_1803BC7C0
0x1803bc7bd  mov     [rax], rsi
0x1803bc7c0  mov     rax, r15
0x1803bc7c3  neg     rax
0x1803bc7c6  sbb     rdx, rdx
0x1803bc7c9  lea     rax, [rsp+1C8h+var_110]
0x1803bc7d1  and     rdx, rax
0x1803bc7d4  mov     rax, r15
0x1803bc7d7  neg     rax
0x1803bc7da  sbb     rcx, rcx
0x1803bc7dd  lea     rax, [rsp+1C8h+var_D0]
0x1803bc7e5  and     rcx, rax
0x1803bc7e8  neg     rbx
0x1803bc7eb  sbb     rax, rax
0x1803bc7ee  lea     r8, [rsp+1C8h+var_98]
0x1803bc7f6  and     rax, r8
0x1803bc7f9  lea     r8, [rsp+1C8h+var_F0]
0x1803bc801  mov     [rsp+1C8h+var_168], r8; void *
0x1803bc806  mov     [rsp+1C8h+var_170], r14; __int64
0x1803bc80b  mov     [rsp+1C8h+var_178], rdx; __int64
0x1803bc810  mov     [rsp+1C8h+var_180], rcx; __int64
0x1803bc815  mov     ecx, [rsp+1C8h+var_100]
0x1803bc81c  mov     dword ptr [rsp+1C8h+var_188], ecx; int
0x1803bc820  mov     dword ptr [rsp+1C8h+var_190], esi; int
0x1803bc824  mov     [rsp+1C8h+var_198], rax; __int64
0x1803bc829  lea     rax, [rsp+1C8h+Src]
0x1803bc831  mov     [rsp+1C8h+var_1A0], rax; __int64
0x1803bc836  mov     r14d, 1
0x1803bc83c  mov     [rsp+1C8h+var_1A8], r14d; int
0x1803bc841  xor     r9d, r9d; int
0x1803bc844  xor     r8d, r8d; int
0x1803bc847  mov     edx, dword ptr [rsp+1C8h+Size]; int
0x1803bc84e  mov     rcx, r12; int
0x1803bc851  call    GetAccountAndUniversalMemberships
0x1803bc856  mov     ebx, eax
0x1803bc858  mov     [rsp+1C8h+var_150], eax
0x1803bc85c  test    eax, eax
0x1803bc85e  jns     short loc_1803BC86D
0x1803bc860  mov     r13, qword ptr [rsp+1C8h+var_144+4]
0x1803bc868  jmp     loc_1803BD4C8
0x1803bc86d  lea     r8, [rsp+1C8h+var_F0]
0x1803bc875  mov     edx, r14d
0x1803bc878  mov     rcx, [rsp+1C8h+var_B8]
0x1803bc880  call    UpdateLowestTTLIfNecessary
0x1803bc885  test    r15, r15
0x1803bc888  jnz     short loc_1803BC897
0x1803bc88a  mov     r13, qword ptr [rsp+1C8h+var_144+4]
0x1803bc892  jmp     loc_1803BD4C8
0x1803bc897  mov     rax, [rsp+1C8h+var_D0]
0x1803bc89f  mov     ecx, [rax+4]
0x1803bc8a2  mov     [rsp+1C8h+var_FC], ecx
0x1803bc8a9  mov     rdx, [rax+8]
0x1803bc8ad  mov     [rsp+1C8h+Src], rdx
0x1803bc8b5  mov     edx, [rax+18h]
0x1803bc8b8  mov     [rsp+1C8h+var_14C], edx
0x1803bc8bc  mov     rax, [rax+20h]
0x1803bc8c0  mov     [rsp+1C8h+var_D0], rax
0x1803bc8c8  mov     rax, [rsp+1C8h+var_110]
0x1803bc8d0  mov     edx, [rax+4]
0x1803bc8d3  mov     dword ptr [rsp+1C8h+var_110], edx
0x1803bc8da  mov     r8, [rax+8]
0x1803bc8de  mov     [rsp+1C8h+var_98], r8
0x1803bc8e6  mov     r8d, [rax+18h]
0x1803bc8ea  mov     [rsp+1C8h+var_148], r8d
0x1803bc8f2  mov     r9, [rax+20h]
0x1803bc8f6  mov     [rsp+1C8h+var_F0], r9
0x1803bc8fe  mov     eax, [rax]
0x1803bc900  and     al, r14b
0x1803bc903  mov     [rsp+1C8h+var_F8], eax
0x1803bc90a  mov     [rsp+1C8h+var_154], al
0x1803bc90e  test    byte ptr [rsp+1C8h+Size], 2
0x1803bc916  jz      loc_1803BD25D
0x1803bc91c  mov     ebx, esi
0x1803bc91e  mov     [rsp+1C8h+var_C8], ebx
0x1803bc925  lea     r13d, [rcx+1]
0x1803bc929  mov     edi, r13d
0x1803bc92c  shl     rdi, 3
0x1803bc930  mov     rcx, rdi
0x1803bc933  call    THAlloc
0x1803bc938  mov     [rsp+1C8h+var_B0], rax
0x1803bc940  test    rax, rax
0x1803bc943  jz      short loc_1803BC997
0x1803bc945  mov     r8, rdi; Size
0x1803bc948  xor     edx, edx; Val
0x1803bc94a  mov     rbx, rax
0x1803bc94d  mov     rcx, rax; void *
0x1803bc950  call    memset_0
0x1803bc955  mov     rax, [rsp+1C8h+var_70]
0x1803bc95d  mov     [rbx], rax
0x1803bc960  mov     [rsp+1C8h+var_C8], r14d
0x1803bc968  mov     r9d, [rsp+1C8h+var_FC]
0x1803bc970  test    r9d, r9d
0x1803bc973  jz      short loc_1803BC98D
0x1803bc975  mov     r8d, r9d
0x1803bc978  shl     r8, 3; Size
0x1803bc97c  lea     rcx, [rbx+8]; void *
0x1803bc980  mov     rdx, [rsp+1C8h+Src]; Src
0x1803bc988  call    memcpy_0
0x1803bc98d  mov     ebx, r13d
0x1803bc990  mov     [rsp+1C8h+var_C8], ebx
0x1803bc997  cmp     [rsp+1C8h+var_B0], rsi
0x1803bc99f  jnz     short loc_1803BC9B7
0x1803bc9a1  mov     ebx, 0C0000017h
0x1803bc9a6  mov     [rsp+1C8h+var_150], ebx
0x1803bc9aa  mov     r13, qword ptr [rsp+1C8h+var_144+4]
0x1803bc9b2  jmp     loc_1803BD4C8
0x1803bc9b7  mov     edi, esi
0x1803bc9b9  mov     [rsp+1C8h+var_120], esi
0x1803bc9c0  mov     eax, dword ptr [rsp+1C8h+var_110]
0x1803bc9c7  add     eax, ebx
0x1803bc9c9  shl     rax, 3
0x1803bc9cd  mov     [rsp+1C8h+Size], rax
0x1803bc9d5  mov     rcx, rax
0x1803bc9d8  call    THAlloc
0x1803bc9dd  mov     r13, rax
0x1803bc9e0  mov     qword ptr [rsp+1C8h+var_144+4], rax
0x1803bc9e8  test    rax, rax
0x1803bc9eb  jz      short loc_1803BCA5E
0x1803bc9ed  mov     r8, [rsp+1C8h+Size]; Size
0x1803bc9f5  xor     edx, edx; Val
0x1803bc9f7  mov     rcx, rax; void *
0x1803bc9fa  call    memset_0
0x1803bc9ff  test    ebx, ebx
0x1803bca01  jz      short loc_1803BCA1A
0x1803bca03  mov     r8d, ebx
0x1803bca06  shl     r8, 3; Size
0x1803bca0a  mov     rdx, [rsp+1C8h+var_B0]; Src
0x1803bca12  mov     rcx, r13; void *
0x1803bca15  call    memcpy_0
0x1803bca1a  mov     [rsp+1C8h+var_120], ebx
0x1803bca21  mov     eax, dword ptr [rsp+1C8h+var_110]
0x1803bca28  test    eax, eax
0x1803bca2a  jz      short loc_1803BCA54
0x1803bca2c  mov     r8d, eax
0x1803bca2f  shl     r8, 3; Size
0x1803bca33  mov     eax, ebx
0x1803bca35  lea     rcx, ds:0[rax*8]
0x1803bca3d  add     rcx, r13; void *
0x1803bca40  mov     rdx, [rsp+1C8h+var_98]; Src
0x1803bca48  call    memcpy_0
0x1803bca4d  mov     eax, dword ptr [rsp+1C8h+var_110]
0x1803bca54  lea     edi, [rbx+rax]
0x1803bca57  mov     [rsp+1C8h+var_120], edi
0x1803bca5e  test    r13, r13
0x1803bca61  jnz     short loc_1803BCA71
0x1803bca63  mov     ebx, 0C0000017h
0x1803bca68  mov     [rsp+1C8h+var_150], ebx
0x1803bca6c  jmp     loc_1803BD4C8
0x1803bca71  mov     eax, [rsp+1C8h+var_14C]
0x1803bca75  test    eax, eax
0x1803bca77  jz      loc_1803BCBE7
0x1803bca7d  mov     [rsp+1C8h+var_128], esi
0x1803bca84  mov     r8d, eax
0x1803bca87  shl     r8, 3
0x1803bca8b  mov     dword ptr [rsp+1C8h+var_1A0], 1F1F1944h
0x1803bca93  mov     [rsp+1C8h+var_1A8], esi
0x1803bca97  mov     r9d, r14d
0x1803bca9a  mov     rdx, r14
0x1803bca9d  mov     rcx, r12
0x1803bcaa0  call    THAlloc_
0x1803bcaa5  mov     [rsp+1C8h+var_E0], rax
0x1803bcaad  mov     ebx, esi
0x1803bcaaf  mov     [rsp+1C8h+var_A8], ebx
0x1803bcab6  mov     eax, [rsp+1C8h+var_14C]
0x1803bcaba  cmp     ebx, eax
0x1803bcabc  jnb     short loc_1803BCB36
0x1803bcabe  mov     dword ptr [rsp+1C8h+var_1A0], 1F1F1944h
0x1803bcac6  mov     [rsp+1C8h+var_1A8], esi
0x1803bcaca  mov     r9d, r14d
0x1803bcacd  mov     r8d, 3Ah ; ':'
0x1803bcad3  mov     rdx, r14
0x1803bcad6  mov     rcx, r12
0x1803bcad9  call    THAlloc_
0x1803bcade  mov     rdx, [rsp+1C8h+var_E0]
0x1803bcae6  mov     [rdx+rbx*8], rax
0x1803bcaea  mov     dword ptr [rax], 3Ah ; ':'
0x1803bcaf0  mov     r9, [rsp+1C8h+var_D0]
0x1803bcaf8  mov     rcx, [r9+rbx*8]; Sid
0x1803bcafc  call    cs:__imp_RtlLengthSid
0x1803bcb02  mov     rdx, [rsp+1C8h+var_E0]
0x1803bcb0a  mov     rcx, [rdx+rbx*8]
0x1803bcb0e  mov     [rcx+4], eax
0x1803bcb11  mov     rcx, [rdx+rbx*8]
0x1803bcb15  lea     rdx, [rcx+18h]; DestinationSid
0x1803bcb19  mov     rax, [rsp+1C8h+var_D0]
0x1803bcb21  mov     r8, [rax+rbx*8]; SourceSid
0x1803bcb25  mov     ecx, [rcx+4]; DestinationSidLength
0x1803bcb28  call    cs:__imp_RtlCopySid
0x1803bcb2e  add     ebx, r14d
0x1803bcb31  jmp     loc_1803BCAAF
0x1803bcb36  mov     [rsp+1C8h+var_128], esi
0x1803bcb3d  add     eax, edi
0x1803bcb3f  shl     rax, 3
0x1803bcb43  mov     [rsp+1C8h+Size], rax
0x1803bcb4b  mov     rcx, rax
0x1803bcb4e  call    THAlloc
0x1803bcb53  mov     rbx, rax
0x1803bcb56  test    rax, rax
0x1803bcb59  jz      short loc_1803BCBB3
0x1803bcb5b  mov     r8, [rsp+1C8h+Size]; Size
0x1803bcb63  xor     edx, edx; Val
0x1803bcb65  mov     rcx, rax; void *
0x1803bcb68  call    memset_0
0x1803bcb6d  test    edi, edi
0x1803bcb6f  jz      short loc_1803BCB83
0x1803bcb71  mov     r8d, edi
0x1803bcb74  shl     r8, 3; Size
0x1803bcb78  mov     rdx, r13; Src
0x1803bcb7b  mov     rcx, rbx; void *
0x1803bcb7e  call    memcpy_0
0x1803bcb83  mov     [rsp+1C8h+var_128], edi
0x1803bcb8a  mov     r8d, [rsp+1C8h+var_14C]
0x1803bcb8f  shl     r8, 3; Size
0x1803bcb93  mov     eax, edi
0x1803bcb95  lea     rcx, [rbx+rax*8]; void *
0x1803bcb99  mov     rdx, [rsp+1C8h+var_E0]; Src
0x1803bcba1  call    memcpy_0
0x1803bcba6  mov     eax, [rsp+1C8h+var_14C]
0x1803bcbaa  add     eax, edi
0x1803bcbac  mov     [rsp+1C8h+var_128], eax
0x1803bcbb3  mov     [rsp+1C8h+var_1A8], 1F1F1944h
0x1803bcbbb  mov     rdx, r13
0x1803bcbbe  mov     rcx, r12
0x1803bcbc1  call    THFreeAux
0x1803bcbc6  mov     qword ptr [rsp+1C8h+var_144+4], rsi
0x1803bcbce  mov     r13, rbx
0x1803bcbd1  mov     qword ptr [rsp+1C8h+var_144+4], rbx
0x1803bcbd9  mov     edi, [rsp+1C8h+var_128]
0x1803bcbe0  mov     [rsp+1C8h+var_120], edi
0x1803bcbe7  test    r13, r13
0x1803bcbea  jnz     short loc_1803BCBFA
0x1803bcbec  mov     ebx, 0C0000017h
0x1803bcbf1  mov     [rsp+1C8h+var_150], ebx
0x1803bcbf5  jmp     loc_1803BD4C8
0x1803bcbfa  mov     eax, [rsp+1C8h+var_148]
0x1803bcc01  test    eax, eax
0x1803bcc03  jz      loc_1803BCD7C
  ... truncated ...
```
