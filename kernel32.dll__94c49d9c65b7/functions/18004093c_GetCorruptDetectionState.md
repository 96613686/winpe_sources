# GetCorruptDetectionState

- ea: `0x18004093c`
- end: `0x180040a41`
- name: `GetCorruptDetectionState`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800402f0`
- `0x180060dac`

## callees

- `0x18004093c`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180040a00`
- `ntdll!NtQueryValueKey` at `0x180040a00`
- `ntdll!NtOpenKey` at `0x1800409d5`
- `ntdll!NtOpenKey` at `0x1800409d5`
- `ntdll!NtClose` at `0x180040a0c`
- `ntdll!NtClose` at `0x180040a0c`
- `ntdll!RtlInitUnicodeString` at `0x18004098f`
- `ntdll!RtlInitUnicodeString` at `0x1800409a0`
- `ntdll!RtlInitUnicodeString` at `0x18004098f`
- `ntdll!RtlInitUnicodeString` at `0x1800409a0`

## string_xrefs

- `0x180040995`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`

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
0x18004093c  mov     [rsp-8+arg_0], rbx
0x180040941  mov     [rsp-8+arg_8], rdi
0x180040946  push    rbp
0x180040947  lea     rbp, [rsp-57h]
0x18004094c  sub     rsp, 0B0h
0x180040953  mov     rax, cs:__security_cookie
0x18004095a  xor     rax, rsp
0x18004095d  mov     [rbp+57h+var_8], rax
0x180040961  xorps   xmm0, xmm0
0x180040964  lea     rdx, aCorruptdetecti; "CorruptDetection"
0x18004096b  xor     edi, edi
0x18004096d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180040971  xorps   xmm1, xmm1
0x180040974  mov     [rbp+57h+KeyHandle], rdi
0x180040978  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18004097c  mov     [rbp+57h+var_80], edi
0x18004097f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180040983  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180040987  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18004098b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004098f  call    cs:__imp_RtlInitUnicodeString
0x180040995  lea     rdx, aRegistryMachin_26; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18004099c  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1800409a0  call    cs:__imp_RtlInitUnicodeString
0x1800409a6  lea     rax, [rbp+57h+var_70]
0x1800409aa  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800409b1  xorps   xmm0, xmm0
0x1800409b4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800409b8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800409bc  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x1800409c0  mov     edx, 20019h; DesiredAccess
0x1800409c5  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800409cc  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800409d0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800409d5  call    cs:__imp_NtOpenKey
0x1800409db  test    eax, eax
0x1800409dd  js      short loc_180040A1E
0x1800409df  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800409e3  lea     rax, [rbp+57h+var_80]
0x1800409e7  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x1800409ec  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800409f0  lea     r8d, [rdi+2]; KeyValueInformationClass
0x1800409f4  mov     [rsp+0B0h+Length], 14h; Length
0x1800409fc  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180040a00  call    cs:__imp_NtQueryValueKey
0x180040a06  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180040a0a  mov     ebx, eax
0x180040a0c  call    cs:__imp_NtClose
0x180040a12  test    ebx, ebx
0x180040a14  js      short loc_180040A1E
0x180040a16  cmp     [rbp+57h+var_1C], 4
0x180040a1a  cmovz   edi, [rbp+57h+var_14]
0x180040a1e  mov     eax, edi
0x180040a20  mov     rcx, [rbp+57h+var_8]
0x180040a24  xor     rcx, rsp; StackCookie
0x180040a27  call    __security_check_cookie
0x180040a2c  lea     r11, [rsp+0B0h+var_s0]
0x180040a34  mov     rbx, [r11+10h]
0x180040a38  mov     rdi, [r11+18h]
0x180040a3c  mov     rsp, r11
0x180040a3f  pop     rbp
0x180040a40  retn
```
