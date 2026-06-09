# DpiFdoDispatchIoctl

- ea: `0x1403ee180`
- end: `0x1403efef4`
- name: `DpiFdoDispatchIoctl`
- size: `7540`
- prototype: `__int64 __fastcall(void *, struct _IRP *)`
- caller_count: `0`
- callee_count: `41`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14004790c`
- `0x1400537ec`
- `0x1400556dc`
- `0x1400571d0`
- `0x140068954`
- `0x14007fc70`
- `0x14007fd7c`
- `0x1400806a4`
- `0x1400a0100`
- `0x1400a0540`
- `0x140187498`
- `0x140273b30`
- `0x140273d78`
- `0x140273ed8`
- `0x140274058`
- `0x140274110`
- `0x140274420`
- `0x140274530`
- `0x140274620`
- `0x1402747a0`
- `0x140274860`
- `0x14027496c`
- `0x140274d7c`
- `0x140274e54`
- `0x140274f2c`
- `0x140275004`
- `0x1402750dc`
- `0x14027545c`
- `0x140275550`
- `0x140275658`
- `0x1402757d8`
- `0x140275974`
- `0x1402af394`
- `0x1402af5ac`
- `0x1402af940`
- `0x1402afad0`
- `0x1402afcb4`
- `0x1402afd90`
- `0x1403e00d0`
- `0x1403ee180`
- `0x1404038f8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1403efaf3`
- `ntoskrnl!IofCallDriver` at `0x1403efaf3`
- `ntoskrnl!IofCompleteRequest` at `0x1403efebb`
- `ntoskrnl!IofCompleteRequest` at `0x1403efebb`
- `ntoskrnl!RtlCopyLuid` at `0x1403ee44a`
- `ntoskrnl!RtlCopyLuid` at `0x1403ee44a`
- `watchdog!WdLogSingleEntry1` at `0x1403ee1fc`
- `watchdog!WdLogSingleEntry1` at `0x1403ee3a3`
- `watchdog!WdLogSingleEntry1` at `0x1403ee3e7`
- `watchdog!WdLogSingleEntry1` at `0x1403ee467`
- `watchdog!WdLogSingleEntry1` at `0x1403ee4a9`
- `watchdog!WdLogSingleEntry1` at `0x1403ee56d`
- `watchdog!WdLogSingleEntry1` at `0x1403ee5a8`
- `watchdog!WdLogSingleEntry1` at `0x1403ee660`
- `watchdog!WdLogSingleEntry1` at `0x1403ee6a5`
- `watchdog!WdLogSingleEntry1` at `0x1403ee704`
- `watchdog!WdLogSingleEntry1` at `0x1403ee8a0`
- `watchdog!WdLogSingleEntry1` at `0x1403ee9d7`
- `watchdog!WdLogSingleEntry1` at `0x1403eea00`
- `watchdog!WdLogSingleEntry1` at `0x1403eeb4a`
- `watchdog!WdLogSingleEntry1` at `0x1403eeb73`
- `watchdog!WdLogSingleEntry1` at `0x1403eec20`
- `watchdog!WdLogSingleEntry1` at `0x1403eed5c`
- `watchdog!WdLogSingleEntry1` at `0x1403eed97`
- `watchdog!WdLogSingleEntry1` at `0x1403eefef`
- `watchdog!WdLogSingleEntry1` at `0x1403ef02a`
- `watchdog!WdLogSingleEntry1` at `0x1403ef0ac`
- `watchdog!WdLogSingleEntry1` at `0x1403ef19e`
- `watchdog!WdLogSingleEntry1` at `0x1403ef1c7`
- `watchdog!WdLogSingleEntry1` at `0x1403ef30d`
- `watchdog!WdLogSingleEntry1` at `0x1403ef336`
- `watchdog!WdLogSingleEntry1` at `0x1403ef428`
- `watchdog!WdLogSingleEntry1` at `0x1403ef451`
- `watchdog!WdLogSingleEntry1` at `0x1403ef505`
- `watchdog!WdLogSingleEntry1` at `0x1403ef52e`
- `watchdog!WdLogSingleEntry1` at `0x1403ef638`
- `watchdog!WdLogSingleEntry1` at `0x1403ef661`
- `watchdog!WdLogSingleEntry1` at `0x1403ef706`
- `watchdog!WdLogSingleEntry1` at `0x1403ef72f`
- `watchdog!WdLogSingleEntry1` at `0x1403ef829`
- `watchdog!WdLogSingleEntry1` at `0x1403ef852`
- `watchdog!WdLogSingleEntry1` at `0x1403ef94d`
- `watchdog!WdLogSingleEntry1` at `0x1403ef976`
- `watchdog!WdLogSingleEntry1` at `0x1403efa5d`
- `watchdog!WdLogSingleEntry1` at `0x1403efa86`
- `watchdog!WdLogSingleEntry1` at `0x1403efb80`
- `watchdog!WdLogSingleEntry1` at `0x1403efc49`
- `watchdog!WdLogSingleEntry1` at `0x1403efd40`
- `watchdog!WdLogSingleEntry1` at `0x1403efd69`
- `watchdog!WdLogSingleEntry1` at `0x1403efe6d`
- `watchdog!WdLogSingleEntry1` at `0x1403efe93`
- `watchdog!WdLogSingleEntry1` at `0x1403ee1fc`
- `watchdog!WdLogSingleEntry1` at `0x1403ee3a3`
- `watchdog!WdLogSingleEntry1` at `0x1403ee3e7`
- `watchdog!WdLogSingleEntry1` at `0x1403ee467`
- `watchdog!WdLogSingleEntry1` at `0x1403ee4a9`
- `watchdog!WdLogSingleEntry1` at `0x1403ee56d`
- `watchdog!WdLogSingleEntry1` at `0x1403ee5a8`
- `watchdog!WdLogSingleEntry1` at `0x1403ee660`
- `watchdog!WdLogSingleEntry1` at `0x1403ee6a5`
- `watchdog!WdLogSingleEntry1` at `0x1403ee704`
- `watchdog!WdLogSingleEntry1` at `0x1403ee8a0`
- `watchdog!WdLogSingleEntry1` at `0x1403ee9d7`
- `watchdog!WdLogSingleEntry1` at `0x1403eea00`
- `watchdog!WdLogSingleEntry1` at `0x1403eeb4a`
- `watchdog!WdLogSingleEntry1` at `0x1403eeb73`
- `watchdog!WdLogSingleEntry1` at `0x1403eec20`
- `watchdog!WdLogSingleEntry1` at `0x1403eed5c`
- `watchdog!WdLogSingleEntry1` at `0x1403eed97`
- `watchdog!WdLogSingleEntry1` at `0x1403eefef`
- `watchdog!WdLogSingleEntry1` at `0x1403ef02a`
- `watchdog!WdLogSingleEntry1` at `0x1403ef0ac`
- `watchdog!WdLogSingleEntry1` at `0x1403ef19e`
- `watchdog!WdLogSingleEntry1` at `0x1403ef1c7`
- `watchdog!WdLogSingleEntry1` at `0x1403ef30d`
- `watchdog!WdLogSingleEntry1` at `0x1403ef336`
- `watchdog!WdLogSingleEntry1` at `0x1403ef428`
- `watchdog!WdLogSingleEntry1` at `0x1403ef451`
- `watchdog!WdLogSingleEntry1` at `0x1403ef505`
- `watchdog!WdLogSingleEntry1` at `0x1403ef52e`
- `watchdog!WdLogSingleEntry1` at `0x1403ef638`
- `watchdog!WdLogSingleEntry1` at `0x1403ef661`
- `watchdog!WdLogSingleEntry1` at `0x1403ef706`
- `watchdog!WdLogSingleEntry1` at `0x1403ef72f`
- `watchdog!WdLogSingleEntry1` at `0x1403ef829`
- `watchdog!WdLogSingleEntry1` at `0x1403ef852`
- `watchdog!WdLogSingleEntry1` at `0x1403ef94d`
- `watchdog!WdLogSingleEntry1` at `0x1403ef976`
- `watchdog!WdLogSingleEntry1` at `0x1403efa5d`
- `watchdog!WdLogSingleEntry1` at `0x1403efa86`
- `watchdog!WdLogSingleEntry1` at `0x1403efb80`
- `watchdog!WdLogSingleEntry1` at `0x1403efc49`
- `watchdog!WdLogSingleEntry1` at `0x1403efd40`
- `watchdog!WdLogSingleEntry1` at `0x1403efd69`
- `watchdog!WdLogSingleEntry1` at `0x1403efe6d`
- `watchdog!WdLogSingleEntry1` at `0x1403efe93`

## pseudocode

```c
NTSTATUS __fastcall DpiFdoDispatchIoctl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PVOID DeviceExtension; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int LowPart; // eax
  NTSTATUS MitigatedRangeCount; // ebx
  unsigned int Length; // ecx
  unsigned int Options; // ebx
  struct _IRP *MasterIrp; // rdi
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // r15d
  void *v19; // rcx
  unsigned int v20; // r15d
  int GpuPartitionInfo; // eax
  unsigned __int32 v22; // eax
  ULONG_PTR v23; // rdi
  void *v24; // rcx
  int MitigatedRanges; // eax
  void *v26; // rcx
  __int64 v27; // xmm1_8
  int VirtualGpuType; // eax
  NTSTATUS v29; // eax
  unsigned int v30; // eax
  __int64 v31; // r15
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  NTSTATUS v38; // eax
  __int64 v39; // rax
  unsigned int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rbx
  bool v43; // zf
  void *v44; // r12
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  __int64 v51; // r15
  int TransferSize; // eax
  int DirtyBitplane; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  NTSTATUS VirtualizationFlags; // eax
  int v62; // eax
  __int64 MdlAddress; // [rsp+30h] [rbp-D0h]
  __int64 v64; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  int v66[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v67[16]; // [rsp+60h] [rbp-A0h] BYREF
  void *v68; // [rsp+70h] [rbp-90h]
  int v69; // [rsp+80h] [rbp-80h]
  __m256i v70; // [rsp+90h] [rbp-70h] BYREF
  int Type; // [rsp+B0h] [rbp-50h]
  _DWORD v72[41]; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v73[306]; // [rsp+160h] [rbp+60h] BYREF

  DeviceExtension = a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v64 = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( !*((_BYTE *)DeviceExtension + 1158) || *((_BYTE *)DeviceExtension + 1159) && LowPart == 2345988 )
  {
    Length = CurrentStackLocation->Parameters.Read.Length;
    Options = CurrentStackLocation->Parameters.Create.Options;
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    v66[0] = Length;
    LODWORD(v65) = Options;
    if ( LowPart <= 0x22646C )
    {
      if ( LowPart == 2253932 )
      {
        v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
        if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
        {
          LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
          wil_details_FeatureReporting_ReportUsageToService(
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
            v64,
            3);
          wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
            v64,
            3,
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
          Options = v65;
        }
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
        {
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4534;
          goto LABEL_282;
        }
        if ( Options < 0x18 || !MasterIrp )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4543;
          goto LABEL_287;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 >= 0 )
        {
          DpiFdoGetVirtualGpuType(a2);
          v38 = DxgkDdiRestoreImmutableMigrationData(*((void **)DeviceExtension + 504), *(_QWORD *)&MasterIrp->Flags);
          goto LABEL_280;
        }
        goto LABEL_281;
      }
      if ( LowPart <= 0x226448 )
      {
        if ( LowPart != 2253896 )
        {
          v11 = LowPart - 2252868;
          if ( v11 )
          {
            v12 = v11 - 4;
            if ( v12 )
            {
              v13 = v12 - 4;
              if ( v13 )
              {
                v14 = v13 - 4;
                if ( v14 )
                {
                  v15 = v14 - 4;
                  if ( !v15 )
                  {
                    MitigatedRangeCount = -1073741637;
                    goto LABEL_287;
                  }
                  v16 = v15 - 4;
                  if ( v16 )
                  {
                    v17 = v16 - 4;
                    if ( v17 )
                    {
                      if ( v17 == 1000 )
                      {
                        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
                        MitigatedRangeCount = v69;
                        if ( v69 < 0 )
                          goto LABEL_32;
                        memset(&v70, 0, 24);
                        if ( !MasterIrp || (v18 = v66[0], v66[0] < 0x18u) )
                        {
                          WdLogSingleEntry1(3);
                          WdLogGlobalForLineNumber = 3902;
                          MitigatedRangeCount = -1073741789;
                          goto LABEL_28;
                        }
                        v66[0] = DpiFdoGetVirtualGpuType(a2);
                        v70.m256i_i64[1] = (__int64)(&MasterIrp->Flags + 1);
                        v19 = (void *)*((_QWORD *)DeviceExtension + 504);
                        v20 = (unsigned int)(v18 - 20) >> 1;
                        v70.m256i_i32[0] = v20;
                        GpuPartitionInfo = DxgkDdiGetGpuPartitionInfo(v19);
                        MitigatedRangeCount = GpuPartitionInfo;
                        if ( GpuPartitionInfo >= 0 )
                        {
                          v22 = v70.m256i_i32[0];
                          if ( g_LimitNumberOfVfs && v70.m256i_i32[0] )
                          {
                            v70.m256i_i32[0] = 1;
                            *(_WORD *)v70.m256i_i64[1] = 1;
                            v22 = v70.m256i_i32[0];
                            v70.m256i_i16[8] = 1;
                          }
                          if ( v22 <= v20 && v22 )
                          {
                            *(_DWORD *)&MasterIrp->Type = v22;
                            WORD2(MasterIrp->MdlAddress) = v70.m256i_i16[8];
                            MasterIrp->Flags = MasterIrp->Flags & 0xFFFFFFFE
                                             | ((unsigned __int8)DpiFdoIsPostDevice(a1) != 0);
                            DxgkDdiQueryPhysicalFunctionLuid(*((void **)DeviceExtension + 504));
                            v23 = (unsigned int)(2 * v70.m256i_i32[0] + 20);
LABEL_33:
                            CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)v67);
                            goto LABEL_283;
                          }
                          WdLogSingleEntry1(3);
                          WdLogGlobalForLineNumber = 3927;
                          MitigatedRangeCount = -1073741811;
LABEL_28:
                          CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)v67);
                          goto LABEL_287;
                        }
                        if ( GpuPartitionInfo != -1073741789 )
                        {
LABEL_32:
                          v23 = 0;
                          goto LABEL_33;
                        }
                        if ( !v70.m256i_i32[0] )
                        {
                          WdLogSingleEntry1(3);
                          WdLogGlobalForLineNumber = 3951;
                          MitigatedRangeCount = -1073741811;
                          goto LABEL_32;
                        }
                        *(_DWORD *)&MasterIrp->Type = v70.m256i_i32[0];
                        MitigatedRangeCount = -2147483643;
                        WORD2(MasterIrp->MdlAddress) = v70.m256i_i16[8];
                        MasterIrp->Flags = MasterIrp->Flags & 0xFFFFFFFE
                                         | ((unsigned __int8)DpiFdoIsPostDevice(a1) != 0);
                        RtlCopyLuid((PLUID)(&MasterIrp->Size + 1), (PLUID)DeviceExtension + 337);
LABEL_35:
                        v23 = 24;
                        goto LABEL_33;
                      }
LABEL_248:
                      ++a2->CurrentLocation;
                      a2->Tail.Overlay.CurrentStackLocation = CurrentStackLocation + 1;
                      return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 20), a2);
                    }
                    if ( a2->RequestorMode )
                    {
                      if ( !(unsigned __int8)DxgkpCheckProcessForVirtualMachineManagementAccess() )
                      {
                        MitigatedRangeCount = -1073741790;
                        WdLogSingleEntry1(2);
                        WdLogGlobalForLineNumber = 4321;
                        goto LABEL_287;
                      }
                      Length = v66[0];
                    }
                    if ( Options >= 4 && MasterIrp && Length >= 0x10 )
                    {
                      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
                      MitigatedRangeCount = v69;
                      if ( v69 < 0 )
                        goto LABEL_32;
                      DpiFdoGetVirtualGpuType(a2);
                      v24 = (void *)*((_QWORD *)DeviceExtension + 504);
                      v70.m256i_i32[0] = (unsigned __int16)MasterIrp->Type;
                      v70.m256i_i32[1] = LOBYTE(MasterIrp->Size);
                      v70.m256i_i64[1] = (unsigned int)v66[0] >> 4;
                      v70.m256i_i64[2] = (__int64)MasterIrp;
                      MitigatedRanges = DxgkDdiQueryMitigatedRanges(v24);
                      v23 = (unsigned int)v66[0];
LABEL_46:
                      MitigatedRangeCount = MitigatedRanges;
                      if ( MitigatedRanges >= 0 )
                        goto LABEL_33;
                      goto LABEL_32;
                    }
                    MitigatedRangeCount = -1073741789;
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 4332;
                  }
                  else
                  {
                    if ( a2->RequestorMode )
                    {
                      if ( !(unsigned __int8)DxgkpCheckProcessForVirtualMachineManagementAccess() )
                      {
                        MitigatedRangeCount = -1073741790;
                        WdLogSingleEntry1(2);
                        WdLogGlobalForLineNumber = 4279;
                        goto LABEL_287;
                      }
                      Length = v66[0];
                    }
                    if ( Options >= 2 && MasterIrp && Length >= 0x18 )
                    {
                      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
                      MitigatedRangeCount = v69;
                      if ( v69 < 0 )
                        goto LABEL_32;
                      DpiFdoGetVirtualGpuType(a2);
                      v70.m256i_i32[0] = (unsigned __int16)MasterIrp->Type;
                      v26 = (void *)*((_QWORD *)DeviceExtension + 504);
                      memset((char *)v70.m256i_i64 + 4, 0, 24);
                      MitigatedRangeCount = DxgkDdiQueryMitigatedRangeCount(v26);
                      if ( MitigatedRangeCount < 0 )
                        goto LABEL_32;
                      v27 = *(__int64 *)((char *)&v70.m256i_i64[2] + 4);
                      *(_OWORD *)&MasterIrp->Type = *(_OWORD *)((char *)v70.m256i_i64 + 4);
                      *(_QWORD *)&MasterIrp->Flags = v27;
                      goto LABEL_35;
                    }
                    MitigatedRangeCount = -1073741789;
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 4290;
                  }
                  goto LABEL_282;
                }
                if ( a2->RequestorMode && !(unsigned __int8)DxgkpCheckProcessForVirtualMachineManagementAccess() )
                {
                  MitigatedRangeCount = -1073741790;
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 4381;
                  goto LABEL_287;
                }
                VirtualGpuType = DpiFdoGetVirtualGpuType(a2);
                v29 = DpiSriovDetach(a1, VirtualGpuType);
              }
              else
              {
                v29 = DpiSriovAttach(a1, a2);
              }
            }
            else
            {
              if ( a2->RequestorMode && !(unsigned __int8)DxgkpCheckProcessForVirtualMachineManagementAccess() )
              {
                MitigatedRangeCount = -1073741790;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4396;
                goto LABEL_287;
              }
              v30 = DpiFdoGetVirtualGpuType(a2);
              v29 = DpiSriovEventComplete(a1, v30, MasterIrp, Options);
            }
          }
          else
          {
            v29 = DpiSriovNotification(a1, a2);
          }
          goto LABEL_65;
        }
        if ( Options < 2 || !MasterIrp || (v31 = 168, Length < 0xA8) )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 3984;
          goto LABEL_282;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 < 0 )
          goto LABEL_32;
        DpiFdoGetVirtualGpuType(a2);
        memset(v72, 0, sizeof(v72));
        Type = (unsigned __int16)MasterIrp->Type;
        MitigatedRangeCount = DxgkDdiGetVirtualGpuProfile(*((void **)DeviceExtension + 504));
        if ( MitigatedRangeCount < 0 )
          goto LABEL_32;
        *(_DWORD *)&MasterIrp->Type = Type;
        *(_DWORD *)(&MasterIrp->Size + 1) = v72[0];
        MasterIrp->MdlAddress = *(PMDL *)&v72[1];
        *(_QWORD *)&MasterIrp->Flags = *(_QWORD *)&v72[3];
        MasterIrp->AssociatedIrp.MasterIrp = *(struct _IRP **)&v72[5];
        MasterIrp->ThreadListEntry.Flink = *(struct _LIST_ENTRY **)&v72[7];
        MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)&v72[9];
        MasterIrp->IoStatus.Pointer = *(PVOID *)&v72[11];
        MasterIrp->IoStatus.Information = *(_QWORD *)&v72[13];
        *(_QWORD *)&MasterIrp->RequestorMode = *(_QWORD *)&v72[15];
        MasterIrp->UserIosb = *(PIO_STATUS_BLOCK *)&v72[17];
        MasterIrp->UserEvent = *(PKEVENT *)&v72[19];
        MasterIrp->Overlay.AllocationSize.QuadPart = *(_QWORD *)&v72[21];
        MasterIrp->Overlay.AsynchronousParameters.UserApcContext = *(PVOID *)&v72[23];
        MasterIrp->CancelRoutine = *(PDRIVER_CANCEL *)&v72[25];
        MasterIrp->UserBuffer = *(PVOID *)&v72[27];
        MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = *(struct _LIST_ENTRY **)&v72[29];
        MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = *(struct _LIST_ENTRY **)&v72[31];
        MasterIrp->Tail.Overlay.DriverContext[2] = *(PVOID *)&v72[33];
        MasterIrp->Tail.Overlay.DriverContext[3] = *(PVOID *)&v72[35];
        MasterIrp->Tail.Overlay.Thread = *(PETHREAD *)&v72[37];
        MasterIrp->Tail.Overlay.AuxiliaryBuffer = *(PCHAR *)&v72[39];
LABEL_78:
        v23 = v31;
        goto LABEL_33;
      }
      v32 = LowPart - 2253900;
      if ( !v32 )
      {
        if ( a2->RequestorMode && !(unsigned __int8)DxgkpCheckProcessForVirtualMachineManagementAccess() )
        {
          MitigatedRangeCount = -1073741790;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4039;
          goto LABEL_287;
        }
        if ( Options < 2 || !MasterIrp )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4050;
          goto LABEL_282;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 >= 0 )
        {
          DpiFdoGetVirtualGpuType(a2);
          v66[0] = (unsigned __int16)MasterIrp->Type;
          v38 = DxgkDdiSetGpuPartitionCount(*((void **)DeviceExtension + 504));
          goto LABEL_280;
        }
LABEL_281:
        CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)v67);
        goto LABEL_282;
      }
      v33 = v32 - 8;
      if ( !v33 )
      {
        if ( a2->RequestorMode )
        {
          if ( !(unsigned __int8)DxgkpCheckProcessForVirtualMachineManagementAccess() )
          {
            MitigatedRangeCount = -1073741790;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 4074;
            goto LABEL_287;
          }
          Length = v66[0];
        }
        if ( Options >= 0x78 && MasterIrp && Length >= 0x88 )
        {
          CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 0, 0, 1);
          MitigatedRangeCount = v69;
          if ( v69 >= 0 )
          {
            DpiFdoGetVirtualGpuType(a2);
            v42 = *(_QWORD *)&MasterIrp->Flags;
            if ( v42 || MasterIrp->AssociatedIrp.MasterIrp || MasterIrp->ThreadListEntry.Flink )
            {
              memset(v73, 0, sizeof(v73));
              v43 = BYTE2(MasterIrp->UserBuffer) == 0;
              v44 = v68;
              LODWORD(v73[0]) = (unsigned __int16)MasterIrp->Type;
              v73[2] = (__int64)MasterIrp->AssociatedIrp.MasterIrp;
              v73[3] = (__int64)MasterIrp->ThreadListEntry.Flink;
              v73[4] = (__int64)MasterIrp->ThreadListEntry.Blink;
              v73[5] = (__int64)MasterIrp->IoStatus.Pointer;
              v73[6] = MasterIrp->IoStatus.Information;
              v73[7] = *(_QWORD *)&MasterIrp->RequestorMode;
              v73[8] = (__int64)MasterIrp->UserIosb;
              v73[9] = (__int64)MasterIrp->UserEvent;
              v73[10] = MasterIrp->Overlay.AllocationSize.QuadPart;
              v73[11] = (__int64)MasterIrp->Overlay.AsynchronousParameters.UserApcContext;
              v73[12] = (__int64)MasterIrp->CancelRoutine;
              MdlAddress = (__int64)MasterIrp->MdlAddress;
              v73[1] = v42;
              MitigatedRangeCount = DxgkDdiCreateVirtualGpu(v68, !v43, (__int64)v73, MdlAddress);
              if ( MitigatedRangeCount >= 0 )
              {
                memset(v72, 0, 0x64u);
                Type = v73[0];
                MitigatedRangeCount = DxgkDdiGetVirtualGpuInfo(v44, (__int64)(&MasterIrp->Flags + 1));
                if ( MitigatedRangeCount >= 0 )
                {
                  LOWORD(MasterIrp->MdlAddress) = v73[0];
                  MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)&v72[1];
                  MasterIrp->IoStatus.Pointer = *(PVOID *)&v72[3];
                  MasterIrp->IoStatus.Information = *(_QWORD *)&v72[5];
                  *(_QWORD *)&MasterIrp->RequestorMode = *(_QWORD *)&v72[7];
                  MasterIrp->UserIosb = *(PIO_STATUS_BLOCK *)&v72[9];
                  MasterIrp->UserEvent = *(PKEVENT *)&v72[11];
                  MasterIrp->Overlay.AllocationSize.QuadPart = *(_QWORD *)&v72[13];
                  MasterIrp->Overlay.AsynchronousParameters.UserApcContext = *(PVOID *)&v72[15];
                  MasterIrp->CancelRoutine = *(PDRIVER_CANCEL *)&v72[17];
                  MasterIrp->UserBuffer = *(PVOID *)&v72[19];
                  MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = *(struct _LIST_ENTRY **)&v72[21];
                  MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = *(struct _LIST_ENTRY **)&v72[23];
                  v23 = 136;
                  goto LABEL_33;
                }
                v66[0] = v73[0];
                DxgkDdiDestroyVirtualGpu(v44);
              }
            }
            else
            {
              v66[0] = (unsigned __int16)MasterIrp->Type;
              MitigatedRangeCount = DxgkDdiDestroyVirtualGpu(v68);
            }
          }
          goto LABEL_32;
        }
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 4087;
        goto LABEL_282;
      }
      v34 = v33 - 4;
      if ( !v34 )
      {
        if ( Options < 2 || !MasterIrp || (v31 = 128, Length < 0x80) )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4196;
          goto LABEL_282;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 < 0 )
          goto LABEL_32;
        DpiFdoGetVirtualGpuType(a2);
        memset(v72, 0, 0x64u);
        Type = (unsigned __int16)MasterIrp->Type;
        MitigatedRangeCount = DxgkDdiGetVirtualGpuInfo(
                                *((void **)DeviceExtension + 504),
                                (__int64)&MasterIrp->MdlAddress + 4);
        if ( MitigatedRangeCount < 0 )
          goto LABEL_32;
        MasterIrp->Type = Type;
        MasterIrp->ThreadListEntry.Flink = *(struct _LIST_ENTRY **)&v72[1];
        MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)&v72[3];
        MasterIrp->IoStatus.Pointer = *(PVOID *)&v72[5];
        MasterIrp->IoStatus.Information = *(_QWORD *)&v72[7];
        *(_QWORD *)&MasterIrp->RequestorMode = *(_QWORD *)&v72[9];
        MasterIrp->UserIosb = *(PIO_STATUS_BLOCK *)&v72[11];
        MasterIrp->UserEvent = *(PKEVENT *)&v72[13];
        MasterIrp->Overlay.AllocationSize.QuadPart = *(_QWORD *)&v72[15];
        MasterIrp->Overlay.AsynchronousParameters.UserApcContext = *(PVOID *)&v72[17];
        MasterIrp->CancelRoutine = *(PDRIVER_CANCEL *)&v72[19];
        MasterIrp->UserBuffer = *(PVOID *)&v72[21];
        MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = *(struct _LIST_ENTRY **)&v72[23];
        goto LABEL_78;
      }
      v35 = v34 - 4;
      if ( v35 )
      {
        v36 = v35 - 4;
        if ( !v36 )
        {
          if ( Options >= 8 && MasterIrp )
          {
            CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 0, 1, 0);
            MitigatedRangeCount = v69;
            if ( v69 < 0 )
              goto LABEL_32;
            v40 = DpiFdoGetVirtualGpuType(a2);
            v70.m256i_i32[1] = v65;
            v41 = *((_QWORD *)DeviceExtension + 504);
            v70.m256i_i32[0] = 0;
            v70.m256i_i64[1] = (unsigned int)v66[0];
            v70.m256i_i64[2] = (__int64)MasterIrp;
            v70.m256i_i64[3] = (__int64)MasterIrp;
            MitigatedRanges = ADAPTER_RENDER::VirtualGpuDriverEscape(*(_QWORD *)(v41 + 3240), v40, MasterIrp, &v70);
            v23 = v70.m256i_u32[2];
            goto LABEL_46;
          }
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4248;
          goto LABEL_282;
        }
        v37 = v36 - 4;
        if ( !v37 )
        {
          v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
          if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
          {
            LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
            wil_details_FeatureReporting_ReportUsageToService(
              Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
              v64,
              3);
            wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
              v64,
              3,
              Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
            Options = v65;
            Length = v66[0];
          }
          if ( (*((_DWORD *)DeviceExtension + 1398) & 4) != 0 )
          {
            if ( Options < 0xC || !MasterIrp || Length < 0x20 )
            {
              MitigatedRangeCount = -1073741789;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 4459;
              goto LABEL_287;
            }
            CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 0, 0, 1);
            MitigatedRangeCount = v69;
            if ( v69 >= 0 )
            {
              DpiFdoGetVirtualGpuType(a2);
              LODWORD(v65) = (v66[0] - 8) / 0x18u;
              MitigatedRangeCount = DxgkDdiPrepareLiveMigration(v68, (__int64)&MasterIrp->MdlAddress, (__int64)&v65);
              v39 = (unsigned int)v65;
              *(_DWORD *)&MasterIrp->Type = v65;
              if ( MitigatedRangeCount >= 0 )
              {
                v23 = 24 * v39 + 8;
                goto LABEL_33;
              }
            }
            goto LABEL_32;
          }
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4448;
          goto LABEL_282;
        }
        if ( v37 != 4 )
          goto LABEL_248;
        v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
        if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
        {
          *(_QWORD *)v66 = __PAIR64__(HIDWORD(v64), Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1u);
          wil_details_FeatureReporting_ReportUsageToService(
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
            __PAIR64__(HIDWORD(v64), Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1u),
            3);
          wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
            *(_QWORD *)v66,
            3,
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
          Options = v65;
        }
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
        {
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4500;
          goto LABEL_282;
        }
        if ( Options < 0x18 || !MasterIrp )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4509;
          goto LABEL_287;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 >= 0 )
        {
          DpiFdoGetVirtualGpuType(a2);
          v38 = DxgkDdiSaveImmutableMigrationData(*((void **)DeviceExtension + 504), *(_QWORD *)&MasterIrp->Flags);
LABEL_280:
          MitigatedRangeCount = v38;
          goto LABEL_281;
        }
        goto LABEL_281;
      }
      v29 = DpiSetPartitionVmbus(a1, a2, MasterIrp, Options);
LABEL_65:
      MitigatedRangeCount = v29;
LABEL_282:
      v23 = 0;
      goto LABEL_283;
    }
    if ( LowPart > 0x22648C )
    {
      v54 = LowPart - 2253968;
      if ( !v54 )
      {
        v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
        if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
        {
          LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
          wil_details_FeatureReporting_ReportUsageToService(
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
            v64,
            3);
          wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
            v64,
            3,
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
          Options = v65;
        }
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
        {
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4886;
          goto LABEL_287;
        }
        if ( Options < 0x20 || !MasterIrp )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4895;
          goto LABEL_287;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 < 0 )
          goto LABEL_281;
        DpiFdoGetVirtualGpuType(a2);
        v38 = DxgkDdiWriteVirtualizedInterrupt(*((void **)DeviceExtension + 504), (__int64)&MasterIrp->Flags);
        goto LABEL_280;
      }
      v55 = v54 - 4;
      if ( !v55 )
      {
        v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
        if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
        {
          LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
          wil_details_FeatureReporting_ReportUsageToService(
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
            v64,
            3);
          wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
            v64,
            3,
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
          Options = v65;
          Length = v66[0];
        }
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
        {
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4675;
          goto LABEL_282;
        }
        v51 = 8;
        if ( Options < 8 || !MasterIrp || Length < 8 )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4686;
          goto LABEL_287;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 < 0 )
          goto LABEL_32;
        DpiFdoGetVirtualGpuType(a2);
        TransferSize = DxgkLiveMigrationGetTransferSize(*((void **)DeviceExtension + 504));
        goto LABEL_197;
      }
      v56 = v55 - 4;
      if ( v56 )
      {
        v57 = v56 - 940;
        if ( !v57 )
        {
          if ( a2->RequestorMode && !(unsigned __int8)DxgkpCheckProcessForVirtualMachineManagementAccess() )
          {
            MitigatedRangeCount = -1073741790;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 4411;
            goto LABEL_287;
          }
          DpiFdoGetVirtualGpuType(a2);
          VirtualizationFlags = DpiGetVirtualizationFlags(a1, (__int64)MasterIrp, v66[0], (__int64)&v64);
          v23 = v64;
          MitigatedRangeCount = VirtualizationFlags;
LABEL_283:
          if ( MitigatedRangeCount == 259 )
            return MitigatedRangeCount;
          goto LABEL_288;
        }
        v58 = v57 - 4;
        if ( v58 )
        {
          v59 = v58 - 20;
          if ( v59 )
          {
            if ( v59 != 91048 )
              goto LABEL_248;
            v66[0] = 0;
            v29 = DpiIndirectDdiIoControl(
                    (_DWORD)DeviceExtension,
                    Options,
                    (_DWORD)MasterIrp,
                    Length,
                    (__int64)MasterIrp,
                    (__int64)v66);
          }
          else
          {
            v29 = DpiFlexIovMitigationUpdate(a1, a2, (__int64)MasterIrp, Length);
          }
        }
        else
        {
          v29 = DpiSetPartitionFlexIovVmbus(a1, a2, MasterIrp, Options);
        }
        goto LABEL_65;
      }
      if ( Options < 8 || !MasterIrp || Length < 4 )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 4923;
        goto LABEL_282;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v69;
      if ( v69 < 0 )
        goto LABEL_32;
      v62 = DpiFdoGetVirtualGpuType(a2);
      *(_DWORD *)&MasterIrp->Type = 0;
      if ( v62 )
      {
LABEL_229:
        v23 = 4;
        goto LABEL_33;
      }
      DirtyBitplane = (*((_DWORD *)DeviceExtension + 1398) >> 2) & 1;
    }
    else
    {
      if ( LowPart == 2253964 )
      {
        v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
        if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
        {
          LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
          wil_details_FeatureReporting_ReportUsageToService(
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
            v64,
            3);
          wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
            v64,
            3,
            Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
          Options = v65;
        }
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
        {
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4854;
          goto LABEL_282;
        }
        if ( Options < 8 || !MasterIrp )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4863;
          goto LABEL_287;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v69;
        if ( v69 >= 0 )
        {
          DpiFdoGetVirtualGpuType(a2);
          v38 = DxgkDdiEndLiveMigration(*((void **)DeviceExtension + 504));
          goto LABEL_280;
        }
        goto LABEL_281;
      }
      v45 = LowPart - 2253936;
      if ( v45 )
      {
        v46 = v45 - 4;
        if ( v46 )
        {
          v47 = v46 - 4;
          if ( !v47 )
          {
            v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
            if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
            {
              LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
              wil_details_FeatureReporting_ReportUsageToService(
                Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
                v64,
                3);
              wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                v64,
                3,
                Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
              Options = v65;
            }
            if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
            {
              MitigatedRangeCount = -1073741637;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 4757;
              goto LABEL_282;
            }
            if ( Options < 0x10 || !MasterIrp )
            {
              MitigatedRangeCount = -1073741789;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 4766;
              goto LABEL_287;
            }
            v29 = DpiLiveMigrationWaitForFence(a1, a2, 0);
            goto LABEL_65;
          }
          v48 = v47 - 4;
          if ( v48 )
          {
            v49 = v48 - 4;
            if ( !v49 )
            {
              v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
              if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
              {
                LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
                wil_details_FeatureReporting_ReportUsageToService(
                  Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
                  v64,
                  3);
                wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                  v64,
                  3,
                  Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
                Options = v65;
              }
              if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
              {
                MitigatedRangeCount = -1073741637;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4826;
                goto LABEL_282;
              }
              if ( Options < 0x10 || !MasterIrp )
              {
                MitigatedRangeCount = -1073741789;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4835;
                goto LABEL_287;
              }
              v29 = DpiLiveMigrationWaitForFence(a1, a2, 1);
              goto LABEL_65;
            }
            v50 = v49 - 4;
            if ( v50 )
            {
              if ( v50 != 4 )
                goto LABEL_248;
              v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
              if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
              {
                LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
                wil_details_FeatureReporting_ReportUsageToService(
                  Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
                  v64,
                  3);
                wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                  v64,
                  3,
                  Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
                Options = v65;
              }
              if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
              {
                MitigatedRangeCount = -1073741637;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4603;
                goto LABEL_282;
              }
              if ( Options < 0x18 || !MasterIrp )
              {
                MitigatedRangeCount = -1073741789;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4612;
                goto LABEL_287;
              }
              CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
              MitigatedRangeCount = v69;
              if ( v69 >= 0 )
              {
                DpiFdoGetVirtualGpuType(a2);
                v38 = DxgkDdiRestoreMutableMigrationData(
                        *((void **)DeviceExtension + 504),
                        *(_QWORD *)&MasterIrp->Flags);
                goto LABEL_280;
              }
            }
            else
            {
              v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
              if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
              {
                LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
                wil_details_FeatureReporting_ReportUsageToService(
                  Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
                  v64,
                  3);
                wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                  v64,
                  3,
                  Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
                Options = v65;
              }
              if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
              {
                MitigatedRangeCount = -1073741637;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4569;
                goto LABEL_282;
              }
              if ( Options < 0x18 || !MasterIrp )
              {
                MitigatedRangeCount = -1073741789;
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 4578;
                goto LABEL_287;
              }
              CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
              MitigatedRangeCount = v69;
              if ( v69 >= 0 )
              {
                DpiFdoGetVirtualGpuType(a2);
                v38 = DxgkDdiSaveMutableMigrationData(*((void **)DeviceExtension + 504), *(_QWORD *)&MasterIrp->Flags);
                goto LABEL_280;
              }
            }
            goto LABEL_281;
          }
          v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
          if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
          {
            LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
            wil_details_FeatureReporting_ReportUsageToService(
              Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
              v64,
              3);
            wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
              v64,
              3,
              Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
            Options = v65;
            Length = v66[0];
          }
          if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
          {
            MitigatedRangeCount = -1073741637;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 4785;
            goto LABEL_282;
          }
          if ( Options < 0xC || !MasterIrp || (v51 = 8, Length < 8) )
          {
            MitigatedRangeCount = -1073741789;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 4796;
            goto LABEL_287;
          }
          CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
          MitigatedRangeCount = v69;
          if ( v69 < 0 )
            goto LABEL_32;
          DpiFdoGetVirtualGpuType(a2);
          TransferSize = DxgkSendDirtyToVRAM(*((void **)DeviceExtension + 504), (__int64)MasterIrp);
        }
        else
        {
          v51 = 16;
          v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
          if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
          {
            LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
            wil_details_FeatureReporting_ReportUsageToService(
              Feature_GpupLiveMigration_dxgkrnl__private_descriptor,
              v64,
              3);
            wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
              v64,
              3,
              Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
            Options = v65;
            Length = v66[0];
          }
          if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
          {
            MitigatedRangeCount = -1073741637;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 4715;
            goto LABEL_282;
          }
          if ( Options < 0xC || !MasterIrp || Length < 0x10 )
          {
            MitigatedRangeCount = -1073741789;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 4726;
            goto LABEL_287;
          }
          CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
          MitigatedRangeCount = v69;
          if ( v69 < 0 )
            goto LABEL_32;
          DpiFdoGetVirtualGpuType(a2);
          TransferSize = DxgkFillBufferWithDirty(*((void **)DeviceExtension + 504), (__int64)MasterIrp);
          LODWORD(MasterIrp->MdlAddress) = TransferSize;
        }
LABEL_197:
        v23 = 0;
        MitigatedRangeCount = TransferSize;
        if ( TransferSize >= 0 )
          v23 = v51;
        goto LABEL_33;
      }
      v64 = (unsigned int)Feature_GpupLiveMigration_dxgkrnl__private_featureState;
      if ( (Feature_GpupLiveMigration_dxgkrnl__private_featureState & 0x10) == 0 )
      {
        LODWORD(v64) = Feature_GpupLiveMigration_dxgkrnl__private_featureState | 1;
        wil_details_FeatureReporting_ReportUsageToService(Feature_GpupLiveMigration_dxgkrnl__private_descriptor, v64, 3);
        wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
          v64,
          3,
          Feature_GpupLiveMigration_dxgkrnl__private_descriptor);
        Options = v65;
        Length = v66[0];
      }
      if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
      {
        MitigatedRangeCount = -1073741637;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 4637;
        goto LABEL_282;
      }
      if ( Options < 0xC || !MasterIrp || Length < 4 )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 4648;
        goto LABEL_287;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v67, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v69;
      if ( v69 < 0 )
        goto LABEL_32;
      DpiFdoGetVirtualGpuType(a2);
      DirtyBitplane = DxgkDdiGetDirtyBitplane(*((void **)DeviceExtension + 504));
      MitigatedRangeCount = DirtyBitplane;
    }
    *(_DWORD *)&MasterIrp->Type = DirtyBitplane;
    goto LABEL_229;
  }
  MitigatedRangeCount = -1073741637;
  WdLogSingleEntry1(2);
  WdLogGlobalForLineNumber = 3875;
LABEL_287:
  v23 = 0;
LABEL_288:
  a2->IoStatus.Status = MitigatedRangeCount;
  a2->IoStatus.Information = v23;
  IofCompleteRequest(a2, 1);
  return MitigatedRangeCount;
}

```

## disassembly

```asm
0x1403ee180  mov     [rsp-8+arg_10], rbx
0x1403ee185  push    rbp
0x1403ee186  push    rsi
0x1403ee187  push    rdi
0x1403ee188  push    r12
0x1403ee18a  push    r13
0x1403ee18c  push    r14
0x1403ee18e  push    r15
0x1403ee190  lea     rbp, [rsp-0A00h]
0x1403ee198  sub     rsp, 0B00h
0x1403ee19f  mov     rax, cs:__security_cookie
0x1403ee1a6  xor     rax, rsp
0x1403ee1a9  mov     [rbp+0A30h+var_40], rax
0x1403ee1b0  mov     r13, [rcx+40h]
0x1403ee1b4  xor     r8d, r8d
0x1403ee1b7  mov     rsi, rdx
0x1403ee1ba  mov     [rsp+0B30h+var_AF0], r8
0x1403ee1bf  mov     rdx, [rdx+0B8h]
0x1403ee1c6  mov     r12, rcx
0x1403ee1c9  mov     [rsp+0B30h+var_AE8], r8
0x1403ee1ce  lea     r14d, [r8+1]
0x1403ee1d2  mov     eax, [rdx+18h]
0x1403ee1d5  cmp     [r13+486h], r8b
0x1403ee1dc  jz      short loc_1403EE217
0x1403ee1de  cmp     [r13+487h], r8b
0x1403ee1e5  jz      short loc_1403EE1EE
0x1403ee1e7  cmp     eax, 23CC04h
0x1403ee1ec  jz      short loc_1403EE217
0x1403ee1ee  mov     rdx, 0FFFFFFFFC00000BBh
0x1403ee1f5  mov     ebx, edx
0x1403ee1f7  mov     ecx, 2
0x1403ee1fc  call    cs:__imp_WdLogSingleEntry1
0x1403ee203  nop     dword ptr [rax+rax+00h]
0x1403ee208  mov     cs:WdLogGlobalForLineNumber, 0F23h
0x1403ee212  jmp     loc_1403EFEA9
0x1403ee217  mov     ecx, [rdx+8]
0x1403ee21a  mov     r9d, 22646Ch
0x1403ee220  mov     ebx, [rdx+10h]
0x1403ee223  mov     rdi, [rsi+18h]
0x1403ee227  mov     [rsp+0B30h+var_AD8], ecx
0x1403ee22b  mov     dword ptr [rsp+0B30h+var_AE0], ebx
0x1403ee22f  cmp     eax, r9d
0x1403ee232  ja      loc_1403EF1E2
0x1403ee238  jz      loc_1403EF0C7
0x1403ee23e  mov     r9d, 226448h
0x1403ee244  cmp     eax, r9d
0x1403ee247  ja      loc_1403EE8BB
0x1403ee24d  jz      loc_1403EE74C
0x1403ee253  sub     eax, 226044h
0x1403ee258  jz      loc_1403EE739
0x1403ee25e  sub     eax, 4
0x1403ee261  jz      loc_1403EE6E6
0x1403ee267  sub     eax, 4
0x1403ee26a  jz      loc_1403EE6D9
0x1403ee270  sub     eax, 4
0x1403ee273  jz      loc_1403EE687
0x1403ee279  sub     eax, 4
0x1403ee27c  jz      loc_1403EE67B
0x1403ee282  sub     eax, 4
0x1403ee285  jz      loc_1403EE588
0x1403ee28b  sub     eax, 4
0x1403ee28e  jz      loc_1403EE489
0x1403ee294  cmp     eax, 3E8h
0x1403ee299  jnz     loc_1403EFADA
0x1403ee29f  mov     [rsp+0B30h+var_B08], r8b; char
0x1403ee2a4  lea     rcx, [rsp+0B30h+var_AD0]; this
0x1403ee2a9  mov     [rsp+0B30h+var_B10], r8b; char
0x1403ee2ae  mov     r9b, r14b; unsigned __int8
0x1403ee2b1  mov     r8, rsi; struct _IRP *
0x1403ee2b4  mov     rdx, r12; void *
0x1403ee2b7  call    ??0CInterfaceCallContext@@QEAA@PEAXPEAU_IRP@@EEE@Z; CInterfaceCallContext::CInterfaceCallContext(void *,_IRP *,uchar,uchar,uchar)
0x1403ee2bc  mov     ebx, [rbp+0A30h+var_AB0]
0x1403ee2bf  test    ebx, ebx
0x1403ee2c1  js      loc_1403EE402
0x1403ee2c7  xor     eax, eax
0x1403ee2c9  xorps   xmm0, xmm0
0x1403ee2cc  mov     [rbp+0A30h+var_A90], rax
0x1403ee2d0  movups  [rbp+0A30h+var_AA0], xmm0
0x1403ee2d4  test    rdi, rdi
0x1403ee2d7  jz      loc_1403EE45D
0x1403ee2dd  mov     r15d, [rsp+0B30h+var_AD8]
0x1403ee2e2  cmp     r15d, 18h
0x1403ee2e6  jb      loc_1403EE45D
0x1403ee2ec  mov     rcx, rsi
0x1403ee2ef  call    DpiFdoGetVirtualGpuType
0x1403ee2f4  lea     rcx, [rdi+14h]
0x1403ee2f8  mov     [rsp+0B30h+var_AD8], eax
0x1403ee2fc  mov     qword ptr [rbp+0A30h+var_AA0+8], rcx
0x1403ee300  lea     r8, [rbp+0A30h+var_AA0]
0x1403ee304  mov     rcx, [r13+0FC0h]; void *
0x1403ee30b  add     r15d, 0FFFFFFECh
0x1403ee30f  shr     r15d, 1
0x1403ee312  mov     edx, eax
0x1403ee314  mov     dword ptr [rbp+0A30h+var_AA0], r15d
0x1403ee318  call    DxgkDdiGetGpuPartitionInfo
0x1403ee31d  mov     ebx, eax
0x1403ee31f  test    eax, eax
0x1403ee321  js      loc_1403EE3CD
0x1403ee327  cmp     cs:?g_LimitNumberOfVfs@@3HA, 0; int g_LimitNumberOfVfs
0x1403ee32e  mov     eax, dword ptr [rbp+0A30h+var_AA0]
0x1403ee331  jz      short loc_1403EE34C
0x1403ee333  cmp     eax, r14d
0x1403ee336  jb      short loc_1403EE34C
0x1403ee338  mov     rcx, qword ptr [rbp+0A30h+var_AA0+8]
0x1403ee33c  mov     dword ptr [rbp+0A30h+var_AA0], r14d
0x1403ee340  mov     [rcx], r14w
0x1403ee344  mov     eax, dword ptr [rbp+0A30h+var_AA0]
0x1403ee347  mov     word ptr [rbp+0A30h+var_A90], r14w
0x1403ee34c  cmp     eax, r15d
0x1403ee34f  ja      short loc_1403EE399
0x1403ee351  test    eax, eax
0x1403ee353  jz      short loc_1403EE399
0x1403ee355  mov     [rdi], eax
0x1403ee357  mov     rcx, r12
0x1403ee35a  movzx   eax, word ptr [rbp+0A30h+var_A90]
0x1403ee35e  mov     [rdi+0Ch], ax
0x1403ee362  call    DpiFdoIsPostDevice
0x1403ee367  mov     edx, [rsp+0B30h+var_AD8]
0x1403ee36b  lea     r8, [rdi+4]
0x1403ee36f  xor     ecx, ecx
0x1403ee371  test    al, al
0x1403ee373  mov     eax, [rdi+10h]
0x1403ee376  setnz   cl
0x1403ee379  and     eax, 0FFFFFFFEh
0x1403ee37c  or      ecx, eax
0x1403ee37e  mov     [rdi+10h], ecx
0x1403ee381  mov     rcx, [r13+0FC0h]; void *
0x1403ee388  call    DxgkDdiQueryPhysicalFunctionLuid
0x1403ee38d  mov     eax, dword ptr [rbp+0A30h+var_AA0]
0x1403ee390  lea     edi, ds:14h[rax*2]
0x1403ee397  jmp     short loc_1403EE407
0x1403ee399  mov     edx, 226444h
0x1403ee39e  mov     ecx, 3
0x1403ee3a3  call    cs:__imp_WdLogSingleEntry1
0x1403ee3aa  nop     dword ptr [rax+rax+00h]
0x1403ee3af  mov     cs:WdLogGlobalForLineNumber, 0F57h
0x1403ee3b9  mov     ebx, 0C000000Dh
0x1403ee3be  lea     rcx, [rsp+0B30h+var_AD0]; this
0x1403ee3c3  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x1403ee3c8  jmp     loc_1403EFEA9
0x1403ee3cd  mov     rdx, 0FFFFFFFFC0000023h
0x1403ee3d4  cmp     eax, edx
0x1403ee3d6  jnz     short loc_1403EE402
0x1403ee3d8  mov     eax, dword ptr [rbp+0A30h+var_AA0]
0x1403ee3db  test    eax, eax
0x1403ee3dd  jnz     short loc_1403EE416
0x1403ee3df  mov     edx, 226444h
0x1403ee3e4  lea     ecx, [rax+3]
0x1403ee3e7  call    cs:__imp_WdLogSingleEntry1
0x1403ee3ee  nop     dword ptr [rax+rax+00h]
0x1403ee3f3  mov     cs:WdLogGlobalForLineNumber, 0F6Fh
0x1403ee3fd  mov     ebx, 0C000000Dh
0x1403ee402  mov     rdi, [rsp+0B30h+var_AF0]
0x1403ee407  lea     rcx, [rsp+0B30h+var_AD0]; this
0x1403ee40c  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x1403ee411  jmp     loc_1403EFE55
0x1403ee416  mov     [rdi], eax
0x1403ee418  mov     rcx, r12
0x1403ee41b  movzx   eax, word ptr [rbp+0A30h+var_A90]
0x1403ee41f  mov     ebx, 80000005h
0x1403ee424  mov     [rdi+0Ch], ax
0x1403ee428  call    DpiFdoIsPostDevice
0x1403ee42d  xor     ecx, ecx
0x1403ee42f  lea     rdx, [r13+0A88h]; SourceLuid
0x1403ee436  test    al, al
0x1403ee438  mov     eax, [rdi+10h]
0x1403ee43b  setnz   cl
0x1403ee43e  and     eax, 0FFFFFFFEh
0x1403ee441  or      ecx, eax
0x1403ee443  mov     [rdi+10h], ecx
0x1403ee446  lea     rcx, [rdi+4]; DestinationLuid
0x1403ee44a  call    cs:__imp_RtlCopyLuid
0x1403ee451  nop     dword ptr [rax+rax+00h]
0x1403ee456  mov     edi, 18h
0x1403ee45b  jmp     short loc_1403EE407
0x1403ee45d  mov     edx, 226444h
0x1403ee462  mov     ecx, 3
0x1403ee467  call    cs:__imp_WdLogSingleEntry1
0x1403ee46e  nop     dword ptr [rax+rax+00h]
0x1403ee473  mov     cs:WdLogGlobalForLineNumber, 0F3Eh
0x1403ee47d  mov     rbx, 0FFFFFFFFC0000023h
0x1403ee484  jmp     loc_1403EE3BE
0x1403ee489  cmp     [rsi+40h], r8b
0x1403ee48d  jz      short loc_1403EE4C8
0x1403ee48f  call    DxgkpCheckProcessForVirtualMachineManagementAccess
0x1403ee494  xor     r8d, r8d
0x1403ee497  test    al, al
0x1403ee499  jnz     short loc_1403EE4C4
0x1403ee49b  mov     rbx, 0FFFFFFFFC0000022h
0x1403ee4a2  lea     ecx, [r8+2]
0x1403ee4a6  mov     rdx, rbx
0x1403ee4a9  call    cs:__imp_WdLogSingleEntry1
0x1403ee4b0  nop     dword ptr [rax+rax+00h]
0x1403ee4b5  mov     cs:WdLogGlobalForLineNumber, 10E1h
0x1403ee4bf  jmp     loc_1403EFEA9
0x1403ee4c4  mov     ecx, [rsp+0B30h+var_AD8]
0x1403ee4c8  cmp     ebx, 4
0x1403ee4cb  jb      loc_1403EE55F
0x1403ee4d1  test    rdi, rdi
0x1403ee4d4  jz      loc_1403EE55F
0x1403ee4da  mov     r15d, 10h
0x1403ee4e0  cmp     ecx, r15d
0x1403ee4e3  jb      short loc_1403EE55F
0x1403ee4e5  mov     [rsp+0B30h+var_B08], r8b; char
0x1403ee4ea  lea     rcx, [rsp+0B30h+var_AD0]; this
0x1403ee4ef  mov     [rsp+0B30h+var_B10], r8b; char
0x1403ee4f4  mov     r9b, r14b; unsigned __int8
0x1403ee4f7  mov     r8, rsi; struct _IRP *
0x1403ee4fa  mov     rdx, r12; void *
0x1403ee4fd  call    ??0CInterfaceCallContext@@QEAA@PEAXPEAU_IRP@@EEE@Z; CInterfaceCallContext::CInterfaceCallContext(void *,_IRP *,uchar,uchar,uchar)
0x1403ee502  mov     ebx, [rbp+0A30h+var_AB0]
0x1403ee505  test    ebx, ebx
0x1403ee507  js      loc_1403EE402
0x1403ee50d  mov     rcx, rsi
0x1403ee510  call    DpiFdoGetVirtualGpuType
0x1403ee515  movzx   edx, word ptr [rdi]
0x1403ee518  lea     r8, [rbp+0A30h+var_AA0]
0x1403ee51c  mov     r15d, [rsp+0B30h+var_AD8]
0x1403ee521  mov     rcx, [r13+0FC0h]; void *
0x1403ee528  mov     dword ptr [rbp+0A30h+var_AA0], edx
0x1403ee52b  movzx   edx, byte ptr [rdi+2]
0x1403ee52f  mov     dword ptr [rbp+0A30h+var_AA0+4], edx
0x1403ee532  mov     edx, r15d
0x1403ee535  shr     edx, 4
0x1403ee538  mov     dword ptr [rbp+0A30h+var_AA0+8], edx
0x1403ee53b  mov     edx, eax
0x1403ee53d  mov     dword ptr [rbp+0A30h+var_AA0+0Ch], 0
0x1403ee544  mov     [rbp+0A30h+var_A90], rdi
0x1403ee548  call    DxgkDdiQueryMitigatedRanges
0x1403ee54d  mov     edi, r15d
0x1403ee550  mov     ebx, eax
0x1403ee552  test    eax, eax
0x1403ee554  jns     loc_1403EE407
0x1403ee55a  jmp     loc_1403EE402
0x1403ee55f  mov     rdx, 0FFFFFFFFC0000023h
0x1403ee566  mov     ebx, edx
0x1403ee568  mov     ecx, 2
0x1403ee56d  call    cs:__imp_WdLogSingleEntry1
0x1403ee574  nop     dword ptr [rax+rax+00h]
0x1403ee579  mov     cs:WdLogGlobalForLineNumber, 10ECh
0x1403ee583  jmp     loc_1403EFE50
0x1403ee588  cmp     [rsi+40h], r8b
0x1403ee58c  jz      short loc_1403EE5C7
0x1403ee58e  call    DxgkpCheckProcessForVirtualMachineManagementAccess
0x1403ee593  xor     r8d, r8d
0x1403ee596  test    al, al
0x1403ee598  jnz     short loc_1403EE5C3
0x1403ee59a  mov     rbx, 0FFFFFFFFC0000022h
0x1403ee5a1  lea     ecx, [r8+2]
0x1403ee5a5  mov     rdx, rbx
0x1403ee5a8  call    cs:__imp_WdLogSingleEntry1
0x1403ee5af  nop     dword ptr [rax+rax+00h]
0x1403ee5b4  mov     cs:WdLogGlobalForLineNumber, 10B7h
0x1403ee5be  jmp     loc_1403EFEA9
0x1403ee5c3  mov     ecx, [rsp+0B30h+var_AD8]
0x1403ee5c7  cmp     ebx, 2
0x1403ee5ca  jb      loc_1403EE652
0x1403ee5d0  test    rdi, rdi
0x1403ee5d3  jz      short loc_1403EE652
0x1403ee5d5  cmp     ecx, 18h
0x1403ee5d8  jb      short loc_1403EE652
0x1403ee5da  mov     [rsp+0B30h+var_B08], r8b; char
0x1403ee5df  lea     rcx, [rsp+0B30h+var_AD0]; this
0x1403ee5e4  mov     [rsp+0B30h+var_B10], r8b; char
0x1403ee5e9  mov     r9b, r14b; unsigned __int8
0x1403ee5ec  mov     r8, rsi; struct _IRP *
0x1403ee5ef  mov     rdx, r12; void *
0x1403ee5f2  call    ??0CInterfaceCallContext@@QEAA@PEAXPEAU_IRP@@EEE@Z; CInterfaceCallContext::CInterfaceCallContext(void *,_IRP *,uchar,uchar,uchar)
0x1403ee5f7  mov     ebx, [rbp+0A30h+var_AB0]
0x1403ee5fa  test    ebx, ebx
0x1403ee5fc  js      loc_1403EE402
0x1403ee602  mov     rcx, rsi
0x1403ee605  call    DpiFdoGetVirtualGpuType
0x1403ee60a  movzx   ecx, word ptr [rdi]
0x1403ee60d  lea     r8, [rbp+0A30h+var_AA0]
0x1403ee611  mov     dword ptr [rbp+0A30h+var_AA0], ecx
0x1403ee614  xorps   xmm0, xmm0
0x1403ee617  mov     rcx, [r13+0FC0h]; void *
0x1403ee61e  mov     edx, eax
0x1403ee620  movdqu  [rbp+0A30h+var_AA0+4], xmm0
0x1403ee625  mov     [rbp+0A30h+var_A90+4], 0
0x1403ee62d  call    DxgkDdiQueryMitigatedRangeCount
0x1403ee632  mov     ebx, eax
0x1403ee634  test    eax, eax
0x1403ee636  js      loc_1403EE402
0x1403ee63c  movups  xmm0, [rbp+0A30h+var_AA0+4]
0x1403ee640  movsd   xmm1, [rbp+0A30h+var_A90+4]
0x1403ee645  movups  xmmword ptr [rdi], xmm0
0x1403ee648  movsd   qword ptr [rdi+10h], xmm1
0x1403ee64d  jmp     loc_1403EE456
0x1403ee652  mov     rdx, 0FFFFFFFFC0000023h
0x1403ee659  mov     ebx, edx
0x1403ee65b  mov     ecx, 2
0x1403ee660  call    cs:__imp_WdLogSingleEntry1
0x1403ee667  nop     dword ptr [rax+rax+00h]
0x1403ee66c  mov     cs:WdLogGlobalForLineNumber, 10C2h
0x1403ee676  jmp     loc_1403EFE50
0x1403ee67b  mov     rbx, 0FFFFFFFFC00000BBh
0x1403ee682  jmp     loc_1403EFEA9
0x1403ee687  cmp     [rsi+40h], r8b
  ... truncated ...
```
