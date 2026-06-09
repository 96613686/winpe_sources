# GetDescriptionOffset

- ea: `0x180003604`
- end: `0x18000371b`
- name: `GetDescriptionOffset`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x1800034c8`

## callees

- `0x180003604`
- `0x180009930`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800036a0`
- `ntdll!NtOpenKey` at `0x1800036a0`
- `ntdll!RtlInitUnicodeString` at `0x180003656`
- `ntdll!RtlInitUnicodeString` at `0x180003667`
- `ntdll!RtlInitUnicodeString` at `0x180003656`
- `ntdll!RtlInitUnicodeString` at `0x180003667`
- `ntdll!NtQueryValueKey` at `0x1800036d1`
- `ntdll!NtQueryValueKey` at `0x1800036d1`
- `ntdll!NtClose` at `0x1800036f6`
- `ntdll!NtClose` at `0x1800036f6`

## string_xrefs

- `0x180003631`: `\Registry\Machine\System\CurrentControlSet\Services\TermService\Performance`

## pseudocode

```c
__int64 GetDescriptionOffset()
{
  NTSTATUS v0; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-19h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp+27h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v8; // [rsp+94h] [rbp+3Bh]
  int v9; // [rsp+98h] [rbp+3Fh]
  int v10; // [rsp+9Ch] [rbp+43h]

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  *(&ObjectAttributes.Length + 1) = 0;
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\TermService\\Performance");
  RtlInitUnicodeString(&ValueName, L"First Counter");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v0 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v0 >= 0 )
  {
    ResultLength = 19;
    v0 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x13u, &ResultLength);
    if ( v0 >= 0 && v9 == 4 && v8 == 4 )
      dword_180012AB0 = v10;
    NtClose(KeyHandle);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180003604  mov     [rsp-8+arg_0], rbx
0x180003609  push    rbp
0x18000360a  lea     rbp, [rsp-57h]
0x18000360f  sub     rsp, 0B0h
0x180003616  mov     rax, cs:__security_cookie
0x18000361d  xor     rax, rsp
0x180003620  mov     [rbp+57h+var_8], rax
0x180003624  xorps   xmm0, xmm0
0x180003627  mov     [rbp+57h+KeyHandle], 0
0x18000362f  xor     eax, eax
0x180003631  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x180003638  xorps   xmm1, xmm1
0x18000363b  mov     [rbp+57h+var_80], eax
0x18000363e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180003642  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180003646  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000364a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000364e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180003652  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x180003656  call    cs:__imp_RtlInitUnicodeString
0x18000365c  lea     rdx, ValueName; "First Counter"
0x180003663  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180003667  call    cs:__imp_RtlInitUnicodeString
0x18000366d  lea     rax, [rbp+57h+DestinationString]
0x180003671  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180003678  xorps   xmm0, xmm0
0x18000367b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000367f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180003683  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000368b  mov     edx, 20019h; DesiredAccess
0x180003690  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180003697  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000369b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800036a0  call    cs:__imp_NtOpenKey
0x1800036a6  mov     ebx, eax
0x1800036a8  test    eax, eax
0x1800036aa  js      short loc_1800036FC
0x1800036ac  mov     ecx, 13h
0x1800036b1  lea     rax, [rbp+57h+var_80]
0x1800036b5  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x1800036ba  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800036be  mov     [rbp+57h+var_80], ecx
0x1800036c1  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800036c5  mov     [rsp+0B0h+Length], ecx; Length
0x1800036c9  lea     r8d, [rcx-11h]; KeyValueInformationClass
0x1800036cd  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800036d1  call    cs:__imp_NtQueryValueKey
0x1800036d7  mov     ebx, eax
0x1800036d9  test    eax, eax
0x1800036db  js      short loc_1800036F2
0x1800036dd  cmp     [rbp+57h+var_18], 4
0x1800036e1  jnz     short loc_1800036F2
0x1800036e3  cmp     [rbp+57h+var_1C], 4
0x1800036e7  jnz     short loc_1800036F2
0x1800036e9  mov     eax, [rbp+57h+var_14]
0x1800036ec  mov     cs:dword_180012AB0, eax
0x1800036f2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800036f6  call    cs:__imp_NtClose
0x1800036fc  mov     eax, ebx
0x1800036fe  mov     rcx, [rbp+57h+var_8]
0x180003702  xor     rcx, rsp; StackCookie
0x180003705  call    __security_check_cookie
0x18000370a  mov     rbx, [rsp+0B0h+arg_0]
0x180003712  add     rsp, 0B0h
0x180003719  pop     rbp
0x18000371a  retn
```
