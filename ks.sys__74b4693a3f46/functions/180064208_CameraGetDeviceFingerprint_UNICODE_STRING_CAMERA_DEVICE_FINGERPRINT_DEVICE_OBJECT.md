# CameraGetDeviceFingerprint(_UNICODE_STRING *,CAMERA_DEVICE_FINGERPRINT *,_DEVICE_OBJECT *)

- ea: `0x180064208`
- end: `0x1800647c7`
- name: `?CameraGetDeviceFingerprint@@YAJPEAU_UNICODE_STRING@@PEAUCAMERA_DEVICE_FINGERPRINT@@PEAU_DEVICE_OBJECT@@@Z`
- size: `1471`
- prototype: `__int64 __fastcall(PUNICODE_STRING SymbolicLinkName, struct CAMERA_DEVICE_FINGERPRINT *, PDEVICE_OBJECT Pdo)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800640e0`

## callees

- `0x18000ec10`
- `0x18000ec90`
- `0x180019fc0`
- `0x180064208`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180064578`
- `ntoskrnl!RtlInitUnicodeString` at `0x180064676`
- `ntoskrnl!RtlInitUnicodeString` at `0x180064578`
- `ntoskrnl!RtlInitUnicodeString` at `0x180064676`
- `ntoskrnl!ZwQueryValueKey` at `0x1800645a3`
- `ntoskrnl!ZwQueryValueKey` at `0x180064627`
- `ntoskrnl!ZwQueryValueKey` at `0x18006469d`
- `ntoskrnl!ZwQueryValueKey` at `0x180064715`
- `ntoskrnl!ZwQueryValueKey` at `0x1800645a3`
- `ntoskrnl!ZwQueryValueKey` at `0x180064627`
- `ntoskrnl!ZwQueryValueKey` at `0x18006469d`
- `ntoskrnl!ZwQueryValueKey` at `0x180064715`
- `ntoskrnl!ZwClose` at `0x180064777`
- `ntoskrnl!ZwClose` at `0x180064777`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006454f`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006454f`
- `ntoskrnl!ExAllocatePool2` at `0x18006426c`
- `ntoskrnl!ExAllocatePool2` at `0x18006426c`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18006430c`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1800643b6`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064467`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064518`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18006430c`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1800643b6`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064467`
- `ntoskrnl!IoGetDevicePropertyData` at `0x180064518`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800645dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800646d1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800645dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800646d1`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x1800642bd`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064364`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064420`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x1800644c9`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x1800642bd`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064364`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x180064420`
- `ntoskrnl!IoGetDeviceInterfacePropertyData` at `0x1800644c9`
- `ntoskrnl!ExFreePool` at `0x18006475c`
- `ntoskrnl!ExFreePool` at `0x18006478b`
- `ntoskrnl!ExFreePool` at `0x18006479f`
- `ntoskrnl!ExFreePool` at `0x18006475c`
- `ntoskrnl!ExFreePool` at `0x18006478b`
- `ntoskrnl!ExFreePool` at `0x18006479f`

## string_xrefs

- `0x180064668`: `CameraDeviceMftClsid`
- `0x180064569`: `CameraPostProcessingPluginCLSID`

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
      RtlStringCbCopyNW((unsigned __int16 *)a2, 0x40u, (const unsigned __int16 *)Data, 0x40u);
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
0x180064208  mov     [rsp-28h+arg_0], rbx
0x18006420d  mov     [rsp-28h+arg_10], rsi
0x180064212  push    rbp
0x180064213  push    rdi
0x180064214  push    r12
0x180064216  push    r14
0x180064218  push    r15
0x18006421a  mov     rbp, rsp
0x18006421d  sub     rsp, 60h
0x180064221  mov     r15, rcx
0x180064224  mov     [rbp+arg_18], 0
0x18006422b  xor     ecx, ecx; Handle
0x18006422d  mov     [rbp+arg_8], 0
0x180064234  xor     r14d, r14d
0x180064237  mov     [rbp+DeviceInterfaceRegKey], rcx
0x18006423b  xor     esi, esi
0x18006423d  mov     r12, r8
0x180064240  mov     rbx, rdx
0x180064243  test    rdx, rdx
0x180064246  jz      loc_18006476D
0x18006424c  test    r15, r15
0x18006424f  jz      loc_18006476D
0x180064255  test    r8, r8
0x180064258  jz      loc_18006476D
0x18006425e  lea     edx, [rcx+40h]
0x180064261  mov     r8d, 434D4143h
0x180064267  mov     ecx, 100h
0x18006426c  call    cs:__imp_ExAllocatePool2
0x180064273  nop     dword ptr [rax+rax+00h]
0x180064278  mov     rdi, rax
0x18006427b  test    rax, rax
0x18006427e  jnz     short loc_18006428E
0x180064280  mov     ebx, 0C000009Ah
0x180064285  mov     rcx, [rbp+DeviceInterfaceRegKey]
0x180064289  jmp     loc_180064772
0x18006428e  lea     rax, [rbp+arg_8]
0x180064292  xor     r9d, r9d
0x180064295  mov     [rsp+60h+Type], rax
0x18006429a  lea     rdx, DEVPKEY_Device_InLocalMachineContainer
0x1800642a1  lea     rax, [rbp+arg_18]
0x1800642a5  xor     r8d, r8d
0x1800642a8  mov     [rsp+60h+RequiredSize], rax
0x1800642ad  mov     rcx, r15
0x1800642b0  mov     [rsp+60h+Data], rdi
0x1800642b5  mov     [rsp+60h+Size], 40h ; '@'
0x1800642bd  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x1800642c4  nop     dword ptr [rax+rax+00h]
0x1800642c9  test    eax, eax
0x1800642cb  js      short loc_1800642DD
0x1800642cd  mov     ecx, [rbp+arg_8]
0x1800642d0  cmp     ecx, 11h
0x1800642d3  jnz     short loc_1800642DD
0x1800642d5  mov     eax, [rbp+arg_18]
0x1800642d8  cmp     eax, 1
0x1800642db  jnb     short loc_180064322
0x1800642dd  lea     rax, [rbp+arg_8]
0x1800642e1  xor     r9d, r9d; Flags
0x1800642e4  mov     [rsp+60h+Type], rax; Type
0x1800642e9  lea     rdx, DEVPKEY_Device_InLocalMachineContainer; PropertyKey
0x1800642f0  lea     rax, [rbp+arg_18]
0x1800642f4  xor     r8d, r8d; Lcid
0x1800642f7  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x1800642fc  mov     rcx, r12; Pdo
0x1800642ff  mov     [rsp+60h+Data], rdi; Data
0x180064304  mov     [rsp+60h+Size], 40h ; '@'; Size
0x18006430c  call    cs:__imp_IoGetDevicePropertyData
0x180064313  nop     dword ptr [rax+rax+00h]
0x180064318  test    eax, eax
0x18006431a  js      short loc_180064335
0x18006431c  mov     eax, [rbp+arg_18]
0x18006431f  mov     ecx, [rbp+arg_8]
0x180064322  cmp     ecx, 11h
0x180064325  jnz     short loc_180064335
0x180064327  cmp     eax, 1
0x18006432a  jb      short loc_180064335
0x18006432c  cmp     byte ptr [rdi], 0FFh
0x18006432f  setz    al
0x180064332  mov     [rbx+48h], al
0x180064335  lea     rax, [rbp+arg_8]
0x180064339  xor     r9d, r9d
0x18006433c  mov     [rsp+60h+Type], rax
0x180064341  lea     rdx, DEVPKEY_Device_PhysicalDeviceLocation
0x180064348  lea     rax, [rbp+arg_18]
0x18006434c  xor     r8d, r8d
0x18006434f  mov     [rsp+60h+RequiredSize], rax
0x180064354  mov     rcx, r15
0x180064357  mov     [rsp+60h+Data], rdi
0x18006435c  mov     [rsp+60h+Size], 40h ; '@'
0x180064364  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x18006436b  nop     dword ptr [rax+rax+00h]
0x180064370  test    eax, eax
0x180064372  js      short loc_180064387
0x180064374  mov     ecx, [rbp+arg_8]
0x180064377  cmp     ecx, 1003h
0x18006437d  jnz     short loc_180064387
0x18006437f  mov     eax, [rbp+arg_18]
0x180064382  cmp     eax, 14h
0x180064385  jnb     short loc_1800643CC
0x180064387  lea     rax, [rbp+arg_8]
0x18006438b  xor     r9d, r9d; Flags
0x18006438e  mov     [rsp+60h+Type], rax; Type
0x180064393  lea     rdx, DEVPKEY_Device_PhysicalDeviceLocation; PropertyKey
0x18006439a  lea     rax, [rbp+arg_18]
0x18006439e  xor     r8d, r8d; Lcid
0x1800643a1  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x1800643a6  mov     rcx, r12; Pdo
0x1800643a9  mov     [rsp+60h+Data], rdi; Data
0x1800643ae  mov     [rsp+60h+Size], 40h ; '@'; Size
0x1800643b6  call    cs:__imp_IoGetDevicePropertyData
0x1800643bd  nop     dword ptr [rax+rax+00h]
0x1800643c2  test    eax, eax
0x1800643c4  js      short loc_1800643F1
0x1800643c6  mov     eax, [rbp+arg_18]
0x1800643c9  mov     ecx, [rbp+arg_8]
0x1800643cc  cmp     ecx, 1003h
0x1800643d2  jnz     short loc_1800643F1
0x1800643d4  cmp     eax, 14h
0x1800643d7  jb      short loc_1800643F1
0x1800643d9  mov     eax, [rdi+8]
0x1800643dc  shr     eax, 3
0x1800643df  and     eax, 7
0x1800643e2  mov     [rbx+4Ch], eax
0x1800643e5  mov     eax, [rdi+0Ch]
0x1800643e8  shr     eax, 13h
0x1800643eb  and     eax, 0Fh
0x1800643ee  mov     [rbx+50h], eax
0x1800643f1  lea     rax, [rbp+arg_8]
0x1800643f5  xor     r9d, r9d
0x1800643f8  mov     [rsp+60h+Type], rax
0x1800643fd  lea     rdx, DEVPKEY_Device_DriverVersion
0x180064404  lea     rax, [rbp+arg_18]
0x180064408  xor     r8d, r8d
0x18006440b  mov     [rsp+60h+RequiredSize], rax
0x180064410  mov     rcx, r15
0x180064413  mov     [rsp+60h+Data], rdi
0x180064418  mov     [rsp+60h+Size], 40h ; '@'
0x180064420  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x180064427  nop     dword ptr [rax+rax+00h]
0x18006442c  test    eax, eax
0x18006442e  js      short loc_180064438
0x180064430  mov     eax, [rbp+arg_8]
0x180064433  cmp     eax, 12h
0x180064436  jz      short loc_18006447F
0x180064438  lea     rax, [rbp+arg_8]
0x18006443c  xor     r9d, r9d; Flags
0x18006443f  mov     [rsp+60h+Type], rax; Type
0x180064444  lea     rdx, DEVPKEY_Device_DriverVersion; PropertyKey
0x18006444b  lea     rax, [rbp+arg_18]
0x18006444f  xor     r8d, r8d; Lcid
0x180064452  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x180064457  mov     rcx, r12; Pdo
0x18006445a  mov     [rsp+60h+Data], rdi; Data
0x18006445f  mov     [rsp+60h+Size], 40h ; '@'; Size
0x180064467  call    cs:__imp_IoGetDevicePropertyData
0x18006446e  nop     dword ptr [rax+rax+00h]
0x180064473  test    eax, eax
0x180064475  js      short loc_18006449A
0x180064477  mov     eax, [rbp+arg_8]
0x18006447a  cmp     eax, 12h
0x18006447d  jnz     short loc_18006449A
0x18006447f  xor     eax, eax
0x180064481  mov     r8, rdi; unsigned __int16 *
0x180064484  mov     [rdi+3Eh], ax
0x180064488  mov     rcx, rbx; unsigned __int16 *
0x18006448b  mov     eax, 40h ; '@'
0x180064490  mov     r9d, eax; unsigned __int64
0x180064493  mov     edx, eax; unsigned __int64
0x180064495  call    ?RtlStringCbCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18006449a  lea     rax, [rbp+arg_8]
0x18006449e  xor     r9d, r9d
0x1800644a1  mov     [rsp+60h+Type], rax
0x1800644a6  lea     rdx, DEVPKEY_Device_DriverDate
0x1800644ad  lea     rax, [rbp+arg_18]
0x1800644b1  xor     r8d, r8d
0x1800644b4  mov     [rsp+60h+RequiredSize], rax
0x1800644b9  mov     rcx, r15
0x1800644bc  mov     [rsp+60h+Data], rdi
0x1800644c1  mov     [rsp+60h+Size], 40h ; '@'
0x1800644c9  call    cs:__imp_IoGetDeviceInterfacePropertyData
0x1800644d0  nop     dword ptr [rax+rax+00h]
0x1800644d5  test    eax, eax
0x1800644d7  js      short loc_1800644E9
0x1800644d9  mov     ecx, [rbp+arg_8]
0x1800644dc  cmp     ecx, 10h
0x1800644df  jnz     short loc_1800644E9
0x1800644e1  mov     eax, [rbp+arg_18]
0x1800644e4  cmp     eax, 8
0x1800644e7  jz      short loc_18006452E
0x1800644e9  lea     rax, [rbp+arg_8]
0x1800644ed  xor     r9d, r9d; Flags
0x1800644f0  mov     [rsp+60h+Type], rax; Type
0x1800644f5  lea     rdx, DEVPKEY_Device_DriverDate; PropertyKey
0x1800644fc  lea     rax, [rbp+arg_18]
0x180064500  xor     r8d, r8d; Lcid
0x180064503  mov     [rsp+60h+RequiredSize], rax; RequiredSize
0x180064508  mov     rcx, r12; Pdo
0x18006450b  mov     [rsp+60h+Data], rdi; Data
0x180064510  mov     [rsp+60h+Size], 40h ; '@'; Size
0x180064518  call    cs:__imp_IoGetDevicePropertyData
0x18006451f  nop     dword ptr [rax+rax+00h]
0x180064524  test    eax, eax
0x180064526  js      short loc_180064543
0x180064528  mov     eax, [rbp+arg_18]
0x18006452b  mov     ecx, [rbp+arg_8]
0x18006452e  cmp     ecx, 10h
0x180064531  jnz     short loc_180064543
0x180064533  cmp     eax, 8
0x180064536  jnz     short loc_180064543
0x180064538  mov     eax, [rdi]
0x18006453a  mov     [rbx+40h], eax
0x18006453d  mov     eax, [rdi+4]
0x180064540  mov     [rbx+44h], eax
0x180064543  lea     r8, [rbp+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x180064547  mov     edx, 80000000h; DesiredAccess
0x18006454c  mov     rcx, r15; SymbolicLinkName
0x18006454f  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x180064556  nop     dword ptr [rax+rax+00h]
0x18006455b  test    eax, eax
0x18006455d  js      loc_180064757
0x180064563  xorps   xmm0, xmm0
0x180064566  mov     [rbp+ResultLength], esi
0x180064569  lea     rdx, aCamerapostproc; "CameraPostProcessingPluginCLSID"
0x180064570  lea     rcx, [rbp+DestinationString]; DestinationString
0x180064574  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180064578  call    cs:__imp_RtlInitUnicodeString
0x18006457f  nop     dword ptr [rax+rax+00h]
0x180064584  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x180064588  lea     rax, [rbp+ResultLength]
0x18006458c  xor     r9d, r9d; KeyValueInformation
0x18006458f  mov     [rsp+60h+Data], rax; ResultLength
0x180064594  lea     rdx, [rbp+DestinationString]; ValueName
0x180064598  mov     [rsp+60h+Size], esi; Length
0x18006459c  lea     r15d, [r9+2]
0x1800645a0  mov     r8d, r15d; KeyValueInformationClass
0x1800645a3  call    cs:__imp_ZwQueryValueKey
0x1800645aa  nop     dword ptr [rax+rax+00h]
0x1800645af  mov     r12d, 0C0000023h
0x1800645b5  cmp     [rbp+ResultLength], r15d
0x1800645b9  jbe     loc_180064668
0x1800645bf  cmp     eax, r12d
0x1800645c2  jz      short loc_1800645CF
0x1800645c4  cmp     eax, 80000005h
0x1800645c9  jnz     loc_180064668
0x1800645cf  mov     edx, [rbp+ResultLength]; NumberOfBytes
0x1800645d2  mov     ecx, 1; PoolType
0x1800645d7  mov     r8d, 434D4143h; Tag
0x1800645dd  call    cs:__imp_ExAllocatePoolWithTag
0x1800645e4  nop     dword ptr [rax+rax+00h]
0x1800645e9  mov     r14, rax
0x1800645ec  test    rax, rax
0x1800645ef  jnz     short loc_1800645FB
0x1800645f1  mov     ebx, 0C000009Ah
0x1800645f6  jmp     loc_180064759
0x1800645fb  mov     r8d, [rbp+ResultLength]; Size
0x1800645ff  xor     edx, edx; Val
0x180064601  mov     rcx, r14; void *
0x180064604  call    memset
0x180064609  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x18006460d  lea     rax, [rbp+ResultLength]
0x180064611  mov     [rsp+60h+Data], rax; ResultLength
0x180064616  lea     rdx, [rbp+DestinationString]; ValueName
0x18006461a  mov     eax, [rbp+ResultLength]
0x18006461d  mov     r9, r14; KeyValueInformation
0x180064620  mov     r8d, r15d; KeyValueInformationClass
0x180064623  mov     [rsp+60h+Size], eax; Length
0x180064627  call    cs:__imp_ZwQueryValueKey
0x18006462e  nop     dword ptr [rax+rax+00h]
0x180064633  test    eax, eax
0x180064635  js      short loc_180064668
0x180064637  cmp     dword ptr [r14+4], 1
0x18006463c  jnz     short loc_180064668
0x18006463e  mov     r9d, [r14+8]; unsigned __int64
0x180064642  lea     rcx, [rbx+54h]; unsigned __int16 *
0x180064646  lea     r8, [r14+0Ch]; unsigned __int16 *
0x18006464a  mov     edx, 4Eh ; 'N'; unsigned __int64
0x18006464f  call    ?RtlStringCbCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180064654  mov     edx, [r14+8]; cbInput
0x180064658  lea     r8, [rbx+0A8h]; unsigned __int64 *
0x18006465f  lea     rcx, [r14+0Ch]; pbInput
0x180064663  call    ?CameraGenerateDWORD64Hash@@YAJPEAEKPEA_K@Z; CameraGenerateDWORD64Hash(uchar *,ulong,unsigned __int64 *)
0x180064668  lea     rdx, aCameradevicemf; "CameraDeviceMftClsid"
0x18006466f  mov     [rbp+ResultLength], esi
0x180064672  lea     rcx, [rbp+DestinationString]; DestinationString
0x180064676  call    cs:__imp_RtlInitUnicodeString
0x18006467d  nop     dword ptr [rax+rax+00h]
0x180064682  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x180064686  lea     rax, [rbp+ResultLength]
0x18006468a  mov     [rsp+60h+Data], rax; ResultLength
0x18006468f  lea     rdx, [rbp+DestinationString]; ValueName
0x180064693  xor     r9d, r9d; KeyValueInformation
0x180064696  mov     [rsp+60h+Size], esi; Length
0x18006469a  mov     r8d, r15d; KeyValueInformationClass
0x18006469d  call    cs:__imp_ZwQueryValueKey
0x1800646a4  nop     dword ptr [rax+rax+00h]
0x1800646a9  cmp     [rbp+ResultLength], r15d
0x1800646ad  jbe     loc_180064757
0x1800646b3  cmp     eax, r12d
0x1800646b6  jz      short loc_1800646C3
0x1800646b8  cmp     eax, 80000005h
0x1800646bd  jnz     loc_180064757
  ... truncated ...
```
