# DeleteExternalEntropyValue

- ea: `0x18005d750`
- end: `0x18005d8a6`
- name: `DeleteExternalEntropyValue`
- size: `342`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d8ac`

## callees

- `0x18000743c`
- `0x180056bb0`
- `0x18005d750`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005d7ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005d7de`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005d7ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005d7de`
- `ntoskrnl!ZwQueryValueKey` at `0x18005d80d`
- `ntoskrnl!ZwQueryValueKey` at `0x18005d80d`
- `ntoskrnl!ZwSetValueKey` at `0x18005d853`
- `ntoskrnl!ZwSetValueKey` at `0x18005d853`
- `ntoskrnl!ZwClose` at `0x18005d887`
- `ntoskrnl!ZwClose` at `0x18005d887`
- `ntoskrnl!ZwDeleteValueKey` at `0x18005d7c0`
- `ntoskrnl!ZwDeleteValueKey` at `0x18005d7c0`

## string_xrefs

- `0x18005d789`: `\Registry\Machine\SYSTEM\RNG`
- `0x18005d869`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\krng.cxx`

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
0x18005d750  push    rbp
0x18005d752  mov     rbp, rsp
0x18005d755  sub     rsp, 70h
0x18005d759  mov     rax, cs:__security_cookie
0x18005d760  xor     rax, rsp
0x18005d763  mov     [rbp+var_8], rax
0x18005d767  xorps   xmm0, xmm0
0x18005d76a  mov     [rbp+KeyHandle], 0
0x18005d772  lea     r8, [rbp+KeyHandle]; KeyHandle
0x18005d776  mov     [rbp+var_30], 0
0x18005d77d  mov     edx, 2; DesiredAccess
0x18005d782  mov     [rbp+Data], 0
0x18005d789  lea     rcx, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\RNG"
0x18005d790  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005d794  call    AccessRegistryKey
0x18005d799  test    eax, eax
0x18005d79b  jz      loc_18005D87E
0x18005d7a1  lea     rdx, aExternalentrop_0; "ExternalEntropy"
0x18005d7a8  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005d7ac  call    cs:__imp_RtlInitUnicodeString
0x18005d7b3  nop     dword ptr [rax+rax+00h]
0x18005d7b8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005d7bc  lea     rdx, [rbp+DestinationString]; ValueName
0x18005d7c0  call    cs:__imp_ZwDeleteValueKey
0x18005d7c7  nop     dword ptr [rax+rax+00h]
0x18005d7cc  lea     rdx, aExternalentrop; "ExternalEntropyCount"
0x18005d7d3  mov     [rbp+Data], 0
0x18005d7da  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005d7de  call    cs:__imp_RtlInitUnicodeString
0x18005d7e5  nop     dword ptr [rax+rax+00h]
0x18005d7ea  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005d7ee  lea     rax, [rbp+var_30]
0x18005d7f2  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18005d7f7  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x18005d7fb  mov     r8d, 2; KeyValueInformationClass
0x18005d801  mov     [rsp+70h+Length], 10h; Length
0x18005d809  lea     rdx, [rbp+DestinationString]; ValueName
0x18005d80d  call    cs:__imp_ZwQueryValueKey
0x18005d814  nop     dword ptr [rax+rax+00h]
0x18005d819  mov     r9d, 4; Type
0x18005d81f  test    eax, eax
0x18005d821  js      short loc_18005D832
0x18005d823  cmp     [rbp+var_14], r9d
0x18005d827  jnz     short loc_18005D832
0x18005d829  mov     eax, [rbp+var_C]
0x18005d82c  cmp     [rbp+var_10], r9d
0x18005d830  jz      short loc_18005D835
0x18005d832  mov     eax, [rbp+Data]
0x18005d835  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005d839  lea     rdx, [rbp+DestinationString]; ValueName
0x18005d83d  inc     eax
0x18005d83f  mov     dword ptr [rsp+70h+ResultLength], r9d; DataSize
0x18005d844  mov     [rbp+Data], eax
0x18005d847  xor     r8d, r8d; TitleIndex
0x18005d84a  lea     rax, [rbp+Data]
0x18005d84e  mov     qword ptr [rsp+70h+Length], rax; Data
0x18005d853  call    cs:__imp_ZwSetValueKey
0x18005d85a  nop     dword ptr [rax+rax+00h]
0x18005d85f  test    eax, eax
0x18005d861  jns     short loc_18005D87E
0x18005d863  mov     r9d, 177h
0x18005d869  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d870  lea     rdx, aStatus; "Status"
0x18005d877  mov     ecx, eax
0x18005d879  call    DebugTraceError
0x18005d87e  mov     rcx, [rbp+KeyHandle]; Handle
0x18005d882  test    rcx, rcx
0x18005d885  jz      short loc_18005D893
0x18005d887  call    cs:__imp_ZwClose
0x18005d88e  nop     dword ptr [rax+rax+00h]
0x18005d893  mov     rcx, [rbp+var_8]
0x18005d897  xor     rcx, rsp; StackCookie
0x18005d89a  call    __security_check_cookie
0x18005d89f  add     rsp, 70h
0x18005d8a3  pop     rbp
0x18005d8a4  retn
```
