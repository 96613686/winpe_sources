# DripsBlockerTrackingHelper::EtwProfilerTypeName(_DXGKETW_PROFILER_TYPE,uint *)

- ea: `0x14033c1e4`
- end: `0x14033ebe5`
- name: `?EtwProfilerTypeName@DripsBlockerTrackingHelper@@KAPEAGW4_DXGKETW_PROFILER_TYPE@@PEAI@Z`
- size: `10753`
- prototype: `const wchar_t *__fastcall(int, _DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140310f6c`
- `0x14033bc7c`
- `0x14033bea8`
- `0x14033c0fc`

## callees

- `0x14033c1e4`

## string_xrefs

- `0x14033c2a1`: `DxgkCreateClose`
- `0x14033c316`: `DpiDispatchCreate`
- `0x14033c3cd`: `DxgkAcquireAdapterCoreSync`
- `0x14033c3af`: `DxgkOpenAdapter`
- `0x14033c391`: `DxgkCreateAllocation`
- `0x14033c409`: `DxgkOpenResource`
- `0x14033c45f`: `DxgkQueryAllocationResidency`
- `0x14033c46e`: `DxgkCreateDevice`
- `0x14033c531`: `DxgkCreateOverlay`
- `0x14033c540`: `DxgkUpdateOverlay`
- `0x14033c659`: `DxgkCreateContext`
- `0x14033c671`: `DxgkCreateSynchronizationObject`
- `0x14033c6f8`: `DxgkOpenSynchronizationObject`
- `0x14033c716`: `DxgkOpenKeyedMutex`
- `0x14033c707`: `DxgkCreateKeyedMutex`
- `0x14033c752`: `DxgkConfigureSharedResource`
- `0x14033c77f`: `DxgkCheckSharedResourceAccess`
- `0x14033c79d`: `DxgkCreateOutputDupl`
- `0x14033c7e8`: `DxgkCreateKeyedMutex2`
- `0x14033c820`: `DxgkOpenKeyedMutex2`
- `0x14033c8a7`: `DxgkOpenResourceFromNtHandle`
- `0x14033c898`: `DxgkOpenNtHandleFromName`
- `0x14033c901`: `DxgkOpenAdapterFromLuid`
- `0x14033c8f2`: `DxgkGetPathsModality`
- `0x14033c93d`: `DxgkOpenSyncObjectFromNtHandle`
- `0x14033c979`: `DxgkGetCachedHybridQueryValue`
- `0x14033c988`: `DxgkCacheHybridQueryValue`
- `0x14033c9c4`: `DxgkConfirmToken`
- `0x14033ca2d`: `DxgkSubmitCommand`
- `0x14033ca1e`: `DxgkCreateContextVirtual`
- `0x14033ca69`: `DxgkUpdateGpuVirtualAddress`
- `0x14033ca87`: `DxgkCreateSwapChain`
- `0x14033ca96`: `DxgkOpenSwapChain`
- `0x14033caf0`: `DxgkMakeResident`
- `0x14033cb0e`: `DxgkCreatePagingQueue`
- `0x14033cb59`: `DxgkInvalidateCache`
- `0x14033cbef`: `DxgkUpdateAllocationProperty`
- `0x14033cc1c`: `DxgkVmBusCreateChannel`
- `0x14033ccc1`: `DxgkGetPostCompositionCaps`
- `0x14033cd2a`: `DxgkCreateProtectedSession`
- `0x14033cd63`: `DxgkOpenProtectedSessionFromNtHandle`
- `0x14033cd72`: `DxgkCreateHwQueue`
- `0x14033cdae`: `DxgkCreateBundleObject`
- `0x14033cddb`: `DxgkSubmitCommandToHwQueue`
- `0x14033cdcc`: `DxgkOpenKeyedMutexFromNtHandle`
- `0x14033ce53`: `DxgkFunctionalizePathsModality`
- `0x14033ce44`: `DxgkPersistPathsModality`
- `0x14033ce71`: `DxgkFinalizePathsModality`
- `0x14033ce62`: `DxgkApplyPathsModality`
- `0x14033ce8f`: `DxgkUpdateGdiInfo`
- `0x14033ce80`: `DxgkEnumerateModesForPathsModality`
- `0x14033cea7`: `DxgkGetDisplayConfigBufferSizes`
- `0x14033ce9e`: `DxgkCompleteTopologyTransition`
- `0x14033cec8`: `DxgkQueryDisplayConfig`
- `0x14033cee6`: `DxgkConvertDisplayConfigToDevMode`
- `0x14033ced7`: `DxgkConvertPathsModalityToDisplayConfig`
- `0x14033cf3d`: `DxgkDisplayConfigDeviceInfo`
- `0x14033cf6a`: `DxgkGetMonitorDescriptor`
- `0x14033d03c`: `DxgkRemoveSurfaceFromSwapChain`
- `0x14033d069`: `DxgkOpenSyncObjectNtHandleFromName`
- `0x14033d087`: `DxgkCreateTrackedWorkload`
- `0x14033d078`: `DxgkOpenBundleObjectNtHandleFromName`
- `0x14033d0c3`: `DxgkTrimProcessCommitment`
- `0x14033d0b4`: `DxgkpProcessVSyncPhaseThread`
- `0x14033d168`: `DxgkCddCreate`
- `0x14033d22b`: `DxgkCddTerminateThread`
- `0x14033d258`: `DxgkCddSyncGPUAccess`
- `0x14033d267`: `DxgkCddCreateAllocation`
- `0x14033d294`: `DxgkCddGdiCommand`
- `0x14033d2c1`: `DxgkCddDrvStrokePath`
- `0x14033d2ee`: `DxgkCddDrvFillPath`
- `0x14033d2fd`: `DxgkCddDrvStrokeAndFillPath`
- `0x14033d366`: `DxgkCddOpenResource`
- `0x14033d3a2`: `DxgkCddUpdateGdiMem`
- `0x14033d393`: `DxgkCddCreateDeviceBitmap`
- `0x14033d3b1`: `DxgkCddAddCommand`
- `0x14033d474`: `DxgkCddSyncDxAccess`
- `0x14033d483`: `DxgkCddFlushCpuCache`
- `0x14033d49b`: `DxgkCddOpenResourceFromNtHandle`
- `0x14033d4e9`: `DxgkCddMakeResident`
- `0x14033d570`: `DpiDxgkDdiRemoveDevice`
- `0x14033d5a6`: `DpiDxgkDdiQueryDeviceDescriptor`
- `0x14033d69f`: `VidSchiDeferredVisibilityThread`
- `0x14033d708`: `DdiCreateDevice`
- `0x14033d6f9`: `DdiCreateAllocation`
- `0x14033d792`: `DdiCommitVidPn`
- `0x14033d7cb`: `DdiSubmitCommand`
- `0x14033d7b9`: `DdiUpdateActiveVidPnPresentPath`
- `0x14033d7da`: `DdiPreemptCommand`
- `0x14033d870`: `DdiRecommendFunctionalVidPn`
- `0x14033d8ac`: `DdiOpenAllocation`
- `0x14033d8f7`: `DdiUpdateOverlay`
- `0x14033d8e8`: `DdiCreateOverlay`
- `0x14033d933`: `DdiRecommendMonitorModes`
- `0x14033d96f`: `DdiCreateContext`
- `0x14033d960`: `DdiRecommendVidPnTopology`
- `0x14033da14`: `DdiCancelCommand`
- `0x14033dab9`: `DdiSubmitCommandVirtual`
- `0x14033dac8`: `DdiCreateProcess`
- `0x14033db4f`: `DdiValidateUpdateAllocationProperty`
- `0x14033db40`: `DdiUpdateMonitorLinkInfo`
- `0x14033db5e`: `DdiCreatePeriodicFrameNotification`
- `0x14033dba9`: `DdiSetTargetAnalogCopyProtection`
- `0x14033dc00`: `DdiGetPostCompositionCaps`
- `0x14033dc1e`: `DdiWriteVirtualFunctionConfig`
- `0x14033dc0f`: `DdiReadVirtualFunctionConfig`
- `0x14033dc3c`: `DdiReadVirtualFunctionConfigBlock`
- `0x14033dc2d`: `DdiWriteVirtualFunctionConfigBlock`
- `0x14033dcde`: `DdiCreateVirtualGpu`
- `0x14033dd56`: `DdiCreateProtectedSession`
- `0x14033dd74`: `DdiCreateHwQueue`
- `0x14033dd92`: `DdiSubmitCommandToHwQueue`
- `0x14033de46`: `DdiUpdateFlipQueueLog`
- `0x14033de7f`: `DdiSetPowerComponentFState`
- `0x14033dee8`: `DdiEndExclusiveAccess`
- `0x14033ded9`: `DdiBeginExclusiveAccess`
- `0x14033df33`: `DdiValidateSubmitCommand`
- `0x14033e020`: `DdiCreateMemoryBasis`
- `0x14033e15b`: `DmmInterfaceAcquriePinnedTargetMode`
- `0x14033e179`: `DmmInterfaceCompareTargetMode`
- `0x14033e1b5`: `DmmInterfaceGetNumPathsFromSource`
- `0x14033e1d3`: `DmmInterfaceGetPathSourceFromTarget`
- `0x14033e1c4`: `DmmInterfaceEnumPathTargetsFromSource`
- `0x14033e1f1`: `DmmInterfaceReleasePath`
- `0x14033e1e2`: `DmmInterfaceAcquirePath`
- `0x14033e20f`: `DmmInterfaceRemovePath`
- `0x14033e200`: `DmmInterfaceAddPath`
- `0x14033e21e`: `DmmInterfaceRemoveAllPaths`
- `0x14033e269`: `DmmInterfaceRecommendVidPnTopology`
- `0x14033e3b3`: `DmmInterfaceCreateVidPn`
- `0x14033e3d1`: `DmmInterfaceCreateVidPnCopy`
- `0x14033e3c2`: `DmmInterfaceCreateVidPnFromActive`
- `0x14033e40d`: `DmmInterfaceRemoveCopyProtection`
- `0x14033e42b`: `DmmInterfaceGetNumPaths`
- `0x14033e41c`: `DmmInterfaceGetPathImportance`
- `0x14033e43a`: `DmmInterfaceEnumPaths`
- `0x14033e4d0`: `DmmMiniportInterfaceCreateNewSourceMode`
- `0x14033e548`: `DmmMiniportInterfaceCreateNewTargetMode`
- `0x14033e5b1`: `DmmMiniportInterfaceCreateNewMonitorSourceMode`
- `0x14033e629`: `DmmMiniportInterfaceAcquireFirstMonitorDescriptor`
- `0x14033e61a`: `DmmMiniportInterfaceGetNumMonitorDescriptors`
- `0x14033e647`: `DmmMiniportInterfaceReleaseMonitorDescriptor`
- `0x14033e638`: `DmmMiniportInterfaceAcquireNextMonitorDescriptor`
- `0x14033e662`: `DmmMiniportInterfaceGetNumPathsFromSource`
- `0x14033e650`: `DmmMiniportInterfaceGetNumPaths`
- `0x14033e680`: `DmmMiniportInterfaceGetPathSourceFromTarget`
- `0x14033e671`: `DmmMiniportInterfaceEnumPathTargetsFromSource`
- `0x14033e69b`: `DmmMiniportInterfaceAcquireFirstPath`
- `0x14033e689`: `DmmMiniportInterfaceAcquirePath`
- `0x14033e6b9`: `DmmMiniportInterfaceUpdatePathSupport`
- `0x14033e6aa`: `DmmMiniportInterfaceAcquireNextPath`
- `0x14033e6d4`: `DmmMiniportInterfaceCreateNewPath`
- `0x14033e6c2`: `DmmMiniportInterfaceReleasePath`
- `0x14033e6e3`: `DmmMiniportInterfaceAddPath`
- `0x14033e71c`: `DmmMiniportInterfaceCreateNewSourceModeSet`
- `0x14033e767`: `DmmMiniportInterfaceCreateNewTargetModeSet`
- `0x14033e7b2`: `DmmMiniportInterfaceGetMonitorDescriptorSet`
- `0x14033e7df`: `DmmMiniportInterfaceRemovePath`
- `0x14033e8cf`: `FlushAllocationCache`
- `0x14033e8ed`: `MakeProcessIdleToFlushTlb`
- `0x14033e90b`: `GdiRenderDuringCS`
- `0x14033e8fc`: `UpdateGpuVirtualAddressSystemCommand`
- `0x14033e947`: `HoldAdapterLockThread`
- `0x14033e965`: `DdiCreateAllocation2`
- `0x14033ea11`: `DxgkOutputDuplDXGDXGIKEYEDMUTEXOpenLocalMutex`
- `0x14033e9c6`: `DxgkDdiMiracastCreateContext`
- `0x14033ea7e`: `UmdDriverCreateMiracastContext`
- `0x14033ebbf`: `DxgkSharedKeyedMutexObjectObDeleteProcedure`
- `0x14033ebce`: `DxgkSharedAllocationObDeleteProcedure`
- `0x14033eba1`: `DxgkSharedProtectedSessionObDeleteProcedure`
- `0x14033ebb0`: `DxgkSharedSyncObjectObDeleteProcedure`
- `0x14033eb92`: `DxgkSharedBundleObjectObDeleteProcedure`
- `0x14033d0f0`: `DxgkVailPromoteCompositionSurface`

## pseudocode

```c
const wchar_t *__fastcall DripsBlockerTrackingHelper::EtwProfilerTypeName(int a1, _DWORD *a2)
{
  const wchar_t *result; // rax
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx

  if ( a1 <= 5005 )
  {
    if ( a1 == 5005 )
    {
      *a2 = 21;
      return L"DdiDestroyAllocation";
    }
    if ( a1 > 2147 )
    {
      if ( a1 > 2239 )
      {
        if ( a1 > 4000 )
        {
          if ( a1 > 5000 )
          {
            v14 = a1 - 5001;
            if ( !v14 )
            {
              *a2 = 16;
              return L"DdiCreateDevice";
            }
            v15 = v14 - 1;
            if ( !v15 )
            {
              *a2 = 20;
              return L"DdiCreateAllocation";
            }
            v16 = v15 - 1;
            if ( !v16 )
            {
              *a2 = 22;
              return L"DdiDescribeAllocation";
            }
            if ( v16 == 1 )
            {
              *a2 = 35;
              return L"DdiGetStandardAllocationDriverData";
            }
            goto LABEL_736;
          }
          if ( a1 == 5000 )
          {
            *a2 = 20;
            return L"DdiQueryAdapterInfo";
          }
          else
          {
            switch ( a1 )
            {
              case 4001:
                *a2 = 22;
                result = L"DpiDxgkDdiStartDevice";
                break;
              case 4002:
                *a2 = 21;
                result = L"DpiDxgkDdiStopDevice";
                break;
              case 4003:
                *a2 = 23;
                result = L"DpiDxgkDdiRemoveDevice";
                break;
              case 4004:
                *a2 = 28;
                result = L"DpiDxgkDdiDispatchIoRequest";
                break;
              case 4005:
                *a2 = 30;
                result = L"DpiDxgkDdiQueryChildRelations";
                break;
              case 4006:
                *a2 = 27;
                result = L"DpiDxgkDdiQueryChildStatus";
                break;
              case 4007:
                result = L"DpiDxgkDdiQueryDeviceDescriptor";
                goto LABEL_743;
              case 4008:
                *a2 = 24;
                result = L"DpiDxgkDdiSetPowerState";
                break;
              case 4009:
                *a2 = 26;
                result = L"DpiDxgkDdiNotifyAcpiEvent";
                break;
              case 4010:
                *a2 = 17;
                result = L"DpiDxgkDdiUnload";
                break;
              case 4011:
                *a2 = 28;
                result = L"DpiDxgkDdiControlEtwLogging";
                break;
              case 4012:
                *a2 = 25;
                result = L"DpiDxgkDdiQueryInterface";
                break;
              case 4013:
                *a2 = 13;
                result = L"DpiDpcForIsr";
                break;
              case 4014:
                *a2 = 30;
                result = L"DpiFdoMessageInterruptRoutine";
                break;
              case 4015:
                *a2 = 25;
                result = L"VidSchDdiNotifyInterrupt";
                break;
              case 4016:
                result = L"VidSchiCallNotifyInterruptAtISR";
                goto LABEL_743;
              case 4017:
                *a2 = 51;
                result = L"DpiDxgkDdiStopDeviceAndReleasePostDisplayOwnership";
                break;
              case 4018:
                *a2 = 30;
                result = L"DpiDxgkDdiGetChildContainerId";
                break;
              case 4019:
                *a2 = 35;
                result = L"DpiDxgkDdiDdiNotifySurpriseRemoval";
                break;
              case 4020:
                *a2 = 27;
                result = L"DpiFdoThermalActiveCooling";
                break;
              case 4021:
                *a2 = 28;
                result = L"DpiFdoThermalPassiveCooling";
                break;
              case 4022:
                *a2 = 26;
                result = L"DxgkCbIndicateChildStatus";
                break;
              case 4023:
                *a2 = 19;
                result = L"DpiPNPPowerRelated";
                break;
              case 4024:
                result = L"VidSchiDeferredVisibilityThread";
                goto LABEL_743;
              default:
                goto LABEL_736;
            }
          }
        }
        else if ( a1 == 4000 )
        {
          *a2 = 20;
          return L"DpiDxgkDdiAddDevice";
        }
        else
        {
          switch ( a1 )
          {
            case 3000:
              *a2 = 14;
              result = L"DxgkCddCreate";
              break;
            case 3001:
              *a2 = 15;
              result = L"DxgkCddDestroy";
              break;
            case 3002:
              *a2 = 14;
              result = L"DxgkCddEnable";
              break;
            case 3003:
              *a2 = 15;
              result = L"DxgkCddDisable";
              break;
            case 3004:
              *a2 = 26;
              result = L"DxgkCddGetDisplayModeList";
              break;
            case 3005:
              *a2 = 21;
              result = L"DxgkCddGetDriverCaps";
              break;
            case 3006:
              *a2 = 12;
              result = L"DxgkCddLock";
              break;
            case 3007:
              *a2 = 14;
              result = L"DxgkCddUnlock";
              break;
            case 3008:
              *a2 = 15;
              result = L"DxgkCddPresent";
              break;
            case 3009:
              *a2 = 20;
              result = L"DxgkCddSetGammaRamp";
              break;
            case 3010:
              *a2 = 18;
              result = L"DxgkCddSetPalette";
              break;
            case 3011:
              *a2 = 26;
              result = L"DxgkCddSetPointerPosition";
              break;
            case 3012:
              *a2 = 23;
              result = L"DxgkCddSetPointerShape";
              break;
            case 3013:
              *a2 = 23;
              result = L"DxgkCddTerminateThread";
              break;
            case 3014:
              *a2 = 17;
              result = L"DxgkCddSetOrigin";
              break;
            case 3015:
              *a2 = 33;
              result = L"DxgkCddWaitForVerticalBlankEvent";
              break;
            case 3016:
              *a2 = 21;
              result = L"DxgkCddSyncGPUAccess";
              break;
            case 3017:
              *a2 = 24;
              result = L"DxgkCddCreateAllocation";
              break;
            case 3018:
              *a2 = 25;
              result = L"DxgkCddDestroyAllocation";
              break;
            case 3019:
              *a2 = 20;
              result = L"DxgkCddBltToPrimary";
              break;
            case 3020:
              *a2 = 18;
              result = L"DxgkCddGdiCommand";
              break;
            case 3021:
              *a2 = 17;
              result = L"DxgkCddDrvBitBlt";
              break;
            case 3022:
              *a2 = 20;
              result = L"DxgkCddDrvColorFill";
              break;
            case 3023:
              *a2 = 21;
              result = L"DxgkCddDrvStrokePath";
              break;
            case 3024:
              *a2 = 21;
              result = L"DxgkCddDrvAlphaBlend";
              break;
            case 3025:
              *a2 = 17;
              result = L"DxgkCddDrvLineTo";
              break;
            case 3026:
              *a2 = 19;
              result = L"DxgkCddDrvFillPath";
              break;
            case 3027:
              *a2 = 28;
              result = L"DxgkCddDrvStrokeAndFillPath";
              break;
            case 3028:
              *a2 = 24;
              result = L"DxgkCddDrvStretchBltROP";
              break;
            case 3029:
              *a2 = 17;
              result = L"DxgkCddDrvPlgBlt";
              break;
            case 3030:
              *a2 = 21;
              result = L"DxgkCddDrvStretchBlt";
              break;
            case 3031:
              *a2 = 18;
              result = L"DxgkCddDrvTextOut";
              break;
            case 3032:
              *a2 = 23;
              result = L"DxgkCddDrvGradientFill";
              break;
            case 3033:
              *a2 = 25;
              result = L"DxgkCddDrvTransparentBlt";
              break;
            case 3034:
              *a2 = 20;
              result = L"DxgkCddOpenResource";
              break;
            case 3035:
              *a2 = 25;
              result = L"DxgkCddQueryResourceInfo";
              break;
            case 3036:
              *a2 = 28;
              result = L"DxgkCddSubmitPresentHistory";
              break;
            case 3037:
              *a2 = 26;
              result = L"DxgkCddCreateDeviceBitmap";
              break;
            case 3038:
              *a2 = 20;
              result = L"DxgkCddUpdateGdiMem";
              break;
            case 3039:
              *a2 = 18;
              result = L"DxgkCddAddCommand";
              break;
            case 3040:
              *a2 = 18;
              result = L"DxgkCddEnableLite";
              break;
            case 3041:
              *a2 = 26;
              result = L"DxgkCddAssertModeInternal";
              break;
            case 3042:
              *a2 = 25;
              result = L"DxgkCddSetLiteModeChange";
              break;
            case 3043:
              *a2 = 26;
              result = L"DxgkCddPresentDisplayOnly";
              break;
            case 3044:
              *a2 = 24;
              result = L"DxgkCddSignalGdiContext";
              break;
            case 3045:
              *a2 = 22;
              result = L"DxgkCddWaitGdiContext";
              break;
            case 3046:
              *a2 = 23;
              result = L"DxgkCddSignalDxContext";
              break;
            case 3047:
              *a2 = 21;
              result = L"DxgkCddWaitDxContext";
              break;
            case 3048:
              *a2 = 22;
              result = L"DxgkCddStartDxInterop";
              break;
            case 3049:
              *a2 = 20;
              result = L"DxgkCddEndDxInterop";
              break;
            case 3050:
              *a2 = 23;
              result = L"DxgkCddAddD3DDirtyRect";
              break;
            case 3051:
              *a2 = 26;
              result = L"DxgkCddDxGdiInteropFailed";
              break;
            case 3052:
              *a2 = 20;
              result = L"DxgkCddSyncDxAccess";
              break;
            case 3053:
              *a2 = 21;
              result = L"DxgkCddFlushCpuCache";
              break;
            case 3054:
              *a2 = 20;
              result = L"DxgkCddLockMdlPages";
              break;
            case 3055:
              result = L"DxgkCddOpenResourceFromNtHandle";
              goto LABEL_743;
            case 3056:
              *a2 = 37;
              result = L"DxgkCddQueryResourceInfoFromNtHandle";
              break;
            case 3057:
              *a2 = 22;
              result = L"DxgkCddUnlockMdlPages";
              break;
            case 3058:
              *a2 = 23;
              result = L"DxgkCddTrimStagingSize";
              break;
            case 3059:
              *a2 = 27;
              result = L"DxgkCddReuseDeviceBitmapEx";
              break;
            case 3060:
              *a2 = 20;
              result = L"DxgkCddMakeResident";
              break;
            case 3061:
              *a2 = 13;
              result = L"DxgkCddEvict";
              break;
            default:
              goto LABEL_736;
          }
        }
      }
      else if ( a1 == 2239 )
      {
        *a2 = 23;
        return L"DxgkNativeFencePresent";
      }
      else
      {
        switch ( a1 )
        {
          case 2148:
            *a2 = 27;
            result = L"DxgkCreateProtectedSession";
            break;
          case 2149:
            *a2 = 28;
            result = L"DxgkDestroyProtectedSession";
            break;
          case 2150:
            result = L"DxgkQueryProtectedSessionStatus";
            goto LABEL_743;
          case 2151:
            *a2 = 42;
            result = L"DxgkQueryProtectedSessionInfoFromNtHandle";
            break;
          case 2152:
            *a2 = 37;
            result = L"DxgkOpenProtectedSessionFromNtHandle";
            break;
          case 2153:
            *a2 = 18;
            result = L"DxgkCreateHwQueue";
            break;
          case 2154:
            *a2 = 19;
            result = L"DxgkDestroyHwQueue";
            break;
          case 2155:
            *a2 = 35;
            result = L"DxgkSetProcessDeviceRemovalSupport";
            break;
          case 2156:
            *a2 = 35;
            result = L"DxgkGetProcessDeviceRemovalSupport";
            break;
          case 2157:
            *a2 = 23;
            result = L"DxgkCreateBundleObject";
            break;
          case 2158:
            *a2 = 24;
            result = L"DxgkExtractBundleObject";
            break;
          case 2159:
            *a2 = 31;
            result = L"DxgkOpenKeyedMutexFromNtHandle";
            break;
          case 2160:
            *a2 = 27;
            result = L"DxgkSubmitCommandToHwQueue";
            break;
          case 2161:
            *a2 = 37;
            result = L"DxgkSubmitSignalSyncObjectsToHwQueue";
            break;
          case 2162:
            *a2 = 38;
            result = L"DxgkSubmitWaitForSyncObjectsToHwQueue";
            break;
          case 2163:
            *a2 = 30;
            result = L"DxgkPresentMultiPlaneOverlay2";
            break;
          case 2164:
            *a2 = 30;
            result = L"DxgkPresentMultiPlaneOverlay3";
            break;
          case 2165:
            *a2 = 33;
            result = L"DxgkInvalidateMonitorConnections";
            break;
          case 2166:
            *a2 = 27;
            result = L"DxgkGetMonitorDeviceObject";
            break;
          case 2167:
            *a2 = 25;
            result = L"DxgkPersistPathsModality";
            break;
          case 2168:
            *a2 = 31;
            result = L"DxgkFunctionalizePathsModality";
            break;
          case 2169:
            *a2 = 23;
            result = L"DxgkApplyPathsModality";
            break;
          case 2170:
            *a2 = 26;
            result = L"DxgkFinalizePathsModality";
            break;
          case 2171:
            *a2 = 35;
            result = L"DxgkEnumerateModesForPathsModality";
            break;
          case 2172:
            *a2 = 18;
            result = L"DxgkUpdateGdiInfo";
            break;
          case 2173:
            *a2 = 31;
            result = L"DxgkCompleteTopologyTransition";
            break;
          case 2174:
            result = L"DxgkGetDisplayConfigBufferSizes";
            goto LABEL_743;
          case 2175:
            *a2 = 28;
            result = L"DxgkIsSourceInHardwareClone";
            break;
          case 2176:
            *a2 = 23;
            result = L"DxgkQueryDisplayConfig";
            break;
          case 2177:
            *a2 = 40;
            result = L"DxgkConvertPathsModalityToDisplayConfig";
            break;
          case 2178:
            *a2 = 34;
            result = L"DxgkConvertDisplayConfigToDevMode";
            break;
          case 2179:
            *a2 = 33;
            result = L"DxgkHandleForceProjectionMonitor";
            break;
          case 2180:
            *a2 = 26;
            result = L"DxgkIsPortraitFirstTarget";
            break;
          case 2181:
            *a2 = 18;
            result = L"DxgkDesktopSwitch";
            break;
          case 2182:
            result = L"DxgkIsVidPnSourceOwnerExclusive";
            goto LABEL_743;
          case 2183:
            *a2 = 17;
            result = L"DxgkDisplayOnOff";
            break;
          case 2184:
            *a2 = 28;
            result = L"DxgkDisplayConfigDeviceInfo";
            break;
          case 2185:
            *a2 = 25;
            result = L"DxgkGetAdapterDeviceDesc";
            break;
          case 2186:
            *a2 = 27;
            result = L"DxgkGetMonitorInternalInfo";
            break;
          case 2187:
            *a2 = 25;
            result = L"DxgkGetMonitorDescriptor";
            break;
          case 2188:
            *a2 = 28;
            result = L"DxgkBeginTopologyTransition";
            break;
          case 2189:
            *a2 = 24;
            result = L"DxgkFlushPresentHistory";
            break;
          case 2190:
            *a2 = 39;
            result = L"DxgkSignalSynchronizationObjectFromGpu";
            break;
          case 2191:
            *a2 = 40;
            result = L"DxgkSignalSynchronizationObjectFromGpu2";
            break;
          case 2192:
            *a2 = 29;
            result = L"DxgkGetDWMVerticalBlankEvent";
            break;
          case 2193:
            *a2 = 28;
            result = L"DxgkGetDpiOverrideForSource";
            break;
          case 2194:
            *a2 = 22;
            result = L"DxgkProcessLockScreen";
            break;
          case 2195:
            *a2 = 23;
            result = L"DxgkStatusChangeNotify";
            break;
          case 2196:
            *a2 = 21;
            result = L"DxgkSessionConnected";
            break;
          case 2197:
            *a2 = 27;
            result = L"DxgkPreSessionDisconnected";
            break;
          case 2198:
            *a2 = 24;
            result = L"DxgkSessionDisconnected";
            break;
          case 2199:
            *a2 = 23;
            result = L"DxgkSessionReconnected";
            break;
          case 2200:
            *a2 = 26;
            result = L"DxgkAddSurfaceToSwapChain";
            break;
          case 2201:
            *a2 = 31;
            result = L"DxgkRemoveSurfaceFromSwapChain";
            break;
          case 2202:
            *a2 = 30;
            result = L"DxgkUnOrderedPresentSwapChain";
            break;
          case 2203:
            *a2 = 19;
            result = L"DxgkGetProcessList";
            break;
          case 2204:
            *a2 = 35;
            result = L"DxgkOpenSyncObjectNtHandleFromName";
            break;
          case 2205:
            *a2 = 37;
            result = L"DxgkOpenBundleObjectNtHandleFromName";
            break;
          case 2206:
            *a2 = 26;
            result = L"DxgkCreateTrackedWorkload";
            break;
          case 2207:
            *a2 = 27;
            result = L"DxgkDestroyTrackedWorkload";
            break;
          case 2208:
            *a2 = 20;
            result = L"DxgkDuplicateHandle";
            break;
          case 2209:
            *a2 = 29;
            result = L"DxgkpProcessVSyncPhaseThread";
            break;
          case 2210:
            *a2 = 26;
            result = L"DxgkTrimProcessCommitment";
            break;
          case 2211:
            *a2 = 29;
            result = L"DxgkpProcessStatusChangeWork";
            break;
          case 2214:
            *a2 = 24;
            result = L"DxgkRegisterVailProcess";
            break;
          case 2215:
            *a2 = 34;
            result = L"DxgkVailPromoteCompositionSurface";
            break;
          case 2216:
            *a2 = 16;
            result = L"DxgkVailConnect";
            break;
          case 2217:
            *a2 = 18;
            result = L"DxgkVailDisonnect";
            break;
          case 2218:
            *a2 = 26;
            result = L"DxgkVmBusSendAsyncMessage";
            break;
          default:
            goto LABEL_736;
        }
      }
    }
    else
    {
      if ( a1 == 2147 )
      {
        *a2 = 22;
        return L"DxgkPresentRedirected";
      }
      if ( a1 > 2066 )
      {
        switch ( a1 )
        {
          case 2067:
            *a2 = 20;
            result = L"DxgkOpenKeyedMutex2";
            break;
          case 2068:
            *a2 = 23;
            result = L"DxgkAcquireKeyedMutex2";
            break;
          case 2069:
            *a2 = 23;
            result = L"DxgkReleaseKeyedMutex2";
            break;
          case 2070:
            *a2 = 21;
            result = L"DxgkOfferAllocations";
            break;
          case 2071:
            *a2 = 23;
            result = L"DxgkReclaimAllocations";
            break;
          case 2072:
            *a2 = 27;
            result = L"DxgkOutputDuplReleaseFrame";
            break;
          case 2073:
            *a2 = 34;
            result = L"DxgkQueryResourceInfoFromNtHandle";
            break;
          case 2074:
            *a2 = 17;
            result = L"DxgkShareObjects";
            break;
          case 2075:
            *a2 = 25;
            result = L"DxgkOpenNtHandleFromName";
            break;
          case 2076:
            *a2 = 29;
            result = L"DxgkOpenResourceFromNtHandle";
            break;
          case 2077:
            *a2 = 25;
            result = L"DxgkSetVidPnSourceOwner1";
            break;
          case 2078:
            *a2 = 17;
            result = L"DxgkEnumAdapters";
            break;
          case 2079:
            *a2 = 27;
            result = L"DxgkPinDirectFlipResources";
            break;
          case 2080:
            *a2 = 29;
            result = L"DxgkUnpinDirectFlipResources";
            break;
          case 2081:
            *a2 = 21;
            result = L"DxgkGetPathsModality";
            break;
          case 2082:
            *a2 = 24;
            result = L"DxgkOpenAdapterFromLuid";
            break;
          case 2083:
            *a2 = 31;
            result = L"DxgkWaitForVerticalBlankEvent2";
            break;
          case 2084:
            *a2 = 42;
            result = L"DxgkSetContextInProcessSchedulingPriority";
            break;
          case 2085:
            *a2 = 42;
            result = L"DxgkGetContextInProcessSchedulingPriority";
            break;
          case 2086:
            *a2 = 31;
            result = L"DxgkOpenSyncObjectFromNtHandle";
            break;
          case 2087:
            *a2 = 31;
            result = L"DxgkNotifyProcessFreezeCallout";
            break;
          case 2088:
            *a2 = 33;
            result = L"DxgkGetSharedResourceAdapterLuid";
            break;
          case 2089:
            *a2 = 21;
            result = L"DxgkSetStereoEnabled";
            break;
          case 2090:
            *a2 = 30;
            result = L"DxgkGetCachedHybridQueryValue";
            break;
          case 2091:
            *a2 = 26;
            result = L"DxgkCacheHybridQueryValue";
            break;
          case 2092:
            *a2 = 29;
            result = L"DxgkPresentMultiPlaneOverlay";
            break;
          case 2093:
            *a2 = 34;
            result = L"DxgkCheckMultiplaneOverlaySupport";
            break;
          case 2094:
            *a2 = 27;
            result = L"DxgkSetIndependentFlipMode";
            break;
          case 2095:
            *a2 = 17;
            result = L"DxgkConfirmToken";
            break;
          case 2096:
            *a2 = 29;
            result = L"DxgkNotifyProcessThawCallout";
            break;
          case 2097:
            *a2 = 25;
            result = L"DxgkSetPresenterViewMode";
            break;
          case 2098:
            *a2 = 29;
            result = L"DxgkReserveGpuVirtualAddress";
            break;
          case 2099:
            *a2 = 26;
            result = L"DxgkFreeGpuVirtualAddress";
            break;
          case 2100:
            *a2 = 25;
            result = L"DxgkMapGpuVirtualAddress";
            break;
          case 2101:
            *a2 = 25;
            result = L"DxgkCreateContextVirtual";
            break;
          case 2102:
            *a2 = 18;
            result = L"DxgkSubmitCommand";
            break;
          case 2103:
            *a2 = 10;
            result = L"DxgkLock2";
            break;
          case 2104:
            *a2 = 12;
            result = L"DxgkUnlock2";
            break;
          case 2105:
            *a2 = 23;
            result = L"DxgkDestroyAllocation2";
            break;
          case 2106:
            *a2 = 28;
            result = L"DxgkUpdateGpuVirtualAddress";
            break;
          case 2107:
            *a2 = 35;
            result = L"DxgkCheckMultiplaneOverlaySupport2";
            break;
          case 2108:
            *a2 = 20;
            result = L"DxgkCreateSwapChain";
            break;
          case 2109:
            *a2 = 18;
            result = L"DxgkOpenSwapChain";
            break;
          case 2110:
            *a2 = 21;
            result = L"DxgkDestroySwapChain";
            break;
          case 2111:
            *a2 = 21;
            result = L"DxgkAcquireSwapChain";
            break;
          case 2112:
            *a2 = 21;
            result = L"DxgkReleaseSwapChain";
            break;
          case 2113:
            *a2 = 21;
            result = L"DxgkAbandonSwapChain";
            break;
          case 2114:
            *a2 = 28;
            result = L"DxgkSetDodIndirectSwapchain";
            break;
          case 2115:
            *a2 = 17;
            result = L"DxgkMakeResident";
            break;
          case 2116:
            *a2 = 10;
            result = L"DxgkEvict";
            break;
          case 2117:
            *a2 = 22;
            result = L"DxgkCreatePagingQueue";
            break;
          case 2118:
            *a2 = 23;
            result = L"DxgkDestroyPagingQueue";
            break;
          case 2119:
            *a2 = 25;
            result = L"DxgkQueryVideoMemoryInfo";
            break;
          case 2120:
            *a2 = 33;
            result = L"DxgkChangeVideoMemoryReservation";
            break;
          case 2121:
            *a2 = 28;
            result = L"DxgkGetSetSwapChainMetadata";
            break;
          case 2122:
            *a2 = 20;
            result = L"DxgkInvalidateCache";
            break;
          case 2123:
            *a2 = 40;
            result = L"DxgkGetResourcePresentPrivateDriverData";
            break;
          case 2124:
            *a2 = 24;
            result = L"DxgkSetStablePowerState";
            break;
          case 2125:
            *a2 = 26;
            result = L"DxgkQueryClockCalibration";
            break;
          case 2126:
            *a2 = 29;
            result = L"QueryVidPnExclusiveOwnership";
            break;
          case 2127:
            *a2 = 26;
            result = L"DxgkAdjustFullscreenGamma";
            break;
          case 2128:
            *a2 = 29;
            result = L"DxgkWin32kSetPointerPosition";
            break;
          case 2129:
            *a2 = 26;
            result = L"DxgkWin32kSetPointerShape";
            break;
          case 2130:
            *a2 = 31;
            result = L"DxgkSetVidPnSourceHwProtection";
            break;
          case 2131:
            *a2 = 22;
            result = L"DxgkMarkDeviceAsError";
            break;
          case 2132:
            *a2 = 29;
            result = L"DxgkUpdateAllocationProperty";
            break;
          case 2133:
            *a2 = 16;
            result = L"DxgkSetFSEBlock";
            break;
          case 2134:
            *a2 = 18;
            result = L"DxgkQueryFSEBlock";
            break;
          case 2135:
            *a2 = 23;
            result = L"DxgkVmBusCreateChannel";
            break;
          case 2136:
            *a2 = 25;
            result = L"DxgkVmBusSendSyncMessage";
            break;
          case 2137:
            *a2 = 24;
            result = L"DxgkVmBusProcessMessage";
            break;
          case 2138:
            *a2 = 26;
            result = L"DxgkGetAllocationPriority";
            break;
          case 2139:
            *a2 = 23;
            result = L"DxgkSetYieldPercentage";
            break;
          case 2140:
            *a2 = 37;
            result = L"DxgkSetProcessSchedulingPriorityBand";
            break;
          case 2141:
            *a2 = 26;
            result = L"DxgkSetMemoryBudgetTarget";
            break;
          case 2142:
            *a2 = 23;
            result = L"DxgkGetYieldPercentage";
            break;
          case 2143:
            *a2 = 37;
            result = L"DxgkGetProcessSchedulingPriorityBand";
            break;
          case 2144:
            *a2 = 26;
            result = L"DxgkGetMemoryBudgetTarget";
            break;
          case 2145:
            *a2 = 19;
            result = L"DxgkGetOverlayCaps";
            break;
          case 2146:
            *a2 = 27;
            result = L"DxgkGetPostCompositionCaps";
            break;
          default:
            goto LABEL_736;
        }
      }
      else
      {
        if ( a1 == 2066 )
        {
          *a2 = 22;
          return L"DxgkCreateKeyedMutex2";
        }
        if ( a1 > 2025 )
        {
          switch ( a1 )
          {
            case 2026:
              *a2 = 30;
              result = L"DxgkWaitForVerticalBlankEvent";
              break;
            case 2027:
              *a2 = 24;
              result = L"DxgkSetVidPnSourceOwner";
              break;
            case 2028:
              *a2 = 19;
              result = L"DxgkGetDeviceState";
              break;
            case 2029:
              *a2 = 33;
              result = L"DxgkSetContextSchedulingPriority";
              break;
            case 2030:
              *a2 = 33;
              result = L"DxgkGetContextSchedulingPriority";
              break;
            case 2031:
              *a2 = 38;
              result = L"DxgkSetProcessSchedulingPriorityClass";
              break;
            case 2032:
              *a2 = 38;
              result = L"DxgkGetProcessSchedulingPriorityClass";
              break;
            case 2033:
              *a2 = 36;
              result = L"DxgkReleaseProcessVidPnSourceOwners";
              break;
            case 2034:
              *a2 = 16;
              result = L"DxgkGetScanLine";
              break;
            case 2035:
              *a2 = 19;
              result = L"DxgkSetQueuedLimit";
              break;
            case 2036:
              *a2 = 24;
              result = L"DxgkPollDisplayChildren";
              break;
            case 2037:
              *a2 = 26;
              result = L"DxgkInvalidateActiveVidPn";
              break;
            case 2038:
              *a2 = 19;
              result = L"DxgkCheckOcclusion";
              break;
            case 2039:
              *a2 = 18;
              result = L"DxgkCreateContext";
              break;
            case 2040:
              *a2 = 19;
              result = L"DxgkDestroyContext";
              break;
            case 2041:
              result = L"DxgkCreateSynchronizationObject";
              goto LABEL_743;
            case 2042:
              *a2 = 33;
              result = L"DxgkDestroySynchronizationObject";
              break;
            case 2043:
              *a2 = 33;
              result = L"DxgkWaitForSynchronizationObject";
              break;
            case 2044:
              result = L"DxgkSignalSynchronizationObject";
              goto LABEL_743;
            case 2045:
              *a2 = 16;
              result = L"DxgkWaitForIdle";
              break;
            case 2046:
              *a2 = 27;
              result = L"DxgkCheckMonitorPowerState";
              break;
            case 2047:
              *a2 = 28;
              result = L"DxgkCheckExclusiveOwnership";
              break;
            case 2048:
              *a2 = 34;
              result = L"DxgkSetDisplayPrivateDriverFormat";
              break;
            case 2049:
              *a2 = 20;
              result = L"DxgkQueryStatistics";
              break;
            case 2050:
              *a2 = 30;
              result = L"DxgkOpenSynchronizationObject";
              break;
            case 2051:
              *a2 = 21;
              result = L"DxgkCreateKeyedMutex";
              break;
            case 2052:
              *a2 = 19;
              result = L"DxgkOpenKeyedMutex";
              break;
            case 2053:
              *a2 = 22;
              result = L"DxgkDestroyKeyedMutex";
              break;
            case 2054:
              *a2 = 22;
              result = L"DxgkAcquireKeyedMutex";
              break;
            case 2055:
              *a2 = 22;
              result = L"DxgkReleaseKeyedMutex";
              break;
            case 2056:
              *a2 = 28;
              result = L"DxgkConfigureSharedResource";
              break;
            case 2057:
              *a2 = 20;
              result = L"DxgkGetOverlayState";
              break;
            case 2058:
              *a2 = 33;
              result = L"DxgkCheckVidPnExclusiveOwnership";
              break;
            case 2059:
              *a2 = 30;
              result = L"DxgkCheckSharedResourceAccess";
              break;
            case 2060:
              *a2 = 22;
              result = L"DxgkGetPresentHistory";
              break;
            case 2061:
              *a2 = 21;
              result = L"DxgkCreateOutputDupl";
              break;
            case 2062:
              *a2 = 22;
              result = L"DxgkDestroyOutputDupl";
              break;
            case 2063:
              *a2 = 27;
              result = L"DxgkOutputDuplGetFrameInfo";
              break;
            case 2064:
              *a2 = 26;
              result = L"DxgkOutputDuplGetMetaData";
              break;
            case 2065:
              *a2 = 34;
              result = L"DxgkOutputDuplGetPointerShapeData";
              break;
            default:
              goto LABEL_736;
          }
        }
        else
        {
          if ( a1 == 2025 )
          {
            *a2 = 19;
            return L"DxgkDestroyOverlay";
          }
          if ( a1 <= 2005 )
          {
            if ( a1 == 2005 )
            {
              *a2 = 17;
              return L"DxgkOpenResource";
            }
            if ( a1 > 1005 )
            {
              v6 = a1 - 1006;
              if ( !v6 )
              {
                *a2 = 17;
                return L"DpiDispatchPower";
              }
              v7 = v6 - 1;
              if ( !v7 )
              {
                *a2 = 25;
                return L"DpiDispatchSystemControl";
              }
              v8 = v7 - 1;
              if ( !v8 )
              {
                *a2 = 16;
                return L"DpiDriverUnload";
              }
              v9 = v8 - 1;
              if ( !v9 )
              {
                *a2 = 27;
                return L"DxgkAcquireAdapterCoreSync";
              }
              v10 = v9 - 991;
              if ( !v10 )
              {
                *a2 = 19;
                return L"DxgkProcessCallout";
              }
              v11 = v10 - 1;
              if ( !v11 )
              {
                *a2 = 16;
                return L"DxgkOpenAdapter";
              }
              v12 = v11 - 1;
              if ( !v12 )
              {
                *a2 = 17;
                return L"DxgkCloseAdapter";
              }
              v13 = v12 - 1;
              if ( !v13 )
              {
                *a2 = 21;
                return L"DxgkCreateAllocation";
              }
              if ( v13 == 1 )
              {
                *a2 = 22;
                return L"DxgkQueryResourceInfo";
              }
            }
            else
            {
              if ( a1 == 1005 )
              {
                *a2 = 15;
                return L"DpiDispatchPnp";
              }
              if ( a1 > 1000 )
              {
                v3 = a1 - 1001;
                if ( !v3 )
                {
                  *a2 = 17;
                  return L"DpiDispatchClose";
                }
                v4 = v3 - 1;
                if ( !v4 )
                {
                  *a2 = 18;
                  return L"DpiDispatchCreate";
                }
                v5 = v4 - 1;
                if ( !v5 )
                {
                  *a2 = 25;
                  return L"DpiDispatchInternalIoctl";
                }
                if ( v5 == 1 )
                {
                  *a2 = 17;
                  return L"DpiDispatchIoctl";
                }
              }
              else
              {
                switch ( a1 )
                {
                  case 1000:
                    *a2 = 13;
                    return L"DpiAddDevice";
                  case -1:
                    *a2 = 8;
                    return L"Unknown";
                  case 0:
                    *a2 = 12;
                    return L"DriverEntry";
                  case 1:
                    *a2 = 16;
                    return L"DxgkCreateClose";
                  case 2:
                    *a2 = 24;
                    return L"DxgkInternalDeviceIoctl";
                  case 3:
                    *a2 = 18;
                    return L"DxgkProcessNotify";
                }
              }
            }
            goto LABEL_736;
          }
          switch ( a1 )
          {
            case 2006:
              *a2 = 22;
              result = L"DxgkDestroyAllocation";
              break;
            case 2007:
              *a2 = 26;
              result = L"DxgkSetAllocationPriority";
              break;
            case 2008:
              *a2 = 29;
              result = L"DxgkQueryAllocationResidency";
              break;
            case 2009:
              *a2 = 17;
              result = L"DxgkCreateDevice";
              break;
            case 2010:
              *a2 = 18;
              result = L"DxgkDestroyDevice";
              break;
            case 2011:
              *a2 = 9;
              result = L"DxgkLock";
              break;
            case 2012:
              *a2 = 11;
              result = L"DxgkUnlock";
              break;
            case 2013:
              *a2 = 11;
              result = L"DxgkRender";
              break;
            case 2014:
              *a2 = 19;
              result = L"DxgkGetRuntimeData";
              break;
            case 2015:
              *a2 = 21;
              result = L"DxgkQueryAdapterInfo";
              break;
            case 2016:
              *a2 = 11;
              result = L"DxgkEscape";
              break;
            case 2017:
              *a2 = 23;
              result = L"DxgkGetDisplayModeList";
              break;
            case 2018:
              *a2 = 19;
              result = L"DxgkSetDisplayMode";
              break;
            case 2019:
              *a2 = 29;
              result = L"DxgkGetMultisampleMethodList";
              break;
            case 2020:
              *a2 = 12;
              result = L"DxgkPresent";
              break;
            case 2021:
              *a2 = 27;
              result = L"DxgkGetSharedPrimaryHandle";
              break;
            case 2022:
              *a2 = 18;
              result = L"DxgkCreateOverlay";
              break;
            case 2023:
              *a2 = 18;
              result = L"DxgkUpdateOverlay";
              break;
            case 2024:
              *a2 = 16;
              result = L"DxgkFlipOverlay";
              break;
            default:
              goto LABEL_736;
          }
        }
      }
    }
    return result;
  }
  if ( a1 <= 6000 )
  {
    if ( a1 == 6000 )
    {
      *a2 = 47;
      return L"DmmInterfaceAcquiredPreferredMonitorSourceMode";
    }
    else
    {
      switch ( a1 )
      {
        case 5006:
          *a2 = 25;
          result = L"DdiAcquireSwizzlingRange";
          break;
        case 5007:
          *a2 = 25;
          result = L"DdiReleaseSwizzlingRange";
          break;
        case 5008:
          *a2 = 9;
          result = L"DdiPatch";
          break;
        case 5009:
          *a2 = 15;
          result = L"DdiCommitVidPn";
          break;
        case 5010:
          *a2 = 25;
          result = L"DdiSetVidPnSourceAddress";
          break;
        case 5011:
          *a2 = 28;
          result = L"DdiSetVidPnSourceVisibility";
          break;
        case 5012:
          result = L"DdiUpdateActiveVidPnPresentPath";
          goto LABEL_743;
        case 5013:
          *a2 = 17;
          result = L"DdiSubmitCommand";
          break;
        case 5014:
          *a2 = 18;
          result = L"DdiPreemptCommand";
          break;
        case 5015:
          *a2 = 21;
          result = L"DdiQueryCurrentFence";
          break;
        case 5016:
          *a2 = 21;
          result = L"DdiBuildPagingBuffer";
          break;
        case 5017:
          *a2 = 14;
          result = L"DdiSetPalette";
          break;
        case 5018:
          *a2 = 19;
          result = L"DdiSetPointerShape";
          break;
        case 5019:
          *a2 = 22;
          result = L"DdiSetPointerPosition";
          break;
        case 5020:
          *a2 = 20;
          result = L"DdiResetFromTimeout";
          break;
        case 5021:
          *a2 = 22;
          result = L"DdiRestartFromTimeout";
          break;
        case 5022:
          *a2 = 10;
          result = L"DdiEscape";
          break;
        case 5023:
          *a2 = 18;
          result = L"DdiCollectDbgInfo";
          break;
        case 5024:
          *a2 = 28;
          result = L"DdiRecommendFunctionalVidPn";
          break;
        case 5025:
          *a2 = 20;
          result = L"DdiIsSupportedVidPn";
          break;
        case 5026:
          *a2 = 27;
          result = L"DdiEnumVidPnCofuncModality";
          break;
        case 5027:
          *a2 = 17;
          result = L"DdiDestroyDevice";
          break;
        case 5028:
          *a2 = 18;
          result = L"DdiOpenAllocation";
          break;
        case 5029:
          *a2 = 19;
          result = L"DdiCloseAllocation";
          break;
        case 5030:
          *a2 = 10;
          result = L"DdiRender";
          break;
        case 5031:
          *a2 = 11;
          result = L"DdiPresent";
          break;
        case 5032:
          *a2 = 17;
          result = L"DdiCreateOverlay";
          break;
        case 5033:
          *a2 = 17;
          result = L"DdiUpdateOverlay";
          break;
        case 5034:
          *a2 = 15;
          result = L"DdiFlipOverlay";
          break;
        case 5035:
          *a2 = 18;
          result = L"DdiDestroyOverlay";
          break;
        case 5036:
          *a2 = 15;
          result = L"DdiGetScanLine";
          break;
        case 5037:
          *a2 = 25;
          result = L"DdiRecommendMonitorModes";
          break;
        case 5038:
          *a2 = 20;
          result = L"DdiControlInterrupt";
          break;
        case 5039:
          *a2 = 15;
          result = L"DdiStopCapture";
          break;
        case 5040:
          *a2 = 26;
          result = L"DdiRecommendVidPnTopology";
          break;
        case 5041:
          *a2 = 17;
          result = L"DdiCreateContext";
          break;
        case 5042:
          *a2 = 18;
          result = L"DdiDestroyContext";
          break;
        case 5043:
          *a2 = 13;
          result = L"DdiNotifyDpc";
          break;
        case 5044:
          *a2 = 33;
          result = L"DdiSetDisplayPrivateDriverFormat";
          break;
        case 5045:
          *a2 = 12;
          result = L"DdiRenderKm";
          break;
        case 5046:
          *a2 = 17;
          result = L"DdiAddTargetMode";
          break;
        case 5047:
          *a2 = 26;
          result = L"DdiQueryVidPnHWCapability";
          break;
        case 5048:
          *a2 = 22;
          result = L"DdiPresentDisplayOnly";
          break;
        case 5049:
          *a2 = 29;
          result = L"DdiQueryDependentEngineGroup";
          break;
        case 5050:
          *a2 = 21;
          result = L"DdiQueryEngineStatus";
          break;
        case 5051:
          *a2 = 15;
          result = L"DdiResetEngine";
          break;
        case 5052:
          *a2 = 17;
          result = L"DdiCancelCommand";
          break;
        case 5053:
          *a2 = 19;
          result = L"DdiGetNodeMetadata";
          break;
        case 5054:
          *a2 = 21;
          result = L"DdiControlInterrupt2";
          break;
        case 5055:
          *a2 = 33;
          result = L"DdiCheckMultiPlaneOverlaySupport";
          break;
        case 5056:
          *a2 = 21;
          result = L"DdiCalibrateGpuClock";
          break;
        case 5057:
          *a2 = 23;
          result = L"DdiFormatHistoryBuffer";
          break;
        case 5058:
          *a2 = 24;
          result = L"DdiGetRootPageTableSize";
          break;
        case 5059:
          *a2 = 20;
          result = L"DdiSetRootPageTable";
          break;
        case 5060:
          *a2 = 28;
          result = L"DdiInitPagingProcessVaSpace";
          break;
        case 5061:
          *a2 = 22;
          result = L"DdiMapCpuHostAperture";
          break;
        case 5062:
          *a2 = 24;
          result = L"DdiUnmapCpuHostAperture";
          break;
        case 5063:
          *a2 = 24;
          result = L"DdiSubmitCommandVirtual";
          break;
        case 5064:
          *a2 = 17;
          result = L"DdiCreateProcess";
          break;
        case 5065:
          *a2 = 18;
          result = L"DdiDestroyProcess";
          break;
        case 5066:
          *a2 = 13;
          result = L"DdiRenderGdi";
          break;
        case 5067:
          *a2 = 34;
          result = L"DdiCheckMultiPlaneOverlaySupport2";
          break;
        case 5068:
          *a2 = 23;
          result = L"DdiSetStablePowerState";
          break;
        case 5069:
          *a2 = 27;
          result = L"DdiSetVideoProtectedRegion";
          break;
        case 5070:
          *a2 = 34;
          result = L"DdiCheckMultiPlaneOverlaySupport3";
          break;
        case 5071:
          *a2 = 23;
          result = L"DdiControlModeBehavior";
          break;
        case 5072:
          *a2 = 25;
          result = L"DdiUpdateMonitorLinkInfo";
          break;
        case 5073:
          *a2 = 36;
          result = L"DdiValidateUpdateAllocationProperty";
          break;
        case 5074:
          *a2 = 35;
          result = L"DdiCreatePeriodicFrameNotification";
          break;
        case 5075:
          *a2 = 36;
          result = L"DdiDestroyPeriodicFrameNotification";
          break;
        case 5076:
          *a2 = 23;
          result = L"DdiSetTimingsFromVidPn";
          break;
        case 5077:
          *a2 = 18;
          result = L"DdiSetTargetGamma";
          break;
        case 5078:
          *a2 = 24;
          result = L"DdiSetTargetContentType";
          break;
        case 5079:
          *a2 = 33;
          result = L"DdiSetTargetAnalogCopyProtection";
          break;
        case 5080:
          result = L"DdiSetTargetAdjustedColorimetry";
          goto LABEL_743;
        case 5081:
          *a2 = 24;
          result = L"DdiDisplayDetectControl";
          break;
        case 5082:
          *a2 = 25;
          result = L"DdiQueryConnectionChange";
          break;
        case 5083:
          *a2 = 24;
          result = L"DdiExchangePreStartInfo";
          break;
        case 5084:
          *a2 = 28;
          result = L"DdiGetMultiPlaneOverlayCaps";
          break;
        case 5085:
          *a2 = 26;
          result = L"DdiGetPostCompositionCaps";
          break;
        case 5086:
          *a2 = 29;
          result = L"DdiReadVirtualFunctionConfig";
          break;
        case 5087:
          *a2 = 30;
          result = L"DdiWriteVirtualFunctionConfig";
          break;
        case 5088:
          *a2 = 35;
          result = L"DdiWriteVirtualFunctionConfigBlock";
          break;
        case 5089:
          *a2 = 34;
          result = L"DdiReadVirtualFunctionConfigBlock";
          break;
        case 5090:
          *a2 = 19;
          result = L"DdiQueryProbedBars";
          break;
        case 5091:
          *a2 = 22;
          result = L"DdiGetVendorAndDevice";
          break;
        case 5092:
          *a2 = 21;
          result = L"DdiGetDeviceLocation";
          break;
        case 5093:
          *a2 = 24;
          result = L"DdiResetVirtualFunction";
          break;
        case 5094:
          result = L"DdiSetVirtualFunctionPowerState";
          goto LABEL_743;
        case 5095:
          *a2 = 21;
          result = L"DdiGetResourceForBar";
          break;
        case 5096:
          *a2 = 28;
          result = L"DdiQueryVirtualFunctionLuid";
          break;
        case 5097:
          *a2 = 23;
          result = L"DdiGetGpuPartitionInfo";
          break;
        case 5098:
          *a2 = 24;
          result = L"DdiGetVirtualGpuProfile";
          break;
        case 5099:
          *a2 = 24;
          result = L"DdiSetGpuPartitionCount";
          break;
        case 5100:
          *a2 = 20;
          result = L"DdiCreateVirtualGpu";
          break;
        case 5101:
          *a2 = 26;
          result = L"DdiSetVirtualGpuResources";
          break;
        case 5102:
          *a2 = 21;
          result = L"DdiDestroyVirtualGpu";
          break;
        case 5103:
          *a2 = 21;
          result = L"DdiGetVirtualGpuInfo";
          break;
        case 5104:
          *a2 = 22;
          result = L"DdiSetVirtualGpuVmBus";
          break;
        case 5105:
          *a2 = 26;
          result = L"DdiVirtualGpuDriverEscape";
          break;
        case 5106:
          *a2 = 28;
          result = L"DdiQueryMitigatedRangeCount";
          break;
        case 5107:
          *a2 = 24;
          result = L"DdiQueryMitigatedRanges";
          break;
        case 5108:
          *a2 = 26;
          result = L"DdiCreateProtectedSession";
          break;
        case 5109:
          *a2 = 27;
          result = L"DdiDestroyProtectedSession";
          break;
        case 5110:
          *a2 = 17;
          result = L"DdiCreateHwQueue";
          break;
        case 5111:
          *a2 = 18;
          result = L"DdiDestroyHwQueue";
          break;
        case 5112:
          *a2 = 26;
          result = L"DdiSubmitCommandToHwQueue";
          break;
        case 5113:
          *a2 = 25;
          result = L"DdiSetVirtualMachineData";
          break;
        case 5114:
          *a2 = 26;
          result = L"DdiSetSchedulingLogBuffer";
          break;
        case 5115:
          *a2 = 22;
          result = L"DdiSetupPriorityBands";
          break;
        case 5116:
          *a2 = 22;
          result = L"DdiNotifyFocusPresent";
          break;
        case 5117:
          *a2 = 34;
          result = L"DdiSetContextSchedulingProperties";
          break;
        case 5118:
          *a2 = 18;
          result = L"DdiSuspendContext";
          break;
        case 5119:
          *a2 = 17;
          result = L"DdiResumeContext";
          break;
        case 5120:
          *a2 = 46;
          result = L"DdiSetVidPnSourceAddressWithMultiPlaneOverlay";
          break;
        case 5121:
          *a2 = 47;
          result = L"DdiSetVidPnSourceAddressWithMultiPlaneOverlay2";
          break;
        case 5122:
          *a2 = 47;
          result = L"DdiSetVidPnSourceAddressWithMultiPlaneOverlay3";
          break;
        case 5123:
          result = L"DdiPostMultiPlaneOverlayPresent";
          goto LABEL_743;
        case 5124:
          *a2 = 27;
          result = L"DdiSetPowerComponentFState";
          break;
        case 5125:
          *a2 = 18;
          result = L"DdiSetPowerPState";
          break;
        case 5126:
          *a2 = 30;
          result = L"DdiPowerRuntimeControlRequest";
          break;
        case 5127:
          *a2 = 31;
          result = L"DdiPowerRuntimeSetDeviceHandle";
          break;
        case 5128:
          *a2 = 31;
          result = L"DdiQueryDiagnosticTypesSupport";
          break;
        case 5129:
          *a2 = 30;
          result = L"DdiControlDiagnosticReporting";
          break;
        case 5130:
          *a2 = 24;
          result = L"DdiBeginExclusiveAccess";
          break;
        case 5131:
          *a2 = 22;
          result = L"DdiEndExclusiveAccess";
          break;
        case 5132:
          *a2 = 17;
          result = L"DdiResetHwEngine";
          break;
        case 5133:
          *a2 = 18;
          result = L"DdiResumeHwEngine";
          break;
        case 5134:
          *a2 = 24;
          result = L"DdiSignalMonitoredFence";
          break;
        case 5135:
          *a2 = 20;
          result = L"DdiPresentToHwQueue";
          break;
        case 5136:
          *a2 = 25;
          result = L"DdiValidateSubmitCommand";
          break;
        case 5137:
          *a2 = 22;
          result = L"DdiGetBackingResource";
          break;
        case 5138:
          *a2 = 21;
          result = L"DdiGetMmioRangeCount";
          break;
        case 5139:
          *a2 = 17;
          result = L"DdiGetMmioRanges";
          break;
        case 5140:
          result = L"DdiSetTrackedWorkloadPowerLevel";
          goto LABEL_743;
        case 5141:
          *a2 = 25;
          result = L"DdiCollectDiagnosticInfo";
          break;
        case 5143:
          *a2 = 21;
          result = L"DdiControlInterrupt3";
          break;
        case 5144:
          *a2 = 11;
          result = L"DdiDsiCaps";
          break;
        case 5145:
          *a2 = 19;
          result = L"DdiDsiTransmission";
          break;
        case 5146:
          *a2 = 12;
          result = L"DdiDsiReset";
          break;
        case 5155:
          *a2 = 31;
          result = L"DdiSetInterruptTargetPresentId";
          break;
        case 5156:
          *a2 = 21;
          result = L"DdiCancelQueuedFlips";
          break;
        case 5160:
          *a2 = 15;
          result = L"DdiCancelFlips";
          break;
        case 5161:
          *a2 = 22;
          result = L"DdiUpdateFlipQueueLog";
          break;
        case 5176:
          *a2 = 21;
          result = L"DdiCreateMemoryBasis";
          break;
        case 5177:
          *a2 = 22;
          result = L"DdiDestroyMemoryBasis";
          break;
        case 5178:
          *a2 = 22;
          result = L"DdiStartDirtyTracking";
          break;
        case 5179:
          *a2 = 21;
          result = L"DdiStopDirtyTracking";
          break;
        case 5180:
          *a2 = 21;
          result = L"DdiQueryDirtyBitData";
          break;
        case 5181:
          *a2 = 24;
          result = L"DdiPrepareLiveMigration";
          break;
        case 5182:
          *a2 = 20;
          result = L"DdiEndLiveMigration";
          break;
        case 5183:
          *a2 = 30;
          result = L"DdiSaveImmutableMigrationData";
          break;
        case 5184:
          *a2 = 33;
          result = L"DdiRestoreImmutableMigrationData";
          break;
        case 5185:
          *a2 = 28;
          result = L"DdiSaveMutableMigrationData";
          break;
        case 5186:
          *a2 = 31;
          result = L"DdiRestoreMutableMigrationData";
          break;
        default:
          goto LABEL_736;
      }
    }
    return result;
  }
  if ( a1 <= 7000 )
  {
    if ( a1 == 7000 )
    {
      *a2 = 38;
      return L"DmmMiniportInterfaceGetNumSourceModes";
    }
    else
    {
      switch ( a1 )
      {
        case 6001:
          *a2 = 37;
          result = L"DmmInterfaceReleaseMonitorSourceMode";
          break;
        case 6002:
          *a2 = 30;
          result = L"DmmInterfaceGetNumSourceModes";
          break;
        case 6003:
          *a2 = 35;
          result = L"DmmInterfaceAcquireFirstSourceMode";
          break;
        case 6004:
          *a2 = 34;
          result = L"DmmInterfaceAcquireNextSourceMode";
          break;
        case 6005:
          *a2 = 36;
          result = L"DmmInterfaceAcquirePinnedSourceMode";
          break;
        case 6006:
          *a2 = 30;
          result = L"DmmInterfaceReleaseSourceMode";
          break;
        case 6007:
          *a2 = 26;
          result = L"DmmInterfacePinSourceMode";
          break;
        case 6008:
          *a2 = 28;
          result = L"DmmInterfaceUnpinSourceMode";
          break;
        case 6009:
          *a2 = 30;
          result = L"DmmInterfaceGetNumTargetModes";
          break;
        case 6010:
          *a2 = 35;
          result = L"DmmInterfaceAcquireFirstTargetMode";
          break;
        case 6011:
          *a2 = 34;
          result = L"DmmInterfaceAcquireNextTargetMode";
          break;
        case 6012:
          *a2 = 36;
          result = L"DmmInterfaceAcquriePinnedTargetMode";
          break;
        case 6013:
          *a2 = 30;
          result = L"DmmInterfaceReleaseTargetMode";
          break;
        case 6014:
          *a2 = 30;
          result = L"DmmInterfaceCompareTargetMode";
          break;
        case 6015:
          *a2 = 26;
          result = L"DmmInterfacePinTargetMode";
          break;
        case 6016:
          *a2 = 28;
          result = L"DmmInterfaceUnpinTargetMode";
          break;
        case 6017:
          *a2 = 43;
          result = L"DmmInterfaceIsTargetModeSupportedByMonitor";
          break;
        case 6018:
          *a2 = 34;
          result = L"DmmInterfaceGetNumPathsFromSource";
          break;
        case 6019:
          *a2 = 38;
          result = L"DmmInterfaceEnumPathTargetsFromSource";
          break;
        case 6020:
          *a2 = 36;
          result = L"DmmInterfaceGetPathSourceFromTarget";
          break;
        case 6021:
          *a2 = 24;
          result = L"DmmInterfaceAcquirePath";
          break;
        case 6022:
          *a2 = 24;
          result = L"DmmInterfaceReleasePath";
          break;
        case 6023:
          *a2 = 20;
          result = L"DmmInterfaceAddPath";
          break;
        case 6024:
          *a2 = 23;
          result = L"DmmInterfaceRemovePath";
          break;
        case 6025:
          *a2 = 27;
          result = L"DmmInterfaceRemoveAllPaths";
          break;
        case 6026:
          *a2 = 23;
          result = L"DmmInterfacePinScaling";
          break;
        case 6027:
          *a2 = 25;
          result = L"DmmInterfaceUnpinScaling";
          break;
        case 6028:
          *a2 = 24;
          result = L"DmmInterfacePinRotation";
          break;
        case 6029:
          *a2 = 26;
          result = L"DmmInterfaceUnpinRotation";
          break;
        case 6030:
          *a2 = 35;
          result = L"DmmInterfaceRecommendVidPnTopology";
          break;
        case 6031:
          *a2 = 37;
          result = L"DmmInterfaceFindFirstAvailableTarget";
          break;
        case 6032:
          *a2 = 36;
          result = L"DmmInterfaceRestoreFromLkgForSource";
          break;
        case 6033:
          *a2 = 24;
          result = L"DmmInterfaceGetTopology";
          break;
        case 6034:
          *a2 = 33;
          result = L"DmmInterfaceAcquireSourceModeSet";
          break;
        case 6035:
          *a2 = 33;
          result = L"DmmInterfaceReleaseSourceModeSet";
          break;
        case 6036:
          *a2 = 33;
          result = L"DmmInterfaceAcquireTargetModeSet";
          break;
        case 6037:
          *a2 = 33;
          result = L"DmmInterfaceReleaseTargetModeSet";
          break;
        case 6038:
          *a2 = 40;
          result = L"DmmInterfaceAcquireMonitorSourceModeSet";
          break;
        case 6039:
          *a2 = 40;
          result = L"DmmInterfaceReleaseMonitorSourceModeSet";
          break;
        case 6040:
          *a2 = 26;
          result = L"DmmInterfaceGetNumSources";
          break;
        case 6041:
          *a2 = 31;
          result = L"DmmInterfaceAcquireFirstSource";
          break;
        case 6042:
          *a2 = 30;
          result = L"DmmInterfaceAcquireNextSource";
          break;
        case 6043:
          *a2 = 26;
          result = L"DmmInterfaceReleaseSource";
          break;
        case 6044:
          *a2 = 26;
          result = L"DmmInterfaceGetNumTargets";
          break;
        case 6045:
          *a2 = 31;
          result = L"DmmInterfaceAcquireFirstTarget";
          break;
        case 6046:
          *a2 = 30;
          result = L"DmmInterfaceAcquireNextTarget";
          break;
        case 6047:
          *a2 = 26;
          result = L"DmmInterfaceReleaseTarget";
          break;
        case 6048:
          *a2 = 29;
          result = L"DmmInterfaceAcquireSourceSet";
          break;
        case 6049:
          *a2 = 29;
          result = L"DmmInterfaceReleaseSourceSet";
          break;
        case 6050:
          *a2 = 29;
          result = L"DmmInterfaceAcquireTargetSet";
          break;
        case 6051:
          *a2 = 29;
          result = L"DmmInterfaceReleaseTargetSet";
          break;
        case 6052:
          *a2 = 24;
          result = L"DmmInterfaceCreateVidPn";
          break;
        case 6053:
          *a2 = 34;
          result = L"DmmInterfaceCreateVidPnFromActive";
          break;
        case 6054:
          *a2 = 28;
          result = L"DmmInterfaceCreateVidPnCopy";
          break;
        case 6055:
          *a2 = 25;
          result = L"DmmInterfaceReleaseVidPn";
          break;
        case 6056:
          *a2 = 41;
          result = L"DmmInterfaceIsUsingDefaultMonitorProfile";
          break;
        case 6057:
          *a2 = 31;
          result = L"DmmInterfaceIsMonitorConnected";
          break;
        case 6058:
          *a2 = 33;
          result = L"DmmInterfaceRemoveCopyProtection";
          break;
        case 6059:
          *a2 = 30;
          result = L"DmmInterfaceGetPathImportance";
          break;
        case 6060:
          *a2 = 24;
          result = L"DmmInterfaceGetNumPaths";
          break;
        case 6061:
          *a2 = 22;
          result = L"DmmInterfaceEnumPaths";
          break;
        default:
          goto LABEL_736;
      }
    }
    return result;
  }
  if ( a1 <= 8000 )
  {
    if ( a1 == 8000 )
    {
      *a2 = 18;
      return L"ProbeAndLockPages";
    }
    else
    {
      switch ( a1 )
      {
        case 7001:
          *a2 = 43;
          result = L"DmmMiniportInterfaceAcquireFirstSourceMode";
          break;
        case 7002:
          *a2 = 42;
          result = L"DmmMiniportInterfaceAcquireNextSourceMode";
          break;
        case 7003:
          *a2 = 44;
          result = L"DmmMiniportInterfaceAcquirePinnedSourceMode";
          break;
        case 7004:
          *a2 = 38;
          result = L"DmmMiniportInterfaceReleaseSourceMode";
          break;
        case 7005:
          *a2 = 40;
          result = L"DmmMiniportInterfaceCreateNewSourceMode";
          break;
        case 7006:
          *a2 = 34;
          result = L"DmmMiniportInterfaceAddSourceMode";
          break;
        case 7007:
          *a2 = 34;
          result = L"DmmMiniportInterfacePinSourceMode";
          break;
        case 7008:
          *a2 = 38;
          result = L"DmmMiniportInterfaceGetNumTargetModes";
          break;
        case 7009:
          *a2 = 43;
          result = L"DmmMiniportInterfaceAcquireFirstTargetMode";
          break;
        case 7010:
          *a2 = 42;
          result = L"DmmMiniportInterfaceAcquireNextTargetMode";
          break;
        case 7011:
          *a2 = 44;
          result = L"DmmMiniportInterfaceAcquirePinnedTargetMode";
          break;
        case 7012:
          *a2 = 38;
          result = L"DmmMiniportInterfaceReleaseTargetMode";
          break;
        case 7013:
          *a2 = 40;
          result = L"DmmMiniportInterfaceCreateNewTargetMode";
          break;
        case 7014:
          *a2 = 34;
          result = L"DmmMiniportInterfaceAddTargetMode";
          break;
        case 7015:
          *a2 = 34;
          result = L"DmmMiniportInterfacePinTargetMode";
          break;
        case 7016:
          *a2 = 45;
          result = L"DmmMiniportInterfaceGetNumMonitorSourceModes";
          break;
        case 7017:
          *a2 = 54;
          result = L"DmmMiniportInterfaceAcquirePreferredMonitorSourceMode";
          break;
        case 7018:
          *a2 = 50;
          result = L"DmmMiniportInterfaceAcquireFirstMonitorSourceMode";
          break;
        case 7019:
          *a2 = 49;
          result = L"DmmMiniportInterfaceAcquireNextMonitorSourceMode";
          break;
        case 7020:
          *a2 = 47;
          result = L"DmmMiniportInterfaceCreateNewMonitorSourceMode";
          break;
        case 7021:
          *a2 = 41;
          result = L"DmmMiniportInterfaceAddMonitorSourceMode";
          break;
        case 7022:
          *a2 = 45;
          result = L"DmmMiniportInterfaceReleaseMonitorSourceMode";
          break;
        case 7023:
          *a2 = 49;
          result = L"DmmMiniportInterfaceGetNumMonitorFrequencyRanges";
          break;
        case 7024:
          *a2 = 54;
          result = L"DmmMiniportInterfaceAcquireFirstMonitorFrequencyRange";
          break;
        case 7025:
          *a2 = 53;
          result = L"DmmMiniportInterfaceAcquireNextMonitorFrequencyRange";
          break;
        case 7026:
          *a2 = 49;
          result = L"DmmMiniportInterfaceReleaseMonitorFrequencyRange";
          break;
        case 7027:
          *a2 = 45;
          result = L"DmmMiniportInterfaceGetNumMonitorDescriptors";
          break;
        case 7028:
          *a2 = 50;
          result = L"DmmMiniportInterfaceAcquireFirstMonitorDescriptor";
          break;
        case 7029:
          *a2 = 49;
          result = L"DmmMiniportInterfaceAcquireNextMonitorDescriptor";
          break;
        case 7030:
          *a2 = 45;
          result = L"DmmMiniportInterfaceReleaseMonitorDescriptor";
          break;
        case 7031:
          result = L"DmmMiniportInterfaceGetNumPaths";
          goto LABEL_743;
        case 7032:
          *a2 = 42;
          result = L"DmmMiniportInterfaceGetNumPathsFromSource";
          break;
        case 7033:
          *a2 = 46;
          result = L"DmmMiniportInterfaceEnumPathTargetsFromSource";
          break;
        case 7034:
          *a2 = 44;
          result = L"DmmMiniportInterfaceGetPathSourceFromTarget";
          break;
        case 7035:
          result = L"DmmMiniportInterfaceAcquirePath";
          goto LABEL_743;
        case 7036:
          *a2 = 37;
          result = L"DmmMiniportInterfaceAcquireFirstPath";
          break;
        case 7037:
          *a2 = 36;
          result = L"DmmMiniportInterfaceAcquireNextPath";
          break;
        case 7038:
          *a2 = 38;
          result = L"DmmMiniportInterfaceUpdatePathSupport";
          break;
        case 7039:
          result = L"DmmMiniportInterfaceReleasePath";
          goto LABEL_743;
        case 7040:
          *a2 = 34;
          result = L"DmmMiniportInterfaceCreateNewPath";
          break;
        case 7041:
          *a2 = 28;
          result = L"DmmMiniportInterfaceAddPath";
          break;
        case 7042:
          result = L"DmmMiniportInterfaceGetTopology";
          goto LABEL_743;
        case 7043:
          *a2 = 41;
          result = L"DmmMiniportInterfaceAcquireSourceModeSet";
          break;
        case 7044:
          *a2 = 41;
          result = L"DmmMiniportInterfaceReleaseSourceModeSet";
          break;
        case 7045:
          *a2 = 43;
          result = L"DmmMiniportInterfaceCreateNewSourceModeSet";
          break;
        case 7046:
          *a2 = 40;
          result = L"DmmMiniportInterfaceAssignSourceModeSet";
          break;
        case 7047:
          *a2 = 43;
          result = L"DmmMiniportInterfaceAssignMultisamplingSet";
          break;
        case 7048:
          *a2 = 41;
          result = L"DmmMiniportInterfaceAcquireTargetModeSet";
          break;
        case 7049:
          *a2 = 41;
          result = L"DmmMiniportInterfaceReleaseTargetModeSet";
          break;
        case 7050:
          *a2 = 43;
          result = L"DmmMiniportInterfaceCreateNewTargetModeSet";
          break;
        case 7051:
          *a2 = 40;
          result = L"DmmMiniportInterfaceAssignTargetModeSet";
          break;
        case 7052:
          *a2 = 48;
          result = L"DmmMiniportInterfaceAcquireMonitorSourceModeSet";
          break;
        case 7053:
          *a2 = 48;
          result = L"DmmMiniportInterfaceReleaseMonitorSourceModeSet";
          break;
        case 7054:
          *a2 = 48;
          result = L"DmmMiniportInterfaceGetMonitorFrequencyRangeSet";
          break;
        case 7055:
          *a2 = 44;
          result = L"DmmMiniportInterfaceGetMonitorDescriptorSet";
          break;
        case 7056:
          *a2 = 40;
          result = L"DmmMiniportInterfaceQueryVidPnInterface";
          break;
        case 7057:
          *a2 = 42;
          result = L"DmmMiniportInterfaceQueryMonitorInterface";
          break;
        case 7058:
          *a2 = 31;
          result = L"DmmMiniportInterfaceRemovePath";
          break;
        case 7059:
          *a2 = 49;
          result = L"DmmMiniportInterfaceGetAdditionalMonitorModesSet";
          break;
        case 7060:
          *a2 = 53;
          result = L"DmmMiniportInterfaceReleaseAdditionalMonitorModesSet";
          break;
        case 7061:
          *a2 = 29;
          result = L"HandleMonitorPnPNotification";
          break;
        default:
          goto LABEL_736;
      }
    }
    return result;
  }
  if ( a1 <= 10005 )
  {
    if ( a1 == 10005 )
    {
      *a2 = 21;
      return L"DdiCreateAllocation2";
    }
    else
    {
      switch ( a1 )
      {
        case 8001:
          *a2 = 12;
          result = L"UnlockPages";
          break;
        case 8002:
          *a2 = 20;
          result = L"MapViewOfAllocation";
          break;
        case 8003:
          *a2 = 22;
          result = L"UnmapViewOfAllocation";
          break;
        case 8004:
          *a2 = 20;
          result = L"ProcessHeapAllocate";
          break;
        case 8005:
          *a2 = 18;
          result = L"ProcessHeapRotate";
          break;
        case 8006:
          *a2 = 20;
          result = L"BootInt10ModeChange";
          break;
        case 8007:
          *a2 = 22;
          result = L"ResumeInt10ModeChange";
          break;
        case 8008:
          *a2 = 21;
          result = L"FlushAllocationCache";
          break;
        case 8009:
          *a2 = 12;
          result = L"NotifyVSync";
          break;
        case 8010:
          *a2 = 26;
          result = L"MakeProcessIdleToFlushTlb";
          break;
        case 8011:
          *a2 = 37;
          result = L"UpdateGpuVirtualAddressSystemCommand";
          break;
        case 8012:
          *a2 = 18;
          result = L"GdiRenderDuringCS";
          break;
        case 8013:
          *a2 = 14;
          result = L"WakeUpAdapter";
          break;
        case 8014:
          *a2 = 16;
          result = L"CsExitInitiated";
          break;
        case 8015:
          *a2 = 20;
          result = L"BlockListProcessing";
          break;
        case 8016:
          *a2 = 22;
          result = L"HoldAdapterLockThread";
          break;
        case 8017:
          *a2 = 23;
          result = L"PowerStateD3transition";
          break;
        default:
          goto LABEL_736;
      }
    }
    return result;
  }
  if ( a1 <= 13104 )
  {
    if ( a1 == 13104 )
    {
      *a2 = 33;
      return L"UmdDriverHandleKernelModeMessage";
    }
    if ( a1 <= 13002 )
    {
      if ( a1 == 13002 )
      {
        *a2 = 25;
        return L"DxgkDdiMiracastIoControl";
      }
      v17 = a1 - 11000;
      if ( !v17 )
      {
        *a2 = 46;
        return L"DxgkOutputDuplDXGDXGIKEYEDMUTEXOpenLocalMutex";
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        *a2 = 49;
        return L"DxgkOutputDuplDXGDXGIKEYEDMUTEXDestroyLocalMutex";
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        *a2 = 33;
        return L"DxgkOutputDuplAccumulateMetadata";
      }
      v20 = v19 - 998;
      if ( !v20 )
      {
        *a2 = 17;
        return L"BLTQUEUE_Present";
      }
      v21 = v20 - 1000;
      if ( !v21 )
      {
        *a2 = 25;
        return L"DxgkDdiMiracastQueryCaps";
      }
      if ( v21 == 1 )
      {
        *a2 = 29;
        return L"DxgkDdiMiracastCreateContext";
      }
      goto LABEL_736;
    }
    v22 = a1 - 13003;
    if ( !v22 )
    {
      *a2 = 30;
      return L"DxgkDdiMiracastDestroyContext";
    }
    v23 = v22 - 47;
    if ( !v23 )
    {
      *a2 = 26;
      return L"DxgkCbSendUserModeMessage";
    }
    v24 = v23 - 50;
    if ( !v24 )
    {
      *a2 = 31;
      return L"UmdDriverCreateMiracastContext";
    }
    v25 = v24 - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( !v26 )
      {
        *a2 = 30;
        return L"UmdDriverStartMiracastSession";
      }
      if ( v26 == 1 )
      {
        *a2 = 29;
        return L"UmdDriverStopMiracastSession";
      }
      goto LABEL_736;
    }
    result = L"UmdDriverDestroyMiracastContext";
    goto LABEL_743;
  }
  if ( a1 <= 14001 )
  {
    if ( a1 == 14001 )
    {
      *a2 = 24;
      return L"VidMmRecalculateBudgets";
    }
    v27 = a1 - 13150;
    if ( !v27 )
    {
      *a2 = 31;
      return L"UmdDriverCbReportSessionStatus";
    }
    v28 = v27 - 1;
    if ( !v28 )
    {
      *a2 = 29;
      return L"UmdDriverCbMiracastIoControl";
    }
    v29 = v28 - 1;
    if ( !v29 )
    {
      *a2 = 27;
      return L"UmdDriverCbReportStatistic";
    }
    v30 = v29 - 1;
    if ( !v30 )
    {
      *a2 = 28;
      return L"UmdDriverCbGetNextChunkData";
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      *a2 = 44;
      return L"UmdDriverCbRegisterForDataRateNotifications";
    }
    if ( v31 == 846 )
    {
      *a2 = 23;
      return L"VidMmProcessOperations";
    }
    goto LABEL_736;
  }
  v32 = a1 - 15000;
  if ( !v32 )
  {
    result = L"DxgkCbSetProtectedSessionStatus";
LABEL_743:
    *a2 = 32;
    return result;
  }
  v33 = v32 - 1000;
  if ( v33 )
  {
    v34 = v33 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( v36 )
        {
          if ( v36 != 1 )
          {
LABEL_736:
            *a2 = 9;
            return L"NotFound";
          }
          *a2 = 40;
          return L"DxgkSharedBundleObjectObDeleteProcedure";
        }
        else
        {
          *a2 = 44;
          return L"DxgkSharedProtectedSessionObDeleteProcedure";
        }
      }
      else
      {
        *a2 = 38;
        return L"DxgkSharedSyncObjectObDeleteProcedure";
      }
    }
    else
    {
      *a2 = 44;
      return L"DxgkSharedKeyedMutexObjectObDeleteProcedure";
    }
  }
  else
  {
    *a2 = 38;
    return L"DxgkSharedAllocationObDeleteProcedure";
  }
}

```

## disassembly

```asm
0x14033c1e4  mov     eax, 138Dh
0x14033c1e9  cmp     ecx, eax
0x14033c1eb  jg      loc_14033D720
0x14033c1f1  jz      loc_14033D711
0x14033c1f7  mov     eax, 863h
0x14033c1fc  cmp     ecx, eax
0x14033c1fe  jg      loc_14033CCD9
0x14033c204  jz      loc_14033CCCA
0x14033c20a  mov     eax, 812h
0x14033c20f  cmp     ecx, eax
0x14033c211  jg      loc_14033C7F1
0x14033c217  jz      loc_14033C7E2
0x14033c21d  mov     eax, 7E9h
0x14033c222  cmp     ecx, eax
0x14033c224  jg      loc_14033C567
0x14033c22a  jz      loc_14033C558
0x14033c230  mov     eax, 7D5h
0x14033c235  cmp     ecx, eax
0x14033c237  jg      loc_14033C412
0x14033c23d  jz      loc_14033C403
0x14033c243  mov     eax, 3EDh
0x14033c248  cmp     ecx, eax
0x14033c24a  jg      loc_14033C33D
0x14033c250  jz      loc_14033C32E
0x14033c256  mov     eax, 3E8h
0x14033c25b  cmp     ecx, eax
0x14033c25d  jg      short loc_14033C2D7
0x14033c25f  jz      short loc_14033C2C8
0x14033c261  cmp     ecx, 0FFFFFFFFh
0x14033c264  jz      short loc_14033C2B9
0x14033c266  test    ecx, ecx
0x14033c268  jz      short loc_14033C2AA
0x14033c26a  cmp     ecx, 1
0x14033c26d  jz      short loc_14033C29B
0x14033c26f  cmp     ecx, 2
0x14033c272  jz      short loc_14033C28C
0x14033c274  cmp     ecx, 3
0x14033c277  jnz     def_14033C435; jumptable 000000014033C435 default case
0x14033c27d  mov     dword ptr [rdx], 12h
0x14033c283  lea     rax, aDxgkprocessnot; "DxgkProcessNotify"
0x14033c28a  retn
0x14033c28c  mov     dword ptr [rdx], 18h
0x14033c292  lea     rax, aDxgkinternalde; "DxgkInternalDeviceIoctl"
0x14033c299  retn
0x14033c29b  mov     dword ptr [rdx], 10h
0x14033c2a1  lea     rax, aDxgkcreateclos; "DxgkCreateClose"
0x14033c2a8  retn
0x14033c2aa  mov     dword ptr [rdx], 0Ch
0x14033c2b0  lea     rax, aDriverentry; "DriverEntry"
0x14033c2b7  retn
0x14033c2b9  mov     dword ptr [rdx], 8
0x14033c2bf  lea     rax, aUnknown; "Unknown"
0x14033c2c6  retn
0x14033c2c8  mov     dword ptr [rdx], 0Dh
0x14033c2ce  lea     rax, aDpiadddevice; "DpiAddDevice"
0x14033c2d5  retn
0x14033c2d7  sub     ecx, 3E9h
0x14033c2dd  jz      short loc_14033C31F
0x14033c2df  sub     ecx, 1
0x14033c2e2  jz      short loc_14033C310
0x14033c2e4  sub     ecx, 1
0x14033c2e7  jz      short loc_14033C301
0x14033c2e9  cmp     ecx, 1
0x14033c2ec  jnz     def_14033C435; jumptable 000000014033C435 default case
0x14033c2f2  mov     dword ptr [rdx], 11h
0x14033c2f8  lea     rax, aDpidispatchioc; "DpiDispatchIoctl"
0x14033c2ff  retn
0x14033c301  mov     dword ptr [rdx], 19h
0x14033c307  lea     rax, aDpidispatchint; "DpiDispatchInternalIoctl"
0x14033c30e  retn
0x14033c310  mov     dword ptr [rdx], 12h
0x14033c316  lea     rax, aDpidispatchcre; "DpiDispatchCreate"
0x14033c31d  retn
0x14033c31f  mov     dword ptr [rdx], 11h
0x14033c325  lea     rax, aDpidispatchclo; "DpiDispatchClose"
0x14033c32c  retn
0x14033c32e  mov     dword ptr [rdx], 0Fh
0x14033c334  lea     rax, aDpidispatchpnp; "DpiDispatchPnp"
0x14033c33b  retn
0x14033c33d  sub     ecx, 3EEh
0x14033c343  jz      loc_14033C3F4
0x14033c349  sub     ecx, 1
0x14033c34c  jz      loc_14033C3E5
0x14033c352  sub     ecx, 1
0x14033c355  jz      short loc_14033C3D6
0x14033c357  sub     ecx, 1
0x14033c35a  jz      short loc_14033C3C7
0x14033c35c  sub     ecx, 3DFh
0x14033c362  jz      short loc_14033C3B8
0x14033c364  sub     ecx, 1
0x14033c367  jz      short loc_14033C3A9
0x14033c369  sub     ecx, 1
0x14033c36c  jz      short loc_14033C39A
0x14033c36e  sub     ecx, 1
0x14033c371  jz      short loc_14033C38B
0x14033c373  cmp     ecx, 1
0x14033c376  jnz     def_14033C435; jumptable 000000014033C435 default case
0x14033c37c  mov     dword ptr [rdx], 16h
0x14033c382  lea     rax, aDxgkqueryresou; "DxgkQueryResourceInfo"
0x14033c389  retn
0x14033c38b  mov     dword ptr [rdx], 15h
0x14033c391  lea     rax, aDxgkcreateallo; "DxgkCreateAllocation"
0x14033c398  retn
0x14033c39a  mov     dword ptr [rdx], 11h
0x14033c3a0  lea     rax, aDxgkcloseadapt; "DxgkCloseAdapter"
0x14033c3a7  retn
0x14033c3a9  mov     dword ptr [rdx], 10h
0x14033c3af  lea     rax, aDxgkopenadapte_0; "DxgkOpenAdapter"
0x14033c3b6  retn
0x14033c3b8  mov     dword ptr [rdx], 13h
0x14033c3be  lea     rax, aDxgkprocesscal; "DxgkProcessCallout"
0x14033c3c5  retn
0x14033c3c7  mov     dword ptr [rdx], 1Bh
0x14033c3cd  lea     rax, aDxgkacquireada; "DxgkAcquireAdapterCoreSync"
0x14033c3d4  retn
0x14033c3d6  mov     dword ptr [rdx], 10h
0x14033c3dc  lea     rax, aDpidriverunloa; "DpiDriverUnload"
0x14033c3e3  retn
0x14033c3e5  mov     dword ptr [rdx], 19h
0x14033c3eb  lea     rax, aDpidispatchsys; "DpiDispatchSystemControl"
0x14033c3f2  retn
0x14033c3f4  mov     dword ptr [rdx], 11h
0x14033c3fa  lea     rax, aDpidispatchpow; "DpiDispatchPower"
0x14033c401  retn
0x14033c403  mov     dword ptr [rdx], 11h
0x14033c409  lea     rax, aDxgkopenresour; "DxgkOpenResource"
0x14033c410  retn
0x14033c412  add     ecx, 0FFFFF82Ah; switch 19 cases
0x14033c418  cmp     ecx, 12h
0x14033c41b  ja      def_14033C435; jumptable 000000014033C435 default case
0x14033c421  movsxd  rax, ecx
0x14033c424  lea     rcx, cs:140000000h
0x14033c42b  mov     eax, ds:(jpt_14033C435 - 140000000h)[rcx+rax*4]
0x14033c432  add     rax, rcx
0x14033c435  jmp     rax; switch jump
0x14033c43b  mov     dword ptr [rdx], 16h; jumptable 000000014033C435 case 2006
0x14033c441  lea     rax, aDxgkdestroyall; "DxgkDestroyAllocation"
0x14033c448  retn
0x14033c44a  mov     dword ptr [rdx], 1Ah; jumptable 000000014033C435 case 2007
0x14033c450  lea     rax, aDxgksetallocat; "DxgkSetAllocationPriority"
0x14033c457  retn
0x14033c459  mov     dword ptr [rdx], 1Dh; jumptable 000000014033C435 case 2008
0x14033c45f  lea     rax, aDxgkqueryalloc_0; "DxgkQueryAllocationResidency"
0x14033c466  retn
0x14033c468  mov     dword ptr [rdx], 11h; jumptable 000000014033C435 case 2009
0x14033c46e  lea     rax, aDxgkcreatedevi; "DxgkCreateDevice"
0x14033c475  retn
0x14033c477  mov     dword ptr [rdx], 12h; jumptable 000000014033C435 case 2010
0x14033c47d  lea     rax, aDxgkdestroydev; "DxgkDestroyDevice"
0x14033c484  retn
0x14033c486  mov     dword ptr [rdx], 9; jumptable 000000014033C435 case 2011
0x14033c48c  lea     rax, aDxgklock; "DxgkLock"
0x14033c493  retn
0x14033c495  mov     dword ptr [rdx], 0Bh; jumptable 000000014033C435 case 2012
0x14033c49b  lea     rax, aDxgkunlock; "DxgkUnlock"
0x14033c4a2  retn
0x14033c4a4  mov     dword ptr [rdx], 0Bh; jumptable 000000014033C435 case 2013
0x14033c4aa  lea     rax, aDxgkrender; "DxgkRender"
0x14033c4b1  retn
0x14033c4b3  mov     dword ptr [rdx], 13h; jumptable 000000014033C435 case 2014
0x14033c4b9  lea     rax, aDxgkgetruntime; "DxgkGetRuntimeData"
0x14033c4c0  retn
0x14033c4c2  mov     dword ptr [rdx], 15h; jumptable 000000014033C435 case 2015
0x14033c4c8  lea     rax, aDxgkqueryadapt; "DxgkQueryAdapterInfo"
0x14033c4cf  retn
0x14033c4d1  mov     dword ptr [rdx], 0Bh; jumptable 000000014033C435 case 2016
0x14033c4d7  lea     rax, aDxgkescape; "DxgkEscape"
0x14033c4de  retn
0x14033c4e0  mov     dword ptr [rdx], 17h; jumptable 000000014033C435 case 2017
0x14033c4e6  lea     rax, aDxgkgetdisplay; "DxgkGetDisplayModeList"
0x14033c4ed  retn
0x14033c4ef  mov     dword ptr [rdx], 13h; jumptable 000000014033C435 case 2018
0x14033c4f5  lea     rax, aDxgksetdisplay; "DxgkSetDisplayMode"
0x14033c4fc  retn
0x14033c4fe  mov     dword ptr [rdx], 1Dh; jumptable 000000014033C435 case 2019
0x14033c504  lea     rax, aDxgkgetmultisa; "DxgkGetMultisampleMethodList"
0x14033c50b  retn
0x14033c50d  mov     dword ptr [rdx], 0Ch; jumptable 000000014033C435 case 2020
0x14033c513  lea     rax, aDxgkpresent; "DxgkPresent"
0x14033c51a  retn
0x14033c51c  mov     dword ptr [rdx], 1Bh; jumptable 000000014033C435 case 2021
0x14033c522  lea     rax, aDxgkgetsharedp; "DxgkGetSharedPrimaryHandle"
0x14033c529  retn
0x14033c52b  mov     dword ptr [rdx], 12h; jumptable 000000014033C435 case 2022
0x14033c531  lea     rax, aDxgkcreateover; "DxgkCreateOverlay"
0x14033c538  retn
0x14033c53a  mov     dword ptr [rdx], 12h; jumptable 000000014033C435 case 2023
0x14033c540  lea     rax, aDxgkupdateover; "DxgkUpdateOverlay"
0x14033c547  retn
0x14033c549  mov     dword ptr [rdx], 10h; jumptable 000000014033C435 case 2024
0x14033c54f  lea     rax, aDxgkflipoverla; "DxgkFlipOverlay"
0x14033c556  retn
0x14033c558  mov     dword ptr [rdx], 13h
0x14033c55e  lea     rax, aDxgkdestroyove; "DxgkDestroyOverlay"
0x14033c565  retn
0x14033c567  add     ecx, 0FFFFF816h; switch 40 cases
0x14033c56d  cmp     ecx, 27h
0x14033c570  ja      def_14033C435; jumptable 000000014033C435 default case
0x14033c576  movsxd  rax, ecx
0x14033c579  lea     rcx, cs:140000000h
0x14033c580  mov     eax, ds:(jpt_14033C58A - 140000000h)[rcx+rax*4]
0x14033c587  add     rax, rcx
0x14033c58a  jmp     rax; switch jump
0x14033c590  mov     dword ptr [rdx], 1Eh; jumptable 000000014033C58A case 2026
0x14033c596  lea     rax, aDxgkwaitforver_0; "DxgkWaitForVerticalBlankEvent"
0x14033c59d  retn
0x14033c59f  mov     dword ptr [rdx], 18h; jumptable 000000014033C58A case 2027
0x14033c5a5  lea     rax, aDxgksetvidpnso_1; "DxgkSetVidPnSourceOwner"
0x14033c5ac  retn
0x14033c5ae  mov     dword ptr [rdx], 13h; jumptable 000000014033C58A case 2028
0x14033c5b4  lea     rax, aDxgkgetdevices; "DxgkGetDeviceState"
0x14033c5bb  retn
0x14033c5bd  mov     dword ptr [rdx], 21h ; '!'; jumptable 000000014033C58A case 2029
0x14033c5c3  lea     rax, aDxgksetcontext_0; "DxgkSetContextSchedulingPriority"
0x14033c5ca  retn
0x14033c5cc  mov     dword ptr [rdx], 21h ; '!'; jumptable 000000014033C58A case 2030
0x14033c5d2  lea     rax, aDxgkgetcontext; "DxgkGetContextSchedulingPriority"
0x14033c5d9  retn
0x14033c5db  mov     dword ptr [rdx], 26h ; '&'; jumptable 000000014033C58A case 2031
0x14033c5e1  lea     rax, aDxgksetprocess; "DxgkSetProcessSchedulingPriorityClass"
0x14033c5e8  retn
0x14033c5ea  mov     dword ptr [rdx], 26h ; '&'; jumptable 000000014033C58A case 2032
0x14033c5f0  lea     rax, aDxgkgetprocess_1; "DxgkGetProcessSchedulingPriorityClass"
0x14033c5f7  retn
0x14033c5f9  mov     dword ptr [rdx], 24h ; '$'; jumptable 000000014033C58A case 2033
0x14033c5ff  lea     rax, aDxgkreleasepro; "DxgkReleaseProcessVidPnSourceOwners"
0x14033c606  retn
0x14033c608  mov     dword ptr [rdx], 10h; jumptable 000000014033C58A case 2034
0x14033c60e  lea     rax, aDxgkgetscanlin; "DxgkGetScanLine"
0x14033c615  retn
0x14033c617  mov     dword ptr [rdx], 13h; jumptable 000000014033C58A case 2035
0x14033c61d  lea     rax, aDxgksetqueuedl; "DxgkSetQueuedLimit"
0x14033c624  retn
0x14033c626  mov     dword ptr [rdx], 18h; jumptable 000000014033C58A case 2036
0x14033c62c  lea     rax, aDxgkpolldispla; "DxgkPollDisplayChildren"
0x14033c633  retn
0x14033c635  mov     dword ptr [rdx], 1Ah; jumptable 000000014033C58A case 2037
0x14033c63b  lea     rax, aDxgkinvalidate_0; "DxgkInvalidateActiveVidPn"
0x14033c642  retn
0x14033c644  mov     dword ptr [rdx], 13h; jumptable 000000014033C58A case 2038
0x14033c64a  lea     rax, aDxgkcheckocclu; "DxgkCheckOcclusion"
0x14033c651  retn
0x14033c653  mov     dword ptr [rdx], 12h; jumptable 000000014033C58A case 2039
0x14033c659  lea     rax, aDxgkcreatecont; "DxgkCreateContext"
0x14033c660  retn
0x14033c662  mov     dword ptr [rdx], 13h; jumptable 000000014033C58A case 2040
0x14033c668  lea     rax, aDxgkdestroycon; "DxgkDestroyContext"
0x14033c66f  retn
0x14033c671  lea     rax, aDxgkcreatesync; jumptable 000000014033C58A case 2041
0x14033c678  jmp     loc_14033EBDE
0x14033c67d  mov     dword ptr [rdx], 21h ; '!'; jumptable 000000014033C58A case 2042
0x14033c683  lea     rax, aDxgkdestroysyn; "DxgkDestroySynchronizationObject"
0x14033c68a  retn
0x14033c68c  mov     dword ptr [rdx], 21h ; '!'; jumptable 000000014033C58A case 2043
0x14033c692  lea     rax, aDxgkwaitforsyn; "DxgkWaitForSynchronizationObject"
0x14033c699  retn
0x14033c69b  lea     rax, aDxgksignalsync_1; jumptable 000000014033C58A case 2044
0x14033c6a2  jmp     loc_14033EBDE
0x14033c6a7  mov     dword ptr [rdx], 10h; jumptable 000000014033C58A case 2045
0x14033c6ad  lea     rax, aDxgkwaitforidl; "DxgkWaitForIdle"
0x14033c6b4  retn
0x14033c6b6  mov     dword ptr [rdx], 1Bh; jumptable 000000014033C58A case 2046
0x14033c6bc  lea     rax, aDxgkcheckmonit_0; "DxgkCheckMonitorPowerState"
0x14033c6c3  retn
0x14033c6c5  mov     dword ptr [rdx], 1Ch; jumptable 000000014033C58A case 2047
0x14033c6cb  lea     rax, aDxgkcheckexclu; "DxgkCheckExclusiveOwnership"
0x14033c6d2  retn
0x14033c6d4  mov     dword ptr [rdx], 22h ; '"'; jumptable 000000014033C58A case 2048
0x14033c6da  lea     rax, aDxgksetdisplay_0; "DxgkSetDisplayPrivateDriverFormat"
0x14033c6e1  retn
0x14033c6e3  mov     dword ptr [rdx], 14h; jumptable 000000014033C58A case 2049
0x14033c6e9  lea     rax, aDxgkquerystati; "DxgkQueryStatistics"
0x14033c6f0  retn
0x14033c6f2  mov     dword ptr [rdx], 1Eh; jumptable 000000014033C58A case 2050
0x14033c6f8  lea     rax, aDxgkopensynchr; "DxgkOpenSynchronizationObject"
0x14033c6ff  retn
0x14033c701  mov     dword ptr [rdx], 15h; jumptable 000000014033C58A case 2051
0x14033c707  lea     rax, aDxgkcreatekeye; "DxgkCreateKeyedMutex"
0x14033c70e  retn
0x14033c710  mov     dword ptr [rdx], 13h; jumptable 000000014033C58A case 2052
0x14033c716  lea     rax, aDxgkopenkeyedm; "DxgkOpenKeyedMutex"
0x14033c71d  retn
0x14033c71f  mov     dword ptr [rdx], 16h; jumptable 000000014033C58A case 2053
0x14033c725  lea     rax, aDxgkdestroykey; "DxgkDestroyKeyedMutex"
0x14033c72c  retn
0x14033c72e  mov     dword ptr [rdx], 16h; jumptable 000000014033C58A case 2054
0x14033c734  lea     rax, aDxgkacquirekey; "DxgkAcquireKeyedMutex"
0x14033c73b  retn
0x14033c73d  mov     dword ptr [rdx], 16h; jumptable 000000014033C58A case 2055
0x14033c743  lea     rax, aDxgkreleasekey_0; "DxgkReleaseKeyedMutex"
0x14033c74a  retn
0x14033c74c  mov     dword ptr [rdx], 1Ch; jumptable 000000014033C58A case 2056
0x14033c752  lea     rax, aDxgkconfigures; "DxgkConfigureSharedResource"
0x14033c759  retn
0x14033c75b  mov     dword ptr [rdx], 14h; jumptable 000000014033C58A case 2057
0x14033c761  lea     rax, aDxgkgetoverlay_0; "DxgkGetOverlayState"
0x14033c768  retn
0x14033c76a  mov     dword ptr [rdx], 21h ; '!'; jumptable 000000014033C58A case 2058
0x14033c770  lea     rax, aDxgkcheckvidpn; "DxgkCheckVidPnExclusiveOwnership"
0x14033c777  retn
  ... truncated ...
```
