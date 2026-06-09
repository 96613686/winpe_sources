# I_PEConfigOptions

- ea: `0x180080d68`
- end: `0x180080e8a`
- name: `I_PEConfigOptions`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x180080888`

## callees

- `0x18002c0d0`
- `0x180080d68`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180080db6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180080dcd`
- `ntoskrnl!RtlInitUnicodeString` at `0x180080db6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180080dcd`
- `ntoskrnl!ZwQueryValueKey` at `0x180080e3f`
- `ntoskrnl!ZwQueryValueKey` at `0x180080e3f`
- `ntoskrnl!ZwClose` at `0x180080e68`
- `ntoskrnl!ZwClose` at `0x180080e68`
- `ntoskrnl!ZwOpenKey` at `0x180080e0c`
- `ntoskrnl!ZwOpenKey` at `0x180080e0c`

## string_xrefs

- `0x180080d92`: `\Registry\Machine\System\CurrentControlSet\Services\PEAuth`

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
0x180080d68  push    rbp
0x180080d6a  lea     rbp, [rsp-57h]
0x180080d6f  sub     rsp, 0B0h
0x180080d76  mov     rax, cs:__security_cookie
0x180080d7d  xor     rax, rsp
0x180080d80  mov     [rbp+57h+var_8], rax
0x180080d84  xorps   xmm0, xmm0
0x180080d87  mov     [rbp+57h+KeyHandle], 0
0x180080d8f  xorps   xmm1, xmm1
0x180080d92  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x180080d99  xor     eax, eax
0x180080d9b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180080d9f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180080da3  mov     [rbp+57h+var_80], eax
0x180080da6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180080daa  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180080dae  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x180080db2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180080db6  call    cs:__imp_RtlInitUnicodeString
0x180080dbd  nop     dword ptr [rax+rax+00h]
0x180080dc2  lea     rdx, aOptions; "Options"
0x180080dc9  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180080dcd  call    cs:__imp_RtlInitUnicodeString
0x180080dd4  nop     dword ptr [rax+rax+00h]
0x180080dd9  lea     rax, [rbp+57h+DestinationString]
0x180080ddd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180080de4  xorps   xmm0, xmm0
0x180080de7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180080deb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180080def  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180080df7  mov     edx, 20019h; DesiredAccess
0x180080dfc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180080e03  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180080e07  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180080e0c  call    cs:__imp_ZwOpenKey
0x180080e13  nop     dword ptr [rax+rax+00h]
0x180080e18  test    eax, eax
0x180080e1a  js      short loc_180080E74
0x180080e1c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180080e20  lea     rax, [rbp+57h+var_80]
0x180080e24  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x180080e29  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180080e2d  mov     r8d, 2; KeyValueInformationClass
0x180080e33  mov     [rsp+0B0h+Length], 14h; Length
0x180080e3b  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180080e3f  call    cs:__imp_ZwQueryValueKey
0x180080e46  nop     dword ptr [rax+rax+00h]
0x180080e4b  test    eax, eax
0x180080e4d  js      short loc_180080E64
0x180080e4f  cmp     [rbp+57h+var_1C], 4
0x180080e53  jnz     short loc_180080E64
0x180080e55  cmp     [rbp+57h+var_18], 4
0x180080e59  jnz     short loc_180080E64
0x180080e5b  mov     eax, [rbp+57h+var_14]
0x180080e5e  mov     cs:g_PEAuthConfigOptions, eax
0x180080e64  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180080e68  call    cs:__imp_ZwClose
0x180080e6f  nop     dword ptr [rax+rax+00h]
0x180080e74  mov     rcx, [rbp+57h+var_8]
0x180080e78  xor     rcx, rsp; StackCookie
0x180080e7b  call    __security_check_cookie
0x180080e80  add     rsp, 0B0h
0x180080e87  pop     rbp
0x180080e88  retn
```
