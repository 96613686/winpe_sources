# I_PEConfigOptions

- ea: `0x180080354`
- end: `0x180080476`
- name: `I_PEConfigOptions`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x18007fe74`

## callees

- `0x18002bf20`
- `0x180080354`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800803a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800803b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800803a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800803b9`
- `ntoskrnl!ZwQueryValueKey` at `0x18008042b`
- `ntoskrnl!ZwQueryValueKey` at `0x18008042b`
- `ntoskrnl!ZwClose` at `0x180080454`
- `ntoskrnl!ZwClose` at `0x180080454`
- `ntoskrnl!ZwOpenKey` at `0x1800803f8`
- `ntoskrnl!ZwOpenKey` at `0x1800803f8`

## string_xrefs

- `0x18008037e`: `\Registry\Machine\System\CurrentControlSet\Services\PEAuth`

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
0x180080354  push    rbp
0x180080356  lea     rbp, [rsp-57h]
0x18008035b  sub     rsp, 0B0h
0x180080362  mov     rax, cs:__security_cookie
0x180080369  xor     rax, rsp
0x18008036c  mov     [rbp+57h+var_8], rax
0x180080370  xorps   xmm0, xmm0
0x180080373  mov     [rbp+57h+KeyHandle], 0
0x18008037b  xorps   xmm1, xmm1
0x18008037e  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x180080385  xor     eax, eax
0x180080387  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008038b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18008038f  mov     [rbp+57h+var_80], eax
0x180080392  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180080396  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18008039a  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x18008039e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800803a2  call    cs:__imp_RtlInitUnicodeString
0x1800803a9  nop     dword ptr [rax+rax+00h]
0x1800803ae  lea     rdx, aOptions; "Options"
0x1800803b5  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800803b9  call    cs:__imp_RtlInitUnicodeString
0x1800803c0  nop     dword ptr [rax+rax+00h]
0x1800803c5  lea     rax, [rbp+57h+DestinationString]
0x1800803c9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800803d0  xorps   xmm0, xmm0
0x1800803d3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800803d7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800803db  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800803e3  mov     edx, 20019h; DesiredAccess
0x1800803e8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800803ef  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800803f3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800803f8  call    cs:__imp_ZwOpenKey
0x1800803ff  nop     dword ptr [rax+rax+00h]
0x180080404  test    eax, eax
0x180080406  js      short loc_180080460
0x180080408  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008040c  lea     rax, [rbp+57h+var_80]
0x180080410  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x180080415  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180080419  mov     r8d, 2; KeyValueInformationClass
0x18008041f  mov     [rsp+0B0h+Length], 14h; Length
0x180080427  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18008042b  call    cs:__imp_ZwQueryValueKey
0x180080432  nop     dword ptr [rax+rax+00h]
0x180080437  test    eax, eax
0x180080439  js      short loc_180080450
0x18008043b  cmp     [rbp+57h+var_1C], 4
0x18008043f  jnz     short loc_180080450
0x180080441  cmp     [rbp+57h+var_18], 4
0x180080445  jnz     short loc_180080450
0x180080447  mov     eax, [rbp+57h+var_14]
0x18008044a  mov     cs:g_PEAuthConfigOptions, eax
0x180080450  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180080454  call    cs:__imp_ZwClose
0x18008045b  nop     dword ptr [rax+rax+00h]
0x180080460  mov     rcx, [rbp+57h+var_8]
0x180080464  xor     rcx, rsp; StackCookie
0x180080467  call    __security_check_cookie
0x18008046c  add     rsp, 0B0h
0x180080473  pop     rbp
0x180080474  retn
```
