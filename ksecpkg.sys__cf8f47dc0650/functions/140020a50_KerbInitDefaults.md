# KerbInitDefaults

- ea: `0x140020a50`
- end: `0x140020b8a`
- name: `KerbInitDefaults`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020c10`

## callees

- `0x140010160`
- `0x140020a50`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140020afe`
- `ntoskrnl!ZwOpenKey` at `0x140020afe`
- `ntoskrnl!ZwClose` at `0x140020b5e`
- `ntoskrnl!ZwClose` at `0x140020b5e`
- `ntoskrnl!ZwQueryValueKey` at `0x140020b33`
- `ntoskrnl!ZwQueryValueKey` at `0x140020b33`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020aa8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020abf`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020aa8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020abf`

## string_xrefs

- `0x140020a85`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters`
- `0x140020ab4`: `MaxTokenSize`

## pseudocode

```c
__int64 KerbInitDefaults()
{
  NTSTATUS v0; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+37h] BYREF

  ResultLength = 0;
  KeyHandle = (void *)-1LL;
  DestinationString = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyValueInformation = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Parameters");
  RtlInitUnicodeString(&ValueName, L"MaxTokenSize");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v0 >= 0 )
  {
    v0 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    if ( v0 >= 0 && DWORD1(KeyValueInformation) == 4 )
      KerbMaxTokenSize = HIDWORD(KeyValueInformation);
  }
  if ( KeyHandle != (void *)-1LL )
    ZwClose(KeyHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140020a50  mov     [rsp-8+arg_0], rbx
0x140020a55  push    rbp
0x140020a56  lea     rbp, [rsp-57h]
0x140020a5b  sub     rsp, 0B0h
0x140020a62  mov     rax, cs:__security_cookie
0x140020a69  xor     rax, rsp
0x140020a6c  mov     [rbp+57h+var_10], rax
0x140020a70  xorps   xmm0, xmm0
0x140020a73  mov     [rbp+57h+var_80], 0
0x140020a7a  xorps   xmm1, xmm1
0x140020a7d  mov     [rbp+57h+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x140020a85  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x140020a8c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140020a90  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140020a94  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140020a98  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140020a9c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140020aa0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140020aa4  movups  [rbp+57h+KeyValueInformation], xmm0
0x140020aa8  call    cs:__imp_RtlInitUnicodeString
0x140020aaf  nop     dword ptr [rax+rax+00h]
0x140020ab4  lea     rdx, aMaxtokensize; "MaxTokenSize"
0x140020abb  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140020abf  call    cs:__imp_RtlInitUnicodeString
0x140020ac6  nop     dword ptr [rax+rax+00h]
0x140020acb  lea     rax, [rbp+57h+DestinationString]
0x140020acf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140020ad6  xorps   xmm0, xmm0
0x140020ad9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140020add  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140020ae1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140020ae9  mov     edx, 20019h; DesiredAccess
0x140020aee  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140020af5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140020af9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140020afe  call    cs:__imp_ZwOpenKey
0x140020b05  nop     dword ptr [rax+rax+00h]
0x140020b0a  mov     ebx, eax
0x140020b0c  test    eax, eax
0x140020b0e  js      short loc_140020B54
0x140020b10  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140020b14  lea     rax, [rbp+57h+var_80]
0x140020b18  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140020b1d  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140020b21  mov     r8d, 2; KeyValueInformationClass
0x140020b27  mov     [rsp+0B0h+Length], 10h; Length
0x140020b2f  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140020b33  call    cs:__imp_ZwQueryValueKey
0x140020b3a  nop     dword ptr [rax+rax+00h]
0x140020b3f  mov     ebx, eax
0x140020b41  test    eax, eax
0x140020b43  js      short loc_140020B54
0x140020b45  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140020b49  jnz     short loc_140020B54
0x140020b4b  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140020b4e  mov     cs:?KerbMaxTokenSize@@3KA, eax; ulong KerbMaxTokenSize
0x140020b54  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140020b58  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140020b5c  jz      short loc_140020B6A
0x140020b5e  call    cs:__imp_ZwClose
0x140020b65  nop     dword ptr [rax+rax+00h]
0x140020b6a  mov     eax, ebx
0x140020b6c  mov     rcx, [rbp+57h+var_10]
0x140020b70  xor     rcx, rsp; StackCookie
0x140020b73  call    __security_check_cookie
0x140020b78  mov     rbx, [rsp+0B0h+arg_0]
0x140020b80  add     rsp, 0B0h
0x140020b87  pop     rbp
0x140020b88  retn
```
