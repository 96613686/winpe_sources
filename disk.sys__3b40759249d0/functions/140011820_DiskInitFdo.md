# DiskInitFdo

- ea: `0x140011820`
- end: `0x140011bb5`
- name: `DiskInitFdo`
- size: `917`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004078`
- `0x140006000`
- `0x140011438`
- `0x140011820`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140011b05`
- `ntoskrnl!IoQueueWorkItem` at `0x140011b05`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011ab5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011ab5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011b53`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011b53`
- `ntoskrnl!KeInitializeEvent` at `0x140011a33`
- `ntoskrnl!KeInitializeEvent` at `0x140011b6d`
- `ntoskrnl!KeInitializeEvent` at `0x140011a33`
- `ntoskrnl!KeInitializeEvent` at `0x140011b6d`
- `ntoskrnl!KeInitializeMutex` at `0x140011b17`
- `ntoskrnl!KeInitializeMutex` at `0x140011b17`
- `ntoskrnl!InitSafeBootMode` at `0x140011ac1`
- `ntoskrnl!IofCallDriver` at `0x140011a90`
- `ntoskrnl!IofCallDriver` at `0x140011a90`
- `ntoskrnl!IoAllocateIrp` at `0x140011b81`
- `ntoskrnl!IoAllocateIrp` at `0x140011b81`
- `ntoskrnl!ExAllocatePool2` at `0x1400118cc`
- `ntoskrnl!ExAllocatePool2` at `0x1400118cc`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140011a78`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140011a78`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011ae1`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011ae1`
- `CLASSPNP!ClassScanForSpecial` at `0x1400118a1`
- `CLASSPNP!ClassScanForSpecial` at `0x1400118a1`
- `CLASSPNP!ClassInitializeSrbLookasideList` at `0x140011847`
- `CLASSPNP!ClassInitializeSrbLookasideList` at `0x140011847`
- `CLASSPNP!ClassQueryTimeOutRegistryValue` at `0x140011949`
- `CLASSPNP!ClassQueryTimeOutRegistryValue` at `0x140011949`
- `CLASSPNP!ClassUpdateInformationInRegistry` at `0x14001198a`
- `CLASSPNP!ClassUpdateInformationInRegistry` at `0x14001198a`
- `CLASSPNP!ClassInitializeMediaChangeDetection` at `0x1400119a0`
- `CLASSPNP!ClassInitializeMediaChangeDetection` at `0x1400119a0`
- `CLASSPNP!ClassReadDriveCapacity` at `0x1400119e6`
- `CLASSPNP!ClassReadDriveCapacity` at `0x1400119e6`

## pseudocode

```c
__int64 __fastcall DiskInitFdo(PDEVICE_OBJECT DeviceObject)
{
  char *DeviceExtension; // rdi
  __int64 v3; // rbp
  __int64 v4; // rax
  __int64 Pool2; // rax
  __int64 result; // rax
  __int64 v7; // rax
  int v8; // ecx
  ULONG TimeOutRegistryValue; // eax
  __int64 v10; // rax
  int v11; // r14d
  IRP *v12; // rax
  struct _IO_WORKITEM *WorkItem; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-58h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v3 = *((_QWORD *)DeviceExtension + 12);
  ClassInitializeSrbLookasideList((PCOMMON_DEVICE_EXTENSION)DeviceExtension, 4u);
  if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 65) + 10LL) )
    DeviceObject->Characteristics |= 1u;
  v4 = *((_QWORD *)DeviceExtension + 65);
  *((_DWORD *)DeviceExtension + 148) |= 0x200000u;
  if ( *(_BYTE *)(v4 + 11) && *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 22LL) )
    *((_DWORD *)DeviceExtension + 148) |= 2u;
  ClassScanForSpecial((PFUNCTIONAL_DEVICE_EXTENSION)DeviceExtension, DiskBadControllers, DiskSetSpecialHacks);
  *(_OWORD *)(DeviceExtension + 552) = 0;
  *((_QWORD *)DeviceExtension + 71) = 0;
  Pool2 = ExAllocatePool2(72, 18, 1933861715);
  *((_QWORD *)DeviceExtension + 72) = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids);
    }
    return 3221225626LL;
  }
  v7 = *((_QWORD *)DeviceExtension + 145);
  DeviceExtension[549] = 18;
  *((_QWORD *)DeviceExtension + 19) = 0;
  if ( !v7 || (v8 = *(unsigned __int16 *)(v7 + 14), !(_WORD)v8) )
  {
    TimeOutRegistryValue = ClassQueryTimeOutRegistryValue(DeviceObject);
    v8 = 10;
    if ( TimeOutRegistryValue )
      v8 = TimeOutRegistryValue;
  }
  *((_DWORD *)DeviceExtension + 146) = v8;
  if ( (DeviceObject->Characteristics & 1) != 0 )
  {
    ClassUpdateInformationInRegistry(DeviceObject, (PCHAR)"PhysicalDrive", *((_DWORD *)DeviceExtension + 147), 0, 0);
    ClassInitializeMediaChangeDetection((PFUNCTIONAL_DEVICE_EXTENSION)DeviceExtension, (PUCHAR)"Disk");
    v10 = *((_QWORD *)DeviceExtension + 65);
    if ( *(_DWORD *)(v10 + 28) != 7 || (*(_BYTE *)(v10 + 9) & 0xF0) != 0x10 )
      goto LABEL_22;
  }
  else
  {
    *((_WORD *)DeviceExtension + 320) |= 4u;
  }
  *((_DWORD *)DeviceExtension + 148) |= 0x100u;
LABEL_22:
  v11 = *((_DWORD *)DeviceExtension + 148);
  ClassReadDriveCapacity(DeviceObject);
  if ( !*((_DWORD *)DeviceExtension + 143) )
  {
    *((_DWORD *)DeviceExtension + 143) = 512;
    DeviceExtension[642] = 9;
  }
  DiskCreateSymbolicLinks(DeviceObject);
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v12 = IoBuildDeviceIoControlRequest(
          0x41018u,
          *((PDEVICE_OBJECT *)DeviceExtension + 2),
          0,
          0,
          (PVOID)(v3 + 8),
          8u,
          0,
          &Event,
          &IoStatusBlock);
  if ( v12 && IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), v12) == 259 )
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  *(_DWORD *)(v3 + 16) = 0;
  if ( !InitSafeBootMode && *(_DWORD *)(*((_QWORD *)DeviceExtension + 65) + 28LL) != 20 )
  {
    WorkItem = IoAllocateWorkItem(DeviceObject);
    if ( WorkItem )
      IoQueueWorkItem(WorkItem, DiskInitializeFailurePrediction, DelayedWorkQueue, WorkItem);
  }
  KeInitializeMutex((PRKMUTEX)(v3 + 56), 0x100u);
  memset((void *)(v3 + 112), 0, 0x198u);
  *(_QWORD *)(v3 + 120) = v3 + 112;
  *(_QWORD *)(v3 + 112) = v3 + 112;
  *(_QWORD *)(v3 + 144) = v3 + 136;
  *(_QWORD *)(v3 + 136) = v3 + 136;
  KeInitializeSpinLock((PKSPIN_LOCK)(v3 + 472));
  KeInitializeEvent((PRKEVENT)(v3 + 480), SynchronizationEvent, 0);
  *(_QWORD *)(v3 + 504) = IoAllocateIrp(DeviceObject->StackSize + 3, 0);
  result = 0;
  *(_BYTE *)(v3 + 512) = 0;
  *((_DWORD *)DeviceExtension + 148) = v11;
  return result;
}

```

## disassembly

```asm
0x140011820  push    rbx
0x140011822  push    rbp
0x140011823  push    rsi
0x140011824  push    rdi
0x140011825  push    r14
0x140011827  push    r15
0x140011829  sub     rsp, 88h
0x140011830  mov     rdi, [rcx+40h]
0x140011834  mov     rsi, rcx
0x140011837  mov     r14d, 4
0x14001183d  mov     rcx, rdi; CommonExtension
0x140011840  mov     edx, r14d; NumberElements
0x140011843  mov     rbp, [rdi+60h]
0x140011847  call    cs:__imp_ClassInitializeSrbLookasideList
0x14001184e  nop     dword ptr [rax+rax+00h]
0x140011853  mov     rax, [rdi+208h]
0x14001185a  xor     r15d, r15d
0x14001185d  cmp     [rax+0Ah], r15b
0x140011861  jz      short loc_140011867
0x140011863  or      dword ptr [rsi+34h], 1
0x140011867  mov     rax, [rdi+208h]
0x14001186e  bts     dword ptr [rdi+250h], 15h
0x140011876  cmp     [rax+0Bh], r15b
0x14001187a  jz      short loc_140011890
0x14001187c  mov     rax, [rdi+210h]
0x140011883  cmp     [rax+16h], r15b
0x140011887  jz      short loc_140011890
0x140011889  or      dword ptr [rdi+250h], 2
0x140011890  lea     r8, DiskSetSpecialHacks; Function
0x140011897  mov     rcx, rdi; FdoExtension
0x14001189a  lea     rdx, DiskBadControllers; DeviceList
0x1400118a1  call    cs:__imp_ClassScanForSpecial
0x1400118a8  nop     dword ptr [rax+rax+00h]
0x1400118ad  xor     eax, eax
0x1400118af  xorps   xmm0, xmm0
0x1400118b2  movups  xmmword ptr [rdi+228h], xmm0
0x1400118b9  mov     r8d, 73446353h
0x1400118bf  mov     [rdi+238h], rax
0x1400118c6  lea     edx, [rax+12h]
0x1400118c9  lea     ecx, [rax+48h]
0x1400118cc  call    cs:__imp_ExAllocatePool2
0x1400118d3  nop     dword ptr [rax+rax+00h]
0x1400118d8  mov     [rdi+240h], rax
0x1400118df  test    rax, rax
0x1400118e2  jnz     short loc_140011923
0x1400118e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118eb  lea     rax, WPP_GLOBAL_Control
0x1400118f2  cmp     rcx, rax
0x1400118f5  jz      short loc_140011919
0x1400118f7  mov     eax, [rcx+2Ch]
0x1400118fa  test    al, 2
0x1400118fc  jz      short loc_140011919
0x1400118fe  cmp     byte ptr [rcx+29h], 2
0x140011902  jb      short loc_140011919
0x140011904  mov     rcx, [rcx+18h]
0x140011908  lea     r8, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids
0x14001190f  mov     edx, 0Eh
0x140011914  call    WPP_SF_
0x140011919  mov     eax, 0C000009Ah
0x14001191e  jmp     loc_140011BA4
0x140011923  mov     rax, [rdi+488h]
0x14001192a  mov     byte ptr [rdi+225h], 12h
0x140011931  mov     [rdi+98h], r15
0x140011938  test    rax, rax
0x14001193b  jz      short loc_140011946
0x14001193d  movzx   ecx, word ptr [rax+0Eh]
0x140011941  test    cx, cx
0x140011944  jnz     short loc_14001195F
0x140011946  mov     rcx, rsi; DeviceObject
0x140011949  call    cs:__imp_ClassQueryTimeOutRegistryValue
0x140011950  nop     dword ptr [rax+rax+00h]
0x140011955  test    eax, eax
0x140011957  mov     ecx, 0Ah
0x14001195c  cmovnz  ecx, eax
0x14001195f  mov     [rdi+248h], ecx
0x140011965  mov     ebx, 100h
0x14001196a  mov     eax, [rsi+34h]
0x14001196d  test    al, 1
0x14001196f  jz      short loc_1400119C4
0x140011971  mov     r8d, [rdi+24Ch]; DeviceNumber
0x140011978  lea     rdx, DeviceName; "PhysicalDrive"
0x14001197f  xor     r9d, r9d; InquiryData
0x140011982  mov     [rsp+0B8h+InquiryDataLength], r15d; InquiryDataLength
0x140011987  mov     rcx, rsi; Fdo
0x14001198a  call    cs:__imp_ClassUpdateInformationInRegistry
0x140011991  nop     dword ptr [rax+rax+00h]
0x140011996  lea     rdx, EventPrefix; "Disk"
0x14001199d  mov     rcx, rdi; FdoExtension
0x1400119a0  call    cs:__imp_ClassInitializeMediaChangeDetection
0x1400119a7  nop     dword ptr [rax+rax+00h]
0x1400119ac  mov     rax, [rdi+208h]
0x1400119b3  cmp     dword ptr [rax+1Ch], 7
0x1400119b7  jnz     short loc_1400119DC
0x1400119b9  mov     al, [rax+9]
0x1400119bc  and     al, 0F0h
0x1400119be  cmp     al, 10h
0x1400119c0  jnz     short loc_1400119DC
0x1400119c2  jmp     short loc_1400119D6
0x1400119c4  movzx   eax, word ptr [rdi+280h]
0x1400119cb  or      ax, r14w
0x1400119cf  mov     [rdi+280h], ax
0x1400119d6  or      [rdi+250h], ebx
0x1400119dc  mov     r14d, [rdi+250h]
0x1400119e3  mov     rcx, rsi; DeviceObject
0x1400119e6  call    cs:__imp_ClassReadDriveCapacity
0x1400119ed  nop     dword ptr [rax+rax+00h]
0x1400119f2  cmp     [rdi+23Ch], r15d
0x1400119f9  jnz     short loc_140011A0C
0x1400119fb  mov     dword ptr [rdi+23Ch], 200h
0x140011a05  mov     byte ptr [rdi+282h], 9
0x140011a0c  mov     rcx, rsi
0x140011a0f  call    DiskCreateSymbolicLinks
0x140011a14  xor     eax, eax
0x140011a16  lea     rcx, [rsp+0B8h+Event]; Event
0x140011a1b  xorps   xmm0, xmm0
0x140011a1e  mov     [rsp+0B8h+Event.Header.WaitListHead.Blink], rax
0x140011a23  xor     r8d, r8d; State
0x140011a26  movups  xmmword ptr [rsp+0B8h+Event.Header], xmm0
0x140011a2b  lea     edx, [rax+1]; Type
0x140011a2e  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x140011a33  call    cs:__imp_KeInitializeEvent
0x140011a3a  nop     dword ptr [rax+rax+00h]
0x140011a3f  mov     rdx, [rdi+10h]; DeviceObject
0x140011a43  lea     rcx, [rsp+0B8h+var_68]
0x140011a48  mov     [rsp+0B8h+IoStatusBlock], rcx; IoStatusBlock
0x140011a4d  lea     rax, [rbp+8]
0x140011a51  lea     rcx, [rsp+0B8h+Event]
0x140011a56  xor     r9d, r9d; InputBufferLength
0x140011a59  mov     [rsp+0B8h+var_80], rcx; Event
0x140011a5e  xor     r8d, r8d; InputBuffer
0x140011a61  mov     [rsp+0B8h+InternalDeviceIoControl], r15b; InternalDeviceIoControl
0x140011a66  mov     ecx, 41018h; IoControlCode
0x140011a6b  mov     [rsp+0B8h+OutputBufferLength], 8; OutputBufferLength
0x140011a73  mov     qword ptr [rsp+0B8h+InquiryDataLength], rax; OutputBuffer
0x140011a78  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140011a7f  nop     dword ptr [rax+rax+00h]
0x140011a84  test    rax, rax
0x140011a87  jz      short loc_140011AC1
0x140011a89  mov     rcx, [rdi+10h]; DeviceObject
0x140011a8d  mov     rdx, rax; Irp
0x140011a90  call    cs:__imp_IofCallDriver
0x140011a97  nop     dword ptr [rax+rax+00h]
0x140011a9c  cmp     eax, 103h
0x140011aa1  jnz     short loc_140011AC1
0x140011aa3  xor     r9d, r9d; Alertable
0x140011aa6  mov     qword ptr [rsp+0B8h+InquiryDataLength], r15; Timeout
0x140011aab  xor     r8d, r8d; WaitMode
0x140011aae  lea     rcx, [rsp+0B8h+Event]; Object
0x140011ab3  xor     edx, edx; WaitReason
0x140011ab5  call    cs:__imp_KeWaitForSingleObject
0x140011abc  nop     dword ptr [rax+rax+00h]
0x140011ac1  mov     rax, cs:__imp_InitSafeBootMode
0x140011ac8  mov     [rbp+10h], r15d
0x140011acc  cmp     [rax], r15d
0x140011acf  jnz     short loc_140011B11
0x140011ad1  mov     rax, [rdi+208h]
0x140011ad8  cmp     dword ptr [rax+1Ch], 14h
0x140011adc  jz      short loc_140011B11
0x140011ade  mov     rcx, rsi; DeviceObject
0x140011ae1  call    cs:__imp_IoAllocateWorkItem
0x140011ae8  nop     dword ptr [rax+rax+00h]
0x140011aed  test    rax, rax
0x140011af0  jz      short loc_140011B11
0x140011af2  mov     r9, rax; Context
0x140011af5  lea     rdx, DiskInitializeFailurePrediction; WorkerRoutine
0x140011afc  mov     r8d, 1; QueueType
0x140011b02  mov     rcx, rax; IoWorkItem
0x140011b05  call    cs:__imp_IoQueueWorkItem
0x140011b0c  nop     dword ptr [rax+rax+00h]
0x140011b11  lea     rcx, [rbp+38h]; Mutex
0x140011b15  mov     edx, ebx; Level
0x140011b17  call    cs:__imp_KeInitializeMutex
0x140011b1e  nop     dword ptr [rax+rax+00h]
0x140011b23  lea     rbx, [rbp+70h]
0x140011b27  xor     edx, edx; Val
0x140011b29  mov     rcx, rbx; void *
0x140011b2c  mov     r8d, 198h; Size
0x140011b32  call    memset
0x140011b37  lea     rax, [rbp+88h]
0x140011b3e  mov     [rbx+8], rbx
0x140011b42  mov     [rbx], rbx
0x140011b45  lea     rcx, [rbp+1D8h]; SpinLock
0x140011b4c  mov     [rax+8], rax
0x140011b50  mov     [rax], rax
0x140011b53  call    cs:__imp_KeInitializeSpinLock
0x140011b5a  nop     dword ptr [rax+rax+00h]
0x140011b5f  xor     r8d, r8d; State
0x140011b62  lea     rcx, [rbp+1E0h]; Event
0x140011b69  lea     edx, [r8+1]; Type
0x140011b6d  call    cs:__imp_KeInitializeEvent
0x140011b74  nop     dword ptr [rax+rax+00h]
0x140011b79  mov     cl, [rsi+4Ch]
0x140011b7c  xor     edx, edx; ChargeQuota
0x140011b7e  add     cl, 3; StackSize
0x140011b81  call    cs:__imp_IoAllocateIrp
0x140011b88  nop     dword ptr [rax+rax+00h]
0x140011b8d  mov     [rbp+1F8h], rax
0x140011b94  xor     eax, eax
0x140011b96  mov     [rbp+200h], r15b
0x140011b9d  mov     [rdi+250h], r14d
0x140011ba4  add     rsp, 88h
0x140011bab  pop     r15
0x140011bad  pop     r14
0x140011baf  pop     rdi
0x140011bb0  pop     rsi
0x140011bb1  pop     rbp
0x140011bb2  pop     rbx
0x140011bb3  retn
```
