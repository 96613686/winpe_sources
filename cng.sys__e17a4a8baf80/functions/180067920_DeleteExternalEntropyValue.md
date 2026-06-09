# DeleteExternalEntropyValue

- ea: `0x180067920`
- end: `0x180067a76`
- name: `DeleteExternalEntropyValue`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180067a7c`

## callees

- `0x18001155c`
- `0x180060d80`
- `0x180067920`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006797c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800679ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006797c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800679ae`
- `ntoskrnl!ZwQueryValueKey` at `0x1800679dd`
- `ntoskrnl!ZwQueryValueKey` at `0x1800679dd`
- `ntoskrnl!ZwSetValueKey` at `0x180067a23`
- `ntoskrnl!ZwSetValueKey` at `0x180067a23`
- `ntoskrnl!ZwClose` at `0x180067a57`
- `ntoskrnl!ZwClose` at `0x180067a57`
- `ntoskrnl!ZwDeleteValueKey` at `0x180067990`
- `ntoskrnl!ZwDeleteValueKey` at `0x180067990`

## string_xrefs

- `0x180067959`: `\Registry\Machine\SYSTEM\RNG`
- `0x180067a39`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\krng.cxx`

## pseudocode

```c
int DeleteExternalEntropyValue()
{
  int result; // eax
  int v1; // eax
  int Data; // [rsp+30h] [rbp-40h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-28h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+58h] [rbp-18h] BYREF
  int v7; // [rsp+5Ch] [rbp-14h]
  int v8; // [rsp+60h] [rbp-10h]
  int v9; // [rsp+64h] [rbp-Ch]

  KeyHandle = 0;
  ResultLength = 0;
  Data = 0;
  DestinationString = 0;
  result = AccessRegistryKey(L"\\Registry\\Machine\\SYSTEM\\RNG", 2u, &KeyHandle);
  if ( result )
  {
    RtlInitUnicodeString(&DestinationString, L"ExternalEntropy");
    ZwDeleteValueKey(KeyHandle, &DestinationString);
    Data = 0;
    RtlInitUnicodeString(&DestinationString, L"ExternalEntropyCount");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x10u,
           &ResultLength) < 0
      || v7 != 4
      || (v1 = v9, v8 != 4) )
    {
      v1 = Data;
    }
    Data = v1 + 1;
    result = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
    if ( result < 0 )
      result = DebugTraceError(
                 (unsigned int)result,
                 "Status",
                 "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\krng.cxx",
                 375);
  }
  if ( KeyHandle )
    return ZwClose(KeyHandle);
  return result;
}

```

## disassembly

```asm
0x180067920  push    rbp
0x180067922  mov     rbp, rsp
0x180067925  sub     rsp, 70h
0x180067929  mov     rax, cs:__security_cookie
0x180067930  xor     rax, rsp
0x180067933  mov     [rbp+var_8], rax
0x180067937  xorps   xmm0, xmm0
0x18006793a  mov     [rbp+KeyHandle], 0
0x180067942  lea     r8, [rbp+KeyHandle]; KeyHandle
0x180067946  mov     [rbp+var_30], 0
0x18006794d  mov     edx, 2; DesiredAccess
0x180067952  mov     [rbp+Data], 0
0x180067959  lea     rcx, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\RNG"
0x180067960  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180067964  call    AccessRegistryKey
0x180067969  test    eax, eax
0x18006796b  jz      loc_180067A4E
0x180067971  lea     rdx, aExternalentrop_0; "ExternalEntropy"
0x180067978  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006797c  call    cs:__imp_RtlInitUnicodeString
0x180067983  nop     dword ptr [rax+rax+00h]
0x180067988  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006798c  lea     rdx, [rbp+DestinationString]; ValueName
0x180067990  call    cs:__imp_ZwDeleteValueKey
0x180067997  nop     dword ptr [rax+rax+00h]
0x18006799c  lea     rdx, aExternalentrop; "ExternalEntropyCount"
0x1800679a3  mov     [rbp+Data], 0
0x1800679aa  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800679ae  call    cs:__imp_RtlInitUnicodeString
0x1800679b5  nop     dword ptr [rax+rax+00h]
0x1800679ba  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800679be  lea     rax, [rbp+var_30]
0x1800679c2  mov     [rsp+70h+ResultLength], rax; ResultLength
0x1800679c7  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x1800679cb  mov     r8d, 2; KeyValueInformationClass
0x1800679d1  mov     [rsp+70h+Length], 10h; Length
0x1800679d9  lea     rdx, [rbp+DestinationString]; ValueName
0x1800679dd  call    cs:__imp_ZwQueryValueKey
0x1800679e4  nop     dword ptr [rax+rax+00h]
0x1800679e9  mov     r9d, 4; Type
0x1800679ef  test    eax, eax
0x1800679f1  js      short loc_180067A02
0x1800679f3  cmp     [rbp+var_14], r9d
0x1800679f7  jnz     short loc_180067A02
0x1800679f9  mov     eax, [rbp+var_C]
0x1800679fc  cmp     [rbp+var_10], r9d
0x180067a00  jz      short loc_180067A05
0x180067a02  mov     eax, [rbp+Data]
0x180067a05  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180067a09  lea     rdx, [rbp+DestinationString]; ValueName
0x180067a0d  inc     eax
0x180067a0f  mov     dword ptr [rsp+70h+ResultLength], r9d; DataSize
0x180067a14  mov     [rbp+Data], eax
0x180067a17  xor     r8d, r8d; TitleIndex
0x180067a1a  lea     rax, [rbp+Data]
0x180067a1e  mov     qword ptr [rsp+70h+Length], rax; Data
0x180067a23  call    cs:__imp_ZwSetValueKey
0x180067a2a  nop     dword ptr [rax+rax+00h]
0x180067a2f  test    eax, eax
0x180067a31  jns     short loc_180067A4E
0x180067a33  mov     r9d, 177h
0x180067a39  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067a40  lea     rdx, aStatus; "Status"
0x180067a47  mov     ecx, eax
0x180067a49  call    DebugTraceError
0x180067a4e  mov     rcx, [rbp+KeyHandle]; Handle
0x180067a52  test    rcx, rcx
0x180067a55  jz      short loc_180067A63
0x180067a57  call    cs:__imp_ZwClose
0x180067a5e  nop     dword ptr [rax+rax+00h]
0x180067a63  mov     rcx, [rbp+var_8]
0x180067a67  xor     rcx, rsp; StackCookie
0x180067a6a  call    __security_check_cookie
0x180067a6f  add     rsp, 70h
0x180067a73  pop     rbp
0x180067a74  retn
```
