# sub_1800DFF4C

- ea: `0x1800dff4c`
- end: `0x1800e0c8e`
- name: `sub_1800DFF4C`
- size: `3394`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800ddaa0`

## callees

- `0x180002d00`
- `0x180059ab4`
- `0x180059cbc`
- `0x180059eac`
- `0x18005ae04`
- `0x18005b17c`
- `0x18005b28c`
- `0x180070420`
- `0x180070474`
- `0x180079880`
- `0x1800dff4c`
- `0x1800e2a28`
- `0x1800e2f50`
- `0x1800e7308`
- `0x180207168`
- `0x1802b5f70`
- `0x1802b9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e07d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e0a7e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e07d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e0a7e`
- `MFPlat!MFCreateCollection` at `0x1800e02b7`
- `MFPlat!MFCreateCollection` at `0x1800e02b7`
- `MFPlat!MFCreateMediaType` at `0x1800e0055`
- `MFPlat!MFCreateMediaType` at `0x1800e0055`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800e073c`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800e073c`

## string_xrefs

- `0x1800dff8e`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e00ab`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e016c`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e024e`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e030d`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e03c0`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e0471`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e0525`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e05d2`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e07c3`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e0895`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`
- `0x1800e0b2d`: `CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage`

## pseudocode

```c
__int64 __fastcall sub_1800DFF4C(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // r14d
  __int64 v6; // rdi
  int v7; // ebx
  HRESULT v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  __int64 v50; // rbx
  __int64 (__fastcall *v51)(__int64, _QWORD, __int64 *); // rdi
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  __int64 v62; // rax
  __int64 v63; // r8
  __int64 *v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r8
  __int64 *v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 *v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 *v75; // rcx
  __int64 v76; // rbx
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 *v80; // rcx
  __int64 v81; // rax
  __int64 v82; // r8
  __int64 v83; // rbx
  __int64 (__fastcall *v84)(__int64, __int64, __int64, IMFMediaType *, IMFMediaBuffer *, __int64); // rdi
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 *v89; // rcx
  IMFMediaType *ppMFType; // [rsp+48h] [rbp-89h] BYREF
  __int64 v92; // [rsp+50h] [rbp-81h] BYREF
  _BYTE v93[8]; // [rsp+58h] [rbp-79h] BYREF
  __int64 v94; // [rsp+60h] [rbp-71h] BYREF
  __int64 v95; // [rsp+68h] [rbp-69h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+70h] [rbp-61h] BYREF
  __int64 v97; // [rsp+78h] [rbp-59h] BYREF
  __int64 v98; // [rsp+80h] [rbp-51h] BYREF
  unsigned int v99; // [rsp+88h] [rbp-49h] BYREF
  __int64 v100; // [rsp+90h] [rbp-41h] BYREF
  __int64 v101; // [rsp+98h] [rbp-39h] BYREF
  _DWORD v102[2]; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v103; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v104; // [rsp+B8h] [rbp-19h]
  _QWORD v105[2]; // [rsp+C0h] [rbp-11h] BYREF
  int v106; // [rsp+D0h] [rbp-1h]
  __int64 v107; // [rsp+D8h] [rbp+7h]
  PROPVARIANT cbMaxLength; // [rsp+E0h] [rbp+Fh] BYREF

  v107 = -2;
  sub_180059AB4(v93, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", 1200);
  v5 = 0;
  if ( *(_BYTE *)(qword_180685260 + 8) && *(_QWORD *)(a1 + 192) )
  {
    v6 = sub_18005AE04(qword_180685260, v2, v3, v4);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 192) + 296LL))(*(_QWORD *)(a1 + 192));
    *(_OWORD *)(v6 + 2000) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(**(_QWORD **)(a1 + 192)
                                                                                         + 280LL))(
                                          *(_QWORD *)(a1 + 192),
                                          &cbMaxLength);
    *(_DWORD *)(v6 + 2016) = v7;
  }
  v105[0] = "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage";
  v105[1] = 0;
  v106 = 15;
  sub_18005B28C(0, 15, "=>%s", "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage");
  if ( *(_QWORD *)(a1 + 424) == *(_QWORD *)(a1 + 416) )
  {
    v8 = 0;
    goto LABEL_183;
  }
  ppMFType = 0;
  sub_180070474(&ppMFType);
  v8 = MFCreateMediaType(&ppMFType);
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 152, qword_1805D7080, 0, v8);
    }
    v12 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v12 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v12 + 8) )
      goto LABEL_182;
    v13 = sub_18005AE04(v12, v9, v10, v11);
    if ( *(_DWORD *)(v13 + 1996) == v8 )
      goto LABEL_182;
    v14 = 1213;
    goto LABEL_16;
  }
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, __int128 *, __int64 *))ppMFType->lpVtbl->SetGUID)(
         ppMFType,
         &xmmword_1805D02A0,
         &qword_1805D0880);
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 153, qword_1805D7080, 0, v8);
    }
    v18 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v18 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v18 + 8) )
      goto LABEL_182;
    v13 = sub_18005AE04(v18, v15, v16, v17);
    if ( *(_DWORD *)(v13 + 1996) == v8 )
      goto LABEL_182;
    v14 = 1215;
LABEL_16:
    sub_180207168(v13, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", v14, (unsigned int)v8);
    goto LABEL_182;
  }
  v94 = *(_QWORD *)(a1 + 208);
  v19 = v94;
  sub_180070420(&v94);
  (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v19 + 40LL))(v19, v102);
  v8 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, unsigned __int64))ppMFType->lpVtbl->SetUINT64)(
         ppMFType,
         qword_1805D0500,
         v102[1] | ((unsigned __int64)v102[0] << 32));
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 154, qword_1805D7080, 0, v8);
    }
    v23 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v23 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v24 = sub_18005AE04(v23, v20, v21, v22);
      if ( *(_DWORD *)(v24 + 1996) != v8 )
        sub_180207168(v24, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", 1218, (unsigned int)v8);
    }
    goto LABEL_181;
  }
  v92 = 0;
  sub_180070474(&v92);
  v8 = MFCreateCollection(&v92);
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 155, qword_1805D7080, 0, v8);
    }
    v28 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v28 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v28 + 8) )
      goto LABEL_180;
    v29 = sub_18005AE04(v28, v25, v26, v27);
    if ( *(_DWORD *)(v29 + 1996) == v8 )
      goto LABEL_180;
    v30 = 1222;
    goto LABEL_47;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 40LL))(v92, v19);
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 156, qword_1805D7080, 0, v8);
    }
    v34 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v34 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v34 + 8) )
      goto LABEL_180;
    v29 = sub_18005AE04(v34, v31, v32, v33);
    if ( *(_DWORD *)(v29 + 1996) == v8 )
      goto LABEL_180;
    v30 = 1225;
LABEL_47:
    sub_180207168(v29, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", v30, (unsigned int)v8);
    goto LABEL_180;
  }
  v95 = 0;
  v35 = **(_QWORD **)(a1 + 416);
  sub_18005B17C(&v95);
  v8 = sub_1800E2A28(v35, &v95);
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 157, qword_1805D7080, 0, v8);
    }
    v39 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v39 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v39 + 8) )
      goto LABEL_179;
    v40 = sub_18005AE04(v39, v36, v37, v38);
    if ( *(_DWORD *)(v40 + 1996) == v8 )
      goto LABEL_179;
    v41 = 1229;
    goto LABEL_68;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 40LL))(v92, v95);
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 158, qword_1805D7080, 0, v8);
    }
    v45 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v45 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v45 + 8) )
      goto LABEL_179;
    v40 = sub_18005AE04(v45, v42, v43, v44);
    if ( *(_DWORD *)(v40 + 1996) == v8 )
      goto LABEL_179;
    v41 = 1232;
    goto LABEL_68;
  }
  v99 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)(a1 + 32) + 32LL))(a1 + 32, &v99);
  if ( v8 < 0 )
  {
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 159, qword_1805D7080, 0, v8);
    }
    v49 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v49 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v49 + 8) )
      goto LABEL_179;
    v40 = sub_18005AE04(v49, v46, v47, v48);
    if ( *(_DWORD *)(v40 + 1996) == v8 )
      goto LABEL_179;
    v41 = 1236;
LABEL_68:
    sub_180207168(v40, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", v41, (unsigned int)v8);
    goto LABEL_179;
  }
  v50 = 0;
  v97 = 0;
  if ( !v99 )
    goto LABEL_94;
  while ( 1 )
  {
    v98 = 0;
    v51 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)(a1 + 32) + 40LL);
    sub_180070474(&v98);
    v8 = v51(a1 + 32, v5, &v98);
    if ( v8 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 160, qword_1805D7080, 0, v8);
      }
      v67 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v67 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v67 + 8) )
        goto LABEL_123;
      v65 = sub_18005AE04(v67, v52, v53, v54);
      if ( *(_DWORD *)(v65 + 1996) == v8 )
        goto LABEL_123;
      v66 = 1242;
      goto LABEL_122;
    }
    *(_OWORD *)&cbMaxLength.vt = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *))(*(_QWORD *)v98 + 24LL))(v98, &cbMaxLength);
    if ( v8 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 161, qword_1805D7080, 0, v8);
      }
      v64 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v64 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v64 + 8) )
        goto LABEL_123;
      v65 = sub_18005AE04(v64, v55, v56, v57);
      if ( *(_DWORD *)(v65 + 1996) == v8 )
        goto LABEL_123;
      v66 = 1245;
LABEL_122:
      sub_180207168(v65, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", v66, (unsigned int)v8);
LABEL_123:
      sub_180070474(&v98);
      goto LABEL_178;
    }
    if ( *(_OWORD *)&cbMaxLength.vt == __PAIR128__(0xE3216DB1AB59A8A7uLL, 0x4EC2C446568D3138LL) )
      break;
    sub_180070474(&v98);
    if ( ++v5 >= v99 )
      goto LABEL_94;
  }
  if ( v98 )
  {
    v101 = v98;
    v50 = v98;
    sub_180070420(&v101);
    v101 = 0;
    v97 = v50;
    sub_180070474(&v101);
  }
  sub_180070474(&v98);
LABEL_94:
  ppBuffer = 0;
  if ( !v50 )
  {
LABEL_154:
    v100 = 0;
    v76 = *(_QWORD *)(a1 + 176);
    sub_18005B17C(&v100);
    v8 = sub_1800E2F50(v76, &v100);
    if ( v8 >= 0 )
    {
      v83 = v100;
      v84 = *(__int64 (__fastcall **)(__int64, __int64, __int64, IMFMediaType *, IMFMediaBuffer *, __int64))(*(_QWORD *)v100 + 112LL);
      sub_18005B17C(a1 + 208);
      LOBYTE(v85) = 1;
      v8 = v84(v83, v85, v92, ppMFType, ppBuffer, a1 + 208);
      if ( v8 >= 0 )
      {
        sub_1800E7308(a1 + 416);
        goto LABEL_176;
      }
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 166, qword_1805D7080, 0, v8);
      }
      v89 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v89 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v89 + 8) )
        goto LABEL_176;
      v81 = sub_18005AE04(v89, v86, v87, v88);
      if ( *(_DWORD *)(v81 + 1996) == v8 )
        goto LABEL_176;
      v82 = 1289;
    }
    else
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 165, qword_1805D7080, 0, v8);
      }
      v80 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v80 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v80 + 8) )
        goto LABEL_176;
      v81 = sub_18005AE04(v80, v77, v78, v79);
      if ( *(_DWORD *)(v81 + 1996) == v8 )
        goto LABEL_176;
      v82 = 1280;
    }
    sub_180207168(v81, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", v82, (unsigned int)v8);
LABEL_176:
    sub_18005B17C(&v100);
    goto LABEL_177;
  }
  v103 = 0;
  v104 = 0;
  memset(&cbMaxLength, 0, sizeof(cbMaxLength));
  LOWORD(v103) = 18;
  WORD4(v103) = 1;
  if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)v50 + 56LL))(
         v50,
         0,
         &v103,
         &cbMaxLength) < 0
    || cbMaxLength.vt != 4113
    || !cbMaxLength.lVal )
  {
LABEL_153:
    PropVariantClear(&cbMaxLength);
    goto LABEL_154;
  }
  sub_180070474(&ppBuffer);
  v8 = MFCreateMemoryBuffer(cbMaxLength.ulVal, &ppBuffer);
  if ( v8 >= 0 )
  {
    v101 = 0;
    v8 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
           ppBuffer,
           &v101,
           0,
           0);
    if ( v8 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 163, qword_1805D7080, 0, v8);
      }
      v71 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v71 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v71 + 8) )
        goto LABEL_109;
      v62 = sub_18005AE04(v71, v68, v69, v70);
      if ( *(_DWORD *)(v62 + 1996) == v8 )
        goto LABEL_109;
      v63 = 1272;
      goto LABEL_108;
    }
    sub_1802B5F70(v101, cbMaxLength.bstrblobVal.pData, cbMaxLength.ulVal);
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    v8 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
           ppBuffer,
           cbMaxLength.ulVal);
    if ( v8 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 164, qword_1805D7080, 0, v8);
      }
      v75 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v75 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v75 + 8) )
        goto LABEL_109;
      v62 = sub_18005AE04(v75, v72, v73, v74);
      if ( *(_DWORD *)(v62 + 1996) == v8 )
        goto LABEL_109;
      v63 = 1275;
LABEL_108:
      sub_180207168(v62, "CWICHeifEncoderFrame::CommitGainMapAndCreateToneMapImage", v63, (unsigned int)v8);
      goto LABEL_109;
    }
    goto LABEL_153;
  }
  if ( RequestContext != &RequestContext
    && (*((_BYTE *)RequestContext + 28) & 1) != 0
    && *((_BYTE *)RequestContext + 25) >= 4u )
  {
    sub_180079880(*((_QWORD *)RequestContext + 2), 162, qword_1805D7080, 0, v8);
  }
  v61 = (__int64 *)qword_180685260;
  if ( !qword_180685260 )
  {
    v61 = &qword_180684620;
    qword_180685260 = (__int64)&qword_180684620;
  }
  if ( *((_BYTE *)v61 + 8) )
  {
    v62 = sub_18005AE04(v61, v58, v59, v60);
    if ( *(_DWORD *)(v62 + 1996) != v8 )
    {
      v63 = 1269;
      goto LABEL_108;
    }
  }
LABEL_109:
  PropVariantClear(&cbMaxLength);
LABEL_177:
  sub_180070474(&ppBuffer);
LABEL_178:
  sub_180070474(&v97);
LABEL_179:
  sub_18005B17C(&v95);
LABEL_180:
  sub_180070474(&v92);
LABEL_181:
  sub_18005B17C(&v94);
LABEL_182:
  sub_180070474(&ppMFType);
LABEL_183:
  sub_180059CBC(v105);
  sub_180059EAC(v93);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800dff4c  mov     rax, rsp
0x1800dff4f  push    rbp
0x1800dff50  push    r12
0x1800dff52  push    r13
0x1800dff54  push    r14
0x1800dff56  push    r15
0x1800dff58  lea     rbp, [rax-5Fh]
0x1800dff5c  sub     rsp, 100h
0x1800dff63  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800dff6b  mov     [rax+10h], rbx
0x1800dff6f  mov     [rax+18h], rsi
0x1800dff73  mov     [rax+20h], rdi
0x1800dff77  mov     rax, cs:__security_cookie
0x1800dff7e  xor     rax, rsp
0x1800dff81  mov     [rbp+57h+var_30], rax
0x1800dff85  mov     r15, rcx
0x1800dff88  mov     r8d, 4B0h
0x1800dff8e  lea     rsi, aCwicheifencode_13; "CWICHeifEncoderFrame::CommitGainMapAndC"...
0x1800dff95  mov     rdx, rsi
0x1800dff98  lea     rcx, [rbp+57h+var_D0]
0x1800dff9c  call    sub_180059AB4
0x1800dffa1  nop
0x1800dffa2  xor     r14d, r14d
0x1800dffa5  mov     rcx, cs:qword_180685260
0x1800dffac  cmp     [rcx+8], r14b
0x1800dffb0  jz      short loc_1800E0006
0x1800dffb2  cmp     [r15+0C0h], r14
0x1800dffb9  jz      short loc_1800E0006
0x1800dffbb  call    sub_18005AE04
0x1800dffc0  mov     rdi, rax
0x1800dffc3  mov     rcx, [r15+0C0h]
0x1800dffca  mov     rdx, [rcx]
0x1800dffcd  mov     rax, [rdx+128h]
0x1800dffd4  call    j__guard_dispatch_icall
0x1800dffd9  mov     ebx, eax
0x1800dffdb  mov     rcx, [r15+0C0h]
0x1800dffe2  mov     rdx, [rcx]
0x1800dffe5  mov     rax, [rdx+118h]
0x1800dffec  lea     rdx, [rbp+57h+cbMaxLength]
0x1800dfff0  call    j__guard_dispatch_icall
0x1800dfff5  movups  xmm0, xmmword ptr [rax]
0x1800dfff8  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800e0000  mov     [rdi+7E0h], ebx
0x1800e0006  mov     [rbp+57h+var_68], rsi
0x1800e000a  mov     [rbp+57h+var_60], r14
0x1800e000e  mov     edx, 0Fh
0x1800e0013  mov     [rbp+57h+var_58], edx
0x1800e0016  mov     r9, rsi
0x1800e0019  lea     r8, aS_0; "=>%s"
0x1800e0020  xor     ecx, ecx
0x1800e0022  call    sub_18005B28C
0x1800e0027  nop
0x1800e0028  lea     r13, [r15+1A0h]
0x1800e002f  mov     rax, [r13+8]
0x1800e0033  cmp     rax, [r13+0]
0x1800e0037  jnz     short loc_1800E0041
0x1800e0039  mov     edi, r14d
0x1800e003c  jmp     loc_1800E0C4B
0x1800e0041  mov     [rsp+120h+ppMFType], r14
0x1800e0046  lea     rcx, [rsp+120h+ppMFType]
0x1800e004b  call    sub_180070474
0x1800e0050  lea     rcx, [rsp+120h+ppMFType]; ppMFType
0x1800e0055  call    cs:MFCreateMediaType
0x1800e005c  nop     dword ptr [rax+rax+00h]
0x1800e0061  mov     edi, eax
0x1800e0063  test    eax, eax
0x1800e0065  jns     loc_1800E0100
0x1800e006b  lea     rax, RequestContext
0x1800e0072  mov     rcx, cs:RequestContext
0x1800e0079  cmp     rcx, rax
0x1800e007c  jz      short loc_1800E00B2
0x1800e007e  mov     esi, 1
0x1800e0083  test    [rcx+1Ch], sil
0x1800e0087  jz      short loc_1800E00AB
0x1800e0089  cmp     byte ptr [rcx+19h], 4
0x1800e008d  jb      short loc_1800E00AB
0x1800e008f  mov     edx, 98h
0x1800e0094  mov     dword ptr [rsp+120h+var_100], edi
0x1800e0098  xor     r9d, r9d
0x1800e009b  lea     r8, qword_1805D7080
0x1800e00a2  mov     rcx, [rcx+10h]
0x1800e00a6  call    sub_180079880
0x1800e00ab  lea     rsi, aCwicheifencode_13; "CWICHeifEncoderFrame::CommitGainMapAndC"...
0x1800e00b2  mov     rcx, cs:qword_180685260
0x1800e00b9  test    rcx, rcx
0x1800e00bc  jnz     short loc_1800E00CC
0x1800e00be  lea     rcx, qword_180684620
0x1800e00c5  mov     cs:qword_180685260, rcx
0x1800e00cc  cmp     [rcx+8], r14b
0x1800e00d0  jz      loc_1800E0C40
0x1800e00d6  call    sub_18005AE04
0x1800e00db  cmp     [rax+7CCh], edi
0x1800e00e1  jz      loc_1800E0C40
0x1800e00e7  mov     r8d, 4BDh
0x1800e00ed  mov     r9d, edi
0x1800e00f0  mov     rdx, rsi
0x1800e00f3  mov     rcx, rax
0x1800e00f6  call    sub_180207168
0x1800e00fb  jmp     loc_1800E0C40
0x1800e0100  mov     rcx, [rsp+120h+ppMFType]
0x1800e0105  mov     rax, [rcx]
0x1800e0108  lea     r8, qword_1805D0880
0x1800e010f  lea     rdx, xmmword_1805D02A0
0x1800e0116  mov     rax, [rax+0C0h]
0x1800e011d  call    j__guard_dispatch_icall
0x1800e0122  mov     edi, eax
0x1800e0124  test    eax, eax
0x1800e0126  jns     loc_1800E01B3
0x1800e012c  lea     rax, RequestContext
0x1800e0133  mov     rcx, cs:RequestContext
0x1800e013a  cmp     rcx, rax
0x1800e013d  jz      short loc_1800E0173
0x1800e013f  mov     esi, 1
0x1800e0144  test    [rcx+1Ch], sil
0x1800e0148  jz      short loc_1800E016C
0x1800e014a  cmp     byte ptr [rcx+19h], 4
0x1800e014e  jb      short loc_1800E016C
0x1800e0150  mov     edx, 99h
0x1800e0155  mov     dword ptr [rsp+120h+var_100], edi
0x1800e0159  xor     r9d, r9d
0x1800e015c  lea     r8, qword_1805D7080
0x1800e0163  mov     rcx, [rcx+10h]
0x1800e0167  call    sub_180079880
0x1800e016c  lea     rsi, aCwicheifencode_13; "CWICHeifEncoderFrame::CommitGainMapAndC"...
0x1800e0173  mov     rcx, cs:qword_180685260
0x1800e017a  test    rcx, rcx
0x1800e017d  jnz     short loc_1800E018D
0x1800e017f  lea     rcx, qword_180684620
0x1800e0186  mov     cs:qword_180685260, rcx
0x1800e018d  cmp     [rcx+8], r14b
0x1800e0191  jz      loc_1800E0C40
0x1800e0197  call    sub_18005AE04
0x1800e019c  cmp     [rax+7CCh], edi
0x1800e01a2  jz      loc_1800E0C40
0x1800e01a8  mov     r8d, 4BFh
0x1800e01ae  jmp     loc_1800E00ED
0x1800e01b3  mov     rbx, [r15+0D0h]
0x1800e01ba  mov     [rbp+57h+var_C8], rbx
0x1800e01be  lea     rcx, [rbp+57h+var_C8]
0x1800e01c2  call    sub_180070420
0x1800e01c7  nop
0x1800e01c8  mov     rax, [rbx]
0x1800e01cb  lea     rdx, [rbp+57h+var_88]
0x1800e01cf  mov     rcx, rbx
0x1800e01d2  mov     rax, [rax+28h]
0x1800e01d6  call    j__guard_dispatch_icall
0x1800e01db  mov     rcx, [rsp+120h+ppMFType]
0x1800e01e0  mov     r8d, [rbp+57h+var_88]
0x1800e01e4  shl     r8, 20h
0x1800e01e8  mov     eax, [rbp+57h+var_84]
0x1800e01eb  or      r8, rax
0x1800e01ee  mov     rax, [rcx]
0x1800e01f1  lea     rdx, qword_1805D0500
0x1800e01f8  mov     rax, [rax+0B0h]
0x1800e01ff  call    j__guard_dispatch_icall
0x1800e0204  mov     edi, eax
0x1800e0206  test    eax, eax
0x1800e0208  jns     loc_1800E02A3
0x1800e020e  lea     rax, RequestContext
0x1800e0215  mov     rcx, cs:RequestContext
0x1800e021c  cmp     rcx, rax
0x1800e021f  jz      short loc_1800E0255
0x1800e0221  mov     esi, 1
0x1800e0226  test    [rcx+1Ch], sil
0x1800e022a  jz      short loc_1800E024E
0x1800e022c  cmp     byte ptr [rcx+19h], 4
0x1800e0230  jb      short loc_1800E024E
0x1800e0232  mov     edx, 9Ah
0x1800e0237  mov     dword ptr [rsp+120h+var_100], edi
0x1800e023b  xor     r9d, r9d
0x1800e023e  lea     r8, qword_1805D7080
0x1800e0245  mov     rcx, [rcx+10h]
0x1800e0249  call    sub_180079880
0x1800e024e  lea     rsi, aCwicheifencode_13; "CWICHeifEncoderFrame::CommitGainMapAndC"...
0x1800e0255  mov     rcx, cs:qword_180685260
0x1800e025c  test    rcx, rcx
0x1800e025f  jnz     short loc_1800E026F
0x1800e0261  lea     rcx, qword_180684620
0x1800e0268  mov     cs:qword_180685260, rcx
0x1800e026f  cmp     [rcx+8], r14b
0x1800e0273  jz      loc_1800E0C36
0x1800e0279  call    sub_18005AE04
0x1800e027e  cmp     [rax+7CCh], edi
0x1800e0284  jz      loc_1800E0C36
0x1800e028a  mov     r9d, edi
0x1800e028d  mov     r8d, 4C2h
0x1800e0293  mov     rdx, rsi
0x1800e0296  mov     rcx, rax
0x1800e0299  call    sub_180207168
0x1800e029e  jmp     loc_1800E0C36
0x1800e02a3  mov     [rsp+120h+var_D8], r14
0x1800e02a8  lea     rcx, [rsp+120h+var_D8]
0x1800e02ad  call    sub_180070474
0x1800e02b2  lea     rcx, [rsp+120h+var_D8]
0x1800e02b7  call    cs:MFCreateCollection
0x1800e02be  nop     dword ptr [rax+rax+00h]
0x1800e02c3  mov     edi, eax
0x1800e02c5  test    eax, eax
0x1800e02c7  jns     loc_1800E0362
0x1800e02cd  lea     rax, RequestContext
0x1800e02d4  mov     rcx, cs:RequestContext
0x1800e02db  cmp     rcx, rax
0x1800e02de  jz      short loc_1800E0314
0x1800e02e0  mov     esi, 1
0x1800e02e5  test    [rcx+1Ch], sil
0x1800e02e9  jz      short loc_1800E030D
0x1800e02eb  cmp     byte ptr [rcx+19h], 4
0x1800e02ef  jb      short loc_1800E030D
0x1800e02f1  mov     edx, 9Bh
0x1800e02f6  mov     dword ptr [rsp+120h+var_100], edi
0x1800e02fa  xor     r9d, r9d
0x1800e02fd  lea     r8, qword_1805D7080
0x1800e0304  mov     rcx, [rcx+10h]
0x1800e0308  call    sub_180079880
0x1800e030d  lea     rsi, aCwicheifencode_13; "CWICHeifEncoderFrame::CommitGainMapAndC"...
0x1800e0314  mov     rcx, cs:qword_180685260
0x1800e031b  test    rcx, rcx
0x1800e031e  jnz     short loc_1800E032E
0x1800e0320  lea     rcx, qword_180684620
0x1800e0327  mov     cs:qword_180685260, rcx
0x1800e032e  cmp     [rcx+8], r14b
0x1800e0332  jz      loc_1800E0C2B
0x1800e0338  call    sub_18005AE04
0x1800e033d  cmp     [rax+7CCh], edi
0x1800e0343  jz      loc_1800E0C2B
0x1800e0349  mov     r8d, 4C6h
0x1800e034f  mov     r9d, edi
0x1800e0352  mov     rdx, rsi
0x1800e0355  mov     rcx, rax
0x1800e0358  call    sub_180207168
0x1800e035d  jmp     loc_1800E0C2B
0x1800e0362  mov     rcx, [rsp+120h+var_D8]
0x1800e0367  mov     rax, [rcx]
0x1800e036a  mov     rdx, rbx
0x1800e036d  mov     rax, [rax+28h]
0x1800e0371  call    j__guard_dispatch_icall
0x1800e0376  mov     edi, eax
0x1800e0378  test    eax, eax
0x1800e037a  jns     loc_1800E0407
0x1800e0380  lea     rax, RequestContext
0x1800e0387  mov     rcx, cs:RequestContext
0x1800e038e  cmp     rcx, rax
0x1800e0391  jz      short loc_1800E03C7
0x1800e0393  mov     esi, 1
0x1800e0398  test    [rcx+1Ch], sil
0x1800e039c  jz      short loc_1800E03C0
0x1800e039e  cmp     byte ptr [rcx+19h], 4
0x1800e03a2  jb      short loc_1800E03C0
0x1800e03a4  mov     edx, 9Ch
0x1800e03a9  mov     dword ptr [rsp+120h+var_100], edi
0x1800e03ad  xor     r9d, r9d
0x1800e03b0  lea     r8, qword_1805D7080
0x1800e03b7  mov     rcx, [rcx+10h]
0x1800e03bb  call    sub_180079880
0x1800e03c0  lea     rsi, aCwicheifencode_13; "CWICHeifEncoderFrame::CommitGainMapAndC"...
0x1800e03c7  mov     rcx, cs:qword_180685260
0x1800e03ce  test    rcx, rcx
0x1800e03d1  jnz     short loc_1800E03E1
0x1800e03d3  lea     rcx, qword_180684620
0x1800e03da  mov     cs:qword_180685260, rcx
0x1800e03e1  cmp     [rcx+8], r14b
0x1800e03e5  jz      loc_1800E0C2B
0x1800e03eb  call    sub_18005AE04
0x1800e03f0  cmp     [rax+7CCh], edi
0x1800e03f6  jz      loc_1800E0C2B
0x1800e03fc  mov     r8d, 4C9h
0x1800e0402  jmp     loc_1800E034F
0x1800e0407  mov     [rbp+57h+var_C0], r14
0x1800e040b  mov     rax, [r13+0]
0x1800e040f  mov     rbx, [rax]
0x1800e0412  lea     rcx, [rbp+57h+var_C0]
0x1800e0416  call    sub_18005B17C
0x1800e041b  lea     rdx, [rbp+57h+var_C0]
0x1800e041f  mov     rcx, rbx
0x1800e0422  call    sub_1800E2A28
0x1800e0427  mov     edi, eax
0x1800e0429  test    eax, eax
0x1800e042b  jns     loc_1800E04C6
0x1800e0431  lea     rax, RequestContext
0x1800e0438  mov     rcx, cs:RequestContext
0x1800e043f  cmp     rcx, rax
0x1800e0442  jz      short loc_1800E0478
0x1800e0444  mov     esi, 1
0x1800e0449  test    [rcx+1Ch], sil
0x1800e044d  jz      short loc_1800E0471
0x1800e044f  cmp     byte ptr [rcx+19h], 4
0x1800e0453  jb      short loc_1800E0471
0x1800e0455  mov     edx, 9Dh
0x1800e045a  mov     dword ptr [rsp+120h+var_100], edi
0x1800e045e  xor     r9d, r9d
0x1800e0461  lea     r8, qword_1805D7080
0x1800e0468  mov     rcx, [rcx+10h]
0x1800e046c  call    sub_180079880
0x1800e0471  lea     rsi, aCwicheifencode_13; "CWICHeifEncoderFrame::CommitGainMapAndC"...
0x1800e0478  mov     rcx, cs:qword_180685260
0x1800e047f  test    rcx, rcx
0x1800e0482  jnz     short loc_1800E0492
0x1800e0484  lea     rcx, qword_180684620
0x1800e048b  mov     cs:qword_180685260, rcx
0x1800e0492  cmp     [rcx+8], r14b
  ... truncated ...
```
