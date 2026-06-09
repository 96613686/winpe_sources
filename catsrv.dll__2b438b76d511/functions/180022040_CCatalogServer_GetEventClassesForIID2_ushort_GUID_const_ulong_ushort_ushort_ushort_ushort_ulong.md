# CCatalogServer::GetEventClassesForIID2(ushort *,_GUID const &,ulong *,ushort * * *,ushort * * *,ushort * * *,ushort * * *,ulong * *)

- ea: `0x180022040`
- end: `0x1800231e9`
- name: `?GetEventClassesForIID2@CCatalogServer@@UEAAJPEAGAEBU_GUID@@PEAKPEAPEAPEAG333PEAPEAK@Z`
- size: `4521`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, unsigned __int16 *, const struct _GUID *, unsigned int *, unsigned __int16 ***, unsigned __int16 ***, unsigned __int16 ***, unsigned __int16 ***, unsigned int **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004d60`
- `0x180004f48`
- `0x18001ece0`
- `0x1800213b0`
- `0x180021484`
- `0x180022040`
- `0x1800554f6`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800227a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800227e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180022824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002285e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002294d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002304c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800230a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800227a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800227e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180022824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002285e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002294d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002304c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180023089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800230a5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180022403`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180022403`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022255`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022255`

## pseudocode

```c
__int64 __fastcall CCatalogServer::GetEventClassesForIID2(
        CCatalogServer *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned int *a4,
        unsigned __int16 ***a5,
        unsigned __int16 ***a6,
        unsigned __int16 ***a7,
        unsigned __int16 ***a8,
        unsigned int **a9)
{
  int v10; // r15d
  unsigned int v11; // r14d
  unsigned __int64 v12; // rsi
  unsigned __int16 **v13; // r12
  unsigned int *v14; // r13
  unsigned int i; // eax
  int v16; // edi
  unsigned int v17; // eax
  int v18; // eax
  void *v19; // r8
  unsigned int v20; // eax
  unsigned __int64 v21; // rdx
  unsigned int v22; // ecx
  int v23; // r9d
  unsigned __int64 v24; // rax
  char *v25; // rcx
  char *v26; // rcx
  char *v27; // rdi
  unsigned int v28; // ecx
  unsigned __int64 v29; // r8
  unsigned int v30; // edx
  int v31; // r9d
  unsigned __int64 v32; // rax
  unsigned int v33; // ecx
  unsigned int v34; // edi
  unsigned __int16 **v35; // rsi
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // edi
  unsigned __int16 **v41; // rsi
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  unsigned int v46; // edi
  unsigned int *v47; // r10
  LPVOID *v48; // r15
  LPVOID *v49; // r14
  LPVOID *v50; // rsi
  unsigned int *v51; // r13
  LPVOID *v52; // r12
  LPVOID v53; // rax
  UTSemReadWrite *v54; // rcx
  __int64 v55; // [rsp+0h] [rbp-298h] BYREF
  LPVOID *ppv; // [rsp+20h] [rbp-278h]
  HRESULT EventClassData; // [rsp+50h] [rbp-248h]
  __int64 *v58; // [rsp+58h] [rbp-240h]
  unsigned int v59; // [rsp+60h] [rbp-238h] BYREF
  int v60; // [rsp+64h] [rbp-234h] BYREF
  struct ISimpleTableRead *v61; // [rsp+68h] [rbp-230h] BYREF
  unsigned int v62; // [rsp+70h] [rbp-228h]
  __int64 *v63; // [rsp+78h] [rbp-220h] BYREF
  int v64; // [rsp+80h] [rbp-218h]
  LPVOID v65; // [rsp+88h] [rbp-210h]
  _DWORD *v66; // [rsp+90h] [rbp-208h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-200h]
  int v68; // [rsp+A0h] [rbp-1F8h]
  LPVOID v69; // [rsp+A8h] [rbp-1F0h]
  _QWORD *v70; // [rsp+B0h] [rbp-1E8h] BYREF
  LPVOID v71; // [rsp+B8h] [rbp-1E0h] BYREF
  int v72; // [rsp+C0h] [rbp-1D8h] BYREF
  unsigned __int16 **v73; // [rsp+C8h] [rbp-1D0h]
  UTSemReadWrite *v74; // [rsp+D0h] [rbp-1C8h]
  unsigned int *v75; // [rsp+D8h] [rbp-1C0h]
  unsigned __int16 **v76; // [rsp+E0h] [rbp-1B8h]
  unsigned __int16 **v77; // [rsp+E8h] [rbp-1B0h]
  unsigned __int16 **v78; // [rsp+F0h] [rbp-1A8h]
  LPVOID *v79; // [rsp+F8h] [rbp-1A0h]
  LPCOLESTR lpsz; // [rsp+100h] [rbp-198h]
  __int64 v81; // [rsp+108h] [rbp-190h] BYREF
  __int64 v82; // [rsp+110h] [rbp-188h] BYREF
  const struct _GUID *v83; // [rsp+118h] [rbp-180h]
  unsigned int *v84; // [rsp+120h] [rbp-178h]
  int v85; // [rsp+128h] [rbp-170h]
  unsigned __int16 ***v86; // [rsp+130h] [rbp-168h]
  unsigned __int16 ***v87; // [rsp+138h] [rbp-160h]
  unsigned __int16 ***v88; // [rsp+140h] [rbp-158h]
  unsigned int *v89; // [rsp+148h] [rbp-150h]
  unsigned __int16 ***v90; // [rsp+150h] [rbp-148h]
  unsigned __int16 ***v91; // [rsp+158h] [rbp-140h]
  unsigned __int16 ***v92; // [rsp+160h] [rbp-138h]
  unsigned __int16 ***v93; // [rsp+168h] [rbp-130h]
  unsigned int **v94; // [rsp+170h] [rbp-128h]
  int *v95; // [rsp+178h] [rbp-120h] BYREF
  int v96; // [rsp+180h] [rbp-118h]
  int v97; // [rsp+184h] [rbp-114h]
  int v98; // [rsp+188h] [rbp-110h]
  int v99; // [rsp+18Ch] [rbp-10Ch]
  int *v100; // [rsp+190h] [rbp-108h]
  int v101; // [rsp+198h] [rbp-100h]
  int v102; // [rsp+19Ch] [rbp-FCh]
  int v103; // [rsp+1A0h] [rbp-F8h]
  int v104; // [rsp+1A4h] [rbp-F4h]
  char *v105; // [rsp+1A8h] [rbp-F0h]
  char *v106; // [rsp+1B0h] [rbp-E8h]
  char *v107; // [rsp+1B8h] [rbp-E0h]
  unsigned __int16 **v108; // [rsp+1C0h] [rbp-D8h]
  unsigned int *v109; // [rsp+1C8h] [rbp-D0h]
  GUID pclsid; // [rsp+1D0h] [rbp-C8h] BYREF
  GUID *p_pclsid; // [rsp+1E0h] [rbp-B8h] BYREF
  int v112; // [rsp+1E8h] [rbp-B0h]
  int v113; // [rsp+1ECh] [rbp-ACh]
  int v114; // [rsp+1F0h] [rbp-A8h]
  int v115; // [rsp+1F4h] [rbp-A4h]
  const struct _GUID *v116; // [rsp+1F8h] [rbp-A0h]
  int v117; // [rsp+200h] [rbp-98h]
  int v118; // [rsp+204h] [rbp-94h]
  int v119; // [rsp+208h] [rbp-90h]
  int v120; // [rsp+20Ch] [rbp-8Ch]
  int *v121; // [rsp+210h] [rbp-88h]
  int v122; // [rsp+218h] [rbp-80h]
  int v123; // [rsp+21Ch] [rbp-7Ch]
  int v124; // [rsp+220h] [rbp-78h]
  int v125; // [rsp+224h] [rbp-74h]
  __int128 v126; // [rsp+230h] [rbp-68h] BYREF
  __int128 v127; // [rsp+240h] [rbp-58h]

  v58 = &v55;
  v84 = a4;
  v83 = a3;
  lpsz = a2;
  v89 = a4;
  v79 = (LPVOID *)a5;
  v90 = a5;
  v86 = a6;
  v91 = a6;
  v87 = a7;
  v92 = a7;
  v88 = a8;
  v93 = a8;
  v74 = (UTSemReadWrite *)a9;
  v94 = a9;
  EventClassData = 0;
  v59 = 0;
  v63 = 0;
  v61 = 0;
  v71 = 0;
  v81 = 0;
  v70 = 0;
  v82 = 0;
  v126 = 0;
  v127 = 0;
  pclsid = 0;
  v60 = 0;
  v72 = 1;
  v66 = 0;
  if ( !a4 || !a5 || !a6 || !a7 || !a8 || !a9 )
    return 2147942487LL;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  if ( !*((_DWORD *)this + 34) )
    return 2148598828LL;
  v10 = 0;
  v11 = 0;
  v62 = 0;
  pv = 0;
  v65 = 0;
  v12 = 0;
  v69 = 0;
  v13 = 0;
  v14 = 0;
  v73 = 0;
  v78 = 0;
  v77 = 0;
  v76 = 0;
  v75 = 0;
  UTSemReadWrite::LockRead(this);
  v60 = 1;
  for ( i = 1; i <= 2; v60 = i )
  {
    EventClassData = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, &v71);
    if ( EventClassData < 0 )
      local_unwind_0(v58, &loc_1800230E9);
    v96 = 0;
    v97 = -268435451;
    v98 = 19;
    v99 = 4;
    v95 = &v72;
    v101 = 0;
    v102 = 8;
    v103 = 19;
    v104 = 4;
    v100 = &v60;
    v16 = 4194305;
    if ( v60 == 1 )
      v16 = 2097153;
    EventClassData = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, int **, __int64, int, int, struct ISimpleTableRead **))(*(_QWORD *)v71 + 24LL))(
                       v71,
                       didCOMSERVICES,
                       tidCOMSERVICES_CLASSES,
                       &v95,
                       2,
                       1,
                       v16,
                       &v61);
    if ( EventClassData < 0 )
      local_unwind_0(v58, &loc_1800230E9);
    EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v61 + 24LL))(v61);
    if ( EventClassData < 0 )
      local_unwind_0(v58, &loc_1800230E9);
    EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v61 + 32LL))(v61);
    if ( EventClassData < 0 )
      local_unwind_0(v58, &loc_1800230E9);
    if ( lpsz && *lpsz )
    {
      EventClassData = CLSIDFromString(lpsz, &pclsid);
      if ( EventClassData < 0 )
        local_unwind_0(v58, &loc_1800230E9);
      v112 = 0;
      v113 = 3;
      v114 = 72;
      v115 = 16;
      p_pclsid = &pclsid;
      v117 = 0;
      v118 = 1;
      v119 = 72;
      v120 = 16;
      v116 = v83;
      v122 = 0;
      v123 = 4;
      v124 = 19;
      v125 = 4;
      v121 = &v60;
      EventClassData = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int128 *, GUID **, __int64, int, int, __int64 **))(*(_QWORD *)v71 + 24LL))(
                         v71,
                         didCOMSERVICES,
                         &tidCOMSERVICES_CLASSINTERFACE,
                         &p_pclsid,
                         3,
                         1,
                         v16,
                         &v63);
      if ( EventClassData < 0 )
        local_unwind_0(v58, &loc_1800230E9);
      EventClassData = (*(__int64 (__fastcall **)(__int64 *))(*v63 + 24))(v63);
      if ( EventClassData < 0 )
        local_unwind_0(v58, &loc_1800230E9);
      EventClassData = (*(__int64 (__fastcall **)(__int64 *))(*v63 + 32))(v63);
      if ( EventClassData < 0 )
        local_unwind_0(v58, &loc_1800230E9);
      EventClassData = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*v63 + 72))(
                         v63,
                         0,
                         0,
                         0,
                         0,
                         0,
                         0,
                         &v59,
                         0);
      if ( EventClassData < 0 )
        local_unwind_0(v58, &loc_1800230E9);
    }
    else
    {
      EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v61 + 72LL))(
                         v61,
                         0,
                         0,
                         0,
                         0,
                         0,
                         0,
                         &v59,
                         0);
      if ( EventClassData < 0 )
      {
        v17 = local_unwind_0(v58, &loc_1800230E9);
        goto LABEL_37;
      }
    }
    v17 = v59;
    if ( !v59 )
    {
      v18 = v60;
      goto LABEL_100;
    }
LABEL_37:
    v19 = pv;
    v73 = (unsigned __int16 **)pv;
    v78 = (unsigned __int16 **)v65;
    v77 = (unsigned __int16 **)v12;
    v76 = v13;
    v75 = v14;
    v62 = v11;
    v20 = v11 + v17;
    v21 = 0xFFFFFFFFLL;
    v22 = -1;
    if ( v20 >= v11 )
      v22 = v20;
    v23 = -2147024362;
    EventClassData = v20 < v11 ? 0x80070216 : 0;
    if ( v20 < v11 )
      local_unwind_0(v58, &loc_1800230E9);
    v24 = 8LL * v22;
    v12 = 8 * v22;
    if ( v24 > v21 )
      v12 = (unsigned int)v21;
    EventClassData = v21 < v24 ? v23 : 0;
    if ( EventClassData < 0 )
      local_unwind_0(v58, &loc_1800230E9);
    v25 = (char *)CoTaskMemRealloc(v19, (unsigned int)v12);
    pv = v25;
    v105 = v25;
    if ( v25 )
      memset_0(&v25[8 * v11], 0, 8LL * v59);
    v26 = (char *)CoTaskMemRealloc(v65, (unsigned int)v12);
    v65 = v26;
    v106 = v26;
    if ( v26 )
      memset_0(&v26[8 * v11], 0, 8LL * v59);
    v27 = (char *)CoTaskMemRealloc(v69, (unsigned int)v12);
    v69 = v27;
    v107 = v27;
    if ( v27 )
      memset_0(&v27[8 * v11], 0, 8LL * v59);
    v13 = (unsigned __int16 **)CoTaskMemRealloc(v13, (unsigned int)v12);
    v108 = v13;
    if ( v13 )
      memset_0(&v13[v11], 0, 8LL * v59);
    v28 = v11 + v59;
    v29 = 0xFFFFFFFFLL;
    v30 = -1;
    if ( v11 + v59 >= v11 )
      v30 = v11 + v59;
    v31 = -2147024362;
    EventClassData = v28 < v11 ? 0x80070216 : 0;
    if ( v28 < v11 )
      local_unwind_0(v58, &loc_1800230E9);
    v32 = 4LL * v30;
    v33 = 4 * v30;
    if ( v32 > v29 )
      v33 = v29;
    EventClassData = v29 < v32 ? v31 : 0;
    if ( EventClassData < 0 )
      local_unwind_0(v58, &loc_1800230E9);
    v14 = (unsigned int *)CoTaskMemRealloc(v14, v33);
    v109 = v14;
    if ( v14 )
      memset_0(&v14[v11], 0, 4LL * v59);
    if ( !pv || !v65 || !v27 || !v13 || !v14 )
    {
      EventClassData = -2147024882;
      local_unwind_0(v58, &loc_1800230E9);
      break;
    }
    v73 = (unsigned __int16 **)pv;
    v78 = (unsigned __int16 **)v65;
    v77 = (unsigned __int16 **)v27;
    v76 = v13;
    v75 = v14;
    if ( lpsz && *lpsz )
    {
      v34 = 0;
      v64 = 0;
      v35 = (unsigned __int16 **)v69;
      while ( v34 < v59 )
      {
        EventClassData = (*(__int64 (__fastcall **)(__int64 *))(*v63 + 40))(v63);
        if ( EventClassData < 0 )
          local_unwind_0(v58, &loc_1800230E9);
        EventClassData = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *))(*v63 + 64))(
                           v63,
                           0,
                           0,
                           0,
                           &v81);
        if ( EventClassData < 0 )
          local_unwind_0(v58, &loc_1800230E9);
        v36 = *v63;
        ppv = (LPVOID *)&v70;
        EventClassData = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v36 + 64))(v63, 1, 0);
        if ( EventClassData < 0 )
          local_unwind_0(v58, &loc_1800230E9);
        v37 = *v63;
        ppv = (LPVOID *)&v82;
        EventClassData = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v37 + 64))(v63, 2, 0);
        if ( EventClassData < 0 )
          local_unwind_0(v58, &loc_1800230E9);
        *(_QWORD *)&v126 = v81;
        *((_QWORD *)&v126 + 1) = v70;
        *(_QWORD *)&v127 = v82;
        *((_QWORD *)&v127 + 1) = &v60;
        EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, __int128 *))(*(_QWORD *)v61 + 56LL))(
                           v61,
                           0,
                           &v126);
        if ( EventClassData )
        {
          if ( EventClassData != -2146367487 )
          {
            local_unwind_0(v58, &loc_1800230E9);
            goto LABEL_93;
          }
          EventClassData = 0;
        }
        else
        {
          v38 = *(_QWORD *)v61;
          ppv = (LPVOID *)&v66;
          EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(v38 + 64))(
                             v61,
                             43,
                             0);
          if ( EventClassData < 0 )
            local_unwind_0(v58, &loc_1800230E9);
          if ( !v66 )
          {
            EventClassData = -2147418113;
            local_unwind_0(v58, &loc_1800230E9);
          }
          if ( *v66 )
          {
            v39 = v11 + v10;
            v62 = v39 + 1;
            EventClassData = CCatalogServer::ExtractEventClassData(
                               (CCatalogServer *)&v13[v39],
                               v61,
                               (unsigned __int16 **)pv + v39,
                               (unsigned __int16 **)v65 + v39,
                               &v35[v39],
                               &v13[v39],
                               &v14[v39]);
            if ( EventClassData < 0 )
              local_unwind_0(v58, &loc_1800230E9);
            v68 = ++v10;
          }
        }
        v64 = ++v34;
      }
    }
    else
    {
LABEL_93:
      v40 = 0;
      v64 = 0;
      v41 = (unsigned __int16 **)v69;
      while ( v40 < v59 )
      {
        EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v61 + 40LL))(v61);
        if ( EventClassData == -2146367487 )
        {
          EventClassData = 0;
          break;
        }
        if ( EventClassData < 0 )
          local_unwind_0(v58, &loc_1800230E9);
        v42 = *(_QWORD *)v61;
        ppv = (LPVOID *)&v66;
        EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(v42 + 64))(v61, 43, 0);
        if ( EventClassData < 0 )
          local_unwind_0(v58, &loc_1800230E9);
        if ( !v66 )
        {
          EventClassData = -2147418113;
          local_unwind_0(v58, &loc_1800230E9);
        }
        if ( *v66 )
        {
          v43 = *(_QWORD *)v61;
          ppv = (LPVOID *)&v70;
          EventClassData = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(v43 + 64))(v61, 6, 0);
          if ( EventClassData < 0 )
            local_unwind_0(v58, &loc_1800230E9);
          v44 = *(_QWORD *)&v83->Data1 - *v70;
          if ( *(_QWORD *)&v83->Data1 == *v70 )
            v44 = *(_QWORD *)v83->Data4 - v70[1];
          if ( !v44 )
          {
            v45 = v11 + v10;
            v62 = v45 + 1;
            EventClassData = CCatalogServer::ExtractEventClassData(
                               (CCatalogServer *)&v13[v45],
                               v61,
                               (unsigned __int16 **)pv + v45,
                               (unsigned __int16 **)v65 + v45,
                               &v41[v45],
                               &v13[v45],
                               &v14[v45]);
            if ( EventClassData < 0 )
              local_unwind_0(v58, &loc_1800230E9);
            v68 = ++v10;
          }
        }
        v64 = ++v40;
      }
    }
    v18 = v60;
    if ( v60 == 1 )
    {
      v11 = v10;
      v85 = v10;
      v10 = 0;
      v68 = 0;
    }
    v12 = (unsigned __int64)v69;
LABEL_100:
    i = v18 + 1;
  }
  v46 = v11 + v10;
  v47 = v84;
  *v84 = v11 + v10;
  *v79 = pv;
  v48 = (LPVOID *)v86;
  *v86 = (unsigned __int16 **)v65;
  v49 = (LPVOID *)v87;
  *v87 = (unsigned __int16 **)v12;
  v50 = (LPVOID *)v88;
  *v88 = v13;
  *(_QWORD *)v74 = v14;
  v51 = v47;
  v52 = v79;
  *v52 = CoTaskMemRealloc(*v79, 8LL * *v47);
  *v48 = CoTaskMemRealloc(*v48, 8LL * *v51);
  *v49 = CoTaskMemRealloc(*v49, 8LL * *v51);
  *v50 = CoTaskMemRealloc(*v50, 8LL * *v51);
  v53 = CoTaskMemRealloc(*(LPVOID *)v74, 4LL * *v51);
  v54 = v74;
  *(_QWORD *)v74 = v53;
  if ( *v51 && (!*v52 || !*v48 || !*v49 || !*v50 || !v53) )
  {
    v62 = v46;
    EventClassData = -2147024882;
  }
  UTSemReadWrite::UnlockRead(v54);
  if ( EventClassData < 0 )
  {
    CleanupMemoryForGetEventClasses(v73, v78, v77, v76, v75, v62);
    *v89 = 0;
    *v90 = 0;
    *v91 = 0;
    *v92 = 0;
    *v93 = 0;
    *v94 = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
    v63 = 0;
  }
  if ( v61 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v71 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v71 + 16LL))(v71);
  return (unsigned int)EventClassData;
}

```

## disassembly

```asm
0x180022040  push    rbx
0x180022042  push    rsi
0x180022043  push    rdi
0x180022044  push    r12
0x180022046  push    r13
0x180022048  push    r14
0x18002204a  push    r15
0x18002204c  sub     rsp, 260h
0x180022053  mov     rax, cs:__security_cookie
0x18002205a  xor     rax, rsp
0x18002205d  mov     [rsp+298h+var_48], rax
0x180022065  mov     [rsp+298h+var_240], rsp
0x18002206a  mov     r10, r9
0x18002206d  mov     [rsp+298h+var_178], r9
0x180022075  mov     [rsp+298h+var_180], r8
0x18002207d  mov     [rsp+298h+lpsz], rdx
0x180022085  mov     [rsp+298h+var_150], r9
0x18002208d  mov     r9, [rsp+298h+arg_20]
0x180022095  mov     [rsp+298h+var_1A0], r9
0x18002209d  mov     [rsp+298h+var_148], r9
0x1800220a5  mov     r8, [rsp+298h+arg_28]
0x1800220ad  mov     [rsp+298h+var_168], r8
0x1800220b5  mov     [rsp+298h+var_140], r8
0x1800220bd  mov     rdx, [rsp+298h+arg_30]
0x1800220c5  mov     [rsp+298h+var_160], rdx
0x1800220cd  mov     [rsp+298h+var_138], rdx
0x1800220d5  mov     rax, [rsp+298h+arg_38]
0x1800220dd  mov     [rsp+298h+var_158], rax
0x1800220e5  mov     [rsp+298h+var_130], rax
0x1800220ed  mov     r11, [rsp+298h+arg_40]
0x1800220f5  mov     [rsp+298h+var_1C8], r11
0x1800220fd  mov     [rsp+298h+var_128], r11
0x180022105  xor     ebx, ebx
0x180022107  mov     [rsp+298h+var_248], ebx
0x18002210b  mov     [rsp+298h+var_238], ebx
0x18002210f  mov     [rsp+298h+var_220], rbx
0x180022114  mov     [rsp+298h+var_230], rbx
0x180022119  mov     [rsp+298h+var_1E0], rbx
0x180022121  mov     [rsp+298h+var_190], rbx
0x180022129  mov     [rsp+298h+var_1E8], rbx
0x180022131  mov     [rsp+298h+var_188], rbx
0x180022139  xorps   xmm0, xmm0
0x18002213c  movups  [rsp+298h+var_68], xmm0
0x180022144  movups  [rsp+298h+var_58], xmm0
0x18002214c  movups  xmmword ptr [rsp+298h+pclsid.Data1], xmm0
0x180022154  mov     [rsp+298h+var_234], ebx
0x180022158  mov     [rsp+298h+var_1D8], 1
0x180022163  mov     [rsp+298h+var_208], rbx
0x18002216b  test    r10, r10
0x18002216e  jz      loc_1800231C1
0x180022174  test    r9, r9
0x180022177  jz      loc_1800231C1
0x18002217d  test    r8, r8
0x180022180  jz      loc_1800231C1
0x180022186  test    rdx, rdx
0x180022189  jz      loc_1800231C1
0x18002218f  test    rax, rax
0x180022192  jz      loc_1800231C1
0x180022198  test    r11, r11
0x18002219b  jz      loc_1800231C1
0x1800221a1  mov     [r10], ebx
0x1800221a4  mov     [r9], rbx
0x1800221a7  mov     [r8], rbx
0x1800221aa  mov     [rdx], rbx
0x1800221ad  mov     [rax], rbx
0x1800221b0  mov     [r11], rbx
0x1800221b3  cmp     [rcx+88h], ebx
0x1800221b9  jnz     short loc_1800221C5
0x1800221bb  mov     eax, 8011042Ch
0x1800221c0  jmp     loc_1800231C6
0x1800221c5  mov     r15d, ebx
0x1800221c8  mov     r14d, ebx
0x1800221cb  mov     [rsp+298h+var_228], ebx
0x1800221cf  mov     [rsp+298h+pv], rbx
0x1800221d7  mov     [rsp+298h+var_210], rbx
0x1800221df  mov     rsi, rbx
0x1800221e2  mov     [rsp+298h+var_1F0], rbx
0x1800221ea  mov     r12, rbx
0x1800221ed  mov     r13, rbx
0x1800221f0  mov     [rsp+298h+var_1D0], rbx
0x1800221f8  mov     [rsp+298h+var_1A8], rbx
0x180022200  mov     [rsp+298h+var_1B0], rbx
0x180022208  mov     [rsp+298h+var_1B8], rbx
0x180022210  mov     [rsp+298h+var_1C0], rbx
0x180022218  call    ?LockRead@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::LockRead(void)
0x18002221d  nop
0x18002221e  mov     [rsp+298h+var_234], 1
0x180022226  mov     eax, 1
0x18002222b  cmp     eax, 2
0x18002222e  ja      loc_180022FE0
0x180022234  lea     rax, [rsp+298h+var_1E0]
0x18002223c  mov     [rsp+298h+ppv], rax; ppv
0x180022241  lea     r9, IID_ISimpleTableDispenser; riid
0x180022248  xor     edx, edx; pUnkOuter
0x18002224a  lea     r8d, [rdx+1]; dwClsContext
0x18002224e  lea     rcx, clsidSTDISP; rclsid
0x180022255  call    cs:__imp_CoCreateInstance
0x18002225b  mov     [rsp+298h+var_248], eax
0x18002225f  mov     eax, [rsp+298h+var_248]
0x180022263  test    eax, eax
0x180022265  jns     short loc_18002229D
0x180022267  mov     eax, [rsp+298h+var_248]
0x18002226b  cmp     eax, 8007000Eh
0x180022270  jz      short loc_18002228C
0x180022272  mov     eax, [rsp+298h+var_248]
0x180022276  cmp     eax, 800705AFh
0x18002227b  jz      short loc_18002228C
0x18002227d  mov     eax, [rsp+298h+var_248]
0x180022281  cmp     eax, 8007045Bh
0x180022286  jz      short loc_18002228C
0x180022288  mov     eax, [rsp+298h+var_248]
0x18002228c  lea     rdx, loc_1800230E9
0x180022293  mov     rcx, [rsp+298h+var_240]
0x180022298  call    _local_unwind_0
0x18002229d  mov     [rsp+298h+var_118], ebx
0x1800222a4  mov     [rsp+298h+var_114], 0F0000005h
0x1800222af  mov     [rsp+298h+var_110], 13h
0x1800222ba  mov     [rsp+298h+var_10C], 4
0x1800222c5  lea     rax, [rsp+298h+var_1D8]
0x1800222cd  mov     [rsp+298h+var_120], rax
0x1800222d5  mov     [rsp+298h+var_100], ebx
0x1800222dc  mov     [rsp+298h+var_FC], 8
0x1800222e7  mov     [rsp+298h+var_F8], 13h
0x1800222f2  mov     [rsp+298h+var_F4], 4
0x1800222fd  lea     rax, [rsp+298h+var_234]
0x180022302  mov     [rsp+298h+var_108], rax
0x18002230a  mov     edi, 400001h
0x18002230f  mov     eax, 200001h
0x180022314  cmp     [rsp+298h+var_234], 1
0x180022319  cmovz   edi, eax
0x18002231c  mov     rcx, [rsp+298h+var_1E0]
0x180022324  mov     rax, [rcx]
0x180022327  lea     rdx, [rsp+298h+var_230]
0x18002232c  mov     [rsp+298h+var_260], rdx
0x180022331  mov     dword ptr [rsp+298h+var_268], edi
0x180022335  mov     dword ptr [rsp+298h+var_270], 1
0x18002233d  mov     [rsp+298h+ppv], 2
0x180022346  lea     r9, [rsp+298h+var_120]
0x18002234e  lea     r8, tidCOMSERVICES_CLASSES
0x180022355  lea     rdx, didCOMSERVICES
0x18002235c  mov     rax, [rax+18h]
0x180022360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022365  mov     [rsp+298h+var_248], eax
0x180022369  mov     eax, [rsp+298h+var_248]
0x18002236d  test    eax, eax
0x18002236f  jns     short loc_180022382
0x180022371  lea     rdx, loc_1800230E9
0x180022378  mov     rcx, [rsp+298h+var_240]
0x18002237d  call    _local_unwind_0
0x180022382  mov     rcx, [rsp+298h+var_230]
0x180022387  mov     rax, [rcx]
0x18002238a  mov     rax, [rax+18h]
0x18002238e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022393  mov     [rsp+298h+var_248], eax
0x180022397  mov     eax, [rsp+298h+var_248]
0x18002239b  test    eax, eax
0x18002239d  jns     short loc_1800223B0
0x18002239f  lea     rdx, loc_1800230E9
0x1800223a6  mov     rcx, [rsp+298h+var_240]
0x1800223ab  call    _local_unwind_0
0x1800223b0  mov     rcx, [rsp+298h+var_230]
0x1800223b5  mov     rax, [rcx]
0x1800223b8  mov     rax, [rax+20h]
0x1800223bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223c1  mov     [rsp+298h+var_248], eax
0x1800223c5  mov     eax, [rsp+298h+var_248]
0x1800223c9  test    eax, eax
0x1800223cb  jns     short loc_1800223DE
0x1800223cd  lea     rdx, loc_1800230E9
0x1800223d4  mov     rcx, [rsp+298h+var_240]
0x1800223d9  call    _local_unwind_0
0x1800223de  mov     rax, [rsp+298h+lpsz]
0x1800223e6  test    rax, rax
0x1800223e9  jz      loc_180022631
0x1800223ef  cmp     [rax], bx
0x1800223f2  jz      loc_180022631
0x1800223f8  lea     rdx, [rsp+298h+pclsid]; pclsid
0x180022400  mov     rcx, rax; lpsz
0x180022403  call    cs:__imp_CLSIDFromString
0x180022409  mov     [rsp+298h+var_248], eax
0x18002240d  mov     eax, [rsp+298h+var_248]
0x180022411  test    eax, eax
0x180022413  jns     short loc_180022426
0x180022415  lea     rdx, loc_1800230E9
0x18002241c  mov     rcx, [rsp+298h+var_240]
0x180022421  call    _local_unwind_0
0x180022426  mov     [rsp+298h+var_B0], ebx
0x18002242d  mov     r8d, 3
0x180022433  mov     [rsp+298h+var_AC], r8d
0x18002243b  lea     ecx, [r8+45h]
0x18002243f  mov     [rsp+298h+var_A8], ecx
0x180022446  lea     edx, [rcx-38h]
0x180022449  mov     [rsp+298h+var_A4], edx
0x180022450  lea     rax, [rsp+298h+pclsid]
0x180022458  mov     [rsp+298h+var_B8], rax
0x180022460  mov     [rsp+298h+var_98], ebx
0x180022467  mov     [rsp+298h+var_94], 1
0x180022472  mov     [rsp+298h+var_90], ecx
0x180022479  mov     [rsp+298h+var_8C], edx
0x180022480  mov     rax, [rsp+298h+var_180]
0x180022488  mov     [rsp+298h+var_A0], rax
0x180022490  mov     [rsp+298h+var_80], ebx
0x180022497  lea     eax, [rcx-44h]
0x18002249a  mov     [rsp+298h+var_7C], eax
0x1800224a1  mov     [rsp+298h+var_78], 13h
0x1800224ac  mov     [rsp+298h+var_74], eax
0x1800224b3  lea     rax, [rsp+298h+var_234]
0x1800224b8  mov     [rsp+298h+var_88], rax
0x1800224c0  mov     rcx, [rsp+298h+var_1E0]
0x1800224c8  mov     rax, [rcx]
0x1800224cb  lea     rdx, [rsp+298h+var_220]
0x1800224d0  mov     [rsp+298h+var_260], rdx
0x1800224d5  mov     dword ptr [rsp+298h+var_268], edi
0x1800224d9  mov     dword ptr [rsp+298h+var_270], 1
0x1800224e1  mov     [rsp+298h+ppv], r8
0x1800224e6  lea     r9, [rsp+298h+var_B8]
0x1800224ee  lea     r8, tidCOMSERVICES_CLASSINTERFACE
0x1800224f5  lea     rdx, didCOMSERVICES
0x1800224fc  mov     rax, [rax+18h]
0x180022500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022505  mov     [rsp+298h+var_248], eax
0x180022509  mov     eax, [rsp+298h+var_248]
0x18002250d  test    eax, eax
0x18002250f  jns     short loc_180022522
0x180022511  lea     rdx, loc_1800230E9
0x180022518  mov     rcx, [rsp+298h+var_240]
0x18002251d  call    _local_unwind_0
0x180022522  mov     rcx, [rsp+298h+var_220]
0x180022527  mov     rax, [rcx]
0x18002252a  mov     rax, [rax+18h]
0x18002252e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022533  mov     [rsp+298h+var_248], eax
0x180022537  mov     eax, [rsp+298h+var_248]
0x18002253b  test    eax, eax
0x18002253d  jns     short loc_180022550
0x18002253f  lea     rdx, loc_1800230E9
0x180022546  mov     rcx, [rsp+298h+var_240]
0x18002254b  call    _local_unwind_0
0x180022550  mov     rcx, [rsp+298h+var_220]
0x180022555  mov     rax, [rcx]
0x180022558  mov     rax, [rax+20h]
0x18002255c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022561  mov     [rsp+298h+var_248], eax
0x180022565  mov     eax, [rsp+298h+var_248]
0x180022569  test    eax, eax
0x18002256b  jns     short loc_1800225A3
0x18002256d  mov     eax, [rsp+298h+var_248]
0x180022571  cmp     eax, 8007000Eh
0x180022576  jz      short loc_180022592
0x180022578  mov     eax, [rsp+298h+var_248]
0x18002257c  cmp     eax, 800705AFh
0x180022581  jz      short loc_180022592
0x180022583  mov     eax, [rsp+298h+var_248]
0x180022587  cmp     eax, 8007045Bh
0x18002258c  jz      short loc_180022592
0x18002258e  mov     eax, [rsp+298h+var_248]
0x180022592  lea     rdx, loc_1800230E9
0x180022599  mov     rcx, [rsp+298h+var_240]
0x18002259e  call    _local_unwind_0
0x1800225a3  mov     rcx, [rsp+298h+var_220]
0x1800225a8  mov     rax, [rcx]
0x1800225ab  mov     [rsp+298h+var_258], rbx
0x1800225b0  lea     rdx, [rsp+298h+var_238]
0x1800225b5  mov     [rsp+298h+var_260], rdx
0x1800225ba  mov     [rsp+298h+var_268], rbx
0x1800225bf  mov     [rsp+298h+var_270], rbx
0x1800225c4  mov     [rsp+298h+ppv], rbx
0x1800225c9  xor     r9d, r9d
0x1800225cc  xor     r8d, r8d
0x1800225cf  xor     edx, edx
0x1800225d1  mov     rax, [rax+48h]
0x1800225d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225da  mov     [rsp+298h+var_248], eax
0x1800225de  mov     eax, [rsp+298h+var_248]
0x1800225e2  test    eax, eax
0x1800225e4  jns     short loc_18002261C
0x1800225e6  mov     eax, [rsp+298h+var_248]
0x1800225ea  cmp     eax, 8007000Eh
0x1800225ef  jz      short loc_18002260B
0x1800225f1  mov     eax, [rsp+298h+var_248]
0x1800225f5  cmp     eax, 800705AFh
0x1800225fa  jz      short loc_18002260B
0x1800225fc  mov     eax, [rsp+298h+var_248]
0x180022600  cmp     eax, 8007045Bh
0x180022605  jz      short loc_18002260B
0x180022607  mov     eax, [rsp+298h+var_248]
0x18002260b  lea     rdx, loc_1800230E9
0x180022612  mov     rcx, [rsp+298h+var_240]
0x180022617  call    _local_unwind_0
0x18002261c  mov     eax, [rsp+298h+var_238]
0x180022620  test    eax, eax
0x180022622  jnz     loc_1800226AA
0x180022628  mov     eax, [rsp+298h+var_234]
0x18002262c  jmp     loc_180022DC2
0x180022631  mov     rcx, [rsp+298h+var_230]
0x180022636  mov     rax, [rcx]
0x180022639  mov     [rsp+298h+var_258], rbx
0x18002263e  lea     rdx, [rsp+298h+var_238]
0x180022643  mov     [rsp+298h+var_260], rdx
0x180022648  mov     [rsp+298h+var_268], rbx
  ... truncated ...
```
