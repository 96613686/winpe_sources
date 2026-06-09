# DiskAddDevice

- ea: `0x140015030`
- end: `0x14001533c`
- name: `DiskAddDevice`
- size: `780`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1400043dc`
- `0x140005834`
- `0x140005890`
- `0x140005c30`
- `0x140006000`
- `0x140015030`
- `0x140015350`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001515c`
- `ntoskrnl!ZwClose` at `0x140015286`
- `ntoskrnl!ZwClose` at `0x14001515c`
- `ntoskrnl!ZwClose` at `0x140015286`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400150a3`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400150a3`
- `ntoskrnl!IoGetConfigurationInformation` at `0x1400152fd`
- `ntoskrnl!IoGetConfigurationInformation` at `0x1400152fd`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140015229`
- `ntoskrnl!ZwOpenKey` at `0x140015149`
- `ntoskrnl!ZwOpenKey` at `0x140015149`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140015209`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140015209`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015102`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400151f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015102`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400151f8`

## string_xrefs

- `0x1400151ce`: `RtlQueryRegistryValuesEx`
- `0x1400151c3`: `RootPartitionMountable`

## pseudocode

```c
__int64 __fastcall DiskAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  NTSTATUS v4; // eax
  __int64 v5; // r8
  __int64 Timer_high; // rdx
  NTSTATUS v7; // r14d
  __int64 v8; // r8
  void *v9; // rbx
  PVOID SystemRoutineAddress; // rax
  __int64 v11; // r8
  int v12; // r14d
  __int16 *v13; // r9
  int Fdo; // ebx
  PCONFIGURATION_INFORMATION ConfigurationInformation; // rax
  void *DestinationString; // [rsp+38h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString_8; // [rsp+40h] [rbp-C8h] BYREF
  struct _UNICODE_STRING SystemRoutineName_8; // [rsp+50h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v21[14]; // [rsp+98h] [rbp-70h] BYREF
  int v22; // [rsp+148h] [rbp+40h] BYREF
  void *DeviceRegKey; // [rsp+150h] [rbp+48h] BYREF

  v22 = 0;
  DeviceRegKey = 0;
  DestinationString = 0;
  DestinationString_8 = 0;
  memset(&ObjectAttributes_8, 0, sizeof(ObjectAttributes_8));
  memset(v21, 0, sizeof(v21));
  v4 = IoOpenDeviceRegistryKey(TargetDevice, 1u, 0x20019u, &DeviceRegKey);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Lq(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v5, (unsigned int)v4, TargetDevice);
    }
LABEL_19:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v13 = word_14000896A;
      if ( !v22 )
        v13 = (__int16 *)"not ";
      WPP_SF_sq(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        (unsigned int)WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids,
        (_DWORD)v13,
        (char)TargetDevice);
    }
    goto LABEL_25;
  }
  RtlInitUnicodeString(&DestinationString_8, L"Disk");
  ObjectAttributes_8.RootDirectory = DeviceRegKey;
  ObjectAttributes_8.Length = 48;
  ObjectAttributes_8.ObjectName = &DestinationString_8;
  ObjectAttributes_8.Attributes = 576;
  *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&DestinationString, 0x20019u, &ObjectAttributes_8);
  ZwClose(DeviceRegKey);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Lqq(WPP_GLOBAL_Control->AttachedDevice, 11, v8, (unsigned int)v7, TargetDevice, DeviceRegKey);
    }
    goto LABEL_19;
  }
  v9 = DestinationString;
  v21[2] = L"RootPartitionMountable";
  LODWORD(v21[1]) = 288;
  v21[3] = &v22;
  LODWORD(v21[4]) = 0x4000000;
  SystemRoutineName_8 = 0;
  RtlInitUnicodeString(&SystemRoutineName_8, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName_8);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v12 = ((__int64 (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
          0x40000000,
          v9,
          v21,
          0,
          0);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Lqq(WPP_GLOBAL_Control->AttachedDevice, 12, v11, (unsigned int)v12, DestinationString, TargetDevice);
  }
  ZwClose(DestinationString);
  if ( v12 < 0 )
    goto LABEL_19;
LABEL_25:
  LODWORD(DeviceRegKey) = 0;
  Fdo = DiskCreateFdo(DriverObject, TargetDevice, (int *)&DeviceRegKey, v22 == 0);
  ConfigurationInformation = IoGetConfigurationInformation();
  if ( Fdo >= 0 )
    ++ConfigurationInformation->DiskCount;
  return (unsigned int)Fdo;
}

```

## disassembly

```asm
0x140015030  mov     rax, rsp
0x140015033  push    rbp
0x140015034  push    rbx
0x140015035  lea     rbp, [rax-28h]
0x140015039  sub     rsp, 118h
0x140015040  mov     [rax+8], rsi
0x140015044  xorps   xmm1, xmm1
0x140015047  mov     [rax-18h], rdi
0x14001504b  mov     rsi, rcx
0x14001504e  mov     [rax-20h], r14
0x140015052  lea     rcx, [rbp+20h+var_90]; void *
0x140015056  mov     [rax-28h], r15
0x14001505a  mov     rdi, rdx
0x14001505d  xor     r15d, r15d
0x140015060  xorps   xmm0, xmm0
0x140015063  xor     edx, edx; Val
0x140015065  mov     [rbp+20h+arg_10], r15d
0x140015069  mov     r8d, 70h ; 'p'; Size
0x14001506f  mov     [rbp+20h+DeviceRegKey], r15
0x140015073  mov     qword ptr [rsp+120h+DestinationString.Length], r15
0x140015078  movups  xmmword ptr [rsp+120h+DestinationString.Buffer], xmm0
0x14001507d  movups  xmmword ptr [rsp+120h+ObjectAttributes+8], xmm1
0x140015082  movups  xmmword ptr [rsp+120h+ObjectAttributes+18h], xmm1
0x140015087  movups  xmmword ptr [rsp+120h+ObjectAttributes+28h], xmm1
0x14001508c  call    memset
0x140015091  lea     r9, [rbp+20h+DeviceRegKey]; DeviceRegKey
0x140015095  mov     edx, 1; DevInstKeyType
0x14001509a  mov     r8d, 20019h; DesiredAccess
0x1400150a0  mov     rcx, rdi; DeviceObject
0x1400150a3  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400150aa  nop     dword ptr [rax+rax+00h]
0x1400150af  test    eax, eax
0x1400150b1  jns     short loc_1400150F6
0x1400150b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150ba  lea     rbx, WPP_GLOBAL_Control
0x1400150c1  cmp     rcx, rbx
0x1400150c4  jz      loc_140015297
0x1400150ca  mov     edx, [rcx+2Ch]
0x1400150cd  test    dl, 2
0x1400150d0  jz      loc_140015297
0x1400150d6  cmp     byte ptr [rcx+29h], 2
0x1400150da  jb      loc_140015297
0x1400150e0  mov     rcx, [rcx+18h]
0x1400150e4  mov     r9d, eax
0x1400150e7  mov     [rsp+120h+var_100], rdi
0x1400150ec  call    WPP_SF_Lq
0x1400150f1  jmp     loc_140015297
0x1400150f6  lea     rdx, SubkeyName; "Disk"
0x1400150fd  lea     rcx, [rsp+120h+DestinationString.Buffer]; DestinationString
0x140015102  call    cs:__imp_RtlInitUnicodeString
0x140015109  nop     dword ptr [rax+rax+00h]
0x14001510e  mov     rax, [rbp+20h+DeviceRegKey]
0x140015112  lea     r8, [rsp+120h+ObjectAttributes+8]; ObjectAttributes
0x140015117  mov     qword ptr [rsp+120h+ObjectAttributes+10h], rax
0x14001511c  lea     rcx, [rsp+120h+DestinationString]; KeyHandle
0x140015121  lea     rax, [rsp+120h+DestinationString.Buffer]
0x140015126  mov     dword ptr [rsp+120h+ObjectAttributes+8], 30h ; '0'
0x14001512e  xorps   xmm0, xmm0
0x140015131  mov     qword ptr [rsp+120h+ObjectAttributes+18h], rax
0x140015136  mov     edx, 20019h; DesiredAccess
0x14001513b  mov     dword ptr [rsp+120h+ObjectAttributes+20h], 240h
0x140015143  movdqu  xmmword ptr [rsp+120h+ObjectAttributes+28h], xmm0
0x140015149  call    cs:__imp_ZwOpenKey
0x140015150  nop     dword ptr [rax+rax+00h]
0x140015155  mov     rcx, [rbp+20h+DeviceRegKey]; Handle
0x140015159  mov     r14d, eax
0x14001515c  call    cs:__imp_ZwClose
0x140015163  nop     dword ptr [rax+rax+00h]
0x140015168  test    r14d, r14d
0x14001516b  jns     short loc_1400151BE
0x14001516d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015174  lea     rbx, WPP_GLOBAL_Control
0x14001517b  cmp     rcx, rbx
0x14001517e  jz      loc_140015297
0x140015184  mov     edx, [rcx+2Ch]
0x140015187  test    dl, 2
0x14001518a  jz      loc_140015297
0x140015190  cmp     byte ptr [rcx+29h], 2
0x140015194  jb      loc_140015297
0x14001519a  mov     rax, [rbp+20h+DeviceRegKey]
0x14001519e  mov     edx, 0Bh
0x1400151a3  mov     rcx, [rcx+18h]
0x1400151a7  mov     r9d, r14d
0x1400151aa  mov     [rsp+120h+var_F8], rax
0x1400151af  mov     [rsp+120h+var_100], rdi
0x1400151b4  call    WPP_SF_Lqq
0x1400151b9  jmp     loc_140015297
0x1400151be  mov     rbx, qword ptr [rsp+120h+DestinationString.Length]
0x1400151c3  lea     rax, aRootpartitionm; "RootPartitionMountable"
0x1400151ca  mov     [rbp+20h+var_80], rax
0x1400151ce  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400151d5  lea     rax, [rbp+20h+arg_10]
0x1400151d9  mov     [rbp+20h+var_88], 120h
0x1400151e0  xorps   xmm0, xmm0
0x1400151e3  mov     [rbp+20h+var_78], rax
0x1400151e7  lea     rcx, [rsp+120h+SystemRoutineName.Buffer]; DestinationString
0x1400151ec  mov     [rbp+20h+var_70], 4000000h
0x1400151f3  movups  xmmword ptr [rsp+120h+SystemRoutineName.Buffer], xmm0
0x1400151f8  call    cs:__imp_RtlInitUnicodeString
0x1400151ff  nop     dword ptr [rax+rax+00h]
0x140015204  lea     rcx, [rsp+120h+SystemRoutineName.Buffer]; SystemRoutineName
0x140015209  call    cs:__imp_MmGetSystemRoutineAddress
0x140015210  nop     dword ptr [rax+rax+00h]
0x140015215  lea     r8, [rbp+20h+var_90]
0x140015219  mov     [rsp+120h+var_100], r15
0x14001521e  test    rax, rax
0x140015221  mov     rdx, rbx
0x140015224  mov     ecx, 40000000h
0x140015229  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140015231  xor     r9d, r9d
0x140015234  call    _guard_dispatch_icall
0x140015239  lea     rbx, WPP_GLOBAL_Control
0x140015240  mov     r14d, eax
0x140015243  test    eax, eax
0x140015245  jns     short loc_140015281
0x140015247  mov     rcx, cs:WPP_GLOBAL_Control
0x14001524e  cmp     rcx, rbx
0x140015251  jz      short loc_140015281
0x140015253  mov     edx, [rcx+2Ch]
0x140015256  test    dl, 2
0x140015259  jz      short loc_140015281
0x14001525b  cmp     byte ptr [rcx+29h], 2
0x14001525f  jb      short loc_140015281
0x140015261  mov     rax, qword ptr [rsp+120h+DestinationString.Length]
0x140015266  mov     edx, 0Ch
0x14001526b  mov     rcx, [rcx+18h]
0x14001526f  mov     r9d, r14d
0x140015272  mov     [rsp+120h+var_F8], rdi
0x140015277  mov     [rsp+120h+var_100], rax
0x14001527c  call    WPP_SF_Lqq
0x140015281  mov     rcx, qword ptr [rsp+120h+DestinationString.Length]; Handle
0x140015286  call    cs:__imp_ZwClose
0x14001528d  nop     dword ptr [rax+rax+00h]
0x140015292  test    r14d, r14d
0x140015295  jns     short loc_1400152E0
0x140015297  mov     rcx, cs:WPP_GLOBAL_Control
0x14001529e  cmp     rcx, rbx
0x1400152a1  jz      short loc_1400152E0
0x1400152a3  mov     eax, [rcx+2Ch]
0x1400152a6  test    al, 2
0x1400152a8  jz      short loc_1400152E0
0x1400152aa  cmp     byte ptr [rcx+29h], 3
0x1400152ae  jb      short loc_1400152E0
0x1400152b0  cmp     [rbp+20h+arg_10], r15d
0x1400152b4  lea     rax, aNot; "not "
0x1400152bb  mov     rcx, [rcx+18h]
0x1400152bf  lea     r9, word_14000896A
0x1400152c6  cmovz   r9, rax
0x1400152ca  mov     [rsp+120h+var_100], rdi
0x1400152cf  mov     edx, 0Dh
0x1400152d4  lea     r8, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids
0x1400152db  call    WPP_SF_sq
0x1400152e0  cmp     [rbp+20h+arg_10], r15d
0x1400152e4  lea     r8, [rbp+20h+DeviceRegKey]
0x1400152e8  mov     rdx, rdi; TargetDevice
0x1400152eb  mov     dword ptr [rbp+20h+DeviceRegKey], r15d
0x1400152ef  setz    r9b
0x1400152f3  mov     rcx, rsi; DriverObject
0x1400152f6  call    DiskCreateFdo
0x1400152fb  mov     ebx, eax
0x1400152fd  call    cs:__imp_IoGetConfigurationInformation
0x140015304  nop     dword ptr [rax+rax+00h]
0x140015309  mov     r15, [rsp+120h+var_20]
0x140015311  mov     r14, [rsp+120h+var_18]
0x140015319  mov     rdi, [rsp+110h]
0x140015321  mov     rsi, [rsp+120h+arg_0]
0x140015329  test    ebx, ebx
0x14001532b  js      short loc_14001532F
0x14001532d  inc     dword ptr [rax]
0x14001532f  mov     eax, ebx
0x140015331  add     rsp, 118h
0x140015338  pop     rbx
0x140015339  pop     rbp
0x14001533a  retn
```
