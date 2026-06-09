# DiscoverApi::BeginRepairJoinInfo(_DSREG_JOIN_TYPE,ushort const *,ushort const * *,ulong,ushort const *,void (*)(struct_dsreg_server_response,unsigned __int64,long),unsigned __int64)

- ea: `0x18006850c`
- end: `0x180068fa2`
- name: `?BeginRepairJoinInfo@DiscoverApi@@SAJW4_DSREG_JOIN_TYPE@@PEBGPEAPEBGK1P6AXUstruct_dsreg_server_response@@_KJ@Z4@Z`
- size: `2710`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 **, unsigned int, int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, installer_update`

## callers

- `0x1800414f8`

## callees

- `0x180001ba0`
- `0x180001cdc`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000ab70`
- `0x18000bac0`
- `0x18000bd20`
- `0x180011fc0`
- `0x180012eb8`
- `0x180017bb0`
- `0x18001c114`
- `0x18001f9d0`
- `0x1800204f0`
- `0x18003334c`
- `0x18003b038`
- `0x18003c61c`
- `0x18004271c`
- `0x180042900`
- `0x18004651c`
- `0x180046540`
- `0x180055174`
- `0x180067f5c`
- `0x180067fb4`
- `0x18006850c`
- `0x1800695e8`
- `0x18006d074`
- `0x18006d100`
- `0x18006e600`
- `0x18009fb90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180068650`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180068650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068852`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068f2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068852`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068f2d`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x1800688a2`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x1800689ce`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x1800688a2`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x1800689ce`

## string_xrefs

- `0x180068b5e`: `GetAutoJoinDomainConfiguration`
- `0x180068c5a`: `CopyStringNullSafeW`
- `0x18006856b`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068723`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068763`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800687af`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068809`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800688a8`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068939`: `DiscoverApi::BeginRepairJoinInfo`
- `0x18006895c`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800689dc`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068a30`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068a83`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068b29`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068b68`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068bdf`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068c37`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068c9f`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068cbd`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068de9`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068e1e`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068e7b`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068ed5`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180068f71`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800687bb`: `%s: Multiple (%lu) join certificates found for the given tenant. Only the first one will be repaired. JoinType: %d(%s), TenantId: %s.`
- `0x180068a09`: `%s: Cannot get existing transport key. Unable to repair transport key type. NgcGetSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key type: %d, Flags: %lu.`
- `0x180068940`: `%s: ConvertKeyStatusToDwordKeyType failed with error code 0x%08x. Unable to repair transport key type.`
- `0x180068a37`: `%s: ConvertKeyStatusToDwordKeyType failed with error code 0x%08x. Unable to repair transport key type.`
- `0x180068810`: `%s: GetCurrentUserSid failed with error code 0x%08x. Unable to repair transport key type.`
- `0x1800688e4`: `%s: Cannot get transport key name. Unable to repair transport key type. NgcGetSymmetricPopKeyTransportKeyName failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key type: %s, Flags: %lu.`
- `0x180068c13`: `%s: GetAutoJoinDomainConfiguration failed with error code: 0x%08x. Unable to recover DJ++ user email.`
- `0x180068df4`: `%s: Repair join info operation started successfully. Tenant ID: "%s", Device ID: "%s", Join type: %d, UPN: "%s", UPN Count: %lu, Request ID: "%s".`
- `0x180068e86`: `%s: Failed to start repair join info operation with error code: 0x%08x. Tenant ID: "%s", Join type: %d, UPN: "%s", UPN Count: %lu, Request ID: "%s".`
- `0x180068edc`: `%s: No need to repair join info. Calling callback function...`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DiscoverApi::BeginRepairJoinInfo(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        __int64 a7)
{
  unsigned int v8; // r13d
  const WCHAR *v9; // rdx
  const WCHAR *v10; // r10
  unsigned __int64 v11; // rdi
  char *v12; // rax
  char *v13; // r14
  const unsigned __int16 *v14; // r12
  __int64 v15; // rsi
  char *v16; // r15
  __int64 v17; // rcx
  unsigned int v18; // ebx
  int JoinInfo; // eax
  _QWORD *v20; // rcx
  __int64 v21; // r8
  int CurrentUserSid; // eax
  int v23; // ebx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  int SymmetricPopKeyTransportKey; // eax
  int v28; // eax
  int v29; // eax
  _QWORD *v30; // rax
  __int64 v31; // rax
  int v32; // r8d
  int AutoJoinDomainConfiguration; // eax
  const wchar_t *v34; // r8
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int FakeUserEmail; // eax
  __int64 v39; // r9
  __int64 v40; // r15
  unsigned int v41; // esi
  const unsigned __int16 *v42; // rax
  unsigned __int16 *v44; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v45; // [rsp+20h] [rbp-E0h]
  __int64 v46; // [rsp+30h] [rbp-D0h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+40h] [rbp-C0h]
  void *v49; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+68h] [rbp-98h] BYREF
  int v51; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h]
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h] BYREF
  __int64 JoinTypeName; // [rsp+90h] [rbp-70h]
  HLOCAL v57; // [rsp+98h] [rbp-68h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 *v59; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v60; // [rsp+B0h] [rbp-50h]
  unsigned int v61; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v62; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v64; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD *v65; // [rsp+E0h] [rbp-20h]
  __int64 v66; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v67; // [rsp+F0h] [rbp-10h]
  _DWORD v68[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v69; // [rsp+100h] [rbp+0h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  __int128 v71; // [rsp+110h] [rbp+10h] BYREF
  __int128 v72; // [rsp+120h] [rbp+20h]
  __int128 v73; // [rsp+130h] [rbp+30h]
  __int64 v74; // [rsp+140h] [rbp+40h]
  unsigned int v75; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v76; // [rsp+1B8h] [rbp+B8h]
  const unsigned __int16 **v77; // [rsp+1C0h] [rbp+C0h]
  unsigned int v78; // [rsp+1C8h] [rbp+C8h]

  v78 = a4;
  v77 = a3;
  v76 = a2;
  v8 = a1;
  JoinTypeName = GetJoinTypeName(a1);
  v10 = &cchOriginalDestLength;
  if ( v9 )
    v10 = v9;
  Logger::TraceVerbose(
    (wchar_t *)L"%s started. joinType: %d(%s), tenantId: %s, clientRequestId: %s.",
    L"DiscoverApi::BeginRepairJoinInfo",
    v8,
    JoinTypeName,
    v10,
    &cchOriginalDestLength);
  v69 = a2;
  v68[1] = 0;
  v67 = 0;
  v74 = 0;
  v68[0] = v8;
  v59 = L"login.windows.net";
  v70 = 0;
  v49 = 0;
  v11 = 0;
  a5 = 1;
  v71 = 0;
  v75 = 0;
  v72 = 0;
  a6 = 0;
  v73 = 0;
  v57 = 0;
  v60 = 0;
  lpMem = 0;
  hMem = 0;
  v50 = 0;
  v62 = 0;
  Block = 0;
  v51 = 0;
  v12 = (char *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v55 = (__int64)v12;
  v13 = v12;
  if ( !v12 )
  {
    v13 = 0;
    v18 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DiscoverApi::BeginRepairJoinInfo");
    goto LABEL_85;
  }
  *(_DWORD *)v12 = 0;
  v12[4] = 0;
  v14 = 0;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v15 = (__int64)(v13 + 8);
    EventActivityIdControl(3u, (LPGUID)(v13 + 8));
  }
  else
  {
    v15 = (__int64)(v13 + 8);
    *(_OWORD *)(v13 + 8) = 0;
  }
  *(_DWORD *)v13 = 1;
  v16 = v13;
  v65 = v13;
  v52 = v15;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v66 = JoinTypeName;
    v64 = v76;
    v61 = v8;
    v63 = 0;
    v55 = 16779264;
    if ( !v13[4] || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v17 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18013D150,
      (__int64)&byte_180129E27,
      v15,
      v17,
      (__int64)&v55,
      &v64,
      &v63,
      (__int64)&v61,
      &v66);
  }
  if ( v8 - 1 > 1 )
  {
    Logger::TraceError(L"%s: Unsupported join type %d", L"DiscoverApi::BeginRepairJoinInfo", v8);
    v18 = -2147024809;
LABEL_75:
    *v65 = 2;
    if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
    {
      v55 = JoinTypeName;
      v63 = v76;
      a5 = v8;
      v64 = 0;
      a6 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (__int64)&dword_18013D150,
        (__int64)byte_180129EC9,
        v15,
        v39,
        (__int64)&a6,
        &v63,
        &v64,
        (__int64)&a5,
        &v55);
    }
    a5 = 1;
    if ( (v18 & 0x80000000) == 0 )
      goto LABEL_79;
LABEL_85:
    v40 = v76;
    v41 = v78;
    Logger::WriteBeginRepairJoinInfoFailureEvent(v18, v76, v8, v77, v78);
    if ( v77 && v41 )
      v42 = *v77;
    else
      v42 = 0;
    LODWORD(v46) = v41;
    LODWORD(v45) = v8;
    Logger::TraceError(
      L"%s: Failed to start repair join info operation with error code: 0x%08x. Tenant ID: \"%s\", Join type: %d, UPN: \"%"
       "s\", UPN Count: %lu, Request ID: \"%s\".",
      L"DiscoverApi::BeginRepairJoinInfo",
      v18,
      v40,
      v45,
      v42,
      v46,
      0);
    if ( (v18 & 0x80000000) != 0 )
      goto LABEL_92;
    goto LABEL_90;
  }
  JoinInfo = DsrGetJoinInfoEx(3, v68, &v49);
  v18 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DiscoverApi::BeginRepairJoinInfo",
      L"DsrGetJoinInfoEx",
      (unsigned int)JoinInfo);
    goto LABEL_75;
  }
  v20 = v49;
  if ( !v49 || (v21 = *((unsigned int *)v49 + 4), !(_DWORD)v21) || !*((_QWORD *)v49 + 1) )
  {
    Logger::TraceError(
      L"%s: Device is not joined. TenantID: %s, JoinType: %d(%s).",
      L"DiscoverApi::BeginRepairJoinInfo",
      v76,
      v8,
      JoinTypeName);
    v18 = -2145647536;
    goto LABEL_74;
  }
  if ( (unsigned int)v21 > 1 )
  {
    Logger::TraceWarning(
      (wchar_t *)L"%s: Multiple (%lu) join certificates found for the given tenant. Only the first one will be repaired. J"
                  "oinType: %d(%s), TenantId: %s.",
      L"DiscoverApi::BeginRepairJoinInfo",
      v21,
      v8,
      JoinTypeName,
      v76);
    v20 = v49;
  }
  if ( v8 == 1 )
  {
    v60 = *(unsigned __int64 *)(v20[1] + 32LL);
    SymmetricPopKeyTransportKey = NgcGetSymmetricPopKeyTransportKey(&v59, 0, 0, 6, &hMem, &v50, 0, 0, 0, 0, &v75);
    if ( SymmetricPopKeyTransportKey >= 0 )
    {
      v28 = ConvertKeyStatusToDwordKeyType(v75, &a6);
      if ( v28 < 0 )
        Logger::TraceWarning(
          (wchar_t *)L"%s: ConvertKeyStatusToDwordKeyType failed with error code 0x%08x. Unable to repair transport key type.",
          L"DiscoverApi::BeginRepairJoinInfo",
          (unsigned int)v28);
    }
    else
    {
      LODWORD(v48) = 6;
      Logger::TraceWarning(
        (wchar_t *)L"%s: Cannot get existing transport key. Unable to repair transport key type. NgcGetSymmetricPopKeyTran"
                    "sportKey failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key"
                    " type: %d, Flags: %lu.",
        L"DiscoverApi::BeginRepairJoinInfo",
        (unsigned int)SymmetricPopKeyTransportKey,
        0,
        v59,
        v60,
        0,
        v48);
    }
    if ( v77 && v78 )
      v14 = *v77;
    goto LABEL_44;
  }
  if ( v8 == 2 )
  {
    *(_QWORD *)&v60 = *(_QWORD *)(v20[1] + 32LL);
    CurrentUserSid = GetCurrentUserSid((LPWSTR *)&v57);
    if ( CurrentUserSid < 0 )
    {
      Logger::TraceWarning(
        (wchar_t *)L"%s: GetCurrentUserSid failed with error code 0x%08x. Unable to repair transport key type.",
        L"DiscoverApi::BeginRepairJoinInfo",
        (unsigned int)CurrentUserSid);
      goto LABEL_44;
    }
    v23 = 0;
    if ( !v78 )
      goto LABEL_35;
    while ( 1 )
    {
      if ( !(unsigned int)IsEmptyString(v77[v23]) )
      {
        *((_QWORD *)&v60 + 1) = v24;
        LocalFree(hMem);
        hMem = 0;
        v25 = NgcGetSymmetricPopKeyTransportKey(&v59, v57, 0, 4, &hMem, &v50, 0, 0, 0, 0, &v75);
        if ( v25 >= 0 )
        {
          v14 = v77[v23];
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Join user email recovered (%s)",
            L"DiscoverApi::BeginRepairJoinInfo",
            v14);
          v26 = ConvertKeyStatusToDwordKeyType(v75, &a6);
          if ( v26 < 0 )
            Logger::TraceWarning(
              (wchar_t *)L"%s: ConvertKeyStatusToDwordKeyType failed with error code 0x%08x. Unable to repair transport key type.",
              L"DiscoverApi::BeginRepairJoinInfo",
              (unsigned int)v26);
LABEL_35:
          if ( (unsigned int)IsEmptyString(v14) )
          {
            v18 = -2145648531;
            Logger::TraceError(
              L"%s: Unable to find the transport key using the given UPNs",
              L"DiscoverApi::BeginRepairJoinInfo");
            goto LABEL_74;
          }
LABEL_44:
          v20 = v49;
          break;
        }
        LODWORD(v47) = 4;
        Logger::TraceWarning(
          (wchar_t *)L"%s: Cannot get transport key name. Unable to repair transport key type. NgcGetSymmetricPopKeyTransp"
                      "ortKeyName failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s,"
                      " Key type: %s, Flags: %lu.",
          L"DiscoverApi::BeginRepairJoinInfo",
          (unsigned int)v25,
          v57,
          v59,
          v60,
          0,
          v47);
      }
      if ( ++v23 >= v78 )
        goto LABEL_35;
    }
  }
  v29 = StringDup(*(const unsigned __int16 **)(v20[1] + 16LL), (unsigned __int16 **)&lpMem, 0);
  v18 = v29;
  if ( v29 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DiscoverApi::BeginRepairJoinInfo",
      L"StringDup",
      (unsigned int)v29);
LABEL_74:
    v15 = v52;
    goto LABEL_75;
  }
  v30 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v55 = (__int64)v30;
  v11 = (unsigned __int64)v30;
  if ( !v30 )
  {
    v11 = 0;
    v18 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DiscoverApi::BeginRepairJoinInfo");
    goto LABEL_74;
  }
  *v30 = 0;
  v30[1] = 0;
  v30[2] = 0;
  *((_DWORD *)v30 + 6) = 0;
  v30[4] = 0;
  v30[5] = 0;
  v13 = 0;
  *v30 = DsrCmdAsyncHelper::RepairJoinInfoCallback;
  v30[1] = a7;
  *((_DWORD *)v30 + 6) = a6;
  v30[4] = v49;
  v49 = 0;
  v31 = v30[4];
  *(_QWORD *)(v11 + 40) = v16;
  v32 = *(_DWORD *)(*(_QWORD *)(v31 + 8) + 60LL);
  if ( v32 )
  {
    if ( v32 != 1 )
    {
      Logger::TraceError(L"%s: Unsupported DSR instance %d", L"DiscoverApi::BeginRepairJoinInfo");
      v18 = -2147024809;
      goto LABEL_85;
    }
    AutoJoinDomainConfiguration = GetAutoJoinDomainConfiguration(0, (unsigned __int16 **)&Block, &v62, 0);
    v18 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"GetAutoJoinDomainConfiguration";
LABEL_53:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DiscoverApi::BeginRepairJoinInfo",
        v34,
        (unsigned int)AutoJoinDomainConfiguration);
      goto LABEL_85;
    }
    AutoJoinDomainConfiguration = MakeFakeUserEmail((const unsigned __int16 *)Block, (unsigned __int16 **)(v11 + 16));
    v18 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"MakeFakeUserEmail";
      goto LABEL_53;
    }
    AutoJoinDomainConfiguration = DsrBeginDiscoverEnterprise(
                                    v62,
                                    (void (__high *)(struct _DISCOVERY_METADATA *, struct struct_dsreg_server_response, unsigned __int64, int))DiscoverApi::AsyncRepairCallback,
                                    v11,
                                    0);
    v18 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"DsrBeginDiscoverEnterprise";
      goto LABEL_53;
    }
  }
  else
  {
    v35 = IsLocalMachineDomainJoined(&v51, 0);
    if ( v35 >= 0 )
    {
      v36 = v51;
    }
    else
    {
      Logger::TraceWarning(
        (wchar_t *)L"%s: IsLocalMachineDomainJoined failed with error code: 0x%08x. Assuming the device is not AD domain joined.",
        L"DiscoverApi::BeginRepairJoinInfo",
        (unsigned int)v35);
      v36 = 0;
    }
    if ( v36 )
    {
      v37 = GetAutoJoinDomainConfiguration(0, (unsigned __int16 **)&Block, 0, 0);
      if ( v37 >= 0 )
      {
        FakeUserEmail = MakeFakeUserEmail((const unsigned __int16 *)Block, (unsigned __int16 **)(v11 + 16));
        if ( FakeUserEmail < 0 )
          Logger::TraceWarning(
            (wchar_t *)L"%s: MakeFakeUserEmail failed with error code: 0x%08x. Unable to recover DJ++ user email.",
            L"DiscoverApi::BeginRepairJoinInfo",
            (unsigned int)FakeUserEmail);
      }
      else
      {
        Logger::TraceWarning(
          L"%s: GetAutoJoinDomainConfiguration failed with error code: 0x%08x. Unable to recover DJ++ user email.",
          L"DiscoverApi::BeginRepairJoinInfo",
          (unsigned int)v37);
      }
    }
    if ( !*(_QWORD *)(v11 + 16) )
    {
      AutoJoinDomainConfiguration = CopyStringNullSafeW(v14, (unsigned __int16 **)(v11 + 16));
      v18 = AutoJoinDomainConfiguration;
      if ( AutoJoinDomainConfiguration < 0 )
      {
        v34 = L"CopyStringNullSafeW";
        goto LABEL_53;
      }
    }
    AutoJoinDomainConfiguration = DsrBeginDiscoverEx(
                                    *(unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v11 + 32) + 8LL) + 32LL),
                                    0);
    v18 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"DsrBeginDiscover";
      goto LABEL_53;
    }
  }
  a5 = 0;
LABEL_79:
  if ( !v14 )
  {
    v14 = 0;
    if ( v77 )
    {
      if ( v78 )
        v14 = *v77;
    }
  }
  v40 = v76;
  Logger::WriteBeginRepairJoinInfoSuccessEvent(v76, lpMem, v8, v14, v78);
  LODWORD(v46) = v78;
  LODWORD(v44) = v8;
  Logger::TraceVerbose(
    (wchar_t *)L"%s: Repair join info operation started successfully. Tenant ID: \"%s\", Device ID: \"%s\", Join type: %d,"
                " UPN: \"%s\", UPN Count: %lu, Request ID: \"%s\".",
    L"DiscoverApi::BeginRepairJoinInfo",
    v40,
    lpMem,
    v44,
    v14,
    v46,
    0);
LABEL_90:
  if ( !a5 )
    goto LABEL_94;
  Logger::WriteRepairJoinInfoCallbackSuccessEvent(
    v40,
    *(_QWORD *)(*((_QWORD *)v49 + 1) + 16LL),
    *(_QWORD *)(*((_QWORD *)v49 + 1) + 40LL),
    v8,
    &v71);
  Logger::TraceVerbose(
    (wchar_t *)L"%s: No need to repair join info. Calling callback function...",
    L"DiscoverApi::BeginRepairJoinInfo");
  v74 = v67;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  DsrCmdAsyncHelper::RepairJoinInfoCallback(&v71, a7, v18);
LABEL_92:
  if ( v11 )
    _JOIN_INFO_REPAIR_CALLBACK_CONTEXT::`scalar deleting destructor'((void **)v11);
LABEL_94:
  LocalFree(hMem);
  LocalFree(v57);
  DsrFreeJoinInfoEx(v49);
  if ( v13 )
    TraceLoggingActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>::`scalar deleting destructor'(v13);
  SafeFree(lpMem);
  operator delete(Block);
  operator delete(v62);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DiscoverApi::BeginRepairJoinInfo", v18);
  return v18;
}

```

## disassembly

```asm
0x18006850c  mov     rax, rsp
0x18006850f  mov     [rax+20h], r9d
0x180068513  mov     [rax+18h], r8
0x180068517  mov     [rax+10h], rdx
0x18006851b  push    rbp
0x18006851c  push    rbx
0x18006851d  push    rsi
0x18006851e  push    rdi
0x18006851f  push    r12
0x180068521  push    r13
0x180068523  push    r14
0x180068525  push    r15
0x180068527  lea     rbp, [rsp-68h]
0x18006852c  sub     rsp, 168h
0x180068533  movaps  xmmword ptr [rax-58h], xmm6
0x180068537  mov     rbx, rdx
0x18006853a  mov     r13d, ecx
0x18006853d  call    ?GetJoinTypeName@@YAPEBGW4_DSREG_JOIN_TYPE@@@Z; GetJoinTypeName(_DSREG_JOIN_TYPE)
0x180068542  lea     rcx, cchOriginalDestLength
0x180068549  mov     [rbp+0A0h+var_110], rax
0x18006854d  mov     r10, rcx
0x180068550  mov     qword ptr [rsp+1A0h+var_178], rcx
0x180068555  xor     esi, esi
0x180068557  lea     rcx, aSStartedJointy; "%s started. joinType: %d(%s), tenantId:"...
0x18006855e  test    rdx, rdx
0x180068561  mov     r9, rax
0x180068564  mov     r8d, r13d
0x180068567  cmovnz  r10, rdx
0x18006856b  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x180068572  mov     [rsp+1A0h+var_180], r10
0x180068577  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006857c  xor     eax, eax
0x18006857e  mov     [rbp+0A0h+var_A0], rbx
0x180068582  xorps   xmm6, xmm6
0x180068585  mov     [rbp+0A0h+var_A4], eax
0x180068588  mov     [rbp+0A0h+var_B0], rax
0x18006858c  lea     ebx, [rsi+1]
0x18006858f  mov     [rbp+0A0h+var_60], rax
0x180068593  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006859a  lea     rax, aLoginWindowsNe; "login.windows.net"
0x1800685a1  mov     [rbp+0A0h+var_A8], r13d
0x1800685a5  xorps   xmm0, xmm0
0x1800685a8  mov     [rbp+0A0h+var_F8], rax
0x1800685ac  lea     ecx, [rsi+28h]; unsigned __int64
0x1800685af  mov     [rbp+0A0h+var_98], rsi
0x1800685b3  mov     [rsp+1A0h+var_140], rsi
0x1800685b8  mov     edi, esi
0x1800685ba  mov     [rbp+0A0h+arg_20], ebx
0x1800685c0  movups  [rbp+0A0h+var_90], xmm6
0x1800685c4  mov     [rbp+0A0h+arg_0], esi
0x1800685ca  movups  [rbp+0A0h+var_80], xmm6
0x1800685ce  mov     [rbp+0A0h+arg_28], esi
0x1800685d4  movups  [rbp+0A0h+var_70], xmm6
0x1800685d8  mov     [rbp+0A0h+var_108], rsi
0x1800685dc  movdqu  [rbp+0A0h+var_F0], xmm0
0x1800685e1  mov     [rbp+0A0h+lpMem], rsi
0x1800685e5  mov     [rsp+1A0h+hMem], rsi
0x1800685ea  mov     [rsp+1A0h+var_138], esi
0x1800685ee  mov     [rbp+0A0h+var_D8], rsi
0x1800685f2  mov     [rbp+0A0h+Block], rsi
0x1800685f6  mov     [rsp+1A0h+var_134], esi
0x1800685fa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800685ff  mov     [rbp+0A0h+var_118], rax
0x180068603  mov     r14, rax
0x180068606  test    rax, rax
0x180068609  jz      loc_180068E1B
0x18006860f  mov     [rax], esi
0x180068611  mov     [rax+4], sil
0x180068615  test    rax, rax
0x180068618  jz      loc_180068E1E
0x18006861e  mov     eax, cs:dword_18013D150
0x180068624  mov     r12d, esi
0x180068627  cmp     eax, 5
0x18006862a  jbe     short loc_180068658
0x18006862c  mov     rdx, 400000000000h
0x180068636  lea     rcx, dword_18013D150
0x18006863d  call    _tlgKeywordOn
0x180068642  test    al, al
0x180068644  jz      short loc_180068658
0x180068646  lea     rsi, [r14+8]
0x18006864a  mov     rdx, rsi; ActivityId
0x18006864d  lea     ecx, [rbx+2]; ControlCode
0x180068650  call    cs:__imp_EventActivityIdControl
0x180068656  jmp     short loc_180068662
0x180068658  lea     rsi, [r14+8]
0x18006865c  xorps   xmm0, xmm0
0x18006865f  movups  xmmword ptr [rsi], xmm0
0x180068662  mov     [r14], ebx
0x180068665  mov     r15, r14
0x180068668  mov     eax, cs:dword_18013D150
0x18006866e  mov     [rbp+0A0h+var_C0], r14
0x180068672  mov     [rsp+1A0h+var_130], rsi
0x180068677  cmp     eax, 5
0x18006867a  jbe     loc_180068718
0x180068680  mov     rdx, 400000000000h
0x18006868a  lea     rcx, dword_18013D150
0x180068691  call    _tlgKeywordOn
0x180068696  test    al, al
0x180068698  jz      short loc_180068718
0x18006869a  mov     rax, [rbp+0A0h+var_110]
0x18006869e  mov     [rbp+0A0h+var_B8], rax
0x1800686a2  mov     rax, [rbp+0A0h+arg_8]
0x1800686a9  mov     [rbp+0A0h+var_C8], rax
0x1800686ad  mov     [rbp+0A0h+var_E0], r13d
0x1800686b1  mov     [rbp+0A0h+var_D0], rdi
0x1800686b5  mov     [rbp+0A0h+var_118], 1000800h
0x1800686bd  cmp     [r14+4], dil
0x1800686c1  jz      short loc_1800686D0
0x1800686c3  lea     rcx, [r14+18h]; struct _GUID *
0x1800686c7  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800686cc  test    al, al
0x1800686ce  jz      short loc_1800686D2
0x1800686d0  xor     ecx, ecx
0x1800686d2  lea     rax, [rbp+0A0h+var_B8]
0x1800686d6  mov     r9, rcx
0x1800686d9  mov     [rsp+1A0h+var_160], rax
0x1800686de  lea     rdx, byte_180129E27
0x1800686e5  lea     rax, [rbp+0A0h+var_E0]
0x1800686e9  mov     r8, rsi
0x1800686ec  mov     [rsp+1A0h+var_168], rax
0x1800686f1  lea     rcx, dword_18013D150
0x1800686f8  lea     rax, [rbp+0A0h+var_D0]
0x1800686fc  mov     qword ptr [rsp+1A0h+var_178+8], rax
0x180068701  lea     rax, [rbp+0A0h+var_C8]
0x180068705  mov     qword ptr [rsp+1A0h+var_178], rax
0x18006870a  lea     rax, [rbp+0A0h+var_118]
0x18006870e  mov     [rsp+1A0h+var_180], rax
0x180068713  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180068718  lea     eax, [r13-1]
0x18006871c  cmp     eax, ebx
0x18006871e  jbe     short loc_180068740
0x180068720  mov     r8d, r13d
0x180068723  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x18006872a  lea     rcx, aSUnsupportedJo; "%s: Unsupported join type %d"
0x180068731  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180068736  mov     ebx, 80070057h
0x18006873b  jmp     loc_180068CE9
0x180068740  lea     r8, [rsp+1A0h+var_140]
0x180068745  mov     ecx, 3
0x18006874a  lea     rdx, [rbp+0A0h+var_A8]
0x18006874e  call    DsrGetJoinInfoEx
0x180068753  mov     ebx, eax
0x180068755  test    eax, eax
0x180068757  jns     short loc_18006877B
0x180068759  mov     r9d, eax
0x18006875c  lea     r8, aDsrgetjoininfo_1; "DsrGetJoinInfoEx"
0x180068763  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x18006876a  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180068771  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180068776  jmp     loc_180068CE9
0x18006877b  mov     rcx, [rsp+1A0h+var_140]
0x180068780  xor     esi, esi
0x180068782  test    rcx, rcx
0x180068785  jz      loc_180068CB9
0x18006878b  mov     r8d, [rcx+10h]
0x18006878f  test    r8d, r8d
0x180068792  jz      loc_180068CB9
0x180068798  cmp     [rcx+8], rsi
0x18006879c  jz      loc_180068CB9
0x1800687a2  cmp     r8d, 1
0x1800687a6  jbe     short loc_1800687D8
0x1800687a8  mov     rax, [rbp+0A0h+arg_8]
0x1800687af  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800687b6  mov     qword ptr [rsp+1A0h+var_178], rax
0x1800687bb  lea     rcx, aSMultipleLuJoi_0; "%s: Multiple (%lu) join certificates fo"...
0x1800687c2  mov     rax, [rbp+0A0h+var_110]
0x1800687c6  mov     r9d, r13d
0x1800687c9  mov     [rsp+1A0h+var_180], rax
0x1800687ce  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800687d3  mov     rcx, [rsp+1A0h+var_140]
0x1800687d8  mov     edx, r13d
0x1800687db  sub     edx, 1
0x1800687de  jz      loc_180068979
0x1800687e4  cmp     edx, 1
0x1800687e7  jnz     loc_180068A5F
0x1800687ed  mov     rax, [rcx+8]
0x1800687f1  mov     rcx, [rax+20h]
0x1800687f5  mov     qword ptr [rbp+0A0h+var_F0], rcx
0x1800687f9  lea     rcx, [rbp+0A0h+var_108]; StringSid
0x1800687fd  call    ?GetCurrentUserSid@@YAJPEAPEAG@Z; GetCurrentUserSid(ushort * *)
0x180068802  test    eax, eax
0x180068804  jns     short loc_180068821
0x180068806  mov     r8d, eax
0x180068809  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x180068810  lea     rcx, aSGetcurrentuse; "%s: GetCurrentUserSid failed with error"...
0x180068817  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006881c  jmp     loc_180068A5A
0x180068821  mov     ebx, esi
0x180068823  cmp     [rbp+0A0h+arg_18], esi
0x180068829  jbe     loc_18006894C
0x18006882f  mov     rax, [rbp+0A0h+arg_10]
0x180068836  mov     esi, ebx
0x180068838  mov     rcx, [rax+rsi*8]; unsigned __int16 *
0x18006883c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180068841  test    eax, eax
0x180068843  jnz     loc_1800688F2
0x180068849  mov     qword ptr [rbp+0A0h+var_F0+8], rcx
0x18006884d  mov     rcx, [rsp+1A0h+hMem]; hMem
0x180068852  call    cs:__imp_LocalFree
0x180068858  mov     rdx, [rbp+0A0h+var_108]
0x18006885c  lea     rax, [rbp+0A0h+arg_0]
0x180068863  mov     [rsp+1A0h+var_150], rax
0x180068868  xor     ecx, ecx
0x18006886a  mov     [rsp+1A0h+var_158], rcx
0x18006886f  lea     rax, [rsp+1A0h+var_138]
0x180068874  mov     [rsp+1A0h+var_160], rcx
0x180068879  xor     r8d, r8d
0x18006887c  mov     [rsp+1A0h+var_168], rcx
0x180068881  mov     qword ptr [rsp+1A0h+var_178+8], rcx
0x180068886  lea     r9d, [rcx+4]
0x18006888a  mov     qword ptr [rsp+1A0h+var_178], rax
0x18006888f  lea     rax, [rsp+1A0h+hMem]
0x180068894  mov     [rsp+1A0h+hMem], rcx
0x180068899  lea     rcx, [rbp+0A0h+var_F8]
0x18006889d  mov     [rsp+1A0h+var_180], rax
0x1800688a2  call    cs:__imp_NgcGetSymmetricPopKeyTransportKey
0x1800688a8  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800688af  test    eax, eax
0x1800688b1  jns     short loc_180068904
0x1800688b3  mov     rcx, qword ptr [rbp+0A0h+var_F0+8]
0x1800688b7  xor     esi, esi
0x1800688b9  mov     r9, [rbp+0A0h+var_108]
0x1800688bd  mov     r8d, eax
0x1800688c0  mov     dword ptr [rsp+1A0h+var_160], 4
0x1800688c8  mov     [rsp+1A0h+var_168], rsi
0x1800688cd  mov     qword ptr [rsp+1A0h+var_178+8], rcx
0x1800688d2  mov     rcx, qword ptr [rbp+0A0h+var_F0]
0x1800688d6  mov     qword ptr [rsp+1A0h+var_178], rcx
0x1800688db  mov     rcx, [rbp+0A0h+var_F8]
0x1800688df  mov     [rsp+1A0h+var_180], rcx
0x1800688e4  lea     rcx, aSCannotGetTran; "%s: Cannot get transport key name. Unab"...
0x1800688eb  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800688f0  jmp     short loc_1800688F4
0x1800688f2  xor     esi, esi
0x1800688f4  inc     ebx
0x1800688f6  cmp     ebx, [rbp+0A0h+arg_18]
0x1800688fc  jb      loc_18006882F
0x180068902  jmp     short loc_18006894C
0x180068904  mov     rax, [rbp+0A0h+arg_10]
0x18006890b  lea     rcx, aSJoinUserEmail; "%s: Join user email recovered (%s)"
0x180068912  mov     r12, [rax+rsi*8]
0x180068916  mov     r8, r12
0x180068919  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006891e  mov     ecx, [rbp+0A0h+arg_0]
0x180068924  lea     rdx, [rbp+0A0h+arg_28]
0x18006892b  call    ?ConvertKeyStatusToDwordKeyType@@YAJW4_NGC_KEY_STATUS@@PEAK@Z; ConvertKeyStatusToDwordKeyType(_NGC_KEY_STATUS,ulong *)
0x180068930  xor     esi, esi
0x180068932  test    eax, eax
0x180068934  jns     short loc_18006894C
0x180068936  mov     r8d, eax
0x180068939  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x180068940  lea     rcx, aSConvertkeysta; "%s: ConvertKeyStatusToDwordKeyType fail"...
0x180068947  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006894c  mov     rcx, r12; unsigned __int16 *
0x18006894f  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180068954  test    eax, eax
0x180068956  jz      loc_180068A5A
0x18006895c  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x180068963  mov     ebx, 801C006Dh
0x180068968  lea     rcx, aSUnableToFindT; "%s: Unable to find the transport key us"...
0x18006896f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180068974  jmp     loc_180068CE4
0x180068979  mov     rax, [rcx+8]
0x18006897d  mov     ebx, 6
0x180068982  mov     r9d, ebx
0x180068985  xor     r8d, r8d
0x180068988  xor     edx, edx
0x18006898a  mov     rcx, [rax+20h]
0x18006898e  lea     rax, [rbp+0A0h+arg_0]
0x180068995  mov     [rsp+1A0h+var_150], rax
0x18006899a  lea     rax, [rsp+1A0h+var_138]
0x18006899f  mov     [rsp+1A0h+var_158], rsi
0x1800689a4  mov     [rsp+1A0h+var_160], rsi
0x1800689a9  mov     [rsp+1A0h+var_168], rsi
0x1800689ae  mov     qword ptr [rsp+1A0h+var_178+8], rsi
0x1800689b3  mov     qword ptr [rsp+1A0h+var_178], rax
0x1800689b8  lea     rax, [rsp+1A0h+hMem]
0x1800689bd  mov     qword ptr [rbp+0A0h+var_F0], rcx
0x1800689c1  lea     rcx, [rbp+0A0h+var_F8]
0x1800689c5  mov     [rsp+1A0h+var_180], rax
0x1800689ca  mov     qword ptr [rbp+0A0h+var_F0+8], rsi
0x1800689ce  call    cs:__imp_NgcGetSymmetricPopKeyTransportKey
0x1800689d4  test    eax, eax
0x1800689d6  jns     short loc_180068A17
0x1800689d8  mov     rcx, qword ptr [rbp+0A0h+var_F0+8]
0x1800689dc  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800689e3  mov     dword ptr [rsp+1A0h+var_160], ebx
0x1800689e7  xor     r9d, r9d
0x1800689ea  mov     [rsp+1A0h+var_168], rsi
0x1800689ef  mov     r8d, eax
0x1800689f2  mov     qword ptr [rsp+1A0h+var_178+8], rcx
0x1800689f7  mov     rcx, qword ptr [rbp+0A0h+var_F0]
0x1800689fb  mov     qword ptr [rsp+1A0h+var_178], rcx
0x180068a00  mov     rcx, [rbp+0A0h+var_F8]
0x180068a04  mov     [rsp+1A0h+var_180], rcx
0x180068a09  lea     rcx, aSCannotGetExis; "%s: Cannot get existing transport key. "...
0x180068a10  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180068a15  jmp     short loc_180068A43
0x180068a17  mov     ecx, [rbp+0A0h+arg_0]
0x180068a1d  lea     rdx, [rbp+0A0h+arg_28]
  ... truncated ...
```
