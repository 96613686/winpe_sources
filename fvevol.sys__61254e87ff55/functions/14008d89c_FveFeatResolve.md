# FveFeatResolve

- ea: `0x14008d89c`
- end: `0x14008ea01`
- name: `FveFeatResolve`
- size: `4453`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14008d6d0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140008e80`
- `0x140008f04`
- `0x14000f45c`
- `0x140022bf0`
- `0x140023040`
- `0x14007b668`
- `0x14008d89c`
- `0x140099114`
- `0x1400dd18c`
- `0x1400dd79c`

## import_xrefs

- `ntoskrnl!ZwQuerySystemInformation` at `0x14008e6ab`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14008e6ab`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008dc18`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008dd15`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008de12`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008df0f`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e00c`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e111`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e225`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e327`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e427`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e532`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008dc18`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008dd15`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008de12`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008df0f`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e00c`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e111`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e225`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e327`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e427`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008e532`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008e6fb`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008e6fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008da66`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008da80`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008db1b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008e720`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008e73a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008da66`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008da80`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008db1b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008e720`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008e73a`

## string_xrefs

- `0x14008d922`: `DeviceEncryption-WindowsCore-PreInstalled`
- `0x14008da57`: `\Registry\Machine\SYSTEM\CurrentControlSet\Policies\Microsoft\FVE`
- `0x14008e719`: `\Registry\Machine\SYSTEM\CurrentControlSet\Policies\Microsoft\FVE`
- `0x14008da72`: `OsvAllowWriteAccess`
- `0x14008e098`: `WcosPreInstalledLevel`
- `0x14008e70e`: `\Registry\Machine\OSBOOT\CurrentControlSet\Policies\Microsoft\FVE`

## pseudocode

```c
__int64 __fastcall FveFeatResolve(__int64 a1)
{
  unsigned int v2; // ebx
  int RegistryValue; // eax
  int v4; // eax
  int v5; // eax
  PDEVICE_OBJECT v6; // rcx
  int v7; // eax
  _DWORD *v8; // rsi
  PDEVICE_OBJECT v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  _DWORD *v12; // rsi
  PDEVICE_OBJECT v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  _DWORD *v16; // rsi
  PDEVICE_OBJECT v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  _DWORD *v20; // rsi
  PDEVICE_OBJECT v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  _DWORD *v24; // rsi
  PDEVICE_OBJECT v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  int *v28; // r13
  PDEVICE_OBJECT v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  _DWORD *v32; // r12
  PDEVICE_OBJECT v33; // rcx
  int v34; // eax
  __int64 v35; // rdx
  _DWORD *v36; // r15
  PDEVICE_OBJECT v37; // rcx
  int v38; // eax
  __int64 v39; // rdx
  _DWORD *v40; // r14
  PDEVICE_OBJECT v41; // rcx
  int v42; // eax
  __int64 v43; // rdx
  _DWORD *v44; // rsi
  int v45; // eax
  PDEVICE_OBJECT v46; // rcx
  __int64 v47; // rdx
  NTSTATUS v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rcx
  char IsStateSeparationEnabled; // al
  const WCHAR *v52; // rdx
  int v53; // eax
  int v54; // eax
  int v56; // [rsp+30h] [rbp-D0h]
  int v57; // [rsp+38h] [rbp-C8h]
  int v58; // [rsp+40h] [rbp-C0h]
  int v59; // [rsp+70h] [rbp-90h] BYREF
  int v60; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v61; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v63[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v64[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v65[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v66[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v67[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v68[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v69[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v70[2]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v71[2]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v72[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v73; // [rsp+128h] [rbp+28h] BYREF
  __int64 v74; // [rsp+130h] [rbp+30h] BYREF
  __int64 v75; // [rsp+138h] [rbp+38h] BYREF
  __int64 v76; // [rsp+140h] [rbp+40h] BYREF
  __int64 v77; // [rsp+148h] [rbp+48h] BYREF
  __int64 v78; // [rsp+150h] [rbp+50h] BYREF
  __int64 v79; // [rsp+158h] [rbp+58h] BYREF
  __int64 v80; // [rsp+160h] [rbp+60h] BYREF
  __int64 v81; // [rsp+168h] [rbp+68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+170h] [rbp+70h] BYREF
  struct _UNICODE_STRING v83; // [rsp+180h] [rbp+80h] BYREF
  struct _UNICODE_STRING v84; // [rsp+190h] [rbp+90h] BYREF
  struct _UNICODE_STRING v85; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _UNICODE_STRING v86; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v87[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 SystemInformation; // [rsp+200h] [rbp+100h] BYREF
  __int64 v89; // [rsp+210h] [rbp+110h]
  _BYTE v90[32]; // [rsp+220h] [rbp+120h] BYREF
  __int64 *v91; // [rsp+240h] [rbp+140h]
  __int64 v92; // [rsp+248h] [rbp+148h]
  __int64 *v93; // [rsp+250h] [rbp+150h]
  __int64 v94; // [rsp+258h] [rbp+158h]
  __int64 *v95; // [rsp+260h] [rbp+160h]
  __int64 v96; // [rsp+268h] [rbp+168h]
  __int64 *v97; // [rsp+270h] [rbp+170h]
  __int64 v98; // [rsp+278h] [rbp+178h]
  __int64 *v99; // [rsp+280h] [rbp+180h]
  __int64 v100; // [rsp+288h] [rbp+188h]
  __int64 *v101; // [rsp+290h] [rbp+190h]
  __int64 v102; // [rsp+298h] [rbp+198h]
  __int64 *v103; // [rsp+2A0h] [rbp+1A0h]
  __int64 v104; // [rsp+2A8h] [rbp+1A8h]
  __int64 *v105; // [rsp+2B0h] [rbp+1B0h]
  __int64 v106; // [rsp+2B8h] [rbp+1B8h]
  __int64 *v107; // [rsp+2C0h] [rbp+1C0h]
  __int64 v108; // [rsp+2C8h] [rbp+1C8h]
  __int64 *v109; // [rsp+2D0h] [rbp+1D0h]
  __int64 v110; // [rsp+2D8h] [rbp+1D8h]
  __int64 *v111; // [rsp+2E0h] [rbp+1E0h]
  __int64 v112; // [rsp+2E8h] [rbp+1E8h]

  memset(v87, 0, sizeof(v87));
  v63[0] = 4718662;
  v67[0] = 4718662;
  v68[0] = 5505106;
  v69[0] = 4980810;
  v63[1] = L"DeviceEncryption-WindowsCore-OSMain";
  v67[1] = L"DeviceEncryption-WindowsCore-OSData";
  v68[1] = L"DeviceEncryption-WindowsCore-PreInstalled";
  v69[1] = L"DeviceEncryption-WindowsCore-UserData";
  v64[1] = L"DeviceEncryption-WindowsCore-BSP";
  v65[1] = L"DeviceEncryption-WindowsCore-DPP";
  v66[1] = L"DeviceEncryption-WindowsCore-WSP";
  v70[1] = L"DeviceEncryption-WindowsCore-ServicingMetadata";
  v71[1] = L"DeviceEncryption-WindowsCore-ServicingFiles";
  v72[1] = L"DeviceEncryption-WindowsCore-ServicingReserve";
  v89 = 0;
  v64[0] = 4325440;
  v65[0] = 4325440;
  v66[0] = 4325440;
  v70[0] = 6160476;
  v71[0] = 5767254;
  v72[0] = 6029402;
  v60 = 0;
  v59 = 0;
  DestinationString = 0;
  v84 = 0;
  v85 = 0;
  SystemInformation = 0;
  v83 = 0;
  v86 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 198, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
  }
  if ( a1 )
  {
    FvepLockAcquireLock((PFAST_MUTEX)(a1 + 10432));
    if ( (*(_BYTE *)(a1 + 10520) & 1) != 0 )
    {
      v2 = 0;
      goto LABEL_234;
    }
    LODWORD(v61) = 0;
    LODWORD(v62) = 4;
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Policies\\Microsoft\\FVE");
    RtlInitUnicodeString(&v84, L"OsvAllowWriteAccess");
    RegistryValue = FveGetRegistryValue(&DestinationString, &v84, 4, &v61, &v62);
    v2 = RegistryValue;
    if ( RegistryValue == -1073741772 )
    {
      v4 = 0;
    }
    else
    {
      if ( RegistryValue < 0 )
        goto LABEL_234;
      v4 = v61;
    }
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 199, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
      }
      *(_QWORD *)(a1 + 10520) |= 0xCuLL;
    }
    LODWORD(v61) = 0;
    LODWORD(v62) = 4;
    RtlInitUnicodeString(&v85, L"WcosDisableBitLockerRO");
    v5 = FveGetRegistryValue(&DestinationString, &v85, 4, &v61, &v62);
    v2 = v5;
    if ( v5 == -1073741772 )
    {
      v7 = 0;
      v2 = 0;
    }
    else
    {
      if ( v5 < 0 )
        goto LABEL_234;
      v7 = v61;
    }
    if ( v7 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 200, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
      }
      *(_QWORD *)(a1 + 10520) |= 8uLL;
    }
    v8 = (_DWORD *)(a1 + 10528);
    if ( (unsigned __int8)FveTestGetDwordOverride(v6, L"WcosOsMainLevel", a1 + 10528) )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          201,
          WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
          (unsigned int)*v8);
      }
      goto LABEL_45;
    }
    v59 = 4;
    v10 = ZwQueryLicenseValue(v63, &v60, a1 + 10528, 4, &v59);
    v2 = v10;
    if ( v10 == -1073741762 )
    {
      *v8 = 0;
      v2 = 0;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_45;
      }
      v11 = 202;
    }
    else
    {
      if ( v10 != -1073741772 )
      {
        if ( v10 < 0 )
          goto LABEL_234;
LABEL_45:
        v12 = (_DWORD *)(a1 + 10532);
        if ( (unsigned __int8)FveTestGetDwordOverride(v9, L"WcosBspLevel", a1 + 10532) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              204,
              WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
              (unsigned int)*v12);
          }
          goto LABEL_62;
        }
        v59 = 4;
        v14 = ZwQueryLicenseValue(v64, &v60, a1 + 10532, 4, &v59);
        v2 = v14;
        if ( v14 == -1073741762 )
        {
          *v12 = 0;
          v2 = 0;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
            goto LABEL_62;
          }
          v15 = 205;
        }
        else
        {
          if ( v14 != -1073741772 )
          {
            if ( v14 < 0 )
              goto LABEL_234;
LABEL_62:
            v16 = (_DWORD *)(a1 + 10536);
            if ( (unsigned __int8)FveTestGetDwordOverride(v13, L"WcosDppLevel", a1 + 10536) )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  207,
                  WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                  (unsigned int)*v16);
              }
              goto LABEL_79;
            }
            v59 = 4;
            v18 = ZwQueryLicenseValue(v65, &v60, a1 + 10536, 4, &v59);
            v2 = v18;
            if ( v18 == -1073741762 )
            {
              *v16 = 0;
              v2 = 0;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
              {
                goto LABEL_79;
              }
              v19 = 208;
            }
            else
            {
              if ( v18 != -1073741772 )
              {
                if ( v18 < 0 )
                  goto LABEL_234;
LABEL_79:
                v20 = (_DWORD *)(a1 + 10540);
                if ( (unsigned __int8)FveTestGetDwordOverride(v17, L"WcosWspLevel", a1 + 10540) )
                {
                  v21 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      210,
                      WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                      (unsigned int)*v20);
                  }
                  goto LABEL_96;
                }
                v59 = 4;
                v22 = ZwQueryLicenseValue(v66, &v60, a1 + 10540, 4, &v59);
                v2 = v22;
                if ( v22 == -1073741762 )
                {
                  *v20 = 0;
                  v2 = 0;
                  v21 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                  {
                    goto LABEL_96;
                  }
                  v23 = 211;
                }
                else
                {
                  if ( v22 != -1073741772 )
                  {
                    if ( v22 < 0 )
                      goto LABEL_234;
LABEL_96:
                    v24 = (_DWORD *)(a1 + 10544);
                    if ( (unsigned __int8)FveTestGetDwordOverride(v21, L"WcosOsDataLevel", a1 + 10544) )
                    {
                      v25 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          213,
                          WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                          (unsigned int)*v24);
                      }
                      goto LABEL_113;
                    }
                    v59 = 4;
                    v26 = ZwQueryLicenseValue(v67, &v60, a1 + 10544, 4, &v59);
                    v2 = v26;
                    if ( v26 == -1073741762 )
                    {
                      *v24 = 0;
                      v2 = 0;
                      v25 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                      {
                        goto LABEL_113;
                      }
                      v27 = 214;
                    }
                    else
                    {
                      if ( v26 != -1073741772 )
                      {
                        if ( v26 < 0 )
                          goto LABEL_234;
LABEL_113:
                        v28 = (int *)(a1 + 10548);
                        if ( (unsigned __int8)FveTestGetDwordOverride(v25, L"WcosPreInstalledLevel", a1 + 10548) )
                        {
                          v29 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              216,
                              WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                              (unsigned int)*v28);
                          }
                          goto LABEL_130;
                        }
                        v59 = 4;
                        v30 = ZwQueryLicenseValue(v68, &v60, a1 + 10548, 4, &v59);
                        v2 = v30;
                        if ( v30 == -1073741762 )
                        {
                          *v28 = 0;
                          v2 = 0;
                          v29 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                          {
                            goto LABEL_130;
                          }
                          v31 = 217;
                        }
                        else
                        {
                          if ( v30 != -1073741772 )
                          {
                            if ( v30 < 0 )
                              goto LABEL_234;
LABEL_130:
                            v32 = (_DWORD *)(a1 + 10552);
                            if ( (unsigned __int8)FveTestGetDwordOverride(v29, L"WcosUserDataLevel", a1 + 10552) )
                            {
                              v33 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                              {
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  219,
                                  WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                                  (unsigned int)*v32);
                              }
                              goto LABEL_147;
                            }
                            v59 = 4;
                            v34 = ZwQueryLicenseValue(v69, &v60, a1 + 10552, 4, &v59);
                            v2 = v34;
                            if ( v34 == -1073741762 )
                            {
                              *v32 = 0;
                              v2 = 0;
                              v33 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                              {
                                goto LABEL_147;
                              }
                              v35 = 220;
                            }
                            else
                            {
                              if ( v34 != -1073741772 )
                              {
                                if ( v34 < 0 )
                                  goto LABEL_234;
LABEL_147:
                                v36 = (_DWORD *)(a1 + 10556);
                                if ( (unsigned __int8)FveTestGetDwordOverride(
                                                        v33,
                                                        L"WcosServicingMetadataLevel",
                                                        a1 + 10556) )
                                {
                                  v37 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                  {
                                    WPP_SF_d(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      222,
                                      WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                                      (unsigned int)*v36);
                                  }
                                  goto LABEL_164;
                                }
                                v59 = 4;
                                v38 = ZwQueryLicenseValue(v70, &v60, a1 + 10556, 4, &v59);
                                v2 = v38;
                                if ( v38 == -1073741762 )
                                {
                                  *v36 = 0;
                                  v2 = 0;
                                  v37 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                                  {
                                    goto LABEL_164;
                                  }
                                  v39 = 223;
                                }
                                else
                                {
                                  if ( v38 != -1073741772 )
                                  {
                                    if ( v38 < 0 )
                                      goto LABEL_234;
LABEL_164:
                                    v40 = (_DWORD *)(a1 + 10560);
                                    if ( (unsigned __int8)FveTestGetDwordOverride(
                                                            v37,
                                                            L"WcosServicingFilesLevel",
                                                            a1 + 10560) )
                                    {
                                      v41 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                      {
                                        WPP_SF_d(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          225,
                                          WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                                          (unsigned int)*v40);
                                      }
                                      goto LABEL_181;
                                    }
                                    v59 = 4;
                                    v42 = ZwQueryLicenseValue(v71, &v60, a1 + 10560, 4, &v59);
                                    v2 = v42;
                                    if ( v42 == -1073741762 )
                                    {
                                      *v40 = 0;
                                      v2 = 0;
                                      v41 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                                      {
                                        goto LABEL_181;
                                      }
                                      v43 = 226;
                                    }
                                    else
                                    {
                                      if ( v42 != -1073741772 )
                                      {
                                        if ( v42 < 0 )
                                          goto LABEL_234;
LABEL_181:
                                        v44 = (_DWORD *)(a1 + 10564);
                                        if ( (unsigned __int8)FveTestGetDwordOverride(
                                                                v41,
                                                                L"WcosServicingReserveLevel",
                                                                a1 + 10564) )
                                        {
                                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                          {
                                            WPP_SF_d(
                                              WPP_GLOBAL_Control->AttachedDevice,
                                              228,
                                              WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
                                              (unsigned int)*v44);
                                          }
                                          goto LABEL_198;
                                        }
                                        v59 = 4;
                                        v45 = ZwQueryLicenseValue(v72, &v60, a1 + 10564, 4, &v59);
                                        v2 = v45;
                                        if ( v45 == -1073741762 )
                                        {
                                          *v44 = 0;
                                          v2 = 0;
                                          v46 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                                          {
                                            goto LABEL_198;
                                          }
                                          v47 = 229;
                                        }
                                        else
                                        {
                                          if ( v45 != -1073741772 )
                                          {
                                            if ( v45 < 0 )
                                              goto LABEL_234;
LABEL_198:
                                            if ( *(_QWORD *)(a1 + 10528)
                                              || *(_DWORD *)(a1 + 10536)
                                              || *(_DWORD *)(a1 + 10540)
                                              || *(_DWORD *)(a1 + 10544)
                                              || *v28
                                              || *v32
                                              || *v36
                                              || *v40
                                              || *v44 )
                                            {
                                              *(_QWORD *)(a1 + 10520) |= 2uLL;
                                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                              {
                                                v58 = *v28;
                                                v57 = *(_DWORD *)(a1 + 10544);
                                                v56 = *(_DWORD *)(a1 + 10540);
                                                WPP_SF_LLLLLLLLLL(WPP_GLOBAL_Control->AttachedDevice);
                                              }
                                            }
                                            if ( (*(_BYTE *)(a1 + 10520) & 2) == 0 )
                                              goto LABEL_233;
                                            v48 = ZwQuerySystemInformation(
                                                    SystemNonPagedPoolInformation|0x80,
                                                    &SystemInformation,
                                                    0x18u,
                                                    0);
                                            if ( v48 >= 0 )
                                            {
                                              if ( (v89 & 0x1000000000LL) != 0 )
LABEL_216:
                                                *(_QWORD *)(a1 + 10520) |= 0x8000000000000000uLL;
                                            }
                                            else if ( v48 == -2143092730 )
                                            {
                                              goto LABEL_216;
                                            }
                                            if ( *(__int64 *)(a1 + 10520) >= 0 )
                                            {
LABEL_230:
                                              if ( (unsigned int)dword_140046040 > 4
                                                && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
                                              {
                                                v62 = *(unsigned int *)(a1 + 10528);
                                                v92 = 8;
                                                v91 = &v62;
                                                v61 = *(unsigned int *)(a1 + 10532);
                                                v93 = &v61;
                                                v73 = *(unsigned int *)(a1 + 10536);
                                                v95 = &v73;
                                                v74 = *(unsigned int *)(a1 + 10540);
                                                v97 = &v74;
                                                v75 = *(unsigned int *)(a1 + 10544);
                                                v99 = &v75;
                                                v76 = (unsigned int)*v28;
                                                v101 = &v76;
                                                v77 = (unsigned int)*v32;
                                                v103 = &v77;
                                                v78 = (unsigned int)*v36;
                                                v105 = &v78;
                                                v79 = (unsigned int)*v40;
                                                v107 = &v79;
                                                v80 = (unsigned int)*v44;
                                                v109 = &v80;
                                                v81 = *(_QWORD *)(a1 + 10520);
                                                v111 = &v81;
                                                v94 = 8;
                                                v96 = 8;
                                                v98 = 8;
                                                v100 = 8;
                                                v102 = 8;
                                                v104 = 8;
                                                v106 = 8;
                                                v108 = 8;
                                                v110 = 8;
                                                v112 = 8;
                                                tlgWriteTransfer_EtwWriteTransfer(
                                                  &dword_140046040,
                                                  byte_14003D5F1,
                                                  0,
                                                  0,
                                                  13,
                                                  v90,
                                                  v56,
                                                  v57,
                                                  v58);
                                              }
LABEL_233:
                                              *(_QWORD *)(a1 + 10520) |= 1uLL;
                                              goto LABEL_234;
                                            }
                                            LODWORD(v61) = 0;
                                            LODWORD(v62) = 4;
                                            IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v50, v49, 0);
                                            v52 = L"\\Registry\\Machine\\OSBOOT\\CurrentControlSet\\Policies\\Microsoft\\FVE";
                                            if ( !IsStateSeparationEnabled )
                                              v52 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Policies\\Microsoft\\FVE";
                                            RtlInitUnicodeString(&v83, v52);
                                            RtlInitUnicodeString(&v86, L"WcosNonRetailNoForcedPoAc");
                                            v53 = FveGetRegistryValue(&v83, &v86, 4, &v61, &v62);
                                            v2 = v53;
                                            if ( v53 == -1073741772 )
                                            {
                                              v54 = 0;
                                              v2 = 0;
                                              goto LABEL_224;
                                            }
                                            if ( v53 >= 0 )
                                            {
                                              v54 = v61;
LABEL_224:
                                              if ( v54 )
                                              {
                                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                                {
                                                  WPP_SF_(
                                                    WPP_GLOBAL_Control->AttachedDevice,
                                                    232,
                                                    WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                                                }
                                                *(_QWORD *)(a1 + 10520) |= 0x4000000000000000uLL;
                                              }
                                              goto LABEL_230;
                                            }
LABEL_234:
                                            FvepLockReleaseLock(v87);
                                            goto LABEL_235;
                                          }
                                          *v44 = 0;
                                          v2 = 0;
                                          v46 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                                          {
                                            goto LABEL_198;
                                          }
                                          v47 = 230;
                                        }
                                        WPP_SF_(
                                          v46->AttachedDevice,
                                          v47,
                                          WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                                        goto LABEL_198;
                                      }
                                      *v40 = 0;
                                      v2 = 0;
                                      v41 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                                      {
                                        goto LABEL_181;
                                      }
                                      v43 = 227;
                                    }
                                    WPP_SF_(v41->AttachedDevice, v43, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                                    goto LABEL_181;
                                  }
                                  *v36 = 0;
                                  v2 = 0;
                                  v37 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                                  {
                                    goto LABEL_164;
                                  }
                                  v39 = 224;
                                }
                                WPP_SF_(v37->AttachedDevice, v39, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                                goto LABEL_164;
                              }
                              *v32 = 0;
                              v2 = 0;
                              v33 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                              {
                                goto LABEL_147;
                              }
                              v35 = 221;
                            }
                            WPP_SF_(v33->AttachedDevice, v35, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                            goto LABEL_147;
                          }
                          *v28 = 0;
                          v2 = 0;
                          v29 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                          {
                            goto LABEL_130;
                          }
                          v31 = 218;
                        }
                        WPP_SF_(v29->AttachedDevice, v31, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                        goto LABEL_130;
                      }
                      *v24 = 0;
                      v2 = 0;
                      v25 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                      {
                        goto LABEL_113;
                      }
                      v27 = 215;
                    }
                    WPP_SF_(v25->AttachedDevice, v27, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                    goto LABEL_113;
                  }
                  *v20 = 0;
                  v2 = 0;
                  v21 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
                  {
                    goto LABEL_96;
                  }
                  v23 = 212;
                }
                WPP_SF_(v21->AttachedDevice, v23, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
                goto LABEL_96;
              }
              *v16 = 0;
              v2 = 0;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
              {
                goto LABEL_79;
              }
              v19 = 209;
            }
            WPP_SF_(v17->AttachedDevice, v19, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
            goto LABEL_79;
          }
          *v12 = 0;
          v2 = 0;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
            goto LABEL_62;
          }
          v15 = 206;
        }
        WPP_SF_(v13->AttachedDevice, v15, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
        goto LABEL_62;
      }
      *v8 = 0;
      v2 = 0;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_45;
      }
      v11 = 203;
    }
    WPP_SF_(v9->AttachedDevice, v11, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
    goto LABEL_45;
  }
  v2 = -1073741811;
LABEL_235:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 233, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x14008d89c  push    rbp
0x14008d89e  push    rbx
0x14008d89f  push    rsi
0x14008d8a0  push    rdi
0x14008d8a1  push    r12
0x14008d8a3  push    r13
0x14008d8a5  push    r14
0x14008d8a7  push    r15
0x14008d8a9  lea     rbp, [rsp-208h]
0x14008d8b1  sub     rsp, 308h
0x14008d8b8  mov     rax, cs:__security_cookie
0x14008d8bf  xor     rax, rsp
0x14008d8c2  mov     [rbp+240h+var_50], rax
0x14008d8c9  mov     rdi, rcx
0x14008d8cc  mov     r12d, 40h ; '@'
0x14008d8d2  mov     r8d, r12d; Size
0x14008d8d5  lea     rcx, [rbp+240h+var_180]; void *
0x14008d8dc  xor     edx, edx; Val
0x14008d8de  call    memset
0x14008d8e3  xor     r14d, r14d
0x14008d8e6  mov     [rbp+240h+var_2B8], 480046h
0x14008d8ee  xorps   xmm0, xmm0
0x14008d8f1  mov     [rbp+240h+var_278], 480046h
0x14008d8f9  xorps   xmm1, xmm1
0x14008d8fc  mov     [rbp+240h+var_268], 540052h
0x14008d904  lea     rax, aDeviceencrypti_6; "DeviceEncryption-WindowsCore-OSMain"
0x14008d90b  mov     [rbp+240h+var_258], 4C004Ah
0x14008d913  mov     [rbp+240h+var_2B0], rax
0x14008d917  lea     rax, aDeviceencrypti; "DeviceEncryption-WindowsCore-OSData"
0x14008d91e  mov     [rbp+240h+var_270], rax
0x14008d922  lea     rax, aDeviceencrypti_4; "DeviceEncryption-WindowsCore-PreInstall"...
0x14008d929  mov     [rbp+240h+var_260], rax
0x14008d92d  lea     rax, aDeviceencrypti_8; "DeviceEncryption-WindowsCore-UserData"
0x14008d934  mov     [rbp+240h+var_250], rax
0x14008d938  lea     rax, aDeviceencrypti_3; "DeviceEncryption-WindowsCore-BSP"
0x14008d93f  mov     [rbp+240h+var_2A0], rax
0x14008d943  lea     rax, aDeviceencrypti_5; "DeviceEncryption-WindowsCore-DPP"
0x14008d94a  mov     [rbp+240h+var_290], rax
0x14008d94e  lea     rax, aDeviceencrypti_1; "DeviceEncryption-WindowsCore-WSP"
0x14008d955  mov     [rbp+240h+var_280], rax
0x14008d959  lea     rax, aDeviceencrypti_7; "DeviceEncryption-WindowsCore-ServicingM"...
0x14008d960  mov     [rbp+240h+var_240], rax
0x14008d964  lea     rax, aDeviceencrypti_0; "DeviceEncryption-WindowsCore-ServicingF"...
0x14008d96b  mov     [rbp+240h+var_230], rax
0x14008d96f  lea     rax, aDeviceencrypti_2; "DeviceEncryption-WindowsCore-ServicingR"...
0x14008d976  mov     [rbp+240h+var_220], rax
0x14008d97a  xor     eax, eax
0x14008d97c  mov     [rbp+240h+var_130], rax
0x14008d983  mov     [rbp+240h+var_2A8], 420040h
0x14008d98b  mov     [rbp+240h+var_298], 420040h
0x14008d993  mov     [rbp+240h+var_288], 420040h
0x14008d99b  mov     [rbp+240h+var_248], 5E005Ch
0x14008d9a3  mov     [rbp+240h+var_238], 580056h
0x14008d9ab  mov     [rbp+240h+var_228], 5C005Ah
0x14008d9b3  mov     [rsp+340h+var_2CC], r14d
0x14008d9b8  mov     [rsp+340h+var_2D0], r14d
0x14008d9bd  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x14008d9c1  movups  xmmword ptr [rbp+240h+var_1B0.Length], xmm1
0x14008d9c8  movups  xmmword ptr [rbp+240h+var_1A0.Length], xmm0
0x14008d9cf  movups  [rbp+240h+SystemInformation], xmm1
0x14008d9d6  movups  xmmword ptr [rbp+240h+var_1C0.Length], xmm0
0x14008d9dd  movups  xmmword ptr [rbp+240h+var_190.Length], xmm1
0x14008d9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d9eb  lea     r13, WPP_GLOBAL_Control
0x14008d9f2  cmp     rcx, r13
0x14008d9f5  jz      short loc_14008DA1A
0x14008d9f7  mov     eax, [rcx+2Ch]
0x14008d9fa  test    r12b, al
0x14008d9fd  jz      short loc_14008DA1A
0x14008d9ff  cmp     byte ptr [rcx+29h], 5
0x14008da03  jb      short loc_14008DA1A
0x14008da05  mov     rcx, [rcx+18h]
0x14008da09  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14008da10  mov     edx, 0C6h
0x14008da15  call    WPP_SF_
0x14008da1a  test    rdi, rdi
0x14008da1d  jnz     short loc_14008DA29
0x14008da1f  mov     ebx, 0C000000Dh
0x14008da24  jmp     loc_14008E9A4
0x14008da29  lea     rcx, [rdi+28C0h]; FastMutex
0x14008da30  mov     r8b, 1
0x14008da33  lea     rdx, [rbp+240h+var_180]
0x14008da3a  call    FvepLockAcquireLock
0x14008da3f  test    byte ptr [rdi+2918h], 1
0x14008da46  jnz     loc_14008E9FC
0x14008da4c  mov     r15d, 4
0x14008da52  mov     dword ptr [rsp+340h+var_2C8], r14d
0x14008da57  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14008da5e  mov     dword ptr [rbp+240h+var_2C0], r15d
0x14008da62  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x14008da66  call    cs:__imp_RtlInitUnicodeString
0x14008da6d  nop     dword ptr [rax+rax+00h]
0x14008da72  lea     rdx, aOsvallowwritea; "OsvAllowWriteAccess"
0x14008da79  lea     rcx, [rbp+240h+var_1B0]; DestinationString
0x14008da80  call    cs:__imp_RtlInitUnicodeString
0x14008da87  nop     dword ptr [rax+rax+00h]
0x14008da8c  lea     rax, [rbp+240h+var_2C0]
0x14008da90  mov     r8d, r15d
0x14008da93  lea     r9, [rsp+340h+var_2C8]
0x14008da98  mov     [rsp+340h+var_320], rax
0x14008da9d  lea     rdx, [rbp+240h+var_1B0]
0x14008daa4  lea     rcx, [rbp+240h+DestinationString]
0x14008daa8  call    FveGetRegistryValue
0x14008daad  mov     esi, 0C0000034h
0x14008dab2  mov     ebx, eax
0x14008dab4  cmp     eax, esi
0x14008dab6  jnz     short loc_14008DABD
0x14008dab8  mov     eax, r14d
0x14008dabb  jmp     short loc_14008DAC9
0x14008dabd  test    eax, eax
0x14008dabf  js      loc_14008E998
0x14008dac5  mov     eax, dword ptr [rsp+340h+var_2C8]
0x14008dac9  test    eax, eax
0x14008dacb  jz      short loc_14008DB04
0x14008dacd  mov     rcx, cs:WPP_GLOBAL_Control
0x14008dad4  cmp     rcx, r13
0x14008dad7  jz      short loc_14008DAFC
0x14008dad9  mov     eax, [rcx+2Ch]
0x14008dadc  test    r12b, al
0x14008dadf  jz      short loc_14008DAFC
0x14008dae1  cmp     [rcx+29h], r15b
0x14008dae5  jb      short loc_14008DAFC
0x14008dae7  mov     rcx, [rcx+18h]
0x14008daeb  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14008daf2  mov     edx, 0C7h
0x14008daf7  call    WPP_SF_
0x14008dafc  or      qword ptr [rdi+2918h], 0Ch
0x14008db04  lea     rdx, aWcosdisablebit; "WcosDisableBitLockerRO"
0x14008db0b  mov     dword ptr [rsp+340h+var_2C8], r14d
0x14008db10  lea     rcx, [rbp+240h+var_1A0]; DestinationString
0x14008db17  mov     dword ptr [rbp+240h+var_2C0], r15d
0x14008db1b  call    cs:__imp_RtlInitUnicodeString
0x14008db22  nop     dword ptr [rax+rax+00h]
0x14008db27  lea     rax, [rbp+240h+var_2C0]
0x14008db2b  mov     r8d, r15d
0x14008db2e  lea     r9, [rsp+340h+var_2C8]
0x14008db33  mov     [rsp+340h+var_320], rax
0x14008db38  lea     rdx, [rbp+240h+var_1A0]
0x14008db3f  lea     rcx, [rbp+240h+DestinationString]
0x14008db43  call    FveGetRegistryValue
0x14008db48  mov     ebx, eax
0x14008db4a  cmp     eax, esi
0x14008db4c  jnz     short loc_14008DB56
0x14008db4e  mov     eax, r14d
0x14008db51  mov     ebx, r14d
0x14008db54  jmp     short loc_14008DB62
0x14008db56  test    eax, eax
0x14008db58  js      loc_14008E998
0x14008db5e  mov     eax, dword ptr [rsp+340h+var_2C8]
0x14008db62  test    eax, eax
0x14008db64  jz      short loc_14008DB9D
0x14008db66  mov     rcx, cs:WPP_GLOBAL_Control
0x14008db6d  cmp     rcx, r13
0x14008db70  jz      short loc_14008DB95
0x14008db72  mov     eax, [rcx+2Ch]
0x14008db75  test    r12b, al
0x14008db78  jz      short loc_14008DB95
0x14008db7a  cmp     [rcx+29h], r15b
0x14008db7e  jb      short loc_14008DB95
0x14008db80  mov     rcx, [rcx+18h]
0x14008db84  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14008db8b  mov     edx, 0C8h
0x14008db90  call    WPP_SF_
0x14008db95  or      qword ptr [rdi+2918h], 8
0x14008db9d  lea     rsi, [rdi+2920h]
0x14008dba4  mov     r8, rsi
0x14008dba7  lea     rdx, aWcososmainleve; "WcosOsMainLevel"
0x14008dbae  call    FveTestGetDwordOverride
0x14008dbb3  test    al, al
0x14008dbb5  jz      short loc_14008DBFA
0x14008dbb7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008dbbe  cmp     rcx, r13
0x14008dbc1  jz      loc_14008DC9A
0x14008dbc7  mov     eax, [rcx+2Ch]
0x14008dbca  test    r12b, al
0x14008dbcd  jz      loc_14008DC9A
0x14008dbd3  cmp     [rcx+29h], r15b
0x14008dbd7  jb      loc_14008DC9A
0x14008dbdd  mov     r9d, [rsi]
0x14008dbe0  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14008dbe7  mov     rcx, [rcx+18h]
0x14008dbeb  mov     edx, 0C9h
0x14008dbf0  call    WPP_SF_d
0x14008dbf5  jmp     loc_14008DC9A
0x14008dbfa  lea     rax, [rsp+340h+var_2D0]
0x14008dbff  mov     [rsp+340h+var_2D0], r15d
0x14008dc04  mov     r9d, r15d
0x14008dc07  mov     [rsp+340h+var_320], rax
0x14008dc0c  mov     r8, rsi
0x14008dc0f  lea     rdx, [rsp+340h+var_2CC]
0x14008dc14  lea     rcx, [rbp+240h+var_2B8]
0x14008dc18  call    cs:__imp_ZwQueryLicenseValue
0x14008dc1f  nop     dword ptr [rax+rax+00h]
0x14008dc24  mov     ebx, eax
0x14008dc26  cmp     eax, 0C000003Eh
0x14008dc2b  jnz     short loc_14008DC54
0x14008dc2d  mov     [rsi], r14d
0x14008dc30  mov     ebx, r14d
0x14008dc33  mov     rcx, cs:WPP_GLOBAL_Control
0x14008dc3a  cmp     rcx, r13
0x14008dc3d  jz      short loc_14008DC9A
0x14008dc3f  mov     eax, [rcx+2Ch]
0x14008dc42  test    r12b, al
0x14008dc45  jz      short loc_14008DC9A
0x14008dc47  cmp     byte ptr [rcx+29h], 3
0x14008dc4b  jb      short loc_14008DC9A
0x14008dc4d  mov     edx, 0CAh
0x14008dc52  jmp     short loc_14008DC80
0x14008dc54  cmp     eax, 0C0000034h
0x14008dc59  jnz     short loc_14008DC92
0x14008dc5b  mov     [rsi], r14d
0x14008dc5e  mov     ebx, r14d
0x14008dc61  mov     rcx, cs:WPP_GLOBAL_Control
0x14008dc68  cmp     rcx, r13
0x14008dc6b  jz      short loc_14008DC9A
0x14008dc6d  mov     eax, [rcx+2Ch]
0x14008dc70  test    r12b, al
0x14008dc73  jz      short loc_14008DC9A
0x14008dc75  cmp     byte ptr [rcx+29h], 3
0x14008dc79  jb      short loc_14008DC9A
0x14008dc7b  mov     edx, 0CBh
0x14008dc80  mov     rcx, [rcx+18h]
0x14008dc84  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14008dc8b  call    WPP_SF_
0x14008dc90  jmp     short loc_14008DC9A
0x14008dc92  test    eax, eax
0x14008dc94  js      loc_14008E998
0x14008dc9a  lea     rsi, [rdi+2924h]
0x14008dca1  mov     r8, rsi
0x14008dca4  lea     rdx, aWcosbsplevel; "WcosBspLevel"
0x14008dcab  call    FveTestGetDwordOverride
0x14008dcb0  test    al, al
0x14008dcb2  jz      short loc_14008DCF7
0x14008dcb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008dcbb  cmp     rcx, r13
0x14008dcbe  jz      loc_14008DD97
0x14008dcc4  mov     eax, [rcx+2Ch]
0x14008dcc7  test    r12b, al
0x14008dcca  jz      loc_14008DD97
0x14008dcd0  cmp     [rcx+29h], r15b
0x14008dcd4  jb      loc_14008DD97
0x14008dcda  mov     r9d, [rsi]
0x14008dcdd  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14008dce4  mov     rcx, [rcx+18h]
0x14008dce8  mov     edx, 0CCh
0x14008dced  call    WPP_SF_d
0x14008dcf2  jmp     loc_14008DD97
0x14008dcf7  lea     rax, [rsp+340h+var_2D0]
0x14008dcfc  mov     [rsp+340h+var_2D0], r15d
0x14008dd01  mov     r9d, r15d
0x14008dd04  mov     [rsp+340h+var_320], rax
0x14008dd09  mov     r8, rsi
0x14008dd0c  lea     rdx, [rsp+340h+var_2CC]
0x14008dd11  lea     rcx, [rbp+240h+var_2A8]
0x14008dd15  call    cs:__imp_ZwQueryLicenseValue
0x14008dd1c  nop     dword ptr [rax+rax+00h]
0x14008dd21  mov     ebx, eax
0x14008dd23  cmp     eax, 0C000003Eh
0x14008dd28  jnz     short loc_14008DD51
0x14008dd2a  mov     [rsi], r14d
0x14008dd2d  mov     ebx, r14d
0x14008dd30  mov     rcx, cs:WPP_GLOBAL_Control
0x14008dd37  cmp     rcx, r13
0x14008dd3a  jz      short loc_14008DD97
0x14008dd3c  mov     eax, [rcx+2Ch]
0x14008dd3f  test    r12b, al
0x14008dd42  jz      short loc_14008DD97
0x14008dd44  cmp     byte ptr [rcx+29h], 3
0x14008dd48  jb      short loc_14008DD97
0x14008dd4a  mov     edx, 0CDh
0x14008dd4f  jmp     short loc_14008DD7D
0x14008dd51  cmp     eax, 0C0000034h
0x14008dd56  jnz     short loc_14008DD8F
0x14008dd58  mov     [rsi], r14d
0x14008dd5b  mov     ebx, r14d
0x14008dd5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008dd65  cmp     rcx, r13
0x14008dd68  jz      short loc_14008DD97
0x14008dd6a  mov     eax, [rcx+2Ch]
0x14008dd6d  test    r12b, al
0x14008dd70  jz      short loc_14008DD97
0x14008dd72  cmp     byte ptr [rcx+29h], 3
0x14008dd76  jb      short loc_14008DD97
0x14008dd78  mov     edx, 0CEh
0x14008dd7d  mov     rcx, [rcx+18h]
0x14008dd81  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14008dd88  call    WPP_SF_
0x14008dd8d  jmp     short loc_14008DD97
0x14008dd8f  test    eax, eax
0x14008dd91  js      loc_14008E998
0x14008dd97  lea     rsi, [rdi+2928h]
0x14008dd9e  mov     r8, rsi
0x14008dda1  lea     rdx, aWcosdpplevel; "WcosDppLevel"
0x14008dda8  call    FveTestGetDwordOverride
0x14008ddad  test    al, al
0x14008ddaf  jz      short loc_14008DDF4
0x14008ddb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ddb8  cmp     rcx, r13
0x14008ddbb  jz      loc_14008DE94
0x14008ddc1  mov     eax, [rcx+2Ch]
  ... truncated ...
```
