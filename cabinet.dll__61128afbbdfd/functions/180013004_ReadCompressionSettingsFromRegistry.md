# ReadCompressionSettingsFromRegistry

- ea: `0x180013004`
- end: `0x180013119`
- name: `ReadCompressionSettingsFromRegistry`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012fdc`

## callees

- `0x180013004`
- `0x180014dc0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x1800130f0`
- `ntdll!NtQueryValueKey` at `0x1800130f0`
- `ntdll!NtClose` at `0x180013111`
- `ntdll!NtClose` at `0x180013111`
- `ntdll!RtlInitUnicodeString` at `0x18001305b`
- `ntdll!RtlInitUnicodeString` at `0x1800130c7`
- `ntdll!RtlInitUnicodeString` at `0x18001305b`
- `ntdll!RtlInitUnicodeString` at `0x1800130c7`
- `ntdll!NtOpenKey` at `0x180013094`
- `ntdll!NtOpenKey` at `0x180013094`

## string_xrefs

- `0x180013023`: `\Registry\Machine\System\CurrentControlSet\Control\Compression`

## pseudocode

```c
int ReadCompressionSettingsFromRegistry()
{
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-19h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp+27h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+37h] BYREF
  int v7; // [rsp+A0h] [rbp+47h]

  ResultLength = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  v7 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  CmpsRegistrySettings = 0;
  DestinationString = 0;
  ValueName = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Compression");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  result = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"Settings");
    result = NtQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               &KeyValueInformation,
               0x14u,
               &ResultLength);
    if ( result >= 0 && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      result = HIDWORD(KeyValueInformation);
      CmpsRegistrySettings = HIDWORD(KeyValueInformation);
    }
  }
  if ( KeyHandle )
    return NtClose(KeyHandle);
  return result;
}

```

## disassembly

```asm
0x180013004  push    rbp
0x180013006  lea     rbp, [rsp-57h]
0x18001300b  sub     rsp, 0B0h
0x180013012  mov     rax, cs:__security_cookie
0x180013019  xor     rax, rsp
0x18001301c  mov     [rbp+57h+var_8], rax
0x180013020  xorps   xmm0, xmm0
0x180013023  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001302a  xor     eax, eax
0x18001302c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180013030  xorps   xmm1, xmm1
0x180013033  mov     [rbp+57h+var_80], eax
0x180013036  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001303a  mov     [rbp+57h+KeyHandle], rax
0x18001303e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180013042  mov     [rbp+57h+var_10], eax
0x180013045  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180013049  mov     cs:CmpsRegistrySettings, eax
0x18001304f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180013053  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x180013057  movups  [rbp+57h+KeyValueInformation], xmm0
0x18001305b  call    cs:__imp_RtlInitUnicodeString
0x180013061  lea     rax, [rbp+57h+DestinationString]
0x180013065  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001306c  xorps   xmm0, xmm0
0x18001306f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180013073  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180013077  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001307f  mov     edx, 20019h; DesiredAccess
0x180013084  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001308b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001308f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013094  call    cs:__imp_NtOpenKey
0x18001309a  test    eax, eax
0x18001309c  jns     short loc_1800130BC
0x18001309e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800130a2  test    rcx, rcx
0x1800130a5  jnz     short loc_180013111
0x1800130a7  mov     rcx, [rbp+57h+var_8]
0x1800130ab  xor     rcx, rsp; StackCookie
0x1800130ae  call    __security_check_cookie
0x1800130b3  add     rsp, 0B0h
0x1800130ba  pop     rbp
0x1800130bb  retn
0x1800130bc  lea     rdx, aSettings; "Settings"
0x1800130c3  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800130c7  call    cs:__imp_RtlInitUnicodeString
0x1800130cd  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800130d1  lea     rax, [rbp+57h+var_80]
0x1800130d5  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x1800130da  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800130de  mov     r8d, 2; KeyValueInformationClass
0x1800130e4  mov     [rsp+0B0h+Length], 14h; Length
0x1800130ec  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800130f0  call    cs:__imp_NtQueryValueKey
0x1800130f6  test    eax, eax
0x1800130f8  js      short loc_18001309E
0x1800130fa  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1800130fe  jnz     short loc_18001309E
0x180013100  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x180013104  jnz     short loc_18001309E
0x180013106  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x180013109  mov     cs:CmpsRegistrySettings, eax
0x18001310f  jmp     short loc_18001309E
0x180013111  call    cs:__imp_NtClose
0x180013117  jmp     short loc_1800130A7
```
