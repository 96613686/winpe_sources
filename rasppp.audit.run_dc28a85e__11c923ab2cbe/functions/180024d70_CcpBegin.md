# CcpBegin

- ea: `0x180024d70`
- end: `0x18002580d`
- name: `CcpBegin`
- size: `2717`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001b424`
- `0x180024d70`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800252d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024dcd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024de4`

## string_xrefs

- `0x1800251ec`: `Send RCI_MacCompressionType = 0x%x`
- `0x180025233`: `Receive RCI_MacCompressionType = 0x%x`
- `0x18002539d`: `Send Compression is Disabled`
- `0x1800254ec`: `We do not want any compression or encryption on the local side`
- `0x180025663`: `Receive Compression is disabled`
- `0x18002572d`: `We do not want to receive any compression or encryption from the remote side`
- `0x180025761`: `ERROR_PROTOCOL_NOT_CONFIGURED`

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
        v14 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
                v18 = *((_QWORD *)&xmmword_18004D7A0 + 1);
                v19 = (const wchar_t *)&v61;
LABEL_42:
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
                  gRasccpEtwContext,
                  v18,
                  v19);
                v14 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
          v14 = *((_QWORD *)&xmmword_18004D7A0 + 1);
          goto LABEL_25;
        }
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          v14,
          L"Will force encryption");
      }
    }
    v14 = *((_QWORD *)&xmmword_18004D7A0 + 1);
    goto LABEL_11;
  }
  if ( (v2 & 0x80u) == 0 )
    goto LABEL_34;
  v51 = g_dwAllowPPTPWeakCrypto == 0;
  v9 = 0;
  v14 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
      v14 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
      v14 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
  v25 = ((__int64 (__fastcall *)(_QWORD, char *, char *))xmmword_18004D4A0)(*(_QWORD *)v6, v6 + 36, v6 + 780);
  if ( v25 )
  {
LABEL_138:
    LocalFree(v6);
    return v25;
  }
  v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
  if ( *((_QWORD *)&xmmword_18004D7A0 + 1) )
  {
    LOWORD(v61) = 0;
    FormatRRASErrorString(&v61, L"Send capabilites from NDISWAN = 0x%x", *((unsigned int *)v6 + 23));
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
      gRasccpEtwContext,
      *((_QWORD *)&xmmword_18004D7A0 + 1),
      &v61);
    v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
    if ( *((_QWORD *)&xmmword_18004D7A0 + 1) )
    {
      LOWORD(v61) = 0;
      FormatRRASErrorString(&v61, L"Receive capabilites from NDISWAN = 0x%x", *((unsigned int *)v6 + 209));
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        *((_QWORD *)&xmmword_18004D7A0 + 1),
        &v61);
      v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
      if ( *((_QWORD *)&xmmword_18004D7A0 + 1) )
      {
        LOWORD(v61) = 0;
        FormatRRASErrorString(&v61, L"Send RCI_MacCompressionType = 0x%x", (unsigned __int8)v6[100]);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
          gRasccpEtwContext,
          *((_QWORD *)&xmmword_18004D7A0 + 1),
          &v61);
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
        if ( *((_QWORD *)&xmmword_18004D7A0 + 1) )
        {
          LOWORD(v61) = 0;
          FormatRRASErrorString(&v61, L"Receive RCI_MacCompressionType = 0x%x", (unsigned __int8)v6[844]);
          ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
            gRasccpEtwContext,
            *((_QWORD *)&xmmword_18004D7A0 + 1),
            &v61);
          v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
          *((_QWORD *)&xmmword_18004D7A0 + 1),
          &v61);
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
            *((_QWORD *)&xmmword_18004D7A0 + 1),
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
          *((_QWORD *)&xmmword_18004D7A0 + 1),
          &v61);
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
      *((_QWORD *)&xmmword_18004D7A0 + 1),
      &v61);
    v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
        v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
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
      v60 = (*((__int64 (__fastcall **)(__int64, char *, char *))&xmmword_18004D490 + 1))(v59, v6 + 36, v6 + 780);
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
        *((_QWORD *)&xmmword_18004D7A0 + 1),
        &v61);
      v26 = *((_QWORD *)&xmmword_18004D7A0 + 1);
    }
    *v29 &= 0xFFFFFFF9;
    v30 = *v29;
    goto LABEL_75;
  }
  LocalFree(v6);
  if ( *((_QWORD *)&xmmword_18004D7A0 + 1) )
  {
    LOWORD(v61) = 0;
    FormatRRASErrorString(&v61, L"Encryption type(s) 0x%x not supported locally", v10);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasccpTemplateFunc)(
      gRasccpEtwContext,
      *((_QWORD *)&xmmword_18004D7A0 + 1),
      &v61);
  }
  return 741;
}

```

## disassembly

```asm
0x180024d70  mov     [rsp-8+arg_10], rbx
0x180024d75  push    rbp
0x180024d76  push    rsi
0x180024d77  push    rdi
0x180024d78  push    r12
0x180024d7a  push    r13
0x180024d7c  push    r14
0x180024d7e  push    r15
0x180024d80  lea     rbp, [rsp-730h]
0x180024d88  sub     rsp, 830h
0x180024d8f  mov     rax, cs:__security_cookie
0x180024d96  xor     rax, rsp
0x180024d99  mov     [rbp+760h+var_40], rax
0x180024da0  mov     r14d, [rdx+2Ch]
0x180024da4  mov     r12, rdx
0x180024da7  mov     rbx, rcx
0x180024daa  xor     r13d, r13d
0x180024dad  xor     edx, edx; Val
0x180024daf  mov     [rsp+860h+var_840], r13d
0x180024db4  lea     rcx, [rsp+860h+var_83C]; void *
0x180024db9  mov     r8d, 7FCh; Size
0x180024dbf  call    memset_0
0x180024dc4  mov     edx, 5F0h; uBytes
0x180024dc9  lea     ecx, [r13+40h]; uFlags
0x180024dcd  call    cs:__imp_LocalAlloc
0x180024dd4  nop     dword ptr [rax+rax+00h]
0x180024dd9  mov     [rbx], rax
0x180024ddc  mov     rdi, rax
0x180024ddf  test    rax, rax
0x180024de2  jnz     short loc_180024DF5
0x180024de4  call    cs:__imp_GetLastError
0x180024deb  nop     dword ptr [rax+rax+00h]
0x180024df0  jmp     loc_1800257E2
0x180024df5  mov     ecx, [r12]
0x180024df9  mov     r15d, r14d
0x180024dfc  mov     [rax+0Ch], ecx
0x180024dff  and     r15d, 80000h
0x180024e06  mov     rax, [r12+8]
0x180024e0b  mov     esi, r13d
0x180024e0e  mov     [rdi], rax
0x180024e11  mov     eax, r14d
0x180024e14  mov     edx, [r12+10h]
0x180024e19  shr     eax, 1
0x180024e1b  not     eax
0x180024e1d  mov     [rdi+8], edx
0x180024e20  and     eax, 1
0x180024e23  mov     [rdi+10h], r13d
0x180024e27  mov     [rdi+14h], eax
0x180024e2a  test    ecx, ecx
0x180024e2c  jz      loc_180024FA8
0x180024e32  movzx   eax, dx
0x180024e35  cmp     eax, 9
0x180024e38  jz      loc_180024F68
0x180024e3e  cmp     eax, 0Eh
0x180024e41  jz      loc_180024F68
0x180024e47  mov     r8, [r12+488h]
0x180024e4f  mov     edx, 7
0x180024e54  call    RasAuthAttributeGetVendorSpecific
0x180024e59  test    rax, rax
0x180024e5c  jz      short loc_180024EB9
0x180024e5e  mov     rcx, [rax+8]
0x180024e62  movzx   edx, byte ptr [rcx+7]
0x180024e66  movzx   eax, byte ptr [rcx+8]
0x180024e6a  shl     eax, 8
0x180024e6d  shl     edx, 10h
0x180024e70  add     edx, eax
0x180024e72  movzx   eax, byte ptr [rcx+6]
0x180024e76  shl     eax, 18h
0x180024e79  add     edx, eax
0x180024e7b  movzx   eax, byte ptr [rcx+9]
0x180024e7f  add     edx, eax
0x180024e81  cmp     edx, 2
0x180024e84  jnz     short loc_180024EB9
0x180024e86  mov     rbx, qword ptr cs:xmmword_18004D7A0+8
0x180024e8d  mov     r15d, r13d
0x180024e90  mov     dword ptr [rdi+10h], 1
0x180024e97  test    rbx, rbx
0x180024e9a  jz      short loc_180024EC0
0x180024e9c  mov     rcx, cs:gRasccpEtwContext
0x180024ea3  lea     r8, aWillForceEncry; "Will force encryption"
0x180024eaa  mov     rax, cs:gRasccpTemplateFunc
0x180024eb1  mov     rdx, rbx
0x180024eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eb9  mov     rbx, qword ptr cs:xmmword_18004D7A0+8
0x180024ec0  mov     r8, [r12+488h]
0x180024ec8  mov     edx, 8
0x180024ecd  call    RasAuthAttributeGetVendorSpecific
0x180024ed2  test    rax, rax
0x180024ed5  jz      short loc_180024F53
0x180024ed7  mov     rax, [rax+8]
0x180024edb  movzx   r8d, byte ptr [rax+9]
0x180024ee0  mov     edx, r8d
0x180024ee3  and     edx, 4
0x180024ee6  cmp     cs:g_dwAllowPPTPWeakCrypto, r13d
0x180024eed  jz      short loc_180024F48
0x180024eef  mov     eax, r8d
0x180024ef2  and     al, 2
0x180024ef4  neg     al
0x180024ef6  sbb     ecx, ecx
0x180024ef8  and     ecx, 30h
0x180024efb  mov     eax, ecx
0x180024efd  or      eax, 40h
0x180024f00  test    edx, edx
0x180024f02  cmovz   eax, ecx
0x180024f05  mov     esi, eax
0x180024f07  bts     esi, 7
0x180024f0b  test    r8b, 8
0x180024f0f  cmovz   esi, eax
0x180024f12  test    esi, esi
0x180024f14  jnz     short loc_180024F74
0x180024f16  mov     [rdi+10h], r13d
0x180024f1a  mov     r15d, 1
0x180024f20  test    rbx, rbx
0x180024f23  jz      loc_180025093
0x180024f29  mov     rcx, cs:gRasccpEtwContext
0x180024f30  lea     r8, aWillNotForceEn; "Will not force encryption: type not spe"...
0x180024f37  mov     rax, cs:gRasccpTemplateFunc
0x180024f3e  mov     rdx, rbx
0x180024f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f46  jmp     short loc_180024F6D
0x180024f48  test    edx, edx
0x180024f4a  jz      short loc_180024F16
0x180024f4c  mov     esi, 40h ; '@'
0x180024f51  jmp     short loc_180024F74
0x180024f53  mov     eax, cs:g_dwAllowPPTPWeakCrypto
0x180024f59  neg     eax
0x180024f5b  sbb     esi, esi
0x180024f5d  and     esi, 0B0h
0x180024f63  add     esi, 40h ; '@'
0x180024f66  jmp     short loc_180024F74
0x180024f68  mov     esi, 0F0h
0x180024f6d  mov     rbx, qword ptr cs:xmmword_18004D7A0+8
0x180024f74  test    rbx, rbx
0x180024f77  jz      loc_180025093
0x180024f7d  mov     r8d, esi
0x180024f80  mov     word ptr [rsp+860h+var_840], r13w
0x180024f86  lea     rdx, aEncryptiontype; "EncryptionTypes: 0x%x"
0x180024f8d  lea     rcx, [rsp+860h+var_840]
0x180024f92  call    FormatRRASErrorString
0x180024f97  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180024f9e  lea     r8, [rsp+860h+var_840]
0x180024fa3  jmp     loc_180025079
0x180024fa8  test    r14b, r14b
0x180024fab  jns     short loc_180025001
0x180024fad  cmp     cs:g_dwAllowPPTPWeakCrypto, r13d
0x180024fb4  mov     r15d, r13d
0x180024fb7  mov     rbx, qword ptr cs:xmmword_18004D7A0+8
0x180024fbe  mov     dword ptr [rdi+10h], 1
0x180024fc5  jz      short loc_180024FDA
0x180024fc7  mov     esi, 0B0h
0x180024fcc  test    rbx, rbx
0x180024fcf  jz      short loc_180025008
0x180024fd1  lea     r8, aEncryption; "Encryption"
0x180024fd8  jmp     short loc_180024FEB
0x180024fda  mov     esi, 40h ; '@'
0x180024fdf  test    rbx, rbx
0x180024fe2  jz      short loc_180025008
0x180024fe4  lea     r8, aStrongEncrypti; "Strong encryption"
0x180024feb  mov     rcx, cs:gRasccpEtwContext
0x180024ff2  mov     rdx, rbx
0x180024ff5  mov     rax, cs:gRasccpTemplateFunc
0x180024ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025001  mov     rbx, qword ptr cs:xmmword_18004D7A0+8
0x180025008  bt      r14d, 0Ch
0x18002500d  jnb     short loc_180025047
0x18002500f  or      esi, 40h
0x180025012  mov     dword ptr [rdi+10h], 1
0x180025019  mov     r15d, r13d
0x18002501c  test    rbx, rbx
0x18002501f  jz      short loc_18002504C
0x180025021  mov     rcx, cs:gRasccpEtwContext
0x180025028  lea     r8, aStrongEncrypti; "Strong encryption"
0x18002502f  mov     rax, cs:gRasccpTemplateFunc
0x180025036  mov     rdx, rbx
0x180025039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002503e  mov     rbx, qword ptr cs:xmmword_18004D7A0+8
0x180025045  jmp     short loc_18002504C
0x180025047  test    r15d, r15d
0x18002504a  jnz     short loc_180025093
0x18002504c  test    esi, esi
0x18002504e  jnz     short loc_180025093
0x180025050  mov     eax, cs:g_dwAllowPPTPWeakCrypto
0x180025056  mov     r15d, r13d
0x180025059  neg     eax
0x18002505b  mov     [rdi+10h], r13d
0x18002505f  sbb     esi, esi
0x180025061  and     esi, 0B0h
0x180025067  add     esi, 40h ; '@'
0x18002506a  test    rbx, rbx
0x18002506d  jz      short loc_180025093
0x18002506f  lea     r8, aNotDisablingEn; "Not disabling encryption; Not forcing e"...
0x180025076  mov     rdx, rbx
0x180025079  mov     rcx, cs:gRasccpEtwContext
0x180025080  mov     rax, cs:gRasccpTemplateFunc
0x180025087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002508c  mov     rbx, qword ptr cs:xmmword_18004D7A0+8
0x180025093  mov     r14, [r12+488h]
0x18002509b  mov     edx, 0Ch
0x1800250a0  mov     r8, r14
0x1800250a3  call    RasAuthAttributeGetVendorSpecific
0x1800250a8  test    rax, rax
0x1800250ab  jnz     short loc_180025118
0x1800250ad  mov     r8, r14
0x1800250b0  lea     edx, [rax+10h]
0x1800250b3  call    RasAuthAttributeGetVendorSpecific
0x1800250b8  test    rax, rax
0x1800250bb  jz      short loc_1800250CF
0x1800250bd  mov     r8, r14
0x1800250c0  mov     edx, 11h
0x1800250c5  call    RasAuthAttributeGetVendorSpecific
0x1800250ca  test    rax, rax
0x1800250cd  jnz     short loc_180025118
0x1800250cf  test    rbx, rbx
0x1800250d2  jz      short loc_1800250F1
0x1800250d4  mov     rcx, cs:gRasccpEtwContext
0x1800250db  lea     r8, aNoMppeKeysWere; "No MPPE keys were obtained"
0x1800250e2  mov     rax, cs:gRasccpTemplateFunc
0x1800250e9  mov     rdx, rbx
0x1800250ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250f1  cmp     [rdi+10h], r13d
0x1800250f5  jnz     loc_1800255D1
0x1800250fb  mov     eax, cs:g_dwAllowPPTPWeakCrypto
0x180025101  mov     r15d, 1
0x180025107  neg     eax
0x180025109  mov     [rdi+10h], r13d
0x18002510d  sbb     esi, esi
0x18002510f  and     esi, 0B0h
0x180025115  add     esi, 40h ; '@'
0x180025118  mov     rcx, [rdi]
0x18002511b  lea     r14, [rdi+30Ch]
0x180025122  mov     rax, qword ptr cs:xmmword_18004D4A0
0x180025129  lea     rdx, [rdi+24h]
0x18002512d  mov     r8, r14
0x180025130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025135  mov     ebx, eax
0x180025137  test    eax, eax
0x180025139  jnz     loc_1800257CD
0x18002513f  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180025146  test    rdx, rdx
0x180025149  jz      loc_180025272
0x18002514f  mov     word ptr [rsp+860h+var_840], r13w
0x180025155  lea     rdx, aSendCapabilite; "Send capabilites from NDISWAN = 0x%x"
0x18002515c  mov     r8d, [rdi+5Ch]
0x180025160  lea     rcx, [rsp+860h+var_840]
0x180025165  call    FormatRRASErrorString
0x18002516a  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180025171  lea     r8, [rsp+860h+var_840]
0x180025176  mov     rcx, cs:gRasccpEtwContext
0x18002517d  mov     rax, cs:gRasccpTemplateFunc
0x180025184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025189  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180025190  test    rdx, rdx
0x180025193  jz      loc_180025272
0x180025199  mov     word ptr [rsp+860h+var_840], r13w
0x18002519f  lea     rdx, aReceiveCapabil; "Receive capabilites from NDISWAN = 0x%x"
0x1800251a6  mov     r8d, [rdi+344h]
0x1800251ad  lea     rcx, [rsp+860h+var_840]
0x1800251b2  call    FormatRRASErrorString
0x1800251b7  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x1800251be  lea     r8, [rsp+860h+var_840]
0x1800251c3  mov     rcx, cs:gRasccpEtwContext
0x1800251ca  mov     rax, cs:gRasccpTemplateFunc
0x1800251d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251d6  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x1800251dd  test    rdx, rdx
0x1800251e0  jz      loc_180025272
0x1800251e6  mov     word ptr [rsp+860h+var_840], r13w
0x1800251ec  lea     rdx, aSendRciMaccomp; "Send RCI_MacCompressionType = 0x%x"
0x1800251f3  movzx   r8d, byte ptr [rdi+64h]
0x1800251f8  lea     rcx, [rsp+860h+var_840]
0x1800251fd  call    FormatRRASErrorString
0x180025202  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180025209  lea     r8, [rsp+860h+var_840]
0x18002520e  mov     rcx, cs:gRasccpEtwContext
0x180025215  mov     rax, cs:gRasccpTemplateFunc
0x18002521c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025221  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180025228  test    rdx, rdx
0x18002522b  jz      short loc_180025272
0x18002522d  mov     word ptr [rsp+860h+var_840], r13w
0x180025233  lea     rdx, aReceiveRciMacc; "Receive RCI_MacCompressionType = 0x%x"
0x18002523a  movzx   r8d, byte ptr [rdi+34Ch]
0x180025242  lea     rcx, [rsp+860h+var_840]
0x180025247  call    FormatRRASErrorString
0x18002524c  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180025253  lea     r8, [rsp+860h+var_840]
0x180025258  mov     rcx, cs:gRasccpEtwContext
0x18002525f  mov     rax, cs:gRasccpTemplateFunc
0x180025266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002526b  mov     rdx, qword ptr cs:xmmword_18004D7A0+8
0x180025272  mov     cl, [rdi+64h]
0x180025275  mov     r9b, 0FEh
0x180025278  cmp     cl, r9b
0x18002527b  jnz     short loc_180025283
0x18002527d  mov     byte ptr [rdi+64h], 0FFh
0x180025281  mov     cl, 0FFh
0x180025283  cmp     [rdi+34Ch], r9b
0x18002528a  jnz     short loc_180025293
0x18002528c  mov     byte ptr [rdi+34Ch], 0FFh
0x180025293  mov     r8d, [rdi+5Ch]
  ... truncated ...
```
