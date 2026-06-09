# ClassReadDriveCapacity

- ea: `0x140001130`
- end: `0x14000179a`
- name: `ClassReadDriveCapacity`
- size: `1642`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `13`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000cab0`
- `0x140014418`
- `0x140019de0`
- `0x1400229f8`
- `0x14002b700`
- `0x14002dabc`
- `0x14002fd18`
- `0x140031d6c`
- `0x1400320dc`
- `0x140032444`
- `0x1400327ac`
- `0x140032d74`
- `0x14005c054`

## callees

- `0x140001130`
- `0x1400017c0`
- `0x1400018a0`
- `0x1400018e4`
- `0x140002230`
- `0x140004950`
- `0x1400074b8`
- `0x1400157d0`
- `0x1400179a8`
- `0x140017bf8`
- `0x140019ce4`
- `0x14001feac`
- `0x14001fedc`
- `0x14002001c`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400012b8`
- `ntoskrnl!KeReleaseMutex` at `0x1400013e6`
- `ntoskrnl!KeReleaseMutex` at `0x1400012b8`
- `ntoskrnl!KeReleaseMutex` at `0x1400013e6`
- `ntoskrnl!KeInitializeEvent` at `0x14000124a`
- `ntoskrnl!KeInitializeEvent` at `0x140001378`
- `ntoskrnl!KeInitializeEvent` at `0x14000124a`
- `ntoskrnl!KeInitializeEvent` at `0x140001378`
- `ntoskrnl!IoQueueWorkItem` at `0x1400015b1`
- `ntoskrnl!IoQueueWorkItem` at `0x1400015b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001233`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001297`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001360`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400013c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001233`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001297`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001360`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400013c5`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001570`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001570`

## pseudocode

```c
NTSTATUS __stdcall ClassReadDriveCapacity(PDEVICE_OBJECT DeviceObject)
{
  char *DeviceExtension; // rbx
  struct _MDL *v3; // rdi
  __int64 v4; // rsi
  unsigned __int8 i; // r15
  ULONG v6; // r12d
  struct _MDL *v7; // r8
  PSLIST_ENTRY v8; // rdi
  NTSTATUS v9; // edi
  PSLIST_ENTRY v10; // rdi
  union _LARGE_INTEGER *Timeout; // r8
  __int128 v12; // xmm6
  int v13; // r12d
  int v14; // r15d
  int v15; // ecx
  int v16; // r8d
  char v17; // r15
  PIO_WORKITEM WorkItem; // rax
  struct _IO_WORKITEM *v19; // r15
  unsigned int v20; // edx
  struct _MDL *Mdl; // [rsp+30h] [rbp-D0h]
  struct _KEVENT Event; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v24[26]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v25[2]; // [rsp+120h] [rbp+20h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v3 = 0;
  v4 = *((_QWORD *)DeviceExtension + 143);
  memset(v25, 0, 12);
  memset(&Event, 0, sizeof(Event));
  memset(v24, 0, sizeof(v24));
  for ( i = (*((_WORD *)DeviceExtension + 320) & 0x20) != 0; ; i = 1 )
  {
    v6 = 4 * i + 8;
    if ( v3 )
      ClasspFreeDeviceMdl(v3);
    Mdl = ClasspBuildDeviceMdl(v25, v6);
    v7 = Mdl;
    if ( !Mdl )
      break;
    v8 = DequeueFreeTransferPacket((__int64)DeviceObject);
    if ( !v8 )
    {
      v9 = -1073741670;
      goto LABEL_47;
    }
    v24[1] = Mdl;
    v24[15] = 1;
    LODWORD(v24[6]) = 0;
    v24[7] = 0;
    if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
      KeWaitForSingleObject(*((PVOID *)DeviceExtension + 143), Executive, 0, 0, 0);
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    SetupDriveCapacityTransferPacket((_DWORD)v8, (unsigned int)v25, v6, (unsigned int)&Event, (__int64)v24, i);
    SubmitTransferPacket((__int64)v8);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
      KeReleaseMutex(*((PRKMUTEX *)DeviceExtension + 143), 0);
    v9 = v24[6];
    if ( SLODWORD(v24[6]) < 0 )
      goto LABEL_27;
    if ( v24[7] < (unsigned __int64)v6 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          61,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          LODWORD(v24[7]),
          4 * i + 8);
      }
      v10 = DequeueFreeTransferPacket((__int64)DeviceObject);
      if ( !v10 )
      {
        v9 = -1073741670;
        goto LABEL_27;
      }
      v24[15] = 1;
      LODWORD(v24[6]) = 0;
      v24[7] = 0;
      if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
        KeWaitForSingleObject(*((PVOID *)DeviceExtension + 143), Executive, (KPROCESSOR_MODE)Timeout, 0, Timeout);
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      SetupDriveCapacityTransferPacket((_DWORD)v10, (unsigned int)v25, v6, (unsigned int)&Event, (__int64)v24, i);
      SubmitTransferPacket((__int64)v10);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
        KeReleaseMutex(*((PRKMUTEX *)DeviceExtension + 143), 0);
      if ( v24[7] < (unsigned __int64)v6 )
      {
        v9 = -2147483631;
LABEL_27:
        v12 = *(_OWORD *)(DeviceExtension + 552);
        v13 = *((_DWORD *)DeviceExtension + 142);
        v14 = *((_DWORD *)DeviceExtension + 143);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            62,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            DeviceObject,
            v9);
        }
        *(_OWORD *)(DeviceExtension + 552) = 0;
        *((_QWORD *)DeviceExtension + 71) = 0;
        if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
        {
          if ( v14 )
          {
            *(_OWORD *)(DeviceExtension + 552) = v12;
            *((_DWORD *)DeviceExtension + 142) = v13;
            *((_DWORD *)DeviceExtension + 143) = v14;
          }
          else
          {
            *((_DWORD *)DeviceExtension + 143) = 4096;
            LOBYTE(v16) = 1;
            DeviceExtension[642] = 12;
          }
          if ( ClassPnPETWEnabled )
            ClasspReadCapacityFailureForSMRDeviceEvent(
              v15,
              (_DWORD)DeviceObject,
              v16,
              *((_DWORD *)DeviceExtension + 143),
              (unsigned __int8)DeviceExtension[642],
              v9);
        }
        else
        {
          if ( v14 )
          {
            *(_OWORD *)(DeviceExtension + 552) = v12;
            *((_DWORD *)DeviceExtension + 142) = v13;
            *((_DWORD *)DeviceExtension + 143) = v14;
          }
          else
          {
            *((_DWORD *)DeviceExtension + 143) = 512;
            LOBYTE(v16) = 1;
            DeviceExtension[642] = 9;
          }
          if ( ClassPnPETWEnabled )
            ClasspReadCapacityFailureEvent(
              v15,
              (_DWORD)DeviceObject,
              v16,
              *((_DWORD *)DeviceExtension + 143),
              (unsigned __int8)DeviceExtension[642],
              v9);
        }
        *((_QWORD *)DeviceExtension + 18) = 0;
        *((_DWORD *)DeviceExtension + 140) = 12 - ((DeviceObject->Characteristics & 1) != 0);
LABEL_47:
        v7 = Mdl;
        goto LABEL_48;
      }
      v9 = v24[6];
      if ( SLODWORD(v24[6]) < 0 )
        goto LABEL_27;
    }
    if ( i )
    {
      *((_WORD *)DeviceExtension + 320) |= 0x20u;
LABEL_37:
      v17 = 1;
      InterpretCapacityData(DeviceObject, v25);
      if ( *(_BYTE *)(v4 + 1580) == 1 && (*(_QWORD *)(v4 + 1568) != v25[0] || *(_DWORD *)(v4 + 1576) != LODWORD(v25[1])) )
        v17 = 0;
      *(_QWORD *)(v4 + 1568) = v25[0];
      *(_DWORD *)(v4 + 1576) = v25[1];
      *(_BYTE *)(v4 + 1580) = 1;
      if ( !v17
        && *(_BYTE *)(v4 + 718) == 1
        && !DeviceExtension[106]
        && !_InterlockedCompareExchange((volatile signed __int32 *)(v4 + 1276), 1, 0) )
      {
        WorkItem = IoAllocateWorkItem(DeviceObject);
        v19 = WorkItem;
        if ( WorkItem )
        {
          ClassAcquireRemoveLockEx(
            *((PDEVICE_OBJECT *)DeviceExtension + 1),
            WorkItem,
            "minkernel\\storage\\classpnp\\class.c",
            0xFFEu);
          IoQueueWorkItem(v19, ClasspUpdateDiskProperties, DelayedWorkQueue, v19);
        }
        else
        {
          _InterlockedExchange((volatile __int32 *)(v4 + 1276), 0);
        }
      }
      goto LABEL_47;
    }
    if ( LODWORD(v25[0]) != -1 )
    {
      *(_QWORD *)((char *)v25 + 4) = v25[0];
      LODWORD(v25[0]) = 0;
      goto LABEL_37;
    }
    v3 = Mdl;
  }
  v9 = -1073741670;
LABEL_48:
  if ( (*(_DWORD *)(*((_QWORD *)DeviceExtension + 143) + 904LL) & 1) != 0 )
    *((_WORD *)DeviceExtension + 320) |= 0x20u;
  if ( (*((_WORD *)DeviceExtension + 320) & 0x20) == 0 )
  {
    v20 = 0xFFFF << DeviceExtension[642];
    if ( v20 >= *(_DWORD *)(v4 + 652) )
      v20 = *(_DWORD *)(v4 + 652);
    *(_DWORD *)(v4 + 652) = v20;
  }
  if ( v7 )
    ClasspFreeDeviceMdl(v7);
  if ( v9 < 0 && *((_DWORD *)DeviceExtension + 140) == 11 )
    *(_BYTE *)(v4 + 1580) = 0;
  if ( v9 == -1073741670 && *(_BYTE *)(v4 + 1580) && *((_DWORD *)DeviceExtension + 140) == 12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    }
    InterpretCapacityData(DeviceObject, v4 + 1568);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x140001130  mov     rax, rsp
0x140001133  push    rbp
0x140001134  push    rbx
0x140001135  push    rsi
0x140001136  push    rdi
0x140001137  push    r12
0x140001139  push    r13
0x14000113b  push    r14
0x14000113d  push    r15
0x14000113f  lea     rbp, [rsp-58h]
0x140001144  sub     rsp, 158h
0x14000114b  movaps  xmmword ptr [rax-58h], xmm6
0x14000114f  mov     rax, cs:__security_cookie
0x140001156  xor     rax, rsp
0x140001159  mov     [rbp+90h+var_60], rax
0x14000115d  mov     rbx, [rcx+40h]
0x140001161  xor     eax, eax
0x140001163  mov     r14, rcx
0x140001166  xorps   xmm0, xmm0
0x140001169  xor     edx, edx; Val
0x14000116b  lea     rcx, [rsp+190h+var_140]; void *
0x140001170  mov     r8d, 0D0h; Size
0x140001176  xor     edi, edi
0x140001178  mov     rsi, [rbx+478h]
0x14000117f  mov     [rbp+90h+var_70], rax
0x140001183  mov     [rbp+90h+var_68], eax
0x140001186  movups  xmmword ptr [rsp+190h+Event.Header.___u0], xmm0
0x14000118b  mov     [rsp+190h+Event.Header.WaitListHead.Blink], rax
0x140001190  call    memset
0x140001195  movzx   r15d, word ptr [rbx+280h]
0x14000119d  lea     r13d, [rdi+1]
0x1400011a1  shr     r15b, 5
0x1400011a5  and     r15b, r13b
0x1400011a8  movzx   eax, r15b
0x1400011ac  lea     r12d, ds:8[rax*4]
0x1400011b4  test    rdi, rdi
0x1400011b7  jz      short loc_1400011C1
0x1400011b9  mov     rcx, rdi; Mdl
0x1400011bc  call    ClasspFreeDeviceMdl
0x1400011c1  mov     edx, r12d
0x1400011c4  lea     rcx, [rbp+90h+var_70]
0x1400011c8  call    ClasspBuildDeviceMdl
0x1400011cd  mov     [rsp+190h+Mdl], rax
0x1400011d2  mov     r8, rax
0x1400011d5  test    rax, rax
0x1400011d8  jz      loc_140001790
0x1400011de  mov     rcx, r14
0x1400011e1  call    DequeueFreeTransferPacket
0x1400011e6  mov     rdi, rax
0x1400011e9  test    rax, rax
0x1400011ec  jz      loc_140001786
0x1400011f2  mov     rax, [rsp+190h+Mdl]
0x1400011f7  mov     rcx, r14
0x1400011fa  mov     [rsp+190h+var_138], rax
0x1400011ff  mov     [rbp+90h+var_C8], r13
0x140001203  mov     [rbp+90h+var_110], 0
0x14000120a  mov     [rbp+90h+var_108], 0
0x140001212  call    ClasspIsManagedZonedDevice
0x140001217  test    al, al
0x140001219  jz      short loc_14000123F
0x14000121b  mov     rcx, [rbx+478h]; Object
0x140001222  xor     r9d, r9d; Alertable
0x140001225  xor     r8d, r8d; WaitMode
0x140001228  mov     [rsp+190h+Timeout], 0; Timeout
0x140001231  xor     edx, edx; WaitReason
0x140001233  call    cs:__imp_KeWaitForSingleObject
0x14000123a  nop     dword ptr [rax+rax+00h]
0x14000123f  xor     r8d, r8d; State
0x140001242  lea     rcx, [rsp+190h+Event]; Event
0x140001247  mov     edx, r13d; Type
0x14000124a  call    cs:__imp_KeInitializeEvent
0x140001251  nop     dword ptr [rax+rax+00h]
0x140001256  lea     rax, [rsp+190h+var_140]
0x14000125b  mov     byte ptr [rsp+190h+var_168], r15b
0x140001260  lea     r9, [rsp+190h+Event]
0x140001265  mov     [rsp+190h+Timeout], rax
0x14000126a  mov     r8d, r12d
0x14000126d  lea     rdx, [rbp+90h+var_70]
0x140001271  mov     rcx, rdi
0x140001274  call    SetupDriveCapacityTransferPacket
0x140001279  mov     rcx, rdi
0x14000127c  call    SubmitTransferPacket
0x140001281  xor     r9d, r9d; Alertable
0x140001284  mov     [rsp+190h+Timeout], 0; Timeout
0x14000128d  xor     r8d, r8d; WaitMode
0x140001290  lea     rcx, [rsp+190h+Event]; Object
0x140001295  xor     edx, edx; WaitReason
0x140001297  call    cs:__imp_KeWaitForSingleObject
0x14000129e  nop     dword ptr [rax+rax+00h]
0x1400012a3  mov     rcx, r14
0x1400012a6  call    ClasspIsManagedZonedDevice
0x1400012ab  test    al, al
0x1400012ad  jz      short loc_1400012C4
0x1400012af  mov     rcx, [rbx+478h]; Mutex
0x1400012b6  xor     edx, edx; Wait
0x1400012b8  call    cs:__imp_KeReleaseMutex
0x1400012bf  nop     dword ptr [rax+rax+00h]
0x1400012c4  mov     edi, [rbp+90h+var_110]
0x1400012c7  test    edi, edi
0x1400012c9  js      loc_140001430
0x1400012cf  mov     r13d, r12d
0x1400012d2  cmp     [rbp+90h+var_108], r13
0x1400012d6  jnb     loc_1400013FF
0x1400012dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012e3  lea     rax, WPP_GLOBAL_Control
0x1400012ea  cmp     rcx, rax
0x1400012ed  jz      short loc_14000131C
0x1400012ef  test    dword ptr [rcx+2Ch], 100h
0x1400012f6  jz      short loc_14000131C
0x1400012f8  cmp     byte ptr [rcx+29h], 2
0x1400012fc  jb      short loc_14000131C
0x1400012fe  mov     r9d, dword ptr [rbp+90h+var_108]
0x140001302  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140001309  mov     rcx, [rcx+18h]
0x14000130d  mov     edx, 3Dh ; '='
0x140001312  mov     dword ptr [rsp+190h+Timeout], r12d
0x140001317  call    WPP_SF_DD
0x14000131c  mov     rcx, r14
0x14000131f  call    DequeueFreeTransferPacket
0x140001324  xor     r8d, r8d
0x140001327  mov     rdi, rax
0x14000132a  test    rax, rax
0x14000132d  jz      loc_1400014CB
0x140001333  mov     rcx, r14
0x140001336  mov     [rbp+90h+var_C8], 1
0x14000133e  mov     [rbp+90h+var_110], r8d
0x140001342  mov     [rbp+90h+var_108], r8
0x140001346  call    ClasspIsManagedZonedDevice
0x14000134b  test    al, al
0x14000134d  jz      short loc_14000136C
0x14000134f  mov     rcx, [rbx+478h]; Object
0x140001356  xor     r9d, r9d; Alertable
0x140001359  xor     edx, edx; WaitReason
0x14000135b  mov     [rsp+190h+Timeout], r8; Timeout
0x140001360  call    cs:__imp_KeWaitForSingleObject
0x140001367  nop     dword ptr [rax+rax+00h]
0x14000136c  xor     r8d, r8d; State
0x14000136f  lea     rcx, [rsp+190h+Event]; Event
0x140001374  lea     edx, [r8+1]; Type
0x140001378  call    cs:__imp_KeInitializeEvent
0x14000137f  nop     dword ptr [rax+rax+00h]
0x140001384  lea     rax, [rsp+190h+var_140]
0x140001389  mov     byte ptr [rsp+190h+var_168], r15b
0x14000138e  lea     r9, [rsp+190h+Event]
0x140001393  mov     [rsp+190h+Timeout], rax
0x140001398  mov     r8d, r12d
0x14000139b  lea     rdx, [rbp+90h+var_70]
0x14000139f  mov     rcx, rdi
0x1400013a2  call    SetupDriveCapacityTransferPacket
0x1400013a7  mov     rcx, rdi
0x1400013aa  call    SubmitTransferPacket
0x1400013af  xor     r9d, r9d; Alertable
0x1400013b2  mov     [rsp+190h+Timeout], 0; Timeout
0x1400013bb  xor     r8d, r8d; WaitMode
0x1400013be  lea     rcx, [rsp+190h+Event]; Object
0x1400013c3  xor     edx, edx; WaitReason
0x1400013c5  call    cs:__imp_KeWaitForSingleObject
0x1400013cc  nop     dword ptr [rax+rax+00h]
0x1400013d1  mov     rcx, r14
0x1400013d4  call    ClasspIsManagedZonedDevice
0x1400013d9  test    al, al
0x1400013db  jz      short loc_1400013F2
0x1400013dd  mov     rcx, [rbx+478h]; Mutex
0x1400013e4  xor     edx, edx; Wait
0x1400013e6  call    cs:__imp_KeReleaseMutex
0x1400013ed  nop     dword ptr [rax+rax+00h]
0x1400013f2  cmp     [rbp+90h+var_108], r13
0x1400013f6  jb      short loc_140001425
0x1400013f8  mov     edi, [rbp+90h+var_110]
0x1400013fb  test    edi, edi
0x1400013fd  js      short loc_14000142A
0x1400013ff  test    r15b, r15b
0x140001402  jnz     loc_1400014E4
0x140001408  cmp     dword ptr [rbp+90h+var_70], 0FFFFFFFFh
0x14000140c  jnz     loc_1400014D5
0x140001412  mov     rdi, [rsp+190h+Mdl]
0x140001417  mov     r13d, 1
0x14000141d  mov     r15b, r13b
0x140001420  jmp     loc_1400011A8
0x140001425  mov     edi, 80000011h
0x14000142a  mov     r13d, 1
0x140001430  movups  xmm6, xmmword ptr [rbx+228h]
0x140001437  mov     r12d, [rbx+238h]
0x14000143e  mov     r15d, [rbx+23Ch]
0x140001445  mov     rcx, cs:WPP_GLOBAL_Control
0x14000144c  lea     rax, WPP_GLOBAL_Control
0x140001453  cmp     rcx, rax
0x140001456  jz      short loc_140001483
0x140001458  test    dword ptr [rcx+2Ch], 100h
0x14000145f  jz      short loc_140001483
0x140001461  cmp     byte ptr [rcx+29h], 3
0x140001465  jb      short loc_140001483
0x140001467  mov     rcx, [rcx+18h]
0x14000146b  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140001472  mov     edx, 3Eh ; '>'
0x140001477  mov     dword ptr [rsp+190h+Timeout], edi
0x14000147b  mov     r9, r14
0x14000147e  call    WPP_SF_qD
0x140001483  xor     eax, eax
0x140001485  xorps   xmm0, xmm0
0x140001488  movups  xmmword ptr [rbx+228h], xmm0
0x14000148f  mov     rcx, r14
0x140001492  mov     [rbx+238h], rax
0x140001499  xor     r8b, r8b
0x14000149c  call    ClasspIsManagedZonedDevice
0x1400014a1  test    al, al
0x1400014a3  jnz     loc_14000170B
0x1400014a9  test    r15d, r15d
0x1400014ac  jnz     loc_1400016CD
0x1400014b2  mov     dword ptr [rbx+23Ch], 200h
0x1400014bc  mov     r8b, r13b
0x1400014bf  mov     byte ptr [rbx+282h], 9
0x1400014c6  jmp     loc_1400016E2
0x1400014cb  mov     edi, 0C000009Ah
0x1400014d0  jmp     loc_14000142A
0x1400014d5  mov     rax, [rbp+90h+var_70]
0x1400014d9  mov     [rbp+90h+var_70+4], rax
0x1400014dd  xor     eax, eax
0x1400014df  mov     dword ptr [rbp+90h+var_70], eax
0x1400014e2  jmp     short loc_1400014F6
0x1400014e4  movzx   eax, word ptr [rbx+280h]
0x1400014eb  or      ax, 20h
0x1400014ef  mov     [rbx+280h], ax
0x1400014f6  mov     r13d, 1
0x1400014fc  lea     rdx, [rbp+90h+var_70]
0x140001500  mov     rcx, r14
0x140001503  mov     r15b, r13b
0x140001506  call    InterpretCapacityData
0x14000150b  mov     al, [rsi+62Ch]
0x140001511  cmp     al, r13b
0x140001514  jnz     short loc_140001531
0x140001516  mov     rax, [rsi+620h]
0x14000151d  cmp     rax, [rbp+90h+var_70]
0x140001521  jnz     short loc_14000152E
0x140001523  mov     eax, [rsi+628h]
0x140001529  cmp     eax, [rbp+90h+var_68]
0x14000152c  jz      short loc_140001531
0x14000152e  xor     r15b, r15b
0x140001531  mov     rax, [rbp+90h+var_70]
0x140001535  mov     [rsi+620h], rax
0x14000153c  mov     eax, [rbp+90h+var_68]
0x14000153f  mov     [rsi+628h], eax
0x140001545  mov     [rsi+62Ch], r13b
0x14000154c  test    r15b, r15b
0x14000154f  jnz     short loc_1400015BD
0x140001551  cmp     [rsi+2CEh], r13b
0x140001558  jnz     short loc_1400015BD
0x14000155a  cmp     [rbx+6Ah], r15b
0x14000155e  jnz     short loc_1400015BD
0x140001560  xor     eax, eax
0x140001562  lock cmpxchg [rsi+4FCh], r13d
0x14000156b  jnz     short loc_1400015BD
0x14000156d  mov     rcx, r14; DeviceObject
0x140001570  call    cs:__imp_IoAllocateWorkItem
0x140001577  nop     dword ptr [rax+rax+00h]
0x14000157c  mov     r15, rax
0x14000157f  test    rax, rax
0x140001582  jz      loc_1400016C2
0x140001588  mov     rcx, [rbx+8]; DeviceObject
0x14000158c  lea     r8, File; "minkernel\\storage\\classpnp\\class.c"
0x140001593  mov     r9d, 0FFEh; Line
0x140001599  mov     rdx, rax; Tag
0x14000159c  call    ClassAcquireRemoveLockEx
0x1400015a1  mov     r9, r15; Context
0x1400015a4  lea     rdx, ClasspUpdateDiskProperties; WorkerRoutine
0x1400015ab  mov     r8d, r13d; QueueType
0x1400015ae  mov     rcx, r15; IoWorkItem
0x1400015b1  call    cs:__imp_IoQueueWorkItem
0x1400015b8  nop     dword ptr [rax+rax+00h]
0x1400015bd  mov     r8, [rsp+190h+Mdl]
0x1400015c2  mov     rax, [rbx+478h]
0x1400015c9  mov     ecx, [rax+388h]
0x1400015cf  test    r13b, cl
0x1400015d2  jz      short loc_1400015E6
0x1400015d4  movzx   eax, word ptr [rbx+280h]
0x1400015db  or      ax, 20h
0x1400015df  mov     [rbx+280h], ax
0x1400015e6  movzx   eax, word ptr [rbx+280h]
0x1400015ed  test    al, 20h
0x1400015ef  jnz     short loc_14000160F
0x1400015f1  mov     cl, [rbx+282h]
0x1400015f7  mov     edx, 0FFFFh
0x1400015fc  mov     eax, [rsi+28Ch]
0x140001602  shl     edx, cl
0x140001604  cmp     edx, eax
0x140001606  cmovnb  edx, eax
0x140001609  mov     [rsi+28Ch], edx
0x14000160f  test    r8, r8
0x140001612  jz      short loc_14000161C
0x140001614  mov     rcx, r8; Mdl
0x140001617  call    ClasspFreeDeviceMdl
0x14000161c  test    edi, edi
0x14000161e  jns     short loc_140001632
0x140001620  mov     eax, [rbx+230h]
0x140001626  cmp     eax, 0Bh
0x140001629  jnz     short loc_140001632
0x14000162b  mov     byte ptr [rsi+62Ch], 0
0x140001632  cmp     edi, 0C000009Ah
0x140001638  jnz     short loc_140001697
0x14000163a  mov     al, [rsi+62Ch]
  ... truncated ...
```
