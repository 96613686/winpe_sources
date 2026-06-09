# sub_1800DEB1C

- ea: `0x1800deb1c`
- end: `0x1800df586`
- name: `sub_1800DEB1C`
- size: `2666`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800e00f0`

## callees

- `0x180001870`
- `0x180005880`
- `0x18000a580`
- `0x180020d88`
- `0x18003d740`
- `0x18004f390`
- `0x18007fdd0`
- `0x1800deb1c`
- `0x18013e2e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dec8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800deeb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df03c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df1c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df30c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df4b2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df551`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dec8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800deeb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df03c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df1c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df30c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df4b2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df551`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800debea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800deca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ded78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dee31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800deed1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800defb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df142`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df1e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df288`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df42e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df4ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800debea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800deca8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ded78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dee31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800deed1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800defb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df142`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df1e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df288`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df42e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800df4ce`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800ded5c`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800ded5c`

## pseudocode

```c
__int64 __fastcall sub_1800DEB1C(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  int (__fastcall *v5)(__int64 *, __int64 *, LONG *); // rax
  __int64 v6; // rdx
  HRESULT inited; // ebx
  __int64 (__fastcall ***v8)(); // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(); // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 (__fastcall ***v17)(); // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 (__fastcall ***v21)(); // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 (__fastcall ***v25)(); // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 (__fastcall ***v30)(); // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 (__fastcall ***v34)(); // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // eax
  __int64 (__fastcall *v39)(__int64, __int64 *, PROPVARIANT *, _QWORD, int); // r10
  __int64 v40; // rdx
  __int64 (__fastcall ***v41)(); // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 (__fastcall ***v45)(); // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 (__fastcall ***v49)(); // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 (__fastcall ***v53)(); // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 (__fastcall ***v58)(); // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 (__fastcall ***v62)(); // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  LONG v66; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v67[4]; // [rsp+34h] [rbp-3Ch] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v69[8]; // [rsp+50h] [rbp-20h] BYREF
  IID clsid; // [rsp+58h] [rbp-18h] BYREF

  sub_18000A580(v67, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1204);
  v4 = *a2;
  v66 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v5 = *(int (__fastcall **)(__int64 *, __int64 *, LONG *))(v4 + 56);
  clsid = 0;
  pvar.vt = 19;
  if ( v5(a2, qword_18014EB20, &v66) < 0 )
    goto LABEL_25;
  pvar.lVal = v66;
  inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
             a1,
             qword_18014C628,
             &pvar,
             0,
             1);
  if ( inited < 0 )
  {
    v8 = (__int64 (__fastcall ***)())qword_180169350;
    if ( !qword_180169350 )
    {
      v9 = MFGetCallStackTracingWeakReference(0, v6);
      qword_180169350 = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v8 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = sub_180001870(v8);
      if ( *(_DWORD *)(v10 + 1996) != inited )
        sub_18007FDD0(v10, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1221, (unsigned int)inited);
    }
    if ( byte_1801692C8 )
    {
      v11 = 103;
LABEL_13:
      sub_18004F390(*((_QWORD *)RequestContext + 2), v11, qword_180159C70, a1, inited);
      goto LABEL_152;
    }
    goto LABEL_152;
  }
  inited = PropVariantClear(&pvar);
  if ( inited >= 0 )
  {
LABEL_25:
    pvar.vt = 72;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *, IID *))(*a2 + 80))(a2, qword_18014EAD0, &clsid) >= 0 )
    {
      inited = InitPropVariantFromCLSID(&clsid, &pvar);
      if ( inited < 0 )
      {
        v17 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v18 = MFGetCallStackTracingWeakReference(0, v16);
          qword_180169350 = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v17 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = sub_180001870(v17);
          if ( *(_DWORD *)(v19 + 1996) != inited )
            sub_18007FDD0(v19, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1237, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 105;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
                 a1,
                 qword_18014C5F8,
                 &pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v21 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v22 = MFGetCallStackTracingWeakReference(0, v20);
          qword_180169350 = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v21 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = sub_180001870(v21);
          if ( *(_DWORD *)(v23 + 1996) != inited )
            sub_18007FDD0(v23, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1238, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 106;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v25 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v26 = MFGetCallStackTracingWeakReference(0, v24);
          qword_180169350 = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v25 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = sub_180001870(v25);
          if ( *(_DWORD *)(v27 + 1996) != inited )
            sub_18007FDD0(v27, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1239, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 107;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v28 = *a2;
    pvar.vt = 19;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *, LONG *))(v28 + 56))(a2, qword_18014EB30, &v66) >= 0 )
    {
      pvar.lVal = v66;
      inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
                 a1,
                 qword_18014C640,
                 &pvar,
                 0,
                 1);
      if ( inited < 0 )
      {
        v30 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v31 = MFGetCallStackTracingWeakReference(0, v29);
          qword_180169350 = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v30 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = sub_180001870(v30);
          if ( *(_DWORD *)(v32 + 1996) != inited )
            sub_18007FDD0(v32, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1249, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 108;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v34 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v35 = MFGetCallStackTracingWeakReference(0, v33);
          qword_180169350 = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v34 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = sub_180001870(v34);
          if ( *(_DWORD *)(v36 + 1996) != inited )
            sub_18007FDD0(v36, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1250, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 109;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    v37 = *a2;
    pvar.vt = 19;
    v38 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, LONG *))(v37 + 56))(a2, qword_18014EB50, &v66);
    v39 = *(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL);
    if ( v38 < 0 )
    {
      pvar.lVal = 16;
      inited = v39(a1, qword_18014C658, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v49 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v50 = MFGetCallStackTracingWeakReference(0, v48);
          qword_180169350 = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v49 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = sub_180001870(v49);
          if ( *(_DWORD *)(v51 + 1996) != inited )
            sub_18007FDD0(v51, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1269, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 112;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v53 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v54 = MFGetCallStackTracingWeakReference(0, v52);
          qword_180169350 = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v53 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v55 = sub_180001870(v53);
          if ( *(_DWORD *)(v55 + 1996) != inited )
            sub_18007FDD0(v55, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1270, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 113;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    else
    {
      pvar.lVal = v66;
      inited = v39(a1, qword_18014C658, &pvar, 0, 1);
      if ( inited < 0 )
      {
        v41 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v42 = MFGetCallStackTracingWeakReference(0, v40);
          qword_180169350 = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v41 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = sub_180001870(v41);
          if ( *(_DWORD *)(v43 + 1996) != inited )
            sub_18007FDD0(v43, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1260, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 110;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
      inited = PropVariantClear(&pvar);
      if ( inited < 0 )
      {
        v45 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v46 = MFGetCallStackTracingWeakReference(0, v44);
          qword_180169350 = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v45 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = sub_180001870(v45);
          if ( *(_DWORD *)(v47 + 1996) != inited )
            sub_18007FDD0(v47, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1261, (unsigned int)inited);
        }
        if ( byte_1801692C8 )
        {
          v11 = 111;
          goto LABEL_13;
        }
        goto LABEL_152;
      }
    }
    if ( !(unsigned int)sub_180020D88(a1 + 48, qword_18014C5B0, v69) )
    {
      v56 = *a2;
      pvar.vt = 19;
      if ( (*(int (__fastcall **)(__int64 *, __int64 *, LONG *))(v56 + 56))(a2, qword_18014EB40, &v66) >= 0 )
      {
        pvar.lVal = 8 * v66;
        inited = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
                   a1,
                   qword_18014C5B0,
                   &pvar,
                   0,
                   1);
        if ( inited < 0 )
        {
          v58 = (__int64 (__fastcall ***)())qword_180169350;
          if ( !qword_180169350 )
          {
            v59 = MFGetCallStackTracingWeakReference(0, v57);
            qword_180169350 = v59;
            if ( v59 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
            {
              v58 = (__int64 (__fastcall ***)())qword_180169350;
            }
            else
            {
              v58 = &off_1801683B0;
              qword_180169350 = (__int64)&off_1801683B0;
            }
          }
          if ( *((_BYTE *)v58 + 8) )
          {
            v60 = sub_180001870(v58);
            if ( *(_DWORD *)(v60 + 1996) != inited )
              sub_18007FDD0(v60, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1285, (unsigned int)inited);
          }
          if ( byte_1801692C8 )
          {
            v11 = 114;
            goto LABEL_13;
          }
          goto LABEL_152;
        }
        inited = PropVariantClear(&pvar);
        if ( inited < 0 )
        {
          v62 = (__int64 (__fastcall ***)())qword_180169350;
          if ( !qword_180169350 )
          {
            v63 = MFGetCallStackTracingWeakReference(0, v61);
            qword_180169350 = v63;
            if ( v63 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
            {
              v62 = (__int64 (__fastcall ***)())qword_180169350;
            }
            else
            {
              v62 = &off_1801683B0;
              qword_180169350 = (__int64)&off_1801683B0;
            }
          }
          if ( *((_BYTE *)v62 + 8) )
          {
            v64 = sub_180001870(v62);
            if ( *(_DWORD *)(v64 + 1996) != inited )
              sub_18007FDD0(v64, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1286, (unsigned int)inited);
          }
          if ( byte_1801692C8 )
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
  v13 = (__int64 (__fastcall ***)())qword_180169350;
  if ( !qword_180169350 )
  {
    v14 = MFGetCallStackTracingWeakReference(0, v12);
    qword_180169350 = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (__int64 (__fastcall ***)())qword_180169350;
    }
    else
    {
      v13 = &off_1801683B0;
      qword_180169350 = (__int64)&off_1801683B0;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = sub_180001870(v13);
    if ( *(_DWORD *)(v15 + 1996) != inited )
      sub_18007FDD0(v15, "CWMPropHandlerBase::AddAudioMediaTypeProperties", 1222, (unsigned int)inited);
  }
  if ( byte_1801692C8 )
  {
    v11 = 104;
    goto LABEL_13;
  }
LABEL_152:
  PropVariantClear(&pvar);
  sub_180005880(v67);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800deb1c  mov     [rsp-38h+arg_10], rbx
0x1800deb21  push    rbp
0x1800deb22  push    rsi
0x1800deb23  push    rdi
0x1800deb24  push    r12
0x1800deb26  push    r13
0x1800deb28  push    r14
0x1800deb2a  push    r15
0x1800deb2c  mov     rbp, rsp
0x1800deb2f  sub     rsp, 70h
0x1800deb33  mov     rax, cs:__security_cookie
0x1800deb3a  xor     rax, rsp
0x1800deb3d  mov     [rbp+var_8], rax
0x1800deb41  mov     rsi, rdx
0x1800deb44  lea     r12, aCwmprophandler_6; "CWMPropHandlerBase::AddAudioMediaTypePr"...
0x1800deb4b  mov     rdi, rcx
0x1800deb4e  mov     rdx, r12
0x1800deb51  mov     r8d, 4B4h
0x1800deb57  lea     rcx, [rbp+var_3C]
0x1800deb5b  call    sub_18000A580
0x1800deb60  xor     eax, eax
0x1800deb62  lea     r8, [rbp+var_40]
0x1800deb66  mov     qword ptr [rbp+pvar+10h], rax
0x1800deb6a  lea     rdx, qword_18014EB20
0x1800deb71  mov     rax, [rsi]
0x1800deb74  xor     r14d, r14d
0x1800deb77  xorps   xmm1, xmm1
0x1800deb7a  mov     [rbp+var_40], r14d
0x1800deb7e  xorps   xmm0, xmm0
0x1800deb81  mov     rcx, rsi
0x1800deb84  movups  xmmword ptr [rbp+pvar], xmm1
0x1800deb88  mov     rax, [rax+38h]
0x1800deb8c  lea     r13d, [r14+13h]
0x1800deb90  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x1800deb94  mov     word ptr [rbp+pvar], r13w
0x1800deb99  call    cs:__guard_dispatch_icall_fptr
0x1800deb9f  lea     r15d, [r14+1]
0x1800deba3  test    eax, eax
0x1800deba5  js      loc_1800DED28
0x1800debab  mov     eax, [rbp+var_40]
0x1800debae  lea     r8, [rbp+pvar]
0x1800debb2  mov     dword ptr [rbp+pvar+8], eax
0x1800debb5  lea     rdx, qword_18014C628
0x1800debbc  mov     rax, [rdi]
0x1800debbf  xor     r9d, r9d
0x1800debc2  mov     rcx, rdi
0x1800debc5  mov     [rsp+70h+var_50], r15d
0x1800debca  mov     rax, [rax+28h]
0x1800debce  call    cs:__guard_dispatch_icall_fptr
0x1800debd4  mov     ebx, eax
0x1800debd6  test    eax, eax
0x1800debd8  jns     loc_1800DEC88
0x1800debde  mov     rcx, cs:qword_180169350
0x1800debe5  test    rcx, rcx
0x1800debe8  jnz     short loc_1800DEC2C
0x1800debea  call    cs:MFGetCallStackTracingWeakReference
0x1800debf0  mov     cs:qword_180169350, rax
0x1800debf7  mov     rcx, rax
0x1800debfa  test    rax, rax
0x1800debfd  jz      short loc_1800DEC1E
0x1800debff  mov     rax, [rax]
0x1800dec02  mov     edx, 7F0h
0x1800dec07  mov     rax, [rax+8]
0x1800dec0b  call    cs:__guard_dispatch_icall_fptr
0x1800dec11  test    eax, eax
0x1800dec13  jz      short loc_1800DEC1E
0x1800dec15  mov     rcx, cs:qword_180169350
0x1800dec1c  jmp     short loc_1800DEC2C
0x1800dec1e  lea     rcx, off_1801683B0
0x1800dec25  mov     cs:qword_180169350, rcx
0x1800dec2c  cmp     [rcx+8], r14b
0x1800dec30  jz      short loc_1800DEC53
0x1800dec32  call    sub_180001870
0x1800dec37  cmp     [rax+7CCh], ebx
0x1800dec3d  jz      short loc_1800DEC53
0x1800dec3f  mov     r9d, ebx
0x1800dec42  mov     r8d, 4C5h
0x1800dec48  mov     rdx, r12
0x1800dec4b  mov     rcx, rax
0x1800dec4e  call    sub_18007FDD0
0x1800dec53  cmp     cs:byte_1801692C8, r15b
0x1800dec5a  jb      loc_1800DF54D
0x1800dec60  mov     edx, 67h ; 'g'
0x1800dec65  mov     rcx, cs:RequestContext
0x1800dec6c  lea     r8, qword_180159C70
0x1800dec73  mov     r9, rdi
0x1800dec76  mov     [rsp+70h+var_50], ebx
0x1800dec7a  mov     rcx, [rcx+10h]
0x1800dec7e  call    sub_18004F390
0x1800dec83  jmp     loc_1800DF54D
0x1800dec88  lea     rcx, [rbp+pvar]; pvar
0x1800dec8c  call    cs:PropVariantClear
0x1800dec92  mov     ebx, eax
0x1800dec94  test    eax, eax
0x1800dec96  jns     loc_1800DED28
0x1800dec9c  mov     rcx, cs:qword_180169350
0x1800deca3  test    rcx, rcx
0x1800deca6  jnz     short loc_1800DECEA
0x1800deca8  call    cs:MFGetCallStackTracingWeakReference
0x1800decae  mov     cs:qword_180169350, rax
0x1800decb5  mov     rcx, rax
0x1800decb8  test    rax, rax
0x1800decbb  jz      short loc_1800DECDC
0x1800decbd  mov     rax, [rax]
0x1800decc0  mov     edx, 7F0h
0x1800decc5  mov     rax, [rax+8]
0x1800decc9  call    cs:__guard_dispatch_icall_fptr
0x1800deccf  test    eax, eax
0x1800decd1  jz      short loc_1800DECDC
0x1800decd3  mov     rcx, cs:qword_180169350
0x1800decda  jmp     short loc_1800DECEA
0x1800decdc  lea     rcx, off_1801683B0
0x1800dece3  mov     cs:qword_180169350, rcx
0x1800decea  cmp     [rcx+8], r14b
0x1800decee  jz      short loc_1800DED11
0x1800decf0  call    sub_180001870
0x1800decf5  cmp     [rax+7CCh], ebx
0x1800decfb  jz      short loc_1800DED11
0x1800decfd  mov     r9d, ebx
0x1800ded00  mov     r8d, 4C6h
0x1800ded06  mov     rdx, r12
0x1800ded09  mov     rcx, rax
0x1800ded0c  call    sub_18007FDD0
0x1800ded11  cmp     cs:byte_1801692C8, r15b
0x1800ded18  jb      loc_1800DF54D
0x1800ded1e  mov     edx, 68h ; 'h'
0x1800ded23  jmp     loc_1800DEC65
0x1800ded28  mov     eax, 48h ; 'H'
0x1800ded2d  lea     r8, [rbp+clsid]
0x1800ded31  mov     word ptr [rbp+pvar], ax
0x1800ded35  lea     rdx, qword_18014EAD0
0x1800ded3c  mov     rax, [rsi]
0x1800ded3f  mov     rcx, rsi
0x1800ded42  mov     rax, [rax+50h]
0x1800ded46  call    cs:__guard_dispatch_icall_fptr
0x1800ded4c  test    eax, eax
0x1800ded4e  js      loc_1800DEF51
0x1800ded54  lea     rdx, [rbp+pvar]; ppropvar
0x1800ded58  lea     rcx, [rbp+clsid]; clsid
0x1800ded5c  call    cs:InitPropVariantFromCLSID
0x1800ded62  mov     ebx, eax
0x1800ded64  test    eax, eax
0x1800ded66  jns     loc_1800DEDF8
0x1800ded6c  mov     rcx, cs:qword_180169350
0x1800ded73  test    rcx, rcx
0x1800ded76  jnz     short loc_1800DEDBA
0x1800ded78  call    cs:MFGetCallStackTracingWeakReference
0x1800ded7e  mov     cs:qword_180169350, rax
0x1800ded85  mov     rcx, rax
0x1800ded88  test    rax, rax
0x1800ded8b  jz      short loc_1800DEDAC
0x1800ded8d  mov     rax, [rax]
0x1800ded90  mov     edx, 7F0h
0x1800ded95  mov     rax, [rax+8]
0x1800ded99  call    cs:__guard_dispatch_icall_fptr
0x1800ded9f  test    eax, eax
0x1800deda1  jz      short loc_1800DEDAC
0x1800deda3  mov     rcx, cs:qword_180169350
0x1800dedaa  jmp     short loc_1800DEDBA
0x1800dedac  lea     rcx, off_1801683B0
0x1800dedb3  mov     cs:qword_180169350, rcx
0x1800dedba  cmp     [rcx+8], r14b
0x1800dedbe  jz      short loc_1800DEDE1
0x1800dedc0  call    sub_180001870
0x1800dedc5  cmp     [rax+7CCh], ebx
0x1800dedcb  jz      short loc_1800DEDE1
0x1800dedcd  mov     r9d, ebx
0x1800dedd0  mov     r8d, 4D5h
0x1800dedd6  mov     rdx, r12
0x1800dedd9  mov     rcx, rax
0x1800deddc  call    sub_18007FDD0
0x1800dede1  cmp     cs:byte_1801692C8, r15b
0x1800dede8  jb      loc_1800DF54D
0x1800dedee  mov     edx, 69h ; 'i'
0x1800dedf3  jmp     loc_1800DEC65
0x1800dedf8  mov     rax, [rdi]
0x1800dedfb  lea     r8, [rbp+pvar]
0x1800dedff  xor     r9d, r9d
0x1800dee02  mov     [rsp+70h+var_50], r15d
0x1800dee07  lea     rdx, qword_18014C5F8
0x1800dee0e  mov     rcx, rdi
0x1800dee11  mov     rax, [rax+28h]
0x1800dee15  call    cs:__guard_dispatch_icall_fptr
0x1800dee1b  mov     ebx, eax
0x1800dee1d  test    eax, eax
0x1800dee1f  jns     loc_1800DEEB1
0x1800dee25  mov     rcx, cs:qword_180169350
0x1800dee2c  test    rcx, rcx
0x1800dee2f  jnz     short loc_1800DEE73
0x1800dee31  call    cs:MFGetCallStackTracingWeakReference
0x1800dee37  mov     cs:qword_180169350, rax
0x1800dee3e  mov     rcx, rax
0x1800dee41  test    rax, rax
0x1800dee44  jz      short loc_1800DEE65
0x1800dee46  mov     rax, [rax]
0x1800dee49  mov     edx, 7F0h
0x1800dee4e  mov     rax, [rax+8]
0x1800dee52  call    cs:__guard_dispatch_icall_fptr
0x1800dee58  test    eax, eax
0x1800dee5a  jz      short loc_1800DEE65
0x1800dee5c  mov     rcx, cs:qword_180169350
0x1800dee63  jmp     short loc_1800DEE73
0x1800dee65  lea     rcx, off_1801683B0
0x1800dee6c  mov     cs:qword_180169350, rcx
0x1800dee73  cmp     [rcx+8], r14b
0x1800dee77  jz      short loc_1800DEE9A
0x1800dee79  call    sub_180001870
0x1800dee7e  cmp     [rax+7CCh], ebx
0x1800dee84  jz      short loc_1800DEE9A
0x1800dee86  mov     r9d, ebx
0x1800dee89  mov     r8d, 4D6h
0x1800dee8f  mov     rdx, r12
0x1800dee92  mov     rcx, rax
0x1800dee95  call    sub_18007FDD0
0x1800dee9a  cmp     cs:byte_1801692C8, r15b
0x1800deea1  jb      loc_1800DF54D
0x1800deea7  mov     edx, 6Ah ; 'j'
0x1800deeac  jmp     loc_1800DEC65
0x1800deeb1  lea     rcx, [rbp+pvar]; pvar
0x1800deeb5  call    cs:PropVariantClear
0x1800deebb  mov     ebx, eax
0x1800deebd  test    eax, eax
0x1800deebf  jns     loc_1800DEF51
0x1800deec5  mov     rcx, cs:qword_180169350
0x1800deecc  test    rcx, rcx
0x1800deecf  jnz     short loc_1800DEF13
0x1800deed1  call    cs:MFGetCallStackTracingWeakReference
0x1800deed7  mov     cs:qword_180169350, rax
0x1800deede  mov     rcx, rax
0x1800deee1  test    rax, rax
0x1800deee4  jz      short loc_1800DEF05
0x1800deee6  mov     rax, [rax]
0x1800deee9  mov     edx, 7F0h
0x1800deeee  mov     rax, [rax+8]
0x1800deef2  call    cs:__guard_dispatch_icall_fptr
0x1800deef8  test    eax, eax
0x1800deefa  jz      short loc_1800DEF05
0x1800deefc  mov     rcx, cs:qword_180169350
0x1800def03  jmp     short loc_1800DEF13
0x1800def05  lea     rcx, off_1801683B0
0x1800def0c  mov     cs:qword_180169350, rcx
0x1800def13  cmp     [rcx+8], r14b
0x1800def17  jz      short loc_1800DEF3A
0x1800def19  call    sub_180001870
0x1800def1e  cmp     [rax+7CCh], ebx
0x1800def24  jz      short loc_1800DEF3A
0x1800def26  mov     r9d, ebx
0x1800def29  mov     r8d, 4D7h
0x1800def2f  mov     rdx, r12
0x1800def32  mov     rcx, rax
0x1800def35  call    sub_18007FDD0
0x1800def3a  cmp     cs:byte_1801692C8, r15b
0x1800def41  jb      loc_1800DF54D
0x1800def47  mov     edx, 6Bh ; 'k'
0x1800def4c  jmp     loc_1800DEC65
0x1800def51  mov     rax, [rsi]
0x1800def54  lea     r8, [rbp+var_40]
0x1800def58  lea     rdx, qword_18014EB30
0x1800def5f  mov     word ptr [rbp+pvar], r13w
0x1800def64  mov     rcx, rsi
0x1800def67  mov     rax, [rax+38h]
0x1800def6b  call    cs:__guard_dispatch_icall_fptr
0x1800def71  test    eax, eax
0x1800def73  js      loc_1800DF0D8
0x1800def79  mov     eax, [rbp+var_40]
0x1800def7c  lea     r8, [rbp+pvar]
0x1800def80  mov     dword ptr [rbp+pvar+8], eax
0x1800def83  lea     rdx, qword_18014C640
0x1800def8a  mov     rax, [rdi]
0x1800def8d  xor     r9d, r9d
0x1800def90  mov     rcx, rdi
0x1800def93  mov     [rsp+70h+var_50], r15d
0x1800def98  mov     rax, [rax+28h]
0x1800def9c  call    cs:__guard_dispatch_icall_fptr
0x1800defa2  mov     ebx, eax
0x1800defa4  test    eax, eax
0x1800defa6  jns     loc_1800DF038
0x1800defac  mov     rcx, cs:qword_180169350
0x1800defb3  test    rcx, rcx
0x1800defb6  jnz     short loc_1800DEFFA
0x1800defb8  call    cs:MFGetCallStackTracingWeakReference
0x1800defbe  mov     cs:qword_180169350, rax
0x1800defc5  mov     rcx, rax
0x1800defc8  test    rax, rax
0x1800defcb  jz      short loc_1800DEFEC
0x1800defcd  mov     rax, [rax]
0x1800defd0  mov     edx, 7F0h
0x1800defd5  mov     rax, [rax+8]
0x1800defd9  call    cs:__guard_dispatch_icall_fptr
0x1800defdf  test    eax, eax
0x1800defe1  jz      short loc_1800DEFEC
0x1800defe3  mov     rcx, cs:qword_180169350
0x1800defea  jmp     short loc_1800DEFFA
0x1800defec  lea     rcx, off_1801683B0
0x1800deff3  mov     cs:qword_180169350, rcx
0x1800deffa  cmp     [rcx+8], r14b
0x1800deffe  jz      short loc_1800DF021
0x1800df000  call    sub_180001870
0x1800df005  cmp     [rax+7CCh], ebx
0x1800df00b  jz      short loc_1800DF021
  ... truncated ...
```
