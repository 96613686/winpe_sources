# ClassSetDeviceParameter

- ea: `0x14005bef0`
- end: `0x14005c04d`
- name: `ClassSetDeviceParameter`
- size: `349`
- prototype: `NTSTATUS __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PWSTR SubkeyName, PWSTR ParameterName, ULONG ParameterValue)`
- caller_count: `5`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140019de0`
- `0x140054740`
- `0x14005479c`
- `0x14005f690`
- `0x14005fe50`

## callees

- `0x14005bef0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14005bf70`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005bf70`
- `ntoskrnl!ZwCreateKey` at `0x14005bfcc`
- `ntoskrnl!ZwCreateKey` at `0x14005bfcc`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005bf35`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005bf35`
- `ntoskrnl!ZwClose` at `0x14005c01b`
- `ntoskrnl!ZwClose` at `0x14005c02b`
- `ntoskrnl!ZwClose` at `0x14005c01b`
- `ntoskrnl!ZwClose` at `0x14005c02b`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14005c004`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14005c004`

## pseudocode

```c
NTSTATUS __stdcall ClassSetDeviceParameter(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        PWSTR SubkeyName,
        PWSTR ParameterName,
        ULONG ParameterValue)
{
  struct _DEVICE_OBJECT *LowerPdo; // rcx
  int v7; // ebx
  const WCHAR *v8; // rdx
  void *KeyHandle; // [rsp+40h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+Fh] BYREF
  void *DeviceRegKey; // [rsp+B0h] [rbp+67h] BYREF
  ULONG ValueData; // [rsp+C8h] [rbp+7Fh] BYREF

  ValueData = ParameterValue;
  LowerPdo = FdoExtension->LowerPdo;
  DeviceRegKey = 0;
  KeyHandle = 0;
  v7 = IoOpenDeviceRegistryKey(LowerPdo, 1u, 0x2001Fu, &DeviceRegKey);
  if ( v7 >= 0 )
  {
    if ( SubkeyName )
    {
      DestinationString = 0;
      memset(&ObjectAttributes, 0, 44);
      RtlInitUnicodeString(&DestinationString, SubkeyName);
      ObjectAttributes.RootDirectory = DeviceRegKey;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
      if ( v7 < 0 )
      {
LABEL_8:
        ZwClose(DeviceRegKey);
        return v7;
      }
      v8 = (const WCHAR *)KeyHandle;
    }
    else
    {
      v8 = (const WCHAR *)DeviceRegKey;
    }
    v7 = RtlWriteRegistryValue(0x40000000u, v8, ParameterName, 4u, &ValueData, 4u);
    if ( SubkeyName )
      ZwClose(KeyHandle);
    goto LABEL_8;
  }
  return v7;
}

```

## disassembly

```asm
0x14005bef0  mov     [rsp-8+arg_8], rbx
0x14005bef5  mov     [rsp-8+ValueData], r9d
0x14005befa  push    rbp
0x14005befb  push    rsi
0x14005befc  push    rdi
0x14005befd  lea     rbp, [rsp-47h]
0x14005bf02  sub     rsp, 90h
0x14005bf09  mov     rcx, [rcx+200h]; DeviceObject
0x14005bf10  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x14005bf14  mov     rsi, r8
0x14005bf17  mov     [rbp+57h+DeviceRegKey], 0
0x14005bf1f  mov     rdi, rdx
0x14005bf22  mov     [rbp+57h+KeyHandle], 0
0x14005bf2a  mov     edx, 1; DevInstKeyType
0x14005bf2f  mov     r8d, 2001Fh; DesiredAccess
0x14005bf35  call    cs:__imp_IoOpenDeviceRegistryKey
0x14005bf3c  nop     dword ptr [rax+rax+00h]
0x14005bf41  mov     ebx, eax
0x14005bf43  test    eax, eax
0x14005bf45  js      loc_14005C037
0x14005bf4b  test    rdi, rdi
0x14005bf4e  jz      loc_14005BFE4
0x14005bf54  xorps   xmm0, xmm0
0x14005bf57  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005bf5b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14005bf5f  xor     eax, eax
0x14005bf61  mov     rdx, rdi; SourceString
0x14005bf64  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14005bf68  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005bf6c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14005bf70  call    cs:__imp_RtlInitUnicodeString
0x14005bf77  nop     dword ptr [rax+rax+00h]
0x14005bf7c  mov     rax, [rbp+57h+DeviceRegKey]
0x14005bf80  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005bf84  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14005bf88  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005bf8c  lea     rax, [rbp+57h+DestinationString]
0x14005bf90  mov     [rsp+0A0h+Disposition], 0; Disposition
0x14005bf99  xorps   xmm0, xmm0
0x14005bf9c  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x14005bfa4  xor     r9d, r9d; TitleIndex
0x14005bfa7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14005bfab  mov     edx, 2001Fh; DesiredAccess
0x14005bfb0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14005bfb7  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14005bfbe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005bfc3  mov     [rsp+0A0h+Class], 0; Class
0x14005bfcc  call    cs:__imp_ZwCreateKey
0x14005bfd3  nop     dword ptr [rax+rax+00h]
0x14005bfd8  mov     ebx, eax
0x14005bfda  test    eax, eax
0x14005bfdc  js      short loc_14005C027
0x14005bfde  mov     rdx, [rbp+57h+KeyHandle]
0x14005bfe2  jmp     short loc_14005BFE8
0x14005bfe4  mov     rdx, [rbp+57h+DeviceRegKey]; Path
0x14005bfe8  mov     r9d, 4; ValueType
0x14005bfee  lea     rax, [rbp+57h+ValueData]
0x14005bff2  mov     [rsp+0A0h+CreateOptions], r9d; ValueLength
0x14005bff7  mov     r8, rsi; ValueName
0x14005bffa  mov     ecx, 40000000h; RelativeTo
0x14005bfff  mov     [rsp+0A0h+Class], rax; ValueData
0x14005c004  call    cs:__imp_RtlWriteRegistryValue
0x14005c00b  nop     dword ptr [rax+rax+00h]
0x14005c010  mov     ebx, eax
0x14005c012  test    rdi, rdi
0x14005c015  jz      short loc_14005C027
0x14005c017  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14005c01b  call    cs:__imp_ZwClose
0x14005c022  nop     dword ptr [rax+rax+00h]
0x14005c027  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x14005c02b  call    cs:__imp_ZwClose
0x14005c032  nop     dword ptr [rax+rax+00h]
0x14005c037  mov     eax, ebx
0x14005c039  mov     rbx, [rsp+0A0h+arg_8]
0x14005c041  add     rsp, 90h
0x14005c048  pop     rdi
0x14005c049  pop     rsi
0x14005c04a  pop     rbp
0x14005c04b  retn
```
