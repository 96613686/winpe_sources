# DeleteExternalEntropyValue

- ea: `0x18005e040`
- end: `0x18005e196`
- name: `DeleteExternalEntropyValue`
- size: `342`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e19c`

## callees

- `0x18000743c`
- `0x1800574a0`
- `0x18005e040`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005e09c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005e0ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005e09c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005e0ce`
- `ntoskrnl!ZwQueryValueKey` at `0x18005e0fd`
- `ntoskrnl!ZwQueryValueKey` at `0x18005e0fd`
- `ntoskrnl!ZwSetValueKey` at `0x18005e143`
- `ntoskrnl!ZwSetValueKey` at `0x18005e143`
- `ntoskrnl!ZwClose` at `0x18005e177`
- `ntoskrnl!ZwClose` at `0x18005e177`
- `ntoskrnl!ZwDeleteValueKey` at `0x18005e0b0`
- `ntoskrnl!ZwDeleteValueKey` at `0x18005e0b0`

## string_xrefs

- `0x18005e079`: `\Registry\Machine\SYSTEM\RNG`
- `0x18005e159`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\krng.cxx`

## pseudocode

```c
NTSTATUS DeleteExternalEntropyValue()
{
  NTSTATUS result; // eax
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
0x18005e040  push    rbp
0x18005e042  mov     rbp, rsp
0x18005e045  sub     rsp, 70h
0x18005e049  mov     rax, cs:__security_cookie
0x18005e050  xor     rax, rsp
0x18005e053  mov     [rbp+var_8], rax
0x18005e057  xorps   xmm0, xmm0
0x18005e05a  mov     [rbp+KeyHandle], 0
0x18005e062  lea     r8, [rbp+KeyHandle]; KeyHandle
0x18005e066  mov     [rbp+var_30], 0
0x18005e06d  mov     edx, 2; DesiredAccess
0x18005e072  mov     [rbp+Data], 0
0x18005e079  lea     rcx, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\RNG"
0x18005e080  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005e084  call    AccessRegistryKey
0x18005e089  test    eax, eax
0x18005e08b  jz      loc_18005E16E
0x18005e091  lea     rdx, aExternalentrop_0; "ExternalEntropy"
0x18005e098  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005e09c  call    cs:__imp_RtlInitUnicodeString
0x18005e0a3  nop     dword ptr [rax+rax+00h]
0x18005e0a8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005e0ac  lea     rdx, [rbp+DestinationString]; ValueName
0x18005e0b0  call    cs:__imp_ZwDeleteValueKey
0x18005e0b7  nop     dword ptr [rax+rax+00h]
0x18005e0bc  lea     rdx, aExternalentrop; "ExternalEntropyCount"
0x18005e0c3  mov     [rbp+Data], 0
0x18005e0ca  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005e0ce  call    cs:__imp_RtlInitUnicodeString
0x18005e0d5  nop     dword ptr [rax+rax+00h]
0x18005e0da  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005e0de  lea     rax, [rbp+var_30]
0x18005e0e2  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18005e0e7  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x18005e0eb  mov     r8d, 2; KeyValueInformationClass
0x18005e0f1  mov     [rsp+70h+Length], 10h; Length
0x18005e0f9  lea     rdx, [rbp+DestinationString]; ValueName
0x18005e0fd  call    cs:__imp_ZwQueryValueKey
0x18005e104  nop     dword ptr [rax+rax+00h]
0x18005e109  mov     r9d, 4; Type
0x18005e10f  test    eax, eax
0x18005e111  js      short loc_18005E122
0x18005e113  cmp     [rbp+var_14], r9d
0x18005e117  jnz     short loc_18005E122
0x18005e119  mov     eax, [rbp+var_C]
0x18005e11c  cmp     [rbp+var_10], r9d
0x18005e120  jz      short loc_18005E125
0x18005e122  mov     eax, [rbp+Data]
0x18005e125  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005e129  lea     rdx, [rbp+DestinationString]; ValueName
0x18005e12d  inc     eax
0x18005e12f  mov     dword ptr [rsp+70h+ResultLength], r9d; DataSize
0x18005e134  mov     [rbp+Data], eax
0x18005e137  xor     r8d, r8d; TitleIndex
0x18005e13a  lea     rax, [rbp+Data]
0x18005e13e  mov     qword ptr [rsp+70h+Length], rax; Data
0x18005e143  call    cs:__imp_ZwSetValueKey
0x18005e14a  nop     dword ptr [rax+rax+00h]
0x18005e14f  test    eax, eax
0x18005e151  jns     short loc_18005E16E
0x18005e153  mov     r9d, 177h
0x18005e159  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005e160  lea     rdx, aStatus; "Status"
0x18005e167  mov     ecx, eax
0x18005e169  call    DebugTraceError
0x18005e16e  mov     rcx, [rbp+KeyHandle]; Handle
0x18005e172  test    rcx, rcx
0x18005e175  jz      short loc_18005E183
0x18005e177  call    cs:__imp_ZwClose
0x18005e17e  nop     dword ptr [rax+rax+00h]
0x18005e183  mov     rcx, [rbp+var_8]
0x18005e187  xor     rcx, rsp; StackCookie
0x18005e18a  call    __security_check_cookie
0x18005e18f  add     rsp, 70h
0x18005e193  pop     rbp
0x18005e194  retn
```
