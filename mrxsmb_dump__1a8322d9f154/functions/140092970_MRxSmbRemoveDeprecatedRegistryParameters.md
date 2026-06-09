# MRxSmbRemoveDeprecatedRegistryParameters

- ea: `0x140092970`
- end: `0x140092a5a`
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
- `0x140092970`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x140092a34`
- `ntoskrnl!ZwDeleteValueKey` at `0x140092a34`
- `ntoskrnl!ZwQueryValueKey` at `0x1400929e3`
- `ntoskrnl!ZwQueryValueKey` at `0x1400929e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400929b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092a20`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400929b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092a20`

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
    if ( (byte_1400712A3 & 4) != 0 )
      return McTemplateK0_EtwWriteTransfer(v3, RequireSecureNegotiateIsDeprecated, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140092970  push    rbx
0x140092972  sub     rsp, 0B0h
0x140092979  mov     rax, cs:__security_cookie
0x140092980  xor     rax, rsp
0x140092983  mov     [rsp+0B8h+var_18], rax
0x14009298b  mov     rbx, rcx
0x14009298e  mov     [rsp+0B8h+var_88], 0
0x140092996  xorps   xmm0, xmm0
0x140092999  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14009299e  xorps   xmm1, xmm1
0x1400929a1  lea     rdx, aRequiresecuren; "RequireSecureNegotiate"
0x1400929a8  movups  xmmword ptr [rsp+0B8h+ValueName.Length], xmm0
0x1400929ad  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm1
0x1400929b2  call    cs:__imp_RtlInitUnicodeString
0x1400929b9  nop     dword ptr [rax+rax+00h]
0x1400929be  lea     rax, [rsp+0B8h+var_88]
0x1400929c3  mov     r8d, 2; KeyValueInformationClass
0x1400929c9  mov     [rsp+0B8h+ResultLength], rax; ResultLength
0x1400929ce  lea     r9, [rsp+0B8h+KeyValueInformation]; KeyValueInformation
0x1400929d3  lea     rdx, [rsp+0B8h+DestinationString]; ValueName
0x1400929d8  mov     [rsp+0B8h+Length], 40h ; '@'; Length
0x1400929e0  mov     rcx, rbx; KeyHandle
0x1400929e3  call    cs:__imp_ZwQueryValueKey
0x1400929ea  nop     dword ptr [rax+rax+00h]
0x1400929ef  test    eax, eax
0x1400929f1  jns     short loc_140092A0D
0x1400929f3  mov     rcx, [rsp+0B8h+var_18]
0x1400929fb  xor     rcx, rsp; StackCookie
0x1400929fe  call    __security_check_cookie
0x140092a03  add     rsp, 0B0h
0x140092a0a  pop     rbx
0x140092a0b  retn
0x140092a0d  cmp     [rsp+0B8h+var_54], 4
0x140092a12  jnz     short loc_1400929F3
0x140092a14  lea     rdx, aRequiresecuren; "RequireSecureNegotiate"
0x140092a1b  lea     rcx, [rsp+0B8h+ValueName]; DestinationString
0x140092a20  call    cs:__imp_RtlInitUnicodeString
0x140092a27  nop     dword ptr [rax+rax+00h]
0x140092a2c  lea     rdx, [rsp+0B8h+ValueName]; ValueName
0x140092a31  mov     rcx, rbx; KeyHandle
0x140092a34  call    cs:__imp_ZwDeleteValueKey
0x140092a3b  nop     dword ptr [rax+rax+00h]
0x140092a40  test    cs:byte_1400712A3, 4
0x140092a47  jz      short loc_1400929F3
0x140092a49  xor     r8d, r8d
0x140092a4c  lea     rdx, RequireSecureNegotiateIsDeprecated
0x140092a53  call    McTemplateK0_EtwWriteTransfer
0x140092a58  jmp     short loc_1400929F3
```
