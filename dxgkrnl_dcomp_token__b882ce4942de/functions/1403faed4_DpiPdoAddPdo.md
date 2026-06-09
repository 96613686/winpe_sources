# DpiPdoAddPdo

- ea: `0x1403faed4`
- end: `0x1403fb71a`
- name: `DpiPdoAddPdo`
- size: `2118`
- prototype: `__int64 __fastcall(int, int, int, int, char, BOOLEAN, struct _DXGK_CONNECTION_USB4_INFO *, unsigned __int8 *, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1403651a8`

## callees

- `0x14004546c`
- `0x14005c75c`
- `0x140188fe0`
- `0x1401ab39c`
- `0x1401ab660`
- `0x1402a27c0`
- `0x1402b199c`
- `0x1402be140`
- `0x1402be56c`
- `0x1402c80fc`
- `0x1403faed4`
- `0x1403fb720`
- `0x140404050`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403fb6af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403fb6f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403fb6af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403fb6f3`
- `ntoskrnl!IoFreeWorkItem` at `0x1403fb695`
- `ntoskrnl!IoFreeWorkItem` at `0x1403fb695`
- `ntoskrnl!ExAllocatePool2` at `0x1403fb1cc`
- `ntoskrnl!ExAllocatePool2` at `0x1403fb1cc`
- `ntoskrnl!KeInitializeEvent` at `0x1403fb178`
- `ntoskrnl!KeInitializeEvent` at `0x1403fb197`
- `ntoskrnl!KeInitializeEvent` at `0x1403fb178`
- `ntoskrnl!KeInitializeEvent` at `0x1403fb197`
- `ntoskrnl!ExDeleteResourceLite` at `0x1403fb67d`
- `ntoskrnl!ExDeleteResourceLite` at `0x1403fb67d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1403fb664`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1403fb664`
- `ntoskrnl!ExInitializeResourceLite` at `0x1403fb21b`
- `ntoskrnl!ExInitializeResourceLite` at `0x1403fb21b`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403fb259`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403fb259`
- `ntoskrnl!RtlCompareMemory` at `0x1403fb034`
- `ntoskrnl!RtlCompareMemory` at `0x1403fb034`
- `ntoskrnl!IoDeleteDevice` at `0x1403fb6cf`
- `ntoskrnl!IoDeleteDevice` at `0x1403fb6cf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb393`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb574`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb626`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb393`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb574`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb626`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb3ac`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb591`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb63f`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb3ac`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb591`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb63f`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1403fb1b7`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1403fb1b7`
- `watchdog!WdLogSingleEntry1` at `0x1403faf6a`
- `watchdog!WdLogSingleEntry1` at `0x1403fafbc`
- `watchdog!WdLogSingleEntry1` at `0x1403fb05f`
- `watchdog!WdLogSingleEntry1` at `0x1403fb0ff`
- `watchdog!WdLogSingleEntry1` at `0x1403fb1f2`
- `watchdog!WdLogSingleEntry1` at `0x1403fb236`
- `watchdog!WdLogSingleEntry1` at `0x1403fb27d`
- `watchdog!WdLogSingleEntry1` at `0x1403fb451`
- `watchdog!WdLogSingleEntry1` at `0x1403fb4bc`
- `watchdog!WdLogSingleEntry1` at `0x1403fb52c`
- `watchdog!WdLogSingleEntry1` at `0x1403faf6a`
- `watchdog!WdLogSingleEntry1` at `0x1403fafbc`
- `watchdog!WdLogSingleEntry1` at `0x1403fb05f`
- `watchdog!WdLogSingleEntry1` at `0x1403fb0ff`
- `watchdog!WdLogSingleEntry1` at `0x1403fb1f2`
- `watchdog!WdLogSingleEntry1` at `0x1403fb236`
- `watchdog!WdLogSingleEntry1` at `0x1403fb27d`
- `watchdog!WdLogSingleEntry1` at `0x1403fb451`
- `watchdog!WdLogSingleEntry1` at `0x1403fb4bc`
- `watchdog!WdLogSingleEntry1` at `0x1403fb52c`

## pseudocode

```c
__int64 __fastcall DpiPdoAddPdo(
        __int64 a1,
        __int64 a2,
        enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY a3,
        char a4,
        char a5,
        BOOLEAN a6,
        struct _DXGK_CONNECTION_USB4_INFO *a7,
        unsigned __int8 *a8,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a9)
{
  __int64 v9; // r14
  PVOID DeviceExtension; // rdi
  _QWORD *v12; // r9
  _QWORD *v14; // rax
  char v15; // r13
  NTSTATUS DeviceIdFromDescriptor; // esi
  int DeviceDescriptor; // eax
  void *v18; // r12
  const void *v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rbx
  GUID *DeviceClassGuid; // rdx
  PDEVICE_OBJECT v24; // rax
  __int64 Pool2; // rax
  PIO_WORKITEM WorkItem; // rax
  _QWORD *v27; // rax
  unsigned __int8 v28; // al
  _QWORD *v29; // rax
  PVOID *v30; // rcx
  struct _IO_WORKITEM *v31; // rcx
  void *v32; // rcx
  BOOLEAN Exclusive; // [rsp+28h] [rbp-48h]
  char v35; // [rsp+50h] [rbp-20h]
  char v36; // [rsp+51h] [rbp-1Fh]
  char v37; // [rsp+52h] [rbp-1Eh]
  PDEVICE_OBJECT DeviceObject; // [rsp+58h] [rbp-18h] BYREF
  void *Source1[2]; // [rsp+60h] [rbp-10h] BYREF

  v9 = *(_QWORD *)(a1 + 64);
  DeviceExtension = 0;
  DeviceObject = 0;
  v36 = 0;
  v37 = 0;
  v12 = *(_QWORD **)(v9 + 3784);
  v14 = v12;
  v35 = 0;
  v15 = 0;
  *(_OWORD *)Source1 = 0;
  while ( 1 )
  {
    if ( (_QWORD *)*v14 == v12 )
      goto LABEL_7;
    DeviceExtension = v14;
    if ( *((_DWORD *)v14 + 126) == *(_DWORD *)(a2 + 24) )
      break;
    v14 = (_QWORD *)*v14;
  }
  DeviceObject = (PDEVICE_OBJECT)v14[3];
  v36 = 1;
  if ( a5 )
  {
LABEL_7:
    LOBYTE(v12) = a4;
    DeviceDescriptor = DpiPdoGetDeviceDescriptor(a1, a2, a3, (_DWORD)v12, a5, a6);
    DeviceIdFromDescriptor = DeviceDescriptor;
    if ( DeviceDescriptor >= 0 )
    {
      if ( DeviceDescriptor == 259 )
      {
        v18 = Source1[1];
        goto LABEL_75;
      }
    }
    else
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 235;
      if ( *(_DWORD *)a2 != 1 )
        goto LABEL_49;
    }
    v18 = Source1[1];
    if ( v36 != 1 )
    {
      v22 = a1;
LABEL_23:
      DeviceClassGuid = &GUID_DEVCLASS_MONITOR;
      if ( *(_DWORD *)a2 != 1 )
        DeviceClassGuid = &GUID_SD_PDO;
      DeviceIdFromDescriptor = WdmlibIoCreateDeviceSecure(
                                 *(PDRIVER_OBJECT *)(*(_QWORD *)(v9 + 40) + 32LL),
                                 0x408u,
                                 0,
                                 0x1Cu,
                                 0x180u,
                                 Exclusive,
                                 &SDDL_DEVOBJ_SYS_ALL_ADM_ALL,
                                 DeviceClassGuid,
                                 &DeviceObject);
      if ( DeviceIdFromDescriptor < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 371;
        goto LABEL_51;
      }
      v37 = 1;
      DeviceExtension = DeviceObject->DeviceExtension;
      *((_DWORD *)DeviceExtension + 4) = 1953656900;
      *((_DWORD *)DeviceExtension + 5) = 5;
      v24 = DeviceObject;
      *((_QWORD *)DeviceExtension + 4) = v22;
      *((_QWORD *)DeviceExtension + 3) = v24;
      *((_QWORD *)DeviceExtension + 5) = *(_QWORD *)(v9 + 40);
      *((_QWORD *)DeviceExtension + 6) = *(_QWORD *)(v9 + 48);
      *((_BYTE *)DeviceExtension + 56) = 1;
      *((_DWORD *)DeviceExtension + 70) = 1;
      LODWORD(v24) = *(_DWORD *)(a2 + 68);
      *((_DWORD *)DeviceExtension + 71) = (_DWORD)v24;
      KeInitializeEvent((PRKEVENT)DeviceExtension + 41, NotificationEvent, (_DWORD)v24 != 1);
      KeInitializeEvent((PRKEVENT)DeviceExtension + 42, NotificationEvent, *((_DWORD *)DeviceExtension + 71) == 1);
      IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, 0x74727044u, 1u, 0, 0x20u);
      Pool2 = ExAllocatePool2(64, 112, 1953656900);
      *((_QWORD *)DeviceExtension + 21) = Pool2;
      if ( !Pool2 )
      {
        DeviceIdFromDescriptor = -1073741801;
        WdLogSingleEntry1(6);
        WdLogGlobalForLineNumber = 433;
        goto LABEL_51;
      }
      *(_DWORD *)(Pool2 + 104) = 1;
      DeviceIdFromDescriptor = ExInitializeResourceLite(*((PERESOURCE *)DeviceExtension + 21));
      if ( DeviceIdFromDescriptor < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 446;
        goto LABEL_51;
      }
      v35 = 1;
      WorkItem = IoAllocateWorkItem(DeviceObject);
      *((_QWORD *)DeviceExtension + 119) = WorkItem;
      if ( !WorkItem )
      {
        DeviceIdFromDescriptor = -1073741801;
        WdLogSingleEntry1(6);
        WdLogGlobalForLineNumber = 465;
        goto LABEL_51;
      }
      *((_QWORD *)DeviceExtension + 14) = &DpiPdoDispatchInternalIoctl;
      *((_QWORD *)DeviceExtension + 16) = DpiPdoDispatchPnp;
      *((_QWORD *)DeviceExtension + 17) = DpiPdoDispatchPower;
      *((_QWORD *)DeviceExtension + 15) = &DpiPdoDispatchIoctl;
      *((_QWORD *)DeviceExtension + 36) = DpiPdoHandleStartDevice;
      *((_QWORD *)DeviceExtension + 40) = DpiPdoHandleStopDevice;
      *((_QWORD *)DeviceExtension + 45) = DpiPdoHandleQueryCapabilities;
      *((_QWORD *)DeviceExtension + 55) = DpiPdoHandleQueryId;
      *((_QWORD *)DeviceExtension + 43) = DpiPdoHandleQueryDeviceRelations;
      *((_QWORD *)DeviceExtension + 48) = DpiPdoHandleQueryDeviceText;
      *((_QWORD *)DeviceExtension + 57) = DpiPdoHandleQueryBusInformation;
      v15 = 1;
      *((_QWORD *)DeviceExtension + 117) = a2;
      *((_DWORD *)DeviceExtension + 124) = *(_DWORD *)a2;
      *((_DWORD *)DeviceExtension + 125) = *(_DWORD *)(a2 + 20);
      *((_DWORD *)DeviceExtension + 126) = *(_DWORD *)(a2 + 24);
      *((_WORD *)DeviceExtension + 254) = 1;
      *((_BYTE *)DeviceExtension + 511) = 0;
      if ( a3 != D3DKMDT_VOT_UNINITIALIZED )
        *((_DWORD *)DeviceExtension + 244) = a3;
      *((_DWORD *)DeviceExtension + 245) = 0;
      KeWaitForSingleObject((PVOID)(v9 + 3544), Executive, 0, 0, 0);
      *(_QWORD *)(a2 + 48) = DeviceObject;
      KeReleaseMutex((PRKMUTEX)(v9 + 3544), 0);
      if ( (unsigned int)Feature_ForceConnectionDetectionOnDcToAc__private_IsEnabledDeviceUsageNoInline() )
      {
        DpiFdoAddPdoToPdoList(v9, DeviceExtension);
      }
      else
      {
        v27 = *(_QWORD **)(v9 + 3792);
        if ( *v27 != v9 + 3784 )
          goto LABEL_62;
        *(_QWORD *)DeviceExtension = v9 + 3784;
        *((_QWORD *)DeviceExtension + 1) = v27;
        *v27 = DeviceExtension;
        *(_QWORD *)(v9 + 3792) = DeviceExtension;
        ++*(_DWORD *)(v9 + 3800);
        if ( *((_DWORD *)DeviceExtension + 124) != 1 )
        {
LABEL_45:
          DeviceIdFromDescriptor = DpiPdoGetDeviceIdFromDescriptor(DeviceObject, Source1);
          if ( DeviceIdFromDescriptor < 0 )
          {
            if ( *((_DWORD *)DeviceExtension + 124) != 1 )
              goto LABEL_50;
            DeviceIdFromDescriptor = 0;
          }
          DpiPdoGetDeviceContainerIdFromDescriptor(DeviceObject);
          _InterlockedAdd((volatile signed __int32 *)(a2 + 56), 1u);
          DeviceObject->Flags |= 4u;
          DeviceObject->Flags |= 0x2000u;
          DeviceObject->Flags &= ~0x4000u;
          DeviceObject->Flags &= ~0x80u;
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 644;
LABEL_49:
          v15 = v35;
          if ( DeviceIdFromDescriptor == 259 )
          {
            v18 = Source1[1];
            goto LABEL_54;
          }
          goto LABEL_50;
        }
        ++*(_DWORD *)(v9 + 3804);
      }
      if ( *((_DWORD *)DeviceExtension + 124) == 1 )
      {
        DeviceIdFromDescriptor = DmmSetTemporaryVideoOutputTechnology(
                                   *(void *const *)(v9 + 4032),
                                   *((_DWORD *)DeviceExtension + 126),
                                   a3,
                                   (enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY)(a7 != 0
                                                                         ? D3DKMDT_VOT_RF|D3DKMDT_VOT_INDIRECT_WIRED
                                                                         : D3DKMDT_VOT_UNINITIALIZED));
        if ( DeviceIdFromDescriptor < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 562;
          goto LABEL_51;
        }
        v28 = IsInternalVideoOutput(*(enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)(a2 + 4));
        DeviceIdFromDescriptor = MonitorCreatePhysicalMonitor(
                                   *(void **)(v9 + 4032),
                                   *((_DWORD *)DeviceExtension + 126),
                                   DeviceObject,
                                   v28,
                                   1,
                                   a7,
                                   a8,
                                   a9);
        if ( DeviceIdFromDescriptor < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 580;
          goto LABEL_51;
        }
      }
      goto LABEL_45;
    }
    if ( Source1[1] != *((void **)DeviceExtension + 116) )
    {
      if ( !IsInternalVideoOutput(*(enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)(a2 + 4)) )
        goto LABEL_16;
      if ( Source1[1] )
        goto LABEL_17;
      if ( !v19 )
      {
LABEL_16:
        if ( !Source1[1] )
        {
LABEL_21:
          *((_BYTE *)DeviceExtension + 511) = 1;
          WdLogSingleEntry1(4);
          LOBYTE(v21) = 1;
          v22 = a1;
          WdLogGlobalForLineNumber = 329;
          DpiPdoRemovePdo(a1, a2, v21, a8, a9);
          goto LABEL_23;
        }
LABEL_17:
        if ( v19 )
        {
          v20 = *((_DWORD *)DeviceExtension + 231);
          if ( HIDWORD(Source1[0]) == v20 && RtlCompareMemory(Source1[1], v19, v20) == HIDWORD(Source1[0]) )
            goto LABEL_20;
        }
        goto LABEL_21;
      }
    }
LABEL_20:
    DeviceIdFromDescriptor = 0x40000000;
    goto LABEL_51;
  }
  DeviceIdFromDescriptor = 0x40000000;
  WdLogSingleEntry1(4);
  WdLogGlobalForLineNumber = 206;
LABEL_50:
  v18 = Source1[1];
LABEL_51:
  if ( *(_BYTE *)(a2 + 64) == 1 )
  {
    KeWaitForSingleObject((PVOID)(v9 + 3544), Executive, 0, 0, 0);
    DpiFdoPendingCreatePdoCompletion(a1, a2);
    KeReleaseMutex((PRKMUTEX)(v9 + 3544), 0);
  }
LABEL_54:
  if ( DeviceIdFromDescriptor >= 0 || v37 != 1 )
    goto LABEL_75;
  if ( v15 == 1 )
  {
    if ( !(unsigned int)Feature_ForceConnectionDetectionOnDcToAc__private_IsEnabledDeviceUsageNoInline() )
    {
      v29 = *(_QWORD **)DeviceExtension;
      if ( *(PVOID *)(*(_QWORD *)DeviceExtension + 8LL) == DeviceExtension )
      {
        v30 = (PVOID *)*((_QWORD *)DeviceExtension + 1);
        if ( *v30 == DeviceExtension )
        {
          *v30 = v29;
          v29[1] = v30;
          --*(_DWORD *)(v9 + 3800);
          if ( *((_DWORD *)DeviceExtension + 124) == 1 )
            --*(_DWORD *)(v9 + 3804);
          goto LABEL_64;
        }
      }
LABEL_62:
      __fastfail(3u);
    }
    DpiFdoRemovePdoFromPdoList(v9, DeviceExtension);
  }
LABEL_64:
  KeWaitForSingleObject((PVOID)(v9 + 3544), Executive, 0, 0, 0);
  *(_QWORD *)(a2 + 48) = 0;
  KeReleaseMutex((PRKMUTEX)(v9 + 3544), 0);
  *((_QWORD *)DeviceExtension + 117) = 0;
  if ( *((_QWORD *)DeviceExtension + 121) )
    RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 60);
  if ( v35 == 1 )
    ExDeleteResourceLite(*((PERESOURCE *)DeviceExtension + 21));
  v31 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 119);
  if ( v31 )
    IoFreeWorkItem(v31);
  v32 = (void *)*((_QWORD *)DeviceExtension + 21);
  if ( v32 )
  {
    ExFreePoolWithTag(v32, 0);
    *((_QWORD *)DeviceExtension + 21) = 0;
  }
  if ( DeviceObject )
  {
    IoDeleteDevice(DeviceObject);
    DeviceObject = 0;
  }
LABEL_75:
  if ( v18 )
    ExFreePoolWithTag(v18, 0);
  return (unsigned int)DeviceIdFromDescriptor;
}

```

## disassembly

```asm
0x1403faed4  mov     [rsp-38h+arg_8], rbx
0x1403faed9  mov     [rsp-38h+arg_10], r8d
0x1403faede  mov     [rsp-38h+arg_0], rcx
0x1403faee3  push    rbp
0x1403faee4  push    rsi
0x1403faee5  push    rdi
0x1403faee6  push    r12
0x1403faee8  push    r13
0x1403faeea  push    r14
0x1403faeec  push    r15
0x1403faeee  mov     rbp, rsp
0x1403faef1  sub     rsp, 70h
0x1403faef5  mov     r14, [rcx+40h]
0x1403faef9  xor     edi, edi
0x1403faefb  mov     r10b, r9b
0x1403faefe  mov     [rbp+var_18], 0
0x1403faf06  xorps   xmm0, xmm0
0x1403faf09  mov     [rbp+var_1F], 0
0x1403faf0d  mov     r11d, r8d
0x1403faf10  mov     [rbp+var_1E], dil
0x1403faf14  mov     r9, [r14+0EC8h]
0x1403faf1b  mov     r15, rdx
0x1403faf1e  mov     rax, r9
0x1403faf21  mov     [rbp+var_20], dil
0x1403faf25  mov     rbx, rcx
0x1403faf28  xor     r13b, r13b
0x1403faf2b  movups  xmmword ptr [rbp+Source1], xmm0
0x1403faf2f  mov     rcx, [rax]
0x1403faf32  mov     r8b, [rbp+arg_20]
0x1403faf36  cmp     rcx, r9
0x1403faf39  jz      short loc_1403FAF85
0x1403faf3b  mov     edx, [r15+18h]
0x1403faf3f  mov     rdi, rax
0x1403faf42  cmp     [rax+1F8h], edx
0x1403faf48  jz      short loc_1403FAF4F
0x1403faf4a  mov     rax, rcx
0x1403faf4d  jmp     short loc_1403FAF2F
0x1403faf4f  mov     rax, [rax+18h]
0x1403faf53  mov     [rbp+var_18], rax
0x1403faf57  mov     [rbp+var_1F], 1
0x1403faf5b  test    r8b, r8b
0x1403faf5e  jnz     short loc_1403FAF85
0x1403faf60  mov     esi, 40000000h
0x1403faf65  mov     ecx, 4
0x1403faf6a  call    cs:__imp_WdLogSingleEntry1
0x1403faf71  nop     dword ptr [rax+rax+00h]
0x1403faf76  mov     cs:WdLogGlobalForLineNumber, 0CEh
0x1403faf80  jmp     loc_1403FB54E
0x1403faf85  lea     rax, [rbp+Source1]
0x1403faf89  mov     r9b, r10b
0x1403faf8c  mov     [rsp+70h+DeviceClassGuid], rax
0x1403faf91  mov     rdx, r15
0x1403faf94  mov     al, [rbp+arg_28]
0x1403faf97  mov     rcx, rbx
0x1403faf9a  mov     [rsp+70h+Exclusive], al; Exclusive
0x1403faf9e  mov     byte ptr [rsp+70h+DeviceCharacteristics], r8b
0x1403fafa3  mov     r8d, r11d
0x1403fafa6  call    DpiPdoGetDeviceDescriptor
0x1403fafab  mov     esi, eax
0x1403fafad  mov     ebx, 4
0x1403fafb2  test    eax, eax
0x1403fafb4  jns     short loc_1403FAFDD
0x1403fafb6  mov     edx, [r15+18h]
0x1403fafba  mov     ecx, ebx
0x1403fafbc  call    cs:__imp_WdLogSingleEntry1
0x1403fafc3  nop     dword ptr [rax+rax+00h]
0x1403fafc8  mov     cs:WdLogGlobalForLineNumber, 0EBh
0x1403fafd2  cmp     dword ptr [r15], 1
0x1403fafd6  jz      short loc_1403FAFE8
0x1403fafd8  jmp     loc_1403FB542
0x1403fafdd  cmp     eax, 103h
0x1403fafe2  jz      loc_1403FB6E5
0x1403fafe8  cmp     [rbp+var_1F], 1
0x1403fafec  mov     r12, [rbp+Source1+8]
0x1403faff0  jnz     loc_1403FB099
0x1403faff6  mov     rdx, [rdi+3A0h]
0x1403faffd  cmp     r12, rdx
0x1403fb000  jz      short loc_1403FB048
0x1403fb002  mov     ecx, [r15+4]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
0x1403fb006  call    ?IsInternalVideoOutput@@YAEW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@@Z; IsInternalVideoOutput(_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY)
0x1403fb00b  test    al, al
0x1403fb00d  jz      short loc_1403FB019
0x1403fb00f  test    r12, r12
0x1403fb012  jnz     short loc_1403FB01E
0x1403fb014  test    rdx, rdx
0x1403fb017  jnz     short loc_1403FB048
0x1403fb019  test    r12, r12
0x1403fb01c  jz      short loc_1403FB052
0x1403fb01e  test    rdx, rdx
0x1403fb021  jz      short loc_1403FB052
0x1403fb023  mov     eax, [rdi+39Ch]
0x1403fb029  cmp     dword ptr [rbp+Source1+4], eax
0x1403fb02c  jnz     short loc_1403FB052
0x1403fb02e  mov     r8d, eax; Length
0x1403fb031  mov     rcx, r12; Source1
0x1403fb034  call    cs:__imp_RtlCompareMemory
0x1403fb03b  nop     dword ptr [rax+rax+00h]
0x1403fb040  mov     ecx, dword ptr [rbp+Source1+4]
0x1403fb043  cmp     rax, rcx
0x1403fb046  jnz     short loc_1403FB052
0x1403fb048  mov     esi, 40000000h
0x1403fb04d  jmp     loc_1403FB552
0x1403fb052  mov     byte ptr [rdi+1FFh], 1
0x1403fb059  mov     rdx, [rbp+var_18]
0x1403fb05d  mov     ecx, ebx
0x1403fb05f  call    cs:__imp_WdLogSingleEntry1
0x1403fb066  nop     dword ptr [rax+rax+00h]
0x1403fb06b  mov     rax, [rbp+arg_40]
0x1403fb072  mov     r8b, 1
0x1403fb075  mov     rbx, [rbp+arg_0]
0x1403fb079  mov     rdx, r15
0x1403fb07c  mov     r9, [rbp+arg_38]
0x1403fb080  mov     rcx, rbx
0x1403fb083  mov     qword ptr [rsp+70h+DeviceCharacteristics], rax
0x1403fb088  mov     cs:WdLogGlobalForLineNumber, 149h
0x1403fb092  call    DpiPdoRemovePdo
0x1403fb097  jmp     short loc_1403FB09D
0x1403fb099  mov     rbx, [rbp+arg_0]
0x1403fb09d  cmp     dword ptr [r15], 1
0x1403fb0a1  lea     rcx, GUID_SD_PDO
0x1403fb0a8  lea     rax, [rbp+var_18]
0x1403fb0ac  mov     r9d, 1Ch; DeviceType
0x1403fb0b2  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1403fb0b7  lea     rdx, GUID_DEVCLASS_MONITOR
0x1403fb0be  cmovnz  rdx, rcx
0x1403fb0c2  lea     rax, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x1403fb0c9  mov     rcx, [r14+28h]
0x1403fb0cd  xor     r8d, r8d; DeviceName
0x1403fb0d0  mov     [rsp+70h+DeviceClassGuid], rdx; DeviceClassGuid
0x1403fb0d5  mov     edx, 408h; DeviceExtensionSize
0x1403fb0da  mov     [rsp+70h+DefaultSDDLString], rax; DefaultSDDLString
0x1403fb0df  mov     [rsp+70h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x1403fb0e7  mov     rcx, [rcx+20h]; DriverObject
0x1403fb0eb  call    WdmlibIoCreateDeviceSecure
0x1403fb0f0  movsxd  rsi, eax
0x1403fb0f3  test    eax, eax
0x1403fb0f5  jns     short loc_1403FB11A
0x1403fb0f7  mov     rdx, rsi
0x1403fb0fa  mov     ecx, 2
0x1403fb0ff  call    cs:__imp_WdLogSingleEntry1
0x1403fb106  nop     dword ptr [rax+rax+00h]
0x1403fb10b  mov     cs:WdLogGlobalForLineNumber, 173h
0x1403fb115  jmp     loc_1403FB552
0x1403fb11a  mov     rax, [rbp+var_18]
0x1403fb11e  mov     esi, 74727044h
0x1403fb123  mov     [rbp+var_1E], 1
0x1403fb127  mov     rdi, [rax+40h]
0x1403fb12b  mov     [rdi+10h], esi
0x1403fb12e  lea     rcx, [rdi+3D8h]; Event
0x1403fb135  mov     dword ptr [rdi+14h], 5
0x1403fb13c  mov     rax, [rbp+var_18]
0x1403fb140  mov     [rdi+20h], rbx
0x1403fb144  mov     ebx, 1
0x1403fb149  mov     [rdi+18h], rax
0x1403fb14d  mov     rax, [r14+28h]
0x1403fb151  mov     [rdi+28h], rax
0x1403fb155  mov     rax, [r14+30h]
0x1403fb159  mov     [rdi+30h], rax
0x1403fb15d  mov     [rdi+38h], bl
0x1403fb160  mov     [rdi+118h], ebx
0x1403fb166  mov     eax, [r15+44h]
0x1403fb16a  cmp     eax, ebx
0x1403fb16c  mov     [rdi+11Ch], eax
0x1403fb172  setnz   r8b; State
0x1403fb176  xor     edx, edx; Type
0x1403fb178  call    cs:__imp_KeInitializeEvent
0x1403fb17f  nop     dword ptr [rax+rax+00h]
0x1403fb184  cmp     [rdi+11Ch], ebx
0x1403fb18a  lea     rcx, [rdi+3F0h]; Event
0x1403fb191  setz    r8b; State
0x1403fb195  xor     edx, edx; Type
0x1403fb197  call    cs:__imp_KeInitializeEvent
0x1403fb19e  nop     dword ptr [rax+rax+00h]
0x1403fb1a3  lea     rcx, [rdi+40h]; Lock
0x1403fb1a7  mov     [rsp+70h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x1403fb1af  xor     r9d, r9d; HighWatermark
0x1403fb1b2  mov     r8d, ebx; MaxLockedMinutes
0x1403fb1b5  mov     edx, esi; AllocateTag
0x1403fb1b7  call    cs:__imp_IoInitializeRemoveLockEx
0x1403fb1be  nop     dword ptr [rax+rax+00h]
0x1403fb1c3  mov     r8d, esi
0x1403fb1c6  lea     edx, [rbx+6Fh]
0x1403fb1c9  lea     ecx, [rbx+3Fh]
0x1403fb1cc  call    cs:__imp_ExAllocatePool2
0x1403fb1d3  nop     dword ptr [rax+rax+00h]
0x1403fb1d8  xor     ebx, ebx
0x1403fb1da  mov     [rdi+0A8h], rax
0x1403fb1e1  test    rax, rax
0x1403fb1e4  jnz     short loc_1403FB20D
0x1403fb1e6  mov     rdx, 0FFFFFFFFC0000017h
0x1403fb1ed  mov     esi, edx
0x1403fb1ef  lea     ecx, [rax+6]
0x1403fb1f2  call    cs:__imp_WdLogSingleEntry1
0x1403fb1f9  nop     dword ptr [rax+rax+00h]
0x1403fb1fe  mov     cs:WdLogGlobalForLineNumber, 1B1h
0x1403fb208  jmp     loc_1403FB552
0x1403fb20d  mov     dword ptr [rax+68h], 1
0x1403fb214  mov     rcx, [rdi+0A8h]; Resource
0x1403fb21b  call    cs:__imp_ExInitializeResourceLite
0x1403fb222  nop     dword ptr [rax+rax+00h]
0x1403fb227  movsxd  rsi, eax
0x1403fb22a  test    eax, eax
0x1403fb22c  jns     short loc_1403FB251
0x1403fb22e  mov     rdx, rsi
0x1403fb231  mov     ecx, 2
0x1403fb236  call    cs:__imp_WdLogSingleEntry1
0x1403fb23d  nop     dword ptr [rax+rax+00h]
0x1403fb242  mov     cs:WdLogGlobalForLineNumber, 1BEh
0x1403fb24c  jmp     loc_1403FB552
0x1403fb251  mov     rcx, [rbp+var_18]; DeviceObject
0x1403fb255  mov     [rbp+var_20], 1
0x1403fb259  call    cs:__imp_IoAllocateWorkItem
0x1403fb260  nop     dword ptr [rax+rax+00h]
0x1403fb265  mov     [rdi+3B8h], rax
0x1403fb26c  test    rax, rax
0x1403fb26f  jnz     short loc_1403FB298
0x1403fb271  mov     rdx, 0FFFFFFFFC0000017h
0x1403fb278  mov     esi, edx
0x1403fb27a  lea     ecx, [rax+6]
0x1403fb27d  call    cs:__imp_WdLogSingleEntry1
0x1403fb284  nop     dword ptr [rax+rax+00h]
0x1403fb289  mov     cs:WdLogGlobalForLineNumber, 1D1h
0x1403fb293  jmp     loc_1403FB552
0x1403fb298  mov     esi, [rbp+arg_10]
0x1403fb29b  lea     rax, DpiPdoDispatchInternalIoctl
0x1403fb2a2  mov     [rdi+70h], rax
0x1403fb2a6  lea     rax, DpiPdoDispatchPnp
0x1403fb2ad  mov     [rdi+80h], rax
0x1403fb2b4  lea     rax, DpiPdoDispatchPower
0x1403fb2bb  mov     [rdi+88h], rax
0x1403fb2c2  lea     rax, DpiPdoDispatchIoctl
0x1403fb2c9  mov     [rdi+78h], rax
0x1403fb2cd  lea     rax, DpiPdoHandleStartDevice
0x1403fb2d4  mov     [rdi+120h], rax
0x1403fb2db  lea     rax, DpiPdoHandleStopDevice
0x1403fb2e2  mov     [rdi+140h], rax
0x1403fb2e9  lea     rax, DpiPdoHandleQueryCapabilities
0x1403fb2f0  mov     [rdi+168h], rax
0x1403fb2f7  lea     rax, DpiPdoHandleQueryId
0x1403fb2fe  mov     [rdi+1B8h], rax
0x1403fb305  lea     rax, DpiPdoHandleQueryDeviceRelations
0x1403fb30c  mov     [rdi+158h], rax
0x1403fb313  lea     rax, DpiPdoHandleQueryDeviceText
0x1403fb31a  mov     [rdi+180h], rax
0x1403fb321  lea     rax, DpiPdoHandleQueryBusInformation
0x1403fb328  mov     [rdi+1C8h], rax
0x1403fb32f  mov     r13d, 1
0x1403fb335  mov     [rdi+3A8h], r15
0x1403fb33c  mov     eax, [r15]
0x1403fb33f  mov     [rdi+1F0h], eax
0x1403fb345  mov     eax, [r15+14h]
0x1403fb349  mov     [rdi+1F4h], eax
0x1403fb34f  mov     eax, [r15+18h]
0x1403fb353  mov     [rdi+1F8h], eax
0x1403fb359  mov     [rdi+1FCh], r13w
0x1403fb361  mov     [rdi+1FFh], bl
0x1403fb367  cmp     esi, 0FFFFFFFEh
0x1403fb36a  jz      short loc_1403FB372
0x1403fb36c  mov     [rdi+3D0h], esi
0x1403fb372  mov     [rdi+3D4h], ebx
0x1403fb378  xor     r9d, r9d; Alertable
0x1403fb37b  lea     rbx, [r14+0DD8h]
0x1403fb382  mov     qword ptr [rsp+70h+DeviceCharacteristics], 0; Timeout
0x1403fb38b  mov     rcx, rbx; Object
0x1403fb38e  xor     r8d, r8d; WaitMode
0x1403fb391  xor     edx, edx; WaitReason
0x1403fb393  call    cs:__imp_KeWaitForSingleObject
0x1403fb39a  nop     dword ptr [rax+rax+00h]
0x1403fb39f  mov     rax, [rbp+var_18]
0x1403fb3a3  xor     edx, edx; Wait
0x1403fb3a5  mov     rcx, rbx; Mutex
0x1403fb3a8  mov     [r15+30h], rax
0x1403fb3ac  call    cs:__imp_KeReleaseMutex
0x1403fb3b3  nop     dword ptr [rax+rax+00h]
0x1403fb3b8  call    Feature_ForceConnectionDetectionOnDcToAc__private_IsEnabledDeviceUsageNoInline
0x1403fb3bd  test    eax, eax
0x1403fb3bf  jnz     short loc_1403FB400
0x1403fb3c1  lea     rcx, [r14+0EC8h]
0x1403fb3c8  mov     rax, [rcx+8]
0x1403fb3cc  cmp     [rax], rcx
0x1403fb3cf  jnz     loc_1403FB5F9
0x1403fb3d5  mov     [rdi], rcx
0x1403fb3d8  mov     [rdi+8], rax
0x1403fb3dc  mov     [rax], rdi
0x1403fb3df  mov     [rcx+8], rdi
0x1403fb3e3  add     [r14+0ED8h], r13d
0x1403fb3ea  cmp     [rdi+1F0h], r13d
0x1403fb3f1  jnz     loc_1403FB4D4
0x1403fb3f7  add     [r14+0EDCh], r13d
0x1403fb3fe  jmp     short loc_1403FB40B
0x1403fb400  mov     rdx, rdi
0x1403fb403  mov     rcx, r14
0x1403fb406  call    DpiFdoAddPdoToPdoList
0x1403fb40b  cmp     [rdi+1F0h], r13d
0x1403fb412  jnz     loc_1403FB4D4
0x1403fb418  mov     rbx, [rbp+arg_30]
0x1403fb41c  mov     r8d, esi; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
0x1403fb41f  mov     edx, [rdi+1F8h]; unsigned int
0x1403fb425  mov     rax, rbx
0x1403fb428  mov     rcx, [r14+0FC0h]; void *
  ... truncated ...
```
