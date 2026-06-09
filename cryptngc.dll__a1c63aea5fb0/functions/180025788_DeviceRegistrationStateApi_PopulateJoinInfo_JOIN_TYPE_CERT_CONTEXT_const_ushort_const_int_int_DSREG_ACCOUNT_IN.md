# DeviceRegistrationStateApi::PopulateJoinInfo(_JOIN_TYPE,_CERT_CONTEXT const *,ushort const *,int,int,_DSREG_ACCOUNT_INFO_2 *)

- ea: `0x180025788`
- end: `0x180026a0e`
- name: `?PopulateJoinInfo@DeviceRegistrationStateApi@@SAJW4_JOIN_TYPE@@PEBU_CERT_CONTEXT@@PEBGHHPEAU_DSREG_ACCOUNT_INFO_2@@@Z`
- size: `4742`
- prototype: `static int __high(enum _JOIN_TYPE, const struct _CERT_CONTEXT *, const unsigned __int16 *, int, int, struct _DSREG_ACCOUNT_INFO_2 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006980`

## callees

- `0x1800073c0`
- `0x180008ad0`
- `0x180008f74`
- `0x180009f5c`
- `0x18000c190`
- `0x18000c3e8`
- `0x18000d240`
- `0x18000f520`
- `0x180017580`
- `0x18001b38c`
- `0x180025788`
- `0x180027278`
- `0x180027448`
- `0x18002918c`
- `0x18002aee4`
- `0x18002baa8`
- `0x18002bc58`
- `0x18002cccc`
- `0x18002e664`
- `0x18002e850`
- `0x18002f6ec`
- `0x18002f710`
- `0x180044870`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002596d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002596d`
- `RPCRT4!RpcStringFreeW` at `0x1800269bc`
- `RPCRT4!RpcStringFreeW` at `0x1800269bc`
- `RPCRT4!UuidToStringW` at `0x180026897`
- `RPCRT4!UuidToStringW` at `0x180026897`
- `CRYPT32!CertFreeCertificateContext` at `0x180026973`
- `CRYPT32!CertFreeCertificateContext` at `0x180026973`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180025948`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180025948`

## string_xrefs

- `0x180025a3c`: `JoinStatusStorage::ReadJoinStatus`
- `0x18002665c`: `StringCompare`
- `0x18002673a`: `StringCompare`
- `0x180025b83`: `CopyStringNullSafeW`
- `0x180025bcf`: `CopyStringNullSafeW`
- `0x180025c1b`: `CopyStringNullSafeW`
- `0x180025c67`: `CopyStringNullSafeW`
- `0x180025cb3`: `CopyStringNullSafeW`
- `0x180025cff`: `CopyStringNullSafeW`
- `0x180025d4b`: `CopyStringNullSafeW`
- `0x180025d97`: `CopyStringNullSafeW`
- `0x180025de3`: `CopyStringNullSafeW`
- `0x180025e2f`: `CopyStringNullSafeW`
- `0x180025e7e`: `CopyStringNullSafeW`
- `0x180025ecd`: `CopyStringNullSafeW`
- `0x180025f1c`: `CopyStringNullSafeW`
- `0x180025f6b`: `CopyStringNullSafeW`
- `0x180025fbd`: `CopyStringNullSafeW`
- `0x18002600f`: `CopyStringNullSafeW`
- `0x180026061`: `CopyStringNullSafeW`
- `0x1800260b3`: `CopyStringNullSafeW`
- `0x180026105`: `CopyStringNullSafeW`
- `0x180026157`: `CopyStringNullSafeW`
- `0x1800261a9`: `CopyStringNullSafeW`
- `0x1800261fb`: `CopyStringNullSafeW`
- `0x18002624d`: `CopyStringNullSafeW`
- `0x18002629f`: `CopyStringNullSafeW`
- `0x1800262f1`: `CopyStringNullSafeW`
- `0x18002636a`: `CopyStringNullSafeW`
- `0x1800263bc`: `CopyStringNullSafeW`
- `0x18002640e`: `CopyStringNullSafeW`
- `0x180026482`: `CopyStringNullSafeW`
- `0x1800264d4`: `CopyStringNullSafeW`
- `0x180026526`: `CopyStringNullSafeW`
- `0x180026578`: `CopyStringNullSafeW`
- `0x1800265da`: `CopyStringNullSafeW`
- `0x18002680d`: `CopyStringNullSafeW`
- `0x180026860`: `CopyStringNullSafeW`
- `0x1800268e4`: `CopyStringNullSafeW`

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
  struct_join_status *v9; // rbx
  NgcStatusStorage *v10; // rsi
  int JoinStatus; // edi
  const unsigned __int16 *v12; // rdx
  void *v13; // rcx
  __int64 v14; // rdx
  _OWORD *v15; // rcx
  _OWORD *v16; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  const unsigned __int16 *v28; // rcx
  __int64 v29; // r8
  signed int LastError; // eax
  int TenantId; // eax
  const unsigned __int16 *v32; // r8
  struct_join_status *v33; // rax
  const wchar_t *v34; // r13
  const wchar_t *v35; // rax
  NgcStatusStorage *v36; // rax
  const wchar_t *v37; // rax
  __int64 Key; // rax
  UUID v39; // xmm0
  const wchar_t *v40; // rax
  const wchar_t *v41; // rax
  const wchar_t *v42; // rax
  const wchar_t *v43; // rax
  const wchar_t *v44; // rax
  const wchar_t *v45; // rax
  const wchar_t *v46; // rax
  const wchar_t *v47; // rax
  const wchar_t *v48; // rax
  const wchar_t *v49; // rax
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
  unsigned int v73; // r8d
  const unsigned __int16 *v74; // rcx
  const unsigned __int16 *v75; // rdx
  const wchar_t *v76; // rax
  const wchar_t *v77; // r9
  unsigned __int16 *v78; // rcx
  const unsigned __int16 *v79; // rcx
  unsigned int v80; // r8d
  const unsigned __int16 *v81; // rdx
  const wchar_t *v82; // rax
  const wchar_t *v83; // r9
  _QWORD *v84; // rax
  unsigned __int16 **v85; // rdx
  const unsigned __int16 *v86; // rcx
  const wchar_t *v87; // rax
  const wchar_t *v88; // rax
  unsigned int v89; // eax
  unsigned int v90; // edx
  int v92; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v94; // [rsp+48h] [rbp-B8h]
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v96; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v97; // [rsp+60h] [rbp-A0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+68h] [rbp-98h]
  _BYTE v99[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v100[336]; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid[4]; // [rsp+200h] [rbp+100h] BYREF

  v96 = a3;
  v94 = a1;
  Block = 0;
  v97 = 0;
  StringUuid = 0;
  v9 = 0;
  memset(Uuid, 0, sizeof(Uuid));
  v10 = 0;
  v92 = 0;
  if ( !a6 )
  {
    JoinStatus = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceRegistrationStateApi::PopulateJoinInfo", L"pJoinInfo");
    v12 = L"pJoinInfo";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceRegistrationStateApi::PopulateJoinInfo", v12);
LABEL_4:
    v13 = 0;
    goto LABEL_216;
  }
  memset_0(v100, 0, sizeof(v100));
  v14 = 2;
  v15 = v100;
  v16 = (_OWORD *)a6;
  do
  {
    v17 = v15[1];
    *v16 = *v15;
    v18 = v15[2];
    v16[1] = v17;
    v19 = v15[3];
    v16[2] = v18;
    v20 = v15[4];
    v16[3] = v19;
    v21 = v15[5];
    v16[4] = v20;
    v22 = v15[6];
    v16[5] = v21;
    v23 = v15[7];
    v15 += 8;
    v16[6] = v22;
    v16[7] = v23;
    v16 += 8;
    --v14;
  }
  while ( v14 );
  v24 = v15[1];
  *v16 = *v15;
  v25 = v15[2];
  v16[1] = v24;
  v26 = v15[3];
  v16[2] = v25;
  v27 = v15[4];
  v16[3] = v26;
  v16[4] = v27;
  if ( !a2 )
  {
    JoinStatus = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      &stru_1800542A8);
    v12 = (const unsigned __int16 *)&stru_1800542A8;
    goto LABEL_3;
  }
  if ( ((a1 - 1) & 0xFFFFFFFB) != 0 )
  {
    JoinStatus = -2147024809;
    v28 = L"%s: Invalid join type %d. Only DEVICE and WORKPLACE are allowed.";
    v29 = a1;
LABEL_11:
    Logger::TraceError(v28, L"DeviceRegistrationStateApi::PopulateJoinInfo", v29);
    goto LABEL_4;
  }
  pCertContext = CertDuplicateCertificateContext(a2);
  if ( !pCertContext )
  {
    LastError = GetLastError();
    JoinStatus = LastError;
    if ( LastError > 0 )
      JoinStatus = (unsigned __int16)LastError | 0x80070000;
    v29 = GetLastError();
    v28 = L"%s: CertDuplicateCertificateContext failed with error code: 0x%08x";
    goto LABEL_11;
  }
  TenantId = RegistrationCertStatus::GetTenantId(a2, (unsigned __int16 **)&Block, &v92);
  JoinStatus = TenantId;
  if ( TenantId >= 0 )
  {
    TenantId = RegistrationCertStatus::GetDeviceId(a2, &v97);
    JoinStatus = TenantId;
    if ( TenantId < 0 )
    {
      v32 = L"RegistrationCertStatus::GetDeviceId";
      goto LABEL_18;
    }
    v33 = (struct_join_status *)operator new(0x140u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v33;
    if ( !v33 )
    {
      JoinStatus = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
      v9 = 0;
      goto LABEL_215;
    }
    struct_join_status::Clear(v33);
    JoinStatus = JoinStatusStorage::ReadJoinStatus(a1 == 1, a2, a4, v9, a5);
    v34 = L"TRUE";
    if ( JoinStatus < 0 )
    {
      v35 = L"TRUE";
      if ( !a4 )
        v35 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"JoinStatusStorage::ReadJoinStatus",
        (unsigned int)JoinStatus,
        v35);
      if ( !a4 )
        goto LABEL_215;
    }
    v36 = (NgcStatusStorage *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v36;
    if ( !v36 )
    {
      JoinStatus = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
      v10 = 0;
      goto LABEL_215;
    }
    *(_QWORD *)v36 = 0;
    *((_QWORD *)v36 + 1) = 0;
    JoinStatus = NgcStatusStorage::Load(v36);
    if ( JoinStatus < 0 )
    {
      v37 = L"TRUE";
      if ( !a4 )
        v37 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"NgcStatusStorage::Load",
        (unsigned int)JoinStatus,
        v37);
      if ( !a4 )
        goto LABEL_215;
    }
    Key = NgcStatusStorage::GetKey(v10, v99);
    Uuid[0] = *(UUID *)Key;
    Uuid[1] = *(UUID *)(Key + 16);
    Uuid[2] = *(UUID *)(Key + 32);
    v39 = *(UUID *)(Key + 48);
    *(_QWORD *)(a6 + 8) = pCertContext;
    Uuid[3] = v39;
    *(_DWORD *)a6 = (v94 != 1) + 1;
    *(_QWORD *)(a6 + 16) = v97;
    *(_QWORD *)(a6 + 32) = Block;
    v97 = 0;
    *(_DWORD *)(a6 + 60) = v92 != 0;
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 1), (unsigned __int16 **)(a6 + 24));
    if ( JoinStatus < 0 )
    {
      v40 = L"TRUE";
      if ( !a4 )
        v40 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v40);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 3), (unsigned __int16 **)(a6 + 40));
    if ( JoinStatus < 0 )
    {
      v41 = L"TRUE";
      if ( !a4 )
        v41 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v41);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 4), (unsigned __int16 **)(a6 + 64));
    if ( JoinStatus < 0 )
    {
      v42 = L"TRUE";
      if ( !a4 )
        v42 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v42);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 5), (unsigned __int16 **)(a6 + 72));
    if ( JoinStatus < 0 )
    {
      v43 = L"TRUE";
      if ( !a4 )
        v43 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v43);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 6), (unsigned __int16 **)(a6 + 80));
    if ( JoinStatus < 0 )
    {
      v44 = L"TRUE";
      if ( !a4 )
        v44 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v44);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 7), (unsigned __int16 **)(a6 + 88));
    if ( JoinStatus < 0 )
    {
      v45 = L"TRUE";
      if ( !a4 )
        v45 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v45);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 8), (unsigned __int16 **)(a6 + 96));
    if ( JoinStatus < 0 )
    {
      v46 = L"TRUE";
      if ( !a4 )
        v46 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v46);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 9), (unsigned __int16 **)(a6 + 104));
    if ( JoinStatus < 0 )
    {
      v47 = L"TRUE";
      if ( !a4 )
        v47 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v47);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 10), (unsigned __int16 **)(a6 + 112));
    if ( JoinStatus < 0 )
    {
      v48 = L"TRUE";
      if ( !a4 )
        v48 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v48);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 11), (unsigned __int16 **)(a6 + 120));
    if ( JoinStatus < 0 )
    {
      v49 = L"TRUE";
      if ( !a4 )
        v49 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v49);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 12), (unsigned __int16 **)(a6 + 128));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 13), (unsigned __int16 **)(a6 + 136));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 14), (unsigned __int16 **)(a6 + 144));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 15), (unsigned __int16 **)(a6 + 152));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 16), (unsigned __int16 **)(a6 + 160));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 17), (unsigned __int16 **)(a6 + 168));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 18), (unsigned __int16 **)(a6 + 176));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 19), (unsigned __int16 **)(a6 + 184));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 20), (unsigned __int16 **)(a6 + 192));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 21), (unsigned __int16 **)(a6 + 200));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 22), (unsigned __int16 **)(a6 + 208));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 23), (unsigned __int16 **)(a6 + 216));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 24), (unsigned __int16 **)(a6 + 224));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 25), (unsigned __int16 **)(a6 + 232));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 28), (unsigned __int16 **)(a6 + 240));
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
        goto LABEL_4;
    }
    *(_DWORD *)(a6 + 248) = 0;
    *(_DWORD *)(a6 + 248) = IsEmptyString(*((const unsigned __int16 **)v9 + 29)) == 0;
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 30), (unsigned __int16 **)(a6 + 256));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 31), (unsigned __int16 **)(a6 + 264));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 34), (unsigned __int16 **)(a6 + 288));
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
        goto LABEL_4;
    }
    *(_DWORD *)(a6 + 272) = *((_DWORD *)v9 + 64) != 0;
    *(_QWORD *)(a6 + 280) = *((_QWORD *)v9 + 33);
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 35), (unsigned __int16 **)(a6 + 296));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 36), (unsigned __int16 **)(a6 + 304));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 37), (unsigned __int16 **)(a6 + 312));
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
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 38), (unsigned __int16 **)(a6 + 320));
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
        goto LABEL_4;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
    {
      JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 39), (unsigned __int16 **)(a6 + 328));
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
          goto LABEL_4;
      }
    }
    v92 = 0;
    if ( (unsigned int)NgcStatusStorage::IsKeyIdEmpty(Uuid) )
      goto LABEL_207;
    v74 = *(const unsigned __int16 **)(a6 + 32);
    v75 = &LocaleName;
    LODWORD(Block) = 0;
    if ( *(_QWORD *)&Uuid[3].Data1 )
      v75 = *(const unsigned __int16 **)&Uuid[3].Data1;
    JoinStatus = StringCompare(v74, v75, v73, (int *)&Block);
    if ( JoinStatus < 0 )
    {
      v76 = L"TRUE";
      if ( !a4 )
        v76 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"StringCompare",
        (unsigned int)JoinStatus,
        v76);
      if ( !a4 )
        goto LABEL_4;
    }
    if ( !(_DWORD)Block )
    {
      v77 = L"<NULL>";
      if ( *(_QWORD *)&Uuid[3].Data1 )
        v77 = *(const wchar_t **)&Uuid[3].Data1;
      Logger::TraceVerbose(
        L"%s: The NGC key is not for the given tenant %s. Key tenant: %s. Return no key.",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        *(_QWORD *)(a6 + 32),
        v77);
      goto LABEL_207;
    }
    if ( (unsigned int)IsEmptyString(v96) )
    {
      if ( v94 == 5 )
      {
        v96 = *(unsigned __int16 **)(a6 + 40);
        if ( !(unsigned int)IsEmptyString(v96) )
        {
          Logger::TraceVerbose(
            L"%s: No explicit UPN given. Using the work account's UPN for matching. UPN: %s.",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            v78);
          v78 = v96;
        }
      }
    }
    if ( !(unsigned int)IsEmptyString(v78) )
    {
      v81 = &LocaleName;
      if ( *(_QWORD *)Uuid[3].Data4 )
        v81 = *(const unsigned __int16 **)Uuid[3].Data4;
      JoinStatus = StringCompare(v79, v81, v80, (int *)&Block);
      if ( JoinStatus < 0 )
      {
        v82 = L"TRUE";
        if ( !a4 )
          v82 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"StringCompare",
          (unsigned int)JoinStatus,
          v82);
        if ( !a4 )
          goto LABEL_4;
      }
      if ( (_DWORD)Block )
      {
LABEL_191:
        v84 = operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
        *(_QWORD *)(a6 + 48) = v84;
        if ( !v84 )
        {
          JoinStatus = -2147024882;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed.",
            L"DeviceRegistrationStateApi::PopulateJoinInfo");
          goto LABEL_4;
        }
        *(_OWORD *)v84 = 0;
        v84[2] = 0;
        v85 = *(unsigned __int16 ***)(a6 + 48);
        v86 = *(const unsigned __int16 **)Uuid[3].Data4;
        *(_DWORD *)(a6 + 56) = 1;
        JoinStatus = CopyStringNullSafeW(v86, v85);
        if ( JoinStatus < 0 )
        {
          v87 = L"TRUE";
          if ( !a4 )
            v87 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"CopyStringNullSafeW",
            (unsigned int)JoinStatus,
            v87);
          if ( !a4 )
            goto LABEL_4;
        }
        JoinStatus = CopyStringNullSafeW(
                       *(const unsigned __int16 **)&Uuid[1].Data1,
                       (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 16LL));
        if ( JoinStatus < 0 )
        {
          v88 = L"TRUE";
          if ( !a4 )
            v88 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"CopyStringNullSafeW",
            (unsigned int)JoinStatus,
            v88);
          if ( !a4 )
            goto LABEL_4;
        }
        v89 = UuidToStringW(Uuid, &StringUuid);
        v92 = v89;
        JoinStatus = v89;
        if ( v89 )
        {
          Logger::TraceError(
            L"%s: UuidToStringW failed with RPC_STATUS error code: 0x%08x",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            v89);
          if ( !a4 )
          {
LABEL_211:
            if ( JoinStatus > 0 )
              JoinStatus = (unsigned __int16)JoinStatus | 0x80070000;
            goto LABEL_4;
          }
        }
        JoinStatus = CopyStringNullSafeW(StringUuid, (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 8LL));
        if ( JoinStatus < 0 )
        {
          if ( !a4 )
            v34 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"CopyStringNullSafeW",
            (unsigned int)JoinStatus,
            v34);
          if ( !a4 )
          {
LABEL_209:
            if ( !v92 )
              goto LABEL_4;
            JoinStatus = v92;
            goto LABEL_211;
          }
        }
LABEL_207:
        if ( a4 )
        {
          JoinStatus = 0;
          goto LABEL_4;
        }
        goto LABEL_209;
      }
      v83 = L"<NULL>";
      if ( *(_QWORD *)Uuid[3].Data4 )
        v83 = *(const wchar_t **)Uuid[3].Data4;
      Logger::TraceVerbose(
        L"%s: The NGC key is not for the given UPN %s. Key UPN: %s. Return no key.",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        v96,
        v83);
    }
    if ( !(_DWORD)Block )
      goto LABEL_207;
    goto LABEL_191;
  }
  v32 = L"RegistrationCertStatus::GetTenantId";
LABEL_18:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"DeviceRegistrationStateApi::PopulateJoinInfo",
    v32,
    (unsigned int)TenantId);
LABEL_215:
  CertFreeCertificateContext(pCertContext);
  v13 = Block;
LABEL_216:
  operator delete(v13);
  operator delete(v97);
  if ( v9 )
    struct_join_status::`scalar deleting destructor'(v9, v90);
  if ( v10 )
  {
    NgcStatusStorage::Cleanup(v10);
    operator delete(v10);
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( JoinStatus < 0 )
    DsrFreeAccountInfoContent(a6);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"DeviceRegistrationStateApi::PopulateJoinInfo", (unsigned int)JoinStatus);
  return (unsigned int)JoinStatus;
}

```

## disassembly

```asm
0x180025788  push    rbp
0x18002578a  push    rbx
0x18002578b  push    rsi
0x18002578c  push    rdi
0x18002578d  push    r12
0x18002578f  push    r13
0x180025791  push    r14
0x180025793  push    r15
0x180025795  lea     rbp, [rsp-158h]
0x18002579d  sub     rsp, 258h
0x1800257a4  mov     rax, cs:__security_cookie
0x1800257ab  xor     rax, rsp
0x1800257ae  mov     [rbp+190h+var_50], rax
0x1800257b5  mov     r12, [rbp+190h+arg_28]
0x1800257bc  xor     edi, edi
0x1800257be  mov     [rsp+290h+var_238], r8
0x1800257c3  xorps   xmm0, xmm0
0x1800257c6  mov     [rsp+290h+var_248], ecx
0x1800257ca  mov     eax, edi
0x1800257cc  mov     [rsp+290h+var_260], rax
0x1800257d1  mov     r14d, r9d
0x1800257d4  mov     [rsp+290h+Block], rax
0x1800257d9  mov     r15, rdx
0x1800257dc  mov     [rsp+290h+var_230], rdi
0x1800257e1  mov     r13d, ecx
0x1800257e4  mov     [rsp+290h+StringUuid], rdi
0x1800257e9  mov     ebx, edi
0x1800257eb  mov     [rbp+190h+Uuid.Data1], edi
0x1800257f1  mov     esi, edi
0x1800257f3  mov     [rsp+290h+var_258], edi
0x1800257f7  movups  xmmword ptr [rbp+190h+var_6C], xmm0
0x1800257fe  movups  xmmword ptr [rbp+190h+Uuid.Data2], xmm0
0x180025805  movups  [rbp+190h+var_7C], xmm0
0x18002580c  movups  xmmword ptr [rbp+190h+var_6C+0Ch], xmm0
0x180025813  test    r12, r12
0x180025816  jnz     short loc_180025853
0x180025818  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18002581f  mov     edi, 80070057h
0x180025824  mov     rdx, r15
0x180025827  lea     r8, aPjoininfo; "pJoinInfo"
0x18002582e  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180025835  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002583a  lea     rdx, aPjoininfo; "pJoinInfo"
0x180025841  mov     rcx, r15; unsigned __int16 *
0x180025844  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180025849  mov     rcx, [rsp+290h+var_260]
0x18002584e  jmp     loc_18002697E
0x180025853  xor     edx, edx; Val
0x180025855  lea     rcx, [rbp+190h+var_1E0]; void *
0x180025859  mov     r8d, 150h; Size
0x18002585f  call    memset_0
0x180025864  mov     edx, 2
0x180025869  lea     rcx, [rbp+190h+var_1E0]
0x18002586d  mov     rax, r12
0x180025870  lea     r8d, [rdx+7Eh]
0x180025874  movups  xmm0, xmmword ptr [rcx]
0x180025877  movups  xmm1, xmmword ptr [rcx+10h]
0x18002587b  movups  xmmword ptr [rax], xmm0
0x18002587e  movups  xmm0, xmmword ptr [rcx+20h]
0x180025882  movups  xmmword ptr [rax+10h], xmm1
0x180025886  movups  xmm1, xmmword ptr [rcx+30h]
0x18002588a  movups  xmmword ptr [rax+20h], xmm0
0x18002588e  movups  xmm0, xmmword ptr [rcx+40h]
0x180025892  movups  xmmword ptr [rax+30h], xmm1
0x180025896  movups  xmm1, xmmword ptr [rcx+50h]
0x18002589a  movups  xmmword ptr [rax+40h], xmm0
0x18002589e  movups  xmm0, xmmword ptr [rcx+60h]
0x1800258a2  movups  xmmword ptr [rax+50h], xmm1
0x1800258a6  movups  xmm1, xmmword ptr [rcx+70h]
0x1800258aa  add     rcx, r8
0x1800258ad  movups  xmmword ptr [rax+60h], xmm0
0x1800258b1  movups  xmmword ptr [rax+70h], xmm1
0x1800258b5  add     rax, r8
0x1800258b8  sub     rdx, 1
0x1800258bc  jnz     short loc_180025874
0x1800258be  movups  xmm0, xmmword ptr [rcx]
0x1800258c1  movups  xmm1, xmmword ptr [rcx+10h]
0x1800258c5  movups  xmmword ptr [rax], xmm0
0x1800258c8  movups  xmm0, xmmword ptr [rcx+20h]
0x1800258cc  movups  xmmword ptr [rax+10h], xmm1
0x1800258d0  movups  xmm1, xmmword ptr [rcx+30h]
0x1800258d4  movups  xmmword ptr [rax+20h], xmm0
0x1800258d8  movups  xmm0, xmmword ptr [rcx+40h]
0x1800258dc  movups  xmmword ptr [rax+30h], xmm1
0x1800258e0  movups  xmmword ptr [rax+40h], xmm0
0x1800258e4  test    r15, r15
0x1800258e7  jnz     short loc_180025917
0x1800258e9  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x1800258f0  mov     edi, 80070057h
0x1800258f5  mov     rdx, r15
0x1800258f8  lea     r8, stru_1800542A8
0x1800258ff  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180025906  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002590b  lea     rdx, stru_1800542A8
0x180025912  jmp     loc_180025841
0x180025917  lea     eax, [r13-1]
0x18002591b  test    eax, 0FFFFFFFBh
0x180025920  jz      short loc_180025945
0x180025922  mov     edi, 80070057h
0x180025927  lea     rcx, aSInvalidJoinTy; "%s: Invalid join type %d. Only DEVICE a"...
0x18002592e  mov     r8d, r13d
0x180025931  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x180025938  mov     rdx, r15
0x18002593b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025940  jmp     loc_180025849
0x180025945  mov     rcx, r15; pCertContext
0x180025948  call    cs:__imp_CertDuplicateCertificateContext
0x18002594e  mov     [rsp+290h+pCertContext], rax
0x180025953  test    rax, rax
0x180025956  jnz     short loc_18002597F
0x180025958  call    cs:__imp_GetLastError
0x18002595e  mov     edi, eax
0x180025960  test    eax, eax
0x180025962  jle     short loc_18002596D
0x180025964  movzx   edi, ax
0x180025967  or      edi, 80070000h
0x18002596d  call    cs:__imp_GetLastError
0x180025973  mov     r8d, eax
0x180025976  lea     rcx, aSCertduplicate; "%s: CertDuplicateCertificateContext fai"...
0x18002597d  jmp     short loc_180025931
0x18002597f  lea     r8, [rsp+290h+var_258]; int *
0x180025984  mov     rcx, r15; struct _CERT_CONTEXT *
0x180025987  lea     rdx, [rsp+290h+Block]; unsigned __int16 **
0x18002598c  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x180025991  mov     edi, eax
0x180025993  test    eax, eax
0x180025995  jns     short loc_1800259BC
0x180025997  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x18002599e  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x1800259a5  mov     r9d, eax
0x1800259a8  mov     rdx, r15
0x1800259ab  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800259b2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800259b7  jmp     loc_18002696E
0x1800259bc  lea     rdx, [rsp+290h+var_230]; unsigned __int16 **
0x1800259c1  mov     rcx, r15; struct _CERT_CONTEXT *
0x1800259c4  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x1800259c9  mov     edi, eax
0x1800259cb  test    eax, eax
0x1800259cd  jns     short loc_1800259D8
0x1800259cf  lea     r8, aRegistrationce_4; "RegistrationCertStatus::GetDeviceId"
0x1800259d6  jmp     short loc_18002599E
0x1800259d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800259df  mov     ecx, 140h; unsigned __int64
0x1800259e4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800259e9  mov     rbx, rax
0x1800259ec  test    rax, rax
0x1800259ef  jz      loc_180026951
0x1800259f5  mov     rcx, rax; this
0x1800259f8  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x1800259fd  mov     eax, [rbp+190h+arg_20]
0x180025a03  xor     ecx, ecx
0x180025a05  cmp     r13d, 1
0x180025a09  mov     [rsp+290h+var_270], eax; int
0x180025a0d  mov     r9, rbx; struct struct_join_status *
0x180025a10  mov     r8d, r14d; int
0x180025a13  setz    cl; int
0x180025a16  mov     rdx, r15; struct _CERT_CONTEXT *
0x180025a19  call    ?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z; JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)
0x180025a1e  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x180025a25  mov     edi, eax
0x180025a27  lea     rcx, aFalse; "FALSE"
0x180025a2e  lea     r13, aTrue; "TRUE"
0x180025a35  test    eax, eax
0x180025a37  jns     short loc_180025A6A
0x180025a39  test    r14d, r14d
0x180025a3c  lea     r8, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180025a43  mov     rax, r13
0x180025a46  mov     r9d, edi
0x180025a49  cmovz   rax, rcx
0x180025a4d  mov     rdx, r15
0x180025a50  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180025a57  mov     qword ptr [rsp+290h+var_270], rax
0x180025a5c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025a61  test    r14d, r14d
0x180025a64  jz      loc_18002696E
0x180025a6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025a71  mov     ecx, 10h; unsigned __int64
0x180025a76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025a7b  mov     rsi, rax
0x180025a7e  test    rax, rax
0x180025a81  jz      loc_180026939
0x180025a87  mov     rcx, rax; this
0x180025a8a  mov     qword ptr [rax], 0
0x180025a91  mov     qword ptr [rax+8], 0
0x180025a99  call    ?Load@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Load(void)
0x180025a9e  mov     edi, eax
0x180025aa0  test    eax, eax
0x180025aa2  jns     short loc_180025ADC
0x180025aa4  lea     rcx, aFalse; "FALSE"
0x180025aab  test    r14d, r14d
0x180025aae  mov     rax, r13
0x180025ab1  lea     r8, aNgcstatusstora; "NgcStatusStorage::Load"
0x180025ab8  cmovz   rax, rcx
0x180025abc  mov     r9d, edi
0x180025abf  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180025ac6  mov     qword ptr [rsp+290h+var_270], rax
0x180025acb  mov     rdx, r15
0x180025ace  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025ad3  test    r14d, r14d
0x180025ad6  jz      loc_18002696E
0x180025adc  lea     rdx, [rsp+290h+var_220]
0x180025ae1  mov     rcx, rsi
0x180025ae4  call    ?GetKey@NgcStatusStorage@@QEAA?AUSTRUCT_NGC_REG_KEY@@XZ; NgcStatusStorage::GetKey(void)
0x180025ae9  mov     rcx, [rsp+290h+pCertContext]
0x180025aee  lea     rdx, [r12+18h]; unsigned __int16 **
0x180025af3  mov     [rsp+290h+var_260], 0
0x180025afc  movups  xmm3, xmmword ptr [rax]
0x180025aff  movaps  xmmword ptr [rbp+190h+Uuid.Data1], xmm3
0x180025b06  movups  xmm0, xmmword ptr [rax+10h]
0x180025b0a  movaps  xmmword ptr [rbp+110h], xmm0
0x180025b11  movups  xmm1, xmmword ptr [rax+20h]
0x180025b15  movaps  [rbp+190h+var_7C+0Ch], xmm1
0x180025b1c  movups  xmm0, xmmword ptr [rax+30h]
0x180025b20  xor     eax, eax
0x180025b22  mov     [r12+8], rcx
0x180025b27  cmp     [rsp+290h+var_248], 1
0x180025b2c  movaps  xmmword ptr [rbp+190h+var_6C+0Ch], xmm0
0x180025b33  setnz   al
0x180025b36  inc     eax
0x180025b38  mov     [r12], eax
0x180025b3c  mov     rax, [rsp+290h+var_230]
0x180025b41  mov     [r12+10h], rax
0x180025b46  mov     rax, [rsp+290h+Block]
0x180025b4b  mov     [r12+20h], rax
0x180025b50  xor     eax, eax
0x180025b52  cmp     [rsp+290h+var_258], eax
0x180025b56  mov     [rsp+290h+var_230], 0
0x180025b5f  setnz   al
0x180025b62  mov     [r12+3Ch], eax
0x180025b67  mov     rcx, [rbx+8]; Source
0x180025b6b  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180025b70  mov     edi, eax
0x180025b72  test    eax, eax
0x180025b74  jns     short loc_180025BAE
0x180025b76  lea     rcx, aFalse; "FALSE"
0x180025b7d  test    r14d, r14d
0x180025b80  mov     rax, r13
0x180025b83  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180025b8a  cmovz   rax, rcx
0x180025b8e  mov     r9d, edi
0x180025b91  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180025b98  mov     qword ptr [rsp+290h+var_270], rax
0x180025b9d  mov     rdx, r15
0x180025ba0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025ba5  test    r14d, r14d
0x180025ba8  jz      loc_180025849
0x180025bae  mov     rcx, [rbx+18h]; Source
0x180025bb2  lea     rdx, [r12+28h]; unsigned __int16 **
0x180025bb7  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180025bbc  mov     edi, eax
0x180025bbe  test    eax, eax
0x180025bc0  jns     short loc_180025BFA
0x180025bc2  lea     rcx, aFalse; "FALSE"
0x180025bc9  test    r14d, r14d
0x180025bcc  mov     rax, r13
0x180025bcf  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180025bd6  cmovz   rax, rcx
0x180025bda  mov     r9d, edi
0x180025bdd  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180025be4  mov     qword ptr [rsp+290h+var_270], rax
0x180025be9  mov     rdx, r15
0x180025bec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025bf1  test    r14d, r14d
0x180025bf4  jz      loc_180025849
0x180025bfa  mov     rcx, [rbx+20h]; Source
0x180025bfe  lea     rdx, [r12+40h]; unsigned __int16 **
0x180025c03  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180025c08  mov     edi, eax
0x180025c0a  test    eax, eax
0x180025c0c  jns     short loc_180025C46
0x180025c0e  lea     rcx, aFalse; "FALSE"
0x180025c15  test    r14d, r14d
0x180025c18  mov     rax, r13
0x180025c1b  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180025c22  cmovz   rax, rcx
0x180025c26  mov     r9d, edi
0x180025c29  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180025c30  mov     qword ptr [rsp+290h+var_270], rax
0x180025c35  mov     rdx, r15
0x180025c38  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025c3d  test    r14d, r14d
0x180025c40  jz      loc_180025849
0x180025c46  mov     rcx, [rbx+28h]; Source
0x180025c4a  lea     rdx, [r12+48h]; unsigned __int16 **
0x180025c4f  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180025c54  mov     edi, eax
0x180025c56  test    eax, eax
0x180025c58  jns     short loc_180025C92
0x180025c5a  lea     rcx, aFalse; "FALSE"
0x180025c61  test    r14d, r14d
0x180025c64  mov     rax, r13
0x180025c67  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180025c6e  cmovz   rax, rcx
0x180025c72  mov     r9d, edi
0x180025c75  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180025c7c  mov     qword ptr [rsp+290h+var_270], rax
0x180025c81  mov     rdx, r15
0x180025c84  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180025c89  test    r14d, r14d
  ... truncated ...
```
