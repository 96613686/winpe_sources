# DpiFdoHandleRemoveDevice

- ea: `0x1402ace50`
- end: `0x1402ad29f`
- name: `DpiFdoHandleRemoveDevice`
- size: `1103`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callees

- `0x140040908`
- `0x14004094c`
- `0x140047b0c`
- `0x140055744`
- `0x14008cd70`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14019b644`
- `0x1401cda84`
- `0x1402ace50`
- `0x1402adc90`
- `0x1402b1eb8`
- `0x1402c3144`
- `0x1402c4274`
- `0x1402c49e0`
- `0x14030cdb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402acfea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad032`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad059`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad08b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402acfea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad032`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad059`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad08b`
- `ntoskrnl!IoFreeWorkItem` at `0x1402ad0f1`
- `ntoskrnl!IoFreeWorkItem` at `0x1402ad0f1`
- `ntoskrnl!ExDeleteResourceLite` at `0x1402acfd0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1402acfd0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402ad1cc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402ad1df`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402ad1cc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402ad1df`
- `ntoskrnl!IofCallDriver` at `0x1402ad21c`
- `ntoskrnl!IofCallDriver` at `0x1402ad21c`
- `ntoskrnl!IoDeleteDevice` at `0x1402ad27c`
- `ntoskrnl!IoDeleteDevice` at `0x1402ad27c`
- `ntoskrnl!KeSetEvent` at `0x1402ad1f7`
- `ntoskrnl!KeSetEvent` at `0x1402ad1f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402acf8f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402acf8f`
- `ntoskrnl!KeReleaseMutex` at `0x1402ad0ac`
- `ntoskrnl!KeReleaseMutex` at `0x1402ad0ac`
- `ntoskrnl!IoDetachDevice` at `0x1402ad26d`
- `ntoskrnl!IoDetachDevice` at `0x1402ad26d`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402acefb`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402acefb`
- `watchdog!WdLogSingleEntry1` at `0x1402ace87`
- `watchdog!WdLogSingleEntry1` at `0x1402ace87`

## pseudocode

```c
__int64 __fastcall DpiFdoHandleRemoveDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rbx
  __int64 v5; // r14
  int v6; // eax
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  PVOID *v9; // rax
  __int64 v10; // rcx
  void *v11; // rcx
  _DWORD *v12; // rcx
  _DWORD *v13; // rcx
  void *v14; // rcx
  int v15; // eax
  struct _IO_WORKITEM *v16; // rcx
  void (__fastcall *v17)(_QWORD); // rax
  void (__fastcall *v18)(_QWORD); // rax
  void (__fastcall *v19)(_QWORD); // rax
  void (__fastcall *v20)(_QWORD); // rax
  unsigned int v21; // ebp
  PVOID v22; // rsi
  struct SYSMM_ADAPTER *v23; // rcx

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v5 = *((_QWORD *)DeviceExtension + 5);
  AcquireMiniportListMutex();
  if ( (PDEVICE_OBJECT)qword_1401630F8 == DeviceObject )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 7025;
    qword_1401630F8 = 0;
  }
  ReleaseMiniportListMutex();
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 )
  {
    if ( (unsigned int)(*((_DWORD *)DeviceExtension + 5) - 2) <= 1
      && (unsigned int)(*((_DWORD *)DeviceExtension + 60) - 1) <= 1 )
    {
      DpiFdoHandleStopDevice(DeviceObject, Irp);
    }
    if ( *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
      DpiPdoDestroyPendingPdoObjects(DeviceObject);
  }
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)DeviceExtension + 2, Irp, 0x20u);
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
    DpiFdoRemoveChildDescriptors(DeviceObject);
  *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244] = *((_DWORD *)DeviceExtension + 60);
  v6 = *((_DWORD *)DeviceExtension + 59);
  ++*((_DWORD *)DeviceExtension + 69);
  *((_DWORD *)DeviceExtension + 60) = v6;
  *((_DWORD *)DeviceExtension + 59) = 7;
  AcquireMiniportListMutex();
  if ( (unsigned __int8)DpiFdoIsPostDevice(DeviceObject) )
    qword_140163100 = 0;
  if ( (unsigned __int8)DpiFdoIsMsBddAnchoredDevice(v7) )
    qword_1401631A8 = 0;
  ReleaseMiniportListMutex();
  KeWaitForSingleObject((PVOID)(v5 + 72), Executive, 0, 0, 0);
  v8 = *(_QWORD **)DeviceExtension;
  if ( *(char **)(*(_QWORD *)DeviceExtension + 8LL) != DeviceExtension
    || (v9 = (PVOID *)*((_QWORD *)DeviceExtension + 1), *v9 != DeviceExtension) )
  {
    __fastfail(3u);
  }
  *v9 = v8;
  v8[1] = v9;
  --*(_DWORD *)(v5 + 128);
  v10 = *((_QWORD *)DeviceExtension + 21);
  if ( *(_DWORD *)(v10 + 104) == 1 )
  {
    ExDeleteResourceLite((PERESOURCE)v10);
    v11 = (void *)*((_QWORD *)DeviceExtension + 21);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0);
      *((_QWORD *)DeviceExtension + 21) = 0;
    }
  }
  if ( DeviceExtension
    && *((_DWORD *)DeviceExtension + 4) == 1953656900
    && (unsigned int)(*((_DWORD *)DeviceExtension + 5) - 2) <= 1 )
  {
    v12 = (_DWORD *)*((_QWORD *)DeviceExtension + 185);
    if ( v12[2] == 1 && v12 )
    {
      ExFreePoolWithTag(v12, 0);
      *((_QWORD *)DeviceExtension + 185) = 0;
    }
    v13 = (_DWORD *)*((_QWORD *)DeviceExtension + 186);
    if ( v13[2] == 1 && v13 )
    {
      ExFreePoolWithTag(v13, 0);
      *((_QWORD *)DeviceExtension + 186) = 0;
    }
    if ( *((_DWORD *)DeviceExtension + 126) )
      DpiLdaUnLinkDeviceFromChain(DeviceObject);
    v14 = (void *)*((_QWORD *)DeviceExtension + 139);
    if ( v14 )
    {
      ExFreePoolWithTag(v14, 0);
      *((_QWORD *)DeviceExtension + 139) = 0;
    }
    DpiCheckSpbResourceLeakage(DeviceExtension);
  }
  KeReleaseMutex((PRKMUTEX)(v5 + 72), 0);
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 )
  {
    v15 = *((_DWORD *)DeviceExtension + 5);
    if ( v15 == 2 )
    {
      DpiFdoResetFdo(DeviceObject);
    }
    else if ( v15 != 3 )
    {
      goto LABEL_57;
    }
    v16 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 346);
    if ( v16 )
    {
      IoFreeWorkItem(v16);
      *((_QWORD *)DeviceExtension + 346) = 0;
    }
    if ( DeviceExtension[1157] == 1 )
      DpiAcpiUnregisterAcpiCallbacks(DeviceObject);
    v17 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 73);
    if ( v17 )
    {
      v17(*((_QWORD *)DeviceExtension + 71));
      memset(DeviceExtension + 560, 0, 0x40u);
    }
    v18 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 81);
    if ( v18 )
    {
      v18(*((_QWORD *)DeviceExtension + 79));
      *((_OWORD *)DeviceExtension + 39) = 0;
      *((_OWORD *)DeviceExtension + 40) = 0;
      *((_OWORD *)DeviceExtension + 41) = 0;
    }
    v19 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 87);
    if ( v19 )
    {
      v19(*((_QWORD *)DeviceExtension + 85));
      memset(DeviceExtension + 672, 0, 0xB8u);
    }
    v20 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 110);
    if ( v20 )
    {
      v20(*((_QWORD *)DeviceExtension + 108));
      memset(DeviceExtension + 856, 0, 0x58u);
    }
    RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 32);
    RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 33);
    KeSetEvent((PRKEVENT)(DeviceExtension + 1288), 0, 0);
  }
LABEL_57:
  ++Irp->CurrentLocation;
  ++Irp->Tail.Overlay.CurrentStackLocation;
  Irp->IoStatus.Status = 0;
  v21 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 20), Irp);
  DpiDxgkDdiRemoveDevice(v5, *((_QWORD *)DeviceExtension + 6));
  if ( DeviceExtension )
  {
    if ( *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
    {
      v22 = DeviceObject->DeviceExtension;
      v23 = (struct SYSMM_ADAPTER *)*((_QWORD *)v22 + 728);
      if ( v23 )
      {
        SysMmDestroyAdapter(v23);
        *((_QWORD *)v22 + 728) = 0;
      }
    }
  }
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 20));
  IoDeleteDevice(DeviceObject);
  return v21;
}

```

## disassembly

```asm
0x1402ace50  push    rbx
0x1402ace52  push    rbp
0x1402ace53  push    rsi
0x1402ace54  push    rdi
0x1402ace55  push    r14
0x1402ace57  push    r15
0x1402ace59  sub     rsp, 38h
0x1402ace5d  mov     rbx, [rcx+40h]
0x1402ace61  mov     rbp, rdx
0x1402ace64  mov     rdi, rcx
0x1402ace67  mov     r14, [rbx+28h]
0x1402ace6b  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402ace70  xor     r15d, r15d
0x1402ace73  cmp     cs:qword_1401630F8, rdi
0x1402ace7a  jnz     short loc_1402ACEA4
0x1402ace7c  mov     rdx, 0FFFFFFFFC00000BBh
0x1402ace83  lea     ecx, [r15+2]
0x1402ace87  call    cs:__imp_WdLogSingleEntry1
0x1402ace8e  nop     dword ptr [rax+rax+00h]
0x1402ace93  mov     cs:WdLogGlobalForLineNumber, 1B71h
0x1402ace9d  mov     cs:qword_1401630F8, r15
0x1402acea4  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402acea9  mov     esi, 74727044h
0x1402aceae  test    rbx, rbx
0x1402aceb1  jz      short loc_1402ACEEE
0x1402aceb3  cmp     [rbx+10h], esi
0x1402aceb6  jnz     short loc_1402ACEEE
0x1402aceb8  mov     eax, [rbx+14h]
0x1402acebb  sub     eax, 2
0x1402acebe  cmp     eax, 1
0x1402acec1  ja      short loc_1402ACEDB
0x1402acec3  mov     eax, [rbx+0F0h]
0x1402acec9  dec     eax
0x1402acecb  cmp     eax, 1
0x1402acece  ja      short loc_1402ACEDB
0x1402aced0  mov     rdx, rbp
0x1402aced3  mov     rcx, rdi
0x1402aced6  call    DpiFdoHandleStopDevice
0x1402acedb  cmp     [rbx+10h], esi
0x1402acede  jnz     short loc_1402ACEEE
0x1402acee0  cmp     dword ptr [rbx+14h], 2
0x1402acee4  jnz     short loc_1402ACEEE
0x1402acee6  mov     rcx, rdi
0x1402acee9  call    DpiPdoDestroyPendingPdoObjects
0x1402aceee  lea     rcx, [rbx+40h]; RemoveLock
0x1402acef2  mov     r8d, 20h ; ' '; RemlockSize
0x1402acef8  mov     rdx, rbp; Tag
0x1402acefb  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1402acf02  nop     dword ptr [rax+rax+00h]
0x1402acf07  test    rbx, rbx
0x1402acf0a  jz      short loc_1402ACF1F
0x1402acf0c  cmp     [rbx+10h], esi
0x1402acf0f  jnz     short loc_1402ACF1F
0x1402acf11  cmp     dword ptr [rbx+14h], 2
0x1402acf15  jnz     short loc_1402ACF1F
0x1402acf17  mov     rcx, rdi
0x1402acf1a  call    DpiFdoRemoveChildDescriptors
0x1402acf1f  mov     ecx, [rbx+114h]
0x1402acf25  mov     eax, [rbx+0F0h]
0x1402acf2b  and     ecx, 7
0x1402acf2e  mov     [rbx+rcx*4+0F4h], eax
0x1402acf35  mov     eax, [rbx+0ECh]
0x1402acf3b  inc     dword ptr [rbx+114h]
0x1402acf41  mov     [rbx+0F0h], eax
0x1402acf47  mov     dword ptr [rbx+0ECh], 7
0x1402acf51  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402acf56  mov     rcx, rdi
0x1402acf59  call    DpiFdoIsPostDevice
0x1402acf5e  test    al, al
0x1402acf60  jz      short loc_1402ACF69
0x1402acf62  mov     cs:qword_140163100, r15
0x1402acf69  call    DpiFdoIsMsBddAnchoredDevice
0x1402acf6e  test    al, al
0x1402acf70  jz      short loc_1402ACF79
0x1402acf72  mov     cs:qword_1401631A8, r15
0x1402acf79  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402acf7e  xor     r9d, r9d; Alertable
0x1402acf81  mov     [rsp+68h+Timeout], r15; Timeout
0x1402acf86  xor     r8d, r8d; WaitMode
0x1402acf89  lea     rcx, [r14+48h]; Object
0x1402acf8d  xor     edx, edx; WaitReason
0x1402acf8f  call    cs:__imp_KeWaitForSingleObject
0x1402acf96  nop     dword ptr [rax+rax+00h]
0x1402acf9b  mov     rcx, [rbx]
0x1402acf9e  cmp     [rcx+8], rbx
0x1402acfa2  jnz     loc_1402AD298
0x1402acfa8  mov     rax, [rbx+8]
0x1402acfac  cmp     [rax], rbx
0x1402acfaf  jnz     loc_1402AD298
0x1402acfb5  mov     [rax], rcx
0x1402acfb8  mov     [rcx+8], rax
0x1402acfbc  dec     dword ptr [r14+80h]
0x1402acfc3  mov     rcx, [rbx+0A8h]; Resource
0x1402acfca  cmp     dword ptr [rcx+68h], 1
0x1402acfce  jnz     short loc_1402ACFFD
0x1402acfd0  call    cs:__imp_ExDeleteResourceLite
0x1402acfd7  nop     dword ptr [rax+rax+00h]
0x1402acfdc  mov     rcx, [rbx+0A8h]; P
0x1402acfe3  test    rcx, rcx
0x1402acfe6  jz      short loc_1402ACFFD
0x1402acfe8  xor     edx, edx; Tag
0x1402acfea  call    cs:__imp_ExFreePoolWithTag
0x1402acff1  nop     dword ptr [rax+rax+00h]
0x1402acff6  mov     [rbx+0A8h], r15
0x1402acffd  test    rbx, rbx
0x1402ad000  jz      loc_1402AD0A6
0x1402ad006  cmp     [rbx+10h], esi
0x1402ad009  jnz     loc_1402AD0A6
0x1402ad00f  mov     eax, [rbx+14h]
0x1402ad012  sub     eax, 2
0x1402ad015  cmp     eax, 1
0x1402ad018  ja      loc_1402AD0A6
0x1402ad01e  mov     rcx, [rbx+5C8h]; P
0x1402ad025  cmp     dword ptr [rcx+8], 1
0x1402ad029  jnz     short loc_1402AD045
0x1402ad02b  test    rcx, rcx
0x1402ad02e  jz      short loc_1402AD045
0x1402ad030  xor     edx, edx; Tag
0x1402ad032  call    cs:__imp_ExFreePoolWithTag
0x1402ad039  nop     dword ptr [rax+rax+00h]
0x1402ad03e  mov     [rbx+5C8h], r15
0x1402ad045  mov     rcx, [rbx+5D0h]; P
0x1402ad04c  cmp     dword ptr [rcx+8], 1
0x1402ad050  jnz     short loc_1402AD06C
0x1402ad052  test    rcx, rcx
0x1402ad055  jz      short loc_1402AD06C
0x1402ad057  xor     edx, edx; Tag
0x1402ad059  call    cs:__imp_ExFreePoolWithTag
0x1402ad060  nop     dword ptr [rax+rax+00h]
0x1402ad065  mov     [rbx+5D0h], r15
0x1402ad06c  cmp     [rbx+1F8h], r15d
0x1402ad073  jz      short loc_1402AD07D
0x1402ad075  mov     rcx, rdi
0x1402ad078  call    DpiLdaUnLinkDeviceFromChain
0x1402ad07d  mov     rcx, [rbx+458h]; P
0x1402ad084  test    rcx, rcx
0x1402ad087  jz      short loc_1402AD09E
0x1402ad089  xor     edx, edx; Tag
0x1402ad08b  call    cs:__imp_ExFreePoolWithTag
0x1402ad092  nop     dword ptr [rax+rax+00h]
0x1402ad097  mov     [rbx+458h], r15
0x1402ad09e  mov     rcx, rbx
0x1402ad0a1  call    DpiCheckSpbResourceLeakage
0x1402ad0a6  xor     edx, edx; Wait
0x1402ad0a8  lea     rcx, [r14+48h]; Mutex
0x1402ad0ac  call    cs:__imp_KeReleaseMutex
0x1402ad0b3  nop     dword ptr [rax+rax+00h]
0x1402ad0b8  test    rbx, rbx
0x1402ad0bb  jz      loc_1402AD203
0x1402ad0c1  cmp     [rbx+10h], esi
0x1402ad0c4  jnz     loc_1402AD203
0x1402ad0ca  mov     eax, [rbx+14h]
0x1402ad0cd  cmp     eax, 2
0x1402ad0d0  jz      short loc_1402AD0DD
0x1402ad0d2  cmp     eax, 3
0x1402ad0d5  jnz     loc_1402AD203
0x1402ad0db  jmp     short loc_1402AD0E5
0x1402ad0dd  mov     rcx, rdi
0x1402ad0e0  call    DpiFdoResetFdo
0x1402ad0e5  mov     rcx, [rbx+0AD0h]; IoWorkItem
0x1402ad0ec  test    rcx, rcx
0x1402ad0ef  jz      short loc_1402AD104
0x1402ad0f1  call    cs:__imp_IoFreeWorkItem
0x1402ad0f8  nop     dword ptr [rax+rax+00h]
0x1402ad0fd  mov     [rbx+0AD0h], r15
0x1402ad104  cmp     byte ptr [rbx+485h], 1
0x1402ad10b  jnz     short loc_1402AD115
0x1402ad10d  mov     rcx, rdi
0x1402ad110  call    DpiAcpiUnregisterAcpiCallbacks
0x1402ad115  lea     rsi, [rbx+230h]
0x1402ad11c  mov     rax, [rsi+18h]
0x1402ad120  test    rax, rax
0x1402ad123  jz      short loc_1402AD13F
0x1402ad125  mov     rcx, [rbx+238h]
0x1402ad12c  call    _guard_dispatch_icall
0x1402ad131  xor     edx, edx; Val
0x1402ad133  mov     rcx, rsi; void *
0x1402ad136  lea     r8d, [rdx+40h]; Size
0x1402ad13a  call    memset
0x1402ad13f  mov     rax, [rbx+288h]
0x1402ad146  test    rax, rax
0x1402ad149  jz      short loc_1402AD16F
0x1402ad14b  mov     rcx, [rbx+278h]
0x1402ad152  call    _guard_dispatch_icall
0x1402ad157  xorps   xmm0, xmm0
0x1402ad15a  movups  xmmword ptr [rbx+270h], xmm0
0x1402ad161  movups  xmmword ptr [rbx+280h], xmm0
0x1402ad168  movups  xmmword ptr [rbx+290h], xmm0
0x1402ad16f  lea     rsi, [rbx+2A0h]
0x1402ad176  mov     rax, [rsi+18h]
0x1402ad17a  test    rax, rax
0x1402ad17d  jz      short loc_1402AD19B
0x1402ad17f  mov     rcx, [rbx+2A8h]
0x1402ad186  call    _guard_dispatch_icall
0x1402ad18b  xor     edx, edx; Val
0x1402ad18d  mov     r8d, 0B8h; Size
0x1402ad193  mov     rcx, rsi; void *
0x1402ad196  call    memset
0x1402ad19b  lea     rsi, [rbx+358h]
0x1402ad1a2  mov     rax, [rsi+18h]
0x1402ad1a6  test    rax, rax
0x1402ad1a9  jz      short loc_1402AD1C5
0x1402ad1ab  mov     rcx, [rbx+360h]
0x1402ad1b2  call    _guard_dispatch_icall
0x1402ad1b7  xor     edx, edx; Val
0x1402ad1b9  mov     rcx, rsi; void *
0x1402ad1bc  lea     r8d, [rdx+58h]; Size
0x1402ad1c0  call    memset
0x1402ad1c5  lea     rcx, [rbx+200h]; UnicodeString
0x1402ad1cc  call    cs:__imp_RtlFreeUnicodeString
0x1402ad1d3  nop     dword ptr [rax+rax+00h]
0x1402ad1d8  lea     rcx, [rbx+210h]; UnicodeString
0x1402ad1df  call    cs:__imp_RtlFreeUnicodeString
0x1402ad1e6  nop     dword ptr [rax+rax+00h]
0x1402ad1eb  lea     rcx, [rbx+508h]; Event
0x1402ad1f2  xor     r8d, r8d; Wait
0x1402ad1f5  xor     edx, edx; Increment
0x1402ad1f7  call    cs:__imp_KeSetEvent
0x1402ad1fe  nop     dword ptr [rax+rax+00h]
0x1402ad203  inc     byte ptr [rbp+43h]
0x1402ad206  mov     rdx, rbp; Irp
0x1402ad209  add     qword ptr [rbp+0B8h], 48h ; 'H'
0x1402ad211  mov     [rbp+30h], r15d
0x1402ad215  mov     rcx, [rbx+0A0h]; DeviceObject
0x1402ad21c  call    cs:__imp_IofCallDriver
0x1402ad223  nop     dword ptr [rax+rax+00h]
0x1402ad228  mov     rdx, [rbx+30h]
0x1402ad22c  mov     rcx, r14
0x1402ad22f  mov     ebp, eax
0x1402ad231  call    DpiDxgkDdiRemoveDevice
0x1402ad236  test    rbx, rbx
0x1402ad239  jz      short loc_1402AD266
0x1402ad23b  cmp     dword ptr [rbx+10h], 74727044h
0x1402ad242  jnz     short loc_1402AD266
0x1402ad244  cmp     dword ptr [rbx+14h], 2
0x1402ad248  jnz     short loc_1402AD266
0x1402ad24a  mov     rsi, [rdi+40h]
0x1402ad24e  mov     rcx, [rsi+16C0h]; struct SYSMM_ADAPTER *
0x1402ad255  test    rcx, rcx
0x1402ad258  jz      short loc_1402AD266
0x1402ad25a  call    ?SysMmDestroyAdapter@@YAXPEAUSYSMM_ADAPTER@@@Z; SysMmDestroyAdapter(SYSMM_ADAPTER *)
0x1402ad25f  mov     [rsi+16C0h], r15
0x1402ad266  mov     rcx, [rbx+0A0h]; TargetDevice
0x1402ad26d  call    cs:__imp_IoDetachDevice
0x1402ad274  nop     dword ptr [rax+rax+00h]
0x1402ad279  mov     rcx, rdi; DeviceObject
0x1402ad27c  call    cs:__imp_IoDeleteDevice
0x1402ad283  nop     dword ptr [rax+rax+00h]
0x1402ad288  mov     eax, ebp
0x1402ad28a  add     rsp, 38h
0x1402ad28e  pop     r15
0x1402ad290  pop     r14
0x1402ad292  pop     rdi
0x1402ad293  pop     rsi
0x1402ad294  pop     rbp
0x1402ad295  pop     rbx
0x1402ad296  retn
0x1402ad298  mov     ecx, 3
0x1402ad29d  int     29h; Win8: RtlFailFast(ecx)
```
