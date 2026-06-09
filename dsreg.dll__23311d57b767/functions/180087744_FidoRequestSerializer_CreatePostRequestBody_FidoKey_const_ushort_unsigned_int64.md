# FidoRequestSerializer::CreatePostRequestBody(FidoKey const *,ushort * *,unsigned __int64 *)

- ea: `0x180087744`
- end: `0x18008839f`
- name: `?CreatePostRequestBody@FidoRequestSerializer@@SAJPEBVFidoKey@@PEAPEAGPEA_K@Z`
- size: `3163`
- prototype: `__int64 __fastcall(const struct FidoKey *this, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800860d4`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x180012cf0`
- `0x1800307c4`
- `0x18003334c`
- `0x180067c6c`
- `0x18006cdf8`
- `0x18007c57c`
- `0x18007ca54`
- `0x18007cbb0`
- `0x18007cc30`
- `0x18007cc9c`
- `0x18007cd1c`
- `0x18007cdd0`
- `0x180087744`
- `0x180088ffc`
- `0x18008c820`

## string_xrefs

- `0x180087aed`: `EscapeStringForJson`
- `0x180087ee3`: `PrintJsonField`
- `0x180087f4c`: `PrintJsonElementStart`
- `0x18008807d`: `PrintJsonArrayStart`
- `0x18008812b`: `PrintJsonArrayElement`
- `0x180088141`: `PrintJsonArrayElement`
- `0x1800881e7`: `PrintJsonArrayEnd`
- `0x1800881fd`: `PrintJsonArrayEnd`
- `0x180088220`: `PrintJsonElementEnd`
- `0x180087ea0`: `PrintJsonStart`
- `0x180087a0e`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x180087a28`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x180087a4d`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x180087a92`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x180087af4`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x180087e60`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x180087eaa`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x180088157`: `FidoRequestSerializer::CreatePostRequestBody`
- `0x1800882ce`: `FidoRequestSerializer::CreatePostRequestBody`

## pseudocode

```c
__int64 __fastcall FidoRequestSerializer::CreatePostRequestBody(
        const struct FidoKey *this,
        wchar_t *a2,
        unsigned __int64 *a3)
{
  const wchar_t *v3; // r12
  int v7; // ecx
  const wchar_t *v8; // r8
  unsigned __int64 v9; // rdx
  int v10; // r15d
  unsigned __int16 *v11; // rdi
  __int64 v12; // r14
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rax
  int AttestationCertificateBase64; // eax
  const wchar_t *v17; // r8
  __int64 v18; // r9
  const unsigned __int16 *v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  const unsigned __int16 *v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  const unsigned __int16 *v25; // rax
  int v26; // eax
  unsigned int i; // r15d
  int v28; // r9d
  int v29; // r9d
  int v30; // r9d
  int v31; // r9d
  int v32; // r9d
  int v33; // r9d
  int v34; // r9d
  int v35; // r9d
  int v36; // r9d
  int v37; // r9d
  int v38; // r9d
  int v39; // r9d
  unsigned __int64 v40; // r12
  wchar_t *v41; // rax
  wchar_t *v42; // r15
  int v43; // eax
  const wchar_t *v44; // r8
  __int64 v45; // r9
  int v46; // eax
  int v47; // eax
  unsigned int j; // r14d
  int v49; // eax
  int v50; // eax
  unsigned __int64 v51; // rdx
  wchar_t *v52; // rcx
  int v53; // eax
  unsigned __int64 *v54; // rsi
  unsigned __int16 *v55; // rcx
  unsigned __int64 v56; // rdx
  unsigned __int16 *v57; // rax
  _BYTE *v58; // rcx
  __int64 v59; // rdx
  _BYTE *v60; // rax
  unsigned __int64 v62; // [rsp+48h] [rbp-C0h] BYREF
  void *lpMem; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v64[3]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v65; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v66; // [rsp+78h] [rbp-90h] BYREF
  int v67; // [rsp+80h] [rbp-88h] BYREF
  int v68; // [rsp+84h] [rbp-84h]
  const wchar_t *v69; // [rsp+88h] [rbp-80h]
  __int64 v70; // [rsp+90h] [rbp-78h]
  unsigned __int16 *v71; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v72; // [rsp+A0h] [rbp-68h] BYREF
  int v73; // [rsp+A8h] [rbp-60h] BYREF
  int v74; // [rsp+ACh] [rbp-5Ch]
  const wchar_t *v75; // [rsp+B0h] [rbp-58h]
  __int64 v76; // [rsp+B8h] [rbp-50h]
  const unsigned __int16 *v77; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v78; // [rsp+C8h] [rbp-40h] BYREF
  int v79; // [rsp+D0h] [rbp-38h] BYREF
  int v80; // [rsp+D4h] [rbp-34h]
  const wchar_t *v81; // [rsp+D8h] [rbp-30h]
  __int64 v82; // [rsp+E0h] [rbp-28h]
  const unsigned __int16 *v83; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v84; // [rsp+F0h] [rbp-18h] BYREF
  int v85; // [rsp+F8h] [rbp-10h] BYREF
  int v86; // [rsp+FCh] [rbp-Ch]
  const wchar_t *v87; // [rsp+100h] [rbp-8h]
  __int64 v88; // [rsp+108h] [rbp+0h]
  const unsigned __int16 *v89; // [rsp+110h] [rbp+8h]
  unsigned __int64 v90; // [rsp+118h] [rbp+10h] BYREF
  _DWORD v91[2]; // [rsp+120h] [rbp+18h] BYREF
  const wchar_t *v92; // [rsp+128h] [rbp+20h]
  __int64 v93; // [rsp+130h] [rbp+28h]
  const wchar_t *v94; // [rsp+138h] [rbp+30h]
  __int64 v95; // [rsp+140h] [rbp+38h]
  _DWORD v96[2]; // [rsp+148h] [rbp+40h] BYREF
  const wchar_t *v97; // [rsp+150h] [rbp+48h]
  __int64 v98; // [rsp+158h] [rbp+50h]
  void *v99; // [rsp+160h] [rbp+58h]
  unsigned __int64 v100; // [rsp+168h] [rbp+60h] BYREF
  _DWORD v101[2]; // [rsp+170h] [rbp+68h] BYREF
  const wchar_t *v102; // [rsp+178h] [rbp+70h]
  __int64 v103; // [rsp+180h] [rbp+78h]
  const wchar_t *v104; // [rsp+188h] [rbp+80h]
  __int64 v105; // [rsp+190h] [rbp+88h]
  _DWORD v106[2]; // [rsp+198h] [rbp+90h] BYREF
  const wchar_t *v107; // [rsp+1A0h] [rbp+98h]
  __int64 v108; // [rsp+1A8h] [rbp+A0h]
  const wchar_t *v109; // [rsp+1B0h] [rbp+A8h]
  __int64 v110; // [rsp+1B8h] [rbp+B0h]
  _DWORD v111[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  const wchar_t *v112; // [rsp+1C8h] [rbp+C0h]
  __int64 v113; // [rsp+1D0h] [rbp+C8h]
  const wchar_t *v114; // [rsp+1D8h] [rbp+D0h]
  __int64 v115; // [rsp+1E0h] [rbp+D8h]
  _DWORD v116[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  const wchar_t *v117; // [rsp+1F0h] [rbp+E8h]
  __int64 v118; // [rsp+1F8h] [rbp+F0h]
  const wchar_t *v119; // [rsp+200h] [rbp+F8h]
  __int64 v120; // [rsp+208h] [rbp+100h]
  _DWORD v121[2]; // [rsp+210h] [rbp+108h] BYREF
  const wchar_t *v122; // [rsp+218h] [rbp+110h]
  __int64 v123; // [rsp+220h] [rbp+118h]
  const wchar_t *v124; // [rsp+228h] [rbp+120h]
  __int64 v125; // [rsp+230h] [rbp+128h]
  _DWORD v126[2]; // [rsp+238h] [rbp+130h] BYREF
  const wchar_t *v127; // [rsp+240h] [rbp+138h]
  __int64 v128; // [rsp+248h] [rbp+140h]
  __int64 v129; // [rsp+250h] [rbp+148h]
  __int64 v130; // [rsp+258h] [rbp+150h]
  wchar_t *Buffer; // [rsp+2B0h] [rbp+1A8h] BYREF
  unsigned __int64 *v132; // [rsp+2B8h] [rbp+1B0h]
  unsigned __int64 v133; // [rsp+2C0h] [rbp+1B8h] BYREF

  v132 = a3;
  Buffer = a2;
  v3 = 0;
  v103 = 11;
  v133 = 0;
  v102 = L"hashVersion";
  lpMem = 0;
  v97 = L"credentialDisplayName";
  v98 = 21;
  v108 = 21;
  v107 = L"credentialAttestation";
  v109 = L"{";
  v69 = L"authenticatorData";
  v114 = L"{";
  v112 = L"attestationData";
  v105 = 1;
  v117 = L"version";
  v110 = 1;
  v87 = L"algorithm";
  v115 = 1;
  v116[1] = 1;
  v120 = 1;
  v7 = 32;
  v64[1] = L"signature";
  v8 = L"clientDataHashAlgorithm";
  v101[0] = 0;
  v9 = 0;
  v101[1] = 16;
  v10 = 256;
  v104 = L"1";
  v73 = 0;
  v11 = 0;
  v74 = 32;
  v75 = L"clientDataHashAlgorithm";
  v76 = 23;
  v78 = 0;
  v96[0] = 0;
  v96[1] = 64;
  v99 = 0;
  v100 = 0;
  v106[0] = 0;
  v106[1] = 128;
  v79 = 0;
  v80 = 256;
  v81 = L"formatType";
  v82 = 10;
  v84 = 0;
  v67 = 0;
  v68 = 512;
  v70 = 17;
  v71 = 0;
  v72 = 0;
  v111[0] = 0;
  v111[1] = 1024;
  v113 = 15;
  v116[0] = 0;
  v118 = 7;
  v119 = L"1";
  v85 = 0;
  v86 = 2048;
  v88 = 9;
  v90 = 0;
  v64[0] = 0x100000000000LL;
  v93 = 16;
  v92 = L"x509Certificates";
  v12 = 0;
  v64[2] = 9;
  v122 = L"usage";
  v124 = L"FIDO";
  v127 = L"attributes";
  v65 = 0;
  v66 = 0;
  v91[0] = 0;
  v91[1] = 0x2000;
  v94 = 0;
  v95 = 0;
  v121[0] = 0;
  v121[1] = 0x4000;
  v123 = 5;
  v125 = 4;
  v126[0] = 1;
  v126[1] = 0x8000;
  v128 = 10;
  v129 = 0;
  v130 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    v13 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"FidoRequestSerializer::CreatePostRequestBody", L"pBuffer");
    v14 = L"pBuffer";
LABEL_5:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"FidoRequestSerializer::CreatePostRequestBody", v14);
LABEL_104:
    v40 = v133;
    goto LABEL_105;
  }
  *(_QWORD *)a2 = 0;
  if ( !this )
  {
    v13 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"FidoRequestSerializer::CreatePostRequestBody", L"pKey");
    v14 = L"pKey";
    goto LABEL_5;
  }
  v15 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  v77 = v15;
  if ( v15 )
  {
    AttestationCertificateBase64 = StringLen(v15, &v78);
    v13 = AttestationCertificateBase64;
    if ( AttestationCertificateBase64 < 0 )
      goto LABEL_10;
    v9 = v78;
    v15 = v77;
    LODWORD(v8) = (_DWORD)v75;
    v7 = v74;
  }
  if ( v7 && (!v15 || !v9) )
    goto LABEL_103;
  v19 = (const unsigned __int16 *)*((_QWORD *)this + 2);
  if ( v19 )
  {
    v20 = EscapeStringForJson(v19, 0, (unsigned __int16 **)&lpMem);
    v13 = v20;
    if ( v20 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"FidoRequestSerializer::CreatePostRequestBody",
        L"EscapeStringForJson",
        (unsigned int)v20);
      v11 = (unsigned __int16 *)lpMem;
      goto LABEL_104;
    }
    v11 = (unsigned __int16 *)lpMem;
  }
  if ( v11 )
  {
    AttestationCertificateBase64 = StringLen(v11, &v100);
    v13 = AttestationCertificateBase64;
    if ( AttestationCertificateBase64 < 0 )
      goto LABEL_10;
  }
  v21 = *(_QWORD *)this;
  v99 = v11;
  v11 = 0;
  lpMem = 0;
  v22 = *(const unsigned __int16 **)(v21 + 8);
  v83 = v22;
  if ( v22 )
  {
    AttestationCertificateBase64 = StringLen(v22, &v84);
    v13 = AttestationCertificateBase64;
    if ( AttestationCertificateBase64 < 0 )
      goto LABEL_10;
    v22 = v83;
    v10 = v80;
  }
  if ( v10 && (!v22 || !v84) )
    goto LABEL_103;
  v23 = BinaryToString(
          *(BYTE **)(*(_QWORD *)this + 24LL),
          *(_DWORD *)(*(_QWORD *)this + 16LL),
          (unsigned int)v8,
          &v71,
          &v72,
          0);
  v13 = v23;
  if ( v23 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"FidoKey::GetAuthenticatorDataBase64",
      L"BinaryToBase64String",
      (unsigned int)v23);
    v18 = v13;
    v17 = L"FidoKey::GetAuthenticatorDataBase64";
LABEL_12:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"FidoRequestSerializer::CreatePostRequestBody",
      v17,
      v18);
    goto LABEL_104;
  }
  if ( v68 && (!v71 || !v72) )
  {
LABEL_103:
    v13 = -2147024809;
    Logger::TraceError(L"%s: %s is required but is empty", L"FidoRequestSerializer::CreatePostRequestBody");
    goto LABEL_104;
  }
  v25 = *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)this + 56LL) + 8LL);
  v89 = v25;
  if ( !v25 )
    goto LABEL_39;
  AttestationCertificateBase64 = StringLen(v25, &v90);
  v13 = AttestationCertificateBase64;
  if ( AttestationCertificateBase64 < 0 )
  {
LABEL_10:
    v17 = L"StringLenNullSafe";
LABEL_11:
    v18 = (unsigned int)AttestationCertificateBase64;
    goto LABEL_12;
  }
  v25 = v89;
LABEL_39:
  if ( v86 && (!v25 || !v90) )
    goto LABEL_103;
  v26 = BinaryToString(
          *(BYTE **)(*(_QWORD *)(*(_QWORD *)this + 56LL) + 24LL),
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 56LL) + 20LL),
          v24,
          &v65,
          &v66,
          0);
  v13 = v26;
  if ( v26 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"FidoKey::GetAttestationSignatureBase64",
      L"BinaryToBase64String",
      (unsigned int)v26);
    v18 = v13;
    v17 = L"FidoKey::GetAttestationSignatureBase64";
    goto LABEL_12;
  }
  if ( HIDWORD(v64[0]) && (!v65 || !v66) )
    goto LABEL_103;
  for ( i = 0; i < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 56LL) + 32LL); ++i )
  {
    v62 = 0;
    AttestationCertificateBase64 = FidoKey::GetAttestationCertificateBase64(this, i, 0, &v62);
    v13 = AttestationCertificateBase64;
    if ( AttestationCertificateBase64 < 0 )
    {
      v17 = L"FidoKey::GetAttestationCertificateBase64";
      goto LABEL_11;
    }
    if ( v62 )
    {
      v12 += v62 + 3;
      v95 = v12;
    }
  }
  if ( v12 )
  {
    v3 = L"[";
    ++v12;
    v94 = L"[";
    v95 = v12;
  }
  if ( !v3 || !v12 )
    goto LABEL_103;
  AddJsonFieldLength(-1, (struct struct_json_field *)v101, &v133);
  AddJsonFieldLength(v28, (struct struct_json_field *)&v73, &v133);
  AddJsonFieldLength(v29, (struct struct_json_field *)v96, &v133);
  AddJsonFieldLength(v30, (struct struct_json_field *)v106, &v133);
  AddJsonFieldLength(v31, (struct struct_json_field *)&v79, &v133);
  AddJsonFieldLength(v32, (struct struct_json_field *)&v67, &v133);
  AddJsonFieldLength(v33, (struct struct_json_field *)v111, &v133);
  AddJsonFieldLength(v34, (struct struct_json_field *)v116, &v133);
  AddJsonFieldLength(v35, (struct struct_json_field *)&v85, &v133);
  AddJsonFieldLength(v36, (struct struct_json_field *)v64, &v133);
  AddJsonFieldLength(v37, (struct struct_json_field *)v91, &v133);
  AddJsonFieldLength(v38, (struct struct_json_field *)v121, &v133);
  AddJsonFieldLength(v39, (struct struct_json_field *)v126, &v133);
  v40 = v133;
  if ( !v133 )
  {
LABEL_105:
    v42 = Buffer;
    goto LABEL_106;
  }
  v41 = (wchar_t *)SafeAlloc(2 * v133);
  v42 = Buffer;
  *(_QWORD *)Buffer = v41;
  if ( !v41 )
  {
    v13 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"FidoRequestSerializer::CreatePostRequestBody");
LABEL_106:
    v54 = v132;
    goto LABEL_107;
  }
  Buffer = v41;
  v62 = v40;
  v43 = PrintJsonStart(&Buffer, &v62);
  v13 = v43;
  if ( v43 < 0 )
  {
    v44 = L"PrintJsonStart";
LABEL_65:
    v45 = (unsigned int)v43;
LABEL_66:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"FidoRequestSerializer::CreatePostRequestBody",
      v44,
      v45);
    goto LABEL_106;
  }
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)v101, 0);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)&v73, 1);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)v96, 1);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v43 = PrintJsonElementStart(&Buffer, &v62, (struct struct_json_field *)v106);
  v13 = v43;
  if ( v43 < 0 )
  {
    v44 = L"PrintJsonElementStart";
    goto LABEL_65;
  }
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)&v79, 1);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)&v67, 1);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v46 = PrintJsonElementStart(&Buffer, &v62, (struct struct_json_field *)v111);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)v116, 0);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)&v85, 1);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)v64, 1);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  if ( v91[0] )
  {
    v47 = StringCchPrintfExW(Buffer, v62, &Buffer, &v62, 0x100u, L"\"%s\":[", v92);
    v13 = v47;
    if ( v47 < 0 )
    {
      Logger::TraceError(
        L"%s: StringCchPrintfExW failed with error code: 0x%08x",
        L"PrintJsonArrayStart",
        (unsigned int)v47);
      v45 = v13;
      goto LABEL_69;
    }
  }
  for ( j = 0; j < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 56LL) + 32LL); ++j )
  {
    v49 = FidoKey::GetAttestationCertificateBase64(this, j, (unsigned __int16 **)&lpMem, 0);
    v13 = v49;
    if ( v49 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"FidoRequestSerializer::CreatePostRequestBody",
        L"FidoKey::GetAttestationCertificateBase64",
        (unsigned int)v49);
      v11 = (unsigned __int16 *)lpMem;
      goto LABEL_106;
    }
    v11 = (unsigned __int16 *)lpMem;
    v50 = StringCchPrintfExW(Buffer, v62, &Buffer, &v62, 0x100u, L"\"%s\",", lpMem);
    v13 = v50;
    if ( v50 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"PrintJsonArrayElement",
        L"StringCchPrintfExW",
        (unsigned int)v50);
      v45 = v13;
      v44 = L"PrintJsonArrayElement";
      goto LABEL_66;
    }
    SafeFree(v11);
    v11 = 0;
    lpMem = 0;
  }
  v51 = v62;
  v52 = Buffer - 1;
  Buffer = v52;
  if ( *v52 == 44 )
    v51 = ++v62;
  else
    Buffer = ++v52;
  v53 = StringCchPrintfExW(v52, v51, &Buffer, &v62, 0x100u, L"%s,", L"]");
  v13 = v53;
  if ( v53 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"PrintJsonArrayEnd",
      L"StringCchPrintfExW",
      (unsigned int)v53);
    v45 = v13;
    v44 = L"PrintJsonArrayEnd";
    goto LABEL_66;
  }
  v43 = PrintJsonElementEnd(&Buffer, &v62);
  v13 = v43;
  if ( v43 < 0 )
  {
LABEL_96:
    v44 = L"PrintJsonElementEnd";
    goto LABEL_65;
  }
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)v121, 1);
  v13 = v46;
  if ( v46 < 0 )
    goto LABEL_68;
  v43 = PrintJsonElementEnd(&Buffer, &v62);
  v13 = v43;
  if ( v43 < 0 )
    goto LABEL_96;
  v46 = PrintJsonField(&Buffer, &v62, (struct struct_json_field *)v126, 1);
  v13 = v46;
  if ( v46 < 0 || (v46 = PrintJsonEnd(&Buffer, &v62), v13 = v46, v46 < 0) )
  {
LABEL_68:
    v45 = (unsigned int)v46;
LABEL_69:
    v44 = L"PrintJsonField";
    goto LABEL_66;
  }
  v54 = v132;
  if ( v132 )
    *v132 = v40 - v62;
LABEL_107:
  SafeFree(v11);
  SafeFree(v99);
  SafeFree(v71);
  v55 = v65;
  if ( v65 )
  {
    v56 = 2 * v66;
    if ( 2 * v66 )
    {
      v57 = v65;
      do
      {
        *(_BYTE *)v57 = 0;
        v57 = (unsigned __int16 *)((char *)v57 + 1);
        --v56;
      }
      while ( v56 );
    }
  }
  SafeFree(v55);
  if ( (v13 & 0x80000000) != 0 )
  {
    if ( v42 )
    {
      v58 = *(_BYTE **)v42;
      if ( *(_QWORD *)v42 )
      {
        v59 = 2 * v40;
        if ( 2 * v40 )
        {
          v60 = *(_BYTE **)v42;
          do
          {
            *v60++ = 0;
            --v59;
          }
          while ( v59 );
        }
      }
      SafeFree(v58);
      *(_QWORD *)v42 = 0;
    }
    if ( v54 )
      *v54 = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180087744  mov     rax, rsp
0x180087747  mov     [rax+8], rbx
0x18008774b  mov     [rax+18h], r8
0x18008774f  mov     [rax+10h], rdx
0x180087753  push    rbp
0x180087754  push    rsi
0x180087755  push    rdi
0x180087756  push    r12
0x180087758  push    r13
0x18008775a  push    r14
0x18008775c  push    r15
0x18008775e  lea     rbp, [rax-198h]
0x180087765  sub     rsp, 260h
0x18008776c  xor     r12d, r12d
0x18008776f  mov     [rbp+190h+var_118], 0Bh
0x180087777  lea     rax, aHashversion; "hashVersion"
0x18008777e  mov     [rbp+190h+arg_18], r12
0x180087785  mov     [rbp+190h+var_120], rax
0x180087789  lea     rbx, a1; "1"
0x180087790  lea     rax, aCredentialdisp; "credentialDisplayName"
0x180087797  mov     [rsp+290h+lpMem], r12
0x18008779c  mov     [rbp+190h+var_148], rax
0x1800877a0  lea     r11d, [r12+15h]
0x1800877a5  mov     [rbp+190h+var_140], r11
0x1800877a9  lea     r15d, [r12+1]
0x1800877ae  mov     [rbp+190h+var_F0], r11
0x1800877b5  lea     rax, aCredentialatte; "credentialAttestation"
0x1800877bc  lea     r11, asc_1800F9498; "{"
0x1800877c3  mov     [rbp+190h+var_F8], rax
0x1800877ca  lea     rax, aAuthenticatord; "authenticatorData"
0x1800877d1  mov     [rbp+190h+var_E8], r11
0x1800877d8  mov     [rbp+190h+var_210], rax
0x1800877dc  lea     r14d, [r12+10h]
0x1800877e1  lea     rax, aAttestationdat_0; "attestationData"
0x1800877e8  mov     [rbp+190h+var_C0], r11
0x1800877ef  lea     r11d, [r12+1]
0x1800877f4  mov     [rbp+190h+var_D0], rax
0x1800877fb  lea     rax, aVersion; "version"
0x180087802  mov     [rbp+190h+var_108], r15
0x180087809  mov     [rbp+190h+var_A8], rax
0x180087810  lea     r13, aFormattype; "formatType"
0x180087817  lea     rax, aAlgorithm; "algorithm"
0x18008781e  mov     [rbp+190h+var_E0], r15
0x180087825  mov     [rbp+190h+var_198], rax
0x180087829  mov     r10, r8
0x18008782c  mov     r9, rdx
0x18008782f  mov     [rbp+190h+var_B8], r11
0x180087836  mov     rsi, rcx
0x180087839  mov     [rbp+190h+var_AC], r11d
0x180087840  mov     [rbp+190h+var_90], r11
0x180087847  lea     rax, aSignature; "signature"
0x18008784e  lea     ecx, [r12+20h]
0x180087853  mov     [rsp+290h+var_238], rax
0x180087858  lea     r8, aClientdatahash; "clientDataHashAlgorithm"
0x18008785f  mov     [rbp+190h+var_128], r12d
0x180087863  mov     edx, r12d
0x180087866  mov     [rbp+190h+var_124], r14d
0x18008786a  mov     r15d, 100h
0x180087870  mov     [rbp+190h+var_110], rbx
0x180087877  lea     r11d, [r12+9]
0x18008787c  mov     [rbp+190h+var_1F0], r12d
0x180087880  mov     edi, r12d
0x180087883  mov     [rbp+190h+var_1EC], ecx
0x180087886  mov     [rbp+190h+var_1E8], r8
0x18008788a  mov     [rbp+190h+var_1E0], 17h
0x180087892  mov     [rbp+190h+var_1D0], rdx
0x180087896  mov     [rbp+190h+var_150], r12d
0x18008789a  mov     [rbp+190h+var_14C], 40h ; '@'
0x1800878a1  mov     [rbp+190h+var_138], r12
0x1800878a5  mov     [rbp+190h+var_130], r12
0x1800878a9  mov     [rbp+190h+var_100], r12d
0x1800878b0  mov     [rbp+190h+var_FC], 80h
0x1800878ba  mov     [rbp+190h+var_1C8], r12d
0x1800878be  mov     [rbp+190h+var_1C4], r15d
0x1800878c2  mov     [rbp+190h+var_1C0], r13
0x1800878c6  mov     [rbp+190h+var_1B8], 0Ah
0x1800878ce  mov     [rbp+190h+var_1A8], r12
0x1800878d2  mov     [rsp+290h+var_218], r12d
0x1800878d7  mov     [rsp+290h+var_214], 200h
0x1800878df  mov     [rbp+190h+var_208], 11h
0x1800878e7  mov     [rbp+190h+var_200], r12
0x1800878eb  mov     [rbp+190h+var_1F8], r12
0x1800878ef  mov     [rbp+190h+var_D8], r12d
0x1800878f6  mov     [rbp+190h+var_D4], 400h
0x180087900  mov     [rbp+190h+var_C8], 0Fh
0x18008790b  mov     [rbp+190h+var_B0], r12d
0x180087912  mov     [rbp+190h+var_A0], 7
0x18008791d  mov     [rbp+190h+var_98], rbx
0x180087924  mov     [rbp+190h+var_1A0], r12d
0x180087928  mov     [rbp+190h+var_19C], 800h
0x18008792f  mov     [rbp+190h+var_190], r11
0x180087933  mov     [rbp+190h+var_180], r12
0x180087937  mov     dword ptr [rsp+290h+var_240], r12d
0x18008793c  mov     dword ptr [rsp+290h+var_240+4], 1000h
0x180087944  lea     rax, aX509certificat; "x509Certificates"
0x18008794b  mov     [rbp+190h+var_168], r14
0x18008794f  mov     [rbp+190h+var_170], rax
0x180087953  xor     r14d, r14d
0x180087956  mov     [rsp+290h+var_230], r11
0x18008795b  lea     rax, aUsage; "usage"
0x180087962  mov     [rbp+190h+var_80], rax
0x180087969  lea     rax, aFido_0; "FIDO"
0x180087970  mov     [rbp+190h+var_70], rax
0x180087977  lea     rax, aAttributes_0; "attributes"
0x18008797e  mov     [rbp+190h+var_58], rax
0x180087985  mov     [rsp+290h+var_228], r12
0x18008798a  mov     [rsp+290h+var_220], r12
0x18008798f  mov     [rbp+190h+var_178], r12d
0x180087993  mov     [rbp+190h+var_174], 2000h
0x18008799a  mov     [rbp+190h+var_160], r12
0x18008799e  mov     [rbp+190h+var_158], r14
0x1800879a2  mov     [rbp+190h+var_88], edx
0x1800879a8  mov     [rbp+190h+var_84], 4000h
0x1800879b2  mov     [rbp+190h+var_78], 5
0x1800879bd  mov     [rbp+190h+var_68], 4
0x1800879c8  mov     [rbp+190h+var_60], 1
0x1800879d2  mov     [rbp+190h+var_5C], 8000h
0x1800879dc  mov     [rbp+190h+var_50], 0Ah
0x1800879e7  mov     [rbp+190h+var_48], rdx
0x1800879ee  mov     [rbp+190h+var_40], rdx
0x1800879f5  test    r10, r10
0x1800879f8  jz      short loc_1800879FD
0x1800879fa  mov     [r10], rdx
0x1800879fd  test    r9, r9
0x180087a00  jnz     short loc_180087A39
0x180087a02  lea     r8, aPbuffer; "pBuffer"
0x180087a09  mov     ebx, 80070057h
0x180087a0e  lea     rdx, aFidorequestser; "FidoRequestSerializer::CreatePostReques"...
0x180087a15  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180087a1c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087a21  lea     rdx, aPbuffer; "pBuffer"
0x180087a28  lea     rcx, aFidorequestser; "FidoRequestSerializer::CreatePostReques"...
0x180087a2f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180087a34  jmp     loc_1800882E6
0x180087a39  mov     [r9], rdx
0x180087a3c  test    rsi, rsi
0x180087a3f  jnz     short loc_180087A69
0x180087a41  lea     r8, aPkey; "pKey"
0x180087a48  mov     ebx, 80070057h
0x180087a4d  lea     rdx, aFidorequestser; "FidoRequestSerializer::CreatePostReques"...
0x180087a54  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180087a5b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087a60  lea     rdx, aPkey; "pKey"
0x180087a67  jmp     short loc_180087A28
0x180087a69  mov     rax, [rsi+18h]
0x180087a6d  mov     [rbp+190h+var_1D8], rax
0x180087a71  test    rax, rax
0x180087a74  jz      short loc_180087AB9
0x180087a76  lea     rdx, [rbp+190h+var_1D0]; unsigned __int64 *
0x180087a7a  mov     rcx, rax; unsigned __int16 *
0x180087a7d  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x180087a82  mov     ebx, eax
0x180087a84  test    eax, eax
0x180087a86  jns     short loc_180087AAA
0x180087a88  lea     r8, aStringlennulls; "StringLenNullSafe"
0x180087a8f  mov     r9d, eax
0x180087a92  lea     rdx, aFidorequestser; "FidoRequestSerializer::CreatePostReques"...
0x180087a99  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180087aa0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087aa5  jmp     loc_1800882E6
0x180087aaa  mov     rdx, [rbp+190h+var_1D0]
0x180087aae  mov     rax, [rbp+190h+var_1D8]
0x180087ab2  mov     r8, [rbp+190h+var_1E8]
0x180087ab6  mov     ecx, [rbp+190h+var_1EC]
0x180087ab9  test    ecx, ecx
0x180087abb  jz      short loc_180087ACF
0x180087abd  test    rax, rax
0x180087ac0  jz      loc_1800882CE
0x180087ac6  test    rdx, rdx
0x180087ac9  jz      loc_1800882CE
0x180087acf  mov     rcx, [rsi+10h]; unsigned __int16 *
0x180087ad3  test    rcx, rcx
0x180087ad6  jz      short loc_180087B16
0x180087ad8  lea     r8, [rsp+290h+lpMem]; unsigned __int16 **
0x180087add  xor     edx, edx; int
0x180087adf  call    ?EscapeStringForJson@@YAJPEBGHPEAPEAG@Z; EscapeStringForJson(ushort const *,int,ushort * *)
0x180087ae4  mov     ebx, eax
0x180087ae6  test    eax, eax
0x180087ae8  jns     short loc_180087B11
0x180087aea  mov     r9d, eax
0x180087aed  lea     r8, aEscapestringfo; "EscapeStringForJson"
0x180087af4  lea     rdx, aFidorequestser; "FidoRequestSerializer::CreatePostReques"...
0x180087afb  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180087b02  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087b07  mov     rdi, [rsp+290h+lpMem]
0x180087b0c  jmp     loc_1800882E6
0x180087b11  mov     rdi, [rsp+290h+lpMem]
0x180087b16  test    rdi, rdi
0x180087b19  jz      short loc_180087B31
0x180087b1b  lea     rdx, [rbp+190h+var_130]; unsigned __int64 *
0x180087b1f  mov     rcx, rdi; unsigned __int16 *
0x180087b22  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x180087b27  mov     ebx, eax
0x180087b29  test    eax, eax
0x180087b2b  js      loc_180087A88
0x180087b31  mov     rax, [rsi]
0x180087b34  mov     [rbp+190h+var_138], rdi
0x180087b38  xor     edi, edi
0x180087b3a  mov     [rsp+290h+lpMem], rdi
0x180087b3f  mov     rcx, [rax+8]; unsigned __int16 *
0x180087b43  mov     [rbp+190h+var_1B0], rcx
0x180087b47  test    rcx, rcx
0x180087b4a  jz      short loc_180087B6B
0x180087b4c  lea     rdx, [rbp+190h+var_1A8]; unsigned __int64 *
0x180087b50  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x180087b55  mov     ebx, eax
0x180087b57  test    eax, eax
0x180087b59  js      loc_180087A88
0x180087b5f  mov     rcx, [rbp+190h+var_1B0]
0x180087b63  mov     r13, [rbp+190h+var_1C0]
0x180087b67  mov     r15d, [rbp+190h+var_1C4]
0x180087b6b  test    r15d, r15d
0x180087b6e  jz      short loc_180087B83
0x180087b70  test    rcx, rcx
0x180087b73  jz      short loc_180087B7B
0x180087b75  cmp     [rbp+190h+var_1A8], rdi
0x180087b79  jnz     short loc_180087B83
0x180087b7b  mov     r8, r13
0x180087b7e  jmp     loc_1800882CE
0x180087b83  mov     rcx, [rsi]
0x180087b86  lea     rax, [rbp+190h+var_1F8]
0x180087b8a  mov     [rsp+290h+var_268], rdi; unsigned __int64
0x180087b8f  lea     r9, [rbp+190h+var_200]; unsigned __int16 **
0x180087b93  mov     [rsp+290h+var_270], rax; unsigned __int64 *
0x180087b98  mov     edx, [rcx+10h]; cbBinary
0x180087b9b  mov     rcx, [rcx+18h]; pbBinary
0x180087b9f  call    ?BinaryToString@@YAJPEBE_KKPEAPEAGPEA_K1@Z; BinaryToString(uchar const *,unsigned __int64,ulong,ushort * *,unsigned __int64 *,unsigned __int64)
0x180087ba4  mov     ebx, eax
0x180087ba6  test    eax, eax
0x180087ba8  jns     short loc_180087BD6
0x180087baa  mov     r9d, eax
0x180087bad  lea     r8, aBinarytobase64; "BinaryToBase64String"
0x180087bb4  lea     rdx, aFidokeyGetauth; "FidoKey::GetAuthenticatorDataBase64"
0x180087bbb  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180087bc2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087bc7  mov     r9d, ebx
0x180087bca  lea     r8, aFidokeyGetauth; "FidoKey::GetAuthenticatorDataBase64"
0x180087bd1  jmp     loc_180087A92
0x180087bd6  cmp     [rsp+290h+var_214], edi
0x180087bda  jz      short loc_180087BF1
0x180087bdc  cmp     [rbp+190h+var_200], rdi
0x180087be0  jz      short loc_180087BE8
0x180087be2  cmp     [rbp+190h+var_1F8], rdi
0x180087be6  jnz     short loc_180087BF1
0x180087be8  mov     r8, [rbp+190h+var_210]
0x180087bec  jmp     loc_1800882CE
0x180087bf1  mov     rax, [rsi]
0x180087bf4  mov     rcx, [rax+38h]
0x180087bf8  mov     rax, [rcx+8]
0x180087bfc  mov     [rbp+190h+var_188], rax
0x180087c00  test    rax, rax
0x180087c03  jz      short loc_180087C1F
0x180087c05  lea     rdx, [rbp+190h+var_180]; unsigned __int64 *
0x180087c09  mov     rcx, rax; unsigned __int16 *
0x180087c0c  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x180087c11  mov     ebx, eax
0x180087c13  test    eax, eax
0x180087c15  js      loc_180087A88
0x180087c1b  mov     rax, [rbp+190h+var_188]
0x180087c1f  cmp     [rbp+190h+var_19C], edi
0x180087c22  jz      short loc_180087C38
0x180087c24  test    rax, rax
0x180087c27  jz      short loc_180087C2F
0x180087c29  cmp     [rbp+190h+var_180], rdi
0x180087c2d  jnz     short loc_180087C38
0x180087c2f  mov     r8, [rbp+190h+var_198]
0x180087c33  jmp     loc_1800882CE
0x180087c38  mov     rax, [rsi]
0x180087c3b  lea     r9, [rsp+290h+var_228]; unsigned __int16 **
0x180087c40  mov     [rsp+290h+var_268], rdi; unsigned __int64
0x180087c45  mov     rcx, [rax+38h]
0x180087c49  lea     rax, [rsp+290h+var_220]
0x180087c4e  mov     [rsp+290h+var_270], rax; unsigned __int64 *
0x180087c53  mov     edx, [rcx+14h]; cbBinary
0x180087c56  mov     rcx, [rcx+18h]; pbBinary
0x180087c5a  call    ?BinaryToString@@YAJPEBE_KKPEAPEAGPEA_K1@Z; BinaryToString(uchar const *,unsigned __int64,ulong,ushort * *,unsigned __int64 *,unsigned __int64)
0x180087c5f  mov     ebx, eax
0x180087c61  test    eax, eax
0x180087c63  jns     short loc_180087C91
0x180087c65  mov     r9d, eax
0x180087c68  lea     r8, aBinarytobase64; "BinaryToBase64String"
0x180087c6f  lea     rdx, aFidokeyGetatte; "FidoKey::GetAttestationSignatureBase64"
0x180087c76  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180087c7d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087c82  mov     r9d, ebx
0x180087c85  lea     r8, aFidokeyGetatte; "FidoKey::GetAttestationSignatureBase64"
0x180087c8c  jmp     loc_180087A92
0x180087c91  cmp     dword ptr [rsp+290h+var_240+4], edi
0x180087c95  jz      short loc_180087CAF
0x180087c97  cmp     [rsp+290h+var_228], rdi
0x180087c9c  jz      short loc_180087CA5
0x180087c9e  cmp     [rsp+290h+var_220], rdi
0x180087ca3  jnz     short loc_180087CAF
0x180087ca5  mov     r8, [rsp+290h+var_238]
0x180087caa  jmp     loc_1800882CE
0x180087caf  xor     r15d, r15d
0x180087cb2  mov     rax, [rsi]
0x180087cb5  mov     rcx, [rax+38h]
0x180087cb9  cmp     r15d, [rcx+20h]
0x180087cbd  jnb     short loc_180087D03
  ... truncated ...
```
