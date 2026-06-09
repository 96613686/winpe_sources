# GetCorruptDetectionState

- ea: `0x1800444e4`
- end: `0x180044608`
- name: `GetCorruptDetectionState`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043e44`
- `0x180067668`

## callees

- `0x1800444e4`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x1800445ba`
- `ntdll!NtQueryValueKey` at `0x1800445ba`
- `ntdll!NtOpenKey` at `0x180044589`
- `ntdll!NtOpenKey` at `0x180044589`
- `ntdll!NtClose` at `0x1800445cc`
- `ntdll!NtClose` at `0x1800445cc`
- `ntdll!RtlInitUnicodeString` at `0x180044537`
- `ntdll!RtlInitUnicodeString` at `0x18004454e`
- `ntdll!RtlInitUnicodeString` at `0x180044537`
- `ntdll!RtlInitUnicodeString` at `0x18004454e`

## string_xrefs

- `0x180044543`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`

## pseudocode

```c
__int64 GetCorruptDetectionState()
{
  unsigned int v0; // edi
  NTSTATUS v1; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING v5; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v9; // [rsp+94h] [rbp+3Bh]
  unsigned int v10; // [rsp+9Ch] [rbp+43h]

  v0 = 0;
  KeyHandle = 0;
  v5 = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"CorruptDetection");
  RtlInitUnicodeString(&v5, L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WOW");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v5;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v1 = NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength);
    NtClose(KeyHandle);
    if ( v1 >= 0 && v9 == 4 )
      return v10;
  }
  return v0;
}

```

## disassembly

```asm
0x1800444e4  mov     [rsp-8+arg_0], rbx
0x1800444e9  mov     [rsp-8+arg_8], rdi
0x1800444ee  push    rbp
0x1800444ef  lea     rbp, [rsp-57h]
0x1800444f4  sub     rsp, 0B0h
0x1800444fb  mov     rax, cs:__security_cookie
0x180044502  xor     rax, rsp
0x180044505  mov     [rbp+57h+var_8], rax
0x180044509  xorps   xmm0, xmm0
0x18004450c  lea     rdx, aCorruptdetecti; "CorruptDetection"
0x180044513  xor     edi, edi
0x180044515  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180044519  xorps   xmm1, xmm1
0x18004451c  mov     [rbp+57h+KeyHandle], rdi
0x180044520  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x180044524  mov     [rbp+57h+var_80], edi
0x180044527  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18004452b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18004452f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180044533  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180044537  call    cs:__imp_RtlInitUnicodeString
0x18004453e  nop     dword ptr [rax+rax+00h]
0x180044543  lea     rdx, aRegistryMachin_26; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18004454a  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18004454e  call    cs:__imp_RtlInitUnicodeString
0x180044555  nop     dword ptr [rax+rax+00h]
0x18004455a  lea     rax, [rbp+57h+var_70]
0x18004455e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180044565  xorps   xmm0, xmm0
0x180044568  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18004456c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180044570  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180044574  mov     edx, 20019h; DesiredAccess
0x180044579  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180044580  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180044584  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180044589  call    cs:__imp_NtOpenKey
0x180044590  nop     dword ptr [rax+rax+00h]
0x180044595  test    eax, eax
0x180044597  js      short loc_1800445E4
0x180044599  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004459d  lea     rax, [rbp+57h+var_80]
0x1800445a1  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x1800445a6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800445aa  lea     r8d, [rdi+2]; KeyValueInformationClass
0x1800445ae  mov     [rsp+0B0h+Length], 14h; Length
0x1800445b6  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800445ba  call    cs:__imp_NtQueryValueKey
0x1800445c1  nop     dword ptr [rax+rax+00h]
0x1800445c6  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800445ca  mov     ebx, eax
0x1800445cc  call    cs:__imp_NtClose
0x1800445d3  nop     dword ptr [rax+rax+00h]
0x1800445d8  test    ebx, ebx
0x1800445da  js      short loc_1800445E4
0x1800445dc  cmp     [rbp+57h+var_1C], 4
0x1800445e0  cmovz   edi, [rbp+57h+var_14]
0x1800445e4  mov     eax, edi
0x1800445e6  mov     rcx, [rbp+57h+var_8]
0x1800445ea  xor     rcx, rsp; StackCookie
0x1800445ed  call    __security_check_cookie
0x1800445f2  lea     r11, [rsp+0B0h+var_s0]
0x1800445fa  mov     rbx, [r11+10h]
0x1800445fe  mov     rdi, [r11+18h]
0x180044602  mov     rsp, r11
0x180044605  pop     rbp
0x180044606  retn
```
