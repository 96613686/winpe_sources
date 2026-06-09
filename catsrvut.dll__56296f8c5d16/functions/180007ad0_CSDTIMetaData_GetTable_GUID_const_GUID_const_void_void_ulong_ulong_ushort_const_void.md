# CSDTIMetaData::GetTable(_GUID const &,_GUID const &,void *,void *,ulong,ulong,ushort const *,void * *)

- ea: `0x180007ad0`
- end: `0x180008b83`
- name: `?GetTable@CSDTIMetaData@@UEAAJAEBU_GUID@@0PEAX1KKPEBGPEAPEAX@Z`
- size: `4275`
- prototype: `int(CSDTIMetaData *__hidden this, const struct _GUID *, const struct _GUID *, void *, void *, unsigned int, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x180007ad0`
- `0x180015594`
- `0x180055822`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000832a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000832a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000872c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000872c`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180007ffd`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180007ffd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSDTIMetaData::GetTable(
        struct _GUID *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        _DWORD *a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        const unsigned __int16 *a8,
        void **a9)
{
  struct _GUID *v11; // r15
  struct _GUID *v13; // rdi
  unsigned int i; // r12d
  __int64 v15; // rax
  __int64 v16; // r14
  int v17; // ebx
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  int SimpleTableDispenser; // ebx
  void *v23; // rcx
  _OWORD *v24; // rax
  const unsigned __int16 *v25; // rcx
  unsigned int v26; // ebx
  unsigned __int16 *v27; // rax
  void *v28; // rcx
  int v29; // eax
  __int64 **v30; // r9
  __int64 **v31; // r9
  int v32; // esi
  int v33; // esi
  bool v34; // zf
  char *v35; // r14
  int v36; // esi
  int v37; // ebx
  bool v38; // zf
  unsigned int v39; // r13d
  unsigned __int8 *Data4; // rsi
  __int64 v41; // rsi
  int v42; // r14d
  int v43; // r15d
  int v44; // eax
  bool v45; // zf
  __int64 v46; // rsi
  unsigned int v47; // r15d
  int v48; // r14d
  int v49; // eax
  __int64 v50; // rcx
  char *pv; // [rsp+50h] [rbp-51h]
  int *v52; // [rsp+58h] [rbp-49h] BYREF
  unsigned int v53; // [rsp+60h] [rbp-41h] BYREF
  __int64 v54; // [rsp+68h] [rbp-39h] BYREF
  __int64 v55; // [rsp+70h] [rbp-31h] BYREF
  __int64 v56; // [rsp+78h] [rbp-29h] BYREF
  __int64 v57; // [rsp+80h] [rbp-21h] BYREF
  unsigned int v58; // [rsp+88h] [rbp-19h] BYREF
  unsigned int v59; // [rsp+8Ch] [rbp-15h] BYREF
  unsigned int v60; // [rsp+90h] [rbp-11h]
  unsigned __int8 *v61; // [rsp+98h] [rbp-9h]

  v11 = this;
  v55 = 0;
  v54 = 0;
  v57 = 0;
  v56 = 0;
  v53 = 0;
  v58 = 0;
  v59 = 0;
  v52 = 0;
  if ( this[2].Data1 )
    return 2147549183LL;
  if ( !a9 )
    return 2147942487LL;
  *a9 = 0;
  if ( memcmp_0(a2, didAPPDU, 0x10u)
    || memcmp_0(a3, &tidCOMSERVICES_CLASSES, 0x10u)
    && memcmp_0(a3, &tidCOMCLASSIC_FILEEXT, 0x10u)
    && memcmp_0(a3, &tidCOMCLASSIC_MIMETYPE, 0x10u)
    && memcmp_0(a3, &tidAPPDU_CLASSROLES, 0x10u)
    && memcmp_0(a3, &tidAPPDU_INTERFACEROLES, 0x10u)
    && memcmp_0(a3, &tidAPPDU_INTERFACEPROP, 0x10u)
    && memcmp_0(a3, &tidAPPDU_METHOD, 0x10u) )
  {
    return 2147942487LL;
  }
  if ( a8 )
    return 2147942487LL;
  v13 = v11 + 4;
  v11[4] = *a3;
  if ( a6 != 1 || !a4 || !(_DWORD)a5 || !memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) && (unsigned int)a5 < 3 )
    return 2148599811LL;
  pv = 0;
  for ( i = 0; i < (unsigned int)a5; ++i )
  {
    if ( i )
    {
      v15 = i;
    }
    else
    {
      if ( a4[3] <= 0xF0000000 )
        goto LABEL_80;
      v15 = 0;
    }
    v16 = 3 * v15;
    v17 = a4[6 * v15 + 3];
    if ( v17 == -268435455 )
    {
      if ( *(_QWORD *)v11[3].Data4 )
        goto LABEL_80;
      if ( a4[6 * v15 + 4] != 130 )
        goto LABEL_80;
      if ( a4[6 * v15 + 2] )
        goto LABEL_80;
      v18 = *(_QWORD *)&a4[6 * v15];
      if ( !v18 )
        goto LABEL_80;
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v18 + 2 * v19) );
      v20 = v19 + 1;
      v21 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v19 + 1, 2u));
      *(_QWORD *)v11[3].Data4 = v21;
      if ( !v21 )
        return 2147942414LL;
      SimpleTableDispenser = StringCchCopyW(v21, v20, *(const unsigned __int16 **)&a4[2 * v16]);
      if ( SimpleTableDispenser < 0 )
      {
        v23 = *(void **)v11[3].Data4;
        if ( v23 )
          CoTaskMemFree(v23);
        *(_QWORD *)v11[3].Data4 = 0;
        goto LABEL_116;
      }
    }
    else
    {
      if ( !memcmp_0(&tidCOMCLASSIC_FILEEXT, &v11[4], 0x10u) && !v17
        || !memcmp_0(&tidCOMCLASSIC_MIMETYPE, &v11[4], 0x10u) && v17 == 1
        || !memcmp_0(&tidAPPDU_CLASSROLES, &v11[4], 0x10u) && !v17
        || !memcmp_0(&tidAPPDU_INTERFACEROLES, &v11[4], 0x10u) && !v17
        || !memcmp_0(&tidAPPDU_INTERFACEPROP, &v11[4], 0x10u) && !v17
        || !memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) && !v17 )
      {
        if ( *(_QWORD *)&v11[5].Data1 || a4[2 * v16 + 4] != 72 || a4[2 * v16 + 2] || !*(_QWORD *)&a4[2 * v16] )
          goto LABEL_80;
        v24 = CoTaskMemAlloc(0x10u);
        *(_QWORD *)&v11[5].Data1 = v24;
LABEL_53:
        if ( !v24 )
          return 2147942414LL;
        *v24 = *(_OWORD *)*(_QWORD *)&a4[2 * v16];
        continue;
      }
      if ( !memcmp_0(&tidAPPDU_INTERFACEROLES, &v11[4], 0x10u) && v17 == 3
        || !memcmp_0(&tidAPPDU_INTERFACEPROP, &v11[4], 0x10u) && v17 == 3
        || !memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) && v17 == 3 )
      {
        if ( !*(_QWORD *)&v11[5].Data1 )
          return 2148599811LL;
        if ( a4[2 * v16 + 4] != 72 || a4[2 * v16 + 2] || !*(_QWORD *)&a4[2 * v16] )
          goto LABEL_80;
        v24 = CoTaskMemAlloc(0x10u);
        *(_QWORD *)v11[5].Data4 = v24;
        goto LABEL_53;
      }
      if ( !memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) && v17 == 8 )
      {
        if ( !*(_QWORD *)&v11[5].Data1 || !*(_QWORD *)v11[5].Data4 )
          return 2148599811LL;
        if ( a4[2 * v16 + 4] != 130 || a4[2 * v16 + 2] || (v25 = *(const unsigned __int16 **)&a4[2 * v16]) == 0 || !*v25 )
        {
LABEL_80:
          SimpleTableDispenser = -2146367485;
LABEL_116:
          v35 = pv;
          goto LABEL_117;
        }
        v26 = safe_lstrlenW(v25) + 1;
        v27 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v26, 2u));
        *(_QWORD *)&v11[6].Data1 = v27;
        if ( !v27 )
          return 2147942414LL;
        SimpleTableDispenser = StringCchCopyW(v27, v26, *(const unsigned __int16 **)&a4[2 * v16]);
        if ( SimpleTableDispenser < 0 )
        {
          v28 = *(void **)&v11[6].Data1;
          if ( v28 )
            CoTaskMemFree(v28);
          *(_QWORD *)&v11[6].Data1 = 0;
          goto LABEL_116;
        }
      }
    }
  }
  if ( !memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u)
    && (!*(_QWORD *)&v11[5].Data1 || !*(_QWORD *)v11[5].Data4 || !*(_QWORD *)&v11[6].Data1) )
  {
    return 2148599811LL;
  }
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v55);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_116;
  if ( memcmp_0(&tidCOMSERVICES_CLASSES, &v11[4], 0x10u) )
  {
    if ( !memcmp_0(&tidCOMCLASSIC_FILEEXT, &v11[4], 0x10u) )
    {
      v30 = &off_18005F000;
    }
    else
    {
      if ( memcmp_0(&tidCOMCLASSIC_MIMETYPE, &v11[4], 0x10u) )
      {
        if ( !memcmp_0(&tidAPPDU_CLASSROLES, &v11[4], 0x10u) )
        {
          v31 = &off_18005F030;
        }
        else if ( !memcmp_0(&tidAPPDU_INTERFACEROLES, &v11[4], 0x10u) )
        {
          v31 = &off_18005F018;
        }
        else if ( !memcmp_0(&tidAPPDU_INTERFACEPROP, &v11[4], 0x10u) )
        {
          v31 = &off_18005EFB8;
        }
        else
        {
          if ( memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) )
            goto LABEL_105;
          v31 = &off_18005F048;
        }
        v29 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *, __int64 **, __int64, int, int, __int64 *))(*(_QWORD *)v55 + 24LL))(
                v55,
                &didCOMSERVICES,
                tidMETA,
                v31,
                1,
                1,
                3,
                &v56);
        goto LABEL_104;
      }
      v30 = &off_18005EFE8;
    }
    v29 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, __int64 **, __int64, int, int, __int64 *))(*(_QWORD *)v55 + 24LL))(
            v55,
            didCOMCLASSIC,
            tidMETA,
            v30,
            1,
            1,
            3,
            &v54);
    goto LABEL_104;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, __int64 (**)[2], __int64, int, int, __int64 *))(*(_QWORD *)v55 + 24LL))(
                           v55,
                           didCOMCLASSIC,
                           tidMETA,
                           &off_18005EFD0,
                           1,
                           1,
                           3,
                           &v54);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_116;
  v29 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *, _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)v55 + 24LL))(
          v55,
          &didCOMSERVICES,
          tidMETA,
          &off_18005EFA0,
          1,
          1,
          3,
          &v57);
LABEL_104:
  SimpleTableDispenser = v29;
  if ( v29 < 0 )
    goto LABEL_116;
LABEL_105:
  if ( !memcmp_0(&tidCOMSERVICES_CLASSES, &v11[4], 0x10u) )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int **))(*(_QWORD *)v54 + 64LL))(
                             v54,
                             1,
                             0,
                             0,
                             &v52);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    v32 = *v52;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v54 + 64LL))(v54, 3, 0);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    if ( v32 == 72 && (*(_BYTE *)v52 & 1) != 0 )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int **))(*(_QWORD *)v57 + 64LL))(
                               v57,
                               1,
                               0,
                               0,
                               &v52);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_116;
      v33 = *v52;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v57 + 64LL))(v57, 3, 0);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_116;
      if ( v33 == 72 )
      {
        v34 = (*(_BYTE *)v52 & 1) == 0;
        goto LABEL_114;
      }
    }
    goto LABEL_115;
  }
  if ( !memcmp_0(&tidCOMCLASSIC_FILEEXT, &v11[4], 0x10u) || !memcmp_0(&tidCOMCLASSIC_MIMETYPE, &v11[4], 0x10u) )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int **))(*(_QWORD *)v54 + 64LL))(
                             v54,
                             1,
                             0,
                             0,
                             &v52);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    v36 = *v52;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v54 + 64LL))(v54, 3, 0);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    v37 = *v52;
    if ( memcmp_0(&tidCOMCLASSIC_FILEEXT, &v11[4], 0x10u) )
    {
      if ( v36 != 130 || (v37 & 1) == 0 )
        goto LABEL_115;
      goto LABEL_147;
    }
LABEL_137:
    v38 = v36 == 130;
    goto LABEL_138;
  }
  if ( memcmp_0(&tidAPPDU_CLASSROLES, &v11[4], 0x10u)
    && memcmp_0(&tidAPPDU_INTERFACEROLES, &v11[4], 0x10u)
    && memcmp_0(&tidAPPDU_INTERFACEPROP, &v11[4], 0x10u)
    && memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) )
  {
    goto LABEL_147;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int **))(*(_QWORD *)v56 + 64LL))(
                           v56,
                           1,
                           0,
                           0,
                           &v52);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_116;
  v36 = *v52;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v56 + 64LL))(v56, 3, 0);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_116;
  v37 = *v52;
  if ( !memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) || memcmp_0(&tidAPPDU_INTERFACEPROP, &v11[4], 0x10u) )
    goto LABEL_137;
  v38 = v36 == 19;
LABEL_138:
  if ( !v38 )
    goto LABEL_115;
  v34 = (v37 & 1) == 0;
LABEL_114:
  if ( v34 )
  {
LABEL_115:
    SimpleTableDispenser = -2147418113;
    goto LABEL_116;
  }
LABEL_147:
  if ( !memcmp_0(&tidCOMSERVICES_CLASSES, &v11[4], 0x10u) )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v54 + 72LL))(
                             v54,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             &v53,
                             0);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v57 + 72LL))(
                             v57,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             &v58,
                             0);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    v39 = v58 + v53 - 1;
  }
  else if ( !memcmp_0(&tidCOMCLASSIC_FILEEXT, &v11[4], 0x10u) || !memcmp_0(&tidCOMCLASSIC_MIMETYPE, &v11[4], 0x10u) )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v54 + 72LL))(
                             v54,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             &v53,
                             0);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    v39 = v53;
  }
  else
  {
    if ( memcmp_0(&tidAPPDU_CLASSROLES, &v11[4], 0x10u)
      && memcmp_0(&tidAPPDU_INTERFACEROLES, &v11[4], 0x10u)
      && memcmp_0(&tidAPPDU_INTERFACEPROP, &v11[4], 0x10u)
      && memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) )
    {
      goto LABEL_115;
    }
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v56 + 72LL))(
                             v56,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             &v59,
                             0);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    v39 = v59;
  }
  Data4 = v11[2].Data4;
  v61 = v11[2].Data4;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD, _QWORD, int, int, unsigned __int8 *))(*(_QWORD *)v55 + 24LL))(
                           v55,
                           didMEMORY,
                           tidMEMORY_SHAPEABLE,
                           0,
                           0,
                           1,
                           8,
                           v11[2].Data4);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_116;
  v35 = (char *)CoTaskMemAlloc(saturated_mul(v39, 0xCu));
  pv = v35;
  if ( !v35 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_117;
  }
  if ( !memcmp_0(&tidCOMSERVICES_CLASSES, &v11[4], 0x10u) )
  {
    v41 = v54;
    v60 = v53;
    v42 = 0;
    v43 = 0;
    while ( 1 )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 32LL))(v41);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_116;
      if ( v41 == v57 )
      {
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 40LL))(v41);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_116;
      }
      while ( 1 )
      {
        v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 40LL))(v41);
        SimpleTableDispenser = v44;
        if ( v44 == -2146367487 )
          break;
        if ( v44 < 0 )
          goto LABEL_116;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 64LL))(v41, 1, 0);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_116;
        *(_DWORD *)&pv[12 * v43] = *v52;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 64LL))(v41, 2, 0);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_116;
        *(_DWORD *)&pv[12 * v43 + 4] = *v52;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 64LL))(v41, 3, 0);
        if ( SimpleTableDispenser < 0 )
          goto LABEL_116;
        *(_DWORD *)&pv[12 * v43++ + 8] = *v52;
        ++v42;
      }
      if ( v60 != v42 )
        goto LABEL_115;
      if ( v41 == v57 )
      {
        v45 = v39 == v43;
        goto LABEL_179;
      }
      v41 = v57;
      v60 = v58;
      v42 = 1;
    }
  }
  if ( !memcmp_0(&tidCOMCLASSIC_FILEEXT, &v11[4], 0x10u)
    || !memcmp_0(&tidCOMCLASSIC_MIMETYPE, &v11[4], 0x10u)
    || !memcmp_0(&tidAPPDU_CLASSROLES, &v11[4], 0x10u)
    || !memcmp_0(&tidAPPDU_INTERFACEROLES, &v11[4], 0x10u)
    || !memcmp_0(&tidAPPDU_INTERFACEPROP, &v11[4], 0x10u)
    || !memcmp_0(&tidAPPDU_METHOD, &v11[4], 0x10u) )
  {
    if ( !memcmp_0(&tidCOMCLASSIC_FILEEXT, &v11[4], 0x10u) || !memcmp_0(&tidCOMCLASSIC_MIMETYPE, &v11[4], 0x10u) )
    {
      v46 = v54;
      v47 = v53;
    }
    else
    {
      v46 = v56;
      v47 = v59;
    }
    v48 = 0;
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 32LL))(v46);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_116;
    while ( 1 )
    {
      v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 40LL))(v46);
      SimpleTableDispenser = v49;
      if ( v49 == -2146367487 )
        break;
      if ( v49 < 0 )
        goto LABEL_116;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v46 + 64LL))(v46, 1, 0);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_116;
      *(_DWORD *)&pv[12 * v48] = *v52;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v46 + 64LL))(v46, 2, 0);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_116;
      *(_DWORD *)&pv[12 * v48 + 4] = *v52;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v46 + 64LL))(v46, 3, 0);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_116;
      *(_DWORD *)&pv[12 * v48++ + 8] = *v52;
    }
    if ( v47 != v48 )
      goto LABEL_115;
    v45 = v39 == v48;
LABEL_179:
    v35 = pv;
    if ( !v45 )
    {
      SimpleTableDispenser = -2147418113;
      goto LABEL_117;
    }
    Data4 = v61;
    v11 = this;
  }
  if ( !memcmp_0(&tidCOMSERVICES_CLASSES, v13, 0x10u) )
  {
    *((_DWORD *)v35 + 6) = 19;
    *(_QWORD *)(v35 + 28) = 4;
  }
  SimpleTableDispenser = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))Data4)(
                           *(_QWORD *)Data4,
                           &IID_ISimpleTableControl,
                           (__int64)&v11[3]);
  if ( SimpleTableDispenser >= 0 )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *))(**(_QWORD **)&v11[3].Data1 + 24LL))(
                             *(_QWORD *)&v11[3].Data1,
                             8,
                             v39,
                             v35);
    if ( SimpleTableDispenser >= 0 )
    {
      *a9 = (void *)((unsigned __int64)v11->Data4 & -(__int64)(v11 != (struct _GUID *)8));
      v50 = (unsigned __int64)v11->Data4 & -(__int64)(v11 != (struct _GUID *)8);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 8LL))(v50, 8LL - (_QWORD)v11);
      _InterlockedIncrement((volatile signed __int32 *)&v11[2]);
      SimpleTableDispenser = 0;
    }
  }
LABEL_117:
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  if ( v57 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
  }
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v35 )
    CoTaskMemFree(v35);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x180007ad0  mov     [rsp-8+arg_0], rcx
0x180007ad5  push    rbp
0x180007ad6  push    rbx
0x180007ad7  push    rsi
0x180007ad8  push    rdi
0x180007ad9  push    r12
0x180007adb  push    r13
0x180007add  push    r14
0x180007adf  push    r15
0x180007ae1  lea     rbp, [rsp-7]
0x180007ae6  sub     rsp, 0A8h
0x180007aed  mov     rsi, r9
0x180007af0  mov     rbx, r8
0x180007af3  mov     rax, rdx
0x180007af6  mov     r15, rcx
0x180007af9  xor     r14d, r14d
0x180007afc  mov     [rbp+3Fh+var_70], r14
0x180007b00  mov     [rbp+3Fh+var_78], r14
0x180007b04  mov     [rbp+3Fh+var_60], r14
0x180007b08  mov     [rbp+3Fh+var_68], r14
0x180007b0c  mov     [rbp+3Fh+var_80], r14d
0x180007b10  mov     [rbp+3Fh+var_58], r14d
0x180007b14  mov     [rbp+3Fh+var_54], r14d
0x180007b18  mov     [rbp+3Fh+var_88], r14
0x180007b1c  cmp     [rcx+20h], r14d
0x180007b20  jz      short loc_180007B2C
0x180007b22  mov     eax, 8000FFFFh
0x180007b27  jmp     loc_180008B6F
0x180007b2c  mov     rcx, [rbp+3Fh+arg_40]
0x180007b33  test    rcx, rcx
0x180007b36  jz      loc_180008B6A
0x180007b3c  mov     [rcx], r14
0x180007b3f  mov     r12d, 10h
0x180007b45  mov     r8d, r12d; Size
0x180007b48  lea     rdx, didAPPDU; Buf2
0x180007b4f  mov     rcx, rax; Buf1
0x180007b52  call    memcmp_0
0x180007b57  test    eax, eax
0x180007b59  jnz     loc_180008B6A
0x180007b5f  mov     r8d, r12d; Size
0x180007b62  lea     rdx, tidCOMSERVICES_CLASSES; Buf2
0x180007b69  mov     rcx, rbx; Buf1
0x180007b6c  call    memcmp_0
0x180007b71  test    eax, eax
0x180007b73  jz      loc_180007C01
0x180007b79  mov     r8d, r12d; Size
0x180007b7c  lea     rdx, tidCOMCLASSIC_FILEEXT; Buf2
0x180007b83  mov     rcx, rbx; Buf1
0x180007b86  call    memcmp_0
0x180007b8b  test    eax, eax
0x180007b8d  jz      short loc_180007C01
0x180007b8f  mov     r8d, r12d; Size
0x180007b92  lea     rdx, tidCOMCLASSIC_MIMETYPE; Buf2
0x180007b99  mov     rcx, rbx; Buf1
0x180007b9c  call    memcmp_0
0x180007ba1  test    eax, eax
0x180007ba3  jz      short loc_180007C01
0x180007ba5  mov     r8d, r12d; Size
0x180007ba8  lea     rdx, tidAPPDU_CLASSROLES; Buf2
0x180007baf  mov     rcx, rbx; Buf1
0x180007bb2  call    memcmp_0
0x180007bb7  test    eax, eax
0x180007bb9  jz      short loc_180007C01
0x180007bbb  mov     r8d, r12d; Size
0x180007bbe  lea     rdx, tidAPPDU_INTERFACEROLES; Buf2
0x180007bc5  mov     rcx, rbx; Buf1
0x180007bc8  call    memcmp_0
0x180007bcd  test    eax, eax
0x180007bcf  jz      short loc_180007C01
0x180007bd1  mov     r8d, r12d; Size
0x180007bd4  lea     rdx, tidAPPDU_INTERFACEPROP; Buf2
0x180007bdb  mov     rcx, rbx; Buf1
0x180007bde  call    memcmp_0
0x180007be3  test    eax, eax
0x180007be5  jz      short loc_180007C01
0x180007be7  mov     r8d, r12d; Size
0x180007bea  lea     rdx, tidAPPDU_METHOD; Buf2
0x180007bf1  mov     rcx, rbx; Buf1
0x180007bf4  call    memcmp_0
0x180007bf9  test    eax, eax
0x180007bfb  jnz     loc_180008B6A
0x180007c01  cmp     [rbp+3Fh+arg_38], r14
0x180007c08  jnz     loc_180008B6A
0x180007c0e  lea     rdi, [r15+40h]
0x180007c12  movups  xmm0, xmmword ptr [rbx]
0x180007c15  movdqu  xmmword ptr [rdi], xmm0
0x180007c19  cmp     [rbp+3Fh+arg_28], 1
0x180007c1d  jnz     loc_180008B63
0x180007c23  test    rsi, rsi
0x180007c26  jz      loc_180008B63
0x180007c2c  mov     r13d, dword ptr [rbp+3Fh+arg_20]
0x180007c30  test    r13d, r13d
0x180007c33  jz      loc_180008B63
0x180007c39  mov     r8, r12; Size
0x180007c3c  mov     rdx, rdi; Buf2
0x180007c3f  lea     rcx, tidAPPDU_METHOD; Buf1
0x180007c46  call    memcmp_0
0x180007c4b  test    eax, eax
0x180007c4d  jnz     short loc_180007C59
0x180007c4f  cmp     r13d, 3
0x180007c53  jb      loc_180008B63
0x180007c59  mov     [rbp+3Fh+pv], r14
0x180007c5d  mov     r12d, r14d
0x180007c60  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007c64  cmp     r12d, r13d
0x180007c67  jnb     loc_180007FB8
0x180007c6d  test    r12d, r12d
0x180007c70  jnz     short loc_180007C84
0x180007c72  cmp     dword ptr [rsi+0Ch], 0F0000000h
0x180007c79  jbe     loc_180007FA4
0x180007c7f  mov     rax, r14
0x180007c82  jmp     short loc_180007C87
0x180007c84  mov     eax, r12d
0x180007c87  lea     r14, [rax+rax*2]
0x180007c8b  mov     ebx, [rsi+r14*8+0Ch]
0x180007c90  cmp     ebx, 0F0000001h
0x180007c96  jnz     loc_180007D36
0x180007c9c  xor     ebx, ebx
0x180007c9e  cmp     [r15+38h], rbx
0x180007ca2  jnz     loc_180007FA4
0x180007ca8  cmp     dword ptr [rsi+r14*8+10h], 82h
0x180007cb1  jnz     loc_180007FA4
0x180007cb7  cmp     [rsi+r14*8+8], ebx
0x180007cbc  jnz     loc_180007FA4
0x180007cc2  mov     rcx, [rsi+r14*8]
0x180007cc6  test    rcx, rcx
0x180007cc9  jz      loc_180007FA4
0x180007ccf  mov     rax, r8
0x180007cd2  inc     rax
0x180007cd5  cmp     [rcx+rax*2], bx
0x180007cd9  jnz     short loc_180007CD2
0x180007cdb  lea     rbx, [rax+1]
0x180007cdf  mov     eax, 2
0x180007ce4  mul     rbx
0x180007ce7  cmovb   rax, r8
0x180007ceb  mov     rcx, rax; cb
0x180007cee  call    cs:__imp_CoTaskMemAlloc
0x180007cf4  mov     [r15+38h], rax
0x180007cf8  test    rax, rax
0x180007cfb  jz      loc_180007FAE
0x180007d01  mov     r8, [rsi+r14*8]; unsigned __int16 *
0x180007d05  mov     rdx, rbx; unsigned __int64
0x180007d08  mov     rcx, rax; unsigned __int16 *
0x180007d0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007d10  mov     ebx, eax
0x180007d12  xor     r14d, r14d
0x180007d15  test    eax, eax
0x180007d17  jns     loc_180007E46
0x180007d1d  mov     rcx, [r15+38h]; pv
0x180007d21  test    rcx, rcx
0x180007d24  jz      short loc_180007D2D
0x180007d26  call    cs:__imp_CoTaskMemFree
0x180007d2c  nop
0x180007d2d  mov     [r15+38h], r14
0x180007d31  jmp     loc_1800082AA
0x180007d36  mov     r8d, 10h; Size
0x180007d3c  mov     rdx, rdi; Buf2
0x180007d3f  lea     rcx, tidCOMCLASSIC_FILEEXT; Buf1
0x180007d46  call    memcmp_0
0x180007d4b  xor     ecx, ecx
0x180007d4d  test    eax, eax
0x180007d4f  jnz     short loc_180007D59
0x180007d51  test    ebx, ebx
0x180007d53  jz      loc_180007DF5
0x180007d59  mov     r8d, 10h; Size
0x180007d5f  mov     rdx, rdi; Buf2
0x180007d62  lea     rcx, tidCOMCLASSIC_MIMETYPE; Buf1
0x180007d69  call    memcmp_0
0x180007d6e  xor     ecx, ecx
0x180007d70  test    eax, eax
0x180007d72  jnz     short loc_180007D79
0x180007d74  cmp     ebx, 1
0x180007d77  jz      short loc_180007DF5
0x180007d79  mov     r8d, 10h; Size
0x180007d7f  mov     rdx, rdi; Buf2
0x180007d82  lea     rcx, tidAPPDU_CLASSROLES; Buf1
0x180007d89  call    memcmp_0
0x180007d8e  xor     ecx, ecx
0x180007d90  test    eax, eax
0x180007d92  jnz     short loc_180007D98
0x180007d94  test    ebx, ebx
0x180007d96  jz      short loc_180007DF5
0x180007d98  mov     r8d, 10h; Size
0x180007d9e  mov     rdx, rdi; Buf2
0x180007da1  lea     rcx, tidAPPDU_INTERFACEROLES; Buf1
0x180007da8  call    memcmp_0
0x180007dad  xor     ecx, ecx
0x180007daf  test    eax, eax
0x180007db1  jnz     short loc_180007DB7
0x180007db3  test    ebx, ebx
0x180007db5  jz      short loc_180007DF5
0x180007db7  mov     r8d, 10h; Size
0x180007dbd  mov     rdx, rdi; Buf2
0x180007dc0  lea     rcx, tidAPPDU_INTERFACEPROP; Buf1
0x180007dc7  call    memcmp_0
0x180007dcc  xor     ecx, ecx
0x180007dce  test    eax, eax
0x180007dd0  jnz     short loc_180007DD6
0x180007dd2  test    ebx, ebx
0x180007dd4  jz      short loc_180007DF5
0x180007dd6  mov     r8d, 10h; Size
0x180007ddc  mov     rdx, rdi; Buf2
0x180007ddf  lea     rcx, tidAPPDU_METHOD; Buf1
0x180007de6  call    memcmp_0
0x180007deb  xor     ecx, ecx
0x180007ded  test    eax, eax
0x180007def  jnz     short loc_180007E4E
0x180007df1  test    ebx, ebx
0x180007df3  jnz     short loc_180007E4E
0x180007df5  cmp     [r15+50h], rcx
0x180007df9  jnz     loc_180007FA4
0x180007dff  cmp     dword ptr [rsi+r14*8+10h], 48h ; 'H'
0x180007e05  jnz     loc_180007FA4
0x180007e0b  cmp     [rsi+r14*8+8], ecx
0x180007e10  jnz     loc_180007FA4
0x180007e16  cmp     [rsi+r14*8], rcx
0x180007e1a  jz      loc_180007FA4
0x180007e20  mov     ecx, 10h; cb
0x180007e25  call    cs:__imp_CoTaskMemAlloc
0x180007e2b  mov     [r15+50h], rax
0x180007e2f  test    rax, rax
0x180007e32  jz      loc_180007FAE
0x180007e38  mov     rcx, [rsi+r14*8]
0x180007e3c  movups  xmm0, xmmword ptr [rcx]
0x180007e3f  movdqu  xmmword ptr [rax], xmm0
0x180007e43  xor     r14d, r14d
0x180007e46  inc     r12d
0x180007e49  jmp     loc_180007C60
0x180007e4e  mov     r8d, 10h; Size
0x180007e54  mov     rdx, rdi; Buf2
0x180007e57  lea     rcx, tidAPPDU_INTERFACEROLES; Buf1
0x180007e5e  call    memcmp_0
0x180007e63  test    eax, eax
0x180007e65  jnz     short loc_180007E6C
0x180007e67  cmp     ebx, 3
0x180007e6a  jz      short loc_180007EA8
0x180007e6c  mov     r8d, 10h; Size
0x180007e72  mov     rdx, rdi; Buf2
0x180007e75  lea     rcx, tidAPPDU_INTERFACEPROP; Buf1
0x180007e7c  call    memcmp_0
0x180007e81  test    eax, eax
0x180007e83  jnz     short loc_180007E8A
0x180007e85  cmp     ebx, 3
0x180007e88  jz      short loc_180007EA8
0x180007e8a  mov     r8d, 10h; Size
0x180007e90  mov     rdx, rdi; Buf2
0x180007e93  lea     rcx, tidAPPDU_METHOD; Buf1
0x180007e9a  call    memcmp_0
0x180007e9f  test    eax, eax
0x180007ea1  jnz     short loc_180007EE7
0x180007ea3  cmp     ebx, 3
0x180007ea6  jnz     short loc_180007EE7
0x180007ea8  xor     ebx, ebx
0x180007eaa  cmp     [r15+50h], rbx
0x180007eae  jz      loc_180008B63
0x180007eb4  cmp     dword ptr [rsi+r14*8+10h], 48h ; 'H'
0x180007eba  jnz     loc_180007FA4
0x180007ec0  cmp     [rsi+r14*8+8], ebx
0x180007ec5  jnz     loc_180007FA4
0x180007ecb  cmp     [rsi+r14*8], rbx
0x180007ecf  jz      loc_180007FA4
0x180007ed5  lea     ecx, [rbx+10h]; cb
0x180007ed8  call    cs:__imp_CoTaskMemAlloc
0x180007ede  mov     [r15+58h], rax
0x180007ee2  jmp     loc_180007E2F
0x180007ee7  mov     r8d, 10h; Size
0x180007eed  mov     rdx, rdi; Buf2
0x180007ef0  lea     rcx, tidAPPDU_METHOD; Buf1
0x180007ef7  call    memcmp_0
0x180007efc  test    eax, eax
0x180007efe  jnz     loc_180007E43
0x180007f04  cmp     ebx, 8
0x180007f07  jnz     loc_180007E43
0x180007f0d  xor     ebx, ebx
0x180007f0f  cmp     [r15+50h], rbx
0x180007f13  jz      loc_180008B63
0x180007f19  cmp     [r15+58h], rbx
0x180007f1d  jz      loc_180008B63
0x180007f23  cmp     dword ptr [rsi+r14*8+10h], 82h
0x180007f2c  jnz     short loc_180007FA4
0x180007f2e  cmp     [rsi+r14*8+8], ebx
0x180007f33  jnz     short loc_180007FA4
0x180007f35  mov     rcx, [rsi+r14*8]; unsigned __int16 *
0x180007f39  test    rcx, rcx
0x180007f3c  jz      short loc_180007FA4
0x180007f3e  cmp     bx, [rcx]
0x180007f41  jz      short loc_180007FA4
0x180007f43  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180007f48  lea     ebx, [rax+1]
0x180007f4b  mov     eax, 2
0x180007f50  mul     rbx
0x180007f53  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007f5a  cmovb   rax, rcx
0x180007f5e  mov     rcx, rax; cb
0x180007f61  call    cs:__imp_CoTaskMemAlloc
0x180007f67  mov     [r15+60h], rax
0x180007f6b  test    rax, rax
0x180007f6e  jz      short loc_180007FAE
0x180007f70  mov     r8, [rsi+r14*8]; unsigned __int16 *
0x180007f74  mov     edx, ebx; unsigned __int64
  ... truncated ...
```
