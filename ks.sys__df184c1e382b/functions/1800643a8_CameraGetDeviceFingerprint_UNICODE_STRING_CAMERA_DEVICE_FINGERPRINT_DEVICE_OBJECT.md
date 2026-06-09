# CameraGetDeviceFingerprint(_UNICODE_STRING *,CAMERA_DEVICE_FINGERPRINT *,_DEVICE_OBJECT *)

- ea: `0x1800643a8`
- end: `0x180064967`
- name: `?CameraGetDeviceFingerprint@@YAJPEAU_UNICODE_STRING@@PEAUCAMERA_DEVICE_FINGERPRINT@@PEAU_DEVICE_OBJECT@@@Z`
- size: `1471`
- prototype: `__int64 __fastcall(PUNICODE_STRING SymbolicLinkName, struct CAMERA_DEVICE_FINGERPRINT *, PDEVICE_OBJECT Pdo)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180064280`

## callees

- `0x18000f300`
- `0x18000f380`
- `0x18001a000`
- `0x1800643a8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180064718`
- `ntoskrnl!RtlInitUnicodeString` at `0x180064816`
- `ntoskrnl!RtlInitUnicodeString` at `0x180064718`
- `ntoskrnl!RtlInitUnicodeString` at `0x180064816`
- `ntoskrnl!ZwQueryValueKey` at `0x180064743`
- `ntoskrnl!ZwQueryValueKey` at `0x1800647c7`
- `ntoskrnl!ZwQueryValueKey` at `0x18006483d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800648b5`
- `ntoskrnl!ZwQueryValueKey` at `0x180064743`
- `ntoskrnl!ZwQueryValueKey` at `0x1800647c7`
- `ntoskrnl!ZwQueryValueKey` at `0x18006483d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800648b5`
- `ntoskrnl!ZwClose` at `0x180064917`
- `ntoskrnl!ZwClose` at `0x180064917`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800646ef`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800646ef`
- `ntoskrnl!ExAllocatePool2` at `0x18006440c`
- `ntoskrnl!ExAllocatePool2` at `0x18006440c`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1800644ac`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064556`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064607`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1800646b8`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1800644ac`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064556`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064607`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1800646b8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18006477d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064871`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18006477d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064871`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x18006445d`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064504`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x1800645c0`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064669`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x18006445d`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064504`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x1800645c0`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064669`
- `ntoskrnl!ExFreePool` at `0x1800648fc`
- `ntoskrnl!ExFreePool` at `0x18006492b`
- `ntoskrnl!ExFreePool` at `0x18006493f`
- `ntoskrnl!ExFreePool` at `0x1800648fc`
- `ntoskrnl!ExFreePool` at `0x18006492b`
- `ntoskrnl!ExFreePool` at `0x18006493f`

## string_xrefs

- `0x180064808`: `CameraDeviceMftClsid`
- `0x180064709`: `CameraPostProcessingPluginCLSID`

## pseudocode

```c
__int64 __fastcall CameraGetDeviceFingerprint(
        PUNICODE_STRING SymbolicLinkName,
        struct CAMERA_DEVICE_FINGERPRINT *a2,
        PDEVICE_OBJECT Pdo)
{
  void *v4; // rcx
  unsigned __int16 *v5; // r14
  unsigned __int16 *v6; // rsi
  _BYTE *Data; // rdi
  unsigned int v10; // ebx
  ULONG v11; // ecx
  ULONG v12; // eax
  ULONG v13; // ecx
  ULONG v14; // eax
  ULONG v15; // ecx
  ULONG v16; // eax
  NTSTATUS v17; // eax
  unsigned __int16 *PoolWithTag; // rax
  NTSTATUS v19; // eax
  unsigned __int16 *v20; // rax
  ULONG ResultLength; // [rsp+40h] [rbp-20h] BYREF
  void *DeviceInterfaceRegKey; // [rsp+48h] [rbp-18h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  ULONG Type; // [rsp+98h] [rbp+38h] BYREF
  ULONG RequiredSize; // [rsp+A8h] [rbp+48h] BYREF

  RequiredSize = 0;
  v4 = 0;
  Type = 0;
  v5 = 0;
  DeviceInterfaceRegKey = 0;
  v6 = 0;
  if ( a2 && SymbolicLinkName && Pdo )
  {
    Data = (_BYTE *)ExAllocatePool2(256, 64, 1129136451);
    if ( !Data )
    {
      v10 = -1073741670;
LABEL_6:
      v4 = DeviceInterfaceRegKey;
      goto LABEL_55;
    }
    if ( (int)IoGetDeviceInterfacePropertyData(
                SymbolicLinkName,
                &DEVPKEY_Device_InLocalMachineContainer,
                0,
                0,
                64,
                Data,
                &RequiredSize,
                &Type) < 0
      || (v11 = Type, Type != 17)
      || (v12 = RequiredSize) == 0 )
    {
      if ( IoGetDevicePropertyData(
             Pdo,
             &DEVPKEY_Device_InLocalMachineContainer,
             0,
             0,
             0x40u,
             Data,
             &RequiredSize,
             &Type) < 0 )
        goto LABEL_15;
      v12 = RequiredSize;
      v11 = Type;
    }
    if ( v11 == 17 && v12 )
      *((_BYTE *)a2 + 72) = *Data == 0xFF;
LABEL_15:
    if ( (int)IoGetDeviceInterfacePropertyData(
                SymbolicLinkName,
                &DEVPKEY_Device_PhysicalDeviceLocation,
                0,
                0,
                64,
                Data,
                &RequiredSize,
                &Type) < 0
      || (v13 = Type, Type != 4099)
      || (v14 = RequiredSize, RequiredSize < 0x14) )
    {
      if ( IoGetDevicePropertyData(Pdo, &DEVPKEY_Device_PhysicalDeviceLocation, 0, 0, 0x40u, Data, &RequiredSize, &Type) < 0 )
        goto LABEL_23;
      v14 = RequiredSize;
      v13 = Type;
    }
    if ( v13 == 4099 && v14 >= 0x14 )
    {
      *((_DWORD *)a2 + 19) = (*((_DWORD *)Data + 2) >> 3) & 7;
      *((_DWORD *)a2 + 20) = (*((_DWORD *)Data + 3) >> 19) & 0xF;
    }
LABEL_23:
    if ( (int)IoGetDeviceInterfacePropertyData(
                SymbolicLinkName,
                &DEVPKEY_Device_DriverVersion,
                0,
                0,
                64,
                Data,
                &RequiredSize,
                &Type) >= 0
      && Type == 18
      || IoGetDevicePropertyData(Pdo, &DEVPKEY_Device_DriverVersion, 0, 0, 0x40u, Data, &RequiredSize, &Type) >= 0
      && Type == 18 )
    {
      *((_WORD *)Data + 31) = 0;
      RtlStringCbCopyNW((unsigned __int16 *)a2, 0x40u, (unsigned __int16 *)Data, 0x40u);
    }
    if ( (int)IoGetDeviceInterfacePropertyData(
                SymbolicLinkName,
                &DEVPKEY_Device_DriverDate,
                0,
                0,
                64,
                Data,
                &RequiredSize,
                &Type) < 0
      || (v15 = Type, Type != 16)
      || (v16 = RequiredSize, RequiredSize != 8) )
    {
      if ( IoGetDevicePropertyData(Pdo, &DEVPKEY_Device_DriverDate, 0, 0, 0x40u, Data, &RequiredSize, &Type) < 0 )
        goto LABEL_36;
      v16 = RequiredSize;
      v15 = Type;
    }
    if ( v15 == 16 && v16 == 8 )
    {
      *((_DWORD *)a2 + 16) = *(_DWORD *)Data;
      *((_DWORD *)a2 + 17) = *((_DWORD *)Data + 1);
    }
LABEL_36:
    if ( IoOpenDeviceInterfaceRegistryKey(SymbolicLinkName, 0x80000000, &DeviceInterfaceRegKey) >= 0 )
    {
      ResultLength = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"CameraPostProcessingPluginCLSID");
      v17 = ZwQueryValueKey(DeviceInterfaceRegKey, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
      if ( ResultLength > 2 && (v17 == -1073741789 || v17 == -2147483643) )
      {
        PoolWithTag = (unsigned __int16 *)ExAllocatePoolWithTag(PagedPool, ResultLength, 0x434D4143u);
        v5 = PoolWithTag;
        if ( !PoolWithTag )
        {
LABEL_41:
          v10 = -1073741670;
LABEL_53:
          ExFreePool(Data);
          goto LABEL_6;
        }
        memset(PoolWithTag, 0, ResultLength);
        if ( ZwQueryValueKey(
               DeviceInterfaceRegKey,
               &DestinationString,
               KeyValuePartialInformation,
               v5,
               ResultLength,
               &ResultLength) >= 0
          && *((_DWORD *)v5 + 1) == 1 )
        {
          RtlStringCbCopyNW((unsigned __int16 *)a2 + 42, 0x4Eu, v5 + 6, *((unsigned int *)v5 + 2));
          CameraGenerateDWORD64Hash((PUCHAR)v5 + 12, *((_DWORD *)v5 + 2), (unsigned __int64 *)a2 + 21);
        }
      }
      ResultLength = 0;
      RtlInitUnicodeString(&DestinationString, L"CameraDeviceMftClsid");
      v19 = ZwQueryValueKey(DeviceInterfaceRegKey, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
      if ( ResultLength > 2 && (v19 == -1073741789 || v19 == -2147483643) )
      {
        v20 = (unsigned __int16 *)ExAllocatePoolWithTag(PagedPool, ResultLength, 0x434D4143u);
        v6 = v20;
        if ( !v20 )
          goto LABEL_41;
        memset(v20, 0, ResultLength);
        if ( ZwQueryValueKey(
               DeviceInterfaceRegKey,
               &DestinationString,
               KeyValuePartialInformation,
               v6,
               ResultLength,
               &ResultLength) >= 0
          && *((_DWORD *)v6 + 1) == 1 )
        {
          RtlStringCbCopyNW((unsigned __int16 *)a2 + 88, 0x4Eu, v6 + 6, *((unsigned int *)v6 + 2));
          CameraGenerateDWORD64Hash((PUCHAR)v6 + 12, *((_DWORD *)v6 + 2), (unsigned __int64 *)a2 + 32);
        }
      }
    }
    v10 = 0;
    goto LABEL_53;
  }
  v10 = -1073741811;
LABEL_55:
  if ( v4 )
    ZwClose(v4);
  if ( v5 )
    ExFreePool(v5);
  if ( v6 )
    ExFreePool(v6);
  return v10;
}

```

## disassembly

```asm
0x1800643a8  mov     [rsp-28h+arg_0], rbx
0x1800643ad  mov     [rsp-28h+arg_10], rsi
0x1800643b2  push    rbp
0x1800643b3  push    rdi
0x1800643b4  push    r12
0x1800643b6  push    r14
0x1800643b8  push    r15
0x1800643ba  mov     rbp, rsp
0x1800643bd  sub     rsp, 60h
0x1800643c1  mov     r15, rcx
0x1800643c4  mov     [rbp+arg_18], 0
0x1800643cb  xor     ecx, ecx; Handle
0x1800643cd  mov     [rbp+arg_8], 0
0x1800643d4  xor     r14d, r14d
0x1800643d7  mov     [rbp+DeviceInterfaceRegKey], rcx
0x1800643db  xor     esi, esi
0x1800643dd  mov     r12, r8
0x1800643e0  mov     rbx, rdx
0x1800643e3  test    rdx, rdx
0x1800643e6  jz      loc_18006490D
0x1800643ec  test    r15, r15
0x1800643ef  jz      loc_18006490D
0x1800643f5  test    r8, r8
0x1800643f8  jz      loc_18006490D
0x1800643fe  lea     edx, [rcx+40h]
0x180064401  mov     r8d, 434D4143h
0x180064407  mov     ecx, 100h
0x18006440c  call    cs:__imp_ExAllocatePool2
0x180064413  nop     dword ptr [rax+rax+00h]
0x180064418  mov     rdi, rax
0x18006441b  test    rax, rax
0x18006441e  jnz     short loc_18006442E
0x180064420  mov     ebx, 0C000009Ah
0x180064425  mov     rcx, [rbp+DeviceInterfaceRegKey]
0x180064429  jmp     loc_180064912
0x18006442e  lea     rax, [rbp+arg_8]
0x180064432  xor     r9d, r9d
0x180064435  mov     [rsp+60h+Type], rax
0x18006443a  lea     rdx, DEVPKEY_Device_InLocalMachineContainer
0x180064441  lea     rax, [rbp+arg_18]
0x180064445  xor     r8d, r8d
0x180064448  mov     [rsp+60h+RequiredSize], rax
0x18006444d  mov     rcx, r15
0x180064450  mov     [rsp+60h+Data], rdi
0x180064455  mov     [rsp+60h+Size], 40h ; '@'
0x18006445d  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x180064464  nop     dword ptr [rax+rax+00h]
0x180064469  test    eax, eax
0x18006446b  js      short loc_18006447D
0x18006446d  mov     ecx, [rbp+arg_8]
0x180064470  cmp     ecx, 11h
0x180064473  jnz     short loc_18006447D
0x180064475  mov     eax, [rbp+arg_18]
0x180064478  cmp     eax, 1
0x18006447b  jnb     short loc_1800644C2
0x18006447d  lea     rax, [rbp+arg_8]
0x180064481  xor     r9d, r9d; Flags
0x180064484  mov     [rsp+60h+Type], rax; Type
0x180064489  lea     rdx, DEVPKEY_Device_InLocalMachineContainer; PropertyKey
0x180064490  lea     rax, [rbp+arg_18]
0x180064494  xor     r8d, r8d; Lcid
0x180064497  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x18006449c  mov     rcx, r12; Pdo
0x18006449f  mov     [rsp+60h+Data], rdi; Data
0x1800644a4  mov     [rsp+60h+Size], 40h ; '@'; Size
0x1800644ac  call    cs:__imp_IoGetDevicePropertyData
0x1800644b3  nop     dword ptr [rax+rax+00h]
0x1800644b8  test    eax, eax
0x1800644ba  js      short loc_1800644D5
0x1800644bc  mov     eax, [rbp+arg_18]
0x1800644bf  mov     ecx, [rbp+arg_8]
0x1800644c2  cmp     ecx, 11h
0x1800644c5  jnz     short loc_1800644D5
0x1800644c7  cmp     eax, 1
0x1800644ca  jb      short loc_1800644D5
0x1800644cc  cmp     byte ptr [rdi], 0FFh
0x1800644cf  setz    al
0x1800644d2  mov     [rbx+48h], al
0x1800644d5  lea     rax, [rbp+arg_8]
0x1800644d9  xor     r9d, r9d
0x1800644dc  mov     [rsp+60h+Type], rax
0x1800644e1  lea     rdx, DEVPKEY_Device_PhysicalDeviceLocation
0x1800644e8  lea     rax, [rbp+arg_18]
0x1800644ec  xor     r8d, r8d
0x1800644ef  mov     [rsp+60h+RequiredSize], rax
0x1800644f4  mov     rcx, r15
0x1800644f7  mov     [rsp+60h+Data], rdi
0x1800644fc  mov     [rsp+60h+Size], 40h ; '@'
0x180064504  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x18006450b  nop     dword ptr [rax+rax+00h]
0x180064510  test    eax, eax
0x180064512  js      short loc_180064527
0x180064514  mov     ecx, [rbp+arg_8]
0x180064517  cmp     ecx, 1003h
0x18006451d  jnz     short loc_180064527
0x18006451f  mov     eax, [rbp+arg_18]
0x180064522  cmp     eax, 14h
0x180064525  jnb     short loc_18006456C
0x180064527  lea     rax, [rbp+arg_8]
0x18006452b  xor     r9d, r9d; Flags
0x18006452e  mov     [rsp+60h+Type], rax; Type
0x180064533  lea     rdx, DEVPKEY_Device_PhysicalDeviceLocation; PropertyKey
0x18006453a  lea     rax, [rbp+arg_18]
0x18006453e  xor     r8d, r8d; Lcid
0x180064541  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x180064546  mov     rcx, r12; Pdo
0x180064549  mov     [rsp+60h+Data], rdi; Data
0x18006454e  mov     [rsp+60h+Size], 40h ; '@'; Size
0x180064556  call    cs:__imp_IoGetDevicePropertyData
0x18006455d  nop     dword ptr [rax+rax+00h]
0x180064562  test    eax, eax
0x180064564  js      short loc_180064591
0x180064566  mov     eax, [rbp+arg_18]
0x180064569  mov     ecx, [rbp+arg_8]
0x18006456c  cmp     ecx, 1003h
0x180064572  jnz     short loc_180064591
0x180064574  cmp     eax, 14h
0x180064577  jb      short loc_180064591
0x180064579  mov     eax, [rdi+8]
0x18006457c  shr     eax, 3
0x18006457f  and     eax, 7
0x180064582  mov     [rbx+4Ch], eax
0x180064585  mov     eax, [rdi+0Ch]
0x180064588  shr     eax, 13h
0x18006458b  and     eax, 0Fh
0x18006458e  mov     [rbx+50h], eax
0x180064591  lea     rax, [rbp+arg_8]
0x180064595  xor     r9d, r9d
0x180064598  mov     [rsp+60h+Type], rax
0x18006459d  lea     rdx, DEVPKEY_Device_DriverVersion
0x1800645a4  lea     rax, [rbp+arg_18]
0x1800645a8  xor     r8d, r8d
0x1800645ab  mov     [rsp+60h+RequiredSize], rax
0x1800645b0  mov     rcx, r15
0x1800645b3  mov     [rsp+60h+Data], rdi
0x1800645b8  mov     [rsp+60h+Size], 40h ; '@'
0x1800645c0  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x1800645c7  nop     dword ptr [rax+rax+00h]
0x1800645cc  test    eax, eax
0x1800645ce  js      short loc_1800645D8
0x1800645d0  mov     eax, [rbp+arg_8]
0x1800645d3  cmp     eax, 12h
0x1800645d6  jz      short loc_18006461F
0x1800645d8  lea     rax, [rbp+arg_8]
0x1800645dc  xor     r9d, r9d; Flags
0x1800645df  mov     [rsp+60h+Type], rax; Type
0x1800645e4  lea     rdx, DEVPKEY_Device_DriverVersion; PropertyKey
0x1800645eb  lea     rax, [rbp+arg_18]
0x1800645ef  xor     r8d, r8d; Lcid
0x1800645f2  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x1800645f7  mov     rcx, r12; Pdo
0x1800645fa  mov     [rsp+60h+Data], rdi; Data
0x1800645ff  mov     [rsp+60h+Size], 40h ; '@'; Size
0x180064607  call    cs:__imp_IoGetDevicePropertyData
0x18006460e  nop     dword ptr [rax+rax+00h]
0x180064613  test    eax, eax
0x180064615  js      short loc_18006463A
0x180064617  mov     eax, [rbp+arg_8]
0x18006461a  cmp     eax, 12h
0x18006461d  jnz     short loc_18006463A
0x18006461f  xor     eax, eax
0x180064621  mov     r8, rdi; unsigned __int16 *
0x180064624  mov     [rdi+3Eh], ax
0x180064628  mov     rcx, rbx; unsigned __int16 *
0x18006462b  mov     eax, 40h ; '@'
0x180064630  mov     r9d, eax; unsigned __int64
0x180064633  mov     edx, eax; unsigned __int64
0x180064635  call    ?RtlStringCbCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18006463a  lea     rax, [rbp+arg_8]
0x18006463e  xor     r9d, r9d
0x180064641  mov     [rsp+60h+Type], rax
0x180064646  lea     rdx, DEVPKEY_Device_DriverDate
0x18006464d  lea     rax, [rbp+arg_18]
0x180064651  xor     r8d, r8d
0x180064654  mov     [rsp+60h+RequiredSize], rax
0x180064659  mov     rcx, r15
0x18006465c  mov     [rsp+60h+Data], rdi
0x180064661  mov     [rsp+60h+Size], 40h ; '@'
0x180064669  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x180064670  nop     dword ptr [rax+rax+00h]
0x180064675  test    eax, eax
0x180064677  js      short loc_180064689
0x180064679  mov     ecx, [rbp+arg_8]
0x18006467c  cmp     ecx, 10h
0x18006467f  jnz     short loc_180064689
0x180064681  mov     eax, [rbp+arg_18]
0x180064684  cmp     eax, 8
0x180064687  jz      short loc_1800646CE
0x180064689  lea     rax, [rbp+arg_8]
0x18006468d  xor     r9d, r9d; Flags
0x180064690  mov     [rsp+60h+Type], rax; Type
0x180064695  lea     rdx, DEVPKEY_Device_DriverDate; PropertyKey
0x18006469c  lea     rax, [rbp+arg_18]
0x1800646a0  xor     r8d, r8d; Lcid
0x1800646a3  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x1800646a8  mov     rcx, r12; Pdo
0x1800646ab  mov     [rsp+60h+Data], rdi; Data
0x1800646b0  mov     [rsp+60h+Size], 40h ; '@'; Size
0x1800646b8  call    cs:__imp_IoGetDevicePropertyData
0x1800646bf  nop     dword ptr [rax+rax+00h]
0x1800646c4  test    eax, eax
0x1800646c6  js      short loc_1800646E3
0x1800646c8  mov     eax, [rbp+arg_18]
0x1800646cb  mov     ecx, [rbp+arg_8]
0x1800646ce  cmp     ecx, 10h
0x1800646d1  jnz     short loc_1800646E3
0x1800646d3  cmp     eax, 8
0x1800646d6  jnz     short loc_1800646E3
0x1800646d8  mov     eax, [rdi]
0x1800646da  mov     [rbx+40h], eax
0x1800646dd  mov     eax, [rdi+4]
0x1800646e0  mov     [rbx+44h], eax
0x1800646e3  lea     r8, [rbp+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x1800646e7  mov     edx, 80000000h; DesiredAccess
0x1800646ec  mov     rcx, r15; SymbolicLinkName
0x1800646ef  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x1800646f6  nop     dword ptr [rax+rax+00h]
0x1800646fb  test    eax, eax
0x1800646fd  js      loc_1800648F7
0x180064703  xorps   xmm0, xmm0
0x180064706  mov     [rbp+ResultLength], esi
0x180064709  lea     rdx, aCamerapostproc; "CameraPostProcessingPluginCLSID"
0x180064710  lea     rcx, [rbp+DestinationString]; DestinationString
0x180064714  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180064718  call    cs:__imp_RtlInitUnicodeString
0x18006471f  nop     dword ptr [rax+rax+00h]
0x180064724  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x180064728  lea     rax, [rbp+ResultLength]
0x18006472c  xor     r9d, r9d; KeyValueInformation
0x18006472f  mov     [rsp+60h+Data], rax; ResultLength
0x180064734  lea     rdx, [rbp+DestinationString]; ValueName
0x180064738  mov     [rsp+60h+Size], esi; Length
0x18006473c  lea     r15d, [r9+2]
0x180064740  mov     r8d, r15d; KeyValueInformationClass
0x180064743  call    cs:__imp_ZwQueryValueKey
0x18006474a  nop     dword ptr [rax+rax+00h]
0x18006474f  mov     r12d, 0C0000023h
0x180064755  cmp     [rbp+ResultLength], r15d
0x180064759  jbe     loc_180064808
0x18006475f  cmp     eax, r12d
0x180064762  jz      short loc_18006476F
0x180064764  cmp     eax, 80000005h
0x180064769  jnz     loc_180064808
0x18006476f  mov     edx, [rbp+ResultLength]; NumberOfBytes
0x180064772  mov     ecx, 1; PoolType
0x180064777  mov     r8d, 434D4143h; Tag
0x18006477d  call    cs:__imp_ExAllocatePoolWithTag
0x180064784  nop     dword ptr [rax+rax+00h]
0x180064789  mov     r14, rax
0x18006478c  test    rax, rax
0x18006478f  jnz     short loc_18006479B
0x180064791  mov     ebx, 0C000009Ah
0x180064796  jmp     loc_1800648F9
0x18006479b  mov     r8d, [rbp+ResultLength]; Size
0x18006479f  xor     edx, edx; Val
0x1800647a1  mov     rcx, r14; void *
0x1800647a4  call    memset
0x1800647a9  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x1800647ad  lea     rax, [rbp+ResultLength]
0x1800647b1  mov     [rsp+60h+Data], rax; ResultLength
0x1800647b6  lea     rdx, [rbp+DestinationString]; ValueName
0x1800647ba  mov     eax, [rbp+ResultLength]
0x1800647bd  mov     r9, r14; KeyValueInformation
0x1800647c0  mov     r8d, r15d; KeyValueInformationClass
0x1800647c3  mov     [rsp+60h+Size], eax; Length
0x1800647c7  call    cs:__imp_ZwQueryValueKey
0x1800647ce  nop     dword ptr [rax+rax+00h]
0x1800647d3  test    eax, eax
0x1800647d5  js      short loc_180064808
0x1800647d7  cmp     dword ptr [r14+4], 1
0x1800647dc  jnz     short loc_180064808
0x1800647de  mov     r9d, [r14+8]; unsigned __int64
0x1800647e2  lea     rcx, [rbx+54h]; unsigned __int16 *
0x1800647e6  lea     r8, [r14+0Ch]; unsigned __int16 *
0x1800647ea  mov     edx, 4Eh ; 'N'; unsigned __int64
0x1800647ef  call    ?RtlStringCbCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800647f4  mov     edx, [r14+8]; cbInput
0x1800647f8  lea     r8, [rbx+0A8h]; unsigned __int64 *
0x1800647ff  lea     rcx, [r14+0Ch]; pbInput
0x180064803  call    ?CameraGenerateDWORD64Hash@@YAJPEAEKPEA_K@Z; CameraGenerateDWORD64Hash(uchar *,ulong,unsigned __int64 *)
0x180064808  lea     rdx, aCameradevicemf; "CameraDeviceMftClsid"
0x18006480f  mov     [rbp+ResultLength], esi
0x180064812  lea     rcx, [rbp+DestinationString]; DestinationString
0x180064816  call    cs:__imp_RtlInitUnicodeString
0x18006481d  nop     dword ptr [rax+rax+00h]
0x180064822  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x180064826  lea     rax, [rbp+ResultLength]
0x18006482a  mov     [rsp+60h+Data], rax; ResultLength
0x18006482f  lea     rdx, [rbp+DestinationString]; ValueName
0x180064833  xor     r9d, r9d; KeyValueInformation
0x180064836  mov     [rsp+60h+Size], esi; Length
0x18006483a  mov     r8d, r15d; KeyValueInformationClass
0x18006483d  call    cs:__imp_ZwQueryValueKey
0x180064844  nop     dword ptr [rax+rax+00h]
0x180064849  cmp     [rbp+ResultLength], r15d
0x18006484d  jbe     loc_1800648F7
0x180064853  cmp     eax, r12d
0x180064856  jz      short loc_180064863
0x180064858  cmp     eax, 80000005h
0x18006485d  jnz     loc_1800648F7
  ... truncated ...
```
