# PsmpGetCpuSpeed

- ea: `0x18001ff84`
- end: `0x18002009b`
- name: `PsmpGetCpuSpeed`
- size: `279`
- prototype: `NTSTATUS __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x18001f7a8`

## callees

- `0x18001b7e0`
- `0x18001ff84`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18002001f`
- `ntdll!NtOpenKey` at `0x18002001f`
- `ntdll!NtClose` at `0x180020072`
- `ntdll!NtClose` at `0x180020072`
- `ntdll!RtlInitUnicodeString` at `0x18001ffe6`
- `ntdll!RtlInitUnicodeString` at `0x180020034`
- `ntdll!RtlInitUnicodeString` at `0x18001ffe6`
- `ntdll!RtlInitUnicodeString` at `0x180020034`
- `ntdll!NtQueryValueKey` at `0x18002005d`
- `ntdll!NtQueryValueKey` at `0x18002005d`

## string_xrefs

- `0x18001ffc1`: `\Registry\Machine\HARDWARE\DESCRIPTION\System\CentralProcessor\0`

## pseudocode

```c
NTSTATUS __fastcall PsmpGetCpuSpeed(_DWORD *a1)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp+27h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+37h] BYREF

  ResultLength = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ValueName = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\0");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  result = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"~MHz");
    v3 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    if ( v3 >= 0 )
      *a1 = HIDWORD(KeyValueInformation);
    NtClose(KeyHandle);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18001ff84  mov     [rsp-8+arg_8], rbx
0x18001ff89  mov     [rsp-8+arg_10], rdi
0x18001ff8e  push    rbp
0x18001ff8f  lea     rbp, [rsp-57h]
0x18001ff94  sub     rsp, 0B0h
0x18001ff9b  mov     rax, cs:__security_cookie
0x18001ffa2  xor     rax, rsp
0x18001ffa5  mov     [rbp+57h+var_10], rax
0x18001ffa9  xorps   xmm0, xmm0
0x18001ffac  mov     [rbp+57h+var_80], 0
0x18001ffb3  mov     rdi, rcx
0x18001ffb6  mov     [rbp+57h+KeyHandle], 0
0x18001ffbe  xorps   xmm1, xmm1
0x18001ffc1  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\HARDWARE\\DESCRIPT"...
0x18001ffc8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001ffcc  xor     eax, eax
0x18001ffce  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001ffd2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001ffd6  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x18001ffda  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18001ffde  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001ffe2  movups  [rbp+57h+KeyValueInformation], xmm0
0x18001ffe6  call    cs:__imp_RtlInitUnicodeString
0x18001ffec  lea     rax, [rbp+57h+DestinationString]
0x18001fff0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001fff7  xorps   xmm0, xmm0
0x18001fffa  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001fffe  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180020002  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002000a  mov     edx, 20019h; DesiredAccess
0x18002000f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180020016  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002001a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002001f  call    cs:__imp_NtOpenKey
0x180020025  test    eax, eax
0x180020027  js      short loc_18002007A
0x180020029  lea     rdx, aMhz; "~MHz"
0x180020030  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180020034  call    cs:__imp_RtlInitUnicodeString
0x18002003a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002003e  lea     rax, [rbp+57h+var_80]
0x180020042  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x180020047  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18002004b  mov     r8d, 2; KeyValueInformationClass
0x180020051  mov     [rsp+0B0h+Length], 10h; Length
0x180020059  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18002005d  call    cs:__imp_NtQueryValueKey
0x180020063  mov     ebx, eax
0x180020065  test    eax, eax
0x180020067  js      short loc_18002006E
0x180020069  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x18002006c  mov     [rdi], ecx
0x18002006e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180020072  call    cs:__imp_NtClose
0x180020078  mov     eax, ebx
0x18002007a  mov     rcx, [rbp+57h+var_10]
0x18002007e  xor     rcx, rsp; StackCookie
0x180020081  call    __security_check_cookie
0x180020086  lea     r11, [rsp+0B0h+var_s0]
0x18002008e  mov     rbx, [r11+18h]
0x180020092  mov     rdi, [r11+20h]
0x180020096  mov     rsp, r11
0x180020099  pop     rbp
0x18002009a  retn
```
