# I_PEConfigOptions

- ea: `0x18007ed28`
- end: `0x18007ee4a`
- name: `I_PEConfigOptions`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x18007e848`

## callees

- `0x18002bef0`
- `0x18007ed28`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007ed76`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007ed8d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007ed76`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007ed8d`
- `ntoskrnl!ZwQueryValueKey` at `0x18007edff`
- `ntoskrnl!ZwQueryValueKey` at `0x18007edff`
- `ntoskrnl!ZwClose` at `0x18007ee28`
- `ntoskrnl!ZwClose` at `0x18007ee28`
- `ntoskrnl!ZwOpenKey` at `0x18007edcc`
- `ntoskrnl!ZwOpenKey` at `0x18007edcc`

## string_xrefs

- `0x18007ed52`: `\Registry\Machine\System\CurrentControlSet\Services\PEAuth`

## pseudocode

```c
int I_PEConfigOptions()
{
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp+27h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v7; // [rsp+94h] [rbp+3Bh]
  int v8; // [rsp+98h] [rbp+3Fh]
  int v9; // [rsp+9Ch] [rbp+43h]

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  ValueName = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\PEAuth");
  RtlInitUnicodeString(&ValueName, L"Options");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength) >= 0
      && v7 == 4
      && v8 == 4 )
    {
      g_PEAuthConfigOptions = v9;
    }
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x18007ed28  push    rbp
0x18007ed2a  lea     rbp, [rsp-57h]
0x18007ed2f  sub     rsp, 0B0h
0x18007ed36  mov     rax, cs:__security_cookie
0x18007ed3d  xor     rax, rsp
0x18007ed40  mov     [rbp+57h+var_8], rax
0x18007ed44  xorps   xmm0, xmm0
0x18007ed47  mov     [rbp+57h+KeyHandle], 0
0x18007ed4f  xorps   xmm1, xmm1
0x18007ed52  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18007ed59  xor     eax, eax
0x18007ed5b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007ed5f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18007ed63  mov     [rbp+57h+var_80], eax
0x18007ed66  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18007ed6a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007ed6e  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x18007ed72  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18007ed76  call    cs:__imp_RtlInitUnicodeString
0x18007ed7d  nop     dword ptr [rax+rax+00h]
0x18007ed82  lea     rdx, aOptions; "Options"
0x18007ed89  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18007ed8d  call    cs:__imp_RtlInitUnicodeString
0x18007ed94  nop     dword ptr [rax+rax+00h]
0x18007ed99  lea     rax, [rbp+57h+DestinationString]
0x18007ed9d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007eda4  xorps   xmm0, xmm0
0x18007eda7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18007edab  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007edaf  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18007edb7  mov     edx, 20019h; DesiredAccess
0x18007edbc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18007edc3  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18007edc7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007edcc  call    cs:__imp_ZwOpenKey
0x18007edd3  nop     dword ptr [rax+rax+00h]
0x18007edd8  test    eax, eax
0x18007edda  js      short loc_18007EE34
0x18007eddc  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18007ede0  lea     rax, [rbp+57h+var_80]
0x18007ede4  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18007ede9  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18007eded  mov     r8d, 2; KeyValueInformationClass
0x18007edf3  mov     [rsp+0B0h+Length], 14h; Length
0x18007edfb  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18007edff  call    cs:__imp_ZwQueryValueKey
0x18007ee06  nop     dword ptr [rax+rax+00h]
0x18007ee0b  test    eax, eax
0x18007ee0d  js      short loc_18007EE24
0x18007ee0f  cmp     [rbp+57h+var_1C], 4
0x18007ee13  jnz     short loc_18007EE24
0x18007ee15  cmp     [rbp+57h+var_18], 4
0x18007ee19  jnz     short loc_18007EE24
0x18007ee1b  mov     eax, [rbp+57h+var_14]
0x18007ee1e  mov     cs:g_PEAuthConfigOptions, eax
0x18007ee24  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18007ee28  call    cs:__imp_ZwClose
0x18007ee2f  nop     dword ptr [rax+rax+00h]
0x18007ee34  mov     rcx, [rbp+57h+var_8]
0x18007ee38  xor     rcx, rsp; StackCookie
0x18007ee3b  call    __security_check_cookie
0x18007ee40  add     rsp, 0B0h
0x18007ee47  pop     rbp
0x18007ee48  retn
```
