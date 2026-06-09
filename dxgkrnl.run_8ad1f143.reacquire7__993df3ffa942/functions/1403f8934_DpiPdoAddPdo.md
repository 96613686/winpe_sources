# DpiPdoAddPdo

- ea: `0x1403f8934`
- end: `0x1403f917a`
- name: `DpiPdoAddPdo`
- size: `2118`
- prototype: `__int64 __fastcall(int, int, int, int, char, BOOLEAN, struct _DXGK_CONNECTION_USB4_INFO *, unsigned __int8 *, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140411a64`

## callees

- `0x1400456cc`
- `0x14005caec`
- `0x14018cfe0`
- `0x1401af2ac`
- `0x1401af570`
- `0x1402a9170`
- `0x1402b834c`
- `0x1402c4b90`
- `0x1402c4fbc`
- `0x1402ceb4c`
- `0x1403f8934`
- `0x1403f9180`
- `0x140401d58`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403f910f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403f9153`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403f910f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403f9153`
- `ntoskrnl!IoFreeWorkItem` at `0x1403f90f5`
- `ntoskrnl!IoFreeWorkItem` at `0x1403f90f5`
- `ntoskrnl!ExAllocatePool2` at `0x1403f8c2c`
- `ntoskrnl!ExAllocatePool2` at `0x1403f8c2c`
- `ntoskrnl!KeInitializeEvent` at `0x1403f8bd8`
- `ntoskrnl!KeInitializeEvent` at `0x1403f8bf7`
- `ntoskrnl!KeInitializeEvent` at `0x1403f8bd8`
- `ntoskrnl!KeInitializeEvent` at `0x1403f8bf7`
- `ntoskrnl!ExDeleteResourceLite` at `0x1403f90dd`
- `ntoskrnl!ExDeleteResourceLite` at `0x1403f90dd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1403f90c4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1403f90c4`
- `ntoskrnl!ExInitializeResourceLite` at `0x1403f8c7b`
- `ntoskrnl!ExInitializeResourceLite` at `0x1403f8c7b`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403f8cb9`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403f8cb9`
- `ntoskrnl!RtlCompareMemory` at `0x1403f8a94`
- `ntoskrnl!RtlCompareMemory` at `0x1403f8a94`
- `ntoskrnl!IoDeleteDevice` at `0x1403f912f`
- `ntoskrnl!IoDeleteDevice` at `0x1403f912f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f8df3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f8fd4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f9086`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f8df3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f8fd4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f9086`
- `ntoskrnl!KeReleaseMutex` at `0x1403f8e0c`
- `ntoskrnl!KeReleaseMutex` at `0x1403f8ff1`
- `ntoskrnl!KeReleaseMutex` at `0x1403f909f`
- `ntoskrnl!KeReleaseMutex` at `0x1403f8e0c`
- `ntoskrnl!KeReleaseMutex` at `0x1403f8ff1`
- `ntoskrnl!KeReleaseMutex` at `0x1403f909f`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1403f8c17`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1403f8c17`
- `watchdog!WdLogSingleEntry1` at `0x1403f89ca`
- `watchdog!WdLogSingleEntry1` at `0x1403f8a1c`
- `watchdog!WdLogSingleEntry1` at `0x1403f8abf`
- `watchdog!WdLogSingleEntry1` at `0x1403f8b5f`
- `watchdog!WdLogSingleEntry1` at `0x1403f8c52`
- `watchdog!WdLogSingleEntry1` at `0x1403f8c96`
- `watchdog!WdLogSingleEntry1` at `0x1403f8cdd`
- `watchdog!WdLogSingleEntry1` at `0x1403f8eb1`
- `watchdog!WdLogSingleEntry1` at `0x1403f8f1c`
- `watchdog!WdLogSingleEntry1` at `0x1403f8f8c`
- `watchdog!WdLogSingleEntry1` at `0x1403f89ca`
- `watchdog!WdLogSingleEntry1` at `0x1403f8a1c`
- `watchdog!WdLogSingleEntry1` at `0x1403f8abf`
- `watchdog!WdLogSingleEntry1` at `0x1403f8b5f`
- `watchdog!WdLogSingleEntry1` at `0x1403f8c52`
- `watchdog!WdLogSingleEntry1` at `0x1403f8c96`
- `watchdog!WdLogSingleEntry1` at `0x1403f8cdd`
- `watchdog!WdLogSingleEntry1` at `0x1403f8eb1`
- `watchdog!WdLogSingleEntry1` at `0x1403f8f1c`
- `watchdog!WdLogSingleEntry1` at `0x1403f8f8c`

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
  __int64 v16; // rdx
  int DeviceIdFromDescriptor; // esi
  int DeviceDescriptor; // eax
  void *v19; // r12
  const void *v20; // rdx
  unsigned int v21; // eax
  SIZE_T v22; // rax
  __int64 v23; // r8
  __int64 v24; // rbx
  GUID *DeviceClassGuid; // rdx
  NTSTATUS v26; // eax
  PDEVICE_OBJECT v27; // rax
  __int64 Pool2; // rax
  NTSTATUS v29; // eax
  PIO_WORKITEM WorkItem; // rax
  _QWORD *v31; // rax
  int v32; // eax
  unsigned __int8 v33; // al
  int PhysicalMonitor; // eax
  _QWORD *v35; // rax
  PVOID *v36; // rcx
  struct _IO_WORKITEM *v37; // rcx
  void *v38; // rcx
  BOOLEAN Exclusive; // [rsp+28h] [rbp-48h]
  int DefaultSDDLString; // [rsp+30h] [rbp-40h]
  char v42; // [rsp+50h] [rbp-20h]
  char v43; // [rsp+51h] [rbp-1Fh]
  char v44; // [rsp+52h] [rbp-1Eh]
  PDEVICE_OBJECT DeviceObject; // [rsp+58h] [rbp-18h] BYREF
  void *Source1[2]; // [rsp+60h] [rbp-10h] BYREF

  v9 = *(_QWORD *)(a1 + 64);
  DeviceExtension = 0;
  DeviceObject = 0;
  v43 = 0;
  v44 = 0;
  v12 = *(_QWORD **)(v9 + 3784);
  v14 = v12;
  v42 = 0;
  v15 = 0;
  *(_OWORD *)Source1 = 0;
  while ( 1 )
  {
    if ( (_QWORD *)*v14 == v12 )
      goto LABEL_7;
    v16 = *(unsigned int *)(a2 + 24);
    DeviceExtension = v14;
    if ( *((_DWORD *)v14 + 126) == (_DWORD)v16 )
      break;
    v14 = (_QWORD *)*v14;
  }
  DeviceObject = (PDEVICE_OBJECT)v14[3];
  v43 = 1;
  if ( a5 )
  {
LABEL_7:
    DeviceDescriptor = DpiPdoGetDeviceDescriptor(a1, (int *)a2, a3, a4, a5, a6, DefaultSDDLString, Source1);
    DeviceIdFromDescriptor = DeviceDescriptor;
    if ( DeviceDescriptor >= 0 )
    {
      if ( DeviceDescriptor == 259 )
      {
        v19 = Source1[1];
        goto LABEL_75;
      }
    }
    else
    {
      WdLogSingleEntry1(4, *(unsigned int *)(a2 + 24));
      WdLogGlobalForLineNumber = 235;
      if ( *(_DWORD *)a2 != 1 )
        goto LABEL_49;
    }
    v19 = Source1[1];
    if ( v43 != 1 )
    {
      v24 = a1;
LABEL_23:
      DeviceClassGuid = &GUID_DEVCLASS_MONITOR;
      if ( *(_DWORD *)a2 != 1 )
        DeviceClassGuid = &GUID_SD_PDO;
      v26 = WdmlibIoCreateDeviceSecure(
              *(PDRIVER_OBJECT *)(*(_QWORD *)(v9 + 40) + 32LL),
              0x408u,
              0,
              0x1Cu,
              0x180u,
              Exclusive,
              &SDDL_DEVOBJ_SYS_ALL_ADM_ALL,
              DeviceClassGuid,
              &DeviceObject);
      DeviceIdFromDescriptor = v26;
      if ( v26 < 0 )
      {
        WdLogSingleEntry1(2, v26);
        WdLogGlobalForLineNumber = 371;
        goto LABEL_51;
      }
      v44 = 1;
      DeviceExtension = DeviceObject->DeviceExtension;
      *((_DWORD *)DeviceExtension + 4) = 1953656900;
      *((_DWORD *)DeviceExtension + 5) = 5;
      v27 = DeviceObject;
      *((_QWORD *)DeviceExtension + 4) = v24;
      *((_QWORD *)DeviceExtension + 3) = v27;
      *((_QWORD *)DeviceExtension + 5) = *(_QWORD *)(v9 + 40);
      *((_QWORD *)DeviceExtension + 6) = *(_QWORD *)(v9 + 48);
      *((_BYTE *)DeviceExtension + 56) = 1;
      *((_DWORD *)DeviceExtension + 70) = 1;
      LODWORD(v27) = *(_DWORD *)(a2 + 68);
      *((_DWORD *)DeviceExtension + 71) = (_DWORD)v27;
      KeInitializeEvent((PRKEVENT)DeviceExtension + 41, NotificationEvent, (_DWORD)v27 != 1);
      KeInitializeEvent((PRKEVENT)DeviceExtension + 42, NotificationEvent, *((_DWORD *)DeviceExtension + 71) == 1);
      IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, 0x74727044u, 1u, 0, 0x20u);
      Pool2 = ExAllocatePool2(64, 112, 1953656900);
      *((_QWORD *)DeviceExtension + 21) = Pool2;
      if ( !Pool2 )
      {
        DeviceIdFromDescriptor = -1073741801;
        WdLogSingleEntry1(6, -1073741801);
        WdLogGlobalForLineNumber = 433;
        goto LABEL_51;
      }
      *(_DWORD *)(Pool2 + 104) = 1;
      v29 = ExInitializeResourceLite(*((PERESOURCE *)DeviceExtension + 21));
      DeviceIdFromDescriptor = v29;
      if ( v29 < 0 )
      {
        WdLogSingleEntry1(2, v29);
        WdLogGlobalForLineNumber = 446;
        goto LABEL_51;
      }
      v42 = 1;
      WorkItem = IoAllocateWorkItem(DeviceObject);
      *((_QWORD *)DeviceExtension + 119) = WorkItem;
      if ( !WorkItem )
      {
        DeviceIdFromDescriptor = -1073741801;
        WdLogSingleEntry1(6, -1073741801);
        WdLogGlobalForLineNumber = 465;
        goto LABEL_51;
      }
      *((_QWORD *)DeviceExtension + 14) = DpiPdoDispatchInternalIoctl;
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
        v31 = *(_QWORD **)(v9 + 3792);
        if ( *v31 != v9 + 3784 )
          goto LABEL_62;
        *(_QWORD *)DeviceExtension = v9 + 3784;
        *((_QWORD *)DeviceExtension + 1) = v31;
        *v31 = DeviceExtension;
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
          WdLogSingleEntry1(4, DeviceObject);
          WdLogGlobalForLineNumber = 644;
LABEL_49:
          v15 = v42;
          if ( DeviceIdFromDescriptor == 259 )
          {
            v19 = Source1[1];
            goto LABEL_54;
          }
          goto LABEL_50;
        }
        ++*(_DWORD *)(v9 + 3804);
      }
      if ( *((_DWORD *)DeviceExtension + 124) == 1 )
      {
        v32 = DmmSetTemporaryVideoOutputTechnology(
                *(void *const *)(v9 + 4032),
                *((_DWORD *)DeviceExtension + 126),
                a3,
                (enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY)(a7 != 0
                                                      ? D3DKMDT_VOT_RF|D3DKMDT_VOT_INDIRECT_WIRED
                                                      : D3DKMDT_VOT_UNINITIALIZED));
        DeviceIdFromDescriptor = v32;
        if ( v32 < 0 )
        {
          WdLogSingleEntry1(2, v32);
          WdLogGlobalForLineNumber = 562;
          goto LABEL_51;
        }
        v33 = IsInternalVideoOutput(*(enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)(a2 + 4));
        PhysicalMonitor = MonitorCreatePhysicalMonitor(
                            *(void **)(v9 + 4032),
                            *((_DWORD *)DeviceExtension + 126),
                            DeviceObject,
                            v33,
                            1,
                            a7,
                            a8,
                            a9);
        DeviceIdFromDescriptor = PhysicalMonitor;
        if ( PhysicalMonitor < 0 )
        {
          WdLogSingleEntry1(2, PhysicalMonitor);
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
      if ( v19 )
        goto LABEL_17;
      if ( !v20 )
      {
LABEL_16:
        if ( !v19 )
        {
LABEL_21:
          *((_BYTE *)DeviceExtension + 511) = 1;
          WdLogSingleEntry1(4, DeviceObject);
          LOBYTE(v23) = 1;
          v24 = a1;
          WdLogGlobalForLineNumber = 329;
          DpiPdoRemovePdo(a1, a2, v23, a8, a9);
          goto LABEL_23;
        }
LABEL_17:
        if ( v20 )
        {
          v21 = *((_DWORD *)DeviceExtension + 231);
          if ( HIDWORD(Source1[0]) == v21 )
          {
            v22 = RtlCompareMemory(v19, v20, v21);
            if ( v22 == HIDWORD(Source1[0]) )
              goto LABEL_20;
          }
        }
        goto LABEL_21;
      }
    }
LABEL_20:
    DeviceIdFromDescriptor = 0x40000000;
    goto LABEL_51;
  }
  DeviceIdFromDescriptor = 0x40000000;
  WdLogSingleEntry1(4, v16);
  WdLogGlobalForLineNumber = 206;
LABEL_50:
  v19 = Source1[1];
LABEL_51:
  if ( *(_BYTE *)(a2 + 64) == 1 )
  {
    KeWaitForSingleObject((PVOID)(v9 + 3544), Executive, 0, 0, 0);
    DpiFdoPendingCreatePdoCompletion(a1, a2);
    KeReleaseMutex((PRKMUTEX)(v9 + 3544), 0);
  }
LABEL_54:
  if ( DeviceIdFromDescriptor >= 0 || v44 != 1 )
    goto LABEL_75;
  if ( v15 == 1 )
  {
    if ( !(unsigned int)Feature_ForceConnectionDetectionOnDcToAc__private_IsEnabledDeviceUsageNoInline() )
    {
      v35 = *(_QWORD **)DeviceExtension;
      if ( *(PVOID *)(*(_QWORD *)DeviceExtension + 8LL) == DeviceExtension )
      {
        v36 = (PVOID *)*((_QWORD *)DeviceExtension + 1);
        if ( *v36 == DeviceExtension )
        {
          *v36 = v35;
          v35[1] = v36;
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
  if ( v42 == 1 )
    ExDeleteResourceLite(*((PERESOURCE *)DeviceExtension + 21));
  v37 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 119);
  if ( v37 )
    IoFreeWorkItem(v37);
  v38 = (void *)*((_QWORD *)DeviceExtension + 21);
  if ( v38 )
  {
    ExFreePoolWithTag(v38, 0);
    *((_QWORD *)DeviceExtension + 21) = 0;
  }
  if ( DeviceObject )
  {
    IoDeleteDevice(DeviceObject);
    DeviceObject = 0;
  }
LABEL_75:
  if ( v19 )
    ExFreePoolWithTag(v19, 0);
  return (unsigned int)DeviceIdFromDescriptor;
}

```

## disassembly

```asm
0x1403f8934  mov     [rsp-38h+arg_8], rbx
0x1403f8939  mov     [rsp-38h+arg_10], r8d
0x1403f893e  mov     [rsp-38h+arg_0], rcx
0x1403f8943  push    rbp
0x1403f8944  push    rsi
0x1403f8945  push    rdi
0x1403f8946  push    r12
0x1403f8948  push    r13
0x1403f894a  push    r14
0x1403f894c  push    r15
0x1403f894e  mov     rbp, rsp
0x1403f8951  sub     rsp, 70h
0x1403f8955  mov     r14, [rcx+40h]
0x1403f8959  xor     edi, edi
0x1403f895b  mov     r10b, r9b
0x1403f895e  mov     [rbp+var_18], 0
0x1403f8966  xorps   xmm0, xmm0
0x1403f8969  mov     [rbp+var_1F], 0
0x1403f896d  mov     r11d, r8d
0x1403f8970  mov     [rbp+var_1E], dil
0x1403f8974  mov     r9, [r14+0EC8h]
0x1403f897b  mov     r15, rdx
0x1403f897e  mov     rax, r9
0x1403f8981  mov     [rbp+var_20], dil
0x1403f8985  mov     rbx, rcx
0x1403f8988  xor     r13b, r13b
0x1403f898b  movups  xmmword ptr [rbp+Source1], xmm0
0x1403f898f  mov     rcx, [rax]
0x1403f8992  mov     r8b, [rbp+arg_20]
0x1403f8996  cmp     rcx, r9
0x1403f8999  jz      short loc_1403F89E5
0x1403f899b  mov     edx, [r15+18h]
0x1403f899f  mov     rdi, rax
0x1403f89a2  cmp     [rax+1F8h], edx
0x1403f89a8  jz      short loc_1403F89AF
0x1403f89aa  mov     rax, rcx
0x1403f89ad  jmp     short loc_1403F898F
0x1403f89af  mov     rax, [rax+18h]
0x1403f89b3  mov     [rbp+var_18], rax
0x1403f89b7  mov     [rbp+var_1F], 1
0x1403f89bb  test    r8b, r8b
0x1403f89be  jnz     short loc_1403F89E5
0x1403f89c0  mov     esi, 40000000h
0x1403f89c5  mov     ecx, 4
0x1403f89ca  call    cs:__imp_WdLogSingleEntry1
0x1403f89d1  nop     dword ptr [rax+rax+00h]
0x1403f89d6  mov     cs:WdLogGlobalForLineNumber, 0CEh
0x1403f89e0  jmp     loc_1403F8FAE
0x1403f89e5  lea     rax, [rbp+Source1]
0x1403f89e9  mov     r9b, r10b
0x1403f89ec  mov     [rsp+70h+DeviceClassGuid], rax
0x1403f89f1  mov     rdx, r15
0x1403f89f4  mov     al, [rbp+arg_28]
0x1403f89f7  mov     rcx, rbx
0x1403f89fa  mov     [rsp+70h+Exclusive], al; Exclusive
0x1403f89fe  mov     byte ptr [rsp+70h+DeviceCharacteristics], r8b
0x1403f8a03  mov     r8d, r11d
0x1403f8a06  call    DpiPdoGetDeviceDescriptor
0x1403f8a0b  mov     esi, eax
0x1403f8a0d  mov     ebx, 4
0x1403f8a12  test    eax, eax
0x1403f8a14  jns     short loc_1403F8A3D
0x1403f8a16  mov     edx, [r15+18h]
0x1403f8a1a  mov     ecx, ebx
0x1403f8a1c  call    cs:__imp_WdLogSingleEntry1
0x1403f8a23  nop     dword ptr [rax+rax+00h]
0x1403f8a28  mov     cs:WdLogGlobalForLineNumber, 0EBh
0x1403f8a32  cmp     dword ptr [r15], 1
0x1403f8a36  jz      short loc_1403F8A48
0x1403f8a38  jmp     loc_1403F8FA2
0x1403f8a3d  cmp     eax, 103h
0x1403f8a42  jz      loc_1403F9145
0x1403f8a48  cmp     [rbp+var_1F], 1
0x1403f8a4c  mov     r12, [rbp+Source1+8]
0x1403f8a50  jnz     loc_1403F8AF9
0x1403f8a56  mov     rdx, [rdi+3A0h]
0x1403f8a5d  cmp     r12, rdx
0x1403f8a60  jz      short loc_1403F8AA8
0x1403f8a62  mov     ecx, [r15+4]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
0x1403f8a66  call    ?IsInternalVideoOutput@@YAEW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@@Z; IsInternalVideoOutput(_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY)
0x1403f8a6b  test    al, al
0x1403f8a6d  jz      short loc_1403F8A79
0x1403f8a6f  test    r12, r12
0x1403f8a72  jnz     short loc_1403F8A7E
0x1403f8a74  test    rdx, rdx
0x1403f8a77  jnz     short loc_1403F8AA8
0x1403f8a79  test    r12, r12
0x1403f8a7c  jz      short loc_1403F8AB2
0x1403f8a7e  test    rdx, rdx
0x1403f8a81  jz      short loc_1403F8AB2
0x1403f8a83  mov     eax, [rdi+39Ch]
0x1403f8a89  cmp     dword ptr [rbp+Source1+4], eax
0x1403f8a8c  jnz     short loc_1403F8AB2
0x1403f8a8e  mov     r8d, eax; Length
0x1403f8a91  mov     rcx, r12; Source1
0x1403f8a94  call    cs:__imp_RtlCompareMemory
0x1403f8a9b  nop     dword ptr [rax+rax+00h]
0x1403f8aa0  mov     ecx, dword ptr [rbp+Source1+4]
0x1403f8aa3  cmp     rax, rcx
0x1403f8aa6  jnz     short loc_1403F8AB2
0x1403f8aa8  mov     esi, 40000000h
0x1403f8aad  jmp     loc_1403F8FB2
0x1403f8ab2  mov     byte ptr [rdi+1FFh], 1
0x1403f8ab9  mov     rdx, [rbp+var_18]
0x1403f8abd  mov     ecx, ebx
0x1403f8abf  call    cs:__imp_WdLogSingleEntry1
0x1403f8ac6  nop     dword ptr [rax+rax+00h]
0x1403f8acb  mov     rax, [rbp+arg_40]
0x1403f8ad2  mov     r8b, 1
0x1403f8ad5  mov     rbx, [rbp+arg_0]
0x1403f8ad9  mov     rdx, r15
0x1403f8adc  mov     r9, [rbp+arg_38]
0x1403f8ae0  mov     rcx, rbx
0x1403f8ae3  mov     qword ptr [rsp+70h+DeviceCharacteristics], rax
0x1403f8ae8  mov     cs:WdLogGlobalForLineNumber, 149h
0x1403f8af2  call    DpiPdoRemovePdo
0x1403f8af7  jmp     short loc_1403F8AFD
0x1403f8af9  mov     rbx, [rbp+arg_0]
0x1403f8afd  cmp     dword ptr [r15], 1
0x1403f8b01  lea     rcx, GUID_SD_PDO
0x1403f8b08  lea     rax, [rbp+var_18]
0x1403f8b0c  mov     r9d, 1Ch; DeviceType
0x1403f8b12  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1403f8b17  lea     rdx, GUID_DEVCLASS_MONITOR
0x1403f8b1e  cmovnz  rdx, rcx
0x1403f8b22  lea     rax, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x1403f8b29  mov     rcx, [r14+28h]
0x1403f8b2d  xor     r8d, r8d; DeviceName
0x1403f8b30  mov     [rsp+70h+DeviceClassGuid], rdx; DeviceClassGuid
0x1403f8b35  mov     edx, 408h; DeviceExtensionSize
0x1403f8b3a  mov     [rsp+70h+DefaultSDDLString], rax; DefaultSDDLString
0x1403f8b3f  mov     [rsp+70h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x1403f8b47  mov     rcx, [rcx+20h]; DriverObject
0x1403f8b4b  call    WdmlibIoCreateDeviceSecure
0x1403f8b50  movsxd  rsi, eax
0x1403f8b53  test    eax, eax
0x1403f8b55  jns     short loc_1403F8B7A
0x1403f8b57  mov     rdx, rsi
0x1403f8b5a  mov     ecx, 2
0x1403f8b5f  call    cs:__imp_WdLogSingleEntry1
0x1403f8b66  nop     dword ptr [rax+rax+00h]
0x1403f8b6b  mov     cs:WdLogGlobalForLineNumber, 173h
0x1403f8b75  jmp     loc_1403F8FB2
0x1403f8b7a  mov     rax, [rbp+var_18]
0x1403f8b7e  mov     esi, 74727044h
0x1403f8b83  mov     [rbp+var_1E], 1
0x1403f8b87  mov     rdi, [rax+40h]
0x1403f8b8b  mov     [rdi+10h], esi
0x1403f8b8e  lea     rcx, [rdi+3D8h]; Event
0x1403f8b95  mov     dword ptr [rdi+14h], 5
0x1403f8b9c  mov     rax, [rbp+var_18]
0x1403f8ba0  mov     [rdi+20h], rbx
0x1403f8ba4  mov     ebx, 1
0x1403f8ba9  mov     [rdi+18h], rax
0x1403f8bad  mov     rax, [r14+28h]
0x1403f8bb1  mov     [rdi+28h], rax
0x1403f8bb5  mov     rax, [r14+30h]
0x1403f8bb9  mov     [rdi+30h], rax
0x1403f8bbd  mov     [rdi+38h], bl
0x1403f8bc0  mov     [rdi+118h], ebx
0x1403f8bc6  mov     eax, [r15+44h]
0x1403f8bca  cmp     eax, ebx
0x1403f8bcc  mov     [rdi+11Ch], eax
0x1403f8bd2  setnz   r8b; State
0x1403f8bd6  xor     edx, edx; Type
0x1403f8bd8  call    cs:__imp_KeInitializeEvent
0x1403f8bdf  nop     dword ptr [rax+rax+00h]
0x1403f8be4  cmp     [rdi+11Ch], ebx
0x1403f8bea  lea     rcx, [rdi+3F0h]; Event
0x1403f8bf1  setz    r8b; State
0x1403f8bf5  xor     edx, edx; Type
0x1403f8bf7  call    cs:__imp_KeInitializeEvent
0x1403f8bfe  nop     dword ptr [rax+rax+00h]
0x1403f8c03  lea     rcx, [rdi+40h]; Lock
0x1403f8c07  mov     [rsp+70h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x1403f8c0f  xor     r9d, r9d; HighWatermark
0x1403f8c12  mov     r8d, ebx; MaxLockedMinutes
0x1403f8c15  mov     edx, esi; AllocateTag
0x1403f8c17  call    cs:__imp_IoInitializeRemoveLockEx
0x1403f8c1e  nop     dword ptr [rax+rax+00h]
0x1403f8c23  mov     r8d, esi
0x1403f8c26  lea     edx, [rbx+6Fh]
0x1403f8c29  lea     ecx, [rbx+3Fh]
0x1403f8c2c  call    cs:__imp_ExAllocatePool2
0x1403f8c33  nop     dword ptr [rax+rax+00h]
0x1403f8c38  xor     ebx, ebx
0x1403f8c3a  mov     [rdi+0A8h], rax
0x1403f8c41  test    rax, rax
0x1403f8c44  jnz     short loc_1403F8C6D
0x1403f8c46  mov     rdx, 0FFFFFFFFC0000017h
0x1403f8c4d  mov     esi, edx
0x1403f8c4f  lea     ecx, [rax+6]
0x1403f8c52  call    cs:__imp_WdLogSingleEntry1
0x1403f8c59  nop     dword ptr [rax+rax+00h]
0x1403f8c5e  mov     cs:WdLogGlobalForLineNumber, 1B1h
0x1403f8c68  jmp     loc_1403F8FB2
0x1403f8c6d  mov     dword ptr [rax+68h], 1
0x1403f8c74  mov     rcx, [rdi+0A8h]; Resource
0x1403f8c7b  call    cs:__imp_ExInitializeResourceLite
0x1403f8c82  nop     dword ptr [rax+rax+00h]
0x1403f8c87  movsxd  rsi, eax
0x1403f8c8a  test    eax, eax
0x1403f8c8c  jns     short loc_1403F8CB1
0x1403f8c8e  mov     rdx, rsi
0x1403f8c91  mov     ecx, 2
0x1403f8c96  call    cs:__imp_WdLogSingleEntry1
0x1403f8c9d  nop     dword ptr [rax+rax+00h]
0x1403f8ca2  mov     cs:WdLogGlobalForLineNumber, 1BEh
0x1403f8cac  jmp     loc_1403F8FB2
0x1403f8cb1  mov     rcx, [rbp+var_18]; DeviceObject
0x1403f8cb5  mov     [rbp+var_20], 1
0x1403f8cb9  call    cs:__imp_IoAllocateWorkItem
0x1403f8cc0  nop     dword ptr [rax+rax+00h]
0x1403f8cc5  mov     [rdi+3B8h], rax
0x1403f8ccc  test    rax, rax
0x1403f8ccf  jnz     short loc_1403F8CF8
0x1403f8cd1  mov     rdx, 0FFFFFFFFC0000017h
0x1403f8cd8  mov     esi, edx
0x1403f8cda  lea     ecx, [rax+6]
0x1403f8cdd  call    cs:__imp_WdLogSingleEntry1
0x1403f8ce4  nop     dword ptr [rax+rax+00h]
0x1403f8ce9  mov     cs:WdLogGlobalForLineNumber, 1D1h
0x1403f8cf3  jmp     loc_1403F8FB2
0x1403f8cf8  mov     esi, [rbp+arg_10]
0x1403f8cfb  lea     rax, DpiPdoDispatchInternalIoctl
0x1403f8d02  mov     [rdi+70h], rax
0x1403f8d06  lea     rax, DpiPdoDispatchPnp
0x1403f8d0d  mov     [rdi+80h], rax
0x1403f8d14  lea     rax, DpiPdoDispatchPower
0x1403f8d1b  mov     [rdi+88h], rax
0x1403f8d22  lea     rax, DpiPdoDispatchIoctl
0x1403f8d29  mov     [rdi+78h], rax
0x1403f8d2d  lea     rax, DpiPdoHandleStartDevice
0x1403f8d34  mov     [rdi+120h], rax
0x1403f8d3b  lea     rax, DpiPdoHandleStopDevice
0x1403f8d42  mov     [rdi+140h], rax
0x1403f8d49  lea     rax, DpiPdoHandleQueryCapabilities
0x1403f8d50  mov     [rdi+168h], rax
0x1403f8d57  lea     rax, DpiPdoHandleQueryId
0x1403f8d5e  mov     [rdi+1B8h], rax
0x1403f8d65  lea     rax, DpiPdoHandleQueryDeviceRelations
0x1403f8d6c  mov     [rdi+158h], rax
0x1403f8d73  lea     rax, DpiPdoHandleQueryDeviceText
0x1403f8d7a  mov     [rdi+180h], rax
0x1403f8d81  lea     rax, DpiPdoHandleQueryBusInformation
0x1403f8d88  mov     [rdi+1C8h], rax
0x1403f8d8f  mov     r13d, 1
0x1403f8d95  mov     [rdi+3A8h], r15
0x1403f8d9c  mov     eax, [r15]
0x1403f8d9f  mov     [rdi+1F0h], eax
0x1403f8da5  mov     eax, [r15+14h]
0x1403f8da9  mov     [rdi+1F4h], eax
0x1403f8daf  mov     eax, [r15+18h]
0x1403f8db3  mov     [rdi+1F8h], eax
0x1403f8db9  mov     [rdi+1FCh], r13w
0x1403f8dc1  mov     [rdi+1FFh], bl
0x1403f8dc7  cmp     esi, 0FFFFFFFEh
0x1403f8dca  jz      short loc_1403F8DD2
0x1403f8dcc  mov     [rdi+3D0h], esi
0x1403f8dd2  mov     [rdi+3D4h], ebx
0x1403f8dd8  xor     r9d, r9d; Alertable
0x1403f8ddb  lea     rbx, [r14+0DD8h]
0x1403f8de2  mov     qword ptr [rsp+70h+DeviceCharacteristics], 0; Timeout
0x1403f8deb  mov     rcx, rbx; Object
0x1403f8dee  xor     r8d, r8d; WaitMode
0x1403f8df1  xor     edx, edx; WaitReason
0x1403f8df3  call    cs:__imp_KeWaitForSingleObject
0x1403f8dfa  nop     dword ptr [rax+rax+00h]
0x1403f8dff  mov     rax, [rbp+var_18]
0x1403f8e03  xor     edx, edx; Wait
0x1403f8e05  mov     rcx, rbx; Mutex
0x1403f8e08  mov     [r15+30h], rax
0x1403f8e0c  call    cs:__imp_KeReleaseMutex
0x1403f8e13  nop     dword ptr [rax+rax+00h]
0x1403f8e18  call    Feature_ForceConnectionDetectionOnDcToAc__private_IsEnabledDeviceUsageNoInline
0x1403f8e1d  test    eax, eax
0x1403f8e1f  jnz     short loc_1403F8E60
0x1403f8e21  lea     rcx, [r14+0EC8h]
0x1403f8e28  mov     rax, [rcx+8]
0x1403f8e2c  cmp     [rax], rcx
0x1403f8e2f  jnz     loc_1403F9059
0x1403f8e35  mov     [rdi], rcx
0x1403f8e38  mov     [rdi+8], rax
0x1403f8e3c  mov     [rax], rdi
0x1403f8e3f  mov     [rcx+8], rdi
0x1403f8e43  add     [r14+0ED8h], r13d
0x1403f8e4a  cmp     [rdi+1F0h], r13d
0x1403f8e51  jnz     loc_1403F8F34
0x1403f8e57  add     [r14+0EDCh], r13d
0x1403f8e5e  jmp     short loc_1403F8E6B
0x1403f8e60  mov     rdx, rdi
0x1403f8e63  mov     rcx, r14
0x1403f8e66  call    DpiFdoAddPdoToPdoList
0x1403f8e6b  cmp     [rdi+1F0h], r13d
0x1403f8e72  jnz     loc_1403F8F34
0x1403f8e78  mov     rbx, [rbp+arg_30]
0x1403f8e7c  mov     r8d, esi; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
0x1403f8e7f  mov     edx, [rdi+1F8h]; unsigned int
0x1403f8e85  mov     rax, rbx
0x1403f8e88  mov     rcx, [r14+0FC0h]; void *
  ... truncated ...
```
