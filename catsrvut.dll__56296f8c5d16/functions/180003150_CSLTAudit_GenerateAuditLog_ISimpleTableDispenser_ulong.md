# CSLTAudit::GenerateAuditLog(ISimpleTableDispenser *,ulong)

- ea: `0x180003150`
- end: `0x180003d6d`
- name: `?GenerateAuditLog@CSLTAudit@@EEAAJPEAUISimpleTableDispenser@@K@Z`
- size: `3101`
- prototype: `__int64 __fastcall(CSLTAudit *__hidden this, struct ISimpleTableDispenser *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003150`
- `0x180007414`
- `0x1800074d8`
- `0x1800075d4`
- `0x180007a4c`
- `0x1800094a4`
- `0x180009c6c`
- `0x180043b94`
- `0x18005583a`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800032bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800032bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ba5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::GenerateAuditLog(CSLTAudit *this, struct ISimpleTableDispenser *a2, unsigned int a3)
{
  unsigned int v3; // r13d
  int v6; // ebx
  unsigned int v8; // ebx
  LPVOID *v9; // r14
  __int64 v10; // rax
  unsigned __int64 i; // rdx
  int v12; // edi
  __int64 v13; // r8
  __int64 v14; // rax
  bool v15; // zf
  unsigned int v16; // eax
  __int64 v17; // rdi
  LPVOID *v18; // rax
  LPVOID *v19; // r9
  unsigned int v20; // r15d
  unsigned int v21; // r12d
  LPVOID *v22; // rax
  unsigned int v23; // r14d
  unsigned int v24; // eax
  CSLTAudit *v25; // rcx
  int IsAllowedColumnForQuery; // eax
  unsigned int v27; // r13d
  __int64 v28; // rcx
  CSLTAudit *v29; // rcx
  int v30; // eax
  __int64 v31; // r11
  void *v32; // rcx
  CSLTAudit *v33; // rcx
  unsigned __int16 *v34; // rdi
  int v35; // eax
  CSLTAudit *v36; // rcx
  unsigned __int16 *v37; // rdi
  int v38; // eax
  int v39; // eax
  int v40; // edx
  int v41; // r14d
  int v42; // eax
  unsigned int j; // ebx
  __int64 v44; // rcx
  __int64 v45; // r15
  __int64 *k; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  int v52; // eax
  CSLTAudit *v53; // rcx
  __int64 v54; // rax
  int v55; // eax
  __int64 (__fastcall *v56)(CSLTAudit *, __int64, _QWORD, _QWORD, void *, __int64, void *, unsigned __int16 **, BOOL); // rdi
  __int64 v57; // rax
  BOOL v58; // eax
  int v59; // eax
  int v60; // eax
  __int64 v61; // r10
  __int64 v62; // rdx
  unsigned int v63; // r8d
  unsigned int v64; // r10d
  _WORD *v65; // rax
  __int64 v66; // rax
  const unsigned __int16 *v67; // rcx
  unsigned __int16 v68; // r9
  _WORD *v69; // rcx
  unsigned int m; // ebx
  unsigned int n; // ebx
  __int64 v72; // [rsp+20h] [rbp-E0h]
  __int64 v73; // [rsp+28h] [rbp-D8h]
  __int64 v74; // [rsp+28h] [rbp-D8h]
  unsigned int v75; // [rsp+50h] [rbp-B0h]
  unsigned int v76; // [rsp+54h] [rbp-ACh]
  LPVOID *pv; // [rsp+58h] [rbp-A8h]
  LPVOID *v78; // [rsp+60h] [rbp-A0h]
  unsigned int v79; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v80; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v81; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v82; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v83; // [rsp+78h] [rbp-88h] BYREF
  int v84; // [rsp+7Ch] [rbp-84h] BYREF
  void *v85; // [rsp+80h] [rbp-80h] BYREF
  int v86[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v87; // [rsp+90h] [rbp-70h] BYREF
  int v88; // [rsp+98h] [rbp-68h] BYREF
  char *v89; // [rsp+A0h] [rbp-60h] BYREF
  void *v90; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v92; // [rsp+B8h] [rbp-48h] BYREF
  int v93; // [rsp+C0h] [rbp-40h]
  __int64 v94; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v95; // [rsp+D0h] [rbp-30h] BYREF
  int v96; // [rsp+D8h] [rbp-28h]
  char *v97; // [rsp+E0h] [rbp-20h] BYREF
  int v98; // [rsp+E8h] [rbp-18h]
  int v99; // [rsp+ECh] [rbp-14h]
  int v100; // [rsp+F0h] [rbp-10h]
  int v101; // [rsp+F4h] [rbp-Ch]
  __int64 v102; // [rsp+F8h] [rbp-8h]
  int v103; // [rsp+100h] [rbp+0h]
  int v104; // [rsp+104h] [rbp+4h]
  __int64 v105; // [rsp+108h] [rbp+8h]
  _OWORD v106[6]; // [rsp+170h] [rbp+70h] BYREF

  v3 = a3;
  v79 = a3;
  v87 = 0;
  v91 = 0;
  v82 = 0;
  v80 = 0;
  v89 = 0;
  v81 = 0;
  v84 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v6 = CImpersonate::SuspendImpersonation((CImpersonate *)&v92);
  if ( v6 < 0 )
    goto LABEL_2;
  v8 = 0;
  v76 = 0;
  v75 = 0;
  v9 = 0;
  pv = 0;
  v10 = *((_QWORD *)this + 8) - *(_QWORD *)&tidCOMSERVICES_CLASSES.Data1;
  if ( !v10 )
    v10 = *((_QWORD *)this + 9) - *(_QWORD *)tidCOMSERVICES_CLASSES.Data4;
  if ( !v10 )
  {
    v8 = 2;
    v97 = (char *)this + 88;
    v98 = 0;
    v99 = -268435451;
    v100 = 19;
    v101 = 4;
    v102 = 0;
    v103 = 0;
    v104 = -268435454;
    v105 = 130;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 5) + 72LL))(
          *((_QWORD *)this + 5),
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          &v81);
  if ( v12 < 0 )
  {
    v19 = 0;
    v20 = 0;
    v21 = 0;
    goto LABEL_140;
  }
  v14 = *((_QWORD *)this + 8) - *(_QWORD *)&tidCOMSERVICES_CLASSES.Data1;
  if ( !v14 )
    v14 = *((_QWORD *)this + 9) - *(_QWORD *)tidCOMSERVICES_CLASSES.Data4;
  v15 = v14 == 0;
  v16 = v81;
  if ( v15 )
    v16 = v81 + 11;
  v17 = v16;
  v18 = (LPVOID *)CoTaskMemAlloc(saturated_mul(v16, 8u));
  v9 = v18;
  v78 = v18;
  if ( v18 )
  {
    memset_0(v18, 0, 8 * v17);
    v22 = (LPVOID *)CoTaskMemAlloc(saturated_mul(v81, 8u));
    v19 = v22;
    pv = v22;
    if ( !v22 )
    {
      v12 = -2147024882;
      v20 = 0;
      v21 = 0;
      goto LABEL_140;
    }
    memset_0(v22, 0, 8LL * v81);
    v23 = 0;
    v19 = pv;
    while ( 1 )
    {
      v24 = v81;
      if ( v23 >= v81 )
        break;
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 5) + 80LL))(
              *((_QWORD *)this + 5),
              v23,
              0,
              0,
              &v84);
      if ( v12 < 0 )
        goto LABEL_50;
      if ( (v84 & 1) == 0 )
      {
        v13 = *((_QWORD *)this + 10);
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v13 + 48); i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v13 + 56) + 4 * i) == v23 )
          {
            v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *, unsigned int *, char **))(**((_QWORD **)this + 5) + 152LL))(
                    *((_QWORD *)this + 5),
                    v23,
                    0,
                    &v82,
                    &v80,
                    &v89);
            if ( v12 >= 0 )
            {
              v95 = 0;
              v85 = 0;
              v12 = CTableInfo::LookupOrdinalName(*((CTableInfo **)this + 10), v23, (const unsigned __int16 **)&v95);
              if ( v12 >= 0 )
              {
                v34 = v95;
                if ( !v95 )
                  goto LABEL_47;
                v35 = CSLTAudit::HideField(v33, (const struct _GUID *)this + 4, v23);
                v12 = (*(__int64 (__fastcall **)(CSLTAudit *, unsigned __int16 *, _QWORD, _QWORD, char *, void **, int))(*(_QWORD *)this + 72LL))(
                        this,
                        v34,
                        v82,
                        v80,
                        v89,
                        &v85,
                        v35);
                if ( v12 >= 0 )
                {
                  v32 = v85;
                  goto LABEL_37;
                }
              }
            }
            goto LABEL_50;
          }
        }
        if ( v3 != 1 )
          goto LABEL_47;
        v95 = 0;
        *(_QWORD *)v86 = 0;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *, unsigned int *, char **))(**((_QWORD **)this + 5) + 152LL))(
                *((_QWORD *)this + 5),
                v23,
                0,
                &v82,
                &v80,
                &v89);
        if ( v12 >= 0 )
        {
          v12 = CTableInfo::LookupOrdinalName(*((CTableInfo **)this + 10), v23, (const unsigned __int16 **)&v95);
          if ( v12 >= 0 )
          {
            v37 = v95;
            if ( !v95 )
              goto LABEL_47;
            v38 = CSLTAudit::HideField(v36, (const struct _GUID *)this + 4, v23);
            v12 = (*(__int64 (__fastcall **)(CSLTAudit *, unsigned __int16 *, _QWORD, _QWORD, char *, int *, int))(*(_QWORD *)this + 72LL))(
                    this,
                    v37,
                    v82,
                    v80,
                    v89,
                    v86,
                    v38);
            if ( v12 >= 0 )
            {
              v19 = pv;
              if ( *(_QWORD *)v86 )
              {
                i = (unsigned __int64)v78;
                v78[v75] = *(LPVOID *)v86;
                v13 = ++v75;
              }
              goto LABEL_48;
            }
          }
        }
        goto LABEL_50;
      }
      if ( v8 >= 6 )
      {
        v12 = -2147418113;
        goto LABEL_50;
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *, unsigned int *, char **))(**((_QWORD **)this + 5) + 152LL))(
              *((_QWORD *)this + 5),
              v23,
              0,
              &v82,
              &v80,
              &v89);
      if ( v12 < 0 )
        goto LABEL_50;
      IsAllowedColumnForQuery = CSLTAudit::IsAllowedColumnForQuery(v25, (const struct _GUID *)this + 4, v23);
      v27 = v82;
      if ( IsAllowedColumnForQuery )
      {
        v28 = 3LL * v8;
        (&v97)[v28] = v89;
        *(&v98 + 2 * v28) = 0;
        *(&v99 + 2 * v28) = v23;
        *(&v100 + 2 * v28) = v27;
        *(&v101 + 2 * v28) = v80;
        ++v8;
      }
      v95 = 0;
      v90 = 0;
      v12 = CTableInfo::LookupOrdinalName(*((CTableInfo **)this + 10), v23, (const unsigned __int16 **)&v95);
      if ( v12 < 0 )
        goto LABEL_50;
      if ( v95 )
      {
        v30 = CSLTAudit::HideField(v29, (const struct _GUID *)this + 4, v23);
        v12 = (*(__int64 (__fastcall **)(CSLTAudit *, __int64, _QWORD, _QWORD, char *, void **, int))(*(_QWORD *)this + 72LL))(
                this,
                v31,
                v27,
                v80,
                v89,
                &v90,
                v30);
        if ( v12 < 0 )
          goto LABEL_50;
        v32 = v90;
        v3 = v79;
LABEL_37:
        v19 = pv;
        if ( v32 )
        {
          pv[v76] = v32;
          i = ++v76;
        }
      }
      else
      {
        v3 = v79;
LABEL_47:
        v19 = pv;
      }
LABEL_48:
      ++v23;
    }
    if ( !v8 )
    {
      v12 = -2147418113;
      v9 = v78;
      v20 = v75;
      v21 = v76;
      goto LABEL_140;
    }
    if ( v3 != 1 )
    {
      v39 = *((_DWORD *)this + 7);
      v40 = 0x200000;
      v41 = 0;
      if ( (v39 & 0x200000) == 0 )
      {
        v40 = 0;
        if ( (v39 & 0x400000) != 0 )
          v40 = 0x400000;
      }
      LODWORD(v73) = 1;
      v12 = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, char *, char **, _QWORD, __int64, unsigned int, __int64 *))(*(_QWORD *)a2 + 24LL))(
              a2,
              &didCOMSERVICES,
              (char *)this + 64,
              &v97,
              v8,
              v73,
              v40 | 1u,
              &v87);
      if ( v12 < 0 )
        goto LABEL_50;
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v87 + 24LL))(v87);
      if ( v12 == -2146367486 )
      {
        v95 = 0;
        v96 = 0;
        v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v87)(v87, &IID_ISimpleTableControl, &v91);
        if ( v6 < 0 )
        {
LABEL_2:
          CImpersonate::~CImpersonate((CImpersonate *)&v92);
          return (unsigned int)v6;
        }
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v91 + 96LL))(v91, 0, &v95);
        if ( v12 < 0 )
          goto LABEL_50;
        v12 = HIDWORD(v95);
      }
      if ( v12 < 0 )
        goto LABEL_50;
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v87 + 32LL))(v87);
      if ( v12 < 0 )
        goto LABEL_50;
      v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v87 + 40LL))(v87);
      v12 = v42;
      if ( v42 == -2146367487 )
      {
        v12 = -2146367479;
        goto LABEL_50;
      }
      if ( v42 < 0 )
      {
LABEL_50:
        v9 = v78;
        v20 = v75;
        goto LABEL_51;
      }
      for ( j = 0; ; ++j )
      {
        v24 = v81;
        if ( j >= v81 )
          break;
        v79 = 0;
        v83 = 0;
        v85 = 0;
        v88 = 0;
        v90 = 0;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 5) + 80LL))(
                *((_QWORD *)this + 5),
                j,
                0,
                0,
                &v84);
        if ( v12 < 0 )
          goto LABEL_50;
        if ( (v84 & 1) == 0 )
        {
          v95 = 0;
          memset(v106, 0, sizeof(v106));
          v86[0] = 0;
          v44 = *((_QWORD *)this + 10);
          v45 = 0;
          if ( *(_QWORD *)v44 )
          {
            for ( k = (__int64 *)(*(_QWORD *)v44 + 8LL * (j % *(_DWORD *)(v44 + 8))); ; k = (__int64 *)(v47 + 16) )
            {
              v47 = *k;
              if ( !v47 )
                break;
              if ( *(_DWORD *)(v47 + 28) == j )
              {
                v45 = *(_QWORD *)(*(_QWORD *)(v47 + 32) + 8LL);
                if ( v45 )
                  goto LABEL_83;
                break;
              }
            }
          }
          if ( j == 30 )
          {
            v48 = *((_QWORD *)this + 8) - *(_QWORD *)&tidCOMSERVICES_CLASSES.Data1;
            if ( !v48 )
              v48 = *((_QWORD *)this + 9) - *(_QWORD *)tidCOMSERVICES_CLASSES.Data4;
            if ( !v48 )
            {
              v41 = 1;
LABEL_83:
              v49 = tidCOMSERVICES_LT_ROLESBYCLSID - *((_QWORD *)this + 8);
              if ( tidCOMSERVICES_LT_ROLESBYCLSID == *((_QWORD *)this + 8) )
                v49 = 0xCAE5B0086000359DuLL - *((_QWORD *)this + 9);
              if ( !v49 && j == 4 )
                goto LABEL_95;
              v50 = tidCOMSERVICES_LT_ROLESBYINTERFACE - *((_QWORD *)this + 8);
              if ( tidCOMSERVICES_LT_ROLESBYINTERFACE == *((_QWORD *)this + 8) )
                v50 = 0xCAE5B0086000359DuLL - *((_QWORD *)this + 9);
              if ( !v50 && j == 5 )
                goto LABEL_95;
              v51 = tidCOMSERVICES_LT_ROLESBYMETHOD - *((_QWORD *)this + 8);
              if ( tidCOMSERVICES_LT_ROLESBYMETHOD == *((_QWORD *)this + 8) )
                v51 = 0xCAE5B0086000359DuLL - *((_QWORD *)this + 9);
              if ( v51 || j != 8 )
                v52 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *, unsigned int *, void **))(*(_QWORD *)v87 + 64LL))(
                        v87,
                        j,
                        &v79,
                        &v83,
                        &v85);
              else
LABEL_95:
                v52 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *, unsigned int *, void **))(**((_QWORD **)this + 5) + 152LL))(
                        *((_QWORD *)this + 5),
                        j,
                        0,
                        &v79,
                        &v83,
                        &v85);
              v12 = v52;
              if ( v52 < 0 )
                goto LABEL_50;
              if ( v3 == 2 )
              {
                v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *, void **))(**((_QWORD **)this + 5)
                                                                                                + 152LL))(
                        *((_QWORD *)this + 5),
                        j,
                        0,
                        0,
                        &v88,
                        &v90);
                if ( v12 < 0 )
                  goto LABEL_50;
                v54 = *(_QWORD *)this;
                if ( v41 )
                {
                  LODWORD(v72) = v88;
                  v55 = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, _QWORD, void *, __int64, void *, int *, _OWORD *))(v54 + 64))(
                          this,
                          v79,
                          v83,
                          v85,
                          v72,
                          v90,
                          v86,
                          v106);
                }
                else
                {
                  v56 = *(__int64 (__fastcall **)(CSLTAudit *, __int64, _QWORD, _QWORD, void *, __int64, void *, unsigned __int16 **, BOOL))(v54 + 56);
                  v57 = *(_QWORD *)&TID_APPLICATION.Data1 - *((_QWORD *)this + 8);
                  if ( *(_QWORD *)&TID_APPLICATION.Data1 == *((_QWORD *)this + 8) )
                    v57 = *(_QWORD *)TID_APPLICATION.Data4 - *((_QWORD *)this + 9);
                  v58 = !v57 && j == 15;
                  LODWORD(v74) = v88;
                  v55 = v56(this, v45, v79, v83, v85, v74, v90, &v95, v58);
                }
                v12 = v55;
                if ( v55 < 0 )
                  goto LABEL_50;
              }
              else
              {
                if ( v41 )
                {
                  v59 = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, _QWORD, void *, int *, _OWORD *))(*(_QWORD *)this + 80LL))(
                          this,
                          v79,
                          v83,
                          v85,
                          v86,
                          v106);
                }
                else
                {
                  v60 = CSLTAudit::HideField(v53, (const struct _GUID *)this + 4, j);
                  v59 = (*(__int64 (__fastcall **)(CSLTAudit *, __int64, _QWORD, _QWORD, void *, unsigned __int16 **, int))(v61 + 72))(
                          this,
                          v45,
                          v79,
                          v83,
                          v85,
                          &v95,
                          v60);
                }
                v12 = v59;
                if ( v59 < 0 )
                  goto LABEL_50;
              }
              if ( v41 )
              {
                v62 = 0;
                v63 = v86[0];
                if ( v86[0] )
                {
                  v64 = v75;
                  do
                  {
                    v78[v64++] = (LPVOID)*((_QWORD *)v106 + v62);
                    v62 = (unsigned int)(v62 + 1);
                  }
                  while ( (unsigned int)v62 < v63 );
                  v75 = v64;
                }
              }
              else if ( v95 )
              {
                v78[v75++] = v95;
              }
            }
          }
        }
        v41 = 0;
      }
    }
    v20 = v75;
    if ( v75 || !v24 )
    {
      v9 = v78;
    }
    else
    {
      v65 = CoTaskMemAlloc(0xEu);
      i = (unsigned __int64)v65;
      v9 = v78;
      if ( !v65 )
      {
        v12 = -2147024882;
        v19 = pv;
        v21 = v76;
        goto LABEL_140;
      }
      *v78 = v65;
      v66 = 2147483646;
      v20 = 1;
      v67 = L"<null>";
      v13 = 7;
      do
      {
        if ( !v66 )
          break;
        v68 = *v67;
        if ( !*v67 )
          break;
        ++v67;
        *(_WORD *)i = v68;
        i += 2LL;
        --v66;
        --v13;
      }
      while ( v13 );
      v12 = -2147024774;
      if ( v13 )
        v12 = 0;
      v69 = (_WORD *)(i - 2);
      if ( v13 )
        v69 = (_WORD *)i;
      *v69 = 0;
      if ( !v13 )
      {
LABEL_51:
        v19 = pv;
        v21 = v76;
        goto LABEL_140;
      }
    }
    LODWORD(v73) = v20;
    v21 = v76;
    v12 = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, _QWORD, _QWORD, LPVOID *, __int64, LPVOID *))(*(_QWORD *)this + 104LL))(
            this,
            *((_QWORD *)this + 10),
            v3,
            v76,
            pv,
            v73,
            v9);
    v19 = pv;
    goto LABEL_140;
  }
  v12 = -2147024882;
  v19 = 0;
  v20 = 0;
  v21 = 0;
LABEL_140:
  if ( (v93 & 1) != 0 )
  {
    v12 = CImpersonate::ResumeImpersonation((CImpersonate *)&v92);
    v19 = pv;
  }
  if ( v87 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
    v87 = 0;
    v19 = pv;
  }
  if ( v91 )
  {
    (*(void (__fastcall **)(__int64, unsigned __int64, __int64, LPVOID *))(*(_QWORD *)v91 + 16LL))(v91, i, v13, v19);
    v91 = 0;
    v19 = pv;
  }
  if ( v19 )
  {
    for ( m = 0; m < v21; v19 = pv )
      CoTaskMemFree(v19[m++]);
    CoTaskMemFree(v19);
  }
  if ( v9 )
  {
    for ( n = 0; n < v20; ++n )
      CoTaskMemFree(v9[n]);
    CoTaskMemFree(v9);
  }
  v86[0] = 0;
  if ( (v93 & 1) != 0 || v92 )
    CImpersonate::Cleanup((CImpersonate *)&v92, v86);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180003150  mov     [rsp-8+arg_18], rbx
0x180003155  push    rbp
0x180003156  push    rsi
0x180003157  push    rdi
0x180003158  push    r12
0x18000315a  push    r13
0x18000315c  push    r14
0x18000315e  push    r15
0x180003160  lea     rbp, [rsp-0E0h]
0x180003168  sub     rsp, 1E0h
0x18000316f  mov     rax, cs:__security_cookie
0x180003176  xor     rax, rsp
0x180003179  mov     [rbp+110h+var_40], rax
0x180003180  mov     r13d, r8d
0x180003183  mov     [rsp+210h+var_1A8], r8d
0x180003188  mov     r15, rdx
0x18000318b  mov     rsi, rcx
0x18000318e  xor     edi, edi
0x180003190  mov     [rbp+110h+var_180], rdi
0x180003194  mov     [rbp+110h+var_160], rdi
0x180003198  mov     [rsp+210h+var_19C], edi
0x18000319c  mov     [rsp+210h+var_1A4], edi
0x1800031a0  mov     [rbp+110h+var_170], rdi
0x1800031a4  mov     [rsp+210h+var_1A0], edi
0x1800031a8  mov     [rsp+210h+var_194], edi
0x1800031ac  mov     [rbp+110h+var_158], rdi
0x1800031b0  mov     [rbp+110h+var_150], edi
0x1800031b3  mov     [rbp+110h+var_148], rdi
0x1800031b7  lea     rcx, [rbp+110h+var_158]; this
0x1800031bb  call    ?SuspendImpersonation@CImpersonate@@QEAAJXZ; CImpersonate::SuspendImpersonation(void)
0x1800031c0  mov     ebx, eax
0x1800031c2  test    eax, eax
0x1800031c4  jns     short loc_1800031D6
0x1800031c6  lea     rcx, [rbp+110h+var_158]; this
0x1800031ca  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1800031cf  mov     eax, ebx
0x1800031d1  jmp     loc_180003D43
0x1800031d6  mov     ebx, edi
0x1800031d8  mov     [rsp+210h+var_1BC], edi
0x1800031dc  mov     [rsp+210h+var_1C0], edi
0x1800031e0  mov     r14, rdi
0x1800031e3  mov     [rsp+210h+pv], rdi
0x1800031e8  mov     rax, [rsi+40h]
0x1800031ec  sub     rax, qword ptr cs:tidCOMSERVICES_CLASSES.Data1
0x1800031f3  jnz     short loc_180003200
0x1800031f5  mov     rax, [rsi+48h]
0x1800031f9  sub     rax, qword ptr cs:tidCOMSERVICES_CLASSES.Data4
0x180003200  test    rax, rax
0x180003203  jnz     short loc_180003240
0x180003205  mov     ebx, 2
0x18000320a  lea     rax, [rsi+58h]
0x18000320e  mov     [rbp+110h+var_130], rax
0x180003212  mov     [rbp+110h+var_128], edi
0x180003215  mov     [rbp+110h+var_124], 0F0000005h
0x18000321c  mov     [rbp+110h+var_120], 13h
0x180003223  mov     [rbp+110h+var_11C], 4
0x18000322a  mov     [rbp+110h+var_118], rdi
0x18000322e  mov     [rbp+110h+var_110], edi
0x180003231  mov     [rbp+110h+var_10C], 0F0000002h
0x180003238  mov     [rbp+110h+var_108], 82h
0x180003240  mov     rcx, [rsi+28h]
0x180003244  mov     rax, [rcx]
0x180003247  lea     rdx, [rsp+210h+var_1A0]
0x18000324c  mov     [rsp+210h+var_1D0], rdx
0x180003251  mov     [rsp+210h+var_1D8], rdi
0x180003256  mov     [rsp+210h+var_1E0], rdi
0x18000325b  mov     [rsp+210h+var_1E8], rdi
0x180003260  mov     [rsp+210h+var_1F0], rdi
0x180003265  xor     r9d, r9d
0x180003268  xor     r8d, r8d
0x18000326b  xor     edx, edx
0x18000326d  mov     rax, [rax+48h]
0x180003271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003276  mov     edi, eax
0x180003278  test    eax, eax
0x18000327a  js      loc_180003C69
0x180003280  mov     rax, [rsi+40h]
0x180003284  sub     rax, qword ptr cs:tidCOMSERVICES_CLASSES.Data1
0x18000328b  jnz     short loc_180003298
0x18000328d  mov     rax, [rsi+48h]
0x180003291  sub     rax, qword ptr cs:tidCOMSERVICES_CLASSES.Data4
0x180003298  test    rax, rax
0x18000329b  mov     eax, [rsp+210h+var_1A0]
0x18000329f  jnz     short loc_1800032A4
0x1800032a1  add     eax, 0Bh
0x1800032a4  mov     edi, eax
0x1800032a6  mov     eax, 8
0x1800032ab  mul     rdi
0x1800032ae  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800032b5  cmovb   rax, rcx
0x1800032b9  mov     rcx, rax; cb
0x1800032bc  call    cs:__imp_CoTaskMemAlloc
0x1800032c2  mov     r14, rax
0x1800032c5  mov     [rsp+210h+var_1B0], rax
0x1800032ca  test    rax, rax
0x1800032cd  jnz     short loc_1800032E4
0x1800032cf  mov     edi, 8007000Eh
0x1800032d4  mov     r9, [rsp+210h+pv]
0x1800032d9  mov     r15d, r9d
0x1800032dc  mov     r12d, r9d
0x1800032df  jmp     loc_180003C72
0x1800032e4  lea     r8, ds:0[rdi*8]; Size
0x1800032ec  xor     edx, edx; Val
0x1800032ee  mov     rcx, rax; void *
0x1800032f1  call    memset_0
0x1800032f6  mov     ecx, [rsp+210h+var_1A0]
0x1800032fa  mov     eax, 8
0x1800032ff  mul     rcx
0x180003302  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003309  cmovb   rax, rcx
0x18000330d  mov     rcx, rax; cb
0x180003310  call    cs:__imp_CoTaskMemAlloc
0x180003316  mov     r9, rax
0x180003319  mov     [rsp+210h+pv], rax
0x18000331e  test    rax, rax
0x180003321  jnz     short loc_180003335
0x180003323  mov     edi, 8007000Eh
0x180003328  mov     r15d, [rsp+210h+var_1C0]
0x18000332d  mov     r12d, r15d
0x180003330  jmp     loc_180003C72
0x180003335  mov     r8d, [rsp+210h+var_1A0]
0x18000333a  shl     r8, 3; Size
0x18000333e  xor     edx, edx; Val
0x180003340  mov     rcx, rax; void *
0x180003343  call    memset_0
0x180003348  xor     r14d, r14d
0x18000334b  mov     r9, [rsp+210h+pv]
0x180003350  mov     eax, [rsp+210h+var_1A0]
0x180003354  cmp     r14d, eax
0x180003357  jnb     loc_1800036B0
0x18000335d  mov     rcx, [rsi+28h]
0x180003361  mov     rax, [rcx]
0x180003364  lea     rdx, [rsp+210h+var_194]
0x180003369  mov     [rsp+210h+var_1F0], rdx
0x18000336e  xor     r9d, r9d
0x180003371  xor     r8d, r8d
0x180003374  mov     edx, r14d
0x180003377  mov     rax, [rax+50h]
0x18000337b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003380  mov     edi, eax
0x180003382  test    eax, eax
0x180003384  js      loc_180003697
0x18000338a  test    byte ptr [rsp+210h+var_194], 1
0x18000338f  jz      loc_1800034A1
0x180003395  cmp     ebx, 6
0x180003398  jnb     loc_180003692
0x18000339e  mov     rcx, [rsi+28h]
0x1800033a2  mov     rax, [rcx]
0x1800033a5  lea     rdx, [rbp+110h+var_170]
0x1800033a9  mov     [rsp+210h+var_1E8], rdx
0x1800033ae  lea     rdx, [rsp+210h+var_1A4]
0x1800033b3  mov     [rsp+210h+var_1F0], rdx
0x1800033b8  lea     r9, [rsp+210h+var_19C]
0x1800033bd  xor     r8d, r8d
0x1800033c0  mov     edx, r14d
0x1800033c3  mov     rax, [rax+98h]
0x1800033ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033cf  mov     edi, eax
0x1800033d1  test    eax, eax
0x1800033d3  js      loc_180003697
0x1800033d9  mov     r8d, r14d; unsigned int
0x1800033dc  lea     rdx, [rsi+40h]; struct _GUID *
0x1800033e0  call    ?IsAllowedColumnForQuery@CSLTAudit@@AEAAHAEBU_GUID@@K@Z; CSLTAudit::IsAllowedColumnForQuery(_GUID const &,ulong)
0x1800033e5  mov     r13d, [rsp+210h+var_19C]
0x1800033ea  test    eax, eax
0x1800033ec  jz      short loc_180003419
0x1800033ee  mov     eax, ebx
0x1800033f0  lea     rcx, [rax+rax*2]
0x1800033f4  mov     rax, [rbp+110h+var_170]
0x1800033f8  mov     [rbp+rcx*8+110h+var_130], rax
0x1800033fd  mov     [rbp+rcx*8+110h+var_128], 0
0x180003405  mov     [rbp+rcx*8+110h+var_124], r14d
0x18000340a  mov     [rbp+rcx*8+110h+var_120], r13d
0x18000340f  mov     eax, [rsp+210h+var_1A4]
0x180003413  mov     [rbp+rcx*8+110h+var_11C], eax
0x180003417  inc     ebx
0x180003419  xor     eax, eax
0x18000341b  mov     [rbp+110h+var_140], rax
0x18000341f  mov     [rbp+110h+var_168], rax
0x180003423  lea     r8, [rbp+110h+var_140]; unsigned __int16 **
0x180003427  mov     edx, r14d; int
0x18000342a  mov     rcx, [rsi+50h]; this
0x18000342e  call    ?LookupOrdinalName@CTableInfo@@QEAAJJPEAPEBG@Z; CTableInfo::LookupOrdinalName(long,ushort const * *)
0x180003433  mov     edi, eax
0x180003435  test    eax, eax
0x180003437  js      loc_180003697
0x18000343d  mov     r11, [rbp+110h+var_140]
0x180003441  test    r11, r11
0x180003444  jz      loc_180003680
0x18000344a  mov     r8d, r14d; unsigned int
0x18000344d  lea     rdx, [rsi+40h]; struct _GUID *
0x180003451  call    ?HideField@CSLTAudit@@AEAAHAEBU_GUID@@K@Z; CSLTAudit::HideField(_GUID const &,ulong)
0x180003456  mov     rcx, [rsi]
0x180003459  mov     r10, [rcx+48h]
0x18000345d  mov     dword ptr [rsp+210h+var_1E0], eax
0x180003461  lea     rax, [rbp+110h+var_168]
0x180003465  mov     [rsp+210h+var_1E8], rax
0x18000346a  mov     rax, [rbp+110h+var_170]
0x18000346e  mov     [rsp+210h+var_1F0], rax
0x180003473  mov     r9d, [rsp+210h+var_1A4]
0x180003478  mov     r8d, r13d
0x18000347b  mov     rdx, r11
0x18000347e  mov     rcx, rsi
0x180003481  mov     rax, r10
0x180003484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003489  mov     edi, eax
0x18000348b  test    eax, eax
0x18000348d  js      loc_180003697
0x180003493  mov     rcx, [rbp+110h+var_168]
0x180003497  mov     r13d, [rsp+210h+var_1A8]
0x18000349c  jmp     loc_18000357A
0x1800034a1  mov     r8, [rsi+50h]
0x1800034a5  xor     edx, edx
0x1800034a7  cmp     edx, [r8+30h]
0x1800034ab  jnb     loc_18000359B
0x1800034b1  mov     rax, [r8+38h]
0x1800034b5  cmp     [rax+rdx*4], r14d
0x1800034b9  jz      short loc_1800034BF
0x1800034bb  inc     edx
0x1800034bd  jmp     short loc_1800034A7
0x1800034bf  mov     rcx, [rsi+28h]
0x1800034c3  mov     rax, [rcx]
0x1800034c6  lea     rdx, [rbp+110h+var_170]
0x1800034ca  mov     [rsp+210h+var_1E8], rdx
0x1800034cf  lea     rdx, [rsp+210h+var_1A4]
0x1800034d4  mov     [rsp+210h+var_1F0], rdx
0x1800034d9  lea     r9, [rsp+210h+var_19C]
0x1800034de  xor     r8d, r8d
0x1800034e1  mov     edx, r14d
0x1800034e4  mov     rax, [rax+98h]
0x1800034eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f0  mov     edi, eax
0x1800034f2  test    eax, eax
0x1800034f4  js      loc_180003697
0x1800034fa  xor     eax, eax
0x1800034fc  mov     [rbp+110h+var_140], rax
0x180003500  mov     [rbp+110h+var_190], rax
0x180003504  lea     r8, [rbp+110h+var_140]; unsigned __int16 **
0x180003508  mov     edx, r14d; int
0x18000350b  mov     rcx, [rsi+50h]; this
0x18000350f  call    ?LookupOrdinalName@CTableInfo@@QEAAJJPEAPEBG@Z; CTableInfo::LookupOrdinalName(long,ushort const * *)
0x180003514  mov     edi, eax
0x180003516  test    eax, eax
0x180003518  js      loc_180003697
0x18000351e  mov     rdi, [rbp+110h+var_140]
0x180003522  test    rdi, rdi
0x180003525  jz      loc_180003685
0x18000352b  mov     r8d, r14d; unsigned int
0x18000352e  lea     rdx, [rsi+40h]; struct _GUID *
0x180003532  call    ?HideField@CSLTAudit@@AEAAHAEBU_GUID@@K@Z; CSLTAudit::HideField(_GUID const &,ulong)
0x180003537  mov     r10, [rbp+110h+var_170]
0x18000353b  mov     rcx, [rsi]
0x18000353e  mov     r11, [rcx+48h]
0x180003542  mov     dword ptr [rsp+210h+var_1E0], eax
0x180003546  lea     rax, [rbp+110h+var_190]
0x18000354a  mov     [rsp+210h+var_1E8], rax
0x18000354f  mov     [rsp+210h+var_1F0], r10
0x180003554  mov     r9d, [rsp+210h+var_1A4]
0x180003559  mov     r8d, [rsp+210h+var_19C]
0x18000355e  mov     rdx, rdi
0x180003561  mov     rcx, rsi
0x180003564  mov     rax, r11
0x180003567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356c  mov     edi, eax
0x18000356e  test    eax, eax
0x180003570  js      loc_180003697
0x180003576  mov     rcx, [rbp+110h+var_190]
0x18000357a  mov     r9, [rsp+210h+pv]
0x18000357f  test    rcx, rcx
0x180003582  jz      loc_18000368A
0x180003588  mov     edx, [rsp+210h+var_1BC]
0x18000358c  mov     [r9+rdx*8], rcx
0x180003590  inc     edx
0x180003592  mov     [rsp+210h+var_1BC], edx
0x180003596  jmp     loc_18000368A
0x18000359b  cmp     r13d, 1
0x18000359f  jnz     loc_180003685
0x1800035a5  mov     [rbp+110h+var_140], 0
0x1800035ad  mov     qword ptr [rbp+110h+var_188], 0
0x1800035b5  mov     rcx, [rsi+28h]
0x1800035b9  mov     rax, [rcx]
0x1800035bc  lea     rdx, [rbp+110h+var_170]
0x1800035c0  mov     [rsp+210h+var_1E8], rdx
0x1800035c5  lea     rdx, [rsp+210h+var_1A4]
0x1800035ca  mov     [rsp+210h+var_1F0], rdx
0x1800035cf  lea     r9, [rsp+210h+var_19C]
0x1800035d4  xor     r8d, r8d
0x1800035d7  mov     edx, r14d
0x1800035da  mov     rax, [rax+98h]
0x1800035e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e6  mov     edi, eax
0x1800035e8  test    eax, eax
0x1800035ea  js      loc_180003697
0x1800035f0  lea     r8, [rbp+110h+var_140]; unsigned __int16 **
0x1800035f4  mov     edx, r14d; int
0x1800035f7  mov     rcx, [rsi+50h]; this
0x1800035fb  call    ?LookupOrdinalName@CTableInfo@@QEAAJJPEAPEBG@Z; CTableInfo::LookupOrdinalName(long,ushort const * *)
0x180003600  mov     edi, eax
0x180003602  test    eax, eax
0x180003604  js      loc_180003697
  ... truncated ...
```
