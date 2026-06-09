# AppendPropVariant_0

- ea: `0x18021cf40`
- end: `0x18021d975`
- name: `AppendPropVariant_0`
- size: `2613`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar, PROPVARIANT *pvarSrc)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802724e0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x180111d68`
- `0x18019d300`
- `0x1801c1658`
- `0x1801dae40`
- `0x18021cf40`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021d952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021d952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d5d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d5d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021cf9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d082`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d1ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d306`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d3cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d609`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d7ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d8a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021cf9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d082`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d1ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d306`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d3cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d609`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d7ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d8a9`

## pseudocode

```c
__int64 __fastcall AppendPropVariant_0(PROPVARIANT *pvar, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 *v7; // rbx
  int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned __int16 v12; // cx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int16 v19; // dx
  int v20; // esi
  unsigned int v21; // ebx
  int v22; // r12d
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  SIZE_T *p_cb; // rcx
  unsigned int v31; // edx
  int v32; // r8d
  _OWORD *v33; // r8
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  char v38; // r9
  __int64 *v39; // rbx
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 *v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rax
  __int16 v49; // cx
  PROPVARIANT *v50; // rax
  PROPVARIANT *v51; // rdx
  __int16 v52; // cx
  unsigned int v53; // ecx
  unsigned int *v54; // r9
  PROPVARIANT *v55; // r15
  size_t v56; // rax
  size_t v57; // r8
  PROPVARIANT v58; // rdx
  unsigned int *v59; // rcx
  unsigned int v60; // r8d
  unsigned int *v61; // rax
  __int64 v62; // r8
  __int64 *v63; // rcx
  __int64 v64; // rax
  __int64 v65; // r8
  __int64 *v66; // rcx
  __int64 v67; // rax
  __int64 v68; // r8
  __int64 v69; // r8
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  PROPVARIANT *v73; // r15
  __int64 *v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 *v80; // rbx
  __int64 v81; // rax
  __int64 v82; // rax
  unsigned int v84; // [rsp+30h] [rbp-39h]
  unsigned int *v85; // [rsp+38h] [rbp-31h]
  PROPVARIANT *v86; // [rsp+40h] [rbp-29h]
  size_t Size; // [rsp+48h] [rbp-21h]
  size_t Sizea; // [rsp+48h] [rbp-21h]
  unsigned int *v89; // [rsp+50h] [rbp-19h]
  _DWORD v90[2]; // [rsp+58h] [rbp-11h]
  PROPVARIANT *v91; // [rsp+60h] [rbp-9h]
  int v92; // [rsp+68h] [rbp-1h]
  PROPVARIANT *v93; // [rsp+70h] [rbp+7h]
  PROPVARIANT *v94; // [rsp+D0h] [rbp+67h] BYREF
  SIZE_T cb; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v96; // [rsp+E0h] [rbp+77h] BYREF
  int v97; // [rsp+E8h] [rbp+7Fh]

  v94 = pvar;
  v96 = 0;
  if ( pvar == pvarSrc )
  {
    sub_18002FEE0(&v94, "CMFPropVariantConvert::Concatenate", 1161);
    v7 = (__int64 *)qword_1803CEF18;
    v8 = -2147467261;
    if ( !qword_1803CEF18 )
    {
      v9 = MFGetCallStackTracingWeakReference(v5, v4, v6);
      qword_1803CEF18 = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v7 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = sub_1800402C0(v7, v4, v6);
      if ( *(_DWORD *)(v10 + 1996) != -2147467261 )
        sub_1800EC0E0(v10, "CMFPropVariantConvert::Concatenate", 1161, 2147500035LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_164;
    v11 = 73;
LABEL_163:
    sub_180050D6C(*((_QWORD *)RequestContext + 2), v11, qword_18035FAF0, 0, v8);
LABEL_164:
    p_cb = (SIZE_T *)&v94;
    goto LABEL_165;
  }
  v12 = *(_WORD *)pvarSrc;
  if ( *(_WORD *)pvarSrc && *(_WORD *)pvar && ((v12 ^ *(_WORD *)pvar) & 0xFFF) != 0 )
  {
    sub_18002FEE0(&v94, "CMFPropVariantConvert::Concatenate", 1168);
    v16 = (__int64 *)qword_1803CEF18;
    v8 = -1072875801;
    if ( !qword_1803CEF18 )
    {
      v17 = MFGetCallStackTracingWeakReference(v14, v13, v15);
      qword_1803CEF18 = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v16 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = sub_1800402C0(v16, v13, v15);
      if ( *(_DWORD *)(v18 + 1996) != -1072875801 )
        sub_1800EC0E0(v18, "CMFPropVariantConvert::Concatenate", 1168, 3222091495LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_164;
    v11 = 74;
    goto LABEL_163;
  }
  v19 = *(_WORD *)pvar;
  if ( (*(_WORD *)pvar & 0xFFF) == 0xE || (v12 & 0xFFF) == 0xE )
  {
    sub_18002FEE0(&v94, "CMFPropVariantConvert::Concatenate", 1174);
    v80 = (__int64 *)qword_1803CEF18;
    v8 = -1072875800;
    if ( !qword_1803CEF18 )
    {
      v81 = MFGetCallStackTracingWeakReference(v78, v77, v79);
      qword_1803CEF18 = v81;
      if ( v81 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
      {
        v80 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v80 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v80 + 8) )
    {
      v82 = sub_1800402C0(v80, v77, v79);
      if ( *(_DWORD *)(v82 + 1996) != -1072875800 )
        sub_1800EC0E0(v82, "CMFPropVariantConvert::Concatenate", 1174, 3222091496LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_164;
    v11 = 75;
    goto LABEL_163;
  }
  v20 = 1;
  if ( v19 )
  {
    v21 = 1;
    if ( (v19 & 0x1000) != 0 )
      v21 = *((_DWORD *)pvar + 2);
  }
  else
  {
    v21 = 0;
  }
  if ( v12 )
  {
    v22 = 1;
    if ( (v12 & 0x1000) != 0 )
      v22 = *((_DWORD *)pvarSrc + 2);
    v8 = sub_1801C1658(pvar, &v96, 4096, 4095);
    sub_18002FEE0(&cb, "CMFPropVariantConvert::Concatenate", 1210);
    if ( v8 < 0 )
    {
      v26 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v27 = MFGetCallStackTracingWeakReference(v24, v23, v25);
        qword_1803CEF18 = v27;
        if ( v27
          && (*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v27 + 8LL))(
               v27,
               2032,
               v25,
               0) )
        {
          v26 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v26 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = sub_1800402C0(v26, v23, v25);
        if ( *(_DWORD *)(v28 + 1996) != v8 )
          sub_1800EC0E0(v28, "CMFPropVariantConvert::Concatenate", 1210, (unsigned int)v8);
      }
      if ( byte_1803CECE8 )
      {
        v29 = 76;
LABEL_46:
        sub_180050D6C(*((_QWORD *)RequestContext + 2), v29, qword_18035FAF0, 0, v8);
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    if ( !v21 && v22 == 1 )
    {
      v31 = *(unsigned __int16 *)pvarSrc;
      if ( (v31 & 0x1000) != 0 )
      {
        LOWORD(v31) = v31 & 0xFFF;
        if ( (unsigned __int16)v31 > 0x1Fu || (v32 = -1073732864, !_bittest(&v32, v31)) )
          v20 = 0;
        v33 = pvarSrc[2];
        if ( v20 )
          v33 = *(_OWORD **)v33;
        v34 = sub_1801DAE40(pvar, v31, v33, v96);
      }
      else
      {
        v34 = sub_18019D300(pvar, pvarSrc);
      }
      v8 = v34;
      goto LABEL_47;
    }
    if ( v22 + v21 < v21 )
    {
      v74 = (__int64 *)qword_1803CEF18;
      v8 = -2147024362;
      if ( !qword_1803CEF18 )
      {
        v75 = MFGetCallStackTracingWeakReference(v24, v23, v25);
        qword_1803CEF18 = v75;
        if ( v75
          && (*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v75 + 8LL))(
               v75,
               2032,
               v25,
               0) )
        {
          v74 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v74 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v74 + 8) )
      {
        v76 = sub_1800402C0(v74, v23, v25);
        if ( *(_DWORD *)(v76 + 1996) != -2147024362 )
          sub_1800EC0E0(v76, "CMFPropVariantConvert::Concatenate", 1263, 2147942934LL);
      }
      if ( byte_1803CECE8 )
      {
        v29 = 77;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    LODWORD(cb) = v22 + v21;
    v8 = sub_180111D68(v96 * (unsigned __int64)(v22 + v21), (int *)&cb);
    if ( v8 < 0 )
    {
      v39 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v40 = MFGetCallStackTracingWeakReference(v36, v35, v37);
        v38 = 0;
        qword_1803CEF18 = v40;
        if ( v40
          && (v41 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v40 + 8LL))(
                      v40,
                      2032,
                      v37,
                      0),
              v38 = 0,
              v41) )
        {
          v39 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v39 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v39 + 8) != v38 )
      {
        v42 = sub_1800402C0(v39, v35, v37);
        if ( *(_DWORD *)(v42 + 1996) != v8 )
          sub_1800EC0E0(v42, "CMFPropVariantConvert::Concatenate", 1264, (unsigned int)v8);
      }
      if ( byte_1803CECE8 )
      {
        v29 = 78;
        goto LABEL_46;
      }
LABEL_47:
      p_cb = &cb;
LABEL_165:
      sub_18003ECB0(p_cb);
      goto LABEL_166;
    }
    v89 = (unsigned int *)CoTaskMemAlloc((unsigned int)cb);
    if ( !v89 )
    {
      v46 = (__int64 *)qword_1803CEF18;
      v8 = -2147024882;
      if ( !qword_1803CEF18 )
      {
        v47 = MFGetCallStackTracingWeakReference(v44, v43, v45);
        qword_1803CEF18 = v47;
        if ( v47 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        {
          v46 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v46 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v48 = sub_1800402C0(v46, v43, v45);
        if ( *(_DWORD *)(v48 + 1996) != -2147024882 )
          sub_1800EC0E0(v48, "CMFPropVariantConvert::Concatenate", 1266, 2147942414LL);
      }
      if ( byte_1803CECE8 )
        sub_180050D6C(*((_QWORD *)RequestContext + 2), 79, qword_18035FAF0, 0, -2147024882);
      goto LABEL_47;
    }
    v49 = *(_WORD *)pvar;
    v90[0] = v21;
    v86 = pvar + 1;
    if ( (v49 & 0x1000) != 0 )
    {
      v50 = (PROPVARIANT *)pvar[2];
    }
    else
    {
      v50 = pvar + 1;
      v86 = pvar + 1;
    }
    v51 = pvarSrc + 1;
    v52 = *(_WORD *)pvarSrc & 0x1000;
    v91 = v50;
    v92 = v22;
    if ( v52 )
      v51 = (PROPVARIANT *)pvarSrc[2];
    else
      v86 = pvar + 1;
    v53 = 0;
    v93 = v51;
    LODWORD(cb) = 0;
    v54 = v89;
    v85 = v89;
    while ( 1 )
    {
      v97 = 0;
      v55 = (&v91)[2 * (int)v53];
      v84 = v90[4 * v53];
      if ( v84 )
        break;
LABEL_141:
      LODWORD(cb) = ++v53;
      if ( v53 >= 2 )
      {
        v73 = v94;
        *(_OWORD *)v94 = 0;
        v73[2] = 0;
        *(_WORD *)v73 = *(_WORD *)pvarSrc | 0x1000;
        *(_DWORD *)v86 = v22 + v21;
        v73[2] = v89;
        goto LABEL_47;
      }
    }
    v56 = v96;
    while ( 1 )
    {
      if ( !v53 )
      {
        v57 = v56;
        goto LABEL_93;
      }
      v60 = 0;
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 8 )
        goto LABEL_114;
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x1E )
      {
        v68 = -1;
        do
          ++v68;
        while ( *((_BYTE *)*v55 + v68) );
        v60 = v68 + 1;
        goto LABEL_100;
      }
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x1F )
      {
LABEL_114:
        v69 = -1;
        do
          ++v69;
        while ( *((_WORD *)*v55 + v69) );
        v60 = 2 * v69 + 2;
      }
      else
      {
        if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x41 )
        {
          v60 = *(_DWORD *)v55;
          goto LABEL_106;
        }
        if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x48 )
        {
          v60 = 16;
LABEL_100:
          Size = v60;
          v61 = (unsigned int *)CoTaskMemAlloc(v60);
          *(_QWORD *)v85 = v61;
          if ( v61 )
          {
            v57 = Size;
            v58 = *v55;
            goto LABEL_138;
          }
          v63 = (__int64 *)qword_1803CEF18;
          v8 = -2147024882;
          if ( !qword_1803CEF18 )
          {
            v64 = MFGetCallStackTracingWeakReference(0, 0, v62);
            qword_1803CEF18 = v64;
            if ( v64 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
            {
              v63 = (__int64 *)qword_1803CEF18;
            }
            else
            {
              v63 = &qword_1803CE250;
              qword_1803CEF18 = (__int64)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v63 + 8) )
          {
            v72 = sub_1800402C0(v63, 0, v62);
            if ( *(_DWORD *)(v72 + 1996) != -2147024882 )
              sub_1800EC0E0(v72, "CMFPropVariantConvert::Concatenate", 1328, 2147942414LL);
          }
          if ( !byte_1803CECE8 )
            goto LABEL_140;
          v71 = 80;
          goto LABEL_136;
        }
      }
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 8
        || (*(_WORD *)pvarSrc & 0xFFF) == 0x1E
        || (*(_WORD *)pvarSrc & 0xFFF) == 0x1F )
      {
        goto LABEL_100;
      }
      if ( (*(_WORD *)pvarSrc & 0xFFF) != 0x41 )
      {
        if ( (*(_WORD *)pvarSrc & 0xFFF) != 0x48 )
        {
          v57 = v96;
LABEL_93:
          v58 = v55;
          v59 = v54;
LABEL_139:
          memcpy(v59, v58, v57);
          goto LABEL_140;
        }
        goto LABEL_100;
      }
LABEL_106:
      Sizea = v60;
      *v54 = v60;
      v61 = (unsigned int *)CoTaskMemAlloc(v60);
      *((_QWORD *)v85 + 1) = v61;
      if ( v61 )
      {
        v57 = Sizea;
        v58 = v55[1];
LABEL_138:
        v59 = v61;
        goto LABEL_139;
      }
      v66 = (__int64 *)qword_1803CEF18;
      v8 = -2147024882;
      if ( !qword_1803CEF18 )
      {
        v67 = MFGetCallStackTracingWeakReference(0, 0, v65);
        qword_1803CEF18 = v67;
        if ( v67 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
        {
          v66 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v66 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v66 + 8) )
      {
        v70 = sub_1800402C0(v66, 0, v65);
        if ( *(_DWORD *)(v70 + 1996) != -2147024882 )
          sub_1800EC0E0(v70, "CMFPropVariantConvert::Concatenate", 1335, 2147942414LL);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_140;
      v71 = 81;
LABEL_136:
      sub_180050D6C(*((_QWORD *)RequestContext + 2), v71, qword_18035FAF0, 0, -2147024882);
LABEL_140:
      v56 = v96;
      v55 = (PROPVARIANT *)((char *)v55 + v96);
      v54 = (unsigned int *)((char *)v85 + v96);
      v53 = cb;
      v85 = v54;
      if ( v84 <= ++v97 )
        goto LABEL_141;
    }
  }
  v8 = 0;
LABEL_166:
  CoTaskMemFree(0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18021cf40  mov     [rsp-8+arg_0], rcx
0x18021cf45  push    rbp
0x18021cf46  push    rbx
0x18021cf47  push    rsi
0x18021cf48  push    rdi
0x18021cf49  push    r12
0x18021cf4b  push    r13
0x18021cf4d  push    r14
0x18021cf4f  push    r15
0x18021cf51  lea     rbp, [rsp-1Fh]
0x18021cf56  sub     rsp, 88h
0x18021cf5d  xor     r12d, r12d
0x18021cf60  mov     r13, rdx
0x18021cf63  mov     [rbp+57h+arg_10], r12d
0x18021cf67  mov     r15, rcx
0x18021cf6a  cmp     rcx, rdx
0x18021cf6d  jnz     loc_18021D028
0x18021cf73  mov     esi, 489h
0x18021cf78  lea     r14, aCmfpropvariant_10; "CMFPropVariantConvert::Concatenate"
0x18021cf7f  mov     r8d, esi
0x18021cf82  lea     rcx, [rbp+57h+arg_0]
0x18021cf86  mov     rdx, r14
0x18021cf89  call    sub_18002FEE0
0x18021cf8e  mov     rbx, cs:qword_1803CEF18
0x18021cf95  mov     edi, 80004003h
0x18021cf9a  test    rbx, rbx
0x18021cf9d  jnz     short loc_18021CFE7
0x18021cf9f  call    cs:MFGetCallStackTracingWeakReference
0x18021cfa6  nop     dword ptr [rax+rax+00h]
0x18021cfab  mov     cs:qword_1803CEF18, rax
0x18021cfb2  mov     rcx, rax
0x18021cfb5  test    rax, rax
0x18021cfb8  jz      short loc_18021CFD9
0x18021cfba  mov     rax, [rax]
0x18021cfbd  mov     edx, 7F0h
0x18021cfc2  mov     rax, [rax+8]
0x18021cfc6  call    cs:__guard_dispatch_icall_fptr
0x18021cfcc  test    eax, eax
0x18021cfce  jz      short loc_18021CFD9
0x18021cfd0  mov     rbx, cs:qword_1803CEF18
0x18021cfd7  jmp     short loc_18021CFE7
0x18021cfd9  lea     rbx, qword_1803CE250
0x18021cfe0  mov     cs:qword_1803CEF18, rbx
0x18021cfe7  cmp     [rbx+8], r12b
0x18021cfeb  jz      short loc_18021D00E
0x18021cfed  mov     rcx, rbx
0x18021cff0  call    sub_1800402C0
0x18021cff5  cmp     [rax+7CCh], edi
0x18021cffb  jz      short loc_18021D00E
0x18021cffd  mov     r9d, edi
0x18021d000  mov     r8d, esi
0x18021d003  mov     rdx, r14
0x18021d006  mov     rcx, rax
0x18021d009  call    sub_1800EC0E0
0x18021d00e  mov     esi, 1
0x18021d013  cmp     cs:byte_1803CECE8, sil
0x18021d01a  jb      loc_18021D947
0x18021d020  lea     edx, [rsi+48h]
0x18021d023  jmp     loc_18021D929
0x18021d028  movzx   ecx, word ptr [rdx]
0x18021d02b  mov     r9d, 0FFFh
0x18021d031  cmp     r12w, cx
0x18021d035  jz      loc_18021D10B
0x18021d03b  movzx   edx, word ptr [r15]
0x18021d03f  cmp     r12w, dx
0x18021d043  jz      loc_18021D10B
0x18021d049  xor     dx, cx
0x18021d04c  test    r9w, dx
0x18021d050  jz      loc_18021D10B
0x18021d056  mov     esi, 490h
0x18021d05b  lea     r14, aCmfpropvariant_10; "CMFPropVariantConvert::Concatenate"
0x18021d062  mov     r8d, esi
0x18021d065  lea     rcx, [rbp+57h+arg_0]
0x18021d069  mov     rdx, r14
0x18021d06c  call    sub_18002FEE0
0x18021d071  mov     rbx, cs:qword_1803CEF18
0x18021d078  mov     edi, 0C00D36E7h
0x18021d07d  test    rbx, rbx
0x18021d080  jnz     short loc_18021D0CA
0x18021d082  call    cs:MFGetCallStackTracingWeakReference
0x18021d089  nop     dword ptr [rax+rax+00h]
0x18021d08e  mov     cs:qword_1803CEF18, rax
0x18021d095  mov     rcx, rax
0x18021d098  test    rax, rax
0x18021d09b  jz      short loc_18021D0BC
0x18021d09d  mov     rax, [rax]
0x18021d0a0  mov     edx, 7F0h
0x18021d0a5  mov     rax, [rax+8]
0x18021d0a9  call    cs:__guard_dispatch_icall_fptr
0x18021d0af  test    eax, eax
0x18021d0b1  jz      short loc_18021D0BC
0x18021d0b3  mov     rbx, cs:qword_1803CEF18
0x18021d0ba  jmp     short loc_18021D0CA
0x18021d0bc  lea     rbx, qword_1803CE250
0x18021d0c3  mov     cs:qword_1803CEF18, rbx
0x18021d0ca  cmp     [rbx+8], r12b
0x18021d0ce  jz      short loc_18021D0F1
0x18021d0d0  mov     rcx, rbx
0x18021d0d3  call    sub_1800402C0
0x18021d0d8  cmp     [rax+7CCh], edi
0x18021d0de  jz      short loc_18021D0F1
0x18021d0e0  mov     r9d, edi
0x18021d0e3  mov     r8d, esi
0x18021d0e6  mov     rdx, r14
0x18021d0e9  mov     rcx, rax
0x18021d0ec  call    sub_1800EC0E0
0x18021d0f1  mov     esi, 1
0x18021d0f6  cmp     cs:byte_1803CECE8, sil
0x18021d0fd  jb      loc_18021D947
0x18021d103  lea     edx, [rsi+49h]
0x18021d106  jmp     loc_18021D929
0x18021d10b  movzx   edx, word ptr [r15]
0x18021d10f  mov     r8d, 0Eh
0x18021d115  movzx   eax, dx
0x18021d118  and     ax, r9w
0x18021d11c  cmp     r8w, ax
0x18021d120  jz      loc_18021D87D
0x18021d126  movzx   eax, cx
0x18021d129  and     ax, r9w
0x18021d12d  cmp     r8w, ax
0x18021d131  jz      loc_18021D87D
0x18021d137  lea     esi, [r8-0Dh]
0x18021d13b  mov     r8d, 1000h
0x18021d141  cmp     r12w, dx
0x18021d145  jnz     short loc_18021D14C
0x18021d147  mov     ebx, r12d
0x18021d14a  jmp     short loc_18021D15C
0x18021d14c  and     dx, r8w
0x18021d150  mov     ebx, esi
0x18021d152  cmp     r12w, dx
0x18021d156  jz      short loc_18021D15C
0x18021d158  mov     ebx, [r15+8]
0x18021d15c  cmp     r12w, cx
0x18021d160  jnz     short loc_18021D16A
0x18021d162  mov     edi, r12d
0x18021d165  jmp     loc_18021D950
0x18021d16a  and     cx, r8w
0x18021d16e  xor     eax, eax
0x18021d170  mov     r12d, esi
0x18021d173  cmp     ax, cx
0x18021d176  jz      short loc_18021D17C
0x18021d178  mov     r12d, [r13+8]
0x18021d17c  lea     rdx, [rbp+57h+arg_10]
0x18021d180  mov     rcx, r15
0x18021d183  call    sub_1801C1658
0x18021d188  lea     r14, aCmfpropvariant_10; "CMFPropVariantConvert::Concatenate"
0x18021d18f  mov     r8d, 4BAh
0x18021d195  mov     rdx, r14
0x18021d198  lea     rcx, [rbp+57h+cb]
0x18021d19c  mov     edi, eax
0x18021d19e  call    sub_18002FEE0
0x18021d1a3  xor     r9d, r9d
0x18021d1a6  test    edi, edi
0x18021d1a8  jns     loc_18021D267
0x18021d1ae  mov     rbx, cs:qword_1803CEF18
0x18021d1b5  test    rbx, rbx
0x18021d1b8  jnz     short loc_18021D208
0x18021d1ba  call    cs:MFGetCallStackTracingWeakReference
0x18021d1c1  nop     dword ptr [rax+rax+00h]
0x18021d1c6  xor     r9d, r9d
0x18021d1c9  mov     cs:qword_1803CEF18, rax
0x18021d1d0  mov     rcx, rax
0x18021d1d3  test    rax, rax
0x18021d1d6  jz      short loc_18021D1FA
0x18021d1d8  mov     rax, [rax]
0x18021d1db  mov     edx, 7F0h
0x18021d1e0  mov     rax, [rax+8]
0x18021d1e4  call    cs:__guard_dispatch_icall_fptr
0x18021d1ea  xor     r9d, r9d
0x18021d1ed  test    eax, eax
0x18021d1ef  jz      short loc_18021D1FA
0x18021d1f1  mov     rbx, cs:qword_1803CEF18
0x18021d1f8  jmp     short loc_18021D208
0x18021d1fa  lea     rbx, qword_1803CE250
0x18021d201  mov     cs:qword_1803CEF18, rbx
0x18021d208  cmp     [rbx+8], r9b
0x18021d20c  jz      short loc_18021D232
0x18021d20e  mov     rcx, rbx
0x18021d211  call    sub_1800402C0
0x18021d216  cmp     [rax+7CCh], edi
0x18021d21c  jz      short loc_18021D232
0x18021d21e  mov     r9d, edi
0x18021d221  mov     r8d, 4BAh
0x18021d227  mov     rdx, r14
0x18021d22a  mov     rcx, rax
0x18021d22d  call    sub_1800EC0E0
0x18021d232  cmp     cs:byte_1803CECE8, sil
0x18021d239  jb      short loc_18021D25E
0x18021d23b  mov     edx, 4Ch ; 'L'
0x18021d240  mov     [rsp+0C0h+var_A0], edi
0x18021d244  mov     rcx, cs:RequestContext
0x18021d24b  lea     r8, qword_18035FAF0
0x18021d252  xor     r9d, r9d
0x18021d255  mov     rcx, [rcx+10h]
0x18021d259  call    sub_180050D6C
0x18021d25e  lea     rcx, [rbp+57h+cb]
0x18021d262  jmp     loc_18021D94B
0x18021d267  test    ebx, ebx
0x18021d269  jnz     short loc_18021D2CC
0x18021d26b  cmp     r12d, esi
0x18021d26e  jnz     short loc_18021D2CC
0x18021d270  movzx   edx, word ptr [r13+0]
0x18021d275  mov     r8d, 1000h
0x18021d27b  movzx   ecx, dx
0x18021d27e  and     cx, r8w
0x18021d282  cmp     r9w, cx
0x18021d286  jz      short loc_18021D2BD
0x18021d288  lea     eax, [r8-1]
0x18021d28c  and     dx, ax
0x18021d28f  cmp     dx, 1Fh
0x18021d293  ja      short loc_18021D2A1
0x18021d295  mov     r8d, 0C0002300h
0x18021d29b  bt      r8d, edx
0x18021d29f  jb      short loc_18021D2A4
0x18021d2a1  mov     esi, r9d
0x18021d2a4  mov     r8, [r13+10h]
0x18021d2a8  mov     rcx, r15; pvar
0x18021d2ab  mov     r9d, [rbp+57h+arg_10]
0x18021d2af  test    esi, esi
0x18021d2b1  jz      short loc_18021D2B6
0x18021d2b3  mov     r8, [r8]
0x18021d2b6  call    sub_1801DAE40
0x18021d2bb  jmp     short loc_18021D2C8
0x18021d2bd  mov     rdx, r13; pvarSrc
0x18021d2c0  mov     rcx, r15; pvarDest
0x18021d2c3  call    sub_18019D300
0x18021d2c8  mov     edi, eax
0x18021d2ca  jmp     short loc_18021D25E
0x18021d2cc  lea     eax, [r12+rbx]
0x18021d2d0  mov     [rbp+57h+var_8C], eax
0x18021d2d3  cmp     eax, ebx
0x18021d2d5  jb      loc_18021D7DD
0x18021d2db  mov     edx, [rbp+57h+arg_10]
0x18021d2de  mov     ecx, eax
0x18021d2e0  imul    rcx, rdx
0x18021d2e4  lea     rdx, [rbp+57h+cb]
0x18021d2e8  mov     dword ptr [rbp+57h+cb], eax
0x18021d2eb  call    sub_180111D68
0x18021d2f0  mov     edi, eax
0x18021d2f2  test    eax, eax
0x18021d2f4  jns     loc_18021D395
0x18021d2fa  mov     rbx, cs:qword_1803CEF18
0x18021d301  test    rbx, rbx
0x18021d304  jnz     short loc_18021D354
0x18021d306  call    cs:MFGetCallStackTracingWeakReference
0x18021d30d  nop     dword ptr [rax+rax+00h]
0x18021d312  xor     r9d, r9d
0x18021d315  mov     cs:qword_1803CEF18, rax
0x18021d31c  mov     rcx, rax
0x18021d31f  test    rax, rax
0x18021d322  jz      short loc_18021D346
0x18021d324  mov     rax, [rax]
0x18021d327  mov     edx, 7F0h
0x18021d32c  mov     rax, [rax+8]
0x18021d330  call    cs:__guard_dispatch_icall_fptr
0x18021d336  xor     r9d, r9d
0x18021d339  test    eax, eax
0x18021d33b  jz      short loc_18021D346
0x18021d33d  mov     rbx, cs:qword_1803CEF18
0x18021d344  jmp     short loc_18021D354
0x18021d346  lea     rbx, qword_1803CE250
0x18021d34d  mov     cs:qword_1803CEF18, rbx
0x18021d354  cmp     [rbx+8], r9b
0x18021d358  jz      short loc_18021D37E
0x18021d35a  mov     rcx, rbx
0x18021d35d  call    sub_1800402C0
0x18021d362  cmp     [rax+7CCh], edi
0x18021d368  jz      short loc_18021D37E
0x18021d36a  mov     r9d, edi
0x18021d36d  mov     r8d, 4F0h
0x18021d373  mov     rdx, r14
0x18021d376  mov     rcx, rax
0x18021d379  call    sub_1800EC0E0
0x18021d37e  cmp     cs:byte_1803CECE8, sil
0x18021d385  jb      loc_18021D25E
0x18021d38b  mov     edx, 4Eh ; 'N'
0x18021d390  jmp     loc_18021D240
0x18021d395  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18021d398  call    cs:CoTaskMemAlloc
0x18021d39f  nop     dword ptr [rax+rax+00h]
0x18021d3a4  xor     r11d, r11d
0x18021d3a7  mov     [rbp+57h+var_70], rax
0x18021d3ab  mov     r10, rax
0x18021d3ae  test    rax, rax
0x18021d3b1  jnz     loc_18021D461
0x18021d3b7  mov     rbx, cs:qword_1803CEF18
0x18021d3be  mov     r12d, 8007000Eh
0x18021d3c4  mov     edi, r12d
0x18021d3c7  test    rbx, rbx
0x18021d3ca  jnz     short loc_18021D41A
0x18021d3cc  call    cs:MFGetCallStackTracingWeakReference
0x18021d3d3  nop     dword ptr [rax+rax+00h]
0x18021d3d8  xor     r11d, r11d
0x18021d3db  mov     cs:qword_1803CEF18, rax
0x18021d3e2  mov     rcx, rax
0x18021d3e5  test    rax, rax
0x18021d3e8  jz      short loc_18021D40C
0x18021d3ea  mov     rax, [rax]
0x18021d3ed  mov     edx, 7F0h
0x18021d3f2  mov     rax, [rax+8]
  ... truncated ...
```
