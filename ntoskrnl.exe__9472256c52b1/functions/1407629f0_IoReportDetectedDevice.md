# IoReportDetectedDevice

- ea: `0x1407629f0`
- end: `0x140763479`
- name: `IoReportDetectedDevice`
- size: `2697`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, INTERFACE_TYPE LegacyBusType, ULONG BusNumber, ULONG SlotNumber, PCM_RESOURCE_LIST ResourceList, PIO_RESOURCE_REQUIREMENTS_LIST ResourceRequirements, BOOLEAN ResourceAssigned, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `56`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140748700`

## callees

- `0x1402146f0`
- `0x140214b10`
- `0x140215ea0`
- `0x140216480`
- `0x140216db0`
- `0x14036f270`
- `0x140388690`
- `0x1403ce2d0`
- `0x140403380`
- `0x14041e400`
- `0x14045119c`
- `0x1404519bc`
- `0x140452ca8`
- `0x140452d0c`
- `0x1404b3438`
- `0x1404c4c74`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406ddfe0`
- `0x1406def60`
- `0x1406f6f80`
- `0x1407629f0`
- `0x140763820`
- `0x1407638b0`
- `0x14076393c`
- `0x140766b48`
- `0x140768a00`
- `0x140769cd4`
- `0x14076a364`
- `0x140772078`
- `0x14077692c`
- `0x14086a27c`
- `0x14086c1e0`
- `0x1408c43e0`
- `0x1408eef70`
- `0x1408f20d0`
- `0x1408fd47c`
- `0x1408fd630`
- `0x140908720`
- `0x140909110`
- `0x14090dd7c`
- `0x14090def4`
- `0x140916af4`
- `0x140919564`
- `0x14091bfe0`
- `0x14091c03c`
- `0x1409e5ea0`
- `0x140a32458`
- `0x140a3b714`
- `0x140a47be8`

## string_xrefs

- `0x14076327b`: `BootConfig`
- `0x1407632cb`: `BasicConfigVector`

## pseudocode

```c
NTSTATUS __stdcall IoReportDetectedDevice(
        PDRIVER_OBJECT DriverObject,
        INTERFACE_TYPE LegacyBusType,
        ULONG BusNumber,
        ULONG SlotNumber,
        PCM_RESOURCE_LIST ResourceList,
        PIO_RESOURCE_REQUIREMENTS_LIST ResourceRequirements,
        BOOLEAN ResourceAssigned,
        PDEVICE_OBJECT *DeviceObject)
{
  UNICODE_STRING *p_ServiceKeyName; // r12
  char *DeviceNode; // rdi
  PDEVICE_OBJECT v11; // rax
  int v12; // r14d
  PDEVICE_OBJECT v13; // r13
  NTSTATUS result; // eax
  wchar_t *Buffer; // rcx
  wchar_t *i; // rax
  const UNICODE_STRING *v17; // rcx
  NTSTATUS appended; // ebx
  int v19; // eax
  unsigned __int16 Length; // cx
  size_t v21; // r14
  signed __int64 v22; // rcx
  __int16 v23; // cx
  struct _DEVICE_OBJECT *v24; // rax
  struct _DEVICE_OBJECT *v25; // r14
  PDEVICE_OBJECT v26; // rcx
  int v27; // eax
  __int64 Pool2; // rax
  __int64 v29; // r9
  __int64 v30; // r8
  __int64 v31; // rdx
  char *v32; // rcx
  NTSTATUS DeviceInstancePath; // eax
  int v34; // eax
  STRSAFE_PCNZWCH v35; // r13
  __int64 v36; // rdx
  PDRIVER_OBJECT v37; // rbx
  bool v38; // zf
  unsigned __int16 *p_Length; // rbx
  int LegacyDeviceIds; // eax
  char v41; // r12
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  unsigned int v45; // eax
  int v46; // ecx
  _DWORD *v47; // r14
  HANDLE v48; // rbx
  ULONG v49; // eax
  HANDLE v50; // rbx
  unsigned int v51; // eax
  unsigned int v52; // ebx
  void *v53; // rax
  void *v54; // rsi
  __int64 v55; // r8
  int v56; // edx
  __int64 v57; // r9
  int *dwFlags; // [rsp+20h] [rbp-E0h]
  NTSTRSAFE_PCWSTR pszFormat; // [rsp+28h] [rbp-D8h]
  __int64 v60; // [rsp+30h] [rbp-D0h]
  int v61; // [rsp+38h] [rbp-C8h]
  int v62; // [rsp+40h] [rbp-C0h]
  char v63; // [rsp+50h] [rbp-B0h] BYREF
  char v64; // [rsp+51h] [rbp-AFh] BYREF
  char v65[2]; // [rsp+52h] [rbp-AEh] BYREF
  _DWORD cbMax[3]; // [rsp+54h] [rbp-ACh] BYREF
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING Destination; // [rsp+68h] [rbp-98h] BYREF
  ULONG v69; // [rsp+78h] [rbp-88h]
  char *v70; // [rsp+80h] [rbp-80h] BYREF
  int v71; // [rsp+88h] [rbp-78h] BYREF
  HANDLE KeyHandle; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v73; // [rsp+98h] [rbp-68h] BYREF
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+A0h] [rbp-60h] BYREF
  PDEVICE_OBJECT v75; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  PDRIVER_OBJECT v77; // [rsp+C0h] [rbp-40h]
  STRSAFE_PCNZWCH psz; // [rsp+C8h] [rbp-38h] BYREF
  size_t pcbLength; // [rsp+D0h] [rbp-30h] BYREF
  PVOID P; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v81; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v82; // [rsp+F0h] [rbp-10h] BYREF
  PDEVICE_OBJECT *v83; // [rsp+100h] [rbp+0h]
  _WORD v84[200]; // [rsp+110h] [rbp+10h] BYREF

  p_ServiceKeyName = &DriverObject->DriverExtension->ServiceKeyName;
  *(_QWORD *)&DestinationString.Length = ResourceRequirements;
  LODWORD(ppszDestEnd) = SlotNumber;
  Destination.Buffer = v84;
  DeviceNode = 0;
  v11 = *DeviceObject;
  v12 = 0;
  v69 = BusNumber;
  v13 = 0;
  v77 = DriverObject;
  v83 = DeviceObject;
  v64 = 0;
  *(_QWORD *)&Destination.Length = 26214400;
  psz = 0;
  memset(cbMax, 0, sizeof(cbMax));
  pcbLength = 0;
  v71 = 0;
  v73 = 0;
  v63 = 0;
  v70 = 0;
  v67 = 0;
  KeyHandle = 0;
  v75 = 0;
  P = 0;
  v81 = 0;
  v82 = 0;
  if ( v11 )
  {
    DeviceNode = (char *)v11->DeviceObjectExtension->DeviceNode;
    v70 = DeviceNode;
    if ( !DeviceNode )
      return -1073741578;
LABEL_13:
    appended = PiPnpRtlBeginOperation(&P);
    if ( appended >= 0 )
    {
      PpDevNodeLockTree(1);
      if ( !DeviceNode && (v77->Flags & 4) == 0 )
      {
        v19 = IopDuplicateDetection((unsigned int)LegacyBusType, v69, (unsigned int)ppszDestEnd, &v70);
        DeviceNode = v70;
        appended = v19;
        if ( v19 >= 0 )
        {
          if ( v70 )
            v12 = 1;
          v67 = v12;
        }
      }
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&PnpRegistryDeviceResource, 1u);
      if ( DeviceNode )
        goto LABEL_90;
      appended = RtlAppendUnicodeToString(&Destination, L"\\");
      if ( appended >= 0 )
      {
        Length = Destination.Length;
        v69 = Destination.Length;
        v21 = (400 - (unsigned __int64)Destination.Length) >> 1;
        while ( 1 )
        {
          Destination.Length = Length;
          LODWORD(v60) = (_DWORD)v13;
          ppszDestEnd = &v84[(unsigned __int64)Length >> 1];
          RtlStringCchPrintfExW(ppszDestEnd, v21, &ppszDestEnd, 0, 0, L"%04u", v60);
          v22 = &ppszDestEnd[-((unsigned __int64)Destination.Length >> 1)] - v84;
          if ( (_DWORD)v22 == -1 )
            v23 = 400 - Destination.Length;
          else
            v23 = 2 * v22;
          Destination.Length += v23;
          appended = CmCreateDevice(
                       *(__int64 *)&PiPnpRtlCtx,
                       (__int64)Destination.Buffer,
                       983103,
                       (HANDLE *)&cbMax[1],
                       &v63,
                       0);
          if ( appended < 0 )
            goto LABEL_32;
          if ( v63 )
          {
            v13 = v75;
            goto LABEL_52;
          }
          dwFlags = &v67;
          v67 = 0;
          if ( (unsigned __int8)IopIsReportedAlready(&Destination, *(_QWORD *)&cbMax[1], p_ServiceKeyName, ResourceList) )
            break;
          ZwClose(*(HANDLE *)&cbMax[1]);
          Length = v69;
          LODWORD(v13) = (_DWORD)v13 + 1;
        }
        v24 = (struct _DEVICE_OBJECT *)PnpDeviceObjectFromDeviceInstanceWithTag(&Destination, 1953261124);
        v75 = v24;
        v13 = v24;
        if ( !v24 )
        {
          appended = -1073741823;
          DeviceNode = 0;
          goto LABEL_32;
        }
        DeviceNode = (char *)v24->DeviceObjectExtension->DeviceNode;
        v70 = DeviceNode;
LABEL_52:
        if ( !DeviceNode )
        {
          appended = IopCreateRootEnumeratedDeviceObject(&v75);
          if ( appended < 0 )
            goto LABEL_32;
          v25 = v75;
          v26 = v75;
          v75->Flags |= 0x1000u;
          v27 = PipAllocateDeviceNode(v26, &v70);
          DeviceNode = v70;
          if ( v27 == -1073740946 || !v70 )
          {
            IoDeleteDevice(v25);
            appended = -1073741670;
            goto LABEL_32;
          }
          if ( (v77->Flags & 4) == 0 )
          {
            Pool2 = ExAllocatePool2(256, p_ServiceKeyName->Length, 1215327824);
            *((_QWORD *)DeviceNode + 8) = Pool2;
            if ( !Pool2 )
              goto LABEL_58;
            *((_WORD *)DeviceNode + 29) = p_ServiceKeyName->Length;
            DeviceInstancePath = RtlUpcaseUnicodeString((PUNICODE_STRING)(DeviceNode + 56), p_ServiceKeyName, 0);
            appended = DeviceInstancePath;
            if ( DeviceInstancePath < 0 )
              goto LABEL_63;
          }
          DeviceInstancePath = PnpAllocateDeviceInstancePath(DeviceNode, (unsigned int)Destination.Length + 2);
          appended = DeviceInstancePath;
          if ( DeviceInstancePath < 0 )
            goto LABEL_63;
          DeviceInstancePath = RtlUpcaseUnicodeString((PUNICODE_STRING)(DeviceNode + 40), &Destination, 0);
          appended = DeviceInstancePath;
          if ( DeviceInstancePath < 0 )
            goto LABEL_63;
          *(_WORD *)(*((_QWORD *)DeviceNode + 6) + 2 * ((unsigned __int64)*((unsigned __int16 *)DeviceNode + 20) >> 1)) = 0;
          v71 = 32;
          v34 = CmSetDeviceRegProp(
                  *(__int64 *)&PiPnpRtlCtx,
                  *((_QWORD *)DeviceNode + 6),
                  *(__int64 *)&cbMax[1],
                  0xBu,
                  4,
                  (__int64)&v71,
                  4,
                  0);
          appended = v34;
          if ( v34 < 0 )
            goto LABEL_67;
          v64 = -1;
          v34 = PnpSetObjectProperty(
                  *(__int64 *)&PiPnpRtlCtx,
                  *((_QWORD *)DeviceNode + 6),
                  1u,
                  *(__int64 *)&cbMax[1],
                  0,
                  (__int64)&DEVPKEY_Device_Reported,
                  17,
                  (__int64)&v64,
                  1u,
                  0);
          appended = v34;
          if ( v34 < 0 )
            goto LABEL_67;
          v34 = PnpUnicodeStringToWstr(&psz, cbMax, &p_ServiceKeyName->Length);
          appended = v34;
          if ( v34 < 0 )
            goto LABEL_67;
          v35 = psz;
          appended = RtlStringCbLengthW(psz, cbMax[0], &pcbLength);
          if ( appended < 0 )
          {
            PnpUnicodeStringToWstrFree(v35, p_ServiceKeyName);
LABEL_73:
            v30 = (unsigned int)appended;
            goto LABEL_68;
          }
          appended = CmSetDeviceRegProp(
                       *(__int64 *)&PiPnpRtlCtx,
                       *((_QWORD *)DeviceNode + 6),
                       *(__int64 *)&cbMax[1],
                       5u,
                       1,
                       (__int64)v35,
                       (int)pcbLength + 2,
                       0);
          PnpUnicodeStringToWstrFree(v35, p_ServiceKeyName);
          if ( appended < 0 )
            goto LABEL_73;
          v73 = 0;
          v34 = CmOpenDeviceRegKey(
                  *(__int64 *)&PiPnpRtlCtx,
                  *((_QWORD *)DeviceNode + 6),
                  19,
                  0,
                  983103,
                  1,
                  (__int64)&v73,
                  0);
          appended = v34;
          if ( v34 < 0 )
            goto LABEL_67;
          v34 = PnpSetRegistryDword(v73);
          appended = v34;
          if ( v34 < 0 )
            goto LABEL_67;
          v37 = v77;
          if ( (v77->Flags & 4) == 0 )
          {
            LOBYTE(v29) = 1;
            LOBYTE(v36) = 1;
            PpDeviceRegistration(&Destination, v36, 0, v29);
          }
          Destination.Buffer = 0;
          v38 = (v37->Flags & 4) == 0;
          p_Length = (unsigned __int16 *)&v81;
          *(_DWORD *)&Destination.Length = 0;
          if ( v38 )
            p_Length = &p_ServiceKeyName->Length;
          cbMax[0] = 400;
          if ( (int)IopGetOriginalServiceName(p_Length, v84, cbMax) >= 0 && cbMax[0] > 2u )
          {
            WORD1(v82) = 400;
            *((_QWORD *)&v82 + 1) = v84;
            LOWORD(v82) = LOWORD(cbMax[0]) - 2;
            p_Length = (unsigned __int16 *)&v82;
          }
          LegacyDeviceIds = IopCreateLegacyDeviceIds((__int64)v25, p_Length, (__int64)ResourceList);
          appended = LegacyDeviceIds;
          v32 = DeviceNode;
          if ( LegacyDeviceIds < 0 )
          {
            v30 = (unsigned int)LegacyDeviceIds;
            v31 = 19;
            goto LABEL_61;
          }
          PipSetDevNodeFlags(DeviceNode, 17);
          *((_DWORD *)DeviceNode + 165) = *((_DWORD *)IopRootDeviceNode + 165);
          PipSetDevNodeState(DeviceNode, 772);
          PpDevNodeInsertIntoTree(IopRootDeviceNode, DeviceNode);
          DeviceInstancePath = PnpMapDeviceObjectToDeviceInstance(v25, DeviceNode + 40);
          appended = DeviceInstancePath;
          if ( DeviceInstancePath < 0 )
          {
LABEL_63:
            v30 = (unsigned int)DeviceInstancePath;
            goto LABEL_59;
          }
          v41 = 1;
          PsReferenceSiloContext(v25);
LABEL_99:
          v47 = *(_DWORD **)&DestinationString.Length;
          if ( !ResourceList && !*(_QWORD *)&DestinationString.Length )
            goto LABEL_106;
          v34 = CmOpenDeviceRegKey(
                  *(__int64 *)&PiPnpRtlCtx,
                  *((_QWORD *)DeviceNode + 6),
                  20,
                  0,
                  983103,
                  1,
                  (__int64)&KeyHandle,
                  0);
          appended = v34;
          if ( v34 >= 0 )
          {
            if ( !ResourceList
              || (v48 = KeyHandle,
                  DestinationString = 0,
                  RtlInitUnicodeString(&DestinationString, L"BootConfig"),
                  v49 = PnpDetermineResourceListSize(ResourceList),
                  v34 = ZwSetValueKey(v48, &DestinationString, 0, 8u, ResourceList, v49),
                  appended = v34,
                  v34 >= 0) )
            {
              if ( !v47
                || (v50 = KeyHandle,
                    DestinationString = 0,
                    RtlInitUnicodeString(&DestinationString, L"BasicConfigVector"),
                    v34 = ZwSetValueKey(v50, &DestinationString, 0, 0xAu, v47, *v47),
                    appended = v34,
                    v34 >= 0) )
              {
LABEL_106:
                if ( ResourceAssigned )
                {
                  PipSetDevNodeFlags(DeviceNode, 256);
                  PnpSetRegistryDword(*(HANDLE *)&cbMax[1]);
                  v51 = PnpDetermineResourceListSize(ResourceList);
                  IopWriteAllocatedResourcesToRegistry(DeviceNode, ResourceList, v51);
                }
                else if ( ResourceList && ResourceList->Count && ResourceList->List[0].PartialResourceList.Count )
                {
                  v52 = PnpDetermineResourceListSize(ResourceList);
                  v53 = (void *)ExAllocatePool2(256, v52, 1198550608);
                  v54 = v53;
                  if ( !v53 )
                  {
LABEL_58:
                    v30 = 3221225626LL;
                    appended = -1073741670;
LABEL_59:
                    v31 = 3;
                    goto LABEL_60;
                  }
                  memmove(v53, ResourceList, v52);
                  pszFormat = (NTSTRSAFE_PCWSTR)*((_QWORD *)DeviceNode + 4);
                  v55 = *((_QWORD *)pszFormat + 1);
                  v65[0] = 0;
                  appended = IoReportResourceUsageInternal(
                               0,
                               v56,
                               v55,
                               0,
                               (_DWORD)dwFlags,
                               (__int64)pszFormat,
                               (__int64)v54,
                               v61,
                               v62,
                               (__int64)v65);
                  ExFreePoolWithTag(v54, 0x47706E50u);
                  if ( appended >= 0 && !v65[0] )
                  {
LABEL_120:
                    *((_DWORD *)DeviceNode + 165) = *(_DWORD *)(*((_QWORD *)DeviceNode + 2) + 660LL);
                    IopDoDeferredSetInterfaceState(DeviceNode);
                    PipSetDevNodeState(DeviceNode, 777);
                    if ( v41 )
                      PipSetDevNodeFlags(DeviceNode, 0x80000000LL);
                    *v83 = (PDEVICE_OBJECT)*((_QWORD *)DeviceNode + 4);
                    goto LABEL_40;
                  }
                  if ( !(unsigned int)PipIsDevNodeDNStarted(DeviceNode) )
                    PipSetDevNodeProblem(DeviceNode, 12, (unsigned int)appended, v57);
                  appended = -1073741800;
                }
                else
                {
                  PipSetDevNodeFlags(DeviceNode, 256);
                }
                if ( appended >= 0 )
                  goto LABEL_120;
                goto LABEL_32;
              }
            }
          }
LABEL_67:
          v30 = (unsigned int)v34;
LABEL_68:
          v31 = 19;
LABEL_60:
          v32 = DeviceNode;
LABEL_61:
          PipSetDevNodeProblem(v32, v31, v30, v29);
          goto LABEL_32;
        }
        v12 = v67;
LABEL_90:
        if ( v12 )
        {
          if ( (unsigned int)PipAreDriversLoaded(DeviceNode)
            || (*((_DWORD *)DeviceNode + 99) & 0x6000) != 0
            && ((v45 = *((_DWORD *)DeviceNode + 101), v45 > 0x1C) || (v46 = 268697602, !_bittest(&v46, v45))) )
          {
            ObfDereferenceObject(*((PVOID *)DeviceNode + 4));
            appended = -1073741810;
            goto LABEL_32;
          }
          if ( !v13 )
            PipClearDevNodeProblem(DeviceNode, v42, v43, v44);
        }
        v41 = 0;
        if ( !*(_QWORD *)&cbMax[1] )
        {
          appended = PnpDeviceObjectToDeviceInstance(*((_QWORD *)DeviceNode + 4), &cbMax[1], 983103);
          if ( appended < 0 )
          {
LABEL_32:
            if ( v63 )
            {
              if ( KeyHandle )
                ZwDeleteKey(KeyHandle);
              if ( v73 )
                ZwDeleteKey(v73);
              if ( *(_QWORD *)&cbMax[1] )
                ZwDeleteKey(*(HANDLE *)&cbMax[1]);
              PnpCleanupDeviceRegistryValues(DeviceNode + 40);
              PpDevNodeRemoveFromTree(DeviceNode);
              IoDeleteDevice(*((PDEVICE_OBJECT *)DeviceNode + 4));
              ObfDereferenceObject(*((PVOID *)DeviceNode + 4));
            }
            goto LABEL_40;
          }
        }
        goto LABEL_99;
      }
    }
LABEL_40:
    ExReleaseResourceLite(&PnpRegistryDeviceResource);
    KeLeaveCriticalRegion();
    PpDevNodeUnlockTree(1);
    if ( KeyHandle )
      ZwClose(KeyHandle);
    if ( v73 )
      ZwClose(v73);
    if ( *(_QWORD *)&cbMax[1] )
      ZwClose(*(HANDLE *)&cbMax[1]);
    if ( P )
      PiPnpRtlEndOperation(P);
    return appended;
  }
  if ( (DriverObject->Flags & 4) != 0 )
  {
    Buffer = p_ServiceKeyName->Buffer;
    for ( i = &Buffer[((unsigned __int64)p_ServiceKeyName->Length >> 1) - 1]; i != Buffer; --i )
    {
      if ( *i == 92 )
      {
        *((_QWORD *)&v81 + 1) = i + 1;
        v17 = (const UNICODE_STRING *)&v81;
        LOWORD(v81) = p_ServiceKeyName->Length
                    - 2 * ((__int64)(unsigned int)((_DWORD)i + 2 - LODWORD(p_ServiceKeyName->Buffer)) >> 1);
        WORD1(v81) = v81;
        goto LABEL_12;
      }
    }
    return -1073741585;
  }
  else
  {
    v17 = p_ServiceKeyName;
LABEL_12:
    result = IopGetRootDeviceId(v17, &Destination);
    if ( result >= 0 )
      goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x1407629f0  push    rbp
0x1407629f2  push    rbx
0x1407629f3  push    rsi
0x1407629f4  push    rdi
0x1407629f5  push    r12
0x1407629f7  push    r13
0x1407629f9  push    r14
0x1407629fb  push    r15
0x1407629fd  lea     rbp, [rsp-1B8h]
0x140762a05  sub     rsp, 2B8h
0x140762a0c  mov     rax, cs:__security_cookie
0x140762a13  xor     rax, rsp
0x140762a16  mov     [rbp+1F0h+var_50], rax
0x140762a1d  mov     rax, [rbp+1F0h+ResourceRequirements]
0x140762a24  xor     ebx, ebx
0x140762a26  mov     r12, [rcx+30h]
0x140762a2a  mov     esi, edx
0x140762a2c  mov     rdx, [rbp+1F0h+DeviceObject]
0x140762a33  add     r12, 18h
0x140762a37  mov     r15, [rbp+1F0h+ResourceList]
0x140762a3e  xorps   xmm0, xmm0
0x140762a41  mov     qword ptr [rbp+1F0h+DestinationString.Length], rax
0x140762a45  xorps   xmm1, xmm1
0x140762a48  lea     rax, [rbp+1F0h+var_1E0]
0x140762a4c  mov     dword ptr [rbp+1F0h+ppszDestEnd], r9d
0x140762a50  mov     [rsp+2F0h+Destination.Buffer], rax
0x140762a55  mov     edi, ebx
0x140762a57  mov     rax, [rdx]
0x140762a5a  mov     r14d, ebx
0x140762a5d  mov     [rsp+2F0h+var_278], r8d
0x140762a62  mov     r13d, ebx
0x140762a65  mov     [rbp+1F0h+var_230], rcx
0x140762a69  mov     [rbp+1F0h+var_1F0], rdx
0x140762a6d  mov     [rsp+2F0h+var_29F], bl
0x140762a71  mov     qword ptr [rsp+2F0h+Destination.Length], 1900000h
0x140762a7a  mov     [rbp+1F0h+psz], rbx
0x140762a7e  mov     dword ptr [rsp+2F0h+cbMax], ebx
0x140762a82  mov     [rbp+1F0h+pcbLength], rbx
0x140762a86  mov     [rbp+1F0h+var_268], ebx
0x140762a89  mov     [rbp+1F0h+var_258], rbx
0x140762a8d  mov     [rsp+2F0h+var_2A0], bl
0x140762a91  mov     [rbp+1F0h+var_270], rbx
0x140762a95  mov     [rsp+2F0h+var_290], ebx
0x140762a99  mov     qword ptr [rsp+2F0h+cbMax+4], rbx
0x140762a9e  mov     [rbp+1F0h+KeyHandle], rbx
0x140762aa2  mov     [rbp+1F0h+var_248], rbx
0x140762aa6  mov     [rbp+1F0h+P], rbx
0x140762aaa  movups  [rbp+1F0h+var_210], xmm0
0x140762aae  movups  [rbp+1F0h+var_200], xmm1
0x140762ab2  test    rax, rax
0x140762ab5  jz      short loc_140762AD9
0x140762ab7  mov     rax, [rax+138h]
0x140762abe  mov     rdi, [rax+28h]
0x140762ac2  mov     [rbp+1F0h+var_270], rdi
0x140762ac6  test    rdi, rdi
0x140762ac9  jnz     loc_140762B4F
0x140762acf  mov     eax, 0C00000F6h
0x140762ad4  jmp     loc_140762DCC
0x140762ad9  mov     eax, [rcx+10h]
0x140762adc  test    al, 4
0x140762ade  jz      short loc_140762B3A
0x140762ae0  movzx   eax, word ptr [r12]
0x140762ae5  mov     rcx, [r12+8]
0x140762aea  shr     rax, 1
0x140762aed  dec     rax
0x140762af0  lea     rax, [rcx+rax*2]
0x140762af4  cmp     rax, rcx
0x140762af7  jz      short loc_140762B30
0x140762af9  cmp     word ptr [rax], 5Ch ; '\'
0x140762afd  jz      short loc_140762B05
0x140762aff  sub     rax, 2
0x140762b03  jmp     short loc_140762AF4
0x140762b05  add     rax, 2
0x140762b09  mov     ecx, eax
0x140762b0b  mov     qword ptr [rbp+1F0h+var_210+8], rax
0x140762b0f  sub     ecx, [r12+8]
0x140762b14  movzx   eax, word ptr [r12]
0x140762b19  sar     rcx, 1
0x140762b1c  add     cx, cx
0x140762b1f  sub     ax, cx
0x140762b22  lea     rcx, [rbp+1F0h+var_210]
0x140762b26  mov     word ptr [rbp+1F0h+var_210], ax
0x140762b2a  mov     word ptr [rbp+1F0h+var_210+2], ax
0x140762b2e  jmp     short loc_140762B3D
0x140762b30  mov     eax, 0C00000EFh
0x140762b35  jmp     loc_140762DCC
0x140762b3a  mov     rcx, r12; Source
0x140762b3d  lea     rdx, [rsp+2F0h+Destination]; Destination
0x140762b42  call    IopGetRootDeviceId
0x140762b47  test    eax, eax
0x140762b49  js      loc_140762DCC
0x140762b4f  lea     rcx, [rbp+1F0h+P]
0x140762b53  call    PiPnpRtlBeginOperation
0x140762b58  mov     ebx, eax
0x140762b5a  test    eax, eax
0x140762b5c  js      loc_140762D76
0x140762b62  mov     ecx, 1
0x140762b67  call    PpDevNodeLockTree
0x140762b6c  test    rdi, rdi
0x140762b6f  jnz     short loc_140762BAC
0x140762b71  mov     rax, [rbp+1F0h+var_230]
0x140762b75  mov     eax, [rax+10h]
0x140762b78  test    al, 4
0x140762b7a  jnz     short loc_140762BAC
0x140762b7c  mov     r8d, dword ptr [rbp+1F0h+ppszDestEnd]
0x140762b80  lea     r9, [rbp+1F0h+var_270]
0x140762b84  mov     edx, [rsp+2F0h+var_278]
0x140762b88  mov     ecx, esi
0x140762b8a  call    IopDuplicateDetection
0x140762b8f  mov     rdi, [rbp+1F0h+var_270]
0x140762b93  mov     ebx, eax
0x140762b95  mov     esi, 1
0x140762b9a  test    eax, eax
0x140762b9c  js      short loc_140762BB1
0x140762b9e  test    rdi, rdi
0x140762ba1  cmovnz  r14d, esi
0x140762ba5  mov     [rsp+2F0h+var_290], r14d
0x140762baa  jmp     short loc_140762BB1
0x140762bac  mov     esi, 1
0x140762bb1  call    KeEnterCriticalRegion
0x140762bb6  mov     dl, sil; Wait
0x140762bb9  lea     rcx, PnpRegistryDeviceResource; Resource
0x140762bc0  call    ExAcquireResourceExclusiveLite
0x140762bc5  mov     esi, 13h
0x140762bca  test    rdi, rdi
0x140762bcd  jnz     loc_1407631A6
0x140762bd3  lea     rdx, asc_140B30730; "\\"
0x140762bda  lea     rcx, [rsp+2F0h+Destination]; Destination
0x140762bdf  call    RtlAppendUnicodeToString
0x140762be4  mov     ebx, eax
0x140762be6  test    eax, eax
0x140762be8  js      loc_140762D76
0x140762bee  movzx   ecx, [rsp+2F0h+Destination.Length]
0x140762bf3  mov     r14d, 190h
0x140762bf9  sub     r14, rcx
0x140762bfc  mov     [rsp+2F0h+var_278], ecx
0x140762c00  shr     r14, 1
0x140762c03  movzx   eax, cx
0x140762c06  lea     r8, [rbp+1F0h+ppszDestEnd]; ppszDestEnd
0x140762c0a  shr     rax, 1
0x140762c0d  xor     r9d, r9d; pcchRemaining
0x140762c10  mov     [rsp+2F0h+Destination.Length], cx
0x140762c15  mov     rdx, r14; cchDest
0x140762c18  mov     dword ptr [rsp+2F0h+var_2C0], r13d
0x140762c1d  lea     rcx, [rbp+1F0h+var_1E0]
0x140762c21  lea     rcx, [rcx+rax*2]; pszDest
0x140762c25  lea     rax, a04u; "%04u"
0x140762c2c  mov     [rbp+1F0h+ppszDestEnd], rcx
0x140762c30  mov     [rsp+2F0h+pszFormat], rax; pszFormat
0x140762c35  mov     qword ptr [rsp+2F0h+dwFlags], 0; dwFlags
0x140762c3e  call    RtlStringCchPrintfExW
0x140762c43  movzx   edx, [rsp+2F0h+Destination.Length]
0x140762c48  mov     rcx, [rbp+1F0h+ppszDestEnd]
0x140762c4c  mov     eax, edx
0x140762c4e  shr     rax, 1
0x140762c51  add     rax, rax
0x140762c54  sub     rcx, rax
0x140762c57  lea     rax, [rbp+1F0h+var_1E0]
0x140762c5b  sub     rcx, rax
0x140762c5e  sar     rcx, 1
0x140762c61  cmp     ecx, 0FFFFFFFFh
0x140762c64  jnz     short loc_140762C70
0x140762c66  mov     ecx, 190h
0x140762c6b  sub     cx, dx
0x140762c6e  jmp     short loc_140762C73
0x140762c70  add     cx, cx
0x140762c73  add     dx, cx
0x140762c76  mov     dword ptr [rsp+2F0h+pszFormat], 0
0x140762c7e  mov     rcx, cs:PiPnpRtlCtx
0x140762c85  lea     rax, [rsp+2F0h+var_2A0]
0x140762c8a  mov     [rsp+2F0h+Destination.Length], dx
0x140762c8f  lea     r9, [rsp+2F0h+cbMax+4]
0x140762c94  mov     rdx, [rsp+2F0h+Destination.Buffer]
0x140762c99  mov     r8d, 0F003Fh
0x140762c9f  mov     qword ptr [rsp+2F0h+dwFlags], rax
0x140762ca4  call    _CmCreateDevice
0x140762ca9  mov     ebx, eax
0x140762cab  test    eax, eax
0x140762cad  js      short loc_140762D21
0x140762caf  cmp     [rsp+2F0h+var_2A0], 0
0x140762cb4  jnz     loc_140762E01
0x140762cba  mov     rdx, qword ptr [rsp+2F0h+cbMax+4]
0x140762cbf  lea     rax, [rsp+2F0h+var_290]
0x140762cc4  mov     r9, r15
0x140762cc7  mov     qword ptr [rsp+2F0h+dwFlags], rax
0x140762ccc  mov     r8, r12
0x140762ccf  mov     [rsp+2F0h+var_290], 0
0x140762cd7  lea     rcx, [rsp+2F0h+Destination]
0x140762cdc  call    IopIsReportedAlready
0x140762ce1  test    al, al
0x140762ce3  jnz     short loc_140762CFB
0x140762ce5  mov     rcx, qword ptr [rsp+2F0h+cbMax+4]; Handle
0x140762cea  call    ZwClose
0x140762cef  mov     ecx, [rsp+2F0h+var_278]
0x140762cf3  inc     r13d
0x140762cf6  jmp     loc_140762C03
0x140762cfb  mov     edx, 746C6644h
0x140762d00  lea     rcx, [rsp+2F0h+Destination]
0x140762d05  call    PnpDeviceObjectFromDeviceInstanceWithTag
0x140762d0a  mov     [rbp+1F0h+var_248], rax
0x140762d0e  mov     r13, rax
0x140762d11  test    rax, rax
0x140762d14  jnz     loc_140762DF0
0x140762d1a  mov     ebx, 0C0000001h
0x140762d1f  xor     edi, edi
0x140762d21  cmp     [rsp+2F0h+var_2A0], 0
0x140762d26  jz      short loc_140762D76
0x140762d28  mov     rcx, [rbp+1F0h+KeyHandle]; KeyHandle
0x140762d2c  test    rcx, rcx
0x140762d2f  jz      short loc_140762D36
0x140762d31  call    ZwDeleteKey
0x140762d36  mov     rcx, [rbp+1F0h+var_258]; KeyHandle
0x140762d3a  test    rcx, rcx
0x140762d3d  jz      short loc_140762D44
0x140762d3f  call    ZwDeleteKey
0x140762d44  mov     rcx, qword ptr [rsp+2F0h+cbMax+4]; KeyHandle
0x140762d49  test    rcx, rcx
0x140762d4c  jz      short loc_140762D53
0x140762d4e  call    ZwDeleteKey
0x140762d53  lea     rcx, [rdi+28h]
0x140762d57  call    PnpCleanupDeviceRegistryValues
0x140762d5c  mov     rcx, rdi
0x140762d5f  call    PpDevNodeRemoveFromTree
0x140762d64  mov     rcx, [rdi+20h]; DeviceObject
0x140762d68  call    IoDeleteDevice
0x140762d6d  mov     rcx, [rdi+20h]; Object
0x140762d71  call    ObfDereferenceObject
0x140762d76  lea     rcx, PnpRegistryDeviceResource; Resource
0x140762d7d  call    ExReleaseResourceLite
0x140762d82  call    KeLeaveCriticalRegion
0x140762d87  mov     ecx, 1
0x140762d8c  call    PpDevNodeUnlockTree
0x140762d91  mov     rcx, [rbp+1F0h+KeyHandle]; Handle
0x140762d95  test    rcx, rcx
0x140762d98  jz      short loc_140762D9F
0x140762d9a  call    ZwClose
0x140762d9f  mov     rcx, [rbp+1F0h+var_258]; Handle
0x140762da3  test    rcx, rcx
0x140762da6  jz      short loc_140762DAD
0x140762da8  call    ZwClose
0x140762dad  mov     rcx, qword ptr [rsp+2F0h+cbMax+4]; Handle
0x140762db2  test    rcx, rcx
0x140762db5  jz      short loc_140762DBC
0x140762db7  call    ZwClose
0x140762dbc  mov     rcx, [rbp+1F0h+P]; P
0x140762dc0  test    rcx, rcx
0x140762dc3  jz      short loc_140762DCA
0x140762dc5  call    PiPnpRtlEndOperation
0x140762dca  mov     eax, ebx
0x140762dcc  mov     rcx, [rbp+1F0h+var_50]
0x140762dd3  xor     rcx, rsp; StackCookie
0x140762dd6  call    __security_check_cookie
0x140762ddb  add     rsp, 2B8h
0x140762de2  pop     r15
0x140762de4  pop     r14
0x140762de6  pop     r13
0x140762de8  pop     r12
0x140762dea  pop     rdi
0x140762deb  pop     rsi
0x140762dec  pop     rbx
0x140762ded  pop     rbp
0x140762dee  retn
0x140762df0  mov     rax, [rax+138h]
0x140762df7  mov     rdi, [rax+28h]
0x140762dfb  mov     [rbp+1F0h+var_270], rdi
0x140762dff  jmp     short loc_140762E05
0x140762e01  mov     r13, [rbp+1F0h+var_248]
0x140762e05  test    rdi, rdi
0x140762e08  jnz     loc_1407631A1
0x140762e0e  lea     rcx, [rbp+1F0h+var_248]
0x140762e12  call    IopCreateRootEnumeratedDeviceObject
0x140762e17  mov     ebx, eax
0x140762e19  test    eax, eax
0x140762e1b  js      loc_140762D21
0x140762e21  mov     r14, [rbp+1F0h+var_248]
0x140762e25  lea     rdx, [rbp+1F0h+var_270]
0x140762e29  mov     rcx, r14
0x140762e2c  bts     dword ptr [r14+30h], 0Ch
0x140762e32  call    PipAllocateDeviceNode
0x140762e37  mov     rdi, [rbp+1F0h+var_270]
0x140762e3b  cmp     eax, 0C000036Eh
0x140762e40  jz      loc_14076318F
0x140762e46  test    rdi, rdi
0x140762e49  jz      loc_14076318F
0x140762e4f  mov     rax, [rbp+1F0h+var_230]
0x140762e53  mov     eax, [rax+10h]
0x140762e56  test    al, 4
0x140762e58  jnz     short loc_140762EB6
0x140762e5a  movzx   edx, word ptr [r12]
0x140762e5f  mov     ecx, 100h
0x140762e64  mov     r8d, 48706E50h
0x140762e6a  call    ExAllocatePool2
0x140762e6f  mov     [rdi+40h], rax
0x140762e73  test    rax, rax
0x140762e76  jnz     short loc_140762E93
0x140762e78  mov     r8d, 0C000009Ah
0x140762e7e  mov     ebx, r8d
0x140762e81  mov     edx, 3
0x140762e86  mov     rcx, rdi
0x140762e89  call    PipSetDevNodeProblem
  ... truncated ...
```
