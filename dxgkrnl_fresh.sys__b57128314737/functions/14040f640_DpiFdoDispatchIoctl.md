# DpiFdoDispatchIoctl

- ea: `0x14040f640`
- end: `0x140411044`
- name: `DpiFdoDispatchIoctl`
- size: `6660`
- prototype: `NTSTATUS __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `42`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140047b0c`
- `0x1400539cc`
- `0x140057440`
- `0x140080570`
- `0x14008067c`
- `0x140080fa4`
- `0x1400815c0`
- `0x140081750`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x14018b498`
- `0x1402792ac`
- `0x1402794f4`
- `0x140279654`
- `0x1402797d4`
- `0x14027988c`
- `0x140279b9c`
- `0x140279cac`
- `0x140279d9c`
- `0x140279f1c`
- `0x140279fdc`
- `0x14027a0e8`
- `0x14027a4f8`
- `0x14027a5d0`
- `0x14027a6a8`
- `0x14027a780`
- `0x14027a858`
- `0x14027abd8`
- `0x14027accc`
- `0x14027add4`
- `0x14027af54`
- `0x14027b0f0`
- `0x14027b1a8`
- `0x1402b5d44`
- `0x1402b5f5c`
- `0x1402b62f0`
- `0x1402b6480`
- `0x1402b6664`
- `0x1402b6740`
- `0x1403e07a8`
- `0x1404012ec`
- `0x14040f640`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140410d28`
- `ntoskrnl!IofCallDriver` at `0x140410d28`
- `ntoskrnl!IofCompleteRequest` at `0x14041100b`
- `ntoskrnl!IofCompleteRequest` at `0x14041100b`
- `ntoskrnl!RtlCopyLuid` at `0x14040f968`
- `ntoskrnl!RtlCopyLuid` at `0x14040f968`
- `watchdog!WdLogSingleEntry1` at `0x14040f6bd`
- `watchdog!WdLogSingleEntry1` at `0x14040f72d`
- `watchdog!WdLogSingleEntry1` at `0x14040f8c1`
- `watchdog!WdLogSingleEntry1` at `0x14040f905`
- `watchdog!WdLogSingleEntry1` at `0x14040f985`
- `watchdog!WdLogSingleEntry1` at `0x14040f9c6`
- `watchdog!WdLogSingleEntry1` at `0x14040fa7d`
- `watchdog!WdLogSingleEntry1` at `0x14040fab7`
- `watchdog!WdLogSingleEntry1` at `0x14040fb6d`
- `watchdog!WdLogSingleEntry1` at `0x14040fbb1`
- `watchdog!WdLogSingleEntry1` at `0x14040fc0f`
- `watchdog!WdLogSingleEntry1` at `0x14040fdb0`
- `watchdog!WdLogSingleEntry1` at `0x14040fe94`
- `watchdog!WdLogSingleEntry1` at `0x14040febd`
- `watchdog!WdLogSingleEntry1` at `0x14040ffb0`
- `watchdog!WdLogSingleEntry1` at `0x14040ffd9`
- `watchdog!WdLogSingleEntry1` at `0x140410081`
- `watchdog!WdLogSingleEntry1` at `0x1404101c0`
- `watchdog!WdLogSingleEntry1` at `0x1404101fa`
- `watchdog!WdLogSingleEntry1` at `0x140410451`
- `watchdog!WdLogSingleEntry1` at `0x14041048b`
- `watchdog!WdLogSingleEntry1` at `0x14041050d`
- `watchdog!WdLogSingleEntry1` at `0x1404105a9`
- `watchdog!WdLogSingleEntry1` at `0x1404105d2`
- `watchdog!WdLogSingleEntry1` at `0x1404106bd`
- `watchdog!WdLogSingleEntry1` at `0x1404106e6`
- `watchdog!WdLogSingleEntry1` at `0x140410782`
- `watchdog!WdLogSingleEntry1` at `0x1404107ab`
- `watchdog!WdLogSingleEntry1` at `0x140410847`
- `watchdog!WdLogSingleEntry1` at `0x140410870`
- `watchdog!WdLogSingleEntry1` at `0x1404108d0`
- `watchdog!WdLogSingleEntry1` at `0x1404108f9`
- `watchdog!WdLogSingleEntry1` at `0x1404109b0`
- `watchdog!WdLogSingleEntry1` at `0x1404109d9`
- `watchdog!WdLogSingleEntry1` at `0x140410a2a`
- `watchdog!WdLogSingleEntry1` at `0x140410a53`
- `watchdog!WdLogSingleEntry1` at `0x140410afd`
- `watchdog!WdLogSingleEntry1` at `0x140410b26`
- `watchdog!WdLogSingleEntry1` at `0x140410bc9`
- `watchdog!WdLogSingleEntry1` at `0x140410bf2`
- `watchdog!WdLogSingleEntry1` at `0x140410c8e`
- `watchdog!WdLogSingleEntry1` at `0x140410cb7`
- `watchdog!WdLogSingleEntry1` at `0x140410db8`
- `watchdog!WdLogSingleEntry1` at `0x140410e6e`
- `watchdog!WdLogSingleEntry1` at `0x140410efa`
- `watchdog!WdLogSingleEntry1` at `0x140410fbd`
- `watchdog!WdLogSingleEntry1` at `0x140410fe3`
- `watchdog!WdLogSingleEntry1` at `0x14040f6bd`
- `watchdog!WdLogSingleEntry1` at `0x14040f72d`
- `watchdog!WdLogSingleEntry1` at `0x14040f8c1`
- `watchdog!WdLogSingleEntry1` at `0x14040f905`
- `watchdog!WdLogSingleEntry1` at `0x14040f985`
- `watchdog!WdLogSingleEntry1` at `0x14040f9c6`
- `watchdog!WdLogSingleEntry1` at `0x14040fa7d`
- `watchdog!WdLogSingleEntry1` at `0x14040fab7`
- `watchdog!WdLogSingleEntry1` at `0x14040fb6d`
- `watchdog!WdLogSingleEntry1` at `0x14040fbb1`
- `watchdog!WdLogSingleEntry1` at `0x14040fc0f`
- `watchdog!WdLogSingleEntry1` at `0x14040fdb0`
- `watchdog!WdLogSingleEntry1` at `0x14040fe94`
- `watchdog!WdLogSingleEntry1` at `0x14040febd`
- `watchdog!WdLogSingleEntry1` at `0x14040ffb0`
- `watchdog!WdLogSingleEntry1` at `0x14040ffd9`
- `watchdog!WdLogSingleEntry1` at `0x140410081`
- `watchdog!WdLogSingleEntry1` at `0x1404101c0`
- `watchdog!WdLogSingleEntry1` at `0x1404101fa`
- `watchdog!WdLogSingleEntry1` at `0x140410451`
- `watchdog!WdLogSingleEntry1` at `0x14041048b`
- `watchdog!WdLogSingleEntry1` at `0x14041050d`
- `watchdog!WdLogSingleEntry1` at `0x1404105a9`
- `watchdog!WdLogSingleEntry1` at `0x1404105d2`
- `watchdog!WdLogSingleEntry1` at `0x1404106bd`
- `watchdog!WdLogSingleEntry1` at `0x1404106e6`
- `watchdog!WdLogSingleEntry1` at `0x140410782`
- `watchdog!WdLogSingleEntry1` at `0x1404107ab`
- `watchdog!WdLogSingleEntry1` at `0x140410847`
- `watchdog!WdLogSingleEntry1` at `0x140410870`
- `watchdog!WdLogSingleEntry1` at `0x1404108d0`
- `watchdog!WdLogSingleEntry1` at `0x1404108f9`
- `watchdog!WdLogSingleEntry1` at `0x1404109b0`
- `watchdog!WdLogSingleEntry1` at `0x1404109d9`
- `watchdog!WdLogSingleEntry1` at `0x140410a2a`
- `watchdog!WdLogSingleEntry1` at `0x140410a53`
- `watchdog!WdLogSingleEntry1` at `0x140410afd`
- `watchdog!WdLogSingleEntry1` at `0x140410b26`
- `watchdog!WdLogSingleEntry1` at `0x140410bc9`
- `watchdog!WdLogSingleEntry1` at `0x140410bf2`
- `watchdog!WdLogSingleEntry1` at `0x140410c8e`
- `watchdog!WdLogSingleEntry1` at `0x140410cb7`
- `watchdog!WdLogSingleEntry1` at `0x140410db8`
- `watchdog!WdLogSingleEntry1` at `0x140410e6e`
- `watchdog!WdLogSingleEntry1` at `0x140410efa`
- `watchdog!WdLogSingleEntry1` at `0x140410fbd`
- `watchdog!WdLogSingleEntry1` at `0x140410fe3`

## pseudocode

```c
NTSTATUS __fastcall DpiFdoDispatchIoctl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PVOID DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  unsigned int LowPart; // ebx
  NTSTATUS MitigatedRangeCount; // ebx
  ULONG Length; // eax
  unsigned int Options; // r12d
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int VirtualGpuType; // eax
  char v14; // zf
  struct _IRP *MasterIrp; // rdi
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  __int64 v23; // rdx
  int v24; // ebx
  void *v25; // rcx
  unsigned int v26; // r12d
  int GpuPartitionInfo; // eax
  unsigned __int32 v28; // eax
  ULONG_PTR v29; // rdi
  __int64 v30; // rdx
  void *v31; // rcx
  int MitigatedRanges; // eax
  __int64 v33; // rdx
  void *v34; // rcx
  __int64 v35; // xmm1_8
  NTSTATUS v36; // eax
  unsigned int v37; // eax
  __int64 v38; // r12
  __int64 v39; // rdx
  unsigned int v40; // ebx
  unsigned int v41; // ebx
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  unsigned int v45; // ebx
  __int64 v46; // rdx
  NTSTATUS v47; // eax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rdx
  unsigned int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rdx
  int v55; // eax
  __int64 v56; // rbx
  int v57; // r14d
  void *v58; // r15
  char v59; // cl
  char v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rdx
  unsigned int v63; // ebx
  unsigned int v64; // ebx
  unsigned int v65; // ebx
  unsigned int v66; // ebx
  unsigned int v67; // ebx
  unsigned int v68; // ebx
  unsigned int v69; // ebx
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // r12
  __int64 v74; // rdx
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rdx
  int DirtyBitplane; // eax
  __int64 v79; // rdx
  unsigned int v80; // ebx
  unsigned int v81; // ebx
  unsigned int v82; // ebx
  unsigned int v83; // ebx
  unsigned int v84; // ebx
  unsigned int v85; // ebx
  NTSTATUS VirtualizationFlags; // eax
  __int64 v88; // rdx
  __int64 v89; // rdx
  int v90; // eax
  __int64 v91; // rdx
  int TransferSize; // eax
  __int64 v93; // r14
  __int64 MdlAddress; // [rsp+30h] [rbp-D0h]
  ULONG_PTR v95; // [rsp+40h] [rbp-C0h]
  __int64 v96; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v97[16]; // [rsp+50h] [rbp-B0h] BYREF
  void *v98; // [rsp+60h] [rbp-A0h]
  int v99; // [rsp+70h] [rbp-90h]
  __int64 v100; // [rsp+80h] [rbp-80h] BYREF
  __m256i v101; // [rsp+88h] [rbp-78h] BYREF
  int Type; // [rsp+B0h] [rbp-50h]
  _DWORD v103[41]; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v104[306]; // [rsp+160h] [rbp+60h] BYREF

  DeviceExtension = a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v95 = 0;
  v100 = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( *((_BYTE *)DeviceExtension + 1158) && (!*((_BYTE *)DeviceExtension + 1159) || LowPart != 2345988) )
  {
    MitigatedRangeCount = -1073741637;
    WdLogSingleEntry1(2, -1073741637);
    WdLogGlobalForLineNumber = 3876;
LABEL_274:
    v29 = 0;
LABEL_275:
    a2->IoStatus.Status = MitigatedRangeCount;
    a2->IoStatus.Information = v29;
    IofCompleteRequest(a2, 1);
    return MitigatedRangeCount;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  Options = CurrentStackLocation->Parameters.Create.Options;
  LODWORD(v96) = Length;
  IsEnabledDeviceUsageNoInline = Feature_Servicing_MSRC106447__private_IsEnabledDeviceUsageNoInline();
  v12 = 0;
  if ( IsEnabledDeviceUsageNoInline && LowPart - 2253892 <= 0x58 )
  {
    VirtualGpuType = DpiFdoGetVirtualGpuType(a2, 0);
    v12 = 0;
    v14 = VirtualGpuType ? *((_QWORD *)DeviceExtension + 363) == 0 : *((_BYTE *)a1->DeviceExtension + 5144) == 0;
    if ( v14 )
    {
      MitigatedRangeCount = -1073741637;
      WdLogSingleEntry1(2, -1073741637);
      WdLogGlobalForLineNumber = 3908;
      goto LABEL_274;
    }
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( LowPart <= 0x22646C )
  {
    if ( LowPart == 2253932 )
    {
      Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
      if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
      {
        MitigatedRangeCount = -1073741637;
        WdLogSingleEntry1(2, -1073741637);
        WdLogGlobalForLineNumber = 4568;
        goto LABEL_269;
      }
      if ( Options < 0x18 || !MasterIrp )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2, -1073741789);
        WdLogGlobalForLineNumber = 4577;
        goto LABEL_274;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v99;
      if ( v99 >= 0 )
      {
        DpiFdoGetVirtualGpuType(a2, v62);
        v47 = DxgkDdiRestoreImmutableMigrationData(*((void **)DeviceExtension + 504), *(_QWORD *)&MasterIrp->Flags);
        goto LABEL_97;
      }
      goto LABEL_268;
    }
    if ( LowPart <= 0x226448 )
    {
      if ( LowPart != 2253896 )
      {
        v16 = LowPart - 2252868;
        if ( v16 )
        {
          v17 = v16 - 4;
          if ( v17 )
          {
            v18 = v17 - 4;
            if ( v18 )
            {
              v19 = v18 - 4;
              if ( v19 )
              {
                v20 = v19 - 4;
                if ( !v20 )
                {
                  MitigatedRangeCount = -1073741637;
                  goto LABEL_274;
                }
                v21 = v20 - 4;
                if ( v21 )
                {
                  v22 = v21 - 4;
                  if ( v22 )
                  {
                    if ( v22 == 1000 )
                    {
                      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
                      MitigatedRangeCount = v99;
                      if ( v99 < 0 )
                        goto LABEL_39;
                      memset(&v101, 0, 24);
                      if ( !MasterIrp || (v24 = v96, (unsigned int)v96 < 0x18) )
                      {
                        WdLogSingleEntry1(3, 2253892);
                        WdLogGlobalForLineNumber = 3936;
                        MitigatedRangeCount = -1073741789;
                        goto LABEL_35;
                      }
                      LODWORD(v96) = DpiFdoGetVirtualGpuType(a2, v23);
                      v101.m256i_i64[1] = (__int64)(&MasterIrp->Flags + 1);
                      v25 = (void *)*((_QWORD *)DeviceExtension + 504);
                      v26 = (unsigned int)(v24 - 20) >> 1;
                      v101.m256i_i32[0] = v26;
                      GpuPartitionInfo = DxgkDdiGetGpuPartitionInfo(v25);
                      MitigatedRangeCount = GpuPartitionInfo;
                      if ( GpuPartitionInfo >= 0 )
                      {
                        v28 = v101.m256i_i32[0];
                        if ( g_LimitNumberOfVfs && v101.m256i_i32[0] )
                        {
                          v101.m256i_i32[0] = 1;
                          *(_WORD *)v101.m256i_i64[1] = 1;
                          v28 = v101.m256i_i32[0];
                          v101.m256i_i16[8] = 1;
                        }
                        if ( v28 <= v26 && v28 )
                        {
                          *(_DWORD *)&MasterIrp->Type = v28;
                          WORD2(MasterIrp->MdlAddress) = v101.m256i_i16[8];
                          MasterIrp->Flags = MasterIrp->Flags & 0xFFFFFFFE
                                           | ((unsigned __int8)DpiFdoIsPostDevice(a1) != 0);
                          DxgkDdiQueryPhysicalFunctionLuid(*((void **)DeviceExtension + 504));
                          v29 = (unsigned int)(2 * v101.m256i_i32[0] + 20);
LABEL_40:
                          CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)v97);
                          goto LABEL_270;
                        }
                        WdLogSingleEntry1(3, 2253892);
                        WdLogGlobalForLineNumber = 3961;
                        MitigatedRangeCount = -1073741811;
LABEL_35:
                        CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)v97);
                        goto LABEL_274;
                      }
                      if ( GpuPartitionInfo != -1073741789 )
                      {
LABEL_39:
                        v29 = 0;
                        goto LABEL_40;
                      }
                      if ( !v101.m256i_i32[0] )
                      {
                        WdLogSingleEntry1(3, 2253892);
                        WdLogGlobalForLineNumber = 3985;
                        MitigatedRangeCount = -1073741811;
                        goto LABEL_39;
                      }
                      *(_DWORD *)&MasterIrp->Type = v101.m256i_i32[0];
                      MitigatedRangeCount = -2147483643;
                      WORD2(MasterIrp->MdlAddress) = v101.m256i_i16[8];
                      MasterIrp->Flags = MasterIrp->Flags & 0xFFFFFFFE | ((unsigned __int8)DpiFdoIsPostDevice(a1) != 0);
                      RtlCopyLuid((PLUID)(&MasterIrp->Size + 1), (PLUID)DeviceExtension + 337);
LABEL_42:
                      v29 = 24;
                      goto LABEL_40;
                    }
LABEL_240:
                    ++a2->CurrentLocation;
                    ++a2->Tail.Overlay.CurrentStackLocation;
                    return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 20), a2);
                  }
                  if ( a2->RequestorMode && !DxgkpCheckProcessForVirtualMachineManagementAccess() )
                  {
                    MitigatedRangeCount = -1073741790;
                    WdLogSingleEntry1(2, -1073741790);
                    WdLogGlobalForLineNumber = 4355;
                    goto LABEL_274;
                  }
                  if ( Options >= 4 && MasterIrp && (unsigned int)v96 >= 0x10 )
                  {
                    CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
                    MitigatedRangeCount = v99;
                    if ( v99 < 0 )
                      goto LABEL_39;
                    DpiFdoGetVirtualGpuType(a2, v30);
                    v31 = (void *)*((_QWORD *)DeviceExtension + 504);
                    v101.m256i_i32[0] = (unsigned __int16)MasterIrp->Type;
                    v101.m256i_i32[1] = LOBYTE(MasterIrp->Size);
                    v101.m256i_i64[1] = (unsigned int)v96 >> 4;
                    v101.m256i_i64[2] = (__int64)MasterIrp;
                    MitigatedRanges = DxgkDdiQueryMitigatedRanges(v31);
                    v29 = (unsigned int)v96;
LABEL_52:
                    MitigatedRangeCount = MitigatedRanges;
                    if ( MitigatedRanges >= 0 )
                      goto LABEL_40;
                    goto LABEL_39;
                  }
                  MitigatedRangeCount = -1073741789;
                  WdLogSingleEntry1(2, -1073741789);
                  WdLogGlobalForLineNumber = 4366;
                }
                else
                {
                  if ( a2->RequestorMode && !DxgkpCheckProcessForVirtualMachineManagementAccess() )
                  {
                    MitigatedRangeCount = -1073741790;
                    WdLogSingleEntry1(2, -1073741790);
                    WdLogGlobalForLineNumber = 4313;
                    goto LABEL_274;
                  }
                  if ( Options >= 2 && MasterIrp && (unsigned int)v96 >= 0x18 )
                  {
                    CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
                    MitigatedRangeCount = v99;
                    if ( v99 < 0 )
                      goto LABEL_39;
                    DpiFdoGetVirtualGpuType(a2, v33);
                    v101.m256i_i32[0] = (unsigned __int16)MasterIrp->Type;
                    v34 = (void *)*((_QWORD *)DeviceExtension + 504);
                    memset((char *)v101.m256i_i64 + 4, 0, 24);
                    MitigatedRangeCount = DxgkDdiQueryMitigatedRangeCount(v34);
                    if ( MitigatedRangeCount < 0 )
                      goto LABEL_39;
                    v35 = *(__int64 *)((char *)&v101.m256i_i64[2] + 4);
                    *(_OWORD *)&MasterIrp->Type = *(_OWORD *)((char *)v101.m256i_i64 + 4);
                    *(_QWORD *)&MasterIrp->Flags = v35;
                    goto LABEL_42;
                  }
                  MitigatedRangeCount = -1073741789;
                  WdLogSingleEntry1(2, -1073741789);
                  WdLogGlobalForLineNumber = 4324;
                }
                goto LABEL_269;
              }
              if ( a2->RequestorMode && !DxgkpCheckProcessForVirtualMachineManagementAccess() )
              {
                MitigatedRangeCount = -1073741790;
                WdLogSingleEntry1(2, -1073741790);
                WdLogGlobalForLineNumber = 4415;
                goto LABEL_274;
              }
              DpiFdoGetVirtualGpuType(a2, v12);
              v36 = DpiSriovDetach(a1);
            }
            else
            {
              v36 = DpiSriovAttach(a1, a2);
            }
          }
          else
          {
            if ( a2->RequestorMode && !DxgkpCheckProcessForVirtualMachineManagementAccess() )
            {
              MitigatedRangeCount = -1073741790;
              WdLogSingleEntry1(2, -1073741790);
              WdLogGlobalForLineNumber = 4430;
              goto LABEL_274;
            }
            v37 = DpiFdoGetVirtualGpuType(a2, v12);
            v36 = DpiSriovEventComplete(a1, v37, MasterIrp, Options);
          }
        }
        else
        {
          v36 = DpiSriovNotification(a1, a2);
        }
        goto LABEL_70;
      }
      if ( Options < 2 || !MasterIrp || (v38 = 168, (unsigned int)v96 < 0xA8) )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2, -1073741789);
        WdLogGlobalForLineNumber = 4018;
        goto LABEL_269;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v99;
      if ( v99 < 0 )
        goto LABEL_39;
      DpiFdoGetVirtualGpuType(a2, v39);
      memset(v103, 0, sizeof(v103));
      Type = (unsigned __int16)MasterIrp->Type;
      MitigatedRangeCount = DxgkDdiGetVirtualGpuProfile(*((void **)DeviceExtension + 504));
      if ( MitigatedRangeCount < 0 )
        goto LABEL_39;
      *(_DWORD *)&MasterIrp->Type = Type;
      *(_DWORD *)(&MasterIrp->Size + 1) = v103[0];
      MasterIrp->MdlAddress = *(PMDL *)&v103[1];
      *(_QWORD *)&MasterIrp->Flags = *(_QWORD *)&v103[3];
      MasterIrp->AssociatedIrp.MasterIrp = *(struct _IRP **)&v103[5];
      MasterIrp->ThreadListEntry.Flink = *(struct _LIST_ENTRY **)&v103[7];
      MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)&v103[9];
      MasterIrp->IoStatus.Pointer = *(PVOID *)&v103[11];
      MasterIrp->IoStatus.Information = *(_QWORD *)&v103[13];
      *(_QWORD *)&MasterIrp->RequestorMode = *(_QWORD *)&v103[15];
      MasterIrp->UserIosb = *(PIO_STATUS_BLOCK *)&v103[17];
      MasterIrp->UserEvent = *(PKEVENT *)&v103[19];
      MasterIrp->Overlay.AllocationSize.QuadPart = *(_QWORD *)&v103[21];
      MasterIrp->Overlay.AsynchronousParameters.UserApcContext = *(PVOID *)&v103[23];
      MasterIrp->CancelRoutine = *(PDRIVER_CANCEL *)&v103[25];
      MasterIrp->UserBuffer = *(PVOID *)&v103[27];
      MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = *(struct _LIST_ENTRY **)&v103[29];
      MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = *(struct _LIST_ENTRY **)&v103[31];
      MasterIrp->Tail.Overlay.DriverContext[2] = *(PVOID *)&v103[33];
      MasterIrp->Tail.Overlay.DriverContext[3] = *(PVOID *)&v103[35];
      MasterIrp->Tail.Overlay.Thread = *(PETHREAD *)&v103[37];
      MasterIrp->Tail.Overlay.AuxiliaryBuffer = *(PCHAR *)&v103[39];
LABEL_83:
      v29 = v38;
      goto LABEL_40;
    }
    v40 = LowPart - 2253900;
    if ( !v40 )
    {
      if ( a2->RequestorMode && !DxgkpCheckProcessForVirtualMachineManagementAccess() )
      {
        MitigatedRangeCount = -1073741790;
        WdLogSingleEntry1(2, -1073741790);
        WdLogGlobalForLineNumber = 4073;
        goto LABEL_274;
      }
      if ( Options < 2 || !MasterIrp )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2, -1073741789);
        WdLogGlobalForLineNumber = 4084;
        goto LABEL_269;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v99;
      if ( v99 >= 0 )
      {
        DpiFdoGetVirtualGpuType(a2, v61);
        LODWORD(v96) = (unsigned __int16)MasterIrp->Type;
        v47 = DxgkDdiSetGpuPartitionCount(*((void **)DeviceExtension + 504));
        goto LABEL_97;
      }
LABEL_268:
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)v97);
      goto LABEL_269;
    }
    v41 = v40 - 8;
    if ( !v41 )
    {
      if ( a2->RequestorMode && !DxgkpCheckProcessForVirtualMachineManagementAccess() )
      {
        MitigatedRangeCount = -1073741790;
        WdLogSingleEntry1(2, -1073741790);
        WdLogGlobalForLineNumber = 4108;
        goto LABEL_274;
      }
      if ( Options >= 0x78 && MasterIrp && (unsigned int)v96 >= 0x88 )
      {
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 0, 0, 1);
        MitigatedRangeCount = v99;
        if ( v99 >= 0 )
        {
          v55 = DpiFdoGetVirtualGpuType(a2, v54);
          v56 = *(_QWORD *)&MasterIrp->Flags;
          v57 = v55;
          if ( v56 || MasterIrp->AssociatedIrp.MasterIrp || MasterIrp->ThreadListEntry.Flink )
          {
            memset(v104, 0, sizeof(v104));
            v14 = BYTE2(MasterIrp->UserBuffer) == 0;
            v58 = v98;
            LODWORD(v104[0]) = (unsigned __int16)MasterIrp->Type;
            v59 = !v14;
            v14 = BYTE1(MasterIrp->UserBuffer) == 0;
            v104[2] = (__int64)MasterIrp->AssociatedIrp.MasterIrp;
            v60 = !v14;
            v14 = LOBYTE(MasterIrp->UserBuffer) == 0;
            v104[3] = (__int64)MasterIrp->ThreadListEntry.Flink;
            v104[4] = (__int64)MasterIrp->ThreadListEntry.Blink;
            v104[5] = (__int64)MasterIrp->IoStatus.Pointer;
            v104[6] = MasterIrp->IoStatus.Information;
            v104[7] = *(_QWORD *)&MasterIrp->RequestorMode;
            v104[8] = (__int64)MasterIrp->UserIosb;
            v104[9] = (__int64)MasterIrp->UserEvent;
            v104[10] = MasterIrp->Overlay.AllocationSize.QuadPart;
            v104[11] = (__int64)MasterIrp->Overlay.AsynchronousParameters.UserApcContext;
            v104[12] = (__int64)MasterIrp->CancelRoutine;
            MdlAddress = (__int64)MasterIrp->MdlAddress;
            v104[1] = v56;
            MitigatedRangeCount = DxgkDdiCreateVirtualGpu((ADAPTER_RENDER **)v98, v57, v14, v60, v59, v104, MdlAddress);
            if ( MitigatedRangeCount >= 0 )
            {
              memset(v103, 0, 0x64u);
              Type = v104[0];
              MitigatedRangeCount = DxgkDdiGetVirtualGpuInfo(v58, (__int64)(&MasterIrp->Flags + 1));
              if ( MitigatedRangeCount >= 0 )
              {
                LOWORD(MasterIrp->MdlAddress) = v104[0];
                MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)&v103[1];
                MasterIrp->IoStatus.Pointer = *(PVOID *)&v103[3];
                MasterIrp->IoStatus.Information = *(_QWORD *)&v103[5];
                *(_QWORD *)&MasterIrp->RequestorMode = *(_QWORD *)&v103[7];
                MasterIrp->UserIosb = *(PIO_STATUS_BLOCK *)&v103[9];
                MasterIrp->UserEvent = *(PKEVENT *)&v103[11];
                MasterIrp->Overlay.AllocationSize.QuadPart = *(_QWORD *)&v103[13];
                MasterIrp->Overlay.AsynchronousParameters.UserApcContext = *(PVOID *)&v103[15];
                MasterIrp->CancelRoutine = *(PDRIVER_CANCEL *)&v103[17];
                MasterIrp->UserBuffer = *(PVOID *)&v103[19];
                MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = *(struct _LIST_ENTRY **)&v103[21];
                MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = *(struct _LIST_ENTRY **)&v103[23];
                v29 = 136;
                goto LABEL_40;
              }
              LODWORD(v96) = v104[0];
              DxgkDdiDestroyVirtualGpu(v58);
            }
          }
          else
          {
            LODWORD(v96) = (unsigned __int16)MasterIrp->Type;
            MitigatedRangeCount = DxgkDdiDestroyVirtualGpu(v98);
          }
        }
        goto LABEL_39;
      }
      MitigatedRangeCount = -1073741789;
      WdLogSingleEntry1(2, -1073741789);
      WdLogGlobalForLineNumber = 4121;
      goto LABEL_269;
    }
    v42 = v41 - 4;
    if ( !v42 )
    {
      if ( Options < 2 || !MasterIrp || (v38 = 128, (unsigned int)v96 < 0x80) )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2, -1073741789);
        WdLogGlobalForLineNumber = 4230;
        goto LABEL_269;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v99;
      if ( v99 < 0 )
        goto LABEL_39;
      DpiFdoGetVirtualGpuType(a2, v53);
      memset(v103, 0, 0x64u);
      Type = (unsigned __int16)MasterIrp->Type;
      MitigatedRangeCount = DxgkDdiGetVirtualGpuInfo(
                              *((void **)DeviceExtension + 504),
                              (__int64)&MasterIrp->MdlAddress + 4);
      if ( MitigatedRangeCount < 0 )
        goto LABEL_39;
      MasterIrp->Type = Type;
      MasterIrp->ThreadListEntry.Flink = *(struct _LIST_ENTRY **)&v103[1];
      MasterIrp->ThreadListEntry.Blink = *(struct _LIST_ENTRY **)&v103[3];
      MasterIrp->IoStatus.Pointer = *(PVOID *)&v103[5];
      MasterIrp->IoStatus.Information = *(_QWORD *)&v103[7];
      *(_QWORD *)&MasterIrp->RequestorMode = *(_QWORD *)&v103[9];
      MasterIrp->UserIosb = *(PIO_STATUS_BLOCK *)&v103[11];
      MasterIrp->UserEvent = *(PKEVENT *)&v103[13];
      MasterIrp->Overlay.AllocationSize.QuadPart = *(_QWORD *)&v103[15];
      MasterIrp->Overlay.AsynchronousParameters.UserApcContext = *(PVOID *)&v103[17];
      MasterIrp->CancelRoutine = *(PDRIVER_CANCEL *)&v103[19];
      MasterIrp->UserBuffer = *(PVOID *)&v103[21];
      MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = *(struct _LIST_ENTRY **)&v103[23];
      goto LABEL_83;
    }
    v43 = v42 - 4;
    if ( v43 )
    {
      v44 = v43 - 4;
      if ( !v44 )
      {
        if ( Options >= 8 && MasterIrp )
        {
          CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 0, 1, 0);
          MitigatedRangeCount = v99;
          if ( v99 < 0 )
            goto LABEL_39;
          v51 = DpiFdoGetVirtualGpuType(a2, v50);
          v101.m256i_i64[1] = (unsigned int)v96;
          v52 = *((_QWORD *)DeviceExtension + 504);
          v101.m256i_i32[0] = 0;
          v101.m256i_i32[1] = Options;
          v101.m256i_i64[2] = (__int64)MasterIrp;
          v101.m256i_i64[3] = (__int64)MasterIrp;
          MitigatedRanges = ADAPTER_RENDER::VirtualGpuDriverEscape(
                              *(_QWORD *)(v52 + 3256),
                              v51,
                              (__int64)MasterIrp,
                              &v101);
          v29 = v101.m256i_u32[2];
          goto LABEL_52;
        }
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2, -1073741789);
        WdLogGlobalForLineNumber = 4282;
        goto LABEL_269;
      }
      v45 = v44 - 4;
      if ( !v45 )
      {
        Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) != 0 )
        {
          if ( Options < 0xC || !MasterIrp || (unsigned int)v96 < 0x20 )
          {
            MitigatedRangeCount = -1073741789;
            WdLogSingleEntry1(2, -1073741789);
            WdLogGlobalForLineNumber = 4493;
            goto LABEL_274;
          }
          CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 0, 0, 1);
          MitigatedRangeCount = v99;
          if ( v99 >= 0 )
          {
            DpiFdoGetVirtualGpuType(a2, v48);
            LODWORD(v96) = ((int)v96 - 8) / 0x18u;
            MitigatedRangeCount = DxgkDdiPrepareLiveMigration(v98, (__int64)&MasterIrp->MdlAddress, (__int64)&v96);
            v49 = (unsigned int)v96;
            *(_DWORD *)&MasterIrp->Type = v96;
            if ( MitigatedRangeCount >= 0 )
            {
              v29 = 24 * v49 + 8;
              goto LABEL_40;
            }
          }
          goto LABEL_39;
        }
        MitigatedRangeCount = -1073741637;
        WdLogSingleEntry1(2, -1073741637);
        WdLogGlobalForLineNumber = 4482;
        goto LABEL_269;
      }
      if ( v45 != 4 )
        goto LABEL_240;
      Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
      if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
      {
        MitigatedRangeCount = -1073741637;
        WdLogSingleEntry1(2, -1073741637);
        WdLogGlobalForLineNumber = 4534;
        goto LABEL_269;
      }
      if ( Options < 0x18 || !MasterIrp )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2, -1073741789);
        WdLogGlobalForLineNumber = 4543;
        goto LABEL_274;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v99;
      if ( v99 >= 0 )
      {
        DpiFdoGetVirtualGpuType(a2, v46);
        v47 = DxgkDdiSaveImmutableMigrationData(*((void **)DeviceExtension + 504), *(_QWORD *)&MasterIrp->Flags);
LABEL_97:
        MitigatedRangeCount = v47;
        goto LABEL_268;
      }
      goto LABEL_268;
    }
    v36 = DpiSetPartitionVmbus(a1, a2, a2->AssociatedIrp.MasterIrp, Options);
LABEL_70:
    MitigatedRangeCount = v36;
LABEL_269:
    v29 = v95;
    goto LABEL_270;
  }
  if ( LowPart <= 0x226490 )
  {
    if ( LowPart == 2253968 )
    {
      Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
      if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
      {
        MitigatedRangeCount = -1073741637;
        WdLogSingleEntry1(2, -1073741637);
        WdLogGlobalForLineNumber = 4920;
        goto LABEL_269;
      }
      if ( Options < 0x20 || !MasterIrp )
      {
        MitigatedRangeCount = -1073741789;
        WdLogSingleEntry1(2, -1073741789);
        WdLogGlobalForLineNumber = 4929;
        goto LABEL_274;
      }
      CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
      MitigatedRangeCount = v99;
      if ( v99 >= 0 )
      {
        DpiFdoGetVirtualGpuType(a2, v79);
        v47 = DxgkDdiWriteVirtualizedInterrupt(*((void **)DeviceExtension + 504), (__int64)&MasterIrp->Flags);
        goto LABEL_97;
      }
      goto LABEL_268;
    }
    v63 = LowPart - 2253936;
    if ( v63 )
    {
      v64 = v63 - 4;
      if ( v64 )
      {
        v65 = v64 - 4;
        if ( !v65 )
        {
          Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
          if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
          {
            MitigatedRangeCount = -1073741637;
            WdLogSingleEntry1(2, -1073741637);
            WdLogGlobalForLineNumber = 4791;
            goto LABEL_269;
          }
          if ( Options < 0x10 || !MasterIrp )
          {
            MitigatedRangeCount = -1073741789;
            WdLogSingleEntry1(2, -1073741789);
            WdLogGlobalForLineNumber = 4800;
            goto LABEL_274;
          }
          v36 = DpiLiveMigrationWaitForFence(a1, a2, 0);
          goto LABEL_70;
        }
        v66 = v65 - 4;
        if ( v66 )
        {
          v67 = v66 - 4;
          if ( !v67 )
          {
            Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
            if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
            {
              MitigatedRangeCount = -1073741637;
              WdLogSingleEntry1(2, -1073741637);
              WdLogGlobalForLineNumber = 4860;
              goto LABEL_269;
            }
            if ( Options < 0x10 || !MasterIrp )
            {
              MitigatedRangeCount = -1073741789;
              WdLogSingleEntry1(2, -1073741789);
              WdLogGlobalForLineNumber = 4869;
              goto LABEL_274;
            }
            v36 = DpiLiveMigrationWaitForFence(a1, a2, 1);
            goto LABEL_70;
          }
          v68 = v67 - 4;
          if ( v68 )
          {
            v69 = v68 - 4;
            if ( v69 )
            {
              if ( v69 != 4 )
                goto LABEL_240;
              Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
              if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
              {
                MitigatedRangeCount = -1073741637;
                WdLogSingleEntry1(2, -1073741637);
                WdLogGlobalForLineNumber = 4888;
                goto LABEL_269;
              }
              if ( Options < 8 || !MasterIrp )
              {
                MitigatedRangeCount = -1073741789;
                WdLogSingleEntry1(2, -1073741789);
                WdLogGlobalForLineNumber = 4897;
                goto LABEL_274;
              }
              CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
              MitigatedRangeCount = v99;
              if ( v99 >= 0 )
              {
                DpiFdoGetVirtualGpuType(a2, v70);
                v47 = DxgkDdiEndLiveMigration(*((void **)DeviceExtension + 504));
                goto LABEL_97;
              }
            }
            else
            {
              Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
              if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
              {
                MitigatedRangeCount = -1073741637;
                WdLogSingleEntry1(2, -1073741637);
                WdLogGlobalForLineNumber = 4637;
                goto LABEL_269;
              }
              if ( Options < 0x18 || !MasterIrp )
              {
                MitigatedRangeCount = -1073741789;
                WdLogSingleEntry1(2, -1073741789);
                WdLogGlobalForLineNumber = 4646;
                goto LABEL_274;
              }
              CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
              MitigatedRangeCount = v99;
              if ( v99 >= 0 )
              {
                DpiFdoGetVirtualGpuType(a2, v71);
                v47 = DxgkDdiRestoreMutableMigrationData(
                        *((void **)DeviceExtension + 504),
                        *(_QWORD *)&MasterIrp->Flags);
                goto LABEL_97;
              }
            }
          }
          else
          {
            Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
            if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
            {
              MitigatedRangeCount = -1073741637;
              WdLogSingleEntry1(2, -1073741637);
              WdLogGlobalForLineNumber = 4603;
              goto LABEL_269;
            }
            if ( Options < 0x18 || !MasterIrp )
            {
              MitigatedRangeCount = -1073741789;
              WdLogSingleEntry1(2, -1073741789);
              WdLogGlobalForLineNumber = 4612;
              goto LABEL_274;
            }
            CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
            MitigatedRangeCount = v99;
            if ( v99 >= 0 )
            {
              DpiFdoGetVirtualGpuType(a2, v72);
              v47 = DxgkDdiSaveMutableMigrationData(*((void **)DeviceExtension + 504), *(_QWORD *)&MasterIrp->Flags);
              goto LABEL_97;
            }
          }
          goto LABEL_268;
        }
        Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
        {
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2, -1073741637);
          WdLogGlobalForLineNumber = 4819;
          goto LABEL_269;
        }
        if ( Options < 0xC || !MasterIrp || (v73 = 8, (unsigned int)v96 < 8) )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2, -1073741789);
          WdLogGlobalForLineNumber = 4830;
          goto LABEL_274;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v99;
        if ( v99 < 0 )
          goto LABEL_268;
        DpiFdoGetVirtualGpuType(a2, v74);
        MitigatedRangeCount = DxgkSendDirtyToVRAM(*((void **)DeviceExtension + 504), (__int64)MasterIrp);
      }
      else
      {
        Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
        if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
        {
          MitigatedRangeCount = -1073741637;
          WdLogSingleEntry1(2, -1073741637);
          WdLogGlobalForLineNumber = 4749;
          goto LABEL_269;
        }
        if ( Options < 0xC || !MasterIrp || (v73 = 16, (unsigned int)v96 < 0x10) )
        {
          MitigatedRangeCount = -1073741789;
          WdLogSingleEntry1(2, -1073741789);
          WdLogGlobalForLineNumber = 4760;
          goto LABEL_274;
        }
        CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
        MitigatedRangeCount = v99;
        if ( v99 < 0 )
          goto LABEL_268;
        DpiFdoGetVirtualGpuType(a2, v76);
        MitigatedRangeCount = DxgkFillBufferWithDirty(*((void **)DeviceExtension + 504), (__int64)MasterIrp);
        LODWORD(MasterIrp->MdlAddress) = MitigatedRangeCount;
      }
      v75 = 0;
      if ( MitigatedRangeCount >= 0 )
        v75 = v73;
      v95 = v75;
      goto LABEL_268;
    }
    Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
    if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
    {
      MitigatedRangeCount = -1073741637;
      WdLogSingleEntry1(2, -1073741637);
      WdLogGlobalForLineNumber = 4671;
      goto LABEL_269;
    }
    if ( Options < 0xC || !MasterIrp || (unsigned int)v96 < 4 )
    {
      MitigatedRangeCount = -1073741789;
      WdLogSingleEntry1(2, -1073741789);
      WdLogGlobalForLineNumber = 4682;
      goto LABEL_274;
    }
    CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
    MitigatedRangeCount = v99;
    if ( v99 < 0 )
      goto LABEL_39;
    DpiFdoGetVirtualGpuType(a2, v77);
    DirtyBitplane = DxgkDdiGetDirtyBitplane(*((void **)DeviceExtension + 504));
    MitigatedRangeCount = DirtyBitplane;
    goto LABEL_222;
  }
  v80 = LowPart - 2253972;
  if ( !v80 )
  {
    Feature_GpupLiveMigration_dxgkrnl__private_IsEnabledPreCheck(v11, 0);
    if ( (*((_DWORD *)DeviceExtension + 1398) & 4) == 0 )
    {
      MitigatedRangeCount = -1073741637;
      WdLogSingleEntry1(2, -1073741637);
      WdLogGlobalForLineNumber = 4709;
      goto LABEL_274;
    }
    if ( Options < 8 || !MasterIrp || (unsigned int)v96 < 8 )
    {
      MitigatedRangeCount = -1073741789;
      WdLogSingleEntry1(2, -1073741789);
      WdLogGlobalForLineNumber = 4720;
      goto LABEL_274;
    }
    CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
    MitigatedRangeCount = v99;
    if ( v99 >= 0 )
    {
      DpiFdoGetVirtualGpuType(a2, v91);
      TransferSize = DxgkLiveMigrationGetTransferSize(*((void **)DeviceExtension + 504));
      v93 = 0;
      MitigatedRangeCount = TransferSize;
      if ( TransferSize >= 0 )
        v93 = 8;
      v95 = v93;
    }
    goto LABEL_268;
  }
  v81 = v80 - 4;
  if ( !v81 )
  {
    if ( Options < 8 || !MasterIrp || (unsigned int)v96 < 4 )
    {
      MitigatedRangeCount = -1073741789;
      WdLogSingleEntry1(2, -1073741789);
      WdLogGlobalForLineNumber = 4957;
      goto LABEL_269;
    }
    CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
    MitigatedRangeCount = v99;
    if ( v99 < 0 )
      goto LABEL_39;
    v90 = DpiFdoGetVirtualGpuType(a2, v89);
    *(_DWORD *)&MasterIrp->Type = 0;
    if ( v90 )
    {
LABEL_223:
      v29 = 4;
      goto LABEL_40;
    }
    DirtyBitplane = (*((_DWORD *)DeviceExtension + 1398) >> 2) & 1;
LABEL_222:
    *(_DWORD *)&MasterIrp->Type = DirtyBitplane;
    goto LABEL_223;
  }
  v82 = v81 - 4;
  if ( !v82 )
  {
    if ( Options < 8 || !MasterIrp )
    {
      MitigatedRangeCount = -1073741789;
      WdLogSingleEntry1(2, -1073741789);
      WdLogGlobalForLineNumber = 4992;
      goto LABEL_269;
    }
    CInterfaceCallContext::CInterfaceCallContext((CInterfaceCallContext *)v97, a1, a2, 1u, 0, 0);
    MitigatedRangeCount = v99;
    if ( v99 >= 0 )
    {
      DpiFdoGetVirtualGpuType(a2, v88);
      v47 = DxgkZeroVirtualGpuAllocations(*((void **)DeviceExtension + 504));
      goto LABEL_97;
    }
    goto LABEL_268;
  }
  v83 = v82 - 936;
  if ( v83 )
  {
    v84 = v83 - 4;
    if ( v84 )
    {
      v85 = v84 - 20;
      if ( v85 )
      {
        if ( v85 != 91048 )
          goto LABEL_240;
        LODWORD(v100) = 0;
        v36 = DpiIndirectDdiIoControl(
                (__int64)DeviceExtension,
                Options,
                (__int64)MasterIrp,
                v96,
                (__int64)MasterIrp,
                (__int64)&v100);
      }
      else
      {
        v36 = DpiFlexIovMitigationUpdate(a1, a2, (__int64)MasterIrp, v96);
      }
    }
    else
    {
      v36 = DpiSetPartitionFlexIovVmbus(a1, a2, a2->AssociatedIrp.MasterIrp, Options);
    }
    goto LABEL_70;
  }
  if ( a2->RequestorMode && !DxgkpCheckProcessForVirtualMachineManagementAccess() )
  {
    MitigatedRangeCount = -1073741790;
    WdLogSingleEntry1(2, -1073741790);
    WdLogGlobalForLineNumber = 4445;
    goto LABEL_274;
  }
  DpiFdoGetVirtualGpuType(a2, v12);
  VirtualizationFlags = DpiGetVirtualizationFlags(a1, (__int64)MasterIrp, v96, (__int64)&v100);
  v29 = v100;
  MitigatedRangeCount = VirtualizationFlags;
LABEL_270:
  if ( MitigatedRangeCount != 259 )
    goto LABEL_275;
  return MitigatedRangeCount;
}

```

## disassembly

```asm
0x14040f640  mov     [rsp-8+arg_10], rbx
0x14040f645  push    rbp
0x14040f646  push    rsi
0x14040f647  push    rdi
0x14040f648  push    r12
0x14040f64a  push    r13
0x14040f64c  push    r14
0x14040f64e  push    r15
0x14040f650  lea     rbp, [rsp-0A00h]
0x14040f658  sub     rsp, 0B00h
0x14040f65f  mov     rax, cs:__security_cookie
0x14040f666  xor     rax, rsp
0x14040f669  mov     [rbp+0A30h+var_40], rax
0x14040f670  mov     r14, [rcx+40h]
0x14040f674  xor     eax, eax
0x14040f676  mov     r12, [rdx+0B8h]
0x14040f67d  mov     rsi, rdx
0x14040f680  mov     r15, rcx
0x14040f683  mov     [rsp+0B30h+var_AF0], rax
0x14040f688  mov     [rbp+0A30h+var_AB0], rax
0x14040f68c  lea     r13d, [rax+1]
0x14040f690  mov     ebx, [r12+18h]
0x14040f695  cmp     [r14+486h], al
0x14040f69c  jz      short loc_14040F6D8
0x14040f69e  cmp     [r14+487h], al
0x14040f6a5  jz      short loc_14040F6AF
0x14040f6a7  cmp     ebx, 23CC04h
0x14040f6ad  jz      short loc_14040F6D8
0x14040f6af  mov     rdx, 0FFFFFFFFC00000BBh
0x14040f6b6  mov     ebx, edx
0x14040f6b8  mov     ecx, 2
0x14040f6bd  call    cs:__imp_WdLogSingleEntry1
0x14040f6c4  nop     dword ptr [rax+rax+00h]
0x14040f6c9  mov     cs:WdLogGlobalForLineNumber, 0F24h
0x14040f6d3  jmp     loc_140410FF9
0x14040f6d8  mov     eax, [r12+8]
0x14040f6dd  mov     r12d, [r12+10h]
0x14040f6e2  mov     dword ptr [rsp+0B30h+var_AE8], eax
0x14040f6e6  call    Feature_Servicing_MSRC106447__private_IsEnabledDeviceUsageNoInline
0x14040f6eb  xor     edx, edx
0x14040f6ed  test    eax, eax
0x14040f6ef  jz      short loc_14040F748
0x14040f6f1  lea     eax, [rbx-226444h]
0x14040f6f7  cmp     eax, 58h ; 'X'
0x14040f6fa  ja      short loc_14040F748
0x14040f6fc  mov     rcx, rsi
0x14040f6ff  call    DpiFdoGetVirtualGpuType
0x14040f704  xor     edx, edx
0x14040f706  test    eax, eax
0x14040f708  jnz     short loc_14040F716
0x14040f70a  mov     rax, [r15+40h]
0x14040f70e  cmp     [rax+1418h], dl
0x14040f714  jmp     short loc_14040F71D
0x14040f716  cmp     [r14+0B58h], rdx
0x14040f71d  jnz     short loc_14040F748
0x14040f71f  mov     rdx, 0FFFFFFFFC00000BBh
0x14040f726  mov     ebx, edx
0x14040f728  mov     ecx, 2
0x14040f72d  call    cs:__imp_WdLogSingleEntry1
0x14040f734  nop     dword ptr [rax+rax+00h]
0x14040f739  mov     cs:WdLogGlobalForLineNumber, 0F44h
0x14040f743  jmp     loc_140410FF9
0x14040f748  mov     rdi, [rsi+18h]
0x14040f74c  mov     eax, 22646Ch
0x14040f751  cmp     ebx, eax
0x14040f753  ja      loc_1404105ED
0x14040f759  jz      loc_140410528
0x14040f75f  mov     eax, 226448h
0x14040f764  cmp     ebx, eax
0x14040f766  ja      loc_14040FDCB
0x14040f76c  jz      loc_14040FC59
0x14040f772  sub     ebx, 226044h
0x14040f778  jz      loc_14040FC44
0x14040f77e  sub     ebx, 4
0x14040f781  jz      loc_14040FBF2
0x14040f787  sub     ebx, 4
0x14040f78a  jz      loc_14040FBE5
0x14040f790  sub     ebx, 4
0x14040f793  jz      loc_14040FB94
0x14040f799  sub     ebx, 4
0x14040f79c  jz      loc_14040FB88
0x14040f7a2  sub     ebx, 4
0x14040f7a5  jz      loc_14040FA98
0x14040f7ab  sub     ebx, 4
0x14040f7ae  jz      loc_14040F9A7
0x14040f7b4  cmp     ebx, 3E8h
0x14040f7ba  jnz     loc_140410D12
0x14040f7c0  mov     [rsp+0B30h+var_B08], dl; char
0x14040f7c4  lea     rcx, [rsp+0B30h+var_AE0]; this
0x14040f7c9  mov     [rsp+0B30h+var_B10], dl; char
0x14040f7cd  mov     r9b, r13b; unsigned __int8
0x14040f7d0  mov     rdx, r15; void *
0x14040f7d3  mov     r8, rsi; struct _IRP *
0x14040f7d6  call    ??0CInterfaceCallContext@@QEAA@PEAXPEAU_IRP@@EEE@Z; CInterfaceCallContext::CInterfaceCallContext(void *,_IRP *,uchar,uchar,uchar)
0x14040f7db  mov     ebx, [rsp+0B30h+var_AC0]
0x14040f7df  test    ebx, ebx
0x14040f7e1  js      loc_14040F920
0x14040f7e7  xor     eax, eax
0x14040f7e9  xorps   xmm0, xmm0
0x14040f7ec  mov     [rbp+0A30h+var_A98], rax
0x14040f7f0  movups  [rbp+0A30h+var_AA8], xmm0
0x14040f7f4  test    rdi, rdi
0x14040f7f7  jz      loc_14040F97B
0x14040f7fd  mov     ebx, dword ptr [rsp+0B30h+var_AE8]
0x14040f801  cmp     ebx, 18h
0x14040f804  jb      loc_14040F97B
0x14040f80a  mov     rcx, rsi
0x14040f80d  call    DpiFdoGetVirtualGpuType
0x14040f812  lea     rcx, [rdi+14h]
0x14040f816  mov     dword ptr [rsp+0B30h+var_AE8], eax
0x14040f81a  mov     qword ptr [rbp+0A30h+var_AA8+8], rcx
0x14040f81e  lea     r12d, [rbx-14h]
0x14040f822  mov     rcx, [r14+0FC0h]; void *
0x14040f829  lea     r8, [rbp+0A30h+var_AA8]
0x14040f82d  shr     r12d, 1
0x14040f830  mov     edx, eax
0x14040f832  mov     dword ptr [rbp+0A30h+var_AA8], r12d
0x14040f836  call    DxgkDdiGetGpuPartitionInfo
0x14040f83b  mov     ebx, eax
0x14040f83d  test    eax, eax
0x14040f83f  js      loc_14040F8EB
0x14040f845  cmp     cs:?g_LimitNumberOfVfs@@3HA, 0; int g_LimitNumberOfVfs
0x14040f84c  mov     eax, dword ptr [rbp+0A30h+var_AA8]
0x14040f84f  jz      short loc_14040F86A
0x14040f851  cmp     eax, r13d
0x14040f854  jb      short loc_14040F86A
0x14040f856  mov     rcx, qword ptr [rbp+0A30h+var_AA8+8]
0x14040f85a  mov     dword ptr [rbp+0A30h+var_AA8], r13d
0x14040f85e  mov     [rcx], r13w
0x14040f862  mov     eax, dword ptr [rbp+0A30h+var_AA8]
0x14040f865  mov     word ptr [rbp+0A30h+var_A98], r13w
0x14040f86a  cmp     eax, r12d
0x14040f86d  ja      short loc_14040F8B7
0x14040f86f  test    eax, eax
0x14040f871  jz      short loc_14040F8B7
0x14040f873  mov     [rdi], eax
0x14040f875  mov     rcx, r15
0x14040f878  movzx   eax, word ptr [rbp+0A30h+var_A98]
0x14040f87c  mov     [rdi+0Ch], ax
0x14040f880  call    DpiFdoIsPostDevice
0x14040f885  mov     edx, dword ptr [rsp+0B30h+var_AE8]
0x14040f889  lea     r8, [rdi+4]
0x14040f88d  xor     ecx, ecx
0x14040f88f  test    al, al
0x14040f891  mov     eax, [rdi+10h]
0x14040f894  setnz   cl
0x14040f897  and     eax, 0FFFFFFFEh
0x14040f89a  or      ecx, eax
0x14040f89c  mov     [rdi+10h], ecx
0x14040f89f  mov     rcx, [r14+0FC0h]; void *
0x14040f8a6  call    DxgkDdiQueryPhysicalFunctionLuid
0x14040f8ab  mov     eax, dword ptr [rbp+0A30h+var_AA8]
0x14040f8ae  lea     edi, ds:14h[rax*2]
0x14040f8b5  jmp     short loc_14040F925
0x14040f8b7  mov     edx, 226444h
0x14040f8bc  mov     ecx, 3
0x14040f8c1  call    cs:__imp_WdLogSingleEntry1
0x14040f8c8  nop     dword ptr [rax+rax+00h]
0x14040f8cd  mov     cs:WdLogGlobalForLineNumber, 0F79h
0x14040f8d7  mov     ebx, 0C000000Dh
0x14040f8dc  lea     rcx, [rsp+0B30h+var_AE0]; this
0x14040f8e1  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x14040f8e6  jmp     loc_140410FF9
0x14040f8eb  mov     rdx, 0FFFFFFFFC0000023h
0x14040f8f2  cmp     eax, edx
0x14040f8f4  jnz     short loc_14040F920
0x14040f8f6  mov     eax, dword ptr [rbp+0A30h+var_AA8]
0x14040f8f9  test    eax, eax
0x14040f8fb  jnz     short loc_14040F934
0x14040f8fd  mov     edx, 226444h
0x14040f902  lea     ecx, [rax+3]
0x14040f905  call    cs:__imp_WdLogSingleEntry1
0x14040f90c  nop     dword ptr [rax+rax+00h]
0x14040f911  mov     cs:WdLogGlobalForLineNumber, 0F91h
0x14040f91b  mov     ebx, 0C000000Dh
0x14040f920  mov     rdi, [rsp+0B30h+var_AF0]
0x14040f925  lea     rcx, [rsp+0B30h+var_AE0]; this
0x14040f92a  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x14040f92f  jmp     loc_140410FA5
0x14040f934  mov     [rdi], eax
0x14040f936  mov     rcx, r15
0x14040f939  movzx   eax, word ptr [rbp+0A30h+var_A98]
0x14040f93d  mov     ebx, 80000005h
0x14040f942  mov     [rdi+0Ch], ax
0x14040f946  call    DpiFdoIsPostDevice
0x14040f94b  xor     ecx, ecx
0x14040f94d  lea     rdx, [r14+0A88h]; SourceLuid
0x14040f954  test    al, al
0x14040f956  mov     eax, [rdi+10h]
0x14040f959  setnz   cl
0x14040f95c  and     eax, 0FFFFFFFEh
0x14040f95f  or      ecx, eax
0x14040f961  mov     [rdi+10h], ecx
0x14040f964  lea     rcx, [rdi+4]; DestinationLuid
0x14040f968  call    cs:__imp_RtlCopyLuid
0x14040f96f  nop     dword ptr [rax+rax+00h]
0x14040f974  mov     edi, 18h
0x14040f979  jmp     short loc_14040F925
0x14040f97b  mov     edx, 226444h
0x14040f980  mov     ecx, 3
0x14040f985  call    cs:__imp_WdLogSingleEntry1
0x14040f98c  nop     dword ptr [rax+rax+00h]
0x14040f991  mov     cs:WdLogGlobalForLineNumber, 0F60h
0x14040f99b  mov     rbx, 0FFFFFFFFC0000023h
0x14040f9a2  jmp     loc_14040F8DC
0x14040f9a7  cmp     [rsi+40h], dl
0x14040f9aa  jz      short loc_14040F9E1
0x14040f9ac  call    DxgkpCheckProcessForVirtualMachineManagementAccess
0x14040f9b1  xor     edx, edx
0x14040f9b3  test    al, al
0x14040f9b5  jnz     short loc_14040F9E1
0x14040f9b7  mov     rbx, 0FFFFFFFFC0000022h
0x14040f9be  mov     ecx, 2
0x14040f9c3  mov     rdx, rbx
0x14040f9c6  call    cs:__imp_WdLogSingleEntry1
0x14040f9cd  nop     dword ptr [rax+rax+00h]
0x14040f9d2  mov     cs:WdLogGlobalForLineNumber, 1103h
0x14040f9dc  jmp     loc_140410FF9
0x14040f9e1  cmp     r12d, 4
0x14040f9e5  jb      loc_14040FA6F
0x14040f9eb  test    rdi, rdi
0x14040f9ee  jz      short loc_14040FA6F
0x14040f9f0  mov     r12d, dword ptr [rsp+0B30h+var_AE8]
0x14040f9f5  cmp     r12d, 10h
0x14040f9f9  jb      short loc_14040FA6F
0x14040f9fb  mov     [rsp+0B30h+var_B08], dl; char
0x14040f9ff  lea     rcx, [rsp+0B30h+var_AE0]; this
0x14040fa04  mov     [rsp+0B30h+var_B10], dl; char
0x14040fa08  mov     r9b, r13b; unsigned __int8
0x14040fa0b  mov     rdx, r15; void *
0x14040fa0e  mov     r8, rsi; struct _IRP *
0x14040fa11  call    ??0CInterfaceCallContext@@QEAA@PEAXPEAU_IRP@@EEE@Z; CInterfaceCallContext::CInterfaceCallContext(void *,_IRP *,uchar,uchar,uchar)
0x14040fa16  mov     ebx, [rsp+0B30h+var_AC0]
0x14040fa1a  test    ebx, ebx
0x14040fa1c  js      loc_14040F920
0x14040fa22  mov     rcx, rsi
0x14040fa25  call    DpiFdoGetVirtualGpuType
0x14040fa2a  movzx   edx, word ptr [rdi]
0x14040fa2d  lea     r8, [rbp+0A30h+var_AA8]
0x14040fa31  mov     rcx, [r14+0FC0h]; void *
0x14040fa38  mov     dword ptr [rbp+0A30h+var_AA8], edx
0x14040fa3b  movzx   edx, byte ptr [rdi+2]
0x14040fa3f  mov     dword ptr [rbp+0A30h+var_AA8+4], edx
0x14040fa42  mov     edx, r12d
0x14040fa45  shr     edx, 4
0x14040fa48  mov     dword ptr [rbp+0A30h+var_AA8+8], edx
0x14040fa4b  mov     edx, eax
0x14040fa4d  mov     dword ptr [rbp+0A30h+var_AA8+0Ch], 0
0x14040fa54  mov     [rbp+0A30h+var_A98], rdi
0x14040fa58  call    DxgkDdiQueryMitigatedRanges
0x14040fa5d  mov     edi, r12d
0x14040fa60  mov     ebx, eax
0x14040fa62  test    eax, eax
0x14040fa64  jns     loc_14040F925
0x14040fa6a  jmp     loc_14040F920
0x14040fa6f  mov     rdx, 0FFFFFFFFC0000023h
0x14040fa76  mov     ebx, edx
0x14040fa78  mov     ecx, 2
0x14040fa7d  call    cs:__imp_WdLogSingleEntry1
0x14040fa84  nop     dword ptr [rax+rax+00h]
0x14040fa89  mov     cs:WdLogGlobalForLineNumber, 110Eh
0x14040fa93  jmp     loc_140410FA0
0x14040fa98  cmp     [rsi+40h], dl
0x14040fa9b  jz      short loc_14040FAD2
0x14040fa9d  call    DxgkpCheckProcessForVirtualMachineManagementAccess
0x14040faa2  xor     edx, edx
0x14040faa4  test    al, al
0x14040faa6  jnz     short loc_14040FAD2
0x14040faa8  mov     rbx, 0FFFFFFFFC0000022h
0x14040faaf  mov     ecx, 2
0x14040fab4  mov     rdx, rbx
0x14040fab7  call    cs:__imp_WdLogSingleEntry1
0x14040fabe  nop     dword ptr [rax+rax+00h]
0x14040fac3  mov     cs:WdLogGlobalForLineNumber, 10D9h
0x14040facd  jmp     loc_140410FF9
0x14040fad2  cmp     r12d, 2
0x14040fad6  jb      loc_14040FB5F
0x14040fadc  test    rdi, rdi
0x14040fadf  jz      short loc_14040FB5F
0x14040fae1  cmp     dword ptr [rsp+0B30h+var_AE8], 18h
0x14040fae6  jb      short loc_14040FB5F
0x14040fae8  mov     [rsp+0B30h+var_B08], dl; char
0x14040faec  lea     rcx, [rsp+0B30h+var_AE0]; this
0x14040faf1  mov     [rsp+0B30h+var_B10], dl; char
0x14040faf5  mov     r9b, r13b; unsigned __int8
0x14040faf8  mov     rdx, r15; void *
0x14040fafb  mov     r8, rsi; struct _IRP *
0x14040fafe  call    ??0CInterfaceCallContext@@QEAA@PEAXPEAU_IRP@@EEE@Z; CInterfaceCallContext::CInterfaceCallContext(void *,_IRP *,uchar,uchar,uchar)
0x14040fb03  mov     ebx, [rsp+0B30h+var_AC0]
0x14040fb07  test    ebx, ebx
0x14040fb09  js      loc_14040F920
0x14040fb0f  mov     rcx, rsi
0x14040fb12  call    DpiFdoGetVirtualGpuType
0x14040fb17  movzx   ecx, word ptr [rdi]
0x14040fb1a  lea     r8, [rbp+0A30h+var_AA8]
0x14040fb1e  mov     dword ptr [rbp+0A30h+var_AA8], ecx
0x14040fb21  xorps   xmm0, xmm0
0x14040fb24  mov     rcx, [r14+0FC0h]; void *
0x14040fb2b  mov     edx, eax
0x14040fb2d  movdqu  [rbp+0A30h+var_AA8+4], xmm0
  ... truncated ...
```
