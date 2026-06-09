# Pku2uInitDefaults

- ea: `0x140021ea0`
- end: `0x140022000`
- name: `Pku2uInitDefaults`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400220c0`

## callees

- `0x140007008`
- `0x140010160`
- `0x140021ea0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140021f4e`
- `ntoskrnl!ZwOpenKey` at `0x140021f4e`
- `ntoskrnl!ZwClose` at `0x140021fd4`
- `ntoskrnl!ZwClose` at `0x140021fd4`
- `ntoskrnl!ZwQueryValueKey` at `0x140021f95`
- `ntoskrnl!ZwQueryValueKey` at `0x140021f95`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021ef8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021f0f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021ef8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021f0f`

## string_xrefs

- `0x140021f04`: `MaxTokenSize`
- `0x140021ed5`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\Pku2uSSP\Parameters`
- `0x140021f69`: `Pku2uInitDefault:OpenKey failed:0x%x\n`

## pseudocode

```c
__int64 Pku2uInitDefaults()
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  NTSTATUS v2; // eax
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
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\Pku2uSSP\\Parameters");
  RtlInitUnicodeString(&ValueName, L"MaxTokenSize");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v2 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    v1 = v2;
    if ( (v2 < 0 || DWORD1(KeyValueInformation) != 4) && KsecInfoLevel )
      KsecDebugOut(2, "Pku2uInitDefault:QueryValueKey failed:0x%x\n", (unsigned int)v2);
  }
  else if ( KsecInfoLevel )
  {
    KsecDebugOut(2, "Pku2uInitDefault:OpenKey failed:0x%x\n", (unsigned int)v0);
  }
  if ( KeyHandle != (void *)-1LL )
    ZwClose(KeyHandle);
  return v1;
}

```

## disassembly

```asm
0x140021ea0  mov     [rsp-8+arg_0], rbx
0x140021ea5  push    rbp
0x140021ea6  lea     rbp, [rsp-57h]
0x140021eab  sub     rsp, 0B0h
0x140021eb2  mov     rax, cs:__security_cookie
0x140021eb9  xor     rax, rsp
0x140021ebc  mov     [rbp+57h+var_10], rax
0x140021ec0  xorps   xmm0, xmm0
0x140021ec3  mov     [rbp+57h+var_80], 0
0x140021eca  xorps   xmm1, xmm1
0x140021ecd  mov     [rbp+57h+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x140021ed5  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140021edc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140021ee0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140021ee4  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140021ee8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140021eec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140021ef0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140021ef4  movups  [rbp+57h+KeyValueInformation], xmm0
0x140021ef8  call    cs:__imp_RtlInitUnicodeString
0x140021eff  nop     dword ptr [rax+rax+00h]
0x140021f04  lea     rdx, aMaxtokensize; "MaxTokenSize"
0x140021f0b  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140021f0f  call    cs:__imp_RtlInitUnicodeString
0x140021f16  nop     dword ptr [rax+rax+00h]
0x140021f1b  lea     rax, [rbp+57h+DestinationString]
0x140021f1f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140021f26  xorps   xmm0, xmm0
0x140021f29  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140021f2d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140021f31  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140021f39  mov     edx, 20019h; DesiredAccess
0x140021f3e  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140021f45  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140021f49  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140021f4e  call    cs:__imp_ZwOpenKey
0x140021f55  nop     dword ptr [rax+rax+00h]
0x140021f5a  mov     ebx, eax
0x140021f5c  test    eax, eax
0x140021f5e  jns     short loc_140021F72
0x140021f60  cmp     cs:KsecInfoLevel, 0
0x140021f67  jz      short loc_140021FCA
0x140021f69  lea     rdx, aPku2uinitdefau_0; "Pku2uInitDefault:OpenKey failed:0x%x\n"
0x140021f70  jmp     short loc_140021FBD
0x140021f72  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140021f76  lea     rax, [rbp+57h+var_80]
0x140021f7a  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140021f7f  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140021f83  mov     r8d, 2; KeyValueInformationClass
0x140021f89  mov     [rsp+0B0h+Length], 10h; Length
0x140021f91  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140021f95  call    cs:__imp_ZwQueryValueKey
0x140021f9c  nop     dword ptr [rax+rax+00h]
0x140021fa1  mov     ebx, eax
0x140021fa3  test    eax, eax
0x140021fa5  js      short loc_140021FAD
0x140021fa7  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140021fab  jz      short loc_140021FCA
0x140021fad  cmp     cs:KsecInfoLevel, 0
0x140021fb4  jz      short loc_140021FCA
0x140021fb6  lea     rdx, aPku2uinitdefau; "Pku2uInitDefault:QueryValueKey failed:0"...
0x140021fbd  mov     r8d, eax
0x140021fc0  mov     ecx, 2
0x140021fc5  call    KsecDebugOut
0x140021fca  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140021fce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140021fd2  jz      short loc_140021FE0
0x140021fd4  call    cs:__imp_ZwClose
0x140021fdb  nop     dword ptr [rax+rax+00h]
0x140021fe0  mov     eax, ebx
0x140021fe2  mov     rcx, [rbp+57h+var_10]
0x140021fe6  xor     rcx, rsp; StackCookie
0x140021fe9  call    __security_check_cookie
0x140021fee  mov     rbx, [rsp+0B0h+arg_0]
0x140021ff6  add     rsp, 0B0h
0x140021ffd  pop     rbp
0x140021ffe  retn
```
