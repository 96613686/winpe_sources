# ClassUpdateInformationInRegistry

- ea: `0x140058e90`
- end: `0x140059235`
- name: `ClassUpdateInformationInRegistry`
- size: `933`
- prototype: `void __stdcall(PDEVICE_OBJECT Fdo, PCHAR DeviceName, ULONG DeviceNumber, PINQUIRYDATA InquiryData, ULONG InquiryDataLength)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x14001fbf4`
- `0x1400269e4`
- `0x140026b20`
- `0x14003e430`
- `0x14003e940`
- `0x140058e90`
- `0x14005e2e0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400591dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400591f3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400591dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400591f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400590a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059162`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400590a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059162`
- `ntoskrnl!ZwClose` at `0x140059209`
- `ntoskrnl!ZwClose` at `0x140059209`
- `ntoskrnl!ZwOpenKey` at `0x140059087`
- `ntoskrnl!ZwOpenKey` at `0x140059087`
- `ntoskrnl!RtlInitString` at `0x140059025`
- `ntoskrnl!RtlInitString` at `0x1400590e5`
- `ntoskrnl!RtlInitString` at `0x140059025`
- `ntoskrnl!RtlInitString` at `0x1400590e5`
- `ntoskrnl!ZwSetValueKey` at `0x14005913a`
- `ntoskrnl!ZwSetValueKey` at `0x14005918a`
- `ntoskrnl!ZwSetValueKey` at `0x14005913a`
- `ntoskrnl!ZwSetValueKey` at `0x14005918a`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14005903d`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400590fe`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14005903d`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400590fe`

## string_xrefs

- `0x140058fe1`: `\Registry\Machine\Hardware\DeviceMap\Scsi\Scsi Port %d\Scsi Bus %d\Target Id %d\Logical Unit Id %d`

## pseudocode

```c
void __stdcall ClassUpdateInformationInRegistry(
        PDEVICE_OBJECT Fdo,
        PCHAR DeviceName,
        ULONG DeviceNumber,
        PINQUIRYDATA InquiryData,
        ULONG InquiryDataLength)
{
  NTSTATUS Status; // ebx
  __int64 Buffer; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-B0h] BYREF
  struct _STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v15; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  char pszDest[256]; // [rsp+D0h] [rbp-30h] BYREF

  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  v15 = 0;
  UnicodeString = 0;
  IoStatus = 0;
  memset(pszDest, 0, sizeof(pszDest));
  KeyHandle = 0;
  ClassSendDeviceIoControlSynchronous(0x41018u, Fdo, &Buffer, 0, 8u, 0, &IoStatus);
  Status = IoStatus.Status;
  if ( IoStatus.Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        186,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        (unsigned int)IoStatus.Status);
    }
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      BYTE6(Buffer),
      BYTE5(Buffer),
      BYTE4(Buffer),
      BYTE5(Buffer),
      BYTE6(Buffer),
      HIBYTE(Buffer));
  }
  Status = RtlStringCchPrintfA(
             pszDest,
             0xFFu,
             "\\Registry\\Machine\\Hardware\\DeviceMap\\Scsi\\Scsi Port %d\\Scsi Bus %d\\Target Id %d\\Logical Unit Id %d",
             BYTE4(Buffer),
             BYTE5(Buffer),
             BYTE6(Buffer),
             HIBYTE(Buffer));
  if ( Status >= 0 )
  {
    RtlInitString(&DestinationString, pszDest);
    Status = RtlAnsiStringToUnicodeString(&v15, &DestinationString, 1u);
    if ( Status >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v15;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      Status = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
      if ( Status >= 0 )
      {
        RtlInitUnicodeString(&ValueName, L"DeviceName");
        Status = RtlStringCchPrintfA(pszDest, 0xFFu, "%s%d", DeviceName, DeviceNumber);
        if ( Status >= 0 )
        {
          RtlInitString(&DestinationString, pszDest);
          Status = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
          if ( Status >= 0 )
          {
            Status = ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, UnicodeString.Buffer, UnicodeString.Length);
            if ( Status >= 0 )
            {
              if ( !InquiryDataLength )
                goto LABEL_23;
              RtlInitUnicodeString(&ValueName, L"InquiryData");
              Status = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, InquiryData, InquiryDataLength);
LABEL_18:
              if ( Status >= 0 )
                goto LABEL_23;
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      188,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      (unsigned int)Status);
  }
LABEL_23:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v15.Buffer )
    RtlFreeUnicodeString(&v15);
  if ( KeyHandle )
    ZwClose(KeyHandle);
}

```

## disassembly

```asm
0x140058e90  push    rbp
0x140058e92  push    rbx
0x140058e93  push    rsi
0x140058e94  push    rdi
0x140058e95  push    r14
0x140058e97  push    r15
0x140058e99  lea     rbp, [rsp-0E8h]
0x140058ea1  sub     rsp, 1E8h
0x140058ea8  mov     rax, cs:__security_cookie
0x140058eaf  xor     rax, rsp
0x140058eb2  mov     [rbp+110h+var_40], rax
0x140058eb9  xorps   xmm0, xmm0
0x140058ebc  mov     [rsp+210h+Buffer], 0
0x140058ec5  xorps   xmm1, xmm1
0x140058ec8  mov     r14d, r8d
0x140058ecb  mov     rsi, rdx
0x140058ece  mov     rbx, rcx
0x140058ed1  xor     edx, edx; Val
0x140058ed3  lea     rcx, [rbp+110h+pszDest]; void *
0x140058ed7  mov     r8d, 100h; Size
0x140058edd  mov     r15, r9
0x140058ee0  movups  xmmword ptr [rbp+110h+ObjectAttributes.Length], xmm0
0x140058ee4  movups  xmmword ptr [rbp+110h+ObjectAttributes.ObjectName], xmm0
0x140058ee8  movups  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x140058eec  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x140058ef1  movups  xmmword ptr [rsp+210h+ValueName.Length], xmm1
0x140058ef6  movups  xmmword ptr [rbp+110h+var_190.Length], xmm0
0x140058efa  movups  xmmword ptr [rsp+210h+UnicodeString.Length], xmm1
0x140058eff  movups  xmmword ptr [rbp+110h+var_180], xmm0
0x140058f03  call    memset
0x140058f08  lea     rax, [rbp+110h+var_180]
0x140058f0c  mov     [rsp+210h+KeyHandle], 0
0x140058f15  mov     [rsp+210h+IoStatus], rax; IoStatus
0x140058f1a  lea     r8, [rsp+210h+Buffer]; Buffer
0x140058f1f  mov     [rsp+210h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140058f24  xor     r9d, r9d; InputBufferLength
0x140058f27  mov     rdx, rbx; TargetDeviceObject
0x140058f2a  mov     [rsp+210h+OutputBufferLength], 8; OutputBufferLength
0x140058f32  mov     ecx, 41018h; IoControlCode
0x140058f37  call    ClassSendDeviceIoControlSynchronous
0x140058f3c  mov     ebx, dword ptr [rbp+110h+var_180]
0x140058f3f  test    ebx, ebx
0x140058f41  jns     short loc_140058F8E
0x140058f43  mov     rcx, cs:WPP_GLOBAL_Control
0x140058f4a  lea     rdi, WPP_GLOBAL_Control
0x140058f51  cmp     rcx, rdi
0x140058f54  jz      loc_140059198
0x140058f5a  test    dword ptr [rcx+2Ch], 100h
0x140058f61  jz      loc_140059198
0x140058f67  cmp     byte ptr [rcx+29h], 3
0x140058f6b  jb      loc_140059198
0x140058f71  mov     rcx, [rcx+18h]
0x140058f75  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140058f7c  mov     edx, 0BAh
0x140058f81  mov     r9d, ebx
0x140058f84  call    WPP_SF_d
0x140058f89  jmp     loc_140059198
0x140058f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140058f95  lea     rdi, WPP_GLOBAL_Control
0x140058f9c  cmp     rcx, rdi
0x140058f9f  jz      short loc_140058FDC
0x140058fa1  test    dword ptr [rcx+2Ch], 100h
0x140058fa8  jz      short loc_140058FDC
0x140058faa  cmp     byte ptr [rcx+29h], 3
0x140058fae  jb      short loc_140058FDC
0x140058fb0  movzx   eax, byte ptr [rsp+210h+Buffer+7]
0x140058fb5  movzx   edx, byte ptr [rsp+210h+Buffer+6]
0x140058fba  movzx   r8d, byte ptr [rsp+210h+Buffer+5]
0x140058fc0  movzx   r9d, byte ptr [rsp+210h+Buffer+4]
0x140058fc6  mov     rcx, [rcx+18h]
0x140058fca  mov     dword ptr [rsp+210h+IoStatus], eax
0x140058fce  mov     dword ptr [rsp+210h+InternalDeviceIoControl], edx
0x140058fd2  mov     [rsp+210h+OutputBufferLength], r8d
0x140058fd7  call    WPP_SF_DDDD
0x140058fdc  movzx   ecx, byte ptr [rsp+210h+Buffer+6]
0x140058fe1  lea     r8, aRegistryMachin; "\\Registry\\Machine\\Hardware\\DeviceMa"...
0x140058fe8  movzx   edx, byte ptr [rsp+210h+Buffer+5]
0x140058fed  movzx   eax, byte ptr [rsp+210h+Buffer+7]
0x140058ff2  movzx   r9d, byte ptr [rsp+210h+Buffer+4]
0x140058ff8  mov     dword ptr [rsp+210h+IoStatus], eax
0x140058ffc  mov     dword ptr [rsp+210h+InternalDeviceIoControl], ecx
0x140059000  lea     rcx, [rbp+110h+pszDest]; pszDest
0x140059004  mov     [rsp+210h+OutputBufferLength], edx
0x140059008  mov     edx, 0FFh; cchDest
0x14005900d  call    RtlStringCchPrintfA
0x140059012  mov     ebx, eax
0x140059014  test    eax, eax
0x140059016  js      loc_14005919C
0x14005901c  lea     rdx, [rbp+110h+pszDest]; SourceString
0x140059020  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x140059025  call    cs:__imp_RtlInitString
0x14005902c  nop     dword ptr [rax+rax+00h]
0x140059031  mov     r8b, 1; AllocateDestinationString
0x140059034  lea     rdx, [rsp+210h+DestinationString]; SourceString
0x140059039  lea     rcx, [rbp+110h+var_190]; DestinationString
0x14005903d  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140059044  nop     dword ptr [rax+rax+00h]
0x140059049  mov     ebx, eax
0x14005904b  test    eax, eax
0x14005904d  js      loc_14005919C
0x140059053  lea     rax, [rbp+110h+var_190]
0x140059057  mov     [rbp+110h+ObjectAttributes.Length], 30h ; '0'
0x14005905e  xorps   xmm0, xmm0
0x140059061  mov     [rbp+110h+ObjectAttributes.ObjectName], rax
0x140059065  lea     r8, [rbp+110h+ObjectAttributes]; ObjectAttributes
0x140059069  mov     [rbp+110h+ObjectAttributes.RootDirectory], 0
0x140059071  mov     edx, 2001Fh; DesiredAccess
0x140059076  mov     [rbp+110h+ObjectAttributes.Attributes], 240h
0x14005907d  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x140059082  movdqu  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x140059087  call    cs:__imp_ZwOpenKey
0x14005908e  nop     dword ptr [rax+rax+00h]
0x140059093  mov     ebx, eax
0x140059095  test    eax, eax
0x140059097  js      loc_14005919C
0x14005909d  lea     rdx, aDevicename; "DeviceName"
0x1400590a4  lea     rcx, [rsp+210h+ValueName]; DestinationString
0x1400590a9  call    cs:__imp_RtlInitUnicodeString
0x1400590b0  nop     dword ptr [rax+rax+00h]
0x1400590b5  mov     r9, rsi
0x1400590b8  mov     [rsp+210h+OutputBufferLength], r14d
0x1400590bd  lea     r8, aSD; "%s%d"
0x1400590c4  mov     edx, 0FFh; cchDest
0x1400590c9  lea     rcx, [rbp+110h+pszDest]; pszDest
0x1400590cd  call    RtlStringCchPrintfA
0x1400590d2  mov     ebx, eax
0x1400590d4  test    eax, eax
0x1400590d6  js      loc_14005919C
0x1400590dc  lea     rdx, [rbp+110h+pszDest]; SourceString
0x1400590e0  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x1400590e5  call    cs:__imp_RtlInitString
0x1400590ec  nop     dword ptr [rax+rax+00h]
0x1400590f1  mov     r8b, 1; AllocateDestinationString
0x1400590f4  lea     rdx, [rsp+210h+DestinationString]; SourceString
0x1400590f9  lea     rcx, [rsp+210h+UnicodeString]; DestinationString
0x1400590fe  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140059105  nop     dword ptr [rax+rax+00h]
0x14005910a  mov     ebx, eax
0x14005910c  test    eax, eax
0x14005910e  js      loc_14005919C
0x140059114  movzx   eax, [rsp+210h+UnicodeString.Length]
0x140059119  lea     rdx, [rsp+210h+ValueName]; ValueName
0x14005911e  mov     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x140059123  mov     r9d, 1; Type
0x140059129  mov     dword ptr [rsp+210h+InternalDeviceIoControl], eax; DataSize
0x14005912d  xor     r8d, r8d; TitleIndex
0x140059130  mov     rax, [rsp+210h+UnicodeString.Buffer]
0x140059135  mov     qword ptr [rsp+210h+OutputBufferLength], rax; Data
0x14005913a  call    cs:__imp_ZwSetValueKey
0x140059141  nop     dword ptr [rax+rax+00h]
0x140059146  mov     ebx, eax
0x140059148  test    eax, eax
0x14005914a  js      short loc_14005919C
0x14005914c  mov     ebx, [rbp+110h+InquiryDataLength]
0x140059152  test    ebx, ebx
0x140059154  jz      short loc_1400591CF
0x140059156  lea     rdx, aInquirydata; "InquiryData"
0x14005915d  lea     rcx, [rsp+210h+ValueName]; DestinationString
0x140059162  call    cs:__imp_RtlInitUnicodeString
0x140059169  nop     dword ptr [rax+rax+00h]
0x14005916e  mov     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x140059173  lea     rdx, [rsp+210h+ValueName]; ValueName
0x140059178  mov     r9d, 3; Type
0x14005917e  mov     dword ptr [rsp+210h+InternalDeviceIoControl], ebx; DataSize
0x140059182  xor     r8d, r8d; TitleIndex
0x140059185  mov     qword ptr [rsp+210h+OutputBufferLength], r15; Data
0x14005918a  call    cs:__imp_ZwSetValueKey
0x140059191  nop     dword ptr [rax+rax+00h]
0x140059196  mov     ebx, eax
0x140059198  test    ebx, ebx
0x14005919a  jns     short loc_1400591CF
0x14005919c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591a3  cmp     rcx, rdi
0x1400591a6  jz      short loc_1400591CF
0x1400591a8  test    dword ptr [rcx+2Ch], 100h
0x1400591af  jz      short loc_1400591CF
0x1400591b1  cmp     byte ptr [rcx+29h], 3
0x1400591b5  jb      short loc_1400591CF
0x1400591b7  mov     rcx, [rcx+18h]
0x1400591bb  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400591c2  mov     edx, 0BCh
0x1400591c7  mov     r9d, ebx
0x1400591ca  call    WPP_SF_d
0x1400591cf  cmp     [rsp+210h+UnicodeString.Buffer], 0
0x1400591d5  jz      short loc_1400591E8
0x1400591d7  lea     rcx, [rsp+210h+UnicodeString]; UnicodeString
0x1400591dc  call    cs:__imp_RtlFreeUnicodeString
0x1400591e3  nop     dword ptr [rax+rax+00h]
0x1400591e8  cmp     [rbp+110h+var_190.Buffer], 0
0x1400591ed  jz      short loc_1400591FF
0x1400591ef  lea     rcx, [rbp+110h+var_190]; UnicodeString
0x1400591f3  call    cs:__imp_RtlFreeUnicodeString
0x1400591fa  nop     dword ptr [rax+rax+00h]
0x1400591ff  mov     rcx, [rsp+210h+KeyHandle]; Handle
0x140059204  test    rcx, rcx
0x140059207  jz      short loc_140059215
0x140059209  call    cs:__imp_ZwClose
0x140059210  nop     dword ptr [rax+rax+00h]
0x140059215  mov     rcx, [rbp+110h+var_40]
0x14005921c  xor     rcx, rsp; StackCookie
0x14005921f  call    __security_check_cookie
0x140059224  add     rsp, 1E8h
0x14005922b  pop     r15
0x14005922d  pop     r14
0x14005922f  pop     rdi
0x140059230  pop     rsi
0x140059231  pop     rbx
0x140059232  pop     rbp
0x140059233  retn
```
