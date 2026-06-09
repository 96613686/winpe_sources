# HvSocketGetAzureFeatureSetEnabled

- ea: `0x14001d60c`
- end: `0x14001d722`
- name: `HvSocketGetAzureFeatureSetEnabled`
- size: `278`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006be0`

## callees

- `0x14000bfa0`
- `0x14001d60c`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14001d6c9`
- `ntoskrnl!ZwQueryValueKey` at `0x14001d6c9`
- `ntoskrnl!ZwClose` at `0x14001d6f6`
- `ntoskrnl!ZwClose` at `0x14001d6f6`
- `ntoskrnl!ZwOpenKey` at `0x14001d696`
- `ntoskrnl!ZwOpenKey` at `0x14001d696`

## string_xrefs

- `0x14001d62c`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Virtualization`

## pseudocode

```c
bool HvSocketGetAzureFeatureSetEnabled()
{
  bool v0; // bl
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v4[2]; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v8; // [rsp+94h] [rbp+3Bh]
  int v9; // [rsp+98h] [rbp+3Fh]
  int v10; // [rsp+9Ch] [rbp+43h]

  KeyHandle = 0;
  v4[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization";
  v4[0] = 10223770;
  ValueName.Buffer = L"AzureFeatureSet";
  *(_QWORD *)&ValueName.Length = 2097182;
  ObjectAttributes.RootDirectory = 0;
  ResultLength = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
  v0 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x10u, &ResultLength) >= 0
      && ResultLength == 16
      && v8 == 4
      && v9 == 4 )
    {
      v0 = v10 != 0;
    }
    ZwClose(KeyHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x14001d60c  mov     [rsp-8+arg_0], rbx
0x14001d611  push    rbp
0x14001d612  lea     rbp, [rsp-57h]
0x14001d617  sub     rsp, 0B0h
0x14001d61e  mov     rax, cs:__security_cookie
0x14001d625  xor     rax, rsp
0x14001d628  mov     [rbp+57h+var_10], rax
0x14001d62c  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x14001d633  mov     [rbp+57h+KeyHandle], 0
0x14001d63b  mov     [rbp+57h+var_68], rax
0x14001d63f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001d643  lea     rax, aAzurefeaturese; "AzureFeatureSet"
0x14001d64a  mov     [rbp+57h+var_70], 9C009Ah
0x14001d652  mov     [rbp+57h+ValueName.Buffer], rax
0x14001d656  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14001d65a  xor     eax, eax
0x14001d65c  mov     qword ptr [rbp+57h+ValueName.Length], 20001Eh
0x14001d664  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14001d668  xorps   xmm0, xmm0
0x14001d66b  lea     rax, [rbp+57h+var_70]
0x14001d66f  mov     [rbp+57h+var_80], 0
0x14001d676  mov     edx, 20019h; DesiredAccess
0x14001d67b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001d67f  xor     bl, bl
0x14001d681  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001d689  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001d691  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d696  call    cs:__imp_ZwOpenKey
0x14001d69d  nop     dword ptr [rax+rax+00h]
0x14001d6a2  test    eax, eax
0x14001d6a4  js      short loc_14001D702
0x14001d6a6  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14001d6aa  lea     rax, [rbp+57h+var_80]
0x14001d6ae  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x14001d6b3  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14001d6b7  mov     r8d, 2; KeyValueInformationClass
0x14001d6bd  mov     [rsp+0B0h+Length], 10h; Length
0x14001d6c5  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14001d6c9  call    cs:__imp_ZwQueryValueKey
0x14001d6d0  nop     dword ptr [rax+rax+00h]
0x14001d6d5  test    eax, eax
0x14001d6d7  js      short loc_14001D6F2
0x14001d6d9  cmp     [rbp+57h+var_80], 10h
0x14001d6dd  jnz     short loc_14001D6F2
0x14001d6df  cmp     [rbp+57h+var_1C], 4
0x14001d6e3  jnz     short loc_14001D6F2
0x14001d6e5  cmp     [rbp+57h+var_18], 4
0x14001d6e9  jnz     short loc_14001D6F2
0x14001d6eb  cmp     [rbp+57h+var_14], 0
0x14001d6ef  setnz   bl
0x14001d6f2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14001d6f6  call    cs:__imp_ZwClose
0x14001d6fd  nop     dword ptr [rax+rax+00h]
0x14001d702  mov     al, bl
0x14001d704  mov     rcx, [rbp+57h+var_10]
0x14001d708  xor     rcx, rsp; StackCookie
0x14001d70b  call    __security_check_cookie
0x14001d710  mov     rbx, [rsp+0B0h+arg_0]
0x14001d718  add     rsp, 0B0h
0x14001d71f  pop     rbp
0x14001d720  retn
```
