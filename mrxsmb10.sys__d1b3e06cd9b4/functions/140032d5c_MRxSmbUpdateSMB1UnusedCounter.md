# MRxSmbUpdateSMB1UnusedCounter

- ea: `0x140032d5c`
- end: `0x140032e57`
- name: `MRxSmbUpdateSMB1UnusedCounter`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000bac0`
- `0x14000f8b4`

## callees

- `0x140032d5c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140032df1`
- `ntoskrnl!ZwOpenKey` at `0x140032df1`
- `ntoskrnl!ZwClose` at `0x140032e32`
- `ntoskrnl!ZwClose` at `0x140032e32`
- `ntoskrnl!ZwSetValueKey` at `0x140032e20`
- `ntoskrnl!ZwSetValueKey` at `0x140032e20`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032d9b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032db2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032d9b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032db2`

## string_xrefs

- `0x140032d73`: `\Registry\Machine\Software\Microsoft\SMB1Uninstall`

## pseudocode

```c
NTSTATUS __fastcall MRxSmbUpdateSMB1UnusedCounter(int a1)
{
  NTSTATUS result; // eax
  NTSTATUS v2; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+90h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+18h] BYREF

  Data = a1;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Microsoft\\SMB1Uninstall");
  RtlInitUnicodeString(&ValueName, L"SMB1ClientCounter");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 2u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v2 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    ZwClose(KeyHandle);
    result = 0;
    if ( v2 < 0 )
      return v2;
  }
  return result;
}

```

## disassembly

```asm
0x140032d5c  mov     [rsp-8+arg_10], rbx
0x140032d61  mov     [rsp-8+arg_0], ecx
0x140032d65  push    rbp
0x140032d66  mov     rbp, rsp
0x140032d69  sub     rsp, 80h
0x140032d70  xorps   xmm0, xmm0
0x140032d73  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x140032d7a  xor     eax, eax
0x140032d7c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140032d80  xorps   xmm1, xmm1
0x140032d83  mov     [rbp+KeyHandle], rax
0x140032d87  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140032d8b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140032d8f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140032d93  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140032d97  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x140032d9b  call    cs:__imp_RtlInitUnicodeString
0x140032da2  nop     dword ptr [rax+rax+00h]
0x140032da7  lea     rdx, aSmb1clientcoun; "SMB1ClientCounter"
0x140032dae  lea     rcx, [rbp+ValueName]; DestinationString
0x140032db2  call    cs:__imp_RtlInitUnicodeString
0x140032db9  nop     dword ptr [rax+rax+00h]
0x140032dbe  lea     rax, [rbp+DestinationString]
0x140032dc2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140032dc9  xorps   xmm0, xmm0
0x140032dcc  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140032dd0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140032dd4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140032ddc  mov     edx, 2; DesiredAccess
0x140032de1  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140032de8  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140032dec  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140032df1  call    cs:__imp_ZwOpenKey
0x140032df8  nop     dword ptr [rax+rax+00h]
0x140032dfd  test    eax, eax
0x140032dff  js      short loc_140032E45
0x140032e01  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140032e05  lea     rax, [rbp+arg_0]
0x140032e09  mov     r9d, 4; Type
0x140032e0f  lea     rdx, [rbp+ValueName]; ValueName
0x140032e13  mov     [rsp+80h+DataSize], r9d; DataSize
0x140032e18  xor     r8d, r8d; TitleIndex
0x140032e1b  mov     [rsp+80h+Data], rax; Data
0x140032e20  call    cs:__imp_ZwSetValueKey
0x140032e27  nop     dword ptr [rax+rax+00h]
0x140032e2c  mov     rcx, [rbp+KeyHandle]; Handle
0x140032e30  mov     ebx, eax
0x140032e32  call    cs:__imp_ZwClose
0x140032e39  nop     dword ptr [rax+rax+00h]
0x140032e3e  xor     eax, eax
0x140032e40  test    ebx, ebx
0x140032e42  cmovs   eax, ebx
0x140032e45  mov     rbx, [rsp+80h+arg_10]
0x140032e4d  add     rsp, 80h
0x140032e54  pop     rbp
0x140032e55  retn
```
