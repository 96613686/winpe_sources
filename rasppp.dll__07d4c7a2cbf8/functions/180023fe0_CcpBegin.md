# CcpBegin

- ea: `0x180023fe0`
- end: `0x180024a64`
- name: `CcpBegin`
- size: `2692`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001aa34`
- `0x180023fe0`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002403d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002403d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002404e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002404e`

## string_xrefs

- `0x180024450`: `Send RCI_MacCompressionType = 0x%x`
- `0x180024497`: `Receive RCI_MacCompressionType = 0x%x`
- `0x1800245fb`: `Send Compression is Disabled`
- `0x18002474a`: `We do not want any compression or encryption on the local side`
- `0x1800248c1`: `Receive Compression is disabled`
- `0x18002498b`: `We do not want to receive any compression or encryption from the remote side`
- `0x1800249bf`: `ERROR_PROTOCOL_NOT_CONFIGURED`

## pseudocode

```c
DWORD __fastcall CcpBegin(char **a1, unsigned int *a2)
{
  unsigned int v2; // r14d
  char *v5; // rax
  char *v6; // rdi
  __int64 v8; // rcx
  int v9; // r15d
  unsigned int v10; // esi
  unsigned int v11; // edx
  __int64 VendorSpecific; // rax
  unsigned __int8 *v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rax
  char v16; // r8
  int v17; // eax
  __int64 v18; // rdx
  const wchar_t *v19; // r8
  const wchar_t *v20; // r8
  bool v21; // cf
  __int64 v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // ebx
  __int64 v26; // rdx
  char v27; // cl
  int v28; // r8d
  int *v29; // rbx
  int v30; // eax
  __int64 v31; // r8
  const wchar_t *v32; // rdx
  __int64 v33; // r8
  _OWORD *v34; // rcx
  _OWORD *v35; // rax
  __int64 v36; // r9
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  int v50; // eax
  bool v51; // zf
  int v52; // ecx
  int v53; // r9d
  int v54; // eax
  char v55; // r8
  __int64 v56; // r8
  const wchar_t *v57; // rdx
  bool v58; // zf
  __int64 v59; // rcx
  int v60; // eax
  int v61; // [rsp+20h] [rbp-E0h] BYREF
  char v62[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v2 = a2[11];
  v61 = 0;
  memset_0(v62, 0, sizeof(v62));
  v5 = (char *)LocalAlloc(0x40u, 0x5F0u);
  *a1 = v5;
  v6 = v5;
  if ( !v5 )
    return GetLastError();
  v8 = *a2;
  *((_DWORD *)v5 + 3) = v8;
  v9 = v2 & 0x80000;
  v10 = 0;
  *(_QWORD *)v5 = *((_QWORD *)a2 + 1);
  v11 = a2[4];
  *((_DWORD *)v5 + 2) = v11;
  *((_DWORD *)v5 + 4) = 0;
  *((_DWORD *)v5 + 5) = (v2 & 2) == 0;
  if ( (_DWORD)v8 )
  {
    if ( (unsigned __int16)v11 == 9 || (unsigned __int16)v11 == 14 )
    {
      v10 = 240;
      goto LABEL_24;
    }
    VendorSpecific = RasAuthAttributeGetVendorSpecific(v8, 7, *((_QWORD *)a2 + 145));
    if ( VendorSpecific )
    {
      v13 = *(unsigned __int8 **)(VendorSpecific + 8);
      if ( v13[9] + (v13[6] << 24) + (v13[8] << 8) + (v13[7] << 16) == 2 )
      {
        v14 = *((_QWORD *)&xmmword_18004C7A0 + 1);
        v9 = 0;
        *((_DWORD *)v6 + 4) = 1;
        if ( !v14 )
        {
LABEL_11:
          v15 = RasAuthAttributeGetVendorSpecific(v13, 8, *((_QWORD *)a2 + 145));
          if ( !v15 )
          {
            v10 = g_dwAllowPPTPWeakCrypto != 0 ? 240 : 64;
            goto LABEL_25;
          }
          v16 = *(_BYTE *)(*(_QWORD *)(v15 + 8) + 9LL);
          if ( g_dwAllowPPTPWeakCrypto )
          {
            v8 = (v16 & 2) != 0 ? 0x30 : 0;
            v17 = ((v16 & 2) != 0 ? 0x30 : 0) | 0x40;
            if ( (v16 & 4) == 0 )
              v17 = (v16 & 2) != 0 ? 0x30 : 0;
            v10 = v17 | 0x80;
            if ( (v16 & 8) == 0 )
              v10 = v17;
            if ( v10 )
            {
LABEL_25:
              if ( v14 )
              {
                LOWORD(v61) = 0;
                FormatRRASErrorString(&v61, L"EncryptionTypes: 0x%x", v10);
                v18 = *((_QWORD *)&xmmword_18004C7A0 + 1);
                v19 = (const wchar_t *)&v61;
LABEL_42:
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
                  gRasccpEtwContext,
                  v18,
                  v19);
                v14 = *((_QWORD *)&xmmword_18004C7A0 + 1);
                goto LABEL_43;
              }
              goto LABEL_43;
            }
          }
          else if ( (v16 & 4) != 0 )
          {
            v10 = 64;
            goto LABEL_25;
          }
          *((_DWORD *)v6 + 4) = 0;
          v9 = 1;
          if ( !v14 )
            goto LABEL_43;
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
            gRasccpEtwContext,
            v14,
            L"Will not force encryption: type not specified");
LABEL_24:
          v14 = *((_QWORD *)&xmmword_18004C7A0 + 1);
          goto LABEL_25;
        }
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v14,
          L"Will force encryption");
      }
    }
    v14 = *((_QWORD *)&xmmword_18004C7A0 + 1);
    goto LABEL_11;
  }
  if ( (v2 & 0x80u) == 0 )
    goto LABEL_34;
  v51 = g_dwAllowPPTPWeakCrypto == 0;
  v9 = 0;
  v14 = *((_QWORD *)&xmmword_18004C7A0 + 1);
  *((_DWORD *)v5 + 4) = 1;
  if ( v51 )
  {
    v10 = 64;
    if ( v14 )
    {
      v20 = L"Strong encryption";
      goto LABEL_33;
    }
  }
  else
  {
    v10 = 176;
    if ( v14 )
    {
      v20 = L"Encryption";
LABEL_33:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(gRasccpEtwContext, v14, v20);
LABEL_34:
      v14 = *((_QWORD *)&xmmword_18004C7A0 + 1);
    }
  }
  if ( (v2 & 0x1000) != 0 )
  {
    v10 |= 0x40u;
    *((_DWORD *)v6 + 4) = 1;
    v9 = 0;
    if ( v14 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        v14,
        L"Strong encryption");
      v14 = *((_QWORD *)&xmmword_18004C7A0 + 1);
    }
  }
  else if ( v9 )
  {
    goto LABEL_43;
  }
  if ( !v10 )
  {
    v9 = 0;
    v21 = g_dwAllowPPTPWeakCrypto != 0;
    *((_DWORD *)v6 + 4) = 0;
    v10 = v21 ? 240 : 64;
    if ( v14 )
    {
      v19 = L"Not disabling encryption; Not forcing encryption";
      v18 = v14;
      goto LABEL_42;
    }
  }
LABEL_43:
  v22 = *((_QWORD *)a2 + 145);
  if ( !RasAuthAttributeGetVendorSpecific(v8, 12, v22)
    && (!RasAuthAttributeGetVendorSpecific(v23, 16, v22) || !RasAuthAttributeGetVendorSpecific(v24, 17, v22)) )
  {
    if ( v14 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        v14,
        L"No MPPE keys were obtained");
    if ( *((_DWORD *)v6 + 4) )
      goto LABEL_108;
    v9 = 1;
    v21 = g_dwAllowPPTPWeakCrypto != 0;
    *((_DWORD *)v6 + 4) = 0;
    v10 = v21 ? 240 : 64;
  }
  v25 = ((__int64 (__fastcall *)(_QWORD, char *, char *))xmmword_18004C4A0)(*(_QWORD *)v6, v6 + 36, v6 + 780);
  if ( v25 )
  {
LABEL_138:
    LocalFree(v6);
    return v25;
  }
  v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
  if ( *((_QWORD *)&xmmword_18004C7A0 + 1) )
  {
    LOWORD(v61) = 0;
    FormatRRASErrorString(&v61, L"Send capabilites from NDISWAN = 0x%x", *((unsigned int *)v6 + 23));
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
      gRasccpEtwContext,
      *((_QWORD *)&xmmword_18004C7A0 + 1),
      &v61);
    v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
    if ( *((_QWORD *)&xmmword_18004C7A0 + 1) )
    {
      LOWORD(v61) = 0;
      FormatRRASErrorString(&v61, L"Receive capabilites from NDISWAN = 0x%x", *((unsigned int *)v6 + 209));
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        *((_QWORD *)&xmmword_18004C7A0 + 1),
        &v61);
      v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      if ( *((_QWORD *)&xmmword_18004C7A0 + 1) )
      {
        LOWORD(v61) = 0;
        FormatRRASErrorString(&v61, L"Send RCI_MacCompressionType = 0x%x", (unsigned __int8)v6[100]);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          *((_QWORD *)&xmmword_18004C7A0 + 1),
          &v61);
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
        if ( *((_QWORD *)&xmmword_18004C7A0 + 1) )
        {
          LOWORD(v61) = 0;
          FormatRRASErrorString(&v61, L"Receive RCI_MacCompressionType = 0x%x", (unsigned __int8)v6[844]);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
            gRasccpEtwContext,
            *((_QWORD *)&xmmword_18004C7A0 + 1),
            &v61);
          v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
        }
      }
    }
  }
  v27 = v6[100];
  if ( v27 == -2 )
  {
    v6[100] = -1;
    v27 = -1;
  }
  if ( v6[844] == -2 )
    v6[844] = -1;
  v28 = *((_DWORD *)v6 + 23);
  v29 = (int *)(v6 + 32);
  *((_DWORD *)v6 + 8) = 0;
  v30 = 0;
  if ( v28 )
  {
    v30 = 1;
    *v29 = 1;
  }
  if ( v27 != -1 )
  {
    if ( v27 )
      v30 |= 4u;
    else
      v30 |= 2u;
    *v29 = v30;
  }
  if ( !*((_DWORD *)v6 + 4) )
  {
LABEL_75:
    if ( *((_DWORD *)v6 + 5) )
    {
      *((_DWORD *)v6 + 23) &= ~1u;
      *v29 = v30 & 0xFFFFFFF9;
      if ( v26 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v26,
          L"Send Compression is Disabled");
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      }
    }
    if ( v9 )
    {
      *((_DWORD *)v6 + 23) &= 0xFFFFFF0F;
      if ( v26 )
      {
        v31 = v10;
        v32 = L"Send Encryption is Disabled 0x%x";
LABEL_84:
        LOWORD(v61) = 0;
        FormatRRASErrorString(&v61, v32, v31);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          *((_QWORD *)&xmmword_18004C7A0 + 1),
          &v61);
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      }
    }
    else if ( !*((_DWORD *)v6 + 4) )
    {
      v31 = v10 & *((_DWORD *)v6 + 23);
      *((_DWORD *)v6 + 23) = v31 | *((_DWORD *)v6 + 23) & 0xFFFFFF0F;
      if ( v26 )
      {
        v32 = L"Send Encryption is Allowed 0x%x";
        goto LABEL_84;
      }
    }
    v33 = 2;
    v34 = v6 + 404;
    v35 = v6 + 32;
    v36 = 128;
    do
    {
      v37 = v35[1];
      *v34 = *v35;
      v38 = v35[2];
      v34[1] = v37;
      v39 = v35[3];
      v34[2] = v38;
      v40 = v35[4];
      v34[3] = v39;
      v41 = v35[5];
      v34[4] = v40;
      v42 = v35[6];
      v34[5] = v41;
      v43 = v35[7];
      v35 += 8;
      v34[6] = v42;
      v34[7] = v43;
      v34 += 8;
      --v33;
    }
    while ( v33 );
    v51 = g_dwAllowPPTPWeakCrypto == 0;
    v44 = v35[1];
    *v34 = *v35;
    v45 = v35[2];
    v34[1] = v44;
    v46 = v35[3];
    v34[2] = v45;
    v47 = v35[4];
    v34[3] = v46;
    v48 = v35[5];
    v34[4] = v47;
    v49 = v35[6];
    v50 = *((_DWORD *)v35 + 28);
    v34[5] = v48;
    v34[6] = v49;
    *((_DWORD *)v34 + 28) = v50;
    if ( v51 )
      v51 = (v6[92] & 0x41) == 0;
    else
      v51 = (v6[92] & 0xF1) == 0;
    if ( v51 )
    {
      *v29 &= ~1u;
      if ( v26 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v26,
          L"We do not want any compression or encryption on the local side",
          128);
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      }
    }
    v52 = *((_DWORD *)v6 + 4);
    if ( !v52 )
    {
      *((_DWORD *)v6 + 116) &= 0xFFFFFF0F;
      if ( v26 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v26,
          L"We do not require encryption locally; we won't request for it",
          v36);
        v52 = *((_DWORD *)v6 + 4);
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      }
      else
      {
        v52 = 0;
      }
    }
    v53 = *((_DWORD *)v6 + 209);
    v54 = 0;
    *((_DWORD *)v6 + 194) = 0;
    if ( v53 )
    {
      v54 = 1;
      *((_DWORD *)v6 + 194) = 1;
    }
    v55 = v6[844];
    if ( v55 != -1 )
    {
      if ( v55 )
        v54 |= 4u;
      else
        v54 |= 2u;
      *((_DWORD *)v6 + 194) = v54;
    }
    if ( v52 )
    {
      if ( (v53 & v10) == 0 )
      {
        if ( v26 )
        {
          LOWORD(v61) = 0;
          FormatRRASErrorString(&v61, L"Encryption type(s) 0x%x not supported locally", v10);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
            gRasccpEtwContext,
            *((_QWORD *)&xmmword_18004C7A0 + 1),
            &v61);
        }
LABEL_108:
        v25 = 741;
        goto LABEL_138;
      }
      *((_DWORD *)v6 + 209) = v53 & (v10 | 0x1000001);
      if ( v26 )
      {
        LOWORD(v61) = 0;
        FormatRRASErrorString(&v61, L"Receive Encryption is Forced 0x%x", *((unsigned int *)v6 + 209));
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          *((_QWORD *)&xmmword_18004C7A0 + 1),
          &v61);
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      }
      *((_DWORD *)v6 + 194) &= 0xFFFFFFF9;
      v54 = *((_DWORD *)v6 + 194);
    }
    if ( *((_DWORD *)v6 + 5) )
    {
      *((_DWORD *)v6 + 209) &= ~1u;
      *((_DWORD *)v6 + 194) = v54 & 0xFFFFFFF9;
      if ( v26 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v26,
          L"Receive Compression is disabled");
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      }
    }
    if ( v9 )
    {
      *((_DWORD *)v6 + 209) &= 0xFFFFFF0F;
      if ( !v26 )
        goto LABEL_122;
      v56 = v10;
      v57 = L"Receive Encryption is Disabled 0x%x";
    }
    else
    {
      if ( *((_DWORD *)v6 + 4) )
        goto LABEL_122;
      v56 = v10 & *((_DWORD *)v6 + 209);
      *((_DWORD *)v6 + 209) = v56 | *((_DWORD *)v6 + 209) & 0xFFFFFF0F;
      if ( !v26 )
        goto LABEL_122;
      v57 = L"Receive Encryption is Allowed 0x%x";
    }
    LOWORD(v61) = 0;
    FormatRRASErrorString(&v61, v57, v56);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
      gRasccpEtwContext,
      *((_QWORD *)&xmmword_18004C7A0 + 1),
      &v61);
    v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
LABEL_122:
    if ( g_dwAllowPPTPWeakCrypto )
      v58 = (v6[836] & 0xF1) == 0;
    else
      v58 = (v6[836] & 0x41) == 0;
    if ( v58 )
    {
      *((_DWORD *)v6 + 194) &= ~1u;
      if ( v26 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v26,
          L"We do not want to receive any compression or encryption from the remote side");
        v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
      }
    }
    if ( *((_DWORD *)v6 + 194) || *v29 )
    {
      if ( !*((_DWORD *)v6 + 4) )
        return 0;
      if ( v26 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v26,
          L"ForceEncryption");
      v59 = *(_QWORD *)v6;
      *((_DWORD *)v6 + 35) = 1;
      *((_DWORD *)v6 + 221) = 1;
      v60 = (*((__int64 (__fastcall **)(__int64, char *, char *))&xmmword_18004C490 + 1))(v59, v6 + 36, v6 + 780);
      if ( !v60 )
        return 0;
      v25 = v60;
    }
    else
    {
      if ( v26 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v26,
          L"ERROR_PROTOCOL_NOT_CONFIGURED");
      v25 = 731;
    }
    goto LABEL_138;
  }
  if ( (v28 & v10) != 0 )
  {
    *((_DWORD *)v6 + 23) = v28 & (v10 | 0x1000001);
    if ( v26 )
    {
      LOWORD(v61) = 0;
      FormatRRASErrorString(&v61, L"Send Encryption is Forced 0x%x", *((unsigned int *)v6 + 23));
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        *((_QWORD *)&xmmword_18004C7A0 + 1),
        &v61);
      v26 = *((_QWORD *)&xmmword_18004C7A0 + 1);
    }
    *v29 &= 0xFFFFFFF9;
    v30 = *v29;
    goto LABEL_75;
  }
  LocalFree(v6);
  if ( *((_QWORD *)&xmmword_18004C7A0 + 1) )
  {
    LOWORD(v61) = 0;
    FormatRRASErrorString(&v61, L"Encryption type(s) 0x%x not supported locally", v10);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
      gRasccpEtwContext,
      *((_QWORD *)&xmmword_18004C7A0 + 1),
      &v61);
  }
  return 741;
}

```

## disassembly

```asm
0x180023fe0  mov     [rsp-8+arg_10], rbx
0x180023fe5  push    rbp
0x180023fe6  push    rsi
0x180023fe7  push    rdi
0x180023fe8  push    r12
0x180023fea  push    r13
0x180023fec  push    r14
0x180023fee  push    r15
0x180023ff0  lea     rbp, [rsp-730h]
0x180023ff8  sub     rsp, 830h
0x180023fff  mov     rax, cs:__security_cookie
0x180024006  xor     rax, rsp
0x180024009  mov     [rbp+760h+var_40], rax
0x180024010  mov     r14d, [rdx+2Ch]
0x180024014  mov     r12, rdx
0x180024017  mov     rbx, rcx
0x18002401a  xor     r13d, r13d
0x18002401d  xor     edx, edx; Val
0x18002401f  mov     [rsp+860h+var_840], r13d
0x180024024  lea     rcx, [rsp+860h+var_83C]; void *
0x180024029  mov     r8d, 7FCh; Size
0x18002402f  call    memset_0
0x180024034  mov     edx, 5F0h; uBytes
0x180024039  lea     ecx, [r13+40h]; uFlags
0x18002403d  call    cs:__imp_LocalAlloc
0x180024043  mov     [rbx], rax
0x180024046  mov     rdi, rax
0x180024049  test    rax, rax
0x18002404c  jnz     short loc_180024059
0x18002404e  call    cs:__imp_GetLastError
0x180024054  jmp     loc_180024A3A
0x180024059  mov     ecx, [r12]
0x18002405d  mov     r15d, r14d
0x180024060  mov     [rax+0Ch], ecx
0x180024063  and     r15d, 80000h
0x18002406a  mov     rax, [r12+8]
0x18002406f  mov     esi, r13d
0x180024072  mov     [rdi], rax
0x180024075  mov     eax, r14d
0x180024078  mov     edx, [r12+10h]
0x18002407d  shr     eax, 1
0x18002407f  not     eax
0x180024081  mov     [rdi+8], edx
0x180024084  and     eax, 1
0x180024087  mov     [rdi+10h], r13d
0x18002408b  mov     [rdi+14h], eax
0x18002408e  test    ecx, ecx
0x180024090  jz      loc_18002420C
0x180024096  movzx   eax, dx
0x180024099  cmp     eax, 9
0x18002409c  jz      loc_1800241CC
0x1800240a2  cmp     eax, 0Eh
0x1800240a5  jz      loc_1800241CC
0x1800240ab  mov     r8, [r12+488h]
0x1800240b3  mov     edx, 7
0x1800240b8  call    RasAuthAttributeGetVendorSpecific
0x1800240bd  test    rax, rax
0x1800240c0  jz      short loc_18002411D
0x1800240c2  mov     rcx, [rax+8]
0x1800240c6  movzx   edx, byte ptr [rcx+7]
0x1800240ca  movzx   eax, byte ptr [rcx+8]
0x1800240ce  shl     eax, 8
0x1800240d1  shl     edx, 10h
0x1800240d4  add     edx, eax
0x1800240d6  movzx   eax, byte ptr [rcx+6]
0x1800240da  shl     eax, 18h
0x1800240dd  add     edx, eax
0x1800240df  movzx   eax, byte ptr [rcx+9]
0x1800240e3  add     edx, eax
0x1800240e5  cmp     edx, 2
0x1800240e8  jnz     short loc_18002411D
0x1800240ea  mov     rbx, qword ptr cs:xmmword_18004C7A0+8
0x1800240f1  mov     r15d, r13d
0x1800240f4  mov     dword ptr [rdi+10h], 1
0x1800240fb  test    rbx, rbx
0x1800240fe  jz      short loc_180024124
0x180024100  mov     rcx, cs:gRasccpEtwContext
0x180024107  lea     r8, aWillForceEncry; "Will force encryption"
0x18002410e  mov     rax, cs:gRasccpTemplateFunc
0x180024115  mov     rdx, rbx
0x180024118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002411d  mov     rbx, qword ptr cs:xmmword_18004C7A0+8
0x180024124  mov     r8, [r12+488h]
0x18002412c  mov     edx, 8
0x180024131  call    RasAuthAttributeGetVendorSpecific
0x180024136  test    rax, rax
0x180024139  jz      short loc_1800241B7
0x18002413b  mov     rax, [rax+8]
0x18002413f  movzx   r8d, byte ptr [rax+9]
0x180024144  mov     edx, r8d
0x180024147  and     edx, 4
0x18002414a  cmp     cs:g_dwAllowPPTPWeakCrypto, r13d
0x180024151  jz      short loc_1800241AC
0x180024153  mov     eax, r8d
0x180024156  and     al, 2
0x180024158  neg     al
0x18002415a  sbb     ecx, ecx
0x18002415c  and     ecx, 30h
0x18002415f  mov     eax, ecx
0x180024161  or      eax, 40h
0x180024164  test    edx, edx
0x180024166  cmovz   eax, ecx
0x180024169  mov     esi, eax
0x18002416b  bts     esi, 7
0x18002416f  test    r8b, 8
0x180024173  cmovz   esi, eax
0x180024176  test    esi, esi
0x180024178  jnz     short loc_1800241D8
0x18002417a  mov     [rdi+10h], r13d
0x18002417e  mov     r15d, 1
0x180024184  test    rbx, rbx
0x180024187  jz      loc_1800242F7
0x18002418d  mov     rcx, cs:gRasccpEtwContext
0x180024194  lea     r8, aWillNotForceEn; "Will not force encryption: type not spe"...
0x18002419b  mov     rax, cs:gRasccpTemplateFunc
0x1800241a2  mov     rdx, rbx
0x1800241a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241aa  jmp     short loc_1800241D1
0x1800241ac  test    edx, edx
0x1800241ae  jz      short loc_18002417A
0x1800241b0  mov     esi, 40h ; '@'
0x1800241b5  jmp     short loc_1800241D8
0x1800241b7  mov     eax, cs:g_dwAllowPPTPWeakCrypto
0x1800241bd  neg     eax
0x1800241bf  sbb     esi, esi
0x1800241c1  and     esi, 0B0h
0x1800241c7  add     esi, 40h ; '@'
0x1800241ca  jmp     short loc_1800241D8
0x1800241cc  mov     esi, 0F0h
0x1800241d1  mov     rbx, qword ptr cs:xmmword_18004C7A0+8
0x1800241d8  test    rbx, rbx
0x1800241db  jz      loc_1800242F7
0x1800241e1  mov     r8d, esi
0x1800241e4  mov     word ptr [rsp+860h+var_840], r13w
0x1800241ea  lea     rdx, aEncryptiontype; "EncryptionTypes: 0x%x"
0x1800241f1  lea     rcx, [rsp+860h+var_840]
0x1800241f6  call    FormatRRASErrorString
0x1800241fb  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x180024202  lea     r8, [rsp+860h+var_840]
0x180024207  jmp     loc_1800242DD
0x18002420c  test    r14b, r14b
0x18002420f  jns     short loc_180024265
0x180024211  cmp     cs:g_dwAllowPPTPWeakCrypto, r13d
0x180024218  mov     r15d, r13d
0x18002421b  mov     rbx, qword ptr cs:xmmword_18004C7A0+8
0x180024222  mov     dword ptr [rdi+10h], 1
0x180024229  jz      short loc_18002423E
0x18002422b  mov     esi, 0B0h
0x180024230  test    rbx, rbx
0x180024233  jz      short loc_18002426C
0x180024235  lea     r8, aEncryption; "Encryption"
0x18002423c  jmp     short loc_18002424F
0x18002423e  mov     esi, 40h ; '@'
0x180024243  test    rbx, rbx
0x180024246  jz      short loc_18002426C
0x180024248  lea     r8, aStrongEncrypti; "Strong encryption"
0x18002424f  mov     rcx, cs:gRasccpEtwContext
0x180024256  mov     rdx, rbx
0x180024259  mov     rax, cs:gRasccpTemplateFunc
0x180024260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024265  mov     rbx, qword ptr cs:xmmword_18004C7A0+8
0x18002426c  bt      r14d, 0Ch
0x180024271  jnb     short loc_1800242AB
0x180024273  or      esi, 40h
0x180024276  mov     dword ptr [rdi+10h], 1
0x18002427d  mov     r15d, r13d
0x180024280  test    rbx, rbx
0x180024283  jz      short loc_1800242B0
0x180024285  mov     rcx, cs:gRasccpEtwContext
0x18002428c  lea     r8, aStrongEncrypti; "Strong encryption"
0x180024293  mov     rax, cs:gRasccpTemplateFunc
0x18002429a  mov     rdx, rbx
0x18002429d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242a2  mov     rbx, qword ptr cs:xmmword_18004C7A0+8
0x1800242a9  jmp     short loc_1800242B0
0x1800242ab  test    r15d, r15d
0x1800242ae  jnz     short loc_1800242F7
0x1800242b0  test    esi, esi
0x1800242b2  jnz     short loc_1800242F7
0x1800242b4  mov     eax, cs:g_dwAllowPPTPWeakCrypto
0x1800242ba  mov     r15d, r13d
0x1800242bd  neg     eax
0x1800242bf  mov     [rdi+10h], r13d
0x1800242c3  sbb     esi, esi
0x1800242c5  and     esi, 0B0h
0x1800242cb  add     esi, 40h ; '@'
0x1800242ce  test    rbx, rbx
0x1800242d1  jz      short loc_1800242F7
0x1800242d3  lea     r8, aNotDisablingEn; "Not disabling encryption; Not forcing e"...
0x1800242da  mov     rdx, rbx
0x1800242dd  mov     rcx, cs:gRasccpEtwContext
0x1800242e4  mov     rax, cs:gRasccpTemplateFunc
0x1800242eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242f0  mov     rbx, qword ptr cs:xmmword_18004C7A0+8
0x1800242f7  mov     r14, [r12+488h]
0x1800242ff  mov     edx, 0Ch
0x180024304  mov     r8, r14
0x180024307  call    RasAuthAttributeGetVendorSpecific
0x18002430c  test    rax, rax
0x18002430f  jnz     short loc_18002437C
0x180024311  mov     r8, r14
0x180024314  lea     edx, [rax+10h]
0x180024317  call    RasAuthAttributeGetVendorSpecific
0x18002431c  test    rax, rax
0x18002431f  jz      short loc_180024333
0x180024321  mov     r8, r14
0x180024324  mov     edx, 11h
0x180024329  call    RasAuthAttributeGetVendorSpecific
0x18002432e  test    rax, rax
0x180024331  jnz     short loc_18002437C
0x180024333  test    rbx, rbx
0x180024336  jz      short loc_180024355
0x180024338  mov     rcx, cs:gRasccpEtwContext
0x18002433f  lea     r8, aNoMppeKeysWere; "No MPPE keys were obtained"
0x180024346  mov     rax, cs:gRasccpTemplateFunc
0x18002434d  mov     rdx, rbx
0x180024350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024355  cmp     [rdi+10h], r13d
0x180024359  jnz     loc_18002482F
0x18002435f  mov     eax, cs:g_dwAllowPPTPWeakCrypto
0x180024365  mov     r15d, 1
0x18002436b  neg     eax
0x18002436d  mov     [rdi+10h], r13d
0x180024371  sbb     esi, esi
0x180024373  and     esi, 0B0h
0x180024379  add     esi, 40h ; '@'
0x18002437c  mov     rcx, [rdi]
0x18002437f  lea     r14, [rdi+30Ch]
0x180024386  mov     rax, qword ptr cs:xmmword_18004C4A0
0x18002438d  lea     rdx, [rdi+24h]
0x180024391  mov     r8, r14
0x180024394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024399  mov     ebx, eax
0x18002439b  test    eax, eax
0x18002439d  jnz     loc_180024A2B
0x1800243a3  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x1800243aa  test    rdx, rdx
0x1800243ad  jz      loc_1800244D6
0x1800243b3  mov     word ptr [rsp+860h+var_840], r13w
0x1800243b9  lea     rdx, aSendCapabilite; "Send capabilites from NDISWAN = 0x%x"
0x1800243c0  mov     r8d, [rdi+5Ch]
0x1800243c4  lea     rcx, [rsp+860h+var_840]
0x1800243c9  call    FormatRRASErrorString
0x1800243ce  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x1800243d5  lea     r8, [rsp+860h+var_840]
0x1800243da  mov     rcx, cs:gRasccpEtwContext
0x1800243e1  mov     rax, cs:gRasccpTemplateFunc
0x1800243e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243ed  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x1800243f4  test    rdx, rdx
0x1800243f7  jz      loc_1800244D6
0x1800243fd  mov     word ptr [rsp+860h+var_840], r13w
0x180024403  lea     rdx, aReceiveCapabil; "Receive capabilites from NDISWAN = 0x%x"
0x18002440a  mov     r8d, [rdi+344h]
0x180024411  lea     rcx, [rsp+860h+var_840]
0x180024416  call    FormatRRASErrorString
0x18002441b  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x180024422  lea     r8, [rsp+860h+var_840]
0x180024427  mov     rcx, cs:gRasccpEtwContext
0x18002442e  mov     rax, cs:gRasccpTemplateFunc
0x180024435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002443a  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x180024441  test    rdx, rdx
0x180024444  jz      loc_1800244D6
0x18002444a  mov     word ptr [rsp+860h+var_840], r13w
0x180024450  lea     rdx, aSendRciMaccomp; "Send RCI_MacCompressionType = 0x%x"
0x180024457  movzx   r8d, byte ptr [rdi+64h]
0x18002445c  lea     rcx, [rsp+860h+var_840]
0x180024461  call    FormatRRASErrorString
0x180024466  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x18002446d  lea     r8, [rsp+860h+var_840]
0x180024472  mov     rcx, cs:gRasccpEtwContext
0x180024479  mov     rax, cs:gRasccpTemplateFunc
0x180024480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024485  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x18002448c  test    rdx, rdx
0x18002448f  jz      short loc_1800244D6
0x180024491  mov     word ptr [rsp+860h+var_840], r13w
0x180024497  lea     rdx, aReceiveRciMacc; "Receive RCI_MacCompressionType = 0x%x"
0x18002449e  movzx   r8d, byte ptr [rdi+34Ch]
0x1800244a6  lea     rcx, [rsp+860h+var_840]
0x1800244ab  call    FormatRRASErrorString
0x1800244b0  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x1800244b7  lea     r8, [rsp+860h+var_840]
0x1800244bc  mov     rcx, cs:gRasccpEtwContext
0x1800244c3  mov     rax, cs:gRasccpTemplateFunc
0x1800244ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244cf  mov     rdx, qword ptr cs:xmmword_18004C7A0+8
0x1800244d6  mov     cl, [rdi+64h]
0x1800244d9  mov     r9b, 0FEh
0x1800244dc  cmp     cl, r9b
0x1800244df  jnz     short loc_1800244E7
0x1800244e1  mov     byte ptr [rdi+64h], 0FFh
0x1800244e5  mov     cl, 0FFh
0x1800244e7  cmp     [rdi+34Ch], r9b
0x1800244ee  jnz     short loc_1800244F7
0x1800244f0  mov     byte ptr [rdi+34Ch], 0FFh
0x1800244f7  mov     r8d, [rdi+5Ch]
0x1800244fb  lea     rbx, [rdi+20h]
0x1800244ff  mov     [rbx], r13d
  ... truncated ...
```
