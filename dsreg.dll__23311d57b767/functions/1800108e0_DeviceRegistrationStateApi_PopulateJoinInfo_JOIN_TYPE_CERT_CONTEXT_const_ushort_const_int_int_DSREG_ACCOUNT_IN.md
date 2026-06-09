# DeviceRegistrationStateApi::PopulateJoinInfo(_JOIN_TYPE,_CERT_CONTEXT const *,ushort const *,int,int,_DSREG_ACCOUNT_INFO_2 *)

- ea: `0x1800108e0`
- end: `0x180011fba`
- name: `?PopulateJoinInfo@DeviceRegistrationStateApi@@SAJW4_JOIN_TYPE@@PEBU_CERT_CONTEXT@@PEBGHHPEAU_DSREG_ACCOUNT_INFO_2@@@Z`
- size: `5850`
- prototype: `static int __high(enum _JOIN_TYPE, const struct _CERT_CONTEXT *, const unsigned __int16 *, int, int, struct _DSREG_ACCOUNT_INFO_2 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180009f10`
- `0x18000bac0`
- `0x18000c550`
- `0x18000d110`
- `0x18000fea8`
- `0x1800108e0`
- `0x180011fc0`
- `0x18001217c`
- `0x1800121a8`
- `0x180012980`
- `0x18001b560`
- `0x18001cf88`
- `0x180025db0`
- `0x1800307c4`
- `0x18003334c`
- `0x180043ef8`
- `0x180044300`
- `0x180044d30`
- `0x18004651c`
- `0x18004654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ae8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010c79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cba`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180011adc`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180011adc`
- `CRYPT32!CertFindExtension` at `0x180010b5d`
- `CRYPT32!CertFindExtension` at `0x180010b5d`
- `CRYPT32!CryptDecodeObjectEx` at `0x180010bbf`
- `CRYPT32!CryptDecodeObjectEx` at `0x180010bbf`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180010a93`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180010a93`
- `CRYPT32!CertFreeCertificateContext` at `0x180011ef8`
- `CRYPT32!CertFreeCertificateContext` at `0x180011ef8`
- `RPCRT4!UuidIsNil` at `0x180011a81`
- `RPCRT4!UuidIsNil` at `0x180011a81`
- `RPCRT4!RpcStringFreeW` at `0x180011f69`
- `RPCRT4!RpcStringFreeW` at `0x180011f69`
- `RPCRT4!UuidToStringW` at `0x180011e1c`
- `RPCRT4!UuidToStringW` at `0x180011e1c`

## string_xrefs

- `0x180010d3e`: `JoinStatusStorage::ReadJoinStatus`
- `0x180010b6f`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180010bd6`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180010c57`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180010b76`: `%s: Extension was not found in the certificate. OID: %hs.`
- `0x180011b41`: `StringCompare`
- `0x180011b48`: `StringCompare`
- `0x180011ba1`: `StringCompare`
- `0x180011ca7`: `StringCompare`
- `0x180011afc`: `CompareStringInternal`
- `0x180011af0`: `CompareStringEx`
- `0x180010ee5`: `CopyStringNullSafeW`
- `0x180010f38`: `CopyStringNullSafeW`
- `0x180010f8b`: `CopyStringNullSafeW`
- `0x180010fde`: `CopyStringNullSafeW`
- `0x180011031`: `CopyStringNullSafeW`
- `0x180011084`: `CopyStringNullSafeW`
- `0x1800110d7`: `CopyStringNullSafeW`
- `0x18001112a`: `CopyStringNullSafeW`
- `0x18001117d`: `CopyStringNullSafeW`
- `0x1800111d0`: `CopyStringNullSafeW`
- `0x180011226`: `CopyStringNullSafeW`
- `0x18001127c`: `CopyStringNullSafeW`
- `0x1800112d2`: `CopyStringNullSafeW`
- `0x180011328`: `CopyStringNullSafeW`
- `0x180011381`: `CopyStringNullSafeW`
- `0x1800113da`: `CopyStringNullSafeW`
- `0x180011433`: `CopyStringNullSafeW`
- `0x18001148c`: `CopyStringNullSafeW`
- `0x1800114e5`: `CopyStringNullSafeW`
- `0x18001153e`: `CopyStringNullSafeW`
- `0x180011597`: `CopyStringNullSafeW`
- `0x1800115f0`: `CopyStringNullSafeW`
- `0x180011649`: `CopyStringNullSafeW`
- `0x1800116a2`: `CopyStringNullSafeW`
- `0x1800116fb`: `CopyStringNullSafeW`
- `0x18001177d`: `CopyStringNullSafeW`
- `0x1800117d6`: `CopyStringNullSafeW`
- `0x18001182f`: `CopyStringNullSafeW`
- `0x1800118a9`: `CopyStringNullSafeW`
- `0x180011902`: `CopyStringNullSafeW`
- `0x18001195b`: `CopyStringNullSafeW`
- `0x1800119b4`: `CopyStringNullSafeW`
- `0x180011a1d`: `CopyStringNullSafeW`
- `0x180011d91`: `CopyStringNullSafeW`
- `0x180011de4`: `CopyStringNullSafeW`
- `0x180011e84`: `CopyStringNullSafeW`

## pseudocode

```c
__int64 __fastcall DeviceRegistrationStateApi::PopulateJoinInfo(
        unsigned int a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 *a3,
        int a4,
        int a5,
        __int64 a6)
{
  void *v6; // r13
  signed int JoinStatus; // ebx
  __int128 *v10; // rax
  __int128 *v11; // rcx
  __int64 v12; // rdx
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  const CERT_CONTEXT *v25; // r14
  signed int LastError; // eax
  __int64 v27; // r8
  NgcStatusStorage *v28; // r12
  struct_join_status *v29; // rdi
  int TenantId; // eax
  __int64 v31; // r9
  const unsigned __int16 *v32; // r8
  PCERT_INFO pCertInfo; // rdx
  PCERT_EXTENSION Extension; // rax
  void *v35; // rcx
  int v36; // eax
  struct_join_status *v37; // rax
  const wchar_t *v38; // rax
  const wchar_t *v39; // rax
  __int64 v40; // rax
  unsigned int v41; // ecx
  __int128 v42; // xmm1
  __m128i v43; // xmm2
  __m128i v44; // xmm3
  __int128 v45; // xmm0
  __int64 v46; // xmm1_8
  int v47; // r14d
  void *v48; // r15
  bool v49; // zf
  const wchar_t *v50; // rax
  const wchar_t *v51; // rax
  const wchar_t *v52; // rax
  const wchar_t *v53; // rax
  const wchar_t *v54; // rax
  const wchar_t *v55; // rax
  const wchar_t *v56; // rax
  const wchar_t *v57; // rax
  const wchar_t *v58; // rax
  const wchar_t *v59; // rax
  const wchar_t *v60; // rax
  const wchar_t *v61; // rax
  const wchar_t *v62; // rax
  const wchar_t *v63; // rax
  const wchar_t *v64; // rax
  const wchar_t *v65; // rax
  const wchar_t *v66; // rax
  const wchar_t *v67; // rax
  const wchar_t *v68; // rax
  const wchar_t *v69; // rax
  const wchar_t *v70; // rax
  const wchar_t *v71; // rax
  const wchar_t *v72; // rax
  const wchar_t *v73; // rax
  const wchar_t *v74; // rax
  _WORD *v75; // rax
  BOOL v76; // eax
  const wchar_t *v77; // rax
  const wchar_t *v78; // rax
  const wchar_t *v79; // rax
  const wchar_t *v80; // rax
  const wchar_t *v81; // rax
  const wchar_t *v82; // rax
  const wchar_t *v83; // rax
  const wchar_t *v84; // rax
  const WCHAR *v85; // r8
  const WCHAR *v86; // rcx
  int v87; // ecx
  int v88; // ecx
  int v89; // eax
  const wchar_t *v90; // rax
  const wchar_t *v91; // r9
  unsigned __int16 *v92; // r8
  wchar_t *v93; // rcx
  unsigned __int16 *v94; // r14
  const WCHAR *v95; // rcx
  const unsigned __int16 *v96; // rdx
  const wchar_t *v97; // rax
  _QWORD *v98; // rax
  unsigned int v99; // edx
  unsigned __int16 **v100; // rdx
  const unsigned __int16 *v101; // rcx
  const wchar_t *v102; // rax
  const wchar_t *v103; // rax
  unsigned int v104; // eax
  int v105; // r14d
  const wchar_t *v106; // rax
  void *v108; // [rsp+58h] [rbp-B0h]
  int v110; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v111; // [rsp+68h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-90h] BYREF
  RPC_WSTR StringUuid; // [rsp+80h] [rbp-88h] BYREF
  DWORD pcbStructInfo; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int16 *v116; // [rsp+90h] [rbp-78h]
  _BYTE v117[48]; // [rsp+9Ch] [rbp-6Ch]
  _BYTE v118[28]; // [rsp+FCh] [rbp-Ch] BYREF
  _BYTE v119[336]; // [rsp+118h] [rbp+10h] BYREF
  UUID v120[4]; // [rsp+268h] [rbp+160h] BYREF
  UUID Uuid; // [rsp+2A8h] [rbp+1A0h] BYREF

  v6 = 0;
  v116 = a3;
  LODWORD(v111) = a1;
  *(_QWORD *)&Uuid.Data1 = 0;
  StringUuid = 0;
  memset(v120, 0, sizeof(v120));
  v110 = 0;
  if ( !a6 )
  {
    JoinStatus = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceRegistrationStateApi::PopulateJoinInfo", L"pJoinInfo");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceRegistrationStateApi::PopulateJoinInfo", L"pJoinInfo");
LABEL_13:
    operator delete(0);
    operator delete(0);
    goto LABEL_259;
  }
  memset_0(v119, 0, sizeof(v119));
  v10 = (__int128 *)a6;
  v11 = (__int128 *)v119;
  v12 = 2;
  do
  {
    v10 += 8;
    v13 = *v11;
    v14 = v11[1];
    v11 += 8;
    *(v10 - 8) = v13;
    v15 = *(v11 - 6);
    *(v10 - 7) = v14;
    v16 = *(v11 - 5);
    *(v10 - 6) = v15;
    v17 = *(v11 - 4);
    *(v10 - 5) = v16;
    v18 = *(v11 - 3);
    *(v10 - 4) = v17;
    v19 = *(v11 - 2);
    *(v10 - 3) = v18;
    v20 = *(v11 - 1);
    *(v10 - 2) = v19;
    *(v10 - 1) = v20;
    --v12;
  }
  while ( v12 );
  v21 = v11[1];
  *v10 = *v11;
  v22 = v11[2];
  v10[1] = v21;
  v23 = v11[3];
  v10[2] = v22;
  v24 = v11[4];
  v10[3] = v23;
  v10[4] = v24;
  if ( !a2 )
  {
    JoinStatus = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"pCertContext");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceRegistrationStateApi::PopulateJoinInfo", L"pCertContext");
    goto LABEL_13;
  }
  if ( ((a1 - 1) & 0xFFFFFFFB) != 0 )
  {
    JoinStatus = -2147024809;
    Logger::TraceError(
      L"%s: Invalid join type %d. Only DEVICE and WORKPLACE are allowed.",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      a1);
    goto LABEL_13;
  }
  v25 = CertDuplicateCertificateContext(a2);
  if ( !v25 )
  {
    LastError = GetLastError();
    JoinStatus = LastError;
    if ( LastError > 0 )
      JoinStatus = (unsigned __int16)LastError | 0x80070000;
    v27 = GetLastError();
    Logger::TraceError(
      L"%s: CertDuplicateCertificateContext failed with error code: 0x%08x",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      v27);
    goto LABEL_13;
  }
  v28 = 0;
  v29 = 0;
  TenantId = RegistrationCertStatus::GetTenantId(a2, (unsigned __int16 **)&Uuid, &v110);
  JoinStatus = TenantId;
  if ( TenantId < 0 )
  {
    v31 = (unsigned int)TenantId;
    v32 = L"RegistrationCertStatus::GetTenantId";
LABEL_16:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      v32,
      v31);
LABEL_252:
    CertFreeCertificateContext(v25);
    v48 = *(void **)&Uuid.Data1;
    goto LABEL_255;
  }
  pCertInfo = a2->pCertInfo;
  hMem = 0;
  JoinStatus = 0;
  pcbStructInfo = 0;
  Block = 0;
  v108 = 0;
  Extension = CertFindExtension("1.2.840.113556.1.5.284.2", pCertInfo->cExtension, pCertInfo->rgExtension);
  if ( !Extension )
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      "1.2.840.113556.1.5.284.2");
    v35 = 0;
    JoinStatus = -2146885628;
LABEL_28:
    operator delete(v35);
    LocalFree(hMem);
    Logger::TraceVerbose(
      (wchar_t *)L"%s - hr: 0x%08x",
      L"RegistrationCertStatus::GetDeviceId",
      (unsigned int)JoinStatus);
LABEL_29:
    v31 = (unsigned int)JoinStatus;
    v32 = L"RegistrationCertStatus::GetDeviceId";
    goto LABEL_16;
  }
  if ( CryptDecodeObjectEx(
         a2->dwCertEncodingType,
         (LPCSTR)0x19,
         Extension->Value.pbData,
         Extension->Value.cbData,
         0x8000u,
         0,
         &hMem,
         &pcbStructInfo) )
  {
    v36 = CertificateUtil::GuidStringFromByteArray(
            *((const unsigned __int8 **)hMem + 1),
            *(_DWORD *)hMem,
            (unsigned __int16 **)&Block);
    JoinStatus = v36;
    if ( v36 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        L"CertificateUtil::GuidStringFromByteArray",
        (unsigned int)v36);
      v35 = Block;
      goto LABEL_28;
    }
    v6 = Block;
    v108 = Block;
    operator delete(0);
    LocalFree(hMem);
    Logger::TraceVerbose(
      (wchar_t *)L"%s - hr: 0x%08x",
      L"RegistrationCertStatus::GetDeviceId",
      (unsigned int)JoinStatus);
  }
  else
  {
    LODWORD(Block) = GetLastError();
    Logger::TraceError(
      L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      (unsigned int)Block);
    if ( (_DWORD)Block )
    {
      if ( (int)Block > 0 )
        JoinStatus = (unsigned __int16)Block | 0x80070000;
      else
        JoinStatus = (int)Block;
    }
    operator delete(0);
    LocalFree(hMem);
    Logger::TraceVerbose(
      (wchar_t *)L"%s - hr: 0x%08x",
      L"RegistrationCertStatus::GetDeviceId",
      (unsigned int)JoinStatus);
    if ( JoinStatus < 0 )
      goto LABEL_29;
  }
  v37 = (struct_join_status *)operator new(0x140u, (const struct std::nothrow_t *)&std::nothrow);
  v29 = v37;
  if ( !v37 )
  {
    v29 = 0;
    goto LABEL_250;
  }
  struct_join_status::Clear(v37);
  JoinStatus = JoinStatusStorage::ReadJoinStatus(v111 == 1, a2, a4, v29, a5);
  if ( JoinStatus < 0 )
  {
    v38 = L"TRUE";
    if ( !a4 )
      v38 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"JoinStatusStorage::ReadJoinStatus",
      (unsigned int)JoinStatus,
      v38);
    if ( !a4 )
      goto LABEL_251;
  }
  v28 = (NgcStatusStorage *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v28 )
  {
    v28 = 0;
LABEL_250:
    JoinStatus = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
LABEL_251:
    v6 = v108;
    goto LABEL_252;
  }
  *(_QWORD *)v28 = 0;
  *((_QWORD *)v28 + 1) = 0;
  JoinStatus = NgcStatusStorage::Load(v28);
  if ( JoinStatus < 0 )
  {
    v39 = L"TRUE";
    if ( !a4 )
      v39 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"NgcStatusStorage::Load",
      (unsigned int)JoinStatus,
      v39);
    if ( !a4 )
      goto LABEL_251;
  }
  if ( *((_QWORD *)v28 + 1) && (v40 = *(_QWORD *)v28) != 0 )
  {
    v41 = *(_DWORD *)v40;
    v42 = *(_OWORD *)(v40 + 36);
    v43 = *(__m128i *)(v40 + 4);
    v44 = *(__m128i *)(v40 + 48);
    *(_OWORD *)&v117[16] = *(_OWORD *)(v40 + 20);
    *(_OWORD *)&v117[32] = v42;
  }
  else
  {
    v43 = 0;
    v44 = 0;
    memset(v118, 0, sizeof(v118));
    v41 = 0;
    *(_OWORD *)&v117[16] = 0;
    *(_OWORD *)&v117[32] = *(_OWORD *)v118;
  }
  v45 = *(_OWORD *)&v117[20];
  *(_QWORD *)(a6 + 8) = v25;
  v46 = *(_QWORD *)&v117[36];
  *(__m128i *)v117 = v43;
  *(_QWORD *)&v120[1].Data1 = *(_QWORD *)&v117[12];
  *(_QWORD *)&v120[0].Data2 = v43.m128i_i64[0];
  *(_QWORD *)&v120[3].Data1 = v44.m128i_i64[0];
  *(_DWORD *)a6 = ((_DWORD)v111 != 1) + 1;
  v47 = 0;
  v48 = 0;
  v49 = v110 == 0;
  *(_QWORD *)(a6 + 32) = *(_QWORD *)&Uuid.Data1;
  *(_DWORD *)(a6 + 60) = !v49;
  v120[0].Data1 = v41;
  *(_DWORD *)&v120[0].Data4[4] = _mm_cvtsi128_si32(_mm_srli_si128(v43, 8));
  *(_OWORD *)v120[1].Data4 = v45;
  *(_QWORD *)(a6 + 16) = v6;
  *(_QWORD *)v120[2].Data4 = v46;
  *(_QWORD *)v120[3].Data4 = _mm_srli_si128(v44, 8).m128i_u64[0];
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 1), (unsigned __int16 **)(a6 + 24));
  if ( JoinStatus < 0 )
  {
    v50 = L"TRUE";
    if ( !a4 )
      v50 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v50);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 3), (unsigned __int16 **)(a6 + 40));
  if ( JoinStatus < 0 )
  {
    v51 = L"TRUE";
    if ( !a4 )
      v51 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v51);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 4), (unsigned __int16 **)(a6 + 64));
  if ( JoinStatus < 0 )
  {
    v52 = L"TRUE";
    if ( !a4 )
      v52 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v52);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 5), (unsigned __int16 **)(a6 + 72));
  if ( JoinStatus < 0 )
  {
    v53 = L"TRUE";
    if ( !a4 )
      v53 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v53);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 6), (unsigned __int16 **)(a6 + 80));
  if ( JoinStatus < 0 )
  {
    v54 = L"TRUE";
    if ( !a4 )
      v54 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v54);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 7), (unsigned __int16 **)(a6 + 88));
  if ( JoinStatus < 0 )
  {
    v55 = L"TRUE";
    if ( !a4 )
      v55 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v55);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 8), (unsigned __int16 **)(a6 + 96));
  if ( JoinStatus < 0 )
  {
    v56 = L"TRUE";
    if ( !a4 )
      v56 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v56);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 9), (unsigned __int16 **)(a6 + 104));
  if ( JoinStatus < 0 )
  {
    v57 = L"TRUE";
    if ( !a4 )
      v57 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v57);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 10), (unsigned __int16 **)(a6 + 112));
  if ( JoinStatus < 0 )
  {
    v58 = L"TRUE";
    if ( !a4 )
      v58 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v58);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 11), (unsigned __int16 **)(a6 + 120));
  if ( JoinStatus < 0 )
  {
    v59 = L"TRUE";
    if ( !a4 )
      v59 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v59);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 12), (unsigned __int16 **)(a6 + 128));
  if ( JoinStatus < 0 )
  {
    v60 = L"TRUE";
    if ( !a4 )
      v60 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v60);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 13), (unsigned __int16 **)(a6 + 136));
  if ( JoinStatus < 0 )
  {
    v61 = L"TRUE";
    if ( !a4 )
      v61 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v61);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 14), (unsigned __int16 **)(a6 + 144));
  if ( JoinStatus < 0 )
  {
    v62 = L"TRUE";
    if ( !a4 )
      v62 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v62);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 15), (unsigned __int16 **)(a6 + 152));
  if ( JoinStatus < 0 )
  {
    v63 = L"TRUE";
    if ( !a4 )
      v63 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v63);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 16), (unsigned __int16 **)(a6 + 160));
  if ( JoinStatus < 0 )
  {
    v64 = L"TRUE";
    if ( !a4 )
      v64 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v64);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 17), (unsigned __int16 **)(a6 + 168));
  if ( JoinStatus < 0 )
  {
    v65 = L"TRUE";
    if ( !a4 )
      v65 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v65);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 18), (unsigned __int16 **)(a6 + 176));
  if ( JoinStatus < 0 )
  {
    v66 = L"TRUE";
    if ( !a4 )
      v66 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v66);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 19), (unsigned __int16 **)(a6 + 184));
  if ( JoinStatus < 0 )
  {
    v67 = L"TRUE";
    if ( !a4 )
      v67 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v67);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 20), (unsigned __int16 **)(a6 + 192));
  if ( JoinStatus < 0 )
  {
    v68 = L"TRUE";
    if ( !a4 )
      v68 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v68);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 21), (unsigned __int16 **)(a6 + 200));
  if ( JoinStatus < 0 )
  {
    v69 = L"TRUE";
    if ( !a4 )
      v69 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v69);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 22), (unsigned __int16 **)(a6 + 208));
  if ( JoinStatus < 0 )
  {
    v70 = L"TRUE";
    if ( !a4 )
      v70 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v70);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 23), (unsigned __int16 **)(a6 + 216));
  if ( JoinStatus < 0 )
  {
    v71 = L"TRUE";
    if ( !a4 )
      v71 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v71);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 24), (unsigned __int16 **)(a6 + 224));
  if ( JoinStatus < 0 )
  {
    v72 = L"TRUE";
    if ( !a4 )
      v72 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v72);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 25), (unsigned __int16 **)(a6 + 232));
  if ( JoinStatus < 0 )
  {
    v73 = L"TRUE";
    if ( !a4 )
      v73 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v73);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 28), (unsigned __int16 **)(a6 + 240));
  if ( JoinStatus < 0 )
  {
    v74 = L"TRUE";
    if ( !a4 )
      v74 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v74);
    if ( !a4 )
      goto LABEL_254;
  }
  *(_DWORD *)(a6 + 248) = 0;
  v75 = (_WORD *)*((_QWORD *)v29 + 29);
  v76 = v75 && *v75;
  *(_DWORD *)(a6 + 248) = v76;
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 30), (unsigned __int16 **)(a6 + 256));
  if ( JoinStatus < 0 )
  {
    v77 = L"TRUE";
    if ( !a4 )
      v77 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v77);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 31), (unsigned __int16 **)(a6 + 264));
  if ( JoinStatus < 0 )
  {
    v78 = L"TRUE";
    if ( !a4 )
      v78 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v78);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 34), (unsigned __int16 **)(a6 + 288));
  if ( JoinStatus < 0 )
  {
    v79 = L"TRUE";
    if ( !a4 )
      v79 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v79);
    if ( !a4 )
      goto LABEL_254;
  }
  *(_DWORD *)(a6 + 272) = *((_DWORD *)v29 + 64) != 0;
  *(_QWORD *)(a6 + 280) = *((_QWORD *)v29 + 33);
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 35), (unsigned __int16 **)(a6 + 296));
  if ( JoinStatus < 0 )
  {
    v80 = L"TRUE";
    if ( !a4 )
      v80 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v80);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 36), (unsigned __int16 **)(a6 + 304));
  if ( JoinStatus < 0 )
  {
    v81 = L"TRUE";
    if ( !a4 )
      v81 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v81);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 37), (unsigned __int16 **)(a6 + 312));
  if ( JoinStatus < 0 )
  {
    v82 = L"TRUE";
    if ( !a4 )
      v82 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v82);
    if ( !a4 )
      goto LABEL_254;
  }
  JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 38), (unsigned __int16 **)(a6 + 320));
  if ( JoinStatus < 0 )
  {
    v83 = L"TRUE";
    if ( !a4 )
      v83 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v83);
    if ( !a4 )
      goto LABEL_254;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
  {
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v29 + 39), (unsigned __int16 **)(a6 + 328));
    if ( JoinStatus < 0 )
    {
      v84 = L"TRUE";
      if ( !a4 )
        v84 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v84);
      if ( !a4 )
      {
LABEL_254:
        v6 = 0;
        goto LABEL_255;
      }
    }
  }
  Uuid = v120[0];
  v6 = 0;
  LODWORD(Block) = 0;
  if ( UuidIsNil(&Uuid, (RPC_STATUS *)&Block) )
    goto LABEL_207;
  v85 = *(const WCHAR **)(a6 + 32);
  v86 = &cchOriginalDestLength;
  v110 = 0;
  if ( *(_QWORD *)&v120[3].Data1 )
    v86 = *(const WCHAR **)&v120[3].Data1;
  JoinStatus = 0;
  v87 = CompareStringEx(&cchOriginalDestLength, 1u, v85, -1, v86, -1, 0, 0, 0);
  if ( v87 )
  {
    if ( v87 == 3 )
    {
      v89 = 3;
    }
    else
    {
      v88 = v87 - 1;
      if ( v88 )
      {
        if ( v88 != 1 )
        {
          LOWORD(JoinStatus) = 1359;
LABEL_194:
          JoinStatus = (unsigned __int16)JoinStatus | 0x80070000;
          goto LABEL_195;
        }
        v89 = 2;
      }
      else
      {
        v89 = 1;
      }
    }
    LOBYTE(v47) = v89 == 2;
    v110 = v47;
    goto LABEL_203;
  }
  JoinStatus = GetLastError();
  if ( !JoinStatus )
    JoinStatus = 1359;
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"CompareStringInternal",
    L"CompareStringEx",
    (unsigned int)JoinStatus);
  if ( JoinStatus > 0 )
    goto LABEL_194;
LABEL_195:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"StringCompare",
    L"StringCompare",
    (unsigned int)JoinStatus);
  v90 = L"TRUE";
  if ( !a4 )
    v90 = L"FALSE";
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
    L"DeviceRegistrationStateApi::PopulateJoinInfo",
    L"StringCompare",
    (unsigned int)JoinStatus,
    v90);
  if ( !a4 )
    goto LABEL_255;
LABEL_203:
  if ( !v47 )
  {
    v91 = L"<NULL>";
    v92 = *(unsigned __int16 **)(a6 + 32);
    v93 = (wchar_t *)L"%s: The NGC key is not for the given tenant %s. Key tenant: %s. Return no key.";
    if ( *(_QWORD *)&v120[3].Data1 )
      v91 = *(const wchar_t **)&v120[3].Data1;
LABEL_206:
    Logger::TraceVerbose(v93, L"DeviceRegistrationStateApi::PopulateJoinInfo", v92, v91);
    goto LABEL_207;
  }
  v94 = v116;
  if ( (unsigned int)IsEmptyString(v116) )
  {
    if ( (_DWORD)v111 == 5 )
    {
      v94 = *(unsigned __int16 **)(a6 + 40);
      v116 = v94;
      if ( !(unsigned int)IsEmptyString(v94) )
        Logger::TraceVerbose(
          (wchar_t *)L"%s: No explicit UPN given. Using the work account's UPN for matching. UPN: %s.",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          v94);
    }
  }
  if ( !(unsigned int)IsEmptyString(v94) )
  {
    v96 = &cchOriginalDestLength;
    if ( *(_QWORD *)v120[3].Data4 )
      v96 = *(const unsigned __int16 **)v120[3].Data4;
    JoinStatus = StringCompare(v95, v96, 1u, &v110);
    if ( JoinStatus >= 0 )
    {
LABEL_221:
      if ( !v110 )
      {
        v91 = L"<NULL>";
        v92 = v94;
        v93 = L"%s: The NGC key is not for the given UPN %s. Key UPN: %s. Return no key.";
        if ( *(_QWORD *)v120[3].Data4 )
          v91 = *(const wchar_t **)v120[3].Data4;
        goto LABEL_206;
      }
      goto LABEL_225;
    }
    v97 = L"TRUE";
    if ( !a4 )
      v97 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"StringCompare",
      (unsigned int)JoinStatus,
      v97);
    if ( a4 )
    {
      v94 = v116;
      goto LABEL_221;
    }
LABEL_255:
    operator delete(v48);
    operator delete(v6);
    if ( !v29 )
      goto LABEL_257;
    goto LABEL_256;
  }
LABEL_225:
  v98 = operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)(a6 + 48) = v98;
  if ( !v98 )
  {
    JoinStatus = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
    goto LABEL_227;
  }
  *(_OWORD *)v98 = 0;
  v98[2] = 0;
  v100 = *(unsigned __int16 ***)(a6 + 48);
  v101 = *(const unsigned __int16 **)v120[3].Data4;
  *(_DWORD *)(a6 + 56) = 1;
  JoinStatus = CopyStringNullSafeW(v101, v100);
  if ( JoinStatus < 0 )
  {
    v102 = L"TRUE";
    if ( !a4 )
      v102 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v102);
    if ( !a4 )
      goto LABEL_253;
  }
  JoinStatus = CopyStringNullSafeW(
                 *(const unsigned __int16 **)&v120[1].Data1,
                 (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 16LL));
  if ( JoinStatus < 0 )
  {
    v103 = L"TRUE";
    if ( !a4 )
      v103 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v103);
    if ( !a4 )
    {
LABEL_253:
      v6 = 0;
      goto LABEL_255;
    }
  }
  v104 = UuidToStringW(v120, &StringUuid);
  LODWORD(v6) = v104;
  if ( v104 )
  {
    Logger::TraceError(
      L"%s: UuidToStringW failed with RPC_STATUS error code: 0x%08x",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      v104);
    v105 = a4;
    if ( !a4 )
    {
LABEL_245:
      if ( (int)v6 > 0 )
        JoinStatus = (unsigned __int16)v6 | 0x80070000;
      else
        JoinStatus = (int)v6;
      goto LABEL_227;
    }
  }
  else
  {
    v105 = a4;
  }
  JoinStatus = CopyStringNullSafeW(StringUuid, (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 8LL));
  if ( JoinStatus < 0 )
  {
    v106 = L"TRUE";
    if ( !v105 )
      v106 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      L"CopyStringNullSafeW",
      (unsigned int)JoinStatus,
      v106);
    if ( v105 )
      goto LABEL_208;
LABEL_244:
    if ( (_DWORD)v6 )
      goto LABEL_245;
    goto LABEL_253;
  }
LABEL_207:
  if ( !a4 )
    goto LABEL_244;
LABEL_208:
  JoinStatus = 0;
LABEL_227:
  operator delete(0);
  operator delete(0);
LABEL_256:
  struct_join_status::`scalar deleting destructor'(v29, v99);
LABEL_257:
  if ( v28 )
    NgcStatusStorage::`scalar deleting destructor'(v28, v99);
LABEL_259:
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( JoinStatus < 0 )
    DsrFreeAccountInfoContent(a6);
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"DeviceRegistrationStateApi::PopulateJoinInfo",
    (unsigned int)JoinStatus);
  return (unsigned int)JoinStatus;
}

```

## disassembly

```asm
0x1800108e0  mov     r11, rsp
0x1800108e3  push    rbp
0x1800108e4  push    rbx
0x1800108e5  push    rsi
0x1800108e6  lea     rbp, [r11-208h]
0x1800108ed  sub     rsp, 2F0h
0x1800108f4  mov     rax, cs:__security_cookie
0x1800108fb  xor     rax, rsp
0x1800108fe  mov     [rbp+200h+var_50], rax
0x180010905  mov     rsi, [rbp+200h+arg_28]
0x18001090c  xorps   xmm0, xmm0
0x18001090f  mov     [r11-20h], rdi
0x180010913  mov     [r11-30h], r13
0x180010917  xor     r13d, r13d
0x18001091a  mov     [r11-38h], r14
0x18001091e  mov     r14d, ecx
0x180010921  mov     [r11-40h], r15
0x180010925  mov     r15, rdx
0x180010928  mov     [rsp+300h+var_2A8], r9d
0x18001092d  mov     [rbp+200h+var_278], r8
0x180010931  mov     dword ptr [rsp+300h+var_2A0], ecx
0x180010935  mov     qword ptr [rbp+200h+Uuid.Data1], r13
0x18001093c  mov     [rsp+300h+StringUuid], r13
0x180010941  mov     [rbp+200h+var_A0.Data1], r13d
0x180010948  mov     [rsp+300h+var_2A4], r13d
0x18001094d  movups  xmmword ptr [rbp+200h+lpString2], xmm0
0x180010954  movups  xmmword ptr [rbp+200h+var_A0.Data2], xmm0
0x18001095b  movups  [rbp+200h+var_8C], xmm0
0x180010962  movups  xmmword ptr [rbp+200h+lpString2+0Ch], xmm0
0x180010969  test    rsi, rsi
0x18001096c  jnz     short loc_1800109A5
0x18001096e  lea     r8, aPjoininfo; "pJoinInfo"
0x180010975  mov     ebx, 80070057h
0x18001097a  lea     rdx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x180010981  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180010988  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001098d  lea     rdx, aPjoininfo; "pJoinInfo"
0x180010994  lea     rcx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x18001099b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800109a0  jmp     loc_180010AD2
0x1800109a5  xor     edx, edx; Val
0x1800109a7  lea     rcx, [rbp+200h+var_1F0]; void *
0x1800109ab  mov     r8d, 150h; Size
0x1800109b1  call    memset_0
0x1800109b6  mov     rax, rsi
0x1800109b9  lea     rcx, [rbp+200h+var_1F0]
0x1800109bd  mov     edx, 2
0x1800109c2  lea     rax, [rax+80h]
0x1800109c9  movups  xmm0, xmmword ptr [rcx]
0x1800109cc  movups  xmm1, xmmword ptr [rcx+10h]
0x1800109d0  lea     rcx, [rcx+80h]
0x1800109d7  movups  xmmword ptr [rax-80h], xmm0
0x1800109db  movups  xmm0, xmmword ptr [rcx-60h]
0x1800109df  movups  xmmword ptr [rax-70h], xmm1
0x1800109e3  movups  xmm1, xmmword ptr [rcx-50h]
0x1800109e7  movups  xmmword ptr [rax-60h], xmm0
0x1800109eb  movups  xmm0, xmmword ptr [rcx-40h]
0x1800109ef  movups  xmmword ptr [rax-50h], xmm1
0x1800109f3  movups  xmm1, xmmword ptr [rcx-30h]
0x1800109f7  movups  xmmword ptr [rax-40h], xmm0
0x1800109fb  movups  xmm0, xmmword ptr [rcx-20h]
0x1800109ff  movups  xmmword ptr [rax-30h], xmm1
0x180010a03  movups  xmm1, xmmword ptr [rcx-10h]
0x180010a07  movups  xmmword ptr [rax-20h], xmm0
0x180010a0b  movups  xmmword ptr [rax-10h], xmm1
0x180010a0f  sub     rdx, 1
0x180010a13  jnz     short loc_1800109C2
0x180010a15  movups  xmm0, xmmword ptr [rcx]
0x180010a18  movups  xmm1, xmmword ptr [rcx+10h]
0x180010a1c  movups  xmmword ptr [rax], xmm0
0x180010a1f  movups  xmm0, xmmword ptr [rcx+20h]
0x180010a23  movups  xmmword ptr [rax+10h], xmm1
0x180010a27  movups  xmm1, xmmword ptr [rcx+30h]
0x180010a2b  movups  xmmword ptr [rax+20h], xmm0
0x180010a2f  movups  xmm0, xmmword ptr [rcx+40h]
0x180010a33  movups  xmmword ptr [rax+30h], xmm1
0x180010a37  movups  xmmword ptr [rax+40h], xmm0
0x180010a3b  test    r15, r15
0x180010a3e  jnz     short loc_180010A74
0x180010a40  lea     r8, aPcertcontext; "pCertContext"
0x180010a47  mov     ebx, 80070057h
0x180010a4c  lea     rdx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x180010a53  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180010a5a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010a5f  lea     rdx, aPcertcontext; "pCertContext"
0x180010a66  lea     rcx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x180010a6d  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180010a72  jmp     short loc_180010AD2
0x180010a74  lea     eax, [r14-1]
0x180010a78  test    eax, 0FFFFFFFBh
0x180010a7d  jz      short loc_180010A90
0x180010a7f  mov     ebx, 80070057h
0x180010a84  lea     rcx, aSInvalidJoinTy_0; "%s: Invalid join type %d. Only DEVICE a"...
0x180010a8b  mov     r8d, r14d
0x180010a8e  jmp     short loc_180010AC6
0x180010a90  mov     rcx, r15; pCertContext
0x180010a93  call    cs:__imp_CertDuplicateCertificateContext
0x180010a99  mov     r14, rax
0x180010a9c  test    rax, rax
0x180010a9f  jnz     short loc_180010AE6
0x180010aa1  call    cs:__imp_GetLastError
0x180010aa7  mov     ebx, eax
0x180010aa9  test    eax, eax
0x180010aab  jle     short loc_180010AB6
0x180010aad  movzx   ebx, ax
0x180010ab0  or      ebx, 80070000h
0x180010ab6  call    cs:__imp_GetLastError
0x180010abc  mov     r8d, eax
0x180010abf  lea     rcx, aSCertduplicate; "%s: CertDuplicateCertificateContext fai"...
0x180010ac6  lea     rdx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x180010acd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010ad2  mov     rcx, r13; Block
0x180010ad5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010ada  xor     ecx, ecx; Block
0x180010adc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010ae1  jmp     loc_180011F44
0x180010ae6  mov     [rsp+300h+var_20], r12
0x180010aee  lea     r8, [rsp+300h+var_2A4]; int *
0x180010af3  lea     rdx, [rbp+200h+Uuid]; unsigned __int16 **
0x180010afa  mov     rcx, r15; struct _CERT_CONTEXT *
0x180010afd  mov     r12, r13
0x180010b00  mov     rdi, r13
0x180010b03  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x180010b08  mov     ebx, eax
0x180010b0a  test    eax, eax
0x180010b0c  jns     short loc_180010B30
0x180010b0e  mov     r9d, eax
0x180010b11  lea     r8, aRegistrationce_21; "RegistrationCertStatus::GetTenantId"
0x180010b18  lea     rdx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x180010b1f  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180010b26  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010b2b  jmp     loc_180011EF5
0x180010b30  mov     rdx, [r15+18h]
0x180010b34  lea     rcx, pszObjId; "1.2.840.113556.1.5.284.2"
0x180010b3b  mov     [rsp+300h+hMem], r13
0x180010b40  xor     ebx, ebx
0x180010b42  mov     [rbp+200h+var_280], r13d
0x180010b46  mov     [rsp+300h+Block], r13
0x180010b4b  mov     r8, [rdx+0C8h]; rgExtensions
0x180010b52  mov     edx, [rdx+0C0h]; cExtensions
0x180010b58  mov     qword ptr [rsp+300h+var_2B0], rbx
0x180010b5d  call    cs:__imp_CertFindExtension
0x180010b63  test    rax, rax
0x180010b66  jnz     short loc_180010B8F
0x180010b68  lea     r8, pszObjId; "1.2.840.113556.1.5.284.2"
0x180010b6f  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x180010b76  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180010b7d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180010b82  mov     rcx, r13
0x180010b85  mov     ebx, 80092004h
0x180010b8a  jmp     loc_180010C6F
0x180010b8f  mov     r9d, [rax+10h]; cbEncoded
0x180010b93  lea     rcx, [rbp+200h+var_280]
0x180010b97  mov     r8, [rax+18h]; pbEncoded
0x180010b9b  mov     edx, 19h; lpszStructType
0x180010ba0  mov     [rsp+300h+pcbStructInfo], rcx; pcbStructInfo
0x180010ba5  lea     rcx, [rsp+300h+hMem]
0x180010baa  mov     [rsp+300h+pvStructInfo], rcx; pvStructInfo
0x180010baf  mov     ecx, [r15]; dwCertEncodingType
0x180010bb2  mov     [rsp+300h+pDecodePara], rbx; pDecodePara
0x180010bb7  mov     [rsp+300h+dwFlags], 8000h; dwFlags
0x180010bbf  call    cs:__imp_CryptDecodeObjectEx
0x180010bc5  test    eax, eax
0x180010bc7  jnz     short loc_180010C32
0x180010bc9  call    cs:__imp_GetLastError
0x180010bcf  mov     r8d, eax
0x180010bd2  mov     dword ptr [rsp+300h+Block], eax
0x180010bd6  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x180010bdd  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x180010be4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010be9  mov     eax, dword ptr [rsp+300h+Block]
0x180010bed  test    eax, eax
0x180010bef  jz      short loc_180010C00
0x180010bf1  jg      short loc_180010BF7
0x180010bf3  mov     ebx, eax
0x180010bf5  jmp     short loc_180010C00
0x180010bf7  movzx   ebx, ax
0x180010bfa  or      ebx, 80070000h
0x180010c00  mov     rcx, r13; Block
0x180010c03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010c08  mov     rcx, [rsp+300h+hMem]; hMem
0x180010c0d  call    cs:__imp_LocalFree
0x180010c13  mov     r8d, ebx
0x180010c16  lea     rdx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x180010c1d  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180010c24  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180010c29  test    ebx, ebx
0x180010c2b  js      short loc_180010C95
0x180010c2d  jmp     loc_180010CD6
0x180010c32  mov     rcx, [rsp+300h+hMem]
0x180010c37  lea     r8, [rsp+300h+Block]; unsigned __int16 **
0x180010c3c  mov     edx, [rcx]; unsigned int
0x180010c3e  mov     rcx, [rcx+8]; unsigned __int8 *
0x180010c42  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x180010c47  mov     ebx, eax
0x180010c49  test    eax, eax
0x180010c4b  jns     short loc_180010CA4
0x180010c4d  mov     r9d, eax
0x180010c50  lea     r8, aCertificateuti_4; "CertificateUtil::GuidStringFromByteArra"...
0x180010c57  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionGuidValue"...
0x180010c5e  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180010c65  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010c6a  mov     rcx, [rsp+300h+Block]; Block
0x180010c6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010c74  mov     rcx, [rsp+300h+hMem]; hMem
0x180010c79  call    cs:__imp_LocalFree
0x180010c7f  mov     r8d, ebx
0x180010c82  lea     rdx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x180010c89  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180010c90  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180010c95  mov     r9d, ebx
0x180010c98  lea     r8, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x180010c9f  jmp     loc_180010B18
0x180010ca4  mov     r13, [rsp+300h+Block]
0x180010ca9  xor     ecx, ecx; Block
0x180010cab  mov     qword ptr [rsp+300h+var_2B0], r13
0x180010cb0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010cb5  mov     rcx, [rsp+300h+hMem]; hMem
0x180010cba  call    cs:__imp_LocalFree
0x180010cc0  mov     r8d, ebx
0x180010cc3  lea     rdx, aRegistrationce_24; "RegistrationCertStatus::GetDeviceId"
0x180010cca  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180010cd1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180010cd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010cdd  mov     ecx, 140h; unsigned __int64
0x180010ce2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010ce7  mov     rdi, rax
0x180010cea  test    rax, rax
0x180010ced  jz      loc_180011ED6
0x180010cf3  mov     rcx, rax; this
0x180010cf6  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x180010cfb  mov     eax, [rbp+200h+arg_20]
0x180010d01  xor     ecx, ecx
0x180010d03  cmp     dword ptr [rsp+300h+var_2A0], 1
0x180010d08  mov     r9, rdi; struct struct_join_status *
0x180010d0b  mov     r8d, [rsp+300h+var_2A8]; int
0x180010d10  mov     rdx, r15; struct _CERT_CONTEXT *
0x180010d13  setz    cl; int
0x180010d16  mov     [rsp+300h+dwFlags], eax; int
0x180010d1a  call    ?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z; JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)
0x180010d1f  mov     r15d, [rsp+300h+var_2A8]
0x180010d24  mov     ebx, eax
0x180010d26  lea     rcx, aFalse_0; "FALSE"
0x180010d2d  test    eax, eax
0x180010d2f  jns     short loc_180010D6A
0x180010d31  test    r15d, r15d
0x180010d34  lea     rax, aTrue_0; "TRUE"
0x180010d3b  mov     r9d, ebx
0x180010d3e  lea     r8, aJoinstatusstor_8; "JoinStatusStorage::ReadJoinStatus"
0x180010d45  cmovz   rax, rcx
0x180010d49  lea     rdx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x180010d50  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x. "...
0x180010d57  mov     qword ptr [rsp+300h+dwFlags], rax
0x180010d5c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010d61  test    r15d, r15d
0x180010d64  jz      loc_180011EF0
0x180010d6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010d71  mov     ecx, 10h; unsigned __int64
0x180010d76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010d7b  mov     r12, rax
0x180010d7e  test    rax, rax
0x180010d81  jz      loc_180011ED1
0x180010d87  xor     eax, eax
0x180010d89  mov     rcx, r12; this
0x180010d8c  mov     [r12], rax
0x180010d90  mov     [r12+8], rax
0x180010d95  call    ?Load@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Load(void)
0x180010d9a  mov     ebx, eax
0x180010d9c  test    eax, eax
0x180010d9e  jns     short loc_180010DE0
0x180010da0  lea     rcx, aFalse_0; "FALSE"
0x180010da7  test    r15d, r15d
0x180010daa  lea     rax, aTrue_0; "TRUE"
0x180010db1  mov     r9d, ebx
0x180010db4  cmovz   rax, rcx
0x180010db8  lea     r8, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x180010dbf  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x. "...
0x180010dc6  mov     qword ptr [rsp+300h+dwFlags], rax
0x180010dcb  lea     rdx, aDeviceregistra_3; "DeviceRegistrationStateApi::PopulateJoi"...
0x180010dd2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010dd7  test    r15d, r15d
0x180010dda  jz      loc_180011EF0
0x180010de0  cmp     qword ptr [r12+8], 0
0x180010de6  jbe     short loc_180010E0D
0x180010de8  mov     rax, [r12]
0x180010dec  test    rax, rax
0x180010def  jz      short loc_180010E0D
0x180010df1  movups  xmm0, xmmword ptr [rax+14h]
0x180010df5  mov     ecx, [rax]
0x180010df7  movups  xmm1, xmmword ptr [rax+24h]
0x180010dfb  movups  xmm2, xmmword ptr [rax+4]
0x180010dff  movups  xmm3, xmmword ptr [rax+30h]
0x180010e03  movups  [rbp+200h+var_25C], xmm0
0x180010e07  movups  [rbp+200h+var_24C], xmm1
0x180010e0b  jmp     short loc_180010E29
0x180010e0d  xorps   xmm2, xmm2
0x180010e10  xorps   xmm3, xmm3
0x180010e13  movups  xmmword ptr [rbp+200h+var_20C], xmm2
0x180010e17  xor     ecx, ecx
0x180010e19  movaps  xmmword ptr [rbp+200h+var_20C+0Ch], xmm3
  ... truncated ...
```
