# FCReadDriverParameters

- ea: `0x140014010`
- end: `0x1400142eb`
- name: `FCReadDriverParameters`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140014300`

## callees

- `0x140003540`
- `0x140014010`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400140ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001410b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014177`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400141e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001424f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400140ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001410b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014177`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400141e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001424f`
- `ntoskrnl!ZwQueryValueKey` at `0x1400140e2`
- `ntoskrnl!ZwQueryValueKey` at `0x140014141`
- `ntoskrnl!ZwQueryValueKey` at `0x1400141ad`
- `ntoskrnl!ZwQueryValueKey` at `0x140014219`
- `ntoskrnl!ZwQueryValueKey` at `0x140014285`
- `ntoskrnl!ZwQueryValueKey` at `0x1400140e2`
- `ntoskrnl!ZwQueryValueKey` at `0x140014141`
- `ntoskrnl!ZwQueryValueKey` at `0x1400141ad`
- `ntoskrnl!ZwQueryValueKey` at `0x140014219`
- `ntoskrnl!ZwQueryValueKey` at `0x140014285`
- `ntoskrnl!ZwOpenKey` at `0x140014082`
- `ntoskrnl!ZwOpenKey` at `0x140014082`
- `ntoskrnl!ZwClose` at `0x1400142bb`
- `ntoskrnl!ZwClose` at `0x140014662`
- `ntoskrnl!ZwClose` at `0x1400142bb`
- `ntoskrnl!ZwClose` at `0x140014662`

## string_xrefs

- `0x1400141d7`: `BypassAccessChecks`

## pseudocode

```c
__int64 __fastcall FCReadDriverParameters(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-78h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-58h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+80h] [rbp-28h] BYREF
  int v8; // [rsp+8Ch] [rbp-1Ch]

  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  v1 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
    if ( !FcDebugTraceLevel )
    {
      RtlInitUnicodeString(&DestinationString, L"DebugTraceLevel");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x14u,
             &ResultLength) >= 0 )
        FcDebugTraceLevel = v8;
    }
    RtlInitUnicodeString(&DestinationString, L"EncryptMedia");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength) >= 0 )
    {
      if ( v8 )
        gFCFlags |= 2u;
      else
        gFCFlags &= ~2u;
    }
    RtlInitUnicodeString(&DestinationString, L"EncryptAll");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength) >= 0 )
    {
      if ( v8 )
        gFCFlags |= 4u;
      else
        gFCFlags &= ~4u;
    }
    RtlInitUnicodeString(&DestinationString, L"BypassAccessChecks");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength) >= 0 )
    {
      if ( v8 )
        gFCFlags |= 0x10u;
      else
        gFCFlags &= ~0x10u;
    }
    RtlInitUnicodeString(&DestinationString, L"FilterEmulatedExternalDrive");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength) >= 0 )
    {
      if ( v8 )
        gFCFlags |= 8u;
      else
        gFCFlags &= ~8u;
    }
    v1 = 0;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140014010  mov     [rsp+arg_8], rbx
0x140014015  push    rdi
0x140014016  sub     rsp, 0A0h
0x14001401d  mov     rax, cs:__security_cookie
0x140014024  xor     rax, rsp
0x140014027  mov     [rsp+0A8h+var_10], rax
0x14001402f  xor     eax, eax
0x140014031  xorps   xmm0, xmm0
0x140014034  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x140014039  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x14001403e  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x140014043  xor     edi, edi
0x140014045  mov     [rsp+0A8h+KeyHandle], rdi
0x14001404a  mov     [rsp+0A8h+var_78], edi
0x14001404e  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x140014053  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x14001405b  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rdi
0x140014060  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x140014068  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rcx
0x14001406d  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014073  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x140014078  mov     edx, 20019h; DesiredAccess
0x14001407d  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x140014082  call    cs:__imp_ZwOpenKey
0x140014089  nop     dword ptr [rax+rax+00h]
0x14001408e  mov     ebx, eax
0x140014090  test    eax, eax
0x140014092  js      loc_1400142B1
0x140014098  cmp     cs:FcDebugTraceLevel, edi
0x14001409e  jnz     short loc_1400140FF
0x1400140a0  lea     rdx, aDebugtraceleve; "DebugTraceLevel"
0x1400140a7  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1400140ac  call    cs:__imp_RtlInitUnicodeString
0x1400140b3  nop     dword ptr [rax+rax+00h]
0x1400140b8  lea     rax, [rsp+0A8h+var_78]
0x1400140bd  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x1400140c2  mov     [rsp+0A8h+Length], 14h; Length
0x1400140ca  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x1400140d2  mov     r8d, 2; KeyValueInformationClass
0x1400140d8  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x1400140dd  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400140e2  call    cs:__imp_ZwQueryValueKey
0x1400140e9  nop     dword ptr [rax+rax+00h]
0x1400140ee  test    eax, eax
0x1400140f0  js      short loc_1400140FF
0x1400140f2  mov     eax, [rsp+0A8h+var_1C]
0x1400140f9  mov     cs:FcDebugTraceLevel, eax
0x1400140ff  lea     rdx, aEncryptmedia; "EncryptMedia"
0x140014106  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x14001410b  call    cs:__imp_RtlInitUnicodeString
0x140014112  nop     dword ptr [rax+rax+00h]
0x140014117  lea     rax, [rsp+0A8h+var_78]
0x14001411c  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x140014121  mov     [rsp+0A8h+Length], 14h; Length
0x140014129  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x140014131  mov     r8d, 2; KeyValueInformationClass
0x140014137  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x14001413c  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x140014141  call    cs:__imp_ZwQueryValueKey
0x140014148  nop     dword ptr [rax+rax+00h]
0x14001414d  test    eax, eax
0x14001414f  js      short loc_14001416B
0x140014151  cmp     [rsp+0A8h+var_1C], 0
0x140014159  jz      short loc_140014164
0x14001415b  or      cs:gFCFlags, 2
0x140014162  jmp     short loc_14001416B
0x140014164  and     cs:gFCFlags, 0FFFFFFFDh
0x14001416b  lea     rdx, aEncryptall; "EncryptAll"
0x140014172  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x140014177  call    cs:__imp_RtlInitUnicodeString
0x14001417e  nop     dword ptr [rax+rax+00h]
0x140014183  lea     rax, [rsp+0A8h+var_78]
0x140014188  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x14001418d  mov     [rsp+0A8h+Length], 14h; Length
0x140014195  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x14001419d  mov     r8d, 2; KeyValueInformationClass
0x1400141a3  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x1400141a8  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400141ad  call    cs:__imp_ZwQueryValueKey
0x1400141b4  nop     dword ptr [rax+rax+00h]
0x1400141b9  test    eax, eax
0x1400141bb  js      short loc_1400141D7
0x1400141bd  cmp     [rsp+0A8h+var_1C], 0
0x1400141c5  jz      short loc_1400141D0
0x1400141c7  or      cs:gFCFlags, 4
0x1400141ce  jmp     short loc_1400141D7
0x1400141d0  and     cs:gFCFlags, 0FFFFFFFBh
0x1400141d7  lea     rdx, aBypassaccessch; "BypassAccessChecks"
0x1400141de  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1400141e3  call    cs:__imp_RtlInitUnicodeString
0x1400141ea  nop     dword ptr [rax+rax+00h]
0x1400141ef  lea     rax, [rsp+0A8h+var_78]
0x1400141f4  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x1400141f9  mov     [rsp+0A8h+Length], 14h; Length
0x140014201  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x140014209  mov     r8d, 2; KeyValueInformationClass
0x14001420f  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x140014214  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x140014219  call    cs:__imp_ZwQueryValueKey
0x140014220  nop     dword ptr [rax+rax+00h]
0x140014225  test    eax, eax
0x140014227  js      short loc_140014243
0x140014229  cmp     [rsp+0A8h+var_1C], 0
0x140014231  jz      short loc_14001423C
0x140014233  or      cs:gFCFlags, 10h
0x14001423a  jmp     short loc_140014243
0x14001423c  and     cs:gFCFlags, 0FFFFFFEFh
0x140014243  lea     rdx, aFilteremulated; "FilterEmulatedExternalDrive"
0x14001424a  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x14001424f  call    cs:__imp_RtlInitUnicodeString
0x140014256  nop     dword ptr [rax+rax+00h]
0x14001425b  lea     rax, [rsp+0A8h+var_78]
0x140014260  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x140014265  mov     [rsp+0A8h+Length], 14h; Length
0x14001426d  lea     r9, [rsp+0A8h+KeyValueInformation]; KeyValueInformation
0x140014275  mov     r8d, 2; KeyValueInformationClass
0x14001427b  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x140014280  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x140014285  call    cs:__imp_ZwQueryValueKey
0x14001428c  nop     dword ptr [rax+rax+00h]
0x140014291  test    eax, eax
0x140014293  js      short loc_1400142AF
0x140014295  cmp     [rsp+0A8h+var_1C], 0
0x14001429d  jz      short loc_1400142A8
0x14001429f  or      cs:gFCFlags, 8
0x1400142a6  jmp     short loc_1400142AF
0x1400142a8  and     cs:gFCFlags, 0FFFFFFF7h
0x1400142af  mov     ebx, edi
0x1400142b1  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x1400142b6  test    rcx, rcx
0x1400142b9  jz      short loc_1400142C7
0x1400142bb  call    cs:__imp_ZwClose
0x1400142c2  nop     dword ptr [rax+rax+00h]
0x1400142c7  mov     eax, ebx
0x1400142c9  mov     rcx, [rsp+0A8h+var_10]
0x1400142d1  xor     rcx, rsp; StackCookie
0x1400142d4  call    __security_check_cookie
0x1400142d9  mov     rbx, [rsp+0A8h+arg_8]
0x1400142e1  add     rsp, 0A0h
0x1400142e8  pop     rdi
0x1400142e9  retn
0x140014650  push    rbp
0x140014652  sub     rsp, 30h
0x140014656  mov     rbp, rdx
0x140014659  mov     rcx, [rbp+38h]; Handle
0x14001465d  test    rcx, rcx
0x140014660  jz      short loc_14001466F
0x140014662  call    cs:__imp_ZwClose
0x140014669  nop     dword ptr [rax+rax+00h]
0x14001466e  nop
0x14001466f  add     rsp, 30h
0x140014673  pop     rbp
0x140014674  retn
```
