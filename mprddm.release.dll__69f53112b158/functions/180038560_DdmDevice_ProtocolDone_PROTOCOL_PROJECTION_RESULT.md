# DdmDevice::ProtocolDone(_PROTOCOL_PROJECTION_RESULT *)

- ea: `0x180038560`
- end: `0x18003956a`
- name: `?ProtocolDone@DdmDevice@@UEAAXPEAU_PROTOCOL_PROJECTION_RESULT@@@Z`
- size: `4106`
- prototype: `void __fastcall(DdmDevice *__hidden this, struct _PROTOCOL_PROJECTION_RESULT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007d00`
- `0x180008b3c`
- `0x18000ace4`
- `0x18000b040`
- `0x180019c88`
- `0x1800265f8`
- `0x18002f010`
- `0x1800304dc`
- `0x180030684`
- `0x180037218`
- `0x180038560`
- `0x18004d028`
- `0x18005adcc`
- `0x180075588`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180039385`
- `KERNEL32!LocalFree` at `0x180039385`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003902f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800393c0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003902f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800393c0`
- `KERNEL32!AcquireSRWLockShared` at `0x180039182`
- `KERNEL32!AcquireSRWLockShared` at `0x180039182`
- `KERNEL32!ReleaseSRWLockShared` at `0x180039291`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800393ad`
- `KERNEL32!ReleaseSRWLockShared` at `0x180039291`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800393ad`
- `KERNEL32!LeaveCriticalSection` at `0x1800394f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800394f3`
- `KERNEL32!EnterCriticalSection` at `0x1800387e4`
- `KERNEL32!EnterCriticalSection` at `0x1800387e4`
- `KERNEL32!GetModuleHandleW` at `0x180038ae5`
- `KERNEL32!GetModuleHandleW` at `0x180038ae5`
- `rtutils!RouterLogEventW` at `0x180038df2`
- `rtutils!RouterLogEventW` at `0x180039323`
- `rtutils!RouterLogEventW` at `0x180039376`
- `rtutils!RouterLogEventW` at `0x180038df2`
- `rtutils!RouterLogEventW` at `0x180039323`
- `rtutils!RouterLogEventW` at `0x180039376`
- `USER32!LoadStringW` at `0x180038b05`
- `USER32!LoadStringW` at `0x180038b05`
- `CRYPT32!CertFreeCertificateContext` at `0x180038bd3`
- `CRYPT32!CertFreeCertificateContext` at `0x180038bd3`
- `CRYPT32!CertGetNameStringW` at `0x180038b5f`
- `CRYPT32!CertGetNameStringW` at `0x180038c62`
- `CRYPT32!CertGetNameStringW` at `0x180038c99`
- `CRYPT32!CertGetNameStringW` at `0x180038b5f`
- `CRYPT32!CertGetNameStringW` at `0x180038c62`
- `CRYPT32!CertGetNameStringW` at `0x180038c99`
- `CRYPT32!CertCreateCertificateContext` at `0x180038a63`
- `CRYPT32!CertCreateCertificateContext` at `0x180038a63`

## string_xrefs

- `0x180038ade`: `MPRDDM.DLL`
- `0x1800386a4`: `DdmDevice::ProtocolDone`
- `0x18003894c`: `ERROR_ACCESS_DENIED`
- `0x18003908b`: `ERROR_ACCESS_DENIED`
- `0x1800390fb`: `ERROR_ACCESS_DENIED`
- `0x1800389b2`: `Updated projection info structure`
- `0x180038a35`: `DdmDevice::ProtocolDone:  cert auth`
- `0x180038ab7`: `DdmDevice::ProtocolDone: Cannot get the certiificate context`
- `0x180038b40`: `DdmDevice::ProtocolDone: FormatMessage failed`
- `0x180038ce8`: `DdmDevice::ProtocolDone: copied username from certificate`
- `0x180038f53`: `Marking interface as CONNECTED for incoming connection at hport: %ld.`
- `0x18003922c`: `Rejecting the connection for hPort=%ld as VPN is getting disabled for this routing domain or the routing domain is getting deleted`
- `0x1800393f7`: `g_fIsICConfigured = 0x%d`
- `0x1800394bd`: `RASSQM: DATAID_RRASC_SQM_IC_CONFIG SQM_RRASC_IC_DIALUP`
- `0x180039495`: `RASSQM: DATAID_RRASC_SQM_IC_CONFIG SQM_RRASC_IC_VPN`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DdmDevice::ProtocolDone(DdmDevice *this, struct _PROTOCOL_PROJECTION_RESULT *a2)
{
  char v4; // cl
  __int64 v5; // rdx
  __int64 v6; // r9
  struct DdmConnectionTable *Instance; // rax
  __int128 *v8; // rsi
  _OWORD *v9; // rcx
  __int64 v10; // rdx
  const wchar_t *v11; // r8
  DWORD v12; // r15d
  const CERT_CONTEXT *CertificateContext; // r14
  DdmConnection *v14; // rbx
  HMODULE ModuleHandleW; // rax
  const wchar_t *v16; // r8
  DWORD NameStringW; // eax
  DWORD cchNameString; // ecx
  __int64 v19; // rdx
  STRSAFE_LPCWSTR v20; // r11
  int v21; // edx
  int v22; // eax
  __int64 v23; // rdx
  _OWORD *v24; // rcx
  DdmConnection *v25; // rax
  int v26; // eax
  unsigned int v27; // ecx
  DdmConnection *v28; // rax
  int v29; // edx
  int v30; // ecx
  DWORD v31; // r8d
  unsigned __int16 *IpAddress; // rax
  unsigned __int16 *v33; // rbx
  char v34; // al
  int v35; // edx
  DdmConnection *v36; // rcx
  DdmConnection *v37; // [rsp+30h] [rbp-D0h] BYREF
  int v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+3Ch] [rbp-C4h] BYREF
  DdmConnection *v40; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v41; // [rsp+48h] [rbp-B8h]
  __int128 v42; // [rsp+58h] [rbp-A8h]
  __int128 v43; // [rsp+68h] [rbp-98h]
  __int128 v44; // [rsp+78h] [rbp-88h]
  __int128 v45; // [rsp+88h] [rbp-78h]
  __int128 v46; // [rsp+98h] [rbp-68h]
  __int128 v47; // [rsp+A8h] [rbp-58h]
  __int128 v48; // [rsp+B8h] [rbp-48h]
  __int128 v49; // [rsp+C8h] [rbp-38h]
  __int128 v50; // [rsp+D8h] [rbp-28h]
  __int128 v51; // [rsp+E8h] [rbp-18h]
  __int128 v52; // [rsp+F8h] [rbp-8h]
  __int128 v53; // [rsp+108h] [rbp+8h]
  __int128 v54; // [rsp+118h] [rbp+18h]
  __int128 v55; // [rsp+128h] [rbp+28h] BYREF
  LPWSTR plpszSubStringArray[2]; // [rsp+138h] [rbp+38h] BYREF
  __int128 v57; // [rsp+148h] [rbp+48h]
  unsigned __int16 *v58; // [rsp+158h] [rbp+58h]
  int v59; // [rsp+160h] [rbp+60h] BYREF
  __int128 v60; // [rsp+164h] [rbp+64h]
  __int128 v61; // [rsp+174h] [rbp+74h]
  int v62; // [rsp+184h] [rbp+84h]
  _OWORD v63[4]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v64; // [rsp+1D0h] [rbp+D0h]
  int v65; // [rsp+1D8h] [rbp+D8h]
  wchar_t v66; // [rsp+1DCh] [rbp+DCh]
  __int16 v67; // [rsp+1DEh] [rbp+DEh]
  wchar_t pszDest[280]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v69; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v70[2044]; // [rsp+414h] [rbp+314h] BYREF

  *(_OWORD *)plpszSubStringArray = 0;
  v57 = 0;
  v58 = 0;
  v38 = 0;
  v63[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v63[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v63[2] = *(_OWORD *)L"000-0000-000000000000}";
  v63[3] = *(_OWORD *)L"-000000000000}";
  v64 = *(_QWORD *)L"00000}";
  v65 = *(_DWORD *)L"0}";
  v66 = a00000000000000[38];
  v67 = 0;
  v37 = 0;
  v69 = 0;
  memset_0(v70, 0, sizeof(v70));
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v55 = 0;
  v4 = byte_1800CF404;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v69) = 0;
    LOWORD(v59) = 0;
    if ( this )
      v5 = *((unsigned int *)this + 24);
    else
      v5 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v59, v5);
    v6 = (__int64)this + 96;
    if ( !this )
      v6 = 96;
    FormatRRASErrorString(&v69, L"%s (hport: %ld)", L"DdmDevice::ProtocolDone", *(_QWORD *)v6);
    v4 = byte_1800CF404;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v69,
        (unsigned int)&v55,
        0,
        (__int64)&v59);
      v4 = byte_1800CF404;
    }
  }
  if ( (unsigned int)(*((_DWORD *)this + 26) - 4) <= 1 )
  {
    (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
    Instance = DdmConnectionTable::GetInstance();
    DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), &v37);
    if ( !v37 )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v59) = 0;
        ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
        if ( (byte_1800CF404 & 0x10) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)L"No ConnObj",
            (unsigned int)&v55,
            0,
            (__int64)&v59);
      }
LABEL_135:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
      goto LABEL_136;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v37 + 16));
    if ( *((_DWORD *)this + 26) == 5 )
    {
      v41 = *(_OWORD *)a2;
      v42 = *((_OWORD *)a2 + 1);
      v43 = *((_OWORD *)a2 + 2);
      v44 = *((_OWORD *)a2 + 3);
      v45 = *((_OWORD *)a2 + 4);
      v46 = *((_OWORD *)a2 + 5);
      v47 = *((_OWORD *)a2 + 6);
      v48 = *((_OWORD *)a2 + 7);
      v8 = (__int128 *)((char *)a2 + 128);
      v49 = *v8;
      v50 = v8[1];
      v51 = v8[2];
      v52 = v8[3];
      v53 = v8[4];
      v54 = v8[5];
      v9 = (_OWORD *)((char *)v37 + 1240);
      *(_OWORD *)((char *)v37 + 1240) = v41;
      v9[1] = v42;
      v9[2] = v43;
      v9[3] = v44;
      v9[4] = v45;
      v9[5] = v46;
      v9[6] = v47;
      v9 += 8;
      *(v9 - 1) = v48;
      *v9 = v49;
      v9[1] = v50;
      v9[2] = v51;
      v9[3] = v52;
      v9[4] = v53;
      v9[5] = v54;
      if ( !(*(unsigned int (__fastcall **)(DdmDevice *, DdmConnection **))(*(_QWORD *)this + 688LL))(this, &v37) )
      {
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v59) = 0;
          ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
          if ( (byte_1800CF404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)L"ERROR_ACCESS_DENIED",
              (unsigned int)&v55,
              0,
              (__int64)&v59);
        }
        v10 = 5;
LABEL_23:
        (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 200LL))(this, v10);
        DdmConnection::Disconnect(v37, 0);
        goto LABEL_133;
      }
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v59) = 0;
        ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          v11 = L"Updated projection info structure";
LABEL_132:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (_DWORD)v11,
            (unsigned int)&v55,
            0,
            (__int64)&v59);
          goto LABEL_133;
        }
      }
      goto LABEL_133;
    }
    LogTunnelTypeTelemetryData(*((_DWORD *)this + 34), *((_DWORD *)v37 + 36) == 2);
    if ( *((_DWORD *)v37 + 20) != 128 || *((_DWORD *)a2 + 34) != 1 )
    {
LABEL_47:
      if ( *((_WORD *)v37 + 596) )
      {
        StringCbCopyW(pszDest, 0x222u, (STRSAFE_LPCWSTR)v37 + 596);
        StringCbCatW(pszDest, 0x222u, L"\\");
        StringCbCatW(pszDest, 0x222u, (STRSAFE_LPCWSTR)v37 + 339);
      }
      else
      {
        StringCbCopyW(pszDest, 0x222u, (STRSAFE_LPCWSTR)v37 + 339);
      }
      MprConvertGuidToString((char *)v37 + 1484, v19, v63);
      plpszSubStringArray[0] = (LPWSTR)v63;
      plpszSubStringArray[1] = (LPWSTR)((char *)this + 1092);
      *(_QWORD *)&v57 = pszDest;
      *((_QWORD *)&v57 + 1) = (char *)this + 714;
      v21 = *((_DWORD *)v37 + 20);
      if ( (v21 & 8) == 0 )
      {
        v22 = (*((_DWORD *)a2 + 1) == 0) + 1;
        if ( *((_DWORD *)a2 + 15) )
          v22 = *((_DWORD *)a2 + 1) == 0;
        if ( !v22 )
        {
          if ( dword_1800CF4E4 )
            RouterLogEventW(hLogHandle, 1u, 0x4F1Du, 4u, plpszSubStringArray, 0);
          v23 = 0;
LABEL_63:
          (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 200LL))(this, v23);
          goto LABEL_133;
        }
        *((_DWORD *)v37 + 20) = v21 & 0xFFFFFFFB;
        *((_BYTE *)v37 + 1224) = 0;
        v41 = *(_OWORD *)a2;
        v42 = *((_OWORD *)a2 + 1);
        v43 = *((_OWORD *)a2 + 2);
        v44 = *((_OWORD *)a2 + 3);
        v45 = *((_OWORD *)a2 + 4);
        v46 = *((_OWORD *)a2 + 5);
        v47 = *((_OWORD *)a2 + 6);
        v48 = *((_OWORD *)a2 + 7);
        v49 = *((_OWORD *)a2 + 8);
        v50 = *((_OWORD *)a2 + 9);
        v51 = *((_OWORD *)a2 + 10);
        v52 = *((_OWORD *)a2 + 11);
        v53 = *((_OWORD *)a2 + 12);
        v54 = *((_OWORD *)a2 + 13);
        v24 = (_OWORD *)((char *)v37 + 1240);
        *(_OWORD *)((char *)v37 + 1240) = v41;
        v24[1] = v42;
        v24[2] = v43;
        v24[3] = v44;
        v24[4] = v45;
        v24[5] = v46;
        v24[6] = v47;
        v24 += 8;
        *(v24 - 1) = v48;
        *v24 = v49;
        v24[1] = v50;
        v24[2] = v51;
        v24[3] = v52;
        v24[4] = v53;
        v24[5] = v54;
        *((_DWORD *)v37 + 20) |= 8u;
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v69) = 0;
          LOWORD(v59) = 0;
          ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
          FormatRRASErrorString(
            &v69,
            L"Marking interface as CONNECTED for incoming connection at hport: %ld.",
            *((_QWORD *)this + 12));
          if ( (byte_1800CF404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v69,
              (unsigned int)&v55,
              0,
              (__int64)&v59);
        }
        v25 = v37;
        v40 = v37;
        if ( v37 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v37 + 2);
          v25 = v37;
        }
        if ( (unsigned int)IfObjectConnectedEx(
                             *((_QWORD *)v25 + 9),
                             *((_QWORD *)v25 + 7),
                             (int)v25 + 1240,
                             (unsigned int)&v40,
                             1) )
        {
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            LOWORD(v59) = 0;
            ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
            if ( (byte_1800CF404 & 0x10) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceInfo,
                (unsigned int)L"Interface does not exist anymore",
                (unsigned int)&v55,
                0,
                (__int64)&v59);
          }
          v10 = 0;
          goto LABEL_23;
        }
        GetSystemTimeAsFileTime((LPFILETIME)v37 + 11);
        if ( !(*(unsigned int (__fastcall **)(DdmDevice *, DdmConnection **))(*(_QWORD *)this + 672LL))(this, &v37) )
        {
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            LOWORD(v59) = 0;
            ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
            if ( (byte_1800CF404 & 0x10) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceInfo,
                (unsigned int)L"ERROR_ACCESS_DENIED",
                (unsigned int)&v55,
                0,
                (__int64)&v59);
          }
          v10 = 5;
          goto LABEL_23;
        }
      }
      if ( !(*(unsigned int (__fastcall **)(DdmDevice *, DdmConnection **))(*(_QWORD *)this + 664LL))(this, &v37) )
      {
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v59) = 0;
          ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
          if ( (byte_1800CF404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)L"ERROR_ACCESS_DENIED",
              (unsigned int)&v55,
              0,
              (__int64)&v59);
        }
        v23 = 5;
        goto LABEL_63;
      }
      v26 = *((_DWORD *)this + 33);
      if ( (v26 & 8) == 0 )
      {
        if ( (v26 & 0x40) != 0 )
          MediaObjRemoveFromTable((wchar_t *)this + 391);
        *((_DWORD *)this + 33) |= 8u;
        v27 = ++dword_1800CF4B0;
        if ( *((_DWORD *)v37 + 36) != 2 )
        {
          ++gblTotalConnections;
          if ( v27 > gblMaxActiveConnections )
            gblMaxActiveConnections = v27;
        }
        DdmDevice::LogConnectEvent(this, &v37, a2);
      }
      AcquireSRWLockShared(&SRWLock);
      v28 = v37;
      if ( !*((_DWORD *)v37 + 36)
        && v37 != (DdmConnection *)-1484LL
        && (*(_QWORD *)((char *)v37 + 1484) != *(_QWORD *)&GUID_NULL.Data1
         || *(_QWORD *)((char *)v37 + 1492) != *(_QWORD *)GUID_NULL.Data4) )
      {
        v39 = 4;
        if ( (unsigned int)RasRoutingDomainGetConfigParam((char *)v37 + 1484, 10, &v39, &v38) == 1168 || (v38 & 9) == 0 )
        {
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v69) = 0;
            LOWORD(v59) = 0;
            ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
            FormatRRASErrorString(
              &v69,
              L"Rejecting the connection for hPort=%ld as VPN is getting disabled for this routing domain or the routing d"
               "omain is getting deleted",
              *((_QWORD *)this + 12));
            if ( (byte_1800CF404 & 8) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceError,
                (unsigned int)&v69,
                (unsigned int)&v55,
                0,
                (__int64)&v59);
          }
          (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 200LL))(this, 913);
          ReleaseSRWLockShared(&SRWLock);
          goto LABEL_133;
        }
        v28 = v37;
      }
      if ( *((_DWORD *)v28 + 345) == 18
        && *((_DWORD *)v28 + 347) == 18
        && (v29 = *((_DWORD *)v28 + 348), (v29 & 0xF0) != 0)
        && (v30 = *((_DWORD *)v28 + 346), (v30 & 0xF0) != 0) )
      {
        if ( ((unsigned __int8)v29 & (unsigned __int8)v30 & 0x40) != 0 )
        {
          if ( (unsigned int)dword_1800CF4E4 > 2 )
          {
            v31 = 20266;
LABEL_113:
            RouterLogEventW(hLogHandle, 4u, v31, 4u, plpszSubStringArray, 0);
          }
        }
        else if ( (unsigned int)dword_1800CF4E4 > 2 )
        {
          v31 = 20265;
          goto LABEL_113;
        }
      }
      else if ( (unsigned int)dword_1800CF4E4 > 2 )
      {
        v31 = 20250;
        goto LABEL_113;
      }
      if ( !*((_DWORD *)a2 + 1) )
      {
        IpAddress = GetIpAddress(*((_DWORD *)a2 + 9));
        v33 = IpAddress;
        if ( IpAddress )
        {
          v58 = IpAddress;
          if ( (unsigned int)dword_1800CF4E4 > 2 )
            RouterLogEventW(hLogHandle, 4u, 0x4F32u, 5u, plpszSubStringArray, 0);
          LocalFree(v33);
        }
      }
      *((_DWORD *)this + 26) = 5;
      ++*((_DWORD *)this + 293);
      *((_DWORD *)this + 33) |= 0x1000u;
      ReleaseSRWLockShared(&SRWLock);
      GetSystemTimeAsFileTime((LPFILETIME)this + 18);
      v34 = byte_1800CF404;
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v69) = 0;
        LOWORD(v59) = 0;
        ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
        FormatRRASErrorString(&v69, L"g_fIsICConfigured = 0x%d", (unsigned int)g_fIsICConfigured);
        v34 = byte_1800CF404;
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)&v69,
            (unsigned int)&v55,
            0,
            (__int64)&v59);
          v34 = byte_1800CF404;
        }
      }
      if ( !g_fIsICConfigured )
        goto LABEL_133;
      v35 = *((_DWORD *)this + 34);
      if ( (v35 & 0xFFFF0000) == 0x40000 || (v35 & 0xFFFD) == 0 )
      {
        if ( (v34 & 0x10) != 0 )
        {
          LOWORD(v59) = 0;
          ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            v11 = L"RASSQM: DATAID_RRASC_SQM_IC_CONFIG SQM_RRASC_IC_DIALUP";
            goto LABEL_132;
          }
        }
      }
      else if ( (v35 & 0xFFFF0000) == 0x10000 && (v34 & 0x10) != 0 )
      {
        LOWORD(v59) = 0;
        ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          v11 = L"RASSQM: DATAID_RRASC_SQM_IC_CONFIG SQM_RRASC_IC_VPN";
          goto LABEL_132;
        }
      }
LABEL_133:
      if ( v37 )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v37 + 16));
      goto LABEL_135;
    }
    v12 = 5;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      LOWORD(v59) = 0;
      ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)L"DdmDevice::ProtocolDone:  cert auth",
          (unsigned int)&v55,
          0,
          (__int64)&v59);
    }
    CertificateContext = CertCreateCertificateContext(
                           *((_DWORD *)a2 + 44),
                           *((const BYTE **)a2 + 21),
                           *((_DWORD *)a2 + 40));
    if ( !CertificateContext )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v59) = 0;
        ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
        if ( (byte_1800CF404 & 0x10) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)L"DdmDevice::ProtocolDone: Cannot get the certiificate context",
            (unsigned int)&v55,
            0,
            (__int64)&v59);
      }
      goto LABEL_47;
    }
    v14 = v37;
    ModuleHandleW = GetModuleHandleW(L"MPRDDM.DLL");
    if ( !LoadStringW(ModuleHandleW, 0xCCu, (LPWSTR)v14 + 339, 257) )
    {
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_46;
      LOWORD(v59) = 0;
      ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_46;
      v16 = L"DdmDevice::ProtocolDone: FormatMessage failed";
LABEL_45:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (_DWORD)v16,
        (unsigned int)&v55,
        0,
        (__int64)&v59);
LABEL_46:
      CertFreeCertificateContext(CertificateContext);
      goto LABEL_47;
    }
    NameStringW = CertGetNameStringW(CertificateContext, 5u, 0, 0, 0, 0);
    cchNameString = NameStringW;
    if ( NameStringW <= 1 )
    {
      v12 = 6;
      cchNameString = CertGetNameStringW(CertificateContext, 6u, 0, 0, 0, 0);
      if ( cchNameString <= 1 )
      {
LABEL_42:
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_46;
        LOWORD(v59) = 0;
        ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
        if ( (byte_1800CF404 & 8) == 0 )
          goto LABEL_46;
        v16 = L"GetRasiConnectionDataEx: CertGetNameString failed to return name of certificate";
        goto LABEL_45;
      }
    }
    else if ( NameStringW > 0x101 )
    {
      goto LABEL_42;
    }
    if ( CertGetNameStringW(CertificateContext, v12, 0, 0, (LPWSTR)v37 + 339, cchNameString) - 2 <= 0xFF )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v59) = 0;
        ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
        if ( (byte_1800CF404 & 0x10) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceInfo,
            (unsigned int)L"DdmDevice::ProtocolDone: copied username from certificate",
            (unsigned int)&v55,
            0,
            (__int64)&v59);
      }
      StringCbCopyW((STRSAFE_LPWSTR)this + 84, 0x202u, (STRSAFE_LPCWSTR)v37 + 339);
      StringCbCopyW((STRSAFE_LPWSTR)v37 + 82, 0x202u, v20);
      goto LABEL_46;
    }
    goto LABEL_42;
  }
  if ( (v4 & 0x10) != 0 )
  {
    LOWORD(v59) = 0;
    ConvertPortNoToString(&v59, *((unsigned int *)this + 24));
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)L"We are not authenicating and not been authenticated",
        (unsigned int)&v55,
        0,
        (__int64)&v59);
  }
LABEL_136:
  v36 = v37;
  if ( v37 && _InterlockedExchangeAdd((volatile signed __int32 *)v37 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( v36 )
      (**(void (__fastcall ***)(DdmConnection *, __int64))v36)(v36, 1);
  }
}

```

## disassembly

```asm
0x180038560  mov     [rsp-8+arg_10], rbx
0x180038565  push    rbp
0x180038566  push    rsi
0x180038567  push    rdi
0x180038568  push    r12
0x18003856a  push    r13
0x18003856c  push    r14
0x18003856e  push    r15
0x180038570  lea     rbp, [rsp-0B20h]
0x180038578  sub     rsp, 0C20h
0x18003857f  mov     rax, cs:__security_cookie
0x180038586  xor     rax, rsp
0x180038589  mov     [rbp+0B50h+var_40], rax
0x180038590  mov     rsi, rdx
0x180038593  mov     rdi, rcx
0x180038596  xorps   xmm0, xmm0
0x180038599  xor     eax, eax
0x18003859b  movups  xmmword ptr [rbp+0B50h+plpszSubStringArray], xmm0
0x18003859f  movups  [rbp+0B50h+var_B08], xmm0
0x1800385a3  mov     [rbp+0B50h+var_AF8], rax
0x1800385a7  xor     r13d, r13d
0x1800385aa  mov     [rsp+0C50h+var_C18], r13d
0x1800385af  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800385b6  movaps  [rbp+0B50h+var_AC0], xmm0
0x1800385bd  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x1800385c4  movaps  [rbp+0B50h+var_AB0], xmm1
0x1800385cb  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x1800385d2  movaps  [rbp+0B50h+var_AA0], xmm0
0x1800385d9  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x1800385e0  movaps  [rbp+0B50h+var_A90], xmm1
0x1800385e7  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x1800385ef  movsd   [rbp+0B50h+var_A80], xmm0
0x1800385f7  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x1800385fd  mov     [rbp+0B50h+var_A78], eax
0x180038603  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x18003860a  mov     [rbp+0B50h+var_A74], ax
0x180038611  xor     eax, eax
0x180038613  mov     [rbp+0B50h+var_A72], ax
0x18003861a  mov     [rsp+0C50h+var_C20], r13
0x18003861f  mov     [rbp+0B50h+var_840], r13d
0x180038626  xor     edx, edx; Val
0x180038628  mov     r8d, 7FCh; Size
0x18003862e  lea     rcx, [rbp+0B50h+var_83C]; void *
0x180038635  call    memset_0
0x18003863a  mov     [rbp+0B50h+var_AF0], r13d
0x18003863e  xorps   xmm0, xmm0
0x180038641  xor     eax, eax
0x180038643  movups  [rbp+0B50h+var_AEC], xmm0
0x180038647  movups  [rbp+0B50h+var_ADC], xmm0
0x18003864b  mov     [rbp+0B50h+var_ACC], eax
0x180038651  movups  [rbp+0B50h+var_B28], xmm0
0x180038655  mov     cl, cs:byte_1800CF404
0x18003865b  lea     r15, RasDdmParamTraceInfo
0x180038662  mov     r14b, 10h
0x180038665  test    r14b, cl
0x180038668  jz      loc_1800386F7
0x18003866e  mov     word ptr [rbp+0B50h+var_840], r13w
0x180038676  mov     word ptr [rbp+0B50h+var_AF0], r13w
0x18003867b  test    rdi, rdi
0x18003867e  jz      short loc_180038685
0x180038680  mov     edx, [rdi+60h]
0x180038683  jmp     short loc_180038688
0x180038685  or      edx, 0FFFFFFFFh
0x180038688  lea     rcx, [rbp+0B50h+var_AF0]
0x18003868c  call    ConvertPortNoToString
0x180038691  lea     r9, [rdi+60h]
0x180038695  mov     eax, 60h ; '`'
0x18003869a  test    rdi, rdi
0x18003869d  cmovz   r9, rax
0x1800386a1  mov     r9, [r9]
0x1800386a4  lea     r8, aDdmdeviceProto_4; "DdmDevice::ProtocolDone"
0x1800386ab  lea     rdx, aSHportLd; "%s (hport: %ld)"
0x1800386b2  lea     rcx, [rbp+0B50h+var_840]
0x1800386b9  call    FormatRRASErrorString
0x1800386be  mov     cl, cs:byte_1800CF404
0x1800386c4  test    r14b, cl
0x1800386c7  jz      short loc_1800386F7
0x1800386c9  lea     rax, [rbp+0B50h+var_AF0]
0x1800386cd  mov     qword ptr [rsp+0C50h+cchNameString], rax
0x1800386d2  mov     [rsp+0C50h+pszNameString], r13
0x1800386d7  lea     r9, [rbp+0B50h+var_B28]
0x1800386db  lea     r8, [rbp+0B50h+var_840]
0x1800386e2  mov     rdx, r15
0x1800386e5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800386ec  call    McTemplateU0zjzz_EventWriteTransfer
0x1800386f1  mov     cl, cs:byte_1800CF404
0x1800386f7  mov     eax, [rdi+68h]
0x1800386fa  sub     eax, 4
0x1800386fd  cmp     eax, 1
0x180038700  jbe     short loc_180038756
0x180038702  test    r14b, cl
0x180038705  jz      loc_180039513
0x18003870b  mov     word ptr [rbp+0B50h+var_AF0], r13w
0x180038710  mov     edx, [rdi+60h]
0x180038713  lea     rcx, [rbp+0B50h+var_AF0]
0x180038717  call    ConvertPortNoToString
0x18003871c  test    cs:byte_1800CF404, r14b
0x180038723  jz      loc_180039513
0x180038729  lea     rax, [rbp+0B50h+var_AF0]
0x18003872d  mov     qword ptr [rsp+0C50h+cchNameString], rax
0x180038732  mov     [rsp+0C50h+pszNameString], r13
0x180038737  lea     r9, [rbp+0B50h+var_B28]
0x18003873b  lea     r8, aWeAreNotAuthen; "We are not authenicating and not been a"...
0x180038742  mov     rdx, r15
0x180038745  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003874c  call    McTemplateU0zjzz_EventWriteTransfer
0x180038751  jmp     loc_180039513
0x180038756  mov     rcx, cs:g_pIDimInterfaceTable
0x18003875d  mov     rax, [rcx]
0x180038760  mov     rax, [rax]
0x180038763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038768  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18003876d  lea     r8, [rsp+0C50h+var_C20]
0x180038772  mov     rdx, [rdi+78h]
0x180038776  mov     rcx, rax
0x180038779  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x18003877e  mov     rcx, [rsp+0C50h+var_C20]
0x180038783  test    rcx, rcx
0x180038786  jnz     short loc_1800387E0
0x180038788  test    cs:byte_1800CF404, r14b
0x18003878f  jz      loc_1800394FF
0x180038795  mov     word ptr [rbp+0B50h+var_AF0], r13w
0x18003879a  mov     edx, [rdi+60h]
0x18003879d  lea     rcx, [rbp+0B50h+var_AF0]
0x1800387a1  call    ConvertPortNoToString
0x1800387a6  test    cs:byte_1800CF404, r14b
0x1800387ad  jz      loc_1800394FF
0x1800387b3  lea     rax, [rbp+0B50h+var_AF0]
0x1800387b7  mov     qword ptr [rsp+0C50h+cchNameString], rax
0x1800387bc  mov     [rsp+0C50h+pszNameString], r13
0x1800387c1  lea     r9, [rbp+0B50h+var_B28]
0x1800387c5  lea     r8, aNoConnobj; "No ConnObj"
0x1800387cc  mov     rdx, r15
0x1800387cf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800387d6  call    McTemplateU0zjzz_EventWriteTransfer
0x1800387db  jmp     loc_1800394FF
0x1800387e0  add     rcx, 10h; lpCriticalSection
0x1800387e4  call    cs:__imp_EnterCriticalSection
0x1800387eb  nop     dword ptr [rax+rax+00h]
0x1800387f0  mov     ebx, 5
0x1800387f5  cmp     [rdi+68h], ebx
0x1800387f8  jnz     loc_1800389BE
0x1800387fe  lea     rax, [rsp+0C50h+var_C08]
0x180038803  movups  xmm0, xmmword ptr [rsi]
0x180038806  movups  xmmword ptr [rax], xmm0
0x180038809  movups  xmm1, xmmword ptr [rsi+10h]
0x18003880d  movups  xmmword ptr [rax+10h], xmm1
0x180038811  movups  xmm0, xmmword ptr [rsi+20h]
0x180038815  movups  xmmword ptr [rax+20h], xmm0
0x180038819  movups  xmm1, xmmword ptr [rsi+30h]
0x18003881d  movups  xmmword ptr [rax+30h], xmm1
0x180038821  movups  xmm0, xmmword ptr [rsi+40h]
0x180038825  movups  xmmword ptr [rax+40h], xmm0
0x180038829  movups  xmm1, xmmword ptr [rsi+50h]
0x18003882d  movups  xmmword ptr [rax+50h], xmm1
0x180038831  movups  xmm0, xmmword ptr [rsi+60h]
0x180038835  movups  xmmword ptr [rax+60h], xmm0
0x180038839  lea     r12d, [rbx+7Bh]
0x18003883d  add     rax, r12
0x180038840  movups  xmm0, xmmword ptr [rsi+70h]
0x180038844  movups  xmmword ptr [rax-10h], xmm0
0x180038848  add     rsi, r12
0x18003884b  movups  xmm1, xmmword ptr [rsi]
0x18003884e  movups  xmmword ptr [rax], xmm1
0x180038851  movups  xmm0, xmmword ptr [rsi+10h]
0x180038855  movups  xmmword ptr [rax+10h], xmm0
0x180038859  movups  xmm1, xmmword ptr [rsi+20h]
0x18003885d  movups  xmmword ptr [rax+20h], xmm1
0x180038861  movups  xmm0, xmmword ptr [rsi+30h]
0x180038865  movups  xmmword ptr [rax+30h], xmm0
0x180038869  movups  xmm1, xmmword ptr [rsi+40h]
0x18003886d  movups  xmmword ptr [rax+40h], xmm1
0x180038871  movups  xmm0, xmmword ptr [rsi+50h]
0x180038875  movups  xmmword ptr [rax+50h], xmm0
0x180038879  mov     rcx, [rsp+0C50h+var_C20]
0x18003887e  add     rcx, 4D8h
0x180038885  lea     rax, [rsp+0C50h+var_C08]
0x18003888a  movups  xmm0, xmmword ptr [rax]
0x18003888d  movups  xmmword ptr [rcx], xmm0
0x180038890  movups  xmm1, xmmword ptr [rax+10h]
0x180038894  movups  xmmword ptr [rcx+10h], xmm1
0x180038898  movups  xmm0, xmmword ptr [rax+20h]
0x18003889c  movups  xmmword ptr [rcx+20h], xmm0
0x1800388a0  movups  xmm1, xmmword ptr [rax+30h]
0x1800388a4  movups  xmmword ptr [rcx+30h], xmm1
0x1800388a8  movups  xmm0, xmmword ptr [rax+40h]
0x1800388ac  movups  xmmword ptr [rcx+40h], xmm0
0x1800388b0  movups  xmm1, xmmword ptr [rax+50h]
0x1800388b4  movups  xmmword ptr [rcx+50h], xmm1
0x1800388b8  movups  xmm0, xmmword ptr [rax+60h]
0x1800388bc  movups  xmmword ptr [rcx+60h], xmm0
0x1800388c0  add     rcx, r12
0x1800388c3  movups  xmm1, xmmword ptr [rax+70h]
0x1800388c7  movups  xmmword ptr [rcx-10h], xmm1
0x1800388cb  add     rax, r12
0x1800388ce  movups  xmm0, xmmword ptr [rax]
0x1800388d1  movups  xmmword ptr [rcx], xmm0
0x1800388d4  movups  xmm1, xmmword ptr [rax+10h]
0x1800388d8  movups  xmmword ptr [rcx+10h], xmm1
0x1800388dc  movups  xmm0, xmmword ptr [rax+20h]
0x1800388e0  movups  xmmword ptr [rcx+20h], xmm0
0x1800388e4  movups  xmm1, xmmword ptr [rax+30h]
0x1800388e8  movups  xmmword ptr [rcx+30h], xmm1
0x1800388ec  movups  xmm0, xmmword ptr [rax+40h]
0x1800388f0  movups  xmmword ptr [rcx+40h], xmm0
0x1800388f4  movups  xmm1, xmmword ptr [rax+50h]
0x1800388f8  movups  xmmword ptr [rcx+50h], xmm1
0x1800388fc  mov     rax, [rdi]
0x1800388ff  lea     rdx, [rsp+0C50h+var_C20]
0x180038904  mov     rcx, rdi
0x180038907  mov     rax, [rax+2B0h]
0x18003890e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038913  test    eax, eax
0x180038915  jnz     short loc_180038987
0x180038917  test    cs:byte_1800CF404, r14b
0x18003891e  jz      short loc_180038962
0x180038920  mov     word ptr [rbp+0B50h+var_AF0], r13w
0x180038925  mov     edx, [rdi+60h]
0x180038928  lea     rcx, [rbp+0B50h+var_AF0]
0x18003892c  call    ConvertPortNoToString
0x180038931  test    cs:byte_1800CF404, r14b
0x180038938  jz      short loc_180038962
0x18003893a  lea     rax, [rbp+0B50h+var_AF0]
0x18003893e  mov     qword ptr [rsp+0C50h+cchNameString], rax
0x180038943  mov     [rsp+0C50h+pszNameString], r13
0x180038948  lea     r9, [rbp+0B50h+var_B28]
0x18003894c  lea     r8, aErrorAccessDen; "ERROR_ACCESS_DENIED"
0x180038953  mov     rdx, r15
0x180038956  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003895d  call    McTemplateU0zjzz_EventWriteTransfer
0x180038962  mov     edx, ebx
0x180038964  mov     rax, [rdi]
0x180038967  mov     rcx, rdi
0x18003896a  mov     rax, [rax+0C8h]
0x180038971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038976  xor     edx, edx; void *
0x180038978  mov     rcx, [rsp+0C50h+var_C20]; this
0x18003897d  call    ?Disconnect@DdmConnection@@QEAAKPEAX@Z; DdmConnection::Disconnect(void *)
0x180038982  jmp     loc_1800394E5
0x180038987  test    cs:byte_1800CF404, r14b
0x18003898e  jz      loc_1800394E5
0x180038994  mov     word ptr [rbp+0B50h+var_AF0], r13w
0x180038999  mov     edx, [rdi+60h]
0x18003899c  lea     rcx, [rbp+0B50h+var_AF0]
0x1800389a0  call    ConvertPortNoToString
0x1800389a5  test    cs:byte_1800CF404, r14b
0x1800389ac  jz      loc_1800394E5
0x1800389b2  lea     r8, aUpdatedProject; "Updated projection info structure"
0x1800389b9  jmp     loc_1800394C4
0x1800389be  mov     edx, r13d
0x1800389c1  mov     rax, [rsp+0C50h+var_C20]
0x1800389c6  cmp     dword ptr [rax+90h], 2
0x1800389cd  setz    dl; int
0x1800389d0  mov     ecx, [rdi+88h]; unsigned int
0x1800389d6  call    ?LogTunnelTypeTelemetryData@@YAXKH@Z; LogTunnelTypeTelemetryData(ulong,int)
0x1800389db  mov     r12d, 80h
0x1800389e1  mov     rax, [rsp+0C50h+var_C20]
0x1800389e6  cmp     [rax+50h], r12d
0x1800389ea  jnz     loc_180038BE9
0x1800389f0  cmp     dword ptr [rsi+88h], 1
0x1800389f7  jnz     loc_180038BE9
0x1800389fd  mov     r15d, ebx
0x180038a00  test    cs:byte_1800CF404, r14b
0x180038a07  jz      short loc_180038A4F
0x180038a09  mov     word ptr [rbp+0B50h+var_AF0], r13w
0x180038a0e  mov     edx, [rdi+60h]
0x180038a11  lea     rcx, [rbp+0B50h+var_AF0]
0x180038a15  call    ConvertPortNoToString
0x180038a1a  test    cs:byte_1800CF404, r14b
0x180038a21  jz      short loc_180038A4F
0x180038a23  lea     rax, [rbp+0B50h+var_AF0]
0x180038a27  mov     qword ptr [rsp+0C50h+cchNameString], rax
0x180038a2c  mov     [rsp+0C50h+pszNameString], r13
0x180038a31  lea     r9, [rbp+0B50h+var_B28]
0x180038a35  lea     r8, aDdmdeviceProto; "DdmDevice::ProtocolDone:  cert auth"
0x180038a3c  lea     rdx, RasDdmParamTraceInfo
0x180038a43  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038a4a  call    McTemplateU0zjzz_EventWriteTransfer
0x180038a4f  mov     r8d, [rsi+0A0h]; cbCertEncoded
0x180038a56  mov     rdx, [rsi+0A8h]; pbCertEncoded
0x180038a5d  mov     ecx, [rsi+0B0h]; dwCertEncodingType
0x180038a63  call    cs:__imp_CertCreateCertificateContext
0x180038a6a  nop     dword ptr [rax+rax+00h]
0x180038a6f  mov     r14, rax
0x180038a72  test    rax, rax
0x180038a75  jnz     short loc_180038AD9
0x180038a77  mov     r14b, 10h
0x180038a7a  test    cs:byte_1800CF404, r14b
0x180038a81  jz      loc_180038BE2
0x180038a87  mov     word ptr [rbp+0B50h+var_AF0], r13w
0x180038a8c  mov     edx, [rdi+60h]
0x180038a8f  lea     rcx, [rbp+0B50h+var_AF0]
0x180038a93  call    ConvertPortNoToString
0x180038a98  test    cs:byte_1800CF404, r14b
0x180038a9f  jz      loc_180038BE2
0x180038aa5  lea     rax, [rbp+0B50h+var_AF0]
0x180038aa9  mov     qword ptr [rsp+0C50h+cchNameString], rax
0x180038aae  mov     [rsp+0C50h+pszNameString], r13
0x180038ab3  lea     r9, [rbp+0B50h+var_B28]
0x180038ab7  lea     r8, aDdmdeviceProto_2; "DdmDevice::ProtocolDone: Cannot get the"...
  ... truncated ...
```
