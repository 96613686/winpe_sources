# ReadDisableMetaFilesRegKey

- ea: `0x180051814`
- end: `0x1800519b9`
- name: `ReadDisableMetaFilesRegKey`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b9f8`

## callees

- `0x180051814`
- `0x18007f800`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800518d6`
- `ntdll!RtlInitUnicodeString` at `0x180051939`
- `ntdll!RtlInitUnicodeString` at `0x1800518d6`
- `ntdll!RtlInitUnicodeString` at `0x180051939`
- `ntdll!NtOpenKey` at `0x18005191d`
- `ntdll!NtOpenKey` at `0x18005191d`
- `ntdll!NtClose` at `0x180051980`
- `ntdll!NtClose` at `0x180051980`
- `ntdll!NtQueryValueKey` at `0x18005196b`
- `ntdll!NtQueryValueKey` at `0x18005196b`

## string_xrefs

- `0x180051830`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\GRE_Initialize`

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
0x180051814  push    rbp
0x180051816  lea     rbp, [rsp-50h]
0x18005181b  sub     rsp, 150h
0x180051822  mov     rax, cs:__security_cookie
0x180051829  xor     rax, rsp
0x18005182c  mov     [rbp+50h+var_10], rax
0x180051830  movaps  xmm1, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x180051837  lea     rdx, [rbp+50h+SourceString]; SourceString
0x18005183b  xorps   xmm0, xmm0
0x18005183e  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x180051843  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x180051848  xor     eax, eax
0x18005184a  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x18005184f  mov     [rsp+150h+KeyHandle], rax
0x180051854  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x180051859  mov     [rsp+150h+var_120], eax
0x18005185d  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x180051862  mov     [rbp+50h+var_C0], eax
0x180051865  movups  [rbp+50h+KeyValueInformation], xmm0
0x180051869  mov     cs:gbDisableMetaFiles, eax
0x18005186f  movaps  xmm0, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\Software\\Microsoft\\Window"...
0x180051876  movups  [rbp+50h+var_A0], xmm0
0x18005187a  movaps  xmm0, xmmword ptr cs:aRegistryMachin+30h; "re\\Microsoft\\Windows NT\\CurrentVersi"...
0x180051881  movups  xmmword ptr [rbp+50h+SourceString], xmm1
0x180051885  movaps  xmm1, xmmword ptr cs:aRegistryMachin+20h; "e\\Software\\Microsoft\\Windows NT\\Cur"...
0x18005188c  movups  [rbp+50h+var_80], xmm0
0x180051890  movaps  xmm0, xmmword ptr cs:aRegistryMachin+50h; "dows NT\\CurrentVersion\\GRE_Initialize"
0x180051897  movups  [rbp+50h+var_90], xmm1
0x18005189b  movaps  xmm1, xmmword ptr cs:aRegistryMachin+40h; "soft\\Windows NT\\CurrentVersion\\GRE_I"...
0x1800518a2  movups  [rbp+50h+var_60], xmm0
0x1800518a6  movaps  xmm0, xmmword ptr cs:aRegistryMachin+70h; "ersion\\GRE_Initialize"
0x1800518ad  movups  [rbp+50h+var_70], xmm1
0x1800518b1  movaps  xmm1, xmmword ptr cs:aRegistryMachin+60h; "CurrentVersion\\GRE_Initialize"
0x1800518b8  movups  [rbp+50h+var_40], xmm0
0x1800518bc  movups  xmm0, xmmword ptr cs:aRegistryMachin+8Ch; "tialize"
0x1800518c3  movups  [rbp+50h+var_50], xmm1
0x1800518c7  movaps  xmm1, xmmword ptr cs:aRegistryMachin+80h; "RE_Initialize"
0x1800518ce  movups  [rbp+50h+var_30], xmm1
0x1800518d2  movups  [rbp+50h+var_30+0Ch], xmm0
0x1800518d6  call    cs:__imp_RtlInitUnicodeString
0x1800518dd  nop     dword ptr [rax+rax+00h]
0x1800518e2  lea     rax, [rsp+150h+DestinationString]
0x1800518e7  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1800518ef  xorps   xmm0, xmm0
0x1800518f2  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x1800518f7  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1800518fc  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x180051905  mov     edx, 20019h; DesiredAccess
0x18005190a  mov     [rsp+150h+ObjectAttributes.Attributes], 40h ; '@'
0x180051912  lea     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x180051917  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005191d  call    cs:__imp_NtOpenKey
0x180051924  nop     dword ptr [rax+rax+00h]
0x180051929  test    eax, eax
0x18005192b  js      short loc_18005198C
0x18005192d  lea     rdx, aDisablemetafil; "DisableMetaFiles"
0x180051934  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x180051939  call    cs:__imp_RtlInitUnicodeString
0x180051940  nop     dword ptr [rax+rax+00h]
0x180051945  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x18005194a  lea     rax, [rsp+150h+var_120]
0x18005194f  mov     [rsp+150h+ResultLength], rax; ResultLength
0x180051954  lea     r9, [rbp+50h+KeyValueInformation]; KeyValueInformation
0x180051958  mov     r8d, 2; KeyValueInformationClass
0x18005195e  mov     [rsp+150h+Length], 14h; Length
0x180051966  lea     rdx, [rsp+150h+DestinationString]; ValueName
0x18005196b  call    cs:__imp_NtQueryValueKey
0x180051972  nop     dword ptr [rax+rax+00h]
0x180051977  test    eax, eax
0x180051979  jns     short loc_1800519A2
0x18005197b  mov     rcx, [rsp+150h+KeyHandle]; Handle
0x180051980  call    cs:__imp_NtClose
0x180051987  nop     dword ptr [rax+rax+00h]
0x18005198c  mov     rcx, [rbp+50h+var_10]
0x180051990  xor     rcx, rsp; StackCookie
0x180051993  call    __security_check_cookie
0x180051998  add     rsp, 150h
0x18005199f  pop     rbp
0x1800519a0  retn
0x1800519a2  cmp     dword ptr [rbp+50h+KeyValueInformation+8], 4
0x1800519a6  jnz     short loc_18005197B
0x1800519a8  cmp     dword ptr [rbp+50h+KeyValueInformation+4], 4
0x1800519ac  jnz     short loc_18005197B
0x1800519ae  mov     eax, dword ptr [rbp+50h+KeyValueInformation+0Ch]
0x1800519b1  mov     cs:gbDisableMetaFiles, eax
0x1800519b7  jmp     short loc_18005197B
```
