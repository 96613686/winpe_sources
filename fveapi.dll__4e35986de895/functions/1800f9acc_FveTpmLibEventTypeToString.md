# FveTpmLibEventTypeToString

- ea: `0x1800f9acc`
- end: `0x1800fae8e`
- name: `FveTpmLibEventTypeToString`
- size: `5058`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a9284`
- `0x1800aa818`

## callees

- `0x1800f9acc`

## string_xrefs

- `0x1800f9bf1`: `EV_PLATFORM_CONFIG_FLAGS`
- `0x1800f9bdf`: `EV_COMPACT_HASH`
- `0x1800f9bbb`: `EV_NONHOST_CONFIG`
- `0x1800fad2e`: `EV_EFI_VARIABLE_DRIVER_CONFIG`
- `0x1800fad13`: `EV_EFI_BOOT_SERVICES_DRIVER`
- `0x1800fad1c`: `EV_EFI_BOOT_SERVICES_APPLICATION`
- `0x1800fad01`: `EV_EFI_RUNTIME_SERVICES_DRIVER`
- `0x1800fae10`: `EV_EFI_SPDM_FIRMWARE_CONFIG`
- `0x1800f9c66`: `EV_TXT_COMBINED_HASH`
- `0x1800fa73b`: `EVENT_PHYSICALADDRESSEXTENSION`
- `0x1800fa789`: `EVENT_HYPERVISOR_PATH`
- `0x1800fa8cf`: `EVENT_SI_POLICY_UPDATE_SIGNER`
- `0x1800fa983`: `EVENT_VTL1_DUMP_CONFIG`
- `0x1800fa8a2`: `EVENT_LSAISO_CONFIG`
- `0x1800fa936`: `EVENT_REFS_ROLLBACK_PROTECTION_USER_PAYLOAD_HASH`
- `0x1800fa92d`: `SIPAEVENT_REFS_ROLLBACK_PROTECTION_VERIFICATION_SUCCEEDED`
- `0x1800fa93f`: `EVENT_REFS_ROLLBACK_PROTECTION_FROZEN_VOLUME_CHECKSUM`
- `0x1800fa924`: `SIPAEVENT_REFS_ROLLBACK_PROTECTION_VOLUME_FIRST_EVER_MOUNT`
- `0x1800fa9e4`: `EVENT_FILEPATH`
- `0x1800fab47`: `EVENT_ELAM_CONFIGURATION`
- `0x1800f9ea8`: `EV_AMD_MP2_CONFIG`
- `0x1800fa218`: `EV_AMD_PSP_SPIROM_CONFIG`

## pseudocode

```c
const wchar_t *__fastcall FveTpmLibEventTypeToString(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  const wchar_t *result; // rax
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  unsigned int v82; // ecx
  unsigned int v83; // ecx
  unsigned int v84; // ecx
  unsigned int v85; // ecx
  unsigned int v86; // ecx
  unsigned int v87; // ecx
  unsigned int v88; // ecx
  unsigned int v89; // ecx
  unsigned int v90; // ecx
  unsigned int v91; // ecx
  unsigned int v92; // ecx
  unsigned int v93; // ecx
  unsigned int v94; // ecx
  unsigned int v95; // ecx
  unsigned int v96; // ecx
  unsigned int v97; // ecx
  unsigned int v98; // ecx
  unsigned int v99; // ecx
  unsigned int v100; // ecx
  unsigned int v101; // ecx
  unsigned int v102; // ecx
  unsigned int v103; // ecx
  unsigned int v104; // ecx
  unsigned int v105; // ecx
  unsigned int v106; // ecx
  unsigned int v107; // ecx
  unsigned int v108; // ecx
  unsigned int v109; // ecx
  unsigned int v110; // ecx
  unsigned int v111; // ecx
  unsigned int v112; // ecx
  unsigned int v113; // ecx
  unsigned int v114; // ecx
  unsigned int v115; // ecx
  unsigned int v116; // ecx
  unsigned int v117; // ecx
  unsigned int v118; // ecx
  unsigned int v119; // ecx
  unsigned int v120; // ecx
  unsigned int v121; // ecx
  unsigned int v122; // ecx
  unsigned int v123; // ecx
  unsigned int v124; // ecx
  unsigned int v125; // ecx
  unsigned int v126; // ecx
  unsigned int v127; // ecx
  unsigned int v128; // ecx
  unsigned int v129; // ecx
  unsigned int v130; // ecx
  unsigned int v131; // ecx
  unsigned int v132; // ecx
  unsigned int v133; // ecx
  unsigned int v134; // ecx
  unsigned int v135; // ecx
  unsigned int v136; // ecx
  unsigned int v137; // ecx
  unsigned int v138; // ecx
  unsigned int v139; // ecx
  const wchar_t *v140; // rax
  bool v141; // zf
  const wchar_t *v142; // rdx

  if ( a1 <= 0x400 )
  {
    if ( a1 == 1024 )
      return L"EV_TXT_EVENT_BASE";
    if ( a1 > 9 )
    {
      v9 = a1 - 10;
      if ( !v9 )
        return L"EV_PLATFORM_CONFIG_FLAGS";
      v10 = v9 - 1;
      if ( !v10 )
        return L"EV_TABLE_OF_DEVICES";
      v11 = v10 - 1;
      if ( !v11 )
        return L"EV_COMPACT_HASH";
      v12 = v11 - 1;
      if ( !v12 )
        return L"EV_IPL";
      v13 = v12 - 1;
      if ( !v13 )
        return L"EV_IPL_PARTITION_DATA";
      v14 = v13 - 1;
      if ( !v14 )
        return L"EV_NONHOST_CODE";
      v15 = v14 - 1;
      if ( !v15 )
        return L"EV_NONHOST_CONFIG";
      v16 = v15 - 1;
      if ( !v16 )
        return L"EV_NONHOST_INFO";
      if ( v16 == 1 )
        return L"EV_OMIT_BOOT_DEVICE_EVENTS";
    }
    else
    {
      if ( a1 == 9 )
        return L"EV_CPU_MICROCODE";
      if ( !a1 )
        return L"EV_PREBOOT_CERT";
      v1 = a1 - 1;
      if ( !v1 )
        return L"EV_POST_CODE";
      v2 = v1 - 1;
      if ( !v2 )
        return L"EV_UNUSED";
      v3 = v2 - 1;
      if ( !v3 )
        return L"EV_NO_ACTION";
      v4 = v3 - 1;
      if ( !v4 )
        return L"EV_SEPARATOR";
      v5 = v4 - 1;
      if ( !v5 )
        return L"EV_ACTION";
      v6 = v5 - 1;
      if ( !v6 )
        return L"EV_EVENT_TAG";
      v7 = v6 - 1;
      if ( !v7 )
        return L"EV_S_CRTM_CONTENTS";
      if ( v7 == 1 )
        return L"EV_S_CRTM_VERSION";
    }
    return L"UNDEFINED";
  }
  if ( a1 <= 0x4FE )
  {
    if ( a1 == 1278 )
      return L"EV_TXT_RANDOM_VALUE";
    if ( a1 > 0x410 )
    {
      if ( a1 > 0x416 )
      {
        v28 = a1 - 1047;
        if ( !v28 )
          return L"EV_TXT_BPM_HASH";
        v29 = v28 - 1;
        if ( !v29 )
          return L"EV_TXT_KM_INFO_HASH";
        v30 = v29 - 1;
        if ( !v30 )
          return L"EV_TXT_BPM_INFO_HASH";
        if ( v30 == 1 )
          return L"EV_TXT_BOOT_POL_HASH";
      }
      else
      {
        if ( a1 == 1046 )
          return L"EV_TXT_KM_HASH";
        v24 = a1 - 1041;
        if ( !v24 )
          return L"EV_TXT_LCP_HASH";
        v25 = v24 - 1;
        if ( !v25 )
          return L"EV_TXT_LCP_DETAILS_HASH";
        v26 = v25 - 1;
        if ( !v26 )
          return L"EV_TXT_LCP_AUTHORITIES_HASH";
        v27 = v26 - 1;
        if ( !v27 )
          return L"EV_TXT_NV_INFO_HASH";
        if ( v27 == 1 )
          return L"EV_TXT_COLD_BOOT_BIOS_HASH";
      }
    }
    else
    {
      if ( a1 == 1040 )
        return L"EV_TXT_SINIT_PUBKEY_HASH";
      if ( a1 > 0x40B )
      {
        v21 = a1 - 1036;
        if ( !v21 )
          return L"EV_TXT_LCP_CONTROL_HASH";
        v22 = v21 - 1;
        if ( !v22 )
          return L"EV_TXT_ELEMENTS_HASH";
        v23 = v22 - 1;
        if ( !v23 )
          return L"EV_TXT_STM_HASH";
        if ( v23 == 1 )
          return L"EV_TXT_OSSINITDATA_CAP_HASH";
      }
      else
      {
        if ( a1 == 1035 )
          return L"EV_TXT_CPU_SCRTM_STAT";
        v17 = a1 - 1025;
        if ( !v17 )
          return L"EV_TXT_PCR_MAPPING";
        v18 = v17 - 1;
        if ( !v18 )
          return L"EV_TXT_HASH_START";
        v19 = v18 - 1;
        if ( !v19 )
          return L"EV_TXT_COMBINED_HASH";
        v20 = v19 - 1;
        if ( !v20 )
          return L"EV_TXT_MLE_HASH";
        if ( v20 == 6 )
          return L"EV_TXT_BIOSAC_REG_DATA";
      }
    }
    return L"UNDEFINED";
  }
  if ( a1 > 0x8302 )
  {
    if ( a1 <= 0x83FF )
    {
      if ( a1 == 33791 )
        return L"EV_AMD_PSP_END";
      if ( a1 > 0x8309 )
      {
        v53 = a1 - 33546;
        if ( !v53 )
          return L"EV_AMD_DRV_ASD";
        v54 = v53 - 1;
        if ( !v54 )
          return L"EV_AMD_DRV_MFD";
        v55 = v54 - 1;
        if ( !v55 )
          return L"EV_AMD_DRV_FHP";
        v56 = v55 - 1;
        if ( !v56 )
          return L"EV_AMD_DRV_SPDM";
        v57 = v56 - 1;
        if ( !v57 )
          return L"EV_AMD_DRV_PLAT";
        if ( v57 == 1 )
          return L"EV_AMD_DRV_IPKEYMGR";
      }
      else
      {
        if ( a1 == 33545 )
          return L"EV_AMD_DRV_RAS";
        v48 = a1 - 33539;
        if ( !v48 )
          return L"EV_AMD_PSP_SOC_DRIVER";
        v49 = v48 - 1;
        if ( !v49 )
          return L"EV_AMD_PSP_HAD_DRIVER";
        v50 = v49 - 1;
        if ( !v50 )
          return L"EV_AMD_PSP_BOOT_DRIVER";
        v51 = v50 - 1;
        if ( !v51 )
          return L"EV_AMD_PSP_INTERFACE_DRIVER";
        v52 = v51 - 1;
        if ( !v52 )
          return L"EV_AMD_PSP_SFDR_DRIVER";
        if ( v52 == 1 )
          return L"EV_AMD_DRV_SEV";
      }
      return L"UNDEFINED";
    }
    if ( a1 <= 0x70001 )
    {
      if ( a1 == 458753 )
        return L"EVENT_FILEPATH";
      if ( a1 > 0x5000F )
      {
        if ( a1 > 0x50032 )
        {
          if ( a1 > 0x60000 )
          {
            v108 = a1 - 393217;
            if ( !v108 )
              return L"EVENT_NOAUTHORITY";
            v109 = v108 - 1;
            if ( !v109 )
              return L"EVENT_AUTHORITYPUBKEY";
            if ( v109 == 65534 )
              return L"TYPE_LOADEDMODULE";
          }
          else
          {
            if ( a1 == 393216 )
              return L"TYPE_AUTHORITY";
            if ( a1 > 0x50039 )
            {
              v104 = a1 - 327738;
              if ( !v104 )
                return L"EVENT_VSM_SEALED_SI_POLICY";
              v105 = v104 - 1;
              if ( !v105 )
                return L"EVENT_VSM_DRTM_KEYROLL_DETECTED";
              v106 = v105 - 3;
              if ( !v106 )
                return L"SIPAEVENT_REFS_ATTESTATION_SUMMARY";
              v107 = v106 - 2;
              if ( !v107 )
                return L"EVENT_VTL1_DUMP_CONFIG";
              if ( v107 == 1 )
                return L"EVENT_SECUREKERNEL_DEBUG";
            }
            else
            {
              if ( a1 == 327737 )
                return L"EVENT_SI_POLICY_SUPPLEMENTAL_POLICY";
              v99 = a1 - 327731;
              if ( !v99 )
                return L"EVENT_REFS_VOLUME_CHECKPOINT_RECORD_CHECKSUM";
              v100 = v99 - 1;
              if ( !v100 )
                return L"EVENT_REFS_ROLLBACK_PROTECTION_FROZEN_VOLUME_CHECKSUM";
              v101 = v100 - 1;
              if ( !v101 )
                return L"EVENT_REFS_ROLLBACK_PROTECTION_USER_PAYLOAD_HASH";
              v102 = v101 - 1;
              if ( !v102 )
                return L"SIPAEVENT_REFS_ROLLBACK_PROTECTION_VERIFICATION_SUCCEEDED";
              v103 = v102 - 1;
              if ( !v103 )
                return L"SIPAEVENT_REFS_ROLLBACK_PROTECTION_VOLUME_FIRST_EVER_MOUNT";
              if ( v103 == 1 )
                return L"EVENT_SI_POLICY_SUPPLEMENTAL_SIGNER";
            }
          }
        }
        else
        {
          if ( a1 == 327730 )
            return L"EVENT_SI_POLICY_UPDATE_SIGNER";
          if ( a1 > 0x50023 )
          {
            v92 = a1 - 327716;
            if ( !v92 )
              return L"EVENT_HIBERNATION_DISABLED";
            v93 = v92 - 1;
            if ( !v93 )
              return L"EVENT_DUMPS_DISABLED";
            v94 = v93 - 1;
            if ( !v94 )
              return L"EVENT_DUMP_ENCRYPTION_ENABLED";
            v95 = v94 - 1;
            if ( !v95 )
              return L"EVENT_DUMP_ENCRYPTION_KEY_DIGEST";
            v96 = v95 - 1;
            if ( !v96 )
              return L"EVENT_LSAISO_CONFIG";
            v97 = v96 - 1;
            if ( !v97 )
              return L"EVENT_SBCP_INFO";
            v98 = v97 - 7;
            if ( !v98 )
              return L"EVENT_HYPERVISOR_BOOT_DMA_PROTECTION";
            if ( v98 == 1 )
              return L"EVENT_SI_POLICY_SIGNER";
          }
          else
          {
            if ( a1 == 327715 )
              return L"EVENT_VSM_IDKS_INFO";
            v85 = a1 - 327696;
            if ( !v85 )
              return L"EVENT_HYPERVISOR_MMIO_NX_POLICY";
            v86 = v85 - 1;
            if ( !v86 )
              return L"EVENT_HYPERVISOR_MSR_FILTER_POLICY";
            v87 = v86 - 1;
            if ( !v87 )
              return L"EVENT_VSM_LAUNCH_TYPE";
            v88 = v87 - 1;
            if ( !v88 )
              return L"EVENT_OS_REVOCATION_LIST";
            v89 = v88 - 1;
            if ( !v89 )
              return L"EVENT_SMT_STATUS";
            v90 = v89 - 12;
            if ( !v90 )
              return L"EVENT_VSM_IDK_INFO";
            v91 = v90 - 1;
            if ( !v91 )
              return L"EVENT_FLIGHTSIGNING";
            if ( v91 == 1 )
              return L"EVENT_PAGEFILE_ENCRYPTION_ENABLED";
          }
        }
      }
      else
      {
        if ( a1 == 327695 )
          return L"EVENT_SI_POLICY";
        if ( a1 > 0x40001 )
        {
          if ( a1 > 0x50007 )
          {
            v79 = a1 - 327688;
            if ( !v79 )
              return L"EVENT_OSDEVICE";
            v80 = v79 - 1;
            if ( !v80 )
              return L"EVENT_SYSTEMROOT";
            v81 = v80 - 1;
            if ( !v81 )
              return L"EVENT_HYPERVISOR_LAUNCH_TYPE";
            v82 = v81 - 1;
            if ( !v82 )
              return L"EVENT_HYPERVISOR_PATH";
            v83 = v82 - 1;
            if ( !v83 )
              return L"EVENT_HYPERVISOR_IOMMU_POLICY";
            v84 = v83 - 1;
            if ( !v84 )
              return L"EVENT_HYPERVISOR_DEBUG";
            if ( v84 == 1 )
              return L"EVENT_DRIVER_LOAD_POLICY";
          }
          else
          {
            if ( a1 == 327687 )
              return L"EVENT_PHYSICALADDRESSEXTENSION";
            v72 = a1 - 262146;
            if ( !v72 )
              return L"EVENT_BOOT_REVOCATION_LIST ";
            v73 = v72 - 65534;
            if ( !v73 )
              return L"TYPE_OSPARAMETER";
            v74 = v73 - 1;
            if ( !v74 )
              return L"EVENT_OSKERNELDEBUG ";
            v75 = v74 - 1;
            if ( !v75 )
              return L"EVENT_CODEINTEGRITY ";
            v76 = v75 - 1;
            if ( !v76 )
              return L"EVENT_TESTSIGNING";
            v77 = v76 - 1;
            if ( !v77 )
              return L"EVENT_DATAEXECUTIONPREVENTION";
            v78 = v77 - 1;
            if ( !v78 )
              return L"EVENT_SAFEMODE";
            if ( v78 == 1 )
              return L"EVENT_WINPE";
          }
        }
        else
        {
          if ( a1 == 262145 )
            return L"EVENT_BOOTDEBUGGING ";
          if ( a1 > 0x20007 )
          {
            v65 = a1 - 131080;
            if ( !v65 )
              return L"EVENT_MORBIT_NOT_CANCELABLE ";
            v66 = v65 - 1;
            if ( !v66 )
              return L"EVENT_APPLICATION_SVN ";
            v67 = v66 - 1;
            if ( !v67 )
              return L"EVENT_SVN_CHAIN_STATUS ";
            v68 = v67 - 1;
            if ( !v68 )
              return L"EVENT_MORBIT_API_STATUS ";
            v69 = v68 - 65525;
            if ( !v69 )
              return L"TYPE_ERROR";
            v70 = v69 - 1;
            if ( !v70 )
              return L"ERROR_FIRMWAREFAILURE";
            v71 = v70 - 2;
            if ( !v71 )
              return L"ERROR_INTERNALFAILURE";
            if ( v71 == 65533 )
              return L"TYPE_PREOSPARAMETER";
          }
          else
          {
            if ( a1 == 131079 )
              return L"EVENT_COUNTERID";
            v58 = a1 - 0x10000;
            if ( !v58 )
              return L"TYPE_CONTAINER";
            v59 = v58 - 0x10000;
            if ( !v59 )
              return L"TYPE_INFORMATION";
            v60 = v59 - 1;
            if ( !v60 )
              return L"EVENT_INFORMATION";
            v61 = v60 - 1;
            if ( !v61 )
              return L"EVENT_BOOTCOUNTER";
            v62 = v61 - 1;
            if ( !v62 )
              return L"EVENT_TRANSFER_CONTROL";
            v63 = v62 - 1;
            if ( !v63 )
              return L"EVENT_APPLICATION_return L";
            v64 = v63 - 1;
            if ( !v64 )
              return L"EVENT_BITLOCKER_UNLOCK";
            if ( v64 == 1 )
              return L"EVENT_EVENTCOUNTER";
          }
        }
      }
      return L"UNDEFINED";
    }
    if ( a1 <= 0x80000 )
    {
      if ( a1 == 0x80000 )
        return L"TYPE_TRUSTPOINT";
      if ( a1 > 0x70008 )
      {
        v115 = a1 - 458761;
        if ( !v115 )
          return L"EVENT_AUTHORITYSHA1THUMBPRINT";
        v116 = v115 - 1;
        if ( !v116 )
          return L"EVENT_IMAGEVALIDATED ";
        v117 = v116 - 1;
        if ( !v117 )
          return L"EVENT_MODULE_SVN";
        v118 = v117 - 2;
        if ( !v118 )
          return L"EVENT_MODULE_ORIGINAL_FILENAME";
        v119 = v118 - 1;
        if ( !v119 )
          return L"EVENT_MODULE_VERSION";
        if ( v119 == 1 )
          return L"EVENT_PUBLISHER_OEMNAME";
      }
      else
      {
        if ( a1 == 458760 )
          return L"EVENT_AUTHORITYPUBLISHER";
        v110 = a1 - 458754;
        if ( !v110 )
          return L"EVENT_IMAGESIZE";
        v111 = v110 - 1;
        if ( !v111 )
          return L"EVENT_HASHALGORITHMID";
        v112 = v111 - 1;
        if ( !v112 )
          return L"EVENT_AUTHENTICODEHASH";
        v113 = v112 - 1;
        if ( !v113 )
          return L"EVENT_AUTHORITYISSUER";
        v114 = v113 - 1;
        if ( !v114 )
          return L"EVENT_AUTHORITYSERIAL";
        if ( v114 == 1 )
          return L"EVENT_IMAGEBASE";
      }
      return L"UNDEFINED";
    }
    if ( a1 > 0x40010005 )
    {
      if ( a1 > 0x80000010 )
      {
        if ( a1 > 0x80080001 )
        {
          switch ( a1 )
          {
            case 0x80080002:
              return L"EVENT_QUOTESIGNATURE";
            case 0x80080003:
              return L"EVENT_AIKID";
            case 0x80080004:
              return L"EVENT_AIKPUBDIGEST";
            case 0xC0010004:
              return L"EVENT_TRUSTPOINT_AGGREGATION";
          }
          result = L"FVE_EVENT_TYPE_NOT_AVAILABLE";
          if ( a1 != -1 )
            return L"UNDEFINED";
          return result;
        }
        switch ( a1 )
        {
          case 0x80080001:
            return L"EVENT_QUOTE";
          case 0x800000E0:
            return L"EV_EFI_VARIABLE_AUTHORITY";
          case 0x800000E1:
            return L"EV_EFI_SPDM_FIRMWARE_BLOB";
          case 0x800000E2:
            return L"EV_EFI_SPDM_FIRMWARE_CONFIG";
          case 0x80030002:
            return L"ERROR_TPMFAILURE";
        }
        v140 = L"ERROR_KSRFAILURE";
        v141 = a1 == -2147287036;
      }
      else
      {
        if ( a1 == -2147483632 )
          return L"EV_EFI_HCRTM_EVENT";
        if ( a1 > 0x80000006 )
        {
          switch ( a1 )
          {
            case 0x80000007:
              return L"EV_EFI_ACTION";
            case 0x80000008:
              return L"EV_EFI_PLATFORM_FIRMWARE_BLOB";
            case 0x80000009:
              return L"EV_EFI_HANDOFF_TABLES";
            case 0x8000000A:
              return L"EV_EFI_PLATFORM_FIRMWARE_BLOB2";
            case 0x8000000B:
              return L"EV_EFI_HANDOFF_TABLES2";
          }
          v140 = L"EV_EFI_VARIABLE_BOOT2";
          v141 = a1 == -2147483636;
        }
        else
        {
          switch ( a1 )
          {
            case 0x80000006:
              return L"EV_EFI_GPT_EVENT";
            case 0x40010006u:
              return L"EVENT_KSR_SIGNED_MEASUREMENT_AGGREGATION";
            case 0x80000000:
              return L"TYPE_NONMEASURED";
            case 0x80000001:
              return L"EV_EFI_VARIABLE_DRIVER_CONFIG";
            case 0x80000002:
              return L"EV_EFI_VARIABLE_BOOT";
            case 0x80000003:
              return L"EV_EFI_BOOT_SERVICES_APPLICATION";
            case 0x80000004:
              return L"EV_EFI_BOOT_SERVICES_DRIVER";
          }
          v140 = L"EV_EFI_RUNTIME_SERVICES_DRIVER";
          v141 = a1 == -2147483643;
        }
      }
      v142 = L"UNDEFINED";
      if ( v141 )
        return v140;
      return v142;
    }
    if ( a1 == 1073807365 )
    {
      return L"EVENT_KSR_AGGREGATION";
    }
    else
    {
      if ( a1 <= 0xA0008 )
      {
        if ( a1 == 655368 )
          return L"EVENT_VBS_MICROSOFT_BOOT_CHAIN_REQUIRED";
        if ( a1 > 0xA0001 )
        {
          v125 = a1 - 655362;
          if ( !v125 )
            return L"EVENT_VBS_SECUREBOOT_REQUIRED";
          v126 = v125 - 1;
          if ( !v126 )
            return L"EVENT_VBS_IOMMU_REQUIRED";
          v127 = v126 - 1;
          if ( !v127 )
            return L"EVENT_VBS_MMIO_NX_REQUIRED";
          v128 = v127 - 1;
          if ( !v128 )
            return L"EVENT_VBS_MSR_FILTERING_REQUIRED";
          v129 = v128 - 1;
          if ( !v129 )
            return L"EVENT_VBS_MANDATORY_ENFORCEMENT";
          if ( v129 == 1 )
            return L"EVENT_VBS_HVCI_POLICY";
        }
        else
        {
          if ( a1 == 655361 )
            return L"EVENT_VBS_VSM_REQUIRED";
          v120 = a1 - 589824;
          if ( !v120 )
            return L"TYPE_ELAM";
          v121 = v120 - 1;
          if ( !v121 )
            return L"EVENT_ELAM_KEYNAME";
          v122 = v121 - 1;
          if ( !v122 )
            return L"EVENT_ELAM_CONFIGURATION";
          v123 = v122 - 1;
          if ( !v123 )
            return L"EVENT_ELAM_POLICY";
          v124 = v123 - 1;
          if ( !v124 )
            return L"EVENT_ELAM_MEASURED";
          if ( v124 == 65532 )
            return L"TYPE_VBS";
        }
        return L"UNDEFINED";
      }
      if ( a1 <= 0xC0002 )
      {
        if ( a1 == 786434 )
          return L"EVENT_DRTM_SMM";
        v130 = a1 - 655369;
        if ( !v130 )
          return L"EVENT_VBS_DUMP_USES_AMEROOT";
        v131 = v130 - 1;
        if ( !v131 )
          return L"EVENT_VBS_VSM_NOSECRETS_ENFORCED";
        v132 = v131 - 65526;
        if ( !v132 )
          return L"TYPE_KSR";
        v133 = v132 - 1;
        if ( !v133 )
          return L"EVENT_KSR_SIGNATURE";
        v134 = v133 - 0xFFFF;
        if ( !v134 )
          return L"TYPE_DRTM";
        if ( v134 == 1 )
          return L"EVENT_DRTM_STATE_AUTH";
        return L"UNDEFINED";
      }
      v135 = a1 - 786435;
      if ( v135 )
      {
        v136 = v135 - 1;
        if ( v136 )
        {
          v137 = v136 - 1072955388;
          if ( v137 )
          {
            v138 = v137 - 65537;
            if ( v138 )
            {
              v139 = v138 - 1;
              if ( v139 )
              {
                if ( v139 != 1 )
                  return L"UNDEFINED";
                return L"EVENT_LOADEDMODULE_AGGREGATION";
              }
              else
              {
                return L"EVENT_ELAM_AGGREGATION";
              }
            }
            else
            {
              return L"EVENT_TRUSTBOUNDARY";
            }
          }
          else
          {
            return L"TYPE_AGGREGATION";
          }
        }
        else
        {
          return L"EVENT_DRTM_AMD_SMM_SIGNER_KEY";
        }
      }
      else
      {
        return L"EVENT_DRTM_AMD_SMM_HASH";
      }
    }
  }
  else
  {
    if ( a1 == 33538 )
      return L"EV_AMD_AGESA_DRV";
    if ( a1 > 0x8243 )
    {
      if ( a1 > 0x826A )
      {
        if ( a1 > 0x82FF )
        {
          v47 = a1 - 33536;
          if ( !v47 )
            return L"EV_AMD_FTPM_DRV";
          if ( v47 == 1 )
            return L"EV_AMD_DRTM_DRV";
          return L"UNDEFINED";
        }
        if ( a1 == 33535 )
        {
          return L"EV_AMD_PSP_BL_END";
        }
        else
        {
          switch ( a1 )
          {
            case 0x826Bu:
              result = L"EV_AMD_PMU3_DATA";
              break;
            case 0x826Cu:
              result = L"EV_AMD_PMU4_DATA";
              break;
            case 0x826Du:
              result = L"EV_AMD_PMU5_DATA";
              break;
            case 0x826Eu:
              result = L"EV_AMD_PMU6_DATA";
              break;
            case 0x826Fu:
              result = L"EV_AMD_PMU7_DATA";
              break;
            case 0x8270u:
              result = L"EV_AMD_PMU8_DATA";
              break;
            case 0x8271u:
              result = L"EV_AMD_PMU9_DATA";
              break;
            case 0x8272u:
              result = L"EV_AMD_PMU10_DATA";
              break;
            case 0x8273u:
              result = L"EV_AMD_PMU11_DATA";
              break;
            case 0x8274u:
              result = L"EV_AMD_PMU12_DATA";
              break;
            case 0x8275u:
              result = L"EV_AMD_PMU13_DATA";
              break;
            case 0x8276u:
              result = L"EV_AMD_PMU14_DATA";
              break;
            case 0x8277u:
              result = L"EV_AMD_PMU15_DATA";
              break;
            case 0x8278u:
              result = L"EV_AMD_PMU3";
              break;
            case 0x8279u:
              result = L"EV_AMD_PMU4";
              break;
            case 0x827Au:
              result = L"EV_AMD_PMU5";
              break;
            case 0x827Bu:
              result = L"EV_AMD_PMU6";
              break;
            case 0x827Cu:
              result = L"EV_AMD_PMU7";
              break;
            case 0x827Du:
              result = L"EV_AMD_PMU8";
              break;
            case 0x827Eu:
              result = L"EV_AMD_PMU9";
              break;
            case 0x827Fu:
              result = L"EV_AMD_PMU10";
              break;
            case 0x8280u:
              result = L"EV_AMD_PMU11";
              break;
            case 0x8281u:
              result = L"EV_AMD_PMU12";
              break;
            case 0x8282u:
              result = L"EV_AMD_PMU13";
              break;
            case 0x8283u:
              result = L"EV_AMD_PMU14";
              break;
            case 0x8284u:
              result = L"EV_AMD_PMU15";
              break;
            case 0x8285u:
              result = L"EV_AMD_MINIZSC_MSMU";
              break;
            case 0x8286u:
              result = L"EV_AMD_DMCU_ERAM";
              break;
            case 0x8287u:
              result = L"EV_AMD_DMCU_ISR";
              break;
            case 0x8288u:
              result = L"EV_AMD_DMUB_ERAM";
              break;
            case 0x8289u:
              result = L"EV_AMD_DMUB_ISR";
              break;
            case 0x828Au:
              result = L"EV_AMD_UZSC_MSMU";
              break;
            case 0x828Bu:
              result = L"EV_AMD_MINIZSC_MSMU_1";
              break;
            case 0x828Cu:
              result = L"EV_AMD_S3_IMAGE";
              break;
            default:
              return L"UNDEFINED";
          }
        }
      }
      else if ( a1 == 33386 )
      {
        return L"EV_AMD_MPIO_C20_PHY_FW";
      }
      else
      {
        switch ( a1 )
        {
          case 0x8244u:
            result = L"EV_AMD_VBL_9";
            break;
          case 0x8245u:
            result = L"EV_AMD_VBL_10";
            break;
          case 0x8246u:
            result = L"EV_AMD_PSP_L1_SEC_POL";
            break;
          case 0x8247u:
            result = L"EV_AMD_IP_DISCOVERY";
            break;
          case 0x8248u:
            result = L"EV_AMD_SYS_DRV";
            break;
          case 0x8249u:
            result = L"EV_AMD_TOS";
            break;
          case 0x824Au:
            result = L"EV_AMD_PSP_TOS_KEYDB";
            break;
          case 0x824Bu:
            result = L"EV_AMD_ABL_TOC";
            break;
          case 0x824Cu:
            result = L"EV_AMD_PMU1_DATA";
            break;
          case 0x824Du:
            result = L"EV_AMD_PMU2_DATA";
            break;
          case 0x824Eu:
            result = L"EV_AMD_PMU1";
            break;
          case 0x824Fu:
            result = L"EV_AMD_PMU2";
            break;
          case 0x8250u:
            result = L"EV_AMD_MPIO_FW";
            break;
          case 0x8251u:
            result = L"EV_AMD_MP5";
            break;
          case 0x8252u:
            result = L"EV_AMD_MPCCX";
            break;
          case 0x8253u:
            result = L"EV_AMD_GMI3";
            break;
          case 0x8254u:
            result = L"EV_AMD_TPMLITE";
            break;
          case 0x8255u:
            result = L"EV_AMD_PSP_SPIROM_CONFIG";
            break;
          case 0x8256u:
            result = L"EV_AMD_PSP_DF_RIB_TOC";
            break;
          case 0x8257u:
            result = L"EV_AMD_PSP_DF_RIB0";
            break;
          case 0x8258u:
            result = L"EV_AMD_PSP_DF_RIB1";
            break;
          case 0x8259u:
            result = L"EV_AMD_PSP_DF_RIB2";
            break;
          case 0x825Au:
            result = L"EV_AMD_PSP_DF_RIB3";
            break;
          case 0x825Bu:
            result = L"EV_AMD_PSP_DF_RIB4";
            break;
          case 0x825Cu:
            result = L"EV_AMD_PSP_DF_RIB5";
            break;
          case 0x825Du:
            result = L"EV_AMD_PSP_DF_RIB6";
            break;
          case 0x825Eu:
            result = L"EV_AMD_PSP_DF_RIB7";
            break;
          case 0x825Fu:
            result = L"EV_AMD_PSP_DF_RIB8";
            break;
          case 0x8260u:
            result = L"EV_AMD_PSP_DF_RIB9";
            break;
          case 0x8261u:
            result = L"EV_AMD_PSP_DF_RIB10";
            break;
          case 0x8262u:
            result = L"EV_AMD_PSP_DF_RIB11";
            break;
          case 0x8263u:
            result = L"EV_AMD_PSP_DF_RIB12";
            break;
          case 0x8264u:
            result = L"EV_AMD_PSP_DF_RIB13";
            break;
          case 0x8265u:
            result = L"EV_AMD_PSP_DF_RIB14";
            break;
          case 0x8266u:
            result = L"EV_AMD_PSP_DF_RIB15";
            break;
          case 0x8267u:
            result = L"EV_AMD_SECURE_DEBUG_UNLOCK";
            break;
          case 0x8268u:
            result = L"EV_AMD_PROMONTORY_21";
            break;
          case 0x8269u:
            result = L"EV_AMD_MPIO_E32_PHY_FW";
            break;
          default:
            return L"UNDEFINED";
        }
      }
    }
    else
    {
      if ( a1 == 33347 )
        return L"EV_AMD_VBL_8";
      if ( a1 > 0x821D )
      {
        switch ( a1 )
        {
          case 0x821Eu:
            result = L"EV_AMD_ABL_21";
            break;
          case 0x821Fu:
            result = L"EV_AMD_ABL_22";
            break;
          case 0x8220u:
            result = L"EV_AMD_ABL_23";
            break;
          case 0x8221u:
            result = L"EV_AMD_ABL_24";
            break;
          case 0x8222u:
            result = L"EV_AMD_ABL_25";
            break;
          case 0x8223u:
            result = L"EV_AMD_ABL_26";
            break;
          case 0x8224u:
            result = L"EV_AMD_ABL_27";
            break;
          case 0x8225u:
            result = L"EV_AMD_ABL_28";
            break;
          case 0x8226u:
            result = L"EV_AMD_ABL_29";
            break;
          case 0x8227u:
            result = L"EV_AMD_ABL_30";
            break;
          case 0x8228u:
            result = L"EV_AMD_ABL_31";
            break;
          case 0x8229u:
            result = L"EV_AMD_ABL_32";
            break;
          case 0x822Au:
            result = L"EV_AMD_ABL_33";
            break;
          case 0x822Bu:
            result = L"EV_AMD_ABL_34";
            break;
          case 0x822Cu:
            result = L"EV_AMD_ABL_35";
            break;
          case 0x822Du:
            result = L"EV_AMD_ABL_36";
            break;
          case 0x822Eu:
            result = L"EV_AMD_ABL_37";
            break;
          case 0x822Fu:
            result = L"EV_AMD_ABL_38";
            break;
          case 0x8230u:
            result = L"EV_AMD_ABL_39";
            break;
          case 0x8231u:
            result = L"EV_AMD_ABL_40";
            break;
          case 0x8232u:
            result = L"EV_AMD_ABL_41";
            break;
          case 0x8233u:
            result = L"EV_AMD_ABL_42";
            break;
          case 0x8234u:
            result = L"EV_AMD_ABL_43";
            break;
          case 0x8235u:
            result = L"EV_AMD_ABL_44";
            break;
          case 0x8236u:
            result = L"EV_AMD_ABL_45";
            break;
          case 0x8237u:
            result = L"EV_AMD_ABL_46";
            break;
          case 0x8238u:
            result = L"EV_AMD_ABL_47";
            break;
          case 0x8239u:
            result = L"EV_AMD_ABL_48";
            break;
          case 0x823Au:
            result = L"EV_AMD_MID_SMU";
            break;
          case 0x823Bu:
            result = L"EV_AMD_PM_FW1";
            break;
          case 0x823Cu:
            result = L"EV_AMD_VBL_1";
            break;
          case 0x823Du:
            result = L"EV_AMD_VBL_2";
            break;
          case 0x823Eu:
            result = L"EV_AMD_VBL_3";
            break;
          case 0x823Fu:
            result = L"EV_AMD_VBL_4";
            break;
          case 0x8240u:
            result = L"EV_AMD_VBL_5";
            break;
          case 0x8241u:
            result = L"EV_AMD_VBL_6";
            break;
          case 0x8242u:
            result = L"EV_AMD_VBL_7";
            break;
          default:
            return L"UNDEFINED";
        }
      }
      else
      {
        if ( a1 == 33309 )
          return L"EV_AMD_ABL_20";
        if ( a1 <= 0x820A )
        {
          if ( a1 == 33290 )
            return L"EV_AMD_ABL_1";
          if ( a1 > 0x8200 )
          {
            v39 = a1 - 33281;
            if ( !v39 )
              return L"EV_AMD_SPL_TABLE_ROM";
            v40 = v39 - 1;
            if ( !v40 )
              return L"EV_AMD_PSP_BL_STAGE_1";
            v41 = v40 - 1;
            if ( !v41 )
              return L"EV_AMD_PSP_KEYDB";
            v42 = v41 - 1;
            if ( !v42 )
              return L"EV_AMD_SPL_TABLE_FW";
            v43 = v42 - 1;
            if ( !v43 )
              return L"EV_AMD_PSP_BL_STAGE_2";
            v44 = v43 - 1;
            if ( !v44 )
              return L"EV_AMD_PSP_L0_SEC_POL";
            v45 = v44 - 1;
            if ( !v45 )
              return L"EV_AMD_PMFW0";
            v46 = v45 - 1;
            if ( !v46 )
              return L"EV_AMD_MP2_CONFIG";
            if ( v46 == 1 )
              return L"EV_AMD_MP2_FW";
          }
          else
          {
            if ( a1 == 33280 )
              return L"EV_AMD_BASE_2";
            v31 = a1 - 1279;
            if ( !v31 )
              return L"EV_TXT_CAP_VALUE";
            v32 = v31 - 31489;
            if ( !v32 )
              return L"EV_AMD_SL_EVENT_BASE";
            v33 = v32 - 1;
            if ( !v33 )
              return L"EV_AMD_SL_LOAD";
            v34 = v33 - 1;
            if ( !v34 )
              return L"EV_AMD_SL_PSP_FW_SPLT";
            v35 = v34 - 1;
            if ( !v35 )
              return L"EV_AMD_SL_TSME_RB_FUSE";
            v36 = v35 - 1;
            if ( !v36 )
              return L"EV_AMD_SL_PUB_KEY";
            v37 = v36 - 1;
            if ( !v37 )
              return L"EV_AMD_SL_SVN";
            v38 = v37 - 1;
            if ( !v38 )
              return L"EV_AMD_SL_LOAD_1";
            if ( v38 == 1 )
              return L"EV_AMD_SL_SEPARATOR";
          }
          return L"UNDEFINED";
        }
        switch ( a1 )
        {
          case 0x820Bu:
            result = L"EV_AMD_ABL_2";
            break;
          case 0x820Cu:
            result = L"EV_AMD_ABL_3";
            break;
          case 0x820Du:
            result = L"EV_AMD_ABL_4";
            break;
          case 0x820Eu:
            result = L"EV_AMD_ABL_5";
            break;
          case 0x820Fu:
            result = L"EV_AMD_ABL_6";
            break;
          case 0x8210u:
            result = L"EV_AMD_ABL_7";
            break;
          case 0x8211u:
            result = L"EV_AMD_ABL_8";
            break;
          case 0x8212u:
            result = L"EV_AMD_ABL_9";
            break;
          case 0x8213u:
            result = L"EV_AMD_ABL_10";
            break;
          case 0x8214u:
            result = L"EV_AMD_ABL_11";
            break;
          case 0x8215u:
            result = L"EV_AMD_ABL_12";
            break;
          case 0x8216u:
            result = L"EV_AMD_ABL_13";
            break;
          case 0x8217u:
            result = L"EV_AMD_ABL_14";
            break;
          case 0x8218u:
            result = L"EV_AMD_ABL_15";
            break;
          case 0x8219u:
            result = L"EV_AMD_ABL_16";
            break;
          case 0x821Au:
            result = L"EV_AMD_ABL_17";
            break;
          case 0x821Bu:
            result = L"EV_AMD_ABL_18";
            break;
          case 0x821Cu:
            result = L"EV_AMD_ABL_19";
            break;
          default:
            return L"UNDEFINED";
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800f9acc  mov     eax, 400h
0x1800f9ad1  cmp     ecx, eax
0x1800f9ad3  ja      loc_1800F9C03
0x1800f9ad9  jz      loc_1800F9BFA
0x1800f9adf  cmp     ecx, 9
0x1800f9ae2  ja      loc_1800F9B78
0x1800f9ae8  jz      loc_1800F9B6F
0x1800f9aee  test    ecx, ecx
0x1800f9af0  jz      short loc_1800F9B66
0x1800f9af2  sub     ecx, 1
0x1800f9af5  jz      short loc_1800F9B5D
0x1800f9af7  sub     ecx, 1
0x1800f9afa  jz      short loc_1800F9B54
0x1800f9afc  sub     ecx, 1
0x1800f9aff  jz      short loc_1800F9B4B
0x1800f9b01  sub     ecx, 1
0x1800f9b04  jz      short loc_1800F9B42
0x1800f9b06  sub     ecx, 1
0x1800f9b09  jz      short loc_1800F9B39
0x1800f9b0b  sub     ecx, 1
0x1800f9b0e  jz      short loc_1800F9B30
0x1800f9b10  sub     ecx, 1
0x1800f9b13  jz      short loc_1800F9B27
0x1800f9b15  cmp     ecx, 1
0x1800f9b18  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9b1e  lea     rax, aEvSCrtmVersion_0; "EV_S_CRTM_VERSION"
0x1800f9b25  retn
0x1800f9b27  lea     rax, aEvSCrtmContent_0; "EV_S_CRTM_CONTENTS"
0x1800f9b2e  retn
0x1800f9b30  lea     rax, aEvEventTag_0; "EV_EVENT_TAG"
0x1800f9b37  retn
0x1800f9b39  lea     rax, aEvAction; "EV_ACTION"
0x1800f9b40  retn
0x1800f9b42  lea     rax, aEvSeparator; "EV_SEPARATOR"
0x1800f9b49  retn
0x1800f9b4b  lea     rax, aEvNoAction_0; "EV_NO_ACTION"
0x1800f9b52  retn
0x1800f9b54  lea     rax, aEvUnused_0; "EV_UNUSED"
0x1800f9b5b  retn
0x1800f9b5d  lea     rax, aEvPostCode; "EV_POST_CODE"
0x1800f9b64  retn
0x1800f9b66  lea     rax, aEvPrebootCert_0; "EV_PREBOOT_CERT"
0x1800f9b6d  retn
0x1800f9b6f  lea     rax, aEvCpuMicrocode; "EV_CPU_MICROCODE"
0x1800f9b76  retn
0x1800f9b78  sub     ecx, 0Ah
0x1800f9b7b  jz      short loc_1800F9BF1
0x1800f9b7d  sub     ecx, 1
0x1800f9b80  jz      short loc_1800F9BE8
0x1800f9b82  sub     ecx, 1
0x1800f9b85  jz      short loc_1800F9BDF
0x1800f9b87  sub     ecx, 1
0x1800f9b8a  jz      short loc_1800F9BD6
0x1800f9b8c  sub     ecx, 1
0x1800f9b8f  jz      short loc_1800F9BCD
0x1800f9b91  sub     ecx, 1
0x1800f9b94  jz      short loc_1800F9BC4
0x1800f9b96  sub     ecx, 1
0x1800f9b99  jz      short loc_1800F9BBB
0x1800f9b9b  sub     ecx, 1
0x1800f9b9e  jz      short loc_1800F9BB2
0x1800f9ba0  cmp     ecx, 1
0x1800f9ba3  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9ba9  lea     rax, aEvOmitBootDevi; "EV_OMIT_BOOT_DEVICE_EVENTS"
0x1800f9bb0  retn
0x1800f9bb2  lea     rax, aEvNonhostInfo; "EV_NONHOST_INFO"
0x1800f9bb9  retn
0x1800f9bbb  lea     rax, aEvNonhostConfi_0; "EV_NONHOST_CONFIG"
0x1800f9bc2  retn
0x1800f9bc4  lea     rax, aEvNonhostCode_0; "EV_NONHOST_CODE"
0x1800f9bcb  retn
0x1800f9bcd  lea     rax, aEvIplPartition_0; "EV_IPL_PARTITION_DATA"
0x1800f9bd4  retn
0x1800f9bd6  lea     rax, aEvIpl; "EV_IPL"
0x1800f9bdd  retn
0x1800f9bdf  lea     rax, aEvCompactHash; "EV_COMPACT_HASH"
0x1800f9be6  retn
0x1800f9be8  lea     rax, aEvTableOfDevic_0; "EV_TABLE_OF_DEVICES"
0x1800f9bef  retn
0x1800f9bf1  lea     rax, aEvPlatformConf_0; "EV_PLATFORM_CONFIG_FLAGS"
0x1800f9bf8  retn
0x1800f9bfa  lea     rax, aEvTxtEventBase; "EV_TXT_EVENT_BASE"
0x1800f9c01  retn
0x1800f9c03  mov     eax, 4FEh
0x1800f9c08  cmp     ecx, eax
0x1800f9c0a  ja      loc_1800F9D7B
0x1800f9c10  jz      loc_1800F9D72
0x1800f9c16  mov     eax, 410h
0x1800f9c1b  cmp     ecx, eax
0x1800f9c1d  ja      loc_1800F9CD2
0x1800f9c23  jz      loc_1800F9CC9
0x1800f9c29  mov     eax, 40Bh
0x1800f9c2e  cmp     ecx, eax
0x1800f9c30  ja      short loc_1800F9C8A
0x1800f9c32  jz      short loc_1800F9C81
0x1800f9c34  sub     ecx, 401h
0x1800f9c3a  jz      short loc_1800F9C78
0x1800f9c3c  sub     ecx, 1
0x1800f9c3f  jz      short loc_1800F9C6F
0x1800f9c41  sub     ecx, 1
0x1800f9c44  jz      short loc_1800F9C66
0x1800f9c46  sub     ecx, 1
0x1800f9c49  jz      short loc_1800F9C5D
0x1800f9c4b  cmp     ecx, 6
0x1800f9c4e  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9c54  lea     rax, aEvTxtBiosacReg; "EV_TXT_BIOSAC_REG_DATA"
0x1800f9c5b  retn
0x1800f9c5d  lea     rax, aEvTxtMleHash; "EV_TXT_MLE_HASH"
0x1800f9c64  retn
0x1800f9c66  lea     rax, aEvTxtCombinedH; "EV_TXT_COMBINED_HASH"
0x1800f9c6d  retn
0x1800f9c6f  lea     rax, aEvTxtHashStart; "EV_TXT_HASH_START"
0x1800f9c76  retn
0x1800f9c78  lea     rax, aEvTxtPcrMappin; "EV_TXT_PCR_MAPPING"
0x1800f9c7f  retn
0x1800f9c81  lea     rax, aEvTxtCpuScrtmS; "EV_TXT_CPU_SCRTM_STAT"
0x1800f9c88  retn
0x1800f9c8a  sub     ecx, 40Ch
0x1800f9c90  jz      short loc_1800F9CC0
0x1800f9c92  sub     ecx, 1
0x1800f9c95  jz      short loc_1800F9CB7
0x1800f9c97  sub     ecx, 1
0x1800f9c9a  jz      short loc_1800F9CAE
0x1800f9c9c  cmp     ecx, 1
0x1800f9c9f  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9ca5  lea     rax, aEvTxtOssinitda; "EV_TXT_OSSINITDATA_CAP_HASH"
0x1800f9cac  retn
0x1800f9cae  lea     rax, aEvTxtStmHash; "EV_TXT_STM_HASH"
0x1800f9cb5  retn
0x1800f9cb7  lea     rax, aEvTxtElementsH; "EV_TXT_ELEMENTS_HASH"
0x1800f9cbe  retn
0x1800f9cc0  lea     rax, aEvTxtLcpContro; "EV_TXT_LCP_CONTROL_HASH"
0x1800f9cc7  retn
0x1800f9cc9  lea     rax, aEvTxtSinitPubk; "EV_TXT_SINIT_PUBKEY_HASH"
0x1800f9cd0  retn
0x1800f9cd2  mov     eax, 416h
0x1800f9cd7  cmp     ecx, eax
0x1800f9cd9  ja      short loc_1800F9D33
0x1800f9cdb  jz      short loc_1800F9D2A
0x1800f9cdd  sub     ecx, 411h
0x1800f9ce3  jz      short loc_1800F9D21
0x1800f9ce5  sub     ecx, 1
0x1800f9ce8  jz      short loc_1800F9D18
0x1800f9cea  sub     ecx, 1
0x1800f9ced  jz      short loc_1800F9D0F
0x1800f9cef  sub     ecx, 1
0x1800f9cf2  jz      short loc_1800F9D06
0x1800f9cf4  cmp     ecx, 1
0x1800f9cf7  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9cfd  lea     rax, aEvTxtColdBootB; "EV_TXT_COLD_BOOT_BIOS_HASH"
0x1800f9d04  retn
0x1800f9d06  lea     rax, aEvTxtNvInfoHas; "EV_TXT_NV_INFO_HASH"
0x1800f9d0d  retn
0x1800f9d0f  lea     rax, aEvTxtLcpAuthor; "EV_TXT_LCP_AUTHORITIES_HASH"
0x1800f9d16  retn
0x1800f9d18  lea     rax, aEvTxtLcpDetail; "EV_TXT_LCP_DETAILS_HASH"
0x1800f9d1f  retn
0x1800f9d21  lea     rax, aEvTxtLcpHash; "EV_TXT_LCP_HASH"
0x1800f9d28  retn
0x1800f9d2a  lea     rax, aEvTxtKmHash; "EV_TXT_KM_HASH"
0x1800f9d31  retn
0x1800f9d33  sub     ecx, 417h
0x1800f9d39  jz      short loc_1800F9D69
0x1800f9d3b  sub     ecx, 1
0x1800f9d3e  jz      short loc_1800F9D60
0x1800f9d40  sub     ecx, 1
0x1800f9d43  jz      short loc_1800F9D57
0x1800f9d45  cmp     ecx, 1
0x1800f9d48  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9d4e  lea     rax, aEvTxtBootPolHa; "EV_TXT_BOOT_POL_HASH"
0x1800f9d55  retn
0x1800f9d57  lea     rax, aEvTxtBpmInfoHa; "EV_TXT_BPM_INFO_HASH"
0x1800f9d5e  retn
0x1800f9d60  lea     rax, aEvTxtKmInfoHas; "EV_TXT_KM_INFO_HASH"
0x1800f9d67  retn
0x1800f9d69  lea     rax, aEvTxtBpmHash; "EV_TXT_BPM_HASH"
0x1800f9d70  retn
0x1800f9d72  lea     rax, aEvTxtRandomVal; "EV_TXT_RANDOM_VALUE"
0x1800f9d79  retn
0x1800f9d7b  mov     eax, 8302h
0x1800f9d80  cmp     ecx, eax
0x1800f9d82  ja      loc_1800FA47E
0x1800f9d88  jz      loc_1800FA475
0x1800f9d8e  mov     eax, 8243h
0x1800f9d93  cmp     ecx, eax
0x1800f9d95  ja      loc_1800FA146
0x1800f9d9b  jz      loc_1800FA13D
0x1800f9da1  mov     eax, 821Dh
0x1800f9da6  cmp     ecx, eax
0x1800f9da8  ja      loc_1800F9FCA
0x1800f9dae  jz      loc_1800F9FC1
0x1800f9db4  mov     eax, 820Ah
0x1800f9db9  cmp     ecx, eax
0x1800f9dbb  ja      loc_1800F9EF9
0x1800f9dc1  jz      loc_1800F9EF0
0x1800f9dc7  mov     eax, 8200h
0x1800f9dcc  cmp     ecx, eax
0x1800f9dce  ja      loc_1800F9E6B
0x1800f9dd4  jz      loc_1800F9E62
0x1800f9dda  sub     ecx, 4FFh
0x1800f9de0  jz      short loc_1800F9E59
0x1800f9de2  sub     ecx, 7B01h
0x1800f9de8  jz      short loc_1800F9E50
0x1800f9dea  sub     ecx, 1
0x1800f9ded  jz      short loc_1800F9E47
0x1800f9def  sub     ecx, 1
0x1800f9df2  jz      short loc_1800F9E3E
0x1800f9df4  sub     ecx, 1
0x1800f9df7  jz      short loc_1800F9E35
0x1800f9df9  sub     ecx, 1
0x1800f9dfc  jz      short loc_1800F9E2C
0x1800f9dfe  sub     ecx, 1
0x1800f9e01  jz      short loc_1800F9E23
0x1800f9e03  sub     ecx, 1
0x1800f9e06  jz      short loc_1800F9E1A
0x1800f9e08  cmp     ecx, 1
0x1800f9e0b  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9e11  lea     rax, aEvAmdSlSeparat; "EV_AMD_SL_SEPARATOR"
0x1800f9e18  retn
0x1800f9e1a  lea     rax, aEvAmdSlLoad1; "EV_AMD_SL_LOAD_1"
0x1800f9e21  retn
0x1800f9e23  lea     rax, aEvAmdSlSvn; "EV_AMD_SL_SVN"
0x1800f9e2a  retn
0x1800f9e2c  lea     rax, aEvAmdSlPubKey; "EV_AMD_SL_PUB_KEY"
0x1800f9e33  retn
0x1800f9e35  lea     rax, aEvAmdSlTsmeRbF; "EV_AMD_SL_TSME_RB_FUSE"
0x1800f9e3c  retn
0x1800f9e3e  lea     rax, aEvAmdSlPspFwSp; "EV_AMD_SL_PSP_FW_SPLT"
0x1800f9e45  retn
0x1800f9e47  lea     rax, aEvAmdSlLoad; "EV_AMD_SL_LOAD"
0x1800f9e4e  retn
0x1800f9e50  lea     rax, aEvAmdSlEventBa; "EV_AMD_SL_EVENT_BASE"
0x1800f9e57  retn
0x1800f9e59  lea     rax, aEvTxtCapValue; "EV_TXT_CAP_VALUE"
0x1800f9e60  retn
0x1800f9e62  lea     rax, aEvAmdBase2; "EV_AMD_BASE_2"
0x1800f9e69  retn
0x1800f9e6b  sub     ecx, 8201h
0x1800f9e71  jz      short loc_1800F9EE7
0x1800f9e73  sub     ecx, 1
0x1800f9e76  jz      short loc_1800F9EDE
0x1800f9e78  sub     ecx, 1
0x1800f9e7b  jz      short loc_1800F9ED5
0x1800f9e7d  sub     ecx, 1
0x1800f9e80  jz      short loc_1800F9ECC
0x1800f9e82  sub     ecx, 1
0x1800f9e85  jz      short loc_1800F9EC3
0x1800f9e87  sub     ecx, 1
0x1800f9e8a  jz      short loc_1800F9EBA
0x1800f9e8c  sub     ecx, 1
0x1800f9e8f  jz      short loc_1800F9EB1
0x1800f9e91  sub     ecx, 1
0x1800f9e94  jz      short loc_1800F9EA8
0x1800f9e96  cmp     ecx, 1
0x1800f9e99  jnz     def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9e9f  lea     rax, aEvAmdMp2Fw; "EV_AMD_MP2_FW"
0x1800f9ea6  retn
0x1800f9ea8  lea     rax, aEvAmdMp2Config; "EV_AMD_MP2_CONFIG"
0x1800f9eaf  retn
0x1800f9eb1  lea     rax, aEvAmdPmfw0; "EV_AMD_PMFW0"
0x1800f9eb8  retn
0x1800f9eba  lea     rax, aEvAmdPspL0SecP; "EV_AMD_PSP_L0_SEC_POL"
0x1800f9ec1  retn
0x1800f9ec3  lea     rax, aEvAmdPspBlStag; "EV_AMD_PSP_BL_STAGE_2"
0x1800f9eca  retn
0x1800f9ecc  lea     rax, aEvAmdSplTableF; "EV_AMD_SPL_TABLE_FW"
0x1800f9ed3  retn
0x1800f9ed5  lea     rax, aEvAmdPspKeydb; "EV_AMD_PSP_KEYDB"
0x1800f9edc  retn
0x1800f9ede  lea     rax, aEvAmdPspBlStag_0; "EV_AMD_PSP_BL_STAGE_1"
0x1800f9ee5  retn
0x1800f9ee7  lea     rax, aEvAmdSplTableR; "EV_AMD_SPL_TABLE_ROM"
0x1800f9eee  retn
0x1800f9ef0  lea     rax, aEvAmdAbl1; "EV_AMD_ABL_1"
0x1800f9ef7  retn
0x1800f9ef9  lea     eax, [rcx-820Bh]; switch 18 cases
0x1800f9eff  cmp     eax, 11h
0x1800f9f02  ja      def_1800F9F19; jumptable 00000001800F9F19 default case
0x1800f9f08  lea     rcx, __ImageBase
0x1800f9f0f  mov     eax, ds:(jpt_1800F9F19 - 180000000h)[rcx+rax*4]
0x1800f9f16  add     rax, rcx
0x1800f9f19  jmp     rax; switch jump
0x1800f9f1f  lea     rax, aEvAmdAbl2; jumptable 00000001800F9F19 case 33291
0x1800f9f26  retn
0x1800f9f28  lea     rax, aEvAmdAbl3; jumptable 00000001800F9F19 case 33292
0x1800f9f2f  retn
0x1800f9f31  lea     rax, aEvAmdAbl4; jumptable 00000001800F9F19 case 33293
0x1800f9f38  retn
0x1800f9f3a  lea     rax, aEvAmdAbl5; jumptable 00000001800F9F19 case 33294
0x1800f9f41  retn
0x1800f9f43  lea     rax, aEvAmdAbl6; jumptable 00000001800F9F19 case 33295
0x1800f9f4a  retn
0x1800f9f4c  lea     rax, aEvAmdAbl7; jumptable 00000001800F9F19 case 33296
0x1800f9f53  retn
0x1800f9f55  lea     rax, aEvAmdAbl8; jumptable 00000001800F9F19 case 33297
0x1800f9f5c  retn
0x1800f9f5e  lea     rax, aEvAmdAbl9; jumptable 00000001800F9F19 case 33298
0x1800f9f65  retn
0x1800f9f67  lea     rax, aEvAmdAbl10; jumptable 00000001800F9F19 case 33299
0x1800f9f6e  retn
  ... truncated ...
```
