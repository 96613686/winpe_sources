# CAppImport::UpdateClassTable(_GUID const &,_GUID const &,ushort *,ulong,CArray<CompInfo *,CompInfo * const &> *)

- ea: `0x180011d74`
- end: `0x180012f4d`
- name: `?UpdateClassTable@CAppImport@@AEAAJAEBU_GUID@@0PEAGKPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@@Z`
- size: `4569`
- prototype: `__int64 __usercall@<rax>(CAppImport *this@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18003caa0`

## callees

- `0x180009098`
- `0x18000fb94`
- `0x180011d74`
- `0x18001a6c8`
- `0x180030140`
- `0x18003f538`
- `0x180041ae4`
- `0x180055502`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180011e47`
- `CLBCatQ!GetSimpleTableDispenser` at `0x1800123bb`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18001279d`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180012993`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180011e47`
- `CLBCatQ!GetSimpleTableDispenser` at `0x1800123bb`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18001279d`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180012993`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012d02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012d02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011f2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011f2c`

## string_xrefs

- `0x1800121db`: `com\complus\src\comcat\import\appimport.cpp`

## pseudocode

```c
__int64 __fastcall CAppImport::UpdateClassTable(
        CAppImport *this,
        __int64 a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rdi
  int v7; // r15d
  _QWORD *v9; // r12
  int v10; // eax
  __int64 v11; // r10
  int SimpleTableDispenser; // ebx
  int v13; // eax
  int v14; // eax
  int v15; // edx
  __int64 v16; // r8
  __int64 v17; // rax
  unsigned int v18; // esi
  bool v19; // zf
  int v20; // r14d
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdi
  int v24; // ebx
  int v25; // eax
  unsigned __int64 v26; // rdi
  int v27; // ebx
  int v28; // esi
  bool v29; // cf
  struct _GUID **v30; // r14
  struct _GUID *v31; // r9
  __int64 v32; // rcx
  __int64 v33; // r14
  unsigned int v34; // edi
  unsigned int v35; // esi
  int v36; // eax
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v40; // r8
  unsigned int i; // esi
  __int64 j; // rax
  int v43; // eax
  unsigned __int16 *v44; // r14
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v46; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  struct ISimpleTableRead *v48; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h] BYREF
  int v50; // [rsp+70h] [rbp-90h]
  int v51; // [rsp+74h] [rbp-8Ch]
  unsigned int *v52; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v53; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *v54; // [rsp+88h] [rbp-78h] BYREF
  int v55; // [rsp+90h] [rbp-70h] BYREF
  int v56; // [rsp+94h] [rbp-6Ch] BYREF
  int v57; // [rsp+98h] [rbp-68h] BYREF
  _WORD *v58; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h] BYREF
  _WORD *v62; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v63; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v64; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID *v65; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v66; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v67; // [rsp+E8h] [rbp-18h] BYREF
  int v68; // [rsp+F0h] [rbp-10h]
  int v69; // [rsp+F4h] [rbp-Ch]
  int v70; // [rsp+F8h] [rbp-8h]
  int v71; // [rsp+FCh] [rbp-4h]
  __int64 v72; // [rsp+100h] [rbp+0h]
  int v73; // [rsp+108h] [rbp+8h]
  int v74; // [rsp+10Ch] [rbp+Ch]
  int v75; // [rsp+110h] [rbp+10h]
  int v76; // [rsp+114h] [rbp+14h]
  struct _GUID v77; // [rsp+120h] [rbp+20h] BYREF
  GUID Buf2; // [rsp+130h] [rbp+30h] BYREF
  GUID *v79; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v80; // [rsp+148h] [rbp+48h]
  int v81; // [rsp+150h] [rbp+50h]
  int v82; // [rsp+154h] [rbp+54h]
  GUID *v83; // [rsp+158h] [rbp+58h]
  __int64 v84; // [rsp+160h] [rbp+60h]
  int v85; // [rsp+168h] [rbp+68h]
  int v86; // [rsp+16Ch] [rbp+6Ch]
  GUID *v87; // [rsp+170h] [rbp+70h]
  int v88; // [rsp+178h] [rbp+78h]
  int v89; // [rsp+17Ch] [rbp+7Ch]
  int v90; // [rsp+180h] [rbp+80h]
  int v91; // [rsp+184h] [rbp+84h]
  GUID *v92; // [rsp+188h] [rbp+88h]
  int v93; // [rsp+190h] [rbp+90h]
  int v94; // [rsp+194h] [rbp+94h]
  int v95; // [rsp+198h] [rbp+98h]
  int v96; // [rsp+19Ch] [rbp+9Ch]
  __int128 v97; // [rsp+1A0h] [rbp+A0h]
  __int64 v98; // [rsp+1B0h] [rbp+B0h]
  GUID *p_Buf2; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v100; // [rsp+1C8h] [rbp+C8h]
  __int128 v101; // [rsp+1D0h] [rbp+D0h]
  __int64 v102; // [rsp+1E0h] [rbp+E0h]
  int v103; // [rsp+1E8h] [rbp+E8h]
  int v104; // [rsp+1ECh] [rbp+ECh]
  GUID *v105; // [rsp+1F0h] [rbp+F0h]
  int v106; // [rsp+1F8h] [rbp+F8h]
  int v107; // [rsp+1FCh] [rbp+FCh]
  int v108; // [rsp+200h] [rbp+100h]
  int v109; // [rsp+204h] [rbp+104h]
  unsigned int *v110; // [rsp+208h] [rbp+108h]
  int v111; // [rsp+210h] [rbp+110h]
  int v112; // [rsp+214h] [rbp+114h]
  int v113; // [rsp+218h] [rbp+118h]
  int v114; // [rsp+21Ch] [rbp+11Ch]

  v6 = a6;
  v7 = 0;
  v66 = a4;
  v65 = a3;
  Buf2 = GUID_NULL;
  v60 = a6;
  v47 = 0;
  v9 = 0;
  v49 = 0;
  v55 = 0;
  v56 = 1;
  v63 = 0;
  v67 = a4;
  v68 = 0;
  v69 = -268435455;
  v70 = 130;
  v10 = safe_lstrlenW(a4);
  v72 = v11;
  v73 = 0;
  v74 = 9;
  v75 = 72;
  v71 = 2 * v10 + 2;
  v76 = 16;
  v48 = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    v53 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v53);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_6;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, (signed __int64)v53, 0) )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v53 + 16LL))(v53);
  }
  v13 = memcmp_0(tidCOMSERVICES_CLASSES_EXPORT, &TID_APPLICATION, 0x10u);
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, struct ISimpleTableRead **))(**((_QWORD **)this + 9) + 24LL))(
                           *((_QWORD *)this + 9),
                           didCOMSERVICES,
                           tidCOMSERVICES_CLASSES_EXPORT,
                           &v67,
                           2,
                           1,
                           v13 != 0 ? 7 : 5,
                           &v48);
LABEL_6:
  if ( SimpleTableDispenser )
    goto LABEL_133;
  if ( !v48 )
    goto LABEL_8;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v48 + 24LL))(v48);
  if ( !SimpleTableDispenser )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v48 + 32LL))(v48);
    if ( !SimpleTableDispenser )
    {
      v9 = CoTaskMemAlloc(0x228u);
      if ( !v9 )
      {
LABEL_8:
        SimpleTableDispenser = -2147024882;
        goto LABEL_133;
      }
      v51 = 0;
LABEL_13:
      v45 = 0;
      Buf2 = GUID_NULL;
      v46 = 0;
      v57 = 0;
      v54 = 0;
      v64 = 0;
      v47 = 0;
      v61 = 0;
      v53 = 0;
      v58 = 0;
      v62 = 0;
      v52 = 0;
      v59 = 0;
      v14 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v48 + 40LL))(v48);
      SimpleTableDispenser = v14;
      if ( v14 == -2146367487 )
      {
        SimpleTableDispenser = 0;
        goto LABEL_141;
      }
      if ( v14 )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, int *, unsigned int *, struct _GUID **))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               0,
                               &v45,
                               &v46,
                               &v54);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      v15 = 0;
      Buf2 = *v54;
      while ( v15 < *(_DWORD *)(v6 + 16) )
      {
        v16 = *(_QWORD *)(*(_QWORD *)(v6 + 8) + 8LL * v15);
        v17 = *(_QWORD *)v16 - *(_QWORD *)&Buf2.Data1;
        if ( *(_QWORD *)v16 == *(_QWORD *)&Buf2.Data1 )
          v17 = *(_QWORD *)(v16 + 8) - *(_QWORD *)Buf2.Data4;
        if ( !v17 && (*(_DWORD *)(v16 + 36) & 0x1000) != 0 )
          goto LABEL_13;
        ++v15;
      }
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, unsigned int **))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               8,
                               &v45,
                               &v46,
                               &v52);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, unsigned __int16 **))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               3,
                               &v45,
                               &v46,
                               &v53);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, __int64 *))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               2,
                               &v45,
                               &v46,
                               &v59);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, struct _GUID **))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               10,
                               &v45,
                               &v46,
                               &v54);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      if ( v54 )
      {
        v77 = 0;
        v77 = *v54;
        SimpleTableDispenser = FixupAliasedComponent(
                                 *((struct ISimpleTableDispenser **)this + 9),
                                 &Buf2,
                                 v53,
                                 &v77,
                                 (const struct _GUID *)this + 6,
                                 v48,
                                 *v52);
        if ( SimpleTableDispenser )
          goto LABEL_133;
      }
      v18 = *v52;
      v45 = 0;
      v46 = 0;
      v54 = 0;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, struct _GUID **))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               30,
                               &v45,
                               &v46,
                               &v54);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      v19 = (v54->Data1 & 0x1000) == 0;
      v20 = v54->Data1 & 0x1000;
      v50 = v20;
      if ( v19 )
      {
        if ( memcmp_0((char *)this + 96, &GUID_DefaultAppPartition, (unsigned int)(SimpleTableDispenser + 16)) )
        {
          LODWORD(p_Buf2) = 0;
          WORD2(p_Buf2) = SimpleTableDispenser + 22;
          LODWORD(v100) = -1073736960;
          v102 = 0;
          v103 = 0;
          v104 = 1;
          v101 = 0;
          CError::WriteToLog((CError *)&p_Buf2, L"com\\complus\\src\\comcat\\import\\appimport.cpp", 0x891u, 0);
          SimpleTableDispenser = -2146368421;
          goto LABEL_133;
        }
      }
      else if ( !a5 )
      {
        goto LABEL_36;
      }
      v45 = 0;
      v46 = 0;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, __int64 *))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               4,
                               &v45,
                               &v46,
                               &v61);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      v77 = Buf2;
      SimpleTableDispenser = CAppImport::AddCLSIDInternal(v21, v6, &v77, v61, 0, 0);
      if ( SimpleTableDispenser )
        goto LABEL_133;
LABEL_36:
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, _WORD **))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               5,
                               &v45,
                               &v46,
                               &v58);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, int *, unsigned int *, _WORD **))(*(_QWORD *)v48 + 64LL))(
                               v48,
                               4,
                               &v45,
                               &v46,
                               &v62);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      if ( !a5 )
        goto LABEL_69;
      v100 = 0;
      LODWORD(v101) = SimpleTableDispenser + 72;
      p_Buf2 = &Buf2;
      *((_QWORD *)&v101 + 1) = (char *)this + 96;
      v105 = &g_guidAppIdForQuery;
      v110 = v52;
      DWORD1(v101) = 16;
      v102 = 0x100000000LL;
      v103 = SimpleTableDispenser + 72;
      v104 = 16;
      v106 = 0;
      v107 = 2;
      v108 = SimpleTableDispenser + 72;
      v109 = 16;
      v111 = 0;
      v112 = 3;
      v113 = 19;
      v114 = 4;
      v49 = 0;
      if ( !*((_QWORD *)this + 9) )
      {
        *(_QWORD *)&v77.Data1 = 0;
        SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v77);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_44;
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, *(signed __int64 *)&v77.Data1, 0) )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v77.Data1 + 16LL))(*(_QWORD *)&v77.Data1);
      }
      SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                               *((_QWORD *)this + 9),
                               didCOMSERVICES,
                               &tidCOMSERVICES_CLASSES_INTERNAL,
                               &p_Buf2,
                               4,
                               1,
                               8388612,
                               &v49);
LABEL_44:
      if ( SimpleTableDispenser )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 24LL))(v49);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 32LL))(v49);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 40LL))(v49);
      SimpleTableDispenser = v22;
      if ( v22 )
      {
        if ( v22 != -2146367487 )
          goto LABEL_133;
      }
      else
      {
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 128LL))(v49);
        if ( SimpleTableDispenser )
          goto LABEL_133;
        if ( v53 )
        {
          if ( *v53 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 160LL))(
                                     v49,
                                     34,
                                     0);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_133;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v49 + 160LL))(
                                     v49,
                                     28,
                                     0,
                                     v53);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_133;
          }
        }
        if ( v58 )
        {
          if ( *v58 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 160LL))(v49, 36);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_133;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _WORD *))(*(_QWORD *)v49 + 160LL))(
                                     v49,
                                     44,
                                     0,
                                     v58);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_133;
          }
        }
        if ( v62 )
        {
          if ( *v62 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 160LL))(v49, 35);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_133;
          }
        }
        if ( v59 )
        {
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 160LL))(v49, 33);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_133;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v49 + 160LL))(
                                   v49,
                                   43,
                                   0,
                                   v59);
          if ( SimpleTableDispenser < 0 )
            goto LABEL_133;
        }
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 144LL))(v49);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_133;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 96LL))(v49);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_133;
      }
      if ( v49 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        v49 = 0;
      }
LABEL_69:
      v86 = 16;
      v98 = 0;
      v97 = 0;
      v88 = 0;
      v91 = 16;
      v93 = 0;
      if ( v20 )
      {
        v87 = (GUID *)((char *)this + 96);
        v96 = 16;
        v79 = (GUID *)&v56;
        v92 = &g_guidAppIdForQuery;
        v23 = 5;
        v83 = &Buf2;
        v95 = 72;
        v80 = 0xF000000500000000uLL;
        v81 = 19;
        v82 = 4;
        v84 = 0;
        v89 = 6;
        v94 = 7;
        *(_QWORD *)&v97 = v52;
        *((_QWORD *)&v97 + 1) = 0x800000000LL;
        v98 = 0x400000013LL;
      }
      else
      {
        v83 = (GUID *)((char *)this + 96);
        v79 = &Buf2;
        v87 = &g_guidAppIdForQuery;
        v82 = 16;
        v23 = 4;
        v96 = 4;
        v80 = 0;
        v81 = 72;
        v84 = 0x600000000LL;
        v89 = 7;
        v92 = (GUID *)v52;
        v94 = 8;
        v95 = 19;
      }
      v90 = 72;
      v85 = 72;
      v47 = 0;
      if ( !*((_QWORD *)this + 9) )
      {
        *(_QWORD *)&v77.Data1 = 0;
        SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v77);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_79;
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, *(signed __int64 *)&v77.Data1, 0) )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v77.Data1 + 16LL))(*(_QWORD *)&v77.Data1);
      }
      v24 = 10485764;
      if ( v18 != 1 )
        v24 = 12582916;
      memcmp_0(tidCOMSERVICES_CLASSES, &TID_APPLICATION, 0x10u);
      SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                               *((_QWORD *)this + 9),
                               didCOMSERVICES,
                               tidCOMSERVICES_CLASSES,
                               &v79,
                               v23,
                               1,
                               v24,
                               &v47);
LABEL_79:
      if ( SimpleTableDispenser )
        goto LABEL_133;
      if ( !v47 )
        goto LABEL_8;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 24LL))(v47);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 32LL))(v47);
      if ( SimpleTableDispenser )
        goto LABEL_133;
      v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 40LL))(v47);
      if ( a5 && v25 == -2146367487 )
      {
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 120LL))(v47);
        if ( SimpleTableDispenser )
          goto LABEL_133;
        v7 = 1;
        v26 = 0;
LABEL_110:
        v28 = v51;
LABEL_111:
        memset_0(v9, 0, 0x228u);
        while ( 1 )
        {
          if ( (unsigned int)v26 >= 0x39 )
          {
            v7 = 0;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 144LL))(v47);
            if ( SimpleTableDispenser )
              goto LABEL_133;
            if ( a5 || (v43 = 0, v28 == 1) )
              v43 = 1;
            v44 = v66;
            v77 = Buf2;
            SimpleTableDispenser = CAppImport::UpdateInterfaceTable(this, &v77, *v52, v66, v43);
            if ( SimpleTableDispenser )
              goto LABEL_133;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 96LL))(v47);
            if ( SimpleTableDispenser )
              goto LABEL_133;
            v77 = Buf2;
            SimpleTableDispenser = CAppImport::UpdateSubscriptionTableAndPropertyBags(this, v65, &v77, v44);
            if ( SimpleTableDispenser )
              goto LABEL_133;
            v6 = v60;
            if ( v47 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
            goto LABEL_13;
          }
          v45 = 0;
          v46 = 0;
          if ( !a5 )
            break;
          if ( !v7 )
          {
            if ( (unsigned int)v26 > 0x24 )
              goto LABEL_117;
            v32 = 0x100000003BLL;
            v29 = _bittest64(&v32, v26);
LABEL_116:
            if ( v29 )
              goto LABEL_170;
            goto LABEL_117;
          }
          if ( (_DWORD)v26 == 36 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v47 + 160LL))(
                                     v47,
                                     36,
                                     0,
                                     &a5);
            if ( SimpleTableDispenser )
              goto LABEL_133;
            goto LABEL_170;
          }
LABEL_117:
          if ( (_DWORD)v26 != 9 || v7 || v28 )
            goto LABEL_124;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned int *, __int64 *))(*(_QWORD *)v47 + 152LL))(
                                   v47,
                                   9,
                                   &v57,
                                   &v45,
                                   &v46,
                                   &v64);
          if ( SimpleTableDispenser )
            goto LABEL_133;
          if ( !v64 )
          {
            if ( v20 )
            {
              SimpleTableDispenser = -2146368509;
              goto LABEL_133;
            }
            v45 = 0;
            v46 = 0;
LABEL_124:
            v30 = (struct _GUID **)&v9[(unsigned int)v26];
            SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, int *, unsigned int *, struct _GUID **))(*(_QWORD *)v48 + 64LL))(
                                     v48,
                                     (unsigned int)v26,
                                     &v45,
                                     &v46,
                                     v30);
            if ( SimpleTableDispenser )
              goto LABEL_133;
            v31 = *v30;
            if ( !*v30 )
              goto LABEL_158;
            if ( (_DWORD)v26 == 9 )
            {
              v31 = v65;
LABEL_155:
              v40 = 0;
              if ( v45 == 128 )
                v40 = v46;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, struct _GUID *))(*(_QWORD *)v47 + 160LL))(
                                       v47,
                                       (unsigned int)v26,
                                       v40,
                                       v31);
              if ( SimpleTableDispenser )
                goto LABEL_133;
LABEL_158:
              if ( (_DWORD)v26 == 30 && *(_DWORD *)v9[30] )
              {
                for ( i = 57; i < 0x45; ++i )
                {
                  if ( i != 64 )
                  {
                    for ( j = 0; (unsigned int)j < 0xC; j = (unsigned int)(j + 1) )
                    {
                      if ( *((_DWORD *)&g_mapClassFlags + 2 * j) == i )
                      {
                        v55 = (*v30)->Data1 & *((_DWORD *)&g_mapClassFlags + 2 * (unsigned int)j + 1);
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, int *))(*(_QWORD *)v47 + 160LL))(
                                                 v47,
                                                 i,
                                                 0,
                                                 &v55);
                        if ( SimpleTableDispenser )
                          goto LABEL_133;
                        break;
                      }
                    }
                  }
                }
              }
            }
            else if ( ((_DWORD)v26 != 6 || v7) && ((_DWORD)v26 != 7 || v7) && ((_DWORD)v26 != 36 || v7) )
            {
              goto LABEL_155;
            }
            v20 = v50;
          }
LABEL_170:
          v28 = v51;
          v26 = (unsigned int)(v26 + 1);
        }
        if ( (_DWORD)v26 == 4 )
          goto LABEL_117;
        v29 = (unsigned int)v26 < 6;
        goto LABEL_116;
      }
      v26 = 0;
      if ( !v20 || v25 != -2146367487 )
      {
        if ( v25 )
          goto LABEL_180;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 128LL))(v47);
        if ( SimpleTableDispenser )
          goto LABEL_133;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v47 + 152LL))(
                                 v47,
                                 2,
                                 0,
                                 0,
                                 0,
                                 &v63);
        if ( SimpleTableDispenser )
          goto LABEL_133;
        if ( v63 )
        {
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v47 + 160LL))(
                                   v47,
                                   48,
                                   0);
          if ( SimpleTableDispenser )
            goto LABEL_133;
        }
        goto LABEL_110;
      }
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v79 = &Buf2;
      v83 = (GUID *)((char *)this + 96);
      v87 = &g_guidAppIdForQuery;
      v92 = (GUID *)v52;
      v80 = 0;
      v81 = 72;
      v82 = 16;
      v84 = 0x600000000LL;
      v85 = 72;
      v86 = 16;
      v88 = 0;
      v89 = 7;
      v90 = 72;
      v91 = 16;
      v93 = 0;
      v94 = 8;
      v95 = 19;
      v96 = 4;
      v47 = 0;
      if ( !*((_QWORD *)this + 9) )
      {
        *(_QWORD *)&v77.Data1 = 0;
        SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v77);
        if ( SimpleTableDispenser < 0 )
        {
LABEL_98:
          if ( SimpleTableDispenser )
            goto LABEL_133;
          if ( !v47 )
          {
            SimpleTableDispenser = -2147024882;
            goto LABEL_133;
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 24LL))(v47);
          if ( SimpleTableDispenser )
            goto LABEL_133;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 32LL))(v47);
          if ( SimpleTableDispenser )
            goto LABEL_133;
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v47 + 40LL))(v47) )
          {
LABEL_180:
            SimpleTableDispenser = -2146368488;
            goto LABEL_133;
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 128LL))(v47);
          if ( SimpleTableDispenser )
            goto LABEL_133;
          v28 = 1;
          v51 = 1;
          goto LABEL_111;
        }
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, *(signed __int64 *)&v77.Data1, 0) )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v77.Data1 + 16LL))(*(_QWORD *)&v77.Data1);
      }
      v27 = 10485764;
      if ( v18 != 1 )
        v27 = 12582916;
      memcmp_0(tidCOMSERVICES_CLASSES, &TID_APPLICATION, 0x10u);
      SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                               *((_QWORD *)this + 9),
                               didCOMSERVICES,
                               tidCOMSERVICES_CLASSES,
                               &v79,
                               4,
                               1,
                               v27,
                               &v47);
      goto LABEL_98;
    }
  }
LABEL_133:
  v33 = v60;
  v34 = 0;
  v35 = *(_DWORD *)(v60 + 16);
  if ( v35 )
  {
    do
    {
      v36 = memcmp_0(&GUID_NULL, &Buf2, 0x10u);
      v37 = *(_QWORD *)(*(_QWORD *)(v33 + 8) + 8LL * (int)v34);
      if ( !v36 )
        goto LABEL_138;
      v38 = *(_QWORD *)&Buf2.Data1 - *(_QWORD *)v37;
      if ( *(_QWORD *)&Buf2.Data1 == *(_QWORD *)v37 )
        v38 = *(_QWORD *)Buf2.Data4 - *(_QWORD *)(v37 + 8);
      if ( !v38 )
      {
LABEL_138:
        *(_DWORD *)(v37 + 104) = SimpleTableDispenser;
        SimpleTableDispenser = -2146368511;
      }
      ++v34;
    }
    while ( v34 < v35 );
  }
  if ( v9 )
  {
LABEL_141:
    *v9 = 0;
    CoTaskMemFree(v9);
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x180011d74  mov     [rsp-8+arg_8], rbx
0x180011d79  push    rbp
0x180011d7a  push    rsi
0x180011d7b  push    rdi
0x180011d7c  push    r12
0x180011d7e  push    r13
0x180011d80  push    r14
0x180011d82  push    r15
0x180011d84  lea     rbp, [rsp-130h]
0x180011d8c  sub     rsp, 230h
0x180011d93  mov     rax, cs:__security_cookie
0x180011d9a  xor     rax, rsp
0x180011d9d  mov     [rbp+160h+var_40], rax
0x180011da4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180011dab  mov     rdi, [rbp+160h+arg_28]
0x180011db2  xor     r15d, r15d
0x180011db5  mov     r13, rcx
0x180011db8  mov     [rbp+160h+var_180], r9
0x180011dbc  mov     rcx, r9; unsigned __int16 *
0x180011dbf  mov     [rbp+160h+var_188], r8
0x180011dc3  movdqu  [rbp+160h+Buf2], xmm0
0x180011dc8  mov     r10, rdx
0x180011dcb  mov     [rbp+160h+var_1B0], rdi
0x180011dcf  mov     [rsp+260h+var_208], r15
0x180011dd4  mov     r12d, r15d
0x180011dd7  mov     [rsp+260h+var_1F8], r15
0x180011ddc  mov     [rbp+160h+var_1D0], r15d
0x180011de0  mov     [rbp+160h+var_1CC], 1
0x180011de7  mov     [rbp+160h+var_198], r15
0x180011deb  mov     [rbp+160h+var_178], r9
0x180011def  mov     [rbp+160h+var_170], r15d
0x180011df3  mov     [rbp+160h+var_16C], 0F0000001h
0x180011dfa  mov     [rbp+160h+var_168], 82h
0x180011e01  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180011e06  lea     esi, [r15+10h]
0x180011e0a  mov     [rbp+160h+var_160], r10
0x180011e0e  mov     [rbp+160h+var_158], r15d
0x180011e12  mov     [rbp+160h+var_154], 9
0x180011e19  lea     eax, ds:2[rax*2]
0x180011e20  mov     [rbp+160h+var_150], 48h ; 'H'
0x180011e27  mov     [rbp+160h+var_164], eax
0x180011e2a  mov     [rbp+160h+var_14C], esi
0x180011e2d  mov     [rsp+260h+var_200], r15
0x180011e32  cmp     [r13+48h], r15
0x180011e36  jnz     short loc_180011E75
0x180011e38  lea     rdx, [rbp+160h+var_1E0]
0x180011e3c  mov     [rbp+160h+var_1E0], r15
0x180011e40  lea     rcx, IID_ISimpleTableDispenser
0x180011e47  call    cs:__imp_GetSimpleTableDispenser
0x180011e4d  mov     ebx, eax
0x180011e4f  test    eax, eax
0x180011e51  js      loc_180011ED8
0x180011e57  mov     rcx, [rbp+160h+var_1E0]
0x180011e5b  xor     eax, eax
0x180011e5d  lock cmpxchg [r13+48h], rcx
0x180011e63  jz      short loc_180011E75
0x180011e65  mov     rcx, [rbp+160h+var_1E0]
0x180011e69  mov     rax, [rcx]
0x180011e6c  mov     rax, [rax+10h]
0x180011e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e75  mov     r8, rsi; Size
0x180011e78  lea     rdx, TID_APPLICATION; Buf2
0x180011e7f  lea     rcx, tidCOMSERVICES_CLASSES_EXPORT; Buf1
0x180011e86  call    memcmp_0
0x180011e8b  mov     rcx, [r13+48h]
0x180011e8f  lea     r9, [rsp+260h+var_200]
0x180011e94  mov     [rsp+260h+var_228], r9
0x180011e99  lea     r8, tidCOMSERVICES_CLASSES_EXPORT
0x180011ea0  neg     eax
0x180011ea2  lea     r9, [rbp+160h+var_178]
0x180011ea6  mov     rax, [rcx]
0x180011ea9  sbb     edx, edx
0x180011eab  and     edx, 2
0x180011eae  add     edx, 5
0x180011eb1  mov     [rsp+260h+var_230], edx
0x180011eb5  lea     rdx, didCOMSERVICES
0x180011ebc  mov     rax, [rax+18h]
0x180011ec0  mov     dword ptr [rsp+260h+var_238], 1
0x180011ec8  mov     [rsp+260h+var_240], 2
0x180011ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed6  mov     ebx, eax
0x180011ed8  test    ebx, ebx
0x180011eda  jnz     loc_180012C92
0x180011ee0  cmp     [rsp+260h+var_200], r15
0x180011ee5  jnz     short loc_180011EF1
0x180011ee7  mov     ebx, 8007000Eh
0x180011eec  jmp     loc_180012C92
0x180011ef1  mov     rcx, [rsp+260h+var_200]
0x180011ef6  mov     rax, [rcx]
0x180011ef9  mov     rax, [rax+18h]
0x180011efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f02  mov     ebx, eax
0x180011f04  test    eax, eax
0x180011f06  jnz     loc_180012C92
0x180011f0c  mov     rcx, [rsp+260h+var_200]
0x180011f11  mov     rax, [rcx]
0x180011f14  mov     rax, [rax+20h]
0x180011f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f1d  mov     ebx, eax
0x180011f1f  test    eax, eax
0x180011f21  jnz     loc_180012C92
0x180011f27  mov     ecx, 228h; cb
0x180011f2c  call    cs:__imp_CoTaskMemAlloc
0x180011f32  mov     r12, rax
0x180011f35  test    rax, rax
0x180011f38  jz      short loc_180011EE7
0x180011f3a  mov     [rsp+260h+var_1EC], r15d
0x180011f3f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180011f46  mov     rcx, [rsp+260h+var_200]
0x180011f4b  mov     [rsp+260h+var_210], r15d
0x180011f50  movdqu  [rbp+160h+Buf2], xmm0
0x180011f55  mov     [rsp+260h+var_20C], r15d
0x180011f5a  mov     [rbp+160h+var_1C8], r15d
0x180011f5e  mov     [rbp+160h+var_1D8], r15
0x180011f62  mov     [rbp+160h+var_190], r15
0x180011f66  mov     [rsp+260h+var_208], r15
0x180011f6b  mov     [rbp+160h+var_1A8], r15
0x180011f6f  mov     [rbp+160h+var_1E0], r15
0x180011f73  mov     [rbp+160h+var_1C0], r15
0x180011f77  mov     [rbp+160h+var_1A0], r15
0x180011f7b  mov     [rsp+260h+var_1E8], r15
0x180011f80  mov     [rbp+160h+var_1B8], r15
0x180011f84  mov     rax, [rcx]
0x180011f87  mov     rax, [rax+28h]
0x180011f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f90  mov     ebx, eax
0x180011f92  cmp     eax, 80110801h
0x180011f97  jz      loc_180012F45
0x180011f9d  test    eax, eax
0x180011f9f  jnz     loc_180012C92
0x180011fa5  mov     rcx, [rsp+260h+var_200]
0x180011faa  lea     rdx, [rbp+160h+var_1D8]
0x180011fae  mov     [rsp+260h+var_240], rdx
0x180011fb3  lea     r9, [rsp+260h+var_20C]
0x180011fb8  lea     r8, [rsp+260h+var_210]
0x180011fbd  xor     edx, edx
0x180011fbf  mov     rax, [rcx]
0x180011fc2  mov     rax, [rax+40h]
0x180011fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fcb  mov     ebx, eax
0x180011fcd  test    eax, eax
0x180011fcf  jnz     loc_180012C92
0x180011fd5  mov     rax, [rbp+160h+var_1D8]
0x180011fd9  mov     edx, r15d
0x180011fdc  movups  xmm0, xmmword ptr [rax]
0x180011fdf  movdqu  [rbp+160h+Buf2], xmm0
0x180011fe4  cmp     edx, [rdi+10h]
0x180011fe7  jge     short loc_18001201C
0x180011fe9  mov     rax, [rdi+8]
0x180011fed  movsxd  rcx, edx
0x180011ff0  mov     r8, [rax+rcx*8]
0x180011ff4  mov     rax, [r8]
0x180011ff7  sub     rax, qword ptr [rbp+160h+Buf2]
0x180011ffb  jnz     short loc_180012005
0x180011ffd  mov     rax, [r8+8]
0x180012001  sub     rax, qword ptr [rbp+160h+Buf2+8]
0x180012005  test    rax, rax
0x180012008  jnz     short loc_180012018
0x18001200a  test    dword ptr [r8+24h], 1000h
0x180012012  jnz     loc_180011F3F
0x180012018  inc     edx
0x18001201a  jmp     short loc_180011FE4
0x18001201c  mov     rcx, [rsp+260h+var_200]
0x180012021  lea     rdx, [rsp+260h+var_1E8]
0x180012026  mov     [rsp+260h+var_240], rdx
0x18001202b  lea     r9, [rsp+260h+var_20C]
0x180012030  lea     r8, [rsp+260h+var_210]
0x180012035  mov     edx, 8
0x18001203a  mov     rax, [rcx]
0x18001203d  mov     rax, [rax+40h]
0x180012041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012046  mov     ebx, eax
0x180012048  test    eax, eax
0x18001204a  jnz     loc_180012C92
0x180012050  mov     rcx, [rsp+260h+var_200]
0x180012055  lea     rdx, [rbp+160h+var_1E0]
0x180012059  mov     [rsp+260h+var_240], rdx
0x18001205e  lea     r9, [rsp+260h+var_20C]
0x180012063  lea     r8, [rsp+260h+var_210]
0x180012068  lea     edx, [rbx+3]
0x18001206b  mov     rax, [rcx]
0x18001206e  mov     rax, [rax+40h]
0x180012072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012077  mov     ebx, eax
0x180012079  test    eax, eax
0x18001207b  jnz     loc_180012C92
0x180012081  mov     rcx, [rsp+260h+var_200]
0x180012086  lea     rdx, [rbp+160h+var_1B8]
0x18001208a  mov     [rsp+260h+var_240], rdx
0x18001208f  lea     r9, [rsp+260h+var_20C]
0x180012094  lea     r8, [rsp+260h+var_210]
0x180012099  lea     edx, [rbx+2]
0x18001209c  mov     rax, [rcx]
0x18001209f  mov     rax, [rax+40h]
0x1800120a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a8  mov     ebx, eax
0x1800120aa  test    eax, eax
0x1800120ac  jnz     loc_180012C92
0x1800120b2  mov     rcx, [rsp+260h+var_200]
0x1800120b7  lea     rdx, [rbp+160h+var_1D8]
0x1800120bb  mov     [rsp+260h+var_240], rdx
0x1800120c0  lea     r9, [rsp+260h+var_20C]
0x1800120c5  lea     r8, [rsp+260h+var_210]
0x1800120ca  lea     edx, [rbx+0Ah]
0x1800120cd  mov     rax, [rcx]
0x1800120d0  mov     rax, [rax+40h]
0x1800120d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d9  mov     ebx, eax
0x1800120db  test    eax, eax
0x1800120dd  jnz     loc_180012C92
0x1800120e3  mov     rax, [rbp+160h+var_1D8]
0x1800120e7  test    rax, rax
0x1800120ea  jz      short loc_180012138
0x1800120ec  mov     r8, [rbp+160h+var_1E0]; unsigned __int16 *
0x1800120f0  lea     rdx, [r13+60h]
0x1800120f4  xorps   xmm0, xmm0
0x1800120f7  lea     r9, [rbp+160h+var_140]; struct _GUID *
0x1800120fb  movups  xmmword ptr [rbp+160h+var_140.Data1], xmm0
0x1800120ff  movups  xmm1, xmmword ptr [rax]
0x180012102  mov     rax, [rsp+260h+var_1E8]
0x180012107  movdqu  xmmword ptr [rbp+160h+var_140.Data1], xmm1
0x18001210c  mov     ecx, [rax]
0x18001210e  mov     rax, [rsp+260h+var_200]
0x180012113  mov     [rsp+260h+var_230], ecx; unsigned int
0x180012117  mov     rcx, [r13+48h]; struct ISimpleTableDispenser *
0x18001211b  mov     [rsp+260h+var_238], rax; struct ISimpleTableRead *
0x180012120  mov     [rsp+260h+var_240], rdx; struct _GUID *
0x180012125  lea     rdx, [rbp+160h+Buf2]; struct _GUID *
0x180012129  call    ?FixupAliasedComponent@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAG11PEAUISimpleTableRead@@K@Z; FixupAliasedComponent(ISimpleTableDispenser *,_GUID const &,ushort *,_GUID const &,_GUID const &,ISimpleTableRead *,ulong)
0x18001212e  mov     ebx, eax
0x180012130  test    eax, eax
0x180012132  jnz     loc_180012C92
0x180012138  mov     rax, [rsp+260h+var_1E8]
0x18001213d  lea     rdx, [rbp+160h+var_1D8]
0x180012141  mov     rcx, [rsp+260h+var_200]
0x180012146  lea     r9, [rsp+260h+var_20C]
0x18001214b  mov     [rsp+260h+var_240], rdx
0x180012150  lea     r8, [rsp+260h+var_210]
0x180012155  mov     edx, 1Eh
0x18001215a  mov     esi, [rax]
0x18001215c  mov     [rsp+260h+var_210], r15d
0x180012161  mov     [rsp+260h+var_20C], r15d
0x180012166  mov     [rbp+160h+var_1D8], r15
0x18001216a  mov     rax, [rcx]
0x18001216d  mov     rax, [rax+40h]
0x180012171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012176  mov     ebx, eax
0x180012178  test    eax, eax
0x18001217a  jnz     loc_180012C92
0x180012180  mov     rax, [rbp+160h+var_1D8]
0x180012184  mov     r14d, [rax]
0x180012187  and     r14d, 1000h
0x18001218e  mov     [rsp+260h+var_1F0], r14d
0x180012193  jnz     short loc_180012211
0x180012195  lea     rcx, [r13+60h]; Buf1
0x180012199  lea     r8d, [rbx+10h]; Size
0x18001219d  lea     rdx, GUID_DefaultAppPartition; Buf2
0x1800121a4  call    memcmp_0
0x1800121a9  test    eax, eax
0x1800121ab  jz      short loc_18001221A
0x1800121ad  lea     eax, [rbx+16h]
0x1800121b0  mov     dword ptr [rbp+160h+var_A0], r15d
0x1800121b7  xorps   xmm0, xmm0
0x1800121ba  mov     word ptr [rbp+160h+var_A0+4], ax
0x1800121c1  xor     r9d, r9d; unsigned __int16 *
0x1800121c4  mov     dword ptr [rbp+160h+var_98], 0C0001300h
0x1800121ce  mov     r8d, 891h; unsigned int
0x1800121d4  mov     [rbp+160h+var_80], r15
0x1800121db  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\import\\appi"...
0x1800121e2  mov     [rbp+160h+var_78], r15d
0x1800121e9  lea     rcx, [rbp+160h+var_A0]; this
0x1800121f0  mov     [rbp+160h+var_74], 1
0x1800121fa  movdqu  [rbp+160h+var_90], xmm0
0x180012202  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180012207  mov     ebx, 8011045Bh
0x18001220c  jmp     loc_180012C92
0x180012211  cmp     [rbp+160h+arg_20], r15d
0x180012218  jz      short loc_180012284
0x18001221a  mov     rcx, [rsp+260h+var_200]
0x18001221f  lea     rdx, [rbp+160h+var_1A8]
0x180012223  mov     [rsp+260h+var_210], r15d
0x180012228  lea     r9, [rsp+260h+var_20C]
0x18001222d  mov     [rsp+260h+var_20C], r15d
0x180012232  lea     r8, [rsp+260h+var_210]
0x180012237  mov     [rsp+260h+var_240], rdx
0x18001223c  mov     edx, 4
0x180012241  mov     rax, [rcx]
0x180012244  mov     rax, [rax+40h]
0x180012248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001224d  mov     ebx, eax
0x18001224f  test    eax, eax
0x180012251  jnz     loc_180012C92
0x180012257  movaps  xmm0, [rbp+160h+Buf2]
0x18001225b  lea     r8, [rbp+160h+var_140]
0x18001225f  mov     r9, [rbp+160h+var_1A8]
0x180012263  mov     rdx, rdi
0x180012266  mov     dword ptr [rsp+260h+var_238], r15d
0x18001226b  movdqa  xmmword ptr [rbp+160h+var_140.Data1], xmm0
0x180012270  mov     dword ptr [rsp+260h+var_240], r15d
0x180012275  call    ?AddCLSIDInternal@CAppImport@@AEAAJPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@U_GUID@@PEBGKJ@Z; CAppImport::AddCLSIDInternal(CArray<CompInfo *,CompInfo * const &> *,_GUID,ushort const *,ulong,long)
  ... truncated ...
```
