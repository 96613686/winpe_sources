# CWin32SerialPort::LoadPropertyValues(CInstance *,CConfigMgrDevice *,ushort const *,uchar * const)

- ea: `0x180055de0`
- end: `0x180056884`
- name: `?LoadPropertyValues@CWin32SerialPort@@IEAAJPEAVCInstance@@PEAVCConfigMgrDevice@@PEBGQEAE@Z`
- size: `2724`
- prototype: `int(CWin32SerialPort *__hidden this, struct CInstance *, struct CConfigMgrDevice *, const unsigned __int16 *, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800557fc`

## callees

- `0x180005988`
- `0x1800086bc`
- `0x180008820`
- `0x18000bc90`
- `0x18000cac0`
- `0x18001a310`
- `0x180053b58`
- `0x180055de0`
- `0x180069d70`
- `0x1800ea460`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800567fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800567fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005680d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005680d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180056191`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180056191`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x1800567b2`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x1800567b2`
- `api-ms-win-core-comm-l1-1-0!GetCommProperties` at `0x1800561c6`
- `api-ms-win-core-comm-l1-1-0!GetCommProperties` at `0x1800561c6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180055ed2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180055fef`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180055ffb`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800560a5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180056134`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800563d6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180055ed2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180055fef`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180055ffb`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800560a5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180056134`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800563d6`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180056146`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180056146`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180056151`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180056151`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180055e8a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180055eab`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800561e8`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180056202`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800563c2`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180055e8a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180055eab`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800561e8`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180056202`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800563c2`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180055ef9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180055fe4`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180056058`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180056073`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18005608e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800560cc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18005655d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180055ef9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180055fe4`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180056058`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180056073`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18005608e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800560cc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18005655d`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180055fa5`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056110`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005658a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800565aa`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800565cb`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800565ec`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005660d`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056633`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056654`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056675`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056696`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800566b7`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800566d6`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800566f6`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056716`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056732`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056753`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056774`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056795`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800567cd`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180055fa5`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056110`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005658a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800565aa`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800565cb`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800565ec`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005660d`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056633`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056654`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056675`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056696`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800566b7`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800566d6`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800566f6`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056716`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056732`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056753`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056774`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180056795`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800567cd`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18005603d`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18005603d`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x18005611c`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x18005611c`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180055fc2`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180055fc2`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180055e51`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180055e51`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180055fd1`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180055fd1`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180056029`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180056029`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180056548`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180056548`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180055ec1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180055ec1`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180055e3f`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800567f2`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180056841`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180055e3f`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800567f2`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180056841`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180055f82`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180055f82`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180055f05`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800560d8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800561a4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180056569`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18005684d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180056859`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180055f05`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800560d8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800561a4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180056569`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18005684d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180056859`
- `OLEAUT32!__imp_VariantInit` at `0x180055f1b`
- `OLEAUT32!__imp_VariantInit` at `0x180055f1b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180055f40`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180055f40`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180055f6a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180055f6a`

## string_xrefs

- `0x180055ea1`: `ConfigManagerUserConfig`
- `0x180055e80`: `ConfigManagerErrorCode`
- `0x180055fb1`: `Win32_ComputerSystem`
- `0x18005652a`: `LAT Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWin32SerialPort::LoadPropertyValues(
        CWin32SerialPort *this,
        struct CInstance *a2,
        struct CConfigMgrDevice *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *const a5)
{
  unsigned int IsUsingForcedConfig; // eax
  SAFEARRAY *v10; // rax
  const struct CHString *LocalComputerName; // rax
  __int64 v12; // rax
  HANDLE FileW; // rsi
  unsigned int PortPropertiesFromRegistry; // eax
  CWin32SerialPort *v15; // rcx
  LONG rgIndices; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int pv; // [rsp+4Ch] [rbp-B4h] BYREF
  _BYTE v20[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[8]; // [rsp+58h] [rbp-A8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-A0h] BYREF
  _COMMPROP CommProp; // [rsp+70h] [rbp-90h] BYREF
  struct _DCB pvarg; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[264]; // [rsp+D0h] [rbp-30h] BYREF

  if ( (a5[3] & 4) != 0 )
  {
    LOWORD(pv) = 2;
    CInstance::SetWBEMINT16(a2, L"Availability", (const __int16 *)&pv);
  }
  if ( (a5[3] & 8) != 0 )
    Provider::SetCreationClassName(this, a2);
  if ( (a5[3] & 0x10) != 0 )
  {
    pv = 0;
    if ( (unsigned int)CConfigMgrDevice::GetStatus(a3, (unsigned int *)&rgIndices, &pv) )
      CInstance::SetDWORD(a2, L"ConfigManagerErrorCode", pv);
  }
  if ( (a5[3] & 0x20) != 0 )
  {
    IsUsingForcedConfig = CConfigMgrDevice::IsUsingForcedConfig(a3);
    CInstance::SetDWORD(a2, L"ConfigManagerUserConfig", IsUsingForcedConfig);
  }
  CInstance::SetCHString(a2, L"DeviceID", a4);
  if ( (a5[3] & 0x80u) != 0 )
  {
    CHString::CHString((CHString *)&rgIndices);
    if ( (unsigned int)CConfigMgrDevice::GetDeviceID(a3, (struct CHString *)&rgIndices) )
      CInstance::SetCHString(a2, L"PNPDeviceID", (const struct CHString *)&rgIndices);
    CHString::~CHString((CHString *)&rgIndices);
  }
  if ( (a5[4] & 1) != 0 )
  {
    VariantInit((VARIANTARG *)&pvarg);
    rgIndices = 0;
    rgsabound = (SAFEARRAYBOUND)1LL;
    v10 = SafeArrayCreate(2u, 1u, &rgsabound);
    *((_QWORD *)&pvarg + 1) = v10;
    LOWORD(pvarg.DCBlength) = 8194;
    if ( v10 )
    {
      pv = 1;
      if ( !SafeArrayPutElement(v10, &rgIndices, &pv) )
        CInstance::SetVariant(a2, L"PowerManagementCapabilities", (const struct tagVARIANT *)&pvarg);
    }
    _variant_t::~_variant_t((VARIANTARG *)&pvarg);
  }
  if ( (a5[4] & 2) != 0 )
    CInstance::Setbool(a2, L"PowerManagementSupported", 0);
  if ( (a5[4] & 8) != 0 )
    CInstance::SetWCHARSplat(a2, L"SystemCreationClassName", L"Win32_ComputerSystem");
  if ( (a5[4] & 0x10) != 0 )
  {
    LocalComputerName = Provider::GetLocalComputerName(this);
    CInstance::SetCHString(a2, L"SystemName", LocalComputerName);
  }
  CHString::CHString((CHString *)v20);
  CHString::CHString((CHString *)v21);
  CConfigMgrDevice::GetStringProperty(a3, 0xDu, (struct CHString *)v20);
  CConfigMgrDevice::GetStringProperty(a3, 1u, (struct CHString *)v21);
  if ( CHString::IsEmpty((CHString *)v20) )
    CHString::operator=(v20, v21);
  if ( (a5[4] & 0x20) != 0 )
    CInstance::SetCHString(a2, L"Caption", (const struct CHString *)v20);
  if ( (a5[4] & 0x40) != 0 )
    CInstance::SetCHString(a2, L"Description", (const struct CHString *)v21);
  if ( (a5[5] & 1) != 0 )
    CInstance::SetCHString(a2, L"Name", (const struct CHString *)v20);
  if ( (a5[5] & 2) != 0 )
  {
    CHString::CHString((CHString *)&rgIndices);
    if ( (unsigned int)CConfigMgrDevice::GetStatus(a3, (struct CHString *)&rgIndices) )
      CInstance::SetCHString(a2, L"Status", (const struct CHString *)&rgIndices);
    CHString::~CHString((CHString *)&rgIndices);
  }
  v18[0] = 2;
  rgsabound = (SAFEARRAYBOUND)-1LL;
  memset_0(&CommProp, 0, sizeof(CommProp));
  if ( (a5[2] & 0x20) != 0 )
    CInstance::Setbool(a2, L"OSAutoDiscovered", 1);
  if ( !CInstance::IsNull(a2, L"DeviceID") )
  {
    CHString::CHString((CHString *)&rgIndices);
    CInstance::GetCHString(a2, L"DeviceID", (struct CHString *)&rgIndices);
    v12 = CHString::operator unsigned short const *(&rgIndices);
    StringCchPrintfW(FileName, 0x104u, L"\\\\.\\%s", v12);
    FileW = CreateFileW(FileName, 0, 0, 0, 3u, 0x80u, 0);
    rgsabound = (SAFEARRAYBOUND)FileW;
    CHString::~CHString((CHString *)&rgIndices);
    if ( FileW != (HANDLE)-1LL )
    {
      CommProp.wPacketLength = 64;
      if ( !GetCommProperties(FileW, &CommProp) )
      {
LABEL_179:
        if ( (a5[4] & 4) != 0 )
          CInstance::SetWBEMINT16(a2, L"StatusInfo", v18);
        CloseHandle(FileW);
        goto LABEL_186;
      }
      if ( (*a5 & 4) != 0 )
        CInstance::SetDWORD(a2, L"MaximumOutputBufferSize", CommProp.dwMaxTxQueue);
      if ( (*a5 & 2) != 0 )
        CInstance::SetDWORD(a2, L"MaximumInputBufferSize", CommProp.dwMaxTxQueue);
      if ( (a5[2] & 0x40) == 0 )
        goto LABEL_97;
      if ( CommProp.dwMaxBaud <= 0x400 )
      {
        if ( CommProp.dwMaxBaud == 1024 )
        {
          PortPropertiesFromRegistry = 7200;
          goto LABEL_96;
        }
        if ( CommProp.dwMaxBaud <= 0x20 )
        {
          if ( CommProp.dwMaxBaud != 32 )
          {
            if ( CommProp.dwMaxBaud != 1 )
            {
              if ( CommProp.dwMaxBaud != 2 )
              {
                if ( CommProp.dwMaxBaud != 4 )
                {
                  if ( CommProp.dwMaxBaud != 8 )
                  {
                    if ( CommProp.dwMaxBaud == 16 )
                    {
LABEL_56:
                      PortPropertiesFromRegistry = 300;
LABEL_96:
                      CInstance::SetDWORD(a2, L"MaxBaudRate", PortPropertiesFromRegistry);
                      goto LABEL_97;
                    }
                    goto LABEL_120;
                  }
LABEL_57:
                  PortPropertiesFromRegistry = 150;
                  goto LABEL_96;
                }
LABEL_58:
                PortPropertiesFromRegistry = 1345;
                goto LABEL_96;
              }
LABEL_59:
              PortPropertiesFromRegistry = 110;
              goto LABEL_96;
            }
            goto LABEL_60;
          }
LABEL_61:
          PortPropertiesFromRegistry = 600;
          goto LABEL_96;
        }
        if ( CommProp.dwMaxBaud != 64 )
        {
          switch ( CommProp.dwMaxBaud )
          {
            case 0x80u:
              PortPropertiesFromRegistry = 1800;
              goto LABEL_96;
            case 0x100u:
              PortPropertiesFromRegistry = 2400;
              goto LABEL_96;
            case 0x200u:
              PortPropertiesFromRegistry = 4800;
              goto LABEL_96;
          }
          goto LABEL_120;
        }
LABEL_69:
        PortPropertiesFromRegistry = 1200;
        goto LABEL_96;
      }
      switch ( CommProp.dwMaxBaud )
      {
        case 0x800u:
          goto LABEL_95;
        case 0x1000u:
          PortPropertiesFromRegistry = 14400;
          goto LABEL_96;
        case 0x2000u:
          goto LABEL_91;
        case 0x4000u:
          goto LABEL_89;
        case 0x8000u:
          goto LABEL_87;
        case 0x10000u:
LABEL_81:
          PortPropertiesFromRegistry = 128000;
          goto LABEL_96;
        case 0x20000u:
LABEL_83:
          PortPropertiesFromRegistry = 115200;
          goto LABEL_96;
        case 0x40000u:
LABEL_85:
          PortPropertiesFromRegistry = 57600;
          goto LABEL_96;
        case 0x10000000u:
          if ( (CommProp.dwSettableBaud & 0x10000) != 0 )
            goto LABEL_81;
          if ( (CommProp.dwSettableBaud & 0x20000) != 0 )
            goto LABEL_83;
          if ( (CommProp.dwSettableBaud & 0x40000) != 0 )
            goto LABEL_85;
          if ( (CommProp.dwSettableBaud & 0x8000) != 0 )
          {
LABEL_87:
            PortPropertiesFromRegistry = 56000;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 0x4000) != 0 )
          {
LABEL_89:
            PortPropertiesFromRegistry = 38400;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 0x2000) != 0 )
          {
LABEL_91:
            PortPropertiesFromRegistry = 19200;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 0x1000) != 0 )
          {
            PortPropertiesFromRegistry = 14400;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 0x800) != 0 )
          {
LABEL_95:
            PortPropertiesFromRegistry = 9600;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 0x400) != 0 )
          {
            PortPropertiesFromRegistry = 7200;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 0x200) != 0 )
          {
            PortPropertiesFromRegistry = 4800;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 0x100) != 0 )
          {
            PortPropertiesFromRegistry = 2400;
            goto LABEL_96;
          }
          if ( (CommProp.dwSettableBaud & 4) != 0 )
            goto LABEL_58;
          if ( (CommProp.dwSettableBaud & 0x40) != 0 )
            goto LABEL_69;
          if ( (CommProp.dwSettableBaud & 0x20) != 0 )
            goto LABEL_61;
          if ( (CommProp.dwSettableBaud & 0x10) != 0 )
            goto LABEL_56;
          if ( (CommProp.dwSettableBaud & 8) != 0 )
            goto LABEL_57;
          if ( (CommProp.dwSettableBaud & 2) != 0 )
            goto LABEL_59;
          if ( (CommProp.dwSettableBaud & 1) != 0 )
          {
LABEL_60:
            PortPropertiesFromRegistry = 75;
            goto LABEL_96;
          }
          break;
      }
LABEL_120:
      PortPropertiesFromRegistry = CWin32SerialPort::GetPortPropertiesFromRegistry((CWin32SerialPort *)0x400, a4);
      if ( PortPropertiesFromRegistry )
        goto LABEL_96;
LABEL_97:
      if ( (*a5 & 8) == 0 )
      {
LABEL_141:
        if ( (a5[1] & 8) != 0 )
          CInstance::Setbool(a2, L"Supports16BitMode", (CommProp.dwProvCapabilities & 0x200) != 0);
        if ( (a5[1] & 0x10) != 0 )
          CInstance::Setbool(a2, L"SupportsDTRDSR", CommProp.dwProvCapabilities & 1);
        if ( (a5[1] & 0x40) != 0 )
          CInstance::Setbool(a2, L"SupportsIntTimeouts", (CommProp.dwProvCapabilities & 0x80) != 0);
        if ( (a5[1] & 0x80u) != 0 )
          CInstance::Setbool(a2, L"SupportsParityCheck", (CommProp.dwProvCapabilities & 8) != 0);
        if ( (a5[2] & 1) != 0 )
          CInstance::Setbool(a2, L"SupportsRLSD", (CommProp.dwProvCapabilities & 4) != 0);
        if ( (a5[2] & 2) != 0 )
          CInstance::Setbool(a2, L"SupportsRTSCTS", (CommProp.dwProvCapabilities & 2) != 0);
        if ( (a5[2] & 0x10) != 0 )
          CInstance::Setbool(a2, L"SupportsXOnXOffSet", (CommProp.dwProvCapabilities & 0x20) != 0);
        if ( (a5[2] & 4) != 0 )
          CInstance::Setbool(a2, L"SupportsSpecialCharacters", CommProp.dwProvCapabilities & 0x100);
        if ( (a5[1] & 0x20) != 0 )
          CInstance::Setbool(a2, L"SupportsElapsedTimeouts", (CommProp.dwProvCapabilities & 0x40) != 0);
        if ( (a5[2] & 8) != 0 )
          CInstance::Setbool(a2, L"SupportsXOnXOff", (CommProp.dwProvCapabilities & 0x10) != 0);
        if ( (*a5 & 0x10) != 0 )
          CInstance::Setbool(a2, L"SettableBaudRate", (CommProp.dwSettableParams & 2) != 0);
        if ( (*a5 & 0x20) != 0 )
          CInstance::Setbool(a2, L"SettableDataBits", (CommProp.dwSettableParams & 4) != 0);
        if ( (*a5 & 0x40) != 0 )
          CInstance::Setbool(a2, L"SettableFlowControl", (CommProp.dwSettableParams & 0x10) != 0);
        if ( (*a5 & 0x80u) != 0 )
          CInstance::Setbool(a2, L"SettableParity", CommProp.dwSettableParams & 1);
        if ( (a5[1] & 1) != 0 )
          CInstance::Setbool(a2, L"SettableParityCheck", (CommProp.dwSettableParams & 0x20) != 0);
        if ( (a5[1] & 2) != 0 )
          CInstance::Setbool(a2, L"SettableRLSD", (CommProp.dwSettableParams & 0x40) != 0);
        if ( (a5[1] & 4) != 0 )
          CInstance::Setbool(a2, L"SettableStopBits", (CommProp.dwSettableParams & 8) != 0);
        if ( (*a5 & 1) != 0 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          if ( GetCommState(FileW, &pvarg) )
            CInstance::Setbool(a2, L"Binary", *((_BYTE *)&pvarg + 8) & 1);
        }
        v18[0] = 3;
        goto LABEL_179;
      }
      CHString::CHString((CHString *)&rgIndices);
      if ( CommProp.dwProvSubType > 0x21 )
      {
        switch ( CommProp.dwProvSubType )
        {
          case 0x22u:
            CHString::operator=(&rgIndices, L"Scanner Device");
            goto LABEL_140;
          case 0x100u:
            CHString::operator=(&rgIndices, L"Network Bridge");
            goto LABEL_140;
          case 0x101u:
            CHString::operator=(&rgIndices, L"LAT Protocol");
            goto LABEL_140;
          case 0x102u:
            CHString::operator=(&rgIndices, L"TCP/IP TelNet");
            goto LABEL_140;
          case 0x103u:
            CHString::operator=(&rgIndices, L"X.25");
            goto LABEL_140;
        }
      }
      else
      {
        switch ( CommProp.dwProvSubType )
        {
          case 0x21u:
            CHString::operator=(&rgIndices, L"FAX Device");
            goto LABEL_140;
          case 1u:
            CHString::operator=(&rgIndices, L"RS232 Serial Port");
            goto LABEL_140;
          case 2u:
            CHString::operator=(&rgIndices, L"Parallel Port");
            goto LABEL_140;
          case 3u:
            CHString::operator=(&rgIndices, L"RS422 Port");
            goto LABEL_140;
          case 4u:
            CHString::operator=(&rgIndices, L"RS423 Port");
            goto LABEL_140;
          case 5u:
            CHString::operator=(&rgIndices, L"RS449 Port");
            goto LABEL_140;
          case 6u:
            CHString::operator=(&rgIndices, L"Modem Device");
LABEL_140:
            CInstance::SetCHString(a2, L"ProviderType", (const struct CHString *)&rgIndices);
            CHString::~CHString((CHString *)&rgIndices);
            goto LABEL_141;
        }
      }
      CHString::operator=(&rgIndices, L"Unspecified");
      goto LABEL_140;
    }
  }
  if ( GetLastError() == 2 && !CWin32SerialPort::hLoadWmiSerialData(v15, a2, a5) && (a5[4] & 4) != 0 )
  {
    v18[0] = 3;
    CInstance::SetWBEMINT16(a2, L"StatusInfo", v18);
  }
LABEL_186:
  CHString::~CHString((CHString *)v21);
  CHString::~CHString((CHString *)v20);
  return 0;
}

```

## disassembly

```asm
0x180055de0  push    rbp
0x180055de2  push    rbx
0x180055de3  push    rsi
0x180055de4  push    rdi
0x180055de5  push    r12
0x180055de7  push    r13
0x180055de9  push    r14
0x180055deb  push    r15
0x180055ded  lea     rbp, [rsp-1F8h]
0x180055df5  sub     rsp, 2F8h
0x180055dfc  mov     rax, cs:__security_cookie
0x180055e03  xor     rax, rsp
0x180055e06  mov     [rbp+230h+var_50], rax
0x180055e0d  mov     r15, r9
0x180055e10  mov     rsi, r8
0x180055e13  mov     rdi, rdx
0x180055e16  mov     r14, rcx
0x180055e19  mov     rbx, [rbp+230h+arg_20]
0x180055e20  mov     eax, 2
0x180055e25  test    byte ptr [rbx+3], 4
0x180055e29  jz      short loc_180055E45
0x180055e2b  mov     word ptr [rsp+330h+pv], ax
0x180055e30  lea     r8, [rsp+330h+pv]
0x180055e35  lea     rdx, aAvailability; "Availability"
0x180055e3c  mov     rcx, rdi
0x180055e3f  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x180055e45  test    byte ptr [rbx+3], 8
0x180055e49  jz      short loc_180055E57
0x180055e4b  mov     rdx, rdi
0x180055e4e  mov     rcx, r14
0x180055e51  call    cs:__imp_?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z; Provider::SetCreationClassName(CInstance *)
0x180055e57  test    byte ptr [rbx+3], 10h
0x180055e5b  jz      short loc_180055E90
0x180055e5d  mov     [rsp+330h+pv], 0
0x180055e65  lea     r8, [rsp+330h+pv]; unsigned int *
0x180055e6a  lea     rdx, [rsp+330h+rgIndices]; unsigned int *
0x180055e6f  mov     rcx, rsi; this
0x180055e72  call    ?GetStatus@CConfigMgrDevice@@QEAAHPEAK0@Z; CConfigMgrDevice::GetStatus(ulong *,ulong *)
0x180055e77  test    eax, eax
0x180055e79  jz      short loc_180055E90
0x180055e7b  mov     r8d, [rsp+330h+pv]
0x180055e80  lea     rdx, aConfigmanagere; "ConfigManagerErrorCode"
0x180055e87  mov     rcx, rdi
0x180055e8a  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180055e90  test    byte ptr [rbx+3], 20h
0x180055e94  jz      short loc_180055EB1
0x180055e96  mov     rcx, rsi; this
0x180055e99  call    ?IsUsingForcedConfig@CConfigMgrDevice@@QEAAHXZ; CConfigMgrDevice::IsUsingForcedConfig(void)
0x180055e9e  mov     r8d, eax
0x180055ea1  lea     rdx, aConfigmanageru; "ConfigManagerUserConfig"
0x180055ea8  mov     rcx, rdi
0x180055eab  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180055eb1  mov     r8, r15
0x180055eb4  lea     r13, aDeviceid; "DeviceID"
0x180055ebb  mov     rdx, r13
0x180055ebe  mov     rcx, rdi
0x180055ec1  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180055ec7  cmp     byte ptr [rbx+3], 0
0x180055ecb  jge     short loc_180055F0B
0x180055ecd  lea     rcx, [rsp+330h+rgIndices]
0x180055ed2  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180055ed8  nop
0x180055ed9  lea     rdx, [rsp+330h+rgIndices]; struct CHString *
0x180055ede  mov     rcx, rsi; this
0x180055ee1  call    ?GetDeviceID@CConfigMgrDevice@@QEAAHAEAVCHString@@@Z; CConfigMgrDevice::GetDeviceID(CHString &)
0x180055ee6  test    eax, eax
0x180055ee8  jz      short loc_180055F00
0x180055eea  lea     r8, [rsp+330h+rgIndices]
0x180055eef  lea     rdx, aPnpdeviceid_0; "PNPDeviceID"
0x180055ef6  mov     rcx, rdi
0x180055ef9  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180055eff  nop
0x180055f00  lea     rcx, [rsp+330h+rgIndices]
0x180055f05  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180055f0b  mov     r12d, 1
0x180055f11  test    [rbx+4], r12b
0x180055f15  jz      short loc_180055F92
0x180055f17  lea     rcx, [rbp+230h+pvarg]; pvarg
0x180055f1b  call    cs:__imp_VariantInit
0x180055f21  nop
0x180055f22  mov     [rsp+330h+rgIndices], 0
0x180055f2a  mov     qword ptr [rsp+330h+rgsabound.cElements], 1
0x180055f33  lea     ecx, [r12+1]; vt
0x180055f38  lea     r8, [rsp+330h+rgsabound]; rgsabound
0x180055f3d  mov     edx, r12d; cDims
0x180055f40  call    cs:__imp_SafeArrayCreate
0x180055f46  mov     qword ptr [rbp+230h+pvarg+8], rax
0x180055f4a  mov     ecx, 2002h
0x180055f4f  mov     word ptr [rbp+230h+pvarg], cx
0x180055f53  test    rax, rax
0x180055f56  jz      short loc_180055F89
0x180055f58  mov     [rsp+330h+pv], r12d
0x180055f5d  lea     r8, [rsp+330h+pv]; pv
0x180055f62  lea     rdx, [rsp+330h+rgIndices]; rgIndices
0x180055f67  mov     rcx, rax; psa
0x180055f6a  call    cs:__imp_SafeArrayPutElement
0x180055f70  test    eax, eax
0x180055f72  jnz     short loc_180055F89
0x180055f74  lea     r8, [rbp+230h+pvarg]
0x180055f78  lea     rdx, aPowermanagemen; "PowerManagementCapabilities"
0x180055f7f  mov     rcx, rdi
0x180055f82  call    cs:__imp_?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z; CInstance::SetVariant(ushort const *,tagVARIANT const &)
0x180055f88  nop
0x180055f89  lea     rcx, [rbp+230h+pvarg]; this
0x180055f8d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180055f92  test    byte ptr [rbx+4], 2
0x180055f96  jz      short loc_180055FAB
0x180055f98  xor     r8d, r8d
0x180055f9b  lea     rdx, aPowermanagemen_0; "PowerManagementSupported"
0x180055fa2  mov     rcx, rdi
0x180055fa5  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180055fab  test    byte ptr [rbx+4], 8
0x180055faf  jz      short loc_180055FC8
0x180055fb1  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x180055fb8  lea     rdx, aSystemcreation; "SystemCreationClassName"
0x180055fbf  mov     rcx, rdi
0x180055fc2  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180055fc8  test    byte ptr [rbx+4], 10h
0x180055fcc  jz      short loc_180055FEA
0x180055fce  mov     rcx, r14
0x180055fd1  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x180055fd7  mov     r8, rax
0x180055fda  lea     rdx, aSystemname; "SystemName"
0x180055fe1  mov     rcx, rdi
0x180055fe4  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180055fea  lea     rcx, [rsp+330h+var_2E0]
0x180055fef  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180055ff5  nop
0x180055ff6  lea     rcx, [rsp+330h+var_2D8]
0x180055ffb  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180056001  nop
0x180056002  lea     r8, [rsp+330h+var_2E0]; struct CHString *
0x180056007  mov     edx, 0Dh; unsigned int
0x18005600c  mov     rcx, rsi; this
0x18005600f  call    ?GetStringProperty@CConfigMgrDevice@@QEAAHKAEAVCHString@@@Z; CConfigMgrDevice::GetStringProperty(ulong,CHString &)
0x180056014  lea     r8, [rsp+330h+var_2D8]; struct CHString *
0x180056019  mov     edx, r12d; unsigned int
0x18005601c  mov     rcx, rsi; this
0x18005601f  call    ?GetStringProperty@CConfigMgrDevice@@QEAAHKAEAVCHString@@@Z; CConfigMgrDevice::GetStringProperty(ulong,CHString &)
0x180056024  lea     rcx, [rsp+330h+var_2E0]
0x180056029  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x18005602f  test    eax, eax
0x180056031  jz      short loc_180056043
0x180056033  lea     rdx, [rsp+330h+var_2D8]
0x180056038  lea     rcx, [rsp+330h+var_2E0]
0x18005603d  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x180056043  test    byte ptr [rbx+4], 20h
0x180056047  jz      short loc_18005605E
0x180056049  lea     r8, [rsp+330h+var_2E0]
0x18005604e  lea     rdx, aCaption; "Caption"
0x180056055  mov     rcx, rdi
0x180056058  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18005605e  test    byte ptr [rbx+4], 40h
0x180056062  jz      short loc_180056079
0x180056064  lea     r8, [rsp+330h+var_2D8]
0x180056069  lea     rdx, aDescription; "Description"
0x180056070  mov     rcx, rdi
0x180056073  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180056079  test    [rbx+5], r12b
0x18005607d  jz      short loc_180056094
0x18005607f  lea     r8, [rsp+330h+var_2E0]
0x180056084  lea     rdx, aName; "Name"
0x18005608b  mov     rcx, rdi
0x18005608e  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180056094  mov     r14d, 2
0x18005609a  test    [rbx+5], r14b
0x18005609e  jz      short loc_1800560DE
0x1800560a0  lea     rcx, [rsp+330h+rgIndices]
0x1800560a5  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800560ab  nop
0x1800560ac  lea     rdx, [rsp+330h+rgIndices]; struct CHString *
0x1800560b1  mov     rcx, rsi; this
0x1800560b4  call    ?GetStatus@CConfigMgrDevice@@QEAAHAEAVCHString@@@Z; CConfigMgrDevice::GetStatus(CHString &)
0x1800560b9  test    eax, eax
0x1800560bb  jz      short loc_1800560D3
0x1800560bd  lea     r8, [rsp+330h+rgIndices]
0x1800560c2  lea     rdx, aStatus; "Status"
0x1800560c9  mov     rcx, rdi
0x1800560cc  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800560d2  nop
0x1800560d3  lea     rcx, [rsp+330h+rgIndices]
0x1800560d8  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800560de  mov     [rsp+330h+var_2E8], r14w
0x1800560e4  mov     qword ptr [rsp+330h+rgsabound.cElements], 0FFFFFFFFFFFFFFFFh
0x1800560ed  xor     edx, edx; Val
0x1800560ef  lea     r8d, [rdx+40h]; Size
0x1800560f3  lea     rcx, [rsp+330h+CommProp]; void *
0x1800560f8  call    memset_0
0x1800560fd  test    byte ptr [rbx+2], 20h
0x180056101  jz      short loc_180056116
0x180056103  mov     r8b, r12b
0x180056106  lea     rdx, aOsautodiscover; "OSAutoDiscovered"
0x18005610d  mov     rcx, rdi
0x180056110  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180056116  mov     rdx, r13
0x180056119  mov     rcx, rdi
0x18005611c  call    cs:__imp_?IsNull@CInstance@@QEBA_NPEBG@Z; CInstance::IsNull(ushort const *)
0x180056122  mov     esi, 3
0x180056127  test    al, al
0x180056129  jnz     loc_18005680D
0x18005612f  lea     rcx, [rsp+330h+rgIndices]
0x180056134  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18005613a  nop
0x18005613b  lea     r8, [rsp+330h+rgIndices]
0x180056140  mov     rdx, r13
0x180056143  mov     rcx, rdi
0x180056146  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x18005614c  lea     rcx, [rsp+330h+rgIndices]
0x180056151  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180056157  mov     r9, rax
0x18005615a  lea     r8, aS_3; "\\\\.\\%s"
0x180056161  mov     edx, 104h; unsigned __int64
0x180056166  lea     rcx, [rbp+230h+FileName]; unsigned __int16 *
0x18005616a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005616f  mov     [rsp+330h+hTemplateFile], 0; hTemplateFile
0x180056178  lea     r14d, [rsi+7Dh]
0x18005617c  mov     [rsp+330h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180056181  mov     [rsp+330h+dwCreationDisposition], esi; dwCreationDisposition
0x180056185  xor     r9d, r9d; lpSecurityAttributes
0x180056188  xor     r8d, r8d; dwShareMode
0x18005618b  xor     edx, edx; dwDesiredAccess
0x18005618d  lea     rcx, [rbp+230h+FileName]; lpFileName
0x180056191  call    cs:__imp_CreateFileW
0x180056197  mov     rsi, rax
0x18005619a  mov     qword ptr [rsp+330h+rgsabound.cElements], rax
0x18005619f  lea     rcx, [rsp+330h+rgIndices]
0x1800561a4  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800561aa  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800561ae  jz      loc_180056804
0x1800561b4  lea     r13d, [r14-40h]
0x1800561b8  mov     [rsp+330h+CommProp.wPacketLength], r13w
0x1800561be  lea     rdx, [rsp+330h+CommProp]; lpCommProp
0x1800561c3  mov     rcx, rsi; hFile
0x1800561c6  call    cs:__imp_GetCommProperties
0x1800561cc  test    eax, eax
0x1800561ce  jz      loc_1800567DD
0x1800561d4  test    byte ptr [rbx], 4
0x1800561d7  jz      short loc_1800561EE
0x1800561d9  mov     r8d, [rsp+330h+CommProp.dwMaxTxQueue]
0x1800561de  lea     rdx, aMaximumoutputb; "MaximumOutputBufferSize"
0x1800561e5  mov     rcx, rdi
0x1800561e8  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800561ee  test    byte ptr [rbx], 2
0x1800561f1  jz      short loc_180056208
0x1800561f3  mov     r8d, [rsp+330h+CommProp.dwMaxTxQueue]
0x1800561f8  lea     rdx, aMaximuminputbu; "MaximumInputBufferSize"
0x1800561ff  mov     rcx, rdi
0x180056202  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180056208  test    [rbx+2], r13b
0x18005620c  jz      loc_1800563C8
0x180056212  mov     eax, [rbp+230h+CommProp.dwMaxBaud]
0x180056215  mov     ecx, 400h; this
0x18005621a  cmp     eax, ecx
0x18005621c  ja      loc_1800562D4
0x180056222  jz      loc_1800562CA
0x180056228  cmp     eax, 20h ; ' '
0x18005622b  ja      short loc_180056288
0x18005622d  jz      short loc_18005627E
0x18005622f  sub     eax, 1
0x180056232  jz      short loc_180056274
0x180056234  sub     eax, 1
0x180056237  jz      short loc_18005626A
0x180056239  sub     eax, 2
0x18005623c  jz      short loc_180056260
0x18005623e  sub     eax, 4
0x180056241  jz      short loc_180056256
0x180056243  cmp     eax, 8
0x180056246  jnz     loc_18005649F
0x18005624c  mov     eax, 12Ch
0x180056251  jmp     loc_1800563B5
0x180056256  mov     eax, 96h
0x18005625b  jmp     loc_1800563B5
0x180056260  mov     eax, 541h
0x180056265  jmp     loc_1800563B5
0x18005626a  mov     eax, 6Eh ; 'n'
0x18005626f  jmp     loc_1800563B5
0x180056274  mov     eax, 4Bh ; 'K'
0x180056279  jmp     loc_1800563B5
0x18005627e  mov     eax, 258h
0x180056283  jmp     loc_1800563B5
0x180056288  sub     eax, r13d
0x18005628b  jz      short loc_1800562C0
0x18005628d  sub     eax, r13d
0x180056290  jz      short loc_1800562B6
0x180056292  sub     eax, r14d
0x180056295  jz      short loc_1800562AC
0x180056297  cmp     eax, 100h
0x18005629c  jnz     loc_18005649F
0x1800562a2  mov     eax, 12C0h
0x1800562a7  jmp     loc_1800563B5
0x1800562ac  mov     eax, 960h
0x1800562b1  jmp     loc_1800563B5
0x1800562b6  mov     eax, 708h
0x1800562bb  jmp     loc_1800563B5
0x1800562c0  mov     eax, 4B0h
0x1800562c5  jmp     loc_1800563B5
0x1800562ca  mov     eax, 1C20h
0x1800562cf  jmp     loc_1800563B5
0x1800562d4  cmp     eax, 800h
0x1800562d9  jz      loc_1800563B0
  ... truncated ...
```
