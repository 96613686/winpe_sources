# sub_1800CE4EC

- ea: `0x1800ce4ec`
- end: `0x1800cefe2`
- name: `sub_1800CE4EC`
- size: `2806`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d0300`

## callees

- `0x180006960`
- `0x18000ac80`
- `0x18000c470`
- `0x18000e400`
- `0x180032d54`
- `0x180037a98`
- `0x180098b50`
- `0x1800a9030`
- `0x1800ce4ec`
- `0x1800fcf10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce663`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce8ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cea48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cebe6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ced40`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ceefa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cefa6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce663`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce8ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cea48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cebe6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ced40`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ceefa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cefa6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce5ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce685`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce762`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce822`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce8cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce9bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cea6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ceb5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cec08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cecb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ced62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cee6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cef1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce5ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce685`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce762`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce822`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce8cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ce9bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cea6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ceb5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cec08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cecb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ced62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cee6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cef1c`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800ce740`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800ce740`

## pseudocode

```c
__int64 __fastcall sub_1800CE4EC(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  int (__fastcall *v5)(__int64 *, __int64 *, int *); // rax
  __int64 v6; // rdx
  HRESULT inited; // ebx
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // eax
  __int64 (__fastcall *v39)(__int64, __int64 *, PROPVARIANT *, _QWORD, int); // r10
  __int64 v40; // rdx
  __int64 *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 *v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 *v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  int v66; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v67[4]; // [rsp+34h] [rbp-3Ch] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v69; // [rsp+48h] [rbp-28h]
  _BYTE v70[8]; // [rsp+50h] [rbp-20h] BYREF
  IID clsid; // [rsp+58h] [rbp-18h] BYREF

  sub_180006960(v67, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1204);
  v69 = 0;
  v4 = *a2;
  v66 = 0;
  *(_OWORD *)pvar = 0;
  v5 = *(int (__fastcall **)(__int64 *, __int64 *, int *))(v4 + 56);
  clsid = 0;
  LOWORD(pvar[0]) = 19;
  if ( v5(a2, qword_18010F400, &v66) < 0 )
    goto LABEL_25;
  LODWORD(pvar[1]) = v66;
  inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
             a1,
             qword_1801093C8,
             pvar,
             0,
             1);
  if ( inited < 0 )
  {
    v8 = (__int64 *)qword_18012EC10;
    if ( !qword_18012EC10 )
    {
      v9 = MFGetCallStackTracingWeakReference(0, v6);
      qword_18012EC10 = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)qword_18012EC10;
      }
      else
      {
        v8 = &qword_18012E0B0;
        qword_18012EC10 = (__int64)&qword_18012E0B0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = sub_18000C470(v8, v6);
      if ( *(_DWORD *)(v10 + 1996) != inited )
        sub_18000E400(v10, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1221, (unsigned int)inited);
    }
    if ( (unsigned __int8)sub_1800A9030(v8, v6) )
    {
      v11 = 103;
LABEL_13:
      sub_180037A98(*((_QWORD *)RequestContext + 2), v11, qword_180114FF8, a1, inited);
      goto LABEL_152;
    }
    goto LABEL_152;
  }
  inited = PropVariantClear(pvar);
  if ( inited >= 0 )
  {
LABEL_25:
    LOWORD(pvar[0]) = 72;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *, IID *))(*a2 + 80))(a2, qword_18010F3A0, &clsid) >= 0 )
    {
      inited = InitPropVariantFromCLSID(&clsid, pvar);
      if ( inited < 0 )
      {
        v17 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v18 = MFGetCallStackTracingWeakReference(0, v16);
          qword_18012EC10 = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v17 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = sub_18000C470(v17, v16);
          if ( *(_DWORD *)(v19 + 1996) != inited )
            sub_18000E400(v19, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1237, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v17, v16) )
        {
          v11 = 105;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
                 a1,
                 qword_180109398,
                 pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v21 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v22 = MFGetCallStackTracingWeakReference(0, v20);
          qword_18012EC10 = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v21 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = sub_18000C470(v21, v20);
          if ( *(_DWORD *)(v23 + 1996) != inited )
            sub_18000E400(v23, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1238, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v21, v20) )
        {
          v11 = 106;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(pvar);
      if ( inited < 0 )
      {
        v25 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v26 = MFGetCallStackTracingWeakReference(0, v24);
          qword_18012EC10 = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v25 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = sub_18000C470(v25, v24);
          if ( *(_DWORD *)(v27 + 1996) != inited )
            sub_18000E400(v27, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1239, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v25, v24) )
        {
          v11 = 107;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v28 = *a2;
    LOWORD(pvar[0]) = 19;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *, int *))(v28 + 56))(a2, qword_18010F410, &v66) >= 0 )
    {
      LODWORD(pvar[1]) = v66;
      inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
                 a1,
                 qword_1801093E0,
                 pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v30 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v31 = MFGetCallStackTracingWeakReference(0, v29);
          qword_18012EC10 = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v30 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = sub_18000C470(v30, v29);
          if ( *(_DWORD *)(v32 + 1996) != inited )
            sub_18000E400(v32, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1249, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v30, v29) )
        {
          v11 = 108;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(pvar);
      if ( inited < 0 )
      {
        v34 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v35 = MFGetCallStackTracingWeakReference(0, v33);
          qword_18012EC10 = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v34 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = sub_18000C470(v34, v33);
          if ( *(_DWORD *)(v36 + 1996) != inited )
            sub_18000E400(v36, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1250, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v34, v33) )
        {
          v11 = 109;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v37 = *a2;
    LOWORD(pvar[0]) = 19;
    v38 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *))(v37 + 56))(a2, qword_18010F440, &v66);
    v39 = *(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL);
    if ( v38 < 0 )
    {
      LODWORD(pvar[1]) = 16;
      inited = v39(a1, qword_1801093F8, pvar, 0, 1);
      if ( inited < 0 )
      {
        v49 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v50 = MFGetCallStackTracingWeakReference(0, v48);
          qword_18012EC10 = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v49 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = sub_18000C470(v49, v48);
          if ( *(_DWORD *)(v51 + 1996) != inited )
            sub_18000E400(v51, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1269, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v49, v48) )
        {
          v11 = 112;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(pvar);
      if ( inited < 0 )
      {
        v53 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v54 = MFGetCallStackTracingWeakReference(0, v52);
          qword_18012EC10 = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v53 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v55 = sub_18000C470(v53, v52);
          if ( *(_DWORD *)(v55 + 1996) != inited )
            sub_18000E400(v55, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1270, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v53, v52) )
        {
          v11 = 113;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    else
    {
      LODWORD(pvar[1]) = v66;
      inited = v39(a1, qword_1801093F8, pvar, 0, 1);
      if ( inited < 0 )
      {
        v41 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v42 = MFGetCallStackTracingWeakReference(0, v40);
          qword_18012EC10 = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v41 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = sub_18000C470(v41, v40);
          if ( *(_DWORD *)(v43 + 1996) != inited )
            sub_18000E400(v43, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1260, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v41, v40) )
        {
          v11 = 110;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(pvar);
      if ( inited < 0 )
      {
        v45 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v46 = MFGetCallStackTracingWeakReference(0, v44);
          qword_18012EC10 = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v45 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = sub_18000C470(v45, v44);
          if ( *(_DWORD *)(v47 + 1996) != inited )
            sub_18000E400(v47, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1261, (unsigned int)inited);
        }
        if ( (unsigned __int8)sub_1800A9030(v45, v44) )
        {
          v11 = 111;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    if ( !(unsigned int)sub_180032D54(a1 + 48, qword_180109350, v70) )
    {
      v56 = *a2;
      LOWORD(pvar[0]) = 19;
      if ( (*(int (__fastcall **)(__int64 *, __int64 *, int *))(v56 + 56))(a2, qword_18010F420, &v66) >= 0 )
      {
        LODWORD(pvar[1]) = 8 * v66;
        inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
                   a1,
                   qword_180109350,
                   pvar,
                   0,
                   1);
        if ( inited < 0 )
        {
          v58 = (__int64 *)qword_18012EC10;
          if ( !qword_18012EC10 )
          {
            v59 = MFGetCallStackTracingWeakReference(0, v57);
            qword_18012EC10 = v59;
            if ( v59 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
            {
              v58 = (__int64 *)qword_18012EC10;
            }
            else
            {
              v58 = &qword_18012E0B0;
              qword_18012EC10 = (__int64)&qword_18012E0B0;
            }
          }
          if ( *((_BYTE *)v58 + 8) )
          {
            v60 = sub_18000C470(v58, v57);
            if ( *(_DWORD *)(v60 + 1996) != inited )
              sub_18000E400(v60, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1285, (unsigned int)inited);
          }
          if ( (unsigned __int8)sub_1800A9030(v58, v57) )
          {
            v11 = 114;
            goto LABEL_13;
          }
          goto LABEL_152;
        }
        inited = PropVariantClear(pvar);
        if ( inited < 0 )
        {
          v62 = (__int64 *)qword_18012EC10;
          if ( !qword_18012EC10 )
          {
            v63 = MFGetCallStackTracingWeakReference(0, v61);
            qword_18012EC10 = v63;
            if ( v63 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
            {
              v62 = (__int64 *)qword_18012EC10;
            }
            else
            {
              v62 = &qword_18012E0B0;
              qword_18012EC10 = (__int64)&qword_18012E0B0;
            }
          }
          if ( *((_BYTE *)v62 + 8) )
          {
            v64 = sub_18000C470(v62, v61);
            if ( *(_DWORD *)(v64 + 1996) != inited )
              sub_18000E400(v64, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1286, (unsigned int)inited);
          }
          if ( (unsigned __int8)sub_1800A9030(v62, v61) )
          {
            v11 = 115;
            goto LABEL_13;
          }
          goto LABEL_152;
        }
      }
    }
    inited = 0;
    goto LABEL_152;
  }
  v13 = (__int64 *)qword_18012EC10;
  if ( !qword_18012EC10 )
  {
    v14 = MFGetCallStackTracingWeakReference(0, v12);
    qword_18012EC10 = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (__int64 *)qword_18012EC10;
    }
    else
    {
      v13 = &qword_18012E0B0;
      qword_18012EC10 = (__int64)&qword_18012E0B0;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = sub_18000C470(v13, v12);
    if ( *(_DWORD *)(v15 + 1996) != inited )
      sub_18000E400(v15, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1222, (unsigned int)inited);
  }
  if ( (unsigned __int8)sub_1800A9030(v13, v12) )
  {
    v11 = 104;
    goto LABEL_13;
  }
LABEL_152:
  PropVariantClear(pvar);
  sub_18000AC80(v67);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800ce4ec  mov     [rsp-38h+arg_10], rbx
0x1800ce4f1  push    rbp
0x1800ce4f2  push    rsi
0x1800ce4f3  push    rdi
0x1800ce4f4  push    r12
0x1800ce4f6  push    r13
0x1800ce4f8  push    r14
0x1800ce4fa  push    r15
0x1800ce4fc  mov     rbp, rsp
0x1800ce4ff  sub     rsp, 70h
0x1800ce503  mov     rax, cs:__security_cookie
0x1800ce50a  xor     rax, rsp
0x1800ce50d  mov     [rbp+var_8], rax
0x1800ce511  mov     rsi, rdx
0x1800ce514  lea     r12, aCwmprophandler_13; "CWMPropHandlerBase::AddAudioMediaTypePr"...
0x1800ce51b  mov     rdi, rcx
0x1800ce51e  mov     rdx, r12
0x1800ce521  mov     r8d, 4B4h
0x1800ce527  lea     rcx, [rbp+var_3C]
0x1800ce52b  call    sub_180006960
0x1800ce530  xor     eax, eax
0x1800ce532  lea     r8, [rbp+var_40]
0x1800ce536  mov     [rbp+var_28], rax
0x1800ce53a  lea     rdx, qword_18010F400
0x1800ce541  mov     rax, [rsi]
0x1800ce544  xor     r14d, r14d
0x1800ce547  xorps   xmm1, xmm1
0x1800ce54a  mov     [rbp+var_40], r14d
0x1800ce54e  xorps   xmm0, xmm0
0x1800ce551  mov     rcx, rsi
0x1800ce554  movups  xmmword ptr [rbp+pvar], xmm1
0x1800ce558  mov     rax, [rax+38h]
0x1800ce55c  lea     r13d, [r14+13h]
0x1800ce560  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x1800ce564  mov     word ptr [rbp+pvar], r13w
0x1800ce569  call    cs:__guard_dispatch_icall_fptr
0x1800ce56f  lea     r15d, [r14+1]
0x1800ce573  test    eax, eax
0x1800ce575  js      loc_1800CE70C
0x1800ce57b  mov     eax, [rbp+var_40]
0x1800ce57e  lea     r8, [rbp+pvar]
0x1800ce582  mov     dword ptr [rbp+pvar+8], eax
0x1800ce585  lea     rdx, qword_1801093C8
0x1800ce58c  mov     rax, [rdi]
0x1800ce58f  xor     r9d, r9d
0x1800ce592  mov     rcx, rdi
0x1800ce595  mov     [rsp+70h+var_50], r15d
0x1800ce59a  mov     rax, [rax+28h]
0x1800ce59e  call    cs:__guard_dispatch_icall_fptr
0x1800ce5a4  mov     ebx, eax
0x1800ce5a6  test    eax, eax
0x1800ce5a8  jns     loc_1800CE65F
0x1800ce5ae  mov     rcx, cs:qword_18012EC10
0x1800ce5b5  test    rcx, rcx
0x1800ce5b8  jnz     short loc_1800CE602
0x1800ce5ba  call    cs:MFGetCallStackTracingWeakReference
0x1800ce5c1  nop     dword ptr [rax+rax+00h]
0x1800ce5c6  mov     cs:qword_18012EC10, rax
0x1800ce5cd  mov     rcx, rax
0x1800ce5d0  test    rax, rax
0x1800ce5d3  jz      short loc_1800CE5F4
0x1800ce5d5  mov     rax, [rax]
0x1800ce5d8  mov     edx, 7F0h
0x1800ce5dd  mov     rax, [rax+8]
0x1800ce5e1  call    cs:__guard_dispatch_icall_fptr
0x1800ce5e7  test    eax, eax
0x1800ce5e9  jz      short loc_1800CE5F4
0x1800ce5eb  mov     rcx, cs:qword_18012EC10
0x1800ce5f2  jmp     short loc_1800CE602
0x1800ce5f4  lea     rcx, qword_18012E0B0
0x1800ce5fb  mov     cs:qword_18012EC10, rcx
0x1800ce602  cmp     [rcx+8], r14b
0x1800ce606  jz      short loc_1800CE629
0x1800ce608  call    sub_18000C470
0x1800ce60d  cmp     [rax+7CCh], ebx
0x1800ce613  jz      short loc_1800CE629
0x1800ce615  mov     r9d, ebx
0x1800ce618  mov     r8d, 4C5h
0x1800ce61e  mov     rdx, r12
0x1800ce621  mov     rcx, rax
0x1800ce624  call    sub_18000E400
0x1800ce629  call    sub_1800A9030
0x1800ce62e  cmp     al, r15b
0x1800ce631  jb      loc_1800CEFA2
0x1800ce637  mov     edx, 67h ; 'g'
0x1800ce63c  mov     rcx, cs:RequestContext
0x1800ce643  lea     r8, qword_180114FF8
0x1800ce64a  mov     r9, rdi
0x1800ce64d  mov     [rsp+70h+var_50], ebx
0x1800ce651  mov     rcx, [rcx+10h]
0x1800ce655  call    sub_180037A98
0x1800ce65a  jmp     loc_1800CEFA2
0x1800ce65f  lea     rcx, [rbp+pvar]; pvar
0x1800ce663  call    cs:PropVariantClear
0x1800ce66a  nop     dword ptr [rax+rax+00h]
0x1800ce66f  mov     ebx, eax
0x1800ce671  test    eax, eax
0x1800ce673  jns     loc_1800CE70C
0x1800ce679  mov     rcx, cs:qword_18012EC10
0x1800ce680  test    rcx, rcx
0x1800ce683  jnz     short loc_1800CE6CD
0x1800ce685  call    cs:MFGetCallStackTracingWeakReference
0x1800ce68c  nop     dword ptr [rax+rax+00h]
0x1800ce691  mov     cs:qword_18012EC10, rax
0x1800ce698  mov     rcx, rax
0x1800ce69b  test    rax, rax
0x1800ce69e  jz      short loc_1800CE6BF
0x1800ce6a0  mov     rax, [rax]
0x1800ce6a3  mov     edx, 7F0h
0x1800ce6a8  mov     rax, [rax+8]
0x1800ce6ac  call    cs:__guard_dispatch_icall_fptr
0x1800ce6b2  test    eax, eax
0x1800ce6b4  jz      short loc_1800CE6BF
0x1800ce6b6  mov     rcx, cs:qword_18012EC10
0x1800ce6bd  jmp     short loc_1800CE6CD
0x1800ce6bf  lea     rcx, qword_18012E0B0
0x1800ce6c6  mov     cs:qword_18012EC10, rcx
0x1800ce6cd  cmp     [rcx+8], r14b
0x1800ce6d1  jz      short loc_1800CE6F4
0x1800ce6d3  call    sub_18000C470
0x1800ce6d8  cmp     [rax+7CCh], ebx
0x1800ce6de  jz      short loc_1800CE6F4
0x1800ce6e0  mov     r9d, ebx
0x1800ce6e3  mov     r8d, 4C6h
0x1800ce6e9  mov     rdx, r12
0x1800ce6ec  mov     rcx, rax
0x1800ce6ef  call    sub_18000E400
0x1800ce6f4  call    sub_1800A9030
0x1800ce6f9  cmp     al, r15b
0x1800ce6fc  jb      loc_1800CEFA2
0x1800ce702  mov     edx, 68h ; 'h'
0x1800ce707  jmp     loc_1800CE63C
0x1800ce70c  mov     eax, 48h ; 'H'
0x1800ce711  lea     r8, [rbp+clsid]
0x1800ce715  mov     word ptr [rbp+pvar], ax
0x1800ce719  lea     rdx, qword_18010F3A0
0x1800ce720  mov     rax, [rsi]
0x1800ce723  mov     rcx, rsi
0x1800ce726  mov     rax, [rax+50h]
0x1800ce72a  call    cs:__guard_dispatch_icall_fptr
0x1800ce730  test    eax, eax
0x1800ce732  js      loc_1800CE956
0x1800ce738  lea     rdx, [rbp+pvar]; ppropvar
0x1800ce73c  lea     rcx, [rbp+clsid]; clsid
0x1800ce740  call    cs:InitPropVariantFromCLSID
0x1800ce747  nop     dword ptr [rax+rax+00h]
0x1800ce74c  mov     ebx, eax
0x1800ce74e  test    eax, eax
0x1800ce750  jns     loc_1800CE7E9
0x1800ce756  mov     rcx, cs:qword_18012EC10
0x1800ce75d  test    rcx, rcx
0x1800ce760  jnz     short loc_1800CE7AA
0x1800ce762  call    cs:MFGetCallStackTracingWeakReference
0x1800ce769  nop     dword ptr [rax+rax+00h]
0x1800ce76e  mov     cs:qword_18012EC10, rax
0x1800ce775  mov     rcx, rax
0x1800ce778  test    rax, rax
0x1800ce77b  jz      short loc_1800CE79C
0x1800ce77d  mov     rax, [rax]
0x1800ce780  mov     edx, 7F0h
0x1800ce785  mov     rax, [rax+8]
0x1800ce789  call    cs:__guard_dispatch_icall_fptr
0x1800ce78f  test    eax, eax
0x1800ce791  jz      short loc_1800CE79C
0x1800ce793  mov     rcx, cs:qword_18012EC10
0x1800ce79a  jmp     short loc_1800CE7AA
0x1800ce79c  lea     rcx, qword_18012E0B0
0x1800ce7a3  mov     cs:qword_18012EC10, rcx
0x1800ce7aa  cmp     [rcx+8], r14b
0x1800ce7ae  jz      short loc_1800CE7D1
0x1800ce7b0  call    sub_18000C470
0x1800ce7b5  cmp     [rax+7CCh], ebx
0x1800ce7bb  jz      short loc_1800CE7D1
0x1800ce7bd  mov     r9d, ebx
0x1800ce7c0  mov     r8d, 4D5h
0x1800ce7c6  mov     rdx, r12
0x1800ce7c9  mov     rcx, rax
0x1800ce7cc  call    sub_18000E400
0x1800ce7d1  call    sub_1800A9030
0x1800ce7d6  cmp     al, r15b
0x1800ce7d9  jb      loc_1800CEFA2
0x1800ce7df  mov     edx, 69h ; 'i'
0x1800ce7e4  jmp     loc_1800CE63C
0x1800ce7e9  mov     rax, [rdi]
0x1800ce7ec  lea     r8, [rbp+pvar]
0x1800ce7f0  xor     r9d, r9d
0x1800ce7f3  mov     [rsp+70h+var_50], r15d
0x1800ce7f8  lea     rdx, qword_180109398
0x1800ce7ff  mov     rcx, rdi
0x1800ce802  mov     rax, [rax+28h]
0x1800ce806  call    cs:__guard_dispatch_icall_fptr
0x1800ce80c  mov     ebx, eax
0x1800ce80e  test    eax, eax
0x1800ce810  jns     loc_1800CE8A9
0x1800ce816  mov     rcx, cs:qword_18012EC10
0x1800ce81d  test    rcx, rcx
0x1800ce820  jnz     short loc_1800CE86A
0x1800ce822  call    cs:MFGetCallStackTracingWeakReference
0x1800ce829  nop     dword ptr [rax+rax+00h]
0x1800ce82e  mov     cs:qword_18012EC10, rax
0x1800ce835  mov     rcx, rax
0x1800ce838  test    rax, rax
0x1800ce83b  jz      short loc_1800CE85C
0x1800ce83d  mov     rax, [rax]
0x1800ce840  mov     edx, 7F0h
0x1800ce845  mov     rax, [rax+8]
0x1800ce849  call    cs:__guard_dispatch_icall_fptr
0x1800ce84f  test    eax, eax
0x1800ce851  jz      short loc_1800CE85C
0x1800ce853  mov     rcx, cs:qword_18012EC10
0x1800ce85a  jmp     short loc_1800CE86A
0x1800ce85c  lea     rcx, qword_18012E0B0
0x1800ce863  mov     cs:qword_18012EC10, rcx
0x1800ce86a  cmp     [rcx+8], r14b
0x1800ce86e  jz      short loc_1800CE891
0x1800ce870  call    sub_18000C470
0x1800ce875  cmp     [rax+7CCh], ebx
0x1800ce87b  jz      short loc_1800CE891
0x1800ce87d  mov     r9d, ebx
0x1800ce880  mov     r8d, 4D6h
0x1800ce886  mov     rdx, r12
0x1800ce889  mov     rcx, rax
0x1800ce88c  call    sub_18000E400
0x1800ce891  call    sub_1800A9030
0x1800ce896  cmp     al, r15b
0x1800ce899  jb      loc_1800CEFA2
0x1800ce89f  mov     edx, 6Ah ; 'j'
0x1800ce8a4  jmp     loc_1800CE63C
0x1800ce8a9  lea     rcx, [rbp+pvar]; pvar
0x1800ce8ad  call    cs:PropVariantClear
0x1800ce8b4  nop     dword ptr [rax+rax+00h]
0x1800ce8b9  mov     ebx, eax
0x1800ce8bb  test    eax, eax
0x1800ce8bd  jns     loc_1800CE956
0x1800ce8c3  mov     rcx, cs:qword_18012EC10
0x1800ce8ca  test    rcx, rcx
0x1800ce8cd  jnz     short loc_1800CE917
0x1800ce8cf  call    cs:MFGetCallStackTracingWeakReference
0x1800ce8d6  nop     dword ptr [rax+rax+00h]
0x1800ce8db  mov     cs:qword_18012EC10, rax
0x1800ce8e2  mov     rcx, rax
0x1800ce8e5  test    rax, rax
0x1800ce8e8  jz      short loc_1800CE909
0x1800ce8ea  mov     rax, [rax]
0x1800ce8ed  mov     edx, 7F0h
0x1800ce8f2  mov     rax, [rax+8]
0x1800ce8f6  call    cs:__guard_dispatch_icall_fptr
0x1800ce8fc  test    eax, eax
0x1800ce8fe  jz      short loc_1800CE909
0x1800ce900  mov     rcx, cs:qword_18012EC10
0x1800ce907  jmp     short loc_1800CE917
0x1800ce909  lea     rcx, qword_18012E0B0
0x1800ce910  mov     cs:qword_18012EC10, rcx
0x1800ce917  cmp     [rcx+8], r14b
0x1800ce91b  jz      short loc_1800CE93E
0x1800ce91d  call    sub_18000C470
0x1800ce922  cmp     [rax+7CCh], ebx
0x1800ce928  jz      short loc_1800CE93E
0x1800ce92a  mov     r9d, ebx
0x1800ce92d  mov     r8d, 4D7h
0x1800ce933  mov     rdx, r12
0x1800ce936  mov     rcx, rax
0x1800ce939  call    sub_18000E400
0x1800ce93e  call    sub_1800A9030
0x1800ce943  cmp     al, r15b
0x1800ce946  jb      loc_1800CEFA2
0x1800ce94c  mov     edx, 6Bh ; 'k'
0x1800ce951  jmp     loc_1800CE63C
0x1800ce956  mov     rax, [rsi]
0x1800ce959  lea     r8, [rbp+var_40]
0x1800ce95d  lea     rdx, qword_18010F410
0x1800ce964  mov     word ptr [rbp+pvar], r13w
0x1800ce969  mov     rcx, rsi
0x1800ce96c  mov     rax, [rax+38h]
0x1800ce970  call    cs:__guard_dispatch_icall_fptr
0x1800ce976  test    eax, eax
0x1800ce978  js      loc_1800CEAF1
0x1800ce97e  mov     eax, [rbp+var_40]
0x1800ce981  lea     r8, [rbp+pvar]
0x1800ce985  mov     dword ptr [rbp+pvar+8], eax
0x1800ce988  lea     rdx, qword_1801093E0
0x1800ce98f  mov     rax, [rdi]
0x1800ce992  xor     r9d, r9d
0x1800ce995  mov     rcx, rdi
0x1800ce998  mov     [rsp+70h+var_50], r15d
0x1800ce99d  mov     rax, [rax+28h]
0x1800ce9a1  call    cs:__guard_dispatch_icall_fptr
0x1800ce9a7  mov     ebx, eax
0x1800ce9a9  test    eax, eax
0x1800ce9ab  jns     loc_1800CEA44
0x1800ce9b1  mov     rcx, cs:qword_18012EC10
0x1800ce9b8  test    rcx, rcx
0x1800ce9bb  jnz     short loc_1800CEA05
0x1800ce9bd  call    cs:MFGetCallStackTracingWeakReference
0x1800ce9c4  nop     dword ptr [rax+rax+00h]
0x1800ce9c9  mov     cs:qword_18012EC10, rax
0x1800ce9d0  mov     rcx, rax
0x1800ce9d3  test    rax, rax
0x1800ce9d6  jz      short loc_1800CE9F7
0x1800ce9d8  mov     rax, [rax]
  ... truncated ...
```
