# ClassUpdateDynamicRegistrySettings

- ea: `0x14002c310`
- end: `0x14002c50f`
- name: `ClassUpdateDynamicRegistrySettings`
- size: `511`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140056a40`

## callees

- `0x14002c310`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002c34f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c3bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c426`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c48d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c34f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c3bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c426`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c48d`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c380`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c3f0`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c457`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c4be`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c380`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c3f0`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c457`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c4be`

## string_xrefs

- `0x14002c3b3`: `ProcessZoneCommandAsync`

## pseudocode

```c
NTSTATUS __fastcall ClassUpdateDynamicRegistrySettings(HANDLE KeyHandle)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v6; // [rsp+54h] [rbp-ACh]
  int v7; // [rsp+5Ch] [rbp-A4h]

  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"NVMeDisablePerfThrottling");
  if ( ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x110u,
         &ResultLength) < 0 )
  {
    ClassNVMeDisablePerfThrottling = 0;
  }
  else if ( v6 == 4 && ResultLength >= 4 )
  {
    ClassNVMeDisablePerfThrottling = v7 != 0;
  }
  RtlInitUnicodeString(&DestinationString, L"ProcessZoneCommandAsync");
  if ( ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x110u,
         &ResultLength) >= 0
    && v6 == 4
    && ResultLength >= 4 )
  {
    ProcessZoneCommandAsynchronously = v7 != 0;
  }
  RtlInitUnicodeString(&DestinationString, L"DisableOptimalIOAlignment");
  if ( ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x110u,
         &ResultLength) >= 0
    && v6 == 4
    && ResultLength >= 4 )
  {
    DisableOptimalIOAlignment = v7 != 0;
  }
  RtlInitUnicodeString(&DestinationString, L"DisableForwardedIo");
  result = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x110u,
             &ResultLength);
  if ( result < 0 )
  {
    ClassDisableForwardedIo = 0;
  }
  else if ( v6 == 4 && ResultLength >= 4 )
  {
    ClassDisableForwardedIo = v7 != 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002c310  mov     [rsp-8+arg_8], rbx
0x14002c315  push    rbp
0x14002c316  lea     rbp, [rsp-70h]
0x14002c31b  sub     rsp, 170h
0x14002c322  mov     rax, cs:__security_cookie
0x14002c329  xor     rax, rsp
0x14002c32c  mov     [rbp+70h+var_10], rax
0x14002c330  mov     rbx, rcx
0x14002c333  mov     [rsp+170h+var_140], 0
0x14002c33b  xorps   xmm0, xmm0
0x14002c33e  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x14002c343  lea     rdx, aNvmedisableper; "NVMeDisablePerfThrottling"
0x14002c34a  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x14002c34f  call    cs:__imp_RtlInitUnicodeString
0x14002c356  nop     dword ptr [rax+rax+00h]
0x14002c35b  lea     rax, [rsp+170h+var_140]
0x14002c360  mov     r8d, 2; KeyValueInformationClass
0x14002c366  mov     [rsp+170h+ResultLength], rax; ResultLength
0x14002c36b  lea     r9, [rsp+170h+KeyValueInformation]; KeyValueInformation
0x14002c370  lea     rdx, [rsp+170h+DestinationString]; ValueName
0x14002c375  mov     [rsp+170h+Length], 110h; Length
0x14002c37d  mov     rcx, rbx; KeyHandle
0x14002c380  call    cs:__imp_ZwQueryValueKey
0x14002c387  nop     dword ptr [rax+rax+00h]
0x14002c38c  test    eax, eax
0x14002c38e  js      short loc_14002C3AC
0x14002c390  cmp     [rsp+170h+var_11C], 4
0x14002c395  jnz     short loc_14002C3B3
0x14002c397  cmp     [rsp+170h+var_140], 4
0x14002c39c  jb      short loc_14002C3B3
0x14002c39e  cmp     [rsp+170h+var_114], 0
0x14002c3a3  setnz   cs:ClassNVMeDisablePerfThrottling
0x14002c3aa  jmp     short loc_14002C3B3
0x14002c3ac  mov     cs:ClassNVMeDisablePerfThrottling, 0
0x14002c3b3  lea     rdx, aProcesszonecom; "ProcessZoneCommandAsync"
0x14002c3ba  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x14002c3bf  call    cs:__imp_RtlInitUnicodeString
0x14002c3c6  nop     dword ptr [rax+rax+00h]
0x14002c3cb  lea     rax, [rsp+170h+var_140]
0x14002c3d0  mov     r8d, 2; KeyValueInformationClass
0x14002c3d6  mov     [rsp+170h+ResultLength], rax; ResultLength
0x14002c3db  lea     r9, [rsp+170h+KeyValueInformation]; KeyValueInformation
0x14002c3e0  lea     rdx, [rsp+170h+DestinationString]; ValueName
0x14002c3e5  mov     [rsp+170h+Length], 110h; Length
0x14002c3ed  mov     rcx, rbx; KeyHandle
0x14002c3f0  call    cs:__imp_ZwQueryValueKey
0x14002c3f7  nop     dword ptr [rax+rax+00h]
0x14002c3fc  test    eax, eax
0x14002c3fe  js      short loc_14002C41A
0x14002c400  cmp     [rsp+170h+var_11C], 4
0x14002c405  jnz     short loc_14002C41A
0x14002c407  cmp     [rsp+170h+var_140], 4
0x14002c40c  jb      short loc_14002C41A
0x14002c40e  cmp     [rsp+170h+var_114], 0
0x14002c413  setnz   cs:ProcessZoneCommandAsynchronously
0x14002c41a  lea     rdx, aDisableoptimal; "DisableOptimalIOAlignment"
0x14002c421  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x14002c426  call    cs:__imp_RtlInitUnicodeString
0x14002c42d  nop     dword ptr [rax+rax+00h]
0x14002c432  lea     rax, [rsp+170h+var_140]
0x14002c437  mov     r8d, 2; KeyValueInformationClass
0x14002c43d  mov     [rsp+170h+ResultLength], rax; ResultLength
0x14002c442  lea     r9, [rsp+170h+KeyValueInformation]; KeyValueInformation
0x14002c447  lea     rdx, [rsp+170h+DestinationString]; ValueName
0x14002c44c  mov     [rsp+170h+Length], 110h; Length
0x14002c454  mov     rcx, rbx; KeyHandle
0x14002c457  call    cs:__imp_ZwQueryValueKey
0x14002c45e  nop     dword ptr [rax+rax+00h]
0x14002c463  test    eax, eax
0x14002c465  js      short loc_14002C481
0x14002c467  cmp     [rsp+170h+var_11C], 4
0x14002c46c  jnz     short loc_14002C481
0x14002c46e  cmp     [rsp+170h+var_140], 4
0x14002c473  jb      short loc_14002C481
0x14002c475  cmp     [rsp+170h+var_114], 0
0x14002c47a  setnz   cs:DisableOptimalIOAlignment
0x14002c481  lea     rdx, aDisableforward; "DisableForwardedIo"
0x14002c488  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x14002c48d  call    cs:__imp_RtlInitUnicodeString
0x14002c494  nop     dword ptr [rax+rax+00h]
0x14002c499  lea     rax, [rsp+170h+var_140]
0x14002c49e  mov     r8d, 2; KeyValueInformationClass
0x14002c4a4  mov     [rsp+170h+ResultLength], rax; ResultLength
0x14002c4a9  lea     r9, [rsp+170h+KeyValueInformation]; KeyValueInformation
0x14002c4ae  lea     rdx, [rsp+170h+DestinationString]; ValueName
0x14002c4b3  mov     [rsp+170h+Length], 110h; Length
0x14002c4bb  mov     rcx, rbx; KeyHandle
0x14002c4be  call    cs:__imp_ZwQueryValueKey
0x14002c4c5  nop     dword ptr [rax+rax+00h]
0x14002c4ca  test    eax, eax
0x14002c4cc  js      short loc_14002C4EA
0x14002c4ce  cmp     [rsp+170h+var_11C], 4
0x14002c4d3  jnz     short loc_14002C4F1
0x14002c4d5  cmp     [rsp+170h+var_140], 4
0x14002c4da  jb      short loc_14002C4F1
0x14002c4dc  cmp     [rsp+170h+var_114], 0
0x14002c4e1  setnz   cs:ClassDisableForwardedIo
0x14002c4e8  jmp     short loc_14002C4F1
0x14002c4ea  mov     cs:ClassDisableForwardedIo, 0
0x14002c4f1  mov     rcx, [rbp+70h+var_10]
0x14002c4f5  xor     rcx, rsp; StackCookie
0x14002c4f8  call    __security_check_cookie
0x14002c4fd  mov     rbx, [rsp+170h+arg_8]
0x14002c505  add     rsp, 170h
0x14002c50c  pop     rbp
0x14002c50d  retn
```
