# FveFeatResolve

- ea: `0x14008b7fc`
- end: `0x14008c95a`
- name: `FveFeatResolve`
- size: `4446`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14008b630`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140008dc0`
- `0x140008e44`
- `0x14000f19c`
- `0x1400218c0`
- `0x140021d00`
- `0x140079638`
- `0x14008b7fc`
- `0x140097060`
- `0x1400da91c`
- `0x1400daf2c`

## import_xrefs

- `ntoskrnl!ZwQuerySystemInformation` at `0x14008c60b`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14008c60b`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bb78`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bc75`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bd72`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008be6f`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bf6c`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c071`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c185`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c287`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c387`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c492`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bb78`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bc75`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bd72`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008be6f`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008bf6c`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c071`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c185`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c287`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c387`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14008c492`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008c65b`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008c65b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008b9c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008b9e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ba7b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008c680`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008c69a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008b9c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008b9e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ba7b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008c680`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008c69a`

## string_xrefs

- `0x14008b882`: `DeviceEncryption-WindowsCore-PreInstalled`
- `0x14008b9b7`: `\Registry\Machine\SYSTEM\CurrentControlSet\Policies\Microsoft\FVE`
- `0x14008c679`: `\Registry\Machine\SYSTEM\CurrentControlSet\Policies\Microsoft\FVE`
- `0x14008b9d2`: `OsvAllowWriteAccess`
- `0x14008bff8`: `WcosPreInstalledLevel`
- `0x14008c66e`: `\Registry\Machine\OSBOOT\CurrentControlSet\Policies\Microsoft\FVE`

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
  _DWORD *v28; // r13
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
  char IsStateSeparationEnabled; // al
  const WCHAR *v50; // rdx
  int v51; // eax
  int v52; // eax
  __int64 v53; // rcx
  int v55; // [rsp+70h] [rbp-90h] BYREF
  int v56; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v57; // [rsp+78h] [rbp-88h] BYREF
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v59[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v60[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v61[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v62[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v63[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v64[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v65[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v66[2]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v67[2]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v68[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v69; // [rsp+128h] [rbp+28h] BYREF
  __int64 v70; // [rsp+130h] [rbp+30h] BYREF
  __int64 v71; // [rsp+138h] [rbp+38h] BYREF
  __int64 v72; // [rsp+140h] [rbp+40h] BYREF
  __int64 v73; // [rsp+148h] [rbp+48h] BYREF
  __int64 v74; // [rsp+150h] [rbp+50h] BYREF
  __int64 v75; // [rsp+158h] [rbp+58h] BYREF
  __int64 v76; // [rsp+160h] [rbp+60h] BYREF
  __int64 v77; // [rsp+168h] [rbp+68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+170h] [rbp+70h] BYREF
  struct _UNICODE_STRING v79; // [rsp+180h] [rbp+80h] BYREF
  struct _UNICODE_STRING v80; // [rsp+190h] [rbp+90h] BYREF
  struct _UNICODE_STRING v81; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _UNICODE_STRING v82; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v83[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 SystemInformation; // [rsp+200h] [rbp+100h] BYREF
  __int64 v85; // [rsp+210h] [rbp+110h]
  _BYTE v86[32]; // [rsp+220h] [rbp+120h] BYREF
  __int64 *v87; // [rsp+240h] [rbp+140h]
  __int64 v88; // [rsp+248h] [rbp+148h]
  __int64 *v89; // [rsp+250h] [rbp+150h]
  __int64 v90; // [rsp+258h] [rbp+158h]
  __int64 *v91; // [rsp+260h] [rbp+160h]
  __int64 v92; // [rsp+268h] [rbp+168h]
  __int64 *v93; // [rsp+270h] [rbp+170h]
  __int64 v94; // [rsp+278h] [rbp+178h]
  __int64 *v95; // [rsp+280h] [rbp+180h]
  __int64 v96; // [rsp+288h] [rbp+188h]
  __int64 *v97; // [rsp+290h] [rbp+190h]
  __int64 v98; // [rsp+298h] [rbp+198h]
  __int64 *v99; // [rsp+2A0h] [rbp+1A0h]
  __int64 v100; // [rsp+2A8h] [rbp+1A8h]
  __int64 *v101; // [rsp+2B0h] [rbp+1B0h]
  __int64 v102; // [rsp+2B8h] [rbp+1B8h]
  __int64 *v103; // [rsp+2C0h] [rbp+1C0h]
  __int64 v104; // [rsp+2C8h] [rbp+1C8h]
  __int64 *v105; // [rsp+2D0h] [rbp+1D0h]
  __int64 v106; // [rsp+2D8h] [rbp+1D8h]
  __int64 *v107; // [rsp+2E0h] [rbp+1E0h]
  __int64 v108; // [rsp+2E8h] [rbp+1E8h]

  memset(v83, 0, sizeof(v83));
  v59[0] = 4718662;
  v63[0] = 4718662;
  v64[0] = 5505106;
  v65[0] = 4980810;
  v59[1] = L"DeviceEncryption-WindowsCore-OSMain";
  v63[1] = L"DeviceEncryption-WindowsCore-OSData";
  v64[1] = L"DeviceEncryption-WindowsCore-PreInstalled";
  v65[1] = L"DeviceEncryption-WindowsCore-UserData";
  v60[1] = L"DeviceEncryption-WindowsCore-BSP";
  v61[1] = L"DeviceEncryption-WindowsCore-DPP";
  v62[1] = L"DeviceEncryption-WindowsCore-WSP";
  v66[1] = L"DeviceEncryption-WindowsCore-ServicingMetadata";
  v67[1] = L"DeviceEncryption-WindowsCore-ServicingFiles";
  v68[1] = L"DeviceEncryption-WindowsCore-ServicingReserve";
  v85 = 0;
  v60[0] = 4325440;
  v61[0] = 4325440;
  v62[0] = 4325440;
  v66[0] = 6160476;
  v67[0] = 5767254;
  v68[0] = 6029402;
  v56 = 0;
  v55 = 0;
  DestinationString = 0;
  v80 = 0;
  v81 = 0;
  SystemInformation = 0;
  v79 = 0;
  v82 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 200, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
  }
  if ( a1 )
  {
    FvepLockAcquireLock((PFAST_MUTEX)(a1 + 10184));
    if ( (*(_BYTE *)(a1 + 10272) & 1) != 0 )
    {
      v2 = 0;
      goto LABEL_234;
    }
    LODWORD(v57) = 0;
    LODWORD(v58) = 4;
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Policies\\Microsoft\\FVE");
    RtlInitUnicodeString(&v80, L"OsvAllowWriteAccess");
    RegistryValue = FveGetRegistryValue(&DestinationString, &v80, 4, &v57, &v58);
    v2 = RegistryValue;
    if ( RegistryValue == -1073741772 )
    {
      v4 = 0;
    }
    else
    {
      if ( RegistryValue < 0 )
        goto LABEL_234;
      v4 = v57;
    }
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 201, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
      }
      *(_QWORD *)(a1 + 10272) |= 0xCuLL;
    }
    LODWORD(v57) = 0;
    LODWORD(v58) = 4;
    RtlInitUnicodeString(&v81, L"WcosDisableBitLockerRO");
    v5 = FveGetRegistryValue(&DestinationString, &v81, 4, &v57, &v58);
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
      v7 = v57;
    }
    if ( v7 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 202, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
      }
      *(_QWORD *)(a1 + 10272) |= 8uLL;
    }
    v8 = (_DWORD *)(a1 + 10280);
    if ( (unsigned __int8)FveTestGetDwordOverride(v6, L"WcosOsMainLevel", a1 + 10280) )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          203,
          WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
          (unsigned int)*v8);
      }
      goto LABEL_45;
    }
    v55 = 4;
    v10 = ZwQueryLicenseValue(v59, &v56, a1 + 10280, 4, &v55);
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
      v11 = 204;
    }
    else
    {
      if ( v10 != -1073741772 )
      {
        if ( v10 < 0 )
          goto LABEL_234;
LABEL_45:
        v12 = (_DWORD *)(a1 + 10284);
        if ( (unsigned __int8)FveTestGetDwordOverride(v9, L"WcosBspLevel", a1 + 10284) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              206,
              WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
              (unsigned int)*v12);
          }
          goto LABEL_62;
        }
        v55 = 4;
        v14 = ZwQueryLicenseValue(v60, &v56, a1 + 10284, 4, &v55);
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
          v15 = 207;
        }
        else
        {
          if ( v14 != -1073741772 )
          {
            if ( v14 < 0 )
              goto LABEL_234;
LABEL_62:
            v16 = (_DWORD *)(a1 + 10288);
            if ( (unsigned __int8)FveTestGetDwordOverride(v13, L"WcosDppLevel", a1 + 10288) )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  209,
                  WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                  (unsigned int)*v16);
              }
              goto LABEL_79;
            }
            v55 = 4;
            v18 = ZwQueryLicenseValue(v61, &v56, a1 + 10288, 4, &v55);
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
              v19 = 210;
            }
            else
            {
              if ( v18 != -1073741772 )
              {
                if ( v18 < 0 )
                  goto LABEL_234;
LABEL_79:
                v20 = (_DWORD *)(a1 + 10292);
                if ( (unsigned __int8)FveTestGetDwordOverride(v17, L"WcosWspLevel", a1 + 10292) )
                {
                  v21 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      212,
                      WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                      (unsigned int)*v20);
                  }
                  goto LABEL_96;
                }
                v55 = 4;
                v22 = ZwQueryLicenseValue(v62, &v56, a1 + 10292, 4, &v55);
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
                  v23 = 213;
                }
                else
                {
                  if ( v22 != -1073741772 )
                  {
                    if ( v22 < 0 )
                      goto LABEL_234;
LABEL_96:
                    v24 = (_DWORD *)(a1 + 10296);
                    if ( (unsigned __int8)FveTestGetDwordOverride(v21, L"WcosOsDataLevel", a1 + 10296) )
                    {
                      v25 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          215,
                          WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                          (unsigned int)*v24);
                      }
                      goto LABEL_113;
                    }
                    v55 = 4;
                    v26 = ZwQueryLicenseValue(v63, &v56, a1 + 10296, 4, &v55);
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
                      v27 = 216;
                    }
                    else
                    {
                      if ( v26 != -1073741772 )
                      {
                        if ( v26 < 0 )
                          goto LABEL_234;
LABEL_113:
                        v28 = (_DWORD *)(a1 + 10300);
                        if ( (unsigned __int8)FveTestGetDwordOverride(v25, L"WcosPreInstalledLevel", a1 + 10300) )
                        {
                          v29 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              218,
                              WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                              (unsigned int)*v28);
                          }
                          goto LABEL_130;
                        }
                        v55 = 4;
                        v30 = ZwQueryLicenseValue(v64, &v56, a1 + 10300, 4, &v55);
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
                          v31 = 219;
                        }
                        else
                        {
                          if ( v30 != -1073741772 )
                          {
                            if ( v30 < 0 )
                              goto LABEL_234;
LABEL_130:
                            v32 = (_DWORD *)(a1 + 10304);
                            if ( (unsigned __int8)FveTestGetDwordOverride(v29, L"WcosUserDataLevel", a1 + 10304) )
                            {
                              v33 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                              {
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  221,
                                  WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                                  (unsigned int)*v32);
                              }
                              goto LABEL_147;
                            }
                            v55 = 4;
                            v34 = ZwQueryLicenseValue(v65, &v56, a1 + 10304, 4, &v55);
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
                              v35 = 222;
                            }
                            else
                            {
                              if ( v34 != -1073741772 )
                              {
                                if ( v34 < 0 )
                                  goto LABEL_234;
LABEL_147:
                                v36 = (_DWORD *)(a1 + 10308);
                                if ( (unsigned __int8)FveTestGetDwordOverride(
                                                        v33,
                                                        L"WcosServicingMetadataLevel",
                                                        a1 + 10308) )
                                {
                                  v37 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                  {
                                    WPP_SF_d(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      224,
                                      WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                                      (unsigned int)*v36);
                                  }
                                  goto LABEL_164;
                                }
                                v55 = 4;
                                v38 = ZwQueryLicenseValue(v66, &v56, a1 + 10308, 4, &v55);
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
                                  v39 = 225;
                                }
                                else
                                {
                                  if ( v38 != -1073741772 )
                                  {
                                    if ( v38 < 0 )
                                      goto LABEL_234;
LABEL_164:
                                    v40 = (_DWORD *)(a1 + 10312);
                                    if ( (unsigned __int8)FveTestGetDwordOverride(
                                                            v37,
                                                            L"WcosServicingFilesLevel",
                                                            a1 + 10312) )
                                    {
                                      v41 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                      {
                                        WPP_SF_d(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          227,
                                          WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                                          (unsigned int)*v40);
                                      }
                                      goto LABEL_181;
                                    }
                                    v55 = 4;
                                    v42 = ZwQueryLicenseValue(v67, &v56, a1 + 10312, 4, &v55);
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
                                      v43 = 228;
                                    }
                                    else
                                    {
                                      if ( v42 != -1073741772 )
                                      {
                                        if ( v42 < 0 )
                                          goto LABEL_234;
LABEL_181:
                                        v44 = (_DWORD *)(a1 + 10316);
                                        if ( (unsigned __int8)FveTestGetDwordOverride(
                                                                v41,
                                                                L"WcosServicingReserveLevel",
                                                                a1 + 10316) )
                                        {
                                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                          {
                                            WPP_SF_d(
                                              WPP_GLOBAL_Control->AttachedDevice,
                                              230,
                                              WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
                                              (unsigned int)*v44);
                                          }
                                          goto LABEL_198;
                                        }
                                        v55 = 4;
                                        v45 = ZwQueryLicenseValue(v68, &v56, a1 + 10316, 4, &v55);
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
                                          v47 = 231;
                                        }
                                        else
                                        {
                                          if ( v45 != -1073741772 )
                                          {
                                            if ( v45 < 0 )
                                              goto LABEL_234;
LABEL_198:
                                            if ( *(_QWORD *)(a1 + 10280)
                                              || *(_DWORD *)(a1 + 10288)
                                              || *(_DWORD *)(a1 + 10292)
                                              || *(_DWORD *)(a1 + 10296)
                                              || *v28
                                              || *v32
                                              || *v36
                                              || *v40
                                              || *v44 )
                                            {
                                              *(_QWORD *)(a1 + 10272) |= 2uLL;
                                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                              {
                                                WPP_SF_LLLLLLLLLL(WPP_GLOBAL_Control->AttachedDevice);
                                              }
                                            }
                                            if ( (*(_BYTE *)(a1 + 10272) & 2) == 0 )
                                              goto LABEL_233;
                                            v48 = ZwQuerySystemInformation(
                                                    SystemNonPagedPoolInformation|0x80,
                                                    &SystemInformation,
                                                    0x18u,
                                                    0);
                                            if ( v48 >= 0 )
                                            {
                                              if ( (v85 & 0x1000000000LL) != 0 )
LABEL_216:
                                                *(_QWORD *)(a1 + 10272) |= 0x8000000000000000uLL;
                                            }
                                            else if ( v48 == -2143092730 )
                                            {
                                              goto LABEL_216;
                                            }
                                            if ( *(__int64 *)(a1 + 10272) >= 0 )
                                            {
LABEL_230:
                                              if ( (unsigned int)dword_140045040 > 4
                                                && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
                                              {
                                                v58 = *(unsigned int *)(a1 + 10280);
                                                v88 = 8;
                                                v87 = &v58;
                                                v57 = *(unsigned int *)(a1 + 10284);
                                                v89 = &v57;
                                                v69 = *(unsigned int *)(a1 + 10288);
                                                v91 = &v69;
                                                v70 = *(unsigned int *)(a1 + 10292);
                                                v93 = &v70;
                                                v71 = *(unsigned int *)(a1 + 10296);
                                                v95 = &v71;
                                                v72 = (unsigned int)*v28;
                                                v97 = &v72;
                                                v73 = (unsigned int)*v32;
                                                v99 = &v73;
                                                v74 = (unsigned int)*v36;
                                                v101 = &v74;
                                                v75 = (unsigned int)*v40;
                                                v103 = &v75;
                                                v76 = (unsigned int)*v44;
                                                v105 = &v76;
                                                v77 = *(_QWORD *)(a1 + 10272);
                                                v107 = &v77;
                                                v90 = 8;
                                                v92 = 8;
                                                v94 = 8;
                                                v96 = 8;
                                                v98 = 8;
                                                v100 = 8;
                                                v102 = 8;
                                                v104 = 8;
                                                v106 = 8;
                                                v108 = 8;
                                                tlgWriteTransfer_EtwWriteTransfer(v53, byte_14003C571, 0, 0, 13, v86);
                                              }
LABEL_233:
                                              *(_QWORD *)(a1 + 10272) |= 1uLL;
                                              goto LABEL_234;
                                            }
                                            LODWORD(v57) = 0;
                                            LODWORD(v58) = 4;
                                            IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
                                            v50 = L"\\Registry\\Machine\\OSBOOT\\CurrentControlSet\\Policies\\Microsoft\\FVE";
                                            if ( !IsStateSeparationEnabled )
                                              v50 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Policies\\Microsoft\\FVE";
                                            RtlInitUnicodeString(&v79, v50);
                                            RtlInitUnicodeString(&v82, L"WcosNonRetailNoForcedPoAc");
                                            v51 = FveGetRegistryValue(&v79, &v82, 4, &v57, &v58);
                                            v2 = v51;
                                            if ( v51 == -1073741772 )
                                            {
                                              v52 = 0;
                                              v2 = 0;
                                              goto LABEL_224;
                                            }
                                            if ( v51 >= 0 )
                                            {
                                              v52 = v57;
LABEL_224:
                                              if ( v52 )
                                              {
                                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
                                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                                {
                                                  WPP_SF_(
                                                    WPP_GLOBAL_Control->AttachedDevice,
                                                    234,
                                                    WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
                                                }
                                                *(_QWORD *)(a1 + 10272) |= 0x4000000000000000uLL;
                                              }
                                              goto LABEL_230;
                                            }
LABEL_234:
                                            FvepLockReleaseLock(v83);
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
                                          v47 = 232;
                                        }
                                        WPP_SF_(
                                          v46->AttachedDevice,
                                          v47,
                                          WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
                                      v43 = 229;
                                    }
                                    WPP_SF_(v41->AttachedDevice, v43, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
                                  v39 = 226;
                                }
                                WPP_SF_(v37->AttachedDevice, v39, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
                              v35 = 223;
                            }
                            WPP_SF_(v33->AttachedDevice, v35, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
                          v31 = 220;
                        }
                        WPP_SF_(v29->AttachedDevice, v31, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
                      v27 = 217;
                    }
                    WPP_SF_(v25->AttachedDevice, v27, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
                  v23 = 214;
                }
                WPP_SF_(v21->AttachedDevice, v23, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
              v19 = 211;
            }
            WPP_SF_(v17->AttachedDevice, v19, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
          v15 = 208;
        }
        WPP_SF_(v13->AttachedDevice, v15, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
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
      v11 = 205;
    }
    WPP_SF_(v9->AttachedDevice, v11, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
    goto LABEL_45;
  }
  v2 = -1073741811;
LABEL_235:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 235, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x14008b7fc  push    rbp
0x14008b7fe  push    rbx
0x14008b7ff  push    rsi
0x14008b800  push    rdi
0x14008b801  push    r12
0x14008b803  push    r13
0x14008b805  push    r14
0x14008b807  push    r15
0x14008b809  lea     rbp, [rsp-208h]
0x14008b811  sub     rsp, 308h
0x14008b818  mov     rax, cs:__security_cookie
0x14008b81f  xor     rax, rsp
0x14008b822  mov     [rbp+240h+var_50], rax
0x14008b829  mov     rdi, rcx
0x14008b82c  mov     r12d, 40h ; '@'
0x14008b832  mov     r8d, r12d; Size
0x14008b835  lea     rcx, [rbp+240h+var_180]; void *
0x14008b83c  xor     edx, edx; Val
0x14008b83e  call    memset
0x14008b843  xor     r14d, r14d
0x14008b846  mov     [rbp+240h+var_2B8], 480046h
0x14008b84e  xorps   xmm0, xmm0
0x14008b851  mov     [rbp+240h+var_278], 480046h
0x14008b859  xorps   xmm1, xmm1
0x14008b85c  mov     [rbp+240h+var_268], 540052h
0x14008b864  lea     rax, aDeviceencrypti_6; "DeviceEncryption-WindowsCore-OSMain"
0x14008b86b  mov     [rbp+240h+var_258], 4C004Ah
0x14008b873  mov     [rbp+240h+var_2B0], rax
0x14008b877  lea     rax, aDeviceencrypti; "DeviceEncryption-WindowsCore-OSData"
0x14008b87e  mov     [rbp+240h+var_270], rax
0x14008b882  lea     rax, aDeviceencrypti_4; "DeviceEncryption-WindowsCore-PreInstall"...
0x14008b889  mov     [rbp+240h+var_260], rax
0x14008b88d  lea     rax, aDeviceencrypti_8; "DeviceEncryption-WindowsCore-UserData"
0x14008b894  mov     [rbp+240h+var_250], rax
0x14008b898  lea     rax, aDeviceencrypti_3; "DeviceEncryption-WindowsCore-BSP"
0x14008b89f  mov     [rbp+240h+var_2A0], rax
0x14008b8a3  lea     rax, aDeviceencrypti_5; "DeviceEncryption-WindowsCore-DPP"
0x14008b8aa  mov     [rbp+240h+var_290], rax
0x14008b8ae  lea     rax, aDeviceencrypti_1; "DeviceEncryption-WindowsCore-WSP"
0x14008b8b5  mov     [rbp+240h+var_280], rax
0x14008b8b9  lea     rax, aDeviceencrypti_7; "DeviceEncryption-WindowsCore-ServicingM"...
0x14008b8c0  mov     [rbp+240h+var_240], rax
0x14008b8c4  lea     rax, aDeviceencrypti_0; "DeviceEncryption-WindowsCore-ServicingF"...
0x14008b8cb  mov     [rbp+240h+var_230], rax
0x14008b8cf  lea     rax, aDeviceencrypti_2; "DeviceEncryption-WindowsCore-ServicingR"...
0x14008b8d6  mov     [rbp+240h+var_220], rax
0x14008b8da  xor     eax, eax
0x14008b8dc  mov     [rbp+240h+var_130], rax
0x14008b8e3  mov     [rbp+240h+var_2A8], 420040h
0x14008b8eb  mov     [rbp+240h+var_298], 420040h
0x14008b8f3  mov     [rbp+240h+var_288], 420040h
0x14008b8fb  mov     [rbp+240h+var_248], 5E005Ch
0x14008b903  mov     [rbp+240h+var_238], 580056h
0x14008b90b  mov     [rbp+240h+var_228], 5C005Ah
0x14008b913  mov     [rsp+340h+var_2CC], r14d
0x14008b918  mov     [rsp+340h+var_2D0], r14d
0x14008b91d  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x14008b921  movups  xmmword ptr [rbp+240h+var_1B0.Length], xmm1
0x14008b928  movups  xmmword ptr [rbp+240h+var_1A0.Length], xmm0
0x14008b92f  movups  [rbp+240h+SystemInformation], xmm1
0x14008b936  movups  xmmword ptr [rbp+240h+var_1C0.Length], xmm0
0x14008b93d  movups  xmmword ptr [rbp+240h+var_190.Length], xmm1
0x14008b944  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b94b  lea     r13, WPP_GLOBAL_Control
0x14008b952  cmp     rcx, r13
0x14008b955  jz      short loc_14008B97A
0x14008b957  mov     eax, [rcx+2Ch]
0x14008b95a  test    r12b, al
0x14008b95d  jz      short loc_14008B97A
0x14008b95f  cmp     byte ptr [rcx+29h], 5
0x14008b963  jb      short loc_14008B97A
0x14008b965  mov     rcx, [rcx+18h]
0x14008b969  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14008b970  mov     edx, 0C8h
0x14008b975  call    WPP_SF_
0x14008b97a  test    rdi, rdi
0x14008b97d  jnz     short loc_14008B989
0x14008b97f  mov     ebx, 0C000000Dh
0x14008b984  jmp     loc_14008C8FD
0x14008b989  lea     rcx, [rdi+27C8h]; FastMutex
0x14008b990  mov     r8b, 1
0x14008b993  lea     rdx, [rbp+240h+var_180]
0x14008b99a  call    FvepLockAcquireLock
0x14008b99f  test    byte ptr [rdi+2820h], 1
0x14008b9a6  jnz     loc_14008C955
0x14008b9ac  mov     r15d, 4
0x14008b9b2  mov     dword ptr [rsp+340h+var_2C8], r14d
0x14008b9b7  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14008b9be  mov     dword ptr [rbp+240h+var_2C0], r15d
0x14008b9c2  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x14008b9c6  call    cs:__imp_RtlInitUnicodeString
0x14008b9cd  nop     dword ptr [rax+rax+00h]
0x14008b9d2  lea     rdx, aOsvallowwritea; "OsvAllowWriteAccess"
0x14008b9d9  lea     rcx, [rbp+240h+var_1B0]; DestinationString
0x14008b9e0  call    cs:__imp_RtlInitUnicodeString
0x14008b9e7  nop     dword ptr [rax+rax+00h]
0x14008b9ec  lea     rax, [rbp+240h+var_2C0]
0x14008b9f0  mov     r8d, r15d
0x14008b9f3  lea     r9, [rsp+340h+var_2C8]
0x14008b9f8  mov     [rsp+340h+var_320], rax
0x14008b9fd  lea     rdx, [rbp+240h+var_1B0]
0x14008ba04  lea     rcx, [rbp+240h+DestinationString]
0x14008ba08  call    FveGetRegistryValue
0x14008ba0d  mov     esi, 0C0000034h
0x14008ba12  mov     ebx, eax
0x14008ba14  cmp     eax, esi
0x14008ba16  jnz     short loc_14008BA1D
0x14008ba18  mov     eax, r14d
0x14008ba1b  jmp     short loc_14008BA29
0x14008ba1d  test    eax, eax
0x14008ba1f  js      loc_14008C8F1
0x14008ba25  mov     eax, dword ptr [rsp+340h+var_2C8]
0x14008ba29  test    eax, eax
0x14008ba2b  jz      short loc_14008BA64
0x14008ba2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ba34  cmp     rcx, r13
0x14008ba37  jz      short loc_14008BA5C
0x14008ba39  mov     eax, [rcx+2Ch]
0x14008ba3c  test    r12b, al
0x14008ba3f  jz      short loc_14008BA5C
0x14008ba41  cmp     [rcx+29h], r15b
0x14008ba45  jb      short loc_14008BA5C
0x14008ba47  mov     rcx, [rcx+18h]
0x14008ba4b  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14008ba52  mov     edx, 0C9h
0x14008ba57  call    WPP_SF_
0x14008ba5c  or      qword ptr [rdi+2820h], 0Ch
0x14008ba64  lea     rdx, aWcosdisablebit; "WcosDisableBitLockerRO"
0x14008ba6b  mov     dword ptr [rsp+340h+var_2C8], r14d
0x14008ba70  lea     rcx, [rbp+240h+var_1A0]; DestinationString
0x14008ba77  mov     dword ptr [rbp+240h+var_2C0], r15d
0x14008ba7b  call    cs:__imp_RtlInitUnicodeString
0x14008ba82  nop     dword ptr [rax+rax+00h]
0x14008ba87  lea     rax, [rbp+240h+var_2C0]
0x14008ba8b  mov     r8d, r15d
0x14008ba8e  lea     r9, [rsp+340h+var_2C8]
0x14008ba93  mov     [rsp+340h+var_320], rax
0x14008ba98  lea     rdx, [rbp+240h+var_1A0]
0x14008ba9f  lea     rcx, [rbp+240h+DestinationString]
0x14008baa3  call    FveGetRegistryValue
0x14008baa8  mov     ebx, eax
0x14008baaa  cmp     eax, esi
0x14008baac  jnz     short loc_14008BAB6
0x14008baae  mov     eax, r14d
0x14008bab1  mov     ebx, r14d
0x14008bab4  jmp     short loc_14008BAC2
0x14008bab6  test    eax, eax
0x14008bab8  js      loc_14008C8F1
0x14008babe  mov     eax, dword ptr [rsp+340h+var_2C8]
0x14008bac2  test    eax, eax
0x14008bac4  jz      short loc_14008BAFD
0x14008bac6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bacd  cmp     rcx, r13
0x14008bad0  jz      short loc_14008BAF5
0x14008bad2  mov     eax, [rcx+2Ch]
0x14008bad5  test    r12b, al
0x14008bad8  jz      short loc_14008BAF5
0x14008bada  cmp     [rcx+29h], r15b
0x14008bade  jb      short loc_14008BAF5
0x14008bae0  mov     rcx, [rcx+18h]
0x14008bae4  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14008baeb  mov     edx, 0CAh
0x14008baf0  call    WPP_SF_
0x14008baf5  or      qword ptr [rdi+2820h], 8
0x14008bafd  lea     rsi, [rdi+2828h]
0x14008bb04  mov     r8, rsi
0x14008bb07  lea     rdx, aWcososmainleve; "WcosOsMainLevel"
0x14008bb0e  call    FveTestGetDwordOverride
0x14008bb13  test    al, al
0x14008bb15  jz      short loc_14008BB5A
0x14008bb17  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bb1e  cmp     rcx, r13
0x14008bb21  jz      loc_14008BBFA
0x14008bb27  mov     eax, [rcx+2Ch]
0x14008bb2a  test    r12b, al
0x14008bb2d  jz      loc_14008BBFA
0x14008bb33  cmp     [rcx+29h], r15b
0x14008bb37  jb      loc_14008BBFA
0x14008bb3d  mov     r9d, [rsi]
0x14008bb40  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14008bb47  mov     rcx, [rcx+18h]
0x14008bb4b  mov     edx, 0CBh
0x14008bb50  call    WPP_SF_d
0x14008bb55  jmp     loc_14008BBFA
0x14008bb5a  lea     rax, [rsp+340h+var_2D0]
0x14008bb5f  mov     [rsp+340h+var_2D0], r15d
0x14008bb64  mov     r9d, r15d
0x14008bb67  mov     [rsp+340h+var_320], rax
0x14008bb6c  mov     r8, rsi
0x14008bb6f  lea     rdx, [rsp+340h+var_2CC]
0x14008bb74  lea     rcx, [rbp+240h+var_2B8]
0x14008bb78  call    cs:__imp_ZwQueryLicenseValue
0x14008bb7f  nop     dword ptr [rax+rax+00h]
0x14008bb84  mov     ebx, eax
0x14008bb86  cmp     eax, 0C000003Eh
0x14008bb8b  jnz     short loc_14008BBB4
0x14008bb8d  mov     [rsi], r14d
0x14008bb90  mov     ebx, r14d
0x14008bb93  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bb9a  cmp     rcx, r13
0x14008bb9d  jz      short loc_14008BBFA
0x14008bb9f  mov     eax, [rcx+2Ch]
0x14008bba2  test    r12b, al
0x14008bba5  jz      short loc_14008BBFA
0x14008bba7  cmp     byte ptr [rcx+29h], 3
0x14008bbab  jb      short loc_14008BBFA
0x14008bbad  mov     edx, 0CCh
0x14008bbb2  jmp     short loc_14008BBE0
0x14008bbb4  cmp     eax, 0C0000034h
0x14008bbb9  jnz     short loc_14008BBF2
0x14008bbbb  mov     [rsi], r14d
0x14008bbbe  mov     ebx, r14d
0x14008bbc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bbc8  cmp     rcx, r13
0x14008bbcb  jz      short loc_14008BBFA
0x14008bbcd  mov     eax, [rcx+2Ch]
0x14008bbd0  test    r12b, al
0x14008bbd3  jz      short loc_14008BBFA
0x14008bbd5  cmp     byte ptr [rcx+29h], 3
0x14008bbd9  jb      short loc_14008BBFA
0x14008bbdb  mov     edx, 0CDh
0x14008bbe0  mov     rcx, [rcx+18h]
0x14008bbe4  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14008bbeb  call    WPP_SF_
0x14008bbf0  jmp     short loc_14008BBFA
0x14008bbf2  test    eax, eax
0x14008bbf4  js      loc_14008C8F1
0x14008bbfa  lea     rsi, [rdi+282Ch]
0x14008bc01  mov     r8, rsi
0x14008bc04  lea     rdx, aWcosbsplevel; "WcosBspLevel"
0x14008bc0b  call    FveTestGetDwordOverride
0x14008bc10  test    al, al
0x14008bc12  jz      short loc_14008BC57
0x14008bc14  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bc1b  cmp     rcx, r13
0x14008bc1e  jz      loc_14008BCF7
0x14008bc24  mov     eax, [rcx+2Ch]
0x14008bc27  test    r12b, al
0x14008bc2a  jz      loc_14008BCF7
0x14008bc30  cmp     [rcx+29h], r15b
0x14008bc34  jb      loc_14008BCF7
0x14008bc3a  mov     r9d, [rsi]
0x14008bc3d  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14008bc44  mov     rcx, [rcx+18h]
0x14008bc48  mov     edx, 0CEh
0x14008bc4d  call    WPP_SF_d
0x14008bc52  jmp     loc_14008BCF7
0x14008bc57  lea     rax, [rsp+340h+var_2D0]
0x14008bc5c  mov     [rsp+340h+var_2D0], r15d
0x14008bc61  mov     r9d, r15d
0x14008bc64  mov     [rsp+340h+var_320], rax
0x14008bc69  mov     r8, rsi
0x14008bc6c  lea     rdx, [rsp+340h+var_2CC]
0x14008bc71  lea     rcx, [rbp+240h+var_2A8]
0x14008bc75  call    cs:__imp_ZwQueryLicenseValue
0x14008bc7c  nop     dword ptr [rax+rax+00h]
0x14008bc81  mov     ebx, eax
0x14008bc83  cmp     eax, 0C000003Eh
0x14008bc88  jnz     short loc_14008BCB1
0x14008bc8a  mov     [rsi], r14d
0x14008bc8d  mov     ebx, r14d
0x14008bc90  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bc97  cmp     rcx, r13
0x14008bc9a  jz      short loc_14008BCF7
0x14008bc9c  mov     eax, [rcx+2Ch]
0x14008bc9f  test    r12b, al
0x14008bca2  jz      short loc_14008BCF7
0x14008bca4  cmp     byte ptr [rcx+29h], 3
0x14008bca8  jb      short loc_14008BCF7
0x14008bcaa  mov     edx, 0CFh
0x14008bcaf  jmp     short loc_14008BCDD
0x14008bcb1  cmp     eax, 0C0000034h
0x14008bcb6  jnz     short loc_14008BCEF
0x14008bcb8  mov     [rsi], r14d
0x14008bcbb  mov     ebx, r14d
0x14008bcbe  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bcc5  cmp     rcx, r13
0x14008bcc8  jz      short loc_14008BCF7
0x14008bcca  mov     eax, [rcx+2Ch]
0x14008bccd  test    r12b, al
0x14008bcd0  jz      short loc_14008BCF7
0x14008bcd2  cmp     byte ptr [rcx+29h], 3
0x14008bcd6  jb      short loc_14008BCF7
0x14008bcd8  mov     edx, 0D0h
0x14008bcdd  mov     rcx, [rcx+18h]
0x14008bce1  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14008bce8  call    WPP_SF_
0x14008bced  jmp     short loc_14008BCF7
0x14008bcef  test    eax, eax
0x14008bcf1  js      loc_14008C8F1
0x14008bcf7  lea     rsi, [rdi+2830h]
0x14008bcfe  mov     r8, rsi
0x14008bd01  lea     rdx, aWcosdpplevel; "WcosDppLevel"
0x14008bd08  call    FveTestGetDwordOverride
0x14008bd0d  test    al, al
0x14008bd0f  jz      short loc_14008BD54
0x14008bd11  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bd18  cmp     rcx, r13
0x14008bd1b  jz      loc_14008BDF4
0x14008bd21  mov     eax, [rcx+2Ch]
  ... truncated ...
```
