# MRxSmbRemoveDeprecatedRegistryParameters

- ea: `0x1400929c0`
- end: `0x140092aaa`
- name: `MRxSmbRemoveDeprecatedRegistryParameters`
- size: `234`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140028fec`

## callees

- `0x140039770`
- `0x140059dc0`
- `0x1400929c0`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x140092a84`
- `ntoskrnl!ZwDeleteValueKey` at `0x140092a84`
- `ntoskrnl!ZwQueryValueKey` at `0x140092a33`
- `ntoskrnl!ZwQueryValueKey` at `0x140092a33`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092a02`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092a70`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092a02`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092a70`

## pseudocode

```c
NTSTATUS __fastcall MRxSmbRemoveDeprecatedRegistryParameters(HANDLE KeyHandle)
{
  NTSTATUS result; // eax
  __int64 v3; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-88h] BYREF
  UNICODE_STRING DestinationString; // [rsp+38h] [rbp-80h] BYREF
  UNICODE_STRING ValueName; // [rsp+48h] [rbp-70h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+60h] [rbp-58h] BYREF
  int v8; // [rsp+64h] [rbp-54h]

  ResultLength = 0;
  ValueName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RequireSecureNegotiate");
  result = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x40u,
             &ResultLength);
  if ( result >= 0 && v8 == 4 )
  {
    RtlInitUnicodeString(&ValueName, L"RequireSecureNegotiate");
    result = ZwDeleteValueKey(KeyHandle, &ValueName);
    if ( (byte_1400712C3 & 4) != 0 )
      return McTemplateK0_EtwWriteTransfer(v3, &RequireSecureNegotiateIsDeprecated, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400929c0  push    rbx
0x1400929c2  sub     rsp, 0B0h
0x1400929c9  mov     rax, cs:__security_cookie
0x1400929d0  xor     rax, rsp
0x1400929d3  mov     [rsp+0B8h+var_18], rax
0x1400929db  mov     rbx, rcx
0x1400929de  mov     [rsp+0B8h+var_88], 0
0x1400929e6  xorps   xmm0, xmm0
0x1400929e9  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1400929ee  xorps   xmm1, xmm1
0x1400929f1  lea     rdx, aRequiresecuren; "RequireSecureNegotiate"
0x1400929f8  movups  xmmword ptr [rsp+0B8h+ValueName.Length], xmm0
0x1400929fd  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm1
0x140092a02  call    cs:__imp_RtlInitUnicodeString
0x140092a09  nop     dword ptr [rax+rax+00h]
0x140092a0e  lea     rax, [rsp+0B8h+var_88]
0x140092a13  mov     r8d, 2; KeyValueInformationClass
0x140092a19  mov     [rsp+0B8h+ResultLength], rax; ResultLength
0x140092a1e  lea     r9, [rsp+0B8h+KeyValueInformation]; KeyValueInformation
0x140092a23  lea     rdx, [rsp+0B8h+DestinationString]; ValueName
0x140092a28  mov     [rsp+0B8h+Length], 40h ; '@'; Length
0x140092a30  mov     rcx, rbx; KeyHandle
0x140092a33  call    cs:__imp_ZwQueryValueKey
0x140092a3a  nop     dword ptr [rax+rax+00h]
0x140092a3f  test    eax, eax
0x140092a41  jns     short loc_140092A5D
0x140092a43  mov     rcx, [rsp+0B8h+var_18]
0x140092a4b  xor     rcx, rsp; StackCookie
0x140092a4e  call    __security_check_cookie
0x140092a53  add     rsp, 0B0h
0x140092a5a  pop     rbx
0x140092a5b  retn
0x140092a5d  cmp     [rsp+0B8h+var_54], 4
0x140092a62  jnz     short loc_140092A43
0x140092a64  lea     rdx, aRequiresecuren; "RequireSecureNegotiate"
0x140092a6b  lea     rcx, [rsp+0B8h+ValueName]; DestinationString
0x140092a70  call    cs:__imp_RtlInitUnicodeString
0x140092a77  nop     dword ptr [rax+rax+00h]
0x140092a7c  lea     rdx, [rsp+0B8h+ValueName]; ValueName
0x140092a81  mov     rcx, rbx; KeyHandle
0x140092a84  call    cs:__imp_ZwDeleteValueKey
0x140092a8b  nop     dword ptr [rax+rax+00h]
0x140092a90  test    cs:byte_1400712C3, 4
0x140092a97  jz      short loc_140092A43
0x140092a99  xor     r8d, r8d
0x140092a9c  lea     rdx, RequireSecureNegotiateIsDeprecated
0x140092aa3  call    McTemplateK0_EtwWriteTransfer
0x140092aa8  jmp     short loc_140092A43
```
