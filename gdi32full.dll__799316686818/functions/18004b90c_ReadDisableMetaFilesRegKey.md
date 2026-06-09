# ReadDisableMetaFilesRegKey

- ea: `0x18004b90c`
- end: `0x18004ba92`
- name: `ReadDisableMetaFilesRegKey`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057424`

## callees

- `0x18004b90c`
- `0x18007ac50`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004b9ce`
- `ntdll!RtlInitUnicodeString` at `0x18004ba25`
- `ntdll!RtlInitUnicodeString` at `0x18004b9ce`
- `ntdll!RtlInitUnicodeString` at `0x18004ba25`
- `ntdll!NtOpenKey` at `0x18004ba0f`
- `ntdll!NtOpenKey` at `0x18004ba0f`
- `ntdll!NtClose` at `0x18004ba60`
- `ntdll!NtClose` at `0x18004ba60`
- `ntdll!NtQueryValueKey` at `0x18004ba51`
- `ntdll!NtQueryValueKey` at `0x18004ba51`

## string_xrefs

- `0x18004b928`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\GRE_Initialize`

## pseudocode

```c
int ReadDisableMetaFilesRegKey()
{
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-80h] BYREF
  int v6; // [rsp+90h] [rbp-70h]
  WCHAR SourceString[80]; // [rsp+A0h] [rbp-60h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  v6 = 0;
  KeyValueInformation = 0;
  gbDisableMetaFiles = 0;
  wcscpy(SourceString, L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\GRE_Itialize");
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"DisableMetaFiles");
    if ( NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x14u,
           &ResultLength) >= 0
      && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      gbDisableMetaFiles = HIDWORD(KeyValueInformation);
    }
    return NtClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x18004b90c  push    rbp
0x18004b90e  lea     rbp, [rsp-50h]
0x18004b913  sub     rsp, 150h
0x18004b91a  mov     rax, cs:__security_cookie
0x18004b921  xor     rax, rsp
0x18004b924  mov     [rbp+50h+var_10], rax
0x18004b928  movaps  xmm1, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x18004b92f  lea     rdx, [rbp+50h+SourceString]; SourceString
0x18004b933  xorps   xmm0, xmm0
0x18004b936  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x18004b93b  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x18004b940  xor     eax, eax
0x18004b942  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x18004b947  mov     [rsp+150h+KeyHandle], rax
0x18004b94c  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x18004b951  mov     [rsp+150h+var_120], eax
0x18004b955  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x18004b95a  mov     [rbp+50h+var_C0], eax
0x18004b95d  movups  [rbp+50h+KeyValueInformation], xmm0
0x18004b961  mov     cs:gbDisableMetaFiles, eax
0x18004b967  movaps  xmm0, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\Software\\Microsoft\\Window"...
0x18004b96e  movups  [rbp+50h+var_A0], xmm0
0x18004b972  movaps  xmm0, xmmword ptr cs:aRegistryMachin+30h; "re\\Microsoft\\Windows NT\\CurrentVersi"...
0x18004b979  movups  xmmword ptr [rbp+50h+SourceString], xmm1
0x18004b97d  movaps  xmm1, xmmword ptr cs:aRegistryMachin+20h; "e\\Software\\Microsoft\\Windows NT\\Cur"...
0x18004b984  movups  [rbp+50h+var_80], xmm0
0x18004b988  movaps  xmm0, xmmword ptr cs:aRegistryMachin+50h; "dows NT\\CurrentVersion\\GRE_Initialize"
0x18004b98f  movups  [rbp+50h+var_90], xmm1
0x18004b993  movaps  xmm1, xmmword ptr cs:aRegistryMachin+40h; "soft\\Windows NT\\CurrentVersion\\GRE_I"...
0x18004b99a  movups  [rbp+50h+var_60], xmm0
0x18004b99e  movaps  xmm0, xmmword ptr cs:aRegistryMachin+70h; "ersion\\GRE_Initialize"
0x18004b9a5  movups  [rbp+50h+var_70], xmm1
0x18004b9a9  movaps  xmm1, xmmword ptr cs:aRegistryMachin+60h; "CurrentVersion\\GRE_Initialize"
0x18004b9b0  movups  [rbp+50h+var_40], xmm0
0x18004b9b4  movups  xmm0, xmmword ptr cs:aRegistryMachin+8Ch; "tialize"
0x18004b9bb  movups  [rbp+50h+var_50], xmm1
0x18004b9bf  movaps  xmm1, xmmword ptr cs:aRegistryMachin+80h; "RE_Initialize"
0x18004b9c6  movups  [rbp+50h+var_30], xmm1
0x18004b9ca  movups  [rbp+50h+var_30+0Ch], xmm0
0x18004b9ce  call    cs:__imp_RtlInitUnicodeString
0x18004b9d4  lea     rax, [rsp+150h+DestinationString]
0x18004b9d9  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x18004b9e1  xorps   xmm0, xmm0
0x18004b9e4  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x18004b9e9  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x18004b9ee  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x18004b9f7  mov     edx, 20019h; DesiredAccess
0x18004b9fc  mov     [rsp+150h+ObjectAttributes.Attributes], 40h ; '@'
0x18004ba04  lea     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x18004ba09  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004ba0f  call    cs:__imp_NtOpenKey
0x18004ba15  test    eax, eax
0x18004ba17  js      short loc_18004BA66
0x18004ba19  lea     rdx, aDisablemetafil; "DisableMetaFiles"
0x18004ba20  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x18004ba25  call    cs:__imp_RtlInitUnicodeString
0x18004ba2b  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x18004ba30  lea     rax, [rsp+150h+var_120]
0x18004ba35  mov     [rsp+150h+ResultLength], rax; ResultLength
0x18004ba3a  lea     r9, [rbp+50h+KeyValueInformation]; KeyValueInformation
0x18004ba3e  mov     r8d, 2; KeyValueInformationClass
0x18004ba44  mov     [rsp+150h+Length], 14h; Length
0x18004ba4c  lea     rdx, [rsp+150h+DestinationString]; ValueName
0x18004ba51  call    cs:__imp_NtQueryValueKey
0x18004ba57  test    eax, eax
0x18004ba59  jns     short loc_18004BA7B
0x18004ba5b  mov     rcx, [rsp+150h+KeyHandle]; Handle
0x18004ba60  call    cs:__imp_NtClose
0x18004ba66  mov     rcx, [rbp+50h+var_10]
0x18004ba6a  xor     rcx, rsp; StackCookie
0x18004ba6d  call    __security_check_cookie
0x18004ba72  add     rsp, 150h
0x18004ba79  pop     rbp
0x18004ba7a  retn
0x18004ba7b  cmp     dword ptr [rbp+50h+KeyValueInformation+8], 4
0x18004ba7f  jnz     short loc_18004BA5B
0x18004ba81  cmp     dword ptr [rbp+50h+KeyValueInformation+4], 4
0x18004ba85  jnz     short loc_18004BA5B
0x18004ba87  mov     eax, dword ptr [rbp+50h+KeyValueInformation+0Ch]
0x18004ba8a  mov     cs:gbDisableMetaFiles, eax
0x18004ba90  jmp     short loc_18004BA5B
```
