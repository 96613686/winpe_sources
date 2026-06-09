# NegoExtsInitDefaults

- ea: `0x1400223a4`
- end: `0x140022504`
- name: `NegoExtsInitDefaults`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140022660`

## callees

- `0x140007008`
- `0x140010160`
- `0x1400223a4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140022452`
- `ntoskrnl!ZwOpenKey` at `0x140022452`
- `ntoskrnl!ZwClose` at `0x1400224d8`
- `ntoskrnl!ZwClose` at `0x1400224d8`
- `ntoskrnl!ZwQueryValueKey` at `0x140022499`
- `ntoskrnl!ZwQueryValueKey` at `0x140022499`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400223fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022413`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400223fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022413`

## string_xrefs

- `0x140022408`: `MaxTokenSize`
- `0x14002246d`: `NegoExtsInitDefault:OpenKey failed:0x%x\n`
- `0x1400223d9`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\NegoExtender\Parameters`

## pseudocode

```c
__int64 NegoExtsInitDefaults()
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
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\NegoExtender\\Parameters");
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
      KsecDebugOut(2, "NegoExtsInitDefault:QueryValueKey failed:0x%x\n", (unsigned int)v2);
  }
  else if ( KsecInfoLevel )
  {
    KsecDebugOut(2, "NegoExtsInitDefault:OpenKey failed:0x%x\n", (unsigned int)v0);
  }
  if ( KeyHandle != (void *)-1LL )
    ZwClose(KeyHandle);
  return v1;
}

```

## disassembly

```asm
0x1400223a4  mov     [rsp-8+arg_0], rbx
0x1400223a9  push    rbp
0x1400223aa  lea     rbp, [rsp-57h]
0x1400223af  sub     rsp, 0B0h
0x1400223b6  mov     rax, cs:__security_cookie
0x1400223bd  xor     rax, rsp
0x1400223c0  mov     [rbp+57h+var_10], rax
0x1400223c4  xorps   xmm0, xmm0
0x1400223c7  mov     [rbp+57h+var_80], 0
0x1400223ce  xorps   xmm1, xmm1
0x1400223d1  mov     [rbp+57h+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x1400223d9  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400223e0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400223e4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400223e8  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1400223ec  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400223f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400223f4  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400223f8  movups  [rbp+57h+KeyValueInformation], xmm0
0x1400223fc  call    cs:__imp_RtlInitUnicodeString
0x140022403  nop     dword ptr [rax+rax+00h]
0x140022408  lea     rdx, aMaxtokensize; "MaxTokenSize"
0x14002240f  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140022413  call    cs:__imp_RtlInitUnicodeString
0x14002241a  nop     dword ptr [rax+rax+00h]
0x14002241f  lea     rax, [rbp+57h+DestinationString]
0x140022423  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002242a  xorps   xmm0, xmm0
0x14002242d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140022431  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140022435  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14002243d  mov     edx, 20019h; DesiredAccess
0x140022442  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140022449  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002244d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140022452  call    cs:__imp_ZwOpenKey
0x140022459  nop     dword ptr [rax+rax+00h]
0x14002245e  mov     ebx, eax
0x140022460  test    eax, eax
0x140022462  jns     short loc_140022476
0x140022464  cmp     cs:KsecInfoLevel, 0
0x14002246b  jz      short loc_1400224CE
0x14002246d  lea     rdx, aNegoextsinitde_0; "NegoExtsInitDefault:OpenKey failed:0x%x"...
0x140022474  jmp     short loc_1400224C1
0x140022476  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002247a  lea     rax, [rbp+57h+var_80]
0x14002247e  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140022483  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140022487  mov     r8d, 2; KeyValueInformationClass
0x14002248d  mov     [rsp+0B0h+Length], 10h; Length
0x140022495  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140022499  call    cs:__imp_ZwQueryValueKey
0x1400224a0  nop     dword ptr [rax+rax+00h]
0x1400224a5  mov     ebx, eax
0x1400224a7  test    eax, eax
0x1400224a9  js      short loc_1400224B1
0x1400224ab  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1400224af  jz      short loc_1400224CE
0x1400224b1  cmp     cs:KsecInfoLevel, 0
0x1400224b8  jz      short loc_1400224CE
0x1400224ba  lea     rdx, aNegoextsinitde; "NegoExtsInitDefault:QueryValueKey faile"...
0x1400224c1  mov     r8d, eax
0x1400224c4  mov     ecx, 2
0x1400224c9  call    KsecDebugOut
0x1400224ce  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400224d2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400224d6  jz      short loc_1400224E4
0x1400224d8  call    cs:__imp_ZwClose
0x1400224df  nop     dword ptr [rax+rax+00h]
0x1400224e4  mov     eax, ebx
0x1400224e6  mov     rcx, [rbp+57h+var_10]
0x1400224ea  xor     rcx, rsp; StackCookie
0x1400224ed  call    __security_check_cookie
0x1400224f2  mov     rbx, [rsp+0B0h+arg_0]
0x1400224fa  add     rsp, 0B0h
0x140022501  pop     rbp
0x140022502  retn
```
