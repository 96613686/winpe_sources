# ClfsRegistryQueryGroupPolicySetting

- ea: `0x14004e124`
- end: `0x14004e28d`
- name: `ClfsRegistryQueryGroupPolicySetting`
- size: `361`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400320b8`
- `0x14004d968`

## callees

- `0x140017e40`
- `0x14004e124`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004e265`
- `ntoskrnl!ZwClose` at `0x140080789`
- `ntoskrnl!ZwClose` at `0x14004e265`
- `ntoskrnl!ZwClose` at `0x140080789`
- `ntoskrnl!ZwOpenKey` at `0x14004e1e1`
- `ntoskrnl!ZwOpenKey` at `0x14004e1e1`
- `ntoskrnl!ZwQueryValueKey` at `0x14004e22d`
- `ntoskrnl!ZwQueryValueKey` at `0x14004e22d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e181`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e199`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e181`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e199`

## string_xrefs

- `0x14004e176`: `\Registry\Machine\System\CurrentControlSet\Policies`

## pseudocode

```c
bool ClfsRegistryQueryGroupPolicySetting()
{
  bool v0; // bl
  void *KeyHandle; // [rsp+30h] [rbp-88h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-80h] BYREF
  UNICODE_STRING v4; // [rsp+40h] [rbp-78h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-58h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp-28h] BYREF
  int v8; // [rsp+A0h] [rbp-18h]

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = 0;
  DestinationString = 0;
  ResultLength = 0;
  v0 = 1;
  RtlInitUnicodeString(&v4, L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies");
  RtlInitUnicodeString(&DestinationString, L"ClfsAuthenticationChecking");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v4;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
  {
    KeyValueInformation = 0;
    v8 = 0;
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x14u,
           &ResultLength) >= 0
      && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      v0 = HIDWORD(KeyValueInformation) == 1;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v0;
}

```

## disassembly

```asm
0x14004e124  mov     r11, rsp
0x14004e127  push    rbx
0x14004e128  sub     rsp, 0B0h
0x14004e12f  mov     rax, cs:__security_cookie
0x14004e136  xor     rax, rsp
0x14004e139  mov     [rsp+0B8h+var_10], rax
0x14004e141  mov     [rsp+0B8h+KeyHandle], 0
0x14004e14a  xorps   xmm0, xmm0
0x14004e14d  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x14004e152  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x14004e157  movups  xmmword ptr [r11-38h], xmm0
0x14004e15c  movups  [rsp+0B8h+var_78], xmm0
0x14004e161  xorps   xmm1, xmm1
0x14004e164  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm1
0x14004e169  mov     [rsp+0B8h+var_80], 0
0x14004e171  mov     ebx, 1
0x14004e176  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004e17d  lea     rcx, [r11-78h]; DestinationString
0x14004e181  call    cs:__imp_RtlInitUnicodeString
0x14004e188  nop     dword ptr [rax+rax+00h]
0x14004e18d  lea     rdx, aClfsauthentica; "ClfsAuthenticationChecking"
0x14004e194  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14004e199  call    cs:__imp_RtlInitUnicodeString
0x14004e1a0  nop     dword ptr [rax+rax+00h]
0x14004e1a5  nop
0x14004e1a6  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x14004e1ae  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], 0
0x14004e1b7  mov     [rsp+0B8h+ObjectAttributes.Attributes], 240h
0x14004e1bf  lea     rax, [rsp+0B8h+var_78]
0x14004e1c4  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x14004e1c9  xorps   xmm0, xmm0
0x14004e1cc  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e1d5  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x14004e1da  mov     edx, ebx; DesiredAccess
0x14004e1dc  lea     rcx, [rsp+0B8h+KeyHandle]; KeyHandle
0x14004e1e1  call    cs:__imp_ZwOpenKey
0x14004e1e8  nop     dword ptr [rax+rax+00h]
0x14004e1ed  test    eax, eax
0x14004e1ef  js      short loc_14004E25B
0x14004e1f1  xorps   xmm0, xmm0
0x14004e1f4  xor     eax, eax
0x14004e1f6  movups  [rsp+0B8h+KeyValueInformation], xmm0
0x14004e1fe  mov     [rsp+0B8h+var_18], eax
0x14004e205  lea     rax, [rsp+0B8h+var_80]
0x14004e20a  mov     [rsp+0B8h+ResultLength], rax; ResultLength
0x14004e20f  mov     [rsp+0B8h+Length], 14h; Length
0x14004e217  lea     r9, [rsp+0B8h+KeyValueInformation]; KeyValueInformation
0x14004e21f  lea     r8d, [rbx+1]; KeyValueInformationClass
0x14004e223  lea     rdx, [rsp+0B8h+DestinationString]; ValueName
0x14004e228  mov     rcx, [rsp+0B8h+KeyHandle]; KeyHandle
0x14004e22d  call    cs:__imp_ZwQueryValueKey
0x14004e234  nop     dword ptr [rax+rax+00h]
0x14004e239  test    eax, eax
0x14004e23b  js      short loc_14004E25B
0x14004e23d  cmp     dword ptr [rsp+0B8h+KeyValueInformation+4], 4
0x14004e245  jnz     short loc_14004E25B
0x14004e247  cmp     dword ptr [rsp+0B8h+KeyValueInformation+8], 4
0x14004e24f  jnz     short loc_14004E25B
0x14004e251  cmp     dword ptr [rsp+0B8h+KeyValueInformation+0Ch], ebx
0x14004e258  setz    bl
0x14004e25b  mov     rcx, [rsp+0B8h+KeyHandle]; Handle
0x14004e260  test    rcx, rcx
0x14004e263  jz      short loc_14004E271
0x14004e265  call    cs:__imp_ZwClose
0x14004e26c  nop     dword ptr [rax+rax+00h]
0x14004e271  mov     al, bl
0x14004e273  mov     rcx, [rsp+0B8h+var_10]
0x14004e27b  xor     rcx, rsp; StackCookie
0x14004e27e  call    __security_check_cookie
0x14004e283  add     rsp, 0B0h
0x14004e28a  pop     rbx
0x14004e28b  retn
0x140080777  push    rbp
0x140080779  sub     rsp, 30h
0x14008077d  mov     rbp, rdx
0x140080780  mov     rcx, [rbp+30h]; Handle
0x140080784  test    rcx, rcx
0x140080787  jz      short loc_140080796
0x140080789  call    cs:__imp_ZwClose
0x140080790  nop     dword ptr [rax+rax+00h]
0x140080795  nop
0x140080796  add     rsp, 30h
0x14008079a  pop     rbp
0x14008079b  retn
```
