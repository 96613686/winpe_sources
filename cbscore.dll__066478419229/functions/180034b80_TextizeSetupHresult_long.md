# TextizeSetupHresult(long)

- ea: `0x180034b80`
- end: `0x1800355a2`
- name: `?TextizeSetupHresult@@YAPEBDJ@Z`
- size: `2594`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035970`

## callees

- `0x180034b80`

## string_xrefs

- `0x180035591`: `CBS_S_ALREADY_EXISTS`
- `0x18003501f`: `CBS_E_OPEN_FAILED`
- `0x18003500d`: `CBS_E_ALREADY_INITIALIZED`
- `0x180035043`: `CBS_E_IMAGE_NOT_ACCESSIBLE`
- `0x18003503a`: `CBS_E_NOT_INSTALLABLE`
- `0x180035067`: `CBS_E_UNKNOWN_UPDATE`
- `0x18003508b`: `CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ATTRIBUTES`
- `0x180035082`: `CBS_E_MANIFEST_VALIDATION_DUPLICATE_ELEMENT`
- `0x180035079`: `CBS_E_MANIFEST_VALIDATION_DUPLICATE_ATTRIBUTES`
- `0x180035070`: `CBS_E_MANIFEST_INVALID_ITEM`
- `0x1800350af`: `CBS_E_INVALID_CONFIG_VALUE`
- `0x1800350a6`: `CBS_E_INVALID_INSTALL_STATE`
- `0x18003509d`: `CBS_E_MANIFEST_VALIDATION_UPDATES_PARENT_MISSING`
- `0x180035094`: `CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ELEMENTS`
- `0x1800350ca`: `CBS_E_PACKAGE_DELETED`
- `0x1800350dc`: `CBS_E_DUPLICATE_UPDATENAME`
- `0x180035169`: `CBS_E_ILLEGAL_COMPONENT_UPDATE`
- `0x180035184`: `CBS_E_CANNOT_REMOVE`
- `0x1800351b1`: `CBS_E_STACK_UPDATE_FAILED_REBOOT_REQUIRED`
- `0x1800351e7`: `CBS_E_IMAGE_UNSERVICEABLE`
- `0x180035226`: `CBS_E_POSTPONED_INSTALL_CONSIDERED`
- `0x1800352b3`: `CBS_E_XML_PARSER_FAILURE`
- `0x18003525c`: `CBS_E_SESSION_READONLY`
- `0x1800352bc`: `CBS_E_MANIFEST_VALIDATION_MULTIPLE_UPDATE_COMPONENT_ON_SAME_FAMILY_NOT_ALLOWED`
- `0x18003530d`: `CBS_E_COMPONENT_NOT_INSTALLED_BY_CBS`
- `0x180035304`: `CBS_E_REPAIR_PACKAGE_CORRUPT`
- `0x180035331`: `CBS_E_WINDOWS_AUTOMATIC_UPDATE_SETTING_DISALLOWED`
- `0x180035328`: `CBS_E_WINDOWS_UPDATE_SEARCH_FAILURE`
- `0x180035355`: `CBS_E_REPAIR_CONTENT_MISSING`
- `0x180035379`: `CBS_E_INSTALLERS_FAILED`
- `0x18003539d`: `CBS_E_CANNOT_REMOVE_CONTAINER_DEPENDENCY`
- `0x1800354cb`: `CBS_E_INVALID_ACTION_LIST_INSTALL_ACTION`
- `0x1800354b9`: `CBS_E_NO_OPTIONAL_CONTENT_FOUND_ON_UPDATE_SERVERS`
- `0x1800354b0`: `CBS_E_INVALID_ACTION_LIST_INSTALL_REASON`
- `0x1800354ef`: `PSFX_E_MATCHING_COMPONENT_DIRECTORY_MISSING`
- `0x1800354e6`: `PSFX_E_MATCHING_COMPONENT_NOT_FOUND`
- `0x1800354d4`: `PSFX_E_DELTA_NOT_SUPPORTED_FOR_COMPONENT`
- `0x18003552e`: `PSFX_E_UNSUPPORTED_COMPRESSION_SWITCH`
- `0x18003551c`: `PSFX_E_INVALID_DELTA_COMBINATION`
- `0x180034cee`: `SPAPI_E_DEVINST_ALREADY_EXISTS`
- `0x180034d36`: `SPAPI_E_DI_NOFILECOPY`
- `0x180034d24`: `SPAPI_E_INVALID_CLASS_INSTALLER`
- `0x180034da7`: `SPAPI_E_BAD_SERVICE_INSTALLSECT`
- `0x180034d95`: `SPAPI_E_NO_CLASSINSTALL_PARAMS`
- `0x180034d8c`: `SPAPI_E_DI_BAD_PATH`
- `0x180034db9`: `SPAPI_E_NO_ASSOCIATED_SERVICE`
- `0x180034ddd`: `SPAPI_E_BAD_INTERFACE_INSTALLSECT`
- `0x180034dd4`: `SPAPI_E_DEVICE_INTERFACE_REMOVED`
- `0x180034e13`: `SPAPI_E_NO_CONFIGMGR_SERVICES`
- `0x180034e01`: `SPAPI_E_REMOTE_COMM_FAILURE`
- `0x180034e37`: `SPAPI_E_INVALID_COINSTALLER`
- `0x180034e5b`: `SPAPI_E_DI_DONT_INSTALL`
- `0x180034e52`: `SPAPI_E_INVALID_INF_LOGCONFIG`
- `0x180034e40`: `SPAPI_E_NO_COMPAT_DRIVERS`
- `0x180034ed6`: `SPAPI_E_CANT_REMOVE_DEVINST`
- `0x180034ec4`: `SPAPI_E_DEVINSTALL_QUEUE_NONNATIVE`
- `0x180034f1e`: `SPAPI_E_PNP_REGISTRY_ERROR`
- `0x180034f30`: `SPAPI_E_NOT_AN_INSTALLED_OEM_INF`
- `0x180034f8a`: `SPAPI_E_DEVICE_INSTALLER_NOT_READY`
- `0x180034fa5`: `SPAPI_E_DRIVER_INSTALL_BLOCKED`
- `0x180034f9c`: `SPAPI_E_DEVICE_INSTALL_BLOCKED`
- `0x180035564`: `SPAPI_E_ERROR_NOT_INSTALLED`
- `0x180034fc0`: `SPAPI_E_DRIVER_STORE_DELETE_FAILED`

## pseudocode

```c
const char *__fastcall TextizeSetupHresult(int a1)
{
  const char *v1; // rdx
  bool v2; // zf
  const char *result; // rax
  int v4; // ecx
  int v5; // ecx

  if ( a1 > -2146498535 )
  {
    if ( a1 > -2146498481 )
    {
      if ( a1 > -2146498256 )
      {
        if ( a1 > -2146496512 )
        {
          v4 = a1 - 985089;
          if ( v4 )
          {
            v5 = v4 - 1;
            if ( v5 )
            {
              if ( v5 == 1 )
                return "CBS_S_STACK_SHUTDOWN_REQUIRED";
              else
                return "Unknown Error";
            }
            else
            {
              return "CBS_S_ALREADY_EXISTS";
            }
          }
          else
          {
            return "CBS_S_BUSY";
          }
        }
        else if ( a1 == -2146496512 )
        {
          return "SPAPI_E_ERROR_NOT_INSTALLED";
        }
        else
        {
          switch ( a1 )
          {
            case -2146498240:
              result = "CBS_E_WUSUS_MAPPING_UNAVAILABLE";
              break;
            case -2146498239:
              result = "CBS_E_WU_MAPPING_UNAVAILABLE";
              break;
            case -2146498238:
              result = "CBS_E_WUSUS_BYPASS_MAPPING_UNAVAILABLE";
              break;
            case -2146498237:
              result = "CBS_E_WUSUS_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498236:
              result = "CBS_E_WU_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498235:
              result = "CBS_E_WUSUS_BYPASS_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498234:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_CAB";
              break;
            case -2146498233:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_EXPRESS";
              break;
            case -2146498232:
              result = "CBS_E_SOURCE_MISSING_FROM_WU_CAB";
              break;
            case -2146498231:
              result = "CBS_E_SOURCE_MISSING_FROM_WU_EXPRESS";
              break;
            case -2146498230:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_BYPASS_CAB";
              break;
            case -2146498229:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_BYPASS_EXPRESS";
              break;
            case -2146498228:
              result = "CBS_E_3RD_PARTY_MAPPING_UNAVAILABLE";
              break;
            case -2146498227:
              result = "CBS_E_3RD_PARTY_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498226:
              result = "CBS_E_SOURCE_MISSING_FROM_3RD_PARTY_CAB";
              break;
            case -2146498225:
              result = "CBS_E_SOURCE_MISSING_FROM_3RD_PARTY_EXPRESS";
              break;
            case -2146498224:
              result = "CBS_E_NO_OPTIONAL_CONTENT_FOUND_FOR_BUILD";
              break;
            case -2146498223:
              result = "CBS_E_INVALID_NO_PRODUCT_REGISTERED";
              break;
            case -2146498222:
              result = "CBS_E_INVALID_ACTION_LIST_PACKAGE_COUNT";
              break;
            case -2146498221:
              result = "CBS_E_INVALID_ACTION_LIST_INSTALL_REASON";
              break;
            case -2146498220:
              result = "CBS_E_NO_OPTIONAL_CONTENT_FOUND_ON_UPDATE_SERVERS";
              break;
            case -2146498219:
              result = "CBS_E_INVALID_PACKAGE_REQUEST_ON_MULTILINGUAL_FOD";
              break;
            case -2146498218:
              result = "CBS_E_INVALID_ACTION_LIST_INSTALL_ACTION";
              break;
            case -2146498176:
              result = "PSFX_E_DELTA_NOT_SUPPORTED_FOR_COMPONENT";
              break;
            case -2146498175:
              result = "PSFX_E_REVERSE_AND_FORWARD_DELTAS_MISSING";
              break;
            case -2146498174:
              result = "PSFX_E_MATCHING_COMPONENT_NOT_FOUND";
              break;
            case -2146498173:
              result = "PSFX_E_MATCHING_COMPONENT_DIRECTORY_MISSING";
              break;
            case -2146498172:
              result = "PSFX_E_MATCHING_BINARY_MISSING";
              break;
            case -2146498171:
              result = "PSFX_E_APPLY_REVERSE_DELTA_FAILED";
              break;
            case -2146498170:
              result = "PSFX_E_APPLY_FORWARD_DELTA_FAILED";
              break;
            case -2146498169:
              result = "PSFX_E_NULL_DELTA_HYDRATION_FAILED";
              break;
            case -2146498168:
              result = "PSFX_E_INVALID_DELTA_COMBINATION";
              break;
            case -2146498167:
              result = "PSFX_E_REVERSE_DELTA_MISSING";
              break;
            case -2146498160:
              result = "PSFX_E_UNSUPPORTED_COMPRESSION_SWITCH";
              break;
            case -2146498159:
              result = "PSFX_E_MISSING_PAYLOAD_FILE";
              break;
            case -2146498158:
              result = "PSFX_E_PARTIAL_HYDRATION";
              break;
            case -2146498157:
              result = "PSFX_E_REBASE_HYDRATION_CANDIDATES_MISSING";
              break;
            case -2146498156:
              result = "PSFX_E_REBASE_HASH_ALG_NOT_SUPPORTED";
              break;
            case -2146498155:
              result = "PSFX_E_REBASE_MISSING_BASE_FILE";
              break;
            default:
              return "Unknown Error";
          }
        }
      }
      else if ( a1 == -2146498256 )
      {
        return "CBS_E_UNO_PACKAGE_CAB_MISSING";
      }
      else
      {
        switch ( a1 )
        {
          case -2146498304:
            result = "CBS_E_XML_PARSER_FAILURE";
            break;
          case -2146498303:
            result = "CBS_E_MANIFEST_VALIDATION_MULTIPLE_UPDATE_COMPONENT_ON_SAME_FAMILY_NOT_ALLOWED";
            break;
          case -2146498302:
            result = "CBS_E_BUSY";
            break;
          case -2146498300:
            result = "CBS_E_MORE_THAN_ONE_ACTIVE_EDITION";
            break;
          case -2146498299:
            result = "CBS_E_NO_ACTIVE_EDITION";
            break;
          case -2146498298:
            result = "CBS_E_DOWNLOAD_FAILURE";
            break;
          case -2146498297:
            result = "CBS_E_GROUPPOLICY_DISALLOWED";
            break;
          case -2146498296:
            result = "CBS_E_METERED_NETWORK";
            break;
          case -2146498295:
            result = "CBS_E_PUBLIC_OBJECT_LEAK";
            break;
          case -2146498293:
            result = "CBS_E_REPAIR_PACKAGE_CORRUPT";
            break;
          case -2146498292:
            result = "CBS_E_COMPONENT_NOT_INSTALLED_BY_CBS";
            break;
          case -2146498291:
            result = "CBS_E_MISSING_PACKAGE_MAPPING_INDEX";
            break;
          case -2146498290:
            result = "CBS_E_EMPTY_PACKAGE_MAPPING_INDEX";
            break;
          case -2146498289:
            result = "CBS_E_WINDOWS_UPDATE_SEARCH_FAILURE";
            break;
          case -2146498288:
            result = "CBS_E_WINDOWS_AUTOMATIC_UPDATE_SETTING_DISALLOWED";
            break;
          case -2146498287:
            result = "CBS_E_SOURCE_MODIFIED";
            break;
          case -2146498286:
            result = "CBS_E_ONDEMAND_LOCALSOURCE_NOT_FOUND";
            break;
          case -2146498284:
            result = "CBS_E_WINRE_NOT_ENABLED";
            break;
          case -2146498283:
            result = "CBS_E_REPAIR_CONTENT_MISSING";
            break;
          case -2146498282:
            result = "CBS_E_PAYLOAD_FILE_MISSING";
            break;
          case -2146498272:
            result = "CBS_E_HANG_DETECTED";
            break;
          case -2146498271:
            result = "CBS_E_PRIMITIVES_FAILED";
            break;
          case -2146498270:
            result = "CBS_E_INSTALLERS_FAILED";
            break;
          case -2146498269:
            result = "CBS_E_SAFEMODE_ENTERED";
            break;
          case -2146498268:
            result = "CBS_E_SESSIONS_LEAKED";
            break;
          case -2146498267:
            result = "CBS_E_INVALID_EXECUTESTATE";
            break;
          case -2146498266:
            result = "CBS_E_CANNOT_REMOVE_CONTAINER_DEPENDENCY";
            break;
          case -2146498265:
            result = "CBS_E_ONDEMAND_RESERVICING_REQUIRED";
            break;
          case -2146498264:
            result = "CBS_E_ONLINE_ACTIONS_POSTPONED";
            break;
          default:
            return "Unknown Error";
        }
      }
    }
    else if ( a1 == -2146498481 )
    {
      return "CBS_E_RESOLVE_FAILED";
    }
    else
    {
      switch ( a1 )
      {
        case -2146498534:
          result = "CBS_E_INVALID_DRIVER_OPERATION_KEY";
          break;
        case -2146498533:
          result = "CBS_E_UNEXPECTED_PROCESSOR_ARCHITECTURE";
          break;
        case -2146498532:
          result = "CBS_E_EXCESSIVE_EVALUATION";
          break;
        case -2146498531:
          result = "CBS_E_CYCLE_EVALUATION";
          break;
        case -2146498530:
          result = "CBS_E_NOT_APPLICABLE ";
          break;
        case -2146498529:
          result = "CBS_E_SOURCE_MISSING";
          break;
        case -2146498528:
          result = "CBS_E_CANCEL";
          break;
        case -2146498527:
          result = "CBS_E_ABORT";
          break;
        case -2146498526:
          result = "CBS_E_ILLEGAL_COMPONENT_UPDATE";
          break;
        case -2146498525:
          result = "CBS_E_NEW_SERVICING_STACK_REQUIRED";
          break;
        case -2146498524:
          result = "CBS_E_SOURCE_NOT_IN_LIST";
          break;
        case -2146498523:
          result = "CBS_E_CANNOT_REMOVE";
          break;
        case -2146498522:
          result = "CBS_E_PENDING_VICTIM";
          break;
        case -2146498521:
          result = "CBS_E_STACK_SHUTDOWN_REQUIRED";
          break;
        case -2146498520:
          result = "CBS_E_INSUFFICIENT_DISK_SPACE";
          break;
        case -2146498519:
          result = "CBS_E_AC_POWER_REQUIRED";
          break;
        case -2146498518:
          result = "CBS_E_STACK_UPDATE_FAILED_REBOOT_REQUIRED";
          break;
        case -2146498517:
          result = "CBS_E_SQM_REPORT_IGNORED_AI_FAILURES_ON_TRANSACTION_RESOLVE";
          break;
        case -2146498516:
          result = "CBS_E_DEPENDENT_FAILURE";
          break;
        case -2146498515:
          result = "CBS_E_PAC_INITIAL_FAILURE";
          break;
        case -2146498514:
          result = "CBS_E_NOT_ALLOWED_OFFLINE";
          break;
        case -2146498513:
          result = "CBS_E_EXCLUSIVE_WOULD_MERGE";
          break;
        case -2146498512:
          result = "CBS_E_IMAGE_UNSERVICEABLE";
          break;
        case -2146498511:
          result = "CBS_E_STORE_CORRUPTION";
          break;
        case -2146498510:
          result = "CBS_E_STORE_TOO_MUCH_CORRUPTION";
          break;
        case -2146498509:
          result = "CBS_S_STACK_RESTART_REQUIRED";
          break;
        case -2146498508:
          result = "CBS_E_CANNOT_USE_PNP_DRIVER_ON_DECONSTRUCTED_DRIVER_IMAGE";
          break;
        case -2146498507:
          result = "CBS_E_STACK_SHUTTING_DOWN";
          break;
        case -2146498506:
          result = "CBS_E_MUV6_STACK_SHUTDOWN_NEEDED";
          break;
        case -2146498505:
          result = "CBS_E_POSTPONED_INSTALL_CONSIDERED";
          break;
        case -2146498504:
          result = "CBS_E_RESERVICING_REQUIRED_BASELINE";
          break;
        case -2146498503:
          result = "CBS_E_RPT_CRASHED";
          break;
        case -2146498496:
          result = "CBS_E_SESSION_CORRUPT";
          break;
        case -2146498495:
          result = "CBS_E_SESSION_INTERRUPTED";
          break;
        case -2146498494:
          result = "CBS_E_SESSION_FINALIZED";
          break;
        case -2146498493:
          result = "CBS_E_SESSION_READONLY";
          break;
        case -2146498490:
          result = "CBS_E_NOT_SUPPORTED_ON_IMAGE_TYPE";
          break;
        default:
          return "Unknown Error";
      }
    }
  }
  else if ( a1 == -2146498535 )
  {
    return "CBS_E_DUPLICATE_UPDATENAME";
  }
  else if ( a1 > -2146500049 )
  {
    if ( a1 > -2146499840 )
    {
      switch ( a1 )
      {
        case -2146498560:
          result = "CBS_E_INTERNAL_ERROR";
          break;
        case -2146498559:
          result = "CBS_E_NOT_INITIALIZED";
          break;
        case -2146498558:
          result = "CBS_E_ALREADY_INITIALIZED";
          break;
        case -2146498557:
          result = "CBS_E_INVALID_PARAMETER";
          break;
        case -2146498556:
          result = "CBS_E_OPEN_FAILED";
          break;
        case -2146498555:
          result = "CBS_E_INVALID_PACKAGE";
          break;
        case -2146498554:
          result = "CBS_E_PENDING";
          break;
        case -2146498553:
          result = "CBS_E_NOT_INSTALLABLE";
          break;
        case -2146498552:
          result = "CBS_E_IMAGE_NOT_ACCESSIBLE";
          break;
        case -2146498551:
          result = "CBS_E_ARRAY_ELEMENT_MISSING";
          break;
        case -2146498550:
          result = "CBS_E_REESTABLISH_SESSION";
          break;
        case -2146498549:
          result = "CBS_E_PROPERTY_NOT_AVAILABLE";
          break;
        case -2146498548:
          result = "CBS_E_UNKNOWN_UPDATE";
          break;
        case -2146498547:
          result = "CBS_E_MANIFEST_INVALID_ITEM";
          break;
        case -2146498546:
          result = "CBS_E_MANIFEST_VALIDATION_DUPLICATE_ATTRIBUTES";
          break;
        case -2146498545:
          result = "CBS_E_MANIFEST_VALIDATION_DUPLICATE_ELEMENT";
          break;
        case -2146498544:
          result = "CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ATTRIBUTES";
          break;
        case -2146498543:
          result = "CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ELEMENTS";
          break;
        case -2146498542:
          result = "CBS_E_MANIFEST_VALIDATION_UPDATES_PARENT_MISSING";
          break;
        case -2146498541:
          result = "CBS_E_INVALID_INSTALL_STATE";
          break;
        case -2146498540:
          result = "CBS_E_INVALID_CONFIG_VALUE";
          break;
        case -2146498539:
          result = "CBS_E_INVALID_CARDINALITY";
          break;
        case -2146498538:
          result = "CBS_E_DPX_JOB_STATE_SAVED";
          break;
        case -2146498537:
          result = "CBS_E_PACKAGE_DELETED";
          break;
        case -2146498536:
          result = "CBS_E_IDENTITY_MISMATCH";
          break;
        default:
          return "Unknown Error";
      }
    }
    else if ( a1 == -2146499840 )
    {
      return "SPAPI_E_UNRECOVERABLE_STACK_OVERFLOW";
    }
    else
    {
      switch ( a1 )
      {
        case -2146500048:
          result = "SPAPI_E_DEVINSTALL_QUEUE_NONNATIVE";
          break;
        case -2146500047:
          result = "SPAPI_E_NOT_DISABLEABLE";
          break;
        case -2146500046:
          result = "SPAPI_E_CANT_REMOVE_DEVINST";
          break;
        case -2146500045:
          result = "SPAPI_E_INVALID_TARGET";
          break;
        case -2146500044:
          result = "SPAPI_E_DRIVER_NONNATIVE";
          break;
        case -2146500043:
          result = "SPAPI_E_IN_WOW64";
          break;
        case -2146500042:
          result = "SPAPI_E_SET_SYSTEM_RESTORE_POINT";
          break;
        case -2146500041:
          result = "SPAPI_E_INCORRECTLY_COPIED_INF";
          break;
        case -2146500040:
          result = "SPAPI_E_SCE_DISABLED";
          break;
        case -2146500039:
          result = "SPAPI_E_UNKNOWN_EXCEPTION";
          break;
        case -2146500038:
          result = "SPAPI_E_PNP_REGISTRY_ERROR";
          break;
        case -2146500037:
          result = "SPAPI_E_REMOTE_REQUEST_UNSUPPORTED";
          break;
        case -2146500036:
          result = "SPAPI_E_NOT_AN_INSTALLED_OEM_INF";
          break;
        case -2146500035:
          result = "SPAPI_E_INF_IN_USE_BY_DEVICES";
          break;
        case -2146500034:
          result = "SPAPI_E_DI_FUNCTION_OBSOLETE";
          break;
        case -2146500033:
          result = "SPAPI_E_NO_AUTHENTICODE_CATALOG";
          break;
        case -2146500032:
          result = "SPAPI_E_AUTHENTICODE_DISALLOWED";
          break;
        case -2146500031:
          result = "SPAPI_E_AUTHENTICODE_TRUSTED_PUBLISHER";
          break;
        case -2146500030:
          result = "SPAPI_E_AUTHENTICODE_TRUST_NOT_ESTABLISHED";
          break;
        case -2146500029:
          result = "SPAPI_E_AUTHENTICODE_PUBLISHER_NOT_TRUSTED";
          break;
        case -2146500028:
          result = "SPAPI_E_SIGNATURE_OSATTRIBUTE_MISMATCH";
          break;
        case -2146500027:
          result = "SPAPI_E_ONLY_VALIDATE_VIA_AUTHENTICODE";
          break;
        case -2146500026:
          result = "SPAPI_E_DEVICE_INSTALLER_NOT_READY";
          break;
        case -2146500025:
          result = "SPAPI_E_DRIVER_STORE_ADD_FAILED";
          break;
        case -2146500024:
          result = "SPAPI_E_DEVICE_INSTALL_BLOCKED";
          break;
        case -2146500023:
          result = "SPAPI_E_DRIVER_INSTALL_BLOCKED";
          break;
        case -2146500022:
          result = "SPAPI_E_WRONG_INF_TYPE";
          break;
        case -2146500021:
          result = "SPAPI_E_FILE_HASH_NOT_IN_CATALOG";
          break;
        case -2146500020:
          result = "SPAPI_E_DRIVER_STORE_DELETE_FAILED";
          break;
        default:
          return "Unknown Error";
      }
    }
  }
  else if ( a1 == -2146500049 )
  {
    return "SPAPI_E_NO_CATALOG_FOR_OEM_INF";
  }
  else if ( a1 > -2146500077 )
  {
    switch ( a1 )
    {
      case -2146500076:
        result = "SPAPI_E_DI_BAD_PATH";
        break;
      case -2146500075:
        result = "SPAPI_E_NO_CLASSINSTALL_PARAMS";
        break;
      case -2146500074:
        result = "SPAPI_E_FILEQUEUE_LOCKED";
        break;
      case -2146500073:
        result = "SPAPI_E_BAD_SERVICE_INSTALLSECT";
        break;
      case -2146500072:
        result = "SPAPI_E_NO_CLASS_DRIVER_LIST";
        break;
      case -2146500071:
        result = "SPAPI_E_NO_ASSOCIATED_SERVICE";
        break;
      case -2146500070:
        result = "SPAPI_E_NO_DEFAULT_DEVICE_INTERFACE";
        break;
      case -2146500069:
        result = "SPAPI_E_DEVICE_INTERFACE_ACTIVE";
        break;
      case -2146500068:
        result = "SPAPI_E_DEVICE_INTERFACE_REMOVED";
        break;
      case -2146500067:
        result = "SPAPI_E_BAD_INTERFACE_INSTALLSECT";
        break;
      case -2146500066:
        result = "SPAPI_E_NO_SUCH_INTERFACE_CLASS";
        break;
      case -2146500065:
        result = "SPAPI_E_INVALID_REFERENCE_STRING";
        break;
      case -2146500064:
        result = "SPAPI_E_INVALID_MACHINENAME";
        break;
      case -2146500063:
        result = "SPAPI_E_REMOTE_COMM_FAILURE";
        break;
      case -2146500062:
        result = "SPAPI_E_MACHINE_UNAVAILABLE";
        break;
      case -2146500061:
        result = "SPAPI_E_NO_CONFIGMGR_SERVICES";
        break;
      case -2146500060:
        result = "SPAPI_E_INVALID_PROPPAGE_PROVIDER";
        break;
      case -2146500059:
        result = "SPAPI_E_NO_SUCH_DEVICE_INTERFACE";
        break;
      case -2146500058:
        result = "SPAPI_E_DI_POSTPROCESSING_REQUIRED";
        break;
      case -2146500057:
        result = "SPAPI_E_INVALID_COINSTALLER";
        break;
      case -2146500056:
        result = "SPAPI_E_NO_COMPAT_DRIVERS";
        break;
      case -2146500055:
        result = "SPAPI_E_NO_DEVICE_ICON";
        break;
      case -2146500054:
        result = "SPAPI_E_INVALID_INF_LOGCONFIG";
        break;
      case -2146500053:
        result = "SPAPI_E_DI_DONT_INSTALL";
        break;
      case -2146500052:
        result = "SPAPI_E_INVALID_FILTER_DRIVER";
        break;
      case -2146500051:
        result = "SPAPI_E_NON_WINDOWS_NT_DRIVER";
        break;
      case -2146500050:
        result = "SPAPI_E_NON_WINDOWS_DRIVER";
        break;
      default:
        return "Unknown Error";
    }
  }
  else if ( a1 == -2146500077 )
  {
    return "SPAPI_E_DEVINFO_DATA_LOCKED";
  }
  else if ( a1 > -2146500091 )
  {
    switch ( a1 )
    {
      case -2146500090:
        result = "SPAPI_E_INVALID_CLASS";
        break;
      case -2146500089:
        result = "SPAPI_E_DEVINST_ALREADY_EXISTS";
        break;
      case -2146500088:
        result = "SPAPI_E_DEVINFO_NOT_REGISTERED";
        break;
      case -2146500087:
        result = "SPAPI_E_INVALID_REG_PROPERTY";
        break;
      case -2146500086:
        result = "SPAPI_E_NO_INF";
        break;
      case -2146500085:
        result = "SPAPI_E_NO_SUCH_DEVINST";
        break;
      case -2146500084:
        result = "SPAPI_E_CANT_LOAD_CLASS_ICON";
        break;
      case -2146500083:
        result = "SPAPI_E_INVALID_CLASS_INSTALLER";
        break;
      case -2146500082:
        result = "SPAPI_E_DI_DO_DEFAULT";
        break;
      case -2146500081:
        result = "SPAPI_E_DI_NOFILECOPY";
        break;
      case -2146500080:
        result = "SPAPI_E_INVALID_HWPROFILE";
        break;
      case -2146500079:
        result = "SPAPI_E_NO_DEVICE_SELECTED";
        break;
      case -2146500078:
        result = "SPAPI_E_DEVINFO_LIST_LOCKED";
        break;
      default:
        return "Unknown Error";
    }
  }
  else if ( a1 == -2146500091 )
  {
    return "SPAPI_E_INVALID_DEVINST_NAME";
  }
  else
  {
    if ( a1 > -2146500350 )
    {
      switch ( a1 )
      {
        case -2146500349:
          return "SPAPI_E_NO_BACKUP";
        case -2146500096:
          return "SPAPI_E_NO_ASSOCIATED_CLASS";
        case -2146500095:
          return "SPAPI_E_CLASS_MISMATCH";
        case -2146500094:
          return "SPAPI_E_DUPLICATE_FOUND";
        case -2146500093:
          return "SPAPI_E_NO_DRIVER_SELECTED";
      }
      v1 = "SPAPI_E_KEY_DOES_NOT_EXIST";
      v2 = a1 == -2146500092;
    }
    else
    {
      switch ( a1 )
      {
        case -2146500350:
          return "SPAPI_E_LINE_NOT_FOUND";
        case -2146500608:
          return "SPAPI_E_EXPECTED_SECTION_NAME";
        case -2146500607:
          return "SPAPI_E_BAD_SECTION_NAME_LINE";
        case -2146500606:
          return "SPAPI_E_SECTION_NAME_TOO_LONG";
        case -2146500605:
          return "SPAPI_E_GENERAL_SYNTAX";
        case -2146500352:
          return "SPAPI_E_WRONG_INF_STYLE";
      }
      v1 = "SPAPI_E_SECTION_NOT_FOUND";
      v2 = a1 == -2146500351;
    }
    result = "Unknown Error";
    if ( v2 )
      return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180034b80  mov     eax, 800F0819h
0x180034b85  cmp     ecx, eax
0x180034b87  jg      loc_1800350E5
0x180034b8d  jz      loc_1800350DC
0x180034b93  mov     eax, 800F022Fh
0x180034b98  cmp     ecx, eax
0x180034b9a  jg      loc_180034E88
0x180034ba0  jz      loc_180034E7F
0x180034ba6  mov     eax, 800F0213h
0x180034bab  cmp     ecx, eax
0x180034bad  jg      loc_180034D63
0x180034bb3  jz      loc_180034D5A
0x180034bb9  mov     eax, 800F0205h
0x180034bbe  cmp     ecx, eax
0x180034bc0  jg      loc_180034CBC
0x180034bc6  jz      loc_180034CB3
0x180034bcc  mov     eax, 800F0102h
0x180034bd1  cmp     ecx, eax
0x180034bd3  jg      short loc_180034C44
0x180034bd5  jz      short loc_180034C3B
0x180034bd7  cmp     ecx, 800F0000h
0x180034bdd  jz      short loc_180034C32
0x180034bdf  cmp     ecx, 800F0001h
0x180034be5  jz      short loc_180034C29
0x180034be7  cmp     ecx, 800F0002h
0x180034bed  jz      short loc_180034C20
0x180034bef  cmp     ecx, 800F0003h
0x180034bf5  jz      short loc_180034C17
0x180034bf7  cmp     ecx, 800F0100h
0x180034bfd  jz      short loc_180034C0E
0x180034bff  lea     rdx, aSpapiESectionN_0; "SPAPI_E_SECTION_NOT_FOUND"
0x180034c06  cmp     ecx, 800F0101h
0x180034c0c  jmp     short loc_180034C79
0x180034c0e  lea     rax, aSpapiEWrongInf; "SPAPI_E_WRONG_INF_STYLE"
0x180034c15  retn
0x180034c17  lea     rax, aSpapiEGeneralS; "SPAPI_E_GENERAL_SYNTAX"
0x180034c1e  retn
0x180034c20  lea     rax, aSpapiESectionN; "SPAPI_E_SECTION_NAME_TOO_LONG"
0x180034c27  retn
0x180034c29  lea     rax, aSpapiEBadSecti; "SPAPI_E_BAD_SECTION_NAME_LINE"
0x180034c30  retn
0x180034c32  lea     rax, aSpapiEExpected; "SPAPI_E_EXPECTED_SECTION_NAME"
0x180034c39  retn
0x180034c3b  lea     rax, aSpapiELineNotF; "SPAPI_E_LINE_NOT_FOUND"
0x180034c42  retn
0x180034c44  cmp     ecx, 800F0103h
0x180034c4a  jz      short loc_180034CAA
0x180034c4c  cmp     ecx, 800F0200h
0x180034c52  jz      short loc_180034CA1
0x180034c54  cmp     ecx, 800F0201h
0x180034c5a  jz      short loc_180034C98
0x180034c5c  cmp     ecx, 800F0202h
0x180034c62  jz      short loc_180034C8F
0x180034c64  cmp     ecx, 800F0203h
0x180034c6a  jz      short loc_180034C86
0x180034c6c  lea     rdx, aSpapiEKeyDoesN; "SPAPI_E_KEY_DOES_NOT_EXIST"
0x180034c73  cmp     ecx, 800F0204h
0x180034c79  lea     rax, Str2; "Unknown Error"
0x180034c80  cmovz   rax, rdx
0x180034c84  retn
0x180034c86  lea     rax, aSpapiENoDriver; "SPAPI_E_NO_DRIVER_SELECTED"
0x180034c8d  retn
0x180034c8f  lea     rax, aSpapiEDuplicat; "SPAPI_E_DUPLICATE_FOUND"
0x180034c96  retn
0x180034c98  lea     rax, aSpapiEClassMis; "SPAPI_E_CLASS_MISMATCH"
0x180034c9f  retn
0x180034ca1  lea     rax, aSpapiENoAssoci_0; "SPAPI_E_NO_ASSOCIATED_CLASS"
0x180034ca8  retn
0x180034caa  lea     rax, aSpapiENoBackup; "SPAPI_E_NO_BACKUP"
0x180034cb1  retn
0x180034cb3  lea     rax, aSpapiEInvalidD; "SPAPI_E_INVALID_DEVINST_NAME"
0x180034cba  retn
0x180034cbc  add     ecx, 7FF0FDFAh; switch 13 cases
0x180034cc2  cmp     ecx, 0Ch
0x180034cc5  ja      def_180034CDF; jumptable 0000000180034CDF default case
0x180034ccb  lea     rdx, __ImageBase
0x180034cd2  movsxd  rax, ecx
0x180034cd5  mov     eax, ds:(jpt_180034CDF - 180000000h)[rdx+rax*4]
0x180034cdc  add     rax, rdx
0x180034cdf  jmp     rax; switch jump
0x180034ce5  lea     rax, aSpapiEInvalidC_0; jumptable 0000000180034CDF case -2146500090
0x180034cec  retn
0x180034cee  lea     rax, aSpapiEDevinstA; jumptable 0000000180034CDF case -2146500089
0x180034cf5  retn
0x180034cf7  lea     rax, aSpapiEDevinfoN; jumptable 0000000180034CDF case -2146500088
0x180034cfe  retn
0x180034d00  lea     rax, aSpapiEInvalidR; jumptable 0000000180034CDF case -2146500087
0x180034d07  retn
0x180034d09  lea     rax, aSpapiENoInf; jumptable 0000000180034CDF case -2146500086
0x180034d10  retn
0x180034d12  lea     rax, aSpapiENoSuchDe; jumptable 0000000180034CDF case -2146500085
0x180034d19  retn
0x180034d1b  lea     rax, aSpapiECantLoad; jumptable 0000000180034CDF case -2146500084
0x180034d22  retn
0x180034d24  lea     rax, aSpapiEInvalidC; jumptable 0000000180034CDF case -2146500083
0x180034d2b  retn
0x180034d2d  lea     rax, aSpapiEDiDoDefa; jumptable 0000000180034CDF case -2146500082
0x180034d34  retn
0x180034d36  lea     rax, aSpapiEDiNofile; jumptable 0000000180034CDF case -2146500081
0x180034d3d  retn
0x180034d3f  lea     rax, aSpapiEInvalidH; jumptable 0000000180034CDF case -2146500080
0x180034d46  retn
0x180034d48  lea     rax, aSpapiENoDevice; jumptable 0000000180034CDF case -2146500079
0x180034d4f  retn
0x180034d51  lea     rax, aSpapiEDevinfoL; jumptable 0000000180034CDF case -2146500078
0x180034d58  retn
0x180034d5a  lea     rax, aSpapiEDevinfoD; "SPAPI_E_DEVINFO_DATA_LOCKED"
0x180034d61  retn
0x180034d63  add     ecx, 7FF0FDECh; switch 27 cases
0x180034d69  cmp     ecx, 1Ah
0x180034d6c  ja      def_180034CDF; jumptable 0000000180034CDF default case
0x180034d72  lea     rdx, __ImageBase
0x180034d79  movsxd  rax, ecx
0x180034d7c  mov     eax, ds:(jpt_180034D86 - 180000000h)[rdx+rax*4]
0x180034d83  add     rax, rdx
0x180034d86  jmp     rax; switch jump
0x180034d8c  lea     rax, aSpapiEDiBadPat; jumptable 0000000180034D86 case -2146500076
0x180034d93  retn
0x180034d95  lea     rax, aSpapiENoClassi; jumptable 0000000180034D86 case -2146500075
0x180034d9c  retn
0x180034d9e  lea     rax, aSpapiEFilequeu; jumptable 0000000180034D86 case -2146500074
0x180034da5  retn
0x180034da7  lea     rax, aSpapiEBadServi; jumptable 0000000180034D86 case -2146500073
0x180034dae  retn
0x180034db0  lea     rax, aSpapiENoClassD; jumptable 0000000180034D86 case -2146500072
0x180034db7  retn
0x180034db9  lea     rax, aSpapiENoAssoci; jumptable 0000000180034D86 case -2146500071
0x180034dc0  retn
0x180034dc2  lea     rax, aSpapiENoDefaul; jumptable 0000000180034D86 case -2146500070
0x180034dc9  retn
0x180034dcb  lea     rax, aSpapiEDeviceIn_1; jumptable 0000000180034D86 case -2146500069
0x180034dd2  retn
0x180034dd4  lea     rax, aSpapiEDeviceIn_0; jumptable 0000000180034D86 case -2146500068
0x180034ddb  retn
0x180034ddd  lea     rax, aSpapiEBadInter; jumptable 0000000180034D86 case -2146500067
0x180034de4  retn
0x180034de6  lea     rax, aSpapiENoSuchIn; jumptable 0000000180034D86 case -2146500066
0x180034ded  retn
0x180034def  lea     rax, aSpapiEInvalidR_0; jumptable 0000000180034D86 case -2146500065
0x180034df6  retn
0x180034df8  lea     rax, aSpapiEInvalidM; jumptable 0000000180034D86 case -2146500064
0x180034dff  retn
0x180034e01  lea     rax, aSpapiERemoteCo; jumptable 0000000180034D86 case -2146500063
0x180034e08  retn
0x180034e0a  lea     rax, aSpapiEMachineU; jumptable 0000000180034D86 case -2146500062
0x180034e11  retn
0x180034e13  lea     rax, aSpapiENoConfig; jumptable 0000000180034D86 case -2146500061
0x180034e1a  retn
0x180034e1c  lea     rax, aSpapiEInvalidP; jumptable 0000000180034D86 case -2146500060
0x180034e23  retn
0x180034e25  lea     rax, aSpapiENoSuchDe_0; jumptable 0000000180034D86 case -2146500059
0x180034e2c  retn
0x180034e2e  lea     rax, aSpapiEDiPostpr; jumptable 0000000180034D86 case -2146500058
0x180034e35  retn
0x180034e37  lea     rax, aSpapiEInvalidC_1; jumptable 0000000180034D86 case -2146500057
0x180034e3e  retn
0x180034e40  lea     rax, aSpapiENoCompat; jumptable 0000000180034D86 case -2146500056
0x180034e47  retn
0x180034e49  lea     rax, aSpapiENoDevice_0; jumptable 0000000180034D86 case -2146500055
0x180034e50  retn
0x180034e52  lea     rax, aSpapiEInvalidI; jumptable 0000000180034D86 case -2146500054
0x180034e59  retn
0x180034e5b  lea     rax, aSpapiEDiDontIn; jumptable 0000000180034D86 case -2146500053
0x180034e62  retn
0x180034e64  lea     rax, aSpapiEInvalidF; jumptable 0000000180034D86 case -2146500052
0x180034e6b  retn
0x180034e6d  lea     rax, aSpapiENonWindo_0; jumptable 0000000180034D86 case -2146500051
0x180034e74  retn
0x180034e76  lea     rax, aSpapiENonWindo; jumptable 0000000180034D86 case -2146500050
0x180034e7d  retn
0x180034e7f  lea     rax, aSpapiENoCatalo; "SPAPI_E_NO_CATALOG_FOR_OEM_INF"
0x180034e86  retn
0x180034e88  mov     eax, 800F0300h
0x180034e8d  cmp     ecx, eax
0x180034e8f  jg      loc_180034FD2
0x180034e95  jz      loc_180034FC9
0x180034e9b  add     ecx, 7FF0FDD0h; switch 29 cases
0x180034ea1  cmp     ecx, 1Ch
0x180034ea4  ja      def_180034CDF; jumptable 0000000180034CDF default case
0x180034eaa  lea     rdx, __ImageBase
0x180034eb1  movsxd  rax, ecx
0x180034eb4  mov     eax, ds:(jpt_180034EBE - 180000000h)[rdx+rax*4]
0x180034ebb  add     rax, rdx
0x180034ebe  jmp     rax; switch jump
0x180034ec4  lea     rax, aSpapiEDevinsta; jumptable 0000000180034EBE case -2146500048
0x180034ecb  retn
0x180034ecd  lea     rax, aSpapiENotDisab; jumptable 0000000180034EBE case -2146500047
0x180034ed4  retn
0x180034ed6  lea     rax, aSpapiECantRemo; jumptable 0000000180034EBE case -2146500046
0x180034edd  retn
0x180034edf  lea     rax, aSpapiEInvalidT; jumptable 0000000180034EBE case -2146500045
0x180034ee6  retn
0x180034ee8  lea     rax, aSpapiEDriverNo; jumptable 0000000180034EBE case -2146500044
0x180034eef  retn
0x180034ef1  lea     rax, aSpapiEInWow64; jumptable 0000000180034EBE case -2146500043
0x180034ef8  retn
0x180034efa  lea     rax, aSpapiESetSyste; jumptable 0000000180034EBE case -2146500042
0x180034f01  retn
0x180034f03  lea     rax, aSpapiEIncorrec; jumptable 0000000180034EBE case -2146500041
0x180034f0a  retn
0x180034f0c  lea     rax, aSpapiESceDisab; jumptable 0000000180034EBE case -2146500040
0x180034f13  retn
0x180034f15  lea     rax, aSpapiEUnknownE; jumptable 0000000180034EBE case -2146500039
0x180034f1c  retn
0x180034f1e  lea     rax, aSpapiEPnpRegis; jumptable 0000000180034EBE case -2146500038
0x180034f25  retn
0x180034f27  lea     rax, aSpapiERemoteRe; jumptable 0000000180034EBE case -2146500037
0x180034f2e  retn
0x180034f30  lea     rax, aSpapiENotAnIns; jumptable 0000000180034EBE case -2146500036
0x180034f37  retn
0x180034f39  lea     rax, aSpapiEInfInUse; jumptable 0000000180034EBE case -2146500035
0x180034f40  retn
0x180034f42  lea     rax, aSpapiEDiFuncti; jumptable 0000000180034EBE case -2146500034
0x180034f49  retn
0x180034f4b  lea     rax, aSpapiENoAuthen; jumptable 0000000180034EBE case -2146500033
0x180034f52  retn
0x180034f54  lea     rax, aSpapiEAuthenti_1; jumptable 0000000180034EBE case -2146500032
0x180034f5b  retn
0x180034f5d  lea     rax, aSpapiEAuthenti_2; jumptable 0000000180034EBE case -2146500031
0x180034f64  retn
0x180034f66  lea     rax, aSpapiEAuthenti; jumptable 0000000180034EBE case -2146500030
0x180034f6d  retn
0x180034f6f  lea     rax, aSpapiEAuthenti_0; jumptable 0000000180034EBE case -2146500029
0x180034f76  retn
0x180034f78  lea     rax, aSpapiESignatur; jumptable 0000000180034EBE case -2146500028
0x180034f7f  retn
0x180034f81  lea     rax, aSpapiEOnlyVali; jumptable 0000000180034EBE case -2146500027
0x180034f88  retn
0x180034f8a  lea     rax, aSpapiEDeviceIn; jumptable 0000000180034EBE case -2146500026
0x180034f91  retn
0x180034f93  lea     rax, aSpapiEDriverSt; jumptable 0000000180034EBE case -2146500025
0x180034f9a  retn
0x180034f9c  lea     rax, aSpapiEDeviceIn_2; jumptable 0000000180034EBE case -2146500024
0x180034fa3  retn
0x180034fa5  lea     rax, aSpapiEDriverIn; jumptable 0000000180034EBE case -2146500023
0x180034fac  retn
0x180034fae  lea     rax, aSpapiEWrongInf_0; jumptable 0000000180034EBE case -2146500022
0x180034fb5  retn
0x180034fb7  lea     rax, aSpapiEFileHash; jumptable 0000000180034EBE case -2146500021
0x180034fbe  retn
0x180034fc0  lea     rax, aSpapiEDriverSt_0; jumptable 0000000180034EBE case -2146500020
0x180034fc7  retn
0x180034fc9  lea     rax, aSpapiEUnrecove; "SPAPI_E_UNRECOVERABLE_STACK_OVERFLOW"
0x180034fd0  retn
0x180034fd2  add     ecx, 7FF0F800h; switch 25 cases
0x180034fd8  cmp     ecx, 18h
0x180034fdb  ja      def_180034CDF; jumptable 0000000180034CDF default case
0x180034fe1  lea     rdx, __ImageBase
0x180034fe8  movsxd  rax, ecx
0x180034feb  mov     eax, ds:(jpt_180034FF5 - 180000000h)[rdx+rax*4]
0x180034ff2  add     rax, rdx
0x180034ff5  jmp     rax; switch jump
0x180034ffb  lea     rax, aCbsEInternalEr; jumptable 0000000180034FF5 case -2146498560
0x180035002  retn
0x180035004  lea     rax, aCbsENotInitial; jumptable 0000000180034FF5 case -2146498559
0x18003500b  retn
0x18003500d  lea     rax, aCbsEAlreadyIni; jumptable 0000000180034FF5 case -2146498558
0x180035014  retn
0x180035016  lea     rax, aCbsEInvalidPar; jumptable 0000000180034FF5 case -2146498557
0x18003501d  retn
0x18003501f  lea     rax, aCbsEOpenFailed; jumptable 0000000180034FF5 case -2146498556
0x180035026  retn
0x180035028  lea     rax, aCbsEInvalidPac; jumptable 0000000180034FF5 case -2146498555
0x18003502f  retn
0x180035031  lea     rax, aCbsEPending; jumptable 0000000180034FF5 case -2146498554
0x180035038  retn
0x18003503a  lea     rax, aCbsENotInstall; jumptable 0000000180034FF5 case -2146498553
0x180035041  retn
0x180035043  lea     rax, aCbsEImageNotAc; jumptable 0000000180034FF5 case -2146498552
0x18003504a  retn
0x18003504c  lea     rax, aCbsEArrayEleme; jumptable 0000000180034FF5 case -2146498551
0x180035053  retn
0x180035055  lea     rax, aCbsEReestablis; jumptable 0000000180034FF5 case -2146498550
0x18003505c  retn
0x18003505e  lea     rax, aCbsEPropertyNo; jumptable 0000000180034FF5 case -2146498549
0x180035065  retn
0x180035067  lea     rax, aCbsEUnknownUpd; jumptable 0000000180034FF5 case -2146498548
0x18003506e  retn
0x180035070  lea     rax, aCbsEManifestIn; jumptable 0000000180034FF5 case -2146498547
0x180035077  retn
0x180035079  lea     rax, aCbsEManifestVa; jumptable 0000000180034FF5 case -2146498546
0x180035080  retn
0x180035082  lea     rax, aCbsEManifestVa_4; jumptable 0000000180034FF5 case -2146498545
0x180035089  retn
0x18003508b  lea     rax, aCbsEManifestVa_2; jumptable 0000000180034FF5 case -2146498544
0x180035092  retn
0x180035094  lea     rax, aCbsEManifestVa_0; jumptable 0000000180034FF5 case -2146498543
0x18003509b  retn
0x18003509d  lea     rax, aCbsEManifestVa_1; jumptable 0000000180034FF5 case -2146498542
0x1800350a4  retn
0x1800350a6  lea     rax, aCbsEInvalidIns; jumptable 0000000180034FF5 case -2146498541
0x1800350ad  retn
0x1800350af  lea     rax, aCbsEInvalidCon; jumptable 0000000180034FF5 case -2146498540
0x1800350b6  retn
0x1800350b8  lea     rax, aCbsEInvalidCar; jumptable 0000000180034FF5 case -2146498539
0x1800350bf  retn
0x1800350c1  lea     rax, aCbsEDpxJobStat; jumptable 0000000180034FF5 case -2146498538
0x1800350c8  retn
0x1800350ca  lea     rax, aCbsEPackageDel; jumptable 0000000180034FF5 case -2146498537
0x1800350d1  retn
  ... truncated ...
```
