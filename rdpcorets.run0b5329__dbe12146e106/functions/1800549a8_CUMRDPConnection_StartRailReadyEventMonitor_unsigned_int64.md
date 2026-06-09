# CUMRDPConnection::StartRailReadyEventMonitor(unsigned __int64)

- ea: `0x1800549a8`
- end: `0x180055856`
- name: `?StartRailReadyEventMonitor@CUMRDPConnection@@IEAAJ_K@Z`
- size: `3758`
- prototype: `int(CUMRDPConnection *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800202a0`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x18000ee00`
- `0x18000f784`
- `0x180010aa0`
- `0x180012200`
- `0x180033da0`
- `0x180045144`
- `0x1800453f0`
- `0x1800549a8`
- `0x180055e40`
- `0x180055e9c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800553d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055114`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005511d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055114`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005511d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005524e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005524e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055194`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055306`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055194`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055306`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005579f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005579f`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180054c21`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180054c21`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180055535`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180055535`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800553c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800553c7`

## string_xrefs

- `0x180055567`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x180054c94`: `StartRailReadyEventMonitor`
- `0x180054d39`: `StartRailReadyEventMonitor`
- `0x180054dc3`: `StartRailReadyEventMonitor`
- `0x180054e7b`: `StartRailReadyEventMonitor`
- `0x180054f1d`: `StartRailReadyEventMonitor`
- `0x180054fba`: `StartRailReadyEventMonitor`
- `0x1800551e3`: `StartRailReadyEventMonitor`
- `0x18005528e`: `StartRailReadyEventMonitor`
- `0x180055352`: `StartRailReadyEventMonitor`
- `0x180055413`: `StartRailReadyEventMonitor`
- `0x1800554ba`: `StartRailReadyEventMonitor`
- `0x180055581`: `StartRailReadyEventMonitor`
- `0x180055633`: `StartRailReadyEventMonitor`
- `0x1800556e0`: `StartRailReadyEventMonitor`
- `0x1800557f3`: `StartRailReadyEventMonitor`
- `0x180054d1f`: `hClientToken is NULL`
- `0x180054dd9`: `RailReadyEventMonitor already exists`
- `0x18005504d`: `WVD::RailReadyEventWaitTimeout`
- `0x180055079`: `Failed to get RailReadyEvent timeout value, using default`
- `0x1800550e1`: `Skipped waiting for RailReadyEvent`
- `0x1800551c9`: `GetTokenInformation failed with 0 userTokenSize returned`
- `0x180055274`: `Failed to allocate userToken buffer`
- `0x180055338`: `GetTokenInformation failed`
- `0x1800553f9`: `ConvertSidToStringSidW failed`
- `0x1800556c6`: `Failed to create RailReadyEvent`
- `0x180055759`: `Created RailReadyEvent`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::StartRailReadyEventMonitor(CUMRDPConnection *this, void *a2, __int64 a3)
{
  char *v4; // rcx
  ULONG v5; // r15d
  PSID *v7; // r14
  bool v8; // zf
  __int64 v9; // rbx
  int v10; // r8d
  int v11; // r9d
  signed int v12; // ebx
  __int64 (__fastcall *v13)(__int64, __int128 *, __int128 *); // rax
  int v14; // r8d
  int v15; // r9d
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rdx
  __int64 v21; // r8
  signed int v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  signed int v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  signed int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  signed int v41; // eax
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // r8
  __int64 v46; // rdx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  signed int LastError; // eax
  int v54; // ecx
  int v55; // r8d
  int v56; // r9d
  int v57; // [rsp+50h] [rbp-B0h] BYREF
  char *v58; // [rsp+58h] [rbp-A8h] BYREF
  const char *v59; // [rsp+60h] [rbp-A0h] BYREF
  const char *v60; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v61[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v62; // [rsp+80h] [rbp-80h] BYREF
  ULONG dwMilliseconds; // [rsp+90h] [rbp-70h] BYREF
  DWORD TokenInformationLength; // [rsp+94h] [rbp-6Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR StringSid; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v70; // [rsp+C0h] [rbp-40h] BYREF
  PSECURITY_DESCRIPTOR v71; // [rsp+C8h] [rbp-38h]
  __int64 v72; // [rsp+D0h] [rbp-30h]
  __int128 v73; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp-18h]
  _DWORD v75[12]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v76; // [rsp+120h] [rbp+20h]
  _DWORD v77[48]; // [rsp+130h] [rbp+30h] BYREF

  v75[0] = 7077959;
  v75[1] = 6422639;
  v75[2] = 7077985;
  v4 = (char *)this + 152;
  v75[3] = 5374044;
  v75[4] = 6881377;
  v5 = 300000;
  v75[5] = 5374060;
  v75[6] = 6357093;
  v75[7] = 7929956;
  v7 = 0;
  v75[8] = 7733317;
  v75[9] = 7209061;
  v75[10] = 2949236;
  v75[11] = 7667749;
  v76 = 0;
  v77[0] = 3801156;
  v77[1] = 4259880;
  v77[2] = 3866683;
  v77[3] = 4259911;
  v77[4] = 3866683;
  v77[5] = 5439547;
  v77[6] = 3211309;
  v77[7] = 3473453;
  v77[8] = 3670061;
  v77[9] = 2949168;
  v77[10] = 3407924;
  v77[11] = 3145782;
  v77[12] = 3211317;
  v77[13] = 3342388;
  v77[14] = 2949168;
  v77[15] = 3473457;
  v77[16] = 3735605;
  v77[17] = 3407923;
  v77[18] = 3604529;
  v77[19] = 3342389;
  v77[20] = 3407917;
  v77[21] = 3538993;
  v77[22] = 3735601;
  v77[23] = 3211316;
  v77[24] = 3276853;
  v77[25] = 2949177;
  v77[26] = 3735601;
  v77[27] = 3145781;
  v77[28] = 3276857;
  v77[29] = 3473464;
  v77[30] = 3342387;
  v77[31] = 3670061;
  v77[32] = 3145777;
  v77[33] = 3670068;
  v77[34] = 3211315;
  v77[35] = 3407920;
  v77[36] = 2621481;
  v77[37] = 3866689;
  v77[38] = 3145787;
  v77[39] = 3211384;
  v77[40] = 3145776;
  v77[41] = 3145776;
  v77[42] = 3866674;
  v77[43] = 3866683;
  v77[44] = 7536677;
  v77[45] = 41;
  v73 = 0;
  hMem = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  SecurityDescriptor = 0;
  v70 = 24;
  v71 = 0;
  v72 = 1;
  dwMilliseconds = 300000;
  v8 = *((_DWORD *)v4 + 2) == 0;
  v67 = 0;
  StringSecurityDescriptor = 0;
  v68 = 0;
  v58 = v4;
  if ( !v8 )
    PAL_System_CritSecEnter(*(_QWORD *)v4, a2, a3);
  v9 = 0;
  if ( *((_QWORD *)this + 29) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v67, a2, a3);
    v9 = *((_QWORD *)this + 29);
    v67 = v9;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v67);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v58);
  if ( !v9 )
  {
    v12 = -2147467261;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v57 = 7256;
      v61[0] = "spRDPStack is NULL";
      LODWORD(v58) = -2147467261;
      v59 = "StartRailReadyEventMonitor";
      v60 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      *(_QWORD *)&v62 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467261,
        (unsigned int)byte_1801926A9,
        v10,
        v11,
        (__int64)&v62,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)v61);
    }
    goto LABEL_35;
  }
  if ( !a2 )
  {
    v12 = -2147467261;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v58) = 7259;
      *(_QWORD *)&v62 = "hClientToken is NULL";
      v57 = -2147467261;
      v60 = "StartRailReadyEventMonitor";
      v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v61[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467261,
        (unsigned int)qword_180192658,
        v10,
        v11,
        (__int64)v61,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v62);
    }
    goto LABEL_35;
  }
  if ( *((_QWORD *)this + 107) )
  {
    v12 = -2147418113;
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      LODWORD(v58) = -2147418113;
      *(_QWORD *)&v62 = "StartRailReadyEventMonitor";
      v60 = "RailReadyEventMonitor already exists";
      v59 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147418113,
        (unsigned int)byte_180192619,
        v10,
        v11,
        (__int64)&v59,
        (__int64)&v60,
        (__int64)&v58,
        (__int64)&v62);
    }
    goto LABEL_35;
  }
  v13 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v9 + 336LL);
  v62 = PROPERTY_TYPE_CONNECTION_GUID;
  v12 = v13(v9, &v62, &v73);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v58) = 7266;
      *(_QWORD *)&v62 = "Failed GetConnectionProperty PROPERTY_TYPE_CONNECTION_GUID";
      v57 = v12;
      v60 = "StartRailReadyEventMonitor";
      v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v61[0] = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)qword_1801925C8,
        v14,
        v15,
        (__int64)v61,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v62);
    }
    goto LABEL_35;
  }
  if ( (_WORD)v73 != 3 )
  {
    v12 = -2147418113;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v58) = 7267;
      *(_QWORD *)&v62 = "Invalid property value type";
      v57 = -2147418113;
      v60 = "StartRailReadyEventMonitor";
      v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v61[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147418113,
        (unsigned int)&byte_180192577,
        v14,
        v15,
        (__int64)v61,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v62);
    }
    goto LABEL_35;
  }
  if ( DWORD2(v73) != 16 )
  {
    v12 = -2147418113;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v58) = 7268;
      *(_QWORD *)&v62 = "Invalid property value size";
      v57 = -2147418113;
      v60 = "StartRailReadyEventMonitor";
      v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v61[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147418113,
        (unsigned int)&word_180192526,
        v14,
        v15,
        (__int64)v61,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v62);
    }
    goto LABEL_35;
  }
  if ( *(_QWORD *)hMem != TERMINAL_TYPE_RDP_REMOTEAPP || *((_QWORD *)hMem + 1) != 0xF44C9D49A3D3984LL )
  {
LABEL_34:
    v12 = 0;
    goto LABEL_35;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, ULONG *))(**((_QWORD **)this + 23) + 40LL))(
          *((_QWORD *)this + 23),
          L"WVD::RailReadyEventWaitTimeout",
          &dwMilliseconds);
  if ( v16 >= 0 )
  {
    v5 = dwMilliseconds;
  }
  else
  {
    v17 = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v57 = v16;
      LODWORD(v58) = 300000;
      *(_QWORD *)&v62 = "Failed to get RailReadyEvent timeout value, using default";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_1801B76C8,
        (unsigned int)&byte_1801924E7,
        v18,
        v19,
        (__int64)&v62,
        (__int64)&v57,
        (__int64)&v58);
    }
    dwMilliseconds = 300000;
  }
  if ( !v5 )
  {
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      LODWORD(v58) = dwMilliseconds;
      v57 = *((_DWORD *)this + 178);
      *(_QWORD *)&v62 = "Skipped waiting for RailReadyEvent";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)&word_1801924AE,
        v18,
        v19,
        (__int64)&v62,
        (__int64)&v57,
        (__int64)&v58);
    }
    goto LABEL_34;
  }
  GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength);
  if ( TokenInformationLength )
  {
    v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v7 )
    {
      if ( GetTokenInformation(a2, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &StringSid,
          0);
        if ( ConvertSidToStringSidW(*v7, &StringSid) )
        {
          v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &StringSecurityDescriptor,
                  v77,
                  StringSid);
          if ( v12 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &SecurityDescriptor,
              0);
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                   StringSecurityDescriptor,
                   1u,
                   &SecurityDescriptor,
                   0) )
            {
              v45 = *((unsigned int *)this + 178);
              v71 = SecurityDescriptor;
              v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &v68,
                      v75,
                      v45);
              if ( v12 >= 0 )
              {
                v12 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                        (char *)this + 864,
                        v46,
                        v68,
                        &v70);
                if ( v12 >= 0 )
                {
                  if ( (unsigned int)dword_1801B76C8 > 4 )
                  {
                    LODWORD(v58) = *((_DWORD *)this + 178);
                    *(_QWORD *)&v62 = "Created RailReadyEvent";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                      v50,
                      (unsigned int)&word_1801921F6,
                      v51,
                      v52,
                      (__int64)&v62,
                      (__int64)&v58);
                  }
                  if ( RegisterWaitForSingleObject(
                         (PHANDLE)this + 107,
                         *((HANDLE *)this + 108),
                         lambda_cb4278d1e6fb5970228797ec9080cec6_::_lambda_invoker_cdecl_,
                         (char *)this + 808,
                         dwMilliseconds,
                         8u) )
                  {
                    goto LABEL_34;
                  }
                  LastError = GetLastError();
                  v12 = LastError;
                  if ( LastError > 0 )
                    v12 = (unsigned __int16)LastError | 0x80070000;
                  if ( v12 >= 0 )
                    goto LABEL_34;
                  if ( (unsigned int)dword_1801B76C8 > 2 )
                  {
                    LODWORD(v58) = 7360;
                    *(_QWORD *)&v62 = "RegisterWaitForSingleObject failed";
                    v57 = v12;
                    v60 = "StartRailReadyEventMonitor";
                    v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
                    v61[0] = "Error HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      v54,
                      (unsigned int)byte_1801921A5,
                      v55,
                      v56,
                      (__int64)v61,
                      (__int64)&v57,
                      (__int64)&v59,
                      (__int64)&v58,
                      (__int64)&v60,
                      (__int64)&v62);
                  }
                }
                else if ( (unsigned int)dword_1801B76C8 > 2 )
                {
                  LODWORD(v58) = 7324;
                  *(_QWORD *)&v62 = "Failed to create RailReadyEvent";
                  v57 = v12;
                  v60 = "StartRailReadyEventMonitor";
                  v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
                  v61[0] = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v50,
                    (unsigned int)&word_180192226,
                    v51,
                    v52,
                    (__int64)v61,
                    (__int64)&v57,
                    (__int64)&v59,
                    (__int64)&v58,
                    (__int64)&v60,
                    (__int64)&v62);
                }
              }
              else if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                LODWORD(v58) = 7321;
                *(_QWORD *)&v62 = "str_printf_nothrow failed";
                v57 = v12;
                v60 = "StartRailReadyEventMonitor";
                v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
                v61[0] = "Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v47,
                  (unsigned int)&byte_180192277,
                  v48,
                  v49,
                  (__int64)v61,
                  (__int64)&v57,
                  (__int64)&v59,
                  (__int64)&v58,
                  (__int64)&v60,
                  (__int64)&v62);
              }
            }
            else
            {
              v41 = GetLastError();
              v12 = v41;
              if ( v41 > 0 )
                v12 = (unsigned __int16)v41 | 0x80070000;
              if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                LODWORD(v58) = 7315;
                *(_QWORD *)&v62 = "ConvertStringSecurityDescriptorToSecurityDescriptor failed";
                v57 = v12;
                v60 = "StartRailReadyEventMonitor";
                v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
                v61[0] = "Error condition failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v42,
                  (unsigned int)qword_1801922C8,
                  v43,
                  v44,
                  (__int64)v61,
                  (__int64)&v57,
                  (__int64)&v59,
                  (__int64)&v58,
                  (__int64)&v60,
                  (__int64)&v62);
              }
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v58) = 7311;
            *(_QWORD *)&v62 = "str_printf_nothrow failed";
            v57 = v12;
            v60 = "StartRailReadyEventMonitor";
            v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
            v61[0] = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v38,
              (unsigned int)byte_180192319,
              v39,
              v40,
              (__int64)v61,
              (__int64)&v57,
              (__int64)&v59,
              (__int64)&v58,
              (__int64)&v60,
              (__int64)&v62);
          }
        }
        else
        {
          v34 = GetLastError();
          v12 = v34;
          if ( v34 > 0 )
            v12 = (unsigned __int16)v34 | 0x80070000;
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v58) = 7308;
            *(_QWORD *)&v62 = "ConvertSidToStringSidW failed";
            v57 = v12;
            v60 = "StartRailReadyEventMonitor";
            v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
            v61[0] = "Error condition failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v35,
              (unsigned int)word_18019236A,
              v36,
              v37,
              (__int64)v61,
              (__int64)&v57,
              (__int64)&v59,
              (__int64)&v58,
              (__int64)&v60,
              (__int64)&v62);
          }
        }
      }
      else
      {
        v30 = GetLastError();
        v12 = v30;
        if ( v30 > 0 )
          v12 = (unsigned __int16)v30 | 0x80070000;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v58) = 7305;
          *(_QWORD *)&v62 = "GetTokenInformation failed";
          v57 = v12;
          v60 = "StartRailReadyEventMonitor";
          v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          v61[0] = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v31,
            (unsigned int)byte_1801923BB,
            v32,
            v33,
            (__int64)v61,
            (__int64)&v57,
            (__int64)&v59,
            (__int64)&v58,
            (__int64)&v60,
            (__int64)&v62);
        }
      }
    }
    else
    {
      v12 = -2147024882;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v58) = 7301;
        *(_QWORD *)&v62 = "Failed to allocate userToken buffer";
        v57 = -2147024882;
        v60 = "StartRailReadyEventMonitor";
        v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v61[0] = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v27,
          (unsigned int)&dword_18019240C,
          v28,
          v29,
          (__int64)v61,
          (__int64)&v57,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v60,
          (__int64)&v62);
      }
    }
  }
  else
  {
    v23 = GetLastError();
    v12 = v23;
    if ( v23 > 0 )
      v12 = (unsigned __int16)v23 | 0x80070000;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v58) = 7298;
      *(_QWORD *)&v62 = "GetTokenInformation failed with 0 userTokenSize returned";
      v57 = v12;
      v60 = "StartRailReadyEventMonitor";
      v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v61[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v24,
        (unsigned int)byte_18019245D,
        v25,
        v26,
        (__int64)v61,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v62);
    }
  }
LABEL_35:
  LocalFree(hMem);
  LocalFree(v7);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v67, v20, v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800549a8  mov     [rsp-8+arg_10], rbx
0x1800549ad  push    rbp
0x1800549ae  push    rsi
0x1800549af  push    rdi
0x1800549b0  push    r12
0x1800549b2  push    r13
0x1800549b4  push    r14
0x1800549b6  push    r15
0x1800549b8  lea     rbp, [rsp-100h]
0x1800549c0  sub     rsp, 200h
0x1800549c7  mov     rax, cs:__security_cookie
0x1800549ce  xor     rax, rsp
0x1800549d1  mov     [rbp+130h+var_40], rax
0x1800549d8  xor     esi, esi
0x1800549da  mov     [rbp+130h+var_140], 6C0047h
0x1800549e1  xor     eax, eax
0x1800549e3  mov     [rbp+130h+var_13C], 62006Fh
0x1800549ea  mov     rdi, rcx
0x1800549ed  mov     [rbp+130h+var_138], 6C0061h
0x1800549f4  add     rcx, 98h
0x1800549fb  mov     [rbp+130h+var_134], 52005Ch
0x180054a02  xorps   xmm0, xmm0
0x180054a05  mov     [rbp+130h+var_130], 690061h
0x180054a0c  mov     r15d, 493E0h
0x180054a12  mov     [rbp+130h+var_12C], 52006Ch
0x180054a19  mov     [rbp+130h+var_128], 610065h
0x180054a20  mov     r12, rdx
0x180054a23  mov     [rbp+130h+var_124], 790064h
0x180054a2a  mov     r14d, esi
0x180054a2d  mov     [rbp+130h+var_120], 760045h
0x180054a34  mov     [rbp+130h+var_11C], 6E0065h
0x180054a3b  mov     [rbp+130h+var_118], 2D0074h
0x180054a42  mov     [rbp+130h+var_114], 750025h
0x180054a49  mov     [rbp+130h+var_110], ax
0x180054a4d  mov     [rbp+130h+var_100], 3A0044h
0x180054a54  mov     [rbp+130h+var_FC], 410028h
0x180054a5b  mov     [rbp+130h+var_F8], 3B003Bh
0x180054a62  mov     [rbp+130h+var_F4], 410047h
0x180054a69  mov     [rbp+130h+var_F0], 3B003Bh
0x180054a70  mov     [rbp+130h+var_EC], 53003Bh
0x180054a77  mov     [rbp+130h+var_E8], 31002Dh
0x180054a7e  mov     [rbp+130h+var_E4], 35002Dh
0x180054a85  mov     [rbp+130h+var_E0], 38002Dh
0x180054a8c  mov     [rbp+130h+var_DC], 2D0030h
0x180054a93  mov     [rbp+130h+var_D8], 340034h
0x180054a9a  mov     [rbp+130h+var_D4], 300036h
0x180054aa1  mov     [rbp+130h+var_D0], 310035h
0x180054aa8  mov     [rbp+130h+var_CC], 330034h
0x180054aaf  mov     [rbp+130h+var_C8], 2D0030h
0x180054ab6  mov     [rbp+130h+var_C4], 350031h
0x180054abd  mov     [rbp+130h+var_C0], 390035h
0x180054ac4  mov     [rbp+130h+var_BC], 340033h
0x180054acb  mov     [rbp+130h+var_B8], 370031h
0x180054ad2  mov     [rbp+130h+var_B4], 330035h
0x180054ad9  mov     [rbp+130h+var_B0], 34002Dh
0x180054ae3  mov     [rbp+130h+var_AC], 360031h
0x180054aed  mov     [rbp+130h+var_A8], 390031h
0x180054af7  mov     [rbp+130h+var_A4], 310034h
0x180054b01  mov     [rbp+130h+var_A0], 320035h
0x180054b0b  mov     [rbp+130h+var_9C], 2D0039h
0x180054b15  mov     [rbp+130h+var_98], 390031h
0x180054b1f  mov     [rbp+130h+var_94], 300035h
0x180054b29  mov     [rbp+130h+var_90], 320039h
0x180054b33  mov     [rbp+130h+var_8C], 350038h
0x180054b3d  mov     [rbp+130h+var_88], 330033h
0x180054b47  mov     [rbp+130h+var_84], 38002Dh
0x180054b51  mov     [rbp+130h+var_80], 300031h
0x180054b5b  mov     [rbp+130h+var_7C], 380034h
0x180054b65  mov     [rbp+130h+var_78], 310033h
0x180054b6f  mov     [rbp+130h+var_74], 340030h
0x180054b79  mov     [rbp+130h+var_70], 280029h
0x180054b83  mov     [rbp+130h+var_6C], 3B0041h
0x180054b8d  mov     [rbp+130h+var_68], 30003Bh
0x180054b97  mov     [rbp+130h+var_64], 310078h
0x180054ba1  mov     [rbp+130h+var_60], 300030h
0x180054bab  mov     [rbp+130h+var_5C], 300030h
0x180054bb5  mov     [rbp+130h+var_58], 3B0032h
0x180054bbf  mov     [rbp+130h+var_54], 3B003Bh
0x180054bc9  mov     [rbp+130h+var_50], 730025h
0x180054bd3  mov     [rbp+130h+var_4C], 29h ; ')'
0x180054bdd  movups  [rbp+130h+var_158], xmm0
0x180054be1  mov     [rbp+130h+hMem], rax
0x180054be5  mov     [rbp+130h+TokenInformationLength], esi
0x180054be8  mov     [rbp+130h+StringSid], rsi
0x180054bec  mov     [rbp+130h+SecurityDescriptor], rsi
0x180054bf0  mov     [rbp+130h+var_170], 18h
0x180054bf8  mov     [rbp+130h+var_168], rsi
0x180054bfc  mov     [rbp+130h+var_160], 1
0x180054c04  mov     [rbp+130h+dwMilliseconds], r15d
0x180054c08  cmp     [rcx+8], esi
0x180054c0b  mov     [rbp+130h+var_188], rsi
0x180054c0f  mov     [rbp+130h+StringSecurityDescriptor], rsi
0x180054c13  mov     [rbp+130h+var_180], rsi
0x180054c17  mov     [rsp+230h+var_1D8], rcx
0x180054c1c  jz      short loc_180054C27
0x180054c1e  mov     rcx, [rcx]
0x180054c21  call    cs:__imp_PAL_System_CritSecEnter
0x180054c27  mov     rbx, rsi
0x180054c2a  cmp     [rdi+0E8h], rsi
0x180054c31  jz      short loc_180054C50
0x180054c33  lea     rcx, [rbp+130h+var_188]
0x180054c37  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180054c3c  mov     rbx, [rdi+0E8h]
0x180054c43  lea     rcx, [rbp+130h+var_188]
0x180054c47  mov     [rbp+130h+var_188], rbx
0x180054c4b  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180054c50  lea     rcx, [rsp+230h+var_1D8]; this
0x180054c55  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180054c5a  test    rbx, rbx
0x180054c5d  jnz     loc_180054D00
0x180054c63  mov     eax, cs:dword_1801B76C8
0x180054c69  mov     ecx, 80004003h
0x180054c6e  mov     ebx, ecx
0x180054c70  cmp     eax, 2
0x180054c73  jbe     loc_180055110
0x180054c79  lea     rax, aSprdpstackIsNu; "spRDPStack is NULL"
0x180054c80  mov     [rsp+230h+var_1E0], 1C58h
0x180054c88  mov     [rsp+230h+var_1C0], rax
0x180054c8d  lea     rdx, byte_1801926A9
0x180054c94  lea     rax, aStartrailready; "StartRailReadyEventMonitor"
0x180054c9b  mov     dword ptr [rsp+230h+var_1D8], ecx
0x180054c9f  mov     [rsp+230h+var_1D0], rax
0x180054ca4  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180054cab  mov     [rsp+230h+var_1C8], rax
0x180054cb0  lea     rax, aErrorCondition; "Error condition failed"
0x180054cb7  mov     qword ptr [rbp+130h+var_1B0], rax
0x180054cbb  lea     rax, [rsp+230h+var_1C0]
0x180054cc0  mov     [rsp+230h+var_1E8], rax
0x180054cc5  lea     rax, [rsp+230h+var_1D0]
0x180054cca  mov     [rsp+230h+var_1F0], rax
0x180054ccf  lea     rax, [rsp+230h+var_1E0]
0x180054cd4  mov     [rsp+230h+var_1F8], rax
0x180054cd9  lea     rax, [rsp+230h+var_1C8]
0x180054cde  mov     [rsp+230h+var_200], rax
0x180054ce3  lea     rax, [rsp+230h+var_1D8]
0x180054ce8  mov     qword ptr [rsp+230h+dwFlags], rax
0x180054ced  lea     rax, [rbp+130h+var_1B0]
0x180054cf1  mov     [rsp+230h+ReturnLength], rax
0x180054cf6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180054cfb  jmp     loc_180055110
0x180054d00  test    r12, r12
0x180054d03  jnz     loc_180054D9C
0x180054d09  mov     eax, cs:dword_1801B76C8
0x180054d0f  mov     ecx, 80004003h
0x180054d14  mov     ebx, ecx
0x180054d16  cmp     eax, 2
0x180054d19  jbe     loc_180055110
0x180054d1f  lea     rax, aHclienttokenIs; "hClientToken is NULL"
0x180054d26  mov     dword ptr [rsp+230h+var_1D8], 1C5Bh
0x180054d2e  mov     qword ptr [rbp+130h+var_1B0], rax
0x180054d32  lea     rdx, qword_180192658
0x180054d39  lea     rax, aStartrailready; "StartRailReadyEventMonitor"
0x180054d40  mov     [rsp+230h+var_1E0], ecx
0x180054d44  mov     [rsp+230h+var_1C8], rax
0x180054d49  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180054d50  mov     [rsp+230h+var_1D0], rax
0x180054d55  lea     rax, aErrorCondition; "Error condition failed"
0x180054d5c  mov     [rsp+230h+var_1C0], rax
0x180054d61  lea     rax, [rbp+130h+var_1B0]
0x180054d65  mov     [rsp+230h+var_1E8], rax
0x180054d6a  lea     rax, [rsp+230h+var_1C8]
0x180054d6f  mov     [rsp+230h+var_1F0], rax
0x180054d74  lea     rax, [rsp+230h+var_1D8]
0x180054d79  mov     [rsp+230h+var_1F8], rax
0x180054d7e  lea     rax, [rsp+230h+var_1D0]
0x180054d83  mov     [rsp+230h+var_200], rax
0x180054d88  lea     rax, [rsp+230h+var_1E0]
0x180054d8d  mov     qword ptr [rsp+230h+dwFlags], rax
0x180054d92  lea     rax, [rsp+230h+var_1C0]
0x180054d97  jmp     loc_180054CF1
0x180054d9c  lea     r13, [rdi+358h]
0x180054da3  cmp     [r13+0], rsi
0x180054da7  jz      short loc_180054E22
0x180054da9  mov     eax, cs:dword_1801B76C8
0x180054daf  mov     esi, 3
0x180054db4  mov     ecx, 8000FFFFh
0x180054db9  mov     ebx, ecx
0x180054dbb  cmp     eax, esi
0x180054dbd  jbe     loc_180055110
0x180054dc3  lea     rax, aStartrailready; "StartRailReadyEventMonitor"
0x180054dca  mov     dword ptr [rsp+230h+var_1D8], ecx
0x180054dce  mov     qword ptr [rbp+130h+var_1B0], rax
0x180054dd2  lea     rdx, byte_180192619
0x180054dd9  lea     rax, aRailreadyevent; "RailReadyEventMonitor already exists"
0x180054de0  mov     [rsp+230h+var_1C8], rax
0x180054de5  lea     rax, aErrorCondition; "Error condition failed"
0x180054dec  mov     [rsp+230h+var_1D0], rax
0x180054df1  lea     rax, [rbp+130h+var_1B0]
0x180054df5  mov     [rsp+230h+var_1F8], rax
0x180054dfa  lea     rax, [rsp+230h+var_1D8]
0x180054dff  mov     [rsp+230h+var_200], rax
0x180054e04  lea     rax, [rsp+230h+var_1C8]
0x180054e09  mov     qword ptr [rsp+230h+dwFlags], rax
0x180054e0e  lea     rax, [rsp+230h+var_1D0]
0x180054e13  mov     [rsp+230h+ReturnLength], rax
0x180054e18  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180054e1d  jmp     loc_180055110
0x180054e22  mov     rax, [rbx]
0x180054e25  lea     r8, [rbp+130h+var_158]
0x180054e29  movups  xmm0, cs:PROPERTY_TYPE_CONNECTION_GUID
0x180054e30  lea     rdx, [rbp+130h+var_1B0]
0x180054e34  mov     rcx, rbx
0x180054e37  mov     rax, [rax+150h]
0x180054e3e  movdqu  [rbp+130h+var_1B0], xmm0
0x180054e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e48  mov     ebx, eax
0x180054e4a  test    eax, eax
0x180054e4c  jns     loc_180054EDE
0x180054e52  mov     ecx, cs:dword_1801B76C8
0x180054e58  cmp     ecx, 2
0x180054e5b  jbe     loc_180055110
0x180054e61  lea     rax, aFailedGetconne_0; "Failed GetConnectionProperty PROPERTY_T"...
0x180054e68  mov     dword ptr [rsp+230h+var_1D8], 1C62h
0x180054e70  mov     qword ptr [rbp+130h+var_1B0], rax
0x180054e74  lea     rdx, qword_1801925C8
0x180054e7b  lea     rax, aStartrailready; "StartRailReadyEventMonitor"
0x180054e82  mov     [rsp+230h+var_1E0], ebx
0x180054e86  mov     [rsp+230h+var_1C8], rax
0x180054e8b  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180054e92  mov     [rsp+230h+var_1D0], rax
0x180054e97  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180054e9e  mov     [rsp+230h+var_1C0], rax
0x180054ea3  lea     rax, [rbp+130h+var_1B0]
0x180054ea7  mov     [rsp+230h+var_1E8], rax
0x180054eac  lea     rax, [rsp+230h+var_1C8]
0x180054eb1  mov     [rsp+230h+var_1F0], rax
0x180054eb6  lea     rax, [rsp+230h+var_1D8]
0x180054ebb  mov     [rsp+230h+var_1F8], rax
0x180054ec0  lea     rax, [rsp+230h+var_1D0]
0x180054ec5  mov     [rsp+230h+var_200], rax
0x180054eca  lea     rax, [rsp+230h+var_1E0]
0x180054ecf  mov     qword ptr [rsp+230h+dwFlags], rax
0x180054ed4  lea     rax, [rsp+230h+var_1C0]
0x180054ed9  jmp     loc_180054CF1
0x180054ede  mov     esi, 3
0x180054ee3  cmp     word ptr [rbp+130h+var_158], si
0x180054ee7  jz      loc_180054F80
0x180054eed  mov     eax, cs:dword_1801B76C8
0x180054ef3  mov     ecx, 8000FFFFh
0x180054ef8  mov     ebx, ecx
0x180054efa  cmp     eax, 2
0x180054efd  jbe     loc_180055110
0x180054f03  lea     rax, aInvalidPropert; "Invalid property value type"
0x180054f0a  mov     dword ptr [rsp+230h+var_1D8], 1C63h
0x180054f12  mov     qword ptr [rbp+130h+var_1B0], rax
0x180054f16  lea     rdx, byte_180192577
0x180054f1d  lea     rax, aStartrailready; "StartRailReadyEventMonitor"
0x180054f24  mov     [rsp+230h+var_1E0], ecx
0x180054f28  mov     [rsp+230h+var_1C8], rax
0x180054f2d  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180054f34  mov     [rsp+230h+var_1D0], rax
0x180054f39  lea     rax, aErrorCondition; "Error condition failed"
0x180054f40  mov     [rsp+230h+var_1C0], rax
0x180054f45  lea     rax, [rbp+130h+var_1B0]
0x180054f49  mov     [rsp+230h+var_1E8], rax
0x180054f4e  lea     rax, [rsp+230h+var_1C8]
0x180054f53  mov     [rsp+230h+var_1F0], rax
0x180054f58  lea     rax, [rsp+230h+var_1D8]
0x180054f5d  mov     [rsp+230h+var_1F8], rax
0x180054f62  lea     rax, [rsp+230h+var_1D0]
0x180054f67  mov     [rsp+230h+var_200], rax
0x180054f6c  lea     rax, [rsp+230h+var_1E0]
0x180054f71  mov     qword ptr [rsp+230h+dwFlags], rax
0x180054f76  lea     rax, [rsp+230h+var_1C0]
0x180054f7b  jmp     loc_180054CF1
0x180054f80  cmp     dword ptr [rbp+130h+var_158+8], 10h
0x180054f84  jz      loc_18005501D
0x180054f8a  mov     eax, cs:dword_1801B76C8
0x180054f90  mov     ecx, 8000FFFFh
0x180054f95  mov     ebx, ecx
0x180054f97  cmp     eax, 2
0x180054f9a  jbe     loc_180055110
0x180054fa0  lea     rax, aInvalidPropert_0; "Invalid property value size"
0x180054fa7  mov     dword ptr [rsp+230h+var_1D8], 1C64h
0x180054faf  mov     qword ptr [rbp+130h+var_1B0], rax
0x180054fb3  lea     rdx, word_180192526
0x180054fba  lea     rax, aStartrailready; "StartRailReadyEventMonitor"
0x180054fc1  mov     [rsp+230h+var_1E0], ecx
0x180054fc5  mov     [rsp+230h+var_1C8], rax
0x180054fca  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180054fd1  mov     [rsp+230h+var_1D0], rax
0x180054fd6  lea     rax, aErrorCondition; "Error condition failed"
0x180054fdd  mov     [rsp+230h+var_1C0], rax
0x180054fe2  lea     rax, [rbp+130h+var_1B0]
0x180054fe6  mov     [rsp+230h+var_1E8], rax
0x180054feb  lea     rax, [rsp+230h+var_1C8]
0x180054ff0  mov     [rsp+230h+var_1F0], rax
0x180054ff5  lea     rax, [rsp+230h+var_1D8]
0x180054ffa  mov     [rsp+230h+var_1F8], rax
0x180054fff  lea     rax, [rsp+230h+var_1D0]
0x180055004  mov     [rsp+230h+var_200], rax
0x180055009  lea     rax, [rsp+230h+var_1E0]
0x18005500e  mov     qword ptr [rsp+230h+dwFlags], rax
0x180055013  lea     rax, [rsp+230h+var_1C0]
0x180055018  jmp     loc_180054CF1
0x18005501d  mov     rcx, [rbp+130h+hMem]
0x180055021  mov     rax, [rcx]
0x180055024  cmp     rax, cs:TERMINAL_TYPE_RDP_REMOTEAPP
0x18005502b  jnz     loc_18005510E
0x180055031  mov     rax, [rcx+8]
  ... truncated ...
```
