# IoReportDetectedDevice

- ea: `0x14075e580`
- end: `0x14075f009`
- name: `IoReportDetectedDevice`
- size: `2697`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, INTERFACE_TYPE LegacyBusType, ULONG BusNumber, ULONG SlotNumber, PCM_RESOURCE_LIST ResourceList, PIO_RESOURCE_REQUIREMENTS_LIST ResourceRequirements, BOOLEAN ResourceAssigned, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `56`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140743f40`

## callees

- `0x140224b50`
- `0x140224f70`
- `0x140226300`
- `0x1402268e0`
- `0x140227210`
- `0x1402f8270`
- `0x1403f2d50`
- `0x1403f4770`
- `0x1403fc6a0`
- `0x140406bc0`
- `0x14043bfa4`
- `0x14043c78c`
- `0x14043da78`
- `0x14043dadc`
- `0x1404a4fc8`
- `0x1404b5524`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406db490`
- `0x1406dc410`
- `0x1406f4480`
- `0x14075e580`
- `0x14075f3b0`
- `0x14075f440`
- `0x14075f4cc`
- `0x1407626d8`
- `0x140764590`
- `0x140765864`
- `0x140765ef4`
- `0x14076dc08`
- `0x1407724bc`
- `0x1408ba060`
- `0x1408bd1c0`
- `0x1408c85dc`
- `0x1408c8790`
- `0x1408d3940`
- `0x1408d4330`
- `0x1408d8f9c`
- `0x1408d9114`
- `0x1408e1d34`
- `0x1408e47a4`
- `0x1408e7220`
- `0x1408e727c`
- `0x14095bf44`
- `0x14095ce38`
- `0x14097e5b0`
- `0x1409df8c0`
- `0x140a2b8d8`
- `0x140a378a4`
- `0x140aa06d0`

## string_xrefs

- `0x14075ee0b`: `BootConfig`
- `0x14075ee5b`: `BasicConfigVector`

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
  int appended; // ebx
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
  __int64 v29; // r8
  __int64 v30; // rdx
  char *v31; // rcx
  NTSTATUS DeviceInstancePath; // eax
  int v33; // eax
  STRSAFE_PCNZWCH v34; // r13
  __int64 v35; // rdx
  __int64 v36; // r9
  PDRIVER_OBJECT v37; // rbx
  bool v38; // zf
  UNICODE_STRING *v39; // rbx
  int LegacyDeviceIds; // eax
  char v41; // r12
  unsigned int v42; // eax
  int v43; // ecx
  _DWORD *v44; // r14
  HANDLE v45; // rbx
  ULONG v46; // eax
  HANDLE v47; // rbx
  unsigned int v48; // eax
  unsigned int v49; // ebx
  void *v50; // rax
  void *v51; // rsi
  __int64 v52; // r8
  int v53; // edx
  int *dwFlags; // [rsp+20h] [rbp-E0h]
  NTSTRSAFE_PCWSTR pszFormat; // [rsp+28h] [rbp-D8h]
  __int64 v56; // [rsp+30h] [rbp-D0h]
  int v57; // [rsp+38h] [rbp-C8h]
  int v58; // [rsp+40h] [rbp-C0h]
  char v59; // [rsp+50h] [rbp-B0h] BYREF
  char v60; // [rsp+51h] [rbp-AFh] BYREF
  char v61[2]; // [rsp+52h] [rbp-AEh] BYREF
  _DWORD cbMax[3]; // [rsp+54h] [rbp-ACh] BYREF
  int v63; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING Destination; // [rsp+68h] [rbp-98h] BYREF
  ULONG v65; // [rsp+78h] [rbp-88h]
  char *v66; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+88h] [rbp-78h] BYREF
  HANDLE KeyHandle; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v69; // [rsp+98h] [rbp-68h] BYREF
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+A0h] [rbp-60h] BYREF
  PDEVICE_OBJECT v71; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  PDRIVER_OBJECT v73; // [rsp+C0h] [rbp-40h]
  STRSAFE_PCNZWCH psz; // [rsp+C8h] [rbp-38h] BYREF
  size_t pcbLength; // [rsp+D0h] [rbp-30h] BYREF
  PVOID P; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v77; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v78; // [rsp+F0h] [rbp-10h] BYREF
  PDEVICE_OBJECT *v79; // [rsp+100h] [rbp+0h]
  _WORD v80[200]; // [rsp+110h] [rbp+10h] BYREF

  p_ServiceKeyName = &DriverObject->DriverExtension->ServiceKeyName;
  *(_QWORD *)&DestinationString.Length = ResourceRequirements;
  LODWORD(ppszDestEnd) = SlotNumber;
  Destination.Buffer = v80;
  DeviceNode = 0;
  v11 = *DeviceObject;
  v12 = 0;
  v65 = BusNumber;
  v13 = 0;
  v73 = DriverObject;
  v79 = DeviceObject;
  v60 = 0;
  *(_QWORD *)&Destination.Length = 26214400;
  psz = 0;
  memset(cbMax, 0, sizeof(cbMax));
  pcbLength = 0;
  v67 = 0;
  v69 = 0;
  v59 = 0;
  v66 = 0;
  v63 = 0;
  KeyHandle = 0;
  v71 = 0;
  P = 0;
  v77 = 0;
  v78 = 0;
  if ( v11 )
  {
    DeviceNode = (char *)v11->DeviceObjectExtension->DeviceNode;
    v66 = DeviceNode;
    if ( !DeviceNode )
      return -1073741578;
LABEL_13:
    appended = PiPnpRtlBeginOperation(&P);
    if ( appended >= 0 )
    {
      PpDevNodeLockTree(1);
      if ( !DeviceNode && (v73->Flags & 4) == 0 )
      {
        v19 = IopDuplicateDetection((unsigned int)LegacyBusType, v65, (unsigned int)ppszDestEnd, &v66);
        DeviceNode = v66;
        appended = v19;
        if ( v19 >= 0 )
        {
          if ( v66 )
            v12 = 1;
          v63 = v12;
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
        v65 = Destination.Length;
        v21 = (400 - (unsigned __int64)Destination.Length) >> 1;
        while ( 1 )
        {
          Destination.Length = Length;
          LODWORD(v56) = (_DWORD)v13;
          ppszDestEnd = &v80[(unsigned __int64)Length >> 1];
          RtlStringCchPrintfExW(ppszDestEnd, v21, &ppszDestEnd, 0, 0, L"%04u", v56);
          v22 = &ppszDestEnd[-((unsigned __int64)Destination.Length >> 1)] - v80;
          if ( (_DWORD)v22 == -1 )
            v23 = 400 - Destination.Length;
          else
            v23 = 2 * v22;
          Destination.Length += v23;
          appended = CmCreateDevice(PiPnpRtlCtx, Destination.Buffer, 983103, (unsigned int)&cbMax[1], (__int64)&v59, 0);
          if ( appended < 0 )
            goto LABEL_32;
          if ( v59 )
          {
            v13 = v71;
            goto LABEL_52;
          }
          dwFlags = &v63;
          v63 = 0;
          if ( (unsigned __int8)IopIsReportedAlready(&Destination, *(_QWORD *)&cbMax[1], p_ServiceKeyName, ResourceList) )
            break;
          ZwClose(*(HANDLE *)&cbMax[1]);
          Length = v65;
          LODWORD(v13) = (_DWORD)v13 + 1;
        }
        v24 = (struct _DEVICE_OBJECT *)PnpDeviceObjectFromDeviceInstanceWithTag(&Destination, 1953261124);
        v71 = v24;
        v13 = v24;
        if ( !v24 )
        {
          appended = -1073741823;
          DeviceNode = 0;
          goto LABEL_32;
        }
        DeviceNode = (char *)v24->DeviceObjectExtension->DeviceNode;
        v66 = DeviceNode;
LABEL_52:
        if ( !DeviceNode )
        {
          appended = IopCreateRootEnumeratedDeviceObject(&v71);
          if ( appended < 0 )
            goto LABEL_32;
          v25 = v71;
          v26 = v71;
          v71->Flags |= 0x1000u;
          v27 = PipAllocateDeviceNode(v26, &v66);
          DeviceNode = v66;
          if ( v27 == -1073740946 || !v66 )
          {
            IoDeleteDevice(v25);
            appended = -1073741670;
            goto LABEL_32;
          }
          if ( (v73->Flags & 4) == 0 )
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
          v67 = 32;
          v33 = CmSetDeviceRegProp(PiPnpRtlCtx, *((_QWORD *)DeviceNode + 6), cbMax[1], 11, 4, (__int64)&v67, 4, 0);
          appended = v33;
          if ( v33 < 0 )
            goto LABEL_67;
          v60 = -1;
          v33 = PnpSetObjectProperty(
                  PiPnpRtlCtx,
                  *((_QWORD *)DeviceNode + 6),
                  1,
                  0,
                  (__int64)&DEVPKEY_Device_Reported,
                  17,
                  (__int64)&v60,
                  1,
                  0);
          appended = v33;
          if ( v33 < 0 )
            goto LABEL_67;
          v33 = PnpUnicodeStringToWstr(&psz, cbMax, p_ServiceKeyName);
          appended = v33;
          if ( v33 < 0 )
            goto LABEL_67;
          v34 = psz;
          appended = RtlStringCbLengthW(psz, cbMax[0], &pcbLength);
          if ( appended < 0 )
          {
            PnpUnicodeStringToWstrFree(v34, p_ServiceKeyName);
LABEL_73:
            v29 = (unsigned int)appended;
            goto LABEL_68;
          }
          appended = CmSetDeviceRegProp(
                       PiPnpRtlCtx,
                       *((_QWORD *)DeviceNode + 6),
                       cbMax[1],
                       5,
                       1,
                       (__int64)v34,
                       (int)pcbLength + 2,
                       0);
          PnpUnicodeStringToWstrFree(v34, p_ServiceKeyName);
          if ( appended < 0 )
            goto LABEL_73;
          v69 = 0;
          v33 = CmOpenDeviceRegKey(
                  *(__int64 *)&PiPnpRtlCtx,
                  *((_QWORD *)DeviceNode + 6),
                  19,
                  0,
                  983103,
                  1,
                  (__int64)&v69,
                  0);
          appended = v33;
          if ( v33 < 0 )
            goto LABEL_67;
          v33 = PnpSetRegistryDword(v69, L"DeviceReported");
          appended = v33;
          if ( v33 < 0 )
            goto LABEL_67;
          v37 = v73;
          if ( (v73->Flags & 4) == 0 )
          {
            LOBYTE(v36) = 1;
            LOBYTE(v35) = 1;
            PpDeviceRegistration(&Destination, v35, 0, v36);
          }
          Destination.Buffer = 0;
          v38 = (v37->Flags & 4) == 0;
          v39 = (UNICODE_STRING *)&v77;
          *(_DWORD *)&Destination.Length = 0;
          if ( v38 )
            v39 = p_ServiceKeyName;
          cbMax[0] = 400;
          if ( (int)IopGetOriginalServiceName(v39, v80, cbMax) >= 0 && cbMax[0] > 2u )
          {
            WORD1(v78) = 400;
            *((_QWORD *)&v78 + 1) = v80;
            LOWORD(v78) = LOWORD(cbMax[0]) - 2;
            v39 = (UNICODE_STRING *)&v78;
          }
          LegacyDeviceIds = IopCreateLegacyDeviceIds(v25, v39, ResourceList);
          appended = LegacyDeviceIds;
          v31 = DeviceNode;
          if ( LegacyDeviceIds < 0 )
          {
            v29 = (unsigned int)LegacyDeviceIds;
            v30 = 19;
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
            v29 = (unsigned int)DeviceInstancePath;
            goto LABEL_59;
          }
          v41 = 1;
          PsReferenceSiloContext(v25);
LABEL_99:
          v44 = *(_DWORD **)&DestinationString.Length;
          if ( !ResourceList && !*(_QWORD *)&DestinationString.Length )
            goto LABEL_106;
          v33 = CmOpenDeviceRegKey(
                  *(__int64 *)&PiPnpRtlCtx,
                  *((_QWORD *)DeviceNode + 6),
                  20,
                  0,
                  983103,
                  1,
                  (__int64)&KeyHandle,
                  0);
          appended = v33;
          if ( v33 >= 0 )
          {
            if ( !ResourceList
              || (v45 = KeyHandle,
                  DestinationString = 0,
                  RtlInitUnicodeString(&DestinationString, L"BootConfig"),
                  v46 = PnpDetermineResourceListSize(ResourceList),
                  v33 = ZwSetValueKey(v45, &DestinationString, 0, 8u, ResourceList, v46),
                  appended = v33,
                  v33 >= 0) )
            {
              if ( !v44
                || (v47 = KeyHandle,
                    DestinationString = 0,
                    RtlInitUnicodeString(&DestinationString, L"BasicConfigVector"),
                    v33 = ZwSetValueKey(v47, &DestinationString, 0, 0xAu, v44, *v44),
                    appended = v33,
                    v33 >= 0) )
              {
LABEL_106:
                if ( ResourceAssigned )
                {
                  PipSetDevNodeFlags(DeviceNode, 256);
                  PnpSetRegistryDword(*(HANDLE *)&cbMax[1], L"NoResourceAtInitTime");
                  v48 = PnpDetermineResourceListSize(ResourceList);
                  IopWriteAllocatedResourcesToRegistry(DeviceNode, ResourceList, v48);
                }
                else if ( ResourceList && ResourceList->Count && ResourceList->List[0].PartialResourceList.Count )
                {
                  v49 = PnpDetermineResourceListSize(ResourceList);
                  v50 = (void *)ExAllocatePool2(256, v49, 1198550608);
                  v51 = v50;
                  if ( !v50 )
                  {
LABEL_58:
                    v29 = 3221225626LL;
                    appended = -1073741670;
LABEL_59:
                    v30 = 3;
                    goto LABEL_60;
                  }
                  memmove(v50, ResourceList, v49);
                  pszFormat = (NTSTRSAFE_PCWSTR)*((_QWORD *)DeviceNode + 4);
                  v52 = *((_QWORD *)pszFormat + 1);
                  v61[0] = 0;
                  appended = IoReportResourceUsageInternal(
                               0,
                               v53,
                               v52,
                               0,
                               (_DWORD)dwFlags,
                               (__int64)pszFormat,
                               (__int64)v51,
                               v57,
                               v58,
                               (__int64)v61);
                  ExFreePoolWithTag(v51, 0x47706E50u);
                  if ( appended >= 0 && !v61[0] )
                  {
LABEL_120:
                    *((_DWORD *)DeviceNode + 165) = *(_DWORD *)(*((_QWORD *)DeviceNode + 2) + 660LL);
                    IopDoDeferredSetInterfaceState(DeviceNode);
                    PipSetDevNodeState(DeviceNode, 777);
                    if ( v41 )
                      PipSetDevNodeFlags(DeviceNode, 0x80000000LL);
                    *v79 = (PDEVICE_OBJECT)*((_QWORD *)DeviceNode + 4);
                    goto LABEL_40;
                  }
                  if ( !(unsigned int)PipIsDevNodeDNStarted(DeviceNode) )
                    PipSetDevNodeProblem(DeviceNode, 12, (unsigned int)appended);
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
          v29 = (unsigned int)v33;
LABEL_68:
          v30 = 19;
LABEL_60:
          v31 = DeviceNode;
LABEL_61:
          PipSetDevNodeProblem(v31, v30, v29);
          goto LABEL_32;
        }
        v12 = v63;
LABEL_90:
        if ( v12 )
        {
          if ( (unsigned int)PipAreDriversLoaded(DeviceNode)
            || (*((_DWORD *)DeviceNode + 99) & 0x6000) != 0
            && ((v42 = *((_DWORD *)DeviceNode + 101), v42 > 0x1C) || (v43 = 268697602, !_bittest(&v43, v42))) )
          {
            ObfDereferenceObject(*((PVOID *)DeviceNode + 4));
            appended = -1073741810;
            goto LABEL_32;
          }
          if ( !v13 )
            PipClearDevNodeProblem(DeviceNode);
        }
        v41 = 0;
        if ( !*(_QWORD *)&cbMax[1] )
        {
          appended = PnpDeviceObjectToDeviceInstance(*((_QWORD *)DeviceNode + 4), &cbMax[1], 983103);
          if ( appended < 0 )
          {
LABEL_32:
            if ( v59 )
            {
              if ( KeyHandle )
                ZwDeleteKey(KeyHandle);
              if ( v69 )
                ZwDeleteKey(v69);
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
    if ( v69 )
      ZwClose(v69);
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
        *((_QWORD *)&v77 + 1) = i + 1;
        v17 = (const UNICODE_STRING *)&v77;
        LOWORD(v77) = p_ServiceKeyName->Length
                    - 2 * ((__int64)(unsigned int)((_DWORD)i + 2 - LODWORD(p_ServiceKeyName->Buffer)) >> 1);
        WORD1(v77) = v77;
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
0x14075e580  push    rbp
0x14075e582  push    rbx
0x14075e583  push    rsi
0x14075e584  push    rdi
0x14075e585  push    r12
0x14075e587  push    r13
0x14075e589  push    r14
0x14075e58b  push    r15
0x14075e58d  lea     rbp, [rsp-1B8h]
0x14075e595  sub     rsp, 2B8h
0x14075e59c  mov     rax, cs:__security_cookie
0x14075e5a3  xor     rax, rsp
0x14075e5a6  mov     [rbp+1F0h+var_50], rax
0x14075e5ad  mov     rax, [rbp+1F0h+ResourceRequirements]
0x14075e5b4  xor     ebx, ebx
0x14075e5b6  mov     r12, [rcx+30h]
0x14075e5ba  mov     esi, edx
0x14075e5bc  mov     rdx, [rbp+1F0h+DeviceObject]
0x14075e5c3  add     r12, 18h
0x14075e5c7  mov     r15, [rbp+1F0h+ResourceList]
0x14075e5ce  xorps   xmm0, xmm0
0x14075e5d1  mov     qword ptr [rbp+1F0h+DestinationString.Length], rax
0x14075e5d5  xorps   xmm1, xmm1
0x14075e5d8  lea     rax, [rbp+1F0h+var_1E0]
0x14075e5dc  mov     dword ptr [rbp+1F0h+ppszDestEnd], r9d
0x14075e5e0  mov     [rsp+2F0h+Destination.Buffer], rax
0x14075e5e5  mov     edi, ebx
0x14075e5e7  mov     rax, [rdx]
0x14075e5ea  mov     r14d, ebx
0x14075e5ed  mov     [rsp+2F0h+var_278], r8d
0x14075e5f2  mov     r13d, ebx
0x14075e5f5  mov     [rbp+1F0h+var_230], rcx
0x14075e5f9  mov     [rbp+1F0h+var_1F0], rdx
0x14075e5fd  mov     [rsp+2F0h+var_29F], bl
0x14075e601  mov     qword ptr [rsp+2F0h+Destination.Length], 1900000h
0x14075e60a  mov     [rbp+1F0h+psz], rbx
0x14075e60e  mov     dword ptr [rsp+2F0h+cbMax], ebx
0x14075e612  mov     [rbp+1F0h+pcbLength], rbx
0x14075e616  mov     [rbp+1F0h+var_268], ebx
0x14075e619  mov     [rbp+1F0h+var_258], rbx
0x14075e61d  mov     [rsp+2F0h+var_2A0], bl
0x14075e621  mov     [rbp+1F0h+var_270], rbx
0x14075e625  mov     [rsp+2F0h+var_290], ebx
0x14075e629  mov     qword ptr [rsp+2F0h+cbMax+4], rbx
0x14075e62e  mov     [rbp+1F0h+KeyHandle], rbx
0x14075e632  mov     [rbp+1F0h+var_248], rbx
0x14075e636  mov     [rbp+1F0h+P], rbx
0x14075e63a  movups  [rbp+1F0h+var_210], xmm0
0x14075e63e  movups  [rbp+1F0h+var_200], xmm1
0x14075e642  test    rax, rax
0x14075e645  jz      short loc_14075E669
0x14075e647  mov     rax, [rax+138h]
0x14075e64e  mov     rdi, [rax+28h]
0x14075e652  mov     [rbp+1F0h+var_270], rdi
0x14075e656  test    rdi, rdi
0x14075e659  jnz     loc_14075E6DF
0x14075e65f  mov     eax, 0C00000F6h
0x14075e664  jmp     loc_14075E95C
0x14075e669  mov     eax, [rcx+10h]
0x14075e66c  test    al, 4
0x14075e66e  jz      short loc_14075E6CA
0x14075e670  movzx   eax, word ptr [r12]
0x14075e675  mov     rcx, [r12+8]
0x14075e67a  shr     rax, 1
0x14075e67d  dec     rax
0x14075e680  lea     rax, [rcx+rax*2]
0x14075e684  cmp     rax, rcx
0x14075e687  jz      short loc_14075E6C0
0x14075e689  cmp     word ptr [rax], 5Ch ; '\'
0x14075e68d  jz      short loc_14075E695
0x14075e68f  sub     rax, 2
0x14075e693  jmp     short loc_14075E684
0x14075e695  add     rax, 2
0x14075e699  mov     ecx, eax
0x14075e69b  mov     qword ptr [rbp+1F0h+var_210+8], rax
0x14075e69f  sub     ecx, [r12+8]
0x14075e6a4  movzx   eax, word ptr [r12]
0x14075e6a9  sar     rcx, 1
0x14075e6ac  add     cx, cx
0x14075e6af  sub     ax, cx
0x14075e6b2  lea     rcx, [rbp+1F0h+var_210]
0x14075e6b6  mov     word ptr [rbp+1F0h+var_210], ax
0x14075e6ba  mov     word ptr [rbp+1F0h+var_210+2], ax
0x14075e6be  jmp     short loc_14075E6CD
0x14075e6c0  mov     eax, 0C00000EFh
0x14075e6c5  jmp     loc_14075E95C
0x14075e6ca  mov     rcx, r12; Source
0x14075e6cd  lea     rdx, [rsp+2F0h+Destination]; Destination
0x14075e6d2  call    IopGetRootDeviceId
0x14075e6d7  test    eax, eax
0x14075e6d9  js      loc_14075E95C
0x14075e6df  lea     rcx, [rbp+1F0h+P]
0x14075e6e3  call    PiPnpRtlBeginOperation
0x14075e6e8  mov     ebx, eax
0x14075e6ea  test    eax, eax
0x14075e6ec  js      loc_14075E906
0x14075e6f2  mov     ecx, 1
0x14075e6f7  call    PpDevNodeLockTree
0x14075e6fc  test    rdi, rdi
0x14075e6ff  jnz     short loc_14075E73C
0x14075e701  mov     rax, [rbp+1F0h+var_230]
0x14075e705  mov     eax, [rax+10h]
0x14075e708  test    al, 4
0x14075e70a  jnz     short loc_14075E73C
0x14075e70c  mov     r8d, dword ptr [rbp+1F0h+ppszDestEnd]
0x14075e710  lea     r9, [rbp+1F0h+var_270]
0x14075e714  mov     edx, [rsp+2F0h+var_278]
0x14075e718  mov     ecx, esi
0x14075e71a  call    IopDuplicateDetection
0x14075e71f  mov     rdi, [rbp+1F0h+var_270]
0x14075e723  mov     ebx, eax
0x14075e725  mov     esi, 1
0x14075e72a  test    eax, eax
0x14075e72c  js      short loc_14075E741
0x14075e72e  test    rdi, rdi
0x14075e731  cmovnz  r14d, esi
0x14075e735  mov     [rsp+2F0h+var_290], r14d
0x14075e73a  jmp     short loc_14075E741
0x14075e73c  mov     esi, 1
0x14075e741  call    KeEnterCriticalRegion
0x14075e746  mov     dl, sil; Wait
0x14075e749  lea     rcx, PnpRegistryDeviceResource; Resource
0x14075e750  call    ExAcquireResourceExclusiveLite
0x14075e755  mov     esi, 13h
0x14075e75a  test    rdi, rdi
0x14075e75d  jnz     loc_14075ED36
0x14075e763  lea     rdx, asc_140B2F250; "\\"
0x14075e76a  lea     rcx, [rsp+2F0h+Destination]; Destination
0x14075e76f  call    RtlAppendUnicodeToString
0x14075e774  mov     ebx, eax
0x14075e776  test    eax, eax
0x14075e778  js      loc_14075E906
0x14075e77e  movzx   ecx, [rsp+2F0h+Destination.Length]
0x14075e783  mov     r14d, 190h
0x14075e789  sub     r14, rcx
0x14075e78c  mov     [rsp+2F0h+var_278], ecx
0x14075e790  shr     r14, 1
0x14075e793  movzx   eax, cx
0x14075e796  lea     r8, [rbp+1F0h+ppszDestEnd]; ppszDestEnd
0x14075e79a  shr     rax, 1
0x14075e79d  xor     r9d, r9d; pcchRemaining
0x14075e7a0  mov     [rsp+2F0h+Destination.Length], cx
0x14075e7a5  mov     rdx, r14; cchDest
0x14075e7a8  mov     dword ptr [rsp+2F0h+var_2C0], r13d
0x14075e7ad  lea     rcx, [rbp+1F0h+var_1E0]
0x14075e7b1  lea     rcx, [rcx+rax*2]; pszDest
0x14075e7b5  lea     rax, a04u; "%04u"
0x14075e7bc  mov     [rbp+1F0h+ppszDestEnd], rcx
0x14075e7c0  mov     [rsp+2F0h+pszFormat], rax; pszFormat
0x14075e7c5  mov     qword ptr [rsp+2F0h+dwFlags], 0; dwFlags
0x14075e7ce  call    RtlStringCchPrintfExW
0x14075e7d3  movzx   edx, [rsp+2F0h+Destination.Length]
0x14075e7d8  mov     rcx, [rbp+1F0h+ppszDestEnd]
0x14075e7dc  mov     eax, edx
0x14075e7de  shr     rax, 1
0x14075e7e1  add     rax, rax
0x14075e7e4  sub     rcx, rax
0x14075e7e7  lea     rax, [rbp+1F0h+var_1E0]
0x14075e7eb  sub     rcx, rax
0x14075e7ee  sar     rcx, 1
0x14075e7f1  cmp     ecx, 0FFFFFFFFh
0x14075e7f4  jnz     short loc_14075E800
0x14075e7f6  mov     ecx, 190h
0x14075e7fb  sub     cx, dx
0x14075e7fe  jmp     short loc_14075E803
0x14075e800  add     cx, cx
0x14075e803  add     dx, cx
0x14075e806  mov     dword ptr [rsp+2F0h+pszFormat], 0
0x14075e80e  mov     rcx, cs:PiPnpRtlCtx
0x14075e815  lea     rax, [rsp+2F0h+var_2A0]
0x14075e81a  mov     [rsp+2F0h+Destination.Length], dx
0x14075e81f  lea     r9, [rsp+2F0h+cbMax+4]
0x14075e824  mov     rdx, [rsp+2F0h+Destination.Buffer]
0x14075e829  mov     r8d, 0F003Fh
0x14075e82f  mov     qword ptr [rsp+2F0h+dwFlags], rax
0x14075e834  call    _CmCreateDevice
0x14075e839  mov     ebx, eax
0x14075e83b  test    eax, eax
0x14075e83d  js      short loc_14075E8B1
0x14075e83f  cmp     [rsp+2F0h+var_2A0], 0
0x14075e844  jnz     loc_14075E991
0x14075e84a  mov     rdx, qword ptr [rsp+2F0h+cbMax+4]
0x14075e84f  lea     rax, [rsp+2F0h+var_290]
0x14075e854  mov     r9, r15
0x14075e857  mov     qword ptr [rsp+2F0h+dwFlags], rax
0x14075e85c  mov     r8, r12
0x14075e85f  mov     [rsp+2F0h+var_290], 0
0x14075e867  lea     rcx, [rsp+2F0h+Destination]
0x14075e86c  call    IopIsReportedAlready
0x14075e871  test    al, al
0x14075e873  jnz     short loc_14075E88B
0x14075e875  mov     rcx, qword ptr [rsp+2F0h+cbMax+4]; Handle
0x14075e87a  call    ZwClose
0x14075e87f  mov     ecx, [rsp+2F0h+var_278]
0x14075e883  inc     r13d
0x14075e886  jmp     loc_14075E793
0x14075e88b  mov     edx, 746C6644h
0x14075e890  lea     rcx, [rsp+2F0h+Destination]
0x14075e895  call    PnpDeviceObjectFromDeviceInstanceWithTag
0x14075e89a  mov     [rbp+1F0h+var_248], rax
0x14075e89e  mov     r13, rax
0x14075e8a1  test    rax, rax
0x14075e8a4  jnz     loc_14075E980
0x14075e8aa  mov     ebx, 0C0000001h
0x14075e8af  xor     edi, edi
0x14075e8b1  cmp     [rsp+2F0h+var_2A0], 0
0x14075e8b6  jz      short loc_14075E906
0x14075e8b8  mov     rcx, [rbp+1F0h+KeyHandle]; KeyHandle
0x14075e8bc  test    rcx, rcx
0x14075e8bf  jz      short loc_14075E8C6
0x14075e8c1  call    ZwDeleteKey
0x14075e8c6  mov     rcx, [rbp+1F0h+var_258]; KeyHandle
0x14075e8ca  test    rcx, rcx
0x14075e8cd  jz      short loc_14075E8D4
0x14075e8cf  call    ZwDeleteKey
0x14075e8d4  mov     rcx, qword ptr [rsp+2F0h+cbMax+4]; KeyHandle
0x14075e8d9  test    rcx, rcx
0x14075e8dc  jz      short loc_14075E8E3
0x14075e8de  call    ZwDeleteKey
0x14075e8e3  lea     rcx, [rdi+28h]
0x14075e8e7  call    PnpCleanupDeviceRegistryValues
0x14075e8ec  mov     rcx, rdi
0x14075e8ef  call    PpDevNodeRemoveFromTree
0x14075e8f4  mov     rcx, [rdi+20h]; DeviceObject
0x14075e8f8  call    IoDeleteDevice
0x14075e8fd  mov     rcx, [rdi+20h]; Object
0x14075e901  call    ObfDereferenceObject
0x14075e906  lea     rcx, PnpRegistryDeviceResource; Resource
0x14075e90d  call    ExReleaseResourceLite
0x14075e912  call    KeLeaveCriticalRegion
0x14075e917  mov     ecx, 1
0x14075e91c  call    PpDevNodeUnlockTree
0x14075e921  mov     rcx, [rbp+1F0h+KeyHandle]; Handle
0x14075e925  test    rcx, rcx
0x14075e928  jz      short loc_14075E92F
0x14075e92a  call    ZwClose
0x14075e92f  mov     rcx, [rbp+1F0h+var_258]; Handle
0x14075e933  test    rcx, rcx
0x14075e936  jz      short loc_14075E93D
0x14075e938  call    ZwClose
0x14075e93d  mov     rcx, qword ptr [rsp+2F0h+cbMax+4]; Handle
0x14075e942  test    rcx, rcx
0x14075e945  jz      short loc_14075E94C
0x14075e947  call    ZwClose
0x14075e94c  mov     rcx, [rbp+1F0h+P]; P
0x14075e950  test    rcx, rcx
0x14075e953  jz      short loc_14075E95A
0x14075e955  call    PiPnpRtlEndOperation
0x14075e95a  mov     eax, ebx
0x14075e95c  mov     rcx, [rbp+1F0h+var_50]
0x14075e963  xor     rcx, rsp; StackCookie
0x14075e966  call    __security_check_cookie
0x14075e96b  add     rsp, 2B8h
0x14075e972  pop     r15
0x14075e974  pop     r14
0x14075e976  pop     r13
0x14075e978  pop     r12
0x14075e97a  pop     rdi
0x14075e97b  pop     rsi
0x14075e97c  pop     rbx
0x14075e97d  pop     rbp
0x14075e97e  retn
0x14075e980  mov     rax, [rax+138h]
0x14075e987  mov     rdi, [rax+28h]
0x14075e98b  mov     [rbp+1F0h+var_270], rdi
0x14075e98f  jmp     short loc_14075E995
0x14075e991  mov     r13, [rbp+1F0h+var_248]
0x14075e995  test    rdi, rdi
0x14075e998  jnz     loc_14075ED31
0x14075e99e  lea     rcx, [rbp+1F0h+var_248]
0x14075e9a2  call    IopCreateRootEnumeratedDeviceObject
0x14075e9a7  mov     ebx, eax
0x14075e9a9  test    eax, eax
0x14075e9ab  js      loc_14075E8B1
0x14075e9b1  mov     r14, [rbp+1F0h+var_248]
0x14075e9b5  lea     rdx, [rbp+1F0h+var_270]
0x14075e9b9  mov     rcx, r14
0x14075e9bc  bts     dword ptr [r14+30h], 0Ch
0x14075e9c2  call    PipAllocateDeviceNode
0x14075e9c7  mov     rdi, [rbp+1F0h+var_270]
0x14075e9cb  cmp     eax, 0C000036Eh
0x14075e9d0  jz      loc_14075ED1F
0x14075e9d6  test    rdi, rdi
0x14075e9d9  jz      loc_14075ED1F
0x14075e9df  mov     rax, [rbp+1F0h+var_230]
0x14075e9e3  mov     eax, [rax+10h]
0x14075e9e6  test    al, 4
0x14075e9e8  jnz     short loc_14075EA46
0x14075e9ea  movzx   edx, word ptr [r12]
0x14075e9ef  mov     ecx, 100h
0x14075e9f4  mov     r8d, 48706E50h
0x14075e9fa  call    ExAllocatePool2
0x14075e9ff  mov     [rdi+40h], rax
0x14075ea03  test    rax, rax
0x14075ea06  jnz     short loc_14075EA23
0x14075ea08  mov     r8d, 0C000009Ah
0x14075ea0e  mov     ebx, r8d
0x14075ea11  mov     edx, 3
0x14075ea16  mov     rcx, rdi
0x14075ea19  call    PipSetDevNodeProblem
  ... truncated ...
```
