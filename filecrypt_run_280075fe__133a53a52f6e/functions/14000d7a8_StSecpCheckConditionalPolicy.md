# StSecpCheckConditionalPolicy

- ea: `0x14000d7a8`
- end: `0x14000d99f`
- name: `StSecpCheckConditionalPolicy`
- size: `503`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1, PUNICODE_STRING ValueName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010890`

## callees

- `0x140003540`
- `0x14000d7a8`
- `0x14000dff8`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000d8b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d8b5`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d959`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d959`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d83a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d854`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d86e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d83a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d854`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d86e`
- `ntoskrnl!ZwOpenKey` at `0x14000d8f4`
- `ntoskrnl!ZwOpenKey` at `0x14000d8f4`
- `ntoskrnl!ZwClose` at `0x14000d928`
- `ntoskrnl!ZwClose` at `0x14000d928`

## string_xrefs

- `0x14000d8aa`: `\REGISTRY\MACHINE\Software\Microsoft\SecurityManager\StorageCardProfiles\Chambers`

## pseudocode

```c
__int64 __fastcall StSecpCheckConditionalPolicy(PCUNICODE_STRING String1, PUNICODE_STRING ValueName, bool *a3)
{
  int v6; // ebx
  NTSTATUS v7; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-69h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-61h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-59h] BYREF
  UNICODE_STRING v12; // [rsp+50h] [rbp-49h] BYREF
  UNICODE_STRING v13; // [rsp+60h] [rbp-39h] BYREF
  __int128 v14; // [rsp+70h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp+17h] BYREF
  __int128 KeyValueInformation; // [rsp+C0h] [rbp+27h] BYREF

  *(_QWORD *)&String2.Length = 2621478;
  *(_QWORD *)&v13.Length = 2359330;
  String2.Buffer = (PWSTR)L"<PackageFamilyName>";
  *(_QWORD *)&v12.Length = 1572886;
  v13.Buffer = (PWSTR)L"<PackageFullName>";
  v12.Buffer = (PWSTR)L"<ProductId>";
  KeyHandle = 0;
  ResultLength = 0;
  v14 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  if ( !RtlCompareUnicodeString(String1, &String2, 1u) || !RtlCompareUnicodeString(String1, &v12, 1u) )
  {
LABEL_6:
    if ( !g_DebugProfileKey )
    {
      RtlInitUnicodeString(
        &DestinationString,
        L"\\REGISTRY\\MACHINE\\Software\\Microsoft\\SecurityManager\\StorageCardProfiles\\Chambers");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
      v6 = v7;
      if ( v7 < 0 )
        goto LABEL_8;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_DebugProfileKey, (signed __int64)KeyHandle, 0) )
        ZwClose(KeyHandle);
    }
    v7 = ZwQueryValueKey(
           g_DebugProfileKey,
           ValueName,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &ResultLength);
    v6 = v7;
    if ( v7 >= 0 )
    {
      *a3 = HIDWORD(KeyValueInformation) != 0;
      goto LABEL_14;
    }
LABEL_8:
    if ( v7 == -1073741772 )
      goto LABEL_9;
    goto LABEL_14;
  }
  if ( RtlCompareUnicodeString(String1, &v13, 1u) )
  {
LABEL_9:
    v6 = 0;
    *a3 = 0;
    goto LABEL_14;
  }
  v6 = StSecpPackageFamilyNameFromFullName(ValueName, &v14);
  if ( v6 >= 0 )
  {
    ValueName = (PUNICODE_STRING)&v14;
    goto LABEL_6;
  }
LABEL_14:
  StSecFree(*((_QWORD *)&v14 + 1));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000d7a8  mov     [rsp-8+arg_18], rbx
0x14000d7ad  push    rbp
0x14000d7ae  push    rsi
0x14000d7af  push    rdi
0x14000d7b0  lea     rbp, [rsp-47h]
0x14000d7b5  sub     rsp, 0E0h
0x14000d7bc  mov     rax, cs:__security_cookie
0x14000d7c3  xor     rax, rsp
0x14000d7c6  mov     [rbp+57h+var_20], rax
0x14000d7ca  xorps   xmm0, xmm0
0x14000d7cd  mov     qword ptr [rbp+57h+String2.Length], 280026h
0x14000d7d5  lea     rax, aPackagefamilyn; "<PackageFamilyName>"
0x14000d7dc  mov     qword ptr [rbp+57h+var_90.Length], 240022h
0x14000d7e4  mov     [rbp+57h+String2.Buffer], rax
0x14000d7e8  mov     rdi, r8
0x14000d7eb  lea     rax, aPackagefullnam_0; "<PackageFullName>"
0x14000d7f2  mov     qword ptr [rbp+57h+var_A0.Length], 180016h
0x14000d7fa  mov     [rbp+57h+var_90.Buffer], rax
0x14000d7fe  mov     rsi, rdx
0x14000d801  lea     rax, aProductid; "<ProductId>"
0x14000d808  xorps   xmm1, xmm1
0x14000d80b  mov     [rbp+57h+var_A0.Buffer], rax
0x14000d80f  lea     rdx, [rbp+57h+String2]; String2
0x14000d813  xor     eax, eax
0x14000d815  mov     r8b, 1; CaseInSensitive
0x14000d818  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000d81c  mov     [rbp+57h+KeyHandle], rax
0x14000d820  mov     rbx, rcx
0x14000d823  mov     [rbp+57h+var_C0], eax
0x14000d826  movups  [rbp+57h+var_80], xmm0
0x14000d82a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14000d82e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000d832  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000d836  movups  [rbp+57h+KeyValueInformation], xmm0
0x14000d83a  call    cs:__imp_RtlCompareUnicodeString
0x14000d841  nop     dword ptr [rax+rax+00h]
0x14000d846  test    eax, eax
0x14000d848  jz      short loc_14000D89C
0x14000d84a  mov     r8b, 1; CaseInSensitive
0x14000d84d  lea     rdx, [rbp+57h+var_A0]; String2
0x14000d851  mov     rcx, rbx; String1
0x14000d854  call    cs:__imp_RtlCompareUnicodeString
0x14000d85b  nop     dword ptr [rax+rax+00h]
0x14000d860  test    eax, eax
0x14000d862  jz      short loc_14000D89C
0x14000d864  mov     r8b, 1; CaseInSensitive
0x14000d867  lea     rdx, [rbp+57h+var_90]; String2
0x14000d86b  mov     rcx, rbx; String1
0x14000d86e  call    cs:__imp_RtlCompareUnicodeString
0x14000d875  nop     dword ptr [rax+rax+00h]
0x14000d87a  test    eax, eax
0x14000d87c  jnz     loc_14000D90D
0x14000d882  lea     rdx, [rbp+57h+var_80]
0x14000d886  mov     rcx, rsi
0x14000d889  call    StSecpPackageFamilyNameFromFullName
0x14000d88e  mov     ebx, eax
0x14000d890  test    eax, eax
0x14000d892  js      loc_14000D974
0x14000d898  lea     rsi, [rbp+57h+var_80]
0x14000d89c  cmp     cs:g_DebugProfileKey, 0
0x14000d8a4  jnz     loc_14000D934
0x14000d8aa  lea     rdx, SourceString; "\\REGISTRY\\MACHINE\\Software\\Microsof"...
0x14000d8b1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000d8b5  call    cs:__imp_RtlInitUnicodeString
0x14000d8bc  nop     dword ptr [rax+rax+00h]
0x14000d8c1  lea     rax, [rbp+57h+DestinationString]
0x14000d8c5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000d8cc  xorps   xmm0, xmm0
0x14000d8cf  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000d8d3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000d8d7  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000d8df  mov     edx, 80000000h; DesiredAccess
0x14000d8e4  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000d8eb  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d8ef  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d8f4  call    cs:__imp_ZwOpenKey
0x14000d8fb  nop     dword ptr [rax+rax+00h]
0x14000d900  mov     ebx, eax
0x14000d902  test    eax, eax
0x14000d904  jns     short loc_14000D913
0x14000d906  cmp     eax, 0C0000034h
0x14000d90b  jnz     short loc_14000D974
0x14000d90d  xor     ebx, ebx
0x14000d90f  mov     [rdi], bl
0x14000d911  jmp     short loc_14000D974
0x14000d913  mov     rcx, [rbp+57h+KeyHandle]
0x14000d917  xor     eax, eax
0x14000d919  lock cmpxchg cs:g_DebugProfileKey, rcx
0x14000d922  jz      short loc_14000D934
0x14000d924  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000d928  call    cs:__imp_ZwClose
0x14000d92f  nop     dword ptr [rax+rax+00h]
0x14000d934  mov     rcx, cs:g_DebugProfileKey; KeyHandle
0x14000d93b  lea     rax, [rbp+57h+var_C0]
0x14000d93f  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000d944  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000d948  mov     r8d, 2; KeyValueInformationClass
0x14000d94e  mov     [rsp+0F0h+Length], 10h; Length
0x14000d956  mov     rdx, rsi; ValueName
0x14000d959  call    cs:__imp_ZwQueryValueKey
0x14000d960  nop     dword ptr [rax+rax+00h]
0x14000d965  mov     ebx, eax
0x14000d967  test    eax, eax
0x14000d969  js      short loc_14000D906
0x14000d96b  cmp     dword ptr [rbp+57h+KeyValueInformation+0Ch], 0
0x14000d96f  setnz   al
0x14000d972  mov     [rdi], al
0x14000d974  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x14000d978  call    StSecFree
0x14000d97d  mov     eax, ebx
0x14000d97f  mov     rcx, [rbp+57h+var_20]
0x14000d983  xor     rcx, rsp; StackCookie
0x14000d986  call    __security_check_cookie
0x14000d98b  mov     rbx, [rsp+0F0h+arg_18]
0x14000d993  add     rsp, 0E0h
0x14000d99a  pop     rdi
0x14000d99b  pop     rsi
0x14000d99c  pop     rbp
0x14000d99d  retn
```
