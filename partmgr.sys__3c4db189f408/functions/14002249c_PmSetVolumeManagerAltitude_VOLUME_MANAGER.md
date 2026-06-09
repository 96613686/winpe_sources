# PmSetVolumeManagerAltitude(_VOLUME_MANAGER *)

- ea: `0x14002249c`
- end: `0x140022718`
- name: `?PmSetVolumeManagerAltitude@@YAJPEAU_VOLUME_MANAGER@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(struct _VOLUME_MANAGER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000e398`

## callees

- `0x140010f20`
- `0x14002249c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400226e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400226e5`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140022601`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140022601`
- `ntoskrnl!ZwClose` at `0x14002265f`
- `ntoskrnl!ZwClose` at `0x1400226a1`
- `ntoskrnl!ZwClose` at `0x14002265f`
- `ntoskrnl!ZwClose` at `0x1400226a1`
- `ntoskrnl!ExAllocatePool2` at `0x14002256b`
- `ntoskrnl!ExAllocatePool2` at `0x14002256b`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14002253e`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400225d3`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14002253e`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400225d3`
- `ntoskrnl!ZwQueryValueKey` at `0x14002268f`
- `ntoskrnl!ZwQueryValueKey` at `0x14002268f`
- `ntoskrnl!ZwOpenKey` at `0x14002264d`
- `ntoskrnl!ZwOpenKey` at `0x14002264d`

## pseudocode

```c
__int64 __fastcall PmSetVolumeManagerAltitude(struct _VOLUME_MANAGER *a1)
{
  __int64 v2; // rcx
  _QWORD *DeviceExtension; // rsi
  NTSTATUS DevicePropertyData; // ebx
  PWSTR Buffer; // r9
  __int64 v6; // rcx
  unsigned int v7; // eax
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  ULONG Type; // [rsp+44h] [rbp-25h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-21h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+98h] [rbp+2Fh] BYREF
  int v16; // [rsp+9Ch] [rbp+33h]
  int v17; // [rsp+A0h] [rbp+37h]
  int v18; // [rsp+A4h] [rbp+3Bh]

  KeyHandle = 0;
  Type = 0;
  v2 = *((_QWORD *)a1 + 6);
  DeviceExtension = PmControlObject->DeviceExtension;
  Handle = 0;
  ResultLength = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DevicePropertyData = IoGetDevicePropertyData(
                         *(PDEVICE_OBJECT *)(v2 + 8),
                         &DEVPKEY_Device_Service,
                         0,
                         0,
                         0,
                         0,
                         &ResultLength,
                         &Type);
  if ( DevicePropertyData == -1073741789 )
  {
    ValueName.Buffer = (PWSTR)ExAllocatePool2(64, ResultLength, 1163291984);
    Buffer = ValueName.Buffer;
    if ( !ValueName.Buffer )
    {
      DevicePropertyData = -1073741670;
      goto LABEL_16;
    }
    v6 = *((_QWORD *)a1 + 6);
    ValueName.MaximumLength = ResultLength;
    ValueName.Length = ResultLength - 2;
    DevicePropertyData = IoGetDevicePropertyData(
                           *(PDEVICE_OBJECT *)(v6 + 8),
                           &DEVPKEY_Device_Service,
                           0,
                           0,
                           ResultLength,
                           ValueName.Buffer,
                           &ResultLength,
                           &Type);
  }
  if ( DevicePropertyData >= 0 )
  {
    DevicePropertyData = IoOpenDriverRegistryKey(DeviceExtension[1], 0, 131097, 0, &Handle);
    if ( DevicePropertyData >= 0 )
    {
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &VolmgrAltitudes;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      DevicePropertyData = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      ZwClose(Handle);
      if ( DevicePropertyData >= 0 )
      {
        DevicePropertyData = ZwQueryValueKey(
                               KeyHandle,
                               &ValueName,
                               KeyValuePartialInformation,
                               KeyValueInformation,
                               0x10u,
                               &ResultLength);
        ZwClose(KeyHandle);
        if ( DevicePropertyData >= 0 && v16 == 4 && v17 == 4 )
        {
          v7 = v18;
        }
        else
        {
          v7 = 31;
          v18 = 31;
        }
        *((_DWORD *)a1 + 14) = v7;
        if ( v7 > 0x20 )
          *((_DWORD *)a1 + 14) = 31;
      }
    }
  }
  Buffer = ValueName.Buffer;
LABEL_16:
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  return (unsigned int)DevicePropertyData;
}

```

## disassembly

```asm
0x14002249c  mov     [rsp-8+arg_8], rbx
0x1400224a1  mov     [rsp-8+arg_10], rsi
0x1400224a6  push    rbp
0x1400224a7  push    rdi
0x1400224a8  push    r12
0x1400224aa  lea     rbp, [rsp-47h]
0x1400224af  sub     rsp, 0B0h
0x1400224b6  mov     rax, cs:__security_cookie
0x1400224bd  xor     rax, rsp
0x1400224c0  mov     [rbp+57h+var_18], rax
0x1400224c4  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400224cb  lea     rdx, DEVPKEY_Device_Service; PropertyKey
0x1400224d2  xorps   xmm1, xmm1
0x1400224d5  mov     [rbp+57h+KeyHandle], 0
0x1400224dd  mov     rdi, rcx
0x1400224e0  mov     [rbp+57h+var_7C], 0
0x1400224e7  mov     rcx, [rcx+30h]
0x1400224eb  xorps   xmm0, xmm0
0x1400224ee  mov     rsi, [rax+40h]
0x1400224f2  xor     r9d, r9d; Flags
0x1400224f5  lea     rax, [rbp+57h+var_7C]
0x1400224f9  mov     [rbp+57h+Handle], 0
0x140022501  mov     [rsp+0C0h+Type], rax; Type
0x140022506  xor     r8d, r8d; Lcid
0x140022509  lea     rax, [rbp+57h+ResultLength]
0x14002250d  mov     [rbp+57h+ResultLength], 0
0x140022514  mov     [rsp+0C0h+RequiredSize], rax; RequiredSize
0x140022519  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14002251d  mov     [rsp+0C0h+Data], 0; Data
0x140022526  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14002252a  mov     [rsp+0C0h+Size], 0; Size
0x140022532  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x140022536  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14002253a  mov     rcx, [rcx+8]; Pdo
0x14002253e  call    cs:__imp_IoGetDevicePropertyData
0x140022545  nop     dword ptr [rax+rax+00h]
0x14002254a  mov     ebx, eax
0x14002254c  mov     r12d, 2
0x140022552  cmp     eax, 0C0000023h
0x140022557  jnz     loc_1400225E1
0x14002255d  mov     edx, [rbp+57h+ResultLength]
0x140022560  lea     ecx, [r12+3Eh]
0x140022565  mov     r8d, 45566D50h
0x14002256b  call    cs:__imp_ExAllocatePool2
0x140022572  nop     dword ptr [rax+rax+00h]
0x140022577  mov     [rbp+57h+ValueName.Buffer], rax
0x14002257b  mov     r9, rax
0x14002257e  test    rax, rax
0x140022581  jnz     short loc_14002258D
0x140022583  mov     ebx, 0C000009Ah
0x140022588  jmp     loc_1400226DB
0x14002258d  mov     r8d, [rbp+57h+ResultLength]
0x140022591  lea     rdx, DEVPKEY_Device_Service; PropertyKey
0x140022598  mov     rcx, [rdi+30h]
0x14002259c  movzx   eax, r8w
0x1400225a0  sub     ax, r12w
0x1400225a4  mov     [rbp+57h+ValueName.MaximumLength], r8w
0x1400225a9  mov     [rbp+57h+ValueName.Length], ax
0x1400225ad  lea     rax, [rbp+57h+var_7C]
0x1400225b1  mov     [rsp+0C0h+Type], rax; Type
0x1400225b6  lea     rax, [rbp+57h+ResultLength]
0x1400225ba  mov     rcx, [rcx+8]; Pdo
0x1400225be  mov     [rsp+0C0h+RequiredSize], rax; RequiredSize
0x1400225c3  mov     [rsp+0C0h+Data], r9; Data
0x1400225c8  xor     r9d, r9d; Flags
0x1400225cb  mov     [rsp+0C0h+Size], r8d; Size
0x1400225d0  xor     r8d, r8d; Lcid
0x1400225d3  call    cs:__imp_IoGetDevicePropertyData
0x1400225da  nop     dword ptr [rax+rax+00h]
0x1400225df  mov     ebx, eax
0x1400225e1  test    ebx, ebx
0x1400225e3  js      loc_1400226D7
0x1400225e9  mov     rcx, [rsi+8]
0x1400225ed  lea     rax, [rbp+57h+Handle]
0x1400225f1  xor     r9d, r9d
0x1400225f4  mov     qword ptr [rsp+0C0h+Size], rax
0x1400225f9  xor     edx, edx
0x1400225fb  mov     r8d, 20019h
0x140022601  call    cs:__imp_IoOpenDriverRegistryKey
0x140022608  nop     dword ptr [rax+rax+00h]
0x14002260d  mov     ebx, eax
0x14002260f  test    eax, eax
0x140022611  js      loc_1400226D7
0x140022617  mov     rax, [rbp+57h+Handle]
0x14002261b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002261f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140022623  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140022627  lea     rax, ?VolmgrAltitudes@@3U_UNICODE_STRING@@A; ",."
0x14002262e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140022635  xorps   xmm0, xmm0
0x140022638  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002263c  mov     edx, 20019h; DesiredAccess
0x140022641  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140022648  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002264d  call    cs:__imp_ZwOpenKey
0x140022654  nop     dword ptr [rax+rax+00h]
0x140022659  mov     rcx, [rbp+57h+Handle]; Handle
0x14002265d  mov     ebx, eax
0x14002265f  call    cs:__imp_ZwClose
0x140022666  nop     dword ptr [rax+rax+00h]
0x14002266b  test    ebx, ebx
0x14002266d  js      short loc_1400226D7
0x14002266f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140022673  lea     rax, [rbp+57h+ResultLength]
0x140022677  mov     [rsp+0C0h+Data], rax; ResultLength
0x14002267c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140022680  mov     r8d, r12d; KeyValueInformationClass
0x140022683  mov     [rsp+0C0h+Size], 10h; Length
0x14002268b  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14002268f  call    cs:__imp_ZwQueryValueKey
0x140022696  nop     dword ptr [rax+rax+00h]
0x14002269b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002269f  mov     ebx, eax
0x1400226a1  call    cs:__imp_ZwClose
0x1400226a8  nop     dword ptr [rax+rax+00h]
0x1400226ad  mov     ecx, 1Fh
0x1400226b2  test    ebx, ebx
0x1400226b4  js      short loc_1400226C7
0x1400226b6  cmp     [rbp+57h+var_24], 4
0x1400226ba  jnz     short loc_1400226C7
0x1400226bc  cmp     [rbp+57h+var_20], 4
0x1400226c0  jnz     short loc_1400226C7
0x1400226c2  mov     eax, [rbp+57h+var_1C]
0x1400226c5  jmp     short loc_1400226CC
0x1400226c7  mov     eax, ecx
0x1400226c9  mov     [rbp+57h+var_1C], ecx
0x1400226cc  mov     [rdi+38h], eax
0x1400226cf  cmp     eax, 20h ; ' '
0x1400226d2  jbe     short loc_1400226D7
0x1400226d4  mov     [rdi+38h], ecx
0x1400226d7  mov     r9, [rbp+57h+ValueName.Buffer]
0x1400226db  test    r9, r9
0x1400226de  jz      short loc_1400226F1
0x1400226e0  xor     edx, edx; Tag
0x1400226e2  mov     rcx, r9; P
0x1400226e5  call    cs:__imp_ExFreePoolWithTag
0x1400226ec  nop     dword ptr [rax+rax+00h]
0x1400226f1  mov     eax, ebx
0x1400226f3  mov     rcx, [rbp+57h+var_18]
0x1400226f7  xor     rcx, rsp; StackCookie
0x1400226fa  call    __security_check_cookie
0x1400226ff  lea     r11, [rsp+0C0h+var_10]
0x140022707  mov     rbx, [r11+28h]
0x14002270b  mov     rsi, [r11+30h]
0x14002270f  mov     rsp, r11
0x140022712  pop     r12
0x140022714  pop     rdi
0x140022715  pop     rbp
0x140022716  retn
```
